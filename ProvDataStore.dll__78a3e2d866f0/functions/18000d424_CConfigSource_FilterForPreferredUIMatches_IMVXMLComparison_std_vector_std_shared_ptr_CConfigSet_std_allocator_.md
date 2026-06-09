# CConfigSource::FilterForPreferredUIMatches(IMVXMLComparison *,std::vector<std::shared_ptr<CConfigSet>,std::allocator<std::shared_ptr<CConfigSet>>> &,bool *)

- ea: `0x18000d424`
- end: `0x18000d608`
- name: `?FilterForPreferredUIMatches@CConfigSource@@CAJPEAVIMVXMLComparison@@AEAV?$vector@V?$shared_ptr@VCConfigSet@@@std@@V?$allocator@V?$shared_ptr@VCConfigSet@@@std@@@2@@std@@PEA_N@Z`
- size: `484`
- prototype: `__int64 __fastcall(__int64, __int64 *, char *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e184`

## callees

- `0x180007d68`
- `0x18000c8dc`
- `0x18000ca0c`
- `0x18000d424`
- `0x18000f704`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CConfigSource::FilterForPreferredUIMatches(__int64 a1, __int64 *a2, char *a3)
{
  int v5; // eax
  __int64 v6; // r9
  __int64 *v7; // r14
  __int64 *v8; // rsi
  __int64 **v9; // rax
  unsigned int v10; // eax
  __int64 *v11; // r15
  __int64 *v12; // r14
  __int64 **v13; // rax
  char v14; // bl
  bool v15; // r12
  volatile signed __int32 *v16; // rsi
  int v17; // r15d
  volatile signed __int32 *v18; // rbx
  __int64 *v20[2]; // [rsp+20h] [rbp-20h] BYREF
  char *v21; // [rsp+30h] [rbp-10h] BYREF
  volatile signed __int32 *v22; // [rsp+38h] [rbp-8h]
  __int64 v23; // [rsp+70h] [rbp+30h] BYREF
  char v24; // [rsp+88h] [rbp+48h] BYREF

  v23 = a1;
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 64LL))(a1);
  v7 = (__int64 *)a2[1];
  v8 = (__int64 *)*a2;
  if ( !v5 )
  {
    while ( v8 != v7 )
    {
      std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(&v21, v8);
      v17 = *((_DWORD *)v21 + 19);
      v18 = v22;
      if ( v22 )
      {
        if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v18)(v18);
          if ( _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
        }
      }
      if ( !v17 )
        goto LABEL_5;
      v8 += 2;
    }
    goto LABEL_26;
  }
  LOBYTE(v6) = 0;
  v9 = (__int64 **)std::remove_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_std::shared_ptr_CConfigSet_________lambda_1b9c3a85c63527149e38144a6bb3f611___(
                     &v24,
                     *a2,
                     a2[1],
                     v6);
  std::vector<std::shared_ptr<CConfigSet>>::erase(a2, v20, *v9, v7);
  v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 72LL))(v23);
  v11 = (__int64 *)a2[1];
  v12 = (__int64 *)*a2;
  if ( v10 > 2 )
  {
    v24 = 0;
    v21 = &v24;
    v22 = (volatile signed __int32 *)&v23;
    v13 = (__int64 **)std::remove_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_std::shared_ptr_CConfigSet_________lambda_c153f23a14c17a2a0fb049d37e5442ee___(
                        v20,
                        v12,
                        v11,
                        &v21);
    std::vector<std::shared_ptr<CConfigSet>>::erase(a2, (__int64 **)&v21, *v13, v11);
    if ( v24 && ((*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v23 + 32LL))(v23) & 0x20) == 0 )
    {
LABEL_5:
      v14 = 0;
      goto LABEL_27;
    }
LABEL_26:
    v14 = 1;
    goto LABEL_27;
  }
  v14 = 1;
  while ( v12 != v11 )
  {
    std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(&v21, v12);
    v15 = !*((_DWORD *)v21 + 19) && *((_DWORD *)v21 + 28) > 2u;
    v16 = v22;
    if ( v22 )
    {
      if ( _InterlockedExchangeAdd(v22 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
        if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
      }
    }
    if ( v15 )
      goto LABEL_5;
    v12 += 2;
  }
LABEL_27:
  *a3 = v14;
  return 0;
}

