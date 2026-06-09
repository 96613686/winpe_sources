# CExec::EnvironmentBlockToMap(ushort const *)

- ea: `0x1400168e0`
- end: `0x140016b47`
- name: `?EnvironmentBlockToMap@CExec@@YA?AV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@UCaseInsensitiveLess@Vml@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@PEBG@Z`
- size: `615`
- prototype: `_QWORD *__fastcall(_QWORD *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x140016cc0`

## callees

- `0x140002334`
- `0x1400026b8`
- `0x1400068ac`
- `0x140008160`
- `0x14000d338`
- `0x14000e3c0`
- `0x14000e86c`
- `0x140015308`
- `0x1400168e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140016aa0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140016aa0`

## string_xrefs

- `0x140016b2f`: `onecore\vm\compute\service\cexec\lib\cexecprocess.cpp`

## pseudocode

```c
_QWORD *__fastcall CExec::EnvironmentBlockToMap(_QWORD *a1, _WORD *a2)
{
  _QWORD *v4; // rax
  __int64 v5; // rbx
  _WORD *v6; // rbp
  __int64 v7; // rax
  __int64 v8; // rbx
  _WORD *v9; // r13
  _WORD *v10; // r12
  _WORD *v11; // r15
  char *v12; // rax
  char *v13; // rsi
  __int64 v14; // rax
  __int128 v15; // xmm6
  __int64 v16; // rdx
  _QWORD *v17; // rdx
  char *v18; // rcx
  _QWORD *v20; // [rsp+28h] [rbp-B0h]
  __int64 v21; // [rsp+30h] [rbp-A8h]
  _OWORD v22[2]; // [rsp+50h] [rbp-88h] BYREF
  _QWORD *v23; // [rsp+70h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v23 = a1;
  *(_OWORD *)a1 = 0;
  *a1 = 0;
  a1[1] = 0;
  v4 = operator new(0x60u);
  *v4 = v4;
  v4[1] = v4;
  v4[2] = v4;
  *((_WORD *)v4 + 12) = 257;
  *a1 = v4;
  v5 = 0;
  if ( *a2 )
  {
    do
    {
      v6 = &a2[v5];
      if ( *v6 != 61 )
      {
        do
        {
          if ( !a2[v5] )
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x261,
              (unsigned int)"onecore\\vm\\compute\\service\\cexec\\lib\\cexecprocess.cpp",
              (const char *)0xD,
              1u);
          ++v5;
        }
        while ( a2[v5] != 61 );
      }
      v7 = v5;
      v8 = v5 + 1;
      v9 = &a2[v8];
      if ( *v9 )
      {
        do
          ++v8;
        while ( a2[v8] );
      }
      v10 = &a2[v8];
      v11 = &a2[v7];
      v21 = *a1;
      v12 = (char *)operator new(0x60u);
      v20 = v12;
      v13 = v12 + 32;
      *(_QWORD *)&v22[0] = v12 + 32;
      *((_OWORD *)v12 + 2) = 0;
      *((_QWORD *)v12 + 6) = 0;
      *((_QWORD *)v12 + 7) = 0;
      if ( v6 == v11 )
      {
        *((_QWORD *)v12 + 7) = 7;
        *(_WORD *)v13 = 0;
      }
      else
      {
        std::wstring::_Construct<1,unsigned short const *>((__int64)(v12 + 32), v6, v11 - v6);
      }
      *((_OWORD *)v13 + 2) = 0;
      *((_QWORD *)v13 + 6) = 0;
      *((_QWORD *)v13 + 7) = 0;
      if ( v9 == v10 )
      {
        *((_QWORD *)v13 + 7) = 7;
        *((_WORD *)v13 + 16) = 0;
      }
      else
      {
        std::wstring::_Construct<1,unsigned short const *>((__int64)(v13 + 32), v9, v10 - v9);
      }
      *v20 = v21;
      v20[1] = v21;
      v20[2] = v21;
      *((_WORD *)v20 + 12) = 0;
      v14 = std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(
              a1,
              v22,
              v13);
      v15 = *(_OWORD *)v14;
      v16 = *(_QWORD *)(v14 + 16);
      if ( *(_BYTE *)(v16 + 25) )
        goto LABEL_21;
      v17 = (_QWORD *)(v16 + 32);
      if ( v17[3] > 7u )
        v17 = (_QWORD *)*v17;
      v18 = *((_QWORD *)v13 + 3) <= 7u ? v13 : *(char **)v13;
      if ( (int)_o__wcsicmp(v18, v17) < 0 )
      {
LABEL_21:
        if ( a1[1] == 0x2AAAAAAAAAAAAAALL )
          std::_Throw_tree_length_error();
        v22[0] = v15;
        std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<CExec::ProcessTracker>>>>::_Insert_node(
          a1,
          (__int64)v22,
          (__int64)v20);
      }
      else
      {
        std::wstring::~wstring((char **)v13 + 4);
        std::wstring::~wstring((char **)v13);
        operator delete(v20);
      }
      v5 = v8 + 1;
    }
    while ( a2[v5] );
  }
  return a1;
}

```

