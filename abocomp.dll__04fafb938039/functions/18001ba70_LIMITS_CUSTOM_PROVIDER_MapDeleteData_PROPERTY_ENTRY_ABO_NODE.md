# LIMITS_CUSTOM_PROVIDER::MapDeleteData(PROPERTY_ENTRY *,ABO_NODE *)

- ea: `0x18001ba70`
- end: `0x18001bb84`
- name: `?MapDeleteData@LIMITS_CUSTOM_PROVIDER@@UEAAJPEAVPROPERTY_ENTRY@@PEAVABO_NODE@@@Z`
- size: `276`
- prototype: `int(LIMITS_CUSTOM_PROVIDER *__hidden this, struct PROPERTY_ENTRY *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180003426`
- `0x180003f14`
- `0x1800047e4`
- `0x18001775c`
- `0x18001ba70`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001bafa`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001bafa`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001bb17`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001bb17`

## pseudocode

```c
__int64 __fastcall LIMITS_CUSTOM_PROVIDER::MapDeleteData(
        LIMITS_CUSTOM_PROVIDER *this,
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
      v6 = (struct INativeConfigurationElement *)*((_QWORD *)this + 3);
      v7 = 0;
      v14 = 0;
      if ( v6 )
      {
        Key = CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,unsigned short const *,CLKRHashTable>::FindKey(
                (char *)g_pPropertySectionTable + 8,
                L"system.applicationHost/webLimits",
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
            if ( !wcscmp_0(Str, L"system.applicationHost/webLimits")
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
0x18001ba70  push    rbx
0x18001ba72  push    rbp
0x18001ba73  push    rsi
0x18001ba74  push    rdi
0x18001ba75  push    r12
0x18001ba77  push    r13
0x18001ba79  push    r14
0x18001ba7b  push    r15
0x18001ba7d  sub     rsp, 28h
0x18001ba81  mov     rsi, r8
0x18001ba84  mov     r14, rdx
0x18001ba87  test    rdx, rdx
0x18001ba8a  jz      loc_18001BB6C
0x18001ba90  test    r8, r8
0x18001ba93  jz      loc_18001BB6C
0x18001ba99  cmp     r8, [rcx+10h]
0x18001ba9d  jz      short loc_18001BAA9
0x18001ba9f  mov     ebx, 80070002h
0x18001baa4  jmp     loc_18001BB71
0x18001baa9  mov     r15, [rcx+18h]
0x18001baad  xor     edi, edi
0x18001baaf  mov     [rsp+68h+arg_8], rdi
0x18001bab4  test    r15, r15
0x18001bab7  jz      loc_18001BB58
0x18001babd  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x18001bac4  lea     r8, [rsp+68h+arg_8]
0x18001bac9  add     rcx, 8
0x18001bacd  lea     rdx, aSystemApplicat_1; "system.applicationHost/webLimits"
0x18001bad4  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x18001bad9  mov     rdi, [rsp+68h+arg_8]
0x18001bade  test    eax, eax
0x18001bae0  jnz     short loc_18001BB51
0x18001bae2  xor     ebx, ebx
0x18001bae4  xor     r12d, r12d
0x18001bae7  xor     ebp, ebp
0x18001bae9  cmp     [rdi+58h], ebx
0x18001baec  jbe     short loc_18001BB51
0x18001baee  mov     rax, [rdi+50h]
0x18001baf2  mov     r13, [rax+rbp*8]
0x18001baf6  lea     rcx, [r13+20h]
0x18001bafa  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18001bb00  mov     rcx, rax; String1
0x18001bb03  lea     rdx, aSystemApplicat_1; "system.applicationHost/webLimits"
0x18001bb0a  call    wcscmp_0
0x18001bb0f  test    eax, eax
0x18001bb11  jnz     short loc_18001BB45
0x18001bb13  lea     rcx, [r14+10h]
0x18001bb17  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001bb1d  mov     ecx, [rax]
0x18001bb1f  cmp     [r13+90h], ecx
0x18001bb26  jnz     short loc_18001BB45
0x18001bb28  mov     r9, r15; struct INativeConfigurationElement *
0x18001bb2b  mov     r8, rsi; struct ABO_NODE *
0x18001bb2e  mov     rdx, r13; struct PROPERTY_MAPPING *
0x18001bb31  mov     rcx, r14; struct PROPERTY_ENTRY *
0x18001bb34  mov     r12d, 1
0x18001bb3a  call    ?DeleteConfigPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(PROPERTY_ENTRY *,PROPERTY_MAPPING *,ABO_NODE *,INativeConfigurationElement *)
0x18001bb3f  mov     ebx, eax
0x18001bb41  test    eax, eax
0x18001bb43  js      short loc_18001BB5D
0x18001bb45  inc     ebp
0x18001bb47  cmp     ebp, [rdi+58h]
0x18001bb4a  jb      short loc_18001BAEE
0x18001bb4c  test    r12d, r12d
0x18001bb4f  jnz     short loc_18001BB5D
0x18001bb51  mov     ebx, 80070002h
0x18001bb56  jmp     short loc_18001BB5D
0x18001bb58  mov     ebx, 80070057h
0x18001bb5d  test    rdi, rdi
0x18001bb60  jz      short loc_18001BB71
0x18001bb62  mov     rcx, rdi; this
0x18001bb65  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18001bb6a  jmp     short loc_18001BB71
0x18001bb6c  mov     ebx, 80070057h
0x18001bb71  mov     eax, ebx
0x18001bb73  add     rsp, 28h
0x18001bb77  pop     r15
0x18001bb79  pop     r14
0x18001bb7b  pop     r13
0x18001bb7d  pop     r12
0x18001bb7f  pop     rdi
0x18001bb80  pop     rsi
0x18001bb81  pop     rbp
0x18001bb82  pop     rbx
0x18001bb83  retn
```
