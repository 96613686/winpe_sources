# CommonUtil::HrChangeServiceConfig(SC_HANDLE__ *,ulong,ulong,ulong,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,ulong *)

- ea: `0x140015cb8`
- end: `0x140015e60`
- name: `?HrChangeServiceConfig@CommonUtil@@YAJPEAUSC_HANDLE__@@KKKPEB_W11111PEAK@Z`
- size: `424`
- prototype: `__int64 __fastcall(SC_HANDLE hService, struct SC_HANDLE__ *, char, char, LPCWSTR, LPCWSTR, LPCWSTR, LPCWSTR, LPCWSTR, LPCWSTR, LPDWORD, unsigned int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x140089c78`

## callees

- `0x140015cb8`
- `0x140017114`
- `0x140017738`
- `0x14003a5c0`
- `0x140166990`

## import_xrefs

- `ADVAPI32!ChangeServiceConfigW` at `0x140015d7f`
- `ADVAPI32!ChangeServiceConfigW` at `0x140015d7f`
- `ADVAPI32!QueryServiceConfigW` at `0x140015de8`
- `ADVAPI32!QueryServiceConfigW` at `0x140015de8`

## pseudocode

```c
__int64 __fastcall CommonUtil::HrChangeServiceConfig(
        SC_HANDLE hService,
        struct SC_HANDLE__ *a2,
        DWORD a3,
        DWORD a4,
        LPCWSTR lpBinaryPathName,
        LPCWSTR lpLoadOrderGroup,
        LPCWSTR lpDependencies,
        LPCWSTR lpServiceStartName,
        LPCWSTR lpPassword,
        LPCWSTR lpDisplayName,
        LPDWORD lpdwTagId)
{
  char v11; // bp
  char v12; // si
  char v13; // di
  unsigned int LastFailure; // ebx
  _QUERY_SERVICE_CONFIGW ServiceConfig[8]; // [rsp+60h] [rbp-238h] BYREF
  DWORD pcbBytesNeeded; // [rsp+260h] [rbp-38h] BYREF

  v11 = (char)a2;
  v12 = a4;
  v13 = a3;
  if ( (_DWORD)a2 == -1
    && a3 == -1
    && a4 == -1
    && !lpBinaryPathName
    && !lpLoadOrderGroup
    && !lpdwTagId
    && !lpDependencies
    && !lpServiceStartName
    && !lpPassword
    && !lpDisplayName
    || ChangeServiceConfigW(
         hService,
         a3,
         (DWORD)a2,
         a4,
         lpBinaryPathName,
         lpLoadOrderGroup,
         lpdwTagId,
         lpDependencies,
         lpServiceStartName,
         lpPassword,
         lpDisplayName) )
  {
    return 0;
  }
  LastFailure = HrGetLastFailure();
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
  {
    memset(ServiceConfig, 0, sizeof(ServiceConfig));
    pcbBytesNeeded = 0;
    if ( !QueryServiceConfigW(hService, ServiceConfig, 0x200u, &pcbBytesNeeded) )
    {
      HrGetLastFailure();
      ServiceConfig[0].lpDisplayName = (LPWSTR)L"<unknown>";
    }
    WPP_SF_SLLLd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), v13, v11, v12, LastFailure);
  }
  return LastFailure;
}

```

## disassembly

