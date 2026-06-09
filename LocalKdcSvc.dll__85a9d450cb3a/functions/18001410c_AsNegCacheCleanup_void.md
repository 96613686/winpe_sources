# AsNegCacheCleanup(void)

- ea: `0x18001410c`
- end: `0x1800141b1`
- name: `?AsNegCacheCleanup@@YAXXZ`
- size: `165`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005a284`

## callees

- `0x18001410c`
- `0x18002057c`
- `0x18005a090`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x1800141a0`
- `ntdll!RtlDeleteCriticalSection` at `0x1800141a0`

## pseudocode

```c
void AsNegCacheCleanup(void)
{
  void *v0; // rbx
  __int64 v1; // rax

  if ( g_fApNegCacheInitialized )
  {
    g_fApNegCacheInitialized = 0;
    while ( 1 )
    {
      v0 = l_ApNegCacheList;
      if ( l_ApNegCacheList == &l_ApNegCacheList )
        break;
      if ( *((void ***)l_ApNegCacheList + 1) != &l_ApNegCacheList
        || (v1 = *(_QWORD *)l_ApNegCacheList, *(void **)(*(_QWORD *)l_ApNegCacheList + 8LL) != l_ApNegCacheList) )
      {
        __fastfail(3u);
      }
      l_ApNegCacheList = *(void **)l_ApNegCacheList;
      *(_QWORD *)(v1 + 8) = &l_ApNegCacheList;
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 193, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, v0);
      MIDL_user_free(v0);
    }
    RtlDeleteCriticalSection(&l_ApNegCacheCritSect);
  }
}

```

## disassembly

```asm
0x18001410c  mov     [rsp+arg_0], rbx
0x180014111  push    rdi
0x180014112  sub     rsp, 20h
0x180014116  cmp     cs:?g_fApNegCacheInitialized@@3EA, 0; uchar g_fApNegCacheInitialized
0x18001411d  jz      loc_1800141A6
0x180014123  mov     cs:?g_fApNegCacheInitialized@@3EA, 0; uchar g_fApNegCacheInitialized
0x18001412a  lea     rdi, ?l_ApNegCacheList@@3U_LIST_ENTRY@@A; _LIST_ENTRY l_ApNegCacheList
0x180014131  mov     rbx, cs:?l_ApNegCacheList@@3U_LIST_ENTRY@@A; _LIST_ENTRY l_ApNegCacheList
0x180014138  cmp     rbx, rdi
0x18001413b  jz      short loc_180014199
0x18001413d  cmp     [rbx+8], rdi
0x180014141  jnz     short loc_180014192
0x180014143  mov     rax, [rbx]
0x180014146  cmp     [rax+8], rbx
0x18001414a  jnz     short loc_180014192
0x18001414c  mov     cs:?l_ApNegCacheList@@3U_LIST_ENTRY@@A, rax; _LIST_ENTRY l_ApNegCacheList
0x180014153  mov     [rax+8], rdi
0x180014157  mov     rcx, cs:WPP_GLOBAL_Control
0x18001415e  lea     rax, WPP_GLOBAL_Control
0x180014165  cmp     rcx, rax
0x180014168  jz      short loc_180014188
0x18001416a  test    byte ptr [rcx+1Ch], 4
0x18001416e  jz      short loc_180014188
0x180014170  mov     rcx, [rcx+10h]
0x180014174  lea     r8, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids
0x18001417b  mov     edx, 0C1h
0x180014180  mov     r9, rbx
0x180014183  call    WPP_SF_q
0x180014188  mov     rcx, rbx; void *
0x18001418b  call    MIDL_user_free
0x180014190  jmp     short loc_180014131
0x180014192  mov     ecx, 3
0x180014197  int     29h; Win8: RtlFailFast(ecx)
0x180014199  lea     rcx, ?l_ApNegCacheCritSect@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x1800141a0  call    cs:__imp_RtlDeleteCriticalSection
0x1800141a6  mov     rbx, [rsp+28h+arg_0]
0x1800141ab  add     rsp, 20h
0x1800141af  pop     rdi
0x1800141b0  retn
```
