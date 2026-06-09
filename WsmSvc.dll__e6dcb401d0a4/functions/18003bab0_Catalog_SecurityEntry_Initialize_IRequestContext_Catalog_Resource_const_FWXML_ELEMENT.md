# Catalog::SecurityEntry::Initialize(IRequestContext &,Catalog::Resource const &,_FWXML_ELEMENT *)

- ea: `0x18003bab0`
- end: `0x18003c453`
- name: `?Initialize@SecurityEntry@Catalog@@QEAA_NAEAVIRequestContext@@AEBVResource@2@PEAU_FWXML_ELEMENT@@@Z`
- size: `2467`
- prototype: `char __fastcall(Catalog::SecurityEntry *this, struct IRequestContext *, const struct Catalog::Resource *, struct _FWXML_ELEMENT *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180038e24`

## callees

- `0x180005d10`
- `0x180036864`
- `0x18003a3a0`
- `0x18003a610`
- `0x18003bab0`
- `0x18003c640`
- `0x180064250`
- `0x18010d8c6`
- `0x1801ba182`
- `0x1801c2010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18003bb6f`
- `msvcrt!_wcsnicmp` at `0x18003bc4e`
- `msvcrt!_wcsnicmp` at `0x18003bcff`
- `msvcrt!_wcsnicmp` at `0x18003bf14`
- `msvcrt!_wcsnicmp` at `0x18003c061`
- `msvcrt!_wcsnicmp` at `0x18003c101`
- `msvcrt!_wcsnicmp` at `0x18003c1a1`
- `msvcrt!_wcsnicmp` at `0x18003bb6f`
- `msvcrt!_wcsnicmp` at `0x18003bc4e`
- `msvcrt!_wcsnicmp` at `0x18003bcff`
- `msvcrt!_wcsnicmp` at `0x18003bf14`
- `msvcrt!_wcsnicmp` at `0x18003c061`
- `msvcrt!_wcsnicmp` at `0x18003c101`
- `msvcrt!_wcsnicmp` at `0x18003c1a1`
- `msvcrt!_wcsicmp` at `0x18003be4c`
- `msvcrt!_wcsicmp` at `0x18003bec1`
- `msvcrt!_wcsicmp` at `0x18003bf55`
- `msvcrt!_wcsicmp` at `0x18003be4c`
- `msvcrt!_wcsicmp` at `0x18003bec1`
- `msvcrt!_wcsicmp` at `0x18003bf55`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18003be7b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x18003be7b`

## string_xrefs

- `0x18003bb34`: `http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration`
- `0x18003bc13`: `http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration`
- `0x18003bcc4`: `http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration`
- `0x18003bdd7`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18003bfc8`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18003c1d1`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18003c201`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18003c255`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18003c285`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18003c2ad`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`
- `0x18003c2dd`: `onecore\admin\wmi\wmx\fwxml\fwxml.cpp`

## pseudocode

