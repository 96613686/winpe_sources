# OPath::GetDirectoryName(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180020494`
- end: `0x180020673`
- name: `?GetDirectoryName@OPath@@SAXAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV23@@Z`
- size: `479`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180021610`

## callees

- `0x1800018e0`
- `0x180003124`
- `0x180004044`
- `0x18000410c`
- `0x1800045ec`
- `0x180020494`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180020626`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180020626`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002062d`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x18002062d`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall OPath::GetDirectoryName(const wchar_t **a1, void **a2)
{
  const wchar_t **v3; // rdi
  size_t v4; // r12
  wchar_t *v5; // r13
  size_t v6; // rcx
  const wchar_t *v7; // r15
  unsigned __int64 v8; // rbx
  __int64 v9; // rcx
  __int64 v10; // rax
  const wchar_t *i; // rbx
  unsigned __int64 v12; // rax
  void *v13; // rcx
  __int16 v15; // [rsp+30h] [rbp-50h] BYREF
  wchar_t *S2[2]; // [rsp+38h] [rbp-48h] BYREF
  size_t N; // [rsp+48h] [rbp-38h]
  unsigned __int64 v18; // [rsp+50h] [rbp-30h]
  void *Block[2]; // [rsp+58h] [rbp-28h] BYREF
  __int128 v20; // [rsp+68h] [rbp-18h]

  v3 = a1;
  v15 = 0;
  *(_OWORD *)S2 = 0;
  N = 0;
  v18 = 7;
  LOWORD(S2[0]) = 0;
  OPath::GetPathSeperator(a1, S2, &v15);
  v4 = N;
  v5 = (wchar_t *)S2;
  if ( v18 > 7 )
    v5 = S2[0];
  v6 = (size_t)v3[2];
  v7 = (const wchar_t *)v3;
  if ( (unsigned __int64)v3[3] > 7 )
    v7 = *v3;
  if ( N )
  {
    if ( N > v6 )
    {
LABEL_32:
      std::wstring::operator=(a2);
      return std::wstring::_Tidy_deallocate(S2);
    }
    _mm_lfence();
    v9 = v6 - N;
    v10 = -1;
    if ( v9 != -1 )
      v10 = v9;
    for ( i = &v7[v10]; ; --i )
    {
      if ( *i == *v5 && !wmemcmp(i, v5, v4) )
      {
        v8 = i - v7;
        goto LABEL_19;
      }
      if ( i == v7 )
        break;
    }
    v8 = -1;
  }
  else
  {
    v8 = -1;
    if ( v6 != -1 )
      v8 = (unsigned __int64)v3[2];
  }
LABEL_19:
  if ( v8 == -1 )
    goto LABEL_32;
  *(_OWORD *)Block = 0;
  v20 = 0;
  if ( (unsigned __int64)v3[2] < v8 )
    v8 = (unsigned __int64)v3[2];
  if ( (unsigned __int64)v3[3] > 7 )
    v3 = (const wchar_t **)*v3;
  std::wstring::_Construct<1,wchar_t const *>(Block, v3, v8);
  if ( a2 == Block )
  {
    v12 = *((_QWORD *)&v20 + 1);
  }
  else
  {
    std::wstring::_Tidy_deallocate(a2);
    *(_OWORD *)a2 = *(_OWORD *)Block;
    *((_OWORD *)a2 + 1) = v20;
    v12 = 7;
    LOWORD(Block[0]) = 0;
  }
  if ( v12 > 7 )
  {
    v13 = Block[0];
    if ( 2 * v12 + 2 >= 0x1000 )
    {
      v13 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v13 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v13);
  }
  return std::wstring::_Tidy_deallocate(S2);
}

```

## disassembly

