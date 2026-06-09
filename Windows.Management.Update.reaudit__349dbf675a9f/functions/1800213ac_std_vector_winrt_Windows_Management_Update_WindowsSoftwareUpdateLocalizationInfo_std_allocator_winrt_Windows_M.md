# std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::insert(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>>,winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo const &)

- ea: `0x1800213ac`
- end: `0x1800214c9`
- name: `?insert@?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@@2@AEBUWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@Z`
- size: `285`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800205d0`

## callees

- `0x180017c3c`
- `0x18001f3f4`
- `0x1800213ac`
- `0x18002c010`

## pseudocode

```c
__int64 **__fastcall std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::insert(
        __int64 **a1,
        __int64 **a2,
        __int64 *a3,
        __int64 *a4)
{
  __int64 *v4; // rsi
  __int64 *updated; // rbx
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 *v10; // r14
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v14[2]; // [rsp+28h] [rbp-10h] BYREF

  v4 = a1[1];
  updated = a3;
  if ( v4 == a1[2] )
  {
    updated = (__int64 *)std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::_Emplace_reallocate<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo const &>(
                           a1,
                           a3,
                           a4);
  }
  else
  {
    v8 = *a4;
    if ( a3 == v4 )
    {
      *v4 = v8;
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
      ++a1[1];
    }
    else
    {
      v14[0] = *a4;
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
      v9 = *(v4 - 1);
      *(v4 - 1) = 0;
      *v4 = v9;
      ++a1[1];
      if ( v4 - 1 != updated )
      {
        do
        {
          v10 = --v4 - 1;
          if ( *v4 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v4);
          v11 = *v10;
          *v10 = 0;
          *v4 = v11;
        }
        while ( v10 != updated );
      }
      if ( updated != v14 )
      {
        if ( *updated )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(updated);
        v12 = v14[0];
        v14[0] = 0;
        *updated = v12;
      }
      if ( v14[0] )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v14);
    }
  }
  *a2 = updated;
  return a2;
}

```

## disassembly

```asm
0x1800213ac  mov     rax, rsp
0x1800213af  mov     [rax+8], rbx
0x1800213b3  mov     [rax+10h], rbp
0x1800213b7  mov     [rax+18h], rsi
0x1800213bb  mov     [rax+20h], r14
0x1800213bf  push    r15
0x1800213c1  sub     rsp, 30h
0x1800213c5  mov     rsi, [rcx+8]
0x1800213c9  mov     rbx, r8
0x1800213cc  mov     r15, rdx
0x1800213cf  mov     rbp, rcx
0x1800213d2  cmp     rsi, [rcx+10h]
0x1800213d6  jz      loc_180021499
0x1800213dc  mov     rcx, [r9]
0x1800213df  cmp     rbx, rsi
0x1800213e2  jnz     short loc_180021402
0x1800213e4  mov     [rsi], rcx
0x1800213e7  test    rcx, rcx
0x1800213ea  jz      short loc_1800213F8
0x1800213ec  mov     rax, [rcx]
0x1800213ef  mov     rax, [rax+8]
0x1800213f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800213f8  add     qword ptr [rbp+8], 8
0x1800213fd  jmp     loc_1800214A7
0x180021402  mov     [rsp+38h+var_18], rbp
0x180021407  mov     [rsp+38h+var_10], rcx
0x18002140c  test    rcx, rcx
0x18002140f  jz      short loc_18002141D
0x180021411  mov     rax, [rcx]
0x180021414  mov     rax, [rax+8]
0x180021418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002141d  lea     rcx, [rsi-8]
0x180021421  mov     rax, [rcx]
0x180021424  and     qword ptr [rcx], 0
0x180021428  mov     [rsi], rax
0x18002142b  add     qword ptr [rbp+8], 8
0x180021430  cmp     rcx, rbx
0x180021433  jz      short loc_18002145F
0x180021435  sub     rsi, 8
0x180021439  lea     r14, [rsi-8]
0x18002143d  cmp     rsi, r14
0x180021440  jz      short loc_18002145A
0x180021442  cmp     qword ptr [rsi], 0
0x180021446  jz      short loc_180021450
0x180021448  mov     rcx, rsi
0x18002144b  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180021450  mov     rax, [r14]
0x180021453  and     qword ptr [r14], 0
0x180021457  mov     [rsi], rax
0x18002145a  cmp     r14, rbx
0x18002145d  jnz     short loc_180021435
0x18002145f  lea     rax, [rsp+38h+var_10]
0x180021464  cmp     rbx, rax
0x180021467  jz      short loc_180021485
0x180021469  cmp     qword ptr [rbx], 0
0x18002146d  jz      short loc_180021477
0x18002146f  mov     rcx, rbx
0x180021472  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180021477  mov     rax, [rsp+38h+var_10]
0x18002147c  and     [rsp+38h+var_10], 0
0x180021482  mov     [rbx], rax
0x180021485  cmp     [rsp+38h+var_10], 0
0x18002148b  jz      short loc_1800214A7
0x18002148d  lea     rcx, [rsp+38h+var_10]
0x180021492  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180021497  jmp     short loc_1800214A7
0x180021499  mov     r8, r9
0x18002149c  mov     rdx, rbx
0x18002149f  call    ??$_Emplace_reallocate@AEBUWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@AEAAPEAUWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@QEAU23456@AEBU23456@@Z; std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::_Emplace_reallocate<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo const &>(winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo * const,winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo const &)
0x1800214a4  mov     rbx, rax
0x1800214a7  mov     [r15], rbx
0x1800214aa  mov     rax, r15
0x1800214ad  mov     rbx, [rsp+38h+arg_0]
0x1800214b2  mov     rbp, [rsp+38h+arg_8]
0x1800214b7  mov     rsi, [rsp+38h+arg_10]
0x1800214bc  mov     r14, [rsp+38h+arg_18]
0x1800214c1  add     rsp, 30h
0x1800214c5  pop     r15
0x1800214c7  retn
```
