# Appx::Packaging::UndockingFactory::LoadExtension(Appx::Packaging::PackagingExtension const *,_GUID const &,void * *)

- ea: `0x1800b5298`
- end: `0x1800b57eb`
- name: `?LoadExtension@UndockingFactory@Packaging@Appx@@AEAAJPEBUPackagingExtension@23@AEBU_GUID@@PEAPEAX@Z`
- size: `1363`
- prototype: `__int64 __fastcall(Appx::Packaging::UndockingFactory *__hidden this, const struct Appx::Packaging::PackagingExtension *, const struct _GUID *, void **)`
- caller_count: `24`
- callee_count: `21`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800ad6e4`
- `0x1800ad920`
- `0x1800adb5c`
- `0x1800add98`
- `0x1800adfd4`
- `0x1800ae210`
- `0x1800ae44c`
- `0x1800ae688`
- `0x1800ae8c4`
- `0x1800aeb00`
- `0x1800aed3c`
- `0x1800aef78`
- `0x1800af1b4`
- `0x1800af3e4`
- `0x1800af614`
- `0x1800af844`
- `0x1800afa74`
- `0x1800afcb0`
- `0x1800afeec`
- `0x1800b0128`
- `0x1800b0358`
- `0x1800b0594`
- `0x1800b07d0`
- `0x1800b5a90`

## callees

- `0x180001008`
- `0x1800016b8`
- `0x1800059f0`
- `0x180005eb8`
- `0x1800133fc`
- `0x18002a224`
- `0x1800446d0`
- `0x18005307c`
- `0x18005bc44`
- `0x18006a900`
- `0x18006b818`
- `0x1800992d0`
- `0x1800a5ad4`
- `0x1800a5d1c`
- `0x1800ab28c`
- `0x1800b1908`
- `0x1800b4d7c`
- `0x1800b5298`
- `0x1800b5e40`
- `0x1800d3f38`
- `0x180106010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b5374`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b5584`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b5374`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b5584`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800b5355`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800b5355`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800b54f8`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800b54f8`
- `api-ms-win-appmodel-runtime-l1-1-5!TryCreatePackageDependency` at `0x1800b5473`
- `api-ms-win-appmodel-runtime-l1-1-5!TryCreatePackageDependency` at `0x1800b5473`
- `api-ms-win-appmodel-runtime-l1-1-5!AddPackageDependency` at `0x1800b54bc`
- `api-ms-win-appmodel-runtime-l1-1-5!AddPackageDependency` at `0x1800b54bc`

## string_xrefs

