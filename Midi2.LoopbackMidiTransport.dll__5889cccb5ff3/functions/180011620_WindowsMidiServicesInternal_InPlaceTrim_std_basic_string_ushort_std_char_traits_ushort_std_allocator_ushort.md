# WindowsMidiServicesInternal::InPlaceTrim(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180011620`
- end: `0x180011807`
- name: `?InPlaceTrim@WindowsMidiServicesInternal@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `487`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x1800134cc`

## callees

- `0x180003c20`
- `0x180004180`
- `0x180005000`
- `0x18000500c`
- `0x18000b740`
- `0x18000e178`
- `0x18000e820`
- `0x180011620`
- `0x18001455c`
- `0x180014994`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall WindowsMidiServicesInternal::InPlaceTrim(wchar_t *Src)
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
  _BYTE v18[256]; // [rsp+30h] [rbp-D0h] BYREF
  wchar_t *S[2]; // [rsp+130h] [rbp+30h] BYREF
  size_t N; // [rsp+140h] [rbp+40h]
  unsigned __int64 v21; // [rsp+148h] [rbp+48h]

  *(_OWORD *)S = 0;
  N = 0;
  v21 = 0;
  std::wstring::_Construct<1,unsigned short const *>(S, L" ");
  v3 = (const wchar_t *)S;
  if ( v21 > 7 )
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
    memset_0(v18, 0, sizeof(v18));
    v9 = v3;
    v10 = &v3[v6];
    if ( v3 == v10 )
    {
LABEL_12:
      v11 = v5;
      if ( v5 >= v8 )
        goto LABEL_29;
      while ( *v11 < 0x100u && v18[*v11] )
      {
        if ( ++v11 >= v8 )
          goto LABEL_29;
      }
      goto LABEL_21;
    }
    while ( *v9 < 0x100u )
    {
      v18[*(unsigned __int8 *)v9++] = 1;
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
  if ( v21 > 7 )
    v16 = (wchar_t **)S[0];
  if ( *((_QWORD *)Src + 3) <= 7u )
    v17 = Src;
  else
    v17 = *(wchar_t **)Src;
  std::_Traits_find_last_not_of<std::char_traits<unsigned short>>(v17, *((_QWORD *)Src + 2), v2, v16, N);
  std::wstring::resize(Src);
  std::wstring::~wstring(S);
}

