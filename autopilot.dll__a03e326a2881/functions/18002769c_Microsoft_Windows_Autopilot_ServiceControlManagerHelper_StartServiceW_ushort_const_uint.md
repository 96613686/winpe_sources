# Microsoft::Windows::Autopilot::ServiceControlManagerHelper::StartServiceW(ushort const *,uint)

- ea: `0x18002769c`
- end: `0x18002792e`
- name: `?StartServiceW@ServiceControlManagerHelper@Autopilot@Windows@Microsoft@@SAJPEBGI@Z`
- size: `658`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180026990`

## callees

- `0x18000ec40`
- `0x1800105f4`
- `0x180027448`
- `0x1800275d8`
- `0x180027680`
- `0x18002769c`
- `0x180027934`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800277a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027884`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002789b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800278b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800278cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800278e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800278fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027917`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800277a2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027884`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002789b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800278b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800278cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800278e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800278fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027917`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180027793`
- `api-ms-win-service-management-l1-1-0!StartServiceW` at `0x180027793`

## string_xrefs

- `0x1800276cf`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scmhelper.cpp`
- `0x18002772d`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scmhelper.cpp`
- `0x1800277e7`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scmhelper.cpp`
- `0x18002782e`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\scmhelper.cpp`

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
  ServiceHandle = Microsoft::Windows::Autopilot::ServiceControlManagerHelper::GetServiceHandle(
                    (__int64)a1,
                    a2,
                    (__int64)&v32);
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
        JUMPOUT(0x18002792DLL);
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
0x18002769c  push    rbp
0x18002769e  push    rbx
0x18002769f  push    rdi
0x1800276a0  push    r14
0x1800276a2  mov     rbp, rsp
0x1800276a5  sub     rsp, 68h
0x1800276a9  lea     r14, ??_7?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::`vftable'
0x1800276b0  mov     [rbp+hService], 0
0x1800276b8  lea     r8, [rbp+var_48]
0x1800276bc  mov     [rbp+var_48], r14
0x1800276c0  call    ?GetServiceHandle@ServiceControlManagerHelper@Autopilot@Windows@Microsoft@@SAJPEBGKAEAV?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@4@@Z; Microsoft::Windows::Autopilot::ServiceControlManagerHelper::GetServiceHandle(ushort const *,ulong,Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits> &)
0x1800276c5  mov     ebx, eax
0x1800276c7  test    eax, eax
0x1800276c9  jns     short loc_180027706
0x1800276cb  mov     rcx, [rbp+20h]; this
0x1800276cf  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800276d6  mov     r9d, eax; char *
0x1800276d9  mov     edx, 19h; void *
0x1800276de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800276e3  cmp     [rbp+hService], 0
0x1800276e8  mov     [rbp+var_48], r14
0x1800276ec  jz      short loc_1800276FF
0x1800276ee  lea     rcx, [rbp+var_48]
0x1800276f2  call    ?InternalClose@?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(void)
0x1800276f7  test    al, al
0x1800276f9  jz      loc_1800278FD
0x1800276ff  mov     eax, ebx
0x180027701  jmp     loc_18002787A
0x180027706  mov     rcx, [rbp+hService]; struct SC_HANDLE__ *
0x18002770a  lea     rdx, [rbp+var_38]; struct _SERVICE_STATUS_PROCESS *
0x18002770e  xorps   xmm0, xmm0
0x180027711  xor     eax, eax
0x180027713  movups  xmmword ptr [rbp+var_38.dwServiceType], xmm0
0x180027717  mov     [rbp+var_38.dwServiceFlags], eax
0x18002771a  movups  xmmword ptr [rbp+var_38.dwServiceSpecificExitCode], xmm0
0x18002771e  call    ?GetServiceStateEx@ServiceControlManagerHelper@Autopilot@Windows@Microsoft@@SAJPEAUSC_HANDLE__@@PEAU_SERVICE_STATUS_PROCESS@@@Z; Microsoft::Windows::Autopilot::ServiceControlManagerHelper::GetServiceStateEx(SC_HANDLE__ *,_SERVICE_STATUS_PROCESS *)
0x180027723  mov     ebx, eax
0x180027725  test    eax, eax
0x180027727  jns     short loc_18002775F
0x180027729  mov     rcx, [rbp+20h]; this
0x18002772d  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\moderndeployment\\au"...
0x180027734  mov     r9d, eax; char *
0x180027737  mov     edx, 1Dh; void *
0x18002773c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027741  cmp     [rbp+hService], 0
0x180027746  mov     [rbp+var_48], r14
0x18002774a  jz      short loc_1800276FF
0x18002774c  lea     rcx, [rbp+var_48]
0x180027750  call    ?InternalClose@?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(void)
0x180027755  test    al, al
0x180027757  jz      loc_18002789B
0x18002775d  jmp     short loc_1800276FF
0x18002775f  cmp     [rbp+var_38.dwCurrentState], 4
0x180027763  jnz     short loc_18002778A
0x180027765  cmp     [rbp+hService], 0
0x18002776a  mov     [rbp+var_48], r14
0x18002776e  jz      loc_180027878
0x180027774  lea     rcx, [rbp+var_48]
0x180027778  call    ?InternalClose@?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(void)
0x18002777d  test    al, al
0x18002777f  jz      loc_1800278B5
0x180027785  jmp     loc_180027878
0x18002778a  mov     rcx, [rbp+hService]; hService
0x18002778e  xor     r8d, r8d; lpServiceArgVectors
0x180027791  xor     edx, edx; dwNumServiceArgs
0x180027793  call    cs:__imp_StartServiceW
0x180027799  mov     ebx, 80070000h
0x18002779e  test    eax, eax
0x1800277a0  jnz     short loc_18002781B
0x1800277a2  call    cs:__imp_GetLastError
0x1800277a8  mov     edi, eax
0x1800277aa  cmp     eax, 420h
0x1800277af  jnz     short loc_1800277D6
0x1800277b1  cmp     [rbp+hService], 0
0x1800277b6  mov     [rbp+var_48], r14
0x1800277ba  jz      loc_180027878
0x1800277c0  lea     rcx, [rbp+var_48]
0x1800277c4  call    ?InternalClose@?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(void)
0x1800277c9  test    al, al
0x1800277cb  jz      loc_1800278CF
0x1800277d1  jmp     loc_180027878
0x1800277d6  test    eax, eax
0x1800277d8  jle     short loc_1800277DF
0x1800277da  movzx   edi, ax
0x1800277dd  or      edi, ebx
0x1800277df  test    edi, edi
0x1800277e1  jns     short loc_18002781B
0x1800277e3  mov     rcx, [rbp+20h]; this
0x1800277e7  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800277ee  mov     r9d, edi; char *
0x1800277f1  mov     edx, 25h ; '%'; void *
0x1800277f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800277fb  cmp     [rbp+hService], 0
0x180027800  mov     [rbp+var_48], r14
0x180027804  jz      short loc_180027817
0x180027806  lea     rcx, [rbp+var_48]
0x18002780a  call    ?InternalClose@?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(void)
0x18002780f  test    al, al
0x180027811  jz      loc_180027917
0x180027817  mov     eax, edi
0x180027819  jmp     short loc_18002787A
0x18002781b  mov     rcx, [rbp+hService]; struct SC_HANDLE__ *
0x18002781f  call    ?WaitForServiceStateViaPolling@ServiceControlManagerHelper@Autopilot@Windows@Microsoft@@SAJPEAUSC_HANDLE__@@KI@Z; Microsoft::Windows::Autopilot::ServiceControlManagerHelper::WaitForServiceStateViaPolling(SC_HANDLE__ *,ulong,uint)
0x180027824  mov     edi, eax
0x180027826  test    eax, eax
0x180027828  jns     short loc_180027860
0x18002782a  mov     rcx, [rbp+20h]; this
0x18002782e  lea     r8, aOnecoreuapAdmi_6; "onecoreuap\\admin\\moderndeployment\\au"...
0x180027835  mov     r9d, eax; char *
0x180027838  mov     edx, 28h ; '('; void *
0x18002783d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027842  cmp     [rbp+hService], 0
0x180027847  mov     [rbp+var_48], r14
0x18002784b  jz      short loc_180027817
0x18002784d  lea     rcx, [rbp+var_48]
0x180027851  call    ?InternalClose@?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(void)
0x180027856  test    al, al
0x180027858  jz      loc_1800278E6
0x18002785e  jmp     short loc_180027817
0x180027860  cmp     [rbp+hService], 0
0x180027865  mov     [rbp+var_48], r14
0x180027869  jz      short loc_180027878
0x18002786b  lea     rcx, [rbp+var_48]
0x18002786f  call    ?InternalClose@?$HandleT@UServiceHandleTraits@Autopilot@Windows@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::Windows::Autopilot::ServiceHandleTraits>::InternalClose(void)
0x180027874  test    al, al
0x180027876  jz      short loc_180027884
0x180027878  xor     eax, eax
0x18002787a  add     rsp, 68h
0x18002787e  pop     r14
0x180027880  pop     rdi
0x180027881  pop     rbx
0x180027882  pop     rbp
0x180027883  retn
0x180027884  call    cs:__imp_GetLastError
0x18002788a  test    eax, eax
0x18002788c  jle     short loc_180027893
0x18002788e  movzx   eax, ax
0x180027891  or      eax, ebx
0x180027893  mov     ecx, eax; this
0x180027895  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x18002789a  int     3; Trap to Debugger
0x18002789b  call    cs:__imp_GetLastError
0x1800278a1  test    eax, eax
0x1800278a3  jle     short loc_1800278AD
0x1800278a5  movzx   eax, ax
0x1800278a8  or      eax, 80070000h
0x1800278ad  mov     ecx, eax; this
0x1800278af  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800278b4  int     3; Trap to Debugger
0x1800278b5  call    cs:__imp_GetLastError
0x1800278bb  test    eax, eax
0x1800278bd  jle     short loc_1800278C7
0x1800278bf  movzx   eax, ax
0x1800278c2  or      eax, 80070000h
0x1800278c7  mov     ecx, eax; this
0x1800278c9  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800278ce  int     3; Trap to Debugger
0x1800278cf  call    cs:__imp_GetLastError
0x1800278d5  test    eax, eax
0x1800278d7  jle     short loc_1800278DE
0x1800278d9  movzx   eax, ax
0x1800278dc  or      eax, ebx
0x1800278de  mov     ecx, eax; this
0x1800278e0  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800278e5  int     3; Trap to Debugger
0x1800278e6  call    cs:__imp_GetLastError
0x1800278ec  test    eax, eax
0x1800278ee  jle     short loc_1800278F5
0x1800278f0  movzx   eax, ax
0x1800278f3  or      eax, ebx
0x1800278f5  mov     ecx, eax; this
0x1800278f7  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x1800278fc  int     3; Trap to Debugger
0x1800278fd  call    cs:__imp_GetLastError
0x180027903  test    eax, eax
0x180027905  jle     short loc_18002790F
0x180027907  movzx   eax, ax
0x18002790a  or      eax, 80070000h
0x18002790f  mov     ecx, eax; this
0x180027911  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
0x180027916  int     3; Trap to Debugger
0x180027917  call    cs:__imp_GetLastError
0x18002791d  test    eax, eax
0x18002791f  jle     short loc_180027926
0x180027921  movzx   eax, ax
0x180027924  or      eax, ebx
0x180027926  mov     ecx, eax; this
0x180027928  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
