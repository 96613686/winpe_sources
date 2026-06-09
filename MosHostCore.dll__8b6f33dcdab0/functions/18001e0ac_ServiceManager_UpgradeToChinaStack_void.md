# ServiceManager::UpgradeToChinaStack(void)

- ea: `0x18001e0ac`
- end: `0x18001e1a5`
- name: `?UpgradeToChinaStack@ServiceManager@@AEAAJXZ`
- size: `249`
- prototype: `__int64 __fastcall(ServiceManager *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, service_task`

## callers

- `0x18001546c`

## callees

- `0x180003410`
- `0x180018508`
- `0x18001e0ac`
- `0x180020060`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001e111`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18001e111`
- `MosStorage!MosStorageGetDataDirectory` at `0x18001e0d9`
- `MosStorage!MosStorageGetDataDirectory` at `0x18001e0d9`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001e0f5`
- `ZTrace_Maps!ZTraceReportPropagation` at `0x18001e0f5`
- `ZTrace_Maps!ZTraceHelper` at `0x18001e15f`
- `ZTrace_Maps!ZTraceHelper` at `0x18001e15f`

## string_xrefs

- `0x18001e0ec`: `ServiceManager::UpgradeToChinaStack`
- `0x18001e132`: `ServiceManager::UpgradeToChinaStack`
- `0x18001e100`: `diskcache`

## pseudocode

```c
int __fastcall ServiceManager::UpgradeToChinaStack(ServiceManager *this)
{
  int DataDirectory; // eax
  int v3; // r8d
  ServiceManager *v4; // r9
  bool v6; // [rsp+30h] [rbp-238h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-228h] BYREF

  v6 = 1;
  DataDirectory = MosStorageGetDataDirectory(pszPath, 0x104u);
  if ( DataDirectory < 0 )
  {
    v3 = 3940;
LABEL_3:
    v4 = this;
    return ZTraceReportPropagation(DataDirectory, "ServiceManager::UpgradeToChinaStack", v3, v4);
  }
  DataDirectory = PathCchAppend(pszPath, 0x104u, L"diskcache");
  if ( DataDirectory < 0 )
  {
    v3 = 3941;
    goto LABEL_3;
  }
  DataDirectory = FolderExists(pszPath, &v6);
  v4 = this;
  if ( DataDirectory < 0 )
  {
    v3 = 3942;
    return ZTraceReportPropagation(DataDirectory, "ServiceManager::UpgradeToChinaStack", v3, v4);
  }
  ZTraceHelper(3, "ServiceManager::UpgradeToChinaStack", 3948, this, "Migrating map data");
  DataDirectory = ServiceManager::MigrateData(this, v6 ? 1 : 3);
  if ( DataDirectory < 0 )
  {
    v3 = 3949;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x18001e0ac  push    rbx
0x18001e0ae  sub     rsp, 260h
0x18001e0b5  mov     rax, cs:__security_cookie
0x18001e0bc  xor     rax, rsp
0x18001e0bf  mov     [rsp+268h+var_18], rax
0x18001e0c7  mov     rbx, rcx
0x18001e0ca  mov     [rsp+268h+var_238], 1
0x18001e0cf  lea     rcx, [rsp+268h+pszPath]
0x18001e0d4  mov     edx, 104h
0x18001e0d9  call    cs:__imp_?MosStorageGetDataDirectory@@YAJPEAGK@Z; MosStorageGetDataDirectory(ushort *,ulong)
0x18001e0df  test    eax, eax
0x18001e0e1  jns     short loc_18001E100
0x18001e0e3  mov     r8d, 0F64h
0x18001e0e9  mov     r9, rbx
0x18001e0ec  lea     rdx, aServicemanager_16; "ServiceManager::UpgradeToChinaStack"
0x18001e0f3  mov     ecx, eax
0x18001e0f5  call    cs:__imp_?ZTraceReportPropagation@@YAJHPEBDHPEBX@Z; ZTraceReportPropagation(int,char const *,int,void const *)
0x18001e0fb  jmp     loc_18001E18C
0x18001e100  lea     r8, pszMore; "diskcache"
0x18001e107  mov     edx, 104h; cchPath
0x18001e10c  lea     rcx, [rsp+268h+pszPath]; pszPath
0x18001e111  call    cs:__imp_PathCchAppend
0x18001e117  test    eax, eax
0x18001e119  jns     short loc_18001E123
0x18001e11b  mov     r8d, 0F65h
0x18001e121  jmp     short loc_18001E0E9
0x18001e123  lea     rdx, [rsp+268h+var_238]; bool *
0x18001e128  lea     rcx, [rsp+268h+pszPath]; unsigned __int16 *
0x18001e12d  call    ?FolderExists@@YAJPEBGPEA_N@Z; FolderExists(ushort const *,bool *)
0x18001e132  lea     rdx, aServicemanager_16; "ServiceManager::UpgradeToChinaStack"
0x18001e139  mov     r9, rbx
0x18001e13c  test    eax, eax
0x18001e13e  jns     short loc_18001E148
0x18001e140  mov     r8d, 0F66h
0x18001e146  jmp     short loc_18001E0F3
0x18001e148  lea     rax, aMigratingMapDa; "Migrating map data"
0x18001e14f  mov     r8d, 0F6Ch
0x18001e155  mov     ecx, 3
0x18001e15a  mov     [rsp+268h+var_248], rax
0x18001e15f  call    cs:__imp_?ZTraceHelper@@YAXW4ZTraceLevel@@PEBDHPEBX1ZZ; ZTraceHelper(ZTraceLevel,char const *,int,void const *,char const *,...)
0x18001e165  mov     al, [rsp+268h+var_238]
0x18001e169  mov     rcx, rbx
0x18001e16c  neg     al
0x18001e16e  sbb     edx, edx
0x18001e170  and     edx, 0FFFFFFFEh
0x18001e173  add     edx, 3
0x18001e176  call    ?MigrateData@ServiceManager@@AEAAJW4StackMode@@@Z; ServiceManager::MigrateData(StackMode)
0x18001e17b  test    eax, eax
0x18001e17d  jns     short loc_18001E18A
0x18001e17f  mov     r8d, 0F6Dh
0x18001e185  jmp     loc_18001E0E9
0x18001e18a  xor     eax, eax
0x18001e18c  mov     rcx, [rsp+268h+var_18]
0x18001e194  xor     rcx, rsp; StackCookie
0x18001e197  call    __security_check_cookie
0x18001e19c  add     rsp, 260h
0x18001e1a3  pop     rbx
0x18001e1a4  retn
```
