# ChannelBasedClientConnectionManager::CreatePipeToProvider(ushort const *,ProcessIdentity const &,std::shared_ptr<ICrossMachineCommunicationServices>,UIA_TIMEOUTDATA &,void * *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::unique_ptr<BasicUtils::CrossMachinePipeNameGuard,std::default_delete<BasicUtils::CrossMachinePipeNameGuard>> *)

- ea: `0x18005d258`
- end: `0x18005d7bb`
- name: `?CreatePipeToProvider@ChannelBasedClientConnectionManager@@AEAAJPEBGAEBUProcessIdentity@@V?$shared_ptr@VICrossMachineCommunicationServices@@@std@@AEAUUIA_TIMEOUTDATA@@PEAPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@PEAV?$unique_ptr@UCrossMachinePipeNameGuard@BasicUtils@@U?$default_delete@UCrossMachinePipeNameGuard@BasicUtils@@@std@@@4@@Z`
- size: `1379`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18005ca40`

## callees

- `0x18002f580`
- `0x180034360`
- `0x18005b9bc`
- `0x18005bad0`
- `0x18005d258`
- `0x180083ed0`
- `0x1800940c4`
- `0x1800948b8`
- `0x1800984e0`
- `0x18010cc74`
- `0x1801334b8`
- `0x18016fbcc`
- `0x1801717f4`
- `0x1801e8320`
- `0x1801fd9f8`
- `0x180234e70`
- `0x1802bf610`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005d358`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005d470`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005d358`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005d470`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x18005d3c2`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x18005d3c2`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18005d404`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18005d509`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18005d550`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18005d597`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18005d5de`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18005d625`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18005d66c`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18005d404`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18005d509`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18005d550`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18005d597`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18005d5de`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18005d625`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18005d66c`

## string_xrefs

- `0x18005d3e1`: `CreateNamedPipe`
- `0x18005d534`: `onecore\windows\accessibletech\uiautomationcore\clientconnection.cpp`
- `0x18005d57b`: `onecore\windows\accessibletech\uiautomationcore\clientconnection.cpp`
- `0x18005d5c2`: `onecore\windows\accessibletech\uiautomationcore\clientconnection.cpp`
- `0x18005d609`: `onecore\windows\accessibletech\uiautomationcore\clientconnection.cpp`
- `0x18005d650`: `onecore\windows\accessibletech\uiautomationcore\clientconnection.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall ChannelBasedClientConnectionManager::CreatePipeToProvider(
        __int64 a1,
        __int64 a2,
        const struct ProcessIdentity *a3,
        _QWORD *a4,
        __int64 a5,
        _QWORD *a6,
        __int64 a7,
        __int64 *a8)
{
  __int64 v11; // rdx
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  unsigned int v15; // ebx
  DWORD CurrentProcessId; // eax
  int v17; // eax
  unsigned int v18; // ebx
  HANDLE v19; // rbx
  unsigned int v20; // ebx
  std::_Ref_count_base *v21; // rcx
  int PlatformSpecificSecurityAttributesLocalMachine; // eax
  unsigned int v24; // ebx
  __int64 v25; // rdx
  _QWORD *Instance; // rax
  std::_Ref_count_base *v27; // rcx
  std::_Ref_count_base *v28; // rcx
  std::_Ref_count_base *v29; // rcx
  std::_Ref_count_base *v30; // rcx
  std::_Ref_count_base *v31; // rcx
  std::_Ref_count_base *v32; // rcx
  int v33; // eax
  unsigned int v34; // ebx
  int nOutBufferSize; // [rsp+20h] [rbp-768h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-748h] BYREF
  HANDLE v37; // [rsp+58h] [rbp-730h] BYREF
  void *v38; // [rsp+60h] [rbp-728h] BYREF
  __int64 v39; // [rsp+68h] [rbp-720h] BYREF
  std::_Ref_count_base *v40; // [rsp+70h] [rbp-718h]
  int v41[2]; // [rsp+78h] [rbp-710h]
  _QWORD *v42; // [rsp+80h] [rbp-708h]
  _BYTE v43[32]; // [rsp+88h] [rbp-700h] BYREF
  _BYTE v44[32]; // [rsp+A8h] [rbp-6E0h] BYREF
  int v45[8]; // [rsp+C8h] [rbp-6C0h] BYREF
  int v46[10]; // [rsp+E8h] [rbp-6A0h] BYREF
  WCHAR Name[264]; // [rsp+110h] [rbp-678h] BYREF
  unsigned __int16 v48[264]; // [rsp+320h] [rbp-468h] BYREF
  unsigned __int16 v49[264]; // [rsp+530h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+788h] [rbp+0h]

  v42 = a4;
  v39 = a5;
  *(_QWORD *)v41 = a7;
  *a6 = 0;
  v11 = *a8;
  *a8 = 0;
  if ( v11 )
    std::default_delete<BasicUtils::CrossMachinePipeNameGuard>::operator()();
  SecurityAttributes.lpSecurityDescriptor = 0;
  if ( *a4 )
  {
    (*(void (__fastcall **)(_QWORD, void **))(*(_QWORD *)*a4 + 40LL))(*a4, &v38);
    SecurityAttributes.nLength = 24;
    SecurityAttributes.lpSecurityDescriptor = v38;
    SecurityAttributes.bInheritHandle = 0;
  }
  else
  {
    PlatformSpecificSecurityAttributesLocalMachine = UiaUtils::GetPlatformSpecificSecurityAttributesLocalMachine(
                                                       a3,
                                                       &SecurityAttributes);
    v24 = PlatformSpecificSecurityAttributesLocalMachine;
    if ( PlatformSpecificSecurityAttributesLocalMachine < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x412,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\clientconnection.cpp",
        (const char *)(unsigned int)PlatformSpecificSecurityAttributesLocalMachine,
        nOutBufferSize);
      if ( SecurityAttributes.lpSecurityDescriptor )
      {
        FreeTransientObjectSecurityDescriptor();
        SecurityAttributes.lpSecurityDescriptor = 0;
      }
      v30 = (std::_Ref_count_base *)a4[1];
      if ( v30 )
        std::_Ref_count_base::_Decref(v30);
      return v24;
    }
  }
  v12 = StringCchPrintfW(v49, 0x104u, L"%ws", a2);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x418,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\clientconnection.cpp",
      (const char *)(unsigned int)v12,
      nOutBufferSize);
    if ( SecurityAttributes.lpSecurityDescriptor )
    {
      FreeTransientObjectSecurityDescriptor();
      SecurityAttributes.lpSecurityDescriptor = 0;
    }
    v31 = (std::_Ref_count_base *)a4[1];
    if ( v31 )
      std::_Ref_count_base::_Decref(v31);
    return v13;
  }
  else
  {
    v14 = StringCchPrintfW(v48, 0x104u, v49, L"UIA_PIPE");
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x419,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\clientconnection.cpp",
        (const char *)(unsigned int)v14,
        nOutBufferSize);
      if ( SecurityAttributes.lpSecurityDescriptor )
      {
        FreeTransientObjectSecurityDescriptor();
        SecurityAttributes.lpSecurityDescriptor = 0;
      }
      v29 = (std::_Ref_count_base *)a4[1];
      if ( v29 )
        std::_Ref_count_base::_Decref(v29);
      return v15;
    }
    else
    {
      CurrentProcessId = GetCurrentProcessId();
      if ( CurrentProcessId == *(_DWORD *)a3 && BasicUtils::IsAppContainer(CurrentProcessId) )
      {
        v33 = StringCchPrintfW(Name, 0x104u, L"\\\\.\\PIPE\\LOCAL\\%ws", v48);
        v34 = v33;
        if ( v33 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x421,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\clientconnection.cpp",
            (const char *)(unsigned int)v33,
            nOutBufferSize);
          if ( SecurityAttributes.lpSecurityDescriptor )
          {
            FreeTransientObjectSecurityDescriptor();
            SecurityAttributes.lpSecurityDescriptor = 0;
          }
          v32 = (std::_Ref_count_base *)a4[1];
          if ( v32 )
            std::_Ref_count_base::_Decref(v32);
          return v34;
        }
        goto LABEL_9;
      }
      v17 = StringCchPrintfW(Name, 0x104u, L"\\\\.\\PIPE\\%ws", v48);
      v18 = v17;
      if ( v17 >= 0 )
      {
LABEL_9:
        v19 = CreateNamedPipeW(Name, 0x40080003u, 0xEu, 0x32u, 0x1000u, 0x1000u, 0, &SecurityAttributes);
        v37 = v19;
        if ( v19 == (HANDLE)-1LL )
        {
          v20 = Error::Win32Error(L"CreateNamedPipe", L"Creating client pipe");
          AutoCleanupInfo<void *>::SafeRelease(&v37);
          if ( SecurityAttributes.lpSecurityDescriptor )
          {
            FreeTransientObjectSecurityDescriptor();
            SecurityAttributes.lpSecurityDescriptor = 0;
          }
          v21 = (std::_Ref_count_base *)a4[1];
          if ( v21 )
            std::_Ref_count_base::_Decref(v21);
          return v20;
        }
        else
        {
          if ( *a4 )
          {
            std::wstring::wstring(v44, Name);
            std::wstring::wstring(v43, v48);
            (*(void (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)*a4 + 24LL))(*a4, *(unsigned int *)(v39 + 4));
            (*(void (__fastcall **)(_QWORD, _BYTE *, _BYTE *, _QWORD))(*(_QWORD *)*a4 + 8LL))(
              *a4,
              v44,
              v43,
              *(unsigned int *)a3);
            std::make_unique<BasicUtils::CrossMachinePipeNameGuard,std::wstring,std::wstring,std::shared_ptr<ICrossMachineCommunicationServices> &,0>(
              &v38,
              v44,
              v43,
              a4);
            std::unique_ptr<BasicUtils::CrossMachinePipeNameGuard>::operator=<std::default_delete<BasicUtils::CrossMachinePipeNameGuard>,0>(
              a8,
              &v38);
            if ( v38 )
              std::default_delete<BasicUtils::CrossMachinePipeNameGuard>::operator()();
            std::wstring::_Tidy_deallocate(v43);
            std::wstring::_Tidy_deallocate(v44);
          }
          *a6 = v19;
          v37 = 0;
          v25 = GetCurrentProcessId();
          GetProcessNameFromPID(v46, v25);
          GetProcessNameFromPID(v45, *(unsigned int *)a3);
          Instance = (_QWORD *)TelemetryUtility::GetInstance(&v39);
          TelemetryUtility::StartConnection(
            *Instance,
            (int)v46,
            (int)v45,
            v41[0],
            (TelemetryUtility *)*(unsigned int *)a3);
          if ( v40 )
            std::_Ref_count_base::_Decref(v40);
          std::wstring::_Tidy_deallocate(v45);
          std::wstring::_Tidy_deallocate(v46);
          AutoCleanupInfo<void *>::SafeRelease(&v37);
          if ( SecurityAttributes.lpSecurityDescriptor )
          {
            FreeTransientObjectSecurityDescriptor();
            SecurityAttributes.lpSecurityDescriptor = 0;
          }
          v27 = (std::_Ref_count_base *)a4[1];
          if ( v27 )
            std::_Ref_count_base::_Decref(v27);
          return 0;
        }
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x425,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\clientconnection.cpp",
        (const char *)(unsigned int)v17,
        nOutBufferSize);
      if ( SecurityAttributes.lpSecurityDescriptor )
      {
        FreeTransientObjectSecurityDescriptor();
        SecurityAttributes.lpSecurityDescriptor = 0;
      }
      v28 = (std::_Ref_count_base *)a4[1];
      if ( v28 )
        std::_Ref_count_base::_Decref(v28);
      return v18;
    }
  }
}

