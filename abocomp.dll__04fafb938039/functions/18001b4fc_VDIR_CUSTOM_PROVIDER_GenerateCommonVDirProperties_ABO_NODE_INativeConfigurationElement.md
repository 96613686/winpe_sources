# VDIR_CUSTOM_PROVIDER::GenerateCommonVDirProperties(ABO_NODE *,INativeConfigurationElement *)

- ea: `0x18001b4fc`
- end: `0x18001b5a4`
- name: `?GenerateCommonVDirProperties@VDIR_CUSTOM_PROVIDER@@SAJPEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z`
- size: `168`
- prototype: `__int64 __fastcall(struct ABO_NODE *, struct INativeConfigurationElement *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012a30`
- `0x180014b90`
- `0x18001b5b0`

## callees

- `0x180003f14`
- `0x1800047e4`
- `0x180017d90`
- `0x18001b4fc`

## string_xrefs

- `0x18001b536`: `virtualDirectory`

## pseudocode

```c
__int64 __fastcall VDIR_CUSTOM_PROVIDER::GenerateCommonVDirProperties(
        struct ABO_NODE *a1,
        struct INativeConfigurationElement *a2)
{
  int Key; // eax
  HANDLE_ENTRY *v5; // rdi
  int v6; // ebx
  __int64 v7; // rsi
  HANDLE_ENTRY *v9; // [rsp+40h] [rbp+8h] BYREF

  if ( a1 && a2 )
  {
    v9 = 0;
    Key = CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::FindKey(
            (char *)g_pPropertySectionTable + 8,
            L"virtualDirectory",
            &v9);
    v5 = v9;
    if ( Key )
    {
      v6 = -2147024894;
    }
    else
    {
      v6 = 0;
      v7 = 0;
      if ( *((_DWORD *)v9 + 22) )
      {
        do
        {
          v6 = CUSTOM_PROPERTY_PROVIDER::SetAboPropertiesByMapping(
                 a2,
                 *(struct PROPERTY_MAPPING **)(*((_QWORD *)v5 + 10) + 8 * v7),
                 a1);
          if ( v6 < 0 )
            break;
          v7 = (unsigned int)(v7 + 1);
        }
        while ( (unsigned int)v7 < *((_DWORD *)v5 + 22) );
      }
    }
    if ( v5 )
      HANDLE_ENTRY::DereferenceHandleEntry(v5);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001b4fc  mov     rax, rsp
0x18001b4ff  mov     [rax+10h], rbx
0x18001b503  mov     [rax+18h], rbp
0x18001b507  push    rsi
0x18001b508  push    rdi
0x18001b509  push    r14
0x18001b50b  sub     rsp, 20h
0x18001b50f  mov     rbp, rdx
0x18001b512  mov     r14, rcx
0x18001b515  test    rcx, rcx
0x18001b518  jz      short loc_18001B58A
0x18001b51a  test    rdx, rdx
0x18001b51d  jz      short loc_18001B58A
0x18001b51f  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x18001b526  lea     r8, [rax+8]
0x18001b52a  add     rcx, 8
0x18001b52e  mov     qword ptr [rax+8], 0
0x18001b536  lea     rdx, aVirtualdirecto_0; "virtualDirectory"
0x18001b53d  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x18001b542  mov     rdi, [rsp+38h+arg_0]
0x18001b547  test    eax, eax
0x18001b549  jz      short loc_18001B552
0x18001b54b  mov     ebx, 80070002h
0x18001b550  jmp     short loc_18001B57B
0x18001b552  xor     ebx, ebx
0x18001b554  xor     esi, esi
0x18001b556  cmp     [rdi+58h], ebx
0x18001b559  jbe     short loc_18001B57B
0x18001b55b  mov     rdx, [rdi+50h]
0x18001b55f  mov     r8, r14; struct ABO_NODE *
0x18001b562  mov     rcx, rbp; struct INativeConfigurationElement *
0x18001b565  mov     rdx, [rdx+rsi*8]; struct PROPERTY_MAPPING *
0x18001b569  call    ?SetAboPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVINativeConfigurationElement@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@@Z; CUSTOM_PROPERTY_PROVIDER::SetAboPropertiesByMapping(INativeConfigurationElement *,PROPERTY_MAPPING *,ABO_NODE *)
0x18001b56e  mov     ebx, eax
0x18001b570  test    eax, eax
0x18001b572  js      short loc_18001B57B
0x18001b574  inc     esi
0x18001b576  cmp     esi, [rdi+58h]
0x18001b579  jb      short loc_18001B55B
0x18001b57b  test    rdi, rdi
0x18001b57e  jz      short loc_18001B58F
0x18001b580  mov     rcx, rdi; this
0x18001b583  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18001b588  jmp     short loc_18001B58F
0x18001b58a  mov     ebx, 80070057h
0x18001b58f  mov     rbp, [rsp+38h+arg_10]
0x18001b594  mov     eax, ebx
0x18001b596  mov     rbx, [rsp+38h+arg_8]
0x18001b59b  add     rsp, 20h
0x18001b59f  pop     r14
0x18001b5a1  pop     rdi
0x18001b5a2  pop     rsi
0x18001b5a3  retn
```
