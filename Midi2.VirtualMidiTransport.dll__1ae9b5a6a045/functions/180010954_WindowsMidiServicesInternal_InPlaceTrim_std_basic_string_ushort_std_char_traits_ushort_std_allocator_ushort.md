# WindowsMidiServicesInternal::InPlaceTrim(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180010954`
- end: `0x180010b3b`
- name: `?InPlaceTrim@WindowsMidiServicesInternal@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `487`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x180011918`

## callees

- `0x1800033a0`
- `0x1800038f0`
- `0x180004694`
- `0x1800046a0`
- `0x18000bf6c`
- `0x18000cb48`
- `0x18000d0ac`
- `0x180010954`
- `0x180012090`
- `0x1800123ec`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WindowsMidiServicesInternal::InPlaceTrim(wchar_t *Src)
{
  __int64 v2; // r8
  const wchar_t *v3; // r12
  __int64 v4; // rcx
  wchar_t *v5; // rsi
  size_t v6; // r15
  unsigned __int64 first_not_of_trivial_pos_2; // rbx
  wchar_t *v8; // r14
  const wchar_t *v9; // rcx
  const wchar_t *v10; // rdx
  wchar_t *v11; // rbx
  unsigned __int64 v12; // rsi
  unsigned __int64 v13; // rax
  wchar_t *v14; // rcx
  unsigned __int64 v15; // rsi
  wchar_t **v16; // r9
  wchar_t *v17; // rcx
  _BYTE v19[256]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *S[2]; // [rsp+130h] [rbp+30h] BYREF
  size_t N; // [rsp+140h] [rbp+40h]
  unsigned __int64 v22; // [rsp+148h] [rbp+48h]

  *(_OWORD *)S = 0;
  N = 0;
  v22 = 0;
  std::wstring::_Construct<1,unsigned short const *>(S, L" ");
  v3 = (const wchar_t *)S;
  if ( v22 > 7 )
    v3 = S[0];
  v4 = *((_QWORD *)Src + 2);
  if ( *((_QWORD *)Src + 3) <= 7u )
    v5 = Src;
  else
    v5 = *(wchar_t **)Src;
  if ( v4 )
  {
    v6 = N;
    if ( v4 + N >= 0x10 )
    {
      first_not_of_trivial_pos_2 = _std_find_first_not_of_trivial_pos_2(v5, *((_QWORD *)Src + 2), v3, N);
      goto LABEL_22;
    }
    v8 = &v5[v4];
    memset_0(v19, 0, sizeof(v19));
    v9 = v3;
    v10 = &v3[v6];
    if ( v3 == v10 )
    {
LABEL_12:
      v11 = v5;
      if ( v5 >= v8 )
        goto LABEL_29;
      while ( *v11 < 0x100u && v19[*v11] )
      {
        if ( ++v11 >= v8 )
          goto LABEL_29;
      }
      goto LABEL_21;
    }
    while ( *v9 < 0x100u )
    {
      v19[*(unsigned __int8 *)v9++] = 1;
      if ( v9 == v10 )
        goto LABEL_12;
    }
    v11 = v5;
    if ( v5 < v8 )
    {
      while ( wmemchr(v3, *v11, v6) )
      {
        if ( ++v11 >= v8 )
          goto LABEL_29;
      }
LABEL_21:
      first_not_of_trivial_pos_2 = v11 - v5;
LABEL_22:
      if ( first_not_of_trivial_pos_2 != -1 )
      {
        v12 = *((_QWORD *)Src + 2);
        v13 = v12;
        if ( v12 >= first_not_of_trivial_pos_2 )
          v13 = first_not_of_trivial_pos_2;
        if ( *((_QWORD *)Src + 3) <= 7u )
          v14 = Src;
        else
          v14 = *(wchar_t **)Src;
        v15 = v12 - v13;
        memmove_0(v14, &v14[v13], 2 * v15 + 2);
        *((_QWORD *)Src + 2) = v15;
      }
    }
  }
LABEL_29:
  v16 = S;
  if ( v22 > 7 )
    v16 = (wchar_t **)S[0];
  if ( *((_QWORD *)Src + 3) <= 7u )
    v17 = Src;
  else
    v17 = *(wchar_t **)Src;
  std::_Traits_find_last_not_of<std::char_traits<unsigned short>>(v17, *((_QWORD *)Src + 2), v2, v16, N);
  std::wstring::resize(Src);
  return std::wstring::~wstring(S);
}

