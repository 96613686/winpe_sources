# ArgumentWriter::FormatArguments<ushort,ushort,ushort,ulong>(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &,ushort const &,ushort const &,ushort const &,ulong const &)

- ea: `0x1800246a0`
- end: `0x180024883`
- name: `??$FormatArguments@GGGK@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBG22AEBK@Z`
- size: `483`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180024108`

## callees

- `0x180001bc0`
- `0x180001f38`
- `0x180003f4c`
- `0x180004544`
- `0x1800045ec`
- `0x1800246a0`
- `0x180024a58`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180024870`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180024870`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180024877`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180024877`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ArgumentWriter::FormatArguments<unsigned short,unsigned short,unsigned short,unsigned long>(
        __int64 a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        _QWORD *a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  unsigned __int16 *v10; // rsi
  __m128i si128; // xmm6
  unsigned __int16 v13; // r8
  unsigned __int16 *v14; // r15
  __int64 v15; // r8
  void *v17; // rcx
  unsigned __int16 *v18; // [rsp+48h] [rbp-59h] BYREF
  __int64 v19; // [rsp+58h] [rbp-49h]
  __int64 v20; // [rsp+60h] [rbp-41h]
  __int64 v21; // [rsp+68h] [rbp-39h]
  void *Block[2]; // [rsp+70h] [rbp-31h] BYREF
  __m128i v23; // [rsp+80h] [rbp-21h]

  v10 = a2;
  v21 = a1;
  v20 = a7;
  v19 = a8;
  if ( a2 >= a3 )
  {
LABEL_12:
    *(_OWORD *)a1 = 0;
    *(_QWORD *)(a1 + 16) = 0;
    *(_QWORD *)(a1 + 24) = 0;
    v15 = a4[2];
    if ( a4[3] > 7u )
      a4 = (_QWORD *)*a4;
    std::wstring::_Construct<2,wchar_t const *>(a1, a4, v15);
    return a1;
  }
  _mm_lfence();
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  while ( 1 )
  {
    *(_OWORD *)Block = 0;
    v23 = si128;
    LOWORD(Block[0]) = 0;
    v13 = *v10;
    v14 = v10 + 1;
    v10 = v14;
    v18 = v14;
    if ( v13 != 37 )
    {
      std::wstring::append(a4);
      goto LABEL_11;
    }
    if ( v14 == a3 || *v14 != 37 )
      break;
    std::wstring::append(a4);
    v10 = v14 + 1;
LABEL_11:
    std::wstring::_Tidy_deallocate(Block);
    if ( v10 >= a3 )
      goto LABEL_12;
  }
  if ( !ArgumentWriter::TryParseFormatSpecificationField((unsigned __int64 *)&v18, a3, a4, (__int64)Block) )
  {
    v10 = v18;
    goto LABEL_11;
  }
  _mm_lfence();
  OFormatHelper::FormatNumber(a4, (wchar_t *)Block);
  ArgumentWriter::FormatArguments<unsigned short,unsigned short,unsigned long>(a1, v18, a3, a4, a6, v20, v19);
  if ( v23.m128i_i64[1] > 7uLL )
  {
    v17 = Block[0];
    if ( (unsigned __int64)(2 * v23.m128i_i64[1] + 2) >= 0x1000 )
    {
      v17 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v17 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v17);
  }
  return a1;
}

```

## disassembly

