# Windows::Compat::Inventory::CacheUtilities::AmiCache::GetInstance(void)

- ea: `0x14000fc78`
- end: `0x14000fdca`
- name: `?GetInstance@AmiCache@CacheUtilities@Inventory@Compat@Windows@@SAPEAV12345@XZ`
- size: `338`
- prototype: `struct Windows::Compat::Inventory::CacheUtilities::AmiCache *(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000de8c`

## callees

- `0x140001ba0`
- `0x140001e90`
- `0x1400026c0`
- `0x1400026cc`
- `0x140009338`
- `0x14000d430`
- `0x14000e730`
- `0x14000fc78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fdae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000fdae`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000fce0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000fce0`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x14000fcaf`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x14000fcaf`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x14000fcf0`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x14000fcf0`

## string_xrefs

- `0x14000fcc2`: `\AppCompat\Programs\InventoryApplicationFile.db`

## pseudocode

```c
struct Windows::Compat::Inventory::CacheUtilities::AmiCache *Windows::Compat::Inventory::CacheUtilities::AmiCache::GetInstance(
        void)
{
  unsigned __int64 v0; // rdx
  int v1; // eax
  _QWORD *v2; // rbx
  ulong pExceptionObject[4]; // [rsp+20h] [rbp-238h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-228h] BYREF

  memset_0(Buffer, 0, 0x208u);
  if ( GetWindowsDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
  {
    pExceptionObject[0] = GetLastError();
    throw pExceptionObject;
  }
  v1 = StringCchCatW(Buffer, v0, L"\\AppCompat\\Programs\\InventoryApplicationFile.db");
  if ( v1 < 0 )
  {
    pExceptionObject[0] = v1;
    throw (long *)pExceptionObject;
  }
  if ( GetFileAttributesW(Buffer) == -1 )
  {
    v2 = operator new(0x50u);
    *(_QWORD *)pExceptionObject = v2;
    memset_0(v2, 0, 0x50u);
    *v2 = &Windows::Compat::Inventory::CacheUtilities::AmiCache::`vftable';
    RtlStringArray::RtlStringArray((RtlStringArray *)(v2 + 1));
    *v2 = &Windows::Compat::Inventory::CacheUtilities::HiveCache::`vftable';
    v2[9] = 0;
  }
  else
  {
    PathRemoveFileSpecW(Buffer);
    v2 = operator new(0x68u);
    *(_QWORD *)pExceptionObject = v2;
    *v2 = &Windows::Compat::Inventory::CacheUtilities::AmiCache::`vftable';
    RtlStringArray::RtlStringArray((RtlStringArray *)(v2 + 1));
    *v2 = &Windows::Compat::Inventory::CacheUtilities::SqliteCache::`vftable';
    std::wstring::wstring(v2 + 9, Buffer);
  }
  return (struct Windows::Compat::Inventory::CacheUtilities::AmiCache *)v2;
}

```

## disassembly

```asm
0x14000fc78  push    rbx
0x14000fc7a  sub     rsp, 250h
0x14000fc81  mov     rax, cs:__security_cookie
0x14000fc88  xor     rax, rsp
0x14000fc8b  mov     [rsp+258h+var_18], rax
0x14000fc93  xor     edx, edx; Val
0x14000fc95  mov     r8d, 208h; Size
0x14000fc9b  lea     rcx, [rsp+258h+Buffer]; void *
0x14000fca0  call    memset_0
0x14000fca5  mov     edx, 104h; uSize
0x14000fcaa  lea     rcx, [rsp+258h+Buffer]; lpBuffer
0x14000fcaf  call    cs:__imp_GetWindowsDirectoryW
0x14000fcb5  dec     eax
0x14000fcb7  cmp     eax, 102h
0x14000fcbc  ja      loc_14000FDAE
0x14000fcc2  lea     r8, aAppcompatProgr; "\\AppCompat\\Programs\\InventoryApplica"...
0x14000fcc9  lea     rcx, [rsp+258h+Buffer]; unsigned __int16 *
0x14000fcce  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000fcd3  test    eax, eax
0x14000fcd5  js      loc_14000FD98
0x14000fcdb  lea     rcx, [rsp+258h+Buffer]; lpFileName
0x14000fce0  call    cs:__imp_GetFileAttributesW
0x14000fce6  cmp     eax, 0FFFFFFFFh
0x14000fce9  jz      short loc_14000FD51
0x14000fceb  lea     rcx, [rsp+258h+Buffer]; pszPath
0x14000fcf0  call    cs:__imp_PathRemoveFileSpecW
0x14000fcf6  mov     ecx, 68h ; 'h'; Size
0x14000fcfb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000fd00  mov     rbx, rax
0x14000fd03  mov     qword ptr [rsp+258h+pExceptionObject], rax
0x14000fd08  lea     rax, ??_7AmiCache@CacheUtilities@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::CacheUtilities::AmiCache::`vftable'
0x14000fd0f  mov     [rbx], rax
0x14000fd12  lea     rcx, [rbx+8]; this
0x14000fd16  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x14000fd1b  nop
0x14000fd1c  lea     rax, ??_7SqliteCache@CacheUtilities@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::CacheUtilities::SqliteCache::`vftable'
0x14000fd23  mov     [rbx], rax
0x14000fd26  lea     rcx, [rbx+48h]
0x14000fd2a  lea     rdx, [rsp+258h+Buffer]
0x14000fd2f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x14000fd34  nop
0x14000fd35  mov     rax, rbx
0x14000fd38  mov     rcx, [rsp+258h+var_18]
0x14000fd40  xor     rcx, rsp; StackCookie
0x14000fd43  call    __security_check_cookie
0x14000fd48  add     rsp, 250h
0x14000fd4f  pop     rbx
0x14000fd50  retn
0x14000fd51  mov     ecx, 50h ; 'P'; Size
0x14000fd56  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000fd5b  mov     rbx, rax
0x14000fd5e  mov     qword ptr [rsp+258h+pExceptionObject], rax
0x14000fd63  xor     edx, edx; Val
0x14000fd65  lea     r8d, [rdx+50h]; Size
0x14000fd69  mov     rcx, rax; void *
0x14000fd6c  call    memset_0
0x14000fd71  lea     rax, ??_7AmiCache@CacheUtilities@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::CacheUtilities::AmiCache::`vftable'
0x14000fd78  mov     [rbx], rax
0x14000fd7b  lea     rcx, [rbx+8]; this
0x14000fd7f  call    ??0RtlStringArray@@QEAA@XZ; RtlStringArray::RtlStringArray(void)
0x14000fd84  lea     rax, ??_7HiveCache@CacheUtilities@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::CacheUtilities::HiveCache::`vftable'
0x14000fd8b  mov     [rbx], rax
0x14000fd8e  mov     qword ptr [rbx+48h], 0
0x14000fd96  jmp     short loc_14000FD35
0x14000fd98  mov     [rsp+258h+pExceptionObject], eax
0x14000fd9c  lea     rdx, _TI1J; pThrowInfo
0x14000fda3  lea     rcx, [rsp+258h+pExceptionObject]; pExceptionObject
0x14000fda8  call    _CxxThrowException_0
0x14000fdae  call    cs:__imp_GetLastError
0x14000fdb4  mov     [rsp+258h+pExceptionObject], eax
0x14000fdb8  lea     rdx, _TI1K; pThrowInfo
0x14000fdbf  lea     rcx, [rsp+258h+pExceptionObject]; pExceptionObject
0x14000fdc4  call    _CxxThrowException_0
```
