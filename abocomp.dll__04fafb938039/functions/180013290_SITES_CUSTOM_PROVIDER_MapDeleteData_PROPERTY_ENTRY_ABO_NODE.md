# SITES_CUSTOM_PROVIDER::MapDeleteData(PROPERTY_ENTRY *,ABO_NODE *)

- ea: `0x180013290`
- end: `0x180013562`
- name: `?MapDeleteData@SITES_CUSTOM_PROVIDER@@UEAAJPEAVPROPERTY_ENTRY@@PEAVABO_NODE@@@Z`
- size: `722`
- prototype: `int(SITES_CUSTOM_PROVIDER *__hidden this, struct PROPERTY_ENTRY *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180003426`
- `0x180003f14`
- `0x1800047e4`
- `0x180013290`
- `0x18001775c`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180013331`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180013405`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800134d4`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180013331`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180013405`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800134d4`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001334e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180013422`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800134f1`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001334e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180013422`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800134f1`

## string_xrefs

- `0x1800134a3`: `virtualDirectory`
- `0x1800134dd`: `virtualDirectory`

## pseudocode

```c
__int64 __fastcall SITES_CUSTOM_PROVIDER::MapDeleteData(
        SITES_CUSTOM_PROVIDER *this,
        struct PROPERTY_ENTRY *a2,
        struct ABO_NODE *a3)
{
  unsigned int v5; // ebx
  int v6; // edi
  HANDLE_ENTRY *v7; // rsi
  int Key; // eax
  int v9; // r14d
  __int64 v10; // r12
  const wchar_t *Str; // rax
  _DWORD *Ptr; // rax
  struct INativeConfigurationElement *v13; // rax
  HANDLE_ENTRY *v14; // rsi
  int v15; // eax
  __int64 v16; // r12
  const wchar_t *v17; // rax
  _DWORD *v18; // rax
  struct INativeConfigurationElement *v19; // r12
  struct PROPERTY_MAPPING *v20; // rsi
  int v21; // eax
  int v22; // r15d
  __int64 v23; // r14
  const wchar_t *v24; // rax
  _DWORD *v25; // rax
  struct INativeConfigurationElement *v27; // [rsp+20h] [rbp-10h]
  struct INativeConfigurationElement *v28; // [rsp+20h] [rbp-10h]
  struct PROPERTY_MAPPING *v29; // [rsp+78h] [rbp+48h] BYREF
  struct ABO_NODE *v30; // [rsp+80h] [rbp+50h]
  HANDLE_ENTRY *v31; // [rsp+88h] [rbp+58h] BYREF

  v30 = a3;
  if ( a2 && a3 )
  {
    v5 = -2147024894;
    if ( a3 == *((struct ABO_NODE **)this + 2) )
    {
      v6 = -2147024809;
      v7 = 0;
      v27 = (struct INativeConfigurationElement *)*((_QWORD *)this + 5);
      v31 = 0;
      if ( v27 )
      {
        Key = CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::FindKey(
                (char *)g_pPropertySectionTable + 8,
                L"site",
                &v31);
        v7 = v31;
        if ( Key || (v9 = 0, LODWORD(v29) = 0, v10 = 0, !*((_DWORD *)v31 + 22)) )
        {
LABEL_12:
          v9 = -2147024894;
        }
        else
        {
          while ( 1 )
          {
            v31 = *(HANDLE_ENTRY **)(*((_QWORD *)v7 + 10) + 8 * v10);
            Str = STRU::QueryStr((HANDLE_ENTRY *)((char *)v31 + 32));
            if ( !wcscmp_0(Str, L"site") )
            {
              Ptr = BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a2 + 16));
              if ( *((_DWORD *)v31 + 36) == *Ptr )
              {
                LODWORD(v29) = 1;
                v9 = CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(a2, v31, v30, v27);
                if ( v9 < 0 )
                  break;
              }
            }
            v10 = (unsigned int)(v10 + 1);
            if ( (unsigned int)v10 >= *((_DWORD *)v7 + 22) )
            {
              if ( (_DWORD)v29 )
                break;
              goto LABEL_12;
            }
          }
        }
      }
      else
      {
        v9 = -2147024809;
      }
      if ( v7 )
        HANDLE_ENTRY::DereferenceHandleEntry(v7);
      if ( v9 != -2147024894 )
        return (unsigned int)v9;
      v13 = (struct INativeConfigurationElement *)*((_QWORD *)this + 4);
      v14 = 0;
      v31 = 0;
      v28 = v13;
      if ( v13 )
      {
        v15 = CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::FindKey(
                (char *)g_pPropertySectionTable + 8,
                L"application",
                &v31);
        v14 = v31;
        if ( v15 || (v9 = 0, LODWORD(v29) = 0, v16 = 0, !*((_DWORD *)v31 + 22)) )
        {
LABEL_25:
          v9 = -2147024894;
        }
        else
        {
          while ( 1 )
          {
            v31 = *(HANDLE_ENTRY **)(*((_QWORD *)v14 + 10) + 8 * v16);
            v17 = STRU::QueryStr((HANDLE_ENTRY *)((char *)v31 + 32));
            if ( !wcscmp_0(v17, L"application") )
            {
              v18 = BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a2 + 16));
              if ( *((_DWORD *)v31 + 36) == *v18 )
              {
                LODWORD(v29) = 1;
                v9 = CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(a2, v31, v30, v28);
                if ( v9 < 0 )
                  break;
              }
            }
            v16 = (unsigned int)(v16 + 1);
            if ( (unsigned int)v16 >= *((_DWORD *)v14 + 22) )
            {
              if ( (_DWORD)v29 )
                break;
              goto LABEL_25;
            }
          }
        }
      }
      else
      {
        v9 = -2147024809;
      }
      if ( v14 )
        HANDLE_ENTRY::DereferenceHandleEntry(v14);
      if ( v9 == -2147024894 )
      {
        v19 = (struct INativeConfigurationElement *)*((_QWORD *)this + 6);
        v20 = 0;
        v29 = 0;
        if ( v19 )
        {
          v21 = CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::FindKey(
                  (char *)g_pPropertySectionTable + 8,
                  L"virtualDirectory",
                  &v29);
          v20 = v29;
          if ( v21 || (v6 = 0, v22 = 0, v23 = 0, !*((_DWORD *)v29 + 22)) )
          {
LABEL_38:
            v6 = -2147024894;
          }
          else
          {
            while ( 1 )
            {
              v29 = *(struct PROPERTY_MAPPING **)(*((_QWORD *)v20 + 10) + 8 * v23);
              v24 = STRU::QueryStr((struct PROPERTY_MAPPING *)((char *)v29 + 32));
              if ( !wcscmp_0(v24, L"virtualDirectory") )
              {
                v25 = BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a2 + 16));
                if ( *((_DWORD *)v29 + 36) == *v25 )
                {
                  v22 = 1;
                  v6 = CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(a2, v29, v30, v19);
                  if ( v6 < 0 )
                    break;
                }
              }
              v23 = (unsigned int)(v23 + 1);
              if ( (unsigned int)v23 >= *((_DWORD *)v20 + 22) )
              {
                if ( v22 )
                  break;
                goto LABEL_38;
              }
            }
          }
        }
        if ( v20 )
          HANDLE_ENTRY::DereferenceHandleEntry(v20);
        return (unsigned int)v6;
      }
      else
      {
        return (unsigned int)v9;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v5;
}

```

