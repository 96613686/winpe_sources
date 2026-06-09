# Cn::Engine::Heap::ProcessAllocate(Cn::Engine::AllocType,unsigned __int64)

- ea: `0x18003773c`
- end: `0x18003779d`
- name: `?ProcessAllocate@Heap@Engine@Cn@@SAPEAXUAllocType@23@_K@Z`
- size: `97`
- prototype: `static void *__high(struct Cn::Engine::AllocType, unsigned __int64)`
- caller_count: `24`
- callee_count: `4`
- tags: ``

## callers

- `0x180025ae0`
- `0x180025bf0`
- `0x180036048`
- `0x180037258`
- `0x1800372fc`
- `0x180037500`
- `0x18003802c`
- `0x180039294`
- `0x180039594`
- `0x180039f68`
- `0x18003a450`
- `0x180049d98`
- `0x18004baf0`
- `0x18005c084`
- `0x18005d9a0`
- `0x1800639c4`
- `0x1800876d0`
- `0x180091fbc`
- `0x18009cf54`
- `0x1800b0a28`
- `0x1800b0cf0`
- `0x1800b79d4`
- `0x1800b7a84`
- `0x1800c2078`

## callees

- `0x18000b0bc`
- `0x18003773c`
- `0x1800a2108`
- `0x1800c7d64`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180037769`
- `api-ms-win-crt-private-l1-1-0!_o_calloc` at `0x180037769`

## string_xrefs

- `0x180037782`: `onecore\internal\sdk\inc\wil\opensource/wil/safecast.h`

## pseudocode

```c
void *__fastcall Cn::Engine::Heap::ProcessAllocate(__int64 a1, unsigned __int64 a2)
{
  int v2; // eax
  unsigned __int64 v3; // rbx
  void *result; // rax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  size_t Count; // [rsp+30h] [rbp+8h] BYREF

  LODWORD(Count) = 0;
  v2 = ULongLongToUInt(a2, (unsigned int *)&Count);
  if ( v2 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x10F,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/safecast.h",
      (const char *)(unsigned int)v2,
      v5);
  v3 = (unsigned int)Count;
  result = calloc((unsigned int)Count, 1u);
  if ( !result )
    CFlat::Abandonment::OutOfMemory(v3);
  return result;
}

```

## disassembly

```asm
0x18003773c  mov     dword ptr [rsp+Count], ecx
0x180037740  push    rbx; int
0x180037741  sub     rsp, 20h
0x180037745  mov     rcx, rdx; unsigned __int64
0x180037748  mov     dword ptr [rsp+28h+Count], 0
0x180037750  lea     rdx, [rsp+28h+Count]; unsigned int *
0x180037755  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18003775a  test    eax, eax
0x18003775c  js      short loc_18003777A
0x18003775e  mov     ebx, dword ptr [rsp+28h+Count]
0x180037762  mov     edx, 1; Size
0x180037767  mov     ecx, ebx; Count
0x180037769  call    cs:__imp_calloc
0x18003776f  test    rax, rax
0x180037772  jz      short loc_180037794
0x180037774  add     rsp, 20h
0x180037778  pop     rbx
0x180037779  retn
0x18003777a  mov     rcx, [rsp+28h]; this
0x18003777f  mov     r9d, eax; char *
0x180037782  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180037789  mov     edx, 10Fh; void *
0x18003778e  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180037794  mov     rcx, rbx; unsigned __int64
0x180037797  call    ?OutOfMemory@Abandonment@CFlat@@SAX_K@Z; CFlat::Abandonment::OutOfMemory(unsigned __int64)
```
