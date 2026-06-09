# CUSTOM_PROPERTY_PROVIDER::SetConfigPropertiesBySectionName(PROPERTY_ENTRY *,ushort const *,ABO_NODE *,INativeConfigurationElement *)

- ea: `0x180018d98`
- end: `0x180018eb0`
- name: `?SetConfigPropertiesBySectionName@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEBGPEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z`
- size: `280`
- prototype: `__int64 __fastcall(struct PROPERTY_ENTRY *, const unsigned __int16 *, struct ABO_NODE *, struct INativeConfigurationElement *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180013570`
- `0x180015880`

## callees

- `0x180003f14`
- `0x1800047e4`
- `0x1800187e0`
- `0x180018d98`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180018e1f`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180018e1f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180018e49`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180018e49`

## pseudocode

```c
__int64 __fastcall CUSTOM_PROPERTY_PROVIDER::SetConfigPropertiesBySectionName(
        struct PROPERTY_ENTRY *a1,
        char *a2,
        struct ABO_NODE *a3,
        struct INativeConfigurationElement *a4)
{
  HANDLE_ENTRY *v4; // rdi
  int Key; // eax
  int v10; // ebx
  int v11; // r15d
  __int64 v12; // rsi
  const unsigned __int16 *Str; // rax
  char *v14; // rdx
  int v15; // ecx
  int v16; // r8d
  _DWORD *Ptr; // rax
  HANDLE_ENTRY *v19; // [rsp+70h] [rbp+8h] BYREF

  v4 = 0;
  v19 = 0;
  if ( a1 && a4 && a3 && a2 )
  {
    Key = CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::FindKey(
            (char *)g_pPropertySectionTable + 8,
            a2,
            &v19);
    v4 = v19;
    if ( Key || (v10 = 0, v11 = 0, v12 = 0, !*((_DWORD *)v19 + 22)) )
    {
LABEL_15:
      v10 = -2147024894;
    }
    else
    {
      while ( 1 )
      {
        v19 = *(HANDLE_ENTRY **)(*((_QWORD *)v4 + 10) + 8 * v12);
        Str = STRU::QueryStr((HANDLE_ENTRY *)((char *)v19 + 32));
        v14 = (char *)(a2 - (char *)Str);
        do
        {
          v15 = *(unsigned __int16 *)&v14[(_QWORD)Str];
          v16 = *Str - v15;
          if ( v16 )
            break;
          ++Str;
        }
        while ( v15 );
        if ( !v16 )
        {
          Ptr = BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a1 + 16));
          if ( *((_DWORD *)v19 + 36) == *Ptr )
          {
            v11 = 1;
            v10 = CUSTOM_PROPERTY_PROVIDER::SetConfigPropertiesByMapping(a1, v19, a3, a4);
            if ( v10 < 0 )
              break;
          }
        }
        v12 = (unsigned int)(v12 + 1);
        if ( (unsigned int)v12 >= *((_DWORD *)v4 + 22) )
        {
          if ( v11 )
            break;
          goto LABEL_15;
        }
      }
    }
  }
  else
  {
    v10 = -2147024809;
  }
  if ( v4 )
    HANDLE_ENTRY::DereferenceHandleEntry(v4);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180018d98  push    rbx
0x180018d9a  push    rbp
0x180018d9b  push    rsi
0x180018d9c  push    rdi
0x180018d9d  push    r12
0x180018d9f  push    r13
0x180018da1  push    r14
0x180018da3  push    r15
0x180018da5  sub     rsp, 28h
0x180018da9  xor     edi, edi
0x180018dab  mov     r12, r9
0x180018dae  mov     [rsp+68h+arg_0], rdi
0x180018db3  mov     r13, r8
0x180018db6  mov     rbp, rdx
0x180018db9  mov     r14, rcx
0x180018dbc  test    rcx, rcx
0x180018dbf  jz      loc_180018E8B
0x180018dc5  test    r9, r9
0x180018dc8  jz      loc_180018E8B
0x180018dce  test    r8, r8
0x180018dd1  jz      loc_180018E8B
0x180018dd7  test    rdx, rdx
0x180018dda  jz      loc_180018E8B
0x180018de0  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x180018de7  lea     r8, [rsp+68h+arg_0]
0x180018dec  add     rcx, 8
0x180018df0  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x180018df5  mov     rdi, [rsp+68h+arg_0]
0x180018dfa  test    eax, eax
0x180018dfc  jnz     loc_180018E84
0x180018e02  xor     ebx, ebx
0x180018e04  xor     r15d, r15d
0x180018e07  xor     esi, esi
0x180018e09  cmp     [rdi+58h], ebx
0x180018e0c  jbe     short loc_180018E84
0x180018e0e  mov     rax, [rdi+50h]
0x180018e12  mov     rax, [rax+rsi*8]
0x180018e16  mov     [rsp+68h+arg_0], rax
0x180018e1b  lea     rcx, [rax+20h]
0x180018e1f  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180018e25  mov     rdx, rbp
0x180018e28  sub     rdx, rax
0x180018e2b  movzx   r8d, word ptr [rax]
0x180018e2f  movzx   ecx, word ptr [rax+rdx]
0x180018e33  sub     r8d, ecx
0x180018e36  jnz     short loc_180018E40
0x180018e38  add     rax, 2
0x180018e3c  test    ecx, ecx
0x180018e3e  jnz     short loc_180018E2B
0x180018e40  test    r8d, r8d
0x180018e43  jnz     short loc_180018E78
0x180018e45  lea     rcx, [r14+10h]
0x180018e49  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180018e4f  mov     rdx, [rsp+68h+arg_0]; struct PROPERTY_MAPPING *
0x180018e54  mov     ecx, [rax]
0x180018e56  cmp     [rdx+90h], ecx
0x180018e5c  jnz     short loc_180018E78
0x180018e5e  mov     r9, r12; struct INativeConfigurationElement *
0x180018e61  mov     r8, r13; struct ABO_NODE *
0x180018e64  mov     rcx, r14; struct PROPERTY_ENTRY *
0x180018e67  mov     r15d, 1
0x180018e6d  call    ?SetConfigPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::SetConfigPropertiesByMapping(PROPERTY_ENTRY *,PROPERTY_MAPPING *,ABO_NODE *,INativeConfigurationElement *)
0x180018e72  mov     ebx, eax
0x180018e74  test    eax, eax
0x180018e76  js      short loc_180018E90
0x180018e78  inc     esi
0x180018e7a  cmp     esi, [rdi+58h]
0x180018e7d  jb      short loc_180018E0E
0x180018e7f  test    r15d, r15d
0x180018e82  jnz     short loc_180018E90
0x180018e84  mov     ebx, 80070002h
0x180018e89  jmp     short loc_180018E90
0x180018e8b  mov     ebx, 80070057h
0x180018e90  test    rdi, rdi
0x180018e93  jz      short loc_180018E9D
0x180018e95  mov     rcx, rdi; this
0x180018e98  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x180018e9d  mov     eax, ebx
0x180018e9f  add     rsp, 28h
0x180018ea3  pop     r15
0x180018ea5  pop     r14
0x180018ea7  pop     r13
0x180018ea9  pop     r12
0x180018eab  pop     rdi
0x180018eac  pop     rsi
0x180018ead  pop     rbp
0x180018eae  pop     rbx
0x180018eaf  retn
```
