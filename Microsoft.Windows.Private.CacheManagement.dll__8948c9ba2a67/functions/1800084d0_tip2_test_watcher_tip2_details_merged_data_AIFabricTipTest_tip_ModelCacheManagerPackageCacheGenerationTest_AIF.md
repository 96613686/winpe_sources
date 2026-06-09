# tip2::test_watcher<tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>>::NotifyFailure(wil::FailureInfo const &)

- ea: `0x1800084d0`
- end: `0x18000858b`
- name: `?NotifyFailure@?$test_watcher@V?$merged_data@U_tip_ModelCacheManagerPackageCacheGenerationTest@AIFabricTipTest@@U12@@details@tip2@@@tip2@@EEAA_NAEBUFailureInfo@wil@@@Z`
- size: `187`
- prototype: `char __fastcall(__int64, const struct wil::FailureInfo *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800084d0`
- `0x18000a770`
- `0x18000e0e0`
- `0x18000fc60`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180008555`
- `KERNEL32!HeapFree` at `0x180008555`
- `KERNEL32!GetProcessHeap` at `0x180008547`
- `KERNEL32!GetProcessHeap` at `0x180008547`
- `KERNEL32!EnterCriticalSection` at `0x1800084eb`
- `KERNEL32!EnterCriticalSection` at `0x1800084eb`

## pseudocode

```c
char __fastcall tip2::test_watcher<tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>>::NotifyFailure(
        __int64 a1,
        const struct wil::FailureInfo *a2)
{
  __int64 v2; // rbx
  char v4; // al
  void *v5; // rdi
  char v6; // si
  HANDLE ProcessHeap; // rax
  _BYTE v9[152]; // [rsp+20h] [rbp-B8h] BYREF
  LPVOID lpMem[4]; // [rsp+B8h] [rbp-20h]

  v2 = *(_QWORD *)(a1 + 48);
  EnterCriticalSection((LPCRITICAL_SECTION)(v2 + 200));
  if ( (*(_DWORD *)(v2 + 72) & 0x100) == 0 )
  {
    *(_OWORD *)lpMem = 0;
    wil::StoredFailureInfo::SetFailureInfo((wil::StoredFailureInfo *)v9, a2);
    v4 = tip2::vector_nothrow<wil::StoredFailureInfo>::push_back(v2 + 80, v9);
    v5 = lpMem[0];
    v6 = v4;
    if ( lpMem[0] && _InterlockedExchangeAdd((volatile signed __int32 *)lpMem[0], 0xFFFFFFFF) == 1 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v5);
    }
    if ( !v6 )
      *(_DWORD *)(v2 + 72) |= 0x100000u;
  }
  tip2::details::shared_data<0,0,0>::end_update(v2 + 8);
  return 0;
}

```

## disassembly

```asm
0x1800084d0  mov     [rsp+arg_8], rbx
0x1800084d5  push    rdi
0x1800084d6  sub     rsp, 0D0h
0x1800084dd  mov     rbx, [rcx+30h]
0x1800084e1  mov     rdi, rdx
0x1800084e4  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800084eb  call    cs:__imp_EnterCriticalSection
0x1800084f1  test    dword ptr [rbx+48h], 100h
0x1800084f8  jnz     short loc_18000856F
0x1800084fa  xorps   xmm0, xmm0
0x1800084fd  mov     [rsp+0D8h+arg_0], rsi
0x180008505  mov     rdx, rdi; struct wil::FailureInfo *
0x180008508  lea     rcx, [rsp+0D8h+var_B8]; this
0x18000850d  movdqu  xmmword ptr [rsp+0D8h+lpMem], xmm0
0x180008516  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x18000851b  lea     rcx, [rbx+50h]
0x18000851f  lea     rdx, [rsp+0D8h+var_B8]
0x180008524  call    ?push_back@?$vector_nothrow@VStoredFailureInfo@wil@@@tip2@@QEAA_N$$QEAVStoredFailureInfo@wil@@@Z; tip2::vector_nothrow<wil::StoredFailureInfo>::push_back(wil::StoredFailureInfo &&)
0x180008529  mov     rdi, [rsp+0D8h+lpMem]
0x180008531  movzx   esi, al
0x180008534  test    rdi, rdi
0x180008537  jz      short loc_18000855B
0x180008539  mov     ecx, 0FFFFFFFFh
0x18000853e  lock xadd [rdi], ecx
0x180008542  cmp     ecx, 1
0x180008545  jnz     short loc_18000855B
0x180008547  call    cs:__imp_GetProcessHeap
0x18000854d  mov     r8, rdi; lpMem
0x180008550  xor     edx, edx; dwFlags
0x180008552  mov     rcx, rax; hHeap
0x180008555  call    cs:__imp_HeapFree
0x18000855b  test    sil, sil
0x18000855e  mov     rsi, [rsp+0D8h+arg_0]
0x180008566  jnz     short loc_18000856F
0x180008568  or      dword ptr [rbx+48h], 100000h
0x18000856f  lea     rcx, [rbx+8]
0x180008573  call    ?end_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXXZ; tip2::details::shared_data<0,0,0>::end_update(void)
0x180008578  mov     rbx, [rsp+0D8h+arg_8]
0x180008580  xor     al, al
0x180008582  add     rsp, 0D0h
0x180008589  pop     rdi
0x18000858a  retn
```
