# APPPOOL_CUSTOM_PROVIDER::MapDeleteData(PROPERTY_ENTRY *,ABO_NODE *)

- ea: `0x180019680`
- end: `0x180019794`
- name: `?MapDeleteData@APPPOOL_CUSTOM_PROVIDER@@UEAAJPEAVPROPERTY_ENTRY@@PEAVABO_NODE@@@Z`
- size: `276`
- prototype: `int(APPPOOL_CUSTOM_PROVIDER *__hidden this, struct PROPERTY_ENTRY *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180003426`
- `0x180003f14`
- `0x1800047e4`
- `0x18001775c`
- `0x180019680`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001970a`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001970a`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180019727`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180019727`

## pseudocode

```c
__int64 __fastcall APPPOOL_CUSTOM_PROVIDER::MapDeleteData(
        APPPOOL_CUSTOM_PROVIDER *this,
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
0x180019680  push    rbx
0x180019682  push    rbp
0x180019683  push    rsi
0x180019684  push    rdi
0x180019685  push    r12
0x180019687  push    r13
0x180019689  push    r14
0x18001968b  push    r15
0x18001968d  sub     rsp, 28h
0x180019691  mov     rsi, r8
0x180019694  mov     r14, rdx
0x180019697  test    rdx, rdx
0x18001969a  jz      loc_18001977C
0x1800196a0  test    r8, r8
0x1800196a3  jz      loc_18001977C
0x1800196a9  cmp     r8, [rcx+10h]
0x1800196ad  jz      short loc_1800196B9
0x1800196af  mov     ebx, 80070002h
0x1800196b4  jmp     loc_180019781
0x1800196b9  mov     r15, [rcx+18h]
0x1800196bd  xor     edi, edi
0x1800196bf  mov     [rsp+68h+arg_8], rdi
0x1800196c4  test    r15, r15
0x1800196c7  jz      loc_180019768
0x1800196cd  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x1800196d4  lea     r8, [rsp+68h+arg_8]
0x1800196d9  add     rcx, 8
0x1800196dd  lea     rdx, aApplicationpoo_0; "applicationPool"
0x1800196e4  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x1800196e9  mov     rdi, [rsp+68h+arg_8]
0x1800196ee  test    eax, eax
0x1800196f0  jnz     short loc_180019761
0x1800196f2  xor     ebx, ebx
0x1800196f4  xor     r12d, r12d
0x1800196f7  xor     ebp, ebp
0x1800196f9  cmp     [rdi+58h], ebx
0x1800196fc  jbe     short loc_180019761
0x1800196fe  mov     rax, [rdi+50h]
0x180019702  mov     r13, [rax+rbp*8]
0x180019706  lea     rcx, [r13+20h]
0x18001970a  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180019710  mov     rcx, rax; String1
0x180019713  lea     rdx, aApplicationpoo_0; "applicationPool"
0x18001971a  call    wcscmp_0
0x18001971f  test    eax, eax
0x180019721  jnz     short loc_180019755
0x180019723  lea     rcx, [r14+10h]
0x180019727  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001972d  mov     ecx, [rax]
0x18001972f  cmp     [r13+90h], ecx
0x180019736  jnz     short loc_180019755
0x180019738  mov     r9, r15; struct INativeConfigurationElement *
0x18001973b  mov     r8, rsi; struct ABO_NODE *
0x18001973e  mov     rdx, r13; struct PROPERTY_MAPPING *
0x180019741  mov     rcx, r14; struct PROPERTY_ENTRY *
0x180019744  mov     r12d, 1
0x18001974a  call    ?DeleteConfigPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(PROPERTY_ENTRY *,PROPERTY_MAPPING *,ABO_NODE *,INativeConfigurationElement *)
0x18001974f  mov     ebx, eax
0x180019751  test    eax, eax
0x180019753  js      short loc_18001976D
0x180019755  inc     ebp
0x180019757  cmp     ebp, [rdi+58h]
0x18001975a  jb      short loc_1800196FE
0x18001975c  test    r12d, r12d
0x18001975f  jnz     short loc_18001976D
0x180019761  mov     ebx, 80070002h
0x180019766  jmp     short loc_18001976D
0x180019768  mov     ebx, 80070057h
0x18001976d  test    rdi, rdi
0x180019770  jz      short loc_180019781
0x180019772  mov     rcx, rdi; this
0x180019775  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18001977a  jmp     short loc_180019781
0x18001977c  mov     ebx, 80070057h
0x180019781  mov     eax, ebx
0x180019783  add     rsp, 28h
0x180019787  pop     r15
0x180019789  pop     r14
0x18001978b  pop     r13
0x18001978d  pop     r12
0x18001978f  pop     rdi
0x180019790  pop     rsi
0x180019791  pop     rbp
0x180019792  pop     rbx
0x180019793  retn
```
