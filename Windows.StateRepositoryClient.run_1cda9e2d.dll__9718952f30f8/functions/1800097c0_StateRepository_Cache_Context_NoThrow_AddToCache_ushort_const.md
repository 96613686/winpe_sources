# StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)

- ea: `0x1800097c0`
- end: `0x1800097fa`
- name: `?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z`
- size: `58`
- prototype: `int(StateRepository::Cache::Context_NoThrow *__hidden this, const unsigned __int16 *)`
- caller_count: `19`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a1c4`
- `0x18000a52c`
- `0x18000aa54`
- `0x18000b454`
- `0x18000b6f0`
- `0x180013264`
- `0x180013a78`
- `0x180013d14`
- `0x180013fb0`
- `0x18001424c`
- `0x1800144e8`
- `0x180014784`
- `0x180014ef0`
- `0x180015190`
- `0x1800158b0`
- `0x180015b4c`
- `0x180017764`
- `0x180017a00`
- `0x180017c9c`

## callees

- `0x1800075e4`
- `0x1800097c0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800097c9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x1800097c9`

## string_xrefs

- `0x1800097da`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Context_NoThrow::AddToCache(
        StateRepository::Cache::Context_NoThrow *this,
        const unsigned __int16 *a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = SRCacheContext_AddToCache(*(_QWORD *)this, a2);
  v3 = v2;
  if ( v2 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1A6,
    (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x1800097c0  push    rbx; int
0x1800097c2  sub     rsp, 20h
0x1800097c6  mov     rcx, [rcx]
0x1800097c9  call    cs:__imp_SRCacheContext_AddToCache
0x1800097cf  mov     ebx, eax
0x1800097d1  test    eax, eax
0x1800097d3  jns     short loc_1800097F2
0x1800097d5  mov     rcx, [rsp+28h]; this
0x1800097da  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x1800097e1  mov     r9d, eax; char *
0x1800097e4  mov     edx, 1A6h; void *
0x1800097e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800097ee  mov     eax, ebx
0x1800097f0  jmp     short loc_1800097F4
0x1800097f2  xor     eax, eax
0x1800097f4  add     rsp, 20h
0x1800097f8  pop     rbx
0x1800097f9  retn
```
