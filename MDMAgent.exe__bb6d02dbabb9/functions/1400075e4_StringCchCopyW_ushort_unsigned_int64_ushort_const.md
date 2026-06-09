# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x1400075e4`
- end: `0x140007622`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `62`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140005144`
- `0x140007820`
- `0x14000829c`
- `0x14000bc88`
- `0x14000bdd4`
- `0x140010618`
- `0x140010718`

## callees

- `0x1400075e4`
- `0x14000768c`

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
0x1400075e4  sub     rsp, 38h
0x1400075e8  mov     rax, rdx
0x1400075eb  test    rdx, rdx
0x1400075ee  jz      short loc_14000760B
0x1400075f0  cmp     rax, 7FFFFFFFh
0x1400075f6  jbe     short loc_1400075FF
0x1400075f8  mov     edx, 80070057h; cchDest
0x1400075fd  jmp     short loc_140007615
0x1400075ff  mov     r9, r8; pszSrc
0x140007602  call    StringCopyWorkerW
0x140007607  mov     edx, eax
0x140007609  jmp     short loc_14000761A
0x14000760b  mov     edx, 80070057h
0x140007610  test    rax, rax
0x140007613  jz      short loc_14000761A
0x140007615  xor     eax, eax
0x140007617  mov     [rcx], ax
0x14000761a  mov     eax, edx
0x14000761c  add     rsp, 38h
0x140007620  retn
```
