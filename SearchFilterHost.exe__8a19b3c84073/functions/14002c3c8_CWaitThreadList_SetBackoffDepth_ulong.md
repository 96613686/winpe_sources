# CWaitThreadList::SetBackoffDepth(ulong)

- ea: `0x14002c3c8`
- end: `0x14002c50a`
- name: `?SetBackoffDepth@CWaitThreadList@@AEAAXK@Z`
- size: `322`
- prototype: `void __fastcall(CWaitThreadList *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140024efc`

## callees

- `0x140024944`
- `0x14002bd6c`
- `0x14002bea0`
- `0x14002c174`
- `0x14002c3c8`
- `0x14002c510`
- `0x14002c590`
- `0x14002ca08`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002c41b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002c427`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002c41b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002c427`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002c40d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002c40d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14002c444`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14002c4c2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14002c444`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14002c4c2`

## string_xrefs

- `0x14002c4f8`: `onecoreuap\base\appmodel\search\mssrch\gather\usractivity\waitthreadhelper.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CWaitThreadList::SetBackoffDepth(CWaitThreadList *this, int a2)
{
  char *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v4; // rcx
  void *v5; // rcx
  __int64 v6; // rcx
  char *v7; // rcx
  const char *v8; // r9
  __int64 **v9; // [rsp+28h] [rbp-20h] BYREF
  __int128 v10; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v12; // [rsp+58h] [rbp+10h] BYREF

  v12 = a2;
  v3 = (char *)this + 8;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SearchIndexerMultiSessionLockFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SearchIndexerMultiSessionLockFix>::GetImpl'::`2'::impl) )
  {
    while ( 1 )
    {
      CSyncReadWrite::SyncRead((CSyncReadWrite *)v3);
      EnterCriticalSection((LPCRITICAL_SECTION)(v3 + 56));
      v4 = (struct _RTL_CRITICAL_SECTION *)(v3 + 56);
      if ( !*(_DWORD *)v3 )
        break;
      LeaveCriticalSection(v4);
    }
    _InterlockedIncrement((volatile signed __int32 *)v3 + 2);
    LeaveCriticalSection(v4);
  }
  else
  {
    while ( 1 )
    {
      if ( *(_DWORD *)v3 )
        CSyncReadWrite::SyncRead((CSyncReadWrite *)v3);
      _InterlockedIncrement((volatile signed __int32 *)v3 + 2);
      if ( !*(_DWORD *)v3 )
        break;
      CSyncReadWrite::SyncReadDecrement((CSyncReadWrite *)v3);
    }
  }
  if ( *((_BYTE *)this + 136) )
  {
    v5 = (void *)*((_QWORD *)this + 16);
    if ( v5 != (void *)-1LL )
    {
      SetEvent(v5);
      LOBYTE(v12) = 0;
      SearchIndexerDiagnosticTelemetry::FilterProcessBackoff<bool>(&v12);
    }
  }
  if ( *((_DWORD *)this + 30) == 5 )
  {
    CSyncReadWrite::ReleaseReadAccess((CSyncReadWrite *)v3);
  }
  else
  {
    *((_DWORD *)this + 30) = 5;
    v9 = (__int64 **)this;
    v10 = 0;
    while ( (unsigned int)TKeyedLiteSListIterator<unsigned long,CThreadSmartWait,TPointer<CThreadSmartWait>,CWaitThreadList>::operator++(&v9) )
    {
      v6 = *(_QWORD *)(v10 + 8);
      if ( *(_DWORD *)(v6 + 16) != 5 )
      {
        *(_DWORD *)(v6 + 16) = 5;
        v7 = *(char **)(v6 + 40);
        if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !SetEvent(v7) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0x1CF,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\usractivity\\waitthreadhelper.cxx",
            v8);
      }
    }
    CSyncReadWrite::ReleaseReadAccess((CSyncReadWrite *)v3);
  }
}

