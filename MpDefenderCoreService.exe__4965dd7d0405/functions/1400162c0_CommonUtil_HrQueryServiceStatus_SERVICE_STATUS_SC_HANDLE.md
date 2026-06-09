# CommonUtil::HrQueryServiceStatus(_SERVICE_STATUS *,SC_HANDLE__ *)

- ea: `0x1400162c0`
- end: `0x1400163b2`
- name: `?HrQueryServiceStatus@CommonUtil@@YAJPEAU_SERVICE_STATUS@@PEAUSC_HANDLE__@@@Z`
- size: `242`
- prototype: `__int64 __fastcall(LPSERVICE_STATUS lpServiceStatus, SC_HANDLE hService, struct SC_HANDLE__ *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400166d4`
- `0x1400f5998`
- `0x1400f60dc`

## callees

- `0x1400162c0`
- `0x140017738`
- `0x14003a5c0`
- `0x140085d94`
- `0x140166990`

## import_xrefs

- `ADVAPI32!QueryServiceStatus` at `0x1400162e8`
- `ADVAPI32!QueryServiceStatus` at `0x1400162e8`
- `ADVAPI32!QueryServiceConfigW` at `0x140016349`
- `ADVAPI32!QueryServiceConfigW` at `0x140016349`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrQueryServiceStatus(
        LPSERVICE_STATUS lpServiceStatus,
        SC_HANDLE hService,
        struct SC_HANDLE__ *a3)
{
  unsigned int LastFailure; // ebx
  const wchar_t *v5; // r9
  struct _QUERY_SERVICE_CONFIGW ServiceConfig[8]; // [rsp+30h] [rbp-218h] BYREF
  DWORD pcbBytesNeeded; // [rsp+230h] [rbp-18h] BYREF

  if ( QueryServiceStatus(hService, lpServiceStatus) )
    return 0;
  LastFailure = HrGetLastFailure();
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    memset(ServiceConfig, 0, sizeof(ServiceConfig));
    pcbBytesNeeded = 0;
    if ( QueryServiceConfigW(hService, ServiceConfig, 0x200u, &pcbBytesNeeded) )
    {
      LODWORD(v5) = ServiceConfig[0].lpDisplayName;
    }
    else
    {
      HrGetLastFailure();
      v5 = L"<unknown>";
      ServiceConfig[0].lpDisplayName = (LPWSTR)L"<unknown>";
    }
    WPP_SF_Sd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      14,
      (unsigned int)WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids,
      (_DWORD)v5,
      LastFailure);
  }
  return LastFailure;
}

```

## disassembly

```asm
0x1400162c0  mov     [rsp+arg_10], rbx
0x1400162c5  push    rdi
0x1400162c6  sub     rsp, 240h
0x1400162cd  mov     rax, cs:__security_cookie
0x1400162d4  xor     rax, rsp
0x1400162d7  mov     [rsp+248h+var_10], rax
0x1400162df  mov     rdi, rdx
0x1400162e2  mov     rdx, rcx; lpServiceStatus
0x1400162e5  mov     rcx, rdi; hService
0x1400162e8  call    cs:__imp_QueryServiceStatus
0x1400162ee  test    eax, eax
0x1400162f0  jnz     loc_14001638F
0x1400162f6  call    HrGetLastFailure
0x1400162fb  mov     ebx, eax
0x1400162fd  mov     rax, cs:WPP_GLOBAL_Control
0x140016304  lea     rcx, WPP_GLOBAL_Control
0x14001630b  cmp     rax, rcx
0x14001630e  jz      short loc_14001638B
0x140016310  test    byte ptr [rax+1Ch], 1
0x140016314  jz      short loc_14001638B
0x140016316  xor     edx, edx; Val
0x140016318  lea     rcx, [rsp+248h+ServiceConfig]; void *
0x14001631d  mov     r8d, 200h; Size
0x140016323  call    memset
0x140016328  lea     r9, [rsp+248h+pcbBytesNeeded]; pcbBytesNeeded
0x140016330  mov     [rsp+248h+pcbBytesNeeded], 0
0x14001633b  mov     r8d, 200h; cbBufSize
0x140016341  lea     rdx, [rsp+248h+ServiceConfig]; lpServiceConfig
0x140016346  mov     rcx, rdi; hService
0x140016349  call    cs:__imp_QueryServiceConfigW
0x14001634f  test    eax, eax
0x140016351  jnz     short loc_140016366
0x140016353  call    HrGetLastFailure
0x140016358  lea     r9, aUnknown_1; "<unknown>"
0x14001635f  mov     [rsp+248h+ServiceConfig.lpDisplayName], r9
0x140016364  jmp     short loc_14001636B
0x140016366  mov     r9, [rsp+248h+ServiceConfig.lpDisplayName]
0x14001636b  mov     rcx, cs:WPP_GLOBAL_Control
0x140016372  lea     r8, WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids
0x140016379  mov     edx, 0Eh
0x14001637e  mov     [rsp+248h+var_228], ebx
0x140016382  mov     rcx, [rcx+10h]
0x140016386  call    WPP_SF_Sd
0x14001638b  mov     eax, ebx
0x14001638d  jmp     short loc_140016391
0x14001638f  xor     eax, eax
0x140016391  mov     rcx, [rsp+248h+var_10]
0x140016399  xor     rcx, rsp; StackCookie
0x14001639c  call    __security_check_cookie
0x1400163a1  mov     rbx, [rsp+248h+arg_10]
0x1400163a9  add     rsp, 240h
0x1400163b0  pop     rdi
0x1400163b1  retn
```
