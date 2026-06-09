# RecycleBinPolicy::CleanupItem(void *,TraceLoggingActivity<&_tlgProvider_t const * const StorageServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider> *)

- ea: `0x18002f210`
- end: `0x18002f705`
- name: `?CleanupItem@RecycleBinPolicy@@UEAAJPEAXPEAV?$TraceLoggingActivity@$1?StorageServiceProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@@Z`
- size: `1269`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000d030`
- `0x180012714`
- `0x180012734`
- `0x180014a00`
- `0x180018d54`
- `0x180019234`
- `0x180019d4c`
- `0x18001dcf4`
- `0x18001fcac`
- `0x18002f210`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f455`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f455`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002f3c4`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002f3c4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18002f2fa`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x18002f2fa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002f43c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002f43c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002f65a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002f65a`
- `RPCRT4!RpcRevertToSelf` at `0x18002f2d6`
- `RPCRT4!RpcRevertToSelf` at `0x18002f33d`
- `RPCRT4!RpcRevertToSelf` at `0x18002f38d`
- `RPCRT4!RpcRevertToSelf` at `0x18002f3f8`
- `RPCRT4!RpcRevertToSelf` at `0x18002f492`
- `RPCRT4!RpcRevertToSelf` at `0x18002f513`
- `RPCRT4!RpcRevertToSelf` at `0x18002f572`
- `RPCRT4!RpcRevertToSelf` at `0x18002f5d6`
- `RPCRT4!RpcRevertToSelf` at `0x18002f633`
- `RPCRT4!RpcRevertToSelf` at `0x18002f686`
- `RPCRT4!RpcRevertToSelf` at `0x18002f6ae`
- `RPCRT4!RpcRevertToSelf` at `0x18002f2d6`
- `RPCRT4!RpcRevertToSelf` at `0x18002f33d`
- `RPCRT4!RpcRevertToSelf` at `0x18002f38d`
- `RPCRT4!RpcRevertToSelf` at `0x18002f3f8`
- `RPCRT4!RpcRevertToSelf` at `0x18002f492`
- `RPCRT4!RpcRevertToSelf` at `0x18002f513`
- `RPCRT4!RpcRevertToSelf` at `0x18002f572`
- `RPCRT4!RpcRevertToSelf` at `0x18002f5d6`
- `RPCRT4!RpcRevertToSelf` at `0x18002f633`
- `RPCRT4!RpcRevertToSelf` at `0x18002f686`
- `RPCRT4!RpcRevertToSelf` at `0x18002f6ae`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f4e3`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002f4e3`

## string_xrefs

