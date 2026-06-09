# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x140007324`
- end: `0x140007361`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `61`
- prototype: `__int64 __fastcall(unsigned __int16 *, size_t, size_t *)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x140004fe4`
- `0x140007560`
- `0x140007f34`
- `0x14000b754`
- `0x14000b894`
- `0x14000fe10`
- `0x14000ff08`

## callees

- `0x140007324`
- `0x1400073cc`

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
0x140007324  sub     rsp, 38h
0x140007328  mov     rax, rdx
0x14000732b  test    rdx, rdx
0x14000732e  jz      short loc_14000734B
0x140007330  cmp     rax, 7FFFFFFFh
0x140007336  jbe     short loc_14000733F
0x140007338  mov     edx, 80070057h; cchDest
0x14000733d  jmp     short loc_140007355
0x14000733f  mov     r9, r8; pszSrc
0x140007342  call    StringCopyWorkerW
0x140007347  mov     edx, eax
0x140007349  jmp     short loc_14000735A
0x14000734b  mov     edx, 80070057h
0x140007350  test    rax, rax
0x140007353  jz      short loc_14000735A
0x140007355  xor     eax, eax
0x140007357  mov     [rcx], ax
0x14000735a  mov     eax, edx
0x14000735c  add     rsp, 38h
0x140007360  retn
```
