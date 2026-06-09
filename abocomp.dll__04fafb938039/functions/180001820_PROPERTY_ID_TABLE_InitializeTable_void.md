# PROPERTY_ID_TABLE::InitializeTable(void)

- ea: `0x180001820`
- end: `0x18000198b`
- name: `?InitializeTable@PROPERTY_ID_TABLE@@QEAAJXZ`
- size: `363`
- prototype: `__int64 __fastcall(PROPERTY_ID_TABLE *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18000118c`

## callees

- `0x180001820`
- `0x1800021e0`
- `0x180002990`
- `0x180003f14`
- `0x18002c010`

## import_xrefs

- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003a7c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003a7c`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800018ce`
- `iisutil!??0STRU@@QEAA@XZ` at `0x1800018ce`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000189c`
- `iisutil!?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z` at `0x18000189c`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180001906`
- `iisutil!?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z` at `0x180001906`

## pseudocode

```c
__int64 __fastcall PROPERTY_ID_TABLE::InitializeTable(PROPERTY_ID_TABLE *this)
{
  ARRAY_LIST *v1; // rax
  unsigned int v2; // esi
  char *v3; // r14
  __int64 v4; // rax
  __int64 v5; // rdi
  unsigned int v6; // r8d
  _DWORD *v7; // rax
  PROPERTY_ID_TABLE *v8; // rbx
  int v9; // eax
  int inserted; // eax
  unsigned int v11; // ebp
  __int64 result; // rax
  PROPERTY_ID_TABLE *v13; // [rsp+50h] [rbp+8h] BYREF

  v13 = this;
  v1 = g_pPropertyMappingTable;
  if ( !g_pPropertyMappingTable )
    return 2147942450LL;
  v2 = 0;
  if ( !*((_DWORD *)g_pPropertyMappingTable + 2) )
    return 0;
  v3 = (char *)g_pPropertyIdTable + 8;
  while ( 1 )
  {
    v4 = *(_QWORD *)v1;
    v13 = 0;
    v5 = *(_QWORD *)(v4 + 8LL * v2);
    if ( (unsigned int)CLKRHashTable::FindKey(v3, *(unsigned int *)(v5 + 144), &v13) )
    {
      v7 = operator new(0x78u);
      v8 = (PROPERTY_ID_TABLE *)v7;
      if ( !v7 )
        return 2147942408LL;
      *(_QWORD *)v7 = &PROPERTY_LIST::`vftable';
      v7[2] = 1;
      STRU::STRU((STRU *)(v7 + 4));
      *((_DWORD *)v8 + 18) = 0;
      *((_QWORD *)v8 + 10) = 0;
      *((_QWORD *)v8 + 11) = 0;
      *((_QWORD *)v8 + 12) = 0;
      *((_QWORD *)v8 + 13) = 0;
      *((_QWORD *)v8 + 14) = 0;
      v9 = *(_DWORD *)(v5 + 144);
      if ( v9 )
      {
        *((_DWORD *)v8 + 18) = v9;
      }
      else
      {
        v11 = STRU::Copy((PROPERTY_ID_TABLE *)((char *)v8 + 16), 0);
        if ( (v11 & 0x80000000) != 0 )
          goto LABEL_25;
      }
      inserted = CLKRHashTable::InsertRecord(v3, v8, 0);
      v11 = inserted;
      if ( inserted )
      {
        if ( inserted > 0 )
          v11 = (unsigned __int16)inserted | 0x80070000;
        goto LABEL_25;
      }
    }
    else
    {
      v8 = v13;
    }
    result = ARRAY_LIST::AddEntry((PROPERTY_ID_TABLE *)((char *)v8 + 80), (struct IArrayListEntry *)v5, v6);
    v11 = result;
    if ( (int)result < 0 )
      break;
    _InterlockedIncrement((volatile signed __int32 *)(v5 + 8));
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v8 + 2, 0xFFFFFFFF) == 1 )
    {
      if ( v8 )
        (**(void (__fastcall ***)(PROPERTY_ID_TABLE *, __int64))v8)(v8, 1);
    }
    v1 = g_pPropertyMappingTable;
    if ( ++v2 >= *((_DWORD *)g_pPropertyMappingTable + 2) )
      return v11;
  }
  if ( v8 )
  {
LABEL_25:
    HANDLE_ENTRY::DereferenceHandleEntry(v8);
    return v11;
  }
  return result;
}

