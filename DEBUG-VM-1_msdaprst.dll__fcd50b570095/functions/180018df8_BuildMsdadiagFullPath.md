# BuildMsdadiagFullPath

- ea: `0x180018df8`
- end: `0x180018e4e`
- name: `BuildMsdadiagFullPath`
- size: `86`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180018c24`
- `0x1800190dc`

## callees

- `0x1800027f0`
- `0x180018df8`

## import_xrefs

- `KERNEL32!GetSystemDirectoryW` at `0x180018e0c`
- `KERNEL32!GetSystemDirectoryW` at `0x180018e0c`

## string_xrefs

- `0x180018e2a`: `\msdadiag.dll`

## pseudocode

```c
_BOOL8 __fastcall BuildMsdadiagFullPath(WCHAR *a1)
{
  __int64 SystemDirectoryW; // rdx

  SystemDirectoryW = GetSystemDirectoryW(a1, 0x10Eu);
  return (unsigned __int64)(SystemDirectoryW - 1) <= 0x10C
      && (int)StringCchCopyW(&a1[SystemDirectoryW], 270 - SystemDirectoryW, L"\\msdadiag.dll") >= 0;
}

```

## disassembly

```asm
0x180018df8  mov     [rsp+arg_0], rbx
0x180018dfd  push    rdi
0x180018dfe  sub     rsp, 20h
0x180018e02  mov     ebx, 10Eh
0x180018e07  mov     rdi, rcx
0x180018e0a  mov     edx, ebx; uSize
0x180018e0c  call    cs:__imp_GetSystemDirectoryW
0x180018e12  mov     edx, eax
0x180018e14  lea     rax, [rdx-1]
0x180018e18  cmp     rax, 10Ch
0x180018e1e  ja      short loc_180018E41
0x180018e20  sub     rbx, rdx
0x180018e23  lea     rcx, [rdi+rdx*2]; unsigned __int16 *
0x180018e27  mov     rdx, rbx; unsigned __int64
0x180018e2a  lea     r8, aMsdadiagDll_0; "\\msdadiag.dll"
0x180018e31  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180018e36  test    eax, eax
0x180018e38  js      short loc_180018E41
0x180018e3a  mov     eax, 1
0x180018e3f  jmp     short loc_180018E43
0x180018e41  xor     eax, eax
0x180018e43  mov     rbx, [rsp+28h+arg_0]
0x180018e48  add     rsp, 20h
0x180018e4c  pop     rdi
0x180018e4d  retn
```
