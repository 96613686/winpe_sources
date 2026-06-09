# CommonUtil::HrStartService(SC_HANDLE__ *,unsigned __int64,wchar_t const * const *)

- ea: `0x1400163b4`
- end: `0x140016538`
- name: `?HrStartService@CommonUtil@@YAJPEAUSC_HANDLE__@@_KPEBQEB_W@Z`
- size: `388`
- prototype: `__int64 __fastcall(SC_HANDLE hService, struct SC_HANDLE__ *, unsigned __int64, const wchar_t *const *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140016f34`

## callees

- `0x1400163b4`
- `0x140017738`
- `0x14003a5c0`
- `0x140085d38`
- `0x140085d94`
- `0x140166990`

## import_xrefs

- `ADVAPI32!StartServiceW` at `0x1400163db`
- `ADVAPI32!StartServiceW` at `0x1400163db`
- `ADVAPI32!QueryServiceConfigW` at `0x14001644b`
- `ADVAPI32!QueryServiceConfigW` at `0x1400164de`
- `ADVAPI32!QueryServiceConfigW` at `0x14001644b`
- `ADVAPI32!QueryServiceConfigW` at `0x1400164de`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrStartService(
        SC_HANDLE hService,
        struct SC_HANDLE__ *a2,
        LPCWSTR *a3,
        const wchar_t *const *a4)
{
  unsigned int LastFailure; // ebx
  const wchar_t *v7; // r9
  LPWSTR lpDisplayName; // r9
  struct _QUERY_SERVICE_CONFIGW ServiceConfig[8]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD pcbBytesNeeded; // [rsp+230h] [rbp+130h] BYREF

  if ( StartServiceW(hService, (DWORD)a2, a3) )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    {
      memset(ServiceConfig, 0, sizeof(ServiceConfig));
      pcbBytesNeeded = 0;
      if ( QueryServiceConfigW(hService, ServiceConfig, 0x200u, &pcbBytesNeeded) )
      {
        lpDisplayName = ServiceConfig[0].lpDisplayName;
      }
      else
      {
        HrGetLastFailure();
        lpDisplayName = (LPWSTR)L"<unknown>";
        ServiceConfig[0].lpDisplayName = (LPWSTR)L"<unknown>";
      }
      WPP_SF_S(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        19,
        WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids,
        lpDisplayName);
    }
    return 0;
  }
  else
  {
    LastFailure = HrGetLastFailure();
    if ( LastFailure == -2147023840 )
    {
      return 1;
    }
    else
    {
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
      {
        memset(ServiceConfig, 0, sizeof(ServiceConfig));
        pcbBytesNeeded = 0;
        if ( QueryServiceConfigW(hService, ServiceConfig, 0x200u, &pcbBytesNeeded) )
        {
          LODWORD(v7) = ServiceConfig[0].lpDisplayName;
        }
        else
        {
          HrGetLastFailure();
          v7 = L"<unknown>";
          ServiceConfig[0].lpDisplayName = (LPWSTR)L"<unknown>";
        }
        WPP_SF_Sd(
          *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
          18,
          (unsigned int)WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids,
          (_DWORD)v7,
          LastFailure);
      }
      return LastFailure;
    }
  }
}