```asm
0x1800246a0  mov     rax, rsp
0x1800246a3  mov     [rax+18h], rbx
0x1800246a7  push    rbp
0x1800246a8  push    rsi
0x1800246a9  push    rdi
0x1800246aa  push    r12
0x1800246ac  push    r13
0x1800246ae  push    r14
0x1800246b0  push    r15
0x1800246b2  lea     rbp, [rax-3Fh]
0x1800246b6  sub     rsp, 0A0h
0x1800246bd  movaps  xmmword ptr [rax-48h], xmm6
0x1800246c1  mov     rax, cs:__security_cookie
0x1800246c8  xor     rax, rsp
0x1800246cb  mov     [rbp+37h+var_48], rax
0x1800246cf  mov     rbx, r9
0x1800246d2  mov     r14, r8
0x1800246d5  mov     rsi, rdx
0x1800246d8  mov     rdi, rcx
0x1800246db  mov     [rbp+37h+var_70], rcx
0x1800246df  mov     r12, [rbp+37h+arg_20]
0x1800246e3  mov     r13, [rbp+37h+arg_28]
0x1800246e7  mov     rax, [rbp+37h+arg_30]
0x1800246eb  mov     [rbp+37h+var_78], rax
0x1800246ef  mov     rax, [rbp+37h+arg_38]
0x1800246f3  mov     [rbp+37h+var_80], rax
0x1800246f7  xor     r15d, r15d
0x1800246fa  cmp     rdx, r8
0x1800246fd  jnb     loc_18002479A
0x180024703  lfence
0x180024706  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18002470e  mov     eax, 25h ; '%'
0x180024713  xorps   xmm0, xmm0
0x180024716  movups  xmmword ptr [rbp+37h+Block], xmm0
0x18002471a  movdqu  [rbp+37h+var_58], xmm6
0x18002471f  mov     word ptr [rbp+37h+Block], r15w
0x180024724  movzx   r8d, word ptr [rsi]
0x180024728  lea     r15, [rsi+2]
0x18002472c  mov     rsi, r15
0x18002472f  mov     [rbp+37h+var_90], r15
0x180024733  cmp     r8w, ax
0x180024737  jz      short loc_180024749
0x180024739  lea     edx, [rax-24h]
0x18002473c  mov     rcx, rbx; Src
0x18002473f  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180024744  xor     r15d, r15d
0x180024747  jmp     short loc_180024788
0x180024749  cmp     r15, r14
0x18002474c  jz      short loc_18002476A
0x18002474e  cmp     [r15], ax
0x180024752  jnz     short loc_18002476A
0x180024754  mov     r8d, eax
0x180024757  mov     edx, 1
0x18002475c  mov     rcx, rbx; Src
0x18002475f  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180024764  lea     rsi, [r15+2]
0x180024768  jmp     short loc_180024744
0x18002476a  lea     r9, [rbp+37h+Block]
0x18002476e  mov     r8, rbx
0x180024771  mov     rdx, r14
0x180024774  lea     rcx, [rbp+37h+var_90]
0x180024778  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x18002477d  xor     r15d, r15d
0x180024780  test    al, al
0x180024782  jnz     short loc_1800247F1
0x180024784  mov     rsi, [rbp+37h+var_90]
0x180024788  lea     rcx, [rbp+37h+Block]
0x18002478c  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180024791  cmp     rsi, r14
0x180024794  jb      loc_18002470E
0x18002479a  xorps   xmm0, xmm0
0x18002479d  movups  xmmword ptr [rdi], xmm0
0x1800247a0  mov     [rdi+10h], r15
0x1800247a4  mov     [rdi+18h], r15
0x1800247a8  mov     r8, [rbx+10h]
0x1800247ac  cmp     qword ptr [rbx+18h], 7
0x1800247b1  jbe     short loc_1800247B6
0x1800247b3  mov     rbx, [rbx]
0x1800247b6  mov     rdx, rbx
0x1800247b9  mov     rcx, rdi
0x1800247bc  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800247c1  nop
0x1800247c2  mov     rax, rdi
0x1800247c5  mov     rcx, [rbp+37h+var_48]
0x1800247c9  xor     rcx, rsp; StackCookie
0x1800247cc  call    __security_check_cookie
0x1800247d1  lea     r11, [rsp+0D0h+var_30]
0x1800247d9  mov     rbx, [r11+50h]
0x1800247dd  movaps  xmm6, xmmword ptr [r11-10h]
0x1800247e2  mov     rsp, r11
0x1800247e5  pop     r15
0x1800247e7  pop     r14
0x1800247e9  pop     r13
0x1800247eb  pop     r12
0x1800247ed  pop     rdi
0x1800247ee  pop     rsi
0x1800247ef  pop     rbp
0x1800247f0  retn
0x1800247f1  lfence
0x1800247f4  movzx   r8d, word ptr [r12]
0x1800247f9  lea     rdx, [rbp+37h+Block]; Format
0x1800247fd  mov     rcx, rbx; Src
0x180024800  call    ?FormatNumber@OFormatHelper@@SAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV23@_K@Z; OFormatHelper::FormatNumber(std::wstring &,std::wstring const &,unsigned __int64)
0x180024805  mov     rax, [rbp+37h+var_80]
0x180024809  mov     [rsp+0D0h+var_A0], rax
0x18002480e  mov     rax, [rbp+37h+var_78]
0x180024812  mov     [rsp+0D0h+var_A8], rax
0x180024817  mov     [rsp+0D0h+Reserved], r13
0x18002481c  mov     r9, rbx
0x18002481f  mov     r8, r14
0x180024822  mov     rdx, [rbp+37h+var_90]
0x180024826  mov     rcx, rdi
0x180024829  call    ??$FormatArguments@GGK@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBG2AEBK@Z; ArgumentWriter::FormatArguments<ushort,ushort,ulong>(wchar_t const *,wchar_t const *,std::wstring &,ushort const &,ushort const &,ulong const &)
0x18002482e  nop
0x18002482f  mov     rax, qword ptr [rbp+37h+var_58+8]
0x180024833  cmp     rax, 7
0x180024837  jbe     short loc_1800247C2
0x180024839  mov     rcx, [rbp+37h+Block]; Block
0x18002483d  mov     rdx, rcx
0x180024840  lea     rax, ds:2[rax*2]
0x180024848  cmp     rax, 1000h
0x18002484e  jb      short loc_180024877
0x180024850  mov     rcx, [rcx-8]
0x180024854  sub     rdx, rcx
0x180024857  lea     rax, [rdx-8]
0x18002485b  cmp     rax, 1Fh
0x18002485f  jbe     short loc_180024877
0x180024861  mov     [rsp+0D0h+Reserved], r15; Reserved
0x180024866  xor     r9d, r9d; LineNo
0x180024869  xor     r8d, r8d; FileName
0x18002486c  xor     edx, edx; FunctionName
0x18002486e  xor     ecx, ecx; Expression
0x180024870  call    cs:__imp__invoke_watson
0x180024877  call    cs:__imp_free
0x18002487d  jmp     loc_1800247C2
```
