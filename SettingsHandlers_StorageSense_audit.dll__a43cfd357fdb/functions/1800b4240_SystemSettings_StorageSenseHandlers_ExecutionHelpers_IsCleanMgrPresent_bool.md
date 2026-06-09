# SystemSettings::StorageSenseHandlers::ExecutionHelpers::IsCleanMgrPresent(bool *)

- ea: `0x1800b4240`
- end: `0x1800b43c6`
- name: `?IsCleanMgrPresent@ExecutionHelpers@StorageSenseHandlers@SystemSettings@@YAJPEA_N@Z`
- size: `390`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::ExecutionHelpers *__hidden this, bool *)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180080fd0`
- `0x1800812d0`
- `0x180081e90`

## callees

- `0x180006e50`
- `0x180007a00`
- `0x18000e6cc`
- `0x1800292a8`
- `0x180035c0c`
- `0x18009d56c`
- `0x1800b4240`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800b435a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800b435a`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800b4300`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800b4300`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1800b432b`
- `api-ms-win-core-path-l1-1-0!PathAllocCanonicalize` at `0x1800b432b`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800b42af`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800b42af`

## pseudocode

```c
__int64 __fastcall SystemSettings::StorageSenseHandlers::ExecutionHelpers::IsCleanMgrPresent(
        SystemSettings::StorageSenseHandlers::ExecutionHelpers *this,
        bool *a2,
        __int64 a3)
{
  unsigned int v4; // ebx
  HRESULT v5; // eax
  __int64 v6; // rdx
  char v7; // di
  __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // rdx
  __int64 v11; // r8
  PWSTR v13; // [rsp+20h] [rbp-E0h] BYREF
  PWSTR ppszPathOut; // [rsp+28h] [rbp-D8h] BYREF
  PWSTR ppszPath; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE FirstFileW; // [rsp+38h] [rbp-C8h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2C8h] [rbp+1C8h]

  ppszPath = 0;
  ppszPathOut = 0;
  v13 = 0;
  if ( !this )
  {
    v4 = -2147024809;
    goto LABEL_15;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPath,
    0);
  v5 = SHGetKnownFolderPath(&FOLDERID_System, 0, 0, &ppszPath);
  v4 = v5;
  if ( v5 < 0 )
  {
    v6 = 1276;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\util.cpp",
      (const char *)(unsigned int)v5,
      (int)v13);
    goto LABEL_15;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPathOut,
    0);
  v7 = 1;
  v5 = PathAllocCombine(ppszPath, L"cleanmgr.exe", 1u, &ppszPathOut);
  v4 = v5;
  if ( v5 < 0 )
  {
    v6 = 1277;
    goto LABEL_5;
  }
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &v13,
    0);
  v5 = PathAllocCanonicalize(ppszPathOut, 1u, &v13);
  v4 = v5;
  if ( v5 < 0 )
  {
    v6 = 1278;
    goto LABEL_5;
  }
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(v13, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL || FindFileData.dwFileAttributes == -1 || (FindFileData.dwFileAttributes & 0x10) != 0 )
    v7 = 0;
  *(_BYTE *)this = v7;
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(&FirstFileW);
  v4 = 0;
LABEL_15:
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
    &v13,
    a2,
    a3);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
    &ppszPathOut,
    v8,
    v9);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
    &ppszPath,
    v10,
    v11);
  return v4;
}

