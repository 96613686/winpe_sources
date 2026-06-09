# Microsoft::Resources::GetMetadataFolderForPackageFullName(ushort const *,ushort const *,Microsoft::Resources::StringResult *)

- ea: `0x18001b830`
- end: `0x18001bb5d`
- name: `?GetMetadataFolderForPackageFullName@Resources@Microsoft@@YAJPEBG0PEAVStringResult@12@@Z`
- size: `813`
- prototype: `int(Microsoft::Resources *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct Microsoft::Resources::StringResult *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800172a0`
- `0x18007b1c0`

## callees

- `0x180017960`
- `0x180017980`
- `0x18001b5fc`
- `0x18001b830`
- `0x18001c2c0`
- `0x1800268c0`
- `0x18002c8d0`
- `0x18002cfd0`
- `0x180083aa8`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001b85c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001b85c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ba58`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ba58`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b87f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001b87f`

## string_xrefs

- `0x18001b855`: `AppxDeploymentClient.dll`

## pseudocode

```c
__int64 __fastcall Microsoft::Resources::GetMetadataFolderForPackageFullName(
        Microsoft::Resources *this,
        Microsoft::Resources *a2,
        const unsigned __int16 *a3,
        struct Microsoft::Resources::StringResult *a4)
{
  HMODULE Library; // rax
  const char *v8; // r9
  HMODULE v9; // rbx
  const char *v10; // r9
  FARPROC ProcAddress; // r15
  struct Microsoft::Resources::StringResult *v12; // r8
  __int64 *v13; // rcx
  int PackageRootFromFullName; // edi
  int v15; // edi
  __int64 v16; // rax
  int v17; // edx
  __int64 v18; // rcx
  int v19; // eax
  int v20; // esi
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rsi
  int v24; // r14d
  unsigned int LastError; // ebx
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rdx
  __int64 v30; // rdx
  int v31; // [rsp+20h] [rbp-48h]
  HMODULE v32; // [rsp+30h] [rbp-38h] BYREF
  unsigned __int16 v33[4]; // [rsp+38h] [rbp-30h] BYREF
  __int64 v34; // [rsp+40h] [rbp-28h] BYREF
  __int64 v35; // [rsp+48h] [rbp-20h]
  Microsoft::Resources *v36; // [rsp+50h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  unsigned int v38; // [rsp+C8h] [rbp+60h] BYREF

  Library = LoadLibraryExW(L"AppxDeploymentClient.dll", 0, 0x800u);
  v32 = Library;
  v9 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "GetMetadataRootForPackage");
    if ( !ProcAddress )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xF4,
                    (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientprofiles.cpp",
                    v10);
      goto LABEL_33;
    }
    DefStringResult_InitBuf(&v34);
    v13 = &v34;
    *(_QWORD *)v33 = &v34;
    if ( this && *(_WORD *)this )
    {
      if ( !v34 && (_DWORD)v35 || !(_DWORD)v35 && v34 )
      {
        v15 = -2147024809;
        v29 = 249;
        goto LABEL_48;
      }
      v36 = this;
    }
    else
    {
      PackageRootFromFullName = Microsoft::Resources::GetPackageRootFromFullName(a2, v33, v12);
      if ( PackageRootFromFullName < 0 )
      {
        v30 = 253;
        goto LABEL_61;
      }
      v13 = *(__int64 **)v33;
    }
    v38 = 0;
    v15 = -2147024809;
    if ( v13 && (*v13 || !*((_DWORD *)v13 + 2)) && (*((_DWORD *)v13 + 2) || !*v13) )
    {
      v16 = v13[2];
      v17 = 0;
    }
    else
    {
      v16 = 0;
      v17 = -2147024809;
    }
    v18 = 0;
    if ( v17 >= 0 )
      v18 = v16;
    v19 = ((__int64 (__fastcall *)(__int64, Microsoft::Resources *, unsigned int *, _QWORD))ProcAddress)(
            v18,
            a2,
            &v38,
            0);
    v20 = v19;
    if ( v19 != -2147024774 )
    {
      if ( v19 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x10E,
          (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientprofiles.cpp",
          (const char *)(unsigned int)v19,
          v31);
        Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)v33);
        LastError = v20;
        goto LABEL_33;
      }
LABEL_43:
      v15 = 0;
