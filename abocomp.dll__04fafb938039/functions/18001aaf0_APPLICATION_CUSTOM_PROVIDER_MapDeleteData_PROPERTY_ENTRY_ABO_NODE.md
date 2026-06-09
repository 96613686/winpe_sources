# APPLICATION_CUSTOM_PROVIDER::MapDeleteData(PROPERTY_ENTRY *,ABO_NODE *)

- ea: `0x18001aaf0`
- end: `0x18001ad07`
- name: `?MapDeleteData@APPLICATION_CUSTOM_PROVIDER@@UEAAJPEAVPROPERTY_ENTRY@@PEAVABO_NODE@@@Z`
- size: `535`
- prototype: `__int64 __fastcall(APPLICATION_CUSTOM_PROVIDER *__hidden this, struct PROPERTY_ENTRY *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config`

## callees

- `0x180003426`
- `0x180003f14`
- `0x1800047e4`
- `0x1800077dc`
- `0x18000a4e8`
- `0x18000ace4`
- `0x18000fec4`
- `0x18001775c`
- `0x18001a4f8`
- `0x18001aaf0`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001abc5`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001abc5`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001ab41`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001ab56`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001abe1`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001ac40`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001ab41`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001ab56`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001abe1`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001ac40`

## pseudocode

```c
__int64 __fastcall APPLICATION_CUSTOM_PROVIDER::MapDeleteData(
        struct ABO_NODE **this,
        struct PROPERTY_ENTRY *a2,
        struct ABO_NODE *a3)
{
  struct PROPERTY_ENTRY *v3; // r14
  int v7; // ebx
  BUFFER *v8; // r15
  struct INativeConfigurationElement *v9; // rax
  HANDLE_ENTRY *v10; // rsi
  int Key; // eax
  __int64 v12; // r12
  const wchar_t *Str; // rax
  _DWORD *Ptr; // rax
  int Entry; // eax
  HANDLE_ENTRY *v17; // [rsp+20h] [rbp-38h] BYREF
  struct INativeConfigurationElement *v18; // [rsp+28h] [rbp-30h]
  int v19; // [rsp+68h] [rbp+10h]
  struct PROPERTY_ENTRY *v20; // [rsp+78h] [rbp+20h] BYREF

  v3 = 0;
  v20 = 0;
  if ( a2 && a3 )
  {
    if ( a3 != this[2] )
      return (unsigned int)-2147024894;
    v8 = (struct PROPERTY_ENTRY *)((char *)a2 + 16);
    if ( *(_DWORD *)BUFFER::QueryPtr((struct PROPERTY_ENTRY *)((char *)a2 + 16)) == 2103
      || *(_DWORD *)BUFFER::QueryPtr(v8) == 2104 )
    {
      v7 = APPLICATION_CUSTOM_PROVIDER::DeleteAppIds((APPLICATION_CUSTOM_PROVIDER *)this);
      if ( v7 < 0 )
        return (unsigned int)v7;
      v7 = ABO_NODE::UnMapNodeAndChildren(a3);
      if ( v7 < 0 )
        return (unsigned int)v7;
      v7 = ABO_NODE::MapNodeAndChildren(a3);
      if ( v7 >= 0 )
        return (unsigned int)v7;
    }
    else
    {
      v9 = this[3];
      v10 = 0;
      v17 = 0;
      v18 = v9;
      if ( v9 )
      {
        Key = CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::FindKey(
                (char *)g_pPropertySectionTable + 8,
                L"application",
                &v17);
        v10 = v17;
        if ( Key || (v7 = 0, v19 = 0, v12 = 0, !*((_DWORD *)v17 + 22)) )
        {
LABEL_15:
          v7 = -2147024894;
        }
        else
        {
          while ( 1 )
          {
            v17 = *(HANDLE_ENTRY **)(*((_QWORD *)v10 + 10) + 8 * v12);
            Str = STRU::QueryStr((HANDLE_ENTRY *)((char *)v17 + 32));
            if ( !wcscmp_0(Str, L"application") )
            {
              Ptr = BUFFER::QueryPtr(v8);
              if ( *((_DWORD *)v17 + 36) == *Ptr )
              {
                v19 = 1;
                v7 = CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(a2, v17, a3, v18);
                if ( v7 < 0 )
                  break;
              }
            }
            v12 = (unsigned int)(v12 + 1);
            if ( (unsigned int)v12 >= *((_DWORD *)v10 + 22) )
            {
              if ( v19 )
                break;
              goto LABEL_15;
            }
          }
        }
      }
      else
      {
        v7 = -2147024809;
      }
      if ( v10 )
        HANDLE_ENTRY::DereferenceHandleEntry(v10);
      if ( *(_DWORD *)BUFFER::QueryPtr(v8) == 9101 )
      {
        Entry = PROPERTY_BAG::FindEntry((struct ABO_NODE *)((char *)a3 + 184), 0x837u, &v20);
        v7 = Entry;
        if ( Entry < 0 )
        {
          if ( Entry != -2147024894
            || (v7 = PROPERTY_BAG::FindEntry((struct ABO_NODE *)((char *)a3 + 184), 0x838u, &v20), v7 < 0) )
          {
            v7 = ABO_NODE::UnMapNodeAndChildren(a3);
            if ( v7 >= 0 )
              v7 = ABO_NODE::MapNodeAndChildren(a3);
          }
        }
        v3 = v20;
      }
    }
  }
  else
  {
    v7 = -2147024809;
  }
  if ( v3 )
    PROPERTY_MAPPING::DereferencePropertyMapping(v3);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001aaf0  mov     [rsp+arg_0], rbx
0x18001aaf5  mov     [rsp+arg_10], rsi
0x18001aafa  push    rdi
0x18001aafb  push    r12
0x18001aafd  push    r13
0x18001aaff  push    r14
0x18001ab01  push    r15
0x18001ab03  sub     rsp, 30h
0x18001ab07  xor     r14d, r14d
0x18001ab0a  mov     rdi, r8
0x18001ab0d  mov     [rsp+58h+arg_18], r14
0x18001ab12  mov     r13, rdx
0x18001ab15  mov     rbx, rcx
0x18001ab18  test    rdx, rdx
0x18001ab1b  jz      loc_18001ACDB
0x18001ab21  test    r8, r8
0x18001ab24  jz      loc_18001ACDB
0x18001ab2a  cmp     r8, [rcx+10h]
0x18001ab2e  jz      short loc_18001AB3A
0x18001ab30  mov     ebx, 80070002h
0x18001ab35  jmp     loc_18001ACED
0x18001ab3a  lea     r15, [rdx+10h]
0x18001ab3e  mov     rcx, r15
0x18001ab41  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001ab47  cmp     dword ptr [rax], 837h
0x18001ab4d  jz      loc_18001ACAF
0x18001ab53  mov     rcx, r15
0x18001ab56  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001ab5c  cmp     dword ptr [rax], 838h
0x18001ab62  jz      loc_18001ACAF
0x18001ab68  mov     rax, [rbx+18h]
0x18001ab6c  xor     esi, esi
0x18001ab6e  mov     [rsp+58h+var_38], rsi
0x18001ab73  mov     [rsp+58h+var_30], rax
0x18001ab78  test    rax, rax
0x18001ab7b  jz      loc_18001AC2B
0x18001ab81  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x18001ab88  lea     r8, [rsp+58h+var_38]
0x18001ab8d  add     rcx, 8
0x18001ab91  lea     rdx, aApplication; "application"
0x18001ab98  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x18001ab9d  mov     rsi, [rsp+58h+var_38]
0x18001aba2  test    eax, eax
0x18001aba4  jnz     short loc_18001AC24
0x18001aba6  xor     ebx, ebx
0x18001aba8  mov     [rsp+58h+arg_8], eax
0x18001abac  xor     r12d, r12d
0x18001abaf  cmp     [rsi+58h], eax
0x18001abb2  jbe     short loc_18001AC24
0x18001abb4  mov     rax, [rsi+50h]
0x18001abb8  mov     rax, [rax+r12*8]
0x18001abbc  mov     [rsp+58h+var_38], rax
0x18001abc1  lea     rcx, [rax+20h]
0x18001abc5  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18001abcb  mov     rcx, rax; String1
0x18001abce  lea     rdx, aApplication; "application"
0x18001abd5  call    wcscmp_0
0x18001abda  test    eax, eax
0x18001abdc  jnz     short loc_18001AC14
0x18001abde  mov     rcx, r15
0x18001abe1  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001abe7  mov     rdx, [rsp+58h+var_38]; struct PROPERTY_MAPPING *
0x18001abec  mov     ecx, [rax]
0x18001abee  cmp     [rdx+90h], ecx
0x18001abf4  jnz     short loc_18001AC14
0x18001abf6  mov     r9, [rsp+58h+var_30]; struct INativeConfigurationElement *
0x18001abfb  mov     r8, rdi; struct ABO_NODE *
0x18001abfe  mov     rcx, r13; struct PROPERTY_ENTRY *
0x18001ac01  mov     [rsp+58h+arg_8], 1
0x18001ac09  call    ?DeleteConfigPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(PROPERTY_ENTRY *,PROPERTY_MAPPING *,ABO_NODE *,INativeConfigurationElement *)
0x18001ac0e  mov     ebx, eax
0x18001ac10  test    eax, eax
0x18001ac12  js      short loc_18001AC30
0x18001ac14  inc     r12d
0x18001ac17  cmp     r12d, [rsi+58h]
0x18001ac1b  jb      short loc_18001ABB4
0x18001ac1d  cmp     [rsp+58h+arg_8], r14d
0x18001ac22  jnz     short loc_18001AC30
0x18001ac24  mov     ebx, 80070002h
0x18001ac29  jmp     short loc_18001AC30
0x18001ac2b  mov     ebx, 80070057h
0x18001ac30  test    rsi, rsi
0x18001ac33  jz      short loc_18001AC3D
0x18001ac35  mov     rcx, rsi; this
0x18001ac38  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18001ac3d  mov     rcx, r15
0x18001ac40  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001ac46  cmp     dword ptr [rax], 238Dh
0x18001ac4c  jnz     loc_18001ACE0
0x18001ac52  lea     rsi, [rdi+0B8h]
0x18001ac59  mov     edx, 837h; unsigned int
0x18001ac5e  mov     rcx, rsi; this
0x18001ac61  lea     r8, [rsp+58h+arg_18]; struct PROPERTY_ENTRY **
0x18001ac66  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x18001ac6b  mov     ebx, eax
0x18001ac6d  test    eax, eax
0x18001ac6f  jns     short loc_18001ACA8
0x18001ac71  cmp     eax, 80070002h
0x18001ac76  jnz     short loc_18001AC90
0x18001ac78  lea     r8, [rsp+58h+arg_18]; struct PROPERTY_ENTRY **
0x18001ac7d  mov     edx, 838h; unsigned int
0x18001ac82  mov     rcx, rsi; this
0x18001ac85  call    ?FindEntry@PROPERTY_BAG@@QEAAJKPEAPEAVPROPERTY_ENTRY@@@Z; PROPERTY_BAG::FindEntry(ulong,PROPERTY_ENTRY * *)
0x18001ac8a  mov     ebx, eax
0x18001ac8c  test    eax, eax
0x18001ac8e  jns     short loc_18001ACA8
0x18001ac90  mov     rcx, rdi; this
0x18001ac93  call    ?UnMapNodeAndChildren@ABO_NODE@@QEAAJXZ; ABO_NODE::UnMapNodeAndChildren(void)
0x18001ac98  mov     ebx, eax
0x18001ac9a  test    eax, eax
0x18001ac9c  js      short loc_18001ACA8
0x18001ac9e  mov     rcx, rdi; this
0x18001aca1  call    ?MapNodeAndChildren@ABO_NODE@@QEAAJXZ; ABO_NODE::MapNodeAndChildren(void)
0x18001aca6  mov     ebx, eax
0x18001aca8  mov     r14, [rsp+58h+arg_18]
0x18001acad  jmp     short loc_18001ACE0
0x18001acaf  mov     rcx, rbx; this
0x18001acb2  call    ?DeleteAppIds@APPLICATION_CUSTOM_PROVIDER@@AEAAJXZ; APPLICATION_CUSTOM_PROVIDER::DeleteAppIds(void)
0x18001acb7  mov     ebx, eax
0x18001acb9  test    eax, eax
0x18001acbb  js      short loc_18001ACED
0x18001acbd  mov     rcx, rdi; this
0x18001acc0  call    ?UnMapNodeAndChildren@ABO_NODE@@QEAAJXZ; ABO_NODE::UnMapNodeAndChildren(void)
0x18001acc5  mov     ebx, eax
0x18001acc7  test    eax, eax
0x18001acc9  js      short loc_18001ACED
0x18001accb  mov     rcx, rdi; this
0x18001acce  call    ?MapNodeAndChildren@ABO_NODE@@QEAAJXZ; ABO_NODE::MapNodeAndChildren(void)
0x18001acd3  mov     ebx, eax
0x18001acd5  test    eax, eax
0x18001acd7  js      short loc_18001ACE0
0x18001acd9  jmp     short loc_18001ACED
0x18001acdb  mov     ebx, 80070057h
0x18001ace0  test    r14, r14
0x18001ace3  jz      short loc_18001ACED
0x18001ace5  mov     rcx, r14; this
0x18001ace8  call    ?DereferencePropertyMapping@PROPERTY_MAPPING@@QEAAXXZ; PROPERTY_MAPPING::DereferencePropertyMapping(void)
0x18001aced  mov     rsi, [rsp+58h+arg_10]
0x18001acf2  mov     eax, ebx
0x18001acf4  mov     rbx, [rsp+58h+arg_0]
0x18001acf9  add     rsp, 30h
0x18001acfd  pop     r15
0x18001acff  pop     r14
0x18001ad01  pop     r13
0x18001ad03  pop     r12
0x18001ad05  pop     rdi
0x18001ad06  retn
```
