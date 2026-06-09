# FILTER_CUSTOM_PROVIDER::MapDeleteData(PROPERTY_ENTRY *,ABO_NODE *)

- ea: `0x18001a130`
- end: `0x18001a244`
- name: `?MapDeleteData@FILTER_CUSTOM_PROVIDER@@UEAAJPEAVPROPERTY_ENTRY@@PEAVABO_NODE@@@Z`
- size: `276`
- prototype: `int(FILTER_CUSTOM_PROVIDER *__hidden this, struct PROPERTY_ENTRY *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x180003426`
- `0x180003f14`
- `0x1800047e4`
- `0x18001775c`
- `0x18001a130`

## import_xrefs

- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001a1ba`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x18001a1ba`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001a1d7`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18001a1d7`

## pseudocode

```c
__int64 __fastcall FILTER_CUSTOM_PROVIDER::MapDeleteData(
        FILTER_CUSTOM_PROVIDER *this,
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
                L"filter",
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
            if ( !wcscmp_0(Str, L"filter")
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
0x18001a130  push    rbx
0x18001a132  push    rbp
0x18001a133  push    rsi
0x18001a134  push    rdi
0x18001a135  push    r12
0x18001a137  push    r13
0x18001a139  push    r14
0x18001a13b  push    r15
0x18001a13d  sub     rsp, 28h
0x18001a141  mov     rsi, r8
0x18001a144  mov     r14, rdx
0x18001a147  test    rdx, rdx
0x18001a14a  jz      loc_18001A22C
0x18001a150  test    r8, r8
0x18001a153  jz      loc_18001A22C
0x18001a159  cmp     r8, [rcx+10h]
0x18001a15d  jz      short loc_18001A169
0x18001a15f  mov     ebx, 80070002h
0x18001a164  jmp     loc_18001A231
0x18001a169  mov     r15, [rcx+18h]
0x18001a16d  xor     edi, edi
0x18001a16f  mov     [rsp+68h+arg_8], rdi
0x18001a174  test    r15, r15
0x18001a177  jz      loc_18001A218
0x18001a17d  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x18001a184  lea     r8, [rsp+68h+arg_8]
0x18001a189  add     rcx, 8
0x18001a18d  lea     rdx, aFilter; "filter"
0x18001a194  call    ?FindKey@?$CTypedHashTable@VBINDING_INFO_TABLE@@VBINDING_INFO_ENTRY@@PEBGVCLKRHashTable@@@@QEBA?AW4LK_RETCODE@@QEBGPEAPEAVBINDING_INFO_ENTRY@@@Z; CTypedHashTable<BINDING_INFO_TABLE,BINDING_INFO_ENTRY,ushort const *,CLKRHashTable>::FindKey(ushort const * const,BINDING_INFO_ENTRY * *)
0x18001a199  mov     rdi, [rsp+68h+arg_8]
0x18001a19e  test    eax, eax
0x18001a1a0  jnz     short loc_18001A211
0x18001a1a2  xor     ebx, ebx
0x18001a1a4  xor     r12d, r12d
0x18001a1a7  xor     ebp, ebp
0x18001a1a9  cmp     [rdi+58h], ebx
0x18001a1ac  jbe     short loc_18001A211
0x18001a1ae  mov     rax, [rdi+50h]
0x18001a1b2  mov     r13, [rax+rbp*8]
0x18001a1b6  lea     rcx, [r13+20h]
0x18001a1ba  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x18001a1c0  mov     rcx, rax; String1
0x18001a1c3  lea     rdx, aFilter; "filter"
0x18001a1ca  call    wcscmp_0
0x18001a1cf  test    eax, eax
0x18001a1d1  jnz     short loc_18001A205
0x18001a1d3  lea     rcx, [r14+10h]
0x18001a1d7  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18001a1dd  mov     ecx, [rax]
0x18001a1df  cmp     [r13+90h], ecx
0x18001a1e6  jnz     short loc_18001A205
0x18001a1e8  mov     r9, r15; struct INativeConfigurationElement *
0x18001a1eb  mov     r8, rsi; struct ABO_NODE *
0x18001a1ee  mov     rdx, r13; struct PROPERTY_MAPPING *
0x18001a1f1  mov     rcx, r14; struct PROPERTY_ENTRY *
0x18001a1f4  mov     r12d, 1
0x18001a1fa  call    ?DeleteConfigPropertiesByMapping@CUSTOM_PROPERTY_PROVIDER@@SAJPEAVPROPERTY_ENTRY@@PEAVPROPERTY_MAPPING@@PEAVABO_NODE@@PEAVINativeConfigurationElement@@@Z; CUSTOM_PROPERTY_PROVIDER::DeleteConfigPropertiesByMapping(PROPERTY_ENTRY *,PROPERTY_MAPPING *,ABO_NODE *,INativeConfigurationElement *)
0x18001a1ff  mov     ebx, eax
0x18001a201  test    eax, eax
0x18001a203  js      short loc_18001A21D
0x18001a205  inc     ebp
0x18001a207  cmp     ebp, [rdi+58h]
0x18001a20a  jb      short loc_18001A1AE
0x18001a20c  test    r12d, r12d
0x18001a20f  jnz     short loc_18001A21D
0x18001a211  mov     ebx, 80070002h
0x18001a216  jmp     short loc_18001A21D
0x18001a218  mov     ebx, 80070057h
0x18001a21d  test    rdi, rdi
0x18001a220  jz      short loc_18001A231
0x18001a222  mov     rcx, rdi; this
0x18001a225  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x18001a22a  jmp     short loc_18001A231
0x18001a22c  mov     ebx, 80070057h
0x18001a231  mov     eax, ebx
0x18001a233  add     rsp, 28h
0x18001a237  pop     r15
0x18001a239  pop     r14
0x18001a23b  pop     r13
0x18001a23d  pop     r12
0x18001a23f  pop     rdi
0x18001a240  pop     rsi
0x18001a241  pop     rbp
0x18001a242  pop     rbx
0x18001a243  retn
```
