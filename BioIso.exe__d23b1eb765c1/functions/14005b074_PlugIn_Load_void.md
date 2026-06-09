# PlugIn::Load(void)

- ea: `0x14005b074`
- end: `0x14005b291`
- name: `?Load@PlugIn@@AEAAJXZ`
- size: `541`
- prototype: `__int64 __fastcall(PlugIn *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14005b310`

## callees

- `0x14000a420`
- `0x14005aaa0`
- `0x14005aac4`
- `0x14005acfc`
- `0x14005aecc`
- `0x14005b074`
- `0x14005b2b4`
- `0x140085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005b0f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005b15f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005b1af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005b0f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005b15f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14005b1af`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14005b0b2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14005b0b2`
- `ntdll!RtlImageNtHeader` at `0x14005b0c8`
- `ntdll!RtlImageNtHeader` at `0x14005b0c8`

## string_xrefs

- `0x14005b121`: `onecore\ds\security\biometrics\service\trustlet\exe\plugin.cpp`
- `0x14005b272`: `onecore\ds\security\biometrics\service\trustlet\exe\plugin.cpp`

## pseudocode

```c
__int64 __fastcall PlugIn::Load(PlugIn *this)
{
  int *v2; // r14
  char *v3; // rcx
  HMODULE Library; // rbx
  PIMAGE_NT_HEADERS v5; // rax
  FARPROC ProcAddress; // rax
  int v7; // eax
  PlugIn *v8; // rcx
  unsigned int v9; // edi
  __int64 v10; // rdx
  __int64 v11; // r9
  __int64 v12; // rdx
  FARPROC v13; // rax
  PlugIn *v14; // rcx
  FARPROC v15; // rax
  PlugIn *v16; // rcx
  struct _WINBIO_STORAGE_INTERFACE *v17; // rdx
  struct _WINBIO_ENGINE_INTERFACE *v18; // rax
  struct _WINBIO_SENSOR_INTERFACE *v19; // rcx
  int v21[4]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]
  struct _WINBIO_SENSOR_INTERFACE *v23; // [rsp+60h] [rbp+30h] BYREF
  struct _WINBIO_ENGINE_INTERFACE *v24; // [rsp+68h] [rbp+38h] BYREF
  struct _WINBIO_STORAGE_INTERFACE *v25; // [rsp+70h] [rbp+40h] BYREF

  if ( *(_DWORD *)this != 1 )
    return 0;
  v2 = (int *)((char *)this + 40);
  if ( *((_QWORD *)this + 5) )
    return 0;
  v3 = (char *)this + 8;
  if ( *((_QWORD *)v3 + 3) > 7u )
    v3 = *(char **)v3;
  Library = LoadLibraryExW((LPCWSTR)v3, 0, 0x900u);
  *(_QWORD *)v21 = Library;
  v5 = RtlImageNtHeader(Library);
  if ( !v5 || SLOBYTE(v5->OptionalHeader.DllCharacteristics) >= 0 )
  {
    v12 = 795;
    goto LABEL_34;
  }
  v23 = 0;
  ProcAddress = GetProcAddress(Library, "WbioQuerySensorInterface");
  if ( !ProcAddress )
  {
LABEL_14:
    v24 = 0;
    v13 = GetProcAddress(Library, "WbioQueryEngineInterface");
    if ( v13 )
    {
      v7 = ((__int64 (__fastcall *)(struct _WINBIO_ENGINE_INTERFACE **))v13)(&v24);
      v9 = v7;
      if ( v7 < 0 )
      {
        v10 = 834;
        goto LABEL_10;
      }
      if ( !PlugIn::IsValidOrNullEngineInterface(v14, v24) )
      {
        v12 = 838;
        goto LABEL_34;
      }
    }
    v25 = 0;
    v15 = GetProcAddress(Library, "WbioQueryStorageInterface");
    if ( v15 )
    {
      v7 = ((__int64 (__fastcall *)(struct _WINBIO_STORAGE_INTERFACE **))v15)(&v25);
      v9 = v7;
      if ( v7 < 0 )
      {
        v10 = 853;
        goto LABEL_10;
      }
      if ( !PlugIn::IsValidOrNullStorageInterface(v16, v25) )
      {
        v12 = 857;
        goto LABEL_34;
      }
    }
    else
    {
      v17 = v25;
    }
    v18 = v24;
    v19 = v23;
    if ( !v23 && !v24 && !v17 )
    {
      v9 = -2147467262;
      v11 = 2147500034LL;
      v10 = 866;
      goto LABEL_11;
    }
    if ( v2 != v21 )
    {
      wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
        v2,
        Library);
      *(_QWORD *)v21 = 0;
      v19 = v23;
      v18 = v24;
      v17 = v25;
    }
    *((_QWORD *)this + 6) = v19;
    *((_QWORD *)this + 7) = v18;
    *((_QWORD *)this + 8) = v17;
    wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v21);
    return 0;
  }
  v7 = ((__int64 (__fastcall *)(struct _WINBIO_SENSOR_INTERFACE **))ProcAddress)(&v23);
  v9 = v7;
  if ( v7 >= 0 )
  {
    if ( !PlugIn::IsValidOrNullSensorInterface(v8, v23) )
    {
      v12 = 819;
LABEL_34:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v12,
        (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\plugin.cpp",
        (const char *)0x8009803DLL,
        v21[0]);
      v9 = -2146860995;
      goto LABEL_35;
    }
    goto LABEL_14;
  }
  v10 = 815;