```asm
0x140015cb8  push    rbx
0x140015cba  push    rbp
0x140015cbb  push    rsi
0x140015cbc  push    rdi
0x140015cbd  push    r14
0x140015cbf  sub     rsp, 270h
0x140015cc6  mov     rax, cs:__security_cookie
0x140015ccd  xor     rax, rsp
0x140015cd0  mov     [rsp+298h+var_30], rax
0x140015cd8  mov     rax, [rsp+298h+arg_20]
0x140015ce0  mov     ebp, edx
0x140015ce2  mov     r10, [rsp+298h+arg_40]
0x140015cea  or      ebx, 0FFFFFFFFh
0x140015ced  mov     rdx, [rsp+298h+arg_48]
0x140015cf5  mov     esi, r9d
0x140015cf8  mov     r9, [rsp+298h+arg_38]
0x140015d00  mov     edi, r8d
0x140015d03  mov     r8, [rsp+298h+arg_30]
0x140015d0b  mov     r14, rcx
0x140015d0e  mov     rcx, [rsp+298h+arg_28]
0x140015d16  mov     r11, [rsp+298h+arg_50]
0x140015d1e  cmp     ebp, ebx
0x140015d20  jnz     short loc_140015D51
0x140015d22  cmp     edi, ebx
0x140015d24  jnz     short loc_140015D51
0x140015d26  cmp     esi, ebx
0x140015d28  jnz     short loc_140015D51
0x140015d2a  test    rax, rax
0x140015d2d  jnz     short loc_140015D51
0x140015d2f  test    rcx, rcx
0x140015d32  jnz     short loc_140015D51
0x140015d34  test    r11, r11
0x140015d37  jnz     short loc_140015D51
0x140015d39  test    r8, r8
0x140015d3c  jnz     short loc_140015D51
0x140015d3e  test    r9, r9
0x140015d41  jnz     short loc_140015D51
0x140015d43  test    r10, r10
0x140015d46  jnz     short loc_140015D51
0x140015d48  test    rdx, rdx
0x140015d4b  jz      loc_140015E40
0x140015d51  mov     [rsp+298h+lpDisplayName], rdx; lpDisplayName
0x140015d56  mov     edx, edi; dwServiceType
0x140015d58  mov     [rsp+298h+lpPassword], r10; lpPassword
0x140015d5d  mov     [rsp+298h+lpServiceStartName], r9; lpServiceStartName
0x140015d62  mov     r9d, esi; dwErrorControl
0x140015d65  mov     [rsp+298h+lpDependencies], r8; lpDependencies
0x140015d6a  mov     r8d, ebp; dwStartType
0x140015d6d  mov     [rsp+298h+lpdwTagId], r11; lpdwTagId
0x140015d72  mov     [rsp+298h+lpLoadOrderGroup], rcx; lpLoadOrderGroup
0x140015d77  mov     rcx, r14; hService
0x140015d7a  mov     [rsp+298h+lpBinaryPathName], rax; lpBinaryPathName
0x140015d7f  call    cs:__imp_ChangeServiceConfigW
0x140015d85  test    eax, eax
0x140015d87  jnz     loc_140015E40
0x140015d8d  call    HrGetLastFailure
0x140015d92  mov     ebx, eax
0x140015d94  mov     rax, cs:WPP_GLOBAL_Control
0x140015d9b  lea     rcx, WPP_GLOBAL_Control
0x140015da2  cmp     rax, rcx
0x140015da5  jz      loc_140015E3C
0x140015dab  test    byte ptr [rax+1Ch], 1
0x140015daf  jz      loc_140015E3C
0x140015db5  xor     edx, edx; Val
0x140015db7  lea     rcx, [rsp+298h+ServiceConfig]; void *
0x140015dbc  mov     r8d, 200h; Size
0x140015dc2  call    memset
0x140015dc7  lea     r9, [rsp+298h+pcbBytesNeeded]; pcbBytesNeeded
0x140015dcf  mov     [rsp+298h+pcbBytesNeeded], 0
0x140015dda  mov     r8d, 200h; cbBufSize
0x140015de0  lea     rdx, [rsp+298h+ServiceConfig]; lpServiceConfig
0x140015de5  mov     rcx, r14; hService
0x140015de8  call    cs:__imp_QueryServiceConfigW
0x140015dee  test    eax, eax
0x140015df0  jnz     short loc_140015E08
0x140015df2  call    HrGetLastFailure
0x140015df7  lea     r9, aUnknown_1; "<unknown>"
0x140015dfe  mov     [rsp+298h+ServiceConfig.lpDisplayName], r9
0x140015e06  jmp     short loc_140015E10
0x140015e08  mov     r9, [rsp+298h+ServiceConfig.lpDisplayName]
0x140015e10  mov     rcx, cs:WPP_GLOBAL_Control
0x140015e17  lea     r8, WPP_2f794a95c3a031461a11d46e8fbe4e7a_Traceguids
0x140015e1e  mov     dword ptr [rsp+298h+lpDependencies], ebx; char
0x140015e22  mov     edx, 16h
0x140015e27  mov     dword ptr [rsp+298h+lpdwTagId], esi; char
0x140015e2b  mov     dword ptr [rsp+298h+lpLoadOrderGroup], ebp; char
0x140015e2f  mov     rcx, [rcx+10h]; LoggerHandle
0x140015e33  mov     dword ptr [rsp+298h+lpBinaryPathName], edi; char
0x140015e37  call    WPP_SF_SLLLd
0x140015e3c  mov     eax, ebx
0x140015e3e  jmp     short loc_140015E42
0x140015e40  xor     eax, eax
0x140015e42  mov     rcx, [rsp+298h+var_30]
0x140015e4a  xor     rcx, rsp; StackCookie
0x140015e4d  call    __security_check_cookie
0x140015e52  add     rsp, 270h
0x140015e59  pop     r14
0x140015e5b  pop     rdi
0x140015e5c  pop     rsi
0x140015e5d  pop     rbp
0x140015e5e  pop     rbx
0x140015e5f  retn
```
