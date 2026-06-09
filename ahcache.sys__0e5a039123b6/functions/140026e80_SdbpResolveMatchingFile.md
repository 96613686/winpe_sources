# SdbpResolveMatchingFile

- ea: `0x140026e80`
- end: `0x140027263`
- name: `SdbpResolveMatchingFile`
- size: `995`
- prototype: ``
- caller_count: `4`
- callee_count: `13`
- tags: ``

## callers

- `0x140026974`
- `0x14002f050`
- `0x14002f430`
- `0x140049ec0`

## callees

- `0x140001480`
- `0x14000448d`
- `0x1400063e8`
- `0x140007b40`
- `0x140026e80`
- `0x1400327e0`
- `0x140032e04`
- `0x14003e364`
- `0x1400431a0`
- `0x140043274`
- `0x140045d44`
- `0x140046840`
- `0x14005498c`

## string_xrefs

- `0x14002721d`: `Invalid path size`
- `0x140027173`: `AslPathClean failed [%x]`

## pseudocode

```c
__int64 __fastcall SdbpResolveMatchingFile(__int64 a1, __int64 a2, void *a3, unsigned int a4, __int64 a5, wchar_t **a6)
{
  __int64 v7; // r15
  unsigned int v9; // r13d
  __int64 v10; // rcx
  _WORD *v11; // r12
  _WORD *v12; // rdi
  __int64 v13; // r14
  int ProcessWowInfo; // eax
  __int16 v15; // ax
  int v16; // eax
  ULONGLONG v17; // rdx
  ULONGLONG v18; // rax
  __int64 v19; // rcx
  unsigned __int64 v20; // rcx
  __int64 v21; // r8
  ULONGLONG v22; // rsi
  wchar_t *v23; // rax
  wchar_t *v24; // rbx
  int v25; // eax
  const char *v26; // r9
  __int64 v27; // r8
  __int16 v28; // ax
  unsigned __int64 v29; // rsi
  int v30; // eax
  __int64 v31; // rcx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v35; // [rsp+20h] [rbp-50h]
  int v36; // [rsp+28h] [rbp-48h]
  __int64 v37; // [rsp+28h] [rbp-48h]
  int v38; // [rsp+30h] [rbp-40h]
  __int16 v39; // [rsp+40h] [rbp-30h] BYREF
  ULONGLONG pullResult; // [rsp+48h] [rbp-28h] BYREF
  wchar_t *v41; // [rsp+50h] [rbp-20h] BYREF
  void *Src[2]; // [rsp+58h] [rbp-18h]
  __int16 v45; // [rsp+C8h] [rbp+58h] BYREF

  v7 = a4;
  pullResult = 0;
  v41 = 0;
  *a6 = 0;
  v45 = -1;
  v9 = 0;
  v39 = -1;
  *(_OWORD *)Src = 0;
  if ( a4 )
  {
    SdbpUmaInit_PCWSTR(a3);
    v12 = Src[0];
    v11 = Src[1];
    if ( !Src[0] && Src[1] )
    {
      AslLogCallPrintf((unsigned int)(LODWORD(Src[0]) + 1), "SdbpResolveMatchingFile", 807, "Out of memory");
      return v9;
    }
    v13 = a5;
    if ( *(_WORD *)Src[0] == 37 )
    {
      ProcessWowInfo = AslEnvGetProcessWowInfo(&v39, &v45);
      if ( ProcessWowInfo < 0 )
      {
        AslLogCallPrintf(1, "SdbpResolveMatchingFile", 830, "AslEnvGetProcessWowInfo failed [%x]", ProcessWowInfo);
        goto LABEL_48;
      }
      v15 = AslImageFileToArchitecture(*(unsigned __int16 *)(a1 + 584));
      if ( v15 == -1 )
        v15 = v45;
      v16 = AslEnvExpandStrings2(*(_QWORD *)(a2 + 56), v12, 0, 0, &pullResult, v39, v15);
      v17 = 0x80000000LL;
      if ( (int)(v16 + 0x80000000) >= 0 && v16 != -1073741789 )
      {
        LODWORD(v35) = v16;
        AslLogCallPrintf(1, "SdbpResolveMatchingFile", 847, "AslEnvExpandStrings2 failed [%x]", v35);
        goto LABEL_48;
      }
      v18 = 2 * pullResult;
    }
    else
    {
      v20 = *(unsigned int *)(a5 + 8);
      v17 = v20 + v7;
      if ( v20 + v7 < v20 )
      {
        v21 = 860;
        goto LABEL_47;
      }
      v18 = v17 + 1;
      if ( v17 + 1 < v17 )
      {
        v21 = 865;
        goto LABEL_47;
      }
    }
    if ( v18 + 20 >= v18 )
    {
      pullResult = v18 + 20;
      if ( RtlULongLongMult(v18 + 20, v17, &pullResult) < 0 )
      {
        AslLogCallPrintf(1, "SdbpResolveMatchingFile", 876, "Invalid buffer size");
        goto LABEL_48;
      }
      v22 = pullResult;
      if ( pullResult < 0x208 )
        v22 = 520;
      v23 = (wchar_t *)AslAlloc(v19, v22, 1);
      v24 = v23;
      if ( !v23 )
      {
        AslLogCallPrintf(1, "SdbpResolveMatchingFile", 884, "Out of memory");
        goto LABEL_48;
      }
      if ( *v12 == 37 )
      {
        v25 = AslEnvGetProcessWowInfo(&v39, &v45);
        if ( v25 < 0 )
        {
          v26 = "AslEnvGetProcessWowInfo failed [%x]";
          v27 = 896;
LABEL_37:
          LODWORD(v35) = v25;
          AslLogCallPrintf(1, "SdbpResolveMatchingFile", v27, v26, v35);
          goto LABEL_38;
        }
        v28 = AslImageFileToArchitecture(*(unsigned __int16 *)(a1 + 584));
        if ( v28 == -1 )
          v28 = v45;
        LOWORD(v38) = v28;
        LOWORD(v36) = v39;
        v29 = v22 >> 1;
        v30 = AslEnvExpandStrings2(*(_QWORD *)(a2 + 56), v12, v24, v29, &pullResult, v36, v38);
        if ( v30 < 0 )
        {
          LODWORD(v37) = v30;
          AslLogCallPrintf(
            1,
            "SdbpResolveMatchingFile",
            913,
            "AslEnvExpandStrings2 failed to expand strings for %ws [%x]",
            v12,
            v37);
LABEL_38:
          AslFree(v31, v24);
          goto LABEL_48;
        }
      }
      else
      {
        memmove(v23, *(const void **)v13, 2LL * *(unsigned int *)(v13 + 8));
        memmove(&v24[*(unsigned int *)(v13 + 8)], v12, 2LL * (unsigned int)(v7 + 1));
        v29 = v22 >> 1;
      }
      v25 = AslPathClean(v24, v24, v29);
      if ( v25 >= 0 )
      {
        if ( (int)AslPathToNetworkPathNt(&v41, (__int64)v24) < 0 )
        {
          if ( wcsnicmp_0(v24, L"\\??\\", 4u) )
          {
            v33 = -1;
            do
              ++v33;
            while ( v24[v33] );
            memmove(v24 + 4, v24, 2 * v33 + 2);
            *(_QWORD *)v24 = 0x5C003F003F005CLL;
          }
        }
        else
        {
          AslFree(v32, v24);
          v24 = v41;
        }
        v9 = 1;
        *a6 = v24;
        goto LABEL_48;
      }
      v26 = "AslPathClean failed [%x]";
      v27 = 938;
      goto LABEL_37;
    }
    v21 = 871;
LABEL_47:
    AslLogCallPrintf(1, "SdbpResolveMatchingFile", v21, "Invalid path size");
    goto LABEL_48;
  }
  AslLogCallPrintf(1, "SdbpResolveMatchingFile", 801, "Invalid match file length");
  v11 = Src[1];
  v12 = Src[0];
LABEL_48:
  if ( v12 && v12 != v11 )
    AslFree(v10, v12);
  return v9;
}

```

