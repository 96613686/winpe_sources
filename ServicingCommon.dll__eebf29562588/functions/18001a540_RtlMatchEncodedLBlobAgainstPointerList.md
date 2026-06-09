# RtlMatchEncodedLBlobAgainstPointerList

- ea: `0x18001a540`
- end: `0x18001a895`
- name: `RtlMatchEncodedLBlobAgainstPointerList`
- size: `853`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180012aa0`
- `0x18001b7e0`
- `0x18001c690`
- `0x180066a50`
- `0x180068110`
- `0x180068530`

## callees

- `0x1800031e0`
- `0x18001a540`
- `0x18001fd10`
- `0x1800a0020`

## string_xrefs

- `0x18001a70a`: `RtlCompareEncodedLBlobs`
- `0x18001a755`: `RtlCompareEncodedLBlobs`
- `0x18001a7b7`: `RtlCompareEncodedLBlobs`
- `0x18001a7de`: `RtlCompareEncodedLBlobs`
- `0x18001a805`: `RtlCompareEncodedLBlobs`
- `0x18001a82c`: `RtlCompareEncodedLBlobs`

## pseudocode

```c
__int64 __fastcall RtlMatchEncodedLBlobAgainstPointerList(
        __int64 a1,
        _QWORD *a2,
        __int64 (__fastcall *a3)(char *, __int64, __int64),
        __int64 (__fastcall *a4)(_QWORD),
        unsigned __int64 a5,
        __int64 a6,
        __int64 (__fastcall *a7)(const char **, __int64, __int64),
        unsigned __int64 *a8)
{
  __int64 v9; // rcx
  _QWORD *v10; // r8
  __int64 (__fastcall *v11)(const char **, __int64, __int64); // r12
  unsigned __int64 v12; // rax
  _QWORD *v13; // rdx
  __int64 v14; // rdi
  __int64 v15; // rbx
  __int64 v16; // r15
  __int64 v17; // r14
  __int64 v18; // rax
  unsigned int v19; // esi
  __int64 v20; // rax
  unsigned int v21; // r12d
  int v22; // esi
  __int64 v23; // rax
  int v24; // esi
  __int64 v25; // rax
  const char *v27; // rax
  const char *v28; // [rsp+20h] [rbp-79h] BYREF
  const char *v29; // [rsp+28h] [rbp-71h]
  __int64 v30; // [rsp+30h] [rbp-69h]
  const char *v31; // [rsp+38h] [rbp-61h]
  __int64 (__fastcall *v32)(_QWORD); // [rsp+40h] [rbp-59h]
  unsigned __int64 v33; // [rsp+48h] [rbp-51h]
  __int64 v34; // [rsp+50h] [rbp-49h]
  _QWORD *v35; // [rsp+58h] [rbp-41h]
  __int64 v36; // [rsp+60h] [rbp-39h]
  unsigned __int64 *v37; // [rsp+68h] [rbp-31h]
  char v38[16]; // [rsp+70h] [rbp-29h] BYREF
  char v39[16]; // [rsp+80h] [rbp-19h] BYREF
  char v40[64]; // [rsp+90h] [rbp-9h] BYREF

  v9 = a6;
  v10 = a2;
  v11 = a7;
  v37 = a8;
  v12 = 0;
  v32 = a4;
  v35 = a2;
  v36 = a6;
  v34 = (__int64)a7;
  v33 = 0;
  if ( !a5 )
  {
LABEL_39:
    *v37 = v12;
    return 0;
  }
  while ( 1 )
  {
    if ( !v10 )
    {
      v30 = 2252;
      v28 = "onecore\\base\\lstring\\lblob.cpp";
      v29 = "RtlCompareEncodedLBlobs";
      v27 = "Not-null check failed: String1";
      goto LABEL_38;
    }
    if ( !a3 )
    {
      v30 = 2253;
      v28 = "onecore\\base\\lstring\\lblob.cpp";
      v29 = "RtlCompareEncodedLBlobs";
      v27 = "Not-null check failed: pfn1";
      goto LABEL_38;
    }
    v13 = *(_QWORD **)(v9 + 8 * v12);
    if ( !v13 )
    {
      v30 = 2254;
      v28 = "onecore\\base\\lstring\\lblob.cpp";
      v29 = "RtlCompareEncodedLBlobs";
      v27 = "Not-null check failed: String2";
      goto LABEL_38;
    }
    if ( !v11 )
    {
      v30 = 2255;
      v28 = "onecore\\base\\lstring\\lblob.cpp";
      v29 = "RtlCompareEncodedLBlobs";
      v27 = "Not-null check failed: pfn2";
LABEL_38:
      v31 = v27;
      RtlReportErrorOrigination(&v28, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, 3221225485LL);
      return 3221225485LL;
    }
    v14 = v10[2];
    v15 = v13[2];
    v16 = v14 + *v10;
    v17 = v15 + *v13;
    if ( v14 == v16 )
      goto LABEL_20;
    if ( a4 )
      break;
    do
    {
      if ( v15 == v17 )
        break;
      v23 = a3(v40, v14, v16);
      v24 = *(_DWORD *)v23;
      v14 = *(_QWORD *)(v23 + 8);
      if ( *(_DWORD *)v23 == -1 )
      {
        if ( (int)v14 >= 0 )
          goto LABEL_40;
        v30 = 2292;
        goto LABEL_29;
      }
      v25 = v11(&v28, v15, v17);
      v15 = *(_QWORD *)(v25 + 8);
      if ( *(_DWORD *)v25 == -1 )
      {
        if ( (int)v15 >= 0 )
          goto LABEL_40;
        v30 = 2293;
LABEL_26:
        v28 = "onecore\\base\\lstring\\lblob.cpp";
        v29 = "RtlCompareEncodedLBlobs";
        v31 = "__rv.UcsCharacter != (0xffffffff)";
        RtlReportErrorOrigination(&v28, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v15);
        return (unsigned int)v15;
      }
      if ( v24 != *(_DWORD *)v25 )
        goto LABEL_22;
    }
    while ( v14 != v16 );
LABEL_19:
    if ( v14 != v16 )
      goto LABEL_22;
LABEL_20:
    if ( v15 == v17 )
    {
      v12 = v33;
      goto LABEL_39;
    }
LABEL_22:
    v12 = v33 + 1;
    v33 = v12;
    if ( v12 >= a5 )
      goto LABEL_39;
    v11 = (__int64 (__fastcall *)(const char **, __int64, __int64))v34;
    a4 = v32;
    v10 = v35;
    v9 = v36;
  }
  while ( 1 )
  {
    if ( v15 == v17 )
      goto LABEL_19;
    v18 = a3(v38, v14, v16);
    v19 = *(_DWORD *)v18;
    v14 = *(_QWORD *)(v18 + 8);
    if ( *(_DWORD *)v18 == -1 )
      break;
    v20 = v11((const char **)v39, v15, v17);
    v21 = *(_DWORD *)v20;
    v15 = *(_QWORD *)(v20 + 8);
    if ( *(_DWORD *)v20 == -1 )
    {
      if ( (int)v15 < 0 )
      {
        v30 = 2276;
        goto LABEL_26;
      }
LABEL_40:
      INTERNAL_ERROR_ACTION(-1073741595);
      JUMPOUT(0x18001A894LL);
    }
    v22 = v32(v19);
    if ( v22 != (unsigned int)v32(v21) )
      goto LABEL_22;
    v11 = (__int64 (__fastcall *)(const char **, __int64, __int64))v34;
    if ( v14 == v16 )
      goto LABEL_20;
  }
  if ( (int)v14 >= 0 )
    goto LABEL_40;
  v30 = 2275;
LABEL_29:
  v28 = "onecore\\base\\lstring\\lblob.cpp";
  v29 = "RtlCompareEncodedLBlobs";
  v31 = "__rv.UcsCharacter != (0xffffffff)";
  RtlReportErrorOrigination(&v28, &GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab, (unsigned int)v14);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18001a540  mov     [rsp-8+arg_0], rbx
0x18001a545  push    rbp
0x18001a546  push    rsi
0x18001a547  push    rdi
0x18001a548  push    r12
0x18001a54a  push    r13
0x18001a54c  push    r14
0x18001a54e  push    r15
0x18001a550  lea     rbp, [rsp-7]
0x18001a555  sub     rsp, 0A0h
0x18001a55c  mov     rax, [rbp+37h+arg_38]
0x18001a560  mov     r13, r8
0x18001a563  mov     rcx, [rbp+37h+arg_28]
0x18001a567  mov     r8, rdx
0x18001a56a  mov     r12, [rbp+37h+arg_30]
0x18001a56e  mov     [rbp+37h+var_68], rax
0x18001a572  xor     eax, eax
0x18001a574  mov     [rbp+37h+var_90], r9
0x18001a578  mov     [rbp+37h+var_78], rdx
0x18001a57c  mov     [rbp+37h+var_70], rcx
0x18001a580  mov     [rbp+37h+var_80], r12
0x18001a584  mov     [rbp+37h+var_88], rax
0x18001a588  cmp     [rbp+37h+arg_20], rax
0x18001a58c  jbe     loc_18001A865
0x18001a592  test    r8, r8
0x18001a595  jz      loc_18001A819
0x18001a59b  test    r13, r13
0x18001a59e  jz      loc_18001A7F2
0x18001a5a4  mov     rdx, [rcx+rax*8]
0x18001a5a8  test    rdx, rdx
0x18001a5ab  jz      loc_18001A7CB
0x18001a5b1  test    r12, r12
0x18001a5b4  jz      loc_18001A7A4
0x18001a5ba  mov     rdi, [r8+10h]
0x18001a5be  xor     ecx, ecx
0x18001a5c0  mov     r15, [r8]
0x18001a5c3  mov     rbx, [rdx+10h]
0x18001a5c7  add     r15, rdi
0x18001a5ca  mov     r14, [rdx]
0x18001a5cd  add     r14, rbx
0x18001a5d0  cmp     rdi, r15
0x18001a5d3  jz      loc_18001A6AE
0x18001a5d9  test    r9, r9
0x18001a5dc  jz      short loc_18001A657
0x18001a5de  xchg    ax, ax
0x18001a5e0  cmp     rbx, r14
0x18001a5e3  jz      loc_18001A6A9
0x18001a5e9  mov     r8, r15
0x18001a5ec  lea     rcx, [rbp+37h+var_60]
0x18001a5f0  mov     rdx, rdi
0x18001a5f3  mov     rax, r13
0x18001a5f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5fb  mov     esi, [rax]
0x18001a5fd  mov     rdi, [rax+8]
0x18001a601  cmp     esi, 0FFFFFFFFh
0x18001a604  jz      loc_18001A730
0x18001a60a  mov     r8, r14
0x18001a60d  lea     rcx, [rbp+37h+var_50]
0x18001a611  mov     rdx, rbx
0x18001a614  mov     rax, r12
0x18001a617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a61c  mov     r12d, [rax]
0x18001a61f  mov     rbx, [rax+8]
0x18001a623  cmp     r12d, 0FFFFFFFFh
0x18001a627  jz      loc_18001A6E5
0x18001a62d  mov     rax, [rbp+37h+var_90]
0x18001a631  mov     ecx, esi
0x18001a633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a638  mov     esi, eax
0x18001a63a  mov     ecx, r12d
0x18001a63d  mov     rax, [rbp+37h+var_90]
0x18001a641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a646  cmp     esi, eax
0x18001a648  jnz     short loc_18001A6BB
0x18001a64a  mov     r12, [rbp+37h+var_80]
0x18001a64e  xor     ecx, ecx
0x18001a650  cmp     rdi, r15
0x18001a653  jnz     short loc_18001A5E0
0x18001a655  jmp     short loc_18001A6AE
0x18001a657  cmp     rbx, r14
0x18001a65a  jz      short loc_18001A6A9
0x18001a65c  mov     r8, r15
0x18001a65f  lea     rcx, [rbp+37h+var_40]
0x18001a663  mov     rdx, rdi
0x18001a666  mov     rax, r13
0x18001a669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a66e  mov     esi, [rax]
0x18001a670  mov     rdi, [rax+8]
0x18001a674  cmp     esi, 0FFFFFFFFh
0x18001a677  jz      loc_18001A792
0x18001a67d  mov     r8, r14
0x18001a680  lea     rcx, [rbp+37h+var_B0]
0x18001a684  mov     rdx, rbx
0x18001a687  mov     rax, r12
0x18001a68a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a68f  mov     ecx, [rax]
0x18001a691  mov     rbx, [rax+8]
0x18001a695  cmp     ecx, 0FFFFFFFFh
0x18001a698  jz      loc_18001A77D
0x18001a69e  cmp     esi, ecx
0x18001a6a0  jnz     short loc_18001A6BB
0x18001a6a2  xor     ecx, ecx
0x18001a6a4  cmp     rdi, r15
0x18001a6a7  jnz     short loc_18001A657
0x18001a6a9  cmp     rdi, r15
0x18001a6ac  jnz     short loc_18001A6BB
0x18001a6ae  cmp     rbx, r14
0x18001a6b1  jnz     short loc_18001A6BB
0x18001a6b3  test    ecx, ecx
0x18001a6b5  jz      loc_18001A861
0x18001a6bb  mov     rax, [rbp+37h+var_88]
0x18001a6bf  inc     rax
0x18001a6c2  mov     [rbp+37h+var_88], rax
0x18001a6c6  cmp     rax, [rbp+37h+arg_20]
0x18001a6ca  jnb     loc_18001A865
0x18001a6d0  mov     r12, [rbp+37h+var_80]
0x18001a6d4  mov     r9, [rbp+37h+var_90]
0x18001a6d8  mov     r8, [rbp+37h+var_78]
0x18001a6dc  mov     rcx, [rbp+37h+var_70]
0x18001a6e0  jmp     loc_18001A592
0x18001a6e5  test    ebx, ebx
0x18001a6e7  jns     loc_18001A88A
0x18001a6ed  mov     [rbp+37h+var_A0], 8E4h
0x18001a6f5  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x18001a6fc  mov     r8d, ebx
0x18001a6ff  mov     [rbp+37h+var_B0], rax
0x18001a703  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18001a70a  lea     rax, aRtlcompareenco_0; "RtlCompareEncodedLBlobs"
0x18001a711  mov     [rbp+37h+var_A8], rax
0x18001a715  lea     rcx, [rbp+37h+var_B0]
0x18001a719  lea     rax, aRvUcscharacter_0; "__rv.UcsCharacter != (0xffffffff)"
0x18001a720  mov     [rbp+37h+var_98], rax
0x18001a724  call    RtlReportErrorOrigination
0x18001a729  mov     eax, ebx
0x18001a72b  jmp     loc_18001A86E
0x18001a730  test    edi, edi
0x18001a732  jns     loc_18001A88A
0x18001a738  mov     [rbp+37h+var_A0], 8E3h
0x18001a740  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x18001a747  mov     r8d, edi
0x18001a74a  mov     [rbp+37h+var_B0], rax
0x18001a74e  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18001a755  lea     rax, aRtlcompareenco_0; "RtlCompareEncodedLBlobs"
0x18001a75c  mov     [rbp+37h+var_A8], rax
0x18001a760  lea     rcx, [rbp+37h+var_B0]
0x18001a764  lea     rax, aRvUcscharacter_0; "__rv.UcsCharacter != (0xffffffff)"
0x18001a76b  mov     [rbp+37h+var_98], rax
0x18001a76f  call    RtlReportErrorOrigination
0x18001a774  mov     ebx, edi
0x18001a776  mov     eax, ebx
0x18001a778  jmp     loc_18001A86E
0x18001a77d  test    ebx, ebx
0x18001a77f  jns     loc_18001A88A
0x18001a785  mov     [rbp+37h+var_A0], 8F5h
0x18001a78d  jmp     loc_18001A6F5
0x18001a792  test    edi, edi
0x18001a794  jns     loc_18001A88A
0x18001a79a  mov     [rbp+37h+var_A0], 8F4h
0x18001a7a2  jmp     short loc_18001A740
0x18001a7a4  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x18001a7ab  mov     [rbp+37h+var_A0], 8CFh
0x18001a7b3  mov     [rbp+37h+var_B0], rax
0x18001a7b7  lea     rax, aRtlcompareenco_0; "RtlCompareEncodedLBlobs"
0x18001a7be  mov     [rbp+37h+var_A8], rax
0x18001a7c2  lea     rax, aNotNullCheckFa_90; "Not-null check failed: pfn2"
0x18001a7c9  jmp     short loc_18001A83E
0x18001a7cb  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x18001a7d2  mov     [rbp+37h+var_A0], 8CEh
0x18001a7da  mov     [rbp+37h+var_B0], rax
0x18001a7de  lea     rax, aRtlcompareenco_0; "RtlCompareEncodedLBlobs"
0x18001a7e5  mov     [rbp+37h+var_A8], rax
0x18001a7e9  lea     rax, aNotNullCheckFa_97; "Not-null check failed: String2"
0x18001a7f0  jmp     short loc_18001A83E
0x18001a7f2  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x18001a7f9  mov     [rbp+37h+var_A0], 8CDh
0x18001a801  mov     [rbp+37h+var_B0], rax
0x18001a805  lea     rax, aRtlcompareenco_0; "RtlCompareEncodedLBlobs"
0x18001a80c  mov     [rbp+37h+var_A8], rax
0x18001a810  lea     rax, aNotNullCheckFa_2; "Not-null check failed: pfn1"
0x18001a817  jmp     short loc_18001A83E
0x18001a819  lea     rax, aOnecoreBaseLst_2; "onecore\\base\\lstring\\lblob.cpp"
0x18001a820  mov     [rbp+37h+var_A0], 8CCh
0x18001a828  mov     [rbp+37h+var_B0], rax
0x18001a82c  lea     rax, aRtlcompareenco_0; "RtlCompareEncodedLBlobs"
0x18001a833  mov     [rbp+37h+var_A8], rax
0x18001a837  lea     rax, aNotNullCheckFa_10; "Not-null check failed: String1"
0x18001a83e  mov     r8d, 0C000000Dh
0x18001a844  mov     [rbp+37h+var_98], rax
0x18001a848  lea     rdx, _GUID_44edceb3_7a6e_47e9_b787_5aa9dadfa4ab
0x18001a84f  lea     rcx, [rbp+37h+var_B0]
0x18001a853  call    RtlReportErrorOrigination
0x18001a858  mov     ebx, 0C000000Dh
0x18001a85d  mov     eax, ebx
0x18001a85f  jmp     short loc_18001A86E
0x18001a861  mov     rax, [rbp+37h+var_88]
0x18001a865  mov     rcx, [rbp+37h+var_68]
0x18001a869  mov     [rcx], rax
0x18001a86c  xor     eax, eax
0x18001a86e  mov     rbx, [rsp+0D0h+arg_0]
0x18001a876  add     rsp, 0A0h
0x18001a87d  pop     r15
0x18001a87f  pop     r14
0x18001a881  pop     r13
0x18001a883  pop     r12
0x18001a885  pop     rdi
0x18001a886  pop     rsi
0x18001a887  pop     rbp
0x18001a888  retn
0x18001a88a  mov     ecx, 0C00000E5h; int
0x18001a88f  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
