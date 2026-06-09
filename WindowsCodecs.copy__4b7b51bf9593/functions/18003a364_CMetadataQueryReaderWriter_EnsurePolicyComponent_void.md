# CMetadataQueryReaderWriter::EnsurePolicyComponent(void)

- ea: `0x18003a364`
- end: `0x18003a539`
- name: `?EnsurePolicyComponent@CMetadataQueryReaderWriter@@AEAAJXZ`
- size: `469`
- prototype: `__int64 __fastcall(CMetadataQueryReaderWriter *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001b8d0`
- `0x18001bfa0`
- `0x180039d40`

## callees

- `0x18003a364`
- `0x1800bb784`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003a4d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003a4d0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003a4a8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003a4a8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003a502`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003a502`

## string_xrefs

- `0x18003a4c6`: `DllGetClassObject`
- `0x18003a49b`: `PhotoMetadataHandler.dll`

## pseudocode

```c
__int64 __fastcall CMetadataQueryReaderWriter::EnsurePolicyComponent(CMetadataQueryReaderWriter *this)
{
  unsigned int v1; // ebx
  LPVOID *v2; // rsi
  __int64 (__fastcall *v5)(GUID *, GUID *, __int64 *); // rax
  int v6; // ebx
  int v7; // eax
  HRESULT v8; // eax
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  LPVOID ppv; // [rsp+40h] [rbp+8h] BYREF
  __int64 v12; // [rsp+48h] [rbp+10h] BYREF

  v1 = 0;
  v2 = (LPVOID *)((char *)this + 104);
  if ( *((_QWORD *)this + 13) || !*((_DWORD *)this + 29) )
    return v1;
  v5 = (__int64 (__fastcall *)(GUID *, GUID *, __int64 *))*(&g_PhotoMetadataHandler_DLL + 1);
  ppv = 0;
  v12 = 0;
  if ( !*(&g_PhotoMetadataHandler_DLL + 1) )
  {
    Library = LoadLibraryExW(L"PhotoMetadataHandler.dll", 0, 0x800u);
    g_PhotoMetadataHandler_DLL = Library;
    if ( Library )
    {
      ProcAddress = GetProcAddress(Library, "DllGetClassObject");
      if ( ProcAddress )
        _InterlockedExchange64((volatile __int64 *)&g_PhotoMetadataHandler_DLL + 1, (__int64)ProcAddress);
    }
    v5 = (__int64 (__fastcall *)(GUID *, GUID *, __int64 *))*(&g_PhotoMetadataHandler_DLL + 1);
  }
  v6 = -2147467259;
  if ( v5 )
  {
    v7 = v5(&CLSID_MetadataPolicyComponent, &IID_IClassFactory, &v12);
    v6 = v7;
    if ( v7 < 0
      || (v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, LPVOID *))(*(_QWORD *)v12 + 24LL))(
                 v12,
                 0,
                 &IID_IWICMetadataPolicyComponent,
                 &ppv),
          v6 = v7,
          v7 < 0) )
    {
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(v7);
    }
  }
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v6 >= 0 )
  {
LABEL_13:
    v8 = (*(__int64 (__fastcall **)(LPVOID, unsigned __int64))(*(_QWORD *)ppv + 24LL))(
           ppv,
           ((unsigned __int64)this + 72) & -(__int64)(this != 0));
    v1 = v8;
    if ( v8 >= 0 )
    {
      *v2 = ppv;
      return v1;
    }
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_3;
    goto LABEL_18;
  }
  v8 = CoCreateInstance(&CLSID_MetadataPolicyComponent, 0, 1u, &IID_IWICMetadataPolicyComponent, &ppv);
  v1 = v8;
  if ( v8 == -2147221164 )
  {
    *((_DWORD *)this + 29) = 0;
    v1 = 0;
  }
  else
  {
    if ( v8 >= 0 )
      goto LABEL_13;
    if ( (_DWORD)g_doStackCaptures )
LABEL_18:
      DoStackCapture(v8);
  }
LABEL_3:
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v1;
}

```

## disassembly

