# CPrintAbstractHelper::GetOptionInternal(char const *,CPrintCoreConfig *,char const * *)

- ea: `0x180033100`
- end: `0x1800333b9`
- name: `?GetOptionInternal@CPrintAbstractHelper@@MEAAJPEBDPEAVCPrintCoreConfig@@PEAPEBD@Z`
- size: `697`
- prototype: `__int64 __fastcall(CPrintAbstractHelper *this, const char *, struct CPrintCoreConfig *, const char **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002dcf0`

## callees

- `0x180031044`
- `0x1800325f8`
- `0x180033100`
- `0x180034320`
- `0x180034384`
- `0x18005f010`

## pseudocode

```c
__int64 __fastcall CPrintAbstractHelper::GetOptionInternal(
        CPrintAbstractHelper *this,
        const char *a2,
        struct CPrintCoreConfig *a3,
        const char **a4)
{
  __int64 v4; // rax
  __int64 v7; // rdi
  char HelperSettingsFlags; // r14
  struct _UIINFO *UIInfo; // rax
  struct _UIINFO *v10; // r13
  unsigned int *KeywordMatchFeature; // rsi
  char *v13; // rcx
  char *v14; // rbp
  __int64 v15; // rax
  unsigned int v16; // ebx
  __int64 v17; // r14
  unsigned int v18; // eax
  _DWORD *v19; // rdi
  __int64 v20; // rcx
  __int64 v21; // rdx
  unsigned int v22; // eax
  __int64 v23; // rax
  __int64 v24; // rbp
  const char *v25; // r8
  int v26; // edx
  int v27; // ecx
  const char *v28; // rax
  _DWORD *v29; // rsi
  __int64 i; // rdi
  __int64 v31; // r9
  __int64 v32; // rdx
  int v33; // eax
  int v34; // r8d
  bool v35; // zf
  char *v36; // [rsp+20h] [rbp-48h]
  unsigned int v37; // [rsp+70h] [rbp+8h] BYREF
  const char **v38; // [rsp+88h] [rbp+20h]

  v38 = a4;
  v4 = *(_QWORD *)this;
  v37 = 0;
  v7 = (*(__int64 (__fastcall **)(CPrintAbstractHelper *, struct CPrintCoreConfig *))(v4 + 72))(this, a3);
  HelperSettingsFlags = CPrintCoreConfig::GetHelperSettingsFlags(a3);
  UIInfo = CPrintCoreConfig::GetUIInfo(a3);
  v10 = UIInfo;
  if ( !UIInfo )
    return 2147549183LL;
  KeywordMatchFeature = PInternalGetKeywordMatchFeature((__int64)UIInfo, a2, 0, &v37);
  if ( (HelperSettingsFlags & 0xA) == 0 )
    return (unsigned int)-2147467259;
  v13 = (char *)a3 + 8;
  v36 = (char *)a3 + 8;
  if ( *((_QWORD *)a3 + 2) )
  {
    v14 = (char *)a3 + 28;
  }
  else
  {
    v15 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v13 + 8LL))(*(_QWORD *)a3, 0);
    v13 = (char *)a3 + 8;
    v14 = (char *)v15;
    v36 = (char *)a3 + 8;
  }
  if ( !v14 )
    return (unsigned int)-2147418113;
  v16 = 0;
  if ( !KeywordMatchFeature )
  {
    if ( v7 )
    {
      v23 = *((_QWORD *)a3 + 2);
      if ( v23 || (v23 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v13 + 48LL))(*(_QWORD *)a3)) != 0 )
        v24 = v23 + *(unsigned __int16 *)(v23 + 68);
      else
        v24 = 0;
      while ( 1 )
      {
        v28 = *(const char **)v7;
        if ( !*(_QWORD *)v7 )
          break;
        v25 = (const char *)(a2 - v28);
        do
        {
          v26 = (unsigned __int8)v25[(_QWORD)v28];
          v27 = *(unsigned __int8 *)v28 - v26;
          if ( v27 )
            break;
          ++v28;
        }
        while ( v26 );
        if ( !v27 )
        {
          v29 = (_DWORD *)(v7 + 8);
          if ( (HelperSettingsFlags & 2) == 0 && !*v29 || (HelperSettingsFlags & 8) == 0 && *v29 == 1 )
            return (unsigned int)-2147467259;
          for ( i = *(_QWORD *)(v7 + 16); *(_QWORD *)i; i += 32 )
          {
            if ( *(_QWORD *)a3 )
              v31 = (*(__int64 (**)(void))(*(_QWORD *)v36 + 40LL))();
            else
              v31 = 0;
            v32 = i;
            if ( !*v29 )
              v31 = v24;
            while ( 1 )
            {
              if ( (*(_BYTE *)(v32 + 8) & 4) == 0 )
              {
                v33 = *(_DWORD *)(v32 + 24);
                if ( v33 )
                {
                  switch ( v33 )
                  {
                    case 1:
                      v34 = 0;
                      v35 = *(_WORD *)(v31 + *(_QWORD *)(v32 + 16)) == *(_WORD *)(v32 + 12);
                      break;
                    case 2:
                      v34 = 0;
                      v35 = (*(_DWORD *)(v32 + 12) & *(_DWORD *)(v31 + *(_QWORD *)(v32 + 16))) == *(_DWORD *)(v32 + 12);
                      break;
                    case 3:
                      v34 = 0;
                      v35 = (*(_DWORD *)(v31 + *(_QWORD *)(v32 + 16)) & *(_DWORD *)(v32 + 12)) == 0;
                      break;
                    default:
                      goto LABEL_58;
                  }
                }
                else
                {
                  v34 = 0;
                  v35 = *(_DWORD *)(v31 + *(_QWORD *)(v32 + 16)) == *(_DWORD *)(v32 + 12);
                }
                LOBYTE(v34) = v35;
                if ( !v34 )
                  break;
              }
              if ( (*(_BYTE *)(v32 + 8) & 2) == 0 )
              {
                *v38 = *(const char **)i;
                return v16;
              }
              v32 += 32;
            }
LABEL_58:
            while ( (*(_BYTE *)(i + 8) & 2) != 0 )
              i += 32;
          }
          return (unsigned int)-2147418113;
        }
        v7 += 24;
      }
    }
    return (unsigned int)-2147467259;
  }
  v17 = v37;
  v18 = (unsigned __int8)v14[2 * v37];
  if ( v18 >= KeywordMatchFeature[13] )
    v19 = 0;
  else
    v19 = (_DWORD *)(*((_QWORD *)v10 + 41) + KeywordMatchFeature[14] + KeywordMatchFeature[12] * v18);
  if ( !BIsParserFeatureReadable(a3, (struct _FEATURE *)KeywordMatchFeature) )
    return (unsigned int)-2147467259;
  if ( !v19 )
  {
    v22 = -2147418113;
    if ( v14[2 * v17] == -1 )
      return (unsigned int)-2147467259;
    return v22;
  }
  if ( *v19 )
  {
    v20 = (unsigned int)*v19;
    v21 = *((_QWORD *)v10 + 40);
    *v38 = (const char *)(v20 + v21);
    if ( v20 + v21 )
      return v16;
  }
  else
  {
    *v38 = 0;
  }
  return (unsigned int)-2147418113;
}

```

