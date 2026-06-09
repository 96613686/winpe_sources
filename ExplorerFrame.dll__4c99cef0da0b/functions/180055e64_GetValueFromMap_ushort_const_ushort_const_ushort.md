# GetValueFromMap(ushort const *,ushort const *,ushort * *)

- ea: `0x180055e64`
- end: `0x1800562e3`
- name: `?GetValueFromMap@@YAJPEBG0PEAPEAG@Z`
- size: `1151`
- prototype: `__int64 __fastcall(PCWSTR pszStart, LPCWSTR pszStr1, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001d780`
- `0x180055b40`
- `0x18007f8e8`
- `0x1800807ec`

## callees

- `0x180055e64`
- `0x1800563fc`
- `0x1801406ec`

## import_xrefs

- `SHLWAPI!StrChrW` at `0x180055ee0`
- `SHLWAPI!StrChrW` at `0x180055f09`
- `SHLWAPI!StrChrW` at `0x180055ee0`
- `SHLWAPI!StrChrW` at `0x180055f09`
- `SHLWAPI!__imp_StrCmpNICW` at `0x180055f5b`
- `SHLWAPI!__imp_StrCmpNICW` at `0x180055fe7`
- `SHLWAPI!__imp_StrCmpNICW` at `0x180055f5b`
- `SHLWAPI!__imp_StrCmpNICW` at `0x180055fe7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180056066`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180056169`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180056066`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180056169`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055f99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056009`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056297`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055f99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056009`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180056297`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetValueFromMap(PCWSTR pszStart, LPCWSTR pszStr1, unsigned __int16 **a3)
{
  const WCHAR *v3; // r15
  const WCHAR *v4; // r13
  __int64 v5; // rax
  _WORD *v6; // r14
  int v7; // esi
  bool v8; // cf
  signed int i; // ebx
  PWSTR v10; // rax
  PWSTR v11; // rbx
  __int64 v12; // rdi
  const WCHAR *v13; // r15
  int v14; // edx
  int v15; // ecx
  PWSTR v16; // r12
  __int64 v17; // rax
  __int64 v18; // r12
  unsigned __int64 v19; // rsi
  unsigned __int16 **v20; // r12
  unsigned __int64 v21; // rdi
  int v23; // r13d
  unsigned __int64 v24; // rsi
  unsigned __int64 v25; // rax
  unsigned __int64 v26; // rdi
  _WORD *v27; // rax
  unsigned __int64 v28; // rcx
  WCHAR *v29; // rax
  WCHAR v30; // dx
  WCHAR *v31; // rcx
  int v32; // r9d
  unsigned __int16 *v33; // rdx
  unsigned __int64 v34; // r8
  unsigned __int16 *v35; // rax
  __int64 v36; // rcx
  WCHAR v37; // r9
  __int64 v38; // r9
  unsigned __int16 *v39; // rcx
  __int64 v40; // rdi
  unsigned __int16 *v41; // rax
  int v42; // [rsp+30h] [rbp-38h]
  const WCHAR *pszStr2; // [rsp+B0h] [rbp+48h]
  const WCHAR *pszStr1a; // [rsp+B8h] [rbp+50h]
  PWSTR v46; // [rsp+C8h] [rbp+60h]

  pszStr2 = pszStart;
  v3 = pszStart;
  v4 = &WindowName;
  if ( pszStr1 )
    v4 = pszStr1;
  pszStr1a = v4;
  v5 = -1;
  do
    ++v5;
  while ( v4[v5] );
  v42 = v5;
  v6 = 0;
  v7 = -1;
  v8 = pszStart != 0;
LABEL_6:
  for ( i = v8 ? 0 : 0x80004005; ; i = -2147467259 )
  {
    while ( 1 )
    {
      if ( i < 0 )
      {
LABEL_77:
        v20 = a3;
        goto LABEL_78;
      }
      v10 = StrChrW(v3, 0x3Du);
      v11 = v10;
      if ( v10 )
        break;
      i = -2147467259;
    }
    v12 = v10 - v3;
    v13 = v10 + 1;
    v16 = StrChrW(v10 + 1, 0x2Cu);
    v46 = v16;
    if ( !v16 )
    {
      v17 = -1;
      do
        ++v17;
      while ( v13[v17] );
      v16 = (PWSTR)&v13[v17];
      v46 = v16;
    }
    v18 = v16 - v13;
    if ( (_DWORD)v12 == 1 )
    {
      if ( !*v4 )
      {
        v32 = v18;
        v20 = a3;
        i = _AllocStringWorker<CTCoAllocPolicy>(v15, v14, (_DWORD)v13, v32);
        goto LABEL_19;
      }
    }
    else if ( (int)v12 < 1 )
    {
      break;
    }
    if ( *(v11 - 1) != 42 )
      break;
    if ( !*v4 )
      goto LABEL_53;
    v23 = v12 - 1;
    if ( (int)v12 - 1 >= 1 && *(v11 - 2) == 46 )
      v23 = v12 - 2;
    if ( StrCmpNICW(pszStr1a, pszStr2, v23) || v23 <= v7 )
      goto LABEL_53;
    if ( v6 )
    {
      CoTaskMemFree(v6);
      v6 = 0;
    }
    if ( v13 )
    {
      v24 = -1;
      do
        ++v24;
      while ( v13[v24] );
      if ( (_DWORD)v18 == -1 )
      {
        v25 = v24;
      }
      else
      {
        v25 = (int)v18;
        if ( (int)v18 < v24 )
          v24 = (int)v18;
      }
      v26 = v25 + 1;
      if ( v25 + 1 >= v25 && is_mul_ok(v26, 2u) )
      {
        v27 = CoTaskMemAlloc(2 * v26);
        if ( v27 )
        {
          i = 0;
          v6 = v27;
          *v27 = 0;
        }
        else
        {
          i = -2147024882;
        }
        if ( i >= 0 && v26 )
        {
          if ( v26 > 0x7FFFFFFF || v24 > 0x7FFFFFFE )
          {
            *v6 = 0;
          }
          else
          {
            v28 = v24;
            v29 = v6;
            do
            {
              if ( !v28 )
                break;
              v30 = *v13;
              if ( !*v13 )
                break;
              ++v13;
              *v29++ = v30;
              --v28;
              --v26;
            }
            while ( v26 );
            v31 = v29 - 1;
            if ( v26 )
              v31 = v29;
            *v31 = 0;
          }
        }
      }
      else
      {
        i = -2147024362;
      }
    }
    else
    {
      i = 0;
    }
    v7 = v23;
LABEL_52:
    if ( i < 0 )
      goto LABEL_77;
LABEL_53:
    v4 = pszStr1a;
    if ( *v46 )
    {
      v3 = v46 + 1;
      pszStr2 = v46 + 1;
      v8 = v46[1] != 0;
      goto LABEL_6;
    }
    v3 = pszStr2;
  }
  if ( (_DWORD)v12 != v42 )
    goto LABEL_53;
  i = 0;
  if ( StrCmpNICW(v4, pszStr2, v12) )
    goto LABEL_52;
  v19 = (int)v18;
  v20 = a3;
  *a3 = 0;
  v21 = v19 + 1;
  if ( v19 + 1 < v19 || !is_mul_ok(v21, 2u) )
  {
    i = -2147024362;
    goto LABEL_19;
  }
  v33 = (unsigned __int16 *)CoTaskMemAlloc(2 * v21);
  *a3 = v33;
  i = v33 == 0 ? 0x8007000E : 0;
  if ( v33 )
  {
    if ( v21 <= 0x7FFFFFFF )
    {
      if ( v19 < 0x7FFFFFFF )
      {
        if ( !v13 )
        {
          v13 = &WindowName;
          v19 = 0;
        }
        if ( v21 )
        {
          v34 = v21;
          v35 = v33;
          v36 = 0;
          do
          {
            if ( !v19 )
              break;
            v37 = *v13;
            if ( !*v13 )
              break;
            ++v13;
            *v35++ = v37;
            --v19;
            ++v36;
            --v34;
          }
          while ( v34 );
          v38 = v36 - 1;
          if ( v34 )
            v38 = v36;
          v39 = v35 - 1;
          if ( v34 )
            v39 = v35;
          *v39 = 0;
          if ( v34 )
          {
            v8 = v21 == v38;
            v40 = v21 - v38;
            if ( !v8 && v40 != 1 && (unsigned __int64)(2 * v40) > 2 )
              memset_0(&v33[v38 + 1], 0, 2 * v40 - 2);
          }
        }
        goto LABEL_19;
      }
      if ( v19 == -1 )
        goto LABEL_19;
    }
    *v33 = 0;
  }
LABEL_19:
  if ( i >= 0 )
    goto LABEL_20;
LABEL_78:
  if ( v6 )
  {
    v41 = v6;
    v6 = 0;
    *v20 = v41;
    i = 0;
  }
LABEL_20:
  if ( v6 )
    CoTaskMemFree(v6);
  return (unsigned int)i;
}

```

