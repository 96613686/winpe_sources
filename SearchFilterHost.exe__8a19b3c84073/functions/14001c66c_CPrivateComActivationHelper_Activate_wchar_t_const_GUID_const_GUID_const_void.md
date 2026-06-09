# CPrivateComActivationHelper::Activate(wchar_t const *,_GUID const &,_GUID const &,void * *)

- ea: `0x14001c66c`
- end: `0x14001c7e8`
- name: `?Activate@CPrivateComActivationHelper@@QEAAJPEB_WAEBU_GUID@@1PEAPEAX@Z`
- size: `380`
- prototype: `__int64 __fastcall(CPrivateComActivationHelper *this, const wchar_t *, const struct _GUID *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14001df20`

## callees

- `0x140009eec`
- `0x140009f14`
- `0x14001bd58`
- `0x14001c66c`
- `0x140021a14`
- `0x14004f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14001c6a3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14001c6a3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001c6c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001c6c4`

## string_xrefs

- `0x14001c6d5`: `onecoreuap\base\appmodel\Search\common\include\PrivateComActivationHelper.h`
- `0x14001c71d`: `onecoreuap\base\appmodel\Search\common\include\PrivateComActivationHelper.h`
- `0x14001c7c3`: `onecoreuap\base\appmodel\Search\common\include\PrivateComActivationHelper.h`
- `0x14001c6ba`: `DllGetClassObject`

## pseudocode

```c
__int64 __fastcall CPrivateComActivationHelper::Activate(
        CPrivateComActivationHelper *this,
        const wchar_t *a2,
        const struct _GUID *a3,
        const struct _GUID *a4,
        void **a5)
{
  HMODULE Library; // rax
  const char *v9; // r9
  HMODULE v10; // rbx
  __int64 v11; // rdx
  FARPROC ProcAddress; // rsi
  unsigned int LastError; // ebx
  int v14; // eax
  int v15; // esi
  __int64 v17; // rbx
  int v18; // eax
  int v19; // [rsp+20h] [rbp-38h]
  HMODULE v20; // [rsp+30h] [rbp-28h] BYREF
  _QWORD v21[4]; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+30h]
  __int64 v23; // [rsp+90h] [rbp+38h] BYREF

  v21[1] = -2;
  if ( !*(_QWORD *)this )
  {
    Library = LoadLibraryExW(a2, 0, 8u);
    v10 = Library;
    v20 = Library;
    if ( !Library )
    {
      v11 = 26;
LABEL_6:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v11,
                    (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\PrivateComActivationHelper.h",
                    v9);
LABEL_9:
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v20);
      return LastError;
    }
    ProcAddress = GetProcAddress(Library, "DllGetClassObject");
    if ( !ProcAddress )
    {
      v11 = 32;
      goto LABEL_6;
    }
    v23 = 0;
    Microsoft::WRL::ComPtr<IFilterHostManager>::InternalRelease(&v23);
    v14 = ((__int64 (__fastcall *)(const struct _GUID *, GUID *, __int64 *))ProcAddress)(
            a3,
            &GUID_00000001_0000_0000_c000_000000000046,
            &v23);
    v15 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x23,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\PrivateComActivationHelper.h",
        (const char *)(unsigned int)v14,
        v19);
      Microsoft::WRL::ComPtr<IFilterHostManager>::InternalRelease(&v23);
      LastError = v15;
      goto LABEL_9;
    }
    v20 = 0;
    *(_QWORD *)this = v10;
    v17 = v23;
    if ( *((_QWORD *)this + 1) != v23 )
    {
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 8LL))(v23);
      v21[0] = *((_QWORD *)this + 1);
      *((_QWORD *)this + 1) = v17;
      Microsoft::WRL::ComPtr<IFilterHostManager>::InternalRelease(v21);
    }
    Microsoft::WRL::ComPtr<IFilterHostManager>::InternalRelease(&v23);
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v20);
  }
  v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, const struct _GUID *, void **))(**((_QWORD **)this + 1) + 24LL))(
          *((_QWORD *)this + 1),
          0,
          a4,
          a5);
  LastError = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\PrivateComActivationHelper.h",
      (const char *)(unsigned int)v18,
      v19);
    return LastError;
  }
  return 0;
}

```

## disassembly

