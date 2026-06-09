# VDIR_CUSTOM_PROVIDER::MapDeleteData(PROPERTY_ENTRY *,ABO_NODE *)

- ea: `0x18001b630`
- end: `0x18001b76e`
- name: `?MapDeleteData@VDIR_CUSTOM_PROVIDER@@UEAAJPEAVPROPERTY_ENTRY@@PEAVABO_NODE@@@Z`
- size: `318`
- prototype: `int(VDIR_CUSTOM_PROVIDER *__hidden this, struct PROPERTY_ENTRY *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180003426`
- `0x180003f14`
- `0x1800047e4`
- `0x18000ace4`
- `0x18001775c`
- `0x18001b630`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001b6e3`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001b6e3`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001b670`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001b700`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001b670`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001b700`

## string_xrefs

- `0x18001b6b1`: `virtualDirectory`
- `0x18001b6ec`: `virtualDirectory`

## pseudocode

```c
__int64 __fastcall VDIR_CUSTOM_PROVIDER::MapDeleteData(
        VDIR_CUSTOM_PROVIDER *this,
        struct PROPERTY_ENTRY *a2,
        struct ABO_NODE *a3)
{
  int v6; // ebx
  struct INativeConfigurationElement *v7; // r12
  HANDLE_ENTRY *v8; // rdi
  int Key; // eax
  int v10; // r15d
  __int64 v11; // rbp
  const wchar_t *Str; // rax
  _DWORD *Ptr; // rax
  HANDLE_ENTRY *v15; // [rsp+78h] [rbp+10h] BYREF

  if ( a2 && a3 )
  {
    if ( a3 == *((struct ABO_NODE **)this + 2) )
    {
      if ( *(_DWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a2 + 16)) == 3001 )
      {
        return (unsigned int)ABO_NODE::UnMapNodeAndChildren(a3);
      }
      else
      {
        v7 = (struct INativeConfigurationElement *)*((_QWORD *)this + 4);
        v8 = 0;
        v15 = 0;
        if ( v7 )
        {
          Key = CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::FindKey(
                  (char *)g_pPropertySectionTable + 8,
                  L"virtualDirectory",
                  &v15);
          v8 = v15;
          if ( Key || (v6 = 0, v10 = 0, v11 = 0, !*((_DWORD *)v15 + 22)) )
          {
LABEL_15:
            v6 = -2147024894;
          }
          else
          {
            while ( 1 )
            {
              v15 = *(HANDLE_ENTRY **)(*((_QWORD *)v8 + 10) + 8 * v11);
              Str = STRU::QueryStr((HANDLE_ENTRY *)((char *)v15 + 32));
              if ( !wcscmp_0(Str, L"virtualDirectory") )
              {
                Ptr = BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a2 + 16));
                if ( *((_DWORD *)v15 + 36) == *Ptr )
                {
                  v10 = 1;
                  v6 = CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(a2, v15, a3, v7);
                  if ( v6 < 0 )
                    break;
                }
              }
              v11 = (unsigned int)(v11 + 1);
              if ( (unsigned int)v11 >= *((_DWORD *)v8 + 22) )
              {
                if ( v10 )
                  break;
                goto LABEL_15;
              }
            }
          }
        }
        else
        {
          v6 = -2147024809;
        }
        if ( v8 )
          HANDLE_ENTRY::DereferenceHandleEntry(v8);
      }
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
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001b630  push    rbx
0x18001b632  push    rbp
0x18001b633  push    rsi
0x18001b634  push    rdi
0x18001b635  push    r12
0x18001b637  push    r13
0x18001b639  push    r14
0x18001b63b  push    r15
0x18001b63d  sub     rsp, 28h
0x18001b641  mov     rsi, r8
0x18001b644  mov     r14, rdx
0x18001b647  mov     rbx, rcx
0x18001b64a  test    rdx, rdx
0x18001b64d  jz      loc_18001B756
0x18001b653  test    r8, r8
0x18001b656  jz      loc_18001B756
0x18001b65c  cmp     r8, [rcx+10h]
0x18001b660  jz      short loc_18001B66C
0x18001b662  mov     ebx, 80070002h
0x18001b667  jmp     loc_18001B75B
0x18001b66c  lea     rcx, [rdx+10h]
0x18001b670  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001b676  cmp     dword ptr [rax], 0BB9h
0x18001b67c  jnz     short loc_18001B68D
0x18001b67e  mov     rcx, rsi; this
0x18001b681  call    ?UnMapNodeAndChildren@ABO_NODE@@QEAAJXZ; ABO_NODE::UnMapNodeAndChildren(void)
0x18001b686  mov     ebx, eax
0x18001b688  jmp     loc_18001B75B
0x18001b68d  mov     r12, [rbx+20h]
0x18001b691  xor     edi, edi
0x18001b693  mov     [rsp+68h+arg_8], rdi
0x18001b698  test    r12, r12
0x18001b69b  jz      loc_18001B742
0x18001b6a1  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x18001b6a8  lea     r8, [rsp+68h+arg_8]
0x18001b6ad  add     rcx, 8
0x18001b6b1  lea     rdx, aVirtualdirecto_0; "virtualDirectory"
0x18001b6b8  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x18001b6bd  mov     rdi, [rsp+68h+arg_8]
0x18001b6c2  test    eax, eax
0x18001b6c4  jnz     short loc_18001B73B
0x18001b6c6  xor     ebx, ebx
0x18001b6c8  xor     r15d, r15d
0x18001b6cb  xor     ebp, ebp
0x18001b6cd  cmp     [rdi+58h], ebx
0x18001b6d0  jbe     short loc_18001B73B
0x18001b6d2  mov     rax, [rdi+50h]
0x18001b6d6  mov     rax, [rax+rbp*8]
0x18001b6da  mov     [rsp+68h+arg_8], rax
0x18001b6df  lea     rcx, [rax+20h]
0x18001b6e3  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18001b6e9  mov     rcx, rax; String1
0x18001b6ec  lea     rdx, aVirtualdirecto_0; "virtualDirectory"
0x18001b6f3  call    wcscmp_0
0x18001b6f8  test    eax, eax
0x18001b6fa  jnz     short loc_18001B72F
0x18001b6fc  lea     rcx, [r14+10h]
0x18001b700  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001b706  mov     rdx, [rsp+68h+arg_8]; struct PROPERTY_MAPPING *
0x18001b70b  mov     ecx, [rax]
0x18001b70d  cmp     [rdx+90h], ecx
0x18001b713  jnz     short loc_18001B72F
0x18001b715  mov     r9, r12; struct INativeConfigurationElement *
0x18001b718  mov     r8, rsi; struct ABO_NODE *
0x18001b71b  mov     rcx, r14; struct PROPERTY_ENTRY *
0x18001b71e  mov     r15d, 1
0x18001b724  call    ?DeleteConfigPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(PROPERTY_ENTRY *,PROPERTY_MAPPING *,ABO_NODE *,INativeConfigurationElement *)
0x18001b729  mov     ebx, eax
0x18001b72b  test    eax, eax
0x18001b72d  js      short loc_18001B747
0x18001b72f  inc     ebp
0x18001b731  cmp     ebp, [rdi+58h]
0x18001b734  jb      short loc_18001B6D2
0x18001b736  test    r15d, r15d
0x18001b739  jnz     short loc_18001B747
0x18001b73b  mov     ebx, 80070002h
0x18001b740  jmp     short loc_18001B747
0x18001b742  mov     ebx, 80070057h
0x18001b747  test    rdi, rdi
0x18001b74a  jz      short loc_18001B75B
0x18001b74c  mov     rcx, rdi; this
0x18001b74f  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18001b754  jmp     short loc_18001B75B
0x18001b756  mov     ebx, 80070057h
0x18001b75b  mov     eax, ebx
0x18001b75d  add     rsp, 28h
0x18001b761  pop     r15
0x18001b763  pop     r14
0x18001b765  pop     r13
0x18001b767  pop     r12
0x18001b769  pop     rdi
0x18001b76a  pop     rsi
0x18001b76b  pop     rbp
0x18001b76c  pop     rbx
0x18001b76d  retn
```
