# ??$FromJsonValue@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$$V$$Z$$V@Marshal@@YA_NAEAVJsonParser@0@PEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBVUnmarshalContext@0@U?$ModifierList@$$V@0@3@Z

- ea: `0x1400048f0`
- end: `0x140004cd9`
- name: `??$FromJsonValue@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$$V$$Z$$V@Marshal@@YA_NAEAVJsonParser@0@PEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@X@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@AEBVUnmarshalContext@0@U?$ModifierList@$$V@0@3@Z`
- size: `1001`
- prototype: `char __fastcall(Marshal::JsonParser *this, __int64 *, __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, registry_config`

## callers

- `0x140004e40`

## callees

- `0x140002310`
- `0x1400026b8`
- `0x140004484`
- `0x140004820`
- `0x1400048f0`
- `0x140005124`
- `0x14000735c`
- `0x140007a24`
- `0x140008160`
- `0x140008fec`
- `0x14000a714`
- `0x14000b3f4`
- `0x14000b8c8`
- `0x14000bc7c`
- `0x14000df30`
- `0x14000e3c0`
- `0x14000e86c`
- `0x14000f3c0`

## pseudocode

```c
char __fastcall ___FromJsonValue_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__less_X_2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2___V__Z__V_Marshal__YA_NAEAVJsonParser_0_PEAV__map_V__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12_U__less_X_2_V__allocator_U__pair___CBV__basic_string_GU__char_traits_G_std__V__allocator_G_2__std__V12__std___2__std__AEBVUnmarshalContext_0_U__ModifierList___V_0_3_Z(
        Marshal::JsonParser *this,
        __int64 *a2,
        __int64 a3)
{
  __int64 v3; // rbx
  __int64 v6; // rdx
  __int64 v7; // r8
  _QWORD *v9; // rsi
  char *v10; // r14
  char *v11; // rdi
  char v12; // r12
  char i; // al
  _QWORD *v14; // rcx
  _QWORD *v15; // rax
  __int64 v16; // r9
  __int64 inserted; // rdi
  int v18; // r14d
  __int64 v19; // rbx
  const wchar_t *v20; // rcx
  size_t v21; // r14
  const wchar_t *v22; // rdx
  size_t v23; // rsi
  size_t v24; // r8
  int v25; // eax
  const wchar_t *v26; // rdx
  size_t v27; // rbx
  size_t v28; // rsi
  const wchar_t *v29; // rcx
  size_t v30; // r8
  int v31; // eax
  _QWORD *v32; // rax
  __int64 v33; // rdi
  char *v34; // rbx
  __int64 **v35; // rcx
  __int64 v36; // rax
  __int64 j; // rcx
  __int64 *k; // rcx
  char *v39; // rdi
  __int64 v40; // rdx
  __int64 v42; // [rsp+38h] [rbp-99h]
  wchar_t **v43; // [rsp+40h] [rbp-91h] BYREF
  __int64 v44; // [rsp+48h] [rbp-89h]
  __int64 v45; // [rsp+50h] [rbp-81h] BYREF
  int v46; // [rsp+58h] [rbp-79h]
  int v47; // [rsp+5Ch] [rbp-75h]
  _QWORD v48[2]; // [rsp+60h] [rbp-71h] BYREF
  __int64 v49; // [rsp+70h] [rbp-61h] BYREF
  void *v50; // [rsp+78h] [rbp-59h]
  wchar_t *S2[2]; // [rsp+80h] [rbp-51h] BYREF
  size_t N; // [rsp+90h] [rbp-41h]
  unsigned __int64 v53; // [rsp+98h] [rbp-39h]
  _QWORD v54[2]; // [rsp+A0h] [rbp-31h] BYREF
  __int64 v55; // [rsp+B0h] [rbp-21h]
  unsigned __int64 v56; // [rsp+B8h] [rbp-19h]
  _QWORD v57[5]; // [rsp+C0h] [rbp-11h] BYREF

  v3 = a3;
  if ( (unsigned int)Marshal::JsonParser::PeekValueType() != 3 )
  {
    Marshal::UnmarshalContext::ReportError(v3, 5);
    return 0;
  }
  if ( (*(_BYTE *)(*(_QWORD *)(v3 + 8) + 24LL) & 8) == 0 )
  {
    v9 = (_QWORD *)*a2;
    v10 = *(char **)(*a2 + 8);
    while ( !v10[25] )
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
        (__int64)a2,
        (__int64)a2,
        *((char **)v10 + 2));
      v11 = v10;
      v10 = *(char **)v10;
      std::wstring::~wstring(v11 + 64);
      std::wstring::~wstring(v11 + 32);
      operator delete(v11, 0x60u);
    }
    v9[1] = v9;
    *v9 = v9;
    v9[2] = v9;
    a2[1] = 0;
  }
  v12 = 1;
  LOBYTE(v7) = 125;
  LOBYTE(v6) = 123;
  for ( i = Marshal::JsonParser::BeginAggregate(this, v6, v7, 9); i; i = Marshal::JsonParser::NextElement(this, v40, 10) )
  {
    Marshal::JsonParser::ParseObjectKey(this);
    std::wstring::wstring(v54, (char *)this + 32);
    v14 = v54;
    if ( v56 > 7 )
      v14 = (_QWORD *)v54[0];
    v57[1] = *(_QWORD *)(v3 + 8);
    v57[2] = v3;
    v57[0] = &Marshal::Details::UnmarshalFieldContext::`vftable';
    v57[3] = v14;
    v57[4] = v55;
    *(_OWORD *)S2 = 0;
    N = 0;
    v53 = 7;
    LOWORD(S2[0]) = 0;
    v15 = v54;
    if ( v56 > 7 )
      v15 = (_QWORD *)v54[0];
    v48[0] = v15;
    v48[1] = v55;
    if ( !(unsigned __int8)Marshal::Details::ParseJsonName<std::wstring,>(v48, S2, v57) )
      goto LABEL_54;
    inserted = *a2;
    v42 = *(_QWORD *)(*a2 + 8);
    v18 = 0;
    v44 = 0;
    v19 = v42;
    while ( !*(_BYTE *)(v19 + 25) )
    {
      v42 = v19;
      v20 = (const wchar_t *)(v19 + 32);
      v21 = N;
      v22 = (const wchar_t *)S2;
      if ( v53 > 7 )
        v22 = S2[0];
      v23 = *(_QWORD *)(v19 + 48);
      if ( *(_QWORD *)(v19 + 56) > 7u )
        v20 = *(const wchar_t **)v20;
      v24 = *(_QWORD *)(v19 + 48);
      if ( N < v23 )
        v24 = N;
      v25 = wmemcmp(v20, v22, v24);
      if ( v25 )
      {
        if ( v25 < 0 )
          goto LABEL_43;
      }
      else if ( v23 < v21 )
      {
LABEL_43:
        v18 = 0;
        v19 = *(_QWORD *)(v19 + 16);
        continue;
      }
      v18 = 1;
      inserted = v19;
      v19 = *(_QWORD *)v19;
    }
    if ( *(_BYTE *)(inserted + 25) )
    {
LABEL_34:
      if ( a2[1] == 0x2AAAAAAAAAAAAAALL )
        std::_Throw_tree_length_error();
      v43 = S2;
      v32 = std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(
              &v49,
              (__int64)a2,
              *a2,
              v16,
              (__int64 *)&v43);
      v33 = v32[1];
      v32[1] = 0;
      v34 = (char *)v50;
      if ( v50 )
      {
        std::wstring::~wstring((char *)v50 + 64);
        std::wstring::~wstring(v34 + 32);
        if ( v50 )
          operator delete(v50, 0x60u);
      }
      v45 = v42;
      v46 = v18;
      v47 = v44;
      inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::shared_ptr<CExec::ProcessTracker>>>>::_Insert_node(
                   a2,
                   &v45,
                   v33);
      v3 = a3;
      goto LABEL_39;
    }
    v26 = (const wchar_t *)(inserted + 32);
    v27 = *(_QWORD *)(inserted + 48);
    if ( *(_QWORD *)(inserted + 56) > 7u )
      v26 = *(const wchar_t **)v26;
    v28 = N;
    v29 = (const wchar_t *)S2;
    if ( v53 > 7 )
      v29 = S2[0];
    v30 = N;
    if ( v27 < N )
      v30 = *(_QWORD *)(inserted + 48);
    v31 = wmemcmp(v29, v26, v30);
    if ( v31 )
    {
      if ( v31 < 0 )
        goto LABEL_34;
    }
    else if ( v28 < v27 )
    {
      goto LABEL_34;
    }
    v3 = a3;
    if ( (*(_BYTE *)(*(_QWORD *)(a3 + 8) + 24LL) & 8) == 0 )
    {
      Marshal::UnmarshalContext::ReportError(v57, 16);
      goto LABEL_54;
    }