```

## disassembly

```asm
0x1800b4240  push    rbp
0x1800b4242  push    rbx
0x1800b4243  push    rsi
0x1800b4244  push    rdi
0x1800b4245  lea     rbp, [rsp-1A8h]
0x1800b424d  sub     rsp, 2A8h
0x1800b4254  mov     rax, cs:__security_cookie
0x1800b425b  xor     rax, rsp
0x1800b425e  mov     [rbp+1C0h+var_30], rax
0x1800b4265  mov     [rsp+2C0h+ppszPath], 0
0x1800b426e  mov     rsi, rcx
0x1800b4271  mov     [rsp+2C0h+ppszPathOut], 0
0x1800b427a  mov     [rsp+2C0h+var_2A0], 0; int
0x1800b4283  test    rcx, rcx
0x1800b4286  jnz     short loc_1800B4292
0x1800b4288  mov     ebx, 80070057h
0x1800b428d  jmp     loc_1800B438B
0x1800b4292  xor     edx, edx
0x1800b4294  lea     rcx, [rsp+2C0h+ppszPath]
0x1800b4299  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800b429e  lea     r9, [rsp+2C0h+ppszPath]; ppszPath
0x1800b42a3  xor     r8d, r8d; hToken
0x1800b42a6  xor     edx, edx; dwFlags
0x1800b42a8  lea     rcx, FOLDERID_System; rfid
0x1800b42af  call    cs:__imp_SHGetKnownFolderPath
0x1800b42b5  mov     ebx, eax
0x1800b42b7  test    eax, eax
0x1800b42b9  jns     short loc_1800B42DB
0x1800b42bb  mov     edx, 4FCh; void *
0x1800b42c0  mov     rcx, [rbp+1C8h]; this
0x1800b42c7  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\coresettinghandlers"...
0x1800b42ce  mov     r9d, eax; char *
0x1800b42d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b42d6  jmp     loc_1800B438B
0x1800b42db  xor     edx, edx
0x1800b42dd  lea     rcx, [rsp+2C0h+ppszPathOut]
0x1800b42e2  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800b42e7  mov     rcx, [rsp+2C0h+ppszPath]; pszPathIn
0x1800b42ec  lea     r9, [rsp+2C0h+ppszPathOut]; ppszPathOut
0x1800b42f1  mov     edi, 1
0x1800b42f6  lea     rdx, pszMore; "cleanmgr.exe"
0x1800b42fd  mov     r8d, edi; dwFlags
0x1800b4300  call    cs:__imp_PathAllocCombine
0x1800b4306  mov     ebx, eax
0x1800b4308  test    eax, eax
0x1800b430a  jns     short loc_1800B4313
0x1800b430c  mov     edx, 4FDh
0x1800b4311  jmp     short loc_1800B42C0
0x1800b4313  xor     edx, edx
0x1800b4315  lea     rcx, [rsp+2C0h+var_2A0]
0x1800b431a  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800b431f  mov     rcx, [rsp+2C0h+ppszPathOut]; pszPathIn
0x1800b4324  lea     r8, [rsp+2C0h+var_2A0]; ppszPathOut
0x1800b4329  mov     edx, edi; dwFlags
0x1800b432b  call    cs:__imp_PathAllocCanonicalize
0x1800b4331  mov     ebx, eax
0x1800b4333  test    eax, eax
0x1800b4335  jns     short loc_1800B433E
0x1800b4337  mov     edx, 4FEh
0x1800b433c  jmp     short loc_1800B42C0
0x1800b433e  xor     edx, edx; Val
0x1800b4340  lea     rcx, [rsp+2C0h+FindFileData]; void *
0x1800b4345  mov     r8d, 250h; Size
0x1800b434b  call    memset_0
0x1800b4350  mov     rcx, [rsp+2C0h+var_2A0]; lpFileName
0x1800b4355  lea     rdx, [rsp+2C0h+FindFileData]; lpFindFileData
0x1800b435a  call    cs:__imp_FindFirstFileW
0x1800b4360  mov     [rsp+2C0h+var_288], rax
0x1800b4365  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b4369  jz      short loc_1800B4379
0x1800b436b  cmp     [rsp+2C0h+FindFileData.dwFileAttributes], 0FFFFFFFFh
0x1800b4370  jz      short loc_1800B4379
0x1800b4372  test    byte ptr [rsp+2C0h+FindFileData.dwFileAttributes], 10h
0x1800b4377  jz      short loc_1800B437C
0x1800b4379  xor     dil, dil
0x1800b437c  lea     rcx, [rsp+2C0h+var_288]
0x1800b4381  mov     [rsi], dil
0x1800b4384  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800b4389  xor     ebx, ebx
0x1800b438b  lea     rcx, [rsp+2C0h+var_2A0]
0x1800b4390  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800b4395  lea     rcx, [rsp+2C0h+ppszPathOut]
0x1800b439a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800b439f  lea     rcx, [rsp+2C0h+ppszPath]
0x1800b43a4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800b43a9  mov     eax, ebx
0x1800b43ab  mov     rcx, [rbp+1C0h+var_30]
0x1800b43b2  xor     rcx, rsp; StackCookie
0x1800b43b5  call    __security_check_cookie
0x1800b43ba  add     rsp, 2A8h
0x1800b43c1  pop     rdi
0x1800b43c2  pop     rsi
0x1800b43c3  pop     rbx
0x1800b43c4  pop     rbp
0x1800b43c5  retn
```
