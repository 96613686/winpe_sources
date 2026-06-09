# StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)

- ea: `0x18000e960`
- end: `0x18000e9a6`
- name: `?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z`
- size: `70`
- prototype: `int(StateRepository::Cache::Context_NoThrow *__hidden this, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180005000`
- `0x1800052b0`
- `0x18002d828`
- `0x1800350cc`
- `0x1800352a8`
- `0x180035484`

## callees

- `0x180007c78`
- `0x18000e960`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000e969`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000e969`

## string_xrefs

- `0x18000e989`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

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
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
    (const char *)(unsigned int)v2,
    v5);
  return v3;
}

```

## disassembly

```asm
0x18000e960  push    rbx; int
0x18000e962  sub     rsp, 20h
0x18000e966  mov     rcx, [rcx]
0x18000e969  call    cs:__imp_SRCacheContext_AddToCache
0x18000e970  nop     dword ptr [rax+rax+00h]
0x18000e975  mov     ebx, eax
0x18000e977  test    eax, eax
0x18000e979  js      short loc_18000E984
0x18000e97b  xor     eax, eax
0x18000e97d  add     rsp, 20h
0x18000e981  pop     rbx
0x18000e982  retn
0x18000e984  mov     rcx, [rsp+28h]; this
0x18000e989  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000e990  mov     r9d, ebx; char *
0x18000e993  mov     edx, 1A6h; void *
0x18000e998  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e99d  mov     eax, ebx
0x18000e99f  add     rsp, 20h
0x18000e9a3  pop     rbx
0x18000e9a4  retn
```
