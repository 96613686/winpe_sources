# SITE_CUSTOM_PROVIDER::MapSetData(PROPERTY_ENTRY *,ABO_NODE *)

- ea: `0x180015880`
- end: `0x180015eed`
- name: `?MapSetData@SITE_CUSTOM_PROVIDER@@UEAAJPEAVPROPERTY_ENTRY@@PEAVABO_NODE@@@Z`
- size: `1645`
- prototype: `__int64 __fastcall(struct INativeConfigurationElement **this, struct PROPERTY_ENTRY *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180003426`
- `0x180003f14`
- `0x1800047e4`
- `0x1800077dc`
- `0x18000ac98`
- `0x18000ace4`
- `0x18000fa00`
- `0x18000fec4`
- `0x180015200`
- `0x1800153f4`
- `0x180015880`
- `0x180016b1c`
- `0x1800187e0`
- `0x180018d98`
- `0x1800293b0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800158f4`
- `msvcrt!_wcsicmp` at `0x1800158f4`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800158e4`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180015a15`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180015d4a`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180015e28`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800158e4`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180015a15`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180015d4a`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180015e28`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800158c0`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001599a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015a31`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015b5f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015b74`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015b8f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015bb4`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015bc5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015be4`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015bf9`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015c0e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015c23`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015c38`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015c4d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015c62`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015c77`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015c8c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015ca1`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015cb6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015d66`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015e44`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800158c0`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001599a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015a31`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015b5f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015b74`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015b8f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015bb4`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015bc5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015be4`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015bf9`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015c0e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015c23`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015c38`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015c4d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015c62`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015c77`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015c8c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015ca1`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015cb6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015d66`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015e44`

## string_xrefs

- `0x180015df6`: `virtualDirectory`
- `0x180015e31`: `virtualDirectory`

## pseudocode

