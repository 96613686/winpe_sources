# SzString_CchLength(ushort const *,ulong *,ulong)

- ea: `0x180004120`
- end: `0x1800041c0`
- name: `?SzString_CchLength@@YAKPEBGPEAKK@Z`
- size: `160`
- prototype: `unsigned int __fastcall(const unsigned __int16 *, unsigned int *, unsigned int)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180001c04`
- `0x180001dd0`
- `0x18000283c`
- `0x1800030a0`
- `0x180003b70`
- `0x180003d20`
- `0x180003dc0`
- `0x180004050`
- `0x180012974`
- `0x18001a008`

## callees

- `0x180004120`

## pseudocode

```c
__int64 __fastcall SzString_CchLength(const unsigned __int16 *a1, unsigned int *a2, unsigned int a3)
{
  unsigned int v5; // r11d
  unsigned int v6; // r8d
  int v7; // edi
  unsigned int v8; // eax
  unsigned int i; // edx

  v5 = 0;
  if ( a2 )
    *a2 = 0;
  if ( !a1 )
    return 87;
  v6 = 0;
  v7 = 0;
  v8 = 0xFFFF;
  if ( a3 )
    v8 = a3;
  for ( i = 0; i < v8; ++i )
  {
    if ( !a1[i] )
    {
      v7 = 1;
      break;
    }
    ++v6;
  }
  if ( v7 )
  {
    if ( a2 )
      *a2 = v6;
  }
  else
  {
    return 122;
  }
  return v5;
}

```

## disassembly

```asm
0x180004120  mov     [rsp+arg_0], rbx
0x180004125  push    rdi
0x180004126  sub     rsp, 10h
0x18000412a  mov     r10d, r8d
0x18000412d  mov     rbx, rdx
0x180004130  mov     r9, rcx
0x180004133  xor     r11d, r11d
0x180004136  test    rdx, rdx
0x180004139  jz      short loc_18000413E
0x18000413b  mov     [rdx], r11d
0x18000413e  test    r9, r9
0x180004141  jz      short loc_1800041A3
0x180004143  mov     r8d, r11d
0x180004146  mov     edi, r11d
0x180004149  mov     eax, 0FFFFh
0x18000414e  test    r10d, r10d
0x180004151  cmovnz  eax, r10d
0x180004155  mov     edx, r11d
0x180004158  mov     [rsp+18h+var_18], edx
0x18000415b  cmp     edx, eax
0x18000415d  jnb     short loc_18000417E
0x18000415f  mov     ecx, edx
0x180004161  cmp     word ptr [r9+rcx*2], 0
0x180004167  jz      short loc_180004175
0x180004169  inc     r8d
0x18000416c  mov     [rsp+18h+var_10], r8d
0x180004171  inc     edx
0x180004173  jmp     short loc_180004158
0x180004175  mov     edi, 1
0x18000417a  mov     [rsp+18h+var_14], edi
0x18000417e  jmp     short loc_180004188
0x180004180  mov     r11d, 7Ah ; 'z'
0x180004186  jmp     short loc_180004194
0x180004188  test    edi, edi
0x18000418a  jz      short loc_1800041B8
0x18000418c  test    rbx, rbx
0x18000418f  jz      short loc_180004194
0x180004191  mov     [rbx], r8d
0x180004194  mov     eax, r11d
0x180004197  mov     rbx, [rsp+18h+arg_0]
0x18000419c  add     rsp, 10h
0x1800041a0  pop     rdi
0x1800041a1  retn
0x1800041a3  mov     r11d, 57h ; 'W'
0x1800041a9  mov     eax, r11d
0x1800041ac  mov     rbx, [rsp+18h+arg_0]
0x1800041b1  add     rsp, 10h
0x1800041b5  pop     rdi
0x1800041b6  retn
0x1800041b8  mov     r11d, 7Ah ; 'z'
0x1800041be  jmp     short loc_180004194
```