- `0x1800b53a1`: `onecore\printscan\appxpackaging\dll\lib\undocking.cpp`
- `0x1800b549a`: `onecore\printscan\appxpackaging\dll\lib\undocking.cpp`
- `0x1800b5526`: `onecore\printscan\appxpackaging\dll\lib\undocking.cpp`
- `0x1800b559c`: `onecore\printscan\appxpackaging\dll\lib\undocking.cpp`
- `0x1800b55e3`: `onecore\printscan\appxpackaging\dll\lib\undocking.cpp`
- `0x1800b5640`: `onecore\printscan\appxpackaging\dll\lib\undocking.cpp`
- `0x1800b56b4`: `onecore\printscan\appxpackaging\dll\lib\undocking.cpp`
- `0x1800b5734`: `onecore\printscan\appxpackaging\dll\lib\undocking.cpp`
- `0x1800b57ab`: `onecore\printscan\appxpackaging\dll\lib\undocking.cpp`
- `0x1800b536d`: `IsPackagingExtensionBeingServiced`
- `0x1800b53b9`: `Not loading extension from %s, package is being serviced`
- `0x1800b551b`: `DllPath=%s`
- `0x1800b557a`: `GetPackagingExtension`
- `0x1800b5656`: `Version from dll=0x%llX, Version from manifest=0x%llX`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::UndockingFactory::LoadExtension(
        Appx::Packaging::UndockingFactory *this,
        const struct Appx::Packaging::PackagingExtension *a2,
        const struct _GUID *a3,
        void **a4)
{
  const unsigned __int16 *v7; // rbx
  Appx::Packaging::UndockingFactory *v8; // rdi
  __int64 v9; // rcx
  char *v10; // rax
  HMODULE *v11; // rbx
  FARPROC ProcAddress; // rax
  char v13; // di
  int PackageDependency; // edi
  HMODULE v15; // rsi
  __int64 v16; // rcx
  int v17; // r9d
  __int64 v18; // rdx
  unsigned __int64 v19; // r9
  __int64 v20; // rdx
  int v21; // eax
  int v22; // eax
  HMODULE LibraryW; // rax
  const struct _tlgProvider_t *v24; // rax
  int v25; // r8d
  int v26; // r9d
  FARPROC v27; // rdi
  const char *v28; // r9
  int v29; // eax
  __int64 v30; // rdx
  struct _GUID v31; // xmm0
  __int64 v32; // rax
  __int64 *v33; // rsi
  __int64 (__fastcall *v34)(__int64 *, int *, _QWORD); // rdi
  int v35; // eax
  __int64 v36; // rdx
  int v37; // eax
  __int64 v38; // rcx
  __int64 v39; // rdx
  int v41; // [rsp+20h] [rbp-60h]
  __int64 (__fastcall ***v42)(_QWORD, const struct _GUID *, void **); // [rsp+40h] [rbp-40h] BYREF
  _BYTE v43[8]; // [rsp+48h] [rbp-38h] BYREF
  HMODULE phModule; // [rsp+50h] [rbp-30h] BYREF
  char *v45; // [rsp+58h] [rbp-28h] BYREF
  int v46[4]; // [rsp+60h] [rbp-20h] BYREF
  char v47; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]
  Appx::Packaging::UndockingFactory *v49; // [rsp+C0h] [rbp+40h] BYREF
  __int64 *v50; // [rsp+C8h] [rbp+48h] BYREF

  v49 = this;
  wil::AcquireSRWLockExclusive(v43, &g_extensionModulesLock);
  v7 = (const unsigned __int16 *)*((_QWORD *)a2 + 4);
  v8 = 0;
  if ( !qword_180169EF8 )
    goto LABEL_4;
  while ( !Common::String::CaseInsensitiveEquals(
             v7,
             *(const unsigned __int16 **)(*((_QWORD *)g_extensionModules + (_QWORD)v8) + 16LL)) )
  {
    v8 = (Appx::Packaging::UndockingFactory *)((char *)v8 + 1);
    if ( (unsigned __int64)v8 >= qword_180169EF8 )
      goto LABEL_4;
  }
  if ( v8 == (Appx::Packaging::UndockingFactory *)0x40000000 )
  {
LABEL_4:
    v10 = (char *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
    v11 = (HMODULE *)v10;
    if ( !v10 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x25,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\undocking.cpp",
        (const char *)0x8007000ELL,
        v41);
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v43);
      return 2147942414LL;
    }
    *(_QWORD *)v10 = 0;
    *((_QWORD *)v10 + 3) = 0;
    *(_OWORD *)(v10 + 8) = 0;
    *((_QWORD *)v10 + 4) = 0;
    *((_QWORD *)v10 + 5) = 0;
    phModule = 0;
    if ( GetModuleHandleExW(2u, L"AppXDeploymentServer", &phModule) )
    {
      ProcAddress = GetProcAddress(phModule, "IsPackagingExtensionBeingServiced");
      if ( ProcAddress )
      {
        v13 = 1;
        if ( ((unsigned int (__fastcall *)(_QWORD))ProcAddress)(*((_QWORD *)a2 + 1)) )
        {
          PackageDependency = -2147009278;
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x34,
            (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\undocking.cpp",
            (const char *)0x80073D02LL,
            (int)"Not loading extension from %s, package is being serviced",
            *((const char **)a2 + 1));
          goto LABEL_47;
        }
        goto LABEL_20;
      }
    }
    v18 = *((_QWORD *)a2 + 1);
    *(_QWORD *)v46 = v11 + 4;
    *(_QWORD *)&v46[2] = 0;
    v47 = 1;
    PackageDependency = TryCreatePackageDependency(0, v18, 0, 0);
    wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::process_heap_deleter>>(v46);
    if ( PackageDependency >= 0 )
    {
      v41 = 0;
      v21 = AddPackageDependency(v11[4], 0, 0, v11 + 5);
      PackageDependency = v21;
      if ( v21 >= 0 )
      {
        v22 = Appx::Packaging::UndockedExtensionsReader::VerifyExtensionDllSignature(*((const unsigned __int16 **)a2 + 4));
        PackageDependency = v22;
        if ( v22 >= 0 )
        {
          v13 = 0;
LABEL_20:
          LibraryW = LoadLibraryW(*((LPCWSTR *)a2 + 4));
          wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
            v11,
            LibraryW);
          v15 = *v11;
          if ( !*v11 )
          {
            PackageDependency = wil::details::in1diag3::Return_GetLastErrorMsg(
                                  retaddr,
                                  (void *)0x43,
                                  (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\undocking.cpp",
                                  "DllPath=%s",
                                  *((const char **)a2 + 4));
            goto LABEL_47;
          }
          v24 = Appx::Packaging::AppxPackagingProvider::Provider();
          if ( *(_DWORD *)v24 > 5u )
          {
            *(_QWORD *)v46 = *((_QWORD *)a2 + 4);
            LOBYTE(v49) = v13;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>>(
              (_DWORD)v24,
              (unsigned int)&dword_180159644,
              v25,
              v26,
              (__int64)v46,
              (__int64)&v49);
          }
          goto LABEL_24;
        }
        v19 = (unsigned int)v22;
        v20 = 62;
      }
      else
      {
        v19 = (unsigned int)v21;
        v20 = 61;
      }
    }
    else
    {
      v19 = (unsigned int)PackageDependency;
      v20 = 60;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\undocking.cpp",
      (const char *)v19,
      0);
    goto LABEL_47;
  }
  v11 = 0;
  v15 = *(HMODULE *)Common::Array<Appx::Packaging::LoadedExtension,Common::ContainerOperations<Appx::Packaging::LoadedExtension,Appx::Packaging::LoadedExtension>,unsigned short,Common::ContainerOperations<unsigned short,Appx::Packaging::LoadedExtension>,Common::ArrayOperations<Appx::Packaging::LoadedExtension,unsigned short>>::operator[](
                      v9,
                      v8);
  v16 = *(unsigned int *)Appx::Packaging::AppxPackagingProvider::Provider();
  if ( (unsigned int)v16 > 5 )
  {
    v49 = v8;
    phModule = *(HMODULE *)(Common::Array<Appx::Packaging::LoadedExtension,Common::ContainerOperations<Appx::Packaging::LoadedExtension,Appx::Packaging::LoadedExtension>,unsigned short,Common::ContainerOperations<unsigned short,Appx::Packaging::LoadedExtension>,Common::ArrayOperations<Appx::Packaging::LoadedExtension,unsigned short>>::operator[](
                              v16,
                              v8)
                          + 16);
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      v17,
      (unsigned int)byte_18015960B,
      0,
      v17,
      (__int64)&phModule,
      (__int64)&v49);
  }
