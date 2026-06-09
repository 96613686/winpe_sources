# SEManager::GetDefaultSEReader(void)

- ea: `0x180011248`
- end: `0x1800113ca`
- name: `?GetDefaultSEReader@SEManager@@SA?AV?$shared_ptr@VSEReader@@@std@@XZ`
- size: `386`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800113d0`

## callees

- `0x180011248`
- `0x180018a08`
- `0x18009d010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011314`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180011314`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800112da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011348`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800112da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011348`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800113ac`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800113ac`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001128e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001128e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_QWORD *__fastcall SEManager::GetDefaultSEReader(_QWORD *a1)
{
  _QWORD *v2; // rbx
  void *v3; // rcx
  _QWORD *v4; // rax
  __int64 v5; // r14
  LPVOID v6; // rdi
  __int64 v7; // rax
  void *v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rcx
  volatile signed __int32 *v11; // rbx
  LPVOID pv; // [rsp+78h] [rbp+38h] BYREF

  *a1 = 0;
  a1[1] = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)&SEManager::s_csLock);
  v2 = SEManager::s_SEReaderList;
  if ( (void *)qword_1801331C8 != SEManager::s_SEReaderList )
  {
    if ( qword_1801331C8 - (_QWORD)SEManager::s_SEReaderList != 16 )
    {
      pv = 0;
      if ( (int)NfcUtilsGetDefaultSEDeviceName(&pv) < 0 )
      {
        v3 = pv;
        pv = 0;
        CoTaskMemFree(v3);
        goto LABEL_18;
      }
      v4 = SEManager::s_SEReaderList;
      v2 = SEManager::s_SEReaderList;
      v5 = qword_1801331C8;
      if ( SEManager::s_SEReaderList != (void *)qword_1801331C8 )
      {
        do
        {
          v6 = pv;
          v7 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v2 + 8LL))(*v2);
          if ( !(unsigned int)_o__wcsicmp(v7, v6) )
            break;
          v2 += 2;
        }
        while ( v2 != (_QWORD *)v5 );
        v5 = qword_1801331C8;
        v4 = SEManager::s_SEReaderList;
      }
      if ( v2 == (_QWORD *)v5 )
        v2 = v4;
      v8 = pv;
      pv = 0;
      CoTaskMemFree(v8);
    }
    v9 = v2[1];
    if ( v9 )
      _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
    v10 = v2[1];
    *a1 = *v2;
    v11 = (volatile signed __int32 *)a1[1];
    a1[1] = v10;
    if ( v11 )
    {
      if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
        if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
  }
LABEL_18:
  LeaveCriticalSection((LPCRITICAL_SECTION)&SEManager::s_csLock);
  return a1;
}

