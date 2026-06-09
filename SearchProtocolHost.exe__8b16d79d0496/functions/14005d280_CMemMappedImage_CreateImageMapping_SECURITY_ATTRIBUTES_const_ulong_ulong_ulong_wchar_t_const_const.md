# CMemMappedImage::CreateImageMapping(_SECURITY_ATTRIBUTES * const,ulong,ulong,ulong,wchar_t const * const)

- ea: `0x14005d280`
- end: `0x14005d331`
- name: `?CreateImageMapping@CMemMappedImage@@QEAAJQEAU_SECURITY_ATTRIBUTES@@KKKQEB_W@Z`
- size: `177`
- prototype: `__int64 __fastcall(CMemMappedImage *__hidden this, struct _SECURITY_ATTRIBUTES *const, unsigned int, unsigned int, DWORD, const wchar_t *const)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x14005dc90`

## callees

- `0x140015958`
- `0x14001eb94`
- `0x140037ca8`
- `0x14005d280`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005d2bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14005d2bc`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x14005d2b3`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x14005d2b3`

## string_xrefs

- `0x14005d2d7`: `onecoreuap\base\appmodel\Search\common\include\MemMappedImage.h`
- `0x14005d304`: `onecoreuap\base\appmodel\Search\common\include\MemMappedImage.h`
- `0x14005d2f8`: `CMemMappedImage::CreateImageMapping : CreateFileMapping failed with hr(0x%08x)`
- `0x14005d2cb`: `CMemMappedImage::CreateImageMapping : An object with provided name already exists!`

## pseudocode

```c
__int64 __fastcall CMemMappedImage::CreateImageMapping(
        CMemMappedImage *this,
        struct _SECURITY_ATTRIBUTES *const a2,
        __int64 a3,
        __int64 a4,
        DWORD dwMaximumSizeLow)
{
  HANDLE FileMappingW; // rdi
  DWORD LastError; // ebx
  const wchar_t *v8; // r9

  FileMappingW = CreateFileMappingW(
                   (HANDLE)0xFFFFFFFFFFFFFFFFLL,
                   0,
                   4u,
                   0,
                   dwMaximumSizeLow,
                   L"Global\\IndexerImageSharedMemMapping");
  LastError = GetLastError();
  if ( LastError == 183 )
    SearchIndexerTrace::Information(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\Search\\common\\include\\MemMappedImage.h",
      (const wchar_t *)0x2B,
      (unsigned int)L"CMemMappedImage::CreateImageMapping : An object with provided name already exists!",
      v8);
  if ( FileMappingW )
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      this,
      FileMappingW);
    return 0;
  }
  else
  {
    if ( (int)LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    SearchIndexerTrace::Error(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\Search\\common\\include\\MemMappedImage.h",
      (const wchar_t *)0x30,
      (unsigned int)L"CMemMappedImage::CreateImageMapping : CreateFileMapping failed with hr(0x%08x)",
      (const wchar_t *)LastError);
    return LastError;
  }
}

```

## disassembly

```asm
0x14005d280  mov     [rsp+arg_0], rbx
0x14005d285  mov     [rsp+arg_8], rsi
0x14005d28a  push    rdi
0x14005d28b  sub     rsp, 30h
0x14005d28f  lea     rax, aGlobalIndexeri; "Global\\IndexerImageSharedMemMapping"
0x14005d296  xor     r9d, r9d; dwMaximumSizeHigh
0x14005d299  mov     [rsp+38h+lpName], rax; lpName
0x14005d29e  mov     rsi, rcx
0x14005d2a1  mov     eax, [rsp+38h+arg_20]
0x14005d2a5  xor     edx, edx; lpFileMappingAttributes
0x14005d2a7  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x14005d2ab  mov     [rsp+38h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x14005d2af  lea     r8d, [r9+4]; flProtect
0x14005d2b3  call    cs:__imp_CreateFileMappingW
0x14005d2b9  mov     rdi, rax
0x14005d2bc  call    cs:__imp_GetLastError
0x14005d2c2  mov     ebx, eax
0x14005d2c4  cmp     eax, 0B7h
0x14005d2c9  jnz     short loc_14005D2E3
0x14005d2cb  lea     r8, aCmemmappedimag; "CMemMappedImage::CreateImageMapping : A"...
0x14005d2d2  mov     edx, 2Bh ; '+'; wchar_t *
0x14005d2d7  lea     rcx, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\Search\\com"...
0x14005d2de  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x14005d2e3  test    rdi, rdi
0x14005d2e6  jnz     short loc_14005D314
0x14005d2e8  test    ebx, ebx
0x14005d2ea  jle     short loc_14005D2F5
0x14005d2ec  movzx   ebx, bx
0x14005d2ef  or      ebx, 80070000h
0x14005d2f5  mov     r9d, ebx; wchar_t *
0x14005d2f8  lea     r8, aCmemmappedimag_1; "CMemMappedImage::CreateImageMapping : C"...
0x14005d2ff  mov     edx, 30h ; '0'; wchar_t *
0x14005d304  lea     rcx, aOnecoreuapBase_10; "onecoreuap\\base\\appmodel\\Search\\com"...
0x14005d30b  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x14005d310  mov     eax, ebx
0x14005d312  jmp     short loc_14005D321
0x14005d314  mov     rdx, rdi
0x14005d317  mov     rcx, rsi
0x14005d31a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x14005d31f  xor     eax, eax
0x14005d321  mov     rbx, [rsp+38h+arg_0]
0x14005d326  mov     rsi, [rsp+38h+arg_8]
0x14005d32b  add     rsp, 30h
0x14005d32f  pop     rdi
0x14005d330  retn
```