LABEL_44:
      Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)v33);
      FreeLibrary(v9);
      return (unsigned int)v15;
    }
    v21 = *(_QWORD *)a3;
    if ( *(_QWORD *)a3 && (*(_QWORD *)v21 || !*(_DWORD *)(v21 + 8)) && (*(_DWORD *)(v21 + 8) || !*(_QWORD *)v21) && v38 )
    {
      v22 = DefStringResult_EnsureEmptyBuffer(v21, v38);
      if ( v22 >= 0 )
      {
        v23 = *(_QWORD *)a3;
        if ( !*(_QWORD *)a3 || !*(_QWORD *)v23 && *(_DWORD *)(v23 + 8) || !*(_DWORD *)(v23 + 8) && *(_QWORD *)v23 )
        {
          v24 = -2147024809;
          goto LABEL_32;
        }
        v24 = DefStringResult_EnsureBuffer(*(_QWORD *)a3, 0);
        if ( v24 < 0 )
        {
LABEL_32:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x108,
            (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientprofiles.cpp",
            (const char *)(unsigned int)v24,
            v31);
          Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)v33);
          LastError = v24;
LABEL_33:
          wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&v32);
          return LastError;
        }
        if ( *(_QWORD *)v33
          && (**(_QWORD **)v33 || !*(_DWORD *)(*(_QWORD *)v33 + 8LL))
          && (*(_DWORD *)(*(_QWORD *)v33 + 8LL) || !**(_QWORD **)v33) )
        {
          v27 = *(_QWORD *)(*(_QWORD *)v33 + 16LL);
          v15 = 0;
        }
        else
        {
          v27 = 0;
        }
        v28 = 0;
        if ( v15 >= 0 )
          v28 = v27;
        PackageRootFromFullName = ((__int64 (__fastcall *)(__int64, Microsoft::Resources *, unsigned int *, _QWORD))ProcAddress)(
                                    v28,
                                    a2,
                                    &v38,
                                    *(_QWORD *)v23);
        if ( PackageRootFromFullName >= 0 )
          goto LABEL_43;
        v30 = 266;
LABEL_61:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v30,
          (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientprofiles.cpp",
          (const char *)(unsigned int)PackageRootFromFullName,
          v31);
        Microsoft::Resources::StringResult::~StringResult((Microsoft::Resources::StringResult *)v33);
        LastError = PackageRootFromFullName;
        goto LABEL_33;
      }
      v15 = v22;
    }
    v29 = 260;
LABEL_48:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v29,
      (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientprofiles.cpp",
      (const char *)(unsigned int)v15,
      v31);
    goto LABEL_44;
  }
  return wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0xEF,
           (unsigned int)"onecoreuap\\base\\mrt\\mrm\\src\\clientprofiles.cpp",
           v8);
}