- `0x18002f2b9`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x18002f320`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x18002f370`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x18002f3db`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x18002f475`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x18002f4f6`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x18002f555`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x18002f5b9`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x18002f616`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x18002f668`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall RecycleBinPolicy::CleanupItem(__int64 a1)
{
  __int64 v2; // rdi
  __int64 (__fastcall *v3)(__int64, __int64, LPCWSTR *); // rbx
  int v4; // eax
  unsigned int v5; // ebx
  char v6; // cl
  LPWSTR FileNameW; // rdi
  unsigned __int64 v8; // rdx
  int v9; // eax
  char v10; // cl
  char v11; // al
  char v12; // al
  HANDLE FileW; // rax
  signed int LastError; // eax
  char v15; // al
  HRESULT v16; // eax
  char v17; // cl
  int v18; // eax
  char v19; // cl
  int v20; // eax
  char v21; // cl
  int v22; // eax
  char v23; // cl
  const char *v24; // r9
  char v25; // cl
  char v26; // al
  int bIgnoreCase; // [rsp+20h] [rbp-29h]
  int bIgnoreCasea; // [rsp+20h] [rbp-29h]
  int bIgnoreCaseb; // [rsp+20h] [rbp-29h]
  int bIgnoreCasec; // [rsp+20h] [rbp-29h]
  _BYTE v32[8]; // [rsp+40h] [rbp-9h] BYREF
  LPVOID ppv; // [rsp+48h] [rbp-1h] BYREF
  __int64 v34; // [rsp+50h] [rbp+7h] BYREF
  __int64 v35; // [rsp+58h] [rbp+Fh] BYREF
  LPCWSTR pszPath; // [rsp+60h] [rbp+17h] BYREF
  __int64 v37; // [rsp+68h] [rbp+1Fh]
  __int64 v38; // [rsp+70h] [rbp+27h]
  unsigned __int64 v39; // [rsp+78h] [rbp+2Fh] BYREF
  WCHAR String2[4]; // [rsp+80h] [rbp+37h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  wcscpy(String2, L"$R");
  pszPath = 0;
  v37 = 0;
  v38 = 0;
  v35 = 0;
  v34 = 0;
  ppv = 0;
  AutoRpcImpersonateClient(v32);
  v2 = *(_QWORD *)(a1 + 64);
  v3 = *(__int64 (__fastcall **)(__int64, __int64, LPCWSTR *))(*(_QWORD *)v2 + 40LL);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
  v37 = -1;
  v38 = -1;
  v4 = v3(v2, 2147844096LL, &pszPath);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45B,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)(unsigned int)v4,
      bIgnoreCase);
    v6 = v32[0];
    v32[0] = 0;
    if ( v6 )
      RpcRevertToSelf();
LABEL_44:
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
    goto LABEL_48;
  }
  FileNameW = PathFindFileNameW(pszPath);
  v39 = 0;
  v9 = StringCchLengthW(FileNameW, v8, &v39);
  v5 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x460,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)(unsigned int)v9,
      bIgnoreCase);
    v10 = v32[0];
    v32[0] = 0;
    if ( v10 )
      RpcRevertToSelf();
    goto LABEL_44;
  }
  if ( v39 < 3 )
  {
    v5 = -2147418113;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x461,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)0x8000FFFFLL,
      bIgnoreCase);
    v11 = v32[0];
    v32[0] = 0;
    if ( v11 )
      RpcRevertToSelf();
    goto LABEL_44;
  }
  if ( CompareStringOrdinal(FileNameW, 2, String2, -1, 1) != 2 )
  {
    v5 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x467,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)0x80070057LL,
      bIgnoreCasea);
    v12 = v32[0];
    v32[0] = 0;
    if ( v12 )
      RpcRevertToSelf();
    goto LABEL_44;
  }
  FileW = CreateFileW(pszPath, 0x80000000, 1u, 0, 3u, 0x2000000u, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &v35,
    FileW);
  if ( v35 == -1 )
  {
    LastError = GetLastError();
    v5 = LastError;
    if ( LastError > 0 )
      v5 = (unsigned __int16)LastError | 0x80070000;
    if ( (v5 & 0x80000000) != 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x475,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
        (const char *)v5,
        bIgnoreCaseb);
    v15 = v32[0];
    v32[0] = 0;
    if ( v15 )
      RpcRevertToSelf();
    goto LABEL_44;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &v35,
    0);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
  v16 = CoCreateInstance(&CLSID_FileOperation, 0, 0x17u, &GUID_947aab5f_0a5c_4c13_b4d6_4bf7836fc9f8, &ppv);
  v5 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x479,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)(unsigned int)v16,
      bIgnoreCasec);
    v17 = v32[0];
    v32[0] = 0;
    if ( v17 )
      RpcRevertToSelf();
    goto LABEL_44;
  }
  v18 = (*(__int64 (__fastcall **)(LPVOID, __int64))(*(_QWORD *)ppv + 40LL))(ppv, 1556);
  v5 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47A,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)(unsigned int)v18,
      bIgnoreCasec);
    v19 = v32[0];
    v32[0] = 0;
    if ( v19 )
      RpcRevertToSelf();
    goto LABEL_44;
  }
  v20 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, _QWORD))(*(_QWORD *)ppv + 144LL))(ppv, *(_QWORD *)(a1 + 64), 0);
  v5 = v20;
  if ( v20 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47B,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)(unsigned int)v20,
      bIgnoreCasec);
    v21 = v32[0];
    v32[0] = 0;
    if ( v21 )
      RpcRevertToSelf();
    goto LABEL_44;
  }
  v22 = (*(__int64 (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 168LL))(ppv);
  v5 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47C,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)(unsigned int)v22,
      bIgnoreCasec);
    v23 = v32[0];
    v32[0] = 0;
    if ( v23 )
      RpcRevertToSelf();
    goto LABEL_44;
  }
  FileNameW[1] = 73;
  if ( !DeleteFileW(pszPath) )
  {
    v5 = wil::details::in1diag3::Return_GetLastError(
           retaddr,
           (void *)0x480,
           (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
           v24);
    v25 = v32[0];
    v32[0] = 0;
    if ( v25 )
      RpcRevertToSelf();
    goto LABEL_44;
  }
  v26 = v32[0];
  v32[0] = 0;
  if ( v26 )
    RpcRevertToSelf();
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&ppv);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
  v5 = 0;
LABEL_48:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v35);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
  return v5;
}

```

