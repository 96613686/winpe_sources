# DownloadsFolderPolicy::UpdateCleanupList(ushort const *,std::list<std::shared_ptr<CCleanupPolicy>,std::allocator<std::shared_ptr<CCleanupPolicy>>> &,std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,std::unordered_map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,SYNC_ROOT_INFO,std::hash<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::equal_to<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,SYNC_ROOT_INFO>>> &)

- ea: `0x1800334b8`
- end: `0x180033764`
- name: `?UpdateCleanupList@DownloadsFolderPolicy@@SAJPEBGAEAV?$list@V?$shared_ptr@VCCleanupPolicy@@@std@@V?$allocator@V?$shared_ptr@VCCleanupPolicy@@@std@@@2@@std@@AEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@3@AEAV?$unordered_map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@USYNC_ROOT_INFO@@U?$hash@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@U?$equal_to@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@USYNC_ROOT_INFO@@@std@@@2@@3@@Z`
- size: `684`
- prototype: `__int64 __fastcall(const WCHAR *, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003253c`

## callees

- `0x180012734`
- `0x180014a00`
- `0x180018d54`
- `0x18001c130`
- `0x18001fcac`
- `0x18002ebe8`
- `0x18003037c`
- `0x180031560`
- `0x1800334b8`
- `0x18008a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800336ca`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x1800336ca`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1800334f7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18003367b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x1800334f7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x18003367b`
- `RPCRT4!RpcRevertToSelf` at `0x180033594`
- `RPCRT4!RpcRevertToSelf` at `0x1800335f4`
- `RPCRT4!RpcRevertToSelf` at `0x180033720`
- `RPCRT4!RpcRevertToSelf` at `0x180033594`
- `RPCRT4!RpcRevertToSelf` at `0x1800335f4`
- `RPCRT4!RpcRevertToSelf` at `0x180033720`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800335c0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800335c0`

## string_xrefs

- `0x180033546`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x1800335d1`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`
- `0x180033690`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall DownloadsFolderPolicy::UpdateCleanupList(const WCHAR *a1, int a2, __int64 a3, __int64 a4)
{
  int DriveNumberW; // r14d
  __int64 v8; // rcx
  int StoragePolicySettings; // eax
  __int64 v10; // rcx
  unsigned int v11; // ebx
  __int64 v12; // rdx
  _BYTE *v13; // rax
  char v14; // al
  HRESULT v15; // eax
  __int64 v16; // rdx
  bool v17; // zf
  LPVOID v18; // rdi
  __int64 (__fastcall *v19)(LPVOID, const GUID *, __int64 *); // rbx
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, _QWORD, LPCWSTR *); // rbx
  __int64 v22; // rdx
  _QWORD **v23; // rdi
  _QWORD *i; // rbx
  const wchar_t *v25; // rax
  char v26; // al
  int ppv; // [rsp+20h] [rbp-58h]
  int ppva; // [rsp+20h] [rbp-58h]
  char v30; // [rsp+30h] [rbp-48h] BYREF
  _BYTE v31[3]; // [rsp+31h] [rbp-47h] BYREF
  int v32; // [rsp+34h] [rbp-44h] BYREF
  int v33; // [rsp+38h] [rbp-40h] BYREF
  __int64 v34; // [rsp+40h] [rbp-38h] BYREF
  LPVOID v35; // [rsp+48h] [rbp-30h] BYREF
  LPCWSTR pszPath; // [rsp+50h] [rbp-28h] BYREF
  __int64 v37; // [rsp+58h] [rbp-20h]
  __int64 v38; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]

  v35 = 0;
  v34 = 0;
  pszPath = 0;
  v37 = 0;
  v38 = 0;
  v33 = 0;
  v32 = 720;
  DriveNumberW = PathGetDriveNumberW(a1);
  v30 = 0;
  StoragePolicySettings = StorageService::GetStoragePolicySettings(v8, 5, 0, &v33);
  v11 = StoragePolicySettings;
  if ( StoragePolicySettings < 0 )
  {
    v12 = 1254;
LABEL_6:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)(unsigned int)StoragePolicySettings,
      ppv);
LABEL_33:
    v30 = 0;
    goto LABEL_34;
  }
  if ( !v33 )
    goto LABEL_32;
  StoragePolicySettings = StorageService::GetStoragePolicySettings(v10, 9, 0, &v32);
  v11 = StoragePolicySettings;
  if ( StoragePolicySettings < 0 )
  {
    v12 = 1256;
    goto LABEL_6;
  }
  if ( !v32 )
  {
LABEL_32:
    v11 = -2147024891;
    goto LABEL_33;
  }
  v32 *= 24;
  v13 = AutoRpcImpersonateClient(v31);
  wil::unique_call<long (*)(void),&long RpcRevertToSelf(void),1>::operator=(&v30, v13);
  v14 = v31[0];
  v31[0] = 0;
  if ( v14 )
    RpcRevertToSelf();
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v35);
  v15 = CoCreateInstance(&CLSID_KnownFolderManager, 0, 1u, &GUID_8be2d872_86aa_4d47_b776_32cca40c7018, &v35);
  v11 = v15;
  if ( v15 < 0 )
  {
    v16 = 1266;
LABEL_12:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)(unsigned int)v15,
      ppva);
    v17 = v30 == 0;
LABEL_13:
    v30 = 0;
    if ( !v17 )
      RpcRevertToSelf();
    goto LABEL_34;
  }
  v18 = v35;
  v19 = *(__int64 (__fastcall **)(LPVOID, const GUID *, __int64 *))(*(_QWORD *)v35 + 48LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
  v15 = v19(v18, &FOLDERID_Downloads, &v34);
  v11 = v15;
  if ( v15 < 0 )
  {
    v16 = 1268;
    goto LABEL_12;
  }
  v20 = v34;
  v21 = *(__int64 (__fastcall **)(__int64, _QWORD, LPCWSTR *))(*(_QWORD *)v34 + 48LL);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
  v37 = -1;
  v38 = -1;
  v15 = v21(v20, 0, &pszPath);
  v11 = v15;
  if ( v15 < 0 )
  {
    v16 = 1269;
    goto LABEL_12;
  }
  if ( DriveNumberW != PathGetDriveNumberW(pszPath) )
  {
    v11 = -2147418113;
    v22 = 1270;
LABEL_21:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v22,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)v11,
      ppva);
    v17 = v30 == 0;
    goto LABEL_13;
  }
  v23 = *(_QWORD ***)(a4 + 8);
  for ( i = *v23; i != v23; i = (_QWORD *)*i )
  {
    v25 = (const wchar_t *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(i + 2);
    if ( wcsstr(pszPath, v25) )
    {
      v11 = -2147024846;
      v22 = 1275;
      goto LABEL_21;
    }
  }
  v15 = Util::RecursiveScanRootFolder(5, (_DWORD)pszPath, v32, a2, a3, a4);
  v11 = v15;
  if ( v15 < 0 )
  {
    v16 = 1283;
    goto LABEL_12;
  }
  v26 = v30;
  v30 = 0;
  if ( v26 )
    RpcRevertToSelf();
  v11 = 0;
LABEL_34:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPath);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v34);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v35);
  return v11;
}

```

