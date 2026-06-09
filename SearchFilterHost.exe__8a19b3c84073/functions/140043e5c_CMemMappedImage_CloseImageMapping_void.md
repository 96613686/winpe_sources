# CMemMappedImage::CloseImageMapping(void)

- ea: `0x140043e5c`
- end: `0x140043ed9`
- name: `?CloseImageMapping@CMemMappedImage@@QEAAJXZ`
- size: `125`
- prototype: `__int64 __fastcall(CMemMappedImage *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400439ac`
- `0x140043b4c`
- `0x1400459e0`

## callees

- `0x14001e440`
- `0x14002b0a4`
- `0x140043e5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140043e78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140043e78`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140043e6e`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x140043e6e`

## string_xrefs

- `0x140043e9c`: `onecoreuap\base\appmodel\Search\common\include\MemMappedImage.h`

## pseudocode

```c
__int64 __fastcall CMemMappedImage::CloseImageMapping(CMemMappedImage *this)
{
  const void *v2; // rcx
  signed int LastError; // eax
  unsigned int v4; // ebx

  v2 = (const void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    if ( !UnmapViewOfFile(v2) )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      SearchIndexerTrace::Error(
        (wchar_t *)L"onecoreuap\\base\\appmodel\\Search\\common\\include\\MemMappedImage.h",
        (const wchar_t *)0x66,
        (unsigned int)L"CMemMappedImage::CloseImageMapping : UnmapViewOfFile failed with hr(0x%08x)",
        (const wchar_t *)v4);
      return v4;
    }
    *((_QWORD *)this + 1) = 0;
  }
  if ( (unsigned __int64)(*(_QWORD *)this - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      this,
      0);
  *((_DWORD *)this + 4) = 0;
  return 0;
}

```

## disassembly

```asm
0x140043e5c  push    rbx
0x140043e5e  sub     rsp, 20h
0x140043e62  mov     rbx, rcx
0x140043e65  mov     rcx, [rcx+8]; lpBaseAddress
0x140043e69  test    rcx, rcx
0x140043e6c  jz      short loc_140043EB4
0x140043e6e  call    cs:__imp_UnmapViewOfFile
0x140043e74  test    eax, eax
0x140043e76  jnz     short loc_140043EAC
0x140043e78  call    cs:__imp_GetLastError
0x140043e7e  mov     ebx, eax
0x140043e80  test    eax, eax
0x140043e82  jle     short loc_140043E8D
0x140043e84  movzx   ebx, ax
0x140043e87  or      ebx, 80070000h
0x140043e8d  mov     r9d, ebx; wchar_t *
0x140043e90  lea     r8, aCmemmappedimag_2; "CMemMappedImage::CloseImageMapping : Un"...
0x140043e97  mov     edx, 66h ; 'f'; wchar_t *
0x140043e9c  lea     rcx, aOnecoreuapBase_7; "onecoreuap\\base\\appmodel\\Search\\com"...
0x140043ea3  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x140043ea8  mov     eax, ebx
0x140043eaa  jmp     short loc_140043ED3
0x140043eac  mov     qword ptr [rbx+8], 0
0x140043eb4  mov     rax, [rbx]
0x140043eb7  dec     rax
0x140043eba  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140043ebe  ja      short loc_140043ECA
0x140043ec0  xor     edx, edx
0x140043ec2  mov     rcx, rbx
0x140043ec5  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140043eca  mov     dword ptr [rbx+10h], 0
0x140043ed1  xor     eax, eax
0x140043ed3  add     rsp, 20h
0x140043ed7  pop     rbx
0x140043ed8  retn
```
