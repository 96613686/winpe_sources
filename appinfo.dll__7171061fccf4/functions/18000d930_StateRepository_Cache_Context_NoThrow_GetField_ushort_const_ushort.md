# StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)

- ea: `0x18000d930`
- end: `0x18000d96e`
- name: `?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z`
- size: `62`
- prototype: `int(StateRepository::Cache::Context_NoThrow *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800053d0`
- `0x180008600`
- `0x1800197fc`
- `0x180031ba0`

## callees

- `0x18000720c`
- `0x18000d930`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000d939`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000d939`

## string_xrefs

- `0x18000d952`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

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
0x18000d930  push    rbx; int
0x18000d932  sub     rsp, 20h
0x18000d936  mov     rcx, [rcx]
0x18000d939  call    cs:__imp_SRCacheContext_GetField_String
0x18000d93f  mov     ebx, eax
0x18000d941  test    eax, eax
0x18000d943  js      short loc_18000D94D
0x18000d945  xor     eax, eax
0x18000d947  add     rsp, 20h
0x18000d94b  pop     rbx
0x18000d94c  retn
0x18000d94d  mov     rcx, [rsp+28h]; this
0x18000d952  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000d959  mov     r9d, ebx; char *
0x18000d95c  mov     edx, 246h; void *
0x18000d961  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d966  mov     eax, ebx
0x18000d968  add     rsp, 20h
0x18000d96c  pop     rbx
0x18000d96d  retn
```