LABEL_24:
  v27 = GetProcAddress(v15, "GetPackagingExtension");
  if ( !v27 )
  {
    PackageDependency = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x56,
                          (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\undocking.cpp",
                          v28);
    goto LABEL_26;
  }
  v50 = 0;
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v50);
  v29 = ((__int64 (__fastcall *)(__int64 **))v27)(&v50);
  PackageDependency = v29;
  if ( v29 < 0 )
  {
    v30 = 89;
LABEL_30:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v30,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\undocking.cpp",
      (const char *)(unsigned int)v29,
      v41);
LABEL_31:
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v50);
LABEL_26:
    if ( !v11 )
    {
LABEL_48:
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v43);
      return (unsigned int)PackageDependency;
    }
LABEL_47:
    Appx::Packaging::LoadedExtension::`scalar deleting destructor'((Appx::Packaging::LoadedExtension *)v11, 1u);
    goto LABEL_48;
  }
  v31 = *a3;
  v45 = 0;
  v32 = *v50;
  *(struct _GUID *)v46 = v31;
  v29 = (*(__int64 (__fastcall **)(__int64 *, int *, char **))(v32 + 24))(v50, v46, &v45);
  PackageDependency = v29;
  if ( v29 < 0 )
  {
    v30 = 92;
    goto LABEL_30;
  }
  if ( v45 != *((char **)a2 + 8) )
  {
    PackageDependency = -2147024885;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x5D,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\undocking.cpp",
      (const char *)0x8007000BLL,
      (int)"Version from dll=0x%llX, Version from manifest=0x%llX",
      v45,
      *((_QWORD *)a2 + 8));
    goto LABEL_31;
  }
  v33 = v50;
  v42 = 0;
  v34 = *(__int64 (__fastcall **)(__int64 *, int *, _QWORD))(*v50 + 32);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v42);
  *(struct _GUID *)v46 = *a3;
  v35 = v34(v33, v46, &v42);
  PackageDependency = v35;
  if ( v35 < 0 )
  {
    v36 = 96;
LABEL_38:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v36,
      (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\undocking.cpp",
      (const char *)(unsigned int)v35,
      v41);
    Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v42);
    goto LABEL_31;
  }
  v35 = (**v42)(v42, a3, a4);
  PackageDependency = v35;
  if ( v35 < 0 )
  {
    v36 = 97;
    goto LABEL_38;
  }
  if ( v11 )
  {
    v37 = Common::StringBuffer::SetValueFromString(
            (Common::StringBuffer *)(v11 + 1),
            *((const unsigned __int16 **)a2 + 4));
    PackageDependency = v37;
    if ( v37 < 0 )
    {
      v39 = 101;
LABEL_46:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v39,
        (unsigned int)"onecore\\printscan\\appxpackaging\\dll\\lib\\undocking.cpp",
        (const char *)(unsigned int)v37,
        v41);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v42);
      Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v50);
      goto LABEL_47;
    }
    v37 = Common::Array<Appx::Packaging::LoadedExtension,Common::ContainerOperations<Appx::Packaging::LoadedExtension,Appx::Packaging::LoadedExtension>,unsigned short,Common::ContainerOperations<unsigned short,Appx::Packaging::LoadedExtension>,Common::ArrayOperations<Appx::Packaging::LoadedExtension,unsigned short>>::EnsureCapacity(
            v38,
            qword_180169EF8 + 1);
    PackageDependency = v37;
    if ( v37 < 0 )
    {
      v39 = 102;
      goto LABEL_46;
    }
    *((_QWORD *)g_extensionModules + qword_180169EF8++) = v11;
  }
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v42);
  Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(&v50);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(v43);
  return 0;
}

```

