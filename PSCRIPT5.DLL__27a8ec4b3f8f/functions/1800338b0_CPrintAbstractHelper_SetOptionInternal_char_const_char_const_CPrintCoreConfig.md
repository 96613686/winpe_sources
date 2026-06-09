# CPrintAbstractHelper::SetOptionInternal(char const *,char const *,CPrintCoreConfig *)

- ea: `0x1800338b0`
- end: `0x180033ba0`
- name: `?SetOptionInternal@CPrintAbstractHelper@@MEAAJPEBD0PEAVCPrintCoreConfig@@@Z`
- size: `752`
- prototype: `__int64 __fastcall(CPrintAbstractHelper *this, const char *, const char *, struct CPrintCoreConfig *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18002e640`

## callees

- `0x180031044`
- `0x1800310e4`
- `0x1800338b0`
- `0x180034320`
- `0x180034384`
- `0x18005f010`

## pseudocode

```c
__int64 __fastcall CPrintAbstractHelper::SetOptionInternal(
        CPrintAbstractHelper *this,
        const char *a2,
        const char *a3,
        struct CPrintCoreConfig *a4)
{
  struct _UIINFO *UIInfo; // rbp
  const char *v10; // rax
  unsigned int v11; // ebx
  int v12; // r8d
  int v13; // ecx
  _DWORD *v14; // rax
  unsigned int *KeywordMatchFeature; // rax
  unsigned int *v16; // rdi
  bool v17; // zf
  char *v18; // rax
  __int64 i; // r15
  const char *v20; // rcx
  const char *v21; // r8
  int v22; // edx
  int v23; // eax
  const char **j; // rdi
  const char *v25; // r8
  int v26; // edx
  int v27; // ecx
  const char *v28; // rax
  __int64 v29; // rax
  char *v30; // r14
  __int64 v31; // rbp
  __int64 v32; // rdx
  int v33; // eax
  int v34; // eax
  unsigned int v35; // [rsp+30h] [rbp-58h] BYREF
  _DWORD v36[21]; // [rsp+34h] [rbp-54h] BYREF

  v35 = 0;
  v36[0] = 0;
  UIInfo = CPrintCoreConfig::GetUIInfo(a4);
  if ( !UIInfo )
    return 2147549183LL;
  v10 = "%FormTrayCheck";
  v11 = 0;
  do
  {
    v12 = (unsigned __int8)v10[a2 - "%FormTrayCheck"];
    v13 = *(unsigned __int8 *)v10 - v12;
    if ( v13 )
      break;
    ++v10;
  }
  while ( v12 );
  if ( v13 )
  {
    KeywordMatchFeature = PInternalGetKeywordMatchFeature((__int64)UIInfo, a2, 0, &v35);
    v16 = KeywordMatchFeature;
    if ( !KeywordMatchFeature )
    {
      for ( i = (*(__int64 (__fastcall **)(CPrintAbstractHelper *, struct CPrintCoreConfig *))(*(_QWORD *)this + 72LL))(
                  this,
                  a4); i; i += 24 )
      {
        v20 = *(const char **)i;
        if ( !*(_QWORD *)i )
          break;
        v21 = (const char *)(a2 - v20);
        do
        {
          v22 = (unsigned __int8)v21[(_QWORD)v20];
          v23 = *(unsigned __int8 *)v20 - v22;
          if ( v23 )
            break;
          ++v20;
        }
        while ( v22 );
        if ( !v23 )
        {
          for ( j = *(const char ***)(i + 16); ; j += 4 )
          {
            v28 = *j;
            if ( !*j )
              break;
            v25 = (const char *)(a3 - v28);
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
              if ( !*(_DWORD *)(i + 8) && (CPrintCoreConfig::GetHelperSettingsFlags(a4) & 1) == 0
                || *(_DWORD *)(i + 8) == 1 && (CPrintCoreConfig::GetHelperSettingsFlags(a4) & 4) == 0 )
              {
                return (unsigned int)-2147467259;
              }
              v29 = *((_QWORD *)a4 + 2);
              v30 = (char *)a4 + 8;
              if ( v29 || (v29 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v30 + 48LL))(*(_QWORD *)a4)) != 0 )
                v31 = v29 + *(unsigned __int16 *)(v29 + 68);
              else
                v31 = 0;
              if ( *(_QWORD *)a4 )
                v32 = (*(__int64 (**)(void))(*(_QWORD *)v30 + 40LL))();
              else
                v32 = 0;
              if ( !*(_DWORD *)(i + 8) )
                v32 = v31;
              do
              {
                v33 = *((_DWORD *)j + 6);
                if ( v33 )
                {
                  switch ( v33 )
                  {
                    case 1:
                      *(_WORD *)&j[2][v32] = *((_WORD *)j + 6);
                      break;
                    case 2:
                      *(_DWORD *)&j[2][v32] |= *((_DWORD *)j + 3);
                      break;
                    case 3:
                      *(_DWORD *)&j[2][v32] &= ~*((_DWORD *)j + 3);
                      break;
                  }
                }
                else
                {
                  *(_DWORD *)&j[2][v32] = *((_DWORD *)j + 3);
                }
                v34 = *((_DWORD *)j + 2);
                j += 4;
              }
              while ( (v34 & 2) != 0 );
              return v11;
            }
            while ( ((_BYTE)j[1] & 2) != 0 )
              j += 4;
          }
        }
      }
      return (unsigned int)-2147467259;
    }
    if ( KeywordMatchFeature[11] < 2 )
    {
      v17 = (CPrintCoreConfig::GetHelperSettingsFlags(a4) & 1) == 0;
    }
    else
    {
      if ( (CPrintCoreConfig::GetHelperSettingsFlags(a4) & 4) != 0 )
        goto LABEL_16;
      v17 = v16[11] == 2;
    }
    if ( v17 )
      return (unsigned int)-2147467259;
LABEL_16:
    if ( PInternalGetKeywordMatchOption((__int64)UIInfo, v16, a3, 0, v36) )
    {
      if ( *((_QWORD *)a4 + 2) )
        v18 = (char *)a4 + 28;
      else
        v18 = (char *)(*(__int64 (__fastcall **)(_QWORD, _QWORD))(*((_QWORD *)a4 + 1) + 8LL))(*(_QWORD *)a4, 0);
      if ( v18 )
        v18[2 * v35] = v36[0];
      else
        v11 = -2147467259;
      if ( v16[7] == 1 )
        (*(void (__fastcall **)(_QWORD))(*((_QWORD *)this + 134) + 88LL))(*(_QWORD *)a4);
      return v11;
    }
    return (unsigned int)-2147467259;
  }
  if ( !strcmp("Disabled", a3) )
  {
    v14 = (_DWORD *)(*(__int64 (__fastcall **)(_QWORD))(*((_QWORD *)a4 + 1) + 64LL))(*(_QWORD *)a4);
    if ( v14 )
      *v14 |= 0x200u;
    return v11;
  }
  return (unsigned int)-2147467259;
}

```

