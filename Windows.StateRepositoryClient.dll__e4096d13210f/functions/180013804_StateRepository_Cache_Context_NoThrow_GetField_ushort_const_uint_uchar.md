# StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &,uchar * *)

- ea: `0x180013804`
- end: `0x180013845`
- name: `?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAIPEAPEAE@Z`
- size: `65`
- prototype: `__int64 __fastcall(StateRepository::Cache::Context_NoThrow *this, const unsigned __int16 *, unsigned int *, unsigned __int8 **)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180012448`
- `0x180012638`
- `0x180016f78`

## callees

- `0x1800075e4`
- `0x180013804`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_GetField_Binary` at `0x180013814`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_GetField_Binary` at `0x180013814`

## string_xrefs

- `0x180013825`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Context_NoThrow::GetField(
        StateRepository::Cache::Context_NoThrow *this,
        const unsigned __int16 *a2,
        unsigned int *a3,
        unsigned __int8 **a4)
{
  int Field_Binary; // eax
  unsigned int v5; // ebx
  int v7; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Field_Binary = SRCacheContext_GetField_Binary(*(_QWORD *)this, L"_Dictionary", a3, a4);
  v5 = Field_Binary;
  if ( Field_Binary >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x24F,
    (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
    (const char *)(unsigned int)Field_Binary,
    v7);
  return v5;
}

```

## disassembly

```asm
0x180013804  push    rbx; int
0x180013806  sub     rsp, 20h
0x18001380a  mov     rcx, [rcx]
0x18001380d  lea     rdx, aDictionary; "_Dictionary"
0x180013814  call    cs:__imp_SRCacheContext_GetField_Binary
0x18001381a  mov     ebx, eax
0x18001381c  test    eax, eax
0x18001381e  jns     short loc_18001383D
0x180013820  mov     rcx, [rsp+28h]; this
0x180013825  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x18001382c  mov     r9d, eax; char *
0x18001382f  mov     edx, 24Fh; void *
0x180013834  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013839  mov     eax, ebx
0x18001383b  jmp     short loc_18001383F
0x18001383d  xor     eax, eax
0x18001383f  add     rsp, 20h
0x180013843  pop     rbx
0x180013844  retn
```
