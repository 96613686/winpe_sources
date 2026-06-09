# PROPERTY_SECTION_TABLE::InitializeTable(void)

- ea: `0x1800016a0`
- end: `0x180001818`
- name: `?InitializeTable@PROPERTY_SECTION_TABLE@@QEAAJXZ`
- size: `376`
- prototype: `__int64 __fastcall(PROPERTY_SECTION_TABLE *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000118c`

## callees

- `0x1800016a0`
- `0x1800021e0`
- `0x180002990`
- `0x180003f14`
- `0x18002c010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800017ea`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800017ea`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180001712`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800017dd`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x180001712`
- `iisutil!?QueryStr@STRU@@QEBAPEBGXZ` at `0x1800017dd`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800017bb`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800017bb`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180001723`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x180001723`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180001803`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180001803`

## pseudocode

```c
__int64 __fastcall PROPERTY_SECTION_TABLE::InitializeTable(PROPERTY_SECTION_TABLE *this)
{
  ARRAY_LIST *v1; // rax
  unsigned int v2; // ebx
  char *v3; // r14
  __int64 v4; // rax
  __int64 v5; // rsi
  const unsigned __int16 *Str; // rax
  unsigned int v7; // r8d
  PROPERTY_SECTION_TABLE *v8; // rdi
  __int64 result; // rax
  unsigned int v10; // ebp
  _DWORD *v11; // rax
  const unsigned __int16 *v12; // rax
  int inserted; // eax
  PROPERTY_SECTION_TABLE *v14; // [rsp+50h] [rbp+8h] BYREF

  v14 = this;
  v1 = g_pPropertyMappingTable;
  if ( !g_pPropertyMappingTable )
    return 2147942450LL;
  v2 = 0;
  if ( !*((_DWORD *)g_pPropertyMappingTable + 2) )
    return 0;
  v3 = (char *)g_pPropertySectionTable + 8;
  while ( 1 )
  {
    v4 = *(_QWORD *)v1;
    v14 = 0;
    v5 = *(_QWORD *)(v4 + 8LL * v2);
    Str = STRU::QueryStr((STRU *)(v5 + 32));
    if ( (unsigned int)CLKRHashTable::FindKey(v3, Str, &v14) )
    {
      v11 = operator new(0x78u);
      v8 = (PROPERTY_SECTION_TABLE *)v11;
      if ( !v11 )
        return 2147942408LL;
      *(_QWORD *)v11 = &PROPERTY_LIST::`vftable';
      v11[2] = 1;
      STRU::STRU((STRU *)(v11 + 4));
      *((_DWORD *)v8 + 18) = 0;
      *((_QWORD *)v8 + 10) = 0;
      *((_QWORD *)v8 + 11) = 0;
      *((_QWORD *)v8 + 12) = 0;
      *((_QWORD *)v8 + 13) = 0;
      *((_QWORD *)v8 + 14) = 0;
      v12 = STRU::QueryStr((STRU *)(v5 + 32));
      v10 = STRU::Copy((PROPERTY_SECTION_TABLE *)((char *)v8 + 16), v12);
      if ( (v10 & 0x80000000) != 0 )
        goto LABEL_22;
      inserted = CLKRHashTable::InsertRecord(v3, v8, 0);
      v10 = inserted;
      if ( inserted )
      {
        if ( inserted > 0 )
          v10 = (unsigned __int16)inserted | 0x80070000;
        goto LABEL_22;
      }
    }
    else
    {
      v8 = v14;
    }
    result = ARRAY_LIST::AddEntry((PROPERTY_SECTION_TABLE *)((char *)v8 + 80), (struct IArrayListEntry *)v5, v7);
    v10 = result;
    if ( (int)result < 0 )
      break;
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 8));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 2, 0xFFFFFFFF) == 1 )
    {
      if ( v8 )
        (**(void (__fastcall ***)(PROPERTY_SECTION_TABLE *, __int64))v8)(v8, 1);
    }
    v1 = g_pPropertyMappingTable;
    if ( ++v2 >= *((_DWORD *)g_pPropertyMappingTable + 2) )
      return v10;
  }
  if ( v8 )
  {
LABEL_22:
    HANDLE_ENTRY::DereferenceHandleEntry(v8);
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x1800016a0  mov     r11, rsp
0x1800016a3  mov     [r11+8], rcx
0x1800016a7  sub     rsp, 48h
0x1800016ab  mov     rax, cs:?g_pPropertyMappingTable@@3PEAVPROPERTY_MAPPING_TABLE@@EA; PROPERTY_MAPPING_TABLE * g_pPropertyMappingTable
0x1800016b2  test    rax, rax
0x1800016b5  jz      loc_180003A0A
0x1800016bb  mov     rcx, cs:?g_pPropertySectionTable@@3PEAVPROPERTY_SECTION_TABLE@@EA; PROPERTY_SECTION_TABLE * g_pPropertySectionTable
0x1800016c2  mov     [r11+10h], rbx
0x1800016c6  mov     [r11-28h], r15
0x1800016ca  xor     r15d, r15d
0x1800016cd  mov     ebx, r15d
0x1800016d0  cmp     [rax+8], r15d
0x1800016d4  jbe     loc_180003A64
0x1800016da  mov     [r11+18h], rbp
0x1800016de  mov     [r11-8], rsi
0x1800016e2  mov     [r11-18h], r12
0x1800016e6  lea     r12, ??_7PROPERTY_LIST@@6B@; const PROPERTY_LIST::`vftable'
0x1800016ed  mov     [r11-20h], r14
0x1800016f1  lea     r14, [rcx+8]
0x1800016f5  mov     [r11-10h], rdi
0x1800016f9  nop     dword ptr [rax+00000000h]
0x180001700  mov     rax, [rax]
0x180001703  mov     ecx, ebx
0x180001705  mov     [rsp+48h+arg_0], r15
0x18000170a  mov     rsi, [rax+rcx*8]
0x18000170e  lea     rcx, [rsi+20h]
0x180001712  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x180001718  lea     r8, [rsp+48h+arg_0]
0x18000171d  mov     rcx, r14
0x180001720  mov     rdx, rax
0x180001723  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x180001729  test    eax, eax
0x18000172b  jnz     short loc_180001797
0x18000172d  mov     rdi, [rsp+48h+arg_0]
0x180001732  lea     rcx, [rdi+50h]; this
0x180001736  mov     rdx, rsi; struct IArrayListEntry *
0x180001739  call    ?AddEntry@ARRAY_LIST@@QEAAJPEAVIArrayListEntry@@K@Z; ARRAY_LIST::AddEntry(IArrayListEntry *,ulong)
0x18000173e  mov     ebp, eax
0x180001740  test    eax, eax
0x180001742  js      loc_180003A4D
0x180001748  lock inc dword ptr [rsi+8]
0x18000174c  mov     eax, 0FFFFFFFFh
0x180001751  lock xadd [rdi+8], eax
0x180001756  cmp     eax, 1
0x180001759  jz      loc_180003A14
0x18000175f  mov     rax, cs:?g_pPropertyMappingTable@@3PEAVPROPERTY_MAPPING_TABLE@@EA; PROPERTY_MAPPING_TABLE * g_pPropertyMappingTable
0x180001766  inc     ebx
0x180001768  cmp     ebx, [rax+8]
0x18000176b  jb      short loc_180001700
0x18000176d  mov     eax, ebp
0x18000176f  mov     rdi, [rsp+48h+var_10]
0x180001774  mov     r12, [rsp+48h+var_18]
0x180001779  mov     r14, [rsp+48h+var_20]
0x18000177e  mov     rsi, [rsp+48h+var_8]
0x180001783  mov     rbp, [rsp+48h+arg_10]
0x180001788  mov     rbx, [rsp+48h+arg_8]
0x18000178d  mov     r15, [rsp+48h+var_28]
0x180001792  add     rsp, 48h
0x180001796  retn
0x180001797  mov     ecx, 78h ; 'x'; Size
0x18000179c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800017a1  mov     rdi, rax
0x1800017a4  test    rax, rax
0x1800017a7  jz      loc_180003A43
0x1800017ad  lea     rcx, [rax+10h]
0x1800017b1  mov     [rax], r12
0x1800017b4  mov     dword ptr [rax+8], 1
0x1800017bb  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800017c1  lea     rcx, [rsi+20h]
0x1800017c5  mov     [rdi+48h], r15d
0x1800017c9  mov     [rdi+50h], r15
0x1800017cd  mov     [rdi+58h], r15
0x1800017d1  mov     [rdi+60h], r15
0x1800017d5  mov     [rdi+68h], r15
0x1800017d9  mov     [rdi+70h], r15
0x1800017dd  call    cs:__imp_?QueryStr@STRU@@QEBAPEBGXZ; STRU::QueryStr(void)
0x1800017e3  mov     rdx, rax
0x1800017e6  lea     rcx, [rdi+10h]
0x1800017ea  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800017f0  mov     ebp, eax
0x1800017f2  test    eax, eax
0x1800017f4  js      loc_180003A56
0x1800017fa  xor     r8d, r8d
0x1800017fd  mov     rdx, rdi
0x180001800  mov     rcx, r14
0x180001803  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x180001809  mov     ebp, eax
0x18000180b  test    eax, eax
0x18000180d  jz      loc_180001732
0x180001813  jmp     loc_180003A36
0x180003a0a  mov     eax, 80070032h
0x180003a0f  jmp     loc_180001792
0x180003a14  test    rdi, rdi
0x180003a17  jz      loc_18000175F
0x180003a1d  mov     rax, [rdi]
0x180003a20  mov     edx, 1
0x180003a25  mov     rcx, rdi
0x180003a28  mov     rax, [rax]
0x180003a2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a30  nop
0x180003a31  jmp     loc_18000175F
0x180003a36  jle     short loc_180003A56
0x180003a38  movzx   ebp, ax
0x180003a3b  or      ebp, 80070000h
0x180003a41  jmp     short loc_180003A56
0x180003a43  mov     eax, 80070008h
0x180003a48  jmp     loc_18000176F
0x180003a4d  test    rdi, rdi
0x180003a50  jz      loc_18000176F
0x180003a56  mov     rcx, rdi; this
0x180003a59  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x180003a5e  nop
0x180003a5f  jmp     loc_18000176D
0x180003a64  mov     eax, r15d
0x180003a67  jmp     loc_180001788
```
