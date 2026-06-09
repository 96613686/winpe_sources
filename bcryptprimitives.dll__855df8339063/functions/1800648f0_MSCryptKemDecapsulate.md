# MSCryptKemDecapsulate

- ea: `0x1800648f0`
- end: `0x180064a77`
- name: `MSCryptKemDecapsulate`
- size: `391`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, unsigned int, unsigned int *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001010`
- `0x18000ecb0`
- `0x180056cf0`
- `0x1800648f0`
- `0x180065430`
- `0x18006f82c`

## string_xrefs

- `0x180064929`: `onecore\ds\security\cryptoapi\ncrypt\msprim\base\kem.c`

## pseudocode

```c
__int64 __fastcall MSCryptKemDecapsulate(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        unsigned int a5,
        unsigned int *a6,
        int a7)
{
  __int64 v8; // r15
  __int64 v10; // r9
  unsigned int v11; // ebx
  __int64 v12; // rcx
  int v13; // eax
  unsigned int v14; // eax
  _QWORD v16[9]; // [rsp+30h] [rbp-48h] BYREF

  v8 = a3;
  v16[0] = 0;
  if ( !a7 )
  {
    if ( !a2 )
    {
      v10 = 1477;
      goto LABEL_3;
    }
    if ( !a6 )
    {
      v10 = 1484;
      goto LABEL_3;
    }
    v13 = ValidateKemKey(a1, v16, 1);
    v11 = v13;
    if ( v13 < 0 )
    {
      v10 = 1491;
LABEL_11:
      v12 = (unsigned int)v13;
      goto LABEL_4;
    }
    if ( *(_DWORD *)(v16[0] + 8LL) != 458753 && *(_DWORD *)(v16[0] + 8LL) != 458754 )
    {
      v10 = 1512;
LABEL_15:
      v11 = -1073741637;
      v12 = 3221225659LL;
      goto LABEL_4;
    }
    if ( !a4 )
    {
      *a6 = 32;
      return v11;
    }
    if ( a5 != 32 )
    {
      v10 = 1529;
      v11 = a5 < 0x20 ? -1073741789 : -1073741306;
      v12 = v11;
      goto LABEL_4;
    }
    if ( (_DWORD)v8 != *(_DWORD *)(*(_QWORD *)(v16[0] + 24LL) + 20LL) )
    {
      v11 = -1073741306;
      v10 = 1536;
      v12 = 3221225990LL;
      goto LABEL_4;
    }
    if ( *(_DWORD *)(v16[0] + 8LL) == 458753 )
    {
      v14 = SymCryptMlKemDecapsulate(*(_QWORD *)(v16[0] + 32LL), a2, v8, a4, 32);
    }
    else
    {
      if ( *(_DWORD *)(v16[0] + 8LL) != 458754 )
      {
        v10 = 1555;
        goto LABEL_15;
      }
      v14 = SymCryptCompositeMlKemDecapsulate(*(_QWORD *)(v16[0] + 32LL), a2, v8, a4, 32);
    }
    if ( !v14 )
    {
      *a6 = a5;
      return v11;
    }
    v13 = SymcryptErrorCodeToNtStatus(v14);
    v11 = v13;
    v10 = 1563;
    goto LABEL_11;
  }
  v10 = 1470;
LABEL_3:
  v11 = -1073741811;
  v12 = 3221225485LL;
LABEL_4:
  DebugTraceError(v12, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\base\\kem.c", v10);
  return v11;
}

```

## disassembly

```asm
0x1800648f0  push    rbx
0x1800648f2  push    rbp
0x1800648f3  push    rsi
0x1800648f4  push    rdi
0x1800648f5  push    r14
0x1800648f7  push    r15
0x1800648f9  sub     rsp, 48h
0x1800648fd  cmp     [rsp+78h+arg_30], 0
0x180064905  mov     r14, r9
0x180064908  mov     r15d, r8d
0x18006490b  mov     rbp, rdx
0x18006490e  mov     [rsp+78h+var_48], 0
0x180064917  jz      short loc_180064941
0x180064919  mov     r9d, 5BEh
0x18006491f  mov     ebx, 0C000000Dh
0x180064924  mov     ecx, 0C000000Dh
0x180064929  lea     r8, aOnecoreDsSecur_27; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180064930  lea     rdx, aStatus; "Status"
0x180064937  call    DebugTraceError
0x18006493c  jmp     loc_180064A67
0x180064941  test    rbp, rbp
0x180064944  jnz     short loc_18006494E
0x180064946  mov     r9d, 5C5h
0x18006494c  jmp     short loc_18006491F
0x18006494e  mov     rdi, [rsp+78h+arg_28]
0x180064956  test    rdi, rdi
0x180064959  jnz     short loc_180064963
0x18006495b  mov     r9d, 5CCh
0x180064961  jmp     short loc_18006491F
0x180064963  mov     r8d, 1
0x180064969  lea     rdx, [rsp+78h+var_48]
0x18006496e  call    ValidateKemKey
0x180064973  mov     ebx, eax
0x180064975  test    eax, eax
0x180064977  jns     short loc_180064983
0x180064979  mov     r9d, 5D3h
0x18006497f  mov     ecx, eax
0x180064981  jmp     short loc_180064929
0x180064983  mov     r10, [rsp+78h+var_48]
0x180064988  mov     r8d, 70001h
0x18006498e  mov     ecx, [r10+8]
0x180064992  mov     eax, ecx
0x180064994  sub     eax, r8d
0x180064997  jz      short loc_1800649B3
0x180064999  cmp     eax, 1
0x18006499c  jz      short loc_1800649B3
0x18006499e  mov     r9d, 5E8h
0x1800649a4  mov     ebx, 0C00000BBh
0x1800649a9  mov     ecx, 0C00000BBh
0x1800649ae  jmp     loc_180064929
0x1800649b3  mov     rax, [r10+18h]
0x1800649b7  mov     edx, [rax+14h]
0x1800649ba  test    r14, r14
0x1800649bd  jnz     short loc_1800649CA
0x1800649bf  mov     dword ptr [rdi], 20h ; ' '
0x1800649c5  jmp     loc_180064A67
0x1800649ca  mov     esi, [rsp+78h+arg_20]
0x1800649d1  cmp     esi, 20h ; ' '
0x1800649d4  jz      short loc_1800649F1
0x1800649d6  sbb     ebx, ebx
0x1800649d8  mov     r9d, 5F9h
0x1800649de  and     ebx, 0FFFFFE1Dh
0x1800649e4  add     ebx, 0C0000206h
0x1800649ea  mov     ecx, ebx
0x1800649ec  jmp     loc_180064929
0x1800649f1  cmp     r15d, edx
0x1800649f4  jz      short loc_180064A0B
0x1800649f6  mov     ebx, 0C0000206h
0x1800649fb  mov     r9d, 600h
0x180064a01  mov     ecx, 0C0000206h
0x180064a06  jmp     loc_180064929
0x180064a0b  sub     ecx, r8d
0x180064a0e  jz      short loc_180064A36
0x180064a10  cmp     ecx, 1
0x180064a13  jz      short loc_180064A1D
0x180064a15  mov     r9d, 613h
0x180064a1b  jmp     short loc_1800649A4
0x180064a1d  mov     rcx, [r10+20h]
0x180064a21  mov     r8, r15
0x180064a24  mov     r9, r14
0x180064a27  mov     [rsp+78h+var_58], rsi
0x180064a2c  mov     rdx, rbp
0x180064a2f  call    SymCryptCompositeMlKemDecapsulate
0x180064a34  jmp     short loc_180064A4D
0x180064a36  mov     rcx, [r10+20h]
0x180064a3a  mov     r8, r15
0x180064a3d  mov     r9, r14
0x180064a40  mov     [rsp+78h+var_58], rsi
0x180064a45  mov     rdx, rbp
0x180064a48  call    SymCryptMlKemDecapsulate
0x180064a4d  test    eax, eax
0x180064a4f  jz      short loc_180064A65
0x180064a51  mov     ecx, eax
0x180064a53  call    SymcryptErrorCodeToNtStatus
0x180064a58  mov     ebx, eax
0x180064a5a  mov     r9d, 61Bh
0x180064a60  jmp     loc_18006497F
0x180064a65  mov     [rdi], esi
0x180064a67  mov     eax, ebx
0x180064a69  add     rsp, 48h
0x180064a6d  pop     r15
0x180064a6f  pop     r14
0x180064a71  pop     rdi
0x180064a72  pop     rsi
0x180064a73  pop     rbp
0x180064a74  pop     rbx
0x180064a75  retn
```