LABEL_10:
  v11 = (unsigned int)v7;
LABEL_11:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\ds\\security\\biometrics\\service\\trustlet\\exe\\plugin.cpp",
    (const char *)v11,
    v21[0]);
LABEL_35:
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(v21);
  return v9;
}

```

## disassembly

```asm
0x14005b074  push    rbp
0x14005b076  push    rbx
0x14005b077  push    rsi
0x14005b078  push    rdi
0x14005b079  push    r14
0x14005b07b  mov     rbp, rsp
0x14005b07e  sub     rsp, 30h
0x14005b082  mov     rsi, rcx
0x14005b085  cmp     dword ptr [rcx], 1
0x14005b088  jnz     loc_14005B257
0x14005b08e  lea     r14, [rcx+28h]
0x14005b092  cmp     qword ptr [r14], 0
0x14005b096  jnz     loc_14005B257
0x14005b09c  add     rcx, 8
0x14005b0a0  cmp     qword ptr [rcx+18h], 7
0x14005b0a5  jbe     short loc_14005B0AA
0x14005b0a7  mov     rcx, [rcx]; lpLibFileName
0x14005b0aa  xor     edx, edx; hFile
0x14005b0ac  mov     r8d, 900h; dwFlags
0x14005b0b2  call    cs:__imp_LoadLibraryExW
0x14005b0b9  nop     dword ptr [rax+rax+00h]
0x14005b0be  mov     rbx, rax
0x14005b0c1  mov     qword ptr [rbp+var_10], rax
0x14005b0c5  mov     rcx, rax; BaseAddress
0x14005b0c8  call    cs:__imp_RtlImageNtHeader
0x14005b0cf  nop     dword ptr [rax+rax+00h]
0x14005b0d4  test    rax, rax
0x14005b0d7  jz      loc_14005B265
0x14005b0dd  test    byte ptr [rax+5Eh], 80h
0x14005b0e1  jz      loc_14005B265
0x14005b0e7  mov     [rbp+arg_0], 0
0x14005b0ef  lea     rdx, aWbioquerysenso; "WbioQuerySensorInterface"
0x14005b0f6  mov     rcx, rbx; hModule
0x14005b0f9  call    cs:__imp_GetProcAddress
0x14005b100  nop     dword ptr [rax+rax+00h]
0x14005b105  test    rax, rax
0x14005b108  jz      short loc_14005B14D
0x14005b10a  lea     rcx, [rbp+arg_0]
0x14005b10e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b113  mov     edi, eax
0x14005b115  test    eax, eax
0x14005b117  jns     short loc_14005B136
0x14005b119  mov     edx, 32Fh; void *
0x14005b11e  mov     r9d, eax; char *
0x14005b121  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\biometrics\\serv"...
0x14005b128  mov     rcx, [rbp+28h]; this
0x14005b12c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005b131  jmp     loc_14005B284
0x14005b136  mov     rdx, [rbp+arg_0]; struct _WINBIO_SENSOR_INTERFACE *
0x14005b13a  call    ?IsValidOrNullSensorInterface@PlugIn@@AEAA_NPEAU_WINBIO_SENSOR_INTERFACE@@@Z; PlugIn::IsValidOrNullSensorInterface(_WINBIO_SENSOR_INTERFACE *)
0x14005b13f  test    al, al
0x14005b141  jnz     short loc_14005B14D
0x14005b143  mov     edx, 333h
0x14005b148  jmp     loc_14005B26A
0x14005b14d  mov     [rbp+arg_8], 0
0x14005b155  lea     rdx, aWbioqueryengin; "WbioQueryEngineInterface"
0x14005b15c  mov     rcx, rbx; hModule
0x14005b15f  call    cs:__imp_GetProcAddress
0x14005b166  nop     dword ptr [rax+rax+00h]
0x14005b16b  test    rax, rax
0x14005b16e  jz      short loc_14005B19D
0x14005b170  lea     rcx, [rbp+arg_8]
0x14005b174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b179  mov     edi, eax
0x14005b17b  test    eax, eax
0x14005b17d  jns     short loc_14005B186
0x14005b17f  mov     edx, 342h
0x14005b184  jmp     short loc_14005B11E
0x14005b186  mov     rdx, [rbp+arg_8]; struct _WINBIO_ENGINE_INTERFACE *
0x14005b18a  call    ?IsValidOrNullEngineInterface@PlugIn@@AEAA_NPEAU_WINBIO_ENGINE_INTERFACE@@@Z; PlugIn::IsValidOrNullEngineInterface(_WINBIO_ENGINE_INTERFACE *)
0x14005b18f  test    al, al
0x14005b191  jnz     short loc_14005B19D
0x14005b193  mov     edx, 346h
0x14005b198  jmp     loc_14005B26A
0x14005b19d  mov     [rbp+arg_10], 0
0x14005b1a5  lea     rdx, aWbioquerystora; "WbioQueryStorageInterface"
0x14005b1ac  mov     rcx, rbx; hModule
0x14005b1af  call    cs:__imp_GetProcAddress
0x14005b1b6  nop     dword ptr [rax+rax+00h]
0x14005b1bb  test    rax, rax
0x14005b1be  jz      short loc_14005B1ED
0x14005b1c0  lea     rcx, [rbp+arg_10]
0x14005b1c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005b1c9  mov     edi, eax
0x14005b1cb  test    eax, eax
0x14005b1cd  jns     short loc_14005B1D9
0x14005b1cf  mov     edx, 355h
0x14005b1d4  jmp     loc_14005B11E
0x14005b1d9  mov     rdx, [rbp+arg_10]; struct _WINBIO_STORAGE_INTERFACE *
0x14005b1dd  call    ?IsValidOrNullStorageInterface@PlugIn@@AEAA_NPEAU_WINBIO_STORAGE_INTERFACE@@@Z; PlugIn::IsValidOrNullStorageInterface(_WINBIO_STORAGE_INTERFACE *)
0x14005b1e2  test    al, al
0x14005b1e4  jnz     short loc_14005B1F1
0x14005b1e6  mov     edx, 359h
0x14005b1eb  jmp     short loc_14005B26A
0x14005b1ed  mov     rdx, [rbp+arg_10]
0x14005b1f1  mov     rax, [rbp+arg_8]
0x14005b1f5  mov     rcx, [rbp+arg_0]
0x14005b1f9  test    rcx, rcx
0x14005b1fc  jnz     short loc_14005B21A
0x14005b1fe  test    rax, rax
0x14005b201  jnz     short loc_14005B21A
0x14005b203  test    rdx, rdx
0x14005b206  jnz     short loc_14005B21A
0x14005b208  mov     edi, 80004002h
0x14005b20d  mov     r9d, edi
0x14005b210  mov     edx, 362h
0x14005b215  jmp     loc_14005B121
0x14005b21a  lea     r8, [rbp+var_10]
0x14005b21e  cmp     r14, r8
0x14005b221  jz      short loc_14005B242
0x14005b223  mov     rdx, rbx
0x14005b226  mov     rcx, r14
0x14005b229  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x14005b22e  mov     qword ptr [rbp+var_10], 0
0x14005b236  mov     rcx, [rbp+arg_0]
0x14005b23a  mov     rax, [rbp+arg_8]
0x14005b23e  mov     rdx, [rbp+arg_10]
0x14005b242  mov     [rsi+30h], rcx
0x14005b246  mov     [rsi+38h], rax
0x14005b24a  mov     [rsi+40h], rdx
0x14005b24e  lea     rcx, [rbp+var_10]
0x14005b252  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x14005b257  xor     eax, eax
0x14005b259  add     rsp, 30h
0x14005b25d  pop     r14
0x14005b25f  pop     rdi
0x14005b260  pop     rsi
0x14005b261  pop     rbx
0x14005b262  pop     rbp
0x14005b263  retn
0x14005b265  mov     edx, 31Bh; void *
0x14005b26a  mov     ebx, 8009803Dh
0x14005b26f  mov     r9d, ebx; char *
0x14005b272  lea     r8, aOnecoreDsSecur_16; "onecore\\ds\\security\\biometrics\\serv"...
0x14005b279  mov     rcx, [rbp+28h]; this
0x14005b27d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14005b282  mov     edi, ebx
0x14005b284  lea     rcx, [rbp+var_10]
0x14005b288  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x14005b28d  mov     eax, edi
0x14005b28f  jmp     short loc_14005B259
```