```

## disassembly

```asm
0x180001820  mov     r11, rsp
0x180001823  mov     [r11+8], rcx
0x180001827  sub     rsp, 48h
0x18000182b  mov     rax, cs:?g_pPropertyMappingTable@@3PEAVPROPERTY_MAPPING_TABLE@@EA; PROPERTY_MAPPING_TABLE * g_pPropertyMappingTable
0x180001832  test    rax, rax
0x180001835  jz      loc_180003A6C
0x18000183b  mov     rcx, cs:?g_pPropertyIdTable@@3PEAVPROPERTY_ID_TABLE@@EA; PROPERTY_ID_TABLE * g_pPropertyIdTable
0x180001842  mov     [r11-8], rsi
0x180001846  mov     [r11-28h], r15
0x18000184a  xor     r15d, r15d
0x18000184d  mov     esi, r15d
0x180001850  cmp     [rax+8], r15d
0x180001854  jbe     loc_180001986
0x18000185a  mov     [r11-10h], rdi
0x18000185e  mov     [r11-18h], r12
0x180001862  lea     r12, ??_7PROPERTY_LIST@@6B@; const PROPERTY_LIST::`vftable'
0x180001869  mov     [r11-20h], r14
0x18000186d  lea     r14, [rcx+8]
0x180001871  mov     [r11+10h], rbx
0x180001875  mov     [r11+18h], rbp
0x180001879  nop     dword ptr [rax+00000000h]
0x180001880  mov     rax, [rax]
0x180001883  lea     r8, [rsp+48h+arg_0]
0x180001888  mov     ecx, esi
0x18000188a  mov     [rsp+48h+arg_0], r15
0x18000188f  mov     rdi, [rax+rcx*8]
0x180001893  mov     rcx, r14
0x180001896  mov     edx, [rdi+90h]
0x18000189c  call    cs:__imp_?FindKey@CLKRHashTable@@QEBA?AW4LK_RETCODE@@_KPEAPEBX@Z; CLKRHashTable::FindKey(unsigned __int64,void const * *)
0x1800018a2  test    eax, eax
0x1800018a4  jz      loc_18000197F
0x1800018aa  mov     ecx, 78h ; 'x'; Size
0x1800018af  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800018b4  mov     rbx, rax
0x1800018b7  test    rax, rax
0x1800018ba  jz      loc_180003ABC
0x1800018c0  lea     rcx, [rax+10h]
0x1800018c4  mov     [rax], r12
0x1800018c7  mov     dword ptr [rax+8], 1
0x1800018ce  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x1800018d4  mov     [rbx+48h], r15d
0x1800018d8  mov     [rbx+50h], r15
0x1800018dc  mov     [rbx+58h], r15
0x1800018e0  mov     [rbx+60h], r15
0x1800018e4  mov     [rbx+68h], r15
0x1800018e8  mov     [rbx+70h], r15
0x1800018ec  mov     eax, [rdi+90h]
0x1800018f2  test    eax, eax
0x1800018f4  jz      loc_180003A76
0x1800018fa  mov     [rbx+48h], eax
0x1800018fd  xor     r8d, r8d
0x180001900  mov     rdx, rbx
0x180001903  mov     rcx, r14
0x180001906  call    cs:__imp_?InsertRecord@CLKRHashTable@@QEAA?AW4LK_RETCODE@@PEBX_N@Z; CLKRHashTable::InsertRecord(void const *,bool)
0x18000190c  mov     ebp, eax
0x18000190e  test    eax, eax
0x180001910  jnz     loc_180003AAF
0x180001916  lea     rcx, [rbx+50h]; this
0x18000191a  mov     rdx, rdi; struct IArrayListEntry *
0x18000191d  call    ?AddEntry@ARRAY_LIST@@QEAAJPEAVIArrayListEntry@@K@Z; ARRAY_LIST::AddEntry(IArrayListEntry *,ulong)
0x180001922  mov     ebp, eax
0x180001924  test    eax, eax
0x180001926  js      loc_180003AC6
0x18000192c  lock inc dword ptr [rdi+8]
0x180001930  mov     eax, 0FFFFFFFFh
0x180001935  lock xadd [rbx+8], eax
0x18000193a  cmp     eax, 1
0x18000193d  jz      loc_180003A8D
0x180001943  mov     rax, cs:?g_pPropertyMappingTable@@3PEAVPROPERTY_MAPPING_TABLE@@EA; PROPERTY_MAPPING_TABLE * g_pPropertyMappingTable
0x18000194a  inc     esi
0x18000194c  cmp     esi, [rax+8]
0x18000194f  jb      loc_180001880
0x180001955  mov     eax, ebp
0x180001957  mov     rbp, [rsp+48h+arg_10]
0x18000195c  mov     rbx, [rsp+48h+arg_8]
0x180001961  mov     rdi, [rsp+48h+var_10]
0x180001966  mov     r12, [rsp+48h+var_18]
0x18000196b  mov     r14, [rsp+48h+var_20]
0x180001970  mov     rsi, [rsp+48h+var_8]
0x180001975  mov     r15, [rsp+48h+var_28]
0x18000197a  add     rsp, 48h
0x18000197e  retn
0x18000197f  mov     rbx, [rsp+48h+arg_0]
0x180001984  jmp     short loc_180001916
0x180001986  mov     eax, r15d
0x180001989  jmp     short loc_180001970
0x180003a6c  mov     eax, 80070032h
0x180003a71  jmp     loc_18000197A
0x180003a76  lea     rcx, [rbx+10h]
0x180003a7a  xor     edx, edx
0x180003a7c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003a82  mov     ebp, eax
0x180003a84  test    eax, eax
0x180003a86  js      short loc_180003ACF
0x180003a88  jmp     loc_1800018FD
0x180003a8d  test    rbx, rbx
0x180003a90  jz      loc_180001943
0x180003a96  mov     rax, [rbx]
0x180003a99  mov     edx, 1
0x180003a9e  mov     rcx, rbx
0x180003aa1  mov     rax, [rax]
0x180003aa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003aa9  nop
0x180003aaa  jmp     loc_180001943
0x180003aaf  jle     short loc_180003ACF
0x180003ab1  movzx   ebp, ax
0x180003ab4  or      ebp, 80070000h
0x180003aba  jmp     short loc_180003ACF
0x180003abc  mov     eax, 80070008h
0x180003ac1  jmp     loc_180001957
0x180003ac6  test    rbx, rbx
0x180003ac9  jz      loc_180001957
0x180003acf  mov     rcx, rbx; this
0x180003ad2  call    ?DereferenceHandleEntry@HANDLE_ENTRY@@QEAAXXZ; HANDLE_ENTRY::DereferenceHandleEntry(void)
0x180003ad7  nop
0x180003ad8  jmp     loc_180001955
```
