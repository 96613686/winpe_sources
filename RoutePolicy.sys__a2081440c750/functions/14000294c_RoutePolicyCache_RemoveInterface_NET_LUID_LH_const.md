# RoutePolicyCache::RemoveInterface(_NET_LUID_LH const &)

- ea: `0x14000294c`
- end: `0x1400029eb`
- name: `?RemoveInterface@RoutePolicyCache@@YAJAEBT_NET_LUID_LH@@@Z`
- size: `159`
- prototype: `__int64 __fastcall(RoutePolicyCache *__hidden this, const union _NET_LUID_LH *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005874`
- `0x14000607c`

## callees

- `0x1400023c0`
- `0x14000294c`
- `0x140007d28`
- `0x140007d7c`
- `0x14000935c`

## pseudocode

```c
__int64 __fastcall RoutePolicyCache::RemoveInterface(RoutePolicyCache *this, const union _NET_LUID_LH *a2)
{
  __int64 *v3; // rcx
  int v4; // edi
  __int64 v5; // rbx
  __int64 **v6; // rax
  _QWORD v8[7]; // [rsp+20h] [rbp-38h] BYREF

  AcquireSpinLock(v8, &g_cacheLock);
  v3 = (__int64 *)g_cacheListHead;
  v4 = -1073741275;
  if ( g_cacheListHead == &g_cacheListHead )
    goto LABEL_8;
  do
  {
    v5 = *v3;
    if ( v3[8] == *(_QWORD *)this )
    {
      if ( *(__int64 **)(v5 + 8) != v3 || (v6 = (__int64 **)v3[1], *v6 != v3) )
        __fastfail(3u);
      *v6 = (__int64 *)v5;
      *(_QWORD *)(v5 + 8) = v6;
      FreeCacheEntry(v3);
      v4 = 0;
    }
    v3 = (__int64 *)v5;
  }
  while ( (PVOID *)v5 != &g_cacheListHead );
  if ( v4 < 0 )
LABEL_8:
    MicrosoftTelemetryAssertTriggeredNoArgsKM();
  if ( v8[0] )
    SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)v8);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000294c  push    rbx
0x14000294e  push    rbp
0x14000294f  push    rsi
0x140002950  push    rdi
0x140002951  sub     rsp, 38h
0x140002955  mov     rsi, rcx
0x140002958  lea     rdx, ?g_cacheLock@@3_KA; unsigned __int64 g_cacheLock
0x14000295f  lea     rcx, [rsp+58h+var_38]
0x140002964  call    ?AcquireSpinLock@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUSpinLockAndSavedIrql@@@Z$1?Release@1@SAX0@ZU?$integral_constant@_K$01@wistd@@U1@PEA_K$0A@$$T@details@wil@@@details@wil@@@wil@@PEA_K@Z; AcquireSpinLock(unsigned __int64 *)
0x140002969  mov     rcx, cs:?g_cacheListHead@@3U_LIST_ENTRY@@A; P
0x140002970  lea     rbp, ?g_cacheListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_cacheListHead
0x140002977  mov     edi, 0C0000225h
0x14000297c  cmp     rcx, rbp
0x14000297f  jz      short loc_1400029B6
0x140002981  mov     rax, [rsi]
0x140002984  mov     rbx, [rcx]
0x140002987  cmp     [rcx+40h], rax
0x14000298b  jnz     short loc_1400029AA
0x14000298d  cmp     [rbx+8], rcx
0x140002991  jnz     short loc_1400029E4
0x140002993  mov     rax, [rcx+8]
0x140002997  cmp     [rax], rcx
0x14000299a  jnz     short loc_1400029E4
0x14000299c  mov     [rax], rbx
0x14000299f  mov     [rbx+8], rax
0x1400029a3  call    FreeCacheEntry
0x1400029a8  xor     edi, edi
0x1400029aa  mov     rcx, rbx
0x1400029ad  cmp     rbx, rbp
0x1400029b0  jnz     short loc_140002981
0x1400029b2  test    edi, edi
0x1400029b4  jns     short loc_1400029BB
0x1400029b6  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400029bb  cmp     [rsp+58h+var_38], 0
0x1400029c1  jz      short loc_1400029D8
0x1400029c3  movaps  xmm0, xmmword ptr [rsp+58h+var_38]
0x1400029c8  lea     rcx, [rsp+58h+var_38]; struct SpinLockAndSavedIrql *
0x1400029cd  movdqa  xmmword ptr [rsp+58h+var_38], xmm0
0x1400029d3  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x1400029d8  mov     eax, edi
0x1400029da  add     rsp, 38h
0x1400029de  pop     rdi
0x1400029df  pop     rsi
0x1400029e0  pop     rbp
0x1400029e1  pop     rbx
0x1400029e2  retn
0x1400029e4  mov     ecx, 3
0x1400029e9  int     29h; Win8: RtlFailFast(ecx)
```
