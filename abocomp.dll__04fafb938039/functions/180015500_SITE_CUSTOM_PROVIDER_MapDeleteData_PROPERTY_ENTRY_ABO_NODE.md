# SITE_CUSTOM_PROVIDER::MapDeleteData(PROPERTY_ENTRY *,ABO_NODE *)

- ea: `0x180015500`
- end: `0x18001583c`
- name: `?MapDeleteData@SITE_CUSTOM_PROVIDER@@UEAAJPEAVPROPERTY_ENTRY@@PEAVABO_NODE@@@Z`
- size: `828`
- prototype: `__int64 __fastcall(struct ABO_NODE **this, struct PROPERTY_ENTRY *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config`

## callees

- `0x180003426`
- `0x180003f14`
- `0x1800047e4`
- `0x18000ace4`
- `0x180015500`
- `0x18001775c`
- `0x1800179d0`
- `0x18002742c`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800156b2`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001579c`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800156b2`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001579c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015546`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015566`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001557b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015590`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800155a5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800155ba`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800155cf`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800155e4`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800155f9`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001560e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800156ce`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800157b8`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015546`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015566`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001557b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180015590`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800155a5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800155ba`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800155cf`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800155e4`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800155f9`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001560e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800156ce`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800157b8`

## string_xrefs

- `0x180015769`: `virtualDirectory`
- `0x1800157a5`: `virtualDirectory`

## pseudocode

```c
__int64 __fastcall SITE_CUSTOM_PROVIDER::MapDeleteData(
        struct ABO_NODE **this,
        struct PROPERTY_ENTRY *a2,
        struct ABO_NODE *a3)
{
  int v6; // ebx
  BUFFER *v7; // rdi
  HANDLE_ENTRY *v9; // rsi
  unsigned int Key; // eax
  int v11; // r14d
  const wchar_t *Str; // rax
  _DWORD *Ptr; // rax
  struct INativeConfigurationElement *v14; // rax
  struct PROPERTY_MAPPING *v15; // rsi
  int v16; // eax
  int v17; // r12d
  __int64 v18; // r14
  const wchar_t *v19; // rax
  _DWORD *v20; // rax
  HANDLE_ENTRY *v22; // [rsp+20h] [rbp-48h] BYREF
  struct INativeConfigurationElement *v23; // [rsp+28h] [rbp-40h]
  struct PROPERTY_MAPPING *v24; // [rsp+78h] [rbp+10h] BYREF
  struct INativeConfigurationElement *v25; // [rsp+88h] [rbp+20h]