```

## disassembly

```asm
0x18000d424  mov     [rsp-28h+arg_8], rbx
0x18000d429  mov     [rsp-28h+arg_10], rsi
0x18000d42e  mov     [rsp-28h+arg_0], rcx
0x18000d433  push    rbp
0x18000d434  push    r12
0x18000d436  push    r13
0x18000d438  push    r14
0x18000d43a  push    r15
0x18000d43c  mov     rbp, rsp
0x18000d43f  sub     rsp, 40h
0x18000d443  mov     r13, r8
0x18000d446  mov     rbx, rdx
0x18000d449  mov     rax, [rcx]
0x18000d44c  mov     rax, [rax+40h]
0x18000d450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d455  mov     r14, [rbx+8]
0x18000d459  mov     rsi, [rbx]
0x18000d45c  test    eax, eax
0x18000d45e  jz      loc_18000D5E1
0x18000d464  xor     r9b, r9b
0x18000d467  mov     r8, r14
0x18000d46a  mov     rdx, rsi
0x18000d46d  lea     rcx, [rbp+arg_18]
0x18000d471  call    std__remove_if_std___Vector_iterator_std___Vector_val_std___Simple_types_std__shared_ptr_CConfigSet_________lambda_1b9c3a85c63527149e38144a6bb3f611___
0x18000d476  mov     r9, r14
0x18000d479  mov     r8, [rax]
0x18000d47c  lea     rdx, [rbp+var_20]
0x18000d480  mov     rcx, rbx
0x18000d483  call    ?erase@?$vector@V?$shared_ptr@VCConfigSet@@@std@@V?$allocator@V?$shared_ptr@VCConfigSet@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@VCConfigSet@@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@VCConfigSet@@@std@@@std@@@std@@@2@0@Z; std::vector<std::shared_ptr<CConfigSet>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::shared_ptr<CConfigSet>>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::shared_ptr<CConfigSet>>>>)
0x18000d488  mov     rcx, [rbp+arg_0]
0x18000d48c  mov     rax, [rcx]
0x18000d48f  mov     rax, [rax+48h]
0x18000d493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d498  mov     r15, [rbx+8]
0x18000d49c  mov     r14, [rbx]
0x18000d49f  cmp     eax, 2
0x18000d4a2  jbe     short loc_18000D506
0x18000d4a4  mov     [rbp+arg_18], 0
0x18000d4a8  lea     rax, [rbp+arg_18]
0x18000d4ac  mov     [rbp+var_10], rax
0x18000d4b0  lea     rax, [rbp+arg_0]
0x18000d4b4  mov     [rbp+var_8], rax
0x18000d4b8  lea     r9, [rbp+var_10]
0x18000d4bc  mov     r8, r15
0x18000d4bf  mov     rdx, r14
0x18000d4c2  lea     rcx, [rbp+var_20]
0x18000d4c6  call    std__remove_if_std___Vector_iterator_std___Vector_val_std___Simple_types_std__shared_ptr_CConfigSet_________lambda_c153f23a14c17a2a0fb049d37e5442ee___
0x18000d4cb  mov     r9, r15
0x18000d4ce  mov     r8, [rax]
0x18000d4d1  lea     rdx, [rbp+var_10]
0x18000d4d5  mov     rcx, rbx
0x18000d4d8  call    ?erase@?$vector@V?$shared_ptr@VCConfigSet@@@std@@V?$allocator@V?$shared_ptr@VCConfigSet@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@VCConfigSet@@@std@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@VCConfigSet@@@std@@@std@@@std@@@2@0@Z; std::vector<std::shared_ptr<CConfigSet>>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::shared_ptr<CConfigSet>>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<std::shared_ptr<CConfigSet>>>>)
0x18000d4dd  cmp     [rbp+arg_18], 0
0x18000d4e1  jz      loc_18000D5E6
0x18000d4e7  mov     rcx, [rbp+arg_0]
0x18000d4eb  mov     rax, [rcx]
0x18000d4ee  mov     rax, [rax+20h]
0x18000d4f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4f7  test    al, 20h
0x18000d4f9  jnz     loc_18000D5E6
0x18000d4ff  xor     bl, bl
0x18000d501  jmp     loc_18000D5E8
0x18000d506  mov     bl, 1
0x18000d508  jmp     short loc_18000D578
0x18000d50a  mov     rdx, r14
0x18000d50d  lea     rcx, [rbp+var_10]
0x18000d511  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000d516  mov     rax, [rbp+var_10]
0x18000d51a  cmp     dword ptr [rax+4Ch], 0
0x18000d51e  jnz     short loc_18000D52B
0x18000d520  cmp     dword ptr [rax+70h], 2
0x18000d524  jbe     short loc_18000D52B
0x18000d526  mov     r12b, bl
0x18000d529  jmp     short loc_18000D52E
0x18000d52b  xor     r12b, r12b
0x18000d52e  mov     rsi, [rbp+var_8]
0x18000d532  test    rsi, rsi
0x18000d535  jz      short loc_18000D56F
0x18000d537  or      eax, 0FFFFFFFFh
0x18000d53a  lock xadd [rsi+8], eax
0x18000d53f  cmp     eax, 1
0x18000d542  jnz     short loc_18000D56F
0x18000d544  mov     rax, [rsi]
0x18000d547  mov     rcx, rsi
0x18000d54a  mov     rax, [rax]
0x18000d54d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d552  or      eax, 0FFFFFFFFh
0x18000d555  lock xadd [rsi+0Ch], eax
0x18000d55a  cmp     eax, 1
0x18000d55d  jnz     short loc_18000D56F
0x18000d55f  mov     rax, [rsi]
0x18000d562  mov     rcx, rsi
0x18000d565  mov     rax, [rax+8]
0x18000d569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d56e  nop
0x18000d56f  test    r12b, r12b
0x18000d572  jnz     short loc_18000D4FF
0x18000d574  add     r14, 10h
0x18000d578  cmp     r14, r15
0x18000d57b  jnz     short loc_18000D50A
0x18000d57d  jmp     short loc_18000D5E8
0x18000d57f  mov     rdx, rsi
0x18000d582  lea     rcx, [rbp+var_10]
0x18000d586  call    ??$?0VCConfigSource@@@?$shared_ptr@$$CBVCConfigSource@@@std@@QEAA@AEBV?$shared_ptr@VCConfigSource@@@1@PEAPEAX@Z; std::shared_ptr<CConfigSource const>::shared_ptr<CConfigSource const>(std::shared_ptr<CConfigSource> const &,void * *)
0x18000d58b  mov     rax, [rbp+var_10]
0x18000d58f  mov     r15d, [rax+4Ch]
0x18000d593  mov     rbx, [rbp+var_8]
0x18000d597  test    rbx, rbx
0x18000d59a  jz      short loc_18000D5D4
0x18000d59c  or      eax, 0FFFFFFFFh
0x18000d59f  lock xadd [rbx+8], eax
0x18000d5a4  cmp     eax, 1
0x18000d5a7  jnz     short loc_18000D5D4
0x18000d5a9  mov     rax, [rbx]
0x18000d5ac  mov     rcx, rbx
0x18000d5af  mov     rax, [rax]
0x18000d5b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5b7  or      eax, 0FFFFFFFFh
0x18000d5ba  lock xadd [rbx+0Ch], eax
0x18000d5bf  cmp     eax, 1
0x18000d5c2  jnz     short loc_18000D5D4
0x18000d5c4  mov     rax, [rbx]
0x18000d5c7  mov     rcx, rbx
0x18000d5ca  mov     rax, [rax+8]
0x18000d5ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5d3  nop
0x18000d5d4  test    r15d, r15d
0x18000d5d7  jz      loc_18000D4FF
0x18000d5dd  add     rsi, 10h
0x18000d5e1  cmp     rsi, r14
0x18000d5e4  jnz     short loc_18000D57F
0x18000d5e6  mov     bl, 1
0x18000d5e8  mov     [r13+0], bl
0x18000d5ec  xor     eax, eax
0x18000d5ee  lea     r11, [rsp+40h+var_s0]
0x18000d5f3  mov     rbx, [r11+38h]
0x18000d5f7  mov     rsi, [r11+40h]
0x18000d5fb  mov     rsp, r11
0x18000d5fe  pop     r15
0x18000d600  pop     r14
0x18000d602  pop     r13
0x18000d604  pop     r12
0x18000d606  pop     rbp
0x18000d607  retn
```
