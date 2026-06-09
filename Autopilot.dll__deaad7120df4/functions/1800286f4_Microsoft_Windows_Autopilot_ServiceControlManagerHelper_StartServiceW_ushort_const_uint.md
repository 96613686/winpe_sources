# Microsoft::Windows::Autopilot::ServiceControlManagerHelper::StartServiceW(ushort const *,uint)

- ea: `0x1800286f4`
- end: `0x1800289bd`
- name: `?StartServiceW@ServiceControlManagerHelper@Autopilot@Windows@Microsoft@@SAJPEBGI@Z`
- size: `713`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180027904`

## callees

- `0x18000ed44`
- `0x180010764`
- `0x180028470`
- `0x180028624`
- `0x1800286d0`
- `0x1800286f4`
- `0x1800289c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800288e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028906`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028926`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028946`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028963`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028980`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800289a0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028800`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800288e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028906`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028926`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028946`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028963`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028980`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800289a0`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800287eb`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x1800287eb`

## string_xrefs

- `0x180028727`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scmhelper.cpp`
- `0x180028785`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scmhelper.cpp`
- `0x18002884b`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scmhelper.cpp`
- `0x180028892`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scmhelper.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::ServiceControlManagerHelper::StartServiceW(
        const unsigned __int16 *a1,
        __int64 a2)
{
  int ServiceHandle; // eax
  unsigned int v3; // ebx
  int ServiceState; // eax
  unsigned int v6; // edx
  unsigned int v7; // r8d
  signed int v8; // eax
  unsigned int v9; // edi
  int v10; // eax
  signed int v11; // eax
  int v12; // edx
  unsigned int v13; // r8d
  signed int v14; // eax
  int v15; // edx
  unsigned int v16; // r8d
  signed int v17; // eax
  int v18; // edx
  unsigned int v19; // r8d
  signed int v20; // eax
  int v21; // edx
  unsigned int v22; // r8d
  signed int v23; // eax
  int v24; // edx
  unsigned int v25; // r8d
  signed int LastError; // eax
  int v27; // edx
  unsigned int v28; // r8d
  signed int v29; // eax
  int v30; // edx
  unsigned int v31; // r8d
  void **v32; // [rsp+20h] [rbp-48h] BYREF
  SC_HANDLE hService; // [rsp+28h] [rbp-40h]
  _SERVICE_STATUS_PROCESS v34; // [rsp+30h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+20h]

  hService = 0;
  v32 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::`vftable';
  ServiceHandle = Microsoft::Windows::Autopilot::ServiceControlManagerHelper::GetServiceHandle(a1, a2, &v32);
  v3 = ServiceHandle;
  if ( ServiceHandle < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\scmhelper.cpp",
      (const char *)(unsigned int)ServiceHandle,
      (int)v32);
    v32 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::`vftable';
    if ( hService
      && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(&v32) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)LastError, v27, v28);
      __debugbreak();
    }
    return v3;
  }
  memset(&v34, 0, sizeof(v34));
  ServiceState = Microsoft::Windows::Autopilot::ServiceControlManagerHelper::GetServiceStateEx(hService, &v34);
  v3 = ServiceState;
  if ( ServiceState < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\scmhelper.cpp",
      (const char *)(unsigned int)ServiceState,
      (int)v32);
    v32 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::`vftable';
    if ( hService
      && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(&v32) )
    {
      v14 = GetLastError();
      if ( v14 > 0 )
        v14 = (unsigned __int16)v14 | 0x80070000;
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v14, v15, v16);
      __debugbreak();
    }
    return v3;
  }
  if ( v34.dwCurrentState != 4 )
  {
    if ( StartServiceW(hService, 0, 0) )
      goto LABEL_24;
    v8 = GetLastError();
    v9 = v8;
    if ( v8 == 1056 )
    {
      v32 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::`vftable';
      if ( hService
        && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(&v32) )
      {
        v20 = GetLastError();
        if ( v20 > 0 )
          v20 = (unsigned __int16)v20 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v20, v21, v22);
        __debugbreak();
      }
      return 0;
    }
    if ( v8 > 0 )
      v9 = (unsigned __int16)v8 | 0x80070000;
    if ( (v9 & 0x80000000) == 0 )
    {
LABEL_24:
      v10 = Microsoft::Windows::Autopilot::ServiceControlManagerHelper::WaitForServiceStateViaPolling(hService, v6, v7);
      v9 = v10;
      if ( v10 >= 0 )
      {
        v32 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::`vftable';
        if ( hService
          && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(&v32) )
        {
          v11 = GetLastError();
          if ( v11 > 0 )
            v11 = (unsigned __int16)v11 | 0x80070000;
          Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v11, v12, v13);
          __debugbreak();
        }
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x28,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\scmhelper.cpp",
        (const char *)(unsigned int)v10,
        (int)v32);
      v32 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::`vftable';
      if ( hService
        && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(&v32) )
      {
        v23 = GetLastError();
        if ( v23 > 0 )
          v23 = (unsigned __int16)v23 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v23, v24, v25);
        __debugbreak();
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x25,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\scmhelper.cpp",
        (const char *)v9,
        (int)v32);
      v32 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::`vftable';
      if ( hService
        && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(&v32) )
      {
        v29 = GetLastError();
        if ( v29 > 0 )
          v29 = (unsigned __int16)v29 | 0x80070000;
        Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v29, v30, v31);
        JUMPOUT(0x1800289BCLL);
      }
    }
    return v9;
  }
  v32 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::`vftable';
  if ( hService
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(&v32) )
  {
    v17 = GetLastError();
    if ( v17 > 0 )
      v17 = (unsigned __int16)v17 | 0x80070000;
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v17, v18, v19);
    __debugbreak();
  }
  return 0;
}

```