```

## disassembly

```asm
0x14002c3c8  mov     rax, rsp
0x14002c3cb  mov     [rax+10h], edx
0x14002c3ce  push    rdi
0x14002c3cf  sub     rsp, 40h
0x14002c3d3  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x14002c3db  mov     [rax+18h], rbx
0x14002c3df  mov     [rax+20h], rsi
0x14002c3e3  mov     rdi, rcx
0x14002c3e6  lea     rbx, [rcx+8]
0x14002c3ea  mov     [rax+8], rbx
0x14002c3ee  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SearchIndexerMultiSessionLockFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SearchIndexerMultiSessionLockFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SearchIndexerMultiSessionLockFix> `wil::Feature<__WilFeatureTraits_Feature_SearchIndexerMultiSessionLockFix>::GetImpl(void)'::`2'::impl
0x14002c3f5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SearchIndexerMultiSessionLockFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SearchIndexerMultiSessionLockFix>::__private_IsEnabled(void)
0x14002c3fa  test    al, al
0x14002c3fc  jz      short loc_14002C46E
0x14002c3fe  lea     rsi, [rbx+38h]
0x14002c402  mov     rcx, rbx; this
0x14002c405  call    ?SyncRead@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::SyncRead(void)
0x14002c40a  mov     rcx, rsi; lpCriticalSection
0x14002c40d  call    cs:__imp_EnterCriticalSection
0x14002c413  mov     rcx, rsi; lpCriticalSection
0x14002c416  cmp     dword ptr [rbx], 0
0x14002c419  jz      short loc_14002C423
0x14002c41b  call    cs:__imp_LeaveCriticalSection
0x14002c421  jmp     short loc_14002C402
0x14002c423  lock inc dword ptr [rbx+8]
0x14002c427  call    cs:__imp_LeaveCriticalSection
0x14002c42d  nop
0x14002c42e  cmp     byte ptr [rdi+88h], 0
0x14002c435  jz      short loc_14002C459
0x14002c437  mov     rcx, [rdi+80h]; hEvent
0x14002c43e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14002c442  jz      short loc_14002C459
0x14002c444  call    cs:__imp_SetEvent
0x14002c44a  mov     byte ptr [rsp+48h+arg_8], 0
0x14002c44f  lea     rcx, [rsp+48h+arg_8]
0x14002c454  call    ??$FilterProcessBackoff@_N@SearchIndexerDiagnosticTelemetry@@SAX$$QEA_N@Z; SearchIndexerDiagnosticTelemetry::FilterProcessBackoff<bool>(bool &&)
0x14002c459  mov     esi, 5
0x14002c45e  cmp     [rdi+78h], esi
0x14002c461  jnz     short loc_14002C48E
0x14002c463  mov     rcx, rbx; this
0x14002c466  call    ?ReleaseReadAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseReadAccess(void)
0x14002c46b  nop
0x14002c46c  jmp     short loc_14002C4E3
0x14002c46e  cmp     dword ptr [rbx], 0
0x14002c471  jz      short loc_14002C47B
0x14002c473  mov     rcx, rbx; this
0x14002c476  call    ?SyncRead@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::SyncRead(void)
0x14002c47b  lock inc dword ptr [rbx+8]
0x14002c47f  cmp     dword ptr [rbx], 0
0x14002c482  jz      short loc_14002C42E
0x14002c484  mov     rcx, rbx; this
0x14002c487  call    ?SyncReadDecrement@CSyncReadWrite@@AEAAXXZ; CSyncReadWrite::SyncReadDecrement(void)
0x14002c48c  jmp     short loc_14002C46E
0x14002c48e  mov     [rdi+78h], esi
0x14002c491  mov     [rsp+48h+var_20], rdi
0x14002c496  xorps   xmm0, xmm0
0x14002c499  movdqu  [rsp+48h+var_18], xmm0
0x14002c49f  jmp     short loc_14002C4CC
0x14002c4a1  mov     rax, qword ptr [rsp+48h+var_18]
0x14002c4a6  mov     rcx, [rax+8]
0x14002c4aa  mov     eax, [rcx+10h]
0x14002c4ad  cmp     eax, esi
0x14002c4af  jz      short loc_14002C4CC
0x14002c4b1  mov     [rcx+10h], esi
0x14002c4b4  mov     rcx, [rcx+28h]; hEvent
0x14002c4b8  lea     rax, [rcx-1]
0x14002c4bc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14002c4c0  ja      short loc_14002C4CC
0x14002c4c2  call    cs:__imp_SetEvent
0x14002c4c8  test    eax, eax
0x14002c4ca  jz      short loc_14002C4F3
0x14002c4cc  lea     rcx, [rsp+48h+var_20]
0x14002c4d1  call    ??E?$TKeyedLiteSListIterator@KVCThreadSmartWait@@V?$TPointer@VCThreadSmartWait@@@@VCWaitThreadList@@@@QEAAHXZ; TKeyedLiteSListIterator<ulong,CThreadSmartWait,TPointer<CThreadSmartWait>,CWaitThreadList>::operator++(void)
0x14002c4d6  test    eax, eax
0x14002c4d8  jnz     short loc_14002C4A1
0x14002c4da  mov     rcx, rbx; this
0x14002c4dd  call    ?ReleaseReadAccess@CSyncReadWrite@@QEAAXXZ; CSyncReadWrite::ReleaseReadAccess(void)
0x14002c4e2  nop
0x14002c4e3  mov     rbx, [rsp+48h+arg_10]
0x14002c4e8  mov     rsi, [rsp+48h+arg_18]
0x14002c4ed  add     rsp, 40h
0x14002c4f1  pop     rdi
0x14002c4f2  retn
0x14002c4f3  mov     rcx, [rsp+48h]; this
0x14002c4f8  lea     r8, aOnecoreuapBase_27; "onecoreuap\\base\\appmodel\\search\\mss"...
0x14002c4ff  mov     edx, 1CFh; void *
0x14002c504  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
