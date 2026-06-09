# SITES_CUSTOM_PROVIDER::MapSetData(PROPERTY_ENTRY *,ABO_NODE *)

- ea: `0x180013570`
- end: `0x18001391c`
- name: `?MapSetData@SITES_CUSTOM_PROVIDER@@UEAAJPEAVPROPERTY_ENTRY@@PEAVABO_NODE@@@Z`
- size: `940`
- prototype: `__int64 __fastcall(struct INativeConfigurationElement **this, struct PROPERTY_ENTRY *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callees

- `0x180003426`
- `0x180003f14`
- `0x1800047e4`
- `0x18000a6fc`
- `0x180013570`
- `0x180013924`
- `0x1800187e0`
- `0x180018d98`
- `0x1800293b0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800138d0`
- `msvcrt!_wcsicmp` at `0x1800138d0`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800136f7`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800137ee`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800138c0`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800136f7`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800137ee`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800138c0`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800135a6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800135b7`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800135db`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180013630`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180013645`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180013713`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001380a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800138dd`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800135a6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800135b7`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800135db`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180013630`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180013645`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180013713`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001380a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800138dd`

## string_xrefs

- `0x1800137b0`: `virtualDirectory`
- `0x1800137f7`: `virtualDirectory`

## pseudocode

```c
__int64 __fastcall SITES_CUSTOM_PROVIDER::MapSetData(
        struct INativeConfigurationElement **this,
        struct PROPERTY_ENTRY *a2,
        struct ABO_NODE *a3)
{
  BUFFER *v6; // r12
  unsigned int v7; // eax
  int updated; // ebx
  __int64 i; // rbp
  HANDLE_ENTRY *v10; // rbp
  unsigned int Key; // eax
  int v12; // r14d
  const wchar_t *v13; // rax
  _DWORD *v14; // rax
  struct INativeConfigurationElement *v15; // rax
  struct PROPERTY_MAPPING *v16; // rbp
  int v17; // eax
  __int64 v18; // r14
  const wchar_t *v19; // rax
  _DWORD *v20; // rax
  __int64 j; // rdi
  __int64 v22; // rbp
  const wchar_t *Str; // rax
  struct _METADATA_RECORD *Ptr; // rax
  HANDLE_ENTRY *v26; // [rsp+20h] [rbp-48h] BYREF
  struct INativeConfigurationElement *v27; // [rsp+28h] [rbp-40h]
  unsigned int v28; // [rsp+78h] [rbp+10h]
  int v29; // [rsp+78h] [rbp+10h]
  struct PROPERTY_MAPPING *v30; // [rsp+88h] [rbp+20h] BYREF

