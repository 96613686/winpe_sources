# StateRepository::Cache::Context_NoThrow::GetField(ushort const *,uint &)

- ea: `0x180007c30`
- end: `0x180007c71`
- name: `?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGAEAI@Z`
- size: `65`
- prototype: `__int64 __fastcall(StateRepository::Cache::Context_NoThrow *__hidden this, const unsigned __int16 *, unsigned int *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800075b0`
- `0x180008b20`
- `0x180018e80`

## callees

- `0x180007c30`
- `0x180007c78`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180007c39`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_UInt32` at `0x180007c39`

## string_xrefs

- `0x180007c50`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

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
0x180007c30  push    rbx; int
0x180007c32  sub     rsp, 20h
0x180007c36  mov     rcx, [rcx]
0x180007c39  call    cs:__imp_SRCacheContext_GetField_UInt32
0x180007c40  nop     dword ptr [rax+rax+00h]
0x180007c45  mov     ebx, eax
0x180007c47  test    eax, eax
0x180007c49  jns     short loc_180007C6D
0x180007c4b  mov     rcx, [rsp+28h]; this
0x180007c50  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007c57  mov     r9d, eax; char *
0x180007c5a  mov     edx, 221h; void *
0x180007c5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007c64  mov     eax, ebx
0x180007c66  add     rsp, 20h
0x180007c6a  pop     rbx
0x180007c6b  retn
0x180007c6d  xor     eax, eax
0x180007c6f  jmp     short loc_180007C66
```