## disassembly

```asm
0x18002f210  mov     [rsp-8+arg_8], rbx
0x18002f215  mov     [rsp-8+arg_10], rsi
0x18002f21a  push    rbp
0x18002f21b  push    rdi
0x18002f21c  push    r14
0x18002f21e  lea     rbp, [rsp-47h]
0x18002f223  sub     rsp, 90h
0x18002f22a  mov     rax, cs:__security_cookie
0x18002f231  xor     rax, rsp
0x18002f234  mov     [rbp+57h+var_18], rax
0x18002f238  mov     rsi, rcx
0x18002f23b  mov     eax, dword ptr cs:aR; "$R"
0x18002f241  mov     dword ptr [rbp+57h+String2], eax
0x18002f244  movzx   eax, word ptr cs:aR+4; ""
0x18002f24b  mov     [rbp+57h+var_1C], ax
0x18002f24f  xor     r14d, r14d
0x18002f252  mov     [rbp+57h+pszPath], r14
0x18002f256  mov     [rbp+57h+var_38], r14
0x18002f25a  mov     [rbp+57h+var_30], r14
0x18002f25e  mov     [rbp+57h+var_48], r14
0x18002f262  mov     [rbp+57h+var_50], r14
0x18002f266  mov     [rbp+57h+ppv], r14
0x18002f26a  lea     rcx, [rbp+57h+var_60]
0x18002f26e  call    ?AutoRpcImpersonateClient@@YA?AV?$unique_call@P6AJXZ$1?RpcRevertToSelf@@YAJXZ$00@wil@@XZ; AutoRpcImpersonateClient(void)
0x18002f273  nop
0x18002f274  mov     rdi, [rsi+40h]
0x18002f278  mov     rax, [rdi]
0x18002f27b  mov     rbx, [rax+28h]
0x18002f27f  lea     rcx, [rbp+57h+pszPath]
0x18002f283  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002f288  mov     [rbp+57h+var_38], 0FFFFFFFFFFFFFFFFh
0x18002f290  mov     [rbp+57h+var_30], 0FFFFFFFFFFFFFFFFh
0x18002f298  lea     r8, [rbp+57h+pszPath]
0x18002f29c  mov     edx, 80058000h
0x18002f2a1  mov     rcx, rdi
0x18002f2a4  mov     rax, rbx
0x18002f2a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f2ac  mov     ebx, eax
0x18002f2ae  test    eax, eax
0x18002f2b0  jns     short loc_18002F2F6
0x18002f2b2  mov     rcx, [rbp+5Fh]; this
0x18002f2b6  mov     r9d, eax; char *
0x18002f2b9  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18002f2c0  mov     edx, 45Bh; void *
0x18002f2c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f2ca  nop
0x18002f2cb  mov     cl, [rbp+57h+var_60]
0x18002f2ce  mov     [rbp+57h+var_60], r14b
0x18002f2d2  test    cl, cl
0x18002f2d4  jz      short loc_18002F2DD
0x18002f2d6  call    cs:__imp_RpcRevertToSelf
0x18002f2dc  nop
0x18002f2dd  lea     rcx, [rbp+57h+ppv]
0x18002f2e1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002f2e6  nop
0x18002f2e7  lea     rcx, [rbp+57h+var_50]
0x18002f2eb  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002f2f0  nop
0x18002f2f1  jmp     loc_18002F6CC
0x18002f2f6  mov     rcx, [rbp+57h+pszPath]; pszPath
0x18002f2fa  call    cs:__imp_PathFindFileNameW
0x18002f300  mov     rdi, rax
0x18002f303  mov     [rbp+57h+var_28], r14
0x18002f307  lea     r8, [rbp+57h+var_28]; unsigned __int64 *
0x18002f30b  mov     rcx, rax; unsigned __int16 *
0x18002f30e  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002f313  mov     ebx, eax
0x18002f315  test    eax, eax
0x18002f317  jns     short loc_18002F35D
0x18002f319  mov     rcx, [rbp+5Fh]; this
0x18002f31d  mov     r9d, eax; char *
0x18002f320  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18002f327  mov     edx, 460h; void *
0x18002f32c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f331  nop
0x18002f332  mov     cl, [rbp+57h+var_60]
0x18002f335  mov     [rbp+57h+var_60], r14b
0x18002f339  test    cl, cl
0x18002f33b  jz      short loc_18002F344
0x18002f33d  call    cs:__imp_RpcRevertToSelf
0x18002f343  nop
0x18002f344  lea     rcx, [rbp+57h+ppv]
0x18002f348  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002f34d  nop
0x18002f34e  lea     rcx, [rbp+57h+var_50]
0x18002f352  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002f357  nop
0x18002f358  jmp     loc_18002F6CC
0x18002f35d  cmp     [rbp+57h+var_28], 3
0x18002f362  jnb     short loc_18002F3AD
0x18002f364  mov     rcx, [rbp+5Fh]; this
0x18002f368  mov     ebx, 8000FFFFh
0x18002f36d  mov     r9d, ebx; char *
0x18002f370  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18002f377  mov     edx, 461h; void *
0x18002f37c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f381  nop
0x18002f382  mov     al, [rbp+57h+var_60]
0x18002f385  mov     [rbp+57h+var_60], r14b
0x18002f389  test    al, al
0x18002f38b  jz      short loc_18002F394
0x18002f38d  call    cs:__imp_RpcRevertToSelf
0x18002f393  nop
0x18002f394  lea     rcx, [rbp+57h+ppv]
0x18002f398  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002f39d  nop
0x18002f39e  lea     rcx, [rbp+57h+var_50]
0x18002f3a2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002f3a7  nop
0x18002f3a8  jmp     loc_18002F6CC
0x18002f3ad  mov     ebx, 1
0x18002f3b2  mov     [rsp+0A0h+bIgnoreCase], ebx; int
0x18002f3b6  or      r9d, 0FFFFFFFFh; cchCount2
0x18002f3ba  lea     r8, [rbp+57h+String2]; lpString2
0x18002f3be  lea     edx, [rbx+1]; cchCount1
0x18002f3c1  mov     rcx, rdi; lpString1
0x18002f3c4  call    cs:__imp_CompareStringOrdinal
0x18002f3ca  cmp     eax, 2
0x18002f3cd  jz      short loc_18002F418
0x18002f3cf  mov     rcx, [rbp+5Fh]; this
0x18002f3d3  mov     ebx, 80070057h
0x18002f3d8  mov     r9d, ebx; char *
0x18002f3db  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18002f3e2  mov     edx, 467h; void *
0x18002f3e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f3ec  nop
0x18002f3ed  mov     al, [rbp+57h+var_60]
0x18002f3f0  mov     [rbp+57h+var_60], r14b
0x18002f3f4  test    al, al
0x18002f3f6  jz      short loc_18002F3FF
0x18002f3f8  call    cs:__imp_RpcRevertToSelf
0x18002f3fe  nop
0x18002f3ff  lea     rcx, [rbp+57h+ppv]
0x18002f403  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002f408  nop
0x18002f409  lea     rcx, [rbp+57h+var_50]
0x18002f40d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002f412  nop
0x18002f413  jmp     loc_18002F6CC
0x18002f418  mov     [rsp+0A0h+hTemplateFile], r14; hTemplateFile
0x18002f41d  mov     [rsp+0A0h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18002f425  mov     [rsp+0A0h+bIgnoreCase], 3; int
0x18002f42d  xor     r9d, r9d; lpSecurityAttributes
0x18002f430  mov     r8d, ebx; dwShareMode
0x18002f433  mov     edx, 80000000h; dwDesiredAccess
0x18002f438  mov     rcx, [rbp+57h+pszPath]; lpFileName
0x18002f43c  call    cs:__imp_CreateFileW
0x18002f442  mov     rdx, rax
0x18002f445  lea     rcx, [rbp+57h+var_48]
0x18002f449  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002f44e  cmp     [rbp+57h+var_48], 0FFFFFFFFFFFFFFFFh
0x18002f453  jnz     short loc_18002F4B2
0x18002f455  call    cs:__imp_GetLastError
0x18002f45b  mov     ebx, eax
0x18002f45d  test    eax, eax
0x18002f45f  jle     short loc_18002F46A
0x18002f461  movzx   ebx, ax
0x18002f464  or      ebx, 80070000h
0x18002f46a  test    ebx, ebx
0x18002f46c  jns     short loc_18002F487
0x18002f46e  mov     rcx, [rbp+5Fh]; this
0x18002f472  mov     r9d, ebx; char *
0x18002f475  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18002f47c  mov     edx, 475h; void *
0x18002f481  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f486  nop
0x18002f487  mov     al, [rbp+57h+var_60]
0x18002f48a  mov     [rbp+57h+var_60], r14b
0x18002f48e  test    al, al
0x18002f490  jz      short loc_18002F499
0x18002f492  call    cs:__imp_RpcRevertToSelf
0x18002f498  nop
0x18002f499  lea     rcx, [rbp+57h+ppv]
0x18002f49d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002f4a2  nop
0x18002f4a3  lea     rcx, [rbp+57h+var_50]
0x18002f4a7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002f4ac  nop
0x18002f4ad  jmp     loc_18002F6CC
0x18002f4b2  xor     edx, edx
0x18002f4b4  lea     rcx, [rbp+57h+var_48]
0x18002f4b8  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002f4bd  lea     rcx, [rbp+57h+ppv]
0x18002f4c1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002f4c6  lea     rax, [rbp+57h+ppv]
0x18002f4ca  mov     qword ptr [rsp+0A0h+bIgnoreCase], rax; int
0x18002f4cf  lea     r9, _GUID_947aab5f_0a5c_4c13_b4d6_4bf7836fc9f8; riid
0x18002f4d6  xor     edx, edx; pUnkOuter
0x18002f4d8  lea     r8d, [rdx+17h]; dwClsContext
0x18002f4dc  lea     rcx, CLSID_FileOperation; rclsid
0x18002f4e3  call    cs:__imp_CoCreateInstance
0x18002f4e9  mov     ebx, eax
0x18002f4eb  test    eax, eax
0x18002f4ed  jns     short loc_18002F533
0x18002f4ef  mov     rcx, [rbp+5Fh]; this
0x18002f4f3  mov     r9d, eax; char *
0x18002f4f6  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18002f4fd  mov     edx, 479h; void *
0x18002f502  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f507  nop
0x18002f508  mov     cl, [rbp+57h+var_60]
0x18002f50b  mov     [rbp+57h+var_60], r14b
0x18002f50f  test    cl, cl
0x18002f511  jz      short loc_18002F51A
0x18002f513  call    cs:__imp_RpcRevertToSelf
0x18002f519  nop
0x18002f51a  lea     rcx, [rbp+57h+ppv]
0x18002f51e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002f523  nop
0x18002f524  lea     rcx, [rbp+57h+var_50]
0x18002f528  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002f52d  nop
0x18002f52e  jmp     loc_18002F6CC
0x18002f533  mov     rcx, [rbp+57h+ppv]
0x18002f537  mov     rax, [rcx]
0x18002f53a  mov     edx, 614h
0x18002f53f  mov     rax, [rax+28h]
0x18002f543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f548  mov     ebx, eax
0x18002f54a  test    eax, eax
0x18002f54c  jns     short loc_18002F592
0x18002f54e  mov     rcx, [rbp+5Fh]; this
0x18002f552  mov     r9d, eax; char *
0x18002f555  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18002f55c  mov     edx, 47Ah; void *
0x18002f561  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f566  nop
0x18002f567  mov     cl, [rbp+57h+var_60]
0x18002f56a  mov     [rbp+57h+var_60], r14b
0x18002f56e  test    cl, cl
0x18002f570  jz      short loc_18002F579
0x18002f572  call    cs:__imp_RpcRevertToSelf
0x18002f578  nop
0x18002f579  lea     rcx, [rbp+57h+ppv]
0x18002f57d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002f582  nop
0x18002f583  lea     rcx, [rbp+57h+var_50]
0x18002f587  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002f58c  nop
0x18002f58d  jmp     loc_18002F6CC
0x18002f592  mov     rcx, [rbp+57h+ppv]
0x18002f596  mov     rax, [rcx]
0x18002f599  xor     r8d, r8d
0x18002f59c  mov     rdx, [rsi+40h]
0x18002f5a0  mov     rax, [rax+90h]
0x18002f5a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5ac  mov     ebx, eax
0x18002f5ae  test    eax, eax
0x18002f5b0  jns     short loc_18002F5F6
0x18002f5b2  mov     rcx, [rbp+5Fh]; this
0x18002f5b6  mov     r9d, eax; char *
0x18002f5b9  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18002f5c0  mov     edx, 47Bh; void *
0x18002f5c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f5ca  nop
0x18002f5cb  mov     cl, [rbp+57h+var_60]
0x18002f5ce  mov     [rbp+57h+var_60], r14b
0x18002f5d2  test    cl, cl
0x18002f5d4  jz      short loc_18002F5DD
0x18002f5d6  call    cs:__imp_RpcRevertToSelf
0x18002f5dc  nop
0x18002f5dd  lea     rcx, [rbp+57h+ppv]
0x18002f5e1  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002f5e6  nop
0x18002f5e7  lea     rcx, [rbp+57h+var_50]
0x18002f5eb  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002f5f0  nop
0x18002f5f1  jmp     loc_18002F6CC
0x18002f5f6  mov     rcx, [rbp+57h+ppv]
0x18002f5fa  mov     rax, [rcx]
0x18002f5fd  mov     rax, [rax+0A8h]
0x18002f604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f609  mov     ebx, eax
0x18002f60b  test    eax, eax
0x18002f60d  jns     short loc_18002F650
0x18002f60f  mov     rcx, [rbp+5Fh]; this
0x18002f613  mov     r9d, eax; char *
0x18002f616  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18002f61d  mov     edx, 47Ch; void *
0x18002f622  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002f627  nop
0x18002f628  mov     cl, [rbp+57h+var_60]
0x18002f62b  mov     [rbp+57h+var_60], r14b
0x18002f62f  test    cl, cl
0x18002f631  jz      short loc_18002F63A
0x18002f633  call    cs:__imp_RpcRevertToSelf
0x18002f639  nop
0x18002f63a  lea     rcx, [rbp+57h+ppv]
0x18002f63e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002f643  nop
0x18002f644  lea     rcx, [rbp+57h+var_50]
0x18002f648  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18002f64d  nop
0x18002f64e  jmp     short loc_18002F6CC
0x18002f650  mov     word ptr [rdi+2], 49h ; 'I'
0x18002f656  mov     rcx, [rbp+57h+pszPath]; lpFileName
0x18002f65a  call    cs:__imp_DeleteFileW
0x18002f660  test    eax, eax
0x18002f662  jnz     short loc_18002F6A3
0x18002f664  mov     rcx, [rbp+5Fh]; this
  ... truncated ...
```
