# StateRepository::Cache::Context_NoThrow::EnumerateData(int,__int64 &)

- ea: `0x180009f64`
- end: `0x180009f9e`
- name: `?EnumerateData@Context_NoThrow@Cache@StateRepository@@QEAAJHAEA_J@Z`
- size: `58`
- prototype: `__int64 __fastcall(StateRepository::Cache::Context_NoThrow *this, __int64, __int64 *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a1c4`
- `0x18000a52c`
- `0x18000aa54`
- `0x180012c68`
- `0x180013264`
- `0x180014ef0`
- `0x180015190`
- `0x1800173d4`

## callees

- `0x1800075e4`
- `0x180009f64`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x180009f6d`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_EnumerateData` at `0x180009f6d`

## string_xrefs

- `0x180009f7e`: `onecore\base\appmodel\StateRepository\Cache\inc\SRCache-Context.hpp`

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
    (unsigned int)"onecore\\base\\appmodel\\StateRepository\\Cache\\inc\\SRCache-Context.hpp",
    (const char *)(unsigned int)v3,
    v6);
  return v4;
}

```

## disassembly

```asm
0x180009f64  push    rbx; int
0x180009f66  sub     rsp, 20h
0x180009f6a  mov     rcx, [rcx]
0x180009f6d  call    cs:__imp_SRCacheContext_EnumerateData
0x180009f73  mov     ebx, eax
0x180009f75  test    eax, eax
0x180009f77  jns     short loc_180009F96
0x180009f79  mov     rcx, [rsp+28h]; this
0x180009f7e  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\StateRepositor"...
0x180009f85  mov     r9d, eax; char *
0x180009f88  mov     edx, 2A6h; void *
0x180009f8d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009f92  mov     eax, ebx
0x180009f94  jmp     short loc_180009F98
0x180009f96  xor     eax, eax
0x180009f98  add     rsp, 20h
0x180009f9c  pop     rbx
0x180009f9d  retn
```