```asm
0x18003a364  mov     [rsp+arg_10], rbx
0x18003a369  mov     [rsp+arg_18], rsi
0x18003a36e  push    rdi
0x18003a36f  sub     rsp, 30h
0x18003a373  xor     ebx, ebx
0x18003a375  lea     rsi, [rcx+68h]
0x18003a379  mov     rdi, rcx
0x18003a37c  cmp     [rsi], rbx
0x18003a37f  jz      short loc_18003A3B3
0x18003a381  mov     rsi, [rsp+38h+arg_18]
0x18003a386  mov     eax, ebx
0x18003a388  mov     rbx, [rsp+38h+arg_10]
0x18003a38d  add     rsp, 30h
0x18003a391  pop     rdi
0x18003a392  retn
0x18003a393  test    eax, eax
0x18003a395  jns     loc_18003A461
0x18003a39b  mov     rcx, [rsp+38h+arg_0]
0x18003a3a0  test    rcx, rcx
0x18003a3a3  jz      short loc_18003A381
0x18003a3a5  mov     rdx, [rcx]
0x18003a3a8  mov     rax, [rdx+10h]
0x18003a3ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a3b1  jmp     short loc_18003A381
0x18003a3b3  cmp     [rcx+74h], ebx
0x18003a3b6  jz      short loc_18003A381
0x18003a3b8  mov     rax, qword ptr cs:?g_PhotoMetadataHandler_DLL@@3U_COMLESS_CO_DLL_DATA@@A+8; _COMLESS_CO_DLL_DATA g_PhotoMetadataHandler_DLL
0x18003a3bf  mov     [rsp+38h+arg_0], rbx
0x18003a3c4  mov     [rsp+38h+arg_8], rbx
0x18003a3c9  test    rax, rax
0x18003a3cc  jz      loc_18003A499
0x18003a3d2  mov     ebx, 80004005h
0x18003a3d7  test    rax, rax
0x18003a3da  jz      short loc_18003A41F
0x18003a3dc  lea     r8, [rsp+38h+arg_8]
0x18003a3e1  lea     rdx, IID_IClassFactory
0x18003a3e8  lea     rcx, CLSID_MetadataPolicyComponent
0x18003a3ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a3f4  mov     ebx, eax
0x18003a3f6  test    eax, eax
0x18003a3f8  js      short loc_18003A46E
0x18003a3fa  mov     rcx, [rsp+38h+arg_8]
0x18003a3ff  lea     r9, [rsp+38h+arg_0]
0x18003a404  lea     r8, IID_IWICMetadataPolicyComponent
0x18003a40b  xor     edx, edx
0x18003a40d  mov     rax, [rcx]
0x18003a410  mov     rax, [rax+18h]
0x18003a414  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a419  mov     ebx, eax
0x18003a41b  test    eax, eax
0x18003a41d  js      short loc_18003A46E
0x18003a41f  mov     rcx, [rsp+38h+arg_8]
0x18003a424  test    rcx, rcx
0x18003a427  jz      short loc_18003A435
0x18003a429  mov     rax, [rcx]
0x18003a42c  mov     rax, [rax+10h]
0x18003a430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a435  test    ebx, ebx
0x18003a437  js      loc_18003A4E4
0x18003a43d  mov     rcx, [rsp+38h+arg_0]
0x18003a442  lea     rax, [rdi+48h]
0x18003a446  neg     rdi
0x18003a449  sbb     rdx, rdx
0x18003a44c  mov     r8, [rcx]
0x18003a44f  and     rdx, rax
0x18003a452  mov     rax, [r8+18h]
0x18003a456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a45b  mov     ebx, eax
0x18003a45d  test    eax, eax
0x18003a45f  js      short loc_18003A480
0x18003a461  mov     rax, [rsp+38h+arg_0]
0x18003a466  mov     [rsi], rax
0x18003a469  jmp     loc_18003A381
0x18003a46e  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18003a475  jz      short loc_18003A41F
0x18003a477  mov     ecx, eax; int
0x18003a479  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18003a47e  jmp     short loc_18003A41F
0x18003a480  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18003a487  jz      loc_18003A393
0x18003a48d  mov     ecx, eax; int
0x18003a48f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18003a494  jmp     loc_18003A39B
0x18003a499  xor     edx, edx; hFile
0x18003a49b  lea     rcx, LibFileName; "PhotoMetadataHandler.dll"
0x18003a4a2  mov     r8d, 800h; dwFlags
0x18003a4a8  call    cs:__imp_LoadLibraryExW
0x18003a4ae  mov     qword ptr cs:?g_PhotoMetadataHandler_DLL@@3U_COMLESS_CO_DLL_DATA@@A, rax; _COMLESS_CO_DLL_DATA g_PhotoMetadataHandler_DLL
0x18003a4b5  test    rax, rax
0x18003a4b8  jnz     short loc_18003A4C6
0x18003a4ba  mov     rax, qword ptr cs:?g_PhotoMetadataHandler_DLL@@3U_COMLESS_CO_DLL_DATA@@A+8; _COMLESS_CO_DLL_DATA g_PhotoMetadataHandler_DLL
0x18003a4c1  jmp     loc_18003A3D2
0x18003a4c6  lea     rdx, ProcName; "DllGetClassObject"
0x18003a4cd  mov     rcx, rax; hModule
0x18003a4d0  call    cs:__imp_GetProcAddress
0x18003a4d6  test    rax, rax
0x18003a4d9  jz      short loc_18003A4BA
0x18003a4db  xchg    rax, qword ptr cs:?g_PhotoMetadataHandler_DLL@@3U_COMLESS_CO_DLL_DATA@@A+8; _COMLESS_CO_DLL_DATA g_PhotoMetadataHandler_DLL
0x18003a4e2  jmp     short loc_18003A4BA
0x18003a4e4  xor     edx, edx; pUnkOuter
0x18003a4e6  lea     rax, [rsp+38h+arg_0]
0x18003a4eb  lea     r9, IID_IWICMetadataPolicyComponent; riid
0x18003a4f2  mov     [rsp+38h+ppv], rax; ppv
0x18003a4f7  lea     rcx, CLSID_MetadataPolicyComponent; rclsid
0x18003a4fe  lea     r8d, [rdx+1]; dwClsContext
0x18003a502  call    cs:__imp_CoCreateInstance
0x18003a508  mov     ebx, eax
0x18003a50a  cmp     eax, 80040154h
0x18003a50f  jz      short loc_18003A52B
0x18003a511  test    eax, eax
0x18003a513  jns     loc_18003A43D
0x18003a519  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18003a520  jz      loc_18003A39B
0x18003a526  jmp     loc_18003A48D
0x18003a52b  mov     dword ptr [rdi+74h], 0
0x18003a532  xor     ebx, ebx
0x18003a534  jmp     loc_18003A39B
```
