# VDIR_CUSTOM_PROVIDER::MapSetData(PROPERTY_ENTRY *,ABO_NODE *)

- ea: `0x18001b7b0`
- end: `0x18001b8c4`
- name: `?MapSetData@VDIR_CUSTOM_PROVIDER@@UEAAJPEAVPROPERTY_ENTRY@@PEAVABO_NODE@@@Z`
- size: `276`
- prototype: `int(VDIR_CUSTOM_PROVIDER *__hidden this, struct PROPERTY_ENTRY *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180003426`
- `0x180003f14`
- `0x1800047e4`
- `0x1800187e0`
- `0x18001b7b0`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001b83a`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001b83a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001b857`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001b857`

## string_xrefs

- `0x18001b80d`: `virtualDirectory`
- `0x18001b843`: `virtualDirectory`

## pseudocode

```c
__int64 __fastcall VDIR_CUSTOM_PROVIDER::MapSetData(
        VDIR_CUSTOM_PROVIDER *this,
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
                L"virtualDirectory",
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
            if ( !wcscmp_0(Str, L"virtualDirectory")
              && v11[36] == *(_DWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a2 + 16)) )
            {
              v9 = 1;
              v5 = CUSTOM_PROPERTY_PROVIDER::SetConfigPropertiesByMapping(a2, (struct PROPERTY_MAPPING *)v11, a3, v6);
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
0x18001b7b0  push    rbx
0x18001b7b2  push    rbp
0x18001b7b3  push    rsi
0x18001b7b4  push    rdi
0x18001b7b5  push    r12
0x18001b7b7  push    r13
0x18001b7b9  push    r14
0x18001b7bb  push    r15
0x18001b7bd  sub     rsp, 28h
0x18001b7c1  mov     rsi, r8
0x18001b7c4  mov     r14, rdx
0x18001b7c7  test    rdx, rdx
0x18001b7ca  jz      loc_18001B8AC
0x18001b7d0  test    r8, r8
0x18001b7d3  jz      loc_18001B8AC
0x18001b7d9  cmp     r8, [rcx+10h]
0x18001b7dd  jz      short loc_18001B7E9
0x18001b7df  mov     ebx, 80070002h
0x18001b7e4  jmp     loc_18001B8B1
0x18001b7e9  mov     r15, [rcx+20h]
0x18001b7ed  xor     edi, edi
0x18001b7ef  mov     [rsp+68h+arg_8], rdi
0x18001b7f4  test    r15, r15
0x18001b7f7  jz      loc_18001B898
0x18001b7fd  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x18001b804  lea     r8, [rsp+68h+arg_8]
0x18001b809  add     rcx, 8
0x18001b80d  lea     rdx, aVirtualdirecto_0; "virtualDirectory"
0x18001b814  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x18001b819  mov     rdi, [rsp+68h+arg_8]
0x18001b81e  test    eax, eax
0x18001b820  jnz     short loc_18001B891
0x18001b822  xor     ebx, ebx
0x18001b824  xor     r12d, r12d
0x18001b827  xor     ebp, ebp
0x18001b829  cmp     [rdi+58h], ebx
0x18001b82c  jbe     short loc_18001B891
0x18001b82e  mov     rax, [rdi+50h]
0x18001b832  mov     r13, [rax+rbp*8]
0x18001b836  lea     rcx, [r13+20h]
0x18001b83a  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18001b840  mov     rcx, rax; String1
0x18001b843  lea     rdx, aVirtualdirecto_0; "virtualDirectory"
0x18001b84a  call    wcscmp_0
0x18001b84f  test    eax, eax
0x18001b851  jnz     short loc_18001B885
0x18001b853  lea     rcx, [r14+10h]
0x18001b857  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001b85d  mov     ecx, [rax]
0x18001b85f  cmp     [r13+90h], ecx
0x18001b866  jnz     short loc_18001B885
0x18001b868  mov     r9, r15; struct INativeConfigurationElement *
0x18001b86b  mov     r8, rsi; struct ABO_NODE *
0x18001b86e  mov     rdx, r13; struct PROPERTY_MAPPING *
0x18001b871  mov     rcx, r14; struct PROPERTY_ENTRY *
0x18001b874  mov     r12d, 1
0x18001b87a  call    ?SetConfigPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::SetConfigPropertiesByMapping(PROPERTY_ENTRY *,PROPERTY_MAPPING *,ABO_NODE *,INativeConfigurationElement *)
0x18001b87f  mov     ebx, eax
0x18001b881  test    eax, eax
0x18001b883  js      short loc_18001B89D
0x18001b885  inc     ebp
0x18001b887  cmp     ebp, [rdi+58h]
0x18001b88a  jb      short loc_18001B82E
0x18001b88c  test    r12d, r12d
0x18001b88f  jnz     short loc_18001B89D
0x18001b891  mov     ebx, 80070002h
0x18001b896  jmp     short loc_18001B89D
0x18001b898  mov     ebx, 80070057h
0x18001b89d  test    rdi, rdi
0x18001b8a0  jz      short loc_18001B8B1
0x18001b8a2  mov     rcx, rdi; this
0x18001b8a5  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18001b8aa  jmp     short loc_18001B8B1
0x18001b8ac  mov     ebx, 80070057h
0x18001b8b1  mov     eax, ebx
0x18001b8b3  add     rsp, 28h
0x18001b8b7  pop     r15
0x18001b8b9  pop     r14
0x18001b8bb  pop     r13
0x18001b8bd  pop     r12
0x18001b8bf  pop     rdi
0x18001b8c0  pop     rsi
0x18001b8c1  pop     rbp
0x18001b8c2  pop     rbx
0x18001b8c3  retn
```