```

## disassembly

```asm
0x180010954  mov     [rsp-8+arg_8], rbx
0x180010959  mov     [rsp-8+arg_10], rsi
0x18001095e  push    rbp
0x18001095f  push    rdi
0x180010960  push    r12
0x180010962  push    r14
0x180010964  push    r15
0x180010966  lea     rbp, [rsp-60h]
0x18001096b  sub     rsp, 160h
0x180010972  mov     rax, cs:__security_cookie
0x180010979  xor     rax, rsp
0x18001097c  mov     [rbp+80h+var_30], rax
0x180010980  mov     rdi, rcx
0x180010983  xorps   xmm0, xmm0
0x180010986  movups  xmmword ptr [rbp+80h+S], xmm0
0x18001098a  mov     [rbp+80h+N], 0
0x180010992  mov     [rbp+80h+var_38], 0
0x18001099a  mov     r8d, 1
0x1800109a0  lea     rdx, asc_1800242C0; " "
0x1800109a7  lea     rcx, [rbp+80h+S]
0x1800109ab  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800109b0  nop
0x1800109b1  lea     r12, [rbp+80h+S]
0x1800109b5  cmp     [rbp+80h+var_38], 7
0x1800109ba  cmova   r12, [rbp+80h+S]
0x1800109bf  mov     rcx, [rdi+10h]
0x1800109c3  cmp     qword ptr [rdi+18h], 7
0x1800109c8  jbe     short loc_1800109CF
0x1800109ca  mov     rsi, [rdi]
0x1800109cd  jmp     short loc_1800109D2
0x1800109cf  mov     rsi, rdi
0x1800109d2  test    rcx, rcx
0x1800109d5  jz      loc_180010ACE
0x1800109db  mov     r15, [rbp+80h+N]
0x1800109df  lea     rax, [rcx+r15]
0x1800109e3  cmp     rax, 10h
0x1800109e7  jb      short loc_180010A02
0x1800109e9  mov     r9, r15
0x1800109ec  mov     r8, r12
0x1800109ef  mov     rdx, rcx
0x1800109f2  mov     rcx, rsi
0x1800109f5  call    __std_find_first_not_of_trivial_pos_2
0x1800109fa  mov     rbx, rax
0x1800109fd  jmp     loc_180010A93
0x180010a02  lea     r14, [rsi+rcx*2]
0x180010a06  mov     ebx, 100h
0x180010a0b  mov     r8d, ebx; Size
0x180010a0e  xor     edx, edx; Val
0x180010a10  lea     rcx, [rsp+180h+var_150]; void *
0x180010a15  call    memset_0
0x180010a1a  mov     rcx, r12
0x180010a1d  lea     rdx, [r12+r15*2]
0x180010a21  cmp     r12, rdx
0x180010a24  jz      short loc_180010A3C
0x180010a26  cmp     [rcx], bx
0x180010a29  jnb     short loc_180010A67
0x180010a2b  movzx   eax, byte ptr [rcx]
0x180010a2e  mov     [rsp+rax+180h+var_150], 1
0x180010a33  add     rcx, 2
0x180010a37  cmp     rcx, rdx
0x180010a3a  jnz     short loc_180010A26
0x180010a3c  mov     rbx, rsi
0x180010a3f  cmp     rsi, r14
0x180010a42  jnb     loc_180010ACE
0x180010a48  mov     ecx, 100h
0x180010a4d  cmp     [rbx], cx
0x180010a50  jnb     short loc_180010A8D
0x180010a52  movzx   eax, word ptr [rbx]
0x180010a55  cmp     [rsp+rax+180h+var_150], 0
0x180010a5a  jz      short loc_180010A8D
0x180010a5c  add     rbx, 2
0x180010a60  cmp     rbx, r14
0x180010a63  jb      short loc_180010A4D
0x180010a65  jmp     short loc_180010ACE
0x180010a67  mov     rbx, rsi
0x180010a6a  cmp     rsi, r14
0x180010a6d  jnb     short loc_180010ACE
0x180010a6f  mov     r8, r15; N
0x180010a72  movzx   edx, word ptr [rbx]; C
0x180010a75  mov     rcx, r12; S
0x180010a78  call    wmemchr
0x180010a7d  test    rax, rax
0x180010a80  jz      short loc_180010A8D
0x180010a82  add     rbx, 2
0x180010a86  cmp     rbx, r14
0x180010a89  jb      short loc_180010A6F
0x180010a8b  jmp     short loc_180010ACE
0x180010a8d  sub     rbx, rsi
0x180010a90  sar     rbx, 1
0x180010a93  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180010a97  jz      short loc_180010ACE
0x180010a99  mov     rsi, [rdi+10h]
0x180010a9d  mov     rax, rsi
0x180010aa0  cmp     rsi, rbx
0x180010aa3  cmovnb  rax, rbx
0x180010aa7  cmp     qword ptr [rdi+18h], 7
0x180010aac  jbe     short loc_180010AB3
0x180010aae  mov     rcx, [rdi]
0x180010ab1  jmp     short loc_180010AB6
0x180010ab3  mov     rcx, rdi; void *
0x180010ab6  sub     rsi, rax
0x180010ab9  lea     r8, ds:2[rsi*2]; Size
0x180010ac1  lea     rdx, [rcx+rax*2]; Src
0x180010ac5  call    memmove_0
0x180010aca  mov     [rdi+10h], rsi
0x180010ace  mov     rax, [rbp+80h+N]
0x180010ad2  lea     r9, [rbp+80h+S]
0x180010ad6  cmp     [rbp+80h+var_38], 7
0x180010adb  cmova   r9, [rbp+80h+S]
0x180010ae0  cmp     qword ptr [rdi+18h], 7
0x180010ae5  jbe     short loc_180010AEC
0x180010ae7  mov     rcx, [rdi]
0x180010aea  jmp     short loc_180010AEF
0x180010aec  mov     rcx, rdi
0x180010aef  mov     [rsp+180h+var_160], rax
0x180010af4  mov     rdx, [rdi+10h]
0x180010af8  call    ??$_Traits_find_last_not_of@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find_last_not_of<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x180010afd  lea     rdx, [rax+1]
0x180010b01  mov     rcx, rdi; Src
0x180010b04  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x180010b09  nop
0x180010b0a  lea     rcx, [rbp+80h+S]
0x180010b0e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180010b13  mov     rcx, [rbp+80h+var_30]
0x180010b17  xor     rcx, rsp; StackCookie
0x180010b1a  call    __security_check_cookie
0x180010b1f  lea     r11, [rsp+180h+var_20]
0x180010b27  mov     rbx, [r11+38h]
0x180010b2b  mov     rsi, [r11+40h]
0x180010b2f  mov     rsp, r11
0x180010b32  pop     r15
0x180010b34  pop     r14
0x180010b36  pop     r12
0x180010b38  pop     rdi
0x180010b39  pop     rbp
0x180010b3a  retn
```
