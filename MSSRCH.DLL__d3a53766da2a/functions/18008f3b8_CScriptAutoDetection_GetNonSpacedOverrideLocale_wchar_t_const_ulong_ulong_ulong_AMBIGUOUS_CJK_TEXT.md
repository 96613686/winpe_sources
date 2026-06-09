# CScriptAutoDetection::GetNonSpacedOverrideLocale(wchar_t const *,ulong,ulong,ulong *,AMBIGUOUS_CJK_TEXT *)

- ea: `0x18008f3b8`
- end: `0x18008f6b6`
- name: `?GetNonSpacedOverrideLocale@CScriptAutoDetection@@QEAAJPEB_WKKPEAKPEAW4AMBIGUOUS_CJK_TEXT@@@Z`
- size: `766`
- prototype: `__int64 __usercall@<rax>(PMAPPING_SERVICE_INFO *prgServices@<rcx>, const wchar_t *@<rdx>, unsigned int@<r8d>, unsigned int@<r9d>, unsigned int *, enum AMBIGUOUS_CJK_TEXT *)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180062b80`
- `0x1801d195c`

## callees

- `0x18008f3b8`
- `0x18008f6bc`
- `0x18008f974`
- `0x18012540e`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x18008f63d`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLangID` at `0x18008f63d`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLangID` at `0x18008f653`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLangID` at `0x18008f653`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x18008f667`
- `api-ms-win-core-localization-obsolete-l1-2-0!GetUserDefaultUILanguage` at `0x18008f667`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008f40d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18008f40d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f5d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008f5d2`

## pseudocode

```c
__int64 __fastcall CScriptAutoDetection::GetNonSpacedOverrideLocale(
        PMAPPING_SERVICE_INFO *prgServices,
        const wchar_t *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int *a5,
        enum AMBIGUOUS_CJK_TEXT *a6)
{
  __int64 v6; // r14
  unsigned __int64 v10; // rdi
  unsigned int HasSpecialScript; // ebx
  WCHAR *v13; // rsi
  const size_t *v14; // r8
  unsigned __int64 v15; // rdx
  WCHAR *v16; // rax
  __int64 v17; // r10
  __int64 v18; // rcx
  WCHAR *v19; // rcx
  __int64 v20; // r9
  unsigned int *v21; // rdi
  enum AMBIGUOUS_CJK_TEXT *v22; // r14
  char v23; // r10
  unsigned __int64 v24; // rcx
  unsigned __int64 v25; // rdx
  unsigned int i; // eax
  char v27; // r8
  WCHAR v28; // r9
  unsigned int v29; // ecx
  unsigned int v30; // eax
  __int64 v31; // rdi
  bool v32; // cf
  LANGID UserDefaultLangID; // ax
  unsigned int v34; // [rsp+30h] [rbp-58h] BYREF
  unsigned int v35[20]; // [rsp+38h] [rbp-50h] BYREF
  unsigned int v36; // [rsp+A0h] [rbp+18h] BYREF

  v6 = a3;
  v10 = a3 + 1LL;
  if ( v10 >= a3 )
  {
    *(_QWORD *)v35 = 0;
    if ( is_mul_ok(v10, 2u) )
    {
      v13 = (WCHAR *)CoTaskMemAlloc(2 * v10);
      HasSpecialScript = v13 == 0 ? 0x8007000E : 0;
      if ( !v13 )
        return HasSpecialScript;
      if ( v10 > 0x7FFFFFFF || (unsigned int)v6 >= 0x7FFFFFFF )
      {
        *v13 = 0;
      }
      else
      {
        v14 = &cchOriginalDestLength;
        v15 = v10;
        v16 = v13;
        v17 = 0;
        v18 = v6 & -(__int64)(a2 != 0);
        if ( a2 )
          v14 = (const size_t *)a2;
        do
        {
          if ( !v18 )
            break;
          if ( !*(_WORD *)v14 )
            break;
          *v16 = *(_WORD *)v14;
          v14 = (const size_t *)((char *)v14 + 2);
          ++v16;
          --v18;
          ++v17;
          --v15;
        }
        while ( v15 );
        v19 = v16 - 1;
        v20 = v17 - 1;
        if ( v15 )
        {
          v19 = v16;
          v20 = v17;
        }
        *v19 = 0;
        if ( v15 )
        {
          v32 = v10 == v20;
          v31 = v10 - v20;
          if ( !v32 && v31 != 1 && (unsigned __int64)(2 * v31) > 2 )
            memset_0(&v13[v20 + 1], 0, 2 * v31 - 2);
        }
      }
      v21 = a5;
      v22 = a6;
      HasSpecialScript = 0;
      v23 = 1;
      *a5 = a4;
      *(_DWORD *)v22 = 0;
      v24 = -1;
      do
        ++v24;
      while ( v13[v24] );
      v25 = 0;
      do
      {
        if ( v25 >= v24 )
          goto LABEL_37;
        for ( i = 0; ; ++i )
        {
          v27 = 0;
          if ( i >= 0xA )
            break;
          v28 = v13[v25];
          if ( *((_WORD *)qword_180267040 + 2 * (int)i) <= v28 && v28 <= *((_WORD *)qword_180267040 + 2 * (int)i + 1) )
          {
            v27 = 1;
            break;
          }
        }
        ++v25;
        v23 &= -(v27 != 0);
      }
      while ( v23 );
      v34 = 0;
      v36 = 0;
      v35[0] = 0;
      HasSpecialScript = CScriptAutoDetection::HasSpecialScript(
                           prgServices,
                           v13,
                           (enum SPECIAL_SCRIPTS_FOUND_FLAGS *)&v34,
                           &v36,
                           v35);
      if ( (HasSpecialScript & 0x80000000) != 0 )
      {
        if ( HasSpecialScript == -2147023611 )
          HasSpecialScript = 0;
        goto LABEL_37;
      }
      v29 = v36;
      if ( v36 )
        *v21 = v36;
      v30 = v34;
      if ( (v34 & 1) != 0 )
      {
        *v21 = 1041;
      }
      else
      {
        if ( (v34 & 2) == 0 )
        {
          if ( !v29 && v35[0] )
          {
            *v21 = v35[0];
          }
          else
          {
            if ( (v34 & 4) == 0 )
              goto LABEL_37;
            if ( IsLocaleCJK(a4) )
            {
              *v21 = a4;
LABEL_36:
              *(_DWORD *)v22 = 2;
              goto LABEL_37;
            }
            UserDefaultLangID = GetUserDefaultLangID();
            if ( UserDefaultLangID == 4
              || (unsigned __int16)(UserDefaultLangID - 17) <= 1u
              || (UserDefaultLangID = GetUserDefaultUILanguage(), UserDefaultLangID == 4)
              || (unsigned __int16)(UserDefaultLangID - 17) <= 1u
              || (UserDefaultLangID = GetSystemDefaultLangID(), UserDefaultLangID == 4)
              || (unsigned __int16)(UserDefaultLangID - 17) <= 1u )
            {
              *v21 = UserDefaultLangID;
              goto LABEL_36;
            }
            *v21 = 1041;
            *(_DWORD *)v22 = 3;
          }
LABEL_37:
          CoTaskMemFree(v13);
          return HasSpecialScript;
        }
        *v21 = 1042;
      }
      *(_DWORD *)v22 = (v30 >> 2) & 1;
      goto LABEL_37;
    }
  }
  return (unsigned int)-2147024362;
}

```