```

## disassembly

```asm
0x180011248  mov     [rsp-28h+arg_10], rbx
0x18001124d  mov     [rsp-28h+arg_0], rcx
0x180011252  push    rbp
0x180011253  push    rsi
0x180011254  push    rdi
0x180011255  push    r12
0x180011257  push    r14
0x180011259  mov     rbp, rsp
0x18001125c  sub     rsp, 40h
0x180011260  mov     rsi, rcx
0x180011263  mov     [rbp+var_20], 0
0x18001126a  mov     qword ptr [rcx], 0
0x180011271  mov     qword ptr [rcx+8], 0
0x180011279  mov     [rbp+var_20], 1
0x180011280  lea     r12, ?s_csLock@SEManager@@0VCComAutoCriticalSection@ATL@@A; ATL::CComAutoCriticalSection SEManager::s_csLock
0x180011287  mov     [rbp+var_18], r12
0x18001128b  mov     rcx, r12; lpCriticalSection
0x18001128e  call    cs:__imp_EnterCriticalSection
0x180011294  mov     [rbp+var_10], 1
0x180011298  mov     rax, cs:qword_1801331C8
0x18001129f  mov     rbx, cs:?s_SEReaderList@SEManager@@0V?$vector@V?$shared_ptr@VSEReader@@@std@@V?$allocator@V?$shared_ptr@VSEReader@@@std@@@2@@std@@A; std::vector<std::shared_ptr<SEReader>> SEManager::s_SEReaderList
0x1800112a6  sub     rax, rbx
0x1800112a9  jz      loc_1800113A9
0x1800112af  cmp     rax, 10h
0x1800112b3  jz      loc_18001134E
0x1800112b9  mov     [rbp+pv], 0
0x1800112c1  lea     rcx, [rbp+pv]
0x1800112c5  call    NfcUtilsGetDefaultSEDeviceName
0x1800112ca  test    eax, eax
0x1800112cc  jns     short loc_1800112E5
0x1800112ce  mov     rcx, [rbp+pv]; pv
0x1800112d2  mov     [rbp+pv], 0
0x1800112da  call    cs:__imp_CoTaskMemFree
0x1800112e0  jmp     loc_1800113A9
0x1800112e5  mov     rax, cs:?s_SEReaderList@SEManager@@0V?$vector@V?$shared_ptr@VSEReader@@@std@@V?$allocator@V?$shared_ptr@VSEReader@@@std@@@2@@std@@A; std::vector<std::shared_ptr<SEReader>> SEManager::s_SEReaderList
0x1800112ec  mov     rbx, rax
0x1800112ef  mov     r14, cs:qword_1801331C8
0x1800112f6  cmp     rax, r14
0x1800112f9  jz      short loc_180011335
0x1800112fb  mov     rdi, [rbp+pv]
0x1800112ff  mov     rcx, [rbx]
0x180011302  mov     rax, [rcx]
0x180011305  mov     rax, [rax+8]
0x180011309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001130e  mov     rdx, rdi
0x180011311  mov     rcx, rax
0x180011314  call    cs:__imp__o__wcsicmp
0x18001131a  test    eax, eax
0x18001131c  jz      short loc_180011327
0x18001131e  add     rbx, 10h
0x180011322  cmp     rbx, r14
0x180011325  jnz     short loc_1800112FB
0x180011327  mov     r14, cs:qword_1801331C8
0x18001132e  mov     rax, cs:?s_SEReaderList@SEManager@@0V?$vector@V?$shared_ptr@VSEReader@@@std@@V?$allocator@V?$shared_ptr@VSEReader@@@std@@@2@@std@@A; std::vector<std::shared_ptr<SEReader>> SEManager::s_SEReaderList
0x180011335  cmp     rbx, r14
0x180011338  cmovz   rbx, rax
0x18001133c  mov     rcx, [rbp+pv]; pv
0x180011340  mov     [rbp+pv], 0
0x180011348  call    cs:__imp_CoTaskMemFree
0x18001134e  mov     rax, [rbx+8]
0x180011352  test    rax, rax
0x180011355  jz      short loc_18001135B
0x180011357  lock inc dword ptr [rax+8]
0x18001135b  mov     rcx, [rbx+8]
0x18001135f  mov     rax, [rbx]
0x180011362  mov     [rsi], rax
0x180011365  mov     rbx, [rsi+8]
0x180011369  mov     [rsi+8], rcx
0x18001136d  test    rbx, rbx
0x180011370  jz      short loc_1800113A9
0x180011372  or      edi, 0FFFFFFFFh
0x180011375  mov     eax, edi
0x180011377  lock xadd [rbx+8], eax
0x18001137c  add     eax, edi
0x18001137e  jnz     short loc_1800113A9
0x180011380  mov     rax, [rbx]
0x180011383  mov     rcx, rbx
0x180011386  mov     rax, [rax]
0x180011389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001138e  mov     eax, edi
0x180011390  lock xadd [rbx+0Ch], eax
0x180011395  add     eax, edi
0x180011397  jnz     short loc_1800113A9
0x180011399  mov     rax, [rbx]
0x18001139c  mov     rcx, rbx
0x18001139f  mov     rax, [rax+8]
0x1800113a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113a8  nop
0x1800113a9  mov     rcx, r12; lpCriticalSection
0x1800113ac  call    cs:__imp_LeaveCriticalSection
0x1800113b2  mov     rax, rsi
0x1800113b5  mov     rbx, [rsp+40h+arg_10]
0x1800113bd  add     rsp, 40h
0x1800113c1  pop     r14
0x1800113c3  pop     r12
0x1800113c5  pop     rdi
0x1800113c6  pop     rsi
0x1800113c7  pop     rbp
0x1800113c8  retn
```
