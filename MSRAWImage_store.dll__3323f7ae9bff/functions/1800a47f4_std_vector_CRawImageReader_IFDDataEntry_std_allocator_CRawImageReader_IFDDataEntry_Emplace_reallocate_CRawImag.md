# std::vector<CRawImageReader::IFDDataEntry,std::allocator<CRawImageReader::IFDDataEntry>>::_Emplace_reallocate<CRawImageReader::IFDDataEntry const &>(CRawImageReader::IFDDataEntry * const,CRawImageReader::IFDDataEntry const &)

- ea: `0x1800a47f4`
- end: `0x1800a4976`
- name: `??$_Emplace_reallocate@AEBUIFDDataEntry@CRawImageReader@@@?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@AEAAPEAUIFDDataEntry@CRawImageReader@@QEAU23@AEBU23@@Z`
- size: `386`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800a46a0`

## callees

- `0x1800a4510`
- `0x1800a47f4`
- `0x1800a4cb4`
- `0x1800a5160`
- `0x1800a5500`
- `0x1800af004`
- `0x1800af23c`
- `0x1800af370`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
CRawImageReader::IFDDataEntry *__fastcall std::vector<CRawImageReader::IFDDataEntry>::_Emplace_reallocate<CRawImageReader::IFDDataEntry const &>(
        __int64 *a1,
        __int64 a2,
        const struct CRawImageReader::IFDDataEntry *a3)
{
  __int64 v6; // r9
  __int64 v7; // r14
  unsigned __int64 v8; // rbp
  unsigned __int64 v9; // rbp
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  unsigned __int64 v12; // rbx
  __int64 v13; // rdi
  CRawImageReader::IFDDataEntry *v14; // r14
  __int64 v15; // rdx
  char *v16; // r8
  __int64 v17; // rcx
  _QWORD v19[2]; // [rsp+28h] [rbp-50h] BYREF
  unsigned __int64 v20; // [rsp+38h] [rbp-40h]
  __int64 v21; // [rsp+40h] [rbp-38h]
  char *v22; // [rsp+48h] [rbp-30h]

  v6 = a2 - *a1;
  v7 = v6 / 40;
  v8 = 0xCCCCCCCCCCCCCCCDuLL * ((a1[1] - *a1) >> 3);
  if ( v8 == 0x666666666666666LL )
    std::vector<unsigned int>::_Xlength(a1, (unsigned __int128)(v6 * (__int128)0x6666666666666667LL) >> 64);
  v9 = v8 + 1;
  v10 = 0xCCCCCCCCCCCCCCCDuLL * ((a1[2] - *a1) >> 3);
  v11 = v10 >> 1;
  if ( v10 <= 0x666666666666666LL - (v10 >> 1) )
  {
    v12 = v9;
    if ( v11 + v10 >= v9 )
      v12 = v11 + v10;
    if ( v12 > 0x666666666666666LL )
      std::_Throw_bad_array_new_length();
  }
  else
  {
    v12 = 0x666666666666666LL;
  }
  v13 = std::_Allocate<16,std::_Default_allocate_traits>(40 * v12);
  v14 = (CRawImageReader::IFDDataEntry *)(v13 + 40 * v7);
  v19[0] = a1;
  v19[1] = v13;
  v20 = v12;
  v22 = (char *)v14 + 40;
  CRawImageReader::IFDDataEntry::IFDDataEntry(v14, a3);
  v21 = (__int64)v14;
  v15 = a1[1];
  v16 = (char *)v13;
  v17 = *a1;
  if ( a2 != v15 )
  {
    std::_Uninitialized_move<CRawImageReader::IFDDataEntry *>(v17, a2, v13);
    v21 = v13;
    v16 = (char *)v14 + 40;
    v15 = a1[1];
    v17 = a2;
  }
  std::_Uninitialized_move<CRawImageReader::IFDDataEntry *>(v17, v15, v16);
  std::vector<CRawImageReader::IFDDataEntry>::_Change_array(a1, v13, v9, v12, -2, v19[0], 0, v20, v21, v22);
  std::vector<CRawImageReader::IFDDataEntry>::_Reallocation_guard::~_Reallocation_guard(v19);
  return v14;
}

```

## disassembly