LABEL_39:
    if ( Marshal::Details::FromJsonGeneric<std::wstring,>((__int64)this, (void **)(inserted + 64), (__int64)v57) )
      goto LABEL_55;
    v35 = *(__int64 ***)(inserted + 16);
    if ( *((_BYTE *)v35 + 25) )
    {
      v36 = inserted;
      for ( j = *(_QWORD *)(inserted + 8); !*(_BYTE *)(j + 25) && v36 == *(_QWORD *)(j + 16); j = *(_QWORD *)(j + 8) )
        v36 = j;
    }
    else
    {
      for ( k = *v35; !*((_BYTE *)k + 25); k = (__int64 *)*k )
        ;
    }
    v39 = (char *)std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Extract(
                    a2,
                    inserted);
    std::wstring::~wstring(v39 + 64);
    std::wstring::~wstring(v39 + 32);
    operator delete(v39, 0x60u);
    v3 = a3;
LABEL_54:
    v12 = 0;
LABEL_55:
    std::wstring::~wstring(S2);
    std::wstring::~wstring(v54);
    LOBYTE(v40) = 125;
  }
  return v12;
}

```

## disassembly

```asm
0x1400048f0  mov     [rsp-8+arg_18], rbx
0x1400048f5  push    rbp
0x1400048f6  push    rsi
0x1400048f7  push    rdi
0x1400048f8  push    r12
0x1400048fa  push    r13
0x1400048fc  push    r14
0x1400048fe  push    r15
0x140004900  lea     rbp, [rsp-1Fh]
0x140004905  sub     rsp, 0F0h
0x14000490c  mov     rax, cs:__security_cookie
0x140004913  xor     rax, rsp
0x140004916  mov     [rbp+4Fh+var_38], rax
0x14000491a  mov     rbx, r8
0x14000491d  mov     [rsp+120h+var_F0], rbx
0x140004922  mov     r15, rdx
0x140004925  mov     r13, rcx
0x140004928  call    ?PeekValueType@JsonParser@Marshal@@QEAA?AW4ValueType@12@XZ; Marshal::JsonParser::PeekValueType(void)
0x14000492d  cmp     eax, 3
0x140004930  jz      short loc_140004946
0x140004932  mov     edx, 5
0x140004937  mov     rcx, rbx
0x14000493a  call    ?ReportError@UnmarshalContext@Marshal@@QEBAXW4UnmarshalError@2@@Z; Marshal::UnmarshalContext::ReportError(Marshal::UnmarshalError)
0x14000493f  xor     al, al
0x140004941  jmp     loc_140004CAC
0x140004946  mov     rax, [rbx+8]
0x14000494a  test    byte ptr [rax+18h], 8
0x14000494e  jnz     short loc_1400049AC
0x140004950  mov     rsi, [r15]
0x140004953  mov     r14, [rsi+8]
0x140004957  cmp     byte ptr [r14+19h], 0
0x14000495c  jnz     short loc_140004999
0x14000495e  mov     r8, [r14+10h]
0x140004962  mov     rdx, r15
0x140004965  mov     rcx, r15
0x140004968  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *)
0x14000496d  mov     rdi, r14
0x140004970  mov     r14, [r14]
0x140004973  lea     rcx, [rdi+40h]
0x140004977  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000497c  lea     rcx, [rdi+20h]
0x140004980  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140004985  mov     edx, 60h ; '`'; unsigned __int64
0x14000498a  mov     rcx, rdi; void *
0x14000498d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140004992  cmp     byte ptr [r14+19h], 0
0x140004997  jz      short loc_14000495E
0x140004999  mov     [rsi+8], rsi
0x14000499d  mov     [rsi], rsi
0x1400049a0  mov     [rsi+10h], rsi
0x1400049a4  mov     qword ptr [r15+8], 0
0x1400049ac  mov     r12b, 1
0x1400049af  mov     r9d, 9
0x1400049b5  mov     r8b, 7Dh ; '}'
0x1400049b8  mov     dl, 7Bh ; '{'
0x1400049ba  mov     rcx, r13
0x1400049bd  call    ?BeginAggregate@JsonParser@Marshal@@AEAA_NDDW4ParseError@12@@Z; Marshal::JsonParser::BeginAggregate(char,char,Marshal::JsonParser::ParseError)
0x1400049c2  test    al, al
0x1400049c4  jz      loc_140004CA9
0x1400049ca  mov     rcx, r13; this
0x1400049cd  call    ?ParseObjectKey@JsonParser@Marshal@@AEAAXXZ; Marshal::JsonParser::ParseObjectKey(void)
0x1400049d2  lea     rax, [r13+20h]
0x1400049d6  mov     rdx, rax
0x1400049d9  lea     rcx, [rbp+4Fh+var_80]
0x1400049dd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1400049e2  nop
0x1400049e3  lea     rcx, [rbp+4Fh+var_80]
0x1400049e7  cmp     [rbp+4Fh+var_68], 7
0x1400049ec  cmova   rcx, [rbp+4Fh+var_80]
0x1400049f1  mov     rdx, [rbp+4Fh+var_70]
0x1400049f5  mov     rax, [rbx+8]
0x1400049f9  mov     [rbp+4Fh+var_58], rax
0x1400049fd  mov     [rbp+4Fh+var_50], rbx
0x140004a01  lea     rax, ??_7UnmarshalFieldContext@Details@Marshal@@6B@; const Marshal::Details::UnmarshalFieldContext::`vftable'
0x140004a08  mov     [rbp+4Fh+var_60], rax
0x140004a0c  mov     [rbp+4Fh+var_48], rcx
0x140004a10  mov     [rbp+4Fh+var_40], rdx
0x140004a14  xorps   xmm0, xmm0
0x140004a17  movups  xmmword ptr [rbp+4Fh+S2], xmm0
0x140004a1b  mov     [rbp+4Fh+N], 0
0x140004a23  mov     [rbp+4Fh+var_88], 7
0x140004a2b  xor     eax, eax
0x140004a2d  mov     word ptr [rbp+4Fh+S2], ax
0x140004a31  lea     rax, [rbp+4Fh+var_80]
0x140004a35  cmp     [rbp+4Fh+var_68], 7
0x140004a3a  cmova   rax, [rbp+4Fh+var_80]
0x140004a3f  mov     [rbp+4Fh+var_C0], rax
0x140004a43  mov     [rbp+4Fh+var_B8], rdx
0x140004a47  lea     r8, [rbp+4Fh+var_60]
0x140004a4b  lea     rdx, [rbp+4Fh+S2]
0x140004a4f  lea     rcx, [rbp+4Fh+var_C0]
0x140004a53  call    ??$ParseJsonName@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@Details@Marshal@@YA_NV?$basic_string_view@GU?$char_traits@G@std@@@std@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@3@AEBVUnmarshalContext@1@@Z; Marshal::Details::ParseJsonName<std::wstring,>(std::basic_string_view<ushort>,std::wstring *,Marshal::UnmarshalContext const &)
0x140004a58  test    al, al
0x140004a5a  jz      loc_140004C7E
0x140004a60  mov     rdi, [r15]
0x140004a63  mov     rax, [rdi+8]
0x140004a67  mov     [rsp+120h+var_E8], rax
0x140004a6c  xor     r14d, r14d
0x140004a6f  xor     ecx, ecx
0x140004a71  mov     [rsp+120h+var_D8], rcx
0x140004a76  mov     rbx, rax
0x140004a79  cmp     [rax+19h], cl
0x140004a7c  jnz     short loc_140004AD6
0x140004a7e  mov     [rsp+120h+var_E8], rbx
0x140004a83  lea     rcx, [rbx+20h]
0x140004a87  mov     r14, [rbp+4Fh+N]
0x140004a8b  lea     rdx, [rbp+4Fh+S2]
0x140004a8f  cmp     [rbp+4Fh+var_88], 7
0x140004a94  cmova   rdx, [rbp+4Fh+S2]; S2
0x140004a99  mov     rsi, [rcx+10h]
0x140004a9d  cmp     qword ptr [rcx+18h], 7
0x140004aa2  jbe     short loc_140004AA7
0x140004aa4  mov     rcx, [rcx]; S1
0x140004aa7  mov     r8, rsi
0x140004aaa  cmp     r14, rsi
0x140004aad  cmovb   r8, r14; N
0x140004ab1  call    wmemcmp
0x140004ab6  test    eax, eax
0x140004ab8  jz      loc_140004BE5
0x140004abe  js      loc_140004BEE
0x140004ac4  mov     r14d, 1
0x140004aca  mov     rdi, rbx
0x140004acd  mov     rbx, [rbx]
0x140004ad0  cmp     byte ptr [rbx+19h], 0
0x140004ad4  jz      short loc_140004A7E
0x140004ad6  cmp     byte ptr [rdi+19h], 0
0x140004ada  jnz     short loc_140004B1D
0x140004adc  lea     rdx, [rdi+20h]
0x140004ae0  mov     rbx, [rdx+10h]
0x140004ae4  cmp     qword ptr [rdx+18h], 7
0x140004ae9  jbe     short loc_140004AEE
0x140004aeb  mov     rdx, [rdx]; S2
0x140004aee  mov     rsi, [rbp+4Fh+N]
0x140004af2  lea     rcx, [rbp+4Fh+S2]
0x140004af6  cmp     [rbp+4Fh+var_88], 7
0x140004afb  cmova   rcx, [rbp+4Fh+S2]; S1
0x140004b00  mov     r8, rsi
0x140004b03  cmp     rbx, rsi
0x140004b06  cmovb   r8, rbx; N
0x140004b0a  call    wmemcmp
0x140004b0f  test    eax, eax
0x140004b11  jz      loc_140004BFA
0x140004b17  jns     loc_140004C03
0x140004b1d  mov     rax, 2AAAAAAAAAAAAAAh
0x140004b27  cmp     [r15+8], rax
0x140004b2b  jz      loc_140004CD3
0x140004b31  lea     rax, [rbp+4Fh+S2]
0x140004b35  mov     [rsp+120h+var_E0], rax
0x140004b3a  lea     rax, [rsp+120h+var_E0]
0x140004b3f  mov     [rsp+120h+var_100], rax
0x140004b44  mov     r8, [r15]
0x140004b47  mov     rdx, r15
0x140004b4a  lea     rcx, [rbp+4Fh+var_B0]
0x140004b4e  call    ??$?0AEBUpiecewise_construct_t@std@@V?$tuple@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@V?$tuple@$$V@1@@?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@std@@@std@@QEAA@AEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@1@AEBUpiecewise_construct_t@1@$$QEAV?$tuple@$$QEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@1@$$QEAV?$tuple@$$V@1@@Z; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *>> &,std::_Tree_node<std::pair<std::wstring const,std::wstring>,void *> *,std::piecewise_construct_t const &,std::tuple<std::wstring &&> &&,std::tuple<> &&)
0x140004b53  mov     rdi, [rax+8]
0x140004b57  mov     qword ptr [rax+8], 0
0x140004b5f  mov     rbx, [rbp+4Fh+var_A8]
0x140004b63  test    rbx, rbx
0x140004b66  jz      short loc_140004B8D
0x140004b68  lea     rcx, [rbx+40h]
0x140004b6c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140004b71  lea     rcx, [rbx+20h]
0x140004b75  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140004b7a  mov     rcx, [rbp+4Fh+var_A8]; void *
0x140004b7e  test    rcx, rcx
0x140004b81  jz      short loc_140004B8D
0x140004b83  mov     edx, 60h ; '`'; unsigned __int64
0x140004b88  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140004b8d  mov     rax, [rsp+120h+var_E8]
0x140004b92  mov     [rsp+120h+var_D0], rax
0x140004b97  mov     [rbp+4Fh+var_C8], r14d
0x140004b9b  mov     rax, [rsp+120h+var_D8]
0x140004ba0  mov     [rbp+4Fh+var_C4], eax
0x140004ba3  mov     r8, rdi
0x140004ba6  lea     rdx, [rsp+120h+var_D0]
0x140004bab  mov     rcx, r15
0x140004bae  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::shared_ptr<CExec::ProcessTracker>>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<ulong const,std::shared_ptr<CExec::ProcessTracker>>,void *> *>,std::_Tree_node<std::pair<ulong const,std::shared_ptr<CExec::ProcessTracker>>,void *> * const)
0x140004bb3  mov     rdi, rax
0x140004bb6  mov     rbx, [rsp+120h+var_F0]
0x140004bbb  lea     rdx, [rdi+40h]
0x140004bbf  lea     r8, [rbp+4Fh+var_60]
0x140004bc3  mov     rcx, r13
0x140004bc6  call    ??$FromJsonGeneric@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@$$V@Details@Marshal@@YA_NAEAVJsonParser@1@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBVUnmarshalContext@1@U?$integral_constant@_N$00@4@@Z; Marshal::Details::FromJsonGeneric<std::wstring,>(Marshal::JsonParser &,std::wstring *,Marshal::UnmarshalContext const &,std::integral_constant<bool,1>)
0x140004bcb  test    al, al
0x140004bcd  jnz     loc_140004C81
0x140004bd3  mov     rcx, [rdi+10h]
0x140004bd7  cmp     [rcx+19h], al
0x140004bda  jz      short loc_140004C37
0x140004bdc  mov     rax, rdi
0x140004bdf  mov     rcx, [rdi+8]
0x140004be3  jmp     short loc_140004C2F
0x140004be5  cmp     rsi, r14
0x140004be8  jnb     loc_140004AC4
0x140004bee  xor     r14d, r14d
0x140004bf1  mov     rbx, [rbx+10h]
0x140004bf5  jmp     loc_140004AD0
0x140004bfa  cmp     rsi, rbx
0x140004bfd  jb      loc_140004B1D
0x140004c03  mov     rbx, [rsp+120h+var_F0]
0x140004c08  mov     rax, [rbx+8]
0x140004c0c  test    byte ptr [rax+18h], 8
0x140004c10  jnz     short loc_140004BBB
0x140004c12  mov     edx, 10h
0x140004c17  lea     rcx, [rbp+4Fh+var_60]
0x140004c1b  call    ?ReportError@UnmarshalContext@Marshal@@QEBAXW4UnmarshalError@2@@Z; Marshal::UnmarshalContext::ReportError(Marshal::UnmarshalError)
0x140004c20  jmp     short loc_140004C7E
0x140004c22  cmp     rax, [rcx+10h]
0x140004c26  jnz     short loc_140004C4C
0x140004c28  mov     rax, rcx
0x140004c2b  mov     rcx, [rcx+8]
0x140004c2f  cmp     byte ptr [rcx+19h], 0
0x140004c33  jz      short loc_140004C22
0x140004c35  jmp     short loc_140004C4C
0x140004c37  mov     rcx, [rcx]
0x140004c3a  cmp     byte ptr [rcx+19h], 0
0x140004c3e  jnz     short loc_140004C4C
0x140004c40  mov     rax, [rcx]
0x140004c43  mov     rcx, rax
0x140004c46  cmp     byte ptr [rax+19h], 0
0x140004c4a  jz      short loc_140004C40
0x140004c4c  mov     rdx, rdi
0x140004c4f  mov     rcx, r15
0x140004c52  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::wstring>>>,std::_Iterator_base0>)
0x140004c57  mov     rdi, rax
0x140004c5a  lea     rcx, [rax+40h]
0x140004c5e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140004c63  lea     rcx, [rdi+20h]
0x140004c67  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140004c6c  mov     edx, 60h ; '`'; unsigned __int64
0x140004c71  mov     rcx, rdi; void *
0x140004c74  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140004c79  mov     rbx, [rsp+120h+var_F0]
0x140004c7e  xor     r12b, r12b
0x140004c81  lea     rcx, [rbp+4Fh+S2]
0x140004c85  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140004c8a  nop
0x140004c8b  lea     rcx, [rbp+4Fh+var_80]
0x140004c8f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140004c94  mov     r8d, 0Ah
0x140004c9a  mov     dl, 7Dh ; '}'
0x140004c9c  mov     rcx, r13
0x140004c9f  call    ?NextElement@JsonParser@Marshal@@AEAA_NDW4ParseError@12@@Z; Marshal::JsonParser::NextElement(char,Marshal::JsonParser::ParseError)
0x140004ca4  jmp     loc_1400049C2
0x140004ca9  mov     al, r12b
0x140004cac  mov     rcx, [rbp+4Fh+var_38]
0x140004cb0  xor     rcx, rsp; StackCookie
0x140004cb3  call    __security_check_cookie
0x140004cb8  mov     rbx, [rsp+120h+arg_18]
0x140004cc0  add     rsp, 0F0h
0x140004cc7  pop     r15
0x140004cc9  pop     r14
0x140004ccb  pop     r13
0x140004ccd  pop     r12
0x140004ccf  pop     rdi
0x140004cd0  pop     rsi
0x140004cd1  pop     rbp
0x140004cd2  retn
0x140004cd3  call    ?_Throw_tree_length_error@std@@YAXXZ; std::_Throw_tree_length_error(void)
```