## disassembly

```asm
0x180013290  mov     [rsp-38h+arg_0], rbx
0x180013295  mov     [rsp-38h+arg_10], r8
0x18001329a  push    rbp
0x18001329b  push    rsi
0x18001329c  push    rdi
0x18001329d  push    r12
0x18001329f  push    r13
0x1800132a1  push    r14
0x1800132a3  push    r15
0x1800132a5  mov     rbp, rsp
0x1800132a8  sub     rsp, 30h
0x1800132ac  mov     rax, r8
0x1800132af  mov     r13, rdx
0x1800132b2  mov     r15, rcx
0x1800132b5  test    rdx, rdx
0x1800132b8  jz      loc_180013546
0x1800132be  test    rax, rax
0x1800132c1  jz      loc_180013546
0x1800132c7  mov     ebx, 80070002h
0x1800132cc  cmp     rax, [rcx+10h]
0x1800132d0  jnz     loc_18001354B
0x1800132d6  mov     rax, [rcx+28h]
0x1800132da  lea     edi, [rbx+55h]
0x1800132dd  xor     esi, esi
0x1800132df  mov     [rbp+var_10], rax
0x1800132e3  mov     [rbp+arg_18], rsi
0x1800132e7  test    rax, rax
0x1800132ea  jz      loc_180013394
0x1800132f0  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x1800132f7  lea     r8, [rbp+arg_18]
0x1800132fb  add     rcx, 8
0x1800132ff  lea     rdx, aSite; "site"
0x180013306  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x18001330b  mov     rsi, [rbp+arg_18]
0x18001330f  test    eax, eax
0x180013311  jnz     short loc_18001338F
0x180013313  xor     r14d, r14d
0x180013316  mov     dword ptr [rbp+arg_8], eax
0x180013319  xor     r12d, r12d
0x18001331c  cmp     [rsi+58h], eax
0x18001331f  jbe     short loc_18001338F
0x180013321  mov     rax, [rsi+50h]
0x180013325  mov     rax, [rax+r12*8]
0x180013329  mov     [rbp+arg_18], rax
0x18001332d  lea     rcx, [rax+20h]
0x180013331  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180013337  mov     rcx, rax; String1
0x18001333a  lea     rdx, aSite; "site"
0x180013341  call    wcscmp_0
0x180013346  test    eax, eax
0x180013348  jnz     short loc_180013380
0x18001334a  lea     rcx, [r13+10h]
0x18001334e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180013354  mov     rdx, [rbp+arg_18]; struct PROPERTY_MAPPING *
0x180013358  mov     ecx, [rax]
0x18001335a  cmp     [rdx+90h], ecx
0x180013360  jnz     short loc_180013380
0x180013362  mov     r9, [rbp+var_10]; struct INativeConfigurationElement *
0x180013366  mov     rcx, r13; struct PROPERTY_ENTRY *
0x180013369  mov     r8, [rbp+arg_10]; struct ABO_NODE *
0x18001336d  mov     dword ptr [rbp+arg_8], 1
0x180013374  call    ?DeleteConfigPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(PROPERTY_ENTRY *,PROPERTY_MAPPING *,ABO_NODE *,INativeConfigurationElement *)
0x180013379  mov     r14d, eax
0x18001337c  test    eax, eax
0x18001337e  js      short loc_180013397
0x180013380  inc     r12d
0x180013383  cmp     r12d, [rsi+58h]
0x180013387  jb      short loc_180013321
0x180013389  cmp     dword ptr [rbp+arg_8], 0
0x18001338d  jnz     short loc_180013397
0x18001338f  mov     r14d, ebx
0x180013392  jmp     short loc_180013397
0x180013394  mov     r14d, edi
0x180013397  test    rsi, rsi
0x18001339a  jz      short loc_1800133A4
0x18001339c  mov     rcx, rsi; this
0x18001339f  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x1800133a4  cmp     r14d, ebx
0x1800133a7  jnz     loc_180013541
0x1800133ad  mov     rax, [r15+20h]
0x1800133b1  xor     esi, esi
0x1800133b3  mov     [rbp+arg_18], rsi
0x1800133b7  mov     [rbp+var_10], rax
0x1800133bb  test    rax, rax
0x1800133be  jz      loc_180013468
0x1800133c4  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x1800133cb  lea     r8, [rbp+arg_18]
0x1800133cf  add     rcx, 8
0x1800133d3  lea     rdx, aApplication; "application"
0x1800133da  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x1800133df  mov     rsi, [rbp+arg_18]
0x1800133e3  test    eax, eax
0x1800133e5  jnz     short loc_180013463
0x1800133e7  xor     r14d, r14d
0x1800133ea  mov     dword ptr [rbp+arg_8], eax
0x1800133ed  xor     r12d, r12d
0x1800133f0  cmp     [rsi+58h], eax
0x1800133f3  jbe     short loc_180013463
0x1800133f5  mov     rax, [rsi+50h]
0x1800133f9  mov     rax, [rax+r12*8]
0x1800133fd  mov     [rbp+arg_18], rax
0x180013401  lea     rcx, [rax+20h]
0x180013405  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18001340b  mov     rcx, rax; String1
0x18001340e  lea     rdx, aApplication; "application"
0x180013415  call    wcscmp_0
0x18001341a  test    eax, eax
0x18001341c  jnz     short loc_180013454
0x18001341e  lea     rcx, [r13+10h]
0x180013422  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180013428  mov     rdx, [rbp+arg_18]; struct PROPERTY_MAPPING *
0x18001342c  mov     ecx, [rax]
0x18001342e  cmp     [rdx+90h], ecx
0x180013434  jnz     short loc_180013454
0x180013436  mov     r9, [rbp+var_10]; struct INativeConfigurationElement *
0x18001343a  mov     rcx, r13; struct PROPERTY_ENTRY *
0x18001343d  mov     r8, [rbp+arg_10]; struct ABO_NODE *
0x180013441  mov     dword ptr [rbp+arg_8], 1
0x180013448  call    ?DeleteConfigPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(PROPERTY_ENTRY *,PROPERTY_MAPPING *,ABO_NODE *,INativeConfigurationElement *)
0x18001344d  mov     r14d, eax
0x180013450  test    eax, eax
0x180013452  js      short loc_18001346B
0x180013454  inc     r12d
0x180013457  cmp     r12d, [rsi+58h]
0x18001345b  jb      short loc_1800133F5
0x18001345d  cmp     dword ptr [rbp+arg_8], 0
0x180013461  jnz     short loc_18001346B
0x180013463  mov     r14d, ebx
0x180013466  jmp     short loc_18001346B
0x180013468  mov     r14d, edi
0x18001346b  test    rsi, rsi
0x18001346e  jz      short loc_180013478
0x180013470  mov     rcx, rsi; this
0x180013473  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x180013478  cmp     r14d, ebx
0x18001347b  jnz     loc_180013541
0x180013481  mov     r12, [r15+30h]
0x180013485  xor     esi, esi
0x180013487  mov     [rbp+arg_8], rsi
0x18001348b  test    r12, r12
0x18001348e  jz      loc_180013530
0x180013494  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x18001349b  lea     r8, [rbp+arg_8]
0x18001349f  add     rcx, 8
0x1800134a3  lea     rdx, aVirtualdirecto_0; "virtualDirectory"
0x1800134aa  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x1800134af  mov     rsi, [rbp+arg_8]
0x1800134b3  test    eax, eax
0x1800134b5  jnz     short loc_18001352E
0x1800134b7  xor     edi, edi
0x1800134b9  xor     r15d, r15d
0x1800134bc  xor     r14d, r14d
0x1800134bf  cmp     [rsi+58h], edi
0x1800134c2  jbe     short loc_18001352E
0x1800134c4  mov     rax, [rsi+50h]
0x1800134c8  mov     rax, [rax+r14*8]
0x1800134cc  mov     [rbp+arg_8], rax
0x1800134d0  lea     rcx, [rax+20h]
0x1800134d4  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x1800134da  mov     rcx, rax; String1
0x1800134dd  lea     rdx, aVirtualdirecto_0; "virtualDirectory"
0x1800134e4  call    wcscmp_0
0x1800134e9  test    eax, eax
0x1800134eb  jnz     short loc_180013520
0x1800134ed  lea     rcx, [r13+10h]
0x1800134f1  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800134f7  mov     rdx, [rbp+arg_8]; struct PROPERTY_MAPPING *
0x1800134fb  mov     ecx, [rax]
0x1800134fd  cmp     [rdx+90h], ecx
0x180013503  jnz     short loc_180013520
0x180013505  mov     r8, [rbp+arg_10]; struct ABO_NODE *
0x180013509  mov     r9, r12; struct INativeConfigurationElement *
0x18001350c  mov     rcx, r13; struct PROPERTY_ENTRY *
0x18001350f  mov     r15d, 1
0x180013515  call    ?DeleteConfigPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(PROPERTY_ENTRY *,PROPERTY_MAPPING *,ABO_NODE *,INativeConfigurationElement *)
0x18001351a  mov     edi, eax
0x18001351c  test    eax, eax
0x18001351e  js      short loc_180013530
0x180013520  inc     r14d
0x180013523  cmp     r14d, [rsi+58h]
0x180013527  jb      short loc_1800134C4
0x180013529  test    r15d, r15d
0x18001352c  jnz     short loc_180013530
0x18001352e  mov     edi, ebx
0x180013530  test    rsi, rsi
0x180013533  jz      short loc_18001353D
0x180013535  mov     rcx, rsi; this
0x180013538  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18001353d  mov     ebx, edi
0x18001353f  jmp     short loc_18001354B
0x180013541  mov     ebx, r14d
0x180013544  jmp     short loc_18001354B
0x180013546  mov     ebx, 80070057h
0x18001354b  mov     eax, ebx
0x18001354d  mov     rbx, [rsp+30h+arg_0]
0x180013552  add     rsp, 30h
0x180013556  pop     r15
0x180013558  pop     r14
0x18001355a  pop     r13
0x18001355c  pop     r12
0x18001355e  pop     rdi
0x18001355f  pop     rsi
0x180013560  pop     rbp
0x180013561  retn
```