```

## disassembly

```asm
0x18001b830  push    rbp
0x18001b832  push    rbx
0x18001b833  push    rsi
0x18001b834  push    rdi
0x18001b835  push    r12
0x18001b837  push    r13
0x18001b839  push    r14
0x18001b83b  push    r15
0x18001b83d  mov     rbp, rsp
0x18001b840  sub     rsp, 68h
0x18001b844  mov     r14, r8
0x18001b847  mov     r12, rdx
0x18001b84a  mov     rdi, rcx
0x18001b84d  xor     edx, edx; hFile
0x18001b84f  mov     r8d, 800h; dwFlags
0x18001b855  lea     rcx, LibFileName; "AppxDeploymentClient.dll"
0x18001b85c  call    cs:__imp_LoadLibraryExW
0x18001b862  xor     r13d, r13d
0x18001b865  mov     [rbp+var_38], rax
0x18001b869  mov     rbx, rax
0x18001b86c  test    rax, rax
0x18001b86f  jz      loc_18001BA71
0x18001b875  lea     rdx, ProcName; "GetMetadataRootForPackage"
0x18001b87c  mov     rcx, rax; hModule
0x18001b87f  call    cs:__imp_GetProcAddress
0x18001b885  mov     r15, rax
0x18001b888  test    rax, rax
0x18001b88b  jz      loc_18001BB03
0x18001b891  lea     rcx, [rbp+var_28]
0x18001b895  call    DefStringResult_InitBuf
0x18001b89a  lea     rcx, [rbp+var_28]
0x18001b89e  mov     qword ptr [rbp+var_30], rcx
0x18001b8a2  test    rdi, rdi
0x18001b8a5  jz      short loc_18001B8D5
0x18001b8a7  cmp     [rdi], r13w
0x18001b8ab  jz      short loc_18001B8D5
0x18001b8ad  mov     rdx, [rbp+var_28]
0x18001b8b1  mov     rax, [rbp+var_20]
0x18001b8b5  test    rdx, rdx
0x18001b8b8  jnz     short loc_18001B8C2
0x18001b8ba  test    eax, eax
0x18001b8bc  jnz     loc_18001BB1F
0x18001b8c2  test    eax, eax
0x18001b8c4  jnz     short loc_18001B8CF
0x18001b8c6  test    rdx, rdx
0x18001b8c9  jnz     loc_18001BB1F
0x18001b8cf  mov     [rbp+var_18], rdi
0x18001b8d3  jmp     short loc_18001B8EF
0x18001b8d5  lea     rdx, [rbp+var_30]; unsigned __int16 *
0x18001b8d9  mov     rcx, r12; this
0x18001b8dc  call    ?GetPackageRootFromFullName@Resources@Microsoft@@YAJPEBGPEAVStringResult@12@@Z; Microsoft::Resources::GetPackageRootFromFullName(ushort const *,Microsoft::Resources::StringResult *)
0x18001b8e1  mov     edi, eax
0x18001b8e3  test    eax, eax
0x18001b8e5  js      loc_18001BB2E
0x18001b8eb  mov     rcx, qword ptr [rbp+var_30]
0x18001b8ef  mov     [rbp+arg_18], r13d
0x18001b8f3  mov     edi, 80070057h
0x18001b8f8  test    rcx, rcx
0x18001b8fb  jz      loc_18001BAC1
0x18001b901  cmp     [rcx], r13
0x18001b904  jnz     short loc_18001B910
0x18001b906  cmp     [rcx+8], r13d
0x18001b90a  ja      loc_18001BAC1
0x18001b910  cmp     [rcx+8], r13d
0x18001b914  jnz     short loc_18001B91F
0x18001b916  cmp     [rcx], r13
0x18001b919  jnz     loc_18001BAC1
0x18001b91f  mov     rax, [rcx+10h]
0x18001b923  mov     edx, r13d
0x18001b926  test    edx, edx
0x18001b928  lea     r8, [rbp+arg_18]
0x18001b92c  mov     rcx, r13
0x18001b92f  mov     rdx, r12
0x18001b932  cmovns  rcx, rax
0x18001b936  xor     r9d, r9d
0x18001b939  mov     rax, r15
0x18001b93c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b941  mov     esi, eax
0x18001b943  cmp     eax, 8007007Ah
0x18001b948  jnz     loc_18001BAD3
0x18001b94e  mov     rcx, [r14]
0x18001b951  test    rcx, rcx
0x18001b954  jz      loc_18001BA8A
0x18001b95a  cmp     [rcx], r13
0x18001b95d  jnz     short loc_18001B969
0x18001b95f  cmp     [rcx+8], r13d
0x18001b963  ja      loc_18001BA8A
0x18001b969  cmp     [rcx+8], r13d
0x18001b96d  jnz     short loc_18001B978
0x18001b96f  cmp     [rcx], r13
0x18001b972  jnz     loc_18001BA8A
0x18001b978  mov     edx, [rbp+arg_18]
0x18001b97b  test    rdx, rdx
0x18001b97e  jz      loc_18001BA8A
0x18001b984  call    _DefStringResult_EnsureEmptyBuffer
0x18001b989  test    eax, eax
0x18001b98b  js      loc_18001BA88
0x18001b991  mov     rsi, [r14]
0x18001b994  test    rsi, rsi
0x18001b997  jz      loc_18001BAAD
0x18001b99d  cmp     [rsi], r13
0x18001b9a0  jz      loc_18001BAB5
0x18001b9a6  cmp     [rsi+8], r13d
0x18001b9aa  jz      loc_18001BAA4
0x18001b9b0  xor     edx, edx
0x18001b9b2  mov     rcx, rsi
0x18001b9b5  call    _DefStringResult_EnsureBuffer
0x18001b9ba  mov     r14d, eax
0x18001b9bd  test    eax, eax
0x18001b9bf  jns     short loc_18001B9F2
0x18001b9c1  mov     rcx, [rbp+40h]; this
0x18001b9c5  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\mrt\\mrm\\src\\client"...
0x18001b9cc  mov     r9d, r14d; char *
0x18001b9cf  mov     edx, 108h; void *
0x18001b9d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b9d9  lea     rcx, [rbp+var_30]; this
0x18001b9dd  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x18001b9e2  mov     ebx, r14d
0x18001b9e5  lea     rcx, [rbp+var_38]
0x18001b9e9  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18001b9ee  mov     eax, ebx
0x18001b9f0  jmp     short loc_18001BA60
0x18001b9f2  mov     rax, qword ptr [rbp+var_30]
0x18001b9f6  test    rax, rax
0x18001b9f9  jz      loc_18001BACB
0x18001b9ff  cmp     [rax], r13
0x18001ba02  jnz     short loc_18001BA0E
0x18001ba04  cmp     [rax+8], r13d
0x18001ba08  ja      loc_18001BACB
0x18001ba0e  cmp     [rax+8], r13d
0x18001ba12  jnz     short loc_18001BA1D
0x18001ba14  cmp     [rax], r13
0x18001ba17  jnz     loc_18001BACB
0x18001ba1d  mov     rdx, [rax+10h]
0x18001ba21  mov     edi, r13d
0x18001ba24  mov     r9, [rsi]
0x18001ba27  lea     r8, [rbp+arg_18]
0x18001ba2b  test    edi, edi
0x18001ba2d  mov     rcx, r13
0x18001ba30  mov     rax, r15
0x18001ba33  cmovns  rcx, rdx
0x18001ba37  mov     rdx, r12
0x18001ba3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba3f  mov     edi, eax
0x18001ba41  test    eax, eax
0x18001ba43  js      loc_18001BB35
0x18001ba49  mov     edi, r13d
0x18001ba4c  lea     rcx, [rbp+var_30]; this
0x18001ba50  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x18001ba55  mov     rcx, rbx; hLibModule
0x18001ba58  call    cs:__imp_FreeLibrary
0x18001ba5e  mov     eax, edi
0x18001ba60  add     rsp, 68h
0x18001ba64  pop     r15
0x18001ba66  pop     r14
0x18001ba68  pop     r13
0x18001ba6a  pop     r12
0x18001ba6c  pop     rdi
0x18001ba6d  pop     rsi
0x18001ba6e  pop     rbx
0x18001ba6f  pop     rbp
0x18001ba70  retn
0x18001ba71  mov     rcx, [rbp+40h]; this
0x18001ba75  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\mrt\\mrm\\src\\client"...
0x18001ba7c  mov     edx, 0EFh; void *
0x18001ba81  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ba86  jmp     short loc_18001BA60
0x18001ba88  mov     edi, eax
0x18001ba8a  mov     edx, 104h; void *
0x18001ba8f  mov     rcx, [rbp+40h]; this
0x18001ba93  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\mrt\\mrm\\src\\client"...
0x18001ba9a  mov     r9d, edi; char *
0x18001ba9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001baa2  jmp     short loc_18001BA4C
0x18001baa4  cmp     [rsi], r13
0x18001baa7  jz      loc_18001B9B0
0x18001baad  mov     r14d, edi
0x18001bab0  jmp     loc_18001B9C1
0x18001bab5  cmp     [rsi+8], r13d
0x18001bab9  jbe     loc_18001B9A6
0x18001babf  jmp     short loc_18001BAAD
0x18001bac1  mov     rax, r13
0x18001bac4  mov     edx, edi
0x18001bac6  jmp     loc_18001B926
0x18001bacb  mov     rdx, r13
0x18001bace  jmp     loc_18001BA24
0x18001bad3  test    esi, esi
0x18001bad5  jns     loc_18001BA49
0x18001badb  mov     rcx, [rbp+40h]; this
0x18001badf  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\mrt\\mrm\\src\\client"...
0x18001bae6  mov     r9d, esi; char *
0x18001bae9  mov     edx, 10Eh; void *
0x18001baee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001baf3  lea     rcx, [rbp+var_30]; this
0x18001baf7  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x18001bafc  mov     ebx, esi
0x18001bafe  jmp     loc_18001B9E5
0x18001bb03  mov     rcx, [rbp+40h]; this
0x18001bb07  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\mrt\\mrm\\src\\client"...
0x18001bb0e  mov     edx, 0F4h; void *
0x18001bb13  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001bb18  mov     ebx, eax
0x18001bb1a  jmp     loc_18001B9E5
0x18001bb1f  mov     edi, 80070057h
0x18001bb24  mov     edx, 0F9h
0x18001bb29  jmp     loc_18001BA8F
0x18001bb2e  mov     edx, 0FDh
0x18001bb33  jmp     short loc_18001BB3A
0x18001bb35  mov     edx, 10Ah; void *
0x18001bb3a  mov     rcx, [rbp+40h]; this
0x18001bb3e  lea     r8, aOnecoreuapBase_7; "onecoreuap\\base\\mrt\\mrm\\src\\client"...
0x18001bb45  mov     r9d, edi; char *
0x18001bb48  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bb4d  lea     rcx, [rbp+var_30]; this
0x18001bb51  call    ??1StringResult@Resources@Microsoft@@QEAA@XZ; Microsoft::Resources::StringResult::~StringResult(void)
0x18001bb56  mov     ebx, edi
0x18001bb58  jmp     loc_18001B9E5
```