## disassembly

```asm
0x1800338b0  push    rbx
0x1800338b2  push    rbp
0x1800338b3  push    rsi
0x1800338b4  push    rdi
0x1800338b5  push    r12
0x1800338b7  push    r13
0x1800338b9  push    r14
0x1800338bb  push    r15
0x1800338bd  sub     rsp, 48h
0x1800338c1  mov     r14, rcx
0x1800338c4  xor     r15d, r15d
0x1800338c7  mov     rcx, r9; this
0x1800338ca  mov     [rsp+88h+var_58], r15d
0x1800338cf  mov     [rsp+88h+var_54], r15d
0x1800338d4  mov     rsi, r9
0x1800338d7  mov     r12, r8
0x1800338da  mov     r13, rdx
0x1800338dd  call    ?GetUIInfo@CPrintCoreConfig@@QEBAPEAU_UIINFO@@XZ; CPrintCoreConfig::GetUIInfo(void)
0x1800338e2  mov     rbp, rax
0x1800338e5  test    rax, rax
0x1800338e8  jnz     short loc_1800338F4
0x1800338ea  mov     eax, 8000FFFFh
0x1800338ef  jmp     loc_180033B11
0x1800338f4  lea     rax, aFormtraycheck; "%FormTrayCheck"
0x1800338fb  mov     rdx, r13
0x1800338fe  sub     rdx, rax
0x180033901  mov     ebx, r15d
0x180033904  movzx   ecx, byte ptr [rax]
0x180033907  movzx   r8d, byte ptr [rax+rdx]
0x18003390c  sub     ecx, r8d
0x18003390f  jnz     short loc_180033919
0x180033911  inc     rax
0x180033914  test    r8d, r8d
0x180033917  jnz     short loc_180033904
0x180033919  test    ecx, ecx
0x18003391b  jnz     short loc_180033964
0x18003391d  lea     rax, aDisabled; "Disabled"
0x180033924  sub     r12, rax
0x180033927  movzx   ecx, byte ptr [rax]
0x18003392a  movzx   edx, byte ptr [rax+r12]
0x18003392f  sub     ecx, edx
0x180033931  jnz     short loc_18003393A
0x180033933  inc     rax
0x180033936  test    edx, edx
0x180033938  jnz     short loc_180033927
0x18003393a  test    ecx, ecx
0x18003393c  jnz     loc_180033B0A
0x180033942  mov     rax, [rsi+8]
0x180033946  mov     rcx, [rsi]
0x180033949  mov     rax, [rax+40h]
0x18003394d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033952  test    rax, rax
0x180033955  jz      loc_180033B0F
0x18003395b  bts     dword ptr [rax], 9
0x18003395f  jmp     loc_180033B0F
0x180033964  lea     r9, [rsp+88h+var_58]
0x180033969  xor     r8d, r8d
0x18003396c  mov     rdx, r13
0x18003396f  mov     rcx, rbp
0x180033972  call    PInternalGetKeywordMatchFeature
0x180033977  mov     rdi, rax
0x18003397a  test    rax, rax
0x18003397d  jz      loc_180033A23
0x180033983  cmp     dword ptr [rax+2Ch], 2
0x180033987  mov     rcx, rsi; this
0x18003398a  jb      short loc_18003399B
0x18003398c  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x180033991  test    al, 4
0x180033993  jnz     short loc_1800339A8
0x180033995  cmp     dword ptr [rdi+2Ch], 2
0x180033999  jmp     short loc_1800339A2
0x18003399b  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x1800339a0  test    al, 1
0x1800339a2  jz      loc_180033B0A
0x1800339a8  lea     rax, [rsp+88h+var_54]
0x1800339ad  xor     r9d, r9d
0x1800339b0  mov     r8, r12
0x1800339b3  mov     [rsp+88h+var_68], rax
0x1800339b8  mov     rdx, rdi
0x1800339bb  mov     rcx, rbp
0x1800339be  call    PInternalGetKeywordMatchOption
0x1800339c3  test    rax, rax
0x1800339c6  jz      loc_180033B0A
0x1800339cc  cmp     [rsi+10h], r15
0x1800339d0  jz      short loc_1800339D8
0x1800339d2  lea     rax, [rsi+1Ch]
0x1800339d6  jmp     short loc_1800339EA
0x1800339d8  mov     rax, [rsi+8]
0x1800339dc  xor     edx, edx
0x1800339de  mov     rcx, [rsi]
0x1800339e1  mov     rax, [rax+8]
0x1800339e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800339ea  test    rax, rax
0x1800339ed  jz      short loc_1800339FC
0x1800339ef  mov     edx, [rsp+88h+var_58]
0x1800339f3  mov     cl, byte ptr [rsp+88h+var_54]
0x1800339f7  mov     [rax+rdx*2], cl
0x1800339fa  jmp     short loc_180033A01
0x1800339fc  mov     ebx, 80004005h
0x180033a01  cmp     dword ptr [rdi+1Ch], 1
0x180033a05  jnz     loc_180033B0F
0x180033a0b  mov     rax, [r14+430h]
0x180033a12  mov     rcx, [rsi]
0x180033a15  mov     rax, [rax+58h]
0x180033a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a1e  jmp     loc_180033B0F
0x180033a23  mov     rax, [r14]
0x180033a26  mov     rdx, rsi
0x180033a29  mov     rcx, r14
0x180033a2c  mov     ebp, r15d
0x180033a2f  mov     rax, [rax+48h]
0x180033a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033a38  mov     r15, rax
0x180033a3b  test    rax, rax
0x180033a3e  jz      loc_180033B0A
0x180033a44  mov     rcx, [r15]
0x180033a47  test    rcx, rcx
0x180033a4a  jz      loc_180033B0A
0x180033a50  mov     r8, r13
0x180033a53  sub     r8, rcx
0x180033a56  movzx   eax, byte ptr [rcx]
0x180033a59  movzx   edx, byte ptr [rcx+r8]
0x180033a5e  sub     eax, edx
0x180033a60  jnz     short loc_180033A69
0x180033a62  inc     rcx
0x180033a65  test    edx, edx
0x180033a67  jnz     short loc_180033A56
0x180033a69  test    eax, eax
0x180033a6b  jnz     loc_180033B00
0x180033a71  mov     rdi, [r15+10h]
0x180033a75  lea     ebp, [rax+1]
0x180033a78  jmp     short loc_180033AF4
0x180033a7a  mov     r8, r12
0x180033a7d  sub     r8, rax
0x180033a80  movzx   ecx, byte ptr [rax]
0x180033a83  movzx   edx, byte ptr [rax+r8]
0x180033a88  sub     ecx, edx
0x180033a8a  jnz     short loc_180033A93
0x180033a8c  inc     rax
0x180033a8f  test    edx, edx
0x180033a91  jnz     short loc_180033A80
0x180033a93  test    ecx, ecx
0x180033a95  jnz     short loc_180033AEA
0x180033a97  cmp     [r15+8], ebx
0x180033a9b  jnz     short loc_180033AAA
0x180033a9d  mov     rcx, rsi; this
0x180033aa0  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x180033aa5  test    bpl, al
0x180033aa8  jz      short loc_180033B0A
0x180033aaa  cmp     [r15+8], ebp
0x180033aae  jnz     short loc_180033ABC
0x180033ab0  mov     rcx, rsi; this
0x180033ab3  call    ?GetHelperSettingsFlags@CPrintCoreConfig@@QEBAKXZ; CPrintCoreConfig::GetHelperSettingsFlags(void)
0x180033ab8  test    al, 4
0x180033aba  jz      short loc_180033B0A
0x180033abc  mov     rax, [rsi+10h]
0x180033ac0  lea     r14, [rsi+8]
0x180033ac4  test    rax, rax
0x180033ac7  jnz     short loc_180033ADD
0x180033ac9  mov     rax, [r14]
0x180033acc  mov     rcx, [rsi]
0x180033acf  mov     rax, [rax+30h]
0x180033ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033ad8  test    rax, rax
0x180033adb  jz      short loc_180033B23
0x180033add  movzx   ebp, word ptr [rax+44h]
0x180033ae1  add     rbp, rax
0x180033ae4  jmp     short loc_180033B25
0x180033ae6  add     rdi, 20h ; ' '
0x180033aea  test    byte ptr [rdi+8], 2
0x180033aee  jnz     short loc_180033AE6
0x180033af0  add     rdi, 20h ; ' '
0x180033af4  mov     rax, [rdi]
0x180033af7  test    rax, rax
0x180033afa  jnz     loc_180033A7A
0x180033b00  add     r15, 18h
0x180033b04  jnz     loc_180033A44
0x180033b0a  mov     ebx, 80004005h
0x180033b0f  mov     eax, ebx
0x180033b11  add     rsp, 48h
0x180033b15  pop     r15
0x180033b17  pop     r14
0x180033b19  pop     r13
0x180033b1b  pop     r12
0x180033b1d  pop     rdi
0x180033b1e  pop     rsi
0x180033b1f  pop     rbp
0x180033b20  pop     rbx
0x180033b21  retn
0x180033b23  xor     ebp, ebp
0x180033b25  mov     rcx, [rsi]
0x180033b28  test    rcx, rcx
0x180033b2b  jz      short loc_180033B3E
0x180033b2d  mov     rax, [r14]
0x180033b30  mov     rax, [rax+28h]
0x180033b34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180033b39  mov     rdx, rax
0x180033b3c  jmp     short loc_180033B40
0x180033b3e  xor     edx, edx
0x180033b40  cmp     [r15+8], ebx
0x180033b44  cmovz   rdx, rbp
0x180033b48  mov     eax, [rdi+18h]
0x180033b4b  test    eax, eax
0x180033b4d  jnz     short loc_180033B5B
0x180033b4f  mov     rcx, [rdi+10h]
0x180033b53  mov     eax, [rdi+0Ch]
0x180033b56  mov     [rdx+rcx], eax
0x180033b59  jmp     short loc_180033B90
0x180033b5b  cmp     eax, 1
0x180033b5e  jnz     short loc_180033B6E
0x180033b60  mov     rcx, [rdi+10h]
0x180033b64  movzx   eax, word ptr [rdi+0Ch]
0x180033b68  mov     [rdx+rcx], ax
0x180033b6c  jmp     short loc_180033B90
0x180033b6e  cmp     eax, 2
0x180033b71  jnz     short loc_180033B7F
0x180033b73  mov     rcx, [rdi+10h]
0x180033b77  mov     eax, [rdi+0Ch]
0x180033b7a  or      [rcx+rdx], eax
0x180033b7d  jmp     short loc_180033B90
0x180033b7f  cmp     eax, 3
0x180033b82  jnz     short loc_180033B90
0x180033b84  mov     eax, [rdi+0Ch]
0x180033b87  mov     rcx, [rdi+10h]
0x180033b8b  not     eax
0x180033b8d  and     [rcx+rdx], eax
0x180033b90  mov     eax, [rdi+8]
0x180033b93  add     rdi, 20h ; ' '
0x180033b97  test    al, 2
0x180033b99  jnz     short loc_180033B48
0x180033b9b  jmp     loc_180033B0F
```