```asm
0x14001c66c  push    rbp
0x14001c66e  push    rbx
0x14001c66f  push    rsi
0x14001c670  push    rdi
0x14001c671  push    r14
0x14001c673  push    r15
0x14001c675  mov     rbp, rsp
0x14001c678  sub     rsp, 58h
0x14001c67c  mov     [rbp+var_18], 0FFFFFFFFFFFFFFFEh
0x14001c684  mov     r15, r9
0x14001c687  mov     r14, r8
0x14001c68a  mov     rax, rdx
0x14001c68d  mov     rdi, rcx
0x14001c690  cmp     qword ptr [rcx], 0
0x14001c694  jnz     loc_14001C79D
0x14001c69a  xor     edx, edx; hFile
0x14001c69c  lea     r8d, [rdx+8]; dwFlags
0x14001c6a0  mov     rcx, rax; lpLibFileName
0x14001c6a3  call    cs:__imp_LoadLibraryExW
0x14001c6a9  mov     rbx, rax
0x14001c6ac  mov     [rbp+var_28], rax
0x14001c6b0  test    rax, rax
0x14001c6b3  jnz     short loc_14001C6BA
0x14001c6b5  lea     edx, [rax+1Ah]
0x14001c6b8  jmp     short loc_14001C6D5
0x14001c6ba  lea     rdx, aDllgetclassobj; "DllGetClassObject"
0x14001c6c1  mov     rcx, rbx; hModule
0x14001c6c4  call    cs:__imp_GetProcAddress
0x14001c6ca  mov     rsi, rax
0x14001c6cd  test    rax, rax
0x14001c6d0  jnz     short loc_14001C6E9
0x14001c6d2  lea     edx, [rax+20h]; void *
0x14001c6d5  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\Search\\com"...
0x14001c6dc  mov     rcx, [rbp+30h]; this
0x14001c6e0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14001c6e5  mov     ebx, eax
0x14001c6e7  jmp     short loc_14001C73A
0x14001c6e9  mov     [rbp+arg_0], 0
0x14001c6f1  lea     rcx, [rbp+arg_0]
0x14001c6f5  call    ?InternalRelease@?$ComPtr@UIFilterHostManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFilterHostManager>::InternalRelease(void)
0x14001c6fa  lea     r8, [rbp+arg_0]
0x14001c6fe  lea     rdx, _GUID_00000001_0000_0000_c000_000000000046
0x14001c705  mov     rcx, r14
0x14001c708  mov     rax, rsi
0x14001c70b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c710  mov     esi, eax
0x14001c712  test    eax, eax
0x14001c714  jns     short loc_14001C74A
0x14001c716  mov     rcx, [rbp+30h]; this
0x14001c71a  mov     r9d, eax; char *
0x14001c71d  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\Search\\com"...
0x14001c724  mov     edx, 23h ; '#'; void *
0x14001c729  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001c72e  nop
0x14001c72f  lea     rcx, [rbp+arg_0]
0x14001c733  call    ?InternalRelease@?$ComPtr@UIFilterHostManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFilterHostManager>::InternalRelease(void)
0x14001c738  mov     ebx, esi
0x14001c73a  lea     rcx, [rbp+var_28]
0x14001c73e  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x14001c743  mov     eax, ebx
0x14001c745  jmp     loc_14001C7DB
0x14001c74a  mov     [rbp+var_28], 0
0x14001c752  mov     [rdi], rbx
0x14001c755  mov     rbx, [rbp+arg_0]
0x14001c759  cmp     [rdi+8], rbx
0x14001c75d  jz      short loc_14001C78A
0x14001c75f  test    rbx, rbx
0x14001c762  jz      short loc_14001C774
0x14001c764  mov     rax, [rbx]
0x14001c767  mov     rcx, rbx
0x14001c76a  mov     rax, [rax+8]
0x14001c76e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c773  nop
0x14001c774  mov     rax, [rdi+8]
0x14001c778  mov     [rbp+var_20], rax
0x14001c77c  mov     [rdi+8], rbx
0x14001c780  lea     rcx, [rbp+var_20]
0x14001c784  call    ?InternalRelease@?$ComPtr@UIFilterHostManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFilterHostManager>::InternalRelease(void)
0x14001c789  nop
0x14001c78a  lea     rcx, [rbp+arg_0]
0x14001c78e  call    ?InternalRelease@?$ComPtr@UIFilterHostManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFilterHostManager>::InternalRelease(void)
0x14001c793  nop
0x14001c794  lea     rcx, [rbp+var_28]
0x14001c798  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x14001c79d  mov     rcx, [rdi+8]
0x14001c7a1  mov     rax, [rcx]
0x14001c7a4  mov     r9, [rbp+arg_20]
0x14001c7a8  mov     r8, r15
0x14001c7ab  xor     edx, edx
0x14001c7ad  mov     rax, [rax+18h]
0x14001c7b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c7b6  mov     ebx, eax
0x14001c7b8  test    eax, eax
0x14001c7ba  jns     short loc_14001C7D9
0x14001c7bc  mov     rcx, [rbp+30h]; this
0x14001c7c0  mov     r9d, eax; char *
0x14001c7c3  lea     r8, aOnecoreuapBase_17; "onecoreuap\\base\\appmodel\\Search\\com"...
0x14001c7ca  mov     edx, 29h ; ')'; void *
0x14001c7cf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14001c7d4  jmp     loc_14001C743
0x14001c7d9  xor     eax, eax
0x14001c7db  add     rsp, 58h
0x14001c7df  pop     r15
0x14001c7e1  pop     r14
0x14001c7e3  pop     rdi
0x14001c7e4  pop     rsi
0x14001c7e5  pop     rbx
0x14001c7e6  pop     rbp
0x14001c7e7  retn
```
