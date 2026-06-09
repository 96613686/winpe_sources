# StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)

- ea: `0x18000b0b0`
- end: `0x18000b0ea`
- name: `?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z`
- size: `58`
- prototype: `int(StateRepository::Cache::Context_NoThrow *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180009938`
- `0x180012448`
- `0x180012638`
- `0x18001284c`
- `0x180014cd8`
- `0x180014de4`
- `0x180016da0`
- `0x180016f78`

## callees

- `0x1800075e4`
- `0x18000b0b0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x18000b0b9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x18000b0b9`

## string_xrefs

- `0x18000b0ca`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Context_NoThrow::GetField(
        StateRepository::Cache::Context_NoThrow *this,
        const unsigned __int16 *a2,
        unsigned int *a3)
{
  int Field_UInt32; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Field_UInt32 = SRCacheContext_GetField_UInt32(*(_QWORD *)this, a2, a3);
  v4 = Field_UInt32;
  if ( Field_UInt32 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x221,
    (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
    (const char *)(unsigned int)Field_UInt32,
    v6);
  return v4;
}

```

## disassembly

```asm
0x18000b0b0  push    rbx; int
0x18000b0b2  sub     rsp, 20h
0x18000b0b6  mov     rcx, [rcx]
0x18000b0b9  call    cs:__imp_SRCacheContext_GetField_UInt32
0x18000b0bf  mov     ebx, eax
0x18000b0c1  test    eax, eax
0x18000b0c3  jns     short loc_18000B0E2
0x18000b0c5  mov     rcx, [rsp+28h]; this
0x18000b0ca  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x18000b0d1  mov     r9d, eax; char *
0x18000b0d4  mov     edx, 221h; void *
0x18000b0d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b0de  mov     eax, ebx
0x18000b0e0  jmp     short loc_18000B0E4
0x18000b0e2  xor     eax, eax
0x18000b0e4  add     rsp, 20h
0x18000b0e8  pop     rbx
0x18000b0e9  retn
```