## disassembly

```asm
0x1400168e0  mov     rax, rsp
0x1400168e3  push    rbx
0x1400168e4  push    rbp
0x1400168e5  push    rsi
0x1400168e6  push    rdi
0x1400168e7  push    r12
0x1400168e9  push    r13
0x1400168eb  push    r14
0x1400168ed  push    r15
0x1400168ef  sub     rsp, 98h
0x1400168f6  movaps  xmmword ptr [rax-58h], xmm6
0x1400168fa  mov     r14, rdx
0x1400168fd  mov     rdi, rcx
0x140016900  mov     [rax-68h], rcx
0x140016904  xor     r12d, r12d
0x140016907  mov     [rsp+0D8h+var_B8], r12d
0x14001690c  xorps   xmm0, xmm0
0x14001690f  movups  xmmword ptr [rcx], xmm0
0x140016912  mov     [rcx], r12
0x140016915  mov     [rcx+8], r12
0x140016919  lea     ecx, [r12+60h]; Size
0x14001691e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140016923  mov     [rax], rax
0x140016926  mov     [rax+8], rax
0x14001692a  mov     [rax+10h], rax
0x14001692e  mov     word ptr [rax+18h], 101h
0x140016934  mov     [rdi], rax
0x140016937  mov     [rsp+0D8h+var_B8], 1; unsigned int
0x14001693f  mov     ebx, r12d
0x140016942  cmp     [r14], r12w
0x140016946  jz      loc_140016B02
0x14001694c  lea     rbp, [r14+rbx*2]
0x140016950  cmp     word ptr [rbp+0], 3Dh ; '='
0x140016955  jz      short loc_14001696D
0x140016957  cmp     [r14+rbx*2], r12w
0x14001695c  jz      loc_140016B21
0x140016962  inc     rbx
0x140016965  cmp     word ptr [r14+rbx*2], 3Dh ; '='
0x14001696b  jnz     short loc_140016957
0x14001696d  mov     rax, rbx
0x140016970  inc     rbx
0x140016973  lea     r13, [r14+rbx*2]
0x140016977  cmp     [r13+0], r12w
0x14001697c  jz      short loc_140016988
0x14001697e  inc     rbx
0x140016981  cmp     [r14+rbx*2], r12w
0x140016986  jnz     short loc_14001697E
0x140016988  lea     r12, [r14+rbx*2]
0x14001698c  lea     r15, [r14+rax*2]
0x140016990  mov     rax, [rdi]
0x140016993  mov     [rsp+0D8h+var_A8], rax
0x140016998  mov     [rsp+0D8h+var_A0], rdi
0x14001699d  mov     [rsp+0D8h+var_98], 0
0x1400169a6  mov     ecx, 60h ; '`'; Size
0x1400169ab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400169b0  mov     [rsp+0D8h+var_B0], rax
0x1400169b5  mov     [rsp+0D8h+var_98], rax
0x1400169ba  lea     rsi, [rax+20h]
0x1400169be  mov     qword ptr [rsp+0D8h+var_88], rsi
0x1400169c3  xorps   xmm0, xmm0
0x1400169c6  movups  xmmword ptr [rsi], xmm0
0x1400169c9  mov     qword ptr [rsi+10h], 0
0x1400169d1  mov     qword ptr [rsi+18h], 0
0x1400169d9  cmp     rbp, r15
0x1400169dc  jnz     short loc_1400169ED
0x1400169de  mov     qword ptr [rsi+18h], 7
0x1400169e6  xor     eax, eax
0x1400169e8  mov     [rsi], ax
0x1400169eb  jmp     short loc_140016A02
0x1400169ed  sub     r15, rbp
0x1400169f0  sar     r15, 1
0x1400169f3  mov     r8, r15
0x1400169f6  mov     rdx, rbp
0x1400169f9  mov     rcx, rsi
0x1400169fc  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140016a01  nop
0x140016a02  lea     r15, [rsi+20h]
0x140016a06  xorps   xmm0, xmm0
0x140016a09  movups  xmmword ptr [r15], xmm0
0x140016a0d  mov     qword ptr [r15+10h], 0
0x140016a15  mov     qword ptr [r15+18h], 0
0x140016a1d  cmp     r13, r12
0x140016a20  jnz     short loc_140016A33
0x140016a22  mov     qword ptr [r15+18h], 7
0x140016a2a  xor     r12d, r12d
0x140016a2d  mov     [r15], r12w
0x140016a31  jmp     short loc_140016A4A
0x140016a33  sub     r12, r13
0x140016a36  sar     r12, 1
0x140016a39  mov     r8, r12
0x140016a3c  mov     rdx, r13
0x140016a3f  mov     rcx, r15
0x140016a42  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140016a47  xor     r12d, r12d
0x140016a4a  mov     rbp, [rsp+0D8h+var_B0]
0x140016a4f  mov     rax, [rsp+0D8h+var_A8]
0x140016a54  mov     [rbp+0], rax
0x140016a58  mov     [rbp+8], rax
0x140016a5c  mov     [rbp+10h], rax
0x140016a60  mov     word ptr [rbp+18h], 0
0x140016a66  mov     r8, rsi
0x140016a69  lea     rdx, [rsp+0D8h+var_88]
0x140016a6e  mov     rcx, rdi
0x140016a71  call    ??$_Find_lower_bound@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@UCaseInsensitiveLess@Vml@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,Vml::CaseInsensitiveLess,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Find_lower_bound<std::wstring>(std::wstring const &)
0x140016a76  movups  xmm6, xmmword ptr [rax]
0x140016a79  mov     rdx, [rax+10h]
0x140016a7d  cmp     [rdx+19h], r12b
0x140016a81  jnz     short loc_140016AC9
0x140016a83  add     rdx, 20h ; ' '
0x140016a87  cmp     qword ptr [rdx+18h], 7
0x140016a8c  jbe     short loc_140016A91
0x140016a8e  mov     rdx, [rdx]
0x140016a91  cmp     qword ptr [rsi+18h], 7
0x140016a96  jbe     short loc_140016A9D
0x140016a98  mov     rcx, [rsi]
0x140016a9b  jmp     short loc_140016AA0
0x140016a9d  mov     rcx, rsi
0x140016aa0  call    cs:__imp__o__wcsicmp
0x140016aa6  test    eax, eax
0x140016aa8  js      short loc_140016AC9
0x140016aaa  mov     rcx, r15
0x140016aad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140016ab2  mov     rcx, rsi
0x140016ab5  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140016aba  mov     edx, 60h ; '`'; unsigned __int64
0x140016abf  mov     rcx, rbp; void *
0x140016ac2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140016ac7  jmp     short loc_140016AF4
0x140016ac9  mov     rax, 2AAAAAAAAAAAAAAh
0x140016ad3  cmp     [rdi+8], rax
0x140016ad7  jz      short loc_140016B41
0x140016ad9  mov     [rsp+0D8h+var_98], r12
0x140016ade  movdqu  [rsp+0D8h+var_88], xmm6
0x140016ae4  mov     r8, rbp
0x140016ae7  lea     rdx, [rsp+0D8h+var_88]
0x140016aec  mov     rcx, rdi
0x140016aef  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<CExec::ProcessTracker>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<ulong const,std::shared_ptr<CExec::ProcessTracker>>,void *> *>,std::_Tree_node<std::pair<ulong const,std::shared_ptr<CExec::ProcessTracker>>,void *> * const)
0x140016af4  inc     rbx
0x140016af7  cmp     [r14+rbx*2], r12w
0x140016afc  jnz     loc_14001694C
0x140016b02  mov     rax, rdi
0x140016b05  movaps  xmm6, [rsp+0D8h+var_58]
0x140016b0d  add     rsp, 98h
0x140016b14  pop     r15
0x140016b16  pop     r14
0x140016b18  pop     r13
0x140016b1a  pop     r12
0x140016b1c  pop     rdi
0x140016b1d  pop     rsi
0x140016b1e  pop     rbp
0x140016b1f  pop     rbx
0x140016b20  retn
0x140016b21  mov     rcx, [rsp+0D8h]; this
0x140016b29  mov     r9d, 0Dh; char *
0x140016b2f  lea     r8, aOnecoreVmCompu_2; "onecore\\vm\\compute\\service\\cexec\\l"...
0x140016b36  mov     edx, 261h; void *
0x140016b3b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140016b41  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