```

## disassembly

```asm
0x1400163b4  push    rbp
0x1400163b6  push    rbx
0x1400163b7  push    rsi
0x1400163b8  lea     rbp, [rsp-140h]
0x1400163c0  sub     rsp, 240h
0x1400163c7  mov     rax, cs:__security_cookie
0x1400163ce  xor     rax, rsp
0x1400163d1  mov     [rbp+150h+var_18], rax
0x1400163d8  mov     rsi, rcx
0x1400163db  call    cs:__imp_StartServiceW
0x1400163e1  test    eax, eax
0x1400163e3  jnz     loc_140016494
0x1400163e9  call    HrGetLastFailure
0x1400163ee  mov     ebx, eax
0x1400163f0  cmp     eax, 80070420h
0x1400163f5  jnz     short loc_140016401
0x1400163f7  mov     eax, 1
0x1400163fc  jmp     loc_14001651E
0x140016401  mov     rdx, cs:WPP_GLOBAL_Control
0x140016408  lea     rax, WPP_GLOBAL_Control
0x14001640f  cmp     rdx, rax
0x140016412  jz      short loc_14001648D
0x140016414  test    byte ptr [rdx+1Ch], 1
0x140016418  jz      short loc_14001648D
0x14001641a  xor     edx, edx; Val
0x14001641c  lea     rcx, [rsp+250h+ServiceConfig]; void *
0x140016421  mov     r8d, 200h; Size
0x140016427  call    memset
0x14001642c  lea     r9, [rbp+150h+pcbBytesNeeded]; pcbBytesNeeded
0x140016433  mov     [rbp+150h+pcbBytesNeeded], 0
0x14001643d  mov     r8d, 200h; cbBufSize
0x140016443  lea     rdx, [rsp+250h+ServiceConfig]; lpServiceConfig
0x140016448  mov     rcx, rsi; hService
0x14001644b  call    cs:__imp_QueryServiceConfigW
0x140016451  test    eax, eax
0x140016453  jnz     short loc_140016468
0x140016455  call    HrGetLastFailure
0x14001645a  lea     r9, aUnknown_1; "<unknown>"
0x140016461  mov     [rsp+250h+ServiceConfig.lpDisplayName], r9
0x140016466  jmp     short loc_14001646D
0x140016468  mov     r9, [rsp+250h+ServiceConfig.lpDisplayName]
0x14001646d  mov     rcx, cs:WPP_GLOBAL_Control
0x140016474  lea     r8, WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids
0x14001647b  mov     edx, 12h
0x140016480  mov     [rsp+250h+var_230], ebx
0x140016484  mov     rcx, [rcx+10h]
0x140016488  call    WPP_SF_Sd
0x14001648d  mov     eax, ebx
0x14001648f  jmp     loc_14001651E
0x140016494  mov     rcx, cs:WPP_GLOBAL_Control
0x14001649b  lea     rax, WPP_GLOBAL_Control
0x1400164a2  cmp     rcx, rax
0x1400164a5  jz      short loc_14001651C
0x1400164a7  test    byte ptr [rcx+1Ch], 4
0x1400164ab  jz      short loc_14001651C
0x1400164ad  xor     edx, edx; Val
0x1400164af  lea     rcx, [rsp+250h+ServiceConfig]; void *
0x1400164b4  mov     r8d, 200h; Size
0x1400164ba  call    memset
0x1400164bf  lea     r9, [rbp+150h+pcbBytesNeeded]; pcbBytesNeeded
0x1400164c6  mov     [rbp+150h+pcbBytesNeeded], 0
0x1400164d0  mov     r8d, 200h; cbBufSize
0x1400164d6  lea     rdx, [rsp+250h+ServiceConfig]; lpServiceConfig
0x1400164db  mov     rcx, rsi; hService
0x1400164de  call    cs:__imp_QueryServiceConfigW
0x1400164e4  test    eax, eax
0x1400164e6  jnz     short loc_1400164FB
0x1400164e8  call    HrGetLastFailure
0x1400164ed  lea     r9, aUnknown_1; "<unknown>"
0x1400164f4  mov     [rsp+250h+ServiceConfig.lpDisplayName], r9
0x1400164f9  jmp     short loc_140016500
0x1400164fb  mov     r9, [rsp+250h+ServiceConfig.lpDisplayName]
0x140016500  mov     rcx, cs:WPP_GLOBAL_Control
0x140016507  lea     r8, WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids
0x14001650e  mov     edx, 13h
0x140016513  mov     rcx, [rcx+10h]
0x140016517  call    WPP_SF_S
0x14001651c  xor     eax, eax
0x14001651e  mov     rcx, [rbp+150h+var_18]
0x140016525  xor     rcx, rsp; StackCookie
0x140016528  call    __security_check_cookie
0x14001652d  add     rsp, 240h
0x140016534  pop     rsi
0x140016535  pop     rbx
0x140016536  pop     rbp
0x140016537  retn
```
