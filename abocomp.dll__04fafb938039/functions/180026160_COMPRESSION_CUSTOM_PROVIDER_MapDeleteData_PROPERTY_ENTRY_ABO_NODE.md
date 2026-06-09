# COMPRESSION_CUSTOM_PROVIDER::MapDeleteData(PROPERTY_ENTRY *,ABO_NODE *)

- ea: `0x180026160`
- end: `0x180026264`
- name: `?MapDeleteData@COMPRESSION_CUSTOM_PROVIDER@@UEAAJPEAVPROPERTY_ENTRY@@PEAVABO_NODE@@@Z`
- size: `260`
- prototype: `int(COMPRESSION_CUSTOM_PROVIDER *__hidden this, struct PROPERTY_ENTRY *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180003426`
- `0x180003f14`
- `0x1800047e4`
- `0x18001775c`
- `0x180026160`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800261da`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800261da`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800261f7`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800261f7`

## string_xrefs

- `0x1800261ad`: `httpCompression`
- `0x1800261e3`: `httpCompression`

## pseudocode

```c
__int64 __fastcall COMPRESSION_CUSTOM_PROVIDER::MapDeleteData(
        COMPRESSION_CUSTOM_PROVIDER *this,
        struct PROPERTY_ENTRY *a2,
        struct ABO_NODE *a3)
{
  struct INativeConfigurationElement *v5; // r15
  HANDLE_ENTRY *v6; // rdi
  int Key; // eax
  int v8; // ebx
  int v9; // r12d
  __int64 v10; // rsi
  _DWORD *v11; // r13
  const wchar_t *Str; // rax
  HANDLE_ENTRY *v14; // [rsp+78h] [rbp+10h] BYREF

  if ( a2 && a3 )
  {
    v5 = (struct INativeConfigurationElement *)*((_QWORD *)this + 3);
    v6 = 0;
    v14 = 0;
    if ( v5 )
    {
      Key = CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::FindKey(
              (char *)g_pPropertySectionTable + 8,
              L"httpCompression",
              &v14);
      v6 = v14;
      if ( Key || (v8 = 0, v9 = 0, v10 = 0, !*((_DWORD *)v14 + 22)) )
      {
LABEL_11:
        v8 = -2147024894;
      }
      else
      {
        while ( 1 )
        {
          v11 = *(_DWORD **)(*((_QWORD *)v6 + 10) + 8 * v10);
          Str = STRU::QueryStr((STRU *)(v11 + 8));
          if ( !wcscmp_0(Str, L"httpCompression")
            && v11[36] == *(_DWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a2 + 16)) )
          {
            v9 = 1;
            v8 = CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(a2, (struct PROPERTY_MAPPING *)v11, a3, v5);
            if ( v8 < 0 )
              break;
          }
          v10 = (unsigned int)(v10 + 1);
          if ( (unsigned int)v10 >= *((_DWORD *)v6 + 22) )
          {
            if ( v9 )
              break;
            goto LABEL_11;
          }
        }
      }
    }
    else
    {
      v8 = -2147024809;
    }
    if ( v6 )
      HANDLE_ENTRY::DereferenceHandleEntry(v6);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180026160  push    rbx
0x180026162  push    rbp
0x180026163  push    rsi
0x180026164  push    rdi
0x180026165  push    r12
0x180026167  push    r13
0x180026169  push    r14
0x18002616b  push    r15
0x18002616d  sub     rsp, 28h
0x180026171  mov     r14, r8
0x180026174  mov     rbp, rdx
0x180026177  test    rdx, rdx
0x18002617a  jz      loc_18002624C
0x180026180  test    r8, r8
0x180026183  jz      loc_18002624C
0x180026189  mov     r15, [rcx+18h]
0x18002618d  xor     edi, edi
0x18002618f  mov     [rsp+68h+arg_8], rdi
0x180026194  test    r15, r15
0x180026197  jz      loc_180026238
0x18002619d  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x1800261a4  lea     r8, [rsp+68h+arg_8]
0x1800261a9  add     rcx, 8
0x1800261ad  lea     rdx, aHttpcompressio; "httpCompression"
0x1800261b4  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x1800261b9  mov     rdi, [rsp+68h+arg_8]
0x1800261be  test    eax, eax
0x1800261c0  jnz     short loc_180026231
0x1800261c2  xor     ebx, ebx
0x1800261c4  xor     r12d, r12d
0x1800261c7  xor     esi, esi
0x1800261c9  cmp     [rdi+58h], ebx
0x1800261cc  jbe     short loc_180026231
0x1800261ce  mov     rax, [rdi+50h]
0x1800261d2  mov     r13, [rax+rsi*8]
0x1800261d6  lea     rcx, [r13+20h]
0x1800261da  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x1800261e0  mov     rcx, rax; String1
0x1800261e3  lea     rdx, aHttpcompressio; "httpCompression"
0x1800261ea  call    wcscmp_0
0x1800261ef  test    eax, eax
0x1800261f1  jnz     short loc_180026225
0x1800261f3  lea     rcx, [rbp+10h]
0x1800261f7  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800261fd  mov     ecx, [rax]
0x1800261ff  cmp     [r13+90h], ecx
0x180026206  jnz     short loc_180026225
0x180026208  mov     r9, r15; struct INativeConfigurationElement *
0x18002620b  mov     r8, r14; struct ABO_NODE *
0x18002620e  mov     rdx, r13; struct PROPERTY_MAPPING *
0x180026211  mov     rcx, rbp; struct PROPERTY_ENTRY *
0x180026214  mov     r12d, 1
0x18002621a  call    ?DeleteConfigPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(PROPERTY_ENTRY *,PROPERTY_MAPPING *,ABO_NODE *,INativeConfigurationElement *)
0x18002621f  mov     ebx, eax
0x180026221  test    eax, eax
0x180026223  js      short loc_18002623D
0x180026225  inc     esi
0x180026227  cmp     esi, [rdi+58h]
0x18002622a  jb      short loc_1800261CE
0x18002622c  test    r12d, r12d
0x18002622f  jnz     short loc_18002623D
0x180026231  mov     ebx, 80070002h
0x180026236  jmp     short loc_18002623D
0x180026238  mov     ebx, 80070057h
0x18002623d  test    rdi, rdi
0x180026240  jz      short loc_180026251
0x180026242  mov     rcx, rdi; this
0x180026245  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18002624a  jmp     short loc_180026251
0x18002624c  mov     ebx, 80070057h
0x180026251  mov     eax, ebx
0x180026253  add     rsp, 28h
0x180026257  pop     r15
0x180026259  pop     r14
0x18002625b  pop     r13
0x18002625d  pop     r12
0x18002625f  pop     rdi
0x180026260  pop     rsi
0x180026261  pop     rbp
0x180026262  pop     rbx
0x180026263  retn
```
