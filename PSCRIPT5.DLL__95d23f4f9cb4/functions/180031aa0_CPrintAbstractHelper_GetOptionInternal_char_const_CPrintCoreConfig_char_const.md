# CPrintAbstractHelper::GetOptionInternal(char const *,CPrintCoreConfig *,char const * *)

- ea: `0x180031aa0`
- end: `0x180031d58`
- name: `?GetOptionInternal@CPrintAbstractHelper@@MEAAJPEBDPEAVCPrintCoreConfig@@PEAPEBD@Z`
- size: `696`
- prototype: `int(CPrintAbstractHelper *__hidden this, const char *, struct CPrintCoreConfig *, const char **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002c8d0`

## callees

- `0x18002fac0`
- `0x180030fb8`
- `0x180031aa0`
- `0x180032cb0`
- `0x180032d10`
- `0x18005d010`

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
  __int64 KeywordMatchFeature; // rsi
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
  KeywordMatchFeature = PInternalGetKeywordMatchFeature(UIInfo, a2, 0, &v37);
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
  if ( v18 >= *(_DWORD *)(KeywordMatchFeature + 52) )
    v19 = 0;
  else
    v19 = (_DWORD *)(*((_QWORD *)v10 + 41)
                   + *(_DWORD *)(KeywordMatchFeature + 56)
                   + *(_DWORD *)(KeywordMatchFeature + 48) * v18);
  if ( !(unsigned int)BIsParserFeatureReadable(a3, (struct _FEATURE *)KeywordMatchFeature) )
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
0x180031aa0  mov     [rsp+arg_8], rbx
0x180031aa5  mov     [rsp+arg_18], r9
0x180031aaa  push    rbp
0x180031aab  push    rsi
0x180031aac  push    rdi
0x180031aad  push    r12
0x180031aaf  push    r13
0x180031ab1  push    r14
0x180031ab3  push    r15
0x180031ab5  sub     rsp, 30h
0x180031ab9  mov     rax, [rcx]
0x180031abc  mov     r12, rdx
0x180031abf  mov     rdx, r8
0x180031ac2  mov     [rsp+68h+arg_0], 0
0x180031aca  mov     r15, r8
0x180031acd  mov     rax, [rax+48h]
0x180031ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ad6  mov     rcx, r15; this
0x180031ad9  mov     rdi, rax
0x180031adc  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x180031ae1  mov     rcx, r15; this
0x180031ae4  mov     r14d, eax
0x180031ae7  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x180031aec  mov     r13, rax
0x180031aef  test    rax, rax
0x180031af2  jnz     short loc_180031AFE
0x180031af4  mov     eax, 8000FFFFh
0x180031af9  jmp     loc_180031C50
0x180031afe  lea     r9, [rsp+68h+arg_0]
0x180031b03  xor     r8d, r8d
0x180031b06  mov     rdx, r12
0x180031b09  mov     rcx, r13
0x180031b0c  call    PInternalGetKeywordMatchFeature
0x180031b11  mov     rsi, rax
0x180031b14  test    r14b, 0Ah
0x180031b18  jz      loc_180031C49
0x180031b1e  cmp     qword ptr [r15+10h], 0
0x180031b23  lea     rcx, [r15+8]
0x180031b27  mov     [rsp+68h+var_48], rcx
0x180031b2c  jz      short loc_180031B34
0x180031b2e  lea     rbp, [r15+1Ch]
0x180031b32  jmp     short loc_180031B51
0x180031b34  mov     rax, [rcx]
0x180031b37  xor     edx, edx
0x180031b39  mov     rcx, [r15]
0x180031b3c  mov     rax, [rax+8]
0x180031b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031b45  lea     rcx, [r15+8]
0x180031b49  mov     rbp, rax
0x180031b4c  mov     [rsp+68h+var_48], rcx
0x180031b51  test    rbp, rbp
0x180031b54  jnz     short loc_180031B60
0x180031b56  mov     ebx, 8000FFFFh
0x180031b5b  jmp     loc_180031C4E
0x180031b60  xor     ebx, ebx
0x180031b62  test    rsi, rsi
0x180031b65  jz      loc_180031BF1
0x180031b6b  mov     r14d, [rsp+68h+arg_0]
0x180031b70  movzx   eax, byte ptr [rbp+r14*2+0]
0x180031b76  cmp     eax, [rsi+34h]
0x180031b79  jnb     short loc_180031B8D
0x180031b7b  imul    eax, [rsi+30h]
0x180031b7f  add     eax, [rsi+38h]
0x180031b82  mov     edi, eax
0x180031b84  add     rdi, [r13+148h]
0x180031b8b  jmp     short loc_180031B8F
0x180031b8d  xor     edi, edi
0x180031b8f  mov     rdx, rsi; struct _FEATURE *
0x180031b92  mov     rcx, r15; this
0x180031b95  call    ?BIsParserFeatureReadable@@YAHPEAVCPrintCoreConfig@@PEAU_FEATURE@@@Z; BIsParserFeatureReadable(CPrintCoreConfig *,_FEATURE *)
0x180031b9a  test    eax, eax
0x180031b9c  jz      loc_180031C49
0x180031ba2  test    rdi, rdi
0x180031ba5  jz      short loc_180031BDA
0x180031ba7  cmp     [rdi], ebx
0x180031ba9  jz      short loc_180031BCA
0x180031bab  mov     ecx, [rdi]
0x180031bad  mov     rdx, [r13+140h]
0x180031bb4  add     rdx, rcx
0x180031bb7  mov     rcx, [rsp+68h+arg_18]
0x180031bbf  mov     [rcx], rdx
0x180031bc2  jnz     loc_180031C4E
0x180031bc8  jmp     short loc_180031B56
0x180031bca  mov     rcx, [rsp+68h+arg_18]
0x180031bd2  mov     [rcx], rbx
0x180031bd5  jmp     loc_180031B56
0x180031bda  cmp     byte ptr [rbp+r14*2+0], 0FFh
0x180031be0  mov     ebx, 80004005h
0x180031be5  mov     eax, 8000FFFFh
0x180031bea  cmovz   eax, ebx
0x180031bed  mov     ebx, eax
0x180031bef  jmp     short loc_180031C4E
0x180031bf1  test    rdi, rdi
0x180031bf4  jz      short loc_180031C49
0x180031bf6  mov     rax, [r15+10h]
0x180031bfa  test    rax, rax
0x180031bfd  jnz     short loc_180031C13
0x180031bff  mov     rax, [rcx]
0x180031c02  mov     rcx, [r15]
0x180031c05  mov     rax, [rax+30h]
0x180031c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031c0e  test    rax, rax
0x180031c11  jz      short loc_180031C1C
0x180031c13  movzx   ebp, word ptr [rax+44h]
0x180031c17  add     rbp, rax
0x180031c1a  jmp     short loc_180031C41
0x180031c1c  xor     ebp, ebp
0x180031c1e  jmp     short loc_180031C41
0x180031c20  mov     r8, r12
0x180031c23  sub     r8, rax
0x180031c26  movzx   ecx, byte ptr [rax]
0x180031c29  movzx   edx, byte ptr [rax+r8]
0x180031c2e  sub     ecx, edx
0x180031c30  jnz     short loc_180031C39
0x180031c32  inc     rax
0x180031c35  test    edx, edx
0x180031c37  jnz     short loc_180031C26
0x180031c39  test    ecx, ecx
0x180031c3b  jz      short loc_180031C65
0x180031c3d  add     rdi, 18h
0x180031c41  mov     rax, [rdi]
0x180031c44  test    rax, rax
0x180031c47  jnz     short loc_180031C20
0x180031c49  mov     ebx, 80004005h
0x180031c4e  mov     eax, ebx
0x180031c50  mov     rbx, [rsp+68h+arg_8]
0x180031c55  add     rsp, 30h
0x180031c59  pop     r15
0x180031c5b  pop     r14
0x180031c5d  pop     r13
0x180031c5f  pop     r12
0x180031c61  pop     rdi
0x180031c62  pop     rsi
0x180031c63  pop     rbp
0x180031c64  retn
0x180031c65  lea     rsi, [rdi+8]
0x180031c69  test    r14b, 2
0x180031c6d  jnz     short loc_180031C73
0x180031c6f  cmp     [rsi], ebx
0x180031c71  jz      short loc_180031C49
0x180031c73  test    r14b, 8
0x180031c77  jnz     short loc_180031C7E
0x180031c79  cmp     dword ptr [rsi], 1
0x180031c7c  jz      short loc_180031C49
0x180031c7e  mov     rdi, [rdi+10h]
0x180031c82  cmp     [rdi], rbx
0x180031c85  jz      loc_180031B56
0x180031c8b  mov     r14, [rsp+68h+var_48]
0x180031c90  mov     rcx, [r15]
0x180031c93  test    rcx, rcx
0x180031c96  jz      short loc_180031CA9
0x180031c98  mov     rax, [r14]
0x180031c9b  mov     rax, [rax+28h]
0x180031c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031ca4  mov     r9, rax
0x180031ca7  jmp     short loc_180031CAC
0x180031ca9  xor     r9d, r9d
0x180031cac  cmp     [rsi], ebx
0x180031cae  mov     rdx, rdi
0x180031cb1  cmovz   r9, rbp
0x180031cb5  test    byte ptr [rdx+8], 4
0x180031cb9  jnz     short loc_180031D1D
0x180031cbb  mov     eax, [rdx+18h]
0x180031cbe  test    eax, eax
0x180031cc0  jnz     short loc_180031CD2
0x180031cc2  mov     rcx, [rdx+10h]
0x180031cc6  xor     r8d, r8d
0x180031cc9  mov     eax, [rdx+0Ch]
0x180031ccc  cmp     [r9+rcx], eax
0x180031cd0  jmp     short loc_180031D14
0x180031cd2  cmp     eax, 1
0x180031cd5  jnz     short loc_180031CE9
0x180031cd7  mov     rcx, [rdx+10h]
0x180031cdb  xor     r8d, r8d
0x180031cde  movzx   eax, word ptr [rdx+0Ch]
0x180031ce2  cmp     [r9+rcx], ax
0x180031ce7  jmp     short loc_180031D14
0x180031ce9  cmp     eax, 2
0x180031cec  jnz     short loc_180031D01
0x180031cee  mov     rax, [rdx+10h]
0x180031cf2  xor     r8d, r8d
0x180031cf5  mov     ecx, [r9+rax]
0x180031cf9  and     ecx, [rdx+0Ch]
0x180031cfc  cmp     ecx, [rdx+0Ch]
0x180031cff  jmp     short loc_180031D14
0x180031d01  cmp     eax, 3
0x180031d04  jnz     short loc_180031D2D
0x180031d06  mov     rax, [rdx+10h]
0x180031d0a  mov     r8d, ebx
0x180031d0d  mov     ecx, [r9+rax]
0x180031d11  test    [rdx+0Ch], ecx
0x180031d14  setz    r8b
0x180031d18  test    r8d, r8d
0x180031d1b  jz      short loc_180031D2D
0x180031d1d  test    byte ptr [rdx+8], 2
0x180031d21  jz      short loc_180031D45
0x180031d23  add     rdx, 20h ; ' '
0x180031d27  jmp     short loc_180031CB5
0x180031d29  add     rdi, 20h ; ' '
0x180031d2d  test    byte ptr [rdi+8], 2
0x180031d31  jnz     short loc_180031D29
0x180031d33  add     rdi, 20h ; ' '
0x180031d37  cmp     [rdi], rbx
0x180031d3a  jnz     loc_180031C90
0x180031d40  jmp     loc_180031B56
0x180031d45  mov     rcx, [rsp+68h+arg_18]
0x180031d4d  mov     rax, [rdi]
0x180031d50  mov     [rcx], rax
0x180031d53  jmp     loc_180031C4E
```
