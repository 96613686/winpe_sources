# StringCbCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x18000bbd4`
- end: `0x18000bc14`
- name: `?StringCbCopyW@@YAJPEAG_KPEBG@Z`
- size: `64`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180002510`
- `0x180003020`
- `0x18000c21c`
- `0x18000ed8c`
- `0x180013214`

## callees

- `0x18000bbd4`
- `0x18000bc60`

## pseudocode

```c
__int64 __fastcall StringCbCopyW(unsigned __int16 *a1, unsigned __int64 a2, size_t *a3)
{
  unsigned int v3; // edx
  size_t v5; // [rsp+20h] [rbp-18h]

  if ( a2 >> 1 )
  {
    if ( a2 >> 1 <= 0x7FFFFFFF )
    {
      return (unsigned int)StringCopyWorkerW(a1, a2 >> 1, a3, (STRSAFE_PCNZWCH)a3, v5);
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
0x18000bbd4  sub     rsp, 38h
0x18000bbd8  mov     rax, rdx
0x18000bbdb  shr     rax, 1
0x18000bbde  jz      short loc_18000BBFE
0x18000bbe0  cmp     rax, 7FFFFFFFh
0x18000bbe6  jbe     short loc_18000BBEF
0x18000bbe8  mov     edx, 80070057h
0x18000bbed  jmp     short loc_18000BC08
0x18000bbef  mov     r9, r8; pszSrc
0x18000bbf2  mov     rdx, rax; cchDest
0x18000bbf5  call    StringCopyWorkerW
0x18000bbfa  mov     edx, eax
0x18000bbfc  jmp     short loc_18000BC0D
0x18000bbfe  mov     edx, 80070057h
0x18000bc03  test    rax, rax
0x18000bc06  jz      short loc_18000BC0D
0x18000bc08  xor     eax, eax
0x18000bc0a  mov     [rcx], ax
0x18000bc0d  mov     eax, edx
0x18000bc0f  add     rsp, 38h
0x18000bc13  retn
```
