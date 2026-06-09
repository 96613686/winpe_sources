# WaasMedic::CRemediationPluginBase::EvaluatePluginImpactLevelBlock(winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentImpactLevel,tagPluginActionApplicability *)

- ea: `0x18001bcdc`
- end: `0x18001bfbd`
- name: `?EvaluatePluginImpactLevelBlock@CRemediationPluginBase@WaasMedic@@IEAAJW4WaaSAssessmentImpactLevel@WaasMedicDocked@Internal@Windows@winrt@@PEAW4tagPluginActionApplicability@@@Z`
- size: `737`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18001cae0`
- `0x18003b790`

## callees

- `0x180003bb0`
- `0x1800070cc`
- `0x180007590`
- `0x180009a54`
- `0x18000b308`
- `0x18001bcdc`
- `0x18001d658`
- `0x18002543c`
- `0x180064010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18001be13`
- `api-ms-win-crt-private-l1-1-0!_o_towupper` at `0x18001be13`

## string_xrefs

- `0x18001bdc7`: `onecore\enduser\waasmedic\lib\plugins\remediationpluginbase.cpp`
- `0x18001bf79`: `onecore\enduser\waasmedic\lib\plugins\remediationpluginbase.cpp`
- `0x18001bf28`: `Plugin %s action inapplicable because of lower impact level.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaasMedic::CRemediationPluginBase::EvaluatePluginImpactLevelBlock(__int64 a1, int a2, _DWORD *a3)
{
  __int64 v6; // rbx
  __int64 (__fastcall *v7)(__int64, _OWORD *, _OWORD *, wchar_t **); // rdi
  __int64 v8; // rdx
  __int64 v9; // r8
  int v10; // ebx
  __m128i v11; // rax
  wchar_t *v12; // rcx
  wchar_t **v13; // rdi
  wchar_t **v14; // r8
  wint_t *v15; // rsi
  wint_t *v16; // rbx
  wchar_t **v17; // r9
  int v18; // r8d
  wchar_t **v19; // r9
  wchar_t **v20; // r9
  wchar_t **v21; // r9
  int v23; // [rsp+20h] [rbp-59h]
  wchar_t *S1[2]; // [rsp+30h] [rbp-49h] BYREF
  __m128i si128; // [rsp+40h] [rbp-39h]
  int v26; // [rsp+50h] [rbp-29h]
  char v27; // [rsp+54h] [rbp-25h]
  _OWORD v28[2]; // [rsp+58h] [rbp-21h] BYREF
  _OWORD v29[2]; // [rsp+78h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  *(_OWORD *)S1 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(S1[0]) = 0;
  v27 = 1;
  v26 = 1;
  *a3 = 0;
  v6 = *(_QWORD *)(a1 + 104);
  v7 = *(__int64 (__fastcall **)(__int64, _OWORD *, _OWORD *, wchar_t **))(*(_QWORD *)v6 + 16LL);
  memset(v29, 0, sizeof(v29));
  std::wstring::_Construct<1,unsigned short const *>(v29, L"IMPACTLEVEL", 11);
  v8 = *(_QWORD *)(a1 + 112);
  memset(v28, 0, sizeof(v28));
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)(v8 + 2 * v9) );
  std::wstring::_Construct<1,unsigned short const *>(v28, v8, v9);
  v10 = v7(v6, v28, v29, S1);
  std::wstring::~wstring(v28);
  std::wstring::~wstring(v29);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x14D,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\remediationpluginbase.cpp",
      (const char *)(unsigned int)v10,
      v23);
    goto LABEL_43;
  }
  v11.m128i_i64[1] = si128.m128i_i64[1];
  v12 = S1[0];
  if ( si128.m128i_i64[1] > 7uLL )
  {
    v13 = (wchar_t **)S1[0];
    v14 = (wchar_t **)S1[0];
  }
  else
  {
    v13 = S1;
    v14 = S1;
  }
  v11.m128i_i64[0] = si128.m128i_i64[0];
  v15 = (wint_t *)v14 + si128.m128i_i64[0];
  v16 = (wint_t *)S1;
  if ( si128.m128i_i64[1] > 7uLL )
    v16 = S1[0];
  if ( v16 != v15 )
  {
    do
    {
      *(_WORD *)v13 = towupper(*v16);
      v13 = (wchar_t **)((char *)v13 + 2);
      ++v16;
    }
    while ( v16 != v15 );
    v11 = si128;
    v12 = S1[0];
  }
  v17 = S1;
  if ( v11.m128i_i64[1] > 7uLL )
    v17 = (wchar_t **)v12;
  if ( v11.m128i_i64[0] != 4 )
  {
LABEL_19:
    v19 = S1;
    if ( v11.m128i_i64[1] > 7uLL )
      v19 = (wchar_t **)v12;
    if ( v11.m128i_i64[0] == 6 )
    {
      if ( !wmemcmp((const wchar_t *)v19, L"MEDIUM", 6u) )
      {
        v18 = 2;
        goto LABEL_36;
      }
      v11 = si128;
      v12 = S1[0];
    }
    v20 = S1;
    if ( v11.m128i_i64[1] > 7uLL )
      v20 = (wchar_t **)v12;
    if ( v11.m128i_i64[0] == 3 )
    {
      if ( !wmemcmp((const wchar_t *)v20, L"LOW", 3u) )
      {
        v18 = 1;
        goto LABEL_36;
      }
      v11 = si128;
      v12 = S1[0];
    }
    v21 = S1;
    if ( v11.m128i_i64[1] > 7uLL )
      v21 = (wchar_t **)v12;
    if ( v11.m128i_i64[0] == 4 )
    {
      if ( !wmemcmp((const wchar_t *)v21, L"NONE", 4u) )
      {
        v18 = 0;
        goto LABEL_36;
      }
      v11.m128i_i64[1] = si128.m128i_i64[1];
      v12 = S1[0];
    }
    v11.m128i_i64[0] = (__int64)S1;
    if ( v11.m128i_i64[1] > 7uLL )
      v11.m128i_i64[0] = (__int64)v12;
    v10 = -2147467259;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x164,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\remediationpluginbase.cpp",
      (const char *)0x80004005LL,
      (int)"Invalid impact level %ws",
      (const char *)v11.m128i_i64[0]);
    goto LABEL_43;
  }
  if ( wmemcmp((const wchar_t *)v17, L"HIGH", 4u) )
  {
    v11 = si128;
    v12 = S1[0];
    goto LABEL_19;
  }
  v18 = 3;
