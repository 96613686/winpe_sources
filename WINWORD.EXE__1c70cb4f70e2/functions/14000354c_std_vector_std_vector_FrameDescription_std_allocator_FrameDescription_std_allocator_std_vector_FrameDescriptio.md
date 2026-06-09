# std::vector<std::vector<FrameDescription,std::allocator<FrameDescription>>,std::allocator<std::vector<FrameDescription,std::allocator<FrameDescription>>>>::_Emplace_reallocate<std::vector<FrameDescription,std::allocator<FrameDescription>> const &>(std::vector<FrameDescription,std::allocator<FrameDescription>> * const,std::vector<FrameDescription,std::allocator<FrameDescription>> const &)

- ea: `0x14000354c`
- end: `0x1400036ef`
- name: `??$_Emplace_reallocate@AEBV?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@@?$vector@V?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@V?$allocator@V?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@@2@@std@@AEAAPEAV?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@1@QEAV21@AEBV21@@Z`
- size: `419`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140003a50`

## callees

- `0x140003430`
- `0x1400034a4`
- `0x14000354c`
- `0x140003800`
- `0x140003978`
- `0x140004138`
- `0x1400041c4`

## import_xrefs

- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x1400035c7`
- `MSVCP140!?_Xlength_error@std@@YAXPEBD@Z` at `0x1400035c7`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char *__fastcall std::vector<std::vector<FrameDescription>>::_Emplace_reallocate<std::vector<FrameDescription> const &>(
        __int64 **a1,
        __int64 *a2,
        _QWORD *a3)
{
  __int64 v6; // r14
  unsigned __int64 v7; // rax
  unsigned __int64 v8; // rbp
  unsigned __int64 v9; // rcx
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rbx
  char *v12; // rdi
  char *v13; // r14
  __int64 *v14; // rdx
  __int64 *v15; // rcx
  char *v16; // r8
  _QWORD v18[2]; // [rsp+20h] [rbp-58h] BYREF
  unsigned __int64 v19; // [rsp+30h] [rbp-48h]
  char *v20; // [rsp+38h] [rbp-40h]
  _QWORD *v21; // [rsp+40h] [rbp-38h]

  v6 = ((char *)a2 - (char *)*a1) / 24;
  v7 = 0xAAAAAAAAAAAAAAABuLL * (a1[1] - *a1);
  if ( v7 == 0xAAAAAAAAAAAAAAALL )
    std::_Xlength_error("vector too long");
  v8 = v7 + 1;
  v9 = 0xAAAAAAAAAAAAAAABuLL * (a1[2] - *a1);
  v10 = v9 >> 1;
  if ( v9 <= 0xAAAAAAAAAAAAAAALL - (v9 >> 1) )
  {
    v11 = v7 + 1;
    if ( v10 + v9 >= v8 )
      v11 = v10 + v9;
    if ( v11 > 0xAAAAAAAAAAAAAAALL )
      std::_Throw_bad_array_new_length();
  }
  else
  {
    v11 = 0xAAAAAAAAAAAAAAALL;
  }
  v12 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(24 * v11);
  v13 = &v12[24 * v6];
  v18[0] = a1;
  v18[1] = v12;
  v19 = v11;
  v20 = v13 + 24;
  v21 = v13 + 24;
  *(_QWORD *)v13 = 0;
  *((_QWORD *)v13 + 1) = 0;
  *((_QWORD *)v13 + 2) = 0;
  std::vector<FrameDescription>::_Construct_n<FrameDescription * const &,FrameDescription * const &>(
    v13,
    (__int64)(a3[1] - *a3) >> 4,
    a3,
    a3 + 1);
  v20 = v13;
  v14 = a1[1];
  v15 = *a1;
  v16 = v12;
  if ( a2 != v14 )
  {
    std::_Uninitialized_move<std::vector<FrameDescription> *,std::allocator<std::vector<FrameDescription>>>(
      v15,
      a2,
      v12);
    v20 = v12;
    v16 = v13 + 24;
    v14 = a1[1];
    v15 = a2;
  }
  std::_Uninitialized_move<std::vector<FrameDescription> *,std::allocator<std::vector<FrameDescription>>>(v15, v14, v16);
  std::vector<std::vector<FrameDescription>>::_Change_array(a1, v12, v8, v11, v18[0], 0, v19, v20, v21);
  std::vector<std::vector<FrameDescription>>::_Reallocation_guard::~_Reallocation_guard(v18);
  return v13;
}

