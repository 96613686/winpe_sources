# GetDeletionCandidates(std::vector<Microsoft::WRL::ComPtr<IUserAccount>,std::allocator<Microsoft::WRL::ComPtr<IUserAccount>>> const &)

- ea: `0x18001d318`
- end: `0x18001d3d6`
- name: `?GetDeletionCandidates@@YA?AV?$vector@V?$com_ptr_t@UIUserAccount@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIUserAccount@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEBV?$vector@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIUserAccount@@@WRL@Microsoft@@@std@@@2@@Z`
- size: `190`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d480`

## callees

- `0x18000ccd4`
- `0x18000f454`
- `0x1800151cc`
- `0x180015490`
- `0x18001ccd4`
- `0x18001ccfc`
- `0x18001d318`
- `0x180026010`

## string_xrefs

- `0x18001d3c4`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\userrequestpolicyengine.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall GetDeletionCandidates(__int64 a1)
{
  __int64 v2; // rdx
  _QWORD *v3; // rdi
  _QWORD *v4; // rsi
  int v5; // eax
  __int64 v6; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v9; // [rsp+58h] [rbp+10h] BYREF
  char v10; // [rsp+60h] [rbp+18h] BYREF

  std::vector<SessionUserInfo>::vector<SessionUserInfo>(a1);
  v3 = *(_QWORD **)v2;
  v4 = *(_QWORD **)(v2 + 8);
  while ( v3 != v4 )
  {
    v9 = 0;
    v5 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*v3 + 80LL))(*v3, &v9);
    if ( v5 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x10,
        (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\userrequestpolicyengine.cpp",
        (const char *)(unsigned int)v5,
        1);
    if ( !v9 )
    {
      wil::com_ptr_t<Windows::System::Internal::IUserProfile,wil::err_exception_policy>::com_ptr_t<Windows::System::Internal::IUserProfile,wil::err_exception_policy>(
        &v10,
        *v3);
      v6 = *(_QWORD *)(a1 + 8);
      if ( v6 == *(_QWORD *)(a1 + 16) )
        std::vector<wil::com_ptr_t<IUserAccount,wil::err_exception_policy>>::_Emplace_reallocate<wil::com_ptr_t<IUserAccount,wil::err_exception_policy>>(
          a1,
          v6,
          &v10);
      else
        std::vector<wil::com_ptr_t<IUserAccount,wil::err_exception_policy>>::_Emplace_back_with_unused_capacity<wil::com_ptr_t<IUserAccount,wil::err_exception_policy>>(
          a1,
          &v10);
      wil::com_ptr_t<Windows::System::Internal::IUserProfile2,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::IUserProfile2,wil::err_exception_policy>(&v10);
    }
    ++v3;
  }
  return a1;
}

```

## disassembly

```asm
0x18001d318  mov     [rsp+arg_0], rcx
0x18001d31d  push    rbx
0x18001d31e  push    rsi
0x18001d31f  push    rdi
0x18001d320  sub     rsp, 30h
0x18001d324  mov     rbx, rcx
0x18001d327  mov     [rsp+48h+var_28], 0
0x18001d32f  call    ??0?$vector@USessionUserInfo@@V?$allocator@USessionUserInfo@@@std@@@std@@QEAA@XZ; std::vector<SessionUserInfo>::vector<SessionUserInfo>(void)
0x18001d334  mov     [rsp+48h+var_28], 1
0x18001d33c  mov     rdi, [rdx]
0x18001d33f  mov     rsi, [rdx+8]
0x18001d343  jmp     short loc_18001D3B1
0x18001d345  mov     [rsp+48h+arg_8], 0
0x18001d34d  mov     rcx, [rdi]
0x18001d350  mov     rax, [rcx]
0x18001d353  lea     rdx, [rsp+48h+arg_8]
0x18001d358  mov     rax, [rax+50h]
0x18001d35c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d361  mov     rcx, [rsp+48h]; this
0x18001d366  test    eax, eax
0x18001d368  js      short loc_18001D3C1
0x18001d36a  cmp     [rsp+48h+arg_8], 0
0x18001d36f  jnz     short loc_18001D3AD
0x18001d371  mov     rdx, [rdi]
0x18001d374  lea     rcx, [rsp+48h+arg_10]
0x18001d379  call    ??0?$com_ptr_t@UIUserProfile@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIUserProfile@Internal@System@Windows@@@Z; wil::com_ptr_t<Windows::System::Internal::IUserProfile,wil::err_exception_policy>::com_ptr_t<Windows::System::Internal::IUserProfile,wil::err_exception_policy>(Windows::System::Internal::IUserProfile *)
0x18001d37e  nop
0x18001d37f  mov     rdx, [rbx+8]
0x18001d383  mov     rcx, rbx
0x18001d386  cmp     rdx, [rbx+10h]
0x18001d38a  jz      short loc_18001D398
0x18001d38c  lea     rdx, [rsp+48h+arg_10]
0x18001d391  call    ??$_Emplace_back_with_unused_capacity@V?$com_ptr_t@UIUserAccount@@Uerr_exception_policy@wil@@@wil@@@?$vector@V?$com_ptr_t@UIUserAccount@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIUserAccount@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAAEAV?$com_ptr_t@UIUserAccount@@Uerr_exception_policy@wil@@@wil@@$$QEAV23@@Z; std::vector<wil::com_ptr_t<IUserAccount,wil::err_exception_policy>>::_Emplace_back_with_unused_capacity<wil::com_ptr_t<IUserAccount,wil::err_exception_policy>>(wil::com_ptr_t<IUserAccount,wil::err_exception_policy> &&)
0x18001d396  jmp     short loc_18001D3A3
0x18001d398  lea     r8, [rsp+48h+arg_10]
0x18001d39d  call    ??$_Emplace_reallocate@V?$com_ptr_t@UIUserAccount@@Uerr_exception_policy@wil@@@wil@@@?$vector@V?$com_ptr_t@UIUserAccount@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UIUserAccount@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAPEAV?$com_ptr_t@UIUserAccount@@Uerr_exception_policy@wil@@@wil@@QEAV23@$$QEAV23@@Z; std::vector<wil::com_ptr_t<IUserAccount,wil::err_exception_policy>>::_Emplace_reallocate<wil::com_ptr_t<IUserAccount,wil::err_exception_policy>>(wil::com_ptr_t<IUserAccount,wil::err_exception_policy> * const,wil::com_ptr_t<IUserAccount,wil::err_exception_policy> &&)
0x18001d3a2  nop
0x18001d3a3  lea     rcx, [rsp+48h+arg_10]
0x18001d3a8  call    ??1?$com_ptr_t@UIUserProfile2@Internal@System@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::System::Internal::IUserProfile2,wil::err_exception_policy>::~com_ptr_t<Windows::System::Internal::IUserProfile2,wil::err_exception_policy>(void)
0x18001d3ad  add     rdi, 8
0x18001d3b1  cmp     rdi, rsi
0x18001d3b4  jnz     short loc_18001D345
0x18001d3b6  mov     rax, rbx
0x18001d3b9  add     rsp, 30h
0x18001d3bd  pop     rdi
0x18001d3be  pop     rsi
0x18001d3bf  pop     rbx
0x18001d3c0  retn
0x18001d3c1  mov     r9d, eax; char *
0x18001d3c4  lea     r8, aShellcommonShe_0; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001d3cb  mov     edx, 10h; void *
0x18001d3d0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
