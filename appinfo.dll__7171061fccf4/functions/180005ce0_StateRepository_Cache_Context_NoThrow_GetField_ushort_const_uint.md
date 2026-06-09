# StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)

- ea: `0x180005ce0`
- end: `0x180005d1a`
- name: `?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z`
- size: `58`
- prototype: `__int64 __fastcall(StateRepository::Cache::Context_NoThrow *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800053d0`
- `0x18001b3a4`

## callees

- `0x180005ce0`
- `0x18000720c`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180005ce9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180005ce9`

## string_xrefs

- `0x180005cfa`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

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
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
    (const char *)(unsigned int)Field_UInt32,
    v6);
  return v4;
}

```

## disassembly

```asm
0x180005ce0  push    rbx; int
0x180005ce2  sub     rsp, 20h
0x180005ce6  mov     rcx, [rcx]
0x180005ce9  call    cs:__imp_SRCacheContext_GetField_UInt32
0x180005cef  mov     ebx, eax
0x180005cf1  test    eax, eax
0x180005cf3  jns     short loc_180005D16
0x180005cf5  mov     rcx, [rsp+28h]; this
0x180005cfa  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180005d01  mov     r9d, eax; char *
0x180005d04  mov     edx, 221h; void *
0x180005d09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005d0e  mov     eax, ebx
0x180005d10  add     rsp, 20h
0x180005d14  pop     rbx
0x180005d15  retn
0x180005d16  xor     eax, eax
0x180005d18  jmp     short loc_180005D10
```
