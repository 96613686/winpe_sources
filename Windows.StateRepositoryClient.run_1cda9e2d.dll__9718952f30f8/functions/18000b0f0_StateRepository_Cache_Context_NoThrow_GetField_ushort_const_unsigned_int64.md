# StateRepository::Cache::Context_NoThrow::GetField(ushort const *,unsigned __int64 &)

- ea: `0x18000b0f0`
- end: `0x18000b12a`
- name: `?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEA_K@Z`
- size: `58`
- prototype: `int(StateRepository::Cache::Context_NoThrow *__hidden this, const unsigned __int16 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009938`
- `0x1800128e8`

## callees

- `0x1800075e4`
- `0x18000b0f0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt64` at `0x18000b0f9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt64` at `0x18000b0f9`

## string_xrefs

- `0x18000b10a`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Context_NoThrow::GetField(
        StateRepository::Cache::Context_NoThrow *this,
        const unsigned __int16 *a2,
        unsigned __int64 *a3)
{
  int Field_UInt64; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Field_UInt64 = SRCacheContext_GetField_UInt64(*(_QWORD *)this, a2, a3);
  v4 = Field_UInt64;
  if ( Field_UInt64 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x230,
    (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
    (const char *)(unsigned int)Field_UInt64,
    v6);
  return v4;
}

```

## disassembly

```asm
0x18000b0f0  push    rbx; int
0x18000b0f2  sub     rsp, 20h
0x18000b0f6  mov     rcx, [rcx]
0x18000b0f9  call    cs:__imp_SRCacheContext_GetField_UInt64
0x18000b0ff  mov     ebx, eax
0x18000b101  test    eax, eax
0x18000b103  jns     short loc_18000B122
0x18000b105  mov     rcx, [rsp+28h]; this
0x18000b10a  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x18000b111  mov     r9d, eax; char *
0x18000b114  mov     edx, 230h; void *
0x18000b119  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b11e  mov     eax, ebx
0x18000b120  jmp     short loc_18000B124
0x18000b122  xor     eax, eax
0x18000b124  add     rsp, 20h
0x18000b128  pop     rbx
0x18000b129  retn
```
