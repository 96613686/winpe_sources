# std::vector<std::unique_ptr<NetSetup2::BindingPath,std::default_delete<NetSetup2::BindingPath>>,std::allocator<std::unique_ptr<NetSetup2::BindingPath,std::default_delete<NetSetup2::BindingPath>>>>::_Reallocate<0>(unsigned __int64 &)

- ea: `0x1800085d8`
- end: `0x180008653`
- name: `??$_Reallocate@$0A@@?$vector@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@@2@@std@@AEAAXAEA_K@Z`
- size: `123`
- prototype: `__int64 __fastcall(_QWORD *, _QWORD *)`
- caller_count: `6`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180007bfc`
- `0x180007d80`
- `0x180007f00`
- `0x180008084`
- `0x180029f54`
- `0x18002a0f8`

## callees

- `0x180006d84`
- `0x1800085ac`
- `0x18000865c`
- `0x1800094e0`
- `0x18000d878`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::vector<std::unique_ptr<NetSetup2::BindingPath>>::_Reallocate<0>(_QWORD *a1, _QWORD *a2)
{
  __int64 v4; // rdi
  size_t size_of; // rax
  _QWORD *v6; // rax
  __int64 v7; // rdx
  _QWORD *v8; // rbx
  __int64 v9; // r9
  _QWORD v11[9]; // [rsp+20h] [rbp-48h] BYREF

  v4 = (__int64)(a1[1] - *a1) >> 3;
  size_of = std::_Get_size_of_n<8>(*a2);
  v6 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v7 = a1[1];
  v11[2] = *a2;
  v8 = v6;
  std::_Uninitialized_move<std::unique_ptr<NetSetup2::BindingPath> *,std::allocator<std::unique_ptr<NetSetup2::BindingPath>>>(
    *a1,
    v7,
    v6,
    a1,
    a1);
  v9 = *a2;
  v11[1] = 0;
  std::vector<std::unique_ptr<NetSetup2::ClientDriver>>::_Change_array(a1, v8, v4, v9);
  return std::vector<std::unique_ptr<NetSetup2::ProtocolDriver>>::_Simple_reallocation_guard::~_Simple_reallocation_guard(v11);
}

```

## disassembly

```asm
0x1800085d8  push    rbx
0x1800085da  push    rsi
0x1800085db  push    rdi
0x1800085dc  push    r14
0x1800085de  sub     rsp, 48h
0x1800085e2  mov     rdi, [rcx+8]
0x1800085e6  mov     r14, rcx
0x1800085e9  sub     rdi, [rcx]
0x1800085ec  mov     rsi, rdx
0x1800085ef  mov     rcx, [rdx]
0x1800085f2  sar     rdi, 3
0x1800085f6  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x1800085fb  mov     rcx, rax
0x1800085fe  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180008603  mov     rcx, [rsi]
0x180008606  mov     r9, r14
0x180008609  mov     rdx, [r14+8]
0x18000860d  mov     r8, rax
0x180008610  mov     [rsp+68h+var_38], rcx
0x180008615  mov     rbx, rax
0x180008618  mov     rcx, [r14]
0x18000861b  mov     [rsp+68h+var_48], r14
0x180008620  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<NetSetup2::BindingPath> *,std::allocator<std::unique_ptr<NetSetup2::BindingPath>>>(std::unique_ptr<NetSetup2::BindingPath> * const,std::unique_ptr<NetSetup2::BindingPath> * const,std::unique_ptr<NetSetup2::BindingPath> *,std::allocator<std::unique_ptr<NetSetup2::BindingPath>> &)
0x180008625  mov     r9, [rsi]
0x180008628  mov     r8, rdi
0x18000862b  mov     rdx, rbx
0x18000862e  mov     [rsp+68h+var_40], 0
0x180008637  mov     rcx, r14
0x18000863a  call    ?_Change_array@?$vector@V?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@std@@@2@@std@@AEAAXQEAV?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@2@_K1@Z; std::vector<std::unique_ptr<NetSetup2::ClientDriver>>::_Change_array(std::unique_ptr<NetSetup2::ClientDriver> * const,unsigned __int64,unsigned __int64)
0x18000863f  lea     rcx, [rsp+68h+var_48]
0x180008644  call    ??1_Simple_reallocation_guard@?$vector@V?$unique_ptr@VProtocolDriver@NetSetup2@@U?$default_delete@VProtocolDriver@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VProtocolDriver@NetSetup2@@U?$default_delete@VProtocolDriver@NetSetup2@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<NetSetup2::ProtocolDriver>>::_Simple_reallocation_guard::~_Simple_reallocation_guard(void)
0x180008649  add     rsp, 48h
0x18000864d  pop     r14
0x18000864f  pop     rdi
0x180008650  pop     rsi
0x180008651  pop     rbx
0x180008652  retn
```
