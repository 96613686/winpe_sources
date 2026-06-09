# PbrVdsServiceCache::Get(IVdsService * *)

- ea: `0x180045294`
- end: `0x1800455ec`
- name: `?Get@PbrVdsServiceCache@@SAJPEAPEAUIVdsService@@@Z`
- size: `856`
- prototype: `__int64 __fastcall(struct IVdsService **)`
- caller_count: `12`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180039968`
- `0x18003a678`
- `0x18003ba10`
- `0x18003bbf4`
- `0x18003bdd8`
- `0x18003d700`
- `0x18003f4b8`
- `0x180041cb0`
- `0x1800455f4`
- `0x18004743c`
- `0x18004767c`
- `0x180049114`

## callees

- `0x180005cc0`
- `0x180023620`
- `0x180037344`
- `0x180045294`
- `0x18006f010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800452ed`
- `KERNEL32!LeaveCriticalSection` at `0x1800452ed`
- `KERNEL32!EnterCriticalSection` at `0x1800452b0`
- `KERNEL32!EnterCriticalSection` at `0x1800452b0`
- `KERNEL32!GetLastError` at `0x1800452d1`
- `KERNEL32!GetLastError` at `0x18004556c`
- `KERNEL32!GetLastError` at `0x1800455ac`
- `KERNEL32!GetLastError` at `0x1800452d1`
- `KERNEL32!GetLastError` at `0x18004556c`
- `KERNEL32!GetLastError` at `0x1800455ac`
- `KERNEL32!TlsAlloc` at `0x1800452c1`
- `KERNEL32!TlsAlloc` at `0x1800452c1`
- `KERNEL32!TlsGetValue` at `0x180045330`
- `KERNEL32!TlsGetValue` at `0x180045330`
- `KERNEL32!TlsSetValue` at `0x180045512`
- `KERNEL32!TlsSetValue` at `0x180045512`
- `ole32!CoCreateInstance` at `0x18004538c`
- `ole32!CoCreateInstance` at `0x18004538c`

## string_xrefs

- `0x1800452f7`: `Failed to initialize thread local storage`
- `0x180045312`: `PbrVdsServiceCache::Get`
- `0x1800453b3`: `PbrVdsServiceCache::Get`
- `0x18004544a`: `PbrVdsServiceCache::Get`
- `0x1800454c3`: `PbrVdsServiceCache::Get`
- `0x180045599`: `PbrVdsServiceCache::Get`
- `0x180045398`: `Failed to create VDS loader`
- `0x18004542f`: `Failed to create the VDS service`
- `0x18004557e`: `Failed to write service object pointer to thread local storage`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PbrVdsServiceCache::Get(struct IVdsService **a1)
{
  int Instance; // ebx
  signed int LastError; // eax
  struct IVdsService *Value; // rax
  struct IVdsService *v5; // rdi
  LPVOID *ppv; // rax
  __int64 v7; // rdi
  __int64 (__fastcall *v8)(__int64, _QWORD, __int64); // rbx
  __int64 v9; // rax
  __int64 v10; // rax
  void *v11; // rax
  __int64 v12; // rax
  struct IVdsService *v13; // rax
  signed int v14; // eax
  signed int v15; // eax
  void **v17; // [rsp+30h] [rbp-28h] BYREF
  struct IVdsService *v18; // [rsp+38h] [rbp-20h]
  _QWORD v19[3]; // [rsp+40h] [rbp-18h] BYREF

  Instance = 0;
  EnterCriticalSection(&PbrVdsServiceCache::Lock);
  if ( PbrVdsServiceCache::hTLS == -1 )
  {
    PbrVdsServiceCache::hTLS = TlsAlloc();
    if ( PbrVdsServiceCache::hTLS == -1 )
    {
      LastError = GetLastError();
      Instance = LastError;
      if ( LastError > 0 )
        Instance = (unsigned __int16)LastError | 0x80070000;
    }
  }
  LeaveCriticalSection(&PbrVdsServiceCache::Lock);
  if ( Instance >= 0 )
  {
    Value = (struct IVdsService *)TlsGetValue(PbrVdsServiceCache::hTLS);
    v5 = Value;
    if ( Value )
    {
      ((void (__fastcall *)(struct IVdsService *))Value->lpVtbl->AddRef)(Value);
      *a1 = v5;
    }
    else
    {
      v19[1] = 0;
      v19[0] = &RAII::CAutoRelease<IVdsServiceLoader *>::`vftable';
      ppv = (LPVOID *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v19);
      Instance = CoCreateInstance(&CLSID_VdsLoader, 0, 0x10004u, &IID_IVdsServiceLoader, ppv);
      if ( Instance >= 0 )
      {
        v18 = 0;
        v17 = &RAII::CAutoRelease<IVdsService *>::`vftable';
        v7 = (*(__int64 (__fastcall **)(_QWORD *))(v19[0] + 24LL))(v19);
        v8 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v7 + 24LL);
        v9 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v17);
        Instance = v8(v7, 0, v9);
        if ( Instance >= 0 )
        {
          v10 = ((__int64 (__fastcall *)(void ***))v17[3])(&v17);
          Instance = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 32LL))(v10);
          if ( Instance >= 0 )
          {
            v11 = (void *)((__int64 (__fastcall *)(void ***))v17[4])(&v17);
            if ( TlsSetValue(PbrVdsServiceCache::hTLS, v11) )
            {
              v12 = ((__int64 (__fastcall *)(void ***))v17[3])(&v17);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 8LL))(v12);
              v13 = v18;
              v18 = 0;
              *a1 = v13;
              v17 = &RAII::CAutoRelease<IVdsService *>::`vftable';
              RAII::CAutoRelease<IXMLDOMParseError *>::Release(&v17);
              v19[0] = &RAII::CAutoRelease<IVdsServiceLoader *>::`vftable';
              RAII::CAutoRelease<IXMLDOMParseError *>::Release(v19);
            }
            else
            {
              v14 = GetLastError();
              if ( v14 > 0 )
                v14 = (unsigned __int16)v14 | 0x80070000;
              PushButtonReset::Logging::TraceErr(
                2,
                (unsigned int)v14,
                "PbrVdsServiceCache::Get",
                "base\\reset\\util\\src\\diskpart.cpp",
                106,
                L"Failed to write service object pointer to thread local storage");
              v15 = GetLastError();
              Instance = v15;
              if ( v15 > 0 )
                Instance = (unsigned __int16)v15 | 0x80070000;
              v17 = &RAII::CAutoRelease<IVdsService *>::`vftable';
              RAII::CAutoRelease<IXMLDOMParseError *>::Release(&v17);
              v19[0] = &RAII::CAutoRelease<IVdsServiceLoader *>::`vftable';
              RAII::CAutoRelease<IXMLDOMParseError *>::Release(v19);
            }
          }
          else
          {
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)Instance,
              "PbrVdsServiceCache::Get",
              "base\\reset\\util\\src\\diskpart.cpp",
              97,
              L"Failed to wait for VDS to initialize");
            v17 = &RAII::CAutoRelease<IVdsService *>::`vftable';
            RAII::CAutoRelease<IXMLDOMParseError *>::Release(&v17);
            v19[0] = &RAII::CAutoRelease<IVdsServiceLoader *>::`vftable';
            RAII::CAutoRelease<IXMLDOMParseError *>::Release(v19);
          }
        }
        else
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)Instance,
            "PbrVdsServiceCache::Get",
            "base\\reset\\util\\src\\diskpart.cpp",
            94,
            L"Failed to create the VDS service");
          v17 = &RAII::CAutoRelease<IVdsService *>::`vftable';
          RAII::CAutoRelease<IXMLDOMParseError *>::Release(&v17);
          v19[0] = &RAII::CAutoRelease<IVdsServiceLoader *>::`vftable';
          RAII::CAutoRelease<IXMLDOMParseError *>::Release(v19);
        }
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Instance,
          "PbrVdsServiceCache::Get",
          "base\\reset\\util\\src\\diskpart.cpp",
          90,
          L"Failed to create VDS loader");
        v19[0] = &RAII::CAutoRelease<IVdsServiceLoader *>::`vftable';
        RAII::CAutoRelease<IXMLDOMParseError *>::Release(v19);
      }
    }
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Instance,
      "PbrVdsServiceCache::Get",
      "base\\reset\\util\\src\\diskpart.cpp",
      68,
      L"Failed to initialize thread local storage");
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180045294  push    rbp
0x180045296  push    rbx
0x180045297  push    rsi
0x180045298  push    rdi
0x180045299  push    r13
0x18004529b  push    r15
0x18004529d  mov     rbp, rsp
0x1800452a0  sub     rsp, 58h
0x1800452a4  mov     rsi, rcx
0x1800452a7  xor     ebx, ebx
0x1800452a9  lea     rcx, ?Lock@PbrVdsServiceCache@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800452b0  call    cs:__imp_EnterCriticalSection
0x1800452b6  or      edi, 0FFFFFFFFh
0x1800452b9  cmp     cs:?hTLS@PbrVdsServiceCache@@0KA, edi; ulong PbrVdsServiceCache::hTLS
0x1800452bf  jnz     short loc_1800452E6
0x1800452c1  call    cs:__imp_TlsAlloc
0x1800452c7  mov     cs:?hTLS@PbrVdsServiceCache@@0KA, eax; ulong PbrVdsServiceCache::hTLS
0x1800452cd  cmp     eax, edi
0x1800452cf  jnz     short loc_1800452E6
0x1800452d1  call    cs:__imp_GetLastError
0x1800452d7  mov     ebx, eax
0x1800452d9  test    eax, eax
0x1800452db  jle     short loc_1800452E6
0x1800452dd  movzx   ebx, ax
0x1800452e0  or      ebx, 80070000h
0x1800452e6  lea     rcx, ?Lock@PbrVdsServiceCache@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800452ed  call    cs:__imp_LeaveCriticalSection
0x1800452f3  test    ebx, ebx
0x1800452f5  jns     short loc_18004532A
0x1800452f7  lea     rax, aFailedToInitia_5; "Failed to initialize thread local stora"...
0x1800452fe  mov     [rsp+58h+var_30], rax
0x180045303  mov     dword ptr [rsp+58h+ppv], 44h ; 'D'
0x18004530b  lea     r9, aBaseResetUtilS_2; "base\\reset\\util\\src\\diskpart.cpp"
0x180045312  lea     r8, aPbrvdsservicec; "PbrVdsServiceCache::Get"
0x180045319  mov     edx, ebx
0x18004531b  mov     ecx, 2
0x180045320  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180045325  jmp     loc_1800455DD
0x18004532a  mov     ecx, cs:?hTLS@PbrVdsServiceCache@@0KA; dwTlsIndex
0x180045330  call    cs:__imp_TlsGetValue
0x180045336  mov     rdi, rax
0x180045339  test    rax, rax
0x18004533c  jz      short loc_180045355
0x18004533e  mov     rcx, [rax]
0x180045341  mov     rax, [rcx+8]
0x180045345  mov     rcx, rdi
0x180045348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004534d  mov     [rsi], rdi
0x180045350  jmp     loc_1800455DD
0x180045355  mov     [rbp+var_10], 0
0x18004535d  lea     r15, ??_7?$CAutoRelease@PEAUIVdsServiceLoader@@@RAII@@6B@; const RAII::CAutoRelease<IVdsServiceLoader *>::`vftable'
0x180045364  mov     [rbp+var_18], r15
0x180045368  lea     rcx, [rbp+var_18]
0x18004536c  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180045371  mov     [rsp+58h+ppv], rax; ppv
0x180045376  lea     r9, IID_IVdsServiceLoader; riid
0x18004537d  xor     edx, edx; pUnkOuter
0x18004537f  mov     r8d, 10004h; dwClsContext
0x180045385  lea     rcx, CLSID_VdsLoader; rclsid
0x18004538c  call    cs:__imp_CoCreateInstance
0x180045392  mov     ebx, eax
0x180045394  test    eax, eax
0x180045396  jns     short loc_1800453DA
0x180045398  lea     rax, aFailedToCreate_11; "Failed to create VDS loader"
0x18004539f  mov     [rsp+58h+var_30], rax
0x1800453a4  mov     dword ptr [rsp+58h+ppv], 5Ah ; 'Z'
0x1800453ac  lea     r9, aBaseResetUtilS_2; "base\\reset\\util\\src\\diskpart.cpp"
0x1800453b3  lea     r8, aPbrvdsservicec; "PbrVdsServiceCache::Get"
0x1800453ba  mov     edx, ebx
0x1800453bc  mov     ecx, 2
0x1800453c1  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800453c6  nop
0x1800453c7  mov     [rbp+var_18], r15
0x1800453cb  lea     rcx, [rbp+var_18]
0x1800453cf  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x1800453d4  nop
0x1800453d5  jmp     loc_1800455DD
0x1800453da  mov     [rbp+var_20], 0
0x1800453e2  lea     r13, ??_7?$CAutoRelease@PEAUIVdsService@@@RAII@@6B@; const RAII::CAutoRelease<IVdsService *>::`vftable'
0x1800453e9  mov     [rbp+var_28], r13
0x1800453ed  mov     rax, [rbp+var_18]
0x1800453f1  lea     rcx, [rbp+var_18]
0x1800453f5  mov     rax, [rax+18h]
0x1800453f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800453fe  mov     rdi, rax
0x180045401  mov     rcx, [rax]
0x180045404  mov     rbx, [rcx+18h]
0x180045408  mov     rcx, [rbp+var_28]
0x18004540c  mov     rax, [rcx+8]
0x180045410  lea     rcx, [rbp+var_28]
0x180045414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045419  mov     r8, rax
0x18004541c  xor     edx, edx
0x18004541e  mov     rcx, rdi
0x180045421  mov     rax, rbx
0x180045424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045429  mov     ebx, eax
0x18004542b  test    eax, eax
0x18004542d  jns     short loc_18004547F
0x18004542f  lea     rax, aFailedToCreate_29; "Failed to create the VDS service"
0x180045436  mov     [rsp+58h+var_30], rax
0x18004543b  mov     dword ptr [rsp+58h+ppv], 5Eh ; '^'
0x180045443  lea     r9, aBaseResetUtilS_2; "base\\reset\\util\\src\\diskpart.cpp"
0x18004544a  lea     r8, aPbrvdsservicec; "PbrVdsServiceCache::Get"
0x180045451  mov     edx, ebx
0x180045453  mov     ecx, 2
0x180045458  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004545d  nop
0x18004545e  mov     [rbp+var_28], r13
0x180045462  lea     rcx, [rbp+var_28]
0x180045466  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18004546b  nop
0x18004546c  mov     [rbp+var_18], r15
0x180045470  lea     rcx, [rbp+var_18]
0x180045474  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x180045479  nop
0x18004547a  jmp     loc_1800455DD
0x18004547f  mov     rax, [rbp+var_28]
0x180045483  lea     rcx, [rbp+var_28]
0x180045487  mov     rax, [rax+18h]
0x18004548b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045490  mov     rdx, rax
0x180045493  mov     rcx, [rax]
0x180045496  mov     rax, [rcx+20h]
0x18004549a  mov     rcx, rdx
0x18004549d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800454a2  mov     ebx, eax
0x1800454a4  test    eax, eax
0x1800454a6  jns     short loc_1800454F8
0x1800454a8  lea     rax, aFailedToWaitFo_0; "Failed to wait for VDS to initialize"
0x1800454af  mov     [rsp+58h+var_30], rax
0x1800454b4  mov     dword ptr [rsp+58h+ppv], 61h ; 'a'
0x1800454bc  lea     r9, aBaseResetUtilS_2; "base\\reset\\util\\src\\diskpart.cpp"
0x1800454c3  lea     r8, aPbrvdsservicec; "PbrVdsServiceCache::Get"
0x1800454ca  mov     edx, ebx
0x1800454cc  mov     ecx, 2
0x1800454d1  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800454d6  nop
0x1800454d7  mov     [rbp+var_28], r13
0x1800454db  lea     rcx, [rbp+var_28]
0x1800454df  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x1800454e4  nop
0x1800454e5  mov     [rbp+var_18], r15
0x1800454e9  lea     rcx, [rbp+var_18]
0x1800454ed  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x1800454f2  nop
0x1800454f3  jmp     loc_1800455DD
0x1800454f8  mov     rax, [rbp+var_28]
0x1800454fc  lea     rcx, [rbp+var_28]
0x180045500  mov     rax, [rax+20h]
0x180045504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045509  mov     rdx, rax; lpTlsValue
0x18004550c  mov     ecx, cs:?hTLS@PbrVdsServiceCache@@0KA; dwTlsIndex
0x180045512  call    cs:__imp_TlsSetValue
0x180045518  test    eax, eax
0x18004551a  jz      short loc_18004556C
0x18004551c  mov     rax, [rbp+var_28]
0x180045520  lea     rcx, [rbp+var_28]
0x180045524  mov     rax, [rax+18h]
0x180045528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004552d  mov     rdx, rax
0x180045530  mov     rcx, [rax]
0x180045533  mov     rax, [rcx+8]
0x180045537  mov     rcx, rdx
0x18004553a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004553f  mov     rax, [rbp+var_20]
0x180045543  mov     [rbp+var_20], 0
0x18004554b  mov     [rsi], rax
0x18004554e  mov     [rbp+var_28], r13
0x180045552  lea     rcx, [rbp+var_28]
0x180045556  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18004555b  nop
0x18004555c  mov     [rbp+var_18], r15
0x180045560  lea     rcx, [rbp+var_18]
0x180045564  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x180045569  nop
0x18004556a  jmp     short loc_1800455DD
0x18004556c  call    cs:__imp_GetLastError
0x180045572  test    eax, eax
0x180045574  jle     short loc_18004557E
0x180045576  movzx   eax, ax
0x180045579  or      eax, 80070000h
0x18004557e  lea     rcx, aFailedToWriteS_4; "Failed to write service object pointer "...
0x180045585  mov     [rsp+58h+var_30], rcx
0x18004558a  mov     dword ptr [rsp+58h+ppv], 6Ah ; 'j'
0x180045592  lea     r9, aBaseResetUtilS_2; "base\\reset\\util\\src\\diskpart.cpp"
0x180045599  lea     r8, aPbrvdsservicec; "PbrVdsServiceCache::Get"
0x1800455a0  mov     edx, eax
0x1800455a2  mov     ecx, 2
0x1800455a7  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800455ac  call    cs:__imp_GetLastError
0x1800455b2  mov     ebx, eax
0x1800455b4  test    eax, eax
0x1800455b6  jle     short loc_1800455C1
0x1800455b8  movzx   ebx, ax
0x1800455bb  or      ebx, 80070000h
0x1800455c1  mov     [rbp+var_28], r13
0x1800455c5  lea     rcx, [rbp+var_28]
0x1800455c9  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x1800455ce  nop
0x1800455cf  mov     [rbp+var_18], r15
0x1800455d3  lea     rcx, [rbp+var_18]
0x1800455d7  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x1800455dc  nop
0x1800455dd  mov     eax, ebx
0x1800455df  add     rsp, 58h
0x1800455e3  pop     r15
0x1800455e5  pop     r13
0x1800455e7  pop     rdi
0x1800455e8  pop     rsi
0x1800455e9  pop     rbx
0x1800455ea  pop     rbp
0x1800455eb  retn
```