## disassembly

```asm
0x180033100  mov     [rsp+arg_8], rbx
0x180033105  mov     [rsp+arg_18], r9
0x18003310a  push    rbp
0x18003310b  push    rsi
0x18003310c  push    rdi
0x18003310d  push    r12
0x18003310f  push    r13
0x180033111  push    r14
0x180033113  push    r15
0x180033115  sub     rsp, 30h
0x180033119  mov     rax, [rcx]
0x18003311c  mov     r12, rdx
0x18003311f  mov     rdx, r8
0x180033122  mov     [rsp+68h+arg_0], 0
0x18003312a  mov     r15, r8
0x18003312d  mov     rax, [rax+48h]
0x180033131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033136  mov     rcx, r15; this
0x180033139  mov     rdi, rax
0x18003313c  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x180033141  mov     rcx, r15; this
0x180033144  mov     r14d, eax
0x180033147  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x18003314c  mov     r13, rax
0x18003314f  test    rax, rax
0x180033152  jnz     short loc_18003315E
0x180033154  mov     eax, 8000FFFFh
0x180033159  jmp     loc_1800332B0
0x18003315e  lea     r9, [rsp+68h+arg_0]
0x180033163  xor     r8d, r8d
0x180033166  mov     rdx, r12
0x180033169  mov     rcx, r13
0x18003316c  call    PInternalGetKeywordMatchFeature
0x180033171  mov     rsi, rax
0x180033174  test    r14b, 0Ah
0x180033178  jz      loc_1800332A9
0x18003317e  cmp     qword ptr [r15+10h], 0
0x180033183  lea     rcx, [r15+8]
0x180033187  mov     [rsp+68h+var_48], rcx
0x18003318c  jz      short loc_180033194
0x18003318e  lea     rbp, [r15+1Ch]
0x180033192  jmp     short loc_1800331B1
0x180033194  mov     rax, [rcx]
0x180033197  xor     edx, edx
0x180033199  mov     rcx, [r15]
0x18003319c  mov     rax, [rax+8]
0x1800331a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800331a5  lea     rcx, [r15+8]
0x1800331a9  mov     rbp, rax
0x1800331ac  mov     [rsp+68h+var_48], rcx
0x1800331b1  test    rbp, rbp
0x1800331b4  jnz     short loc_1800331C0
0x1800331b6  mov     ebx, 8000FFFFh
0x1800331bb  jmp     loc_1800332AE
0x1800331c0  xor     ebx, ebx
0x1800331c2  test    rsi, rsi
0x1800331c5  jz      loc_180033251
0x1800331cb  mov     r14d, [rsp+68h+arg_0]
0x1800331d0  movzx   eax, byte ptr [rbp+r14*2+0]
0x1800331d6  cmp     eax, [rsi+34h]
0x1800331d9  jnb     short loc_1800331ED
0x1800331db  imul    eax, [rsi+30h]
0x1800331df  add     eax, [rsi+38h]
0x1800331e2  mov     edi, eax
0x1800331e4  add     rdi, [r13+148h]
0x1800331eb  jmp     short loc_1800331EF
0x1800331ed  xor     edi, edi
0x1800331ef  mov     rdx, rsi; struct _FEATURE *
0x1800331f2  mov     rcx, r15; this
0x1800331f5  call    ?BIsParserFeatureReadable@@YAHPEAVCPrintCoreConfig@@PEAU_FEATURE@@@Z; BIsParserFeatureReadable(CPrintCoreConfig *,_FEATURE *)
0x1800331fa  test    eax, eax
0x1800331fc  jz      loc_1800332A9
0x180033202  test    rdi, rdi
0x180033205  jz      short loc_18003323A
0x180033207  cmp     [rdi], ebx
0x180033209  jz      short loc_18003322A
0x18003320b  mov     ecx, [rdi]
0x18003320d  mov     rdx, [r13+140h]
0x180033214  add     rdx, rcx
0x180033217  mov     rcx, [rsp+68h+arg_18]
0x18003321f  mov     [rcx], rdx
0x180033222  jnz     loc_1800332AE
0x180033228  jmp     short loc_1800331B6
0x18003322a  mov     rcx, [rsp+68h+arg_18]
0x180033232  mov     [rcx], rbx
0x180033235  jmp     loc_1800331B6
0x18003323a  cmp     byte ptr [rbp+r14*2+0], 0FFh
0x180033240  mov     ebx, 80004005h
0x180033245  mov     eax, 8000FFFFh
0x18003324a  cmovz   eax, ebx
0x18003324d  mov     ebx, eax
0x18003324f  jmp     short loc_1800332AE
0x180033251  test    rdi, rdi
0x180033254  jz      short loc_1800332A9
0x180033256  mov     rax, [r15+10h]
0x18003325a  test    rax, rax
0x18003325d  jnz     short loc_180033273
0x18003325f  mov     rax, [rcx]
0x180033262  mov     rcx, [r15]
0x180033265  mov     rax, [rax+30h]
0x180033269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003326e  test    rax, rax
0x180033271  jz      short loc_18003327C
0x180033273  movzx   ebp, word ptr [rax+44h]
0x180033277  add     rbp, rax
0x18003327a  jmp     short loc_1800332A1
0x18003327c  xor     ebp, ebp
0x18003327e  jmp     short loc_1800332A1
0x180033280  mov     r8, r12
0x180033283  sub     r8, rax
0x180033286  movzx   ecx, byte ptr [rax]
0x180033289  movzx   edx, byte ptr [rax+r8]
0x18003328e  sub     ecx, edx
0x180033290  jnz     short loc_180033299
0x180033292  inc     rax
0x180033295  test    edx, edx
0x180033297  jnz     short loc_180033286
0x180033299  test    ecx, ecx
0x18003329b  jz      short loc_1800332C6
0x18003329d  add     rdi, 18h
0x1800332a1  mov     rax, [rdi]
0x1800332a4  test    rax, rax
0x1800332a7  jnz     short loc_180033280
0x1800332a9  mov     ebx, 80004005h
0x1800332ae  mov     eax, ebx
0x1800332b0  mov     rbx, [rsp+68h+arg_8]
0x1800332b5  add     rsp, 30h
0x1800332b9  pop     r15
0x1800332bb  pop     r14
0x1800332bd  pop     r13
0x1800332bf  pop     r12
0x1800332c1  pop     rdi
0x1800332c2  pop     rsi
0x1800332c3  pop     rbp
0x1800332c4  retn
0x1800332c6  lea     rsi, [rdi+8]
0x1800332ca  test    r14b, 2
0x1800332ce  jnz     short loc_1800332D4
0x1800332d0  cmp     [rsi], ebx
0x1800332d2  jz      short loc_1800332A9
0x1800332d4  test    r14b, 8
0x1800332d8  jnz     short loc_1800332DF
0x1800332da  cmp     dword ptr [rsi], 1
0x1800332dd  jz      short loc_1800332A9
0x1800332df  mov     rdi, [rdi+10h]
0x1800332e3  cmp     [rdi], rbx
0x1800332e6  jz      loc_1800331B6
0x1800332ec  mov     r14, [rsp+68h+var_48]
0x1800332f1  mov     rcx, [r15]
0x1800332f4  test    rcx, rcx
0x1800332f7  jz      short loc_18003330A
0x1800332f9  mov     rax, [r14]
0x1800332fc  mov     rax, [rax+28h]
0x180033300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033305  mov     r9, rax
0x180033308  jmp     short loc_18003330D
0x18003330a  xor     r9d, r9d
0x18003330d  cmp     [rsi], ebx
0x18003330f  mov     rdx, rdi
0x180033312  cmovz   r9, rbp
0x180033316  test    byte ptr [rdx+8], 4
0x18003331a  jnz     short loc_18003337E
0x18003331c  mov     eax, [rdx+18h]
0x18003331f  test    eax, eax
0x180033321  jnz     short loc_180033333
0x180033323  mov     rcx, [rdx+10h]
0x180033327  xor     r8d, r8d
0x18003332a  mov     eax, [rdx+0Ch]
0x18003332d  cmp     [r9+rcx], eax
0x180033331  jmp     short loc_180033375
0x180033333  cmp     eax, 1
0x180033336  jnz     short loc_18003334A
0x180033338  mov     rcx, [rdx+10h]
0x18003333c  xor     r8d, r8d
0x18003333f  movzx   eax, word ptr [rdx+0Ch]
0x180033343  cmp     [r9+rcx], ax
0x180033348  jmp     short loc_180033375
0x18003334a  cmp     eax, 2
0x18003334d  jnz     short loc_180033362
0x18003334f  mov     rax, [rdx+10h]
0x180033353  xor     r8d, r8d
0x180033356  mov     ecx, [r9+rax]
0x18003335a  and     ecx, [rdx+0Ch]
0x18003335d  cmp     ecx, [rdx+0Ch]
0x180033360  jmp     short loc_180033375
0x180033362  cmp     eax, 3
0x180033365  jnz     short loc_18003338E
0x180033367  mov     rax, [rdx+10h]
0x18003336b  mov     r8d, ebx
0x18003336e  mov     ecx, [r9+rax]
0x180033372  test    [rdx+0Ch], ecx
0x180033375  setz    r8b
0x180033379  test    r8d, r8d
0x18003337c  jz      short loc_18003338E
0x18003337e  test    byte ptr [rdx+8], 2
0x180033382  jz      short loc_1800333A6
0x180033384  add     rdx, 20h ; ' '
0x180033388  jmp     short loc_180033316
0x18003338a  add     rdi, 20h ; ' '
0x18003338e  test    byte ptr [rdi+8], 2
0x180033392  jnz     short loc_18003338A
0x180033394  add     rdi, 20h ; ' '
0x180033398  cmp     [rdi], rbx
0x18003339b  jnz     loc_1800332F1
0x1800333a1  jmp     loc_1800331B6
0x1800333a6  mov     rcx, [rsp+68h+arg_18]
0x1800333ae  mov     rax, [rdi]
0x1800333b1  mov     [rcx], rax
0x1800333b4  jmp     loc_1800332AE
```
