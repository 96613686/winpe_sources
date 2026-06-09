# CPrintAbstractHelper::WhyConstrainedFromParser(CPrintCoreConfig *,char const *,char const *,_PRINT_FEATURE_OPTION const * *,ulong *)

- ea: `0x180033d58`
- end: `0x180033ff0`
- name: `?WhyConstrainedFromParser@CPrintAbstractHelper@@IEAAJPEAVCPrintCoreConfig@@PEBD1PEAPEBU_PRINT_FEATURE_OPTION@@PEAK@Z`
- size: `664`
- prototype: `__int64 __fastcall(CPrintAbstractHelper *this, struct CPrintCoreConfig *, const char *, const char *, const struct _PRINT_FEATURE_OPTION **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180034280`

## callees

- `0x180031044`
- `0x1800310e4`
- `0x1800325f8`
- `0x180033d58`
- `0x180034384`
- `0x1800343c8`
- `0x18005da98`
- `0x18005f010`

## pseudocode

```c
__int64 __fastcall CPrintAbstractHelper::WhyConstrainedFromParser(
        CPrintAbstractHelper *this,
        struct CPrintCoreConfig *a2,
        const char *a3,
        const char *a4,
        const struct _PRINT_FEATURE_OPTION **a5,
        unsigned int *a6)
{
  struct _UIINFO *UIInfo; // rax
  struct _UIINFO *v10; // rdi
  __int64 v11; // rcx
  unsigned int *KeywordMatchFeature; // r14
  unsigned int *KeywordMatchOption; // r12
  __int64 v14; // rcx
  _DWORD *v15; // r15
  unsigned int v16; // ebx
  char *v17; // rax
  const struct _PRINT_FEATURE_OPTION *v18; // rdx
  unsigned int *v19; // r8
  unsigned int v20; // r11d
  unsigned int v21; // r10d
  __int64 v22; // rax
  _DWORD *v23; // rax
  const CHAR *v24; // rcx
  const CHAR *v25; // rcx
  const CHAR *v26; // rcx
  const CHAR *v27; // rax
  unsigned int v29; // [rsp+30h] [rbp-20h] BYREF
  unsigned int v30[6]; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v31; // [rsp+80h] [rbp+30h] BYREF
  int v32; // [rsp+84h] [rbp+34h]

  v32 = HIDWORD(this);
  v31 = 0;
  v29 = 0;
  UIInfo = CPrintCoreConfig::GetUIInfo(a2);
  v10 = UIInfo;
  if ( !UIInfo )
    return (unsigned int)-2147418113;
  KeywordMatchFeature = PInternalGetKeywordMatchFeature((__int64)UIInfo, a3, 0, &v31);
  if ( !KeywordMatchFeature )
    return (unsigned int)-2147467259;
  KeywordMatchOption = PInternalGetKeywordMatchOption(v11, KeywordMatchFeature, a4, 0, &v29);
  if ( !KeywordMatchOption )
    return (unsigned int)-2147467259;
  v14 = *(_QWORD *)a2;
  *(_OWORD *)v30 = 0;
  if ( !v14 )
    return (unsigned int)-2147418113;
  v15 = (_DWORD *)(*(__int64 (**)(void))(*((_QWORD *)a2 + 1) + 32LL))();
  if ( !v15 )
    return (unsigned int)-2147418113;
  if ( BIsParserFeatureReadable(a2, (struct _FEATURE *)KeywordMatchFeature) )
  {
    v16 = 0;
    if ( *((_QWORD *)a2 + 2) )
      v17 = (char *)a2 + 28;
    else
      v17 = (char *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(*((_QWORD *)a2 + 1) + 8LL))(*(_QWORD *)a2, 0);
    if ( !(unsigned int)EnumNewPickOneUIConflict(v15, (__int64)v17, v31, v29, v30) )
    {
      *a5 = 0;
      *a6 = 0;
      return v16;
    }
    v18 = (const struct _PRINT_FEATURE_OPTION *)CPrintCoreConfig::PrivateAlloc(a2, 0x20u);
    if ( !v18 )
      return (unsigned int)-2147024882;
    if ( *(_QWORD *)v30 == __PAIR64__(v29, v31) )
    {
      if ( v30[2] >= *((_DWORD *)v10 + 6) + *((_DWORD *)v10 + 7) )
        return (unsigned int)-2147418113;
      v19 = (unsigned int *)(*((_QWORD *)v10 + 41) + *((unsigned int *)v10 + 8) + 84LL * v30[2]);
      if ( !v19 )
        return (unsigned int)-2147418113;
      v20 = 0;
      v21 = 1;
      if ( v30[3] < v19[13] )
      {
        v22 = v19[14] + v19[12] * v30[3];
LABEL_23:
        v23 = (_DWORD *)(*((_QWORD *)v10 + 41) + v22);
LABEL_25:
        if ( v23 )
        {
          v24 = *KeywordMatchFeature ? (const CHAR *)(*((_QWORD *)v10 + 40) + *KeywordMatchFeature) : 0LL;
          v18[v20].pszFeature = v24;
          v25 = *KeywordMatchOption ? (const CHAR *)(*((_QWORD *)v10 + 40) + *KeywordMatchOption) : 0LL;
          v18[v20].pszOption = v25;
          v26 = *v19 ? (const CHAR *)(*((_QWORD *)v10 + 40) + *v19) : 0LL;
          v18[v21].pszFeature = v26;
          v27 = *v23 ? (const CHAR *)(*((_QWORD *)v10 + 40) + (unsigned int)*v23) : 0LL;
          v18[v21].pszOption = v27;
          if ( v18[v20].pszFeature )
          {
            if ( v18[v20].pszOption && v26 && v27 )
            {
              *a5 = v18;
              *a6 = 2;
              return v16;
            }
          }
        }
        return (unsigned int)-2147418113;
      }
    }
    else
    {
      if ( v30[0] >= *((_DWORD *)v10 + 6) + *((_DWORD *)v10 + 7) )
        return (unsigned int)-2147418113;
      v19 = (unsigned int *)(*((_QWORD *)v10 + 41) + *((unsigned int *)v10 + 8) + 84LL * v30[0]);
      if ( !v19 )
        return (unsigned int)-2147418113;
      v21 = 0;
      v20 = 1;
      if ( v30[1] < v19[13] )
      {
        v22 = v19[14] + v19[12] * v30[1];
        goto LABEL_23;
      }
    }
    v23 = 0;
    goto LABEL_25;
  }
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x180033d58  mov     [rsp-28h+arg_8], rbx
0x180033d5d  mov     [rsp-28h+arg_10], rsi
0x180033d62  mov     [rsp-28h+arg_0], rcx
0x180033d67  push    rbp
0x180033d68  push    rdi
0x180033d69  push    r12
0x180033d6b  push    r14
0x180033d6d  push    r15
0x180033d6f  mov     rbp, rsp
0x180033d72  sub     rsp, 50h
0x180033d76  mov     rcx, rdx; this
0x180033d79  mov     dword ptr [rbp+arg_0], 0
0x180033d80  mov     r15, r9
0x180033d83  mov     [rbp+var_20], 0
0x180033d8a  mov     rbx, r8
0x180033d8d  mov     rsi, rdx
0x180033d90  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x180033d95  mov     rdi, rax
0x180033d98  test    rax, rax
0x180033d9b  jz      loc_180033FCF
0x180033da1  lea     r9, [rbp+arg_0]
0x180033da5  xor     r8d, r8d
0x180033da8  mov     rdx, rbx
0x180033dab  mov     rcx, rax
0x180033dae  call    PInternalGetKeywordMatchFeature
0x180033db3  mov     r14, rax
0x180033db6  test    rax, rax
0x180033db9  jz      short loc_180033E15
0x180033dbb  lea     rax, [rbp+var_20]
0x180033dbf  xor     r9d, r9d
0x180033dc2  mov     r8, r15
0x180033dc5  mov     [rsp+50h+var_30], rax
0x180033dca  mov     rdx, r14
0x180033dcd  call    PInternalGetKeywordMatchOption
0x180033dd2  mov     r12, rax
0x180033dd5  test    rax, rax
0x180033dd8  jz      short loc_180033E15
0x180033dda  mov     rcx, [rsi]
0x180033ddd  xorps   xmm0, xmm0
0x180033de0  movups  xmmword ptr [rbp+var_18], xmm0
0x180033de4  test    rcx, rcx
0x180033de7  jz      loc_180033FCF
0x180033ded  mov     rax, [rsi+8]
0x180033df1  mov     rax, [rax+20h]
0x180033df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033dfa  mov     r15, rax
0x180033dfd  test    rax, rax
0x180033e00  jz      loc_180033FCF
0x180033e06  mov     rdx, r14; struct _FEATURE *
0x180033e09  mov     rcx, rsi; this
0x180033e0c  call    ?BIsParserFeatureReadable@@YAHPEAVCPrintCoreConfig@@PEAU_FEATURE@@@Z; BIsParserFeatureReadable(CPrintCoreConfig *,_FEATURE *)
0x180033e11  test    eax, eax
0x180033e13  jnz     short loc_180033E1F
0x180033e15  mov     ebx, 80004005h
0x180033e1a  jmp     loc_180033FD4
0x180033e1f  xor     ebx, ebx
0x180033e21  cmp     [rsi+10h], rbx
0x180033e25  jz      short loc_180033E2D
0x180033e27  lea     rax, [rsi+1Ch]
0x180033e2b  jmp     short loc_180033E3F
0x180033e2d  mov     rax, [rsi+8]
0x180033e31  xor     edx, edx
0x180033e33  mov     rcx, [rsi]
0x180033e36  mov     rax, [rax+8]
0x180033e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033e3f  mov     r9d, [rbp+var_20]
0x180033e43  lea     rcx, [rbp+var_18]
0x180033e47  mov     r8d, dword ptr [rbp+arg_0]
0x180033e4b  mov     rdx, rax
0x180033e4e  mov     [rsp+50h+var_30], rcx
0x180033e53  mov     rcx, r15
0x180033e56  call    EnumNewPickOneUIConflict
0x180033e5b  test    eax, eax
0x180033e5d  jz      loc_180033FC0
0x180033e63  mov     edx, 20h ; ' '; unsigned __int64
0x180033e68  mov     rcx, rsi; this
0x180033e6b  call    ?PrivateAlloc@CPrintCoreConfig@@QEAAPEAX_K@Z; CPrintCoreConfig::PrivateAlloc(unsigned __int64)
0x180033e70  mov     rdx, rax
0x180033e73  test    rax, rax
0x180033e76  jnz     short loc_180033E82
0x180033e78  mov     ebx, 8007000Eh
0x180033e7d  jmp     loc_180033FD4
0x180033e82  mov     ecx, [rbp+var_18]
0x180033e85  mov     r9d, [rbp+var_18+4]
0x180033e89  cmp     ecx, dword ptr [rbp+arg_0]
0x180033e8c  jnz     short loc_180033ED8
0x180033e8e  cmp     r9d, [rbp+var_20]
0x180033e92  jnz     short loc_180033ED8
0x180033e94  mov     eax, [rdi+1Ch]
0x180033e97  add     eax, [rdi+18h]
0x180033e9a  cmp     [rbp+var_18+8], eax
0x180033e9d  jnb     loc_180033FCF
0x180033ea3  mov     eax, [rbp+var_18+8]
0x180033ea6  imul    r8, rax, 54h ; 'T'
0x180033eaa  mov     eax, [rdi+20h]
0x180033ead  add     r8, rax
0x180033eb0  add     r8, [rdi+148h]
0x180033eb7  jz      loc_180033FCF
0x180033ebd  mov     eax, [rbp+var_18+0Ch]
0x180033ec0  xor     r11d, r11d
0x180033ec3  lea     r10d, [r11+1]
0x180033ec7  cmp     eax, [r8+34h]
0x180033ecb  jnb     short loc_180033F21
0x180033ecd  imul    eax, [r8+30h]
0x180033ed2  add     eax, [r8+38h]
0x180033ed6  jmp     short loc_180033F18
0x180033ed8  mov     eax, [rdi+1Ch]
0x180033edb  add     eax, [rdi+18h]
0x180033ede  cmp     ecx, eax
0x180033ee0  jnb     loc_180033FCF
0x180033ee6  mov     eax, [rdi+20h]
0x180033ee9  imul    r8, rcx, 54h ; 'T'
0x180033eed  add     r8, rax
0x180033ef0  add     r8, [rdi+148h]
0x180033ef7  jz      loc_180033FCF
0x180033efd  xor     r10d, r10d
0x180033f00  mov     r11d, 1
0x180033f06  cmp     r9d, [r8+34h]
0x180033f0a  jnb     short loc_180033F21
0x180033f0c  imul    r9d, [r8+30h]
0x180033f11  add     r9d, [r8+38h]
0x180033f15  mov     eax, r9d
0x180033f18  add     rax, [rdi+148h]
0x180033f1f  jmp     short loc_180033F23
0x180033f21  xor     eax, eax
0x180033f23  test    rax, rax
0x180033f26  jz      loc_180033FCF
0x180033f2c  cmp     [r14], ebx
0x180033f2f  jz      short loc_180033F3D
0x180033f31  mov     ecx, [r14]
0x180033f34  add     rcx, [rdi+140h]
0x180033f3b  jmp     short loc_180033F3F
0x180033f3d  xor     ecx, ecx
0x180033f3f  mov     r9d, r11d
0x180033f42  add     r9, r9
0x180033f45  mov     [rdx+r9*8], rcx
0x180033f49  cmp     [r12], ebx
0x180033f4d  jz      short loc_180033F5C
0x180033f4f  mov     ecx, [r12]
0x180033f53  add     rcx, [rdi+140h]
0x180033f5a  jmp     short loc_180033F5E
0x180033f5c  xor     ecx, ecx
0x180033f5e  mov     [rdx+r9*8+8], rcx
0x180033f63  cmp     [r8], ebx
0x180033f66  jz      short loc_180033F74
0x180033f68  mov     ecx, [r8]
0x180033f6b  add     rcx, [rdi+140h]
0x180033f72  jmp     short loc_180033F76
0x180033f74  xor     ecx, ecx
0x180033f76  mov     r8d, r10d
0x180033f79  add     r8, r8
0x180033f7c  mov     [rdx+r8*8], rcx
0x180033f80  cmp     [rax], ebx
0x180033f82  jz      short loc_180033F8F
0x180033f84  mov     eax, [rax]
0x180033f86  add     rax, [rdi+140h]
0x180033f8d  jmp     short loc_180033F91
0x180033f8f  xor     eax, eax
0x180033f91  mov     [rdx+r8*8+8], rax
0x180033f96  cmp     [rdx+r9*8], rbx
0x180033f9a  jz      short loc_180033FCF
0x180033f9c  cmp     [rdx+r9*8+8], rbx
0x180033fa1  jz      short loc_180033FCF
0x180033fa3  test    rcx, rcx
0x180033fa6  jz      short loc_180033FCF
0x180033fa8  test    rax, rax
0x180033fab  jz      short loc_180033FCF
0x180033fad  mov     rax, [rbp+arg_20]
0x180033fb1  mov     [rax], rdx
0x180033fb4  mov     rax, [rbp+arg_28]
0x180033fb8  mov     dword ptr [rax], 2
0x180033fbe  jmp     short loc_180033FD4
0x180033fc0  mov     rax, [rbp+arg_20]
0x180033fc4  mov     [rax], rbx
0x180033fc7  mov     rax, [rbp+arg_28]
0x180033fcb  mov     [rax], ebx
0x180033fcd  jmp     short loc_180033FD4
0x180033fcf  mov     ebx, 8000FFFFh
0x180033fd4  lea     r11, [rsp+50h+var_s0]
0x180033fd9  mov     eax, ebx
0x180033fdb  mov     rbx, [r11+38h]
0x180033fdf  mov     rsi, [r11+40h]
0x180033fe3  mov     rsp, r11
0x180033fe6  pop     r15
0x180033fe8  pop     r14
0x180033fea  pop     r12
0x180033fec  pop     rdi
0x180033fed  pop     rbp
0x180033fee  retn
```
