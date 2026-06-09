# std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>,std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>::_Clear_and_reserve_geometric(unsigned __int64)

- ea: `0x14000dec8`
- end: `0x14000dfd1`
- name: `?_Clear_and_reserve_geometric@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@AEAAX_K@Z`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000d104`

## callees

- `0x140002330`
- `0x140003474`
- `0x140003494`
- `0x14000d9b0`
- `0x14000dec8`
- `0x14001382c`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x14000dfbe`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x14000dfbe`

## pseudocode

```c
__int64 __fastcall std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Clear_and_reserve_geometric(
        __int64 *a1,
        unsigned __int64 a2,
        __int64 a3)
{
  unsigned __int64 v4; // rcx
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // rbx
  _QWORD *v7; // rcx
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 result; // rax

  if ( a2 > 0xFFFFFFFFFFFFFFFLL )
    std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Xlength(a1, a2, a3);
  v4 = (a1[2] - *a1) >> 4;
  v5 = v4 >> 1;
  if ( v4 <= 0xFFFFFFFFFFFFFFFLL - (v4 >> 1) )
  {
    v6 = v5 + v4;
    if ( v5 + v4 < a2 )
      v6 = a2;
  }
  else
  {
    v6 = 0xFFFFFFFFFFFFFFFLL;
  }
  if ( *a1 )
  {
    std::_Destroy_range<std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>(*a1, a1[1]);
    v7 = (_QWORD *)*a1;
    if ( ((a1[2] - *a1) & 0xFFFFFFFFFFFFFFF0uLL) >= 0x1000 )
    {
      _mm_lfence();
      if ( (unsigned __int64)v7 - *(v7 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v7 = (_QWORD *)*(v7 - 1);
    }
    operator delete(v7);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
  if ( v6 > 0xFFFFFFFFFFFFFFFLL )
    __scrt_throw_std_bad_array_new_length();
  _mm_lfence();
  v8 = 16 * v6;
  v9 = std::_Allocate<16,std::_Default_allocate_traits>(v8, a2, v5);
  *a1 = v9;
  a1[1] = v9;
  result = v8 + v9;
  a1[2] = result;
  return result;
}

```

## disassembly

```asm
0x14000dec8  mov     [rsp+arg_10], rbx
0x14000decd  mov     [rsp+arg_18], rbp
0x14000ded2  push    rdi
0x14000ded3  sub     rsp, 30h
0x14000ded7  mov     rbp, 0FFFFFFFFFFFFFFFh
0x14000dee1  mov     rdi, rcx
0x14000dee4  cmp     rdx, rbp
0x14000dee7  ja      loc_14000DFCB
0x14000deed  mov     rcx, [rcx+10h]
0x14000def1  mov     rax, rbp
0x14000def4  sub     rcx, [rdi]
0x14000def7  sar     rcx, 4
0x14000defb  mov     r8, rcx
0x14000defe  shr     r8, 1
0x14000df01  sub     rax, r8
0x14000df04  cmp     rcx, rax
0x14000df07  jbe     short loc_14000DF0E
0x14000df09  mov     rbx, rbp
0x14000df0c  jmp     short loc_14000DF19
0x14000df0e  lea     rbx, [r8+rcx]
0x14000df12  cmp     rbx, rdx
0x14000df15  cmovb   rbx, rdx
0x14000df19  cmp     qword ptr [rdi], 0
0x14000df1d  jz      short loc_14000DF79
0x14000df1f  mov     rdx, [rdi+8]
0x14000df23  mov     rcx, [rdi]
0x14000df26  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VILogWriter@DiagHubCommon@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>>>(std::shared_ptr<DiagHubCommon::ILogWriter> *,std::shared_ptr<DiagHubCommon::ILogWriter> * const,std::allocator<std::shared_ptr<DiagHubCommon::ILogWriter>> &)
0x14000df2b  mov     rcx, [rdi]
0x14000df2e  mov     rdx, [rdi+10h]
0x14000df32  sub     rdx, rcx
0x14000df35  and     rdx, 0FFFFFFFFFFFFFFF0h
0x14000df39  cmp     rdx, 1000h
0x14000df40  jb      short loc_14000DF5D
0x14000df42  lfence
0x14000df45  mov     rax, [rcx-8]
0x14000df49  add     rdx, 27h ; '''
0x14000df4d  sub     rcx, rax
0x14000df50  sub     rcx, 8
0x14000df54  cmp     rcx, 1Fh
0x14000df58  ja      short loc_14000DFAB
0x14000df5a  mov     rcx, rax; Block
0x14000df5d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000df62  mov     qword ptr [rdi], 0
0x14000df69  mov     qword ptr [rdi+8], 0
0x14000df71  mov     qword ptr [rdi+10h], 0
0x14000df79  cmp     rbx, rbp
0x14000df7c  ja      short loc_14000DFC5
0x14000df7e  lfence
0x14000df81  shl     rbx, 4
0x14000df85  mov     rcx, rbx
0x14000df88  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x14000df8d  mov     rbp, [rsp+38h+arg_18]
0x14000df92  mov     [rdi], rax
0x14000df95  mov     [rdi+8], rax
0x14000df99  add     rax, rbx
0x14000df9c  mov     rbx, [rsp+38h+arg_10]
0x14000dfa1  mov     [rdi+10h], rax
0x14000dfa5  add     rsp, 30h
0x14000dfa9  pop     rdi
0x14000dfaa  retn
0x14000dfab  xor     r9d, r9d; LineNo
0x14000dfae  mov     [rsp+38h+Reserved], 0; Reserved
0x14000dfb7  xor     r8d, r8d; FileName
0x14000dfba  xor     edx, edx; FunctionName
0x14000dfbc  xor     ecx, ecx; Expression
0x14000dfbe  call    cs:__imp__invoke_watson
0x14000dfc5  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x14000dfcb  call    ?_Xlength@?$vector@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@V?$allocator@V?$shared_ptr@VILogWriter@DiagHubCommon@@@std@@@2@@std@@CAXXZ; std::vector<std::shared_ptr<DiagHubCommon::ILogWriter>>::_Xlength(void)
```