## disassembly

```asm
0x1800b5298  mov     [rsp-38h+arg_10], rbx
0x1800b529d  mov     [rsp-38h+arg_0], rcx
0x1800b52a2  push    rbp
0x1800b52a3  push    rsi
0x1800b52a4  push    rdi
0x1800b52a5  push    r12
0x1800b52a7  push    r13
0x1800b52a9  push    r14
0x1800b52ab  push    r15
0x1800b52ad  mov     rbp, rsp
0x1800b52b0  sub     rsp, 80h
0x1800b52b7  mov     r14, rdx
0x1800b52ba  lea     rcx, [rbp+var_38]
0x1800b52be  lea     rdx, ?g_extensionModulesLock@@3Vsrwlock@wil@@A; wil::srwlock g_extensionModulesLock
0x1800b52c5  mov     r12, r9
0x1800b52c8  mov     r15, r8
0x1800b52cb  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1800b52d0  mov     rbx, [r14+20h]
0x1800b52d4  xor     r13d, r13d
0x1800b52d7  cmp     cs:qword_180169EF8, r13
0x1800b52de  mov     edi, r13d
0x1800b52e1  jbe     short loc_1800B530E
0x1800b52e3  mov     rax, cs:?g_extensionModules@@3V?$Array@ULoadedExtension@Packaging@Appx@@V?$ContainerOperations@ULoadedExtension@Packaging@Appx@@U123@@Common@@GV?$ContainerOperations@GULoadedExtension@Packaging@Appx@@@5@V?$ArrayOperations@ULoadedExtension@Packaging@Appx@@G@5@@Common@@A; Common::Array<Appx::Packaging::LoadedExtension,Common::ContainerOperations<Appx::Packaging::LoadedExtension,Appx::Packaging::LoadedExtension>,ushort,Common::ContainerOperations<ushort,Appx::Packaging::LoadedExtension>,Common::ArrayOperations<Appx::Packaging::LoadedExtension,ushort>> g_extensionModules
0x1800b52ea  mov     rcx, rbx; unsigned __int16 *
0x1800b52ed  mov     rdx, [rax+rdi*8]
0x1800b52f1  mov     rdx, [rdx+10h]; unsigned __int16 *
0x1800b52f5  call    ?CaseInsensitiveEquals@String@Common@@SAHPEBG0@Z; Common::String::CaseInsensitiveEquals(ushort const *,ushort const *)
0x1800b52fa  test    eax, eax
0x1800b52fc  jnz     loc_1800B53D4
0x1800b5302  inc     rdi
0x1800b5305  cmp     rdi, cs:qword_180169EF8
0x1800b530c  jb      short loc_1800B52E3
0x1800b530e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800b5315  mov     ecx, 30h ; '0'; unsigned __int64
0x1800b531a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800b531f  mov     rbx, rax
0x1800b5322  test    rax, rax
0x1800b5325  jz      loc_1800B57A7
0x1800b532b  mov     [rax], r13
0x1800b532e  lea     r8, [rbp+phModule]; phModule
0x1800b5332  mov     [rax+18h], r13
0x1800b5336  lea     rdx, ModuleName; "AppXDeploymentServer"
0x1800b533d  xorps   xmm0, xmm0
0x1800b5340  mov     ecx, 2; dwFlags
0x1800b5345  movups  xmmword ptr [rax+8], xmm0
0x1800b5349  mov     [rax+20h], r13
0x1800b534d  mov     [rax+28h], r13
0x1800b5351  mov     [rbp+phModule], r13
0x1800b5355  call    cs:__imp_GetModuleHandleExW
0x1800b535c  nop     dword ptr [rax+rax+00h]
0x1800b5361  test    eax, eax
0x1800b5363  jz      loc_1800B543F
0x1800b5369  mov     rcx, [rbp+phModule]; hModule
0x1800b536d  lea     rdx, aIspackagingext; "IsPackagingExtensionBeingServiced"
0x1800b5374  call    cs:__imp_GetProcAddress
0x1800b537b  nop     dword ptr [rax+rax+00h]
0x1800b5380  test    rax, rax
0x1800b5383  jz      loc_1800B543F
0x1800b5389  mov     rcx, [r14+8]
0x1800b538d  mov     dil, 1
0x1800b5390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5395  test    eax, eax
0x1800b5397  jz      loc_1800B54F4
0x1800b539d  mov     rax, [r14+8]
0x1800b53a1  lea     r8, aOnecorePrintsc_195; "onecore\\printscan\\appxpackaging\\dll"...
0x1800b53a8  mov     rcx, [rbp+38h]; this
0x1800b53ac  mov     edi, 80073D02h
0x1800b53b1  mov     [rsp+80h+var_58], rax; char *
0x1800b53b6  mov     r9d, edi; char *
0x1800b53b9  lea     rax, aNotLoadingExte; "Not loading extension from %s, package "...
0x1800b53c0  mov     edx, 34h ; '4'; void *
0x1800b53c5  mov     [rsp+80h+var_60], rax; int
0x1800b53ca  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800b53cf  jmp     loc_1800B5755
0x1800b53d4  cmp     rdi, 40000000h
0x1800b53db  jz      loc_1800B530E
0x1800b53e1  mov     rdx, rdi
0x1800b53e4  mov     rbx, r13
0x1800b53e7  call    ??A?$Array@ULoadedExtension@Packaging@Appx@@V?$ContainerOperations@ULoadedExtension@Packaging@Appx@@U123@@Common@@GV?$ContainerOperations@GULoadedExtension@Packaging@Appx@@@5@V?$ArrayOperations@ULoadedExtension@Packaging@Appx@@G@5@@Common@@QEAAPEAULoadedExtension@Packaging@Appx@@_K@Z; Common::Array<Appx::Packaging::LoadedExtension,Common::ContainerOperations<Appx::Packaging::LoadedExtension,Appx::Packaging::LoadedExtension>,ushort,Common::ContainerOperations<ushort,Appx::Packaging::LoadedExtension>,Common::ArrayOperations<Appx::Packaging::LoadedExtension,ushort>>::operator[](unsigned __int64)
0x1800b53ec  mov     rsi, [rax]
0x1800b53ef  call    ?Provider@AppxPackagingProvider@Packaging@Appx@@SAPEBU_tlgProvider_t@@XZ; Appx::Packaging::AppxPackagingProvider::Provider(void)
0x1800b53f4  mov     r9, rax
0x1800b53f7  mov     ecx, [rax]
0x1800b53f9  cmp     ecx, 5
0x1800b53fc  jbe     loc_1800B557A
0x1800b5402  mov     rdx, rdi
0x1800b5405  mov     [rbp+arg_0], rdi
0x1800b5409  call    ??A?$Array@ULoadedExtension@Packaging@Appx@@V?$ContainerOperations@ULoadedExtension@Packaging@Appx@@U123@@Common@@GV?$ContainerOperations@GULoadedExtension@Packaging@Appx@@@5@V?$ArrayOperations@ULoadedExtension@Packaging@Appx@@G@5@@Common@@QEAAPEAULoadedExtension@Packaging@Appx@@_K@Z; Common::Array<Appx::Packaging::LoadedExtension,Common::ContainerOperations<Appx::Packaging::LoadedExtension,Appx::Packaging::LoadedExtension>,ushort,Common::ContainerOperations<ushort,Appx::Packaging::LoadedExtension>,Common::ArrayOperations<Appx::Packaging::LoadedExtension,ushort>>::operator[](unsigned __int64)
0x1800b540e  xor     r8d, r8d
0x1800b5411  lea     rdx, byte_18015960B
0x1800b5418  mov     rcx, [rax+10h]
0x1800b541c  lea     rax, [rbp+arg_0]
0x1800b5420  mov     [rsp+80h+var_58], rax
0x1800b5425  lea     rax, [rbp+phModule]
0x1800b5429  mov     [rbp+phModule], rcx
0x1800b542d  mov     rcx, r9
0x1800b5430  mov     [rsp+80h+var_60], rax
0x1800b5435  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x1800b543a  jmp     loc_1800B557A
0x1800b543f  mov     rdx, [r14+8]
0x1800b5443  lea     rax, [rbp+var_20+8]
0x1800b5447  mov     [rsp+80h+var_48], rax
0x1800b544c  lea     rsi, [rbx+20h]
0x1800b5450  mov     dword ptr [rsp+80h+var_50], r13d
0x1800b5455  mov     r8, r13
0x1800b5458  mov     [rsp+80h+var_58], r13
0x1800b545d  xor     r9d, r9d
0x1800b5460  xor     ecx, ecx
0x1800b5462  mov     dword ptr [rsp+80h+var_60], r13d; int
0x1800b5467  mov     qword ptr [rbp+var_20], rsi
0x1800b546b  mov     qword ptr [rbp+var_20+8], r13
0x1800b546f  mov     [rbp+var_10], 1
0x1800b5473  call    cs:__imp_TryCreatePackageDependency
0x1800b547a  nop     dword ptr [rax+rax+00h]
0x1800b547f  lea     rcx, [rbp+var_20]
0x1800b5483  mov     edi, eax
0x1800b5485  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GUprocess_heap_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::process_heap_deleter>>(void)
0x1800b548a  test    edi, edi
0x1800b548c  jns     short loc_1800B54AB
0x1800b548e  mov     r9d, edi; char *
0x1800b5491  mov     edx, 3Ch ; '<'; void *
0x1800b5496  mov     rcx, [rbp+38h]; this
0x1800b549a  lea     r8, aOnecorePrintsc_195; "onecore\\printscan\\appxpackaging\\dll"...
0x1800b54a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b54a6  jmp     loc_1800B5755
0x1800b54ab  mov     rcx, [rsi]
0x1800b54ae  lea     r9, [rbx+28h]
0x1800b54b2  xor     r8d, r8d
0x1800b54b5  mov     [rsp+80h+var_60], r13
0x1800b54ba  xor     edx, edx
0x1800b54bc  call    cs:__imp_AddPackageDependency
0x1800b54c3  nop     dword ptr [rax+rax+00h]
0x1800b54c8  mov     edi, eax
0x1800b54ca  test    eax, eax
0x1800b54cc  jns     short loc_1800B54D8
0x1800b54ce  mov     r9d, eax
0x1800b54d1  mov     edx, 3Dh ; '='
0x1800b54d6  jmp     short loc_1800B5496
0x1800b54d8  mov     rcx, [r14+20h]; unsigned __int16 *
0x1800b54dc  call    ?VerifyExtensionDllSignature@UndockedExtensionsReader@Packaging@Appx@@SAJPEBG@Z; Appx::Packaging::UndockedExtensionsReader::VerifyExtensionDllSignature(ushort const *)
0x1800b54e1  mov     edi, eax
0x1800b54e3  test    eax, eax
0x1800b54e5  jns     short loc_1800B54F1
0x1800b54e7  mov     r9d, eax
0x1800b54ea  mov     edx, 3Eh ; '>'
0x1800b54ef  jmp     short loc_1800B5496
0x1800b54f1  mov     dil, r13b
0x1800b54f4  mov     rcx, [r14+20h]; lpLibFileName
0x1800b54f8  call    cs:__imp_LoadLibraryW
0x1800b54ff  nop     dword ptr [rax+rax+00h]
0x1800b5504  mov     rdx, rax
0x1800b5507  mov     rcx, rbx
0x1800b550a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x1800b550f  mov     rsi, [rbx]
0x1800b5512  test    rsi, rsi
0x1800b5515  jnz     short loc_1800B5541
0x1800b5517  mov     rax, [r14+20h]
0x1800b551b  lea     r9, aDllpathS; "DllPath=%s"
0x1800b5522  mov     rcx, [rbp+38h]; this
0x1800b5526  lea     r8, aOnecorePrintsc_195; "onecore\\printscan\\appxpackaging\\dll"...
0x1800b552d  lea     edx, [rsi+43h]; void *
0x1800b5530  mov     [rsp+80h+var_60], rax; char *
0x1800b5535  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1800b553a  mov     edi, eax
0x1800b553c  jmp     loc_1800B5755
0x1800b5541  call    ?Provider@AppxPackagingProvider@Packaging@Appx@@SAPEBU_tlgProvider_t@@XZ; Appx::Packaging::AppxPackagingProvider::Provider(void)
0x1800b5546  mov     ecx, [rax]
0x1800b5548  cmp     ecx, 5
0x1800b554b  jbe     short loc_1800B557A
0x1800b554d  mov     rcx, [r14+20h]
0x1800b5551  lea     rdx, dword_180159644
0x1800b5558  mov     qword ptr [rbp+var_20], rcx
0x1800b555c  lea     rcx, [rbp+arg_0]
0x1800b5560  mov     [rsp+80h+var_58], rcx
0x1800b5565  lea     rcx, [rbp+var_20]
0x1800b5569  mov     [rsp+80h+var_60], rcx; int
0x1800b556e  mov     rcx, rax
0x1800b5571  mov     byte ptr [rbp+arg_0], dil
0x1800b5575  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &)
0x1800b557a  lea     rdx, aGetpackagingex; "GetPackagingExtension"
0x1800b5581  mov     rcx, rsi; hModule
0x1800b5584  call    cs:__imp_GetProcAddress
0x1800b558b  nop     dword ptr [rax+rax+00h]
0x1800b5590  mov     rdi, rax
0x1800b5593  test    rax, rax
0x1800b5596  jnz     short loc_1800B55BB
0x1800b5598  mov     rcx, [rbp+38h]; this
0x1800b559c  lea     r8, aOnecorePrintsc_195; "onecore\\printscan\\appxpackaging\\dll"...
0x1800b55a3  lea     edx, [rax+56h]; void *
0x1800b55a6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800b55ab  mov     edi, eax
0x1800b55ad  test    rbx, rbx
0x1800b55b0  jz      loc_1800B5762
0x1800b55b6  jmp     loc_1800B5755
0x1800b55bb  lea     rcx, [rbp+arg_8]
0x1800b55bf  mov     [rbp+arg_8], r13
0x1800b55c3  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800b55c8  lea     rcx, [rbp+arg_8]
0x1800b55cc  mov     rax, rdi
0x1800b55cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b55d4  mov     edi, eax
0x1800b55d6  test    eax, eax
0x1800b55d8  jns     short loc_1800B55FD
0x1800b55da  mov     edx, 59h ; 'Y'; void *
0x1800b55df  mov     rcx, [rbp+38h]; this
0x1800b55e3  lea     r8, aOnecorePrintsc_195; "onecore\\printscan\\appxpackaging\\dll"...
0x1800b55ea  mov     r9d, eax; char *
0x1800b55ed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b55f2  lea     rcx, [rbp+arg_8]
0x1800b55f6  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800b55fb  jmp     short loc_1800B55AD
0x1800b55fd  mov     rcx, [rbp+arg_8]
0x1800b5601  lea     r8, [rbp+var_28]
0x1800b5605  movups  xmm0, xmmword ptr [r15]
0x1800b5609  mov     [rbp+var_28], r13
0x1800b560d  lea     rdx, [rbp+var_20]
0x1800b5611  mov     rax, [rcx]
0x1800b5614  movdqu  xmmword ptr [rbp+var_20], xmm0
0x1800b5619  mov     rax, [rax+18h]
0x1800b561d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b5622  mov     edi, eax
0x1800b5624  test    eax, eax
0x1800b5626  jns     short loc_1800B562F
0x1800b5628  mov     edx, 5Ch ; '\'
0x1800b562d  jmp     short loc_1800B55DF
0x1800b562f  mov     rax, [r14+40h]
0x1800b5633  mov     rdx, [rbp+var_28]
0x1800b5637  cmp     rdx, rax
0x1800b563a  jz      short loc_1800B5671
0x1800b563c  mov     rcx, [rbp+38h]; this
0x1800b5640  lea     r8, aOnecorePrintsc_195; "onecore\\printscan\\appxpackaging\\dll"...
0x1800b5647  mov     [rsp+80h+var_50], rax
0x1800b564c  mov     edi, 8007000Bh
0x1800b5651  mov     [rsp+80h+var_58], rdx; char *
0x1800b5656  lea     rax, aVersionFromDll; "Version from dll=0x%llX, Version from m"...
0x1800b565d  mov     r9d, edi; char *
0x1800b5660  mov     [rsp+80h+var_60], rax; int
0x1800b5665  mov     edx, 5Dh ; ']'; void *
0x1800b566a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800b566f  jmp     short loc_1800B55F2
0x1800b5671  mov     rsi, [rbp+arg_8]
0x1800b5675  lea     rcx, [rbp+var_40]
0x1800b5679  mov     [rbp+var_40], r13
0x1800b567d  mov     rax, [rsi]
0x1800b5680  mov     rdi, [rax+20h]
0x1800b5684  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800b5689  movups  xmm0, xmmword ptr [r15]
0x1800b568d  lea     r8, [rbp+var_40]
0x1800b5691  mov     rcx, rsi
0x1800b5694  lea     rdx, [rbp+var_20]
0x1800b5698  mov     rax, rdi
0x1800b569b  movdqu  xmmword ptr [rbp+var_20], xmm0
0x1800b56a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b56a5  mov     edi, eax
0x1800b56a7  test    eax, eax
0x1800b56a9  jns     short loc_1800B56D1
0x1800b56ab  mov     edx, 60h ; '`'; void *
0x1800b56b0  mov     rcx, [rbp+38h]; this
0x1800b56b4  lea     r8, aOnecorePrintsc_195; "onecore\\printscan\\appxpackaging\\dll"...
0x1800b56bb  mov     r9d, eax; char *
0x1800b56be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b56c3  lea     rcx, [rbp+var_40]
0x1800b56c7  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800b56cc  jmp     loc_1800B55F2
0x1800b56d1  mov     rcx, [rbp+var_40]
0x1800b56d5  mov     r8, r12
0x1800b56d8  mov     rdx, r15
0x1800b56db  mov     rax, [rcx]
0x1800b56de  mov     rax, [rax]
0x1800b56e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b56e6  mov     edi, eax
0x1800b56e8  test    eax, eax
0x1800b56ea  jns     short loc_1800B56F3
0x1800b56ec  mov     edx, 61h ; 'a'
0x1800b56f1  jmp     short loc_1800B56B0
0x1800b56f3  test    rbx, rbx
0x1800b56f6  jz      loc_1800B5788
0x1800b56fc  mov     rdx, [r14+20h]; unsigned __int16 *
0x1800b5700  lea     rcx, [rbx+8]; this
0x1800b5704  call    ?SetValueFromString@StringBuffer@Common@@QEAAJPEBG@Z; Common::StringBuffer::SetValueFromString(ushort const *)
0x1800b5709  mov     edi, eax
0x1800b570b  test    eax, eax
0x1800b570d  jns     short loc_1800B5716
0x1800b570f  mov     edx, 65h ; 'e'
0x1800b5714  jmp     short loc_1800B5730
0x1800b5716  mov     rdx, cs:qword_180169EF8
0x1800b571d  inc     rdx
0x1800b5720  call    ?EnsureCapacity@?$Array@ULoadedExtension@Packaging@Appx@@V?$ContainerOperations@ULoadedExtension@Packaging@Appx@@U123@@Common@@GV?$ContainerOperations@GULoadedExtension@Packaging@Appx@@@5@V?$ArrayOperations@ULoadedExtension@Packaging@Appx@@G@5@@Common@@QEAAJ_K@Z; Common::Array<Appx::Packaging::LoadedExtension,Common::ContainerOperations<Appx::Packaging::LoadedExtension,Appx::Packaging::LoadedExtension>,ushort,Common::ContainerOperations<ushort,Appx::Packaging::LoadedExtension>,Common::ArrayOperations<Appx::Packaging::LoadedExtension,ushort>>::EnsureCapacity(unsigned __int64)
0x1800b5725  mov     edi, eax
0x1800b5727  test    eax, eax
0x1800b5729  jns     short loc_1800B576F
0x1800b572b  mov     edx, 66h ; 'f'; void *
0x1800b5730  mov     rcx, [rbp+38h]; this
0x1800b5734  lea     r8, aOnecorePrintsc_195; "onecore\\printscan\\appxpackaging\\dll"...
0x1800b573b  mov     r9d, eax; char *
0x1800b573e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b5743  lea     rcx, [rbp+var_40]
0x1800b5747  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
0x1800b574c  lea     rcx, [rbp+arg_8]
0x1800b5750  call    ?InternalRelease@?$ComPtr@UICreateErrorInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ICreateErrorInfo>::InternalRelease(void)
  ... truncated ...
```
