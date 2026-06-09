# NgcUtils::CombineSeparateStrings(ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x180006fa0`
- end: `0x180007354`
- name: `?CombineSeparateStrings@NgcUtils@@YAJPEBG00PEAPEAG@Z`
- size: `948`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800088d8`

## callees

- `0x180006fa0`
- `0x18000782c`
- `0x180062abc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800071d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007299`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800071d4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180007299`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800070bf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800070bf`

## string_xrefs

- `0x180007035`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x1800071c2`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x180007282`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x1800072ab`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x180007314`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x180007339`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x1800072d1`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall NgcUtils::CombineSeparateStrings(
        NgcUtils *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  const unsigned __int16 *v4; // r13
  NgcUtils *v5; // rbx
  NgcUtils *v6; // rax
  __int64 v7; // rcx
  int v8; // r12d
  const char *v9; // r9
  int v10; // edi
  __int64 v11; // rcx
  const unsigned __int16 *v12; // r14
  const unsigned __int16 *i; // rax
  const unsigned __int16 *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r10
  int v18; // edi
  unsigned __int64 v19; // rsi
  _WORD *v20; // rax
  _WORD *v21; // r15
  __int64 v22; // r9
  unsigned __int64 v23; // rdx
  __int64 v24; // rcx
  _WORD *v25; // r8
  _WORD *v26; // rax
  unsigned int v27; // edi
  unsigned int v28; // ebx
  unsigned __int64 v29; // rcx
  _WORD *v30; // rax
  unsigned __int64 v31; // rax
  _WORD *v32; // r8
  __int64 v33; // rcx
  unsigned __int64 v34; // rdx
  _WORD *v35; // rax
  __int64 v36; // rdx
  unsigned __int64 v37; // rcx
  _WORD *v38; // rax
  unsigned __int64 v39; // rax
  _WORD *v40; // rcx
  unsigned __int64 j; // rsi
  _WORD *v42; // rax
  int v43; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v4 = a3;
  v5 = this;
  if ( !this )
  {
    v10 = -2147024809;
LABEL_74:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
      (const char *)(unsigned int)v10,
      v43);
    return (unsigned int)v10;
  }
  v6 = this;
  v7 = 260;
  while ( *(_WORD *)v6 )
  {
    v6 = (NgcUtils *)((char *)v6 + 2);
    if ( !--v7 )
    {
      v8 = -2147024809;
      v9 = 0;
      v10 = -2147024809;
      goto LABEL_7;
    }
  }
  v8 = -2147024809;
  v9 = (const char *)(260 - v7);
  v10 = 0;
LABEL_7:
  if ( v10 < 0 )
    goto LABEL_74;
  v11 = 260;
  v12 = L"\\";
  for ( i = L"\\"; *i; ++i )
  {
    if ( !--v11 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB9,
        (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
        (const char *)0x80070057LL,
        v43);
      return 2147942487LL;
    }
  }
  if ( !a3 )
  {
    v18 = -2147024809;
LABEL_72:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBF,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
      (const char *)(unsigned int)v18,
      v43);
    return (unsigned int)v18;
  }
  v15 = a3;
  v16 = 260;
  while ( *v15 )
  {
    ++v15;
    if ( !--v16 )
    {
      v17 = 0;
      v18 = -2147024809;
      goto LABEL_18;
    }
  }
  v17 = 260 - v16;
  v18 = 0;
LABEL_18:
  if ( v18 < 0 )
    goto LABEL_72;
  v19 = (unsigned __int64)&v9[v17 + 1 + 260 - v11];
  if ( v19 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v9);
  v20 = LocalAlloc(0, 2 * v19 + 2);
  v21 = v20;
  if ( !v20 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
      (const char *)0x8007000ELL,
      v43);
    return 2147942414LL;
  }
  *v20 = 0;
  v20[v19] = 0;
  if ( !v19 )
  {
    v28 = -2147024809;
    goto LABEL_48;
  }
  if ( v19 > 0x7FFFFFFF )
  {
    v28 = -2147024809;
    *v20 = 0;
LABEL_48:
    v36 = 205;
    goto LABEL_46;
  }
  v22 = 2147483646;
  v23 = v19;
  v24 = 2147483646;
  v25 = v20;
  do
  {
    if ( !v24 )
      break;
    if ( !*(_WORD *)v5 )
      break;
    *v25 = *(_WORD *)v5;
    v5 = (NgcUtils *)((char *)v5 + 2);
    ++v25;
    --v24;
    --v23;
  }
  while ( v23 );
  v26 = v25 - 1;
  v27 = -2147024774;
  if ( v23 )
    v26 = v25;
  v28 = -2147024774;
  if ( v23 )
    v28 = 0;
  *v26 = 0;
  if ( !v23 )
    goto LABEL_48;
  v29 = v19;
  v30 = v21;
  do
  {
    if ( !*v30 )
      break;
    ++v30;
    --v29;
  }
  while ( v29 );
  v28 = -2147024809;
  if ( v29 )
  {
    v28 = 0;
    v31 = v19 - v29;
  }
  else
  {
    v31 = 0;
  }
  if ( !v29 )
    goto LABEL_45;
  v32 = &v21[v31];
  v33 = 2147483646;
  v34 = v19 - v31;
  if ( v19 != v31 )
  {
    do
    {
      if ( !v33 )
        break;
      if ( !*v12 )
        break;
      *v32++ = *v12++;
      --v33;
      --v34;
    }
    while ( v34 );
  }
  v35 = v32 - 1;
  v28 = -2147024774;
  if ( v34 )
  {
    v35 = v32;
    v28 = 0;
  }
  *v35 = 0;
  if ( !v34 )
  {
LABEL_45:
    v36 = 210;
LABEL_46:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v36,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
      (const char *)v28,
      v43);
    LocalFree(v21);
    return v28;
  }
  v37 = v19;
  v38 = v21;
  do
  {
    if ( !*v38 )
      break;
    ++v38;
    --v37;
  }
  while ( v37 );
  if ( v37 )
  {
    v8 = 0;
    v39 = v19 - v37;
  }
  else
  {
    v39 = 0;
  }
  if ( v37 )
  {
    v40 = &v21[v39];
    for ( j = v19 - v39; j; --j )
    {
      if ( !v22 )
        break;
      if ( !*v4 )
        break;
      *v40++ = *v4++;
      --v22;
    }
    v42 = v40 - 1;
    if ( j )
    {
      v42 = v40;
      v27 = 0;
    }
    *v42 = 0;
    if ( j )
    {
      *(_QWORD *)a4 = v21;
      return 0;
    }
  }
  else
  {
    v27 = v8;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD7,
    (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
    (const char *)v27,
    v43);
  LocalFree(v21);
  return v27;
}

```

