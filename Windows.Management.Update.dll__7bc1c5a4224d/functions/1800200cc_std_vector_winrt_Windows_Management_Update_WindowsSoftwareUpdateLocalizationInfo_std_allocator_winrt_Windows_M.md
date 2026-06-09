# std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::insert(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>>,winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo const &)

- ea: `0x1800200cc`
- end: `0x1800201d2`
- name: `?insert@?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@@2@AEBUWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@Z`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001f2d0`

## callees

- `0x180016fe4`
- `0x18001e128`
- `0x1800200cc`
- `0x18002a010`

## pseudocode

```c
__int64 **__fastcall std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::insert(
        __int64 a1,
        __int64 **a2,
        char *a3,
        __int64 *a4)
{
  __int64 *v4; // rdi
  __int64 *updated; // rbx
  __int64 v8; // rcx
  __int64 *v9; // r14
  __int64 v10; // rax
  __int64 v12[6]; // [rsp+28h] [rbp-30h] BYREF

  v4 = *(__int64 **)(a1 + 8);
  updated = (__int64 *)a3;
  if ( v4 == *(__int64 **)(a1 + 16) )
  {
    updated = std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::_Emplace_reallocate<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo const &>(
                (char **)a1,
                a3,
                a4);
  }
  else
  {
    v8 = *a4;
    if ( a3 == (char *)v4 )
    {
      *v4 = v8;
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
      *(_QWORD *)(a1 + 8) += 8LL;
    }
    else
    {
      v12[0] = *a4;
      if ( v8 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
      v9 = v4 - 1;
      *v4 = *(v4 - 1);
      *(v4 - 1) = 0;
      *(_QWORD *)(a1 + 8) += 8LL;
      while ( v9 != updated )
      {
        if ( --v4 != --v9 )
        {
          if ( *v4 )
            winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v4);
          v10 = *v9;
          *v9 = 0;
          *v4 = v10;
        }
      }
      if ( updated != v12 )
      {
        if ( *updated )
          winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(updated);
        *updated = v12[0];
        v12[0] = 0;
      }
      if ( v12[0] )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v12);
    }
  }
  *a2 = updated;
  return a2;
}

```

## disassembly

```asm
0x1800200cc  push    rbx
0x1800200ce  push    rbp
0x1800200cf  push    rdi
0x1800200d0  push    r14
0x1800200d2  push    r15
0x1800200d4  sub     rsp, 30h
0x1800200d8  mov     rdi, [rcx+8]
0x1800200dc  mov     rbx, r8
0x1800200df  mov     r15, rdx
0x1800200e2  mov     rbp, rcx
0x1800200e5  cmp     rdi, [rcx+10h]
0x1800200e9  jz      loc_1800201B2
0x1800200ef  mov     rcx, [r9]
0x1800200f2  cmp     rbx, rdi
0x1800200f5  jnz     short loc_180020115
0x1800200f7  mov     [rdi], rcx
0x1800200fa  test    rcx, rcx
0x1800200fd  jz      short loc_18002010B
0x1800200ff  mov     rax, [rcx]
0x180020102  mov     rax, [rax+8]
0x180020106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002010b  add     qword ptr [rbp+8], 8
0x180020110  jmp     loc_1800201C0
0x180020115  mov     [rsp+58h+var_38], rbp
0x18002011a  mov     [rsp+58h+var_30], rcx
0x18002011f  test    rcx, rcx
0x180020122  jz      short loc_180020130
0x180020124  mov     rax, [rcx]
0x180020127  mov     rax, [rax+8]
0x18002012b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020130  lea     r14, [rdi-8]
0x180020134  mov     rax, [r14]
0x180020137  mov     [rdi], rax
0x18002013a  mov     qword ptr [r14], 0
0x180020141  add     qword ptr [rbp+8], 8
0x180020146  jmp     short loc_180020170
0x180020148  sub     r14, 8
0x18002014c  sub     rdi, 8
0x180020150  cmp     rdi, r14
0x180020153  jz      short loc_180020170
0x180020155  cmp     qword ptr [rdi], 0
0x180020159  jz      short loc_180020163
0x18002015b  mov     rcx, rdi
0x18002015e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180020163  mov     rax, [r14]
0x180020166  mov     qword ptr [r14], 0
0x18002016d  mov     [rdi], rax
0x180020170  cmp     r14, rbx
0x180020173  jnz     short loc_180020148
0x180020175  lea     rax, [rsp+58h+var_30]
0x18002017a  cmp     rbx, rax
0x18002017d  jz      short loc_18002019E
0x18002017f  cmp     qword ptr [rbx], 0
0x180020183  jz      short loc_18002018D
0x180020185  mov     rcx, rbx
0x180020188  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18002018d  mov     rax, [rsp+58h+var_30]
0x180020192  mov     [rbx], rax
0x180020195  mov     [rsp+58h+var_30], 0
0x18002019e  cmp     [rsp+58h+var_30], 0
0x1800201a4  jz      short loc_1800201C0
0x1800201a6  lea     rcx, [rsp+58h+var_30]
0x1800201ab  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x1800201b0  jmp     short loc_1800201C0
0x1800201b2  mov     r8, r9
0x1800201b5  mov     rdx, rbx
0x1800201b8  call    ??$_Emplace_reallocate@AEBUWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@AEAAPEAUWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@QEAU23456@AEBU23456@@Z; std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::_Emplace_reallocate<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo const &>(winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo * const,winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo const &)
0x1800201bd  mov     rbx, rax
0x1800201c0  mov     [r15], rbx
0x1800201c3  mov     rax, r15
0x1800201c6  add     rsp, 30h
0x1800201ca  pop     r15
0x1800201cc  pop     r14
0x1800201ce  pop     rdi
0x1800201cf  pop     rbp
0x1800201d0  pop     rbx
0x1800201d1  retn
```
