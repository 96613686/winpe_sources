# CPrintAbstractHelper::EnumConstrainedOptionsFromParser(CPrintCoreConfig *,char const *,char const * * * const,ulong *)

- ea: `0x180031170`
- end: `0x18003133f`
- name: `?EnumConstrainedOptionsFromParser@CPrintAbstractHelper@@IEAAJPEAVCPrintCoreConfig@@PEBDQEAPEAPEBDPEAK@Z`
- size: `463`
- prototype: `int(CPrintAbstractHelper *__hidden this, struct CPrintCoreConfig *, const char *, const char ***const, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180031350`

## callees

- `0x180001ee0`
- `0x1800028d8`
- `0x18002fac0`
- `0x180030fb8`
- `0x180031170`
- `0x180032d10`
- `0x180032d54`
- `0x18005bd18`
- `0x18005d010`

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
  struct _FEATURE *KeywordMatchFeature; // rax
  struct _FEATURE *v12; // rbp
  __int64 v13; // rsi
  int v14; // ebx
  int v15; // eax
  __int64 v16; // rcx
  unsigned int v17; // esi
  unsigned int v18; // edx
  const char **v19; // rax
  __int64 v20; // r11
  __int64 v21; // r8
  _DWORD *v22; // r9
  const char *v23; // rcx
  _DWORD v24[4]; // [rsp+30h] [rbp-458h] BYREF
  _DWORD v25[256]; // [rsp+40h] [rbp-448h] BYREF

  v24[0] = 0;
  UIInfo = CPrintCoreConfig::GetUIInfo(a2);
  v9 = UIInfo;
  if ( !UIInfo )
    return 2147549183LL;
  KeywordMatchFeature = (struct _FEATURE *)PInternalGetKeywordMatchFeature(UIInfo, a3, 0, v24);
  v12 = KeywordMatchFeature;
  if ( KeywordMatchFeature && (unsigned int)BIsParserFeatureReadable(a2, KeywordMatchFeature) )
  {
    memset_0(v25, 0, sizeof(v25));
    if ( *(_QWORD *)a2 && (v13 = (*(__int64 (**)(void))(*((_QWORD *)a2 + 1) + 32LL))()) != 0 )
    {
      v14 = 0;
      if ( *((_QWORD *)a2 + 2) )
        v15 = (_DWORD)a2 + 28;
      else
        v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*((_QWORD *)a2 + 1) + 8LL))(*(_QWORD *)a2, 0);
      EnumEnabledOptions(v13, v15, v24[0], (unsigned int)v25);
      v16 = 0;
      v17 = 0;
      if ( !*((_DWORD *)v12 + 13) )
        goto LABEL_30;
      do
      {
        v18 = v17 + 1;
        if ( v25[v16] )
          v18 = v17;
        v16 = (unsigned int)(v16 + 1);
        v17 = v18;
      }
      while ( (unsigned int)v16 < *((_DWORD *)v12 + 13) );
      if ( v18 )
      {
        v19 = (const char **)CPrintCoreConfig::PrivateAlloc(a2, 8LL * v18);
        if ( v19 )
        {
          v20 = 0;
          v21 = 0;
          while ( (unsigned int)v21 < *((_DWORD *)v12 + 13) )
          {
            if ( !v25[v21] )
            {
              v22 = (_DWORD *)(*((_QWORD *)v9 + 41) + (unsigned int)(*((_DWORD *)v12 + 14) + *((_DWORD *)v12 + 12) * v21));
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
0x180031170  push    rbx
0x180031172  push    rbp
0x180031173  push    rsi
0x180031174  push    rdi
0x180031175  push    r12
0x180031177  push    r14
0x180031179  push    r15
0x18003117b  sub     rsp, 450h
0x180031182  mov     rax, cs:__security_cookie
0x180031189  xor     rax, rsp
0x18003118c  mov     [rsp+488h+var_48], rax
0x180031194  mov     r12, [rsp+488h+arg_20]
0x18003119c  mov     rcx, rdx; this
0x18003119f  mov     r15, r9
0x1800311a2  mov     [rsp+488h+var_458], 0
0x1800311aa  mov     rbx, r8
0x1800311ad  mov     rdi, rdx
0x1800311b0  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x1800311b5  mov     r14, rax
0x1800311b8  test    rax, rax
0x1800311bb  jnz     short loc_1800311C7
0x1800311bd  mov     eax, 8000FFFFh
0x1800311c2  jmp     loc_18003131D
0x1800311c7  lea     r9, [rsp+488h+var_458]
0x1800311cc  xor     r8d, r8d
0x1800311cf  mov     rdx, rbx
0x1800311d2  mov     rcx, r14
0x1800311d5  call    PInternalGetKeywordMatchFeature
0x1800311da  mov     rbp, rax
0x1800311dd  test    rax, rax
0x1800311e0  jz      loc_180031316
0x1800311e6  mov     rdx, rax; struct _FEATURE *
0x1800311e9  mov     rcx, rdi; this
0x1800311ec  call    ?BIsParserFeatureReadable@@YAHPEAVCPrintCoreConfig@@PEAU_FEATURE@@@Z; BIsParserFeatureReadable(CPrintCoreConfig *,_FEATURE *)
0x1800311f1  test    eax, eax
0x1800311f3  jz      loc_180031316
0x1800311f9  xor     edx, edx; Val
0x1800311fb  lea     rcx, [rsp+488h+var_448]; void *
0x180031200  mov     r8d, 400h; Size
0x180031206  call    memset_0
0x18003120b  mov     rcx, [rdi]
0x18003120e  test    rcx, rcx
0x180031211  jz      loc_18003130F
0x180031217  mov     rax, [rdi+8]
0x18003121b  mov     rax, [rax+20h]
0x18003121f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031224  mov     rsi, rax
0x180031227  test    rax, rax
0x18003122a  jz      loc_18003130F
0x180031230  xor     ebx, ebx
0x180031232  cmp     [rdi+10h], rbx
0x180031236  jz      short loc_18003123E
0x180031238  lea     rax, [rdi+1Ch]
0x18003123c  jmp     short loc_180031250
0x18003123e  mov     rax, [rdi+8]
0x180031242  xor     edx, edx
0x180031244  mov     rcx, [rdi]
0x180031247  mov     rax, [rax+8]
0x18003124b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031250  mov     r8d, [rsp+488h+var_458]
0x180031255  lea     r9, [rsp+488h+var_448]
0x18003125a  mov     rdx, rax
0x18003125d  mov     rcx, rsi
0x180031260  call    EnumEnabledOptions
0x180031265  xor     ecx, ecx
0x180031267  xor     esi, esi
0x180031269  cmp     [rbp+34h], ecx
0x18003126c  jbe     loc_180031306
0x180031272  cmp     [rsp+rcx*4+488h+var_448], ebx
0x180031276  lea     edx, [rsi+1]
0x180031279  cmovnz  edx, esi
0x18003127c  inc     ecx
0x18003127e  mov     esi, edx
0x180031280  cmp     ecx, [rbp+34h]
0x180031283  jb      short loc_180031272
0x180031285  test    edx, edx
0x180031287  jz      short loc_180031306
0x180031289  mov     edx, esi
0x18003128b  mov     rcx, rdi; this
0x18003128e  shl     rdx, 3; unsigned __int64
0x180031292  call    ?PrivateAlloc@CPrintCoreConfig@@QEAAPEAX_K@Z; CPrintCoreConfig::PrivateAlloc(unsigned __int64)
0x180031297  test    rax, rax
0x18003129a  jnz     short loc_1800312A3
0x18003129c  mov     ebx, 8007000Eh
0x1800312a1  jmp     short loc_18003131B
0x1800312a3  xor     r11d, r11d
0x1800312a6  mov     edx, 8000FFFFh
0x1800312ab  xor     r8d, r8d
0x1800312ae  cmp     r8d, [rbp+34h]
0x1800312b2  jnb     short loc_18003131B
0x1800312b4  cmp     [rsp+r8*4+488h+var_448], 0
0x1800312ba  jnz     short loc_1800312F2
0x1800312bc  mov     r9d, r8d
0x1800312bf  imul    r9d, [rbp+30h]
0x1800312c4  add     r9d, [rbp+38h]
0x1800312c8  add     r9, [r14+148h]
0x1800312cf  jz      short loc_180031302
0x1800312d1  cmp     dword ptr [r9], 0
0x1800312d5  jz      short loc_1800312E3
0x1800312d7  mov     ecx, [r9]
0x1800312da  add     rcx, [r14+140h]
0x1800312e1  jmp     short loc_1800312E5
0x1800312e3  xor     ecx, ecx
0x1800312e5  test    rcx, rcx
0x1800312e8  mov     [rax+r11*8], rcx
0x1800312ec  cmovz   ebx, edx
0x1800312ef  inc     r11d
0x1800312f2  test    ebx, ebx
0x1800312f4  js      short loc_18003131B
0x1800312f6  mov     [r15], rax
0x1800312f9  inc     r8d
0x1800312fc  mov     [r12], esi
0x180031300  jmp     short loc_1800312AE
0x180031302  mov     ebx, edx
0x180031304  jmp     short loc_18003131B
0x180031306  mov     [r15], rbx
0x180031309  mov     [r12], ebx
0x18003130d  jmp     short loc_18003131B
0x18003130f  mov     ebx, 8000FFFFh
0x180031314  jmp     short loc_18003131B
0x180031316  mov     ebx, 80004005h
0x18003131b  mov     eax, ebx
0x18003131d  mov     rcx, [rsp+488h+var_48]
0x180031325  xor     rcx, rsp; StackCookie
0x180031328  call    __security_check_cookie
0x18003132d  add     rsp, 450h
0x180031334  pop     r15
0x180031336  pop     r14
0x180031338  pop     r12
0x18003133a  pop     rdi
0x18003133b  pop     rsi
0x18003133c  pop     rbp
0x18003133d  pop     rbx
0x18003133e  retn
```
