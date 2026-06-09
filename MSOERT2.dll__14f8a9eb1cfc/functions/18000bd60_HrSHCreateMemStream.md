# HrSHCreateMemStream

- ea: `0x18000bd60`
- end: `0x18000bd8e`
- name: `HrSHCreateMemStream`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000bd60`

## import_xrefs

- `SHLWAPI!__imp_SHCreateMemStream` at `0x18000bd73`
- `SHLWAPI!__imp_SHCreateMemStream` at `0x18000bd73`

## pseudocode

```c
__int64 __fastcall HrSHCreateMemStream(const BYTE *a1, UINT a2, IStream **a3)
{
  __int64 result; // rax
  IStream *v5; // rax

  result = 2147942487LL;
  if ( a3 )
  {
    v5 = SHCreateMemStream(a1, a2);
    *a3 = v5;
    return v5 == 0 ? 0x8007000E : 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000bd60  push    rbx
0x18000bd62  sub     rsp, 20h
0x18000bd66  mov     rbx, r8
0x18000bd69  mov     eax, 80070057h
0x18000bd6e  test    r8, r8
0x18000bd71  jz      short loc_18000BD88
0x18000bd73  call    cs:__imp_SHCreateMemStream
0x18000bd79  mov     [rbx], rax
0x18000bd7c  neg     rax
0x18000bd7f  sbb     eax, eax
0x18000bd81  not     eax
0x18000bd83  and     eax, 8007000Eh
0x18000bd88  add     rsp, 20h
0x18000bd8c  pop     rbx
0x18000bd8d  retn
```
