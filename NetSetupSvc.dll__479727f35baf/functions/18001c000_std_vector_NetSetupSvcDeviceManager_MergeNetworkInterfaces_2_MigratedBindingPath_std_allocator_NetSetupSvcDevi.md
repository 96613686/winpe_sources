# std::vector__NetSetupSvcDeviceManager::MergeNetworkInterfaces_::_2_::MigratedBindingPath_std::allocator__NetSetupSvcDeviceManager::MergeNetworkInterfaces_::_2_::MigratedBindingPath___::_Emplace_reallocate_std::vector__NETSETUP_OBJECT_ID_std::allocator__NETSETUP_OBJECT_ID____NetSetup2::BindingPathTemplate_

- ea: `0x18001c000`
- end: `0x18001c14d`
- name: `std::vector__NetSetupSvcDeviceManager::MergeNetworkInterfaces_::_2_::MigratedBindingPath_std::allocator__NetSetupSvcDeviceManager::MergeNetworkInterfaces_::_2_::MigratedBindingPath___::_Emplace_reallocate_std::vector__NETSETUP_OBJECT_ID_std::allocator__NETSETUP_OBJECT_ID____NetSetup2::BindingPathTemplate_`
- size: `333`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x18001cb00`

## callees

- `0x180006d84`
- `0x18001c000`
- `0x18001c48c`
- `0x18001c764`
- `0x18001c984`
- `0x18001d810`
- `0x180023d08`
- `0x180024320`

## pseudocode

```c
_QWORD *__fastcall std::vector__NetSetupSvcDeviceManager::MergeNetworkInterfaces_::_2_::MigratedBindingPath_std::allocator__NetSetupSvcDeviceManager::MergeNetworkInterfaces_::_2_::MigratedBindingPath___::_Emplace_reallocate_std::vector__NETSETUP_OBJECT_ID_std::allocator__NETSETUP_OBJECT_ID____NetSetup2::BindingPathTemplate_(
        __int64 *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v5; // rbx
  unsigned __int64 v7; // r8
  unsigned __int64 v9; // r14
  __int64 v10; // r12
  unsigned __int64 v11; // rcx
  unsigned __int64 v12; // rdx
  size_t size_of; // rax
  _QWORD *v14; // rax
  _QWORD *v15; // rbp
  _QWORD *v16; // rdi
  __int64 v17; // rcx
  __int64 v18; // rdx
  _QWORD *v19; // r8
  __int64 v20; // rcx
  _QWORD v23[3]; // [rsp+28h] [rbp-70h] BYREF
  _QWORD *v24; // [rsp+40h] [rbp-58h]
  _QWORD *v25; // [rsp+48h] [rbp-50h]

  v5 = 0x555555555555555LL;
  v7 = 0xAAAAAAAAAAAAAAABuLL * ((a1[1] - *a1) >> 4);
  if ( v7 == 0x555555555555555LL )
    std::vector__NetSetupSvcDeviceManager::MergeNetworkInterfaces_::_2_::MigratedBindingPath_std::allocator__NetSetupSvcDeviceManager::MergeNetworkInterfaces_::_2_::MigratedBindingPath___::_Xlength();
  v9 = v7 + 1;
  v10 = (a2 - *a1) / 48;
  v11 = 0xAAAAAAAAAAAAAAABuLL * ((a1[2] - *a1) >> 4);
  v12 = (0xAAAAAAAAAAAAAAABuLL * ((a1[2] - *a1) >> 4)) >> 1;
  if ( v11 <= 0x555555555555555LL - v12 )
  {
    v5 = v12 + v11;
    if ( v12 + v11 < v9 )
      v5 = v7 + 1;
  }
  size_of = std::_Get_size_of_n<48>(v5);
  v14 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v15 = &v14[6 * v10];
  v23[0] = a1;
  v23[2] = v5;
  v16 = v14;
  v25 = v15 + 6;
  std::_Default_allocator_traits_std::allocator__NetSetupSvcDeviceManager::MergeNetworkInterfaces_::_2_::MigratedBindingPath___::construct__NetSetupSvcDeviceManager::MergeNetworkInterfaces_::_2_::MigratedBindingPath_std::vector__NETSETUP_OBJECT_ID_std::allocator__NETSETUP_OBJECT_ID____NetSetup2::BindingPathTemplate_(
    v17,
    v15,
    a3,
    a4);
  v18 = a1[1];
  v19 = v16;
  v20 = *a1;
  v24 = v15;
  if ( a2 != v18 )
  {
    std::_Uninitialized_move__NetSetupSvcDeviceManager::MergeNetworkInterfaces_::_2_::MigratedBindingPath___std::allocator__NetSetupSvcDeviceManager::MergeNetworkInterfaces_::_2_::MigratedBindingPath___(
      v20,
      a2,
      v16);
    v18 = a1[1];
    v19 = v15 + 6;
    v20 = a2;
    v24 = v16;
  }
  std::_Uninitialized_move__NetSetupSvcDeviceManager::MergeNetworkInterfaces_::_2_::MigratedBindingPath___std::allocator__NetSetupSvcDeviceManager::MergeNetworkInterfaces_::_2_::MigratedBindingPath___(
    v20,
    v18,
    v19);
  v23[1] = 0;
  std::vector__NetSetupSvcDeviceManager::MergeNetworkInterfaces_::_2_::MigratedBindingPath_std::allocator__NetSetupSvcDeviceManager::MergeNetworkInterfaces_::_2_::MigratedBindingPath___::_Change_array(
    a1,
    v16,
    v9,
    v5);
  std::vector__NetSetupSvcDeviceManager::MergeNetworkInterfaces_::_2_::MigratedBindingPath_std::allocator__NetSetupSvcDeviceManager::MergeNetworkInterfaces_::_2_::MigratedBindingPath___::_Reallocation_guard::__Reallocation_guard(v23);
  return v15;
}

