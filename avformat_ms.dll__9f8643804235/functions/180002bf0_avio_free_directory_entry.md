# avio_free_directory_entry

- ea: `0x180002bf0`
- end: `0x180002c1b`
- name: `avio_free_directory_entry`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180002e20`

## callees

- `0x180002bf0`
- `0x18001bba0`
- `0x18001bba6`

## pseudocode

```c
__int64 __fastcall avio_free_directory_entry(_QWORD *a1)
{
  _QWORD *v2; // rcx
  __int64 result; // rax

  if ( a1 )
  {
    v2 = (_QWORD *)*a1;
    if ( v2 )
    {
      av_free(*v2);
      return av_freep(a1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180002bf0  test    rcx, rcx
0x180002bf3  jz      short locret_180002C1A
0x180002bf5  push    rbx
0x180002bf6  sub     rsp, 20h
0x180002bfa  mov     rbx, rcx
0x180002bfd  mov     rcx, [rcx]
0x180002c00  test    rcx, rcx
0x180002c03  jz      short loc_180002C15
0x180002c05  mov     rcx, [rcx]
0x180002c08  call    av_free
0x180002c0d  mov     rcx, rbx
0x180002c10  call    av_freep
0x180002c15  add     rsp, 20h
0x180002c19  pop     rbx
0x180002c1a  retn
```