  if ( !a2 || !a3 )
    return (unsigned int)-2147024809;
  v6 = (struct PROPERTY_ENTRY *)((char *)a2 + 16);
  if ( *(_DWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a2 + 16)) == 1015
    && *((_DWORD *)BUFFER::QueryPtr(v6) + 3) == 2 )
  {
    return (unsigned int)SITES_CUSTOM_PROVIDER::UpgradeToSite((SITES_CUSTOM_PROVIDER *)this, a2, a3);
  }
  updated = 0;
  if ( *(_DWORD *)BUFFER::QueryPtr(v6) == 5519 )
  {
    for ( i = 0; (unsigned int)i < *((_DWORD *)a3 + 10); i = (unsigned int)(i + 1) )
    {
      updated = UpdateSSLProperty(a2, *(struct ABO_NODE **)(*((_QWORD *)a3 + 4) + 8 * i));
      if ( ((updated + 0x80000000) & 0x80000000) == 0 && updated != -2147024894 )
        break;
    }
  }
  else if ( *(_DWORD *)BUFFER::QueryPtr(v6) == 7501 || *(_DWORD *)BUFFER::QueryPtr(v6) == 7502 )
  {
    for ( j = 0; (unsigned int)j < *((_DWORD *)a3 + 10); j = (unsigned int)(j + 1) )
    {
      v22 = *(_QWORD *)(*((_QWORD *)a3 + 4) + 8 * j);
      Str = STRU::QueryStr((STRU *)(v22 + 56));
      if ( !_wcsicmp(Str, L"APPPOOLS") )
      {
        Ptr = (struct _METADATA_RECORD *)BUFFER::QueryPtr(v6);
        updated = ABO_NODE::SetData((ABO_NODE *)v22, Ptr, 0);
        if ( updated < 0 )
          break;
      }
    }
  }
  else if ( a3 == this[2] )
  {
    updated = CUSTOM_PROPERTY_PROVIDER::SetConfigPropertiesBySectionName(a2, L"site", a3, this[5]);
    if ( updated == -2147024894 )
    {
      updated = -2147024809;
      v10 = 0;
      v27 = this[4];
      v26 = 0;
      if ( v27 )
      {
        Key = CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::FindKey(
                (char *)g_pPropertySectionTable + 8,
                L"application",
                &v26);
        v10 = v26;
        if ( Key || (v12 = 0, LODWORD(v30) = 0, v28 = 0, !*((_DWORD *)v26 + 22)) )
        {
LABEL_25:
          v12 = -2147024894;
        }
        else
        {
          while ( 1 )
          {
            v26 = *(HANDLE_ENTRY **)(*((_QWORD *)v10 + 10) + 8LL * Key);
            v13 = STRU::QueryStr((HANDLE_ENTRY *)((char *)v26 + 32));
            if ( !wcscmp_0(v13, L"application") )
            {
              v14 = BUFFER::QueryPtr(v6);
              if ( *((_DWORD *)v26 + 36) == *v14 )
              {
                LODWORD(v30) = 1;
                v12 = CUSTOM_PROPERTY_PROVIDER::SetConfigPropertiesByMapping(a2, v26, a3, v27);
                if ( v12 < 0 )
                  break;
              }
            }
            Key = v28 + 1;
            v28 = Key;
            if ( Key >= *((_DWORD *)v10 + 22) )
            {
              if ( (_DWORD)v30 )
                break;
              goto LABEL_25;
            }
          }
        }
      }
      else
      {
        v12 = -2147024809;
      }
      if ( v10 )
        HANDLE_ENTRY::DereferenceHandleEntry(v10);
      if ( v12 == -2147024894 )
      {
        v15 = this[6];
        v16 = 0;
        v30 = 0;
        v27 = v15;
        if ( v15 )
        {
          v17 = CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::FindKey(
                  (char *)g_pPropertySectionTable + 8,
                  L"virtualDirectory",
                  &v30);
          v16 = v30;
          if ( v17 || (updated = 0, v29 = 0, v18 = 0, !*((_DWORD *)v30 + 22)) )
          {
LABEL_38:
            updated = -2147024894;
          }
          else
          {
            while ( 1 )
            {
              v30 = *(struct PROPERTY_MAPPING **)(*((_QWORD *)v16 + 10) + 8 * v18);
              v19 = STRU::QueryStr((struct PROPERTY_MAPPING *)((char *)v30 + 32));
              if ( !wcscmp_0(v19, L"virtualDirectory") )
              {
                v20 = BUFFER::QueryPtr(v6);
                if ( *((_DWORD *)v30 + 36) == *v20 )
                {
                  v29 = 1;
                  updated = CUSTOM_PROPERTY_PROVIDER::SetConfigPropertiesByMapping(a2, v30, a3, v27);
                  if ( updated < 0 )
                    break;
                }
              }
              v18 = (unsigned int)(v18 + 1);
              if ( (unsigned int)v18 >= *((_DWORD *)v16 + 22) )
              {
                if ( v29 )
                  break;
                goto LABEL_38;
              }
            }
          }
        }
        if ( v16 )
          HANDLE_ENTRY::DereferenceHandleEntry(v16);
        if ( updated == -2147024894 )
          updated = CUSTOM_PROPERTY_PROVIDER::SetConfigPropertiesBySectionName(a2, L"log", a3, this[7]);
      }
      else
      {
        updated = v12;
      }
    }
    v7 = CUSTOM_PROPERTY_PROVIDER::SetConfigPropertiesBySectionName(a2, L"log", a3, this[7]);
    if ( (int)(v7 + 0x80000000) >= 0 && v7 != -2147024894 )
      return v7;
  }
  else
  {
    return (unsigned int)-2147024894;
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180013570  mov     [rsp+arg_0], rbx
0x180013575  push    rbp
0x180013576  push    rsi
0x180013577  push    rdi
0x180013578  push    r12
0x18001357a  push    r13
0x18001357c  push    r14
0x18001357e  push    r15
0x180013580  sub     rsp, 30h
0x180013584  mov     rsi, r8
0x180013587  mov     r15, rdx
0x18001358a  mov     r13, rcx
0x18001358d  test    rdx, rdx
0x180013590  jz      loc_180013900
0x180013596  test    r8, r8
0x180013599  jz      loc_180013900
0x18001359f  lea     r12, [rdx+10h]
0x1800135a3  mov     rcx, r12
0x1800135a6  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800135ac  cmp     dword ptr [rax], 3F7h
0x1800135b2  jnz     short loc_1800135D6
0x1800135b4  mov     rcx, r12
0x1800135b7  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800135bd  cmp     dword ptr [rax+0Ch], 2
0x1800135c1  jnz     short loc_1800135D6
0x1800135c3  mov     r8, rsi; struct ABO_NODE *
0x1800135c6  mov     rdx, r15; struct PROPERTY_ENTRY *
0x1800135c9  mov     rcx, r13; this
0x1800135cc  call    ?UpgradeToSite@SITES_CUSTOM_PROVIDER@@AEAAJPEAVPROPERTY_ENTRY@@PEAVABO_NODE@@@Z; SITES_CUSTOM_PROVIDER::UpgradeToSite(PROPERTY_ENTRY *,ABO_NODE *)
0x1800135d1  jmp     loc_1800138A9
0x1800135d6  mov     rcx, r12
0x1800135d9  xor     ebx, ebx
0x1800135db  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800135e1  cmp     dword ptr [rax], 158Fh
0x1800135e7  jnz     short loc_18001362D
0x1800135e9  xor     ebp, ebp
0x1800135eb  cmp     [rsi+28h], ebx
0x1800135ee  jbe     loc_180013905
0x1800135f4  mov     edi, 80070002h
0x1800135f9  mov     r14d, 80000000h
0x1800135ff  mov     rdx, [rsi+20h]
0x180013603  mov     rcx, r15; struct PROPERTY_ENTRY *
0x180013606  mov     rdx, [rdx+rbp*8]; struct ABO_NODE *
0x18001360a  call    ?UpdateSSLProperty@@YAJPEAVPROPERTY_ENTRY@@PEAVABO_NODE@@@Z; UpdateSSLProperty(PROPERTY_ENTRY *,ABO_NODE *)
0x18001360f  mov     ebx, eax
0x180013611  add     eax, r14d
0x180013614  test    r14d, eax
0x180013617  jnz     short loc_180013621
0x180013619  cmp     ebx, edi
0x18001361b  jnz     loc_180013905
0x180013621  inc     ebp
0x180013623  cmp     ebp, [rsi+28h]
0x180013626  jb      short loc_1800135FF
0x180013628  jmp     loc_180013905
0x18001362d  mov     rcx, r12
0x180013630  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180013636  cmp     dword ptr [rax], 1D4Dh
0x18001363c  jz      loc_1800138AD
0x180013642  mov     rcx, r12
0x180013645  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001364b  cmp     dword ptr [rax], 1D4Eh
0x180013651  jz      loc_1800138AD
0x180013657  cmp     rsi, [r13+10h]
0x18001365b  jz      short loc_180013667
0x18001365d  mov     ebx, 80070002h
0x180013662  jmp     loc_180013905
0x180013667  mov     r9, [r13+28h]; struct INativeConfigurationElement *
0x18001366b  lea     rdx, aSite; "site"
0x180013672  mov     r8, rsi; struct ABO_NODE *
0x180013675  mov     rcx, r15; struct PROPERTY_ENTRY *
0x180013678  call    ?SetConfigPropertiesBySectionName@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEBGPEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::SetConfigPropertiesBySectionName(PROPERTY_ENTRY *,ushort const *,ABO_NODE *,INativeConfigurationElement *)
0x18001367d  mov     edi, 80070002h
0x180013682  mov     ebx, eax
0x180013684  cmp     eax, edi
0x180013686  jnz     loc_180013880
0x18001368c  mov     rax, [r13+20h]
0x180013690  lea     ebx, [rdi+55h]
0x180013693  xor     ebp, ebp
0x180013695  mov     [rsp+68h+var_40], rax
0x18001369a  mov     [rsp+68h+var_48], rbp
0x18001369f  test    rax, rax
0x1800136a2  jz      loc_180013768
0x1800136a8  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x1800136af  lea     r8, [rsp+68h+var_48]
0x1800136b4  add     rcx, 8
0x1800136b8  lea     rdx, aApplication; "application"
0x1800136bf  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x1800136c4  mov     rbp, [rsp+68h+var_48]
0x1800136c9  test    eax, eax
0x1800136cb  jnz     loc_180013763
0x1800136d1  xor     r14d, r14d
0x1800136d4  mov     dword ptr [rsp+68h+arg_18], eax
0x1800136db  mov     [rsp+68h+arg_8], eax
0x1800136df  cmp     [rbp+58h], eax
0x1800136e2  jbe     short loc_180013763
0x1800136e4  mov     ecx, eax
0x1800136e6  mov     rax, [rbp+50h]
0x1800136ea  mov     rax, [rax+rcx*8]
0x1800136ee  mov     [rsp+68h+var_48], rax
0x1800136f3  lea     rcx, [rax+20h]
0x1800136f7  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x1800136fd  mov     rcx, rax; String1
0x180013700  lea     rdx, aApplication; "application"
0x180013707  call    wcscmp_0
0x18001370c  test    eax, eax
0x18001370e  jnz     short loc_18001374A
0x180013710  mov     rcx, r12
0x180013713  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180013719  mov     rdx, [rsp+68h+var_48]; struct PROPERTY_MAPPING *
0x18001371e  mov     ecx, [rax]
0x180013720  cmp     [rdx+90h], ecx
0x180013726  jnz     short loc_18001374A
0x180013728  mov     r9, [rsp+68h+var_40]; struct INativeConfigurationElement *
0x18001372d  mov     r8, rsi; struct ABO_NODE *
0x180013730  mov     rcx, r15; struct PROPERTY_ENTRY *
0x180013733  mov     dword ptr [rsp+68h+arg_18], 1
0x18001373e  call    ?SetConfigPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::SetConfigPropertiesByMapping(PROPERTY_ENTRY *,PROPERTY_MAPPING *,ABO_NODE *,INativeConfigurationElement *)
0x180013743  mov     r14d, eax
0x180013746  test    eax, eax
0x180013748  js      short loc_18001376B
0x18001374a  mov     eax, [rsp+68h+arg_8]
0x18001374e  inc     eax
0x180013750  mov     [rsp+68h+arg_8], eax
0x180013754  cmp     eax, [rbp+58h]
0x180013757  jb      short loc_1800136E4
0x180013759  cmp     dword ptr [rsp+68h+arg_18], 0
0x180013761  jnz     short loc_18001376B
0x180013763  mov     r14d, edi
0x180013766  jmp     short loc_18001376B
0x180013768  mov     r14d, ebx
0x18001376b  test    rbp, rbp
0x18001376e  jz      short loc_180013778
0x180013770  mov     rcx, rbp; this
0x180013773  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x180013778  cmp     r14d, edi
0x18001377b  jnz     loc_18001387D
0x180013781  mov     rax, [r13+30h]
0x180013785  xor     ebp, ebp
0x180013787  mov     [rsp+68h+arg_18], rbp
0x18001378f  mov     [rsp+68h+var_40], rax
0x180013794  test    rax, rax
0x180013797  jz      loc_180013852
0x18001379d  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x1800137a4  lea     r8, [rsp+68h+arg_18]
0x1800137ac  add     rcx, 8
0x1800137b0  lea     rdx, aVirtualdirecto_0; "virtualDirectory"
0x1800137b7  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x1800137bc  mov     rbp, [rsp+68h+arg_18]
0x1800137c4  test    eax, eax
0x1800137c6  jnz     loc_180013850
0x1800137cc  xor     ebx, ebx
0x1800137ce  mov     [rsp+68h+arg_8], eax
0x1800137d2  xor     r14d, r14d
0x1800137d5  cmp     [rbp+58h], eax
0x1800137d8  jbe     short loc_180013850
0x1800137da  mov     rax, [rbp+50h]
0x1800137de  mov     rax, [rax+r14*8]
0x1800137e2  mov     [rsp+68h+arg_18], rax
0x1800137ea  lea     rcx, [rax+20h]
0x1800137ee  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x1800137f4  mov     rcx, rax; String1
0x1800137f7  lea     rdx, aVirtualdirecto_0; "virtualDirectory"
0x1800137fe  call    wcscmp_0
0x180013803  test    eax, eax
0x180013805  jnz     short loc_180013840
0x180013807  mov     rcx, r12
0x18001380a  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180013810  mov     rdx, [rsp+68h+arg_18]; struct PROPERTY_MAPPING *
0x180013818  mov     ecx, [rax]
0x18001381a  cmp     [rdx+90h], ecx
0x180013820  jnz     short loc_180013840
0x180013822  mov     r9, [rsp+68h+var_40]; struct INativeConfigurationElement *
0x180013827  mov     r8, rsi; struct ABO_NODE *
0x18001382a  mov     rcx, r15; struct PROPERTY_ENTRY *
0x18001382d  mov     [rsp+68h+arg_8], 1
0x180013835  call    ?SetConfigPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::SetConfigPropertiesByMapping(PROPERTY_ENTRY *,PROPERTY_MAPPING *,ABO_NODE *,INativeConfigurationElement *)
0x18001383a  mov     ebx, eax
0x18001383c  test    eax, eax
0x18001383e  js      short loc_180013852
0x180013840  inc     r14d
0x180013843  cmp     r14d, [rbp+58h]
0x180013847  jb      short loc_1800137DA
0x180013849  cmp     [rsp+68h+arg_8], 0
0x18001384e  jnz     short loc_180013852
0x180013850  mov     ebx, edi
0x180013852  test    rbp, rbp
0x180013855  jz      short loc_18001385F
0x180013857  mov     rcx, rbp; this
0x18001385a  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18001385f  cmp     ebx, edi
0x180013861  jnz     short loc_180013880
0x180013863  mov     r9, [r13+38h]; struct INativeConfigurationElement *
0x180013867  lea     rdx, aLog; "log"
0x18001386e  mov     r8, rsi; struct ABO_NODE *
0x180013871  mov     rcx, r15; struct PROPERTY_ENTRY *
0x180013874  call    ?SetConfigPropertiesBySectionName@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEBGPEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::SetConfigPropertiesBySectionName(PROPERTY_ENTRY *,ushort const *,ABO_NODE *,INativeConfigurationElement *)
0x180013879  mov     ebx, eax
0x18001387b  jmp     short loc_180013880
0x18001387d  mov     ebx, r14d
0x180013880  mov     r9, [r13+38h]; struct INativeConfigurationElement *
0x180013884  lea     rdx, aLog; "log"
0x18001388b  mov     r8, rsi; struct ABO_NODE *
0x18001388e  mov     rcx, r15; struct PROPERTY_ENTRY *
0x180013891  call    ?SetConfigPropertiesBySectionName@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEBGPEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::SetConfigPropertiesBySectionName(PROPERTY_ENTRY *,ushort const *,ABO_NODE *,INativeConfigurationElement *)
0x180013896  mov     r14d, 80000000h
0x18001389c  lea     ecx, [rax+r14]
0x1800138a0  test    r14d, ecx
0x1800138a3  jnz     short loc_180013905
0x1800138a5  cmp     eax, edi
0x1800138a7  jz      short loc_180013905
0x1800138a9  mov     ebx, eax
0x1800138ab  jmp     short loc_180013905
0x1800138ad  xor     edi, edi
0x1800138af  cmp     [rsi+28h], ebx
0x1800138b2  jbe     short loc_180013905
0x1800138b4  mov     rax, [rsi+20h]
0x1800138b8  mov     rbp, [rax+rdi*8]
0x1800138bc  lea     rcx, [rbp+38h]
0x1800138c0  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x1800138c6  mov     rcx, rax; String1
0x1800138c9  lea     rdx, aApppools; "APPPOOLS"
0x1800138d0  call    cs:__imp__wcsicmp
0x1800138d6  test    eax, eax
0x1800138d8  jnz     short loc_1800138F7
0x1800138da  mov     rcx, r12
0x1800138dd  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800138e3  xor     r8d, r8d; int
0x1800138e6  mov     rcx, rbp; this
0x1800138e9  mov     rdx, rax; struct _METADATA_RECORD *
0x1800138ec  call    ?SetData@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@H@Z; ABO_NODE::SetData(_METADATA_RECORD *,int)
0x1800138f1  mov     ebx, eax
0x1800138f3  test    eax, eax
0x1800138f5  js      short loc_180013905
0x1800138f7  inc     edi
0x1800138f9  cmp     edi, [rsi+28h]
0x1800138fc  jb      short loc_1800138B4
0x1800138fe  jmp     short loc_180013905
0x180013900  mov     ebx, 80070057h
0x180013905  mov     eax, ebx
0x180013907  mov     rbx, [rsp+68h+arg_0]
0x18001390c  add     rsp, 30h
0x180013910  pop     r15
0x180013912  pop     r14
0x180013914  pop     r13
0x180013916  pop     r12
0x180013918  pop     rdi
0x180013919  pop     rsi
0x18001391a  pop     rbp
0x18001391b  retn
```
