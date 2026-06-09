# SCHEME_CUSTOM_PROVIDER::MapDeleteData(PROPERTY_ENTRY *,ABO_NODE *)

- ea: `0x180026710`
- end: `0x180026814`
- name: `?MapDeleteData@SCHEME_CUSTOM_PROVIDER@@UEAAJPEAVPROPERTY_ENTRY@@PEAVABO_NODE@@@Z`
- size: `260`
- prototype: `int(SCHEME_CUSTOM_PROVIDER *__hidden this, struct PROPERTY_ENTRY *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180003426`
- `0x180003f14`
- `0x1800047e4`
- `0x18001775c`
- `0x180026710`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18002678a`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18002678a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800267a7`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800267a7`

## pseudocode

```c
__int64 __fastcall SCHEME_CUSTOM_PROVIDER::MapDeleteData(
        SCHEME_CUSTOM_PROVIDER *this,
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
              L"scheme",
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
          if ( !wcscmp_0(Str, L"scheme")
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
0x180026710  push    rbx
0x180026712  push    rbp
0x180026713  push    rsi
0x180026714  push    rdi
0x180026715  push    r12
0x180026717  push    r13
0x180026719  push    r14
0x18002671b  push    r15
0x18002671d  sub     rsp, 28h
0x180026721  mov     r14, r8
0x180026724  mov     rbp, rdx
0x180026727  test    rdx, rdx
0x18002672a  jz      loc_1800267FC
0x180026730  test    r8, r8
0x180026733  jz      loc_1800267FC
0x180026739  mov     r15, [rcx+18h]
0x18002673d  xor     edi, edi
0x18002673f  mov     [rsp+68h+arg_8], rdi
0x180026744  test    r15, r15
0x180026747  jz      loc_1800267E8
0x18002674d  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x180026754  lea     r8, [rsp+68h+arg_8]
0x180026759  add     rcx, 8
0x18002675d  lea     rdx, aScheme; "scheme"
0x180026764  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x180026769  mov     rdi, [rsp+68h+arg_8]
0x18002676e  test    eax, eax
0x180026770  jnz     short loc_1800267E1
0x180026772  xor     ebx, ebx
0x180026774  xor     r12d, r12d
0x180026777  xor     esi, esi
0x180026779  cmp     [rdi+58h], ebx
0x18002677c  jbe     short loc_1800267E1
0x18002677e  mov     rax, [rdi+50h]
0x180026782  mov     r13, [rax+rsi*8]
0x180026786  lea     rcx, [r13+20h]
0x18002678a  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180026790  mov     rcx, rax; String1
0x180026793  lea     rdx, aScheme; "scheme"
0x18002679a  call    wcscmp_0
0x18002679f  test    eax, eax
0x1800267a1  jnz     short loc_1800267D5
0x1800267a3  lea     rcx, [rbp+10h]
0x1800267a7  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800267ad  mov     ecx, [rax]
0x1800267af  cmp     [r13+90h], ecx
0x1800267b6  jnz     short loc_1800267D5
0x1800267b8  mov     r9, r15; struct INativeConfigurationElement *
0x1800267bb  mov     r8, r14; struct ABO_NODE *
0x1800267be  mov     rdx, r13; struct PROPERTY_MAPPING *
0x1800267c1  mov     rcx, rbp; struct PROPERTY_ENTRY *
0x1800267c4  mov     r12d, 1
0x1800267ca  call    ?DeleteConfigPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(PROPERTY_ENTRY *,PROPERTY_MAPPING *,ABO_NODE *,INativeConfigurationElement *)
0x1800267cf  mov     ebx, eax
0x1800267d1  test    eax, eax
0x1800267d3  js      short loc_1800267ED
0x1800267d5  inc     esi
0x1800267d7  cmp     esi, [rdi+58h]
0x1800267da  jb      short loc_18002677E
0x1800267dc  test    r12d, r12d
0x1800267df  jnz     short loc_1800267ED
0x1800267e1  mov     ebx, 80070002h
0x1800267e6  jmp     short loc_1800267ED
0x1800267e8  mov     ebx, 80070057h
0x1800267ed  test    rdi, rdi
0x1800267f0  jz      short loc_180026801
0x1800267f2  mov     rcx, rdi; this
0x1800267f5  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x1800267fa  jmp     short loc_180026801
0x1800267fc  mov     ebx, 80070057h
0x180026801  mov     eax, ebx
0x180026803  add     rsp, 28h
0x180026807  pop     r15
0x180026809  pop     r14
0x18002680b  pop     r13
0x18002680d  pop     r12
0x18002680f  pop     rdi
0x180026810  pop     rsi
0x180026811  pop     rbp
0x180026812  pop     rbx
0x180026813  retn
```