LABEL_36:
  if ( v18 <= a2 )
  {
    std::wstring::~wstring(S1);
    return 0;
  }
  *a3 = 2;
  LogLevelW(4u, L"Plugin %s action inapplicable because of lower impact level.", *(_QWORD *)(a1 + 112));
  v10 = 0;
LABEL_43:
  std::wstring::~wstring(S1);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001bcdc  mov     [rsp-8+arg_8], rbx
0x18001bce1  push    rbp
0x18001bce2  push    rsi
0x18001bce3  push    rdi
0x18001bce4  push    r12
0x18001bce6  push    r13
0x18001bce8  push    r14
0x18001bcea  push    r15
0x18001bcec  lea     rbp, [rsp-27h]
0x18001bcf1  sub     rsp, 0A0h
0x18001bcf8  mov     rax, cs:__security_cookie
0x18001bcff  xor     rax, rsp
0x18001bd02  mov     [rbp+57h+var_38], rax
0x18001bd06  mov     r15, r8
0x18001bd09  mov     r12d, edx
0x18001bd0c  mov     r14, rcx
0x18001bd0f  xorps   xmm0, xmm0
0x18001bd12  movups  xmmword ptr [rbp+57h+S1], xmm0
0x18001bd16  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001bd1e  movdqu  [rbp+57h+var_90], xmm1
0x18001bd23  xor     r13d, r13d
0x18001bd26  mov     word ptr [rbp+57h+S1], r13w
0x18001bd2b  mov     [rbp+57h+var_7C], 1
0x18001bd2f  mov     [rbp+57h+var_80], 1
0x18001bd36  mov     [r8], r13d
0x18001bd39  mov     rbx, [rcx+68h]
0x18001bd3d  mov     rax, [rbx]
0x18001bd40  mov     rdi, [rax+10h]
0x18001bd44  movups  [rbp+57h+var_58], xmm0
0x18001bd48  xorps   xmm1, xmm1
0x18001bd4b  movdqu  [rbp+57h+var_48], xmm1
0x18001bd50  lea     r8d, [r13+0Bh]
0x18001bd54  lea     rdx, aImpactlevel; "IMPACTLEVEL"
0x18001bd5b  lea     rcx, [rbp+57h+var_58]
0x18001bd5f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001bd64  nop
0x18001bd65  mov     rdx, [r14+70h]
0x18001bd69  xorps   xmm0, xmm0
0x18001bd6c  movups  [rbp+57h+var_78], xmm0
0x18001bd70  xorps   xmm1, xmm1
0x18001bd73  movdqu  [rbp+57h+var_68], xmm1
0x18001bd78  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001bd7c  inc     r8
0x18001bd7f  cmp     [rdx+r8*2], r13w
0x18001bd84  jnz     short loc_18001BD7C
0x18001bd86  lea     rcx, [rbp+57h+var_78]
0x18001bd8a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001bd8f  nop
0x18001bd90  lea     r9, [rbp+57h+S1]
0x18001bd94  lea     r8, [rbp+57h+var_58]
0x18001bd98  lea     rdx, [rbp+57h+var_78]
0x18001bd9c  mov     rcx, rbx
0x18001bd9f  mov     rax, rdi
0x18001bda2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bda7  mov     ebx, eax
0x18001bda9  lea     rcx, [rbp+57h+var_78]; void *
0x18001bdad  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bdb2  nop
0x18001bdb3  lea     rcx, [rbp+57h+var_58]; void *
0x18001bdb7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bdbc  test    ebx, ebx
0x18001bdbe  jns     short loc_18001BDDD
0x18001bdc0  mov     rcx, [rbp+5Fh]; this
0x18001bdc4  mov     r9d, ebx; char *
0x18001bdc7  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18001bdce  mov     edx, 14Dh; void *
0x18001bdd3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001bdd8  jmp     loc_18001BF8B
0x18001bddd  mov     rdx, qword ptr [rbp+57h+var_90+8]
0x18001bde1  mov     rcx, [rbp+57h+S1]
0x18001bde5  cmp     rdx, 7
0x18001bde9  ja      short loc_18001BDF5
0x18001bdeb  lea     rdi, [rbp+57h+S1]
0x18001bdef  lea     r8, [rbp+57h+S1]
0x18001bdf3  jmp     short loc_18001BDFB
0x18001bdf5  mov     rdi, rcx
0x18001bdf8  mov     r8, rcx
0x18001bdfb  mov     rax, qword ptr [rbp+57h+var_90]
0x18001bdff  lea     rsi, [r8+rax*2]
0x18001be03  lea     rbx, [rbp+57h+S1]
0x18001be07  cmova   rbx, rcx
0x18001be0b  cmp     rbx, rsi
0x18001be0e  jz      short loc_18001BE35
0x18001be10  movzx   ecx, word ptr [rbx]; C
0x18001be13  call    cs:__imp_towupper
0x18001be19  mov     [rdi], ax
0x18001be1c  lea     rdi, [rdi+2]
0x18001be20  add     rbx, 2
0x18001be24  cmp     rbx, rsi
0x18001be27  jnz     short loc_18001BE10
0x18001be29  mov     rdx, qword ptr [rbp+57h+var_90+8]
0x18001be2d  mov     rax, qword ptr [rbp+57h+var_90]
0x18001be31  mov     rcx, [rbp+57h+S1]
0x18001be35  lea     r9, [rbp+57h+S1]
0x18001be39  cmp     rdx, 7
0x18001be3d  cmova   r9, rcx
0x18001be41  mov     ebx, 4
0x18001be46  cmp     rax, rbx
0x18001be49  jnz     short loc_18001BE76
0x18001be4b  mov     r8d, ebx; N
0x18001be4e  lea     rdx, aHigh; "HIGH"
0x18001be55  mov     rcx, r9; S1
0x18001be58  call    wmemcmp
0x18001be5d  test    eax, eax
0x18001be5f  jnz     short loc_18001BE6A
0x18001be61  lea     r8d, [rbx-1]
0x18001be65  jmp     loc_18001BF18
0x18001be6a  mov     rdx, qword ptr [rbp+57h+var_90+8]
0x18001be6e  mov     rax, qword ptr [rbp+57h+var_90]
0x18001be72  mov     rcx, [rbp+57h+S1]
0x18001be76  lea     r9, [rbp+57h+S1]
0x18001be7a  cmp     rdx, 7
0x18001be7e  cmova   r9, rcx
0x18001be82  mov     r8d, 6; N
0x18001be88  cmp     rax, r8
0x18001be8b  jnz     short loc_18001BEB2
0x18001be8d  lea     rdx, aMedium; "MEDIUM"
0x18001be94  mov     rcx, r9; S1
0x18001be97  call    wmemcmp
0x18001be9c  test    eax, eax
0x18001be9e  jnz     short loc_18001BEA6
0x18001bea0  lea     r8d, [rax+2]
0x18001bea4  jmp     short loc_18001BF18
0x18001bea6  mov     rdx, qword ptr [rbp+57h+var_90+8]
0x18001beaa  mov     rax, qword ptr [rbp+57h+var_90]
0x18001beae  mov     rcx, [rbp+57h+S1]
0x18001beb2  lea     r9, [rbp+57h+S1]
0x18001beb6  cmp     rdx, 7
0x18001beba  cmova   r9, rcx
0x18001bebe  mov     r8d, 3; N
0x18001bec4  cmp     rax, r8
0x18001bec7  jnz     short loc_18001BEEE
0x18001bec9  lea     rdx, aLow; "LOW"
0x18001bed0  mov     rcx, r9; S1
0x18001bed3  call    wmemcmp
0x18001bed8  test    eax, eax
0x18001beda  jnz     short loc_18001BEE2
0x18001bedc  lea     r8d, [rax+1]
0x18001bee0  jmp     short loc_18001BF18
0x18001bee2  mov     rdx, qword ptr [rbp+57h+var_90+8]
0x18001bee6  mov     rax, qword ptr [rbp+57h+var_90]
0x18001beea  mov     rcx, [rbp+57h+S1]
0x18001beee  lea     r9, [rbp+57h+S1]
0x18001bef2  cmp     rdx, 7
0x18001bef6  cmova   r9, rcx
0x18001befa  cmp     rax, rbx
0x18001befd  jnz     short loc_18001BF50
0x18001beff  mov     r8, rbx; N
0x18001bf02  lea     rdx, aNone_0; "NONE"
0x18001bf09  mov     rcx, r9; S1
0x18001bf0c  call    wmemcmp
0x18001bf11  test    eax, eax
0x18001bf13  jnz     short loc_18001BF48
0x18001bf15  mov     r8d, r13d
0x18001bf18  cmp     r8d, r12d
0x18001bf1b  jle     short loc_18001BF3B
0x18001bf1d  mov     dword ptr [r15], 2
0x18001bf24  mov     r8, [r14+70h]
0x18001bf28  lea     rdx, aPluginSActionI; "Plugin %s action inapplicable because o"...
0x18001bf2f  mov     ecx, ebx; unsigned __int8
0x18001bf31  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001bf36  mov     ebx, r13d
0x18001bf39  jmp     short loc_18001BF8B
0x18001bf3b  lea     rcx, [rbp+57h+S1]; void *
0x18001bf3f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bf44  xor     eax, eax
0x18001bf46  jmp     short loc_18001BF96
0x18001bf48  mov     rdx, qword ptr [rbp+57h+var_90+8]
0x18001bf4c  mov     rcx, [rbp+57h+S1]
0x18001bf50  lea     rax, [rbp+57h+S1]
0x18001bf54  cmp     rdx, 7
0x18001bf58  cmova   rax, rcx
0x18001bf5c  mov     rcx, [rbp+5Fh]; this
0x18001bf60  mov     [rsp+0D0h+var_A8], rax; char *
0x18001bf65  lea     rax, aInvalidImpactL; "Invalid impact level %ws"
0x18001bf6c  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18001bf71  mov     ebx, 80004005h
0x18001bf76  mov     r9d, ebx; char *
0x18001bf79  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18001bf80  mov     edx, 164h; void *
0x18001bf85  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18001bf8a  nop
0x18001bf8b  lea     rcx, [rbp+57h+S1]; void *
0x18001bf8f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001bf94  mov     eax, ebx
0x18001bf96  mov     rcx, [rbp+57h+var_38]
0x18001bf9a  xor     rcx, rsp; StackCookie
0x18001bf9d  call    __security_check_cookie
0x18001bfa2  mov     rbx, [rsp+0D0h+arg_8]
0x18001bfaa  add     rsp, 0A0h
0x18001bfb1  pop     r15
0x18001bfb3  pop     r14
0x18001bfb5  pop     r13
0x18001bfb7  pop     r12
0x18001bfb9  pop     rdi
0x18001bfba  pop     rsi
0x18001bfbb  pop     rbp
0x18001bfbc  retn
```