```c
char __fastcall Catalog::SecurityEntry::Initialize(
        Catalog::SecurityEntry *this,
        struct IRequestContext *a2,
        const struct Catalog::Resource *a3,
        struct _FWXML_ELEMENT *a4)
{
  unsigned int v4; // r15d
  int v5; // esi
  struct IRequestContext *v7; // r12
  Catalog::SecurityEntry *v8; // rbp
  __int64 v9; // r14
  __int64 v10; // rdi
  const wchar_t **v11; // rax
  __int64 v12; // rcx
  const wchar_t *v13; // rax
  const wchar_t *v14; // rcx
  const wchar_t *v15; // rax
  const unsigned __int16 *AttributeValue; // rax
  unsigned __int16 *v17; // rax
  int v18; // esi
  __int64 v19; // r14
  __int64 v20; // rdi
  const wchar_t **v21; // rax
  __int64 v22; // rcx
  const wchar_t *v23; // rax
  const wchar_t *v24; // rcx
  const wchar_t *v25; // rax
  const wchar_t *v26; // rax
  const wchar_t *v27; // rdi
  int v28; // edi
  __int64 v29; // r14
  __int64 v30; // rsi
  const wchar_t **v31; // rax
  __int64 v32; // rcx
  const wchar_t *v33; // rax
  const wchar_t *v34; // rcx
  const wchar_t *v35; // rax
  BOOL v36; // r9d
  __int64 v37; // rcx
  __int64 v38; // rdx
  _QWORD *v39; // rax
  const unsigned __int16 *v40; // rdi
  __int64 v41; // r14
  int v42; // ebx
  unsigned int v43; // r13d
  unsigned __int16 v44; // bp
  __int64 v45; // r12
  const unsigned __int16 *v46; // r8
  unsigned int v47; // edx
  __int64 v48; // rdx
  __int64 v49; // rax
  __int64 v52; // rsi
  SIZE_T v53; // rbp
  HLOCAL v54; // rsi
  const wchar_t *v55; // rbp
  __int64 v56; // rax
  __int64 v57; // rsi
  const wchar_t **v58; // rax
  __int64 v59; // rcx
  const wchar_t *v60; // rax
  const wchar_t *v61; // rcx
  int i; // edi
  const wchar_t *v63; // rax
  __int64 v64; // rsi
  const wchar_t **v65; // rax
  __int64 v66; // rcx
  const wchar_t *v67; // rax
  const wchar_t *v68; // rcx
  int k; // edi
  const wchar_t *v70; // rax
  __int64 v71; // rsi
  const wchar_t **v72; // rax
  __int64 v73; // rcx
  const wchar_t *v74; // rax
  const wchar_t *v75; // rcx
  int j; // edi
  const wchar_t *v77; // rax
  int m; // eax
  const wchar_t *v79; // rbx
  __int64 v80; // [rsp+30h] [rbp-58h]
  int v84; // [rsp+A8h] [rbp+20h] BYREF

  v4 = 0;
  v5 = 0;
  v7 = a2;
  v8 = this;
  while ( 1 )
  {
    if ( v5 == *((_DWORD *)a4 + 28) )
    {
      for ( i = 0; ; ++i )
      {
        if ( i == *((_DWORD *)a4 + 28) )
          goto LABEL_56;
        v9 = 104LL * i;
        v57 = v9 + *((_QWORD *)a4 + 15);
        v58 = (const wchar_t **)(v57 + 48);
        if ( v57 == -48 )
          break;
        if ( !*(_DWORD *)(v57 + 64) )
        {
          v59 = *(_QWORD *)(v57 + 56);
          if ( v59 == -1 )
          {
            v61 = *v58;
          }
          else
          {
            v60 = *v58;
            v61 = v60 ? (const wchar_t *)(*(_QWORD *)v60 + 2 * v59) : 0LL;
          }
          if ( !wcsncmp_0(v61, &Class, 0) )
          {
            if ( !v57 )
              break;
            if ( *(_DWORD *)(v57 + 16) == 3 )
            {
              v63 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v57);
              if ( !_wcsnicmp(v63, L"Uri", 3u) )
                goto LABEL_13;
            }
          }
        }
LABEL_103:
        ;
      }
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
      goto LABEL_103;
    }
    v9 = 104LL * v5;
    v10 = v9 + *((_QWORD *)a4 + 15);
    v11 = (const wchar_t **)(v10 + 48);
    if ( v10 == -48 )
      goto LABEL_136;
    if ( *(_DWORD *)(v10 + 64) == 68 )
    {
      v12 = *(_QWORD *)(v10 + 56);
      if ( v12 == -1 )
      {
        v14 = *v11;
      }
      else
      {
        v13 = *v11;
        v14 = v13 ? (const wchar_t *)(*(_QWORD *)v13 + 2 * v12) : 0LL;
      }
      if ( !wcsncmp_0(v14, L"http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration", 0x44u) )
      {
        if ( !v10 )
        {
LABEL_136:
          WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
          goto LABEL_11;
        }
        if ( *(_DWORD *)(v10 + 16) == 3 )
        {
          v15 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v10);
          if ( !_wcsnicmp(v15, L"Uri", 3u) )
            break;
        }
      }
    }
LABEL_11:
    ++v5;
  }
LABEL_13:
  AttributeValue = (const unsigned __int16 *)FwXmlGetAttributeValue(v9 + *((_QWORD *)a4 + 15));
  if ( !AttributeValue )
    goto LABEL_56;
  if ( !v7 )
  {
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 0x108u, L"264", 0x54Fu, 0);
    *(_QWORD *)v8 = 0;
    return 0;
  }
  v84 = 0;
  v17 = CopyString(AttributeValue, &v84, v7);
  *(_QWORD *)v8 = v17;
  if ( !v17 )
    return 0;
  v18 = 0;
  while ( 2 )
  {
    if ( v18 == *((_DWORD *)a4 + 28) )
    {
      for ( j = 0; ; ++j )
      {
        if ( j == *((_DWORD *)a4 + 28) )
          goto LABEL_29;
        v19 = 104LL * j;
        v71 = v19 + *((_QWORD *)a4 + 15);
        v72 = (const wchar_t **)(v71 + 48);
        if ( v71 == -48 )
          break;
        if ( !*(_DWORD *)(v71 + 64) )
        {
          v73 = *(_QWORD *)(v71 + 56);
          if ( v73 == -1 )
          {
            v75 = *v72;
          }
          else
          {
            v74 = *v72;
            v75 = v74 ? (const wchar_t *)(*(_QWORD *)v74 + 2 * v73) : 0LL;
          }
          if ( !wcsncmp_0(v75, &Class, 0) )
          {
            if ( !v71 )
              break;
            if ( *(_DWORD *)(v71 + 16) == 10 )
            {
              v77 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v71);
              if ( !_wcsnicmp(v77, L"ExactMatch", 0xAu) )
                goto LABEL_28;
            }
          }
        }
LABEL_131:
        ;
      }
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
      goto LABEL_131;
    }
    v19 = 104LL * v18;
    v20 = v19 + *((_QWORD *)a4 + 15);
    v21 = (const wchar_t **)(v20 + 48);
    if ( v20 == -48 )
      goto LABEL_140;
    if ( *(_DWORD *)(v20 + 64) != 68 )
      goto LABEL_26;
    v22 = *(_QWORD *)(v20 + 56);
    if ( v22 == -1 )
    {
      v24 = *v21;
    }
    else
    {
      v23 = *v21;
      v24 = v23 ? (const wchar_t *)(*(_QWORD *)v23 + 2 * v22) : 0LL;
    }
    if ( wcsncmp_0(v24, L"http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration", 0x44u) )
      goto LABEL_26;
    if ( !v20 )
    {
LABEL_140:
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
LABEL_26:
      ++v18;
      continue;
    }
    break;
  }
  if ( *(_DWORD *)(v20 + 16) != 10 )
    goto LABEL_26;
  v25 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v20);
  if ( _wcsnicmp(v25, L"ExactMatch", 0xAu) )
    goto LABEL_26;
LABEL_28:
  v26 = (const wchar_t *)FwXmlGetAttributeValue(v19 + *((_QWORD *)a4 + 15));
  v27 = v26;
  if ( v26 )
  {
    if ( _wcsicmp(v26, L"false") )
    {
      if ( !_wcsicmp(v27, L"true") )
        *((_BYTE *)v8 + 32) = 1;
    }
    else
    {
      *((_BYTE *)v8 + 32) = 0;
    }
  }
LABEL_29:
  v28 = 0;
  while ( 2 )
  {
    if ( v28 == *((_DWORD *)a4 + 28) )
    {
      for ( k = 0; ; ++k )
      {
        if ( k == *((_DWORD *)a4 + 28) )
          goto LABEL_56;
        v29 = 104LL * k;
        v64 = v29 + *((_QWORD *)a4 + 15);
        v65 = (const wchar_t **)(v64 + 48);
        if ( v64 == -48 )
          break;
        if ( !*(_DWORD *)(v64 + 64) )
        {
          v66 = *(_QWORD *)(v64 + 56);
          if ( v66 == -1 )
          {
            v68 = *v65;
          }
          else
          {
            v67 = *v65;
            v68 = v67 ? (const wchar_t *)(*(_QWORD *)v67 + 2 * v66) : 0LL;
          }
          if ( !wcsncmp_0(v68, &Class, 0) )
          {
            if ( !v64 )
              break;
            if ( *(_DWORD *)(v64 + 16) == 4 )
            {
              v70 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v64);
              if ( !_wcsnicmp(v70, L"Sddl", 4u) )
                goto LABEL_41;
            }
          }
        }
LABEL_117:
        ;
      }
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
      goto LABEL_117;
    }
    v29 = 104LL * v28;
    v30 = v29 + *((_QWORD *)a4 + 15);
    v31 = (const wchar_t **)(v30 + 48);
    if ( v30 == -48 )
      goto LABEL_143;
    if ( *(_DWORD *)(v30 + 64) != 68 )
      goto LABEL_39;
    v32 = *(_QWORD *)(v30 + 56);
    if ( v32 == -1 )
    {
      v34 = *v31;
    }
    else
    {
      v33 = *v31;
      v34 = v33 ? (const wchar_t *)(*(_QWORD *)v33 + 2 * v32) : 0LL;
    }
    if ( wcsncmp_0(v34, L"http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration", 0x44u) )
      goto LABEL_39;
    if ( !v30 )
    {
LABEL_143:
      WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x20Au, L"522", 0x54Fu, 0);
LABEL_39:
      ++v28;
      continue;
    }
    break;
  }
  if ( *(_DWORD *)(v30 + 16) != 4 )
    goto LABEL_39;
  v35 = (const wchar_t *)OffsetPtr<unsigned short,unsigned __int64>::operator unsigned short *(v30);
  if ( _wcsnicmp(v35, L"Sddl", 4u) )
    goto LABEL_39;
LABEL_41:
  v37 = v29 + *((_QWORD *)a4 + 15);
  if ( !v37 )
  {
    v46 = L"1397";
    v47 = 1397;
LABEL_55:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", v47, v46, 0x54Fu, 0);
    goto LABEL_56;
  }
  if ( *(_DWORD *)(v37 + 96) != 1 )
  {
LABEL_56:
    v48 = 2150858819LL;
LABEL_57:
    (*(void (__fastcall **)(struct IRequestContext *, __int64))(*(_QWORD *)v7 + 72LL))(v7, v48);
    return 0;
  }
  v38 = *(_QWORD *)(v37 + 80);
  if ( v38 != -1 )
  {
    v39 = *(_QWORD **)(v37 + 72);
    if ( v39 )
    {
      v40 = (const unsigned __int16 *)(*v39 + 2 * v38);
      goto LABEL_46;
    }
    *(_WORD *)(2LL * *(unsigned int *)(v37 + 88)) = 0;
LABEL_93:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\fwxml\\fwxml.cpp", 0x44Cu, L"1100", 0x54Fu, 0);
    goto LABEL_54;
  }
  v40 = *(const unsigned __int16 **)(v37 + 72);
LABEL_46:
  v41 = *(unsigned int *)(v37 + 88);
  v40[v41] = 0;
  if ( !v40 )
    goto LABEL_93;
  v42 = 0;
  v43 = v41 + 1;
  if ( (_DWORD)v41 )
  {
    do
    {
      v44 = v40[v42];
      v45 = v4;
      if ( v44 == 38 )
      {
        for ( m = 0; ; m = v84 + 1 )
        {
          v84 = m;
          if ( m == 5 )
            break;
          v80 = 3LL * m;
          if ( !wcsncmp_0(&v40[v42], (const wchar_t *)qword_18027B030[v80 + 1], LODWORD(qword_18027B030[v80 + 2])) )
          {
            if ( ++v4 <= v43 )
              v40[v45] = qword_18027B030[v80];
            v42 = LODWORD(qword_18027B030[v80 + 2]) + v42 - 1;
            goto LABEL_51;
          }
        }
      }
      if ( ++v4 <= v43 )
        v40[v45] = v44;
LABEL_51:
      ++v42;
    }
    while ( v42 < (unsigned int)v41 );
    v7 = a2;
    v8 = this;
  }
  if ( v4 + 1 > v43 )
  {
LABEL_54:
    v46 = L"1410";
    v47 = 1410;
    goto LABEL_55;
  }
  v52 = -1;
  v40[v4] = 0;
  v49 = -1;
  v79 = *(const wchar_t **)v8;
  do
    ++v49;
  while ( v79[v49] );
  *((_QWORD *)v8 + 1) = v49;
  if ( v49 )
  {
    v55 = (const wchar_t *)*((_QWORD *)a3 + 3);
    if ( *((_BYTE *)a3 + 34) )
    {
      if ( !v79 )
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 0x8Bu, L"139", 0x54Fu, 0);
      if ( !v55 )
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 0x8Cu, L"140", 0x54Fu, 0);
      if ( _wcsicmp(v79, v55) )
        goto LABEL_77;
    }
    else
    {
      if ( !v79 )
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 0x9Cu, L"156", 0x54Fu, 0);
      if ( !v55 )
        WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", 0x9Du, L"157", 0x54Fu, 0);
      v56 = -1;
      do
        ++v56;
      while ( v55[v56] );
      if ( _wcsnicmp(v79, v55, (unsigned int)v56) )
      {
LABEL_77:
        v48 = 2150859183LL;
        goto LABEL_57;
      }
    }
    v8 = this;
  }
  if ( !(unsigned int)SDDLToSecurityDescriptor(v7, v40, (void **)v8 + 2, v36) )
    return 0;
  while ( v40[++v52] != 0 )
    ;
  v53 = 2 * (int)v52 + 2;
  v54 = LocalAlloc(0, v53);
  AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>((char *)this + 24);
  *((_QWORD *)this + 3) = v54;
  if ( !v54 )
  {
    (*(void (__fastcall **)(struct IRequestContext *))(*(_QWORD *)v7 + 24LL))(v7);
    return 0;
  }
  memcpy_0(v54, v40, v53);
  return 1;
}

```

