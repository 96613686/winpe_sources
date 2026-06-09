# wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(void)

- ea: `0x1800094a4`
- end: `0x1800094ce`
- name: `??1?$out_param_t@V?$unique_ptr@USRCacheManager@@Usrcache_manager_deleter@Cache@StateRepository@@@wistd@@@details@wil@@QEAA@XZ`
- size: `42`
- prototype: `__int64 __fastcall(__int64 **)`
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bf90`
- `0x18000db30`
- `0x180014b20`
- `0x180015ec0`
- `0x180015ff0`
- `0x1800161e0`
- `0x180018040`

## callees

- `0x1800094a4`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800094c3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCacheManager_Close` at `0x1800094c3`

## pseudocode

```c
__int64 __fastcall wil::details::out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>::~out_param_t<wistd::unique_ptr<SRCacheManager,StateRepository::Cache::srcache_manager_deleter>>(
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
      return SRCacheManager_Close(v2);
  }
  return result;
}

```

## disassembly

```asm
0x1800094a4  sub     rsp, 28h
0x1800094a8  cmp     byte ptr [rcx+10h], 0
0x1800094ac  jz      short loc_1800094C9
0x1800094ae  mov     rdx, [rcx]
0x1800094b1  mov     rax, [rcx+8]
0x1800094b5  mov     r8, [rdx]
0x1800094b8  mov     [rdx], rax
0x1800094bb  test    r8, r8
0x1800094be  jz      short loc_1800094C9
0x1800094c0  mov     rcx, r8
0x1800094c3  call    cs:__imp_SRCacheManager_Close
0x1800094c9  add     rsp, 28h
0x1800094cd  retn
```
