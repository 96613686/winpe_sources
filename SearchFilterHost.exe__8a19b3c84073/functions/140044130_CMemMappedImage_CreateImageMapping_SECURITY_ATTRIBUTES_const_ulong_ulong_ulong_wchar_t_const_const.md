# CMemMappedImage::CreateImageMapping(_SECURITY_ATTRIBUTES * const,ulong,ulong,ulong,wchar_t const * const)

- ea: `0x140044130`
- end: `0x1400441e1`
- name: `?CreateImageMapping@CMemMappedImage@@QEAAJQEAU_SECURITY_ATTRIBUTES@@KKKQEB_W@Z`
- size: `177`
- prototype: `__int64 __fastcall(CMemMappedImage *__hidden this, struct _SECURITY_ATTRIBUTES *const, unsigned int, unsigned int, DWORD, const wchar_t *const)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x140044b40`

## callees

- `0x14001e440`
- `0x14002b0a4`
- `0x14002dfb4`
- `0x140044130`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004416c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004416c`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x140044163`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x140044163`

## string_xrefs

- `0x14004417b`: `CMemMappedImage::CreateImageMapping : An object with provided name already exists!`
- `0x140044187`: `onecoreuap\base\appmodel\Search\common\include\MemMappedImage.h`
- `0x1400441b4`: `onecoreuap\base\appmodel\Search\common\include\MemMappedImage.h`
- `0x1400441a8`: `CMemMappedImage::CreateImageMapping : CreateFileMapping failed with hr(0x%08x)`

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
0x140044130  mov     [rsp+arg_0], rbx
0x140044135  mov     [rsp+arg_8], rsi
0x14004413a  push    rdi
0x14004413b  sub     rsp, 30h
0x14004413f  lea     rax, Name; "Global\\IndexerImageSharedMemMapping"
0x140044146  xor     r9d, r9d; dwMaximumSizeHigh
0x140044149  mov     [rsp+38h+lpName], rax; lpName
0x14004414e  mov     rsi, rcx
0x140044151  mov     eax, [rsp+38h+arg_20]
0x140044155  xor     edx, edx; lpFileMappingAttributes
0x140044157  or      rcx, 0FFFFFFFFFFFFFFFFh; hFile
0x14004415b  mov     [rsp+38h+dwMaximumSizeLow], eax; dwMaximumSizeLow
0x14004415f  lea     r8d, [r9+4]; flProtect
0x140044163  call    cs:__imp_CreateFileMappingW
0x140044169  mov     rdi, rax
0x14004416c  call    cs:__imp_GetLastError
0x140044172  mov     ebx, eax
0x140044174  cmp     eax, 0B7h
0x140044179  jnz     short loc_140044193
0x14004417b  lea     r8, aCmemmappedimag; "CMemMappedImage::CreateImageMapping : A"...
0x140044182  mov     edx, 2Bh ; '+'; wchar_t *
0x140044187  lea     rcx, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\Search\\com"...
0x14004418e  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x140044193  test    rdi, rdi
0x140044196  jnz     short loc_1400441C4
0x140044198  test    ebx, ebx
0x14004419a  jle     short loc_1400441A5
0x14004419c  movzx   ebx, bx
0x14004419f  or      ebx, 80070000h
0x1400441a5  mov     r9d, ebx; wchar_t *
0x1400441a8  lea     r8, aCmemmappedimag_1; "CMemMappedImage::CreateImageMapping : C"...
0x1400441af  mov     edx, 30h ; '0'; wchar_t *
0x1400441b4  lea     rcx, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1400441bb  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x1400441c0  mov     eax, ebx
0x1400441c2  jmp     short loc_1400441D1
0x1400441c4  mov     rdx, rdi
0x1400441c7  mov     rcx, rsi
0x1400441ca  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1400441cf  xor     eax, eax
0x1400441d1  mov     rbx, [rsp+38h+arg_0]
0x1400441d6  mov     rsi, [rsp+38h+arg_8]
0x1400441db  add     rsp, 30h
0x1400441df  pop     rdi
0x1400441e0  retn
```