```

## disassembly

```asm
0x14000354c  mov     [rsp+arg_8], rbx
0x140003551  mov     [rsp+arg_10], rbp
0x140003556  mov     [rsp+arg_18], rsi
0x14000355b  push    rdi
0x14000355c  push    r12
0x14000355e  push    r13
0x140003560  push    r14
0x140003562  push    r15
0x140003564  sub     rsp, 50h
0x140003568  mov     r13, r8
0x14000356b  mov     r15, rdx
0x14000356e  mov     rsi, rcx
0x140003571  mov     r10, [rcx]
0x140003574  mov     r9, rdx
0x140003577  sub     r9, r10
0x14000357a  mov     rax, 2AAAAAAAAAAAAAABh
0x140003584  imul    r9
0x140003587  mov     r14, rdx
0x14000358a  sar     r14, 2
0x14000358e  mov     rax, r14
0x140003591  shr     rax, 3Fh
0x140003595  add     r14, rax
0x140003598  mov     rax, [rcx+8]
0x14000359c  sub     rax, r10
0x14000359f  sar     rax, 3
0x1400035a3  mov     rdx, 0AAAAAAAAAAAAAAABh
0x1400035ad  imul    rax, rdx
0x1400035b1  mov     r8, 0AAAAAAAAAAAAAAAh
0x1400035bb  cmp     rax, r8
0x1400035be  jnz     short loc_1400035CE
0x1400035c0  lea     rcx, aVectorTooLong; "vector too long"
0x1400035c7  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x1400035ce  lea     rbp, [rax+1]
0x1400035d2  mov     rcx, [rcx+10h]
0x1400035d6  sub     rcx, r10
0x1400035d9  sar     rcx, 3
0x1400035dd  imul    rcx, rdx
0x1400035e1  mov     rdx, rcx
0x1400035e4  shr     rdx, 1
0x1400035e7  mov     rax, r8
0x1400035ea  sub     rax, rdx
0x1400035ed  cmp     rcx, rax
0x1400035f0  jbe     loc_1400036D2
0x1400035f6  mov     rbx, r8
0x1400035f9  lea     rcx, [rbx+rbx*2]
0x1400035fd  shl     rcx, 3
0x140003601  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x140003606  mov     rdi, rax
0x140003609  lea     rcx, [r14+r14*2]
0x14000360d  lea     r14, [rax+rcx*8]
0x140003611  lea     r12, [r14+18h]
0x140003615  mov     [rsp+78h+var_58], rsi
0x14000361a  mov     [rsp+78h+var_50], rax
0x14000361f  mov     [rsp+78h+var_48], rbx
0x140003624  mov     [rsp+78h+var_40], r12
0x140003629  mov     [rsp+78h+var_38], r12
0x14000362e  mov     [rsp+78h+arg_0], r14
0x140003636  xor     eax, eax
0x140003638  mov     [r14], rax
0x14000363b  mov     [r14+8], rax
0x14000363f  mov     [r14+10h], rax
0x140003643  lea     r9, [r13+8]
0x140003647  mov     rdx, [r9]
0x14000364a  sub     rdx, [r13+0]
0x14000364e  sar     rdx, 4
0x140003652  mov     r8, r13
0x140003655  mov     rcx, r14
0x140003658  call    ??$_Construct_n@AEBQEAUFrameDescription@@AEBQEAU1@@?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@AEAAX_KAEBQEAUFrameDescription@@1@Z; std::vector<FrameDescription>::_Construct_n<FrameDescription * const &,FrameDescription * const &>(unsigned __int64,FrameDescription * const &,FrameDescription * const &)
0x14000365d  mov     [rsp+78h+var_40], r14
0x140003662  mov     rdx, [rsi+8]
0x140003666  mov     rcx, [rsi]
0x140003669  mov     r8, rdi
0x14000366c  cmp     r15, rdx
0x14000366f  jz      short loc_140003688
0x140003671  mov     rdx, r15
0x140003674  call    ??$_Uninitialized_move@PEAV?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@V?$allocator@V?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@@2@@std@@YAPEAV?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::vector<FrameDescription> *,std::allocator<std::vector<FrameDescription>>>(std::vector<FrameDescription> * const,std::vector<FrameDescription> * const,std::vector<FrameDescription> *,std::allocator<std::vector<FrameDescription>> &)
0x140003679  mov     [rsp+78h+var_40], rdi
0x14000367e  mov     r8, r12
0x140003681  mov     rdx, [rsi+8]
0x140003685  mov     rcx, r15
0x140003688  call    ??$_Uninitialized_move@PEAV?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@V?$allocator@V?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@@2@@std@@YAPEAV?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@@0@@Z; std::_Uninitialized_move<std::vector<FrameDescription> *,std::allocator<std::vector<FrameDescription>>>(std::vector<FrameDescription> * const,std::vector<FrameDescription> * const,std::vector<FrameDescription> *,std::allocator<std::vector<FrameDescription>> &)
0x14000368d  mov     [rsp+78h+var_50], 0
0x140003696  mov     r9, rbx
0x140003699  mov     r8, rbp
0x14000369c  mov     rdx, rdi
0x14000369f  mov     rcx, rsi
0x1400036a2  call    ?_Change_array@?$vector@V?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@V?$allocator@V?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@@2@@std@@AEAAXQEAV?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@2@_K1@Z; std::vector<std::vector<FrameDescription>>::_Change_array(std::vector<FrameDescription> * const,unsigned __int64,unsigned __int64)
0x1400036a7  lea     rcx, [rsp+78h+var_58]
0x1400036ac  call    ??1_Reallocation_guard@?$vector@V?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@V?$allocator@V?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@@2@@std@@QEAA@XZ; std::vector<std::vector<FrameDescription>>::_Reallocation_guard::~_Reallocation_guard(void)
0x1400036b1  mov     rax, r14
0x1400036b4  lea     r11, [rsp+78h+var_28]
0x1400036b9  mov     rbx, [r11+38h]
0x1400036bd  mov     rbp, [r11+40h]
0x1400036c1  mov     rsi, [r11+48h]
0x1400036c5  mov     rsp, r11
0x1400036c8  pop     r15
0x1400036ca  pop     r14
0x1400036cc  pop     r13
0x1400036ce  pop     r12
0x1400036d0  pop     rdi
0x1400036d1  retn
0x1400036d2  lea     rax, [rdx+rcx]
0x1400036d6  mov     rbx, rbp
0x1400036d9  cmp     rax, rbp
0x1400036dc  cmovnb  rbx, rax
0x1400036e0  cmp     rbx, r8
0x1400036e3  jbe     loc_1400035F9
0x1400036e9  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
```