```

## disassembly

```asm
0x18005d258  push    rbx
0x18005d25a  push    rsi
0x18005d25b  push    rdi
0x18005d25c  push    r12
0x18005d25e  push    r13
0x18005d260  push    r14
0x18005d262  push    r15
0x18005d264  sub     rsp, 750h
0x18005d26b  mov     rax, cs:__security_cookie
0x18005d272  xor     rax, rsp
0x18005d275  mov     [rsp+788h+var_48], rax
0x18005d27d  mov     rsi, r9
0x18005d280  mov     r14, r8
0x18005d283  mov     r12, rdx
0x18005d286  mov     [rsp+788h+var_708], r9
0x18005d28e  mov     rax, [rsp+788h+arg_20]
0x18005d296  mov     [rsp+788h+var_720], rax
0x18005d29b  mov     r13, [rsp+788h+arg_28]
0x18005d2a3  mov     rax, [rsp+788h+arg_30]
0x18005d2ab  mov     qword ptr [rsp+788h+var_710], rax
0x18005d2b0  mov     r15, [rsp+788h+arg_38]
0x18005d2b8  xor     edi, edi
0x18005d2ba  mov     [r13+0], rdi
0x18005d2be  mov     rdx, [r15]
0x18005d2c1  mov     [r15], rdi
0x18005d2c4  test    rdx, rdx
0x18005d2c7  jnz     loc_18005D753
0x18005d2cd  mov     [rsp+788h+SecurityAttributes.lpSecurityDescriptor], rdi
0x18005d2d2  mov     rcx, [rsi]
0x18005d2d5  test    rcx, rcx
0x18005d2d8  jz      loc_18005D442
0x18005d2de  mov     rax, [rcx]
0x18005d2e1  lea     rdx, [rsp+788h+var_728]
0x18005d2e6  mov     rax, [rax+28h]
0x18005d2ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d2ef  mov     [rsp+788h+SecurityAttributes.nLength], 18h
0x18005d2f7  mov     rax, [rsp+788h+var_728]
0x18005d2fc  mov     [rsp+788h+SecurityAttributes.lpSecurityDescriptor], rax
0x18005d301  mov     [rsp+788h+SecurityAttributes.bInheritHandle], edi
0x18005d305  mov     r9, r12
0x18005d308  lea     r8, aWs; "%ws"
0x18005d30f  mov     r12d, 104h
0x18005d315  mov     edx, r12d; unsigned __int64
0x18005d318  lea     rcx, [rsp+788h+var_258]; unsigned __int16 *
0x18005d320  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005d325  mov     ebx, eax
0x18005d327  test    eax, eax
0x18005d329  js      loc_18005D5FE
0x18005d32f  lea     r9, aUiaPipe; "UIA_PIPE"
0x18005d336  lea     r8, [rsp+788h+var_258]; unsigned __int16 *
0x18005d33e  mov     edx, r12d; unsigned __int64
0x18005d341  lea     rcx, [rsp+788h+var_468]; unsigned __int16 *
0x18005d349  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005d34e  mov     ebx, eax
0x18005d350  test    eax, eax
0x18005d352  js      loc_18005D570
0x18005d358  call    cs:__imp_GetCurrentProcessId
0x18005d35e  cmp     eax, [r14]
0x18005d361  jz      loc_18005D75D
0x18005d367  lea     r9, [rsp+788h+var_468]
0x18005d36f  lea     r8, aPipeWs; "\\\\.\\PIPE\\%ws"
0x18005d376  mov     rdx, r12; unsigned __int64
0x18005d379  lea     rcx, [rsp+788h+Name]; unsigned __int16 *
0x18005d381  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18005d386  mov     ebx, eax
0x18005d388  test    eax, eax
0x18005d38a  js      loc_18005D529
0x18005d390  lea     rax, [rsp+788h+SecurityAttributes]
0x18005d395  mov     [rsp+788h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18005d39a  mov     [rsp+788h+nDefaultTimeOut], edi; nDefaultTimeOut
0x18005d39e  mov     eax, 1000h
0x18005d3a3  mov     [rsp+788h+nInBufferSize], eax; nInBufferSize
0x18005d3a7  mov     [rsp+788h+nOutBufferSize], eax; nOutBufferSize
0x18005d3ab  mov     edx, 40080003h; dwOpenMode
0x18005d3b0  mov     r9d, 32h ; '2'; nMaxInstances
0x18005d3b6  lea     r8d, [r9-24h]; dwPipeMode
0x18005d3ba  lea     rcx, [rsp+788h+Name]; lpName
0x18005d3c2  call    cs:__imp_CreateNamedPipeW
0x18005d3c8  mov     rbx, rax
0x18005d3cb  mov     [rsp+788h+var_730], rax
0x18005d3d0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18005d3d4  jnz     loc_18005D45E
0x18005d3da  lea     rdx, aCreatingClient; "Creating client pipe"
0x18005d3e1  lea     rcx, aCreatenamedpip; "CreateNamedPipe"
0x18005d3e8  call    ?Win32Error@Error@@SAJPEBG0@Z; Error::Win32Error(ushort const *,ushort const *)
0x18005d3ed  mov     ebx, eax
0x18005d3ef  lea     rcx, [rsp+788h+var_730]
0x18005d3f4  call    ?SafeRelease@?$AutoCleanupInfo@PEAX@@SAXAEAPEAX@Z; AutoCleanupInfo<void *>::SafeRelease(void * &)
0x18005d3f9  nop
0x18005d3fa  mov     rcx, [rsp+788h+SecurityAttributes.lpSecurityDescriptor]
0x18005d3ff  test    rcx, rcx
0x18005d402  jz      short loc_18005D40F
0x18005d404  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18005d40a  mov     [rsp+788h+SecurityAttributes.lpSecurityDescriptor], rdi
0x18005d40f  mov     rcx, [rsi+8]; this
0x18005d413  test    rcx, rcx
0x18005d416  jz      short loc_18005D41D
0x18005d418  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005d41d  mov     eax, ebx
0x18005d41f  mov     rcx, [rsp+788h+var_48]
0x18005d427  xor     rcx, rsp; StackCookie
0x18005d42a  call    __security_check_cookie
0x18005d42f  add     rsp, 750h
0x18005d436  pop     r15
0x18005d438  pop     r14
0x18005d43a  pop     r13
0x18005d43c  pop     r12
0x18005d43e  pop     rdi
0x18005d43f  pop     rsi
0x18005d440  pop     rbx
0x18005d441  retn
0x18005d442  lea     rdx, [rsp+788h+SecurityAttributes]; struct _SECURITY_ATTRIBUTES *
0x18005d447  mov     rcx, r14; struct ProcessIdentity *
0x18005d44a  call    ?GetPlatformSpecificSecurityAttributesLocalMachine@UiaUtils@@SAJAEBUProcessIdentity@@PEAU_SECURITY_ATTRIBUTES@@@Z; UiaUtils::GetPlatformSpecificSecurityAttributesLocalMachine(ProcessIdentity const &,_SECURITY_ATTRIBUTES *)
0x18005d44f  mov     ebx, eax
0x18005d451  test    eax, eax
0x18005d453  jns     loc_18005D305
0x18005d459  jmp     loc_18005D5B7
0x18005d45e  cmp     [rsi], rdi
0x18005d461  jnz     loc_18005D69A
0x18005d467  mov     [r13+0], rbx
0x18005d46b  mov     [rsp+788h+var_730], rdi
0x18005d470  call    cs:__imp_GetCurrentProcessId
0x18005d476  mov     edx, eax
0x18005d478  lea     rcx, [rsp+788h+var_6A0]
0x18005d480  call    ?GetProcessNameFromPID@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; GetProcessNameFromPID(uint)
0x18005d485  nop
0x18005d486  mov     edx, [r14]
0x18005d489  lea     rcx, [rsp+788h+var_6C0]
0x18005d491  call    ?GetProcessNameFromPID@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@I@Z; GetProcessNameFromPID(uint)
0x18005d496  nop
0x18005d497  lea     rcx, [rsp+788h+var_720]
0x18005d49c  call    ?GetInstance@TelemetryUtility@@SA?AV?$shared_ptr@VTelemetryUtility@@@std@@XZ; TelemetryUtility::GetInstance(void)
0x18005d4a1  nop
0x18005d4a2  mov     ecx, [r14]
0x18005d4a5  mov     qword ptr [rsp+788h+nOutBufferSize], rcx; TelemetryUtility *
0x18005d4aa  mov     r9, qword ptr [rsp+788h+var_710]; int
0x18005d4af  lea     r8, [rsp+788h+var_6C0]; int
0x18005d4b7  lea     rdx, [rsp+788h+var_6A0]; int
0x18005d4bf  mov     rcx, [rax]; int
0x18005d4c2  call    ?StartConnection@TelemetryUtility@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00_K@Z; TelemetryUtility::StartConnection(std::wstring const &,std::wstring const &,std::wstring const &,unsigned __int64)
0x18005d4c7  nop
0x18005d4c8  mov     rcx, [rsp+788h+var_718]; this
0x18005d4cd  test    rcx, rcx
0x18005d4d0  jz      short loc_18005D4D8
0x18005d4d2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005d4d7  nop
0x18005d4d8  lea     rcx, [rsp+788h+var_6C0]
0x18005d4e0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005d4e5  nop
0x18005d4e6  lea     rcx, [rsp+788h+var_6A0]
0x18005d4ee  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005d4f3  nop
0x18005d4f4  lea     rcx, [rsp+788h+var_730]
0x18005d4f9  call    ?SafeRelease@?$AutoCleanupInfo@PEAX@@SAXAEAPEAX@Z; AutoCleanupInfo<void *>::SafeRelease(void * &)
0x18005d4fe  nop
0x18005d4ff  mov     rcx, [rsp+788h+SecurityAttributes.lpSecurityDescriptor]
0x18005d504  test    rcx, rcx
0x18005d507  jz      short loc_18005D514
0x18005d509  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18005d50f  mov     [rsp+788h+SecurityAttributes.lpSecurityDescriptor], rdi
0x18005d514  mov     rcx, [rsi+8]; this
0x18005d518  test    rcx, rcx
0x18005d51b  jz      short loc_18005D522
0x18005d51d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005d522  xor     eax, eax
0x18005d524  jmp     loc_18005D41F
0x18005d529  mov     rcx, [rsp+788h]; this
0x18005d531  mov     r9d, ebx; char *
0x18005d534  lea     r8, aOnecoreWindows_105; "onecore\\windows\\accessibletech\\uiaut"...
0x18005d53b  mov     edx, 425h; void *
0x18005d540  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d545  nop
0x18005d546  mov     rcx, [rsp+788h+SecurityAttributes.lpSecurityDescriptor]
0x18005d54b  test    rcx, rcx
0x18005d54e  jz      short loc_18005D55B
0x18005d550  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18005d556  mov     [rsp+788h+SecurityAttributes.lpSecurityDescriptor], rdi
0x18005d55b  mov     rcx, [rsi+8]; this
0x18005d55f  test    rcx, rcx
0x18005d562  jz      short loc_18005D569
0x18005d564  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005d569  mov     eax, ebx
0x18005d56b  jmp     loc_18005D41F
0x18005d570  mov     rcx, [rsp+788h]; this
0x18005d578  mov     r9d, ebx; char *
0x18005d57b  lea     r8, aOnecoreWindows_105; "onecore\\windows\\accessibletech\\uiaut"...
0x18005d582  mov     edx, 419h; void *
0x18005d587  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d58c  nop
0x18005d58d  mov     rcx, [rsp+788h+SecurityAttributes.lpSecurityDescriptor]
0x18005d592  test    rcx, rcx
0x18005d595  jz      short loc_18005D5A2
0x18005d597  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18005d59d  mov     [rsp+788h+SecurityAttributes.lpSecurityDescriptor], rdi
0x18005d5a2  mov     rcx, [rsi+8]; this
0x18005d5a6  test    rcx, rcx
0x18005d5a9  jz      short loc_18005D5B0
0x18005d5ab  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005d5b0  mov     eax, ebx
0x18005d5b2  jmp     loc_18005D41F
0x18005d5b7  mov     rcx, [rsp+788h]; this
0x18005d5bf  mov     r9d, ebx; char *
0x18005d5c2  lea     r8, aOnecoreWindows_105; "onecore\\windows\\accessibletech\\uiaut"...
0x18005d5c9  mov     edx, 412h; void *
0x18005d5ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d5d3  nop
0x18005d5d4  mov     rcx, [rsp+788h+SecurityAttributes.lpSecurityDescriptor]
0x18005d5d9  test    rcx, rcx
0x18005d5dc  jz      short loc_18005D5E9
0x18005d5de  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18005d5e4  mov     [rsp+788h+SecurityAttributes.lpSecurityDescriptor], rdi
0x18005d5e9  mov     rcx, [rsi+8]; this
0x18005d5ed  test    rcx, rcx
0x18005d5f0  jz      short loc_18005D5F7
0x18005d5f2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005d5f7  mov     eax, ebx
0x18005d5f9  jmp     loc_18005D41F
0x18005d5fe  mov     rcx, [rsp+788h]; this
0x18005d606  mov     r9d, ebx; char *
0x18005d609  lea     r8, aOnecoreWindows_105; "onecore\\windows\\accessibletech\\uiaut"...
0x18005d610  mov     edx, 418h; void *
0x18005d615  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d61a  nop
0x18005d61b  mov     rcx, [rsp+788h+SecurityAttributes.lpSecurityDescriptor]
0x18005d620  test    rcx, rcx
0x18005d623  jz      short loc_18005D630
0x18005d625  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18005d62b  mov     [rsp+788h+SecurityAttributes.lpSecurityDescriptor], rdi
0x18005d630  mov     rcx, [rsi+8]; this
0x18005d634  test    rcx, rcx
0x18005d637  jz      short loc_18005D63E
0x18005d639  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005d63e  mov     eax, ebx
0x18005d640  jmp     loc_18005D41F
0x18005d645  mov     rcx, [rsp+788h]; this
0x18005d64d  mov     r9d, ebx; char *
0x18005d650  lea     r8, aOnecoreWindows_105; "onecore\\windows\\accessibletech\\uiaut"...
0x18005d657  mov     edx, 421h; void *
0x18005d65c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005d661  nop
0x18005d662  mov     rcx, [rsp+788h+SecurityAttributes.lpSecurityDescriptor]
0x18005d667  test    rcx, rcx
0x18005d66a  jz      short loc_18005D677
0x18005d66c  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18005d672  mov     [rsp+788h+SecurityAttributes.lpSecurityDescriptor], rdi
0x18005d677  mov     rcx, [rsi+8]; this
0x18005d67b  test    rcx, rcx
0x18005d67e  jz      short loc_18005D685
0x18005d680  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005d685  mov     eax, ebx
0x18005d687  jmp     loc_18005D41F
0x18005d68c  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005d691  mov     eax, dword ptr [rsp+788h+var_730]
0x18005d695  jmp     loc_18005D41F
0x18005d69a  lea     rdx, [rsp+788h+Name]
0x18005d6a2  lea     rcx, [rsp+788h+var_6E0]
0x18005d6aa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005d6af  nop
0x18005d6b0  lea     rdx, [rsp+788h+var_468]
0x18005d6b8  lea     rcx, [rsp+788h+var_700]
0x18005d6c0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005d6c5  nop
0x18005d6c6  mov     rcx, [rsi]
0x18005d6c9  mov     rax, [rcx]
0x18005d6cc  mov     rdx, [rsp+788h+var_720]
0x18005d6d1  mov     edx, [rdx+4]
0x18005d6d4  mov     rax, [rax+18h]
0x18005d6d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d6dd  mov     rcx, [rsi]
0x18005d6e0  mov     rax, [rcx]
0x18005d6e3  mov     r9d, [r14]
0x18005d6e6  lea     r8, [rsp+788h+var_700]
0x18005d6ee  lea     rdx, [rsp+788h+var_6E0]
0x18005d6f6  mov     rax, [rax+8]
0x18005d6fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d6ff  mov     r9, rsi
0x18005d702  lea     r8, [rsp+788h+var_700]
0x18005d70a  lea     rdx, [rsp+788h+var_6E0]
0x18005d712  lea     rcx, [rsp+788h+var_728]
0x18005d717  call    ??$make_unique@UCrossMachinePipeNameGuard@BasicUtils@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V34@AEAV?$shared_ptr@VICrossMachineCommunicationServices@@@4@$0A@@std@@YA?AV?$unique_ptr@UCrossMachinePipeNameGuard@BasicUtils@@U?$default_delete@UCrossMachinePipeNameGuard@BasicUtils@@@std@@@0@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0AEAV?$shared_ptr@VICrossMachineCommunicationServices@@@0@@Z; std::make_unique<BasicUtils::CrossMachinePipeNameGuard,std::wstring,std::wstring,std::shared_ptr<ICrossMachineCommunicationServices> &,0>(std::wstring &&,std::wstring &&,std::shared_ptr<ICrossMachineCommunicationServices> &)
0x18005d71c  lea     rdx, [rsp+788h+var_728]
0x18005d721  mov     rcx, r15
0x18005d724  call    ??$?4U?$default_delete@UCrossMachinePipeNameGuard@BasicUtils@@@std@@$0A@@?$unique_ptr@UCrossMachinePipeNameGuard@BasicUtils@@U?$default_delete@UCrossMachinePipeNameGuard@BasicUtils@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<BasicUtils::CrossMachinePipeNameGuard>::operator=<std::default_delete<BasicUtils::CrossMachinePipeNameGuard>,0>(std::unique_ptr<BasicUtils::CrossMachinePipeNameGuard> &&)
0x18005d729  mov     rdx, [rsp+788h+var_728]
0x18005d72e  test    rdx, rdx
0x18005d731  jnz     short loc_18005D79A
0x18005d733  lea     rcx, [rsp+788h+var_700]
0x18005d73b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005d740  nop
0x18005d741  lea     rcx, [rsp+788h+var_6E0]
0x18005d749  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005d74e  jmp     loc_18005D467
0x18005d753  call    ??R?$default_delete@UCrossMachinePipeNameGuard@BasicUtils@@@std@@QEBAXPEAUCrossMachinePipeNameGuard@BasicUtils@@@Z; std::default_delete<BasicUtils::CrossMachinePipeNameGuard>::operator()(BasicUtils::CrossMachinePipeNameGuard *)
0x18005d758  jmp     loc_18005D2CD
0x18005d75d  mov     ecx, eax; unsigned int
0x18005d75f  call    ?IsAppContainer@BasicUtils@@SA_NI@Z; BasicUtils::IsAppContainer(uint)
0x18005d764  test    al, al
0x18005d766  jz      loc_18005D367
0x18005d76c  lea     r9, [rsp+788h+var_468]
  ... truncated ...
```
