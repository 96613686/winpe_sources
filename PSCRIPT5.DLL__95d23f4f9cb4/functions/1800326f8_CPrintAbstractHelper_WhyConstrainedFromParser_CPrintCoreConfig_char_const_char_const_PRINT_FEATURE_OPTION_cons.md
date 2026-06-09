# CPrintAbstractHelper::WhyConstrainedFromParser(CPrintCoreConfig *,char const *,char const *,_PRINT_FEATURE_OPTION const * *,ulong *)

- ea: `0x1800326f8`
- end: `0x18003298f`
- name: `?WhyConstrainedFromParser@CPrintAbstractHelper@@IEAAJPEAVCPrintCoreConfig@@PEBD1PEAPEBU_PRINT_FEATURE_OPTION@@PEAK@Z`
- size: `663`
- prototype: `int(CPrintAbstractHelper *__hidden this, struct CPrintCoreConfig *, const char *, const char *, const struct _PRINT_FEATURE_OPTION **, unsigned int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180032c10`

## callees

- `0x18002fac0`
- `0x18002fb5c`
- `0x180030fb8`
- `0x1800326f8`
- `0x180032d10`
- `0x180032d54`
- `0x18005be24`
- `0x18005d010`

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
  int v6; // r15d
  struct _UIINFO *UIInfo; // rax
  struct _UIINFO *v10; // rdi
  int v11; // ecx
  struct _FEATURE *KeywordMatchFeature; // r14
  _DWORD *KeywordMatchOption; // r12
  __int64 v14; // rcx
  __int64 v15; // r15
  unsigned int v16; // ebx
  int v17; // eax
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
  __int128 v30; // [rsp+38h] [rbp-18h] BYREF
  unsigned int v31; // [rsp+80h] [rbp+30h] BYREF
  int v32; // [rsp+84h] [rbp+34h]

  v32 = HIDWORD(this);
  v31 = 0;
  v6 = (int)a4;
  v29 = 0;
  UIInfo = CPrintCoreConfig::GetUIInfo(a2);
  v10 = UIInfo;
  if ( !UIInfo )
    return (unsigned int)-2147418113;
  KeywordMatchFeature = (struct _FEATURE *)PInternalGetKeywordMatchFeature(UIInfo, a3, 0, &v31);
  if ( !KeywordMatchFeature )
    return (unsigned int)-2147467259;
  KeywordMatchOption = (_DWORD *)PInternalGetKeywordMatchOption(v11, (_DWORD)KeywordMatchFeature, v6, 0, (__int64)&v29);
  if ( !KeywordMatchOption )
    return (unsigned int)-2147467259;
  v14 = *(_QWORD *)a2;
  v30 = 0;
  if ( !v14 )
    return (unsigned int)-2147418113;
  v15 = (*(__int64 (**)(void))(*((_QWORD *)a2 + 1) + 32LL))();
  if ( !v15 )
    return (unsigned int)-2147418113;
  if ( (unsigned int)BIsParserFeatureReadable(a2, KeywordMatchFeature) )
  {
    v16 = 0;
    if ( *((_QWORD *)a2 + 2) )
      v17 = (_DWORD)a2 + 28;
    else
      v17 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*((_QWORD *)a2 + 1) + 8LL))(*(_QWORD *)a2, 0);
    if ( !(unsigned int)EnumNewPickOneUIConflict(v15, v17, v31, v29, (__int64)&v30) )
    {
      *a5 = 0;
      *a6 = 0;
      return v16;
    }
    v18 = (const struct _PRINT_FEATURE_OPTION *)CPrintCoreConfig::PrivateAlloc(a2, 0x20u);
    if ( !v18 )
      return (unsigned int)-2147024882;
    if ( (_QWORD)v30 == __PAIR64__(v29, v31) )
    {
      if ( DWORD2(v30) >= *((_DWORD *)v10 + 6) + *((_DWORD *)v10 + 7) )
        return (unsigned int)-2147418113;
      v19 = (unsigned int *)(*((_QWORD *)v10 + 41) + *((unsigned int *)v10 + 8) + 84LL * DWORD2(v30));
      if ( !v19 )
        return (unsigned int)-2147418113;
      v20 = 0;
      v21 = 1;
      if ( HIDWORD(v30) < v19[13] )
      {
        v22 = v19[14] + v19[12] * HIDWORD(v30);
LABEL_23:
        v23 = (_DWORD *)(*((_QWORD *)v10 + 41) + v22);
LABEL_25:
        if ( v23 )
        {
          v24 = *(_DWORD *)KeywordMatchFeature
              ? (const CHAR *)(*((_QWORD *)v10 + 40) + *(unsigned int *)KeywordMatchFeature)
              : 0LL;
          v18[v20].pszFeature = v24;
          v25 = *KeywordMatchOption ? (const CHAR *)(*((_QWORD *)v10 + 40) + (unsigned int)*KeywordMatchOption) : 0LL;
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
      if ( (unsigned int)v30 >= *((_DWORD *)v10 + 6) + *((_DWORD *)v10 + 7) )
        return (unsigned int)-2147418113;
      v19 = (unsigned int *)(*((_QWORD *)v10 + 41) + *((unsigned int *)v10 + 8) + 84LL * (unsigned int)v30);
      if ( !v19 )
        return (unsigned int)-2147418113;
      v21 = 0;
      v20 = 1;
      if ( DWORD1(v30) < v19[13] )
      {
        v22 = v19[14] + v19[12] * DWORD1(v30);
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
0x1800326f8  mov     [rsp-28h+arg_8], rbx
0x1800326fd  mov     [rsp-28h+arg_10], rsi
0x180032702  mov     [rsp-28h+arg_0], rcx
0x180032707  push    rbp
0x180032708  push    rdi
0x180032709  push    r12
0x18003270b  push    r14
0x18003270d  push    r15
0x18003270f  mov     rbp, rsp
0x180032712  sub     rsp, 50h
0x180032716  mov     rcx, rdx; this
0x180032719  mov     dword ptr [rbp+arg_0], 0
0x180032720  mov     r15, r9
0x180032723  mov     [rbp+var_20], 0
0x18003272a  mov     rbx, r8
0x18003272d  mov     rsi, rdx
0x180032730  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x180032735  mov     rdi, rax
0x180032738  test    rax, rax
0x18003273b  jz      loc_18003296F
0x180032741  lea     r9, [rbp+arg_0]
0x180032745  xor     r8d, r8d
0x180032748  mov     rdx, rbx
0x18003274b  mov     rcx, rax
0x18003274e  call    PInternalGetKeywordMatchFeature
0x180032753  mov     r14, rax
0x180032756  test    rax, rax
0x180032759  jz      short loc_1800327B5
0x18003275b  lea     rax, [rbp+var_20]
0x18003275f  xor     r9d, r9d
0x180032762  mov     r8, r15
0x180032765  mov     [rsp+50h+var_30], rax
0x18003276a  mov     rdx, r14
0x18003276d  call    PInternalGetKeywordMatchOption
0x180032772  mov     r12, rax
0x180032775  test    rax, rax
0x180032778  jz      short loc_1800327B5
0x18003277a  mov     rcx, [rsi]
0x18003277d  xorps   xmm0, xmm0
0x180032780  movups  [rbp+var_18], xmm0
0x180032784  test    rcx, rcx
0x180032787  jz      loc_18003296F
0x18003278d  mov     rax, [rsi+8]
0x180032791  mov     rax, [rax+20h]
0x180032795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003279a  mov     r15, rax
0x18003279d  test    rax, rax
0x1800327a0  jz      loc_18003296F
0x1800327a6  mov     rdx, r14; struct _FEATURE *
0x1800327a9  mov     rcx, rsi; this
0x1800327ac  call    ?BIsParserFeatureReadable@@YAHPEAVCPrintCoreConfig@@PEAU_FEATURE@@@Z; BIsParserFeatureReadable(CPrintCoreConfig *,_FEATURE *)
0x1800327b1  test    eax, eax
0x1800327b3  jnz     short loc_1800327BF
0x1800327b5  mov     ebx, 80004005h
0x1800327ba  jmp     loc_180032974
0x1800327bf  xor     ebx, ebx
0x1800327c1  cmp     [rsi+10h], rbx
0x1800327c5  jz      short loc_1800327CD
0x1800327c7  lea     rax, [rsi+1Ch]
0x1800327cb  jmp     short loc_1800327DF
0x1800327cd  mov     rax, [rsi+8]
0x1800327d1  xor     edx, edx
0x1800327d3  mov     rcx, [rsi]
0x1800327d6  mov     rax, [rax+8]
0x1800327da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800327df  mov     r9d, [rbp+var_20]
0x1800327e3  lea     rcx, [rbp+var_18]
0x1800327e7  mov     r8d, dword ptr [rbp+arg_0]
0x1800327eb  mov     rdx, rax
0x1800327ee  mov     [rsp+50h+var_30], rcx
0x1800327f3  mov     rcx, r15
0x1800327f6  call    EnumNewPickOneUIConflict
0x1800327fb  test    eax, eax
0x1800327fd  jz      loc_180032960
0x180032803  mov     edx, 20h ; ' '; unsigned __int64
0x180032808  mov     rcx, rsi; this
0x18003280b  call    ?PrivateAlloc@CPrintCoreConfig@@QEAAPEAX_K@Z; CPrintCoreConfig::PrivateAlloc(unsigned __int64)
0x180032810  mov     rdx, rax
0x180032813  test    rax, rax
0x180032816  jnz     short loc_180032822
0x180032818  mov     ebx, 8007000Eh
0x18003281d  jmp     loc_180032974
0x180032822  mov     ecx, dword ptr [rbp+var_18]
0x180032825  mov     r9d, dword ptr [rbp+var_18+4]
0x180032829  cmp     ecx, dword ptr [rbp+arg_0]
0x18003282c  jnz     short loc_180032878
0x18003282e  cmp     r9d, [rbp+var_20]
0x180032832  jnz     short loc_180032878
0x180032834  mov     eax, [rdi+1Ch]
0x180032837  add     eax, [rdi+18h]
0x18003283a  cmp     dword ptr [rbp+var_18+8], eax
0x18003283d  jnb     loc_18003296F
0x180032843  mov     eax, dword ptr [rbp+var_18+8]
0x180032846  imul    r8, rax, 54h ; 'T'
0x18003284a  mov     eax, [rdi+20h]
0x18003284d  add     r8, rax
0x180032850  add     r8, [rdi+148h]
0x180032857  jz      loc_18003296F
0x18003285d  mov     eax, dword ptr [rbp+var_18+0Ch]
0x180032860  xor     r11d, r11d
0x180032863  lea     r10d, [r11+1]
0x180032867  cmp     eax, [r8+34h]
0x18003286b  jnb     short loc_1800328C1
0x18003286d  imul    eax, [r8+30h]
0x180032872  add     eax, [r8+38h]
0x180032876  jmp     short loc_1800328B8
0x180032878  mov     eax, [rdi+1Ch]
0x18003287b  add     eax, [rdi+18h]
0x18003287e  cmp     ecx, eax
0x180032880  jnb     loc_18003296F
0x180032886  mov     eax, [rdi+20h]
0x180032889  imul    r8, rcx, 54h ; 'T'
0x18003288d  add     r8, rax
0x180032890  add     r8, [rdi+148h]
0x180032897  jz      loc_18003296F
0x18003289d  xor     r10d, r10d
0x1800328a0  mov     r11d, 1
0x1800328a6  cmp     r9d, [r8+34h]
0x1800328aa  jnb     short loc_1800328C1
0x1800328ac  imul    r9d, [r8+30h]
0x1800328b1  add     r9d, [r8+38h]
0x1800328b5  mov     eax, r9d
0x1800328b8  add     rax, [rdi+148h]
0x1800328bf  jmp     short loc_1800328C3
0x1800328c1  xor     eax, eax
0x1800328c3  test    rax, rax
0x1800328c6  jz      loc_18003296F
0x1800328cc  cmp     [r14], ebx
0x1800328cf  jz      short loc_1800328DD
0x1800328d1  mov     ecx, [r14]
0x1800328d4  add     rcx, [rdi+140h]
0x1800328db  jmp     short loc_1800328DF
0x1800328dd  xor     ecx, ecx
0x1800328df  mov     r9d, r11d
0x1800328e2  add     r9, r9
0x1800328e5  mov     [rdx+r9*8], rcx
0x1800328e9  cmp     [r12], ebx
0x1800328ed  jz      short loc_1800328FC
0x1800328ef  mov     ecx, [r12]
0x1800328f3  add     rcx, [rdi+140h]
0x1800328fa  jmp     short loc_1800328FE
0x1800328fc  xor     ecx, ecx
0x1800328fe  mov     [rdx+r9*8+8], rcx
0x180032903  cmp     [r8], ebx
0x180032906  jz      short loc_180032914
0x180032908  mov     ecx, [r8]
0x18003290b  add     rcx, [rdi+140h]
0x180032912  jmp     short loc_180032916
0x180032914  xor     ecx, ecx
0x180032916  mov     r8d, r10d
0x180032919  add     r8, r8
0x18003291c  mov     [rdx+r8*8], rcx
0x180032920  cmp     [rax], ebx
0x180032922  jz      short loc_18003292F
0x180032924  mov     eax, [rax]
0x180032926  add     rax, [rdi+140h]
0x18003292d  jmp     short loc_180032931
0x18003292f  xor     eax, eax
0x180032931  mov     [rdx+r8*8+8], rax
0x180032936  cmp     [rdx+r9*8], rbx
0x18003293a  jz      short loc_18003296F
0x18003293c  cmp     [rdx+r9*8+8], rbx
0x180032941  jz      short loc_18003296F
0x180032943  test    rcx, rcx
0x180032946  jz      short loc_18003296F
0x180032948  test    rax, rax
0x18003294b  jz      short loc_18003296F
0x18003294d  mov     rax, [rbp+arg_20]
0x180032951  mov     [rax], rdx
0x180032954  mov     rax, [rbp+arg_28]
0x180032958  mov     dword ptr [rax], 2
0x18003295e  jmp     short loc_180032974
0x180032960  mov     rax, [rbp+arg_20]
0x180032964  mov     [rax], rbx
0x180032967  mov     rax, [rbp+arg_28]
0x18003296b  mov     [rax], ebx
0x18003296d  jmp     short loc_180032974
0x18003296f  mov     ebx, 8000FFFFh
0x180032974  lea     r11, [rsp+50h+var_s0]
0x180032979  mov     eax, ebx
0x18003297b  mov     rbx, [r11+38h]
0x18003297f  mov     rsi, [r11+40h]
0x180032983  mov     rsp, r11
0x180032986  pop     r15
0x180032988  pop     r14
0x18003298a  pop     r12
0x18003298c  pop     rdi
0x18003298d  pop     rbp
0x18003298e  retn
```
