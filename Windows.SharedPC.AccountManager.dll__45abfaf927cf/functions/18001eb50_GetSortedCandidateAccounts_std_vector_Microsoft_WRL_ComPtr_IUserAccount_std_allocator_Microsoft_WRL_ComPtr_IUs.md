# GetSortedCandidateAccounts(std::vector<Microsoft::WRL::ComPtr<IUserAccount>,std::allocator<Microsoft::WRL::ComPtr<IUserAccount>>> &)

- ea: `0x18001eb50`
- end: `0x18001ec4e`
- name: `?GetSortedCandidateAccounts@@YA?AV?$vector@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@std@@AEAV12@@Z`
- size: `254`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001eca0`
- `0x18001f490`
- `0x180020070`
- `0x1800218d0`

## callees

- `0x18000ccd4`
- `0x18000f454`
- `0x1800147a0`
- `0x1800147cc`
- `0x18001e924`
- `0x18001eb50`
- `0x180026010`

## string_xrefs

- `0x18001ec27`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\util.h`
- `0x18001ec3c`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\util.h`

## pseudocode

```c
_QWORD *__fastcall GetSortedCandidateAccounts(_QWORD *a1)
{
  __int64 v2; // rdx
  _QWORD *v3; // rdi
  _QWORD *v4; // rsi
  int v5; // eax
  int v6; // eax
  __int64 v7; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v10; // [rsp+58h] [rbp+10h] BYREF
  int v11; // [rsp+60h] [rbp+18h] BYREF

  std::vector<SessionUserInfo>::vector<SessionUserInfo>(a1);
  v3 = *(_QWORD **)v2;
  v4 = *(_QWORD **)(v2 + 8);
  while ( v3 != v4 )
  {
    v10 = 0;
    v5 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v3 + 40LL))(*v3, &v10);
    if ( v5 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0xF,
        (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\util.h",
        (const char *)(unsigned int)v5,
        1);
    if ( (unsigned int)(v10 - 2) <= 1 )
    {
      v11 = 0;
      v6 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v3 + 80LL))(*v3, &v11);
      if ( v6 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x15,
          (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\util.h",
          (const char *)(unsigned int)v6,
          1);
      if ( !v11 )
      {
        v7 = a1[1];
        if ( v7 == a1[2] )
          std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IUserAccount> const &>(
            a1,
            v7,
            v3);
        else
          std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::_Emplace_back_with_unused_capacity<Microsoft::WRL::ComPtr<IUserAccount> const &>(
            a1,
            v3);
      }
    }
    ++v3;
  }
  std::sort<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<Microsoft::WRL::ComPtr<IUserAccount>>>>,_lambda_13145fbecff4ab278b99ceeccaf2b550_>(
    *a1,
    a1[1]);
  return a1;
}

```

## disassembly

```asm
0x18001eb50  mov     [rsp+arg_0], rcx
0x18001eb55  push    rbx
0x18001eb56  push    rsi
0x18001eb57  push    rdi
0x18001eb58  sub     rsp, 30h
0x18001eb5c  mov     rbx, rcx
0x18001eb5f  mov     [rsp+48h+var_28], 0
0x18001eb67  call    ??0?$vector@USessionUserInfo@@V?$allocator@USessionUserInfo@@@std@@@std@@QEAA@XZ; std::vector<SessionUserInfo>::vector<SessionUserInfo>(void)
0x18001eb6c  mov     [rsp+48h+var_28], 1
0x18001eb74  mov     rdi, [rdx]
0x18001eb77  mov     rsi, [rdx+8]
0x18001eb7b  jmp     loc_18001EC04
0x18001eb80  mov     [rsp+48h+arg_8], 0
0x18001eb88  mov     rcx, [rdi]
0x18001eb8b  mov     rax, [rcx]
0x18001eb8e  lea     rdx, [rsp+48h+arg_8]
0x18001eb93  mov     rax, [rax+28h]
0x18001eb97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb9c  mov     rcx, [rsp+48h]; this
0x18001eba1  test    eax, eax
0x18001eba3  js      loc_18001EC39
0x18001eba9  mov     eax, [rsp+48h+arg_8]
0x18001ebad  add     eax, 0FFFFFFFEh
0x18001ebb0  cmp     eax, 1
0x18001ebb3  ja      short loc_18001EC00
0x18001ebb5  mov     [rsp+48h+arg_10], 0
0x18001ebbd  mov     rcx, [rdi]
0x18001ebc0  mov     rax, [rcx]
0x18001ebc3  lea     rdx, [rsp+48h+arg_10]
0x18001ebc8  mov     rax, [rax+50h]
0x18001ebcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebd1  mov     rcx, [rsp+48h]; this
0x18001ebd6  test    eax, eax
0x18001ebd8  js      short loc_18001EC24
0x18001ebda  cmp     [rsp+48h+arg_10], 0
0x18001ebdf  jnz     short loc_18001EC00
0x18001ebe1  mov     rdx, [rbx+8]
0x18001ebe5  mov     rcx, rbx
0x18001ebe8  cmp     rdx, [rbx+10h]
0x18001ebec  jz      short loc_18001EBF8
0x18001ebee  mov     rdx, rdi
0x18001ebf1  call    ??$_Emplace_back_with_unused_capacity@AEBV?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@?$vector@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@std@@AEAAAEAV?$ComPtr@UIUserAccount@@@WRL@Microsoft@@AEBV234@@Z; std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::_Emplace_back_with_unused_capacity<Microsoft::WRL::ComPtr<IUserAccount> const &>(Microsoft::WRL::ComPtr<IUserAccount> const &)
0x18001ebf6  jmp     short loc_18001EC00
0x18001ebf8  mov     r8, rdi
0x18001ebfb  call    ??$_Emplace_reallocate@AEBV?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@?$vector@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@std@@AEAAPEAV?$ComPtr@UIUserAccount@@@WRL@Microsoft@@QEAV234@AEBV234@@Z; std::vector<Microsoft::WRL::ComPtr<IUserAccount>>::_Emplace_reallocate<Microsoft::WRL::ComPtr<IUserAccount> const &>(Microsoft::WRL::ComPtr<IUserAccount> * const,Microsoft::WRL::ComPtr<IUserAccount> const &)
0x18001ec00  add     rdi, 8
0x18001ec04  cmp     rdi, rsi
0x18001ec07  jnz     loc_18001EB80
0x18001ec0d  mov     rdx, [rbx+8]
0x18001ec11  mov     rcx, [rbx]
0x18001ec14  call    ??$sort@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@std@@@std@@V_lambda_13145fbecff4ab278b99ceeccaf2b550_@@@std@@YAXV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@std@@@0@0V_lambda_13145fbecff4ab278b99ceeccaf2b550_@@@Z; std::sort<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<Microsoft::WRL::ComPtr<IUserAccount>>>>,_lambda_13145fbecff4ab278b99ceeccaf2b550_>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<Microsoft::WRL::ComPtr<IUserAccount>>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<Microsoft::WRL::ComPtr<IUserAccount>>>>,_lambda_13145fbecff4ab278b99ceeccaf2b550_)
0x18001ec19  mov     rax, rbx
0x18001ec1c  add     rsp, 30h
0x18001ec20  pop     rdi
0x18001ec21  pop     rsi
0x18001ec22  pop     rbx
0x18001ec23  retn
0x18001ec24  mov     r9d, eax; char *
0x18001ec27  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001ec2e  mov     edx, 15h; void *
0x18001ec33  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001ec39  mov     r9d, eax; char *
0x18001ec3c  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001ec43  mov     edx, 0Fh; void *
0x18001ec48  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