  if ( !a2 || !a3 )
    return (unsigned int)-2147024809;
  if ( a3 != this[2] )
    return (unsigned int)-2147024894;
  v7 = (struct PROPERTY_ENTRY *)((char *)a2 + 16);
  if ( *(_DWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a2 + 16)) == 1015 )
    return (unsigned int)ABO_NODE::UnMapNodeAndChildren(a3);
  if ( *(_DWORD *)BUFFER::QueryPtr(v7) == 5511
    || *(_DWORD *)BUFFER::QueryPtr(v7) == 5506
    || *(_DWORD *)BUFFER::QueryPtr(v7) == 5512
    || *(_DWORD *)BUFFER::QueryPtr(v7) == 5517
    || *(_DWORD *)BUFFER::QueryPtr(v7) == 2160
    || *(_DWORD *)BUFFER::QueryPtr(v7) == 5519
    || *(_DWORD *)BUFFER::QueryPtr(v7) == 5521
    || *(_DWORD *)BUFFER::QueryPtr(v7) == 2161
    || *(_DWORD *)BUFFER::QueryPtr(v7) == 2162 )
  {
    return (unsigned int)DeleteSSLProperty(a2, a3);
  }
  v6 = CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesBySectionName(a2, L"site", a3, this[3]);
  if ( v6 == -2147024894 )
  {
    v6 = -2147024809;
    v9 = 0;
    v23 = this[6];
    v22 = 0;
    if ( v23 )
    {
      Key = CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::FindKey(
              (char *)g_pPropertySectionTable + 8,
              L"application",
              &v22);
      v9 = v22;
      if ( Key || (v11 = 0, LODWORD(v25) = 0, LODWORD(v24) = 0, !*((_DWORD *)v22 + 22)) )
      {
LABEL_26:
        v11 = -2147024894;
      }
      else
      {
        while ( 1 )
        {
          v22 = *(HANDLE_ENTRY **)(*((_QWORD *)v9 + 10) + 8LL * Key);
          Str = STRU::QueryStr((HANDLE_ENTRY *)((char *)v22 + 32));
          if ( !wcscmp_0(Str, L"application") )
          {
            Ptr = BUFFER::QueryPtr(v7);
            if ( *((_DWORD *)v22 + 36) == *Ptr )
            {
              LODWORD(v25) = 1;
              v11 = CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(a2, v22, a3, v23);
              if ( v11 < 0 )
                break;
            }
          }
          Key = (_DWORD)v24 + 1;
          LODWORD(v24) = Key;
          if ( Key >= *((_DWORD *)v9 + 22) )
          {
            if ( (_DWORD)v25 )
              break;
            goto LABEL_26;
          }
        }
      }
    }
    else
    {
      v11 = -2147024809;
    }
    if ( v9 )
      HANDLE_ENTRY::DereferenceHandleEntry(v9);
    if ( v11 == -2147024894 )
    {
      v14 = this[5];
      v15 = 0;
      v24 = 0;
      v25 = v14;
      if ( v14 )
      {
        v16 = CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::FindKey(
                (char *)g_pPropertySectionTable + 8,
                L"virtualDirectory",
                &v24);
        v15 = v24;
        if ( v16 || (v6 = 0, v17 = 0, v18 = 0, !*((_DWORD *)v24 + 22)) )
        {
LABEL_39:
          v6 = -2147024894;
        }
        else
        {
          while ( 1 )
          {
            v24 = *(struct PROPERTY_MAPPING **)(*((_QWORD *)v15 + 10) + 8 * v18);
            v19 = STRU::QueryStr((struct PROPERTY_MAPPING *)((char *)v24 + 32));
            if ( !wcscmp_0(v19, L"virtualDirectory") )
            {
              v20 = BUFFER::QueryPtr(v7);
              if ( *((_DWORD *)v24 + 36) == *v20 )
              {
                v17 = 1;
                v6 = CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(a2, v24, a3, v25);
                if ( v6 < 0 )
                  break;
              }
            }
            v18 = (unsigned int)(v18 + 1);
            if ( (unsigned int)v18 >= *((_DWORD *)v15 + 22) )
            {
              if ( v17 )
                break;
              goto LABEL_39;
            }
          }
        }
      }
      if ( v15 )
        HANDLE_ENTRY::DereferenceHandleEntry(v15);
    }
    else
    {
      return (unsigned int)v11;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180015500  mov     [rsp+arg_0], rbx
0x180015505  push    rbp
0x180015506  push    rsi
0x180015507  push    rdi
0x180015508  push    r12
0x18001550a  push    r13
0x18001550c  push    r14
0x18001550e  push    r15
0x180015510  sub     rsp, 30h
0x180015514  mov     r15, r8
0x180015517  mov     r13, rdx
0x18001551a  mov     r12, rcx
0x18001551d  test    rdx, rdx
0x180015520  jz      loc_180015820
0x180015526  test    r8, r8
0x180015529  jz      loc_180015820
0x18001552f  cmp     r8, [rcx+10h]
0x180015533  jz      short loc_18001553F
0x180015535  mov     ebx, 80070002h
0x18001553a  jmp     loc_180015825
0x18001553f  lea     rdi, [rdx+10h]
0x180015543  mov     rcx, rdi
0x180015546  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001554c  cmp     dword ptr [rax], 3F7h
0x180015552  jnz     short loc_180015563
0x180015554  mov     rcx, r15; this
0x180015557  call    ?UnMapNodeAndChildren@ABO_NODE@@QEAAJXZ; ABO_NODE::UnMapNodeAndChildren(void)
0x18001555c  mov     ebx, eax
0x18001555e  jmp     loc_180015825
0x180015563  mov     rcx, rdi
0x180015566  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001556c  cmp     dword ptr [rax], 1587h
0x180015572  jz      loc_180015810
0x180015578  mov     rcx, rdi
0x18001557b  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180015581  cmp     dword ptr [rax], 1582h
0x180015587  jz      loc_180015810
0x18001558d  mov     rcx, rdi
0x180015590  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180015596  cmp     dword ptr [rax], 1588h
0x18001559c  jz      loc_180015810
0x1800155a2  mov     rcx, rdi
0x1800155a5  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800155ab  cmp     dword ptr [rax], 158Dh
0x1800155b1  jz      loc_180015810
0x1800155b7  mov     rcx, rdi
0x1800155ba  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800155c0  cmp     dword ptr [rax], 870h
0x1800155c6  jz      loc_180015810
0x1800155cc  mov     rcx, rdi
0x1800155cf  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800155d5  cmp     dword ptr [rax], 158Fh
0x1800155db  jz      loc_180015810
0x1800155e1  mov     rcx, rdi
0x1800155e4  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800155ea  cmp     dword ptr [rax], 1591h
0x1800155f0  jz      loc_180015810
0x1800155f6  mov     rcx, rdi
0x1800155f9  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800155ff  cmp     dword ptr [rax], 871h
0x180015605  jz      loc_180015810
0x18001560b  mov     rcx, rdi
0x18001560e  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180015614  cmp     dword ptr [rax], 872h
0x18001561a  jz      loc_180015810
0x180015620  mov     r9, [r12+18h]; struct INativeConfigurationElement *
0x180015625  lea     rdx, aSite; "site"
0x18001562c  mov     r8, r15; struct ABO_NODE *
0x18001562f  mov     rcx, r13; struct PROPERTY_ENTRY *
0x180015632  call    ?DeleteConfigPropertiesBySectionName@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEBGPEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesBySectionName(PROPERTY_ENTRY *,ushort const *,ABO_NODE *,INativeConfigurationElement *)
0x180015637  mov     ebp, 80070002h
0x18001563c  mov     ebx, eax
0x18001563e  cmp     eax, ebp
0x180015640  jnz     loc_180015825
0x180015646  mov     rax, [r12+30h]
0x18001564b  lea     ebx, [rbp+55h]
0x18001564e  xor     esi, esi
0x180015650  mov     [rsp+68h+var_40], rax
0x180015655  mov     [rsp+68h+var_48], rsi
0x18001565a  test    rax, rax
0x18001565d  jz      loc_180015723
0x180015663  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x18001566a  lea     r8, [rsp+68h+var_48]
0x18001566f  add     rcx, 8
0x180015673  lea     rdx, aApplication; "application"
0x18001567a  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x18001567f  mov     rsi, [rsp+68h+var_48]
0x180015684  test    eax, eax
0x180015686  jnz     loc_18001571E
0x18001568c  xor     r14d, r14d
0x18001568f  mov     dword ptr [rsp+68h+arg_18], eax
0x180015696  mov     dword ptr [rsp+68h+arg_8], eax
0x18001569a  cmp     [rsi+58h], eax
0x18001569d  jbe     short loc_18001571E
0x18001569f  mov     ecx, eax
0x1800156a1  mov     rax, [rsi+50h]
0x1800156a5  mov     rax, [rax+rcx*8]
0x1800156a9  mov     [rsp+68h+var_48], rax
0x1800156ae  lea     rcx, [rax+20h]
0x1800156b2  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x1800156b8  mov     rcx, rax; String1
0x1800156bb  lea     rdx, aApplication; "application"
0x1800156c2  call    wcscmp_0
0x1800156c7  test    eax, eax
0x1800156c9  jnz     short loc_180015705
0x1800156cb  mov     rcx, rdi
0x1800156ce  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800156d4  mov     rdx, [rsp+68h+var_48]; struct PROPERTY_MAPPING *
0x1800156d9  mov     ecx, [rax]
0x1800156db  cmp     [rdx+90h], ecx
0x1800156e1  jnz     short loc_180015705
0x1800156e3  mov     r9, [rsp+68h+var_40]; struct INativeConfigurationElement *
0x1800156e8  mov     r8, r15; struct ABO_NODE *
0x1800156eb  mov     rcx, r13; struct PROPERTY_ENTRY *
0x1800156ee  mov     dword ptr [rsp+68h+arg_18], 1
0x1800156f9  call    ?DeleteConfigPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(PROPERTY_ENTRY *,PROPERTY_MAPPING *,ABO_NODE *,INativeConfigurationElement *)
0x1800156fe  mov     r14d, eax
0x180015701  test    eax, eax
0x180015703  js      short loc_180015726
0x180015705  mov     eax, dword ptr [rsp+68h+arg_8]
0x180015709  inc     eax
0x18001570b  mov     dword ptr [rsp+68h+arg_8], eax
0x18001570f  cmp     eax, [rsi+58h]
0x180015712  jb      short loc_18001569F
0x180015714  cmp     dword ptr [rsp+68h+arg_18], 0
0x18001571c  jnz     short loc_180015726
0x18001571e  mov     r14d, ebp
0x180015721  jmp     short loc_180015726
0x180015723  mov     r14d, ebx
0x180015726  test    rsi, rsi
0x180015729  jz      short loc_180015733
0x18001572b  mov     rcx, rsi; this
0x18001572e  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x180015733  cmp     r14d, ebp
0x180015736  jnz     loc_18001580B
0x18001573c  mov     rax, [r12+28h]
0x180015741  xor     esi, esi
0x180015743  mov     [rsp+68h+arg_8], rsi
0x180015748  mov     [rsp+68h+arg_18], rax
0x180015750  test    rax, rax
0x180015753  jz      loc_1800157FC
0x180015759  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x180015760  lea     r8, [rsp+68h+arg_8]
0x180015765  add     rcx, 8
0x180015769  lea     rdx, aVirtualdirecto_0; "virtualDirectory"
0x180015770  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x180015775  mov     rsi, [rsp+68h+arg_8]
0x18001577a  test    eax, eax
0x18001577c  jnz     short loc_1800157FA
0x18001577e  xor     ebx, ebx
0x180015780  xor     r12d, r12d
0x180015783  xor     r14d, r14d
0x180015786  cmp     [rsi+58h], ebx
0x180015789  jbe     short loc_1800157FA
0x18001578b  mov     rax, [rsi+50h]
0x18001578f  mov     rax, [rax+r14*8]
0x180015793  mov     [rsp+68h+arg_8], rax
0x180015798  lea     rcx, [rax+20h]
0x18001579c  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x1800157a2  mov     rcx, rax; String1
0x1800157a5  lea     rdx, aVirtualdirecto_0; "virtualDirectory"
0x1800157ac  call    wcscmp_0
0x1800157b1  test    eax, eax
0x1800157b3  jnz     short loc_1800157EC
0x1800157b5  mov     rcx, rdi
0x1800157b8  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800157be  mov     rdx, [rsp+68h+arg_8]; struct PROPERTY_MAPPING *
0x1800157c3  mov     ecx, [rax]
0x1800157c5  cmp     [rdx+90h], ecx
0x1800157cb  jnz     short loc_1800157EC
0x1800157cd  mov     r9, [rsp+68h+arg_18]; struct INativeConfigurationElement *
0x1800157d5  mov     r8, r15; struct ABO_NODE *
0x1800157d8  mov     rcx, r13; struct PROPERTY_ENTRY *
0x1800157db  mov     r12d, 1
0x1800157e1  call    ?DeleteConfigPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(PROPERTY_ENTRY *,PROPERTY_MAPPING *,ABO_NODE *,INativeConfigurationElement *)
0x1800157e6  mov     ebx, eax
0x1800157e8  test    eax, eax
0x1800157ea  js      short loc_1800157FC
0x1800157ec  inc     r14d
0x1800157ef  cmp     r14d, [rsi+58h]
0x1800157f3  jb      short loc_18001578B
0x1800157f5  test    r12d, r12d
0x1800157f8  jnz     short loc_1800157FC
0x1800157fa  mov     ebx, ebp
0x1800157fc  test    rsi, rsi
0x1800157ff  jz      short loc_180015825
0x180015801  mov     rcx, rsi; this
0x180015804  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x180015809  jmp     short loc_180015825
0x18001580b  mov     ebx, r14d
0x18001580e  jmp     short loc_180015825
0x180015810  mov     rdx, r15; struct ABO_NODE *
0x180015813  mov     rcx, r13; struct PROPERTY_ENTRY *
0x180015816  call    ?DeleteSSLProperty@@YAJPEAVPROPERTY_ENTRY@@PEAVABO_NODE@@@Z; DeleteSSLProperty(PROPERTY_ENTRY *,ABO_NODE *)
0x18001581b  jmp     loc_18001555C
0x180015820  mov     ebx, 80070057h
0x180015825  mov     eax, ebx
0x180015827  mov     rbx, [rsp+68h+arg_0]
0x18001582c  add     rsp, 30h
0x180015830  pop     r15
0x180015832  pop     r14
0x180015834  pop     r13
0x180015836  pop     r12
0x180015838  pop     rdi
0x180015839  pop     rsi
0x18001583a  pop     rbp
0x18001583b  retn
```