```c
__int64 __fastcall SITE_CUSTOM_PROVIDER::MapSetData(
        struct INativeConfigurationElement **this,
        struct PROPERTY_ENTRY *a2,
        struct ABO_NODE *a3)
{
  struct PROPERTY_ENTRY *v3; // r14
  BUFFER *v7; // rdi
  const wchar_t *Str; // rax
  int Entry; // eax
  SITE_CUSTOM_PROVIDER *v10; // rcx
  int v11; // ebx
  struct INativeConfigurationElement *v12; // rax
  HANDLE_ENTRY *v13; // r15
  unsigned int Key; // eax
  const wchar_t *v15; // rax
  _DWORD *Ptr; // rax
  int v17; // eax
  SITE_CUSTOM_PROVIDER *v18; // rcx
  int v19; // eax
  int updated; // eax
  struct INativeConfigurationElement *v21; // rax
  HANDLE_ENTRY *v22; // r15
  unsigned int v23; // eax
  const wchar_t *v24; // rax
  _DWORD *v25; // rax
  struct INativeConfigurationElement *v26; // rax
  HANDLE_ENTRY *v27; // r15
  int v28; // eax
  __int64 v29; // r13
  const wchar_t *v30; // rax
  _DWORD *v31; // rax
  HANDLE_ENTRY *v33; // [rsp+20h] [rbp-20h] BYREF
  struct INativeConfigurationElement *v34; // [rsp+28h] [rbp-18h]
  struct INativeConfigurationElement *v35; // [rsp+30h] [rbp-10h]
  struct PROPERTY_ENTRY *v36; // [rsp+88h] [rbp+48h] BYREF
  HANDLE_ENTRY *v37; // [rsp+98h] [rbp+58h] BYREF

  v3 = 0;
  v36 = 0;
  if ( !a2 || !a3 )
    return (unsigned int)-2147024809;
  v7 = (struct PROPERTY_ENTRY *)((char *)a2 + 16);
  if ( *(_DWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a2 + 16)) == 3001
    && this[2] == *((struct INativeConfigurationElement **)a3 + 2) )
  {
    Str = STRU::QueryStr((struct ABO_NODE *)((char *)a3 + 56));
    if ( !_wcsicmp(Str, L"ROOT") )
    {
      Entry = PROPERTY_BAG::FindEntry((struct ABO_NODE *)((char *)a3 + 184), 0x837u, &v36);
      if ( Entry < 0
        && (Entry != -2147024894 || (int)PROPERTY_BAG::FindEntry((struct ABO_NODE *)((char *)a3 + 184), 0x838u, &v36) < 0) )
      {
        v11 = SITE_CUSTOM_PROVIDER::InjectAppProperty(v10, a3);
        if ( v11 < 0 )
          goto LABEL_40;
        v11 = PROPERTY_BAG::FindEntry((struct ABO_NODE *)((char *)a3 + 184), 0x838u, &v36);
        if ( v11 < 0 )
          goto LABEL_40;
      }
      v3 = v36;
      v11 = SITE_CUSTOM_PROVIDER::UpgradeToApplication((SITE_CUSTOM_PROVIDER *)this, v36, a3);
      if ( v11 < 0 )
        goto LABEL_92;
      if ( v3 )
      {
        PROPERTY_MAPPING::DereferencePropertyMapping(v3);
        v3 = 0;
        v36 = 0;
      }
    }
  }
  if ( *(_DWORD *)BUFFER::QueryPtr(v7) != 9101 )
    goto LABEL_42;
  if ( a3 == this[2] )
  {
    v12 = this[6];
    v13 = 0;
    v33 = 0;
    v34 = v12;
    if ( v12 )
    {
      Key = CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::FindKey(
              (char *)g_pPropertySectionTable + 8,
              L"application",
              &v33);
      v13 = v33;
      if ( Key || (v11 = 0, LODWORD(v37) = 0, LODWORD(v36) = 0, !*((_DWORD *)v33 + 22)) )
      {
LABEL_24:
        v11 = -2147024894;
      }
      else
      {
        while ( 1 )
        {
          v33 = *(HANDLE_ENTRY **)(*((_QWORD *)v13 + 10) + 8LL * Key);
          v15 = STRU::QueryStr((HANDLE_ENTRY *)((char *)v33 + 32));
          if ( !wcscmp_0(v15, L"application") )
          {
            Ptr = BUFFER::QueryPtr(v7);
            if ( *((_DWORD *)v33 + 36) == *Ptr )
            {
              LODWORD(v37) = 1;
              v11 = CUSTOM_PROPERTY_PROVIDER::SetConfigPropertiesByMapping(a2, v33, a3, v34);
              if ( v11 < 0 )
                break;
            }
          }
          Key = (_DWORD)v36 + 1;
          LODWORD(v36) = Key;
          if ( Key >= *((_DWORD *)v13 + 22) )
          {
            if ( (_DWORD)v37 )
              break;
            goto LABEL_24;
          }
        }
      }
    }
    else
    {
      v11 = -2147024809;
    }
    if ( v13 )
      HANDLE_ENTRY::DereferenceHandleEntry(v13);
    if ( v11 < 0 )
      goto LABEL_92;
    goto LABEL_42;
  }
  PROPERTY_ENTRY::SetMapped(a2, 0, 1);
  v11 = PROPERTY_BAG::AddEntry((struct ABO_NODE *)((char *)a3 + 184), a2, 1);
  if ( v11 < 0 )
    goto LABEL_92;
  v17 = PROPERTY_BAG::FindEntry((struct ABO_NODE *)((char *)a3 + 184), 0x838u, &v36);
  v11 = v17;
  if ( v17 >= 0 )
  {
    v3 = v36;
    goto LABEL_42;
  }
  if ( v17 != -2147024894
    || (v11 = SITE_CUSTOM_PROVIDER::InjectAppProperty(v18, a3), v11 < 0)
    || (v11 = PROPERTY_BAG::FindEntry((struct ABO_NODE *)((char *)a3 + 184), 0x838u, &v36), v11 < 0) )
  {
LABEL_40:
    v3 = v36;
    goto LABEL_92;
  }
  v3 = v36;
  v19 = SITE_CUSTOM_PROVIDER::UpgradeToApplication((SITE_CUSTOM_PROVIDER *)this, v36, a3);
  v11 = v19;
  if ( v19 < 0 )
  {
    if ( v19 != -2147024846 )
      goto LABEL_92;
    goto LABEL_37;
  }
  if ( v3 )
  {
    PROPERTY_MAPPING::DereferencePropertyMapping(v3);
    v3 = 0;
  }
LABEL_42:
  if ( *(_DWORD *)BUFFER::QueryPtr(v7) == 2103 || *(_DWORD *)BUFFER::QueryPtr(v7) == 2104 )
  {
    updated = SITE_CUSTOM_PROVIDER::UpgradeToApplication((SITE_CUSTOM_PROVIDER *)this, a2, a3);
LABEL_91:
    v11 = updated;
    goto LABEL_92;
  }
  if ( a3 != this[2] )
  {
LABEL_37:
    v11 = -2147024894;
    goto LABEL_92;
  }
  if ( *(_DWORD *)BUFFER::QueryPtr(v7) != 1015 )
  {
    if ( *(_DWORD *)BUFFER::QueryPtr(v7) == 1012 && *((_DWORD *)BUFFER::QueryPtr(v7) + 3) == 1 )
    {
      updated = SITE_CUSTOM_PROVIDER::HandleSiteCommand((SITE_CUSTOM_PROVIDER *)this, a2);
    }
    else
    {
      if ( *(_DWORD *)BUFFER::QueryPtr(v7) == 1099 || *(_DWORD *)BUFFER::QueryPtr(v7) == 1016 )
      {
        v11 = 0;
        goto LABEL_92;
      }
      if ( *(_DWORD *)BUFFER::QueryPtr(v7) != 5511
        && *(_DWORD *)BUFFER::QueryPtr(v7) != 5506
        && *(_DWORD *)BUFFER::QueryPtr(v7) != 5512
        && *(_DWORD *)BUFFER::QueryPtr(v7) != 5517
        && *(_DWORD *)BUFFER::QueryPtr(v7) != 2160
        && *(_DWORD *)BUFFER::QueryPtr(v7) != 5519
        && *(_DWORD *)BUFFER::QueryPtr(v7) != 5521
        && *(_DWORD *)BUFFER::QueryPtr(v7) != 2161
        && *(_DWORD *)BUFFER::QueryPtr(v7) != 2162 )
      {
        v11 = CUSTOM_PROPERTY_PROVIDER::SetConfigPropertiesBySectionName(a2, L"site", a3, this[3]);
        if ( v11 == -2147024894 )
        {
          v21 = this[6];
          v22 = 0;
          v33 = 0;
          v35 = v21;
          if ( v21 )
          {
            v23 = CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::FindKey(
                    (char *)g_pPropertySectionTable + 8,
                    L"application",
                    &v33);
            v22 = v33;
            if ( v23 || (v11 = 0, LODWORD(v37) = 0, LODWORD(v36) = 0, !*((_DWORD *)v33 + 22)) )
            {
LABEL_71:
              v11 = -2147024894;
            }
            else
            {
              while ( 1 )
              {
                v34 = *(struct INativeConfigurationElement **)(*((_QWORD *)v22 + 10) + 8LL * v23);
                v24 = STRU::QueryStr((struct INativeConfigurationElement *)((char *)v34 + 32));
                if ( !wcscmp_0(v24, L"application") )
                {
                  v25 = BUFFER::QueryPtr(v7);
                  if ( *((_DWORD *)v34 + 36) == *v25 )
                  {
                    LODWORD(v37) = 1;
                    v11 = CUSTOM_PROPERTY_PROVIDER::SetConfigPropertiesByMapping(a2, v34, a3, v35);
                    if ( v11 < 0 )
                      break;
                  }
                }
                v23 = (_DWORD)v36 + 1;
                LODWORD(v36) = v23;
                if ( v23 >= *((_DWORD *)v22 + 22) )
                {
                  if ( (_DWORD)v37 )
                    break;
                  goto LABEL_71;
                }
              }
            }
          }
          else
          {
            v11 = -2147024809;
          }
          if ( v22 )
            HANDLE_ENTRY::DereferenceHandleEntry(v22);
          if ( v11 == -2147024894 )
          {
            v26 = this[5];
            v27 = 0;
            v37 = 0;
            v35 = v26;
            if ( v26 )
            {
              v28 = CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::FindKey(
                      (char *)g_pPropertySectionTable + 8,
                      L"virtualDirectory",
                      &v37);
              v27 = v37;
              if ( v28 || (v11 = 0, LODWORD(v36) = 0, v29 = 0, !*((_DWORD *)v37 + 22)) )
              {
LABEL_84:
                v11 = -2147024894;
              }
              else
              {
                while ( 1 )
                {
                  v37 = *(HANDLE_ENTRY **)(*((_QWORD *)v27 + 10) + 8 * v29);
                  v30 = STRU::QueryStr((HANDLE_ENTRY *)((char *)v37 + 32));
                  if ( !wcscmp_0(v30, L"virtualDirectory") )
                  {
                    v31 = BUFFER::QueryPtr(v7);
                    if ( *((_DWORD *)v37 + 36) == *v31 )
                    {
                      LODWORD(v36) = 1;
                      v11 = CUSTOM_PROPERTY_PROVIDER::SetConfigPropertiesByMapping(a2, v37, a3, v35);
                      if ( v11 < 0 )
                        break;
                    }
                  }
                  v29 = (unsigned int)(v29 + 1);
                  if ( (unsigned int)v29 >= *((_DWORD *)v27 + 22) )
                  {
                    if ( (_DWORD)v36 )
                      break;
                    goto LABEL_84;
                  }
                }
              }
            }
            else
            {
              v11 = -2147024809;
            }
            if ( v27 )
              HANDLE_ENTRY::DereferenceHandleEntry(v27);
          }
        }
        goto LABEL_92;
      }
      updated = UpdateSSLProperty(a2, a3);
    }
    goto LABEL_91;
  }
  v11 = ABO_NODE::UnMapNodeAndChildren(a3);
  if ( v11 >= 0 )
    goto LABEL_37;
LABEL_92:
  if ( v3 )
    PROPERTY_MAPPING::DereferencePropertyMapping(v3);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180015880  mov     [rsp-38h+arg_0], rbx
0x180015885  push    rbp
0x180015886  push    rsi
0x180015887  push    rdi
0x180015888  push    r12
0x18001588a  push    r13
0x18001588c  push    r14
0x18001588e  push    r15
0x180015890  mov     rbp, rsp
0x180015893  sub     rsp, 40h
0x180015897  xor     r14d, r14d
0x18001589a  mov     rsi, r8
0x18001589d  mov     [rbp+arg_8], r14
0x1800158a1  mov     r12, rdx
0x1800158a4  mov     r13, rcx
0x1800158a7  test    rdx, rdx
0x1800158aa  jz      loc_180015ECE
0x1800158b0  test    r8, r8
0x1800158b3  jz      loc_180015ECE
0x1800158b9  lea     rdi, [rdx+10h]
0x1800158bd  mov     rcx, rdi
0x1800158c0  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800158c6  cmp     dword ptr [rax], 0BB9h
0x1800158cc  jnz     loc_180015997
0x1800158d2  mov     rax, [rsi+10h]
0x1800158d6  cmp     [r13+10h], rax
0x1800158da  jnz     loc_180015997
0x1800158e0  lea     rcx, [rsi+38h]
0x1800158e4  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x1800158ea  mov     rcx, rax; String1
0x1800158ed  lea     rdx, aRoot_0; "ROOT"
0x1800158f4  call    cs:__imp__wcsicmp
0x1800158fa  test    eax, eax
0x1800158fc  jnz     loc_180015997
0x180015902  lea     r14, [rsi+0B8h]
0x180015909  mov     edx, 837h; unsigned int
0x18001590e  mov     rcx, r14; this
0x180015911  lea     r8, [rbp+arg_8]; struct PROPERTY_ENTRY **
0x180015915  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x18001591a  test    eax, eax
0x18001591c  jns     short loc_180015967
0x18001591e  cmp     eax, 80070002h
0x180015923  jnz     short loc_18001593A
0x180015925  lea     r8, [rbp+arg_8]; struct PROPERTY_ENTRY **
0x180015929  mov     edx, 838h; unsigned int
0x18001592e  mov     rcx, r14; this
0x180015931  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x180015936  test    eax, eax
0x180015938  jns     short loc_180015967
0x18001593a  mov     rdx, rsi; struct ABO_NODE *
0x18001593d  call    ?InjectAppProperty@SITE_CUSTOM_PROVIDER@@AEAAJPEAVABO_NODE@@@Z; SITE_CUSTOM_PROVIDER::InjectAppProperty(ABO_NODE *)
0x180015942  mov     ebx, eax
0x180015944  test    eax, eax
0x180015946  js      loc_180015B4F
0x18001594c  lea     r8, [rbp+arg_8]; struct PROPERTY_ENTRY **
0x180015950  mov     edx, 838h; unsigned int
0x180015955  mov     rcx, r14; this
0x180015958  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x18001595d  mov     ebx, eax
0x18001595f  test    eax, eax
0x180015961  js      loc_180015B4F
0x180015967  mov     r14, [rbp+arg_8]
0x18001596b  mov     r8, rsi; struct ABO_NODE *
0x18001596e  mov     rdx, r14; struct PROPERTY_ENTRY *
0x180015971  mov     rcx, r13; this
0x180015974  call    ?UpgradeToApplication@SITE_CUSTOM_PROVIDER@@AEAAJPEAVPROPERTY_ENTRY@@PEAVABO_NODE@@@Z; SITE_CUSTOM_PROVIDER::UpgradeToApplication(PROPERTY_ENTRY *,ABO_NODE *)
0x180015979  mov     ebx, eax
0x18001597b  test    eax, eax
0x18001597d  js      loc_180015EBF
0x180015983  test    r14, r14
0x180015986  jz      short loc_180015997
0x180015988  mov     rcx, r14; this
0x18001598b  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x180015990  xor     r14d, r14d
0x180015993  mov     [rbp+arg_8], r14
0x180015997  mov     rcx, rdi
0x18001599a  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800159a0  cmp     dword ptr [rax], 238Dh
0x1800159a6  jnz     loc_180015B5C
0x1800159ac  cmp     rsi, [r13+10h]
0x1800159b0  jnz     loc_180015A9B
0x1800159b6  mov     rax, [r13+30h]
0x1800159ba  xor     r15d, r15d
0x1800159bd  mov     [rbp+var_20], r15
0x1800159c1  mov     [rbp+var_18], rax
0x1800159c5  test    rax, rax
0x1800159c8  jz      loc_180015A7C
0x1800159ce  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x1800159d5  lea     r8, [rbp+var_20]
0x1800159d9  add     rcx, 8
0x1800159dd  lea     rdx, aApplication; "application"
0x1800159e4  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x1800159e9  mov     r15, [rbp+var_20]
0x1800159ed  test    eax, eax
0x1800159ef  jnz     loc_180015A75
0x1800159f5  xor     ebx, ebx
0x1800159f7  mov     dword ptr [rbp+arg_18], eax
0x1800159fa  mov     dword ptr [rbp+arg_8], eax
0x1800159fd  cmp     [r15+58h], eax
0x180015a01  jbe     short loc_180015A75
0x180015a03  mov     ecx, eax
0x180015a05  mov     rax, [r15+50h]
0x180015a09  mov     rax, [rax+rcx*8]
0x180015a0d  mov     [rbp+var_20], rax
0x180015a11  lea     rcx, [rax+20h]
0x180015a15  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180015a1b  mov     rcx, rax; String1
0x180015a1e  lea     rdx, aApplication; "application"
0x180015a25  call    wcscmp_0
0x180015a2a  test    eax, eax
0x180015a2c  jnz     short loc_180015A61
0x180015a2e  mov     rcx, rdi
0x180015a31  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180015a37  mov     rdx, [rbp+var_20]; struct PROPERTY_MAPPING *
0x180015a3b  mov     ecx, [rax]
0x180015a3d  cmp     [rdx+90h], ecx
0x180015a43  jnz     short loc_180015A61
0x180015a45  mov     r9, [rbp+var_18]; struct INativeConfigurationElement *
0x180015a49  mov     r8, rsi; struct ABO_NODE *
0x180015a4c  mov     rcx, r12; struct PROPERTY_ENTRY *
0x180015a4f  mov     dword ptr [rbp+arg_18], 1
0x180015a56  call    ?SetConfigPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::SetConfigPropertiesByMapping(PROPERTY_ENTRY *,PROPERTY_MAPPING *,ABO_NODE *,INativeConfigurationElement *)
0x180015a5b  mov     ebx, eax
0x180015a5d  test    eax, eax
0x180015a5f  js      short loc_180015A81
0x180015a61  mov     eax, dword ptr [rbp+arg_8]
0x180015a64  inc     eax
0x180015a66  mov     dword ptr [rbp+arg_8], eax
0x180015a69  cmp     eax, [r15+58h]
0x180015a6d  jb      short loc_180015A03
0x180015a6f  cmp     dword ptr [rbp+arg_18], 0
0x180015a73  jnz     short loc_180015A81
0x180015a75  mov     ebx, 80070002h
0x180015a7a  jmp     short loc_180015A81
0x180015a7c  mov     ebx, 80070057h
0x180015a81  test    r15, r15
0x180015a84  jz      short loc_180015A8E
0x180015a86  mov     rcx, r15; this
0x180015a89  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x180015a8e  test    ebx, ebx
0x180015a90  jns     loc_180015B5C
0x180015a96  jmp     loc_180015EBF
0x180015a9b  xor     edx, edx; int
0x180015a9d  mov     rcx, r12; this
0x180015aa0  lea     r8d, [rdx+1]; int
0x180015aa4  call    ?SetMapped@PROPERTY_ENTRY@@QEAAXHH@Z; PROPERTY_ENTRY::SetMapped(int,int)
0x180015aa9  lea     r15, [rsi+0B8h]
0x180015ab0  mov     r8d, 1; int
0x180015ab6  mov     rcx, r15; this
0x180015ab9  mov     rdx, r12; struct PROPERTY_ENTRY *
0x180015abc  call    ?AddEntry@PROPERTY_BAG@@QEAAJPEAVPROPERTY_ENTRY@@H@Z; PROPERTY_BAG::AddEntry(PROPERTY_ENTRY *,int)
0x180015ac1  mov     ebx, eax
0x180015ac3  test    eax, eax
0x180015ac5  js      loc_180015EBF
0x180015acb  mov     r14d, 838h
0x180015ad1  lea     r8, [rbp+arg_8]; struct PROPERTY_ENTRY **
0x180015ad5  mov     edx, r14d; unsigned int
0x180015ad8  mov     rcx, r15; this
0x180015adb  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x180015ae0  mov     ebx, eax
0x180015ae2  test    eax, eax
0x180015ae4  jns     short loc_180015B58
0x180015ae6  cmp     eax, 80070002h
0x180015aeb  jnz     short loc_180015B4F
0x180015aed  mov     rdx, rsi; struct ABO_NODE *
0x180015af0  call    ?InjectAppProperty@SITE_CUSTOM_PROVIDER@@AEAAJPEAVABO_NODE@@@Z; SITE_CUSTOM_PROVIDER::InjectAppProperty(ABO_NODE *)
0x180015af5  mov     ebx, eax
0x180015af7  test    eax, eax
0x180015af9  js      short loc_180015B4F
0x180015afb  lea     r8, [rbp+arg_8]; struct PROPERTY_ENTRY **
0x180015aff  mov     edx, r14d; unsigned int
0x180015b02  mov     rcx, r15; this
0x180015b05  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x180015b0a  mov     ebx, eax
0x180015b0c  test    eax, eax
0x180015b0e  js      short loc_180015B4F
0x180015b10  mov     r14, [rbp+arg_8]
0x180015b14  mov     r8, rsi; struct ABO_NODE *
0x180015b17  mov     rdx, r14; struct PROPERTY_ENTRY *
0x180015b1a  mov     rcx, r13; this
0x180015b1d  call    ?UpgradeToApplication@SITE_CUSTOM_PROVIDER@@AEAAJPEAVPROPERTY_ENTRY@@PEAVABO_NODE@@@Z; SITE_CUSTOM_PROVIDER::UpgradeToApplication(PROPERTY_ENTRY *,ABO_NODE *)
0x180015b22  mov     ebx, eax
0x180015b24  test    eax, eax
0x180015b26  jns     short loc_180015B3D
0x180015b28  cmp     eax, 80070032h
0x180015b2d  jnz     loc_180015EBF
0x180015b33  mov     ebx, 80070002h
0x180015b38  jmp     loc_180015EBF
0x180015b3d  test    r14, r14
0x180015b40  jz      short loc_180015B5C
0x180015b42  mov     rcx, r14; this
0x180015b45  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x180015b4a  xor     r14d, r14d
0x180015b4d  jmp     short loc_180015B5C
0x180015b4f  mov     r14, [rbp+arg_8]
0x180015b53  jmp     loc_180015EBF
0x180015b58  mov     r14, [rbp+arg_8]
0x180015b5c  mov     rcx, rdi
0x180015b5f  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180015b65  cmp     dword ptr [rax], 837h
0x180015b6b  jz      loc_180015EAF
0x180015b71  mov     rcx, rdi
0x180015b74  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180015b7a  cmp     dword ptr [rax], 838h
0x180015b80  jz      loc_180015EAF
0x180015b86  cmp     rsi, [r13+10h]
0x180015b8a  jnz     short loc_180015B33
0x180015b8c  mov     rcx, rdi
0x180015b8f  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180015b95  cmp     dword ptr [rax], 3F7h
0x180015b9b  jnz     short loc_180015BB1
0x180015b9d  mov     rcx, rsi; this
0x180015ba0  call    ?UnMapNodeAndChildren@ABO_NODE@@QEAAJXZ; ABO_NODE::UnMapNodeAndChildren(void)
0x180015ba5  mov     ebx, eax
0x180015ba7  test    eax, eax
0x180015ba9  js      loc_180015EBF
0x180015baf  jmp     short loc_180015B33
0x180015bb1  mov     rcx, rdi
0x180015bb4  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180015bba  cmp     dword ptr [rax], 3F4h
0x180015bc0  jnz     short loc_180015BE1
0x180015bc2  mov     rcx, rdi
0x180015bc5  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180015bcb  cmp     dword ptr [rax+0Ch], 1
0x180015bcf  jnz     short loc_180015BE1
0x180015bd1  mov     rdx, r12; struct PROPERTY_ENTRY *
0x180015bd4  mov     rcx, r13; this
0x180015bd7  call    ?HandleSiteCommand@SITE_CUSTOM_PROVIDER@@AEAAJPEAVPROPERTY_ENTRY@@@Z; SITE_CUSTOM_PROVIDER::HandleSiteCommand(PROPERTY_ENTRY *)
0x180015bdc  jmp     loc_180015EBD
0x180015be1  mov     rcx, rdi
0x180015be4  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180015bea  cmp     dword ptr [rax], 44Bh
0x180015bf0  jz      loc_180015EAB
0x180015bf6  mov     rcx, rdi
0x180015bf9  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180015bff  cmp     dword ptr [rax], 3F8h
0x180015c05  jz      loc_180015EAB
0x180015c0b  mov     rcx, rdi
0x180015c0e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180015c14  cmp     dword ptr [rax], 1587h
0x180015c1a  jz      loc_180015E9E
0x180015c20  mov     rcx, rdi
0x180015c23  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180015c29  cmp     dword ptr [rax], 1582h
0x180015c2f  jz      loc_180015E9E
0x180015c35  mov     rcx, rdi
0x180015c38  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180015c3e  cmp     dword ptr [rax], 1588h
0x180015c44  jz      loc_180015E9E
0x180015c4a  mov     rcx, rdi
0x180015c4d  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180015c53  cmp     dword ptr [rax], 158Dh
0x180015c59  jz      loc_180015E9E
0x180015c5f  mov     rcx, rdi
0x180015c62  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180015c68  cmp     dword ptr [rax], 870h
0x180015c6e  jz      loc_180015E9E
0x180015c74  mov     rcx, rdi
0x180015c77  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180015c7d  cmp     dword ptr [rax], 158Fh
0x180015c83  jz      loc_180015E9E
0x180015c89  mov     rcx, rdi
0x180015c8c  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180015c92  cmp     dword ptr [rax], 1591h
0x180015c98  jz      loc_180015E9E
0x180015c9e  mov     rcx, rdi
0x180015ca1  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180015ca7  cmp     dword ptr [rax], 871h
0x180015cad  jz      loc_180015E9E
0x180015cb3  mov     rcx, rdi
0x180015cb6  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180015cbc  cmp     dword ptr [rax], 872h
0x180015cc2  jz      loc_180015E9E
0x180015cc8  mov     r9, [r13+18h]; struct INativeConfigurationElement *
0x180015ccc  lea     rdx, aSite; "site"
0x180015cd3  mov     r8, rsi; struct ABO_NODE *
0x180015cd6  mov     rcx, r12; struct PROPERTY_ENTRY *
0x180015cd9  call    ?SetConfigPropertiesBySectionName@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEBGPEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::SetConfigPropertiesBySectionName(PROPERTY_ENTRY *,ushort const *,ABO_NODE *,INativeConfigurationElement *)
0x180015cde  mov     ebx, eax
0x180015ce0  cmp     eax, 80070002h
0x180015ce5  jnz     loc_180015EBF
0x180015ceb  mov     rax, [r13+30h]
0x180015cef  xor     r15d, r15d
0x180015cf2  mov     [rbp+var_20], r15
0x180015cf6  mov     [rbp+var_10], rax
0x180015cfa  test    rax, rax
0x180015cfd  jz      loc_180015DB1
0x180015d03  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x180015d0a  lea     r8, [rbp+var_20]
0x180015d0e  add     rcx, 8
0x180015d12  lea     rdx, aApplication; "application"
0x180015d19  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x180015d1e  mov     r15, [rbp+var_20]
0x180015d22  test    eax, eax
0x180015d24  jnz     loc_180015DAA
0x180015d2a  xor     ebx, ebx
0x180015d2c  mov     dword ptr [rbp+arg_18], eax
0x180015d2f  mov     dword ptr [rbp+arg_8], eax
0x180015d32  cmp     [r15+58h], eax
0x180015d36  jbe     short loc_180015DAA
  ... truncated ...
```
