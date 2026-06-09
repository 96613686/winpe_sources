# CSyncRootManagerCache::MigrateKF(ushort const *,ulong,KFMapping *,int,HWND__ *,ushort * *)

- ea: `0x180067254`
- end: `0x18006745c`
- name: `?MigrateKF@CSyncRootManagerCache@@QEAAJPEBGKPEAUKFMapping@@HPEAUHWND__@@PEAPEAG@Z`
- size: `520`
- prototype: `__int64 __fastcall(CSyncRootManagerCache *__hidden this, const unsigned __int16 *, unsigned int, struct KFMapping *, int, HWND, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800671f0`

## callees

- `0x180004a54`
- `0x180007900`
- `0x1800092d0`
- `0x18001d320`
- `0x180067254`
- `0x180089010`

## import_xrefs

- `Windows.Storage!SHGetKnownFolderPath` at `0x180067350`
- `Windows.Storage!SHGetKnownFolderPath` at `0x180067350`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180067427`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180067427`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006729f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18006729f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800672db`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800672db`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800673e7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800673e7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180067364`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180067370`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180067364`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetDriveNumberW` at `0x180067370`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!PathIsDirectoryEmptyW` at `0x1800673f5`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!PathIsDirectoryEmptyW` at `0x1800673f5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSyncRootManagerCache::MigrateKF(
        RTL_SRWLOCK *this,
        WCHAR *a2,
        unsigned int a3,
        struct KFMapping *a4,
        int a5,
        HWND a6,
        unsigned __int16 **a7)
{
  HRESULT Instance; // ebx
  RTL_SRWLOCK *v11; // r14
  LPVOID v12; // rdi
  __int64 (__fastcall *v13)(LPVOID, GUID *, unsigned __int16 ***); // rbx
  __int64 i; // rdi
  char *v15; // rsi
  int DriveNumberW; // ebx
  int v17; // eax
  bool v18; // zf
  __int64 (__fastcall *v19)(unsigned __int16 **, char *, HWND, __int64, _QWORD, _DWORD, _QWORD, _QWORD); // rax
  int v20; // eax
  LPVOID ppv[2]; // [rsp+50h] [rbp-10h] BYREF
  PWSTR ppszPath; // [rsp+98h] [rbp+38h] BYREF

  ppszPath = a2;
  *a7 = 0;
  Instance = CSyncRootManagerCache::_EnsureCachedValuesReaderModeWrapper(this, 0xFFFFFFFFLL);
  if ( Instance >= 0 )
  {
    v11 = this + 3;
    AcquireSRWLockShared(this + 3);
    ppv[0] = 0;
    a7 = 0;
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(ppv);
    Instance = CoCreateInstance(&CLSID_KnownFolderManager, 0, 1u, &GUID_8be2d872_86aa_4d47_b776_32cca40c7018, ppv);
    if ( Instance >= 0 )
    {
      v12 = ppv[0];
      v13 = **(__int64 (__fastcall ***)(LPVOID, GUID *, unsigned __int16 ***))ppv[0];
      Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&a7);
      Instance = v13(v12, &GUID_9a690e7c_9c93_4be4_8b16_500465462d02, &a7);
      if ( Instance >= 0 )
      {
        for ( i = 0; ; i = (unsigned int)(i + 1) )
        {
          if ( (unsigned int)i >= a3 )
            goto LABEL_19;
          ppszPath = 0;
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
            &ppszPath,
            0);
          v15 = (char *)a4 + 24 * i;
          Instance = SHGetKnownFolderPath((const KNOWNFOLDERID *const)v15, 0, 0, &ppszPath);
          if ( Instance < 0 )
            goto LABEL_18;
          DriveNumberW = PathGetDriveNumberW(ppszPath);
          v17 = PathGetDriveNumberW(*((LPCWSTR *)v15 + 2));
          if ( DriveNumberW == -1 || v17 == -1 )
            break;
          v18 = DriveNumberW == v17;
          v19 = (__int64 (__fastcall *)(unsigned __int16 **, char *, HWND, __int64, _QWORD, _DWORD, _QWORD, _QWORD))*((_QWORD *)*a7 + 3);
          if ( v18 )
            v20 = v19(a7, (char *)a4 + 24 * i, a6, 67110432, *((_QWORD *)v15 + 2), 0, 0, 0);
          else
            v20 = v19(a7, (char *)a4 + 24 * i, a6, 1568, *((_QWORD *)v15 + 2), 0, 0, 0);
          Instance = v20;
          if ( v20 < 0 )
            goto LABEL_18;
          if ( PathFileExistsW(ppszPath) && !PathIsDirectoryEmptyW(ppszPath) )
          {
            Instance = -2147024662;
LABEL_18:
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&ppszPath);
            goto LABEL_19;
          }
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(&ppszPath);
        }
        Instance = -2147024893;
        goto LABEL_18;
      }
    }
LABEL_19:
    ReleaseSRWLockShared(v11);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(&a7);
    Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(ppv);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180067254  mov     [rsp-28h+arg_0], rbx
0x180067259  mov     [rsp-28h+arg_10], rsi
0x18006725e  mov     [rsp-28h+ppszPath], rdx
0x180067263  push    rbp
0x180067264  push    rdi
0x180067265  push    r12
0x180067267  push    r14
0x180067269  push    r15
0x18006726b  mov     rbp, rsp
0x18006726e  sub     rsp, 60h
0x180067272  mov     r12, r9
0x180067275  mov     r15d, r8d
0x180067278  mov     rdi, rcx
0x18006727b  mov     rax, [rbp+arg_30]
0x18006727f  mov     qword ptr [rax], 0
0x180067286  or      edx, 0FFFFFFFFh
0x180067289  call    ?_EnsureCachedValuesReaderModeWrapper@CSyncRootManagerCache@@AEAAJW4SPGSP_FLAGS@@@Z; CSyncRootManagerCache::_EnsureCachedValuesReaderModeWrapper(SPGSP_FLAGS)
0x18006728e  mov     ebx, eax
0x180067290  test    eax, eax
0x180067292  js      loc_180067441
0x180067298  lea     r14, [rdi+18h]
0x18006729c  mov     rcx, r14; SRWLock
0x18006729f  call    cs:__imp_AcquireSRWLockShared
0x1800672a5  mov     [rbp+var_10], 0
0x1800672ad  mov     [rbp+arg_30], 0
0x1800672b5  lea     rcx, [rbp+var_10]
0x1800672b9  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800672be  lea     rax, [rbp+var_10]
0x1800672c2  mov     [rsp+60h+ppv], rax; ppv
0x1800672c7  lea     r9, _GUID_8be2d872_86aa_4d47_b776_32cca40c7018; riid
0x1800672ce  xor     edx, edx; pUnkOuter
0x1800672d0  lea     r8d, [rdx+1]; dwClsContext
0x1800672d4  lea     rcx, CLSID_KnownFolderManager; rclsid
0x1800672db  call    cs:__imp_CoCreateInstance
0x1800672e1  mov     ebx, eax
0x1800672e3  test    eax, eax
0x1800672e5  js      loc_180067424
0x1800672eb  mov     rdi, [rbp+var_10]
0x1800672ef  mov     rax, [rdi]
0x1800672f2  mov     rbx, [rax]
0x1800672f5  lea     rcx, [rbp+arg_30]
0x1800672f9  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x1800672fe  lea     r8, [rbp+arg_30]
0x180067302  lea     rdx, _GUID_9a690e7c_9c93_4be4_8b16_500465462d02
0x180067309  mov     rcx, rdi
0x18006730c  mov     rax, rbx
0x18006730f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067314  mov     ebx, eax
0x180067316  test    eax, eax
0x180067318  js      loc_180067424
0x18006731e  xor     edi, edi
0x180067320  cmp     edi, r15d
0x180067323  jnb     loc_180067424
0x180067329  mov     [rbp+ppszPath], 0
0x180067331  xor     edx, edx
0x180067333  lea     rcx, [rbp+ppszPath]
0x180067337  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18006733c  lea     rcx, [rdi+rdi*2]
0x180067340  lea     rsi, [r12+rcx*8]
0x180067344  lea     r9, [rbp+ppszPath]; ppszPath
0x180067348  xor     r8d, r8d; hToken
0x18006734b  xor     edx, edx; dwFlags
0x18006734d  mov     rcx, rsi; rfid
0x180067350  call    cs:__imp_SHGetKnownFolderPath
0x180067356  mov     ebx, eax
0x180067358  test    eax, eax
0x18006735a  js      loc_18006741B
0x180067360  mov     rcx, [rbp+ppszPath]; pszPath
0x180067364  call    cs:__imp_PathGetDriveNumberW
0x18006736a  mov     ebx, eax
0x18006736c  mov     rcx, [rsi+10h]; pszPath
0x180067370  call    cs:__imp_PathGetDriveNumberW
0x180067376  cmp     ebx, 0FFFFFFFFh
0x180067379  jz      loc_180067416
0x18006737f  cmp     eax, 0FFFFFFFFh
0x180067382  jz      loc_180067416
0x180067388  mov     rcx, [rbp+arg_30]
0x18006738c  mov     [rsp+60h+var_28], 0
0x180067395  mov     [rsp+60h+var_30], 0
0x18006739e  mov     [rsp+60h+var_38], 0
0x1800673a6  cmp     ebx, eax
0x1800673a8  mov     rax, [rcx]
0x1800673ab  mov     rax, [rax+18h]
0x1800673af  jnz     short loc_1800673C2
0x1800673b1  mov     r8, [rsi+10h]
0x1800673b5  mov     [rsp+60h+ppv], r8
0x1800673ba  mov     r9d, 4000620h
0x1800673c0  jmp     short loc_1800673D1
0x1800673c2  mov     rdx, [rsi+10h]
0x1800673c6  mov     [rsp+60h+ppv], rdx
0x1800673cb  mov     r9d, 620h
0x1800673d1  mov     r8, [rbp+arg_28]
0x1800673d5  mov     rdx, rsi
0x1800673d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800673dd  mov     ebx, eax
0x1800673df  test    eax, eax
0x1800673e1  js      short loc_18006741B
0x1800673e3  mov     rcx, [rbp+ppszPath]; pszPath
0x1800673e7  call    cs:__imp_PathFileExistsW
0x1800673ed  test    eax, eax
0x1800673ef  jz      short loc_1800673FF
0x1800673f1  mov     rcx, [rbp+ppszPath]; pszPath
0x1800673f5  call    cs:__imp_PathIsDirectoryEmptyW
0x1800673fb  test    eax, eax
0x1800673fd  jz      short loc_18006740F
0x1800673ff  lea     rcx, [rbp+ppszPath]; void *
0x180067403  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180067408  inc     edi
0x18006740a  jmp     loc_180067320
0x18006740f  mov     ebx, 800700EAh
0x180067414  jmp     short loc_18006741B
0x180067416  mov     ebx, 80070003h
0x18006741b  lea     rcx, [rbp+ppszPath]; void *
0x18006741f  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>(void)
0x180067424  mov     rcx, r14; SRWLock
0x180067427  call    cs:__imp_ReleaseSRWLockShared
0x18006742d  nop
0x18006742e  lea     rcx, [rbp+arg_30]
0x180067432  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180067437  nop
0x180067438  lea     rcx, [rbp+var_10]
0x18006743c  call    ?InternalRelease@?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<ISyncRootManager>::InternalRelease(void)
0x180067441  mov     eax, ebx
0x180067443  lea     r11, [rsp+60h+var_s0]
0x180067448  mov     rbx, [r11+30h]
0x18006744c  mov     rsi, [r11+40h]
0x180067450  mov     rsp, r11
0x180067453  pop     r15
0x180067455  pop     r14
0x180067457  pop     r12
0x180067459  pop     rdi
0x18006745a  pop     rbp
0x18006745b  retn
```
