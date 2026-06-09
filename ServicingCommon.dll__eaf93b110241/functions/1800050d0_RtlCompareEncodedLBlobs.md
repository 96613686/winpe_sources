# RtlCompareEncodedLBlobs

- ea: `0x1800050d0`
- end: `0x180005472`
- name: `RtlCompareEncodedLBlobs`
- size: `930`
- prototype: ``
- caller_count: `20`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004620`
- `0x180004ff0`
- `0x180005020`
- `0x1800050a0`
- `0x18000c5c0`
- `0x18000d1b0`
- `0x18001b760`
- `0x18001c690`
- `0x18001ccf0`
- `0x18001d7d0`
- `0x18001f8d0`
- `0x180020d24`
- `0x18004fda0`
- `0x180064f60`
- `0x180067680`
- `0x180067cc0`
- `0x180067e20`
- `0x18006e744`
- `0x180090964`
- `0x180090cf8`

## callees

- `0x1800031e0`
- `0x1800050d0`
- `0x18001fd10`
- `0x1800a0020`

## string_xrefs

- `0x180005126`: `RtlCompareEncodedLBlobs`
- `0x18000517d`: `RtlCompareEncodedLBlobs`
- `0x1800051a9`: `RtlCompareEncodedLBlobs`
- `0x1800051d8`: `RtlCompareEncodedLBlobs`
- `0x180005387`: `RtlCompareEncodedLBlobs`
- `0x180005400`: `RtlCompareEncodedLBlobs`
- `0x180005450`: `RtlCompareEncodedLBlobs`
- `0x18000545b`: `Not-null check failed: ComparisonResult`

## pseudocode

```c
__int64 __fastcall RtlCompareEncodedLBlobs(
        _QWORD *a1,
        __int64 (__fastcall *a2)(const char **, __int64, __int64),
        _QWORD *a3,
        __int64 (__fastcall *a4)(const char **, __int64, __int64),
        __int64 (__fastcall *a5)(_QWORD),
        int *a6)
{
  __int64 (__fastcall *v7)(const char **, __int64, __int64); // r12
  __int64 (__fastcall *v8)(const char **, __int64, __int64); // r9
  const char *v9; // rax
  int v11; // ecx
  __int64 v12; // rbx
  __int64 v13; // rdi
  __int64 v14; // r14
  __int64 v15; // r15
  __int64 v16; // rax
  unsigned int v17; // esi
  __int64 v18; // rax
  unsigned int v19; // r12d
  unsigned int v20; // esi
  unsigned int v21; // eax
  __int64 v22; // rax
  unsigned int v23; // esi
  __int64 v24; // rax
  unsigned int v25; // ecx
  const char *v26; // [rsp+20h] [rbp-49h] BYREF
  const char *v27; // [rsp+28h] [rbp-41h]
  __int64 v28; // [rsp+30h] [rbp-39h]
  const char *v29; // [rsp+38h] [rbp-31h]
  __int64 (__fastcall *v30)(const char **, __int64, __int64); // [rsp+40h] [rbp-29h]
  __int64 (__fastcall *v31)(const char **, __int64, __int64); // [rsp+48h] [rbp-21h]
  int *v32; // [rsp+50h] [rbp-19h]
  _BYTE v33[32]; // [rsp+58h] [rbp-11h] BYREF

  v7 = a4;
  v31 = a4;
  v8 = a2;
  v30 = a2;
  v32 = a6;
  if ( !a6 )
  {
    v28 = 2251;
    v26 = "onecore\\base\\lstring\\lblob.cpp";
    v27 = "RtlCompareEncodedLBlobs";
    v9 = "Not-null check failed: ComparisonResult";
    goto LABEL_4;
  }
  *a6 = 0;
  if ( !a1 )
  {
    v28 = 2252;
    v26 = "onecore\\base\\lstring\\lblob.cpp";
    v27 = "RtlCompareEncodedLBlobs";
    v9 = "Not-null check failed: String1";
LABEL_4:
    v29 = v9;
    RtlReportErrorOrigination(&v26, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
    return 3221225485LL;
  }
  if ( !a2 )
  {
    v28 = 2253;
    v26 = "onecore\\base\\lstring\\lblob.cpp";
    v27 = "RtlCompareEncodedLBlobs";
    v9 = "Not-null check failed: pfn1";
    goto LABEL_4;
  }
  if ( !a3 )
  {
    v28 = 2254;
    v26 = "onecore\\base\\lstring\\lblob.cpp";
    v27 = "RtlCompareEncodedLBlobs";
    v9 = "Not-null check failed: String2";
    goto LABEL_4;
  }
  if ( !v7 )
  {
    v28 = 2255;
    v26 = "onecore\\base\\lstring\\lblob.cpp";
    v27 = "RtlCompareEncodedLBlobs";
    v9 = "Not-null check failed: pfn2";
    goto LABEL_4;
  }
  v11 = 0;
  v12 = a1[2];
  v13 = a3[2];
  v14 = v12 + *a1;
  v15 = v13 + *a3;
  if ( v12 == v14 )
  {
LABEL_40:
    if ( v13 != v15 )
      v11 = -1;
    *v32 = v11;
    return 0;
  }
  else if ( a5 )
  {
    while ( 1 )
    {
      if ( v13 == v15 )
        goto LABEL_19;
      v16 = v8((const char **)v33, v12, v14);
      v17 = *(_DWORD *)v16;
      v12 = *(_QWORD *)(v16 + 8);
      if ( *(_DWORD *)v16 == -1 )
        break;
      v18 = v7(&v26, v13, v15);
      v19 = *(_DWORD *)v18;
      v13 = *(_QWORD *)(v18 + 8);
      if ( *(_DWORD *)v18 == -1 )
      {
        if ( (int)v13 < 0 )
        {
          v28 = 2276;
          goto LABEL_35;
        }
LABEL_44:
        INTERNAL_ERROR_ACTION(-1073741595);
        JUMPOUT(0x180005471LL);
      }
      v20 = a5(v17);
      v21 = a5(v19);
      if ( v20 < v21 )
        goto LABEL_32;
      if ( v20 != v21 )
        goto LABEL_20;
      v8 = v30;
      v11 = 0;
      v7 = v31;
      if ( v12 == v14 )
        goto LABEL_19;
    }
    if ( (int)v12 >= 0 )
      goto LABEL_44;
    v28 = 2275;
LABEL_39:
    v26 = "onecore\\base\\lstring\\lblob.cpp";
    v27 = "RtlCompareEncodedLBlobs";
    v29 = "__rv.UcsCharacter != (0xffffffff)";
    RtlReportErrorOrigination(&v26, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v12);
    return (unsigned int)v12;
  }
  else
  {
    while ( 1 )
    {
      if ( v13 == v15 )
      {
LABEL_19:
        if ( v12 == v14 )
          goto LABEL_40;
LABEL_20:
        *v32 = 1;
        return 0;
      }
      v22 = v8(&v26, v12, v14);
      v23 = *(_DWORD *)v22;
      v12 = *(_QWORD *)(v22 + 8);
      if ( *(_DWORD *)v22 == -1 )
      {
        if ( (int)v12 >= 0 )
          goto LABEL_44;
        v28 = 2292;
        goto LABEL_39;
      }
      v24 = v7((const char **)v33, v13, v15);
      v25 = *(_DWORD *)v24;
      v13 = *(_QWORD *)(v24 + 8);
      if ( *(_DWORD *)v24 == -1 )
        break;
      if ( v23 < v25 )
      {
LABEL_32:
        *v32 = -1;
        return 0;
      }
      if ( v23 != v25 )
        goto LABEL_20;
      v8 = v30;
      v11 = 0;
      if ( v12 == v14 )
        goto LABEL_19;
    }
    if ( (int)v13 >= 0 )
      goto LABEL_44;
    v28 = 2293;
LABEL_35:
    v26 = "onecore\\base\\lstring\\lblob.cpp";
    v27 = "RtlCompareEncodedLBlobs";
    v29 = "__rv.UcsCharacter != (0xffffffff)";
    RtlReportErrorOrigination(&v26, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v13);
    return (unsigned int)v13;
  }
}

```

## disassembly

```asm
0x1800050d0  push    rbp
0x1800050d2  push    r12
0x1800050d4  push    r13
0x1800050d6  lea     rbp, [rsp-37h]
0x1800050db  sub     rsp, 0A0h
0x1800050e2  mov     r13, [rbp+47h+arg_20]
0x1800050e6  mov     rax, rcx
0x1800050e9  mov     rcx, [rbp+47h+arg_28]
0x1800050ed  mov     r12, r9
0x1800050f0  mov     [rbp+47h+var_68], r9
0x1800050f4  mov     r9, rdx
0x1800050f7  mov     [rbp+47h+var_70], rdx
0x1800050fb  mov     [rbp+47h+var_60], rcx
0x1800050ff  test    rcx, rcx
0x180005102  jz      loc_18000543D
0x180005108  mov     dword ptr [rcx], 0
0x18000510e  test    rax, rax
0x180005111  jnz     short loc_180005165
0x180005113  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x18000511a  mov     [rbp+47h+var_80], 8CCh
0x180005122  mov     [rbp+47h+var_90], rax
0x180005126  lea     rax, aRtlcompareenco_0; "RtlCompareEncodedLBlobs"
0x18000512d  mov     [rbp+47h+var_88], rax
0x180005131  lea     rax, aNotNullCheckFa_10; "Not-null check failed: String1"
0x180005138  mov     r8d, 0C000000Dh
0x18000513e  mov     [rbp+47h+var_78], rax
0x180005142  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180005149  lea     rcx, [rbp+47h+var_90]
0x18000514d  call    RtlReportErrorOrigination
0x180005152  mov     eax, 0C000000Dh
0x180005157  add     rsp, 0A0h
0x18000515e  pop     r13
0x180005160  pop     r12
0x180005162  pop     rbp
0x180005163  retn
0x180005165  test    rdx, rdx
0x180005168  jnz     short loc_180005191
0x18000516a  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180005171  mov     [rbp+47h+var_80], 8CDh
0x180005179  mov     [rbp+47h+var_90], rax
0x18000517d  lea     rax, aRtlcompareenco_0; "RtlCompareEncodedLBlobs"
0x180005184  mov     [rbp+47h+var_88], rax
0x180005188  lea     rax, aNotNullCheckFa_2; "Not-null check failed: pfn1"
0x18000518f  jmp     short loc_180005138
0x180005191  test    r8, r8
0x180005194  jnz     short loc_1800051C0
0x180005196  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x18000519d  mov     [rbp+47h+var_80], 8CEh
0x1800051a5  mov     [rbp+47h+var_90], rax
0x1800051a9  lea     rax, aRtlcompareenco_0; "RtlCompareEncodedLBlobs"
0x1800051b0  mov     [rbp+47h+var_88], rax
0x1800051b4  lea     rax, aNotNullCheckFa_97; "Not-null check failed: String2"
0x1800051bb  jmp     loc_180005138
0x1800051c0  test    r12, r12
0x1800051c3  jnz     short loc_1800051EF
0x1800051c5  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x1800051cc  mov     [rbp+47h+var_80], 8CFh
0x1800051d4  mov     [rbp+47h+var_90], rax
0x1800051d8  lea     rax, aRtlcompareenco_0; "RtlCompareEncodedLBlobs"
0x1800051df  mov     [rbp+47h+var_88], rax
0x1800051e3  lea     rax, aNotNullCheckFa_90; "Not-null check failed: pfn2"
0x1800051ea  jmp     loc_180005138
0x1800051ef  mov     [rsp+0B0h+var_18], rbx
0x1800051f7  xor     ecx, ecx
0x1800051f9  mov     rbx, [rax+10h]
0x1800051fd  mov     [rsp+0B0h+var_20], rsi
0x180005205  mov     [rsp+0B0h+var_28], rdi
0x18000520d  mov     rdi, [r8+10h]
0x180005211  mov     [rsp+0B0h+var_30], r14
0x180005219  mov     r14, [rax]
0x18000521c  mov     [rsp+0B0h+var_38], r15
0x180005221  add     r14, rbx
0x180005224  mov     r15, [r8]
0x180005227  add     r15, rdi
0x18000522a  cmp     rbx, r14
0x18000522d  jz      loc_180005423
0x180005233  test    r13, r13
0x180005236  jz      loc_1800052F6
0x18000523c  nop     dword ptr [rax+00h]
0x180005240  cmp     rdi, r15
0x180005243  jz      short loc_1800052B1
0x180005245  mov     r8, r14
0x180005248  lea     rcx, [rbp+47h+var_58]
0x18000524c  mov     rdx, rbx
0x18000524f  mov     rax, r9
0x180005252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005257  mov     esi, [rax]
0x180005259  mov     rbx, [rax+8]
0x18000525d  cmp     esi, 0FFFFFFFFh
0x180005260  jz      short loc_1800052E1
0x180005262  mov     r8, r15
0x180005265  lea     rcx, [rbp+47h+var_90]
0x180005269  mov     rdx, rdi
0x18000526c  mov     rax, r12
0x18000526f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005274  mov     r12d, [rax]
0x180005277  mov     rdi, [rax+8]
0x18000527b  cmp     r12d, 0FFFFFFFFh
0x18000527f  jz      short loc_1800052CC
0x180005281  mov     ecx, esi
0x180005283  mov     rax, r13
0x180005286  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000528b  mov     esi, eax
0x18000528d  mov     ecx, r12d
0x180005290  mov     rax, r13
0x180005293  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005298  cmp     esi, eax
0x18000529a  jb      loc_180005353
0x1800052a0  jnz     short loc_1800052BA
0x1800052a2  mov     r9, [rbp+47h+var_70]
0x1800052a6  xor     ecx, ecx
0x1800052a8  mov     r12, [rbp+47h+var_68]
0x1800052ac  cmp     rbx, r14
0x1800052af  jnz     short loc_180005240
0x1800052b1  cmp     rbx, r14
0x1800052b4  jz      loc_180005423
0x1800052ba  mov     rcx, [rbp+47h+var_60]
0x1800052be  mov     eax, 1
0x1800052c3  mov     [rcx], eax
0x1800052c5  xor     eax, eax
0x1800052c7  jmp     loc_1800053A8
0x1800052cc  test    edi, edi
0x1800052ce  jns     loc_180005467
0x1800052d4  mov     [rbp+47h+var_80], 8E4h
0x1800052dc  jmp     loc_180005372
0x1800052e1  test    ebx, ebx
0x1800052e3  jns     loc_180005467
0x1800052e9  mov     [rbp+47h+var_80], 8E3h
0x1800052f1  jmp     loc_1800053EB
0x1800052f6  cmp     rdi, r15
0x1800052f9  jz      short loc_1800052B1
0x1800052fb  mov     r8, r14
0x1800052fe  lea     rcx, [rbp+47h+var_90]
0x180005302  mov     rdx, rbx
0x180005305  mov     rax, r9
0x180005308  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000530d  mov     esi, [rax]
0x18000530f  mov     rbx, [rax+8]
0x180005313  cmp     esi, 0FFFFFFFFh
0x180005316  jz      loc_1800053DB
0x18000531c  mov     r8, r15
0x18000531f  lea     rcx, [rbp+47h+var_58]
0x180005323  mov     rdx, rdi
0x180005326  mov     rax, r12
0x180005329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000532e  mov     ecx, [rax]
0x180005330  mov     rdi, [rax+8]
0x180005334  cmp     ecx, 0FFFFFFFFh
0x180005337  jz      short loc_180005362
0x180005339  cmp     esi, ecx
0x18000533b  jb      short loc_180005353
0x18000533d  jnz     loc_1800052BA
0x180005343  mov     r9, [rbp+47h+var_70]
0x180005347  xor     ecx, ecx
0x180005349  cmp     rbx, r14
0x18000534c  jnz     short loc_1800052F6
0x18000534e  jmp     loc_1800052B1
0x180005353  mov     rcx, [rbp+47h+var_60]
0x180005357  mov     eax, 0FFFFFFFFh
0x18000535c  mov     [rcx], eax
0x18000535e  xor     eax, eax
0x180005360  jmp     short loc_1800053A8
0x180005362  test    edi, edi
0x180005364  jns     loc_180005467
0x18000536a  mov     [rbp+47h+var_80], 8F5h
0x180005372  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180005379  mov     r8d, edi
0x18000537c  mov     [rbp+47h+var_90], rax
0x180005380  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180005387  lea     rax, aRtlcompareenco_0; "RtlCompareEncodedLBlobs"
0x18000538e  mov     [rbp+47h+var_88], rax
0x180005392  lea     rcx, [rbp+47h+var_90]
0x180005396  lea     rax, aRvUcscharacter_0; "__rv.UcsCharacter != (0xffffffff)"
0x18000539d  mov     [rbp+47h+var_78], rax
0x1800053a1  call    RtlReportErrorOrigination
0x1800053a6  mov     eax, edi
0x1800053a8  mov     r14, [rsp+0B0h+var_30]
0x1800053b0  mov     rdi, [rsp+0B0h+var_28]
0x1800053b8  mov     rsi, [rsp+0B0h+var_20]
0x1800053c0  mov     rbx, [rsp+0B0h+var_18]
0x1800053c8  mov     r15, [rsp+0B0h+var_38]
0x1800053cd  add     rsp, 0A0h
0x1800053d4  pop     r13
0x1800053d6  pop     r12
0x1800053d8  pop     rbp
0x1800053d9  retn
0x1800053db  test    ebx, ebx
0x1800053dd  jns     loc_180005467
0x1800053e3  mov     [rbp+47h+var_80], 8F4h
0x1800053eb  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x1800053f2  mov     r8d, ebx
0x1800053f5  mov     [rbp+47h+var_90], rax
0x1800053f9  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x180005400  lea     rax, aRtlcompareenco_0; "RtlCompareEncodedLBlobs"
0x180005407  mov     [rbp+47h+var_88], rax
0x18000540b  lea     rcx, [rbp+47h+var_90]
0x18000540f  lea     rax, aRvUcscharacter_0; "__rv.UcsCharacter != (0xffffffff)"
0x180005416  mov     [rbp+47h+var_78], rax
0x18000541a  call    RtlReportErrorOrigination
0x18000541f  mov     eax, ebx
0x180005421  jmp     short loc_1800053A8
0x180005423  cmp     rdi, r15
0x180005426  mov     eax, 0FFFFFFFFh
0x18000542b  cmovnz  ecx, eax
0x18000542e  mov     eax, ecx
0x180005430  mov     rcx, [rbp+47h+var_60]
0x180005434  mov     [rcx], eax
0x180005436  xor     eax, eax
0x180005438  jmp     loc_1800053A8
0x18000543d  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x180005444  mov     [rbp+47h+var_80], 8CBh
0x18000544c  mov     [rbp+47h+var_90], rax
0x180005450  lea     rax, aRtlcompareenco_0; "RtlCompareEncodedLBlobs"
0x180005457  mov     [rbp+47h+var_88], rax
0x18000545b  lea     rax, aNotNullCheckFa_81; "Not-null check failed: ComparisonResult"
0x180005462  jmp     loc_180005138
0x180005467  mov     ecx, 0C00000E5h; int
0x18000546c  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
