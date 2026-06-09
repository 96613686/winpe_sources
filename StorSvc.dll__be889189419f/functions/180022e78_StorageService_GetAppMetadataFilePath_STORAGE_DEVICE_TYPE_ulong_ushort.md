# StorageService::GetAppMetadataFilePath(_STORAGE_DEVICE_TYPE,ulong,ushort *)

- ea: `0x180022e78`
- end: `0x180022ee4`
- name: `?GetAppMetadataFilePath@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KPEAG@Z`
- size: `108`
- prototype: `int __fastcall(__int64, int, unsigned int, wchar_t *)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, registry_config, service_task`

## callers

- `0x180024334`
- `0x1800298cc`

## callees

- `0x180012c9c`
- `0x180022e78`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180022ebd`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180022ed3`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180022ebd`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180022ed3`

## pseudocode

```c
int __fastcall StorageService::GetAppMetadataFilePath(__int64 a1, int a2, unsigned int a3, wchar_t *a4)
{
  int result; // eax

  result = StringCchCopyW(a4, 0x104u, (const wchar_t *)(*(_QWORD *)(a1 + 8LL * a2 + 40) + 4LL + 1112LL * a3));
  if ( result >= 0 )
  {
    result = PathCchAppend(a4, 0x104u, L"System Volume Information");
    if ( result >= 0 )
      return PathCchAppend(a4, 0x104u, L"WPAppSettings.dat");
  }
  return result;
}

```

## disassembly

```asm
0x180022e78  mov     [rsp+arg_0], rbx
0x180022e7d  push    rdi
0x180022e7e  sub     rsp, 20h
0x180022e82  mov     eax, r8d
0x180022e85  mov     edi, 104h
0x180022e8a  imul    r8, rax, 458h
0x180022e91  movsxd  r10, edx
0x180022e94  mov     rbx, r9
0x180022e97  mov     edx, edi; unsigned __int64
0x180022e99  mov     rax, [rcx+r10*8+28h]
0x180022e9e  mov     rcx, r9; wchar_t *
0x180022ea1  add     rax, 4
0x180022ea5  add     r8, rax; wchar_t *
0x180022ea8  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180022ead  test    eax, eax
0x180022eaf  js      short loc_180022ED9
0x180022eb1  lea     r8, aSystemVolumeIn; "System Volume Information"
0x180022eb8  mov     edx, edi; cchPath
0x180022eba  mov     rcx, rbx; pszPath
0x180022ebd  call    cs:__imp_PathCchAppend
0x180022ec3  test    eax, eax
0x180022ec5  js      short loc_180022ED9
0x180022ec7  lea     r8, aWpappsettingsD; "WPAppSettings.dat"
0x180022ece  mov     edx, edi; cchPath
0x180022ed0  mov     rcx, rbx; pszPath
0x180022ed3  call    cs:__imp_PathCchAppend
0x180022ed9  mov     rbx, [rsp+28h+arg_0]
0x180022ede  add     rsp, 20h
0x180022ee2  pop     rdi
0x180022ee3  retn
```