```asm
0x180020494  mov     [rsp-28h+arg_10], rbx
0x180020499  mov     [rsp-28h+arg_18], rdi
0x18002049e  push    rbp
0x18002049f  push    r12
0x1800204a1  push    r13
0x1800204a3  push    r14
0x1800204a5  push    r15
0x1800204a7  mov     rbp, rsp
0x1800204aa  sub     rsp, 80h
0x1800204b1  mov     rax, cs:__security_cookie
0x1800204b8  xor     rax, rsp
0x1800204bb  mov     [rbp+var_8], rax
0x1800204bf  mov     r14, rdx
0x1800204c2  mov     rdi, rcx
0x1800204c5  xor     ebx, ebx
0x1800204c7  mov     [rbp+var_50], bx
0x1800204cb  xorps   xmm0, xmm0
0x1800204ce  movups  xmmword ptr [rbp+S2], xmm0
0x1800204d2  mov     [rbp+N], rbx
0x1800204d6  mov     [rbp+var_30], 7
0x1800204de  mov     word ptr [rbp+S2], bx
0x1800204e2  lea     r8, [rbp+var_50]
0x1800204e6  lea     rdx, [rbp+S2]
0x1800204ea  call    ?GetPathSeperator@OPath@@SA_NAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV23@AEA_W@Z; OPath::GetPathSeperator(std::wstring const &,std::wstring &,wchar_t &)
0x1800204ef  mov     r12, [rbp+N]
0x1800204f3  lea     r13, [rbp+S2]
0x1800204f7  cmp     [rbp+var_30], 7
0x1800204fc  cmova   r13, [rbp+S2]
0x180020501  mov     rcx, [rdi+10h]
0x180020505  mov     r15, rdi
0x180020508  cmp     qword ptr [rdi+18h], 7
0x18002050d  jbe     short loc_180020512
0x18002050f  mov     r15, [rdi]
0x180020512  test    r12, r12
0x180020515  jnz     short loc_180020524
0x180020517  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002051b  cmp     rcx, rbx
0x18002051e  cmovb   rbx, rcx
0x180020522  jmp     short loc_180020576
0x180020524  cmp     r12, rcx
0x180020527  ja      loc_180020635
0x18002052d  lfence
0x180020530  sub     rcx, [rbp+N]
0x180020534  or      rax, 0FFFFFFFFFFFFFFFFh
0x180020538  cmp     rcx, rax
0x18002053b  cmovb   rax, rcx
0x18002053f  lea     rbx, [r15+rax*2]
0x180020543  movzx   eax, word ptr [r13+0]
0x180020548  cmp     [rbx], ax
0x18002054b  jnz     short loc_18002055F
0x18002054d  mov     r8, r12; N
0x180020550  mov     rdx, r13; S2
0x180020553  mov     rcx, rbx; S1
0x180020556  call    wmemcmp
0x18002055b  test    eax, eax
0x18002055d  jz      short loc_18002056A
0x18002055f  cmp     rbx, r15
0x180020562  jz      short loc_180020572
0x180020564  sub     rbx, 2
0x180020568  jmp     short loc_180020543
0x18002056a  sub     rbx, r15
0x18002056d  sar     rbx, 1
0x180020570  jmp     short loc_180020576
0x180020572  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180020576  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002057a  jz      loc_180020635
0x180020580  xorps   xmm0, xmm0
0x180020583  movups  xmmword ptr [rbp+Block], xmm0
0x180020587  xorps   xmm1, xmm1
0x18002058a  movdqu  [rbp+var_18], xmm1
0x18002058f  cmp     [rdi+10h], rbx
0x180020593  cmovb   rbx, [rdi+10h]
0x180020598  cmp     qword ptr [rdi+18h], 7
0x18002059d  jbe     short loc_1800205A2
0x18002059f  mov     rdi, [rdi]
0x1800205a2  mov     r8, rbx
0x1800205a5  mov     rdx, rdi
0x1800205a8  lea     rcx, [rbp+Block]
0x1800205ac  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800205b1  lea     rax, [rbp+Block]
0x1800205b5  cmp     r14, rax
0x1800205b8  jz      short loc_1800205E2
0x1800205ba  mov     rcx, r14
0x1800205bd  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800205c2  movups  xmm0, xmmword ptr [rbp+Block]
0x1800205c6  movups  xmmword ptr [r14], xmm0
0x1800205ca  movups  xmm1, [rbp+var_18]
0x1800205ce  movups  xmmword ptr [r14+10h], xmm1
0x1800205d3  mov     eax, 7
0x1800205d8  xor     r8d, r8d
0x1800205db  mov     word ptr [rbp+Block], r8w
0x1800205e0  jmp     short loc_1800205E9
0x1800205e2  mov     rax, qword ptr [rbp+var_18+8]
0x1800205e6  xor     r8d, r8d
0x1800205e9  cmp     rax, 7
0x1800205ed  jbe     short loc_180020641
0x1800205ef  mov     rcx, [rbp+Block]; Block
0x1800205f3  mov     rdx, rcx
0x1800205f6  lea     rax, ds:2[rax*2]
0x1800205fe  cmp     rax, 1000h
0x180020604  jb      short loc_18002062D
0x180020606  mov     rcx, [rcx-8]
0x18002060a  sub     rdx, rcx
0x18002060d  lea     rax, [rdx-8]
0x180020611  cmp     rax, 1Fh
0x180020615  jbe     short loc_18002062D
0x180020617  mov     [rsp+80h+Reserved], r8; Reserved
0x18002061c  xor     r9d, r9d; LineNo
0x18002061f  xor     r8d, r8d; FileName
0x180020622  xor     edx, edx; FunctionName
0x180020624  xor     ecx, ecx; Expression
0x180020626  call    cs:__imp__invoke_watson
0x18002062d  call    cs:__imp_free
0x180020633  jmp     short loc_180020641
0x180020635  mov     rdx, rdi
0x180020638  mov     rcx, r14; void *
0x18002063b  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180020640  nop
0x180020641  lea     rcx, [rbp+S2]
0x180020645  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002064a  mov     rcx, [rbp+var_8]
0x18002064e  xor     rcx, rsp; StackCookie
0x180020651  call    __security_check_cookie
0x180020656  lea     r11, [rsp+80h+var_s0]
0x18002065e  mov     rbx, [r11+40h]
0x180020662  mov     rdi, [r11+48h]
0x180020666  mov     rsp, r11
0x180020669  pop     r15
0x18002066b  pop     r14
0x18002066d  pop     r13
0x18002066f  pop     r12
0x180020671  pop     rbp
0x180020672  retn
```
