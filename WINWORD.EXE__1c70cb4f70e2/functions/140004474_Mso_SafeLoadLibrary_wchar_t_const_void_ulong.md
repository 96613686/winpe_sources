# Mso::SafeLoadLibrary(wchar_t const *,void *,ulong)

- ea: `0x140004474`
- end: `0x140004499`
- name: `?SafeLoadLibrary@Mso@@YAPEAUHINSTANCE__@@PEB_WPEAXK@Z`
- size: `37`
- prototype: `HINSTANCE __fastcall(Mso *__hidden this, const wchar_t *, void *, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140004244`
- `0x140004c68`
- `0x1400052b0`

## callees

- `0x140004474`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x140004492`

## pseudocode

```c
HINSTANCE __fastcall Mso::SafeLoadLibrary(const WCHAR *this, const wchar_t *a2, void *a3)
{
  if ( !*this )
    __fastfail(5u);
  return LoadLibraryExW(this, 0, (unsigned int)a3 & 0xFFFFEFF7 | 0x1000);
}

```

## disassembly

```asm
0x140004474  cmp     word ptr [rcx], 0
0x140004478  mov     rax, rcx
0x14000447b  jnz     short loc_140004484
0x14000447d  mov     ecx, 5
0x140004482  int     29h; Win8: RtlFailFast(ecx)
0x140004484  and     r8d, 0FFFFFFF7h
0x140004488  xor     edx, edx
0x14000448a  bts     r8d, 0Ch
0x14000448f  mov     rcx, rax
0x140004492  jmp     cs:__imp_LoadLibraryExW
```
