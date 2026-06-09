# StateRepository::Cache::Context_NoThrow::AddToCache(ushort const *)

- ea: `0x18000dee0`
- end: `0x18000df1e`
- name: `?AddToCache@Context_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z`
- size: `62`
- prototype: `__int64 __fastcall(StateRepository::Cache::Context_NoThrow *this, const unsigned __int16 *)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1800047f4`
- `0x180004a70`
- `0x18001d56c`
- `0x18001d7f0`
- `0x18001ddf0`
- `0x18001e0b0`

## callees

- `0x18000720c`
- `0x18000dee0`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000dee9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-4!SRCacheContext_AddToCache` at `0x18000dee9`

## string_xrefs

- `0x18000df02`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

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
0x18000dee0  push    rbx; int
0x18000dee2  sub     rsp, 20h
0x18000dee6  mov     rcx, [rcx]
0x18000dee9  call    cs:__imp_SRCacheContext_AddToCache
0x18000deef  mov     ebx, eax
0x18000def1  test    eax, eax
0x18000def3  js      short loc_18000DEFD
0x18000def5  xor     eax, eax
0x18000def7  add     rsp, 20h
0x18000defb  pop     rbx
0x18000defc  retn
0x18000defd  mov     rcx, [rsp+28h]; this
0x18000df02  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000df09  mov     r9d, ebx; char *
0x18000df0c  mov     edx, 1A6h; void *
0x18000df11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000df16  mov     eax, ebx
0x18000df18  add     rsp, 20h
0x18000df1c  pop     rbx
0x18000df1d  retn
```
