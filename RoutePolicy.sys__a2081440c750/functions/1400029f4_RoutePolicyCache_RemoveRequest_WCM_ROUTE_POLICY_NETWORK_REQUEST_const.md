# RoutePolicyCache::RemoveRequest(_WCM_ROUTE_POLICY_NETWORK_REQUEST const &)

- ea: `0x1400029f4`
- end: `0x140002ab6`
- name: `?RemoveRequest@RoutePolicyCache@@YAJAEBU_WCM_ROUTE_POLICY_NETWORK_REQUEST@@@Z`
- size: `194`
- prototype: `__int64 __fastcall(RoutePolicyCache *__hidden this, const struct _WCM_ROUTE_POLICY_NETWORK_REQUEST *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000607c`
- `0x14000664c`

## callees

- `0x140001580`
- `0x1400023c0`
- `0x1400029f4`
- `0x140007d28`
- `0x140007d7c`
- `0x14000935c`

## pseudocode

```c
__int64 __fastcall RoutePolicyCache::RemoveRequest(
        RoutePolicyCache *this,
        const struct _WCM_ROUTE_POLICY_NETWORK_REQUEST *a2)
{
  PVOID *i; // rbx
  char v4; // al
  PVOID *v5; // rcx
  PVOID **v6; // rax
  __int128 v8; // [rsp+20h] [rbp-18h] BYREF

  AcquireSpinLock(&v8, &g_cacheLock);
  for ( i = (PVOID *)g_cacheListHead; i != &g_cacheListHead; i = (PVOID *)*i )
  {
    v4 = operator__(i + 2, this);
    v5 = (PVOID *)*i;
    if ( v4 )
    {
      if ( v5[1] != i || (v6 = (PVOID **)i[1], *v6 != i) )
        __fastfail(3u);
      *v6 = v5;
      v5[1] = v6;
      FreeCacheEntry(i);
      if ( (_QWORD)v8 )
        SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v8);
      return 0;
    }
  }
  MicrosoftTelemetryAssertTriggeredNoArgsKM();
  if ( (_QWORD)v8 )
    SpinLockAndSavedIrql::Release((const struct SpinLockAndSavedIrql *)&v8);
  return 3221226021LL;
}

```

## disassembly

```asm
0x1400029f4  mov     [rsp+arg_0], rbx
0x1400029f9  push    rdi
0x1400029fa  sub     rsp, 30h
0x1400029fe  mov     rdi, rcx
0x140002a01  lea     rdx, ?g_cacheLock@@3_KA; unsigned __int64 g_cacheLock
0x140002a08  lea     rcx, [rsp+38h+var_18]
0x140002a0d  call    ?AcquireSpinLock@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUSpinLockAndSavedIrql@@@Z$1?Release@1@SAX0@ZU?$integral_constant@_K$01@wistd@@U1@PEA_K$0A@$$T@details@wil@@@details@wil@@@wil@@PEA_K@Z; AcquireSpinLock(unsigned __int64 *)
0x140002a12  mov     rbx, cs:?g_cacheListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_cacheListHead
0x140002a19  lea     rax, ?g_cacheListHead@@3U_LIST_ENTRY@@A; _LIST_ENTRY g_cacheListHead
0x140002a20  cmp     rbx, rax
0x140002a23  jz      short loc_140002A83
0x140002a25  lea     rcx, [rbx+10h]
0x140002a29  mov     rdx, rdi
0x140002a2c  call    operator__
0x140002a31  mov     rcx, [rbx]
0x140002a34  test    al, al
0x140002a36  jnz     short loc_140002A3D
0x140002a38  mov     rbx, rcx
0x140002a3b  jmp     short loc_140002A19
0x140002a3d  cmp     [rcx+8], rbx
0x140002a41  jnz     short loc_140002A7C
0x140002a43  mov     rax, [rbx+8]
0x140002a47  cmp     [rax], rbx
0x140002a4a  jnz     short loc_140002A7C
0x140002a4c  mov     [rax], rcx
0x140002a4f  mov     [rcx+8], rax
0x140002a53  mov     rcx, rbx; P
0x140002a56  call    FreeCacheEntry
0x140002a5b  cmp     qword ptr [rsp+38h+var_18], 0
0x140002a61  jz      short loc_140002A78
0x140002a63  movaps  xmm0, [rsp+38h+var_18]
0x140002a68  lea     rcx, [rsp+38h+var_18]; struct SpinLockAndSavedIrql *
0x140002a6d  movdqa  [rsp+38h+var_18], xmm0
0x140002a73  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x140002a78  xor     eax, eax
0x140002a7a  jmp     short loc_140002AAA
0x140002a7c  mov     ecx, 3
0x140002a81  int     29h; Win8: RtlFailFast(ecx)
0x140002a83  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x140002a88  cmp     qword ptr [rsp+38h+var_18], 0
0x140002a8e  jz      short loc_140002AA5
0x140002a90  movaps  xmm0, [rsp+38h+var_18]
0x140002a95  lea     rcx, [rsp+38h+var_18]; struct SpinLockAndSavedIrql *
0x140002a9a  movdqa  [rsp+38h+var_18], xmm0
0x140002aa0  call    ?Release@SpinLockAndSavedIrql@@SAXAEBU1@@Z; SpinLockAndSavedIrql::Release(SpinLockAndSavedIrql const &)
0x140002aa5  mov     eax, 0C0000225h
0x140002aaa  mov     rbx, [rsp+38h+arg_0]
0x140002aaf  add     rsp, 30h
0x140002ab3  pop     rdi
0x140002ab4  retn
```