## disassembly

```asm
0x1800286f4  push    rbp
0x1800286f6  push    rbx
0x1800286f7  push    rdi
0x1800286f8  push    r14
0x1800286fa  mov     rbp, rsp
0x1800286fd  sub     rsp, 68h
0x180028701  lea     r14, ??_7?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::`vftable'
0x180028708  mov     [rbp+hService], 0
0x180028710  lea     r8, [rbp+var_48]
0x180028714  mov     [rbp+var_48], r14
0x180028718  call    ?GetServiceHandle@ServiceControlManagerHelper@Autopilot@Windows@Microsoft@@SAJPEBGKAEAV?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@4@@Z; Microsoft::Windows::Autopilot::ServiceControlManagerHelper::GetServiceHandle(ushort const *,ulong,Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits> &)
0x18002871d  mov     ebx, eax
0x18002871f  test    eax, eax
0x180028721  jns     short loc_18002875E
0x180028723  mov     rcx, [rbp+20h]; this
0x180028727  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002872e  mov     r9d, eax; char *
0x180028731  mov     edx, 19h; void *
0x180028736  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002873b  cmp     [rbp+hService], 0
0x180028740  mov     [rbp+var_48], r14
0x180028744  jz      short loc_180028757
0x180028746  lea     rcx, [rbp+var_48]
0x18002874a  call    ?InternalClose@?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(void)
0x18002874f  test    al, al
0x180028751  jz      loc_180028980
0x180028757  mov     eax, ebx
0x180028759  jmp     loc_1800288DE
0x18002875e  mov     rcx, [rbp+hService]; struct SC_HANDLE__ *
0x180028762  lea     rdx, [rbp+var_38]; struct _SERVICE_STATUS_PROCESS *
0x180028766  xorps   xmm0, xmm0
0x180028769  xor     eax, eax
0x18002876b  movups  xmmword ptr [rbp+var_38.dwServiceType], xmm0
0x18002876f  mov     [rbp+var_38.dwServiceFlags], eax
0x180028772  movups  xmmword ptr [rbp+var_38.dwServiceSpecificExitCode], xmm0
0x180028776  call    ?GetServiceStateEx@ServiceControlManagerHelper@Autopilot@Windows@Microsoft@@SAJPEAUSC_HANDLE__@@PEAU_SERVICE_STATUS_PROCESS@@@Z; Microsoft::Windows::Autopilot::ServiceControlManagerHelper::GetServiceStateEx(SC_HANDLE__ *,_SERVICE_STATUS_PROCESS *)
0x18002877b  mov     ebx, eax
0x18002877d  test    eax, eax
0x18002877f  jns     short loc_1800287B7
0x180028781  mov     rcx, [rbp+20h]; this
0x180028785  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\moderndeployment\\au"...
0x18002878c  mov     r9d, eax; char *
0x18002878f  mov     edx, 1Dh; void *
0x180028794  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028799  cmp     [rbp+hService], 0
0x18002879e  mov     [rbp+var_48], r14
0x1800287a2  jz      short loc_180028757
0x1800287a4  lea     rcx, [rbp+var_48]
0x1800287a8  call    ?InternalClose@?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(void)
0x1800287ad  test    al, al
0x1800287af  jz      loc_180028906
0x1800287b5  jmp     short loc_180028757
0x1800287b7  cmp     [rbp+var_38.dwCurrentState], 4
0x1800287bb  jnz     short loc_1800287E2
0x1800287bd  cmp     [rbp+hService], 0
0x1800287c2  mov     [rbp+var_48], r14
0x1800287c6  jz      loc_1800288DC
0x1800287cc  lea     rcx, [rbp+var_48]
0x1800287d0  call    ?InternalClose@?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(void)
0x1800287d5  test    al, al
0x1800287d7  jz      loc_180028926
0x1800287dd  jmp     loc_1800288DC
0x1800287e2  mov     rcx, [rbp+hService]; hService
0x1800287e6  xor     r8d, r8d; lpServiceArgVectors
0x1800287e9  xor     edx, edx; dwNumServiceArgs
0x1800287eb  call    cs:__imp_StartServiceW
0x1800287f2  nop     dword ptr [rax+rax+00h]
0x1800287f7  mov     ebx, 80070000h
0x1800287fc  test    eax, eax
0x1800287fe  jnz     short loc_18002887F
0x180028800  call    cs:__imp_GetLastError
0x180028807  nop     dword ptr [rax+rax+00h]
0x18002880c  mov     edi, eax
0x18002880e  cmp     eax, 420h
0x180028813  jnz     short loc_18002883A
0x180028815  cmp     [rbp+hService], 0
0x18002881a  mov     [rbp+var_48], r14
0x18002881e  jz      loc_1800288DC
0x180028824  lea     rcx, [rbp+var_48]
0x180028828  call    ?InternalClose@?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(void)
0x18002882d  test    al, al
0x18002882f  jz      loc_180028946
0x180028835  jmp     loc_1800288DC
0x18002883a  test    eax, eax
0x18002883c  jle     short loc_180028843
0x18002883e  movzx   edi, ax
0x180028841  or      edi, ebx
0x180028843  test    edi, edi
0x180028845  jns     short loc_18002887F
0x180028847  mov     rcx, [rbp+20h]; this
0x18002884b  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\moderndeployment\\au"...
0x180028852  mov     r9d, edi; char *
0x180028855  mov     edx, 25h ; '%'; void *
0x18002885a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002885f  cmp     [rbp+hService], 0
0x180028864  mov     [rbp+var_48], r14
0x180028868  jz      short loc_18002887B
0x18002886a  lea     rcx, [rbp+var_48]
0x18002886e  call    ?InternalClose@?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(void)
0x180028873  test    al, al
0x180028875  jz      loc_1800289A0
0x18002887b  mov     eax, edi
0x18002887d  jmp     short loc_1800288DE
0x18002887f  mov     rcx, [rbp+hService]; struct SC_HANDLE__ *
0x180028883  call    ?WaitForServiceStateViaPolling@ServiceControlManagerHelper@Autopilot@Windows@Microsoft@@SAJPEAUSC_HANDLE__@@KI@Z; Microsoft::Windows::Autopilot::ServiceControlManagerHelper::WaitForServiceStateViaPolling(SC_HANDLE__ *,ulong,uint)
0x180028888  mov     edi, eax
0x18002888a  test    eax, eax
0x18002888c  jns     short loc_1800288C4
0x18002888e  mov     rcx, [rbp+20h]; this
0x180028892  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\moderndeployment\\au"...
0x180028899  mov     r9d, eax; char *
0x18002889c  mov     edx, 28h ; '('; void *
0x1800288a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800288a6  cmp     [rbp+hService], 0
0x1800288ab  mov     [rbp+var_48], r14
0x1800288af  jz      short loc_18002887B
0x1800288b1  lea     rcx, [rbp+var_48]
0x1800288b5  call    ?InternalClose@?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(void)
0x1800288ba  test    al, al
0x1800288bc  jz      loc_180028963
0x1800288c2  jmp     short loc_18002887B
0x1800288c4  cmp     [rbp+hService], 0
0x1800288c9  mov     [rbp+var_48], r14
0x1800288cd  jz      short loc_1800288DC
0x1800288cf  lea     rcx, [rbp+var_48]
0x1800288d3  call    ?InternalClose@?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(void)
0x1800288d8  test    al, al
0x1800288da  jz      short loc_1800288E9
0x1800288dc  xor     eax, eax
0x1800288de  add     rsp, 68h
0x1800288e2  pop     r14
0x1800288e4  pop     rdi
0x1800288e5  pop     rbx
0x1800288e6  pop     rbp
0x1800288e7  retn
0x1800288e9  call    cs:__imp_GetLastError
0x1800288f0  nop     dword ptr [rax+rax+00h]
0x1800288f5  test    eax, eax
0x1800288f7  jle     short loc_1800288FE
0x1800288f9  movzx   eax, ax
0x1800288fc  or      eax, ebx
0x1800288fe  mov     ecx, eax; this
0x180028900  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180028905  int     3; Trap to Debugger
0x180028906  call    cs:__imp_GetLastError
0x18002890d  nop     dword ptr [rax+rax+00h]
0x180028912  test    eax, eax
0x180028914  jle     short loc_18002891E
0x180028916  movzx   eax, ax
0x180028919  or      eax, 80070000h
0x18002891e  mov     ecx, eax; this
0x180028920  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180028925  int     3; Trap to Debugger
0x180028926  call    cs:__imp_GetLastError
0x18002892d  nop     dword ptr [rax+rax+00h]
0x180028932  test    eax, eax
0x180028934  jle     short loc_18002893E
0x180028936  movzx   eax, ax
0x180028939  or      eax, 80070000h
0x18002893e  mov     ecx, eax; this
0x180028940  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180028945  int     3; Trap to Debugger
0x180028946  call    cs:__imp_GetLastError
0x18002894d  nop     dword ptr [rax+rax+00h]
0x180028952  test    eax, eax
0x180028954  jle     short loc_18002895B
0x180028956  movzx   eax, ax
0x180028959  or      eax, ebx
0x18002895b  mov     ecx, eax; this
0x18002895d  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180028962  int     3; Trap to Debugger
0x180028963  call    cs:__imp_GetLastError
0x18002896a  nop     dword ptr [rax+rax+00h]
0x18002896f  test    eax, eax
0x180028971  jle     short loc_180028978
0x180028973  movzx   eax, ax
0x180028976  or      eax, ebx
0x180028978  mov     ecx, eax; this
0x18002897a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18002897f  int     3; Trap to Debugger
0x180028980  call    cs:__imp_GetLastError
0x180028987  nop     dword ptr [rax+rax+00h]
0x18002898c  test    eax, eax
0x18002898e  jle     short loc_180028998
0x180028990  movzx   eax, ax
0x180028993  or      eax, 80070000h
0x180028998  mov     ecx, eax; this
0x18002899a  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18002899f  int     3; Trap to Debugger
0x1800289a0  call    cs:__imp_GetLastError
0x1800289a7  nop     dword ptr [rax+rax+00h]
0x1800289ac  test    eax, eax
0x1800289ae  jle     short loc_1800289B5
0x1800289b0  movzx   eax, ax
0x1800289b3  or      eax, ebx
0x1800289b5  mov     ecx, eax; this
0x1800289b7  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
