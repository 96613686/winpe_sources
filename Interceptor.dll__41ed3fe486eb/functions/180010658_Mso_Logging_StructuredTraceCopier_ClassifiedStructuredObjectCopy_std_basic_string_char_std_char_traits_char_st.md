# Mso::Logging::StructuredTraceCopier::ClassifiedStructuredObjectCopy<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>::ClassifiedStructuredObjectCopy<std::basic_string<char,std::char_traits<char>,std::allocator<char>>>(Mso::Diagnostics::ClassifiedStructuredObject<std::basic_string<char,std::char_traits<char>,std::allocator<char>>> const &)

- ea: `0x180010658`
- end: `0x180010825`
- name: `??0?$ClassifiedStructuredObjectCopy@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@StructuredTraceCopier@Logging@Mso@@QEAA@AEBU?$ClassifiedStructuredObject@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Diagnostics@3@@Z`
- size: `461`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18000f06c`

## callees

- `0x180001bac`
- `0x180005224`
- `0x18000a208`
- `0x18000a2ec`
- `0x18000ab0c`
- `0x180010658`
- `0x18002b3c0`
- `0x18002b780`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001080c`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x18001080c`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Mso::Logging::StructuredTraceCopier::ClassifiedStructuredObjectCopy<std::string>::ClassifiedStructuredObjectCopy<std::string>(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // r8
  _QWORD *v7; // r14
  _QWORD *v8; // rdx
  __int16 v9; // r12
  _QWORD *v10; // rdi
  unsigned __int64 v11; // rbp
  __int64 v12; // rsi
  size_t v13; // rcx
  void *v14; // rax

  *(_QWORD *)a1 = &Mso::Logging::StructuredTraceCopier::ClassifiedStructuredObjectCopy<std::string>::`vftable';
  v4 = (_QWORD *)(a1 + 8);
  v5 = a2[1];
  *(_OWORD *)(a1 + 8) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  v6 = -1;
  do
    ++v6;
  while ( *(_BYTE *)(v5 + v6) );
  std::string::_Construct<1,char const *>(a1 + 8);
  *(_OWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 7;
  *(_WORD *)(a1 + 40) = 0;
  v7 = (_QWORD *)(a1 + 72);
  v8 = a2 + 2;
  *(_OWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 0;
  if ( a2[5] > 0xFu )
    v8 = (_QWORD *)*v8;
  std::string::_Construct<2,char const *>(a1 + 72, v8, a2[4]);
  v9 = (*(__int64 (__fastcall **)(_QWORD *))(*a2 + 24LL))(a2);
  if ( v4[3] > 0xFu )
    v4 = (_QWORD *)*v4;
  *(_QWORD *)(a1 + 104) = &Mso::Diagnostics::ClassifiedStructuredObject<std::string>::`vftable';
  *(_QWORD *)(a1 + 112) = v4;
  v10 = (_QWORD *)(a1 + 120);
  *(_OWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 136) = 0;
  *(_QWORD *)(a1 + 144) = 0;
  v11 = *(_QWORD *)(a1 + 88);
  if ( *(_QWORD *)(a1 + 96) > 0xFu )
    v7 = (_QWORD *)*v7;
  v12 = 0x7FFFFFFFFFFFFFFFLL;
  if ( v11 > 0x7FFFFFFFFFFFFFFFLL )
    std::_Xlen_string();
  if ( v11 > 0xF )
  {
    if ( (v11 | 0xF) <= 0x7FFFFFFFFFFFFFFFLL )
    {
      v12 = v11 | 0xF;
      if ( (v11 | 0xF) < 0x16 )
        v12 = 22;
    }
    v13 = v12 + 1;
    if ( v12 == -1 )
    {
      v14 = 0;
    }
    else
    {
      _mm_lfence();
      if ( v13 < 0x1000 )
      {
        v14 = malloc(v13);
        if ( !v14 )
          std::_Xbad_alloc();
      }
      else
      {
        v14 = (void *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v13);
      }
    }
    *v10 = v14;
    *(_QWORD *)(a1 + 136) = v11;
    *(_QWORD *)(a1 + 144) = v12;
    memmove(v14, v7, v11 + 1);
  }
  else
  {
    *(_QWORD *)(a1 + 136) = v11;
    *(_QWORD *)(a1 + 144) = 15;
    *(_OWORD *)v10 = *(_OWORD *)v7;
  }
  *(_WORD *)(a1 + 152) = v9;
  *(_OWORD *)(a1 + 160) = 0;
  *(_QWORD *)(a1 + 176) = 0;
  *(_QWORD *)(a1 + 184) = 7;
  *(_WORD *)(a1 + 160) = 0;
  return a1;
}

```

## disassembly

```asm
0x180010658  mov     [rsp+arg_10], rbx
0x18001065d  mov     [rsp+arg_0], rcx
0x180010662  push    rbp
0x180010663  push    rsi
0x180010664  push    rdi
0x180010665  push    r12
0x180010667  push    r13
0x180010669  push    r14
0x18001066b  push    r15
0x18001066d  sub     rsp, 20h
0x180010671  mov     rbx, rdx
0x180010674  mov     r15, rcx
0x180010677  xor     r13d, r13d
0x18001067a  lea     rax, ??_7?$ClassifiedStructuredObjectCopy@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@StructuredTraceCopier@Logging@Mso@@6B@; const Mso::Logging::StructuredTraceCopier::ClassifiedStructuredObjectCopy<std::string>::`vftable'
0x180010681  mov     [rcx], rax
0x180010684  lea     rdi, [rcx+8]
0x180010688  mov     [rsp+58h+arg_8], rdi
0x18001068d  mov     rdx, [rdx+8]
0x180010691  xorps   xmm0, xmm0
0x180010694  movups  xmmword ptr [rdi], xmm0
0x180010697  mov     [rdi+10h], r13
0x18001069b  mov     [rdi+18h], r13
0x18001069f  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800106a3  inc     r8
0x1800106a6  cmp     [rdx+r8], r13b
0x1800106aa  jnz     short loc_1800106A3
0x1800106ac  mov     rcx, rdi
0x1800106af  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x1800106b4  xorps   xmm0, xmm0
0x1800106b7  movups  xmmword ptr [r15+28h], xmm0
0x1800106bc  mov     [r15+38h], r13
0x1800106c0  mov     qword ptr [r15+40h], 7
0x1800106c8  mov     [r15+28h], r13w
0x1800106cd  lea     r14, [r15+48h]
0x1800106d1  mov     [rsp+58h+arg_8], r14
0x1800106d6  lea     rdx, [rbx+10h]
0x1800106da  movups  xmmword ptr [r14], xmm0
0x1800106de  mov     [r14+10h], r13
0x1800106e2  mov     [r14+18h], r13
0x1800106e6  mov     r8, [rdx+10h]
0x1800106ea  cmp     qword ptr [rdx+18h], 0Fh
0x1800106ef  jbe     short loc_1800106F4
0x1800106f1  mov     rdx, [rdx]
0x1800106f4  mov     rcx, r14
0x1800106f7  call    ??$_Construct@$01PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<2,char const *>(char const * const,unsigned __int64)
0x1800106fc  mov     rax, [rbx]
0x1800106ff  mov     rcx, rbx
0x180010702  mov     rax, [rax+18h]
0x180010706  call    cs:__guard_dispatch_icall_fptr
0x18001070c  movzx   r12d, ax
0x180010710  mov     ecx, 0Fh
0x180010715  cmp     [rdi+18h], rcx
0x180010719  jbe     short loc_18001071E
0x18001071b  mov     rdi, [rdi]
0x18001071e  lea     rbx, [r15+68h]
0x180010722  mov     [rsp+58h+arg_8], rbx
0x180010727  lea     rax, ??_7?$ClassifiedStructuredObject@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredObject<std::string>::`vftable'
0x18001072e  mov     [rbx], rax
0x180010731  mov     [rbx+8], rdi
0x180010735  lea     rdi, [rbx+10h]
0x180010739  mov     [rsp+58h+arg_8], rdi
0x18001073e  xorps   xmm0, xmm0
0x180010741  movups  xmmword ptr [rdi], xmm0
0x180010744  mov     [rdi+10h], r13
0x180010748  mov     [rdi+18h], r13
0x18001074c  mov     rbp, [r14+10h]
0x180010750  cmp     [r14+18h], rcx
0x180010754  jbe     short loc_180010759
0x180010756  mov     r14, [r14]
0x180010759  mov     rsi, 7FFFFFFFFFFFFFFFh
0x180010763  cmp     rbp, rsi
0x180010766  ja      loc_180010819
0x18001076c  cmp     rbp, rcx
0x18001076f  ja      short loc_180010783
0x180010771  mov     [rdi+10h], rbp
0x180010775  mov     [rdi+18h], rcx
0x180010779  movups  xmm0, xmmword ptr [r14]
0x18001077d  movdqu  xmmword ptr [rdi], xmm0
0x180010781  jmp     short loc_1800107C4
0x180010783  mov     rax, rbp
0x180010786  or      rax, rcx
0x180010789  cmp     rax, rsi
0x18001078c  ja      short loc_18001079D
0x18001078e  mov     rsi, rax
0x180010791  mov     ecx, 16h
0x180010796  cmp     rax, rcx
0x180010799  cmovb   rsi, rcx
0x18001079d  lea     rcx, [rsi+1]; Size
0x1800107a1  test    rcx, rcx
0x1800107a4  jnz     short loc_1800107F9
0x1800107a6  mov     rax, r13
0x1800107a9  mov     [rdi], rax
0x1800107ac  mov     [rdi+10h], rbp
0x1800107b0  mov     [rdi+18h], rsi
0x1800107b4  lea     r8, [rbp+1]; Size
0x1800107b8  mov     rdx, r14; Src
0x1800107bb  mov     rcx, rax; void *
0x1800107be  call    memmove
0x1800107c3  nop
0x1800107c4  mov     [rbx+30h], r12w
0x1800107c9  xorps   xmm0, xmm0
0x1800107cc  movups  xmmword ptr [rbx+38h], xmm0
0x1800107d0  mov     [rbx+48h], r13
0x1800107d4  mov     qword ptr [rbx+50h], 7
0x1800107dc  mov     [rbx+38h], r13w
0x1800107e1  mov     rax, r15
0x1800107e4  mov     rbx, [rsp+58h+arg_10]
0x1800107e9  add     rsp, 20h
0x1800107ed  pop     r15
0x1800107ef  pop     r14
0x1800107f1  pop     r13
0x1800107f3  pop     r12
0x1800107f5  pop     rdi
0x1800107f6  pop     rsi
0x1800107f7  pop     rbp
0x1800107f8  retn
0x1800107f9  lfence
0x1800107fc  cmp     rcx, 1000h
0x180010803  jb      short loc_18001080C
0x180010805  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x18001080a  jmp     short loc_1800107A9
0x18001080c  call    cs:__imp_malloc
0x180010812  test    rax, rax
0x180010815  jz      short loc_18001081F
0x180010817  jmp     short loc_1800107A9
0x180010819  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18001081f  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