## disassembly

```asm
0x140026e80  mov     [rsp-38h+arg_10], rbx
0x140026e85  mov     [rsp-38h+arg_8], rdx
0x140026e8a  mov     [rsp-38h+arg_0], rcx
0x140026e8f  push    rbp
0x140026e90  push    rsi
0x140026e91  push    rdi
0x140026e92  push    r12
0x140026e94  push    r13
0x140026e96  push    r14
0x140026e98  push    r15
0x140026e9a  mov     rbp, rsp
0x140026e9d  sub     rsp, 70h
0x140026ea1  mov     rax, [rbp+arg_28]
0x140026ea5  mov     rsi, rcx
0x140026ea8  xor     ecx, ecx
0x140026eaa  mov     r15d, r9d
0x140026ead  mov     [rbp+pullResult], rcx
0x140026eb1  xorps   xmm0, xmm0
0x140026eb4  mov     [rbp+var_20], rcx
0x140026eb8  mov     rbx, rdx
0x140026ebb  mov     [rax], rcx
0x140026ebe  mov     eax, 0FFFFh
0x140026ec3  mov     [rbp+arg_18], ax
0x140026ec7  mov     r13d, ecx
0x140026eca  mov     [rbp+var_30], ax
0x140026ece  movups  xmmword ptr [rbp+Src], xmm0
0x140026ed2  test    r9d, r9d
0x140026ed5  jnz     short loc_140026F02
0x140026ed7  lea     r9, aInvalidMatchFi; "Invalid match file length"
0x140026ede  mov     r8d, 321h
0x140026ee4  lea     rdx, aSdbpresolvemat; "SdbpResolveMatchingFile"
0x140026eeb  mov     ecx, 1
0x140026ef0  call    AslLogCallPrintf
0x140026ef5  mov     r12, [rbp+Src+8]
0x140026ef9  mov     rdi, [rbp+Src]
0x140026efd  jmp     loc_140027235
0x140026f02  lea     rdx, [rbp+Src]
0x140026f06  mov     rcx, r8; Src
0x140026f09  call    SdbpUmaInit_PCWSTR
0x140026f0e  mov     rdi, [rbp+Src]
0x140026f12  mov     r12, [rbp+Src+8]
0x140026f16  test    rdi, rdi
0x140026f19  jnz     short loc_140026F41
0x140026f1b  test    r12, r12
0x140026f1e  jz      short loc_140026F41
0x140026f20  lea     r9, aOutOfMemory; "Out of memory"
0x140026f27  mov     r8d, 327h
0x140026f2d  lea     rdx, aSdbpresolvemat; "SdbpResolveMatchingFile"
0x140026f34  lea     ecx, [rdi+1]
0x140026f37  call    AslLogCallPrintf
0x140026f3c  jmp     loc_140027247
0x140026f41  cmp     word ptr [rdi], 25h ; '%'
0x140026f45  mov     r14, [rbp+arg_20]
0x140026f49  jnz     loc_140027028
0x140026f4f  lea     rdx, [rbp+arg_18]
0x140026f53  lea     rcx, [rbp+var_30]
0x140026f57  call    AslEnvGetProcessWowInfo
0x140026f5c  test    eax, eax
0x140026f5e  jns     short loc_140026F87
0x140026f60  mov     dword ptr [rsp+70h+var_50], eax
0x140026f64  lea     r9, aAslenvgetproce_1; "AslEnvGetProcessWowInfo failed [%x]"
0x140026f6b  mov     r8d, 33Eh
0x140026f71  lea     rdx, aSdbpresolvemat; "SdbpResolveMatchingFile"
0x140026f78  mov     ecx, 1
0x140026f7d  call    AslLogCallPrintf
0x140026f82  jmp     loc_140027235
0x140026f87  movzx   ecx, word ptr [rsi+248h]
0x140026f8e  call    AslImageFileToArchitecture
0x140026f93  mov     ecx, 0FFFFh
0x140026f98  mov     rdx, rdi
0x140026f9b  cmp     ax, cx
0x140026f9e  mov     rcx, [rbx+38h]
0x140026fa2  cmovz   ax, [rbp+arg_18]
0x140026fa7  xor     r9d, r9d
0x140026faa  mov     word ptr [rsp+70h+var_40], ax
0x140026faf  xor     r8d, r8d
0x140026fb2  movzx   eax, [rbp+var_30]
0x140026fb6  mov     word ptr [rsp+70h+var_48], ax
0x140026fbb  lea     rax, [rbp+pullResult]
0x140026fbf  mov     [rsp+70h+var_50], rax
0x140026fc4  call    AslEnvExpandStrings2
0x140026fc9  mov     edx, 80000000h; ullMultiplier
0x140026fce  mov     ecx, eax
0x140026fd0  add     eax, edx
0x140026fd2  test    edx, eax
0x140026fd4  jnz     short loc_140026FF1
0x140026fd6  cmp     ecx, 0C0000023h
0x140026fdc  jz      short loc_140026FF1
0x140026fde  mov     dword ptr [rsp+70h+var_50], ecx
0x140026fe2  lea     r9, aAslenvexpandst_0; "AslEnvExpandStrings2 failed [%x]"
0x140026fe9  mov     r8d, 34Fh
0x140026fef  jmp     short loc_140026F71
0x140026ff1  mov     rax, [rbp+pullResult]
0x140026ff5  add     rax, rax
0x140026ff8  lea     rcx, [rax+14h]; ullMultiplicand
0x140026ffc  cmp     rcx, rax
0x140026fff  jb      loc_140027217
0x140027005  lea     r8, [rbp+pullResult]; pullResult
0x140027009  mov     [rbp+pullResult], rcx
0x14002700d  call    RtlULongLongMult
0x140027012  test    eax, eax
0x140027014  jns     short loc_140027054
0x140027016  lea     r9, aInvalidBufferS; "Invalid buffer size"
0x14002701d  mov     r8d, 36Ch
0x140027023  jmp     loc_140027224
0x140027028  mov     ecx, [r14+8]
0x14002702c  lea     rdx, [rcx+r15]
0x140027030  cmp     rdx, rcx
0x140027033  jnb     short loc_140027040
0x140027035  mov     r8d, 35Ch
0x14002703b  jmp     loc_14002721D
0x140027040  lea     rax, [rdx+1]
0x140027044  cmp     rax, rdx
0x140027047  jnb     short loc_140026FF8
0x140027049  mov     r8d, 361h
0x14002704f  jmp     loc_14002721D
0x140027054  mov     rsi, [rbp+pullResult]
0x140027058  mov     eax, 208h
0x14002705d  cmp     rsi, rax
0x140027060  mov     r8d, 1
0x140027066  cmovb   rsi, rax
0x14002706a  mov     rdx, rsi
0x14002706d  call    AslAlloc
0x140027072  mov     rbx, rax
0x140027075  test    rax, rax
0x140027078  jnz     short loc_14002708C
0x14002707a  lea     r9, aOutOfMemory; "Out of memory"
0x140027081  mov     r8d, 374h
0x140027087  jmp     loc_140027224
0x14002708c  cmp     word ptr [rdi], 25h ; '%'
0x140027090  jnz     loc_140027133
0x140027096  lea     rdx, [rbp+arg_18]
0x14002709a  lea     rcx, [rbp+var_30]
0x14002709e  call    AslEnvGetProcessWowInfo
0x1400270a3  test    eax, eax
0x1400270a5  jns     short loc_1400270B9
0x1400270a7  lea     r9, aAslenvgetproce_1; "AslEnvGetProcessWowInfo failed [%x]"
0x1400270ae  mov     r8d, 380h
0x1400270b4  jmp     loc_140027180
0x1400270b9  mov     rcx, [rbp+arg_0]
0x1400270bd  movzx   ecx, word ptr [rcx+248h]
0x1400270c4  call    AslImageFileToArchitecture
0x1400270c9  mov     ecx, 0FFFFh
0x1400270ce  mov     r8, rbx
0x1400270d1  cmp     ax, cx
0x1400270d4  mov     rdx, rdi
0x1400270d7  mov     rcx, [rbp+arg_8]
0x1400270db  cmovz   ax, [rbp+arg_18]
0x1400270e0  mov     word ptr [rsp+70h+var_40], ax
0x1400270e5  movzx   eax, [rbp+var_30]
0x1400270e9  mov     rcx, [rcx+38h]
0x1400270ed  mov     word ptr [rsp+70h+var_48], ax
0x1400270f2  lea     rax, [rbp+pullResult]
0x1400270f6  shr     rsi, 1
0x1400270f9  mov     r9, rsi
0x1400270fc  mov     [rsp+70h+var_50], rax
0x140027101  call    AslEnvExpandStrings2
0x140027106  test    eax, eax
0x140027108  jns     short loc_14002715F
0x14002710a  mov     dword ptr [rsp+70h+var_48], eax
0x14002710e  lea     r9, aAslenvexpandst_1; "AslEnvExpandStrings2 failed to expand s"...
0x140027115  mov     r8d, 391h
0x14002711b  mov     [rsp+70h+var_50], rdi
0x140027120  lea     rdx, aSdbpresolvemat; "SdbpResolveMatchingFile"
0x140027127  mov     ecx, 1
0x14002712c  call    AslLogCallPrintf
0x140027131  jmp     short loc_140027195
0x140027133  mov     r8d, [r14+8]
0x140027137  mov     rcx, rbx; void *
0x14002713a  mov     rdx, [r14]; Src
0x14002713d  add     r8, r8; Size
0x140027140  call    memmove
0x140027145  mov     eax, [r14+8]
0x140027149  lea     r8d, [r15+1]
0x14002714d  add     r8, r8; Size
0x140027150  mov     rdx, rdi; Src
0x140027153  lea     rcx, [rbx+rax*2]; void *
0x140027157  call    memmove
0x14002715c  shr     rsi, 1
0x14002715f  mov     r8, rsi
0x140027162  mov     rdx, rbx; void *
0x140027165  mov     rcx, rbx; Src
0x140027168  call    AslPathClean
0x14002716d  xor     esi, esi
0x14002716f  test    eax, eax
0x140027171  jns     short loc_1400271A2
0x140027173  lea     r9, aAslpathcleanFa; "AslPathClean failed [%x]"
0x14002717a  mov     r8d, 3AAh
0x140027180  lea     rdx, aSdbpresolvemat; "SdbpResolveMatchingFile"
0x140027187  mov     dword ptr [rsp+70h+var_50], eax
0x14002718b  mov     ecx, 1
0x140027190  call    AslLogCallPrintf
0x140027195  mov     rdx, rbx
0x140027198  call    AslFree
0x14002719d  jmp     loc_140027235
0x1400271a2  mov     rdx, rbx
0x1400271a5  lea     rcx, [rbp+var_20]
0x1400271a9  call    AslPathToNetworkPathNt
0x1400271ae  test    eax, eax
0x1400271b0  js      short loc_1400271C0
0x1400271b2  mov     rdx, rbx
0x1400271b5  call    AslFree
0x1400271ba  mov     rbx, [rbp+var_20]
0x1400271be  jmp     short loc_140027208
0x1400271c0  mov     r8d, 4; MaxCount
0x1400271c6  lea     rdx, asc_14000EAD8; "\\??\\"
0x1400271cd  mov     rcx, rbx; Str1
0x1400271d0  call    _wcsnicmp_0
0x1400271d5  test    eax, eax
0x1400271d7  jz      short loc_140027208
0x1400271d9  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400271dd  inc     r8
0x1400271e0  cmp     [rbx+r8*2], si
0x1400271e5  jnz     short loc_1400271DD
0x1400271e7  lea     r8, ds:2[r8*2]; Size
0x1400271ef  mov     rdx, rbx; Src
0x1400271f2  lea     rcx, [rbx+8]; void *
0x1400271f6  call    memmove
0x1400271fb  mov     rax, 5C003F003F005Ch
0x140027205  mov     [rbx], rax
0x140027208  mov     rax, [rbp+arg_28]
0x14002720c  mov     r13d, 1
0x140027212  mov     [rax], rbx
0x140027215  jmp     short loc_140027235
0x140027217  mov     r8d, 367h
0x14002721d  lea     r9, aInvalidPathSiz; "Invalid path size"
0x140027224  lea     rdx, aSdbpresolvemat; "SdbpResolveMatchingFile"
0x14002722b  mov     ecx, 1
0x140027230  call    AslLogCallPrintf
0x140027235  test    rdi, rdi
0x140027238  jz      short loc_140027247
0x14002723a  cmp     rdi, r12
0x14002723d  jz      short loc_140027247
0x14002723f  mov     rdx, rdi
0x140027242  call    AslFree
0x140027247  mov     rbx, [rsp+70h+arg_10]
0x14002724f  mov     eax, r13d
0x140027252  add     rsp, 70h
0x140027256  pop     r15
0x140027258  pop     r14
0x14002725a  pop     r13
0x14002725c  pop     r12
0x14002725e  pop     rdi
0x14002725f  pop     rsi
0x140027260  pop     rbp
0x140027261  retn
```
