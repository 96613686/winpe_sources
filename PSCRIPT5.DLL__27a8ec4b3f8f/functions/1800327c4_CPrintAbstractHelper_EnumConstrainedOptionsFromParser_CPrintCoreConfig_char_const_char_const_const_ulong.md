# CPrintAbstractHelper::EnumConstrainedOptionsFromParser(CPrintCoreConfig *,char const *,char const * * * const,ulong *)

- ea: `0x1800327c4`
- end: `0x180032994`
- name: `?EnumConstrainedOptionsFromParser@CPrintAbstractHelper@@IEAAJPEAVCPrintCoreConfig@@PEBDQEAPEAPEBDPEAK@Z`
- size: `464`
- prototype: `__int64 __fastcall(CPrintAbstractHelper *this, struct CPrintCoreConfig *, const char *, const char ***const, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800329a0`

## callees

- `0x180001f20`
- `0x180002938`
- `0x180031044`
- `0x1800325f8`
- `0x1800327c4`
- `0x180034384`
- `0x1800343c8`
- `0x18005d988`
- `0x18005f010`

## pseudocode

```c
__int64 __fastcall CPrintAbstractHelper::EnumConstrainedOptionsFromParser(
        CPrintAbstractHelper *this,
        struct CPrintCoreConfig *a2,
        const char *a3,
        const char ***const a4,
        unsigned int *a5)
{
  struct _UIINFO *UIInfo; // rax
  struct _UIINFO *v9; // r14
  unsigned int *KeywordMatchFeature; // rax
  unsigned int *v12; // rbp
  _DWORD *v13; // rsi
  int v14; // ebx
  char *v15; // rax
  __int64 v16; // rcx
  unsigned int v17; // esi
  unsigned int v18; // edx
  const char **v19; // rax
  __int64 v20; // r11
  __int64 v21; // r8
  _DWORD *v22; // r9
  const char *v23; // rcx
  int v24; // [rsp+20h] [rbp-468h]
  unsigned int v25[4]; // [rsp+30h] [rbp-458h] BYREF
  _DWORD v26[256]; // [rsp+40h] [rbp-448h] BYREF

  v25[0] = 0;
  UIInfo = CPrintCoreConfig::GetUIInfo(a2);
  v9 = UIInfo;
  if ( !UIInfo )
    return 2147549183LL;
  KeywordMatchFeature = PInternalGetKeywordMatchFeature((__int64)UIInfo, a3, 0, v25);
  v12 = KeywordMatchFeature;
  if ( KeywordMatchFeature && BIsParserFeatureReadable(a2, (struct _FEATURE *)KeywordMatchFeature) )
  {
    memset_0(v26, 0, sizeof(v26));
    if ( *(_QWORD *)a2 && (v13 = (_DWORD *)(*(__int64 (**)(void))(*((_QWORD *)a2 + 1) + 32LL))()) != 0 )
    {
      v14 = 0;
      if ( *((_QWORD *)a2 + 2) )
        v15 = (char *)a2 + 28;
      else
        v15 = (char *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(*((_QWORD *)a2 + 1) + 8LL))(*(_QWORD *)a2, 0);
      EnumEnabledOptions(v13, (__int64)v15, v25[0], (__int64)v26, v24);
      v16 = 0;
      v17 = 0;
      if ( !v12[13] )
        goto LABEL_30;
      do
      {
        v18 = v17 + 1;
        if ( v26[v16] )
          v18 = v17;
        v16 = (unsigned int)(v16 + 1);
        v17 = v18;
      }
      while ( (unsigned int)v16 < v12[13] );
      if ( v18 )
      {
        v19 = (const char **)CPrintCoreConfig::PrivateAlloc(a2, 8LL * v18);
        if ( v19 )
        {
          v20 = 0;
          v21 = 0;
          while ( (unsigned int)v21 < v12[13] )
          {
            if ( !v26[v21] )
            {
              v22 = (_DWORD *)(*((_QWORD *)v9 + 41) + v12[14] + v12[12] * (_DWORD)v21);
              if ( !v22 )
                return (unsigned int)-2147418113;
              if ( *v22 )
                v23 = (const char *)(*((_QWORD *)v9 + 40) + (unsigned int)*v22);
              else
                v23 = 0;
              v19[v20] = v23;
              if ( !v23 )
                v14 = -2147418113;
              v20 = (unsigned int)(v20 + 1);
            }
            if ( v14 < 0 )
              return (unsigned int)v14;
            *a4 = v19;
            v21 = (unsigned int)(v21 + 1);
            *a5 = v17;
          }
        }
        else
        {
          return (unsigned int)-2147024882;
        }
      }
      else
      {
LABEL_30:
        *a4 = 0;
        *a5 = 0;
      }
    }
    else
    {
      return (unsigned int)-2147418113;
    }
  }
  else
  {
    return (unsigned int)-2147467259;
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1800327c4  push    rbx
0x1800327c6  push    rbp
0x1800327c7  push    rsi
0x1800327c8  push    rdi
0x1800327c9  push    r12
0x1800327cb  push    r14
0x1800327cd  push    r15
0x1800327cf  sub     rsp, 450h
0x1800327d6  mov     rax, cs:__security_cookie
0x1800327dd  xor     rax, rsp
0x1800327e0  mov     [rsp+488h+var_48], rax
0x1800327e8  mov     r12, [rsp+488h+arg_20]
0x1800327f0  mov     rcx, rdx; this
0x1800327f3  mov     r15, r9
0x1800327f6  mov     [rsp+488h+var_458], 0
0x1800327fe  mov     rbx, r8
0x180032801  mov     rdi, rdx
0x180032804  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x180032809  mov     r14, rax
0x18003280c  test    rax, rax
0x18003280f  jnz     short loc_18003281B
0x180032811  mov     eax, 8000FFFFh
0x180032816  jmp     loc_180032971
0x18003281b  lea     r9, [rsp+488h+var_458]
0x180032820  xor     r8d, r8d
0x180032823  mov     rdx, rbx
0x180032826  mov     rcx, r14
0x180032829  call    PInternalGetKeywordMatchFeature
0x18003282e  mov     rbp, rax
0x180032831  test    rax, rax
0x180032834  jz      loc_18003296A
0x18003283a  mov     rdx, rax; struct _FEATURE *
0x18003283d  mov     rcx, rdi; this
0x180032840  call    ?BIsParserFeatureReadable@@YAHPEAVCPrintCoreConfig@@PEAU_FEATURE@@@Z; BIsParserFeatureReadable(CPrintCoreConfig *,_FEATURE *)
0x180032845  test    eax, eax
0x180032847  jz      loc_18003296A
0x18003284d  xor     edx, edx; Val
0x18003284f  lea     rcx, [rsp+488h+var_448]; void *
0x180032854  mov     r8d, 400h; Size
0x18003285a  call    memset_0
0x18003285f  mov     rcx, [rdi]
0x180032862  test    rcx, rcx
0x180032865  jz      loc_180032963
0x18003286b  mov     rax, [rdi+8]
0x18003286f  mov     rax, [rax+20h]
0x180032873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032878  mov     rsi, rax
0x18003287b  test    rax, rax
0x18003287e  jz      loc_180032963
0x180032884  xor     ebx, ebx
0x180032886  cmp     [rdi+10h], rbx
0x18003288a  jz      short loc_180032892
0x18003288c  lea     rax, [rdi+1Ch]
0x180032890  jmp     short loc_1800328A4
0x180032892  mov     rax, [rdi+8]
0x180032896  xor     edx, edx
0x180032898  mov     rcx, [rdi]
0x18003289b  mov     rax, [rax+8]
0x18003289f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800328a4  mov     r8d, [rsp+488h+var_458]
0x1800328a9  lea     r9, [rsp+488h+var_448]
0x1800328ae  mov     rdx, rax
0x1800328b1  mov     rcx, rsi
0x1800328b4  call    EnumEnabledOptions
0x1800328b9  xor     ecx, ecx
0x1800328bb  xor     esi, esi
0x1800328bd  cmp     [rbp+34h], ecx
0x1800328c0  jbe     loc_18003295A
0x1800328c6  cmp     [rsp+rcx*4+488h+var_448], ebx
0x1800328ca  lea     edx, [rsi+1]
0x1800328cd  cmovnz  edx, esi
0x1800328d0  inc     ecx
0x1800328d2  mov     esi, edx
0x1800328d4  cmp     ecx, [rbp+34h]
0x1800328d7  jb      short loc_1800328C6
0x1800328d9  test    edx, edx
0x1800328db  jz      short loc_18003295A
0x1800328dd  mov     edx, esi
0x1800328df  mov     rcx, rdi; this
0x1800328e2  shl     rdx, 3; unsigned __int64
0x1800328e6  call    ?PrivateAlloc@CPrintCoreConfig@@QEAAPEAX_K@Z; CPrintCoreConfig::PrivateAlloc(unsigned __int64)
0x1800328eb  test    rax, rax
0x1800328ee  jnz     short loc_1800328F7
0x1800328f0  mov     ebx, 8007000Eh
0x1800328f5  jmp     short loc_18003296F
0x1800328f7  xor     r11d, r11d
0x1800328fa  mov     edx, 8000FFFFh
0x1800328ff  xor     r8d, r8d
0x180032902  cmp     r8d, [rbp+34h]
0x180032906  jnb     short loc_18003296F
0x180032908  cmp     [rsp+r8*4+488h+var_448], 0
0x18003290e  jnz     short loc_180032946
0x180032910  mov     r9d, r8d
0x180032913  imul    r9d, [rbp+30h]
0x180032918  add     r9d, [rbp+38h]
0x18003291c  add     r9, [r14+148h]
0x180032923  jz      short loc_180032956
0x180032925  cmp     dword ptr [r9], 0
0x180032929  jz      short loc_180032937
0x18003292b  mov     ecx, [r9]
0x18003292e  add     rcx, [r14+140h]
0x180032935  jmp     short loc_180032939
0x180032937  xor     ecx, ecx
0x180032939  test    rcx, rcx
0x18003293c  mov     [rax+r11*8], rcx
0x180032940  cmovz   ebx, edx
0x180032943  inc     r11d
0x180032946  test    ebx, ebx
0x180032948  js      short loc_18003296F
0x18003294a  mov     [r15], rax
0x18003294d  inc     r8d
0x180032950  mov     [r12], esi
0x180032954  jmp     short loc_180032902
0x180032956  mov     ebx, edx
0x180032958  jmp     short loc_18003296F
0x18003295a  mov     [r15], rbx
0x18003295d  mov     [r12], ebx
0x180032961  jmp     short loc_18003296F
0x180032963  mov     ebx, 8000FFFFh
0x180032968  jmp     short loc_18003296F
0x18003296a  mov     ebx, 80004005h
0x18003296f  mov     eax, ebx
0x180032971  mov     rcx, [rsp+488h+var_48]
0x180032979  xor     rcx, rsp; StackCookie
0x18003297c  call    __security_check_cookie
0x180032981  add     rsp, 450h
0x180032988  pop     r15
0x18003298a  pop     r14
0x18003298c  pop     r12
0x18003298e  pop     rdi
0x18003298f  pop     rsi
0x180032990  pop     rbp
0x180032991  pop     rbx
0x180032992  retn
```
