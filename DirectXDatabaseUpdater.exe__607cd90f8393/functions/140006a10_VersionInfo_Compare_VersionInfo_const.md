# VersionInfo::Compare(VersionInfo const &)

- ea: `0x140006a10`
- end: `0x140006a39`
- name: `?Compare@VersionInfo@@QEBAHAEBV1@@Z`
- size: `41`
- prototype: `__int64 __fastcall(VersionInfo *__hidden this, const struct VersionInfo *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000b0cc`
- `0x14000d384`
- `0x140010ce8`

## callees

- `0x140006a10`

## pseudocode

```c
__int64 __fastcall VersionInfo::Compare(VersionInfo *this, const struct VersionInfo *a2)
{
  __int64 i; // r8
  unsigned int v4; // r9d
  unsigned int v5; // edx

  for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
  {
    v4 = *((_DWORD *)this + i);
    v5 = *((_DWORD *)a2 + i);
    if ( v5 != v4 )
      return v5 < v4 ? 1 : -1;
  }
  return 0;
}

```

## disassembly

```asm
0x140006a10  mov     r10, rdx
0x140006a13  xor     r8d, r8d
0x140006a16  cmp     r8d, 3
0x140006a1a  jnb     short loc_140006A36
0x140006a1c  mov     r9d, [rcx+r8*4]
0x140006a20  mov     edx, [r10+r8*4]
0x140006a24  cmp     edx, r9d
0x140006a27  jnz     short loc_140006A2E
0x140006a29  inc     r8d
0x140006a2c  jmp     short loc_140006A16
0x140006a2e  sbb     eax, eax
0x140006a30  and     eax, 2
0x140006a33  dec     eax
0x140006a35  retn
0x140006a36  xor     eax, eax
0x140006a38  retn
```
