# wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(void)

- ea: `0x180009474`
- end: `0x18000949e`
- name: `??1?$out_param_t@V?$unique_ptr@USRCacheContext@@Usrcache_context_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ`
- size: `42`
- prototype: ``
- caller_count: `19`
- callee_count: `1`
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

- `0x180009474`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180009493`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheContext_Close` at `0x180009493`

## pseudocode

```c
__int64 __fastcall wil::details::out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheContext,StateRepository::Cache::srcache_context_deleter>>(
        __int64 **a1)
{
  __int64 result; // rax
  __int64 v2; // r8

  if ( *((_BYTE *)a1 + 16) )
  {
    result = (__int64)a1[1];
    v2 = **a1;
    **a1 = result;
    if ( v2 )
      return SRCacheContext_Close(v2);
  }
  return result;
}

```

## disassembly

```asm
0x180009474  sub     rsp, 28h
0x180009478  cmp     byte ptr [rcx+10h], 0
0x18000947c  jz      short loc_180009499
0x18000947e  mov     rdx, [rcx]
0x180009481  mov     rax, [rcx+8]
0x180009485  mov     r8, [rdx]
0x180009488  mov     [rdx], rax
0x18000948b  test    r8, r8
0x18000948e  jz      short loc_180009499
0x180009490  mov     rcx, r8
0x180009493  call    cs:__imp_SRCacheContext_Close
0x180009499  add     rsp, 28h
0x18000949d  retn
```
