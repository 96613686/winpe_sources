# CMtfPredictionCandidate::SetNextPath(IMtfLatticePath *)

- ea: `0x180029e80`
- end: `0x180029f2f`
- name: `?SetNextPath@CMtfPredictionCandidate@@UEAAJPEAUIMtfLatticePath@@@Z`
- size: `175`
- prototype: `__int64 __fastcall(CMtfPredictionCandidate *__hidden this, struct IMtfLatticePath *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180029e80`
- `0x18002a8a0`
- `0x18002f010`

## pseudocode

```c
__int64 __fastcall CMtfPredictionCandidate::SetNextPath(CMtfPredictionCandidate *this, struct IMtfLatticePath *a2)
{
  char *v3; // rbx
  __int64 v4; // r8
  unsigned __int64 v5; // rax
  __int64 v6; // rcx
  __int64 result; // rax
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+50h] [rbp+18h] BYREF

  try
  {
    v3 = (char *)this + 16;
    v4 = *((_QWORD *)this + 3);
    v5 = (v4 - *((_QWORD *)this + 2)) >> 3;
    if ( v5 < 2 )
    {
      v8 = 0;
      std::vector<MtfLatticeImpl::MtfLatticeFrameImpl *>::_Insert_n((char *)this + 16, &v9, v4, 2 - v5, &v8);
    }
    v6 = *(_QWORD *)(*(_QWORD *)v3 + 8LL);
    if ( v6 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
      *(_QWORD *)(*(_QWORD *)v3 + 8LL) = 0;
    }
    if ( a2
      && (**(int (__fastcall ***)(struct IMtfLatticePath *, GUID *, __int64))a2)(
           a2,
           &GUID_5f445657_746b_468a_9ebb_ae80a72c4f7a,
           *(_QWORD *)v3 + 8LL) < 0 )
    {
      result = 2147500037LL;
    }
    else
    {
      result = 0;
    }
  }
  catch ( ... )
  {
    return 2147500037LL;
  }
  return result;
}

```

## disassembly

```asm
0x180029e80  mov     r11, rsp
0x180029e83  mov     [r11+10h], rbx
0x180029e87  push    rdi
0x180029e88  sub     rsp, 30h
0x180029e8c  mov     rdi, rdx
0x180029e8f  lea     rbx, [rcx+10h]
0x180029e93  mov     r8, [rbx+8]
0x180029e97  mov     rax, r8
0x180029e9a  sub     rax, [rbx]
0x180029e9d  sar     rax, 3
0x180029ea1  mov     r9d, 2
0x180029ea7  cmp     rax, r9
0x180029eaa  jnb     short loc_180029ECB
0x180029eac  mov     qword ptr [r11+8], 0
0x180029eb4  sub     r9, rax
0x180029eb7  lea     rax, [r11+8]
0x180029ebb  mov     [r11-18h], rax
0x180029ebf  lea     rdx, [r11+18h]
0x180029ec3  mov     rcx, rbx
0x180029ec6  call    ?_Insert_n@?$vector@PEAVMtfLatticeFrameImpl@MtfLatticeImpl@@V?$allocator@PEAVMtfLatticeFrameImpl@MtfLatticeImpl@@@std@@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@PEAVMtfLatticeFrameImpl@MtfLatticeImpl@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@PEAVMtfLatticeFrameImpl@MtfLatticeImpl@@@std@@@std@@@2@_KAEBQEAVMtfLatticeFrameImpl@MtfLatticeImpl@@@Z; std::vector<MtfLatticeImpl::MtfLatticeFrameImpl *>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<MtfLatticeImpl::MtfLatticeFrameImpl *>>>,unsigned __int64,MtfLatticeImpl::MtfLatticeFrameImpl * const &)
0x180029ecb  mov     rax, [rbx]
0x180029ece  mov     rcx, [rax+8]
0x180029ed2  test    rcx, rcx
0x180029ed5  jz      short loc_180029EEE
0x180029ed7  mov     rax, [rcx]
0x180029eda  mov     rax, [rax+10h]
0x180029ede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029ee3  mov     rax, [rbx]
0x180029ee6  mov     qword ptr [rax+8], 0
0x180029eee  test    rdi, rdi
0x180029ef1  jz      short loc_180029F1A
0x180029ef3  mov     rax, [rdi]
0x180029ef6  mov     r8, [rbx]
0x180029ef9  add     r8, 8
0x180029efd  lea     rdx, _GUID_5f445657_746b_468a_9ebb_ae80a72c4f7a
0x180029f04  mov     rcx, rdi
0x180029f07  mov     rax, [rax]
0x180029f0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029f0f  test    eax, eax
0x180029f11  jns     short loc_180029F1A
0x180029f13  mov     eax, 80004005h
0x180029f18  jmp     short loc_180029F23
0x180029f1a  xor     eax, eax
0x180029f1c  jmp     short loc_180029F23
0x180029f1e  mov     eax, 80004005h
0x180029f23  mov     rbx, [rsp+38h+arg_8]
0x180029f28  add     rsp, 30h
0x180029f2c  pop     rdi
0x180029f2d  retn
```
