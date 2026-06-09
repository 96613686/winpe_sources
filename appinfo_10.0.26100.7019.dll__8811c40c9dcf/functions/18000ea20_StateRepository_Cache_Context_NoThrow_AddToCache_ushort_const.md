# StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)

- ea: `0x18000ea20`
- end: `0x18000ea66`
- name: `?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z`
- size: `70`
- prototype: `int(StateRepository::Cache::Context_NoThrow *__hidden this, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180005000`
- `0x1800052b0`
- `0x18002ee48`
- `0x18003501c`
- `0x1800351f8`
- `0x1800353d4`

## callees

- `0x180007c78`
- `0x18000ea20`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000ea29`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000ea29`

## string_xrefs

- `0x18000ea49`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

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
0x18000ea20  push    rbx; int
0x18000ea22  sub     rsp, 20h
0x18000ea26  mov     rcx, [rcx]
0x18000ea29  call    cs:__imp_SRCacheContext_AddToCache
0x18000ea30  nop     dword ptr [rax+rax+00h]
0x18000ea35  mov     ebx, eax
0x18000ea37  test    eax, eax
0x18000ea39  js      short loc_18000EA44
0x18000ea3b  xor     eax, eax
0x18000ea3d  add     rsp, 20h
0x18000ea41  pop     rbx
0x18000ea42  retn
0x18000ea44  mov     rcx, [rsp+28h]; this
0x18000ea49  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000ea50  mov     r9d, ebx; char *
0x18000ea53  mov     edx, 1A6h; void *
0x18000ea58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ea5d  mov     eax, ebx
0x18000ea5f  add     rsp, 20h
0x18000ea63  pop     rbx
0x18000ea64  retn
```
