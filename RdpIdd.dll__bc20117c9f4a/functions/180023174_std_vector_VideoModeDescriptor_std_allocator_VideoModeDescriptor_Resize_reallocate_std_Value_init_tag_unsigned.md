# std::vector<_VideoModeDescriptor,std::allocator<_VideoModeDescriptor>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)

- ea: `0x180023174`
- end: `0x18002326b`
- name: `??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@U_VideoModeDescriptor@@V?$allocator@U_VideoModeDescriptor@@@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180026b00`

## callees

- `0x180007b2c`
- `0x1800086fc`
- `0x18000bdcc`
- `0x180020f04`
- `0x180023174`
- `0x180023274`
- `0x180023a18`
- `0x180028034`

## pseudocode

```c
__int64 __fastcall std::vector<_VideoModeDescriptor>::_Resize_reallocate<std::_Value_init_tag>(
        const void **a1,
        unsigned __int64 a2)
{
  __int64 v2; // rsi
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // rdx
  __int64 v7; // rbx
  __int64 v8; // rax
  void *v9; // rdi
  __int64 v10; // rax
  size_t v11; // r8
  const void *v12; // rdx
  _QWORD v14[3]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v15; // [rsp+38h] [rbp-40h]
  __int64 v16; // [rsp+40h] [rbp-38h]

  v2 = 0x492492492492492LL;
  if ( a2 > 0x492492492492492LL )
    std::vector<_RDP_MONITORCONFIG_MODE>::_Xlength();
  v5 = 0x6DB6DB6DB6DB6DB7LL * (((_BYTE *)a1[2] - (_BYTE *)*a1) >> 3);
  v6 = v5 >> 1;
  if ( v5 <= 0x492492492492492LL - (v5 >> 1) )
  {
    if ( v5 + v6 >= a2 )
    {
      if ( v5 + v6 > 0x492492492492492LL )
        std::_Throw_bad_array_new_length();
      v2 = v5 + v6;
    }
    else
    {
      v2 = a2;
    }
  }
  v7 = 0x6DB6DB6DB6DB6DB7LL * (((_BYTE *)a1[1] - (_BYTE *)*a1) >> 3);
  v8 = std::_Allocate<16,std::_Default_allocate_traits>(56 * v2);
  v14[0] = a1;
  v14[2] = v2;
  v15 = v8 + 56 * v7;
  v9 = (void *)v8;
  v10 = std::_Uninitialized_value_construct_n<std::allocator<_VideoModeDescriptor>>(v15, a2 - v7);
  v11 = (_BYTE *)a1[1] - (_BYTE *)*a1;
  v12 = *a1;
  v16 = v10;
  memmove_0(v9, v12, v11);
  v14[1] = 0;
  std::vector<_VideoModeDescriptor>::_Change_array(a1, v9, a2, v2);
  return std::vector<_VideoModeDescriptor>::_Reallocation_guard::~_Reallocation_guard(v14);
}

```

## disassembly

```asm
0x180023174  push    rbx
0x180023176  push    rbp
0x180023177  push    rsi
0x180023178  push    rdi
0x180023179  push    r14
0x18002317b  sub     rsp, 50h
0x18002317f  mov     rsi, 492492492492492h
0x180023189  mov     rbp, rdx
0x18002318c  mov     r14, rcx
0x18002318f  cmp     rdx, rsi
0x180023192  ja      loc_180023265
0x180023198  mov     rcx, [rcx+10h]
0x18002319c  mov     r8, 6DB6DB6DB6DB6DB7h
0x1800231a6  sub     rcx, [r14]
0x1800231a9  mov     rax, rsi
0x1800231ac  sar     rcx, 3
0x1800231b0  imul    rcx, r8
0x1800231b4  mov     rdx, rcx
0x1800231b7  shr     rdx, 1
0x1800231ba  sub     rax, rdx
0x1800231bd  cmp     rcx, rax
0x1800231c0  ja      short loc_1800231DC
0x1800231c2  lea     rax, [rcx+rdx]
0x1800231c6  cmp     rax, rbp
0x1800231c9  jnb     short loc_1800231D0
0x1800231cb  mov     rsi, rbp
0x1800231ce  jmp     short loc_1800231DC
0x1800231d0  cmp     rax, rsi
0x1800231d3  ja      loc_18002325F
0x1800231d9  mov     rsi, rax
0x1800231dc  mov     rbx, [r14+8]
0x1800231e0  sub     rbx, [r14]
0x1800231e3  imul    rcx, rsi, 38h ; '8'
0x1800231e7  sar     rbx, 3
0x1800231eb  imul    rbx, r8
0x1800231ef  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800231f4  imul    rcx, rbx, 38h ; '8'
0x1800231f8  mov     rdx, rbp
0x1800231fb  mov     [rsp+78h+var_58], r14
0x180023200  add     rcx, rax
0x180023203  mov     [rsp+78h+var_48], rsi
0x180023208  sub     rdx, rbx
0x18002320b  mov     [rsp+78h+var_40], rcx
0x180023210  mov     rdi, rax
0x180023213  call    ??$_Uninitialized_value_construct_n@V?$allocator@U_VideoModeDescriptor@@@std@@@std@@YAPEAU_VideoModeDescriptor@@PEAU1@_KAEAV?$allocator@U_VideoModeDescriptor@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<_VideoModeDescriptor>>(_VideoModeDescriptor *,unsigned __int64,std::allocator<_VideoModeDescriptor> &)
0x180023218  mov     r8, [r14+8]
0x18002321c  mov     rcx, rdi; void *
0x18002321f  sub     r8, [r14]; Size
0x180023222  mov     rdx, [r14]; Src
0x180023225  mov     [rsp+78h+var_38], rax
0x18002322a  call    memmove_0
0x18002322f  mov     r9, rsi
0x180023232  mov     [rsp+78h+var_50], 0
0x18002323b  mov     r8, rbp
0x18002323e  mov     rdx, rdi
0x180023241  mov     rcx, r14
0x180023244  call    ?_Change_array@?$vector@U_VideoModeDescriptor@@V?$allocator@U_VideoModeDescriptor@@@std@@@std@@AEAAXQEAU_VideoModeDescriptor@@_K1@Z; std::vector<_VideoModeDescriptor>::_Change_array(_VideoModeDescriptor * const,unsigned __int64,unsigned __int64)
0x180023249  lea     rcx, [rsp+78h+var_58]
0x18002324e  call    ??1_Reallocation_guard@?$vector@U_VideoModeDescriptor@@V?$allocator@U_VideoModeDescriptor@@@std@@@std@@QEAA@XZ; std::vector<_VideoModeDescriptor>::_Reallocation_guard::~_Reallocation_guard(void)
0x180023253  add     rsp, 50h
0x180023257  pop     r14
0x180023259  pop     rdi
0x18002325a  pop     rsi
0x18002325b  pop     rbp
0x18002325c  pop     rbx
0x18002325d  retn
0x18002325f  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
0x180023265  call    ?_Xlength@?$vector@U_RDP_MONITORCONFIG_MODE@@V?$allocator@U_RDP_MONITORCONFIG_MODE@@@std@@@std@@CAXXZ; std::vector<_RDP_MONITORCONFIG_MODE>::_Xlength(void)
```