## disassembly

```asm
0x180055e64  mov     [rsp-40h+arg_10], r8
0x180055e69  mov     [rsp-40h+pszStr2], rcx
0x180055e6e  push    rbp
0x180055e6f  push    rbx
0x180055e70  push    rsi
0x180055e71  push    rdi
0x180055e72  push    r12
0x180055e74  push    r13
0x180055e76  push    r14
0x180055e78  push    r15
0x180055e7a  mov     rbp, rsp
0x180055e7d  sub     rsp, 68h
0x180055e81  mov     r15, rcx
0x180055e84  lea     r13, WindowName
0x180055e8b  xor     r10d, r10d
0x180055e8e  test    rdx, rdx
0x180055e91  cmovnz  r13, rdx
0x180055e95  mov     [rbp+pszStr1], r13
0x180055e99  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180055e9d  mov     rax, rcx
0x180055ea0  inc     rax
0x180055ea3  cmp     [r13+rax*2+0], r10w
0x180055ea9  jnz     short loc_180055EA0
0x180055eab  mov     qword ptr [rbp+var_38], rax
0x180055eaf  mov     r14, r10
0x180055eb2  mov     [rbp+var_28], r10
0x180055eb6  mov     [rbp+var_20], r10
0x180055eba  mov     [rbp+var_18], r10
0x180055ebe  mov     esi, ecx
0x180055ec0  mov     rax, r15
0x180055ec3  neg     rax
0x180055ec6  sbb     ebx, ebx
0x180055ec8  not     ebx
0x180055eca  and     ebx, 80004005h
0x180055ed0  test    ebx, ebx
0x180055ed2  js      loc_180056237
0x180055ed8  mov     edx, 3Dh ; '='; wMatch
0x180055edd  mov     rcx, r15; pszStart
0x180055ee0  call    cs:__imp_StrChrW
0x180055ee6  mov     rbx, rax
0x180055ee9  xor     r10d, r10d
0x180055eec  test    rax, rax
0x180055eef  jz      loc_180055FB2
0x180055ef5  mov     rdi, rax
0x180055ef8  sub     rdi, r15
0x180055efb  sar     rdi, 1
0x180055efe  lea     r15, [rax+2]
0x180055f02  lea     edx, [r10+2Ch]; wMatch
0x180055f06  mov     rcx, r15; pszStart
0x180055f09  call    cs:__imp_StrChrW
0x180055f0f  mov     r12, rax
0x180055f12  mov     [rbp+arg_18], rax
0x180055f16  xor     r10d, r10d
0x180055f19  test    rax, rax
0x180055f1c  jnz     short loc_180055F34
0x180055f1e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180055f22  inc     rax
0x180055f25  cmp     [r15+rax*2], r10w
0x180055f2a  jnz     short loc_180055F22
0x180055f2c  lea     r12, [r15+rax*2]
0x180055f30  mov     [rbp+arg_18], r12
0x180055f34  sub     r12, r15
0x180055f37  sar     r12, 1
0x180055f3a  cmp     edi, 1
0x180055f3d  jz      loc_180056128
0x180055f43  jge     short loc_180055FBC
0x180055f45  cmp     edi, [rbp+var_38]
0x180055f48  jnz     loc_1800560FB
0x180055f4e  mov     ebx, r10d
0x180055f51  mov     r8d, edi; nChar
0x180055f54  mov     rdx, [rbp+pszStr2]; pszStr2
0x180055f58  mov     rcx, r13; pszStr1
0x180055f5b  call    cs:__imp_StrCmpNICW
0x180055f61  xor     r10d, r10d
0x180055f64  test    eax, eax
0x180055f66  jnz     loc_1800560EF
0x180055f6c  movsxd  rsi, r12d
0x180055f6f  mov     r12, [rbp+arg_10]
0x180055f73  mov     [r12], r10
0x180055f77  lea     rdi, [rsi+1]
0x180055f7b  cmp     rdi, rsi
0x180055f7e  jnb     loc_180056151
0x180055f84  mov     ebx, 80070216h
0x180055f89  test    ebx, ebx
0x180055f8b  js      loc_18005623B
0x180055f91  test    r14, r14
0x180055f94  jz      short loc_180055F9F
0x180055f96  mov     rcx, r14; pv
0x180055f99  call    cs:__imp_CoTaskMemFree
0x180055f9f  mov     eax, ebx
0x180055fa1  add     rsp, 68h
0x180055fa5  pop     r15
0x180055fa7  pop     r14
0x180055fa9  pop     r13
0x180055fab  pop     r12
0x180055fad  pop     rdi
0x180055fae  pop     rsi
0x180055faf  pop     rbx
0x180055fb0  pop     rbp
0x180055fb1  retn
0x180055fb2  mov     ebx, 80004005h
0x180055fb7  jmp     loc_180055ED0
0x180055fbc  cmp     word ptr [rbx-2], 2Ah ; '*'
0x180055fc1  jnz     short loc_180055F45
0x180055fc3  cmp     [r13+0], r10w
0x180055fc8  jz      loc_1800560FB
0x180055fce  lea     r13d, [rdi-1]
0x180055fd2  cmp     r13d, 1
0x180055fd6  jge     loc_1800562C6
0x180055fdc  mov     r8d, r13d; nChar
0x180055fdf  mov     rdx, [rbp+pszStr2]; pszStr2
0x180055fe3  mov     rcx, [rbp+pszStr1]; pszStr1
0x180055fe7  call    cs:__imp_StrCmpNICW
0x180055fed  xor     r10d, r10d
0x180055ff0  test    eax, eax
0x180055ff2  jnz     loc_1800560FB
0x180055ff8  cmp     r13d, esi
0x180055ffb  jle     loc_1800560FB
0x180056001  test    r14, r14
0x180056004  jz      short loc_180056019
0x180056006  mov     rcx, r14; pv
0x180056009  call    cs:__imp_CoTaskMemFree
0x18005600f  xor     r10d, r10d
0x180056012  mov     r14d, r10d
0x180056015  mov     [rbp+var_28], r10
0x180056019  mov     [rbp+var_20], r10
0x18005601d  mov     [rbp+var_18], r10
0x180056021  test    r15, r15
0x180056024  jz      loc_18005628C
0x18005602a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18005602e  inc     rsi
0x180056031  cmp     [r15+rsi*2], r10w
0x180056036  jnz     short loc_18005602E
0x180056038  cmp     r12d, 0FFFFFFFFh
0x18005603c  jnz     loc_180056256
0x180056042  mov     rax, rsi
0x180056045  lea     rdi, [rax+1]
0x180056049  cmp     rdi, rax
0x18005604c  jb      loc_180056121
0x180056052  mov     eax, 2
0x180056057  mul     rdi
0x18005605a  test    rdx, rdx
0x18005605d  jnz     loc_180056121
0x180056063  mov     rcx, rax; cb
0x180056066  call    cs:__imp_CoTaskMemAlloc
0x18005606c  xor     r10d, r10d
0x18005606f  test    rax, rax
0x180056072  jz      loc_180056265
0x180056078  mov     ebx, r10d
0x18005607b  mov     [rbp+var_18], rdi
0x18005607f  mov     r14, rax
0x180056082  mov     [rbp+var_28], rax
0x180056086  mov     [rax], r10w
0x18005608a  test    ebx, ebx
0x18005608c  js      short loc_1800560E8
0x18005608e  test    rdi, rdi
0x180056091  jz      short loc_1800560E4
0x180056093  cmp     rdi, 7FFFFFFFh
0x18005609a  ja      loc_1800562D9
0x1800560a0  cmp     rsi, 7FFFFFFEh
0x1800560a7  ja      loc_1800562D9
0x1800560ad  mov     rcx, rsi
0x1800560b0  mov     rax, r14
0x1800560b3  test    rcx, rcx
0x1800560b6  jz      short loc_1800560D5
0x1800560b8  movzx   edx, word ptr [r15]
0x1800560bc  test    dx, dx
0x1800560bf  jz      short loc_1800560D5
0x1800560c1  add     r15, 2
0x1800560c5  mov     [rax], dx
0x1800560c8  add     rax, 2
0x1800560cc  dec     rcx
0x1800560cf  sub     rdi, 1
0x1800560d3  jnz     short loc_1800560B3
0x1800560d5  lea     rcx, [rax-2]
0x1800560d9  test    rdi, rdi
0x1800560dc  cmovnz  rcx, rax
0x1800560e0  mov     [rcx], r10w
0x1800560e4  mov     [rbp+var_20], rsi
0x1800560e8  mov     esi, r13d
0x1800560eb  mov     r13, [rbp+pszStr1]
0x1800560ef  test    ebx, ebx
0x1800560f1  mov     r15, [rbp+pszStr2]
0x1800560f5  js      loc_180056237
0x1800560fb  mov     rax, [rbp+arg_18]
0x1800560ff  mov     r13, [rbp+pszStr1]
0x180056103  cmp     [rax], r10w
0x180056107  jz      loc_18005626F
0x18005610d  lea     r15, [rax+2]
0x180056111  mov     [rbp+pszStr2], r15
0x180056115  movzx   eax, word ptr [r15]
0x180056119  neg     ax
0x18005611c  jmp     loc_180055EC6
0x180056121  mov     ebx, 80070216h
0x180056126  jmp     short loc_1800560E8
0x180056128  cmp     [r13+0], r10w
0x18005612d  jnz     loc_180055FBC
0x180056133  movsxd  r9, r12d
0x180056136  mov     r12, [rbp+arg_10]
0x18005613a  mov     [rsp+68h+var_40], r12
0x18005613f  mov     r8, r15
0x180056142  call    ??$_AllocStringWorker@VCTCoAllocPolicy@@@@YAJPEAXKPEBG_K2PEAPEAG@Z; _AllocStringWorker<CTCoAllocPolicy>(void *,ulong,ushort const *,unsigned __int64,unsigned __int64,ushort * *)
0x180056147  mov     ebx, eax
0x180056149  xor     r10d, r10d
0x18005614c  jmp     loc_180055F89
0x180056151  mov     r13d, 2
0x180056157  mov     eax, r13d
0x18005615a  mul     rdi
0x18005615d  test    rdx, rdx
0x180056160  jnz     loc_180055F84
0x180056166  mov     rcx, rax; cb
0x180056169  call    cs:__imp_CoTaskMemAlloc
0x18005616f  mov     rdx, rax
0x180056172  mov     [r12], rax
0x180056176  mov     rcx, rax
0x180056179  neg     rcx
0x18005617c  sbb     ebx, ebx
0x18005617e  not     ebx
0x180056180  and     ebx, 8007000Eh
0x180056186  xor     r10d, r10d
0x180056189  test    rax, rax
0x18005618c  jz      loc_180055F89
0x180056192  mov     eax, 7FFFFFFFh
0x180056197  cmp     rdi, rax
0x18005619a  ja      loc_1800562BD
0x1800561a0  cmp     rsi, rax
0x1800561a3  jnb     loc_1800562B4
0x1800561a9  test    r15, r15
0x1800561ac  jz      loc_18005627D
0x1800561b2  test    rdi, rdi
0x1800561b5  jz      loc_180055F89
0x1800561bb  mov     r8, rdi
0x1800561be  mov     rax, rdx
0x1800561c1  mov     rcx, r10
0x1800561c4  test    rsi, rsi
0x1800561c7  jz      short loc_1800561E9
0x1800561c9  movzx   r9d, word ptr [r15]
0x1800561cd  test    r9w, r9w
0x1800561d1  jz      short loc_1800561E9
0x1800561d3  add     r15, r13
0x1800561d6  mov     [rax], r9w
0x1800561da  add     rax, r13
0x1800561dd  dec     rsi
0x1800561e0  inc     rcx
0x1800561e3  sub     r8, 1
0x1800561e7  jnz     short loc_1800561C4
0x1800561e9  lea     r9, [rcx-1]
0x1800561ed  test    r8, r8
0x1800561f0  cmovnz  r9, rcx
0x1800561f4  lea     rcx, [rax-2]
0x1800561f8  cmovnz  rcx, rax
0x1800561fc  mov     [rcx], r10w
0x180056200  jz      loc_180055F89
0x180056206  sub     rdi, r9
0x180056209  cmp     rdi, 1
0x18005620d  jbe     loc_180055F89
0x180056213  lea     r8, [rdi+rdi]
0x180056217  cmp     r8, r13
0x18005621a  jbe     loc_180055F89
0x180056220  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x180056224  inc     r9
0x180056227  lea     rcx, [rdx+r9*2]; void *
0x18005622b  xor     edx, edx; Val
0x18005622d  call    memset_0
0x180056232  jmp     loc_180056149
0x180056237  mov     r12, [rbp+arg_10]
0x18005623b  test    r14, r14
0x18005623e  jz      loc_180055F91
0x180056244  mov     rax, r14
0x180056247  mov     r14, r10
0x18005624a  mov     [r12], rax
0x18005624e  mov     ebx, r10d
0x180056251  jmp     loc_180055F91
0x180056256  movsxd  rax, r12d
0x180056259  cmp     rax, rsi
0x18005625c  cmovb   rsi, rax
0x180056260  jmp     loc_180056045
0x180056265  mov     ebx, 8007000Eh
0x18005626a  jmp     loc_18005608A
0x18005626f  mov     ebx, 80004005h
0x180056274  mov     r15, [rbp+pszStr2]
0x180056278  jmp     loc_180055ED0
0x18005627d  lea     r15, WindowName
0x180056284  mov     rsi, r10
0x180056287  jmp     loc_1800561B2
0x18005628c  mov     ebx, r10d
0x18005628f  test    r14, r14
0x180056292  jz      short loc_1800562A7
0x180056294  mov     rcx, r14; pv
0x180056297  call    cs:__imp_CoTaskMemFree
0x18005629d  xor     r10d, r10d
0x1800562a0  mov     r14d, r10d
0x1800562a3  mov     [rbp+var_28], r10
0x1800562a7  mov     [rbp+var_20], r10
0x1800562ab  mov     [rbp+var_18], r10
0x1800562af  jmp     loc_1800560E8
0x1800562b4  test    rdi, rdi
0x1800562b7  jz      loc_180055F89
0x1800562bd  mov     [rdx], r10w
0x1800562c1  jmp     loc_180055F89
  ... truncated ...
```
