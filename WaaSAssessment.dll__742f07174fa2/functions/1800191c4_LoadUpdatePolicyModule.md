# LoadUpdatePolicyModule

- ea: `0x1800191c4`
- end: `0x180019287`
- name: `LoadUpdatePolicyModule`
- size: `195`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180019290`
- `0x1800193b8`
- `0x1800194f4`
- `0x1800195b4`

## callees

- `0x18000efcc`
- `0x1800191c4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001923f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001923f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001921f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001921f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800191d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x1800191d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019276`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180019276`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019200`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019200`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800191ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800191f7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800191ea`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800191f7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019247`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019247`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019234`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019234`

## string_xrefs

- `0x18001925e`: `onecore\enduser\windowsupdate\client\policy\wrapper\wrapper.cpp`
- `0x180019212`: `UpdatePolicy.dll`

## pseudocode

```c
__int64 LoadUpdatePolicyModule()
{
  HMODULE Library; // rax
  const char *v2; // r9
  HMODULE v3; // rsi
  HMODULE v4; // rdi
  DWORD LastError; // ebx
  unsigned int v6; // ebx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  AcquireSRWLockShared(&g_LoadUpdatePolicyModuleLock);
  if ( g_hUpdatePolicyModule )
  {
    ReleaseSRWLockShared(&g_LoadUpdatePolicyModuleLock);
    return 0;
  }
  else
  {
    ReleaseSRWLockShared(&g_LoadUpdatePolicyModuleLock);
    AcquireSRWLockExclusive(&g_LoadUpdatePolicyModuleLock);
    if ( g_hUpdatePolicyModule )
      goto LABEL_8;
    Library = LoadLibraryExW(L"UpdatePolicy.dll", 0, 0x800u);
    v3 = g_hUpdatePolicyModule;
    v4 = Library;
    if ( g_hUpdatePolicyModule )
    {
      LastError = GetLastError();
      FreeLibrary(v3);
      SetLastError(LastError);
    }
    g_hUpdatePolicyModule = v4;
    if ( v4 )
LABEL_8:
      v6 = 0;
    else
      v6 = wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x20,
             (unsigned int)"onecore\\enduser\\windowsupdate\\client\\policy\\wrapper\\wrapper.cpp",
             v2);
    ReleaseSRWLockExclusive(&g_LoadUpdatePolicyModuleLock);
    return v6;
  }
}

```

## disassembly

```asm
0x1800191c4  push    rbx
0x1800191c6  push    rbp
0x1800191c7  push    rsi
0x1800191c8  push    rdi
0x1800191c9  sub     rsp, 28h
0x1800191cd  lea     rbp, ?g_LoadUpdatePolicyModuleLock@@3Vsrwlock@wil@@A; wil::srwlock g_LoadUpdatePolicyModuleLock
0x1800191d4  mov     rcx, rbp; SRWLock
0x1800191d7  call    cs:__imp_AcquireSRWLockShared
0x1800191dd  cmp     cs:?g_hUpdatePolicyModule@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, 0; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> g_hUpdatePolicyModule
0x1800191e5  mov     rcx, rbp; SRWLock
0x1800191e8  jz      short loc_1800191F7
0x1800191ea  call    cs:__imp_ReleaseSRWLockShared
0x1800191f0  xor     eax, eax
0x1800191f2  jmp     loc_18001927E
0x1800191f7  call    cs:__imp_ReleaseSRWLockShared
0x1800191fd  mov     rcx, rbp; SRWLock
0x180019200  call    cs:__imp_AcquireSRWLockExclusive
0x180019206  cmp     cs:?g_hUpdatePolicyModule@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, 0; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> g_hUpdatePolicyModule
0x18001920e  jnz     short loc_180019271
0x180019210  xor     edx, edx; hFile
0x180019212  lea     rcx, aUpdatepolicyDl; "UpdatePolicy.dll"
0x180019219  mov     r8d, 800h; dwFlags
0x18001921f  call    cs:__imp_LoadLibraryExW
0x180019225  mov     rsi, cs:?g_hUpdatePolicyModule@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> g_hUpdatePolicyModule
0x18001922c  mov     rdi, rax
0x18001922f  test    rsi, rsi
0x180019232  jz      short loc_18001924D
0x180019234  call    cs:__imp_GetLastError
0x18001923a  mov     rcx, rsi; hLibModule
0x18001923d  mov     ebx, eax
0x18001923f  call    cs:__imp_FreeLibrary
0x180019245  mov     ecx, ebx; dwErrCode
0x180019247  call    cs:__imp_SetLastError
0x18001924d  mov     cs:?g_hUpdatePolicyModule@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A, rdi; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>> g_hUpdatePolicyModule
0x180019254  test    rdi, rdi
0x180019257  jnz     short loc_180019271
0x180019259  mov     rcx, [rsp+48h]; this
0x18001925e  lea     r8, aOnecoreEnduser; "onecore\\enduser\\windowsupdate\\client"...
0x180019265  lea     edx, [rdi+20h]; void *
0x180019268  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001926d  mov     ebx, eax
0x18001926f  jmp     short loc_180019273
0x180019271  xor     ebx, ebx
0x180019273  mov     rcx, rbp; SRWLock
0x180019276  call    cs:__imp_ReleaseSRWLockExclusive
0x18001927c  mov     eax, ebx
0x18001927e  add     rsp, 28h
0x180019282  pop     rdi
0x180019283  pop     rsi
0x180019284  pop     rbp
0x180019285  pop     rbx
0x180019286  retn
```
