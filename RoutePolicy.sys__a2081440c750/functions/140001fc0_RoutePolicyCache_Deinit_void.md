# RoutePolicyCache::Deinit(void)

- ea: `0x140001fc0`
- end: `0x140002098`
- name: `?Deinit@RoutePolicyCache@@YAXXZ`
- size: `216`
- prototype: `void __fastcall(RoutePolicyCache *__hidden this)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x14000607c`
- `0x140008060`
- `0x14001903c`

## callees

- `0x140001fc0`
- `0x1400023c0`
- `0x14000242c`
- `0x140002498`
- `0x140007d28`
- `0x140007d7c`

## pseudocode

```c
void __fastcall RoutePolicyCache::Deinit(RoutePolicyCache *this)
{
  PVOID v1; // rcx
  _QWORD *v2; // rax
  PVOID *v3; // rdx
  PVOID v4; // rcx
  _QWORD *v5; // rax
  PVOID *v6; // rdx
  PVOID v7; // rcx
  _QWORD *v8; // rax
  PVOID *v9; // rdx
  __int128 v10; // [rsp+20h] [rbp-18h] BYREF

  AcquireSpinLock(&v10, &g_cacheLock);
  while ( 1 )
  {
    v1 = g_cacheListHead;
    if ( g_cacheListHead == &g_cacheListHead )
      break;
    v2 = *(_QWORD **)g_cacheListHead;
    if ( *(PVOID *)(*(_QWORD *)g_cacheListHead + 8LL) != g_cacheListHead
      || (v3 = (PVOID *)*((_QWORD *)g_cacheListHead + 1), *v3 != g_cacheListHead) )
    {
LABEL_14:
      __fastfail(3u);
    }
    *v3 = v2;
    v2[1] = v3;
    FreeCacheEntry(v1);
  }
  while ( 1 )
  {
    v4 = g_rulesListHead;
    if ( g_rulesListHead == &g_rulesListHead )
      break;
    v5 = *(_QWORD **)g_rulesListHead;
    if ( *(PVOID *)(*(_QWORD *)g_rulesListHead + 8LL) != g_rulesListHead )
      goto LABEL_14;
    v6 = (PVOID *)*((_QWORD *)g_rulesListHead + 1);
    if ( *v6 != g_rulesListHead )
      goto LABEL_14;
    *v6 = v5;
    v5[1] = v6;
    FreeRulesEntry(v4);
  }
  while ( 1 )
  {
    v7 = g_packageListHead;
    if ( g_packageListHead == &g_packageListHead )
      break;
    v8 = *(_QWORD **)g_packageListHead;
    if ( *(PVOID *)(*(_QWORD *)g_packageListHead + 8LL) != g_packageListHead )
      goto LABEL_14;
    v9 = (PVOID *)*((_QWORD *)g_packageListHead + 1);
    if ( *v9 != g_packageListHead )
      goto LABEL_14;
    *v9 = v8;
    v8[1] = v9;
    FreePackageEntry(v7);
  }
  if ( (_QWORD)v10 )
    SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v10);
}

```

## disassembly

```asm
0x140001fc0  sub     rsp, 38h
0x140001fc4  lea     rdx, ?g_cacheLock@@3_KA; unsigned __int64 g_cacheLock
0x140001fcb  lea     rcx, [rsp+38h+var_18]
0x140001fd0  call    ?AcquireSpinLock@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUSpinLockAndSavedIrql@@@Z$1?Release@1@SAX0@ZU?$integral_constant@_K$01@wistd@@U1@PEA_K$0A@$$T@details@wil@@@details@wil@@@wil@@PEA_K@Z; AcquireSpinLock(unsigned __int64 *)
0x140001fd5  mov     rcx, cs:?g_cacheListHead@@3U_LIST_ENTRY@@A; P
0x140001fdc  lea     rax, ?g_cacheListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_cacheListHead
0x140001fe3  cmp     rcx, rax
0x140001fe6  jz      short loc_140002008
0x140001fe8  mov     rax, [rcx]
0x140001feb  cmp     [rax+8], rcx
0x140001fef  jnz     short loc_14000206E
0x140001ff1  mov     rdx, [rcx+8]
0x140001ff5  cmp     [rdx], rcx
0x140001ff8  jnz     short loc_14000206E
0x140001ffa  mov     [rdx], rax
0x140001ffd  mov     [rax+8], rdx
0x140002001  call    FreeCacheEntry
0x140002006  jmp     short loc_140001FD5
0x140002008  mov     rcx, cs:?g_rulesListHead@@3U_LIST_ENTRY@@A; P
0x14000200f  lea     rax, ?g_rulesListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_rulesListHead
0x140002016  cmp     rcx, rax
0x140002019  jz      short loc_14000203B
0x14000201b  mov     rax, [rcx]
0x14000201e  cmp     [rax+8], rcx
0x140002022  jnz     short loc_14000206E
0x140002024  mov     rdx, [rcx+8]
0x140002028  cmp     [rdx], rcx
0x14000202b  jnz     short loc_14000206E
0x14000202d  mov     [rdx], rax
0x140002030  mov     [rax+8], rdx
0x140002034  call    FreeRulesEntry
0x140002039  jmp     short loc_140002008
0x14000203b  mov     rcx, cs:?g_packageListHead@@3U_LIST_ENTRY@@A; P
0x140002042  lea     rax, ?g_packageListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_packageListHead
0x140002049  cmp     rcx, rax
0x14000204c  jz      short loc_140002075
0x14000204e  mov     rax, [rcx]
0x140002051  cmp     [rax+8], rcx
0x140002055  jnz     short loc_14000206E
0x140002057  mov     rdx, [rcx+8]
0x14000205b  cmp     [rdx], rcx
0x14000205e  jnz     short loc_14000206E
0x140002060  mov     [rdx], rax
0x140002063  mov     [rax+8], rdx
0x140002067  call    FreePackageEntry
0x14000206c  jmp     short loc_14000203B
0x14000206e  mov     ecx, 3
0x140002073  int     29h; Win8: RtlFailFast(ecx)
0x140002075  cmp     qword ptr [rsp+38h+var_18], 0
0x14000207b  jz      short loc_140002092
0x14000207d  movaps  xmm0, [rsp+38h+var_18]
0x140002082  lea     rcx, [rsp+38h+var_18]; struct SpinLockAndSavedIrql *
0x140002087  movdqa  [rsp+38h+var_18], xmm0
0x14000208d  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x140002092  add     rsp, 38h
0x140002096  retn
```
