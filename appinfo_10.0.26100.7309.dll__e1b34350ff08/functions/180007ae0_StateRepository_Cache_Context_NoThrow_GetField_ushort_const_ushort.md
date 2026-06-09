# StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)

- ea: `0x180007ae0`
- end: `0x180007b26`
- name: `?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z`
- size: `70`
- prototype: `__int64 __fastcall(StateRepository::Cache::Context_NoThrow *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800075b0`
- `0x180008b20`
- `0x18000e410`
- `0x18002c818`
- `0x18002d418`

## callees

- `0x180007ae0`
- `0x180007c78`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180007ae9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x180007ae9`

## string_xrefs

- `0x180007b09`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Context_NoThrow::GetField(
        StateRepository::Cache::Context_NoThrow *this,
        const unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  int Field_String; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Field_String = SRCacheContext_GetField_String(*(_QWORD *)this, a2, a3);
  v4 = Field_String;
  if ( Field_String >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x246,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
    (const char *)(unsigned int)Field_String,
    v6);
  return v4;
}

```

## disassembly

```asm
0x180007ae0  push    rbx; int
0x180007ae2  sub     rsp, 20h
0x180007ae6  mov     rcx, [rcx]
0x180007ae9  call    cs:__imp_SRCacheContext_GetField_String
0x180007af0  nop     dword ptr [rax+rax+00h]
0x180007af5  mov     ebx, eax
0x180007af7  test    eax, eax
0x180007af9  js      short loc_180007B04
0x180007afb  xor     eax, eax
0x180007afd  add     rsp, 20h
0x180007b01  pop     rbx
0x180007b02  retn
0x180007b04  mov     rcx, [rsp+28h]; this
0x180007b09  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007b10  mov     r9d, ebx; char *
0x180007b13  mov     edx, 246h; void *
0x180007b18  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007b1d  mov     eax, ebx
0x180007b1f  add     rsp, 20h
0x180007b23  pop     rbx
0x180007b24  retn
```
