# tip2::tip_test<tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>>::start_and_watch_errors(void)

- ea: `0x1800095d0`
- end: `0x1800097d1`
- name: `?start_and_watch_errors@?$tip_test@V?$merged_data@U_tip_ModelCacheManagerPackageCacheGenerationTest@AIFabricTipTest@@U12@@details@tip2@@@tip2@@QEAA?AV?$test_watcher@V?$merged_data@U_tip_ModelCacheManagerPackageCacheGenerationTest@AIFabricTipTest@@U12@@details@tip2@@@2@XZ`
- size: `513`
- prototype: `__int64 __fastcall(char **, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007410`

## callees

- `0x180002b50`
- `0x1800095d0`
- `0x180009e10`
- `0x18000a930`
- `0x18000eab0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000979c`
- `KERNEL32!GetCurrentThreadId` at `0x18000979c`
- `KERNEL32!InitializeCriticalSection` at `0x1800096ed`
- `KERNEL32!InitializeCriticalSection` at `0x1800096ed`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009614`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009614`

## string_xrefs

- `0x180009640`: `ModelCacheManagerPackageCacheGenerationTest`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall tip2::tip_test<tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>>::start_and_watch_errors(
        char **a1,
        __int64 a2)
{
  char *v4; // rcx
  char *v5; // rax
  wil::details::in1diag3 *v6; // rcx
  char *v7; // rbx
  char *v8; // rcx
  __int64 v9; // rcx
  _QWORD *v10; // rbx
  _QWORD *Local; // rax
  char *v12; // rcx
  __int128 v14; // [rsp+20h] [rbp-58h]
  __int128 v15; // [rsp+30h] [rbp-48h]
  __int128 v16; // [rsp+50h] [rbp-28h] BYREF

  v4 = *a1;
  if ( v4 && (*((_QWORD *)v4 + 30) || (*((_DWORD *)v4 + 18) & 0x100) != 0) )
  {
    *a1 = 0;
    tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>::Release(v4);
  }
  if ( !*a1 )
  {
    v5 = (char *)CoTaskMemAlloc(0x130u);
    v7 = v5;
    if ( !v5 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v6);
    *(_QWORD *)v5 = &tip2::details::test_data_interface::`vftable';
    *(_QWORD *)&v14 = 0xC1000347B7E4LL;
    *((_QWORD *)&v14 + 1) = "ModelCacheManagerPackageCacheGenerationTest";
    LOWORD(v15) = 1;
    *((_QWORD *)&v15 + 1) = 0;
    *((_QWORD *)v5 + 1) = v5;
    *((_QWORD *)v5 + 2) = 0;
    *((_DWORD *)v5 + 18) = 0;
    *((_QWORD *)v5 + 10) = 0;
    *((_QWORD *)v5 + 11) = 0;
    *((_QWORD *)v5 + 12) = 0;
    *((_QWORD *)v5 + 13) = 0;
    *((_QWORD *)v5 + 14) = 0;
    *((_QWORD *)v5 + 15) = 0;
    *((_QWORD *)v5 + 16) = 0;
    *((_QWORD *)v5 + 17) = 0;
    *((_QWORD *)v5 + 18) = 0;
    *(_OWORD *)(v5 + 152) = 0;
    v5[168] = 0;
    *((_WORD *)v5 + 85) = -1;
    *((_QWORD *)v5 + 22) = 0;
    *((_QWORD *)v5 + 23) = 0;
    *((_DWORD *)v5 + 48) = 0;
    *((_QWORD *)v5 + 30) = 0;
    *(_OWORD *)(v5 + 24) = v14;
    *(_OWORD *)(v5 + 40) = v15;
    *(_OWORD *)(v5 + 56) = 0u;
    InitializeCriticalSection((LPCRITICAL_SECTION)v5 + 5);
    *(_OWORD *)(v7 + 264) = 0;
    *((_QWORD *)v7 + 35) = 0;
    *((_QWORD *)v7 + 36) = 7;
    *((_WORD *)v7 + 132) = 0;
    *(_QWORD *)v7 = &tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>::`vftable';
    *((_DWORD *)v7 + 74) = 1;
    *((_QWORD *)v7 + 32) = v7 + 16;
    v8 = *a1;
    *a1 = v7;
    if ( v8 )
      tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>::Release(v8);
  }
  tip2::details::shared_data<0,0,0>::start((__int64)(*a1 + 8), &v16);
  *(_QWORD *)a2 = &tip2::test_watcher<tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>>::`vftable';
  v10 = (_QWORD *)(a2 + 8);
  *(_QWORD *)(a2 + 8) = 0;
  *(_QWORD *)(a2 + 16) = a2;
  *(_QWORD *)(a2 + 24) = 0;
  *(_DWORD *)(a2 + 32) = 0;
  *(_QWORD *)(a2 + 40) = 0;
  if ( wil::details::g_pThreadFailureCallbacks )
  {
    Local = (_QWORD *)wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(v9, 1);
    *v10 = Local;
    if ( Local )
    {
      *(_QWORD *)(a2 + 24) = *Local;
      *Local = v10;
      *(_DWORD *)(a2 + 32) = GetCurrentThreadId();
    }
  }
  v12 = *a1;
  *(_QWORD *)(a2 + 48) = *a1;
  if ( v12 )
    _InterlockedIncrement((volatile signed __int32 *)v12 + 74);
  return a2;
}

```

## disassembly

```asm
0x1800095d0  mov     [rsp+arg_10], rbx
0x1800095d5  push    rbp
0x1800095d6  push    rsi
0x1800095d7  push    rdi
0x1800095d8  sub     rsp, 60h
0x1800095dc  mov     rsi, rdx
0x1800095df  mov     rdi, rcx
0x1800095e2  mov     rcx, [rcx]; pv
0x1800095e5  xor     ebp, ebp
0x1800095e7  test    rcx, rcx
0x1800095ea  jz      short loc_180009606
0x1800095ec  cmp     [rcx+0F0h], rbp
0x1800095f3  jnz     short loc_1800095FE
0x1800095f5  test    dword ptr [rcx+48h], 100h
0x1800095fc  jz      short loc_180009606
0x1800095fe  mov     [rdi], rbp
0x180009601  call    ?Release@?$merged_data@U_tip_ModelCacheManagerPackageCacheGenerationTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>::Release(void)
0x180009606  cmp     [rdi], rbp
0x180009609  jnz     loc_180009745
0x18000960f  mov     ecx, 130h; cb
0x180009614  call    cs:__imp_CoTaskMemAlloc
0x18000961a  mov     rbx, rax
0x18000961d  test    rax, rax
0x180009620  jz      loc_1800097CB
0x180009626  lea     rax, ??_7test_data_interface@details@tip2@@6B@; const tip2::details::test_data_interface::`vftable'
0x18000962d  mov     [rbx], rax
0x180009630  mov     dword ptr [rsp+78h+var_58], 347B7E4h
0x180009638  mov     dword ptr [rsp+78h+var_58+4], 0C100h
0x180009640  lea     rax, aModelcachemana; "ModelCacheManagerPackageCacheGeneration"...
0x180009647  mov     qword ptr [rsp+78h+var_58+8], rax
0x18000964c  mov     word ptr [rsp+78h+var_48], 1
0x180009653  xorps   xmm0, xmm0
0x180009656  movdqu  [rsp+78h+var_48+8], xmm0
0x18000965c  mov     [rsp+78h+var_30], rbp
0x180009661  mov     [rbx+8], rbx
0x180009665  mov     [rbx+10h], rbp
0x180009669  mov     [rbx+48h], ebp
0x18000966c  mov     [rbx+50h], rbp
0x180009670  mov     [rbx+58h], rbp
0x180009674  mov     [rbx+60h], rbp
0x180009678  mov     [rbx+68h], rbp
0x18000967c  mov     [rbx+70h], rbp
0x180009680  mov     [rbx+78h], rbp
0x180009684  mov     [rbx+80h], rbp
0x18000968b  mov     [rbx+88h], rbp
0x180009692  mov     [rbx+90h], rbp
0x180009699  movups  xmmword ptr [rbx+98h], xmm0
0x1800096a0  mov     [rbx+0A8h], bpl
0x1800096a7  mov     word ptr [rbx+0AAh], 0FFFFh
0x1800096b0  mov     [rbx+0B0h], rbp
0x1800096b7  mov     [rbx+0B8h], rbp
0x1800096be  mov     [rbx+0C0h], ebp
0x1800096c4  mov     [rbx+0F0h], rbp
0x1800096cb  movups  xmm0, [rsp+78h+var_58]
0x1800096d0  movups  xmmword ptr [rbx+18h], xmm0
0x1800096d4  movups  xmm1, [rsp+78h+var_48]
0x1800096d9  movups  xmmword ptr [rbx+28h], xmm1
0x1800096dd  movups  xmm0, xmmword ptr [rsp+40h]
0x1800096e2  movups  xmmword ptr [rbx+38h], xmm0
0x1800096e6  lea     rcx, [rbx+0C8h]; lpCriticalSection
0x1800096ed  call    cs:__imp_InitializeCriticalSection
0x1800096f3  xorps   xmm0, xmm0
0x1800096f6  movups  xmmword ptr [rbx+108h], xmm0
0x1800096fd  mov     [rbx+118h], rbp
0x180009704  mov     qword ptr [rbx+120h], 7
0x18000970f  mov     [rbx+108h], bp
0x180009716  lea     rax, ??_7?$merged_data@U_tip_ModelCacheManagerPackageCacheGenerationTest@AIFabricTipTest@@U12@@details@tip2@@6B@; const tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>::`vftable'
0x18000971d  mov     [rbx], rax
0x180009720  mov     dword ptr [rbx+128h], 1
0x18000972a  lea     rax, [rbx+10h]
0x18000972e  mov     [rbx+100h], rax
0x180009735  mov     rcx, [rdi]; pv
0x180009738  mov     [rdi], rbx
0x18000973b  test    rcx, rcx
0x18000973e  jz      short loc_180009745
0x180009740  call    ?Release@?$merged_data@U_tip_ModelCacheManagerPackageCacheGenerationTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ; tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>::Release(void)
0x180009745  mov     rcx, [rdi]
0x180009748  add     rcx, 8
0x18000974c  lea     rdx, [rsp+78h+var_28]
0x180009751  call    ?start@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA?AU_GUID@@XZ; tip2::details::shared_data<0,0,0>::start(void)
0x180009756  lea     rax, ??_7?$test_watcher@V?$merged_data@U_tip_ModelCacheManagerPackageCacheGenerationTest@AIFabricTipTest@@U12@@details@tip2@@@tip2@@6B@; const tip2::test_watcher<tip2::details::merged_data<AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest,AIFabricTipTest::_tip_ModelCacheManagerPackageCacheGenerationTest>>::`vftable'
0x18000975d  mov     [rsi], rax
0x180009760  lea     rbx, [rsi+8]
0x180009764  mov     [rbx], rbp
0x180009767  mov     [rbx+8], rsi
0x18000976b  mov     [rbx+10h], rbp
0x18000976f  mov     [rbx+18h], ebp
0x180009772  mov     [rbx+20h], rbp
0x180009776  cmp     cs:?g_pThreadFailureCallbacks@details@wil@@3PEAV?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@2@EA, 0; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *> * wil::details::g_pThreadFailureCallbacks
0x18000977e  jz      short loc_1800097A5
0x180009780  mov     dl, 1
0x180009782  call    ?GetLocal@?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAAPEAPEAVThreadFailureCallbackHolder@details@3@_N@Z; wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::GetLocal(bool)
0x180009787  mov     rcx, rax
0x18000978a  mov     [rbx], rax
0x18000978d  test    rax, rax
0x180009790  jz      short loc_1800097A5
0x180009792  mov     rax, [rax]
0x180009795  mov     [rbx+10h], rax
0x180009799  mov     [rcx], rbx
0x18000979c  call    cs:__imp_GetCurrentThreadId
0x1800097a2  mov     [rbx+18h], eax
0x1800097a5  mov     rcx, [rdi]
0x1800097a8  mov     [rsi+30h], rcx
0x1800097ac  test    rcx, rcx
0x1800097af  jz      short loc_1800097B8
0x1800097b1  lock inc dword ptr [rcx+128h]
0x1800097b8  mov     rax, rsi
0x1800097bb  mov     rbx, [rsp+78h+arg_10]
0x1800097c3  add     rsp, 60h
0x1800097c7  pop     rdi
0x1800097c8  pop     rsi
0x1800097c9  pop     rbp
0x1800097ca  retn
0x1800097cb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