## disassembly

```asm
0x1800334b8  push    rbp
0x1800334ba  push    rbx
0x1800334bb  push    rsi
0x1800334bc  push    rdi
0x1800334bd  push    r12
0x1800334bf  push    r13
0x1800334c1  push    r14
0x1800334c3  push    r15
0x1800334c5  mov     rbp, rsp
0x1800334c8  sub     rsp, 78h
0x1800334cc  mov     rsi, r9
0x1800334cf  mov     r15, r8
0x1800334d2  mov     r12, rdx
0x1800334d5  xor     r13d, r13d
0x1800334d8  mov     [rbp+var_30], r13
0x1800334dc  mov     [rbp+var_38], r13
0x1800334e0  mov     [rbp+pszPath], r13
0x1800334e4  mov     [rbp+var_20], r13
0x1800334e8  mov     [rbp+var_18], r13
0x1800334ec  mov     [rbp+var_40], r13d
0x1800334f0  mov     [rbp+var_44], 2D0h
0x1800334f7  call    cs:__imp_PathGetDriveNumberW
0x1800334fd  mov     r14d, eax
0x180033500  mov     [rbp+var_48], r13b
0x180033504  lea     r9, [rbp+var_40]
0x180033508  xor     r8d, r8d
0x18003350b  lea     edx, [r13+5]
0x18003350f  call    ?GetStoragePolicySettings@StorageService@@QEAAJW4_STORAGE_POLICY@@PEBGPEAK@Z; StorageService::GetStoragePolicySettings(_STORAGE_POLICY,ushort const *,ulong *)
0x180033514  mov     ebx, eax
0x180033516  test    eax, eax
0x180033518  jns     short loc_180033521
0x18003351a  mov     edx, 4E6h
0x18003351f  jmp     short loc_180033546
0x180033521  cmp     [rbp+var_40], r13d
0x180033525  jz      loc_18003372B
0x18003352b  lea     r9, [rbp+var_44]
0x18003352f  xor     r8d, r8d
0x180033532  lea     edx, [r8+9]
0x180033536  call    ?GetStoragePolicySettings@StorageService@@QEAAJW4_STORAGE_POLICY@@PEBGPEAK@Z; StorageService::GetStoragePolicySettings(_STORAGE_POLICY,ushort const *,ulong *)
0x18003353b  mov     ebx, eax
0x18003353d  test    eax, eax
0x18003353f  jns     short loc_18003355E
0x180033541  mov     edx, 4E8h; void *
0x180033546  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18003354d  mov     r9d, eax; char *
0x180033550  mov     rcx, [rbp+40h]; this
0x180033554  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180033559  jmp     loc_180033730
0x18003355e  mov     eax, [rbp+var_44]
0x180033561  test    eax, eax
0x180033563  jz      loc_18003372B
0x180033569  lea     eax, [rax+rax*2]
0x18003356c  shl     eax, 3
0x18003356f  mov     [rbp+var_44], eax
0x180033572  lea     rcx, [rbp+var_47]
0x180033576  call    ?AutoRpcImpersonateClient@@YA?AV?$unique_call@P6AJXZ$1?RpcRevertToSelf@@YAJXZ$00@wil@@XZ; AutoRpcImpersonateClient(void)
0x18003357b  nop
0x18003357c  mov     rdx, rax
0x18003357f  lea     rcx, [rbp+var_48]
0x180033583  call    ??4?$unique_call@P6AJXZ$1?RpcRevertToSelf@@YAJXZ$00@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_call<long (*)(void),&RpcRevertToSelf(void),1>::operator=(wil::unique_call<long (*)(void),&RpcRevertToSelf(void),1> &&)
0x180033588  nop
0x180033589  mov     al, [rbp+var_47]
0x18003358c  mov     [rbp+var_47], r13b
0x180033590  test    al, al
0x180033592  jz      short loc_18003359A
0x180033594  call    cs:__imp_RpcRevertToSelf
0x18003359a  lea     rcx, [rbp+var_30]
0x18003359e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800335a3  lea     rax, [rbp+var_30]
0x1800335a7  mov     [rsp+78h+ppv], rax; int
0x1800335ac  lea     r9, _GUID_8be2d872_86aa_4d47_b776_32cca40c7018; riid
0x1800335b3  xor     edx, edx; pUnkOuter
0x1800335b5  lea     r8d, [rdx+1]; dwClsContext
0x1800335b9  lea     rcx, CLSID_KnownFolderManager; rclsid
0x1800335c0  call    cs:__imp_CoCreateInstance
0x1800335c6  mov     ebx, eax
0x1800335c8  test    eax, eax
0x1800335ca  jns     short loc_1800335FF
0x1800335cc  mov     edx, 4F2h; void *
0x1800335d1  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x1800335d8  mov     r9d, eax; char *
0x1800335db  mov     rcx, [rbp+40h]; this
0x1800335df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800335e4  nop
0x1800335e5  mov     cl, [rbp+var_48]
0x1800335e8  test    cl, cl
0x1800335ea  mov     [rbp+var_48], r13b
0x1800335ee  jz      loc_180033734
0x1800335f4  call    cs:__imp_RpcRevertToSelf
0x1800335fa  jmp     loc_180033734
0x1800335ff  mov     rdi, [rbp+var_30]
0x180033603  mov     rax, [rdi]
0x180033606  mov     rbx, [rax+30h]
0x18003360a  lea     rcx, [rbp+var_38]
0x18003360e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180033613  lea     r8, [rbp+var_38]
0x180033617  lea     rdx, FOLDERID_Downloads
0x18003361e  mov     rcx, rdi
0x180033621  mov     rax, rbx
0x180033624  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033629  mov     ebx, eax
0x18003362b  test    eax, eax
0x18003362d  jns     short loc_180033636
0x18003362f  mov     edx, 4F4h
0x180033634  jmp     short loc_1800335D1
0x180033636  mov     rdi, [rbp+var_38]
0x18003363a  mov     rax, [rdi]
0x18003363d  mov     rbx, [rax+30h]
0x180033641  lea     rcx, [rbp+pszPath]
0x180033645  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003364a  or      rax, 0FFFFFFFFFFFFFFFFh
0x18003364e  mov     [rbp+var_20], rax
0x180033652  mov     [rbp+var_18], rax
0x180033656  lea     r8, [rbp+pszPath]
0x18003365a  xor     edx, edx
0x18003365c  mov     rcx, rdi
0x18003365f  mov     rax, rbx
0x180033662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033667  mov     ebx, eax
0x180033669  test    eax, eax
0x18003366b  jns     short loc_180033677
0x18003366d  mov     edx, 4F5h
0x180033672  jmp     loc_1800335D1
0x180033677  mov     rcx, [rbp+pszPath]; pszPath
0x18003367b  call    cs:__imp_PathGetDriveNumberW
0x180033681  cmp     r14d, eax
0x180033684  jz      short loc_1800336AE
0x180033686  mov     ebx, 8000FFFFh
0x18003368b  mov     edx, 4F6h; void *
0x180033690  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x180033697  mov     r9d, ebx; char *
0x18003369a  mov     rcx, [rbp+40h]; this
0x18003369e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800336a3  nop
0x1800336a4  mov     al, [rbp+var_48]
0x1800336a7  test    al, al
0x1800336a9  jmp     loc_1800335EA
0x1800336ae  mov     rdi, [rsi+8]
0x1800336b2  mov     rbx, [rdi]
0x1800336b5  cmp     rbx, rdi
0x1800336b8  jz      short loc_1800336E6
0x1800336ba  lea     rcx, [rbx+10h]
0x1800336be  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800336c3  mov     rdx, rax; SubStr
0x1800336c6  mov     rcx, [rbp+pszPath]; Str
0x1800336ca  call    cs:__imp_wcsstr
0x1800336d0  test    rax, rax
0x1800336d3  jnz     short loc_1800336DA
0x1800336d5  mov     rbx, [rbx]
0x1800336d8  jmp     short loc_1800336B5
0x1800336da  mov     ebx, 80070032h
0x1800336df  mov     edx, 4FBh
0x1800336e4  jmp     short loc_180033690
0x1800336e6  mov     [rsp+78h+var_50], rsi
0x1800336eb  mov     [rsp+78h+ppv], r15
0x1800336f0  mov     r9, r12
0x1800336f3  mov     r8d, [rbp+var_44]
0x1800336f7  mov     rdx, [rbp+pszPath]
0x1800336fb  mov     ecx, 5
0x180033700  call    Util__RecursiveScanRootFolder
0x180033705  mov     ebx, eax
0x180033707  test    eax, eax
0x180033709  jns     short loc_180033715
0x18003370b  mov     edx, 503h
0x180033710  jmp     loc_1800335D1
0x180033715  mov     al, [rbp+var_48]
0x180033718  mov     [rbp+var_48], r13b
0x18003371c  test    al, al
0x18003371e  jz      short loc_180033726
0x180033720  call    cs:__imp_RpcRevertToSelf
0x180033726  mov     ebx, r13d
0x180033729  jmp     short loc_180033734
0x18003372b  mov     ebx, 80070005h
0x180033730  mov     [rbp+var_48], r13b
0x180033734  lea     rcx, [rbp+pszPath]
0x180033738  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18003373d  nop
0x18003373e  lea     rcx, [rbp+var_38]
0x180033742  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180033747  nop
0x180033748  lea     rcx, [rbp+var_30]
0x18003374c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x180033751  mov     eax, ebx
0x180033753  add     rsp, 78h
0x180033757  pop     r15
0x180033759  pop     r14
0x18003375b  pop     r13
0x18003375d  pop     r12
0x18003375f  pop     rdi
0x180033760  pop     rsi
0x180033761  pop     rbx
0x180033762  pop     rbp
0x180033763  retn
```