```asm
0x1800a47f4  mov     rax, rsp
0x1800a47f7  push    rdi
0x1800a47f8  push    r12
0x1800a47fa  push    r13
0x1800a47fc  push    r14
0x1800a47fe  push    r15
0x1800a4800  sub     rsp, 50h
0x1800a4804  mov     qword ptr [rax-58h], 0FFFFFFFFFFFFFFFEh
0x1800a480c  mov     [rax+8], rbx
0x1800a4810  mov     [rax+10h], rbp
0x1800a4814  mov     [rax+18h], rsi
0x1800a4818  mov     r13, r8
0x1800a481b  mov     r15, rdx
0x1800a481e  mov     rsi, rcx
0x1800a4821  mov     r9, rdx
0x1800a4824  sub     r9, [rcx]
0x1800a4827  mov     rax, 6666666666666667h
0x1800a4831  imul    r9
0x1800a4834  mov     r14, rdx
0x1800a4837  sar     r14, 4
0x1800a483b  mov     rax, r14
0x1800a483e  shr     rax, 3Fh
0x1800a4842  add     r14, rax
0x1800a4845  mov     rbp, [rcx+8]
0x1800a4849  sub     rbp, [rcx]
0x1800a484c  sar     rbp, 3
0x1800a4850  mov     rax, 0CCCCCCCCCCCCCCCDh
0x1800a485a  imul    rbp, rax
0x1800a485e  mov     r8, 666666666666666h
0x1800a4868  cmp     rbp, r8
0x1800a486b  jz      loc_1800A496A
0x1800a4871  inc     rbp
0x1800a4874  mov     rcx, [rcx+10h]
0x1800a4878  sub     rcx, [rsi]
0x1800a487b  sar     rcx, 3
0x1800a487f  imul    rcx, rax
0x1800a4883  mov     rdx, rcx
0x1800a4886  shr     rdx, 1
0x1800a4889  mov     rax, r8
0x1800a488c  sub     rax, rdx
0x1800a488f  cmp     rcx, rax
0x1800a4892  jbe     loc_1800A4952
0x1800a4898  mov     rbx, r8
0x1800a489b  lea     rcx, [rbx+rbx*4]
0x1800a489f  shl     rcx, 3
0x1800a48a3  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x1800a48a8  mov     rdi, rax
0x1800a48ab  lea     rcx, [r14+r14*4]
0x1800a48af  lea     r14, [rax+rcx*8]
0x1800a48b3  lea     r12, [r14+28h]
0x1800a48b7  mov     [rsp+78h+var_50], rsi
0x1800a48bc  mov     [rsp+78h+var_48], rax
0x1800a48c1  mov     [rsp+78h+var_40], rbx
0x1800a48c6  mov     [rsp+78h+var_38], r12
0x1800a48cb  mov     [rsp+78h+var_30], r12
0x1800a48d0  mov     rdx, r13; struct CRawImageReader::IFDDataEntry *
0x1800a48d3  mov     rcx, r14; this
0x1800a48d6  call    ??0IFDDataEntry@CRawImageReader@@QEAA@AEBU01@@Z; CRawImageReader::IFDDataEntry::IFDDataEntry(CRawImageReader::IFDDataEntry const &)
0x1800a48db  mov     [rsp+78h+var_38], r14
0x1800a48e0  mov     rdx, [rsi+8]
0x1800a48e4  mov     r8, rdi
0x1800a48e7  mov     rcx, [rsi]
0x1800a48ea  cmp     r15, rdx
0x1800a48ed  jz      short loc_1800A4906
0x1800a48ef  mov     rdx, r15
0x1800a48f2  call    ??$_Uninitialized_move@PEAUIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@YAPEAUIFDDataEntry@CRawImageReader@@QEAU12@0PEAU12@AEAV?$allocator@UIFDDataEntry@CRawImageReader@@@0@@Z; std::_Uninitialized_move<CRawImageReader::IFDDataEntry *>(CRawImageReader::IFDDataEntry * const,CRawImageReader::IFDDataEntry * const,CRawImageReader::IFDDataEntry *,std::allocator<CRawImageReader::IFDDataEntry> &)
0x1800a48f7  mov     [rsp+78h+var_38], rdi
0x1800a48fc  mov     r8, r12
0x1800a48ff  mov     rdx, [rsi+8]
0x1800a4903  mov     rcx, r15
0x1800a4906  call    ??$_Uninitialized_move@PEAUIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@YAPEAUIFDDataEntry@CRawImageReader@@QEAU12@0PEAU12@AEAV?$allocator@UIFDDataEntry@CRawImageReader@@@0@@Z; std::_Uninitialized_move<CRawImageReader::IFDDataEntry *>(CRawImageReader::IFDDataEntry * const,CRawImageReader::IFDDataEntry * const,CRawImageReader::IFDDataEntry *,std::allocator<CRawImageReader::IFDDataEntry> &)
0x1800a490b  mov     [rsp+78h+var_48], 0
0x1800a4914  mov     r9, rbx
0x1800a4917  mov     r8, rbp
0x1800a491a  mov     rdx, rdi
0x1800a491d  mov     rcx, rsi
0x1800a4920  call    ?_Change_array@?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@AEAAXQEAUIFDDataEntry@CRawImageReader@@_K1@Z; std::vector<CRawImageReader::IFDDataEntry>::_Change_array(CRawImageReader::IFDDataEntry * const,unsigned __int64,unsigned __int64)
0x1800a4925  nop
0x1800a4926  lea     rcx, [rsp+78h+var_50]
0x1800a492b  call    ??1_Reallocation_guard@?$vector@UIFDDataEntry@CRawImageReader@@V?$allocator@UIFDDataEntry@CRawImageReader@@@std@@@std@@QEAA@XZ; std::vector<CRawImageReader::IFDDataEntry>::_Reallocation_guard::~_Reallocation_guard(void)
0x1800a4930  mov     rax, r14
0x1800a4933  lea     r11, [rsp+78h+var_28]
0x1800a4938  mov     rbx, [r11+30h]
0x1800a493c  mov     rbp, [r11+38h]
0x1800a4940  mov     rsi, [r11+40h]
0x1800a4944  mov     rsp, r11
0x1800a4947  pop     r15
0x1800a4949  pop     r14
0x1800a494b  pop     r13
0x1800a494d  pop     r12
0x1800a494f  pop     rdi
0x1800a4950  retn
0x1800a4952  lea     rax, [rdx+rcx]
0x1800a4956  mov     rbx, rbp
0x1800a4959  cmp     rax, rbp
0x1800a495c  cmovnb  rbx, rax
0x1800a4960  cmp     rbx, r8
0x1800a4963  ja      short loc_1800A4970
0x1800a4965  jmp     loc_1800A489B
0x1800a496a  call    ?_Xlength@?$vector@IV?$allocator@I@std@@@std@@CAXXZ; std::vector<uint>::_Xlength(void)
0x1800a4970  call    ?_Throw_bad_array_new_length@std@@YAXXZ; std::_Throw_bad_array_new_length(void)
```