## disassembly

```asm
0x180006fa0  mov     [rsp+arg_18], r9
0x180006fa5  push    rbx
0x180006fa6  push    rbp
0x180006fa7  push    rdi
0x180006fa8  push    r12
0x180006faa  push    r13; int
0x180006fac  sub     rsp, 20h
0x180006fb0  mov     r13, r8
0x180006fb3  mov     rbx, rcx
0x180006fb6  test    rcx, rcx
0x180006fb9  jz      loc_18000732F
0x180006fbf  mov     r10d, 104h
0x180006fc5  mov     rax, rbx
0x180006fc8  mov     ecx, r10d
0x180006fcb  nop     dword ptr [rax+rax+00h]
0x180006fd0  cmp     word ptr [rax], 0
0x180006fd4  jz      short loc_180006FF0
0x180006fd6  add     rax, 2
0x180006fda  sub     rcx, 1
0x180006fde  jnz     short loc_180006FD0
0x180006fe0  xor     ebp, ebp
0x180006fe2  mov     r12d, 80070057h
0x180006fe8  mov     r9d, ebp
0x180006feb  mov     edi, r12d
0x180006fee  jmp     short loc_180007000
0x180006ff0  mov     r9, r10
0x180006ff3  mov     r12d, 80070057h
0x180006ff9  sub     r9, rcx; char *
0x180006ffc  xor     ebp, ebp
0x180006ffe  mov     edi, ebp
0x180007000  test    edi, edi
0x180007002  js      loc_180007334
0x180007008  mov     [rsp+48h+arg_8], r14
0x18000700d  mov     rcx, r10
0x180007010  lea     r14, asc_1800DB4FC; "\\"
0x180007017  mov     rax, r14
0x18000701a  nop     word ptr [rax+rax+00h]
0x180007020  cmp     word ptr [rax], 0
0x180007024  jz      short loc_18000705D
0x180007026  add     rax, 2
0x18000702a  sub     rcx, 1
0x18000702e  jnz     short loc_180007020
0x180007030  mov     rcx, [rsp+48h]; this
0x180007035  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18000703c  mov     r9d, r12d; char *
0x18000703f  mov     edx, 0B9h; void *
0x180007044  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007049  mov     r14, [rsp+48h+arg_8]
0x18000704e  mov     eax, r12d
0x180007051  add     rsp, 20h
0x180007055  pop     r13
0x180007057  pop     r12
0x180007059  pop     rdi
0x18000705a  pop     rbp
0x18000705b  pop     rbx
0x18000705c  retn
0x18000705d  test    r8, r8
0x180007060  jz      loc_18000730C
0x180007066  mov     rax, r8
0x180007069  mov     rdx, r10
0x18000706c  mov     r8, r10
0x18000706f  sub     r8, rcx
0x180007072  cmp     word ptr [rax], 0
0x180007076  jz      short loc_18000708A
0x180007078  add     rax, 2
0x18000707c  sub     rdx, 1
0x180007080  jnz     short loc_180007072
0x180007082  mov     r10, rbp
0x180007085  mov     edi, r12d
0x180007088  jmp     short loc_18000708F
0x18000708a  sub     r10, rdx
0x18000708d  mov     edi, ebp
0x18000708f  test    edi, edi
0x180007091  js      loc_18000730F
0x180007097  mov     [rsp+48h+arg_0], rsi
0x18000709c  lea     rsi, [r8+1]
0x1800070a0  add     rsi, r10
0x1800070a3  add     rsi, r9
0x1800070a6  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800070aa  jz      loc_1800072CC
0x1800070b0  lea     rdx, ds:2[rsi*2]; uBytes
0x1800070b8  mov     [rsp+48h+arg_10], r15
0x1800070bd  xor     ecx, ecx; uFlags
0x1800070bf  call    cs:__imp_LocalAlloc
0x1800070c5  mov     r15, rax
0x1800070c8  test    rax, rax
0x1800070cb  jz      loc_1800072A6
0x1800070d1  mov     [rax], bp
0x1800070d4  mov     [rax+rsi*2], bp
0x1800070d8  test    rsi, rsi
0x1800070db  jz      loc_1800072F8
0x1800070e1  cmp     rsi, 7FFFFFFFh
0x1800070e8  ja      loc_1800072E3
0x1800070ee  mov     r9d, 7FFFFFFEh
0x1800070f4  mov     rdx, rsi
0x1800070f7  mov     ecx, r9d
0x1800070fa  mov     r8, rax
0x1800070fd  nop     dword ptr [rax]
0x180007100  test    rcx, rcx
0x180007103  jz      short loc_180007122
0x180007105  movzx   eax, word ptr [rbx]
0x180007108  test    ax, ax
0x18000710b  jz      short loc_180007122
0x18000710d  mov     [r8], ax
0x180007111  add     rbx, 2
0x180007115  add     r8, 2
0x180007119  dec     rcx
0x18000711c  sub     rdx, 1
0x180007120  jnz     short loc_180007100
0x180007122  test    rdx, rdx
0x180007125  lea     rax, [r8-2]
0x180007129  mov     edi, 8007007Ah
0x18000712e  cmovnz  rax, r8
0x180007132  mov     ebx, edi
0x180007134  cmovnz  ebx, ebp
0x180007137  mov     [rax], bp
0x18000713a  jz      loc_1800071F7
0x180007140  mov     rcx, rsi
0x180007143  mov     rax, r15
0x180007146  cmp     word ptr [rax], 0
0x18000714a  jz      short loc_180007156
0x18000714c  add     rax, 2
0x180007150  sub     rcx, 1
0x180007154  jnz     short loc_180007146
0x180007156  test    rcx, rcx
0x180007159  mov     ebx, r12d
0x18000715c  cmovnz  ebx, ebp
0x18000715f  jz      loc_1800072E8
0x180007165  mov     rax, rsi
0x180007168  sub     rax, rcx
0x18000716b  test    rcx, rcx
0x18000716e  jz      short loc_1800071B8
0x180007170  mov     rdx, rsi
0x180007173  lea     r8, [r15+rax*2]
0x180007177  mov     rcx, r9
0x18000717a  sub     rdx, rax
0x18000717d  jz      short loc_1800071A3
0x18000717f  nop
0x180007180  test    rcx, rcx
0x180007183  jz      short loc_1800071A3
0x180007185  movzx   eax, word ptr [r14]
0x180007189  test    ax, ax
0x18000718c  jz      short loc_1800071A3
0x18000718e  mov     [r8], ax
0x180007192  add     r14, 2
0x180007196  add     r8, 2
0x18000719a  dec     rcx
0x18000719d  sub     rdx, 1
0x1800071a1  jnz     short loc_180007180
0x1800071a3  test    rdx, rdx
0x1800071a6  lea     rax, [r8-2]
0x1800071aa  mov     ebx, edi
0x1800071ac  cmovnz  rax, r8
0x1800071b0  cmovnz  ebx, ebp
0x1800071b3  mov     [rax], bp
0x1800071b6  jnz     short loc_1800071FE
0x1800071b8  mov     edx, 0D2h; void *
0x1800071bd  mov     rcx, [rsp+48h]; this
0x1800071c2  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800071c9  mov     r9d, ebx; char *
0x1800071cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800071d1  mov     rcx, r15; hMem
0x1800071d4  call    cs:__imp_LocalFree
0x1800071da  mov     eax, ebx
0x1800071dc  mov     r15, [rsp+48h+arg_10]
0x1800071e1  mov     rsi, [rsp+48h+arg_0]
0x1800071e6  mov     r14, [rsp+48h+arg_8]
0x1800071eb  add     rsp, 20h
0x1800071ef  pop     r13
0x1800071f1  pop     r12
0x1800071f3  pop     rdi
0x1800071f4  pop     rbp
0x1800071f5  pop     rbx
0x1800071f6  retn
0x1800071f7  mov     edx, 0CDh
0x1800071fc  jmp     short loc_1800071BD
0x1800071fe  mov     rcx, rsi
0x180007201  mov     rax, r15
0x180007204  cmp     word ptr [rax], 0
0x180007208  jz      short loc_180007214
0x18000720a  add     rax, 2
0x18000720e  sub     rcx, 1
0x180007212  jnz     short loc_180007204
0x180007214  test    rcx, rcx
0x180007217  cmovnz  r12d, ebp
0x18000721b  jz      loc_1800072F0
0x180007221  mov     rax, rsi
0x180007224  sub     rax, rcx
0x180007227  test    rcx, rcx
0x18000722a  jz      short loc_18000727A
0x18000722c  lea     rcx, [r15+rax*2]
0x180007230  sub     rsi, rax
0x180007233  jz      short loc_180007258
0x180007235  test    r9, r9
0x180007238  jz      short loc_180007258
0x18000723a  movzx   eax, word ptr [r13+0]
0x18000723f  test    ax, ax
0x180007242  jz      short loc_180007258
0x180007244  mov     [rcx], ax
0x180007247  add     r13, 2
0x18000724b  add     rcx, 2
0x18000724f  dec     r9
0x180007252  sub     rsi, 1
0x180007256  jnz     short loc_180007235
0x180007258  test    rsi, rsi
0x18000725b  lea     rax, [rcx-2]
0x18000725f  cmovnz  rax, rcx
0x180007263  cmovnz  edi, ebp
0x180007266  mov     [rax], bp
0x180007269  jz      short loc_18000727D
0x18000726b  mov     rax, [rsp+48h+arg_18]
0x180007270  mov     [rax], r15
0x180007273  xor     eax, eax
0x180007275  jmp     loc_1800071DC
0x18000727a  mov     edi, r12d
0x18000727d  mov     rcx, [rsp+48h]; this
0x180007282  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180007289  mov     r9d, edi; char *
0x18000728c  mov     edx, 0D7h; void *
0x180007291  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007296  mov     rcx, r15; hMem
0x180007299  call    cs:__imp_LocalFree
0x18000729f  mov     eax, edi
0x1800072a1  jmp     loc_1800071DC
0x1800072a6  mov     rcx, [rsp+48h]; this
0x1800072ab  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800072b2  mov     r9d, 8007000Eh; char *
0x1800072b8  mov     edx, 0C7h; void *
0x1800072bd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800072c2  mov     eax, 8007000Eh
0x1800072c7  jmp     loc_1800071DC
0x1800072cc  mov     rcx, [rsp+48h]; this
0x1800072d1  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800072d8  mov     edx, 0F89h; void *
0x1800072dd  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800072e3  mov     ebx, r12d
0x1800072e6  jmp     short loc_180007304
0x1800072e8  mov     rax, rbp
0x1800072eb  jmp     loc_18000716B
0x1800072f0  mov     rax, rbp
0x1800072f3  jmp     loc_180007227
0x1800072f8  mov     ebx, r12d
0x1800072fb  test    rsi, rsi
0x1800072fe  jz      loc_1800071F7
0x180007304  mov     [rax], bp
0x180007307  jmp     loc_1800071F7
0x18000730c  mov     edi, r12d
0x18000730f  mov     rcx, [rsp+48h]; this
0x180007314  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18000731b  mov     r9d, edi; char *
0x18000731e  mov     edx, 0BFh; void *
0x180007323  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007328  mov     eax, edi
0x18000732a  jmp     loc_1800071E6
0x18000732f  mov     edi, 80070057h
0x180007334  mov     rcx, [rsp+48h]; this
0x180007339  lea     r8, aOnecoreDsSecur_36; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180007340  mov     r9d, edi; char *
0x180007343  mov     edx, 0B3h; void *
0x180007348  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000734d  mov     eax, edi
0x18000734f  jmp     loc_1800071EB
```
