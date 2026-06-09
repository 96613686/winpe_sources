# std::remove_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_std::shared_ptr_CConfigSet_________lambda_1b9c3a85c63527149e38144a6bb3f611___

- ea: `0x18000c8dc`
- end: `0x18000ca04`
- name: `std::remove_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_std::shared_ptr_CConfigSet_________lambda_1b9c3a85c63527149e38144a6bb3f611___`
- size: `296`
- prototype: `__int64 **__fastcall(__int64 **, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000d424`

## callees

- `0x180007d68`
- `0x180009068`
- `0x18000c8dc`
- `0x180012010`

## pseudocode

```c
__int64 **__fastcall std::remove_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_std::shared_ptr_CConfigSet_________lambda_1b9c3a85c63527149e38144a6bb3f611___(
        __int64 **a1,
        __int64 *a2,
        __int64 *a3)
{
  __int64 *v4; // rdi
  int v6; // ebp
  volatile signed __int32 *v7; // rsi
  __int64 *i; // rsi
  bool v9; // bp
  volatile signed __int32 *v10; // r15
  __int64 *v11; // rcx
  __int64 **result; // rax
  __int64 v13; // [rsp+20h] [rbp-48h] BYREF
  volatile signed __int32 *v14; // [rsp+28h] [rbp-40h]

  v4 = a2;
  if ( a2 != a3 )
  {
    do
    {
      std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(&v13, v4);
      v6 = *(_DWORD *)(v13 + 76);
      v7 = v14;
      if ( v14 )
      {
        if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
          if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
        }
      }
      if ( v6 )
        break;
      v4 += 2;
    }
    while ( v4 != a3 );
    if ( v4 != a3 )
    {
      for ( i = v4 + 2; i != a3; i += 2 )
      {
        std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(&v13, i);
        v9 = *(_DWORD *)(v13 + 76) != 0;
        v10 = v14;
        if ( v14 )
        {
          if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
            if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
          }
        }
        if ( !v9 )
        {
          v11 = v4;
          v4 += 2;
          std::shared_ptr<CConfigSet>::operator=(v11, i);
        }
      }
    }
  }
  result = a1;
  *a1 = v4;
  return result;
}

```

## disassembly

```asm
0x18000c8dc  push    rbx
0x18000c8de  push    rbp
0x18000c8df  push    rsi
0x18000c8e0  push    rdi
0x18000c8e1  push    r12
0x18000c8e3  push    r14
0x18000c8e5  push    r15
0x18000c8e7  sub     rsp, 30h
0x18000c8eb  mov     rbx, r8
0x18000c8ee  mov     rdi, rdx
0x18000c8f1  mov     r14, rcx
0x18000c8f4  cmp     rdx, r8
0x18000c8f7  jz      loc_18000C9EF
0x18000c8fd  or      r12d, 0FFFFFFFFh
0x18000c901  mov     rdx, rdi
0x18000c904  lea     rcx, [rsp+68h+var_48]
0x18000c909  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000c90e  mov     rax, [rsp+68h+var_48]
0x18000c913  mov     ebp, [rax+4Ch]
0x18000c916  mov     rsi, [rsp+68h+var_40]
0x18000c91b  test    rsi, rsi
0x18000c91e  jz      short loc_18000C958
0x18000c920  mov     eax, r12d
0x18000c923  lock xadd [rsi+8], eax
0x18000c928  add     eax, r12d
0x18000c92b  jnz     short loc_18000C958
0x18000c92d  mov     rax, [rsi]
0x18000c930  mov     rcx, rsi
0x18000c933  mov     rax, [rax]
0x18000c936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c93b  mov     eax, r12d
0x18000c93e  lock xadd [rsi+0Ch], eax
0x18000c943  add     eax, r12d
0x18000c946  jnz     short loc_18000C958
0x18000c948  mov     rax, [rsi]
0x18000c94b  mov     rcx, rsi
0x18000c94e  mov     rax, [rax+8]
0x18000c952  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c957  nop
0x18000c958  test    ebp, ebp
0x18000c95a  jnz     short loc_18000C965
0x18000c95c  add     rdi, 10h
0x18000c960  cmp     rdi, rbx
0x18000c963  jnz     short loc_18000C901
0x18000c965  cmp     rdi, rbx
0x18000c968  jz      loc_18000C9EF
0x18000c96e  lea     rsi, [rdi+10h]
0x18000c972  jmp     short loc_18000C9EA
0x18000c974  mov     rdx, rsi
0x18000c977  lea     rcx, [rsp+68h+var_48]
0x18000c97c  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000c981  mov     rax, [rsp+68h+var_48]
0x18000c986  cmp     dword ptr [rax+4Ch], 0
0x18000c98a  setnz   bpl
0x18000c98e  mov     r15, [rsp+68h+var_40]
0x18000c993  test    r15, r15
0x18000c996  jz      short loc_18000C9D2
0x18000c998  mov     eax, r12d
0x18000c99b  lock xadd [r15+8], eax
0x18000c9a1  add     eax, r12d
0x18000c9a4  jnz     short loc_18000C9D2
0x18000c9a6  mov     rax, [r15]
0x18000c9a9  mov     rcx, r15
0x18000c9ac  mov     rax, [rax]
0x18000c9af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9b4  mov     eax, r12d
0x18000c9b7  lock xadd [r15+0Ch], eax
0x18000c9bd  add     eax, r12d
0x18000c9c0  jnz     short loc_18000C9D2
0x18000c9c2  mov     rax, [r15]
0x18000c9c5  mov     rcx, r15
0x18000c9c8  mov     rax, [rax+8]
0x18000c9cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9d1  nop
0x18000c9d2  test    bpl, bpl
0x18000c9d5  jnz     short loc_18000C9E6
0x18000c9d7  mov     rcx, rdi
0x18000c9da  add     rdi, 10h
0x18000c9de  mov     rdx, rsi
0x18000c9e1  call    ??4?$shared_ptr@VCConfigSet@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<CConfigSet>::operator=(std::shared_ptr<CConfigSet> &&)
0x18000c9e6  add     rsi, 10h
0x18000c9ea  cmp     rsi, rbx
0x18000c9ed  jnz     short loc_18000C974
0x18000c9ef  mov     rax, r14
0x18000c9f2  mov     [r14], rdi
0x18000c9f5  add     rsp, 30h
0x18000c9f9  pop     r15
0x18000c9fb  pop     r14
0x18000c9fd  pop     r12
0x18000c9ff  pop     rdi
0x18000ca00  pop     rsi
0x18000ca01  pop     rbp
0x18000ca02  pop     rbx
0x18000ca03  retn
```