## disassembly

```asm
0x18008f3b8  push    rbx
0x18008f3ba  push    rbp
0x18008f3bb  push    rsi
0x18008f3bc  push    rdi
0x18008f3bd  push    r12
0x18008f3bf  push    r13
0x18008f3c1  push    r14
0x18008f3c3  push    r15
0x18008f3c5  sub     rsp, 48h
0x18008f3c9  mov     r14d, r8d
0x18008f3cc  mov     r12d, r9d
0x18008f3cf  mov     r15, rdx
0x18008f3d2  mov     r13, rcx
0x18008f3d5  lea     rdi, [r14+1]
0x18008f3d9  cmp     rdi, r14
0x18008f3dc  jb      short loc_18008F3F2
0x18008f3de  xor     r8d, r8d
0x18008f3e1  mov     qword ptr [rsp+88h+var_50], r8
0x18008f3e6  lea     eax, [r8+2]
0x18008f3ea  mul     rdi
0x18008f3ed  test    rdx, rdx
0x18008f3f0  jz      short loc_18008F40A
0x18008f3f2  mov     ebx, 80070216h
0x18008f3f7  mov     eax, ebx
0x18008f3f9  add     rsp, 48h
0x18008f3fd  pop     r15
0x18008f3ff  pop     r14
0x18008f401  pop     r13
0x18008f403  pop     r12
0x18008f405  pop     rdi
0x18008f406  pop     rsi
0x18008f407  pop     rbp
0x18008f408  pop     rbx
0x18008f409  retn
0x18008f40a  mov     rcx, rax; cb
0x18008f40d  call    cs:__imp_CoTaskMemAlloc
0x18008f413  mov     rsi, rax
0x18008f416  neg     rax
0x18008f419  sbb     ebx, ebx
0x18008f41b  xor     r11d, r11d
0x18008f41e  not     ebx
0x18008f420  and     ebx, 8007000Eh
0x18008f426  test    rsi, rsi
0x18008f429  jz      short loc_18008F3F7
0x18008f42b  mov     eax, 7FFFFFFFh
0x18008f430  cmp     rdi, rax
0x18008f433  ja      loc_18008F67D
0x18008f439  cmp     r14d, eax
0x18008f43c  jnb     loc_18008F67D
0x18008f442  mov     rax, r15
0x18008f445  lea     r8, cchOriginalDestLength
0x18008f44c  neg     rax
0x18008f44f  mov     rdx, rdi
0x18008f452  mov     rax, rsi
0x18008f455  mov     r10d, r11d
0x18008f458  sbb     rcx, rcx
0x18008f45b  and     rcx, r14
0x18008f45e  test    r15, r15
0x18008f461  cmovnz  r8, r15
0x18008f465  test    rcx, rcx
0x18008f468  jz      short loc_18008F48C
0x18008f46a  movzx   r9d, word ptr [r8]
0x18008f46e  test    r9w, r9w
0x18008f472  jz      short loc_18008F48C
0x18008f474  mov     [rax], r9w
0x18008f478  add     r8, 2
0x18008f47c  add     rax, 2
0x18008f480  dec     rcx
0x18008f483  inc     r10
0x18008f486  sub     rdx, 1
0x18008f48a  jnz     short loc_18008F465
0x18008f48c  test    rdx, rdx
0x18008f48f  lea     rcx, [rax-2]
0x18008f493  lea     r9, [r10-1]
0x18008f497  cmovnz  rcx, rax
0x18008f49b  cmovnz  r9, r10
0x18008f49f  mov     [rcx], r11w
0x18008f4a3  jnz     loc_18008F5EC
0x18008f4a9  mov     rdi, [rsp+88h+arg_20]
0x18008f4b1  mov     ebp, 1
0x18008f4b6  mov     r14, [rsp+88h+arg_28]
0x18008f4be  mov     ebx, r11d
0x18008f4c1  mov     r10b, bpl
0x18008f4c4  mov     [rdi], r12d
0x18008f4c7  mov     [r14], r11d
0x18008f4ca  test    rsi, rsi
0x18008f4cd  jz      loc_18008F5E4
0x18008f4d3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18008f4d7  inc     rcx
0x18008f4da  cmp     [rsi+rcx*2], r11w
0x18008f4df  jnz     short loc_18008F4D7
0x18008f4e1  mov     rdx, r11
0x18008f4e4  lea     r15, qword_180267040
0x18008f4eb  cmp     rdx, rcx
0x18008f4ee  jnb     loc_18008F5CF
0x18008f4f4  mov     eax, r11d
0x18008f4f7  mov     r8b, r11b
0x18008f4fa  cmp     eax, 0Ah
0x18008f4fd  jnb     short loc_18008F521
0x18008f4ff  movzx   r9d, word ptr [rsi+rdx*2]
0x18008f504  movsxd  r8, eax
0x18008f507  cmp     [r15+r8*4], r9w
0x18008f50c  ja      loc_18008F5DD
0x18008f512  cmp     r9w, [r15+r8*4+2]
0x18008f518  ja      loc_18008F5DD
0x18008f51e  mov     r8b, bpl
0x18008f521  neg     r8b
0x18008f524  sbb     al, al
0x18008f526  add     rdx, rbp
0x18008f529  and     al, r10b
0x18008f52c  mov     r10b, al
0x18008f52f  test    al, al
0x18008f531  jnz     short loc_18008F4EB
0x18008f533  lea     rax, [rsp+88h+var_50]
0x18008f538  mov     [rsp+88h+var_58], r11d
0x18008f53d  lea     r9, [rsp+88h+arg_10]; unsigned int *
0x18008f545  mov     [rsp+88h+var_68], rax; unsigned int *
0x18008f54a  lea     r8, [rsp+88h+var_58]; enum SPECIAL_SCRIPTS_FOUND_FLAGS *
0x18008f54f  mov     [rsp+88h+arg_10], r11d
0x18008f557  mov     rdx, rsi; pszText
0x18008f55a  mov     [rsp+88h+var_50], r11d
0x18008f55f  mov     rcx, r13; prgServices
0x18008f562  call    ?HasSpecialScript@CScriptAutoDetection@@QEAAJPEB_WPEAW4SPECIAL_SCRIPTS_FOUND_FLAGS@@PEAK2@Z; CScriptAutoDetection::HasSpecialScript(wchar_t const *,SPECIAL_SCRIPTS_FOUND_FLAGS *,ulong *,ulong *)
0x18008f567  xor     r8d, r8d
0x18008f56a  mov     ebx, eax
0x18008f56c  test    eax, eax
0x18008f56e  js      loc_18008F631
0x18008f574  mov     ecx, [rsp+88h+arg_10]
0x18008f57b  test    ecx, ecx
0x18008f57d  jnz     loc_18008F686
0x18008f583  mov     eax, [rsp+88h+var_58]
0x18008f587  test    bpl, al
0x18008f58a  jnz     loc_18008F621
0x18008f590  mov     r15d, 2
0x18008f596  test    r15b, al
0x18008f599  jnz     loc_18008F68D
0x18008f59f  test    ecx, ecx
0x18008f5a1  jnz     short loc_18008F5AF
0x18008f5a3  mov     ecx, [rsp+88h+var_50]
0x18008f5a7  test    ecx, ecx
0x18008f5a9  jnz     loc_18008F695
0x18008f5af  mov     r13w, 4
0x18008f5b4  test    r13b, al
0x18008f5b7  jz      short loc_18008F5CF
0x18008f5b9  mov     ecx, r12d; unsigned int
0x18008f5bc  call    ?IsLocaleCJK@@YA_NK@Z; IsLocaleCJK(ulong)
0x18008f5c1  test    al, al
0x18008f5c3  jz      loc_18008F653
0x18008f5c9  mov     [rdi], r12d
0x18008f5cc  mov     [r14], r15d
0x18008f5cf  mov     rcx, rsi; pv
0x18008f5d2  call    cs:__imp_CoTaskMemFree
0x18008f5d8  jmp     loc_18008F3F7
0x18008f5dd  add     eax, ebp
0x18008f5df  jmp     loc_18008F4F7
0x18008f5e4  mov     rcx, r11
0x18008f5e7  jmp     loc_18008F4E1
0x18008f5ec  sub     rdi, r9
0x18008f5ef  cmp     rdi, 1
0x18008f5f3  jbe     loc_18008F4A9
0x18008f5f9  lea     r8, [rdi+rdi]
0x18008f5fd  cmp     r8, 2
0x18008f601  jbe     loc_18008F4A9
0x18008f607  inc     r9
0x18008f60a  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18008f60e  xor     edx, edx; Val
0x18008f610  lea     rcx, [rsi+r9*2]; void *
0x18008f614  call    memset_0
0x18008f619  xor     r11d, r11d
0x18008f61c  jmp     loc_18008F4A9
0x18008f621  mov     dword ptr [rdi], 411h
0x18008f627  shr     eax, 2
0x18008f62a  and     eax, ebp
0x18008f62c  mov     [r14], eax
0x18008f62f  jmp     short loc_18008F5CF
0x18008f631  cmp     ebx, 80070505h
0x18008f637  cmovz   ebx, r8d
0x18008f63b  jmp     short loc_18008F5CF
0x18008f63d  call    cs:__imp_GetSystemDefaultLangID
0x18008f643  cmp     ax, r13w
0x18008f647  jnz     short loc_18008F69C
0x18008f649  movzx   eax, ax
0x18008f64c  mov     [rdi], eax
0x18008f64e  jmp     loc_18008F5CC
0x18008f653  call    cs:__imp_GetUserDefaultLangID
0x18008f659  cmp     ax, r13w
0x18008f65d  jz      short loc_18008F649
0x18008f65f  lea     ecx, [rax-11h]
0x18008f662  cmp     cx, bp
0x18008f665  jbe     short loc_18008F649
0x18008f667  call    cs:__imp_GetUserDefaultUILanguage
0x18008f66d  cmp     ax, r13w
0x18008f671  jz      short loc_18008F649
0x18008f673  lea     ecx, [rax-11h]
0x18008f676  cmp     cx, bp
0x18008f679  jbe     short loc_18008F649
0x18008f67b  jmp     short loc_18008F63D
0x18008f67d  mov     [rsi], r11w
0x18008f681  jmp     loc_18008F4A9
0x18008f686  mov     [rdi], ecx
0x18008f688  jmp     loc_18008F583
0x18008f68d  mov     dword ptr [rdi], 412h
0x18008f693  jmp     short loc_18008F627
0x18008f695  mov     [rdi], ecx
0x18008f697  jmp     loc_18008F5CF
0x18008f69c  lea     ecx, [rax-11h]
0x18008f69f  cmp     cx, bp
0x18008f6a2  jbe     short loc_18008F649
0x18008f6a4  mov     dword ptr [rdi], 411h
0x18008f6aa  mov     dword ptr [r14], 3
0x18008f6b1  jmp     loc_18008F5CF
```