```

## disassembly

```asm
0x18001c000  push    rbx
0x18001c002  push    rbp
0x18001c003  push    rsi
0x18001c004  push    rdi
0x18001c005  push    r12
0x18001c007  push    r13
0x18001c009  push    r14
0x18001c00b  push    r15
0x18001c00d  sub     rsp, 58h
0x18001c011  mov     r13, r8
0x18001c014  mov     [rsp+98h+var_78], r9
0x18001c019  mov     r8, [rcx+8]
0x18001c01d  mov     r9, 0AAAAAAAAAAAAAAABh
0x18001c027  sub     r8, [rcx]
0x18001c02a  mov     rbx, 555555555555555h
0x18001c034  sar     r8, 4
0x18001c038  mov     r15, rdx
0x18001c03b  imul    r8, r9
0x18001c03f  mov     rsi, rcx
0x18001c042  cmp     r8, rbx
0x18001c045  jz      loc_18001C147
0x18001c04b  mov     rcx, rdx
0x18001c04e  lea     r14, [r8+1]
0x18001c052  sub     rcx, [rsi]
0x18001c055  mov     rax, 2AAAAAAAAAAAAAABh
0x18001c05f  imul    rcx
0x18001c062  mov     rcx, [rsi+10h]
0x18001c066  sub     rcx, [rsi]
0x18001c069  mov     r12, rdx
0x18001c06c  sar     r12, 3
0x18001c070  sar     rcx, 4
0x18001c074  mov     rax, r12
0x18001c077  shr     rax, 3Fh
0x18001c07b  add     r12, rax
0x18001c07e  mov     rax, rbx
0x18001c081  imul    rcx, r9
0x18001c085  mov     rdx, rcx
0x18001c088  shr     rdx, 1
0x18001c08b  sub     rax, rdx
0x18001c08e  cmp     rcx, rax
0x18001c091  ja      short loc_18001C09E
0x18001c093  lea     rbx, [rdx+rcx]
0x18001c097  cmp     rbx, r14
0x18001c09a  cmovb   rbx, r14
0x18001c09e  mov     rcx, rbx
0x18001c0a1  call    ??$_Get_size_of_n@$0DA@@std@@YA_K_K@Z; std::_Get_size_of_n<48>(unsigned __int64)
0x18001c0a6  mov     rcx, rax
0x18001c0a9  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001c0ae  mov     r9, [rsp+98h+var_78]
0x18001c0b3  lea     rbp, [r12+r12*2]
0x18001c0b7  shl     rbp, 4
0x18001c0bb  mov     r8, r13
0x18001c0be  add     rbp, rax
0x18001c0c1  mov     [rsp+98h+var_70], rsi
0x18001c0c6  mov     rdx, rbp
0x18001c0c9  mov     [rsp+98h+var_60], rbx
0x18001c0ce  mov     rdi, rax
0x18001c0d1  lea     r12, [rbp+30h]
0x18001c0d5  mov     [rsp+98h+var_50], r12
0x18001c0da  call    std___Default_allocator_traits_std__allocator__NetSetupSvcDeviceManager__MergeNetworkInterfaces____2___MigratedBindingPath_____construct__NetSetupSvcDeviceManager__MergeNetworkInterfaces____2___MigratedBindingPath_std__vector__NETSETUP_OBJECT_ID_std__allocator__NETSETUP_OBJECT_ID____NetSetup2__BindingPathTemplate_
0x18001c0df  mov     rdx, [rsi+8]
0x18001c0e3  mov     r8, rdi
0x18001c0e6  mov     rcx, [rsi]
0x18001c0e9  mov     [rsp+98h+var_58], rbp
0x18001c0ee  cmp     r15, rdx
0x18001c0f1  jz      short loc_18001C10A
0x18001c0f3  mov     rdx, r15
0x18001c0f6  call    std___Uninitialized_move__NetSetupSvcDeviceManager__MergeNetworkInterfaces____2___MigratedBindingPath___std__allocator__NetSetupSvcDeviceManager__MergeNetworkInterfaces____2___MigratedBindingPath___
0x18001c0fb  mov     rdx, [rsi+8]
0x18001c0ff  mov     r8, r12
0x18001c102  mov     rcx, r15
0x18001c105  mov     [rsp+98h+var_58], rdi
0x18001c10a  call    std___Uninitialized_move__NetSetupSvcDeviceManager__MergeNetworkInterfaces____2___MigratedBindingPath___std__allocator__NetSetupSvcDeviceManager__MergeNetworkInterfaces____2___MigratedBindingPath___
0x18001c10f  mov     r9, rbx
0x18001c112  mov     [rsp+98h+var_68], 0
0x18001c11b  mov     r8, r14
0x18001c11e  mov     rdx, rdi
0x18001c121  mov     rcx, rsi
0x18001c124  call    std__vector__NetSetupSvcDeviceManager__MergeNetworkInterfaces____2___MigratedBindingPath_std__allocator__NetSetupSvcDeviceManager__MergeNetworkInterfaces____2___MigratedBindingPath______Change_array
0x18001c129  lea     rcx, [rsp+98h+var_70]
0x18001c12e  call    std__vector__NetSetupSvcDeviceManager__MergeNetworkInterfaces____2___MigratedBindingPath_std__allocator__NetSetupSvcDeviceManager__MergeNetworkInterfaces____2___MigratedBindingPath______Reallocation_guard____Reallocation_guard
0x18001c133  mov     rax, rbp
0x18001c136  add     rsp, 58h
0x18001c13a  pop     r15
0x18001c13c  pop     r14
0x18001c13e  pop     r13
0x18001c140  pop     r12
0x18001c142  pop     rdi
0x18001c143  pop     rsi
0x18001c144  pop     rbp
0x18001c145  pop     rbx
0x18001c146  retn
0x18001c147  call    std__vector__NetSetupSvcDeviceManager__MergeNetworkInterfaces____2___MigratedBindingPath_std__allocator__NetSetupSvcDeviceManager__MergeNetworkInterfaces____2___MigratedBindingPath______Xlength
```
