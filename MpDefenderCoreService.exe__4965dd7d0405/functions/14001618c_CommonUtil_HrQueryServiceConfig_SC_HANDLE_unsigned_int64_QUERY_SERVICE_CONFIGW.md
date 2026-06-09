# CommonUtil::HrQueryServiceConfig(SC_HANDLE__ *,unsigned __int64 *,_QUERY_SERVICE_CONFIGW *)

- ea: `0x14001618c`
- end: `0x1400162c0`
- name: `?HrQueryServiceConfig@CommonUtil@@YAJPEAUSC_HANDLE__@@PEA_KPEAU_QUERY_SERVICE_CONFIGW@@@Z`
- size: `308`
- prototype: `__int64 __fastcall(SC_HANDLE hService, struct SC_HANDLE__ *, unsigned __int64 *, struct _QUERY_SERVICE_CONFIGW *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140016e4c`

## callees

- `0x14001618c`
- `0x140017738`
- `0x14003a5c0`
- `0x140085d94`
- `0x140166990`

## import_xrefs

- `ADVAPI32!QueryServiceConfigW` at `0x1400161cc`
- `ADVAPI32!QueryServiceConfigW` at `0x140016239`
- `ADVAPI32!QueryServiceConfigW` at `0x1400161cc`
- `ADVAPI32!QueryServiceConfigW` at `0x140016239`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrQueryServiceConfig(
        SC_HANDLE hService,
        struct SC_HANDLE__ *a2,
        struct _QUERY_SERVICE_CONFIGW *a3,
        struct _QUERY_SERVICE_CONFIGW *a4)
{
  DWORD v4; // edi
  unsigned int LastFailure; // ebx
  __int64 result; // rax
  const wchar_t *v9; // r9
  struct _QUERY_SERVICE_CONFIGW ServiceConfig[8]; // [rsp+30h] [rbp-228h] BYREF
  DWORD v11; // [rsp+230h] [rbp-28h] BYREF
  DWORD pcbBytesNeeded; // [rsp+234h] [rbp-24h] BYREF

  v4 = *(_DWORD *)a2;
  v11 = 0;
  if ( QueryServiceConfigW(hService, a3, v4, &v11) )
    return 0;
  LastFailure = HrGetLastFailure();
  result = 2147942522LL;
  if ( LastFailure == -2147024774 )
  {
    if ( v11 > v4 )
      *(_QWORD *)a2 = v11;
    else
      return 2147549183LL;
  }
  else
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    {
      memset(ServiceConfig, 0, sizeof(ServiceConfig));
      pcbBytesNeeded = 0;
      if ( QueryServiceConfigW(hService, ServiceConfig, 0x200u, &pcbBytesNeeded) )
      {
        LODWORD(v9) = ServiceConfig[0].lpDisplayName;
      }
      else
      {
        HrGetLastFailure();
        v9 = L"<unknown>";
        ServiceConfig[0].lpDisplayName = (LPWSTR)L"<unknown>";
      }
      WPP_SF_Sd(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        15,
        (unsigned int)WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids,
        (_DWORD)v9,
        LastFailure);
    }
    return LastFailure;
  }
  return result;
}

```

## disassembly

```asm
0x14001618c  mov     r11, rsp
0x14001618f  mov     [r11+20h], rbx
0x140016193  push    rbp
0x140016194  push    rsi
0x140016195  push    rdi
0x140016196  sub     rsp, 240h
0x14001619d  mov     rax, cs:__security_cookie
0x1400161a4  xor     rax, rsp
0x1400161a7  mov     [rsp+258h+var_20], rax
0x1400161af  mov     edi, [rdx]
0x1400161b1  lea     r9, [r11-28h]; pcbBytesNeeded
0x1400161b5  mov     rax, r8
0x1400161b8  mov     dword ptr [r11-28h], 0
0x1400161c0  mov     rsi, rdx
0x1400161c3  mov     r8d, edi; cbBufSize
0x1400161c6  mov     rdx, rax; lpServiceConfig
0x1400161c9  mov     rbp, rcx
0x1400161cc  call    cs:__imp_QueryServiceConfigW
0x1400161d2  test    eax, eax
0x1400161d4  jnz     loc_14001629B
0x1400161da  call    HrGetLastFailure
0x1400161df  mov     ebx, eax
0x1400161e1  mov     eax, 8007007Ah
0x1400161e6  cmp     ebx, eax
0x1400161e8  jz      loc_14001627F
0x1400161ee  mov     rax, cs:WPP_GLOBAL_Control
0x1400161f5  lea     rcx, WPP_GLOBAL_Control
0x1400161fc  cmp     rax, rcx
0x1400161ff  jz      short loc_14001627B
0x140016201  test    byte ptr [rax+1Ch], 1
0x140016205  jz      short loc_14001627B
0x140016207  mov     edi, 200h
0x14001620c  lea     rcx, [rsp+258h+ServiceConfig]; void *
0x140016211  mov     r8d, edi; Size
0x140016214  xor     edx, edx; Val
0x140016216  call    memset
0x14001621b  lea     r9, [rsp+258h+pcbBytesNeeded]; pcbBytesNeeded
0x140016223  mov     [rsp+258h+pcbBytesNeeded], 0
0x14001622e  mov     r8d, edi; cbBufSize
0x140016231  lea     rdx, [rsp+258h+ServiceConfig]; lpServiceConfig
0x140016236  mov     rcx, rbp; hService
0x140016239  call    cs:__imp_QueryServiceConfigW
0x14001623f  test    eax, eax
0x140016241  jnz     short loc_140016256
0x140016243  call    HrGetLastFailure
0x140016248  lea     r9, aUnknown_1; "<unknown>"
0x14001624f  mov     [rsp+258h+ServiceConfig.lpDisplayName], r9
0x140016254  jmp     short loc_14001625B
0x140016256  mov     r9, [rsp+258h+ServiceConfig.lpDisplayName]
0x14001625b  mov     rcx, cs:WPP_GLOBAL_Control
0x140016262  lea     r8, WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids
0x140016269  mov     edx, 0Fh
0x14001626e  mov     [rsp+258h+var_238], ebx
0x140016272  mov     rcx, [rcx+10h]
0x140016276  call    WPP_SF_Sd
0x14001627b  mov     eax, ebx
0x14001627d  jmp     short loc_14001629D
0x14001627f  cmp     [rsp+258h+var_28], edi
0x140016286  ja      short loc_14001628F
0x140016288  mov     eax, 8000FFFFh
0x14001628d  jmp     short loc_14001629D
0x14001628f  mov     ecx, [rsp+258h+var_28]
0x140016296  mov     [rsi], rcx
0x140016299  jmp     short loc_14001629D
0x14001629b  xor     eax, eax
0x14001629d  mov     rcx, [rsp+258h+var_20]
0x1400162a5  xor     rcx, rsp; StackCookie
0x1400162a8  call    __security_check_cookie
0x1400162ad  mov     rbx, [rsp+258h+arg_18]
0x1400162b5  add     rsp, 240h
0x1400162bc  pop     rdi
0x1400162bd  pop     rsi
0x1400162be  pop     rbp
0x1400162bf  retn
```
