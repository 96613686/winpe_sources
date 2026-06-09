# SetComplexPermLayerStates(int (*)(ushort const *,ushort const *,ulong,int,int),ushort const *,ulong,ulong,int,int)

- ea: `0x18000ec5c`
- end: `0x18000ecd8`
- name: `?SetComplexPermLayerStates@@YAHP6AHPEBG0KHH@Z0KKHH@Z`
- size: `124`
- prototype: `__int64 __fastcall(int (*)(const unsigned __int16 *, const unsigned __int16 *, unsigned int, int, int), const unsigned __int16 *, unsigned int, unsigned int, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f740`

## callees

- `0x18000ec5c`
- `0x180017010`

## pseudocode

```c
__int64 __fastcall SetComplexPermLayerStates(
        int (*a1)(const unsigned __int16 *, const unsigned __int16 *, unsigned int, int, int),
        const unsigned __int16 *a2,
        int a3,
        unsigned int a4,
        unsigned int a5,
        int a6)
{
  int v10; // ebx
  __int64 v11; // r9

  v10 = 0;
  while ( 1 )
  {
    v11 = 54LL * v10;
    if ( (a3 & *(_DWORD *)&aHighdpiaware[v11 + 48]) != 0
      && !((unsigned int (__fastcall *)(const unsigned __int16 *, wchar_t *, _QWORD, _QWORD, int))a1)(
            a2,
            &aHighdpiaware[v11],
            a4,
            a5,
            a6) )
    {
      break;
    }
    if ( (unsigned int)++v10 >= 3 )
      return 1;
  }
  return 0;
}

```

## disassembly

```asm
0x18000ec5c  push    rbx
0x18000ec5e  push    rbp
0x18000ec5f  push    rsi
0x18000ec60  push    rdi
0x18000ec61  push    r12
0x18000ec63  push    r14
0x18000ec65  push    r15
0x18000ec67  sub     rsp, 30h
0x18000ec6b  mov     r15d, [rsp+68h+arg_28]
0x18000ec73  lea     r12, aHighdpiaware; "HIGHDPIAWARE"
0x18000ec7a  mov     esi, r9d
0x18000ec7d  mov     edi, r8d
0x18000ec80  mov     rbp, rdx
0x18000ec83  mov     r14, rcx
0x18000ec86  xor     ebx, ebx
0x18000ec88  movsxd  rax, ebx
0x18000ec8b  imul    r9, rax, 6Ch ; 'l'
0x18000ec8f  test    [r9+r12+60h], edi
0x18000ec94  jz      short loc_18000ECB9
0x18000ec96  lea     rdx, [r9+r12]
0x18000ec9a  mov     [rsp+68h+var_48], r15d
0x18000ec9f  mov     r9d, [rsp+68h+arg_20]
0x18000eca7  mov     r8d, esi
0x18000ecaa  mov     rcx, rbp
0x18000ecad  mov     rax, r14
0x18000ecb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecb5  test    eax, eax
0x18000ecb7  jz      short loc_18000ECD4
0x18000ecb9  inc     ebx
0x18000ecbb  cmp     ebx, 3
0x18000ecbe  jb      short loc_18000EC88
0x18000ecc0  mov     eax, 1
0x18000ecc5  add     rsp, 30h
0x18000ecc9  pop     r15
0x18000eccb  pop     r14
0x18000eccd  pop     r12
0x18000eccf  pop     rdi
0x18000ecd0  pop     rsi
0x18000ecd1  pop     rbp
0x18000ecd2  pop     rbx
0x18000ecd3  retn
0x18000ecd4  xor     eax, eax
0x18000ecd6  jmp     short loc_18000ECC5
```