## disassembly

```asm
0x18003bab0  mov     [rsp+arg_10], r8
0x18003bab5  mov     [rsp+arg_8], rdx
0x18003baba  mov     [rsp+arg_0], rcx
0x18003babf  push    rbx
0x18003bac0  push    rbp
0x18003bac1  push    rsi
0x18003bac2  push    r12
0x18003bac4  push    r15
0x18003bac6  sub     rsp, 60h
0x18003baca  xor     r15d, r15d
0x18003bacd  mov     [rsp+88h+var_30], rdi
0x18003bad2  mov     esi, r15d
0x18003bad5  mov     [rsp+88h+var_40], r14
0x18003bada  mov     rbx, r9
0x18003badd  mov     r12, rdx
0x18003bae0  mov     rbp, rcx
0x18003bae3  cmp     esi, [rbx+70h]
0x18003bae6  jz      loc_18003C1E2
0x18003baec  mov     rdi, [rbx+78h]
0x18003baf0  movsxd  rax, esi
0x18003baf3  imul    r14, rax, 68h ; 'h'
0x18003baf7  add     rdi, r14
0x18003bafa  lea     rax, [rdi+30h]
0x18003bafe  test    rax, rax
0x18003bb01  jz      loc_18003C1BA
0x18003bb07  cmp     dword ptr [rax+10h], 44h ; 'D'
0x18003bb0b  jnz     short loc_18003BB53
0x18003bb0d  mov     rcx, [rax+8]
0x18003bb11  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003bb15  jz      loc_18003BF6C
0x18003bb1b  mov     rax, [rax]
0x18003bb1e  test    rax, rax
0x18003bb21  jz      loc_18003BF84
0x18003bb27  mov     rax, [rax]
0x18003bb2a  lea     rcx, [rax+rcx*2]; String1
0x18003bb2e  mov     r8d, 44h ; 'D'; MaxCount
0x18003bb34  lea     rdx, aHttpSchemasMic_9; "http://schemas.microsoft.com/wbem/wsman"...
0x18003bb3b  call    wcsncmp_0
0x18003bb40  test    eax, eax
0x18003bb42  jnz     short loc_18003BB53
0x18003bb44  test    rdi, rdi
0x18003bb47  jz      loc_18003C1BA
0x18003bb4d  cmp     dword ptr [rdi+10h], 3
0x18003bb51  jz      short loc_18003BB57
0x18003bb53  inc     esi
0x18003bb55  jmp     short loc_18003BAE3
0x18003bb57  mov     rcx, rdi
0x18003bb5a  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x18003bb5f  mov     rcx, rax; String1
0x18003bb62  lea     rdx, aUri_0; "Uri"
0x18003bb69  mov     r8d, 3; MaxCount
0x18003bb6f  call    cs:__imp__wcsnicmp
0x18003bb75  test    eax, eax
0x18003bb77  jnz     short loc_18003BB53
0x18003bb79  mov     rcx, [rbx+78h]
0x18003bb7d  add     rcx, r14
0x18003bb80  call    FwXmlGetAttributeValue
0x18003bb85  test    rax, rax
0x18003bb88  jz      loc_18003BDE3
0x18003bb8e  test    r12, r12
0x18003bb91  jz      loc_18003C212
0x18003bb97  mov     r8, r12; struct IRequestContext *
0x18003bb9a  mov     [rsp+88h+arg_18], r15d
0x18003bba2  lea     rdx, [rsp+88h+arg_18]; int *
0x18003bbaa  mov     rcx, rax; unsigned __int16 *
0x18003bbad  call    ?CopyString@@YAPEAGPEBGAEBHAEAVIRequestContext@@@Z; CopyString(ushort const *,int const &,IRequestContext &)
0x18003bbb2  mov     [rbp+0], rax
0x18003bbb6  test    rax, rax
0x18003bbb9  jz      loc_18003BE2A
0x18003bbbf  mov     esi, r15d
0x18003bbc2  cmp     esi, [rbx+70h]
0x18003bbc5  jz      loc_18003C266
0x18003bbcb  mov     rdi, [rbx+78h]
0x18003bbcf  movsxd  rax, esi
0x18003bbd2  imul    r14, rax, 68h ; 'h'
0x18003bbd6  add     rdi, r14
0x18003bbd9  lea     rax, [rdi+30h]
0x18003bbdd  test    rax, rax
0x18003bbe0  jz      loc_18003C23E
0x18003bbe6  cmp     dword ptr [rax+10h], 44h ; 'D'
0x18003bbea  jnz     short loc_18003BC32
0x18003bbec  mov     rcx, [rax+8]
0x18003bbf0  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003bbf4  jz      loc_18003BF74
0x18003bbfa  mov     rax, [rax]
0x18003bbfd  test    rax, rax
0x18003bc00  jz      loc_18003BF8C
0x18003bc06  mov     rax, [rax]
0x18003bc09  lea     rcx, [rax+rcx*2]; String1
0x18003bc0d  mov     r8d, 44h ; 'D'; MaxCount
0x18003bc13  lea     rdx, aHttpSchemasMic_9; "http://schemas.microsoft.com/wbem/wsman"...
0x18003bc1a  call    wcsncmp_0
0x18003bc1f  test    eax, eax
0x18003bc21  jnz     short loc_18003BC32
0x18003bc23  test    rdi, rdi
0x18003bc26  jz      loc_18003C23E
0x18003bc2c  cmp     dword ptr [rdi+10h], 0Ah
0x18003bc30  jz      short loc_18003BC36
0x18003bc32  inc     esi
0x18003bc34  jmp     short loc_18003BBC2
0x18003bc36  mov     rcx, rdi
0x18003bc39  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x18003bc3e  mov     rcx, rax; String1
0x18003bc41  lea     rdx, aExactmatch; "ExactMatch"
0x18003bc48  mov     r8d, 0Ah; MaxCount
0x18003bc4e  call    cs:__imp__wcsnicmp
0x18003bc54  test    eax, eax
0x18003bc56  jnz     short loc_18003BC32
0x18003bc58  mov     rcx, [rbx+78h]
0x18003bc5c  add     rcx, r14
0x18003bc5f  call    FwXmlGetAttributeValue
0x18003bc64  mov     rdi, rax
0x18003bc67  test    rax, rax
0x18003bc6a  jnz     loc_18003BE42
0x18003bc70  mov     edi, r15d
0x18003bc73  cmp     edi, [rbx+70h]
0x18003bc76  jz      loc_18003C2BE
0x18003bc7c  mov     rsi, [rbx+78h]
0x18003bc80  movsxd  rax, edi
0x18003bc83  imul    r14, rax, 68h ; 'h'
0x18003bc87  add     rsi, r14
0x18003bc8a  lea     rax, [rsi+30h]
0x18003bc8e  test    rax, rax
0x18003bc91  jz      loc_18003C296
0x18003bc97  cmp     dword ptr [rax+10h], 44h ; 'D'
0x18003bc9b  jnz     short loc_18003BCE3
0x18003bc9d  mov     rcx, [rax+8]
0x18003bca1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003bca5  jz      loc_18003BF7C
0x18003bcab  mov     rax, [rax]
0x18003bcae  test    rax, rax
0x18003bcb1  jz      loc_18003BF94
0x18003bcb7  mov     rax, [rax]
0x18003bcba  lea     rcx, [rax+rcx*2]; String1
0x18003bcbe  mov     r8d, 44h ; 'D'; MaxCount
0x18003bcc4  lea     rdx, aHttpSchemasMic_9; "http://schemas.microsoft.com/wbem/wsman"...
0x18003bccb  call    wcsncmp_0
0x18003bcd0  test    eax, eax
0x18003bcd2  jnz     short loc_18003BCE3
0x18003bcd4  test    rsi, rsi
0x18003bcd7  jz      loc_18003C296
0x18003bcdd  cmp     dword ptr [rsi+10h], 4
0x18003bce1  jz      short loc_18003BCE7
0x18003bce3  inc     edi
0x18003bce5  jmp     short loc_18003BC73
0x18003bce7  mov     rcx, rsi
0x18003bcea  call    ??B?$OffsetPtr@G_K@@QEAAPEAGXZ; OffsetPtr<ushort,unsigned __int64>::operator ushort *(void)
0x18003bcef  mov     rcx, rax; String1
0x18003bcf2  lea     rdx, aSddl; "Sddl"
0x18003bcf9  mov     r8d, 4; MaxCount
0x18003bcff  call    cs:__imp__wcsnicmp
0x18003bd05  test    eax, eax
0x18003bd07  jnz     short loc_18003BCE3
0x18003bd09  mov     rcx, [rbx+78h]
0x18003bd0d  add     rcx, r14
0x18003bd10  test    rcx, rcx
0x18003bd13  jz      loc_18003C2EE
0x18003bd19  cmp     dword ptr [rcx+60h], 1
0x18003bd1d  jnz     loc_18003BDE3
0x18003bd23  mov     rdx, [rcx+50h]
0x18003bd27  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18003bd2b  jz      loc_18003BF9C
0x18003bd31  mov     rax, [rcx+48h]
0x18003bd35  test    rax, rax
0x18003bd38  jz      loc_18003BFA5
0x18003bd3e  mov     rax, [rax]
0x18003bd41  lea     rdi, [rax+rdx*2]
0x18003bd45  mov     r14d, [rcx+58h]
0x18003bd49  mov     [rdi+r14*2], r15w
0x18003bd4e  test    rdi, rdi
0x18003bd51  jz      loc_18003BFB1
0x18003bd57  xor     ebx, ebx
0x18003bd59  mov     [rsp+88h+var_38], r13
0x18003bd5e  lea     r13d, [r14+1]
0x18003bd62  test    r14d, r14d
0x18003bd65  jz      short loc_18003BDAB
0x18003bd67  lea     rdx, qword_18027B030
0x18003bd6e  xchg    ax, ax
0x18003bd70  movsxd  rax, ebx
0x18003bd73  movzx   ebp, word ptr [rdi+rax*2]
0x18003bd77  lea     rsi, [rdi+rax*2]
0x18003bd7b  mov     r12d, r15d
0x18003bd7e  cmp     bp, 26h ; '&'
0x18003bd82  jz      loc_18003C2FF
0x18003bd88  inc     r15d
0x18003bd8b  cmp     r15d, r13d
0x18003bd8e  jbe     loc_18003C37D
0x18003bd94  inc     ebx
0x18003bd96  cmp     ebx, r14d
0x18003bd99  jb      short loc_18003BD70
0x18003bd9b  mov     r12, [rsp+88h+arg_8]
0x18003bda3  mov     rbp, [rsp+88h+arg_0]
0x18003bdab  lea     eax, [r15+1]
0x18003bdaf  cmp     eax, r13d
0x18003bdb2  mov     r13, [rsp+88h+var_38]
0x18003bdb7  jbe     loc_18003C387
0x18003bdbd  xor     r15d, r15d
0x18003bdc0  lea     r8, a1410; "1410"
0x18003bdc7  mov     edx, 582h; unsigned int
0x18003bdcc  mov     r9d, 54Fh; unsigned int
0x18003bdd2  mov     [rsp+88h+var_68], r15; struct IRequestContext *
0x18003bdd7  lea     rcx, aOnecoreAdminWm_5; "onecore\\admin\\wmi\\wmx\\fwxml\\fwxml."...
0x18003bdde  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18003bde3  mov     edx, 80338043h
0x18003bde8  mov     rax, [r12]
0x18003bdec  mov     rcx, r12
0x18003bdef  mov     rax, [rax+48h]
0x18003bdf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bdf8  jmp     short loc_18003BE2A
0x18003be00  inc     rax
0x18003be03  cmp     word ptr [rbx+rax*2], 0
0x18003be08  jnz     short loc_18003BE00
0x18003be0a  mov     [rbp+8], rax
0x18003be0e  test    rax, rax
0x18003be11  jnz     loc_18003BED8
0x18003be17  lea     r8, [rbp+10h]; void **
0x18003be1b  mov     rdx, rdi; unsigned __int16 *
0x18003be1e  mov     rcx, r12; struct IRequestContext *
0x18003be21  call    ?SDDLToSecurityDescriptor@@YAHPEAVIRequestContext@@PEBGPEAPEAXH@Z; SDDLToSecurityDescriptor(IRequestContext *,ushort const *,void * *,int)
0x18003be26  test    eax, eax
0x18003be28  jnz     short loc_18003BE60
0x18003be2a  xor     al, al
0x18003be2c  mov     r14, [rsp+88h+var_40]
0x18003be31  mov     rdi, [rsp+88h+var_30]
0x18003be36  add     rsp, 60h
0x18003be3a  pop     r15
0x18003be3c  pop     r12
0x18003be3e  pop     rsi
0x18003be3f  pop     rbp
0x18003be40  pop     rbx
0x18003be41  retn
0x18003be42  lea     rdx, aFalse; "false"
0x18003be49  mov     rcx, rdi; String1
0x18003be4c  call    cs:__imp__wcsicmp
0x18003be52  test    eax, eax
0x18003be54  jnz     short loc_18003BEB7
0x18003be56  mov     [rbp+20h], r15b
0x18003be5a  jmp     loc_18003BC70
0x18003be60  cmp     word ptr [rdi+rsi*2+2], 0
0x18003be66  lea     rsi, [rsi+1]
0x18003be6a  jnz     short loc_18003BE60
0x18003be6c  lea     eax, ds:2[rsi*2]
0x18003be73  xor     ecx, ecx; uFlags
0x18003be75  movsxd  rbp, eax
0x18003be78  mov     rdx, rbp; uBytes
0x18003be7b  call    cs:__imp_LocalAlloc
0x18003be81  mov     rbx, [rsp+88h+arg_0]
0x18003be89  mov     rsi, rax
0x18003be8c  lea     rcx, [rbx+18h]; void *
0x18003be90  call    ??1?$AutoCleanup@VAutoSecurityDescriptor@@PEAX@@QEAA@XZ; AutoCleanup<AutoSecurityDescriptor,void *>::~AutoCleanup<AutoSecurityDescriptor,void *>(void)
0x18003be95  mov     [rbx+18h], rsi
0x18003be99  test    rsi, rsi
0x18003be9c  jz      loc_18003BF28
0x18003bea2  mov     r8, rbp; Size
0x18003bea5  mov     rdx, rdi; Src
0x18003bea8  mov     rcx, rsi; void *
0x18003beab  call    memcpy_0
0x18003beb0  mov     al, 1
0x18003beb2  jmp     loc_18003BE2C
0x18003beb7  lea     rdx, aTrue; "true"
0x18003bebe  mov     rcx, rdi; String1
0x18003bec1  call    cs:__imp__wcsicmp
0x18003bec7  test    eax, eax
0x18003bec9  jnz     loc_18003BC70
0x18003becf  mov     byte ptr [rbp+20h], 1
0x18003bed3  jmp     loc_18003BC70
0x18003bed8  mov     rax, [rsp+88h+arg_10]
0x18003bee0  cmp     byte ptr [rax+22h], 0
0x18003bee4  mov     rbp, [rax+18h]
0x18003bee8  jnz     short loc_18003BF3D
0x18003beea  test    rbx, rbx
0x18003beed  jz      loc_18003C3FB
0x18003bef3  test    rbp, rbp
0x18003bef6  jz      loc_18003C427
0x18003befc  mov     rax, rsi
0x18003beff  nop
0x18003bf00  inc     rax
0x18003bf03  cmp     word ptr [rbp+rax*2+0], 0
0x18003bf09  jnz     short loc_18003BF00
0x18003bf0b  mov     r8d, eax; MaxCount
0x18003bf0e  mov     rdx, rbp; String2
0x18003bf11  mov     rcx, rbx; String1
0x18003bf14  call    cs:__imp__wcsnicmp
0x18003bf1a  test    eax, eax
0x18003bf1c  jz      short loc_18003BF5F
0x18003bf1e  mov     edx, 803381AFh
0x18003bf23  jmp     loc_18003BDE8
0x18003bf28  mov     rax, [r12]
0x18003bf2c  mov     rcx, r12
0x18003bf2f  mov     rax, [rax+18h]
0x18003bf33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003bf38  jmp     loc_18003BE2A
0x18003bf3d  test    rbx, rbx
0x18003bf40  jz      loc_18003C3A3
0x18003bf46  test    rbp, rbp
0x18003bf49  jz      loc_18003C3CF
0x18003bf4f  mov     rdx, rbp; String2
0x18003bf52  mov     rcx, rbx; String1
0x18003bf55  call    cs:__imp__wcsicmp
0x18003bf5b  test    eax, eax
  ... truncated ...
```
