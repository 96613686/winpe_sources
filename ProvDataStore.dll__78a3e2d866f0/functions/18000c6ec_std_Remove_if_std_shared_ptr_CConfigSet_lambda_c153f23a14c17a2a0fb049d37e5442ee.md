# std::_Remove_if_std::shared_ptr_CConfigSet_____lambda_c153f23a14c17a2a0fb049d37e5442ee___

- ea: `0x18000c6ec`
- end: `0x18000c7de`
- name: `std::_Remove_if_std::shared_ptr_CConfigSet_____lambda_c153f23a14c17a2a0fb049d37e5442ee___`
- size: `242`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000ca0c`

## callees

- `0x180007d68`
- `0x180009068`
- `0x18000c6ec`
- `0x180012010`

## pseudocode

```c
_QWORD *__fastcall std::_Remove_if_std::shared_ptr_CConfigSet_____lambda_c153f23a14c17a2a0fb049d37e5442ee___(
        _QWORD *a1,
        __int64 *a2,
        __int64 a3)
{
  _QWORD *v5; // rsi
  __int64 *v6; // rbx
  bool *v7; // r15
  __int64 v8; // rcx
  int v9; // edi
  bool v10; // al
  bool v11; // bp
  volatile signed __int32 *v12; // rdi
  _QWORD *v13; // rcx
  __int64 v15; // [rsp+20h] [rbp-48h] BYREF
  volatile signed __int32 *v16; // [rsp+28h] [rbp-40h]

  v5 = a1;
  v6 = a1 + 2;
  if ( a1 + 2 != a2 )
  {
    v7 = *(bool **)a3;
    do
    {
      std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(&v15, v6);
      v8 = v15;
      v9 = *(_DWORD *)(v15 + 104) & 0x20;
      v10 = *v7 || v9;
      *v7 = v10;
      v11 = *(_DWORD *)(v8 + 112) < 3u
         || ((*(__int64 (__fastcall **)(_QWORD))(***(_QWORD ***)(a3 + 8) + 32LL))(**(_QWORD **)(a3 + 8)) & 0x20) != 0
         && !v9;
      v12 = v16;
      if ( v16 )
      {
        if ( _InterlockedExchangeAdd(v16 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v12)(v12);
          if ( _InterlockedExchangeAdd(v12 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v12 + 8LL))(v12);
        }
      }
      if ( !v11 )
      {
        v13 = v5;
        v5 += 2;
        std::shared_ptr<CConfigSet>::operator=(v13, v6);
      }
      v6 += 2;
    }
    while ( v6 != a2 );
  }
  return v5;
}

```

## disassembly

```asm
0x18000c6ec  push    rbx
0x18000c6ee  push    rbp
0x18000c6ef  push    rsi
0x18000c6f0  push    rdi
0x18000c6f1  push    r12
0x18000c6f3  push    r14
0x18000c6f5  push    r15
0x18000c6f7  sub     rsp, 30h
0x18000c6fb  mov     r12, r8
0x18000c6fe  mov     r14, rdx
0x18000c701  mov     rsi, rcx
0x18000c704  lea     rbx, [rcx+10h]
0x18000c708  cmp     rbx, rdx
0x18000c70b  jz      loc_18000C7CC
0x18000c711  mov     r15, [r8]
0x18000c714  mov     rdx, rbx
0x18000c717  lea     rcx, [rsp+68h+var_48]
0x18000c71c  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000c721  mov     rcx, [rsp+68h+var_48]
0x18000c726  mov     edi, [rcx+68h]
0x18000c729  and     edi, 20h
0x18000c72c  cmp     byte ptr [r15], 0
0x18000c730  jnz     short loc_18000C73A
0x18000c732  test    edi, edi
0x18000c734  jnz     short loc_18000C73A
0x18000c736  xor     al, al
0x18000c738  jmp     short loc_18000C73C
0x18000c73a  mov     al, 1
0x18000c73c  mov     [r15], al
0x18000c73f  cmp     dword ptr [rcx+70h], 3
0x18000c743  jb      short loc_18000C766
0x18000c745  mov     rax, [r12+8]
0x18000c74a  mov     rcx, [rax]
0x18000c74d  mov     rax, [rcx]
0x18000c750  mov     rax, [rax+20h]
0x18000c754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c759  test    al, 20h
0x18000c75b  jz      short loc_18000C761
0x18000c75d  test    edi, edi
0x18000c75f  jz      short loc_18000C766
0x18000c761  xor     bpl, bpl
0x18000c764  jmp     short loc_18000C769
0x18000c766  mov     bpl, 1
0x18000c769  mov     rdi, [rsp+68h+var_40]
0x18000c76e  test    rdi, rdi
0x18000c771  jz      short loc_18000C7AB
0x18000c773  or      eax, 0FFFFFFFFh
0x18000c776  lock xadd [rdi+8], eax
0x18000c77b  cmp     eax, 1
0x18000c77e  jnz     short loc_18000C7AB
0x18000c780  mov     rax, [rdi]
0x18000c783  mov     rcx, rdi
0x18000c786  mov     rax, [rax]
0x18000c789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c78e  or      eax, 0FFFFFFFFh
0x18000c791  lock xadd [rdi+0Ch], eax
0x18000c796  cmp     eax, 1
0x18000c799  jnz     short loc_18000C7AB
0x18000c79b  mov     rax, [rdi]
0x18000c79e  mov     rcx, rdi
0x18000c7a1  mov     rax, [rax+8]
0x18000c7a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c7aa  nop
0x18000c7ab  test    bpl, bpl
0x18000c7ae  jnz     short loc_18000C7BF
0x18000c7b0  mov     rcx, rsi
0x18000c7b3  add     rsi, 10h
0x18000c7b7  mov     rdx, rbx
0x18000c7ba  call    ??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)
0x18000c7bf  add     rbx, 10h
0x18000c7c3  cmp     rbx, r14
0x18000c7c6  jnz     loc_18000C714
0x18000c7cc  mov     rax, rsi
0x18000c7cf  add     rsp, 30h
0x18000c7d3  pop     r15
0x18000c7d5  pop     r14
0x18000c7d7  pop     r12
0x18000c7d9  pop     rdi
0x18000c7da  pop     rsi
0x18000c7db  pop     rbp
0x18000c7dc  pop     rbx
0x18000c7dd  retn
```
