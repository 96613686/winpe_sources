# std::vector<std::unique_ptr<NetSetup2::NetworkInterface,std::default_delete<NetSetup2::NetworkInterface>>,std::allocator<std::unique_ptr<NetSetup2::NetworkInterface,std::default_delete<NetSetup2::NetworkInterface>>>>::_Emplace_reallocate<std::unique_ptr<NetSetup2::NetworkInterface,std::default_delete<NetSetup2::NetworkInterface>>>(std::unique_ptr<NetSetup2::NetworkInterface,std::default_delete<NetSetup2::NetworkInterface>> * const,std::unique_ptr<NetSetup2::NetworkInterface,std::default_delete<NetSetup2::NetworkInterface>> &&)

- ea: `0x180008478`
- end: `0x1800085a3`
- name: `??$_Emplace_reallocate@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@?$vector@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@2@@std@@AEAAPEAV?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@1@QEAV21@$$QEAV21@@Z`
- size: `299`
- prototype: `_QWORD *__fastcall(__int64 *, __int64, __int64 *)`
- caller_count: `6`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180007bfc`
- `0x180007d80`
- `0x180007f00`
- `0x180008084`
- `0x180029f54`
- `0x18002a0f8`

## callees

- `0x180006d84`
- `0x180007460`
- `0x180008478`
- `0x1800085ac`
- `0x18000865c`
- `0x1800094a4`
- `0x18000d878`

## pseudocode

```c
_QWORD *__fastcall std::vector<std::unique_ptr<NetSetup2::NetworkInterface>>::_Emplace_reallocate<std::unique_ptr<NetSetup2::NetworkInterface>>(
        __int64 *a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v3; // rbx
  __int64 v5; // rax
  unsigned __int64 v8; // r15
  __int64 v9; // rbp
  unsigned __int64 v10; // rcx
  __int64 v11; // rbp
  unsigned __int64 v12; // rdx
  size_t size_of; // rax
  _QWORD *v14; // rax
  __int64 v15; // rcx
  _QWORD *v16; // rsi
  _QWORD *v17; // r12
  _QWORD *v18; // rbp
  __int64 v19; // rdx
  __int64 v20; // rcx
  _QWORD v22[3]; // [rsp+20h] [rbp-68h] BYREF
  _QWORD *v23; // [rsp+38h] [rbp-50h]
  _QWORD *v24; // [rsp+40h] [rbp-48h]

  v3 = 0x1FFFFFFFFFFFFFFFLL;
  v5 = (a1[1] - *a1) >> 3;
  if ( v5 == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<std::unique_ptr<NetSetup2::BindingPath>>::_Xlength();
  v8 = v5 + 1;
  v9 = a2 - *a1;
  v10 = (a1[2] - *a1) >> 3;
  v11 = v9 >> 3;
  v12 = v10 >> 1;
  if ( v10 <= 0x1FFFFFFFFFFFFFFFLL - (v10 >> 1) )
  {
    v3 = v12 + v10;
    if ( v12 + v10 < v8 )
      v3 = v5 + 1;
  }
  size_of = std::_Get_size_of_n<8>(v3);
  v14 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v15 = *a3;
  v16 = v14;
  *a3 = 0;
  v22[0] = a1;
  v17 = &v14[v11];
  v22[2] = v3;
  *v17 = v15;
  v18 = v17 + 1;
  v19 = a1[1];
  v20 = *a1;
  v24 = v17 + 1;
  v23 = v17;
  if ( a2 == v19 )
  {
    v18 = v14;
  }
  else
  {
    std::_Uninitialized_move<std::unique_ptr<NetSetup2::BindingPath> *,std::allocator<std::unique_ptr<NetSetup2::BindingPath>>>(
      v20,
      a2,
      v14,
      a1,
      v22[0]);
    v19 = a1[1];
    v20 = a2;
    v23 = v16;
  }
  std::_Uninitialized_move<std::unique_ptr<NetSetup2::BindingPath> *,std::allocator<std::unique_ptr<NetSetup2::BindingPath>>>(
    v20,
    v19,
    v18,
    a1,
    v22[0]);
  v22[1] = 0;
  std::vector<std::unique_ptr<NetSetup2::ClientDriver>>::_Change_array(a1, v16, v8, v3);
  std::vector<std::unique_ptr<NetSetup2::ReflectedProperty>>::_Reallocation_guard::~_Reallocation_guard(v22);
  return v17;
}

```

## disassembly

```asm
0x180008478  mov     [rsp+arg_18], rbx
0x18000847d  push    rbp
0x18000847e  push    rsi
0x18000847f  push    rdi
0x180008480  push    r12
0x180008482  push    r13
0x180008484  push    r14
0x180008486  push    r15
0x180008488  sub     rsp, 50h
0x18000848c  mov     rax, [rcx+8]
0x180008490  mov     rbx, 1FFFFFFFFFFFFFFFh
0x18000849a  sub     rax, [rcx]
0x18000849d  mov     r13, r8
0x1800084a0  sar     rax, 3
0x1800084a4  mov     r14, rdx
0x1800084a7  mov     rdi, rcx
0x1800084aa  cmp     rax, rbx
0x1800084ad  jz      loc_18000859D
0x1800084b3  mov     rbp, rdx
0x1800084b6  lea     r15, [rax+1]
0x1800084ba  sub     rbp, [rcx]
0x1800084bd  mov     rax, rbx
0x1800084c0  mov     rcx, [rcx+10h]
0x1800084c4  sub     rcx, [rdi]
0x1800084c7  sar     rcx, 3
0x1800084cb  mov     rdx, rcx
0x1800084ce  sar     rbp, 3
0x1800084d2  shr     rdx, 1
0x1800084d5  sub     rax, rdx
0x1800084d8  cmp     rcx, rax
0x1800084db  ja      short loc_1800084E8
0x1800084dd  lea     rbx, [rdx+rcx]
0x1800084e1  cmp     rbx, r15
0x1800084e4  cmovb   rbx, r15
0x1800084e8  mov     rcx, rbx
0x1800084eb  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x1800084f0  mov     rcx, rax
0x1800084f3  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800084f8  mov     rcx, [r13+0]
0x1800084fc  mov     rsi, rax
0x1800084ff  mov     qword ptr [r13+0], 0
0x180008507  mov     [rsp+88h+var_68], rdi
0x18000850c  lea     r12, [rax+rbp*8]
0x180008510  mov     [rsp+88h+var_58], rbx
0x180008515  mov     [r12], rcx
0x180008519  lea     rbp, [r12+8]
0x18000851e  mov     rdx, [rdi+8]
0x180008522  mov     rcx, [rdi]
0x180008525  mov     [rsp+88h+var_48], rbp
0x18000852a  mov     [rsp+88h+var_50], r12
0x18000852f  cmp     r14, rdx
0x180008532  jnz     short loc_180008539
0x180008534  mov     rbp, rax
0x180008537  jmp     short loc_180008553
0x180008539  mov     r9, rdi
0x18000853c  mov     r8, rsi
0x18000853f  mov     rdx, r14
0x180008542  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<NetSetup2::BindingPath> *,std::allocator<std::unique_ptr<NetSetup2::BindingPath>>>(std::unique_ptr<NetSetup2::BindingPath> * const,std::unique_ptr<NetSetup2::BindingPath> * const,std::unique_ptr<NetSetup2::BindingPath> *,std::allocator<std::unique_ptr<NetSetup2::BindingPath>> &)
0x180008547  mov     rdx, [rdi+8]
0x18000854b  mov     rcx, r14
0x18000854e  mov     [rsp+88h+var_50], rsi
0x180008553  mov     r9, rdi
0x180008556  mov     r8, rbp
0x180008559  call    ??$_Uninitialized_move@PEAV?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@@2@@std@@YAPEAV?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::unique_ptr<NetSetup2::BindingPath> *,std::allocator<std::unique_ptr<NetSetup2::BindingPath>>>(std::unique_ptr<NetSetup2::BindingPath> * const,std::unique_ptr<NetSetup2::BindingPath> * const,std::unique_ptr<NetSetup2::BindingPath> *,std::allocator<std::unique_ptr<NetSetup2::BindingPath>> &)
0x18000855e  mov     r9, rbx
0x180008561  mov     [rsp+88h+var_60], 0
0x18000856a  mov     r8, r15
0x18000856d  mov     rdx, rsi
0x180008570  mov     rcx, rdi
0x180008573  call    ?_Change_array@?$vector@V?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@std@@@2@@std@@AEAAXQEAV?$unique_ptr@VClientDriver@NetSetup2@@U?$default_delete@VClientDriver@NetSetup2@@@std@@@2@_K1@Z; std::vector<std::unique_ptr<NetSetup2::ClientDriver>>::_Change_array(std::unique_ptr<NetSetup2::ClientDriver> * const,unsigned __int64,unsigned __int64)
0x180008578  lea     rcx, [rsp+88h+var_68]
0x18000857d  call    ??1_Reallocation_guard@?$vector@V?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VReflectedProperty@NetSetup2@@U?$default_delete@VReflectedProperty@NetSetup2@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::unique_ptr<NetSetup2::ReflectedProperty>>::_Reallocation_guard::~_Reallocation_guard(void)
0x180008582  mov     rbx, [rsp+88h+arg_18]
0x18000858a  mov     rax, r12
0x18000858d  add     rsp, 50h
0x180008591  pop     r15
0x180008593  pop     r14
0x180008595  pop     r13
0x180008597  pop     r12
0x180008599  pop     rdi
0x18000859a  pop     rsi
0x18000859b  pop     rbp
0x18000859c  retn
0x18000859d  call    ?_Xlength@?$vector@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VBindingPath@NetSetup2@@U?$default_delete@VBindingPath@NetSetup2@@@std@@@std@@@2@@std@@CAXXZ; std::vector<std::unique_ptr<NetSetup2::BindingPath>>::_Xlength(void)
```
