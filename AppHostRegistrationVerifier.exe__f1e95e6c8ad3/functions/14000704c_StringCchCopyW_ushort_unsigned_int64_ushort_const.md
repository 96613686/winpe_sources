# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x14000704c`
- end: `0x140007089`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `61`
- prototype: `__int64 __fastcall(unsigned __int16 *, size_t, size_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140004fd0`
- `0x140007248`
- `0x14000a934`

## callees

- `0x14000704c`
- `0x14000713c`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, size_t a2, size_t *a3)
{
  unsigned int v3; // edx
  size_t v5; // [rsp+20h] [rbp-18h]

  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      return (unsigned int)StringCopyWorkerW(a1, a2, a3, (STRSAFE_PCNZWCH)a3, v5);
    }
    else
    {
      v3 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x14000704c  sub     rsp, 38h
0x140007050  mov     rax, rdx
0x140007053  test    rdx, rdx
0x140007056  jz      short loc_140007073
0x140007058  cmp     rax, 7FFFFFFFh
0x14000705e  jbe     short loc_140007067
0x140007060  mov     edx, 80070057h; cchDest
0x140007065  jmp     short loc_14000707D
0x140007067  mov     r9, r8; pszSrc
0x14000706a  call    StringCopyWorkerW
0x14000706f  mov     edx, eax
0x140007071  jmp     short loc_140007082
0x140007073  mov     edx, 80070057h
0x140007078  test    rax, rax
0x14000707b  jz      short loc_140007082
0x14000707d  xor     eax, eax
0x14000707f  mov     [rcx], ax
0x140007082  mov     eax, edx
0x140007084  add     rsp, 38h
0x140007088  retn
```
