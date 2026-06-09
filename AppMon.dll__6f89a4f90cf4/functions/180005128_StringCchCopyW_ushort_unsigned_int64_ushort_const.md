# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180005128`
- end: `0x180005165`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `61`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800034c0`
- `0x180005328`
- `0x18000bafc`

## callees

- `0x180005128`
- `0x180005218`

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
0x180005128  sub     rsp, 38h
0x18000512c  mov     rax, rdx
0x18000512f  test    rdx, rdx
0x180005132  jz      short loc_18000514F
0x180005134  cmp     rax, 7FFFFFFFh
0x18000513a  jbe     short loc_180005143
0x18000513c  mov     edx, 80070057h; cchDest
0x180005141  jmp     short loc_180005159
0x180005143  mov     r9, r8; pszSrc
0x180005146  call    StringCopyWorkerW
0x18000514b  mov     edx, eax
0x18000514d  jmp     short loc_18000515E
0x18000514f  mov     edx, 80070057h
0x180005154  test    rax, rax
0x180005157  jz      short loc_18000515E
0x180005159  xor     eax, eax
0x18000515b  mov     [rcx], ax
0x18000515e  mov     eax, edx
0x180005160  add     rsp, 38h
0x180005164  retn
```
