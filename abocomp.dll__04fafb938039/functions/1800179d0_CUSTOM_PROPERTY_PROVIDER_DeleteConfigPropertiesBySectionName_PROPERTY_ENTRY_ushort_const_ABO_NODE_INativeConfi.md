# CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesBySectionName(PROPERTY_ENTRY *,ushort const *,ABO_NODE *,INativeConfigurationElement *)

- ea: `0x1800179d0`
- end: `0x180017ae8`
- name: `?DeleteConfigPropertiesBySectionName@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEBGPEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z`
- size: `280`
- prototype: `__int64 __fastcall(struct PROPERTY_ENTRY *, const unsigned __int16 *, struct ABO_NODE *, struct INativeConfigurationElement *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180015500`

## callees

- `0x180003f14`
- `0x1800047e4`
- `0x18001775c`
- `0x1800179d0`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180017a57`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180017a57`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180017a81`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180017a81`

## pseudocode

```c
__int64 __fastcall CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesBySectionName(
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
            v10 = CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(a1, v19, a3, a4);
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
0x1800179d0  push    rbx
0x1800179d2  push    rbp
0x1800179d3  push    rsi
0x1800179d4  push    rdi
0x1800179d5  push    r12
0x1800179d7  push    r13
0x1800179d9  push    r14
0x1800179db  push    r15
0x1800179dd  sub     rsp, 28h
0x1800179e1  xor     edi, edi
0x1800179e3  mov     r12, r9
0x1800179e6  mov     [rsp+68h+arg_0], rdi
0x1800179eb  mov     r13, r8
0x1800179ee  mov     rbp, rdx
0x1800179f1  mov     r14, rcx
0x1800179f4  test    rcx, rcx
0x1800179f7  jz      loc_180017AC3
0x1800179fd  test    r9, r9
0x180017a00  jz      loc_180017AC3
0x180017a06  test    r8, r8
0x180017a09  jz      loc_180017AC3
0x180017a0f  test    rdx, rdx
0x180017a12  jz      loc_180017AC3
0x180017a18  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x180017a1f  lea     r8, [rsp+68h+arg_0]
0x180017a24  add     rcx, 8
0x180017a28  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x180017a2d  mov     rdi, [rsp+68h+arg_0]
0x180017a32  test    eax, eax
0x180017a34  jnz     loc_180017ABC
0x180017a3a  xor     ebx, ebx
0x180017a3c  xor     r15d, r15d
0x180017a3f  xor     esi, esi
0x180017a41  cmp     [rdi+58h], ebx
0x180017a44  jbe     short loc_180017ABC
0x180017a46  mov     rax, [rdi+50h]
0x180017a4a  mov     rax, [rax+rsi*8]
0x180017a4e  mov     [rsp+68h+arg_0], rax
0x180017a53  lea     rcx, [rax+20h]
0x180017a57  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180017a5d  mov     rdx, rbp
0x180017a60  sub     rdx, rax
0x180017a63  movzx   r8d, word ptr [rax]
0x180017a67  movzx   ecx, word ptr [rax+rdx]
0x180017a6b  sub     r8d, ecx
0x180017a6e  jnz     short loc_180017A78
0x180017a70  add     rax, 2
0x180017a74  test    ecx, ecx
0x180017a76  jnz     short loc_180017A63
0x180017a78  test    r8d, r8d
0x180017a7b  jnz     short loc_180017AB0
0x180017a7d  lea     rcx, [r14+10h]
0x180017a81  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180017a87  mov     rdx, [rsp+68h+arg_0]; struct PROPERTY_MAPPING *
0x180017a8c  mov     ecx, [rax]
0x180017a8e  cmp     [rdx+90h], ecx
0x180017a94  jnz     short loc_180017AB0
0x180017a96  mov     r9, r12; struct INativeConfigurationElement *
0x180017a99  mov     r8, r13; struct ABO_NODE *
0x180017a9c  mov     rcx, r14; struct PROPERTY_ENTRY *
0x180017a9f  mov     r15d, 1
0x180017aa5  call    ?DeleteConfigPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(PROPERTY_ENTRY *,PROPERTY_MAPPING *,ABO_NODE *,INativeConfigurationElement *)
0x180017aaa  mov     ebx, eax
0x180017aac  test    eax, eax
0x180017aae  js      short loc_180017AC8
0x180017ab0  inc     esi
0x180017ab2  cmp     esi, [rdi+58h]
0x180017ab5  jb      short loc_180017A46
0x180017ab7  test    r15d, r15d
0x180017aba  jnz     short loc_180017AC8
0x180017abc  mov     ebx, 80070002h
0x180017ac1  jmp     short loc_180017AC8
0x180017ac3  mov     ebx, 80070057h
0x180017ac8  test    rdi, rdi
0x180017acb  jz      short loc_180017AD5
0x180017acd  mov     rcx, rdi; this
0x180017ad0  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x180017ad5  mov     eax, ebx
0x180017ad7  add     rsp, 28h
0x180017adb  pop     r15
0x180017add  pop     r14
0x180017adf  pop     r13
0x180017ae1  pop     r12
0x180017ae3  pop     rdi
0x180017ae4  pop     rsi
0x180017ae5  pop     rbp
0x180017ae6  pop     rbx
0x180017ae7  retn
```
