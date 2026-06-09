# StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)

- ea: `0x180007780`
- end: `0x1800077ba`
- name: `?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z`
- size: `58`
- prototype: `__int64 __fastcall(StateRepository::Cache::Context_NoThrow *this, __int64, __int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800046a4`
- `0x18001d7f0`
- `0x180031ad8`

## callees

- `0x18000720c`
- `0x180007780`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x180007789`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x180007789`

## string_xrefs

- `0x18000779a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Context_NoThrow::EnumerateData(
        StateRepository::Cache::Context_NoThrow *this,
        __int64 a2,
        __int64 *a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = SRCacheContext_EnumerateData(*(_QWORD *)this, a2, a3);
  v4 = v3;
  if ( v3 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2A6,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Context.hpp",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x180007780  push    rbx; int
0x180007782  sub     rsp, 20h
0x180007786  mov     rcx, [rcx]
0x180007789  call    cs:__imp_SRCacheContext_EnumerateData
0x18000778f  mov     ebx, eax
0x180007791  test    eax, eax
0x180007793  jns     short loc_1800077B6
0x180007795  mov     rcx, [rsp+28h]; this
0x18000779a  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800077a1  mov     r9d, eax; char *
0x1800077a4  mov     edx, 2A6h; void *
0x1800077a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800077ae  mov     eax, ebx
0x1800077b0  add     rsp, 20h
0x1800077b4  pop     rbx
0x1800077b5  retn
0x1800077b6  xor     eax, eax
0x1800077b8  jmp     short loc_1800077B0
```
