# CMetadataQueryReaderWriter::EnsurePolicyComponent(void)

- ea: `0x180029dec`
- end: `0x180029fd4`
- name: `?EnsurePolicyComponent@CMetadataQueryReaderWriter@@AEAAJXZ`
- size: `488`
- prototype: `__int64 __fastcall(CMetadataQueryReaderWriter *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800297f0`
- `0x180040c80`
- `0x180041360`

## callees

- `0x180029dec`
- `0x1800bd9d4`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029f5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180029f5f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180029f31`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180029f31`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029f97`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029f97`

## string_xrefs

- `0x180029f55`: `DllGetClassObject`
- `0x180029f24`: `PhotoMetadataHandler.dll`

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
0x180029dec  mov     [rsp+arg_10], rbx
0x180029df1  mov     [rsp+arg_18], rsi
0x180029df6  push    rdi
0x180029df7  sub     rsp, 30h
0x180029dfb  xor     ebx, ebx
0x180029dfd  lea     rsi, [rcx+68h]
0x180029e01  mov     rdi, rcx
0x180029e04  cmp     [rsi], rbx
0x180029e07  jz      short loc_180029E3C
0x180029e09  mov     rsi, [rsp+38h+arg_18]
0x180029e0e  mov     eax, ebx
0x180029e10  mov     rbx, [rsp+38h+arg_10]
0x180029e15  add     rsp, 30h
0x180029e19  pop     rdi
0x180029e1a  retn
0x180029e1c  test    eax, eax
0x180029e1e  jns     loc_180029EEA
0x180029e24  mov     rcx, [rsp+38h+arg_0]
0x180029e29  test    rcx, rcx
0x180029e2c  jz      short loc_180029E09
0x180029e2e  mov     rdx, [rcx]
0x180029e31  mov     rax, [rdx+10h]
0x180029e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e3a  jmp     short loc_180029E09
0x180029e3c  cmp     [rcx+74h], ebx
0x180029e3f  jz      short loc_180029E09
0x180029e41  mov     rax, qword ptr cs:?g_PhotoMetadataHandler_DLL@@3U_COMLESS_CO_DLL_DATA@@A+8; _COMLESS_CO_DLL_DATA g_PhotoMetadataHandler_DLL
0x180029e48  mov     [rsp+38h+arg_0], rbx
0x180029e4d  mov     [rsp+38h+arg_8], rbx
0x180029e52  test    rax, rax
0x180029e55  jz      loc_180029F22
0x180029e5b  mov     ebx, 80004005h
0x180029e60  test    rax, rax
0x180029e63  jz      short loc_180029EA8
0x180029e65  lea     r8, [rsp+38h+arg_8]
0x180029e6a  lea     rdx, IID_IClassFactory
0x180029e71  lea     rcx, CLSID_MetadataPolicyComponent
0x180029e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e7d  mov     ebx, eax
0x180029e7f  test    eax, eax
0x180029e81  js      short loc_180029EF7
0x180029e83  mov     rcx, [rsp+38h+arg_8]
0x180029e88  lea     r9, [rsp+38h+arg_0]
0x180029e8d  lea     r8, IID_IWICMetadataPolicyComponent
0x180029e94  xor     edx, edx
0x180029e96  mov     rax, [rcx]
0x180029e99  mov     rax, [rax+18h]
0x180029e9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ea2  mov     ebx, eax
0x180029ea4  test    eax, eax
0x180029ea6  js      short loc_180029EF7
0x180029ea8  mov     rcx, [rsp+38h+arg_8]
0x180029ead  test    rcx, rcx
0x180029eb0  jz      short loc_180029EBE
0x180029eb2  mov     rax, [rcx]
0x180029eb5  mov     rax, [rax+10h]
0x180029eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ebe  test    ebx, ebx
0x180029ec0  js      loc_180029F79
0x180029ec6  mov     rcx, [rsp+38h+arg_0]
0x180029ecb  lea     rax, [rdi+48h]
0x180029ecf  neg     rdi
0x180029ed2  sbb     rdx, rdx
0x180029ed5  mov     r8, [rcx]
0x180029ed8  and     rdx, rax
0x180029edb  mov     rax, [r8+18h]
0x180029edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ee4  mov     ebx, eax
0x180029ee6  test    eax, eax
0x180029ee8  js      short loc_180029F09
0x180029eea  mov     rax, [rsp+38h+arg_0]
0x180029eef  mov     [rsi], rax
0x180029ef2  jmp     loc_180029E09
0x180029ef7  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180029efe  jz      short loc_180029EA8
0x180029f00  mov     ecx, eax; int
0x180029f02  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180029f07  jmp     short loc_180029EA8
0x180029f09  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180029f10  jz      loc_180029E1C
0x180029f16  mov     ecx, eax; int
0x180029f18  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180029f1d  jmp     loc_180029E24
0x180029f22  xor     edx, edx; hFile
0x180029f24  lea     rcx, LibFileName; "PhotoMetadataHandler.dll"
0x180029f2b  mov     r8d, 800h; dwFlags
0x180029f31  call    cs:__imp_LoadLibraryExW
0x180029f38  nop     dword ptr [rax+rax+00h]
0x180029f3d  mov     qword ptr cs:?g_PhotoMetadataHandler_DLL@@3U_COMLESS_CO_DLL_DATA@@A, rax; _COMLESS_CO_DLL_DATA g_PhotoMetadataHandler_DLL
0x180029f44  test    rax, rax
0x180029f47  jnz     short loc_180029F55
0x180029f49  mov     rax, qword ptr cs:?g_PhotoMetadataHandler_DLL@@3U_COMLESS_CO_DLL_DATA@@A+8; _COMLESS_CO_DLL_DATA g_PhotoMetadataHandler_DLL
0x180029f50  jmp     loc_180029E5B
0x180029f55  lea     rdx, ProcName; "DllGetClassObject"
0x180029f5c  mov     rcx, rax; hModule
0x180029f5f  call    cs:__imp_GetProcAddress
0x180029f66  nop     dword ptr [rax+rax+00h]
0x180029f6b  test    rax, rax
0x180029f6e  jz      short loc_180029F49
0x180029f70  xchg    rax, qword ptr cs:?g_PhotoMetadataHandler_DLL@@3U_COMLESS_CO_DLL_DATA@@A+8; _COMLESS_CO_DLL_DATA g_PhotoMetadataHandler_DLL
0x180029f77  jmp     short loc_180029F49
0x180029f79  xor     edx, edx; pUnkOuter
0x180029f7b  lea     rax, [rsp+38h+arg_0]
0x180029f80  lea     r9, IID_IWICMetadataPolicyComponent; riid
0x180029f87  mov     [rsp+38h+ppv], rax; ppv
0x180029f8c  lea     rcx, CLSID_MetadataPolicyComponent; rclsid
0x180029f93  lea     r8d, [rdx+1]; dwClsContext
0x180029f97  call    cs:__imp_CoCreateInstance
0x180029f9e  nop     dword ptr [rax+rax+00h]
0x180029fa3  mov     ebx, eax
0x180029fa5  cmp     eax, 80040154h
0x180029faa  jz      short loc_180029FC6
0x180029fac  test    eax, eax
0x180029fae  jns     loc_180029EC6
0x180029fb4  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x180029fbb  jz      loc_180029E24
0x180029fc1  jmp     loc_180029F16
0x180029fc6  mov     dword ptr [rdi+74h], 0
0x180029fcd  xor     ebx, ebx
0x180029fcf  jmp     loc_180029E24
```
