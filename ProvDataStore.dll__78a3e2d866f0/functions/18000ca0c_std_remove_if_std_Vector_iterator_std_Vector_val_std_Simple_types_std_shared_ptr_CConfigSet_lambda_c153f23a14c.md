# std::remove_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_std::shared_ptr_CConfigSet_________lambda_c153f23a14c17a2a0fb049d37e5442ee___

- ea: `0x18000ca0c`
- end: `0x18000cb1b`
- name: `std::remove_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_std::shared_ptr_CConfigSet_________lambda_c153f23a14c17a2a0fb049d37e5442ee___`
- size: `271`
- prototype: `__int64 **__fastcall(__int64 **, __int64 *, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000d424`

## callees

- `0x180007d68`
- `0x18000c6ec`
- `0x18000ca0c`
- `0x180012010`

## pseudocode

```c
__int64 **__fastcall std::remove_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_std::shared_ptr_CConfigSet_________lambda_c153f23a14c17a2a0fb049d37e5442ee___(
        __int64 **a1,
        __int64 *a2,
        __int64 *a3,
        __int64 a4)
{
  __int64 *v6; // rdi
  bool *v8; // r12
  _QWORD *v9; // r13
  __int64 v10; // rcx
  int v11; // esi
  bool v12; // al
  bool v13; // bp
  volatile signed __int32 *v14; // rsi
  _OWORD v16[5]; // [rsp+20h] [rbp-58h] BYREF

  v6 = a2;
  v8 = *(bool **)a4;
  v9 = *(_QWORD **)(a4 + 8);
  if ( a2 == a3 )
    goto LABEL_19;
  do
  {
    std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(v16, v6);
    v10 = *(_QWORD *)&v16[0];
    v11 = *(_DWORD *)(*(_QWORD *)&v16[0] + 104LL) & 0x20;
    v12 = *v8 || v11;
    *v8 = v12;
    v13 = *(_DWORD *)(v10 + 112) < 3u
       || ((*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v9 + 32LL))(*v9) & 0x20) != 0 && !v11;
    v14 = (volatile signed __int32 *)*((_QWORD *)&v16[0] + 1);
    if ( *((_QWORD *)&v16[0] + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v16[0] + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
        if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
      }
    }
    if ( v13 )
      break;
    v6 += 2;
  }
  while ( v6 != a3 );
  if ( v6 == a3 )
  {
LABEL_19:
    *a1 = v6;
  }
  else
  {
    v16[0] = *(_OWORD *)a4;
    *a1 = std::_Remove_if_std::shared_ptr_CConfigSet_____lambda_c153f23a14c17a2a0fb049d37e5442ee___(
            v6,
            a3,
            (__int64)v16);
  }
  return a1;
}

```

## disassembly

```asm
0x18000ca0c  push    rbx
0x18000ca0e  push    rbp
0x18000ca0f  push    rsi
0x18000ca10  push    rdi
0x18000ca11  push    r12
0x18000ca13  push    r13
0x18000ca15  push    r14
0x18000ca17  push    r15
0x18000ca19  sub     rsp, 38h
0x18000ca1d  mov     r15, r9
0x18000ca20  mov     rbx, r8
0x18000ca23  mov     rdi, rdx
0x18000ca26  mov     r14, rcx
0x18000ca29  mov     r12, [r9]
0x18000ca2c  mov     r13, [r9+8]
0x18000ca30  cmp     rdx, r8
0x18000ca33  jz      loc_18000CB04
0x18000ca39  mov     rdx, rdi
0x18000ca3c  lea     rcx, [rsp+78h+var_58]
0x18000ca41  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000ca46  mov     rcx, qword ptr [rsp+78h+var_58]
0x18000ca4b  mov     esi, [rcx+68h]
0x18000ca4e  and     esi, 20h
0x18000ca51  cmp     byte ptr [r12], 0
0x18000ca56  jnz     short loc_18000CA60
0x18000ca58  test    esi, esi
0x18000ca5a  jnz     short loc_18000CA60
0x18000ca5c  xor     al, al
0x18000ca5e  jmp     short loc_18000CA62
0x18000ca60  mov     al, 1
0x18000ca62  mov     [r12], al
0x18000ca66  cmp     dword ptr [rcx+70h], 3
0x18000ca6a  jb      short loc_18000CA89
0x18000ca6c  mov     rcx, [r13+0]
0x18000ca70  mov     rax, [rcx]
0x18000ca73  mov     rax, [rax+20h]
0x18000ca77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca7c  test    al, 20h
0x18000ca7e  jz      short loc_18000CA84
0x18000ca80  test    esi, esi
0x18000ca82  jz      short loc_18000CA89
0x18000ca84  xor     bpl, bpl
0x18000ca87  jmp     short loc_18000CA8C
0x18000ca89  mov     bpl, 1
0x18000ca8c  mov     rsi, qword ptr [rsp+78h+var_58+8]
0x18000ca91  test    rsi, rsi
0x18000ca94  jz      short loc_18000CACE
0x18000ca96  or      eax, 0FFFFFFFFh
0x18000ca99  lock xadd [rsi+8], eax
0x18000ca9e  cmp     eax, 1
0x18000caa1  jnz     short loc_18000CACE
0x18000caa3  mov     rax, [rsi]
0x18000caa6  mov     rcx, rsi
0x18000caa9  mov     rax, [rax]
0x18000caac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cab1  or      eax, 0FFFFFFFFh
0x18000cab4  lock xadd [rsi+0Ch], eax
0x18000cab9  cmp     eax, 1
0x18000cabc  jnz     short loc_18000CACE
0x18000cabe  mov     rax, [rsi]
0x18000cac1  mov     rcx, rsi
0x18000cac4  mov     rax, [rax+8]
0x18000cac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cacd  nop
0x18000cace  test    bpl, bpl
0x18000cad1  jnz     short loc_18000CAE0
0x18000cad3  add     rdi, 10h
0x18000cad7  cmp     rdi, rbx
0x18000cada  jnz     loc_18000CA39
0x18000cae0  cmp     rdi, rbx
0x18000cae3  jz      short loc_18000CB04
0x18000cae5  movaps  xmm0, xmmword ptr [r15]
0x18000cae9  movdqa  [rsp+78h+var_58], xmm0
0x18000caef  lea     r8, [rsp+78h+var_58]
0x18000caf4  mov     rdx, rbx
0x18000caf7  mov     rcx, rdi
0x18000cafa  call    std___Remove_if_std__shared_ptr_CConfigSet_____lambda_c153f23a14c17a2a0fb049d37e5442ee___
0x18000caff  mov     [r14], rax
0x18000cb02  jmp     short loc_18000CB07
0x18000cb04  mov     [r14], rdi
0x18000cb07  mov     rax, r14
0x18000cb0a  add     rsp, 38h
0x18000cb0e  pop     r15
0x18000cb10  pop     r14
0x18000cb12  pop     r13
0x18000cb14  pop     r12
0x18000cb16  pop     rdi
0x18000cb17  pop     rsi
0x18000cb18  pop     rbp
0x18000cb19  pop     rbx
0x18000cb1a  retn
```
