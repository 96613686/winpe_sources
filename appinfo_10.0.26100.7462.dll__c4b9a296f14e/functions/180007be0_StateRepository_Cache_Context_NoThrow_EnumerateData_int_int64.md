# StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)

- ea: `0x180007be0`
- end: `0x180007c21`
- name: `?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z`
- size: `65`
- prototype: `__int64 __fastcall(StateRepository::Cache::Context_NoThrow *__hidden this, int, __int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180004eb0`
- `0x18002d40c`
- `0x18002d8f8`

## callees

- `0x180007be0`
- `0x180007c78`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x180007be9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x180007be9`

## string_xrefs

- `0x180007c00`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Context.hpp`

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
0x180007be0  push    rbx; int
0x180007be2  sub     rsp, 20h
0x180007be6  mov     rcx, [rcx]
0x180007be9  call    cs:__imp_SRCacheContext_EnumerateData
0x180007bf0  nop     dword ptr [rax+rax+00h]
0x180007bf5  mov     ebx, eax
0x180007bf7  test    eax, eax
0x180007bf9  jns     short loc_180007C1D
0x180007bfb  mov     rcx, [rsp+28h]; this
0x180007c00  lea     r8, aOnecorePrivate_9; "onecore\\private\\base\\inc\\appmodel\\"...
0x180007c07  mov     r9d, eax; char *
0x180007c0a  mov     edx, 2A6h; void *
0x180007c0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007c14  mov     eax, ebx
0x180007c16  add     rsp, 20h
0x180007c1a  pop     rbx
0x180007c1b  retn
0x180007c1d  xor     eax, eax
0x180007c1f  jmp     short loc_180007C16
```