```

## disassembly

```asm
0x180011620  mov     [rsp-8+arg_8], rbx
0x180011625  mov     [rsp-8+arg_10], rsi
0x18001162a  push    rbp
0x18001162b  push    rdi
0x18001162c  push    r12
0x18001162e  push    r14
0x180011630  push    r15
0x180011632  lea     rbp, [rsp-60h]
0x180011637  sub     rsp, 160h
0x18001163e  mov     rax, cs:__security_cookie
0x180011645  xor     rax, rsp
0x180011648  mov     [rbp+80h+var_30], rax
0x18001164c  mov     rdi, rcx
0x18001164f  xorps   xmm0, xmm0
0x180011652  movups  xmmword ptr [rbp+80h+S], xmm0
0x180011656  mov     [rbp+80h+N], 0
0x18001165e  mov     [rbp+80h+var_38], 0
0x180011666  mov     r8d, 1
0x18001166c  lea     rdx, asc_1800525A8; " "
0x180011673  lea     rcx, [rbp+80h+S]
0x180011677  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001167c  nop
0x18001167d  lea     r12, [rbp+80h+S]
0x180011681  cmp     [rbp+80h+var_38], 7
0x180011686  cmova   r12, [rbp+80h+S]
0x18001168b  mov     rcx, [rdi+10h]
0x18001168f  cmp     qword ptr [rdi+18h], 7
0x180011694  jbe     short loc_18001169B
0x180011696  mov     rsi, [rdi]
0x180011699  jmp     short loc_18001169E
0x18001169b  mov     rsi, rdi
0x18001169e  test    rcx, rcx
0x1800116a1  jz      loc_18001179A
0x1800116a7  mov     r15, [rbp+80h+N]
0x1800116ab  lea     rax, [rcx+r15]
0x1800116af  cmp     rax, 10h
0x1800116b3  jb      short loc_1800116CE
0x1800116b5  mov     r9, r15
0x1800116b8  mov     r8, r12
0x1800116bb  mov     rdx, rcx
0x1800116be  mov     rcx, rsi
0x1800116c1  call    __std_find_first_not_of_trivial_pos_2
0x1800116c6  mov     rbx, rax
0x1800116c9  jmp     loc_18001175F
0x1800116ce  lea     r14, [rsi+rcx*2]
0x1800116d2  mov     ebx, 100h
0x1800116d7  mov     r8d, ebx; Size
0x1800116da  xor     edx, edx; Val
0x1800116dc  lea     rcx, [rsp+180h+var_150]; void *
0x1800116e1  call    memset_0
0x1800116e6  mov     rcx, r12
0x1800116e9  lea     rdx, [r12+r15*2]
0x1800116ed  cmp     r12, rdx
0x1800116f0  jz      short loc_180011708
0x1800116f2  cmp     [rcx], bx
0x1800116f5  jnb     short loc_180011733
0x1800116f7  movzx   eax, byte ptr [rcx]
0x1800116fa  mov     [rsp+rax+180h+var_150], 1
0x1800116ff  add     rcx, 2
0x180011703  cmp     rcx, rdx
0x180011706  jnz     short loc_1800116F2
0x180011708  mov     rbx, rsi
0x18001170b  cmp     rsi, r14
0x18001170e  jnb     loc_18001179A
0x180011714  mov     ecx, 100h
0x180011719  cmp     [rbx], cx
0x18001171c  jnb     short loc_180011759
0x18001171e  movzx   eax, word ptr [rbx]
0x180011721  cmp     [rsp+rax+180h+var_150], 0
0x180011726  jz      short loc_180011759
0x180011728  add     rbx, 2
0x18001172c  cmp     rbx, r14
0x18001172f  jb      short loc_180011719
0x180011731  jmp     short loc_18001179A
0x180011733  mov     rbx, rsi
0x180011736  cmp     rsi, r14
0x180011739  jnb     short loc_18001179A
0x18001173b  mov     r8, r15; N
0x18001173e  movzx   edx, word ptr [rbx]; C
0x180011741  mov     rcx, r12; S
0x180011744  call    wmemchr
0x180011749  test    rax, rax
0x18001174c  jz      short loc_180011759
0x18001174e  add     rbx, 2
0x180011752  cmp     rbx, r14
0x180011755  jb      short loc_18001173B
0x180011757  jmp     short loc_18001179A
0x180011759  sub     rbx, rsi
0x18001175c  sar     rbx, 1
0x18001175f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180011763  jz      short loc_18001179A
0x180011765  mov     rsi, [rdi+10h]
0x180011769  mov     rax, rsi
0x18001176c  cmp     rsi, rbx
0x18001176f  cmovnb  rax, rbx
0x180011773  cmp     qword ptr [rdi+18h], 7
0x180011778  jbe     short loc_18001177F
0x18001177a  mov     rcx, [rdi]
0x18001177d  jmp     short loc_180011782
0x18001177f  mov     rcx, rdi; void *
0x180011782  sub     rsi, rax
0x180011785  lea     r8, ds:2[rsi*2]; Size
0x18001178d  lea     rdx, [rcx+rax*2]; Src
0x180011791  call    memmove_0
0x180011796  mov     [rdi+10h], rsi
0x18001179a  mov     rax, [rbp+80h+N]
0x18001179e  lea     r9, [rbp+80h+S]
0x1800117a2  cmp     [rbp+80h+var_38], 7
0x1800117a7  cmova   r9, [rbp+80h+S]
0x1800117ac  cmp     qword ptr [rdi+18h], 7
0x1800117b1  jbe     short loc_1800117B8
0x1800117b3  mov     rcx, [rdi]
0x1800117b6  jmp     short loc_1800117BB
0x1800117b8  mov     rcx, rdi
0x1800117bb  mov     [rsp+180h+var_160], rax
0x1800117c0  mov     rdx, [rdi+10h]
0x1800117c4  call    ??$_Traits_find_last_not_of@U?$char_traits@G@std@@@std@@YA_KQEBG_K101@Z; std::_Traits_find_last_not_of<std::char_traits<ushort>>(ushort const * const,unsigned __int64,unsigned __int64,ushort const * const,unsigned __int64)
0x1800117c9  lea     rdx, [rax+1]
0x1800117cd  mov     rcx, rdi; Src
0x1800117d0  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1800117d5  nop
0x1800117d6  lea     rcx, [rbp+80h+S]; void *
0x1800117da  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800117df  mov     rcx, [rbp+80h+var_30]
0x1800117e3  xor     rcx, rsp; StackCookie
0x1800117e6  call    __security_check_cookie
0x1800117eb  lea     r11, [rsp+180h+var_20]
0x1800117f3  mov     rbx, [r11+38h]
0x1800117f7  mov     rsi, [r11+40h]
0x1800117fb  mov     rsp, r11
0x1800117fe  pop     r15
0x180011800  pop     r14
0x180011802  pop     r12
0x180011804  pop     rdi
0x180011805  pop     rbp
0x180011806  retn
```
