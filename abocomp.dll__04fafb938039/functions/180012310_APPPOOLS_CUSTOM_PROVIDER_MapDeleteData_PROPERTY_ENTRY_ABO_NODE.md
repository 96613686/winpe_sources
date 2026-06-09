# APPPOOLS_CUSTOM_PROVIDER::MapDeleteData(PROPERTY_ENTRY *,ABO_NODE *)

- ea: `0x180012310`
- end: `0x180012424`
- name: `?MapDeleteData@APPPOOLS_CUSTOM_PROVIDER@@UEAAJPEAVPROPERTY_ENTRY@@PEAVABO_NODE@@@Z`
- size: `276`
- prototype: `int(APPPOOLS_CUSTOM_PROVIDER *__hidden this, struct PROPERTY_ENTRY *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180003426`
- `0x180003f14`
- `0x1800047e4`
- `0x180012310`
- `0x18001775c`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001239a`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001239a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800123b7`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800123b7`

## pseudocode

```c
__int64 __fastcall APPPOOLS_CUSTOM_PROVIDER::MapDeleteData(
        APPPOOLS_CUSTOM_PROVIDER *this,
        struct PROPERTY_ENTRY *a2,
        struct ABO_NODE *a3)
{
  int v5; // ebx
  struct INativeConfigurationElement *v6; // r15
  HANDLE_ENTRY *v7; // rdi
  int Key; // eax
  int v9; // r12d
  __int64 v10; // rbp
  _DWORD *v11; // r13
  const wchar_t *Str; // rax
  HANDLE_ENTRY *v14; // [rsp+78h] [rbp+10h] BYREF

  if ( a2 && a3 )
  {
    if ( a3 == *((struct ABO_NODE **)this + 2) )
    {
      v6 = (struct INativeConfigurationElement *)*((_QWORD *)this + 4);
      v7 = 0;
      v14 = 0;
      if ( v6 )
      {
        Key = CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::FindKey(
                (char *)g_pPropertySectionTable + 8,
                L"applicationPool",
                &v14);
        v7 = v14;
        if ( Key || (v5 = 0, v9 = 0, v10 = 0, !*((_DWORD *)v14 + 22)) )
        {
LABEL_13:
          v5 = -2147024894;
        }
        else
        {
          while ( 1 )
          {
            v11 = *(_DWORD **)(*((_QWORD *)v7 + 10) + 8 * v10);
            Str = STRU::QueryStr((STRU *)(v11 + 8));
            if ( !wcscmp_0(Str, L"applicationPool")
              && v11[36] == *(_DWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a2 + 16)) )
            {
              v9 = 1;
              v5 = CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(a2, (struct PROPERTY_MAPPING *)v11, a3, v6);
              if ( v5 < 0 )
                break;
            }
            v10 = (unsigned int)(v10 + 1);
            if ( (unsigned int)v10 >= *((_DWORD *)v7 + 22) )
            {
              if ( v9 )
                break;
              goto LABEL_13;
            }
          }
        }
      }
      else
      {
        v5 = -2147024809;
      }
      if ( v7 )
        HANDLE_ENTRY::DereferenceHandleEntry(v7);
    }
    else
    {
      return (unsigned int)-2147024894;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180012310  push    rbx
0x180012312  push    rbp
0x180012313  push    rsi
0x180012314  push    rdi
0x180012315  push    r12
0x180012317  push    r13
0x180012319  push    r14
0x18001231b  push    r15
0x18001231d  sub     rsp, 28h
0x180012321  mov     rsi, r8
0x180012324  mov     r14, rdx
0x180012327  test    rdx, rdx
0x18001232a  jz      loc_18001240C
0x180012330  test    r8, r8
0x180012333  jz      loc_18001240C
0x180012339  cmp     r8, [rcx+10h]
0x18001233d  jz      short loc_180012349
0x18001233f  mov     ebx, 80070002h
0x180012344  jmp     loc_180012411
0x180012349  mov     r15, [rcx+20h]
0x18001234d  xor     edi, edi
0x18001234f  mov     [rsp+68h+arg_8], rdi
0x180012354  test    r15, r15
0x180012357  jz      loc_1800123F8
0x18001235d  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x180012364  lea     r8, [rsp+68h+arg_8]
0x180012369  add     rcx, 8
0x18001236d  lea     rdx, aApplicationpoo_0; "applicationPool"
0x180012374  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x180012379  mov     rdi, [rsp+68h+arg_8]
0x18001237e  test    eax, eax
0x180012380  jnz     short loc_1800123F1
0x180012382  xor     ebx, ebx
0x180012384  xor     r12d, r12d
0x180012387  xor     ebp, ebp
0x180012389  cmp     [rdi+58h], ebx
0x18001238c  jbe     short loc_1800123F1
0x18001238e  mov     rax, [rdi+50h]
0x180012392  mov     r13, [rax+rbp*8]
0x180012396  lea     rcx, [r13+20h]
0x18001239a  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x1800123a0  mov     rcx, rax; String1
0x1800123a3  lea     rdx, aApplicationpoo_0; "applicationPool"
0x1800123aa  call    wcscmp_0
0x1800123af  test    eax, eax
0x1800123b1  jnz     short loc_1800123E5
0x1800123b3  lea     rcx, [r14+10h]
0x1800123b7  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800123bd  mov     ecx, [rax]
0x1800123bf  cmp     [r13+90h], ecx
0x1800123c6  jnz     short loc_1800123E5
0x1800123c8  mov     r9, r15; struct INativeConfigurationElement *
0x1800123cb  mov     r8, rsi; struct ABO_NODE *
0x1800123ce  mov     rdx, r13; struct PROPERTY_MAPPING *
0x1800123d1  mov     rcx, r14; struct PROPERTY_ENTRY *
0x1800123d4  mov     r12d, 1
0x1800123da  call    ?DeleteConfigPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(PROPERTY_ENTRY *,PROPERTY_MAPPING *,ABO_NODE *,INativeConfigurationElement *)
0x1800123df  mov     ebx, eax
0x1800123e1  test    eax, eax
0x1800123e3  js      short loc_1800123FD
0x1800123e5  inc     ebp
0x1800123e7  cmp     ebp, [rdi+58h]
0x1800123ea  jb      short loc_18001238E
0x1800123ec  test    r12d, r12d
0x1800123ef  jnz     short loc_1800123FD
0x1800123f1  mov     ebx, 80070002h
0x1800123f6  jmp     short loc_1800123FD
0x1800123f8  mov     ebx, 80070057h
0x1800123fd  test    rdi, rdi
0x180012400  jz      short loc_180012411
0x180012402  mov     rcx, rdi; this
0x180012405  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18001240a  jmp     short loc_180012411
0x18001240c  mov     ebx, 80070057h
0x180012411  mov     eax, ebx
0x180012413  add     rsp, 28h
0x180012417  pop     r15
0x180012419  pop     r14
0x18001241b  pop     r13
0x18001241d  pop     r12
0x18001241f  pop     rdi
0x180012420  pop     rsi
0x180012421  pop     rbp
0x180012422  pop     rbx
0x180012423  retn
```
