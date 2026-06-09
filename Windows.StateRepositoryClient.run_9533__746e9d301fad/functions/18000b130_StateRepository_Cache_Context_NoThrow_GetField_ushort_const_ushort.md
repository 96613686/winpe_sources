# StateRepository::Cache::Context_NoThrow::GetField(ushort const *,ushort * *)

- ea: `0x18000b130`
- end: `0x18000b16a`
- name: `?GetField@Context_NoThrow@Cache@StateRepository@@QEAAJPEBGPEAPEAG@Z`
- size: `58`
- prototype: `int(StateRepository::Cache::Context_NoThrow *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180009938`
- `0x180009fa4`
- `0x180012448`
- `0x180012638`
- `0x18001284c`
- `0x18001297c`
- `0x180016da0`
- `0x180016f78`

## callees

- `0x1800075e4`
- `0x18000b130`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000b139`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_GetField_String` at `0x18000b139`

## string_xrefs

- `0x18000b14a`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`

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
    (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
    (const char *)(unsigned int)Field_String,
    v6);
  return v4;
}

```

## disassembly

```asm
0x18000b130  push    rbx; int
0x18000b132  sub     rsp, 20h
0x18000b136  mov     rcx, [rcx]
0x18000b139  call    cs:__imp_SRCacheContext_GetField_String
0x18000b13f  mov     ebx, eax
0x18000b141  test    eax, eax
0x18000b143  jns     short loc_18000B162
0x18000b145  mov     rcx, [rsp+28h]; this
0x18000b14a  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x18000b151  mov     r9d, eax; char *
0x18000b154  mov     edx, 246h; void *
0x18000b159  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b15e  mov     eax, ebx
0x18000b160  jmp     short loc_18000B164
0x18000b162  xor     eax, eax
0x18000b164  add     rsp, 20h
0x18000b168  pop     rbx
0x18000b169  retn
```
