# CMapiManager::AddStoreWatcher(ulong,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)

- ea: `0x18002d4e0`
- end: `0x18002d64c`
- name: `?AddStoreWatcher@CMapiManager@@QEAAHKAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@Z`
- size: `364`
- prototype: `__int64 __fastcall(__int64, DWORD, __int64)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180032328`
- `0x1800347f0`

## callees

- `0x180002780`
- `0x180004c20`
- `0x18000fd58`
- `0x180011530`
- `0x18002d454`
- `0x18002d4e0`
- `0x18002ff78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d51b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002d51b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d601`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002d601`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d610`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d610`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002d594`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18002d594`

## string_xrefs

- `0x18002d616`: `CMapiManager failed to create store watcher`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CMapiManager::AddStoreWatcher(__int64 a1, DWORD a2, __int64 a3)
{
  unsigned int v7; // ebx
  HANDLE v8; // rsi
  int v9; // ebp
  _QWORD *v10; // rax
  _QWORD *v11; // [rsp+50h] [rbp+8h] BYREF
  struct _RTL_CRITICAL_SECTION *v12; // [rsp+68h] [rbp+20h] BYREF

  if ( !*(_DWORD *)(a1 + 156) )
    return 0;
  v12 = (struct _RTL_CRITICAL_SECTION *)(a1 + 352);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 352));
  v11 = 0;
  if ( !(unsigned __int8)ATL::CAtlMap<unsigned long,CMapiManager::CStoreWatcher *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::Lookup(
                           a1 + 280,
                           a2,
                           &v11) )
  {
    v7 = 1;
    if ( a2 )
    {
      v8 = OpenProcess(0x100000u, 0, a2);
      if ( !v8 )
        goto LABEL_15;
      v9 = 0;
    }
    else
    {
      v8 = *(HANDLE *)(a1 + 264);
      if ( !v8 )
        goto LABEL_15;
      *(_QWORD *)(a1 + 264) = 0;
      v9 = 1;
    }
    v10 = operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
    v11 = v10;
    if ( v10 )
    {
      v10[2] = 0;
      v10[3] = 0;
      *v10 = v8;
      *((_DWORD *)v10 + 2) = v9;
      v11 = v10;
      ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::Add(
        v10 + 2,
        a3);
      ATL::CAtlMap<unsigned long,CMapiManager::CStoreWatcher *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::SetAt(
        a1 + 280,
        a2,
        &v11);
      SetEvent(*(HANDLE *)(a1 + 272));
      goto LABEL_16;
    }
    if ( !v9 )
      CloseHandle(v8);
    CLogger::Error(-2147024882, L"CMapiManager failed to create store watcher");
LABEL_15:
    v7 = 0;
    goto LABEL_16;
  }
  ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::Add(
    v11 + 2,
    a3);
  v7 = 1;
LABEL_16:
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v12);
  return v7;
}

```

## disassembly

```asm
0x18002d4e0  mov     [rsp+arg_8], rbx
0x18002d4e5  mov     [rsp+arg_10], rbp
0x18002d4ea  push    rsi
0x18002d4eb  push    rdi
0x18002d4ec  push    r12
0x18002d4ee  push    r14
0x18002d4f0  push    r15
0x18002d4f2  sub     rsp, 20h
0x18002d4f6  mov     r15, r8
0x18002d4f9  mov     r14d, edx
0x18002d4fc  mov     rdi, rcx
0x18002d4ff  cmp     dword ptr [rcx+9Ch], 0
0x18002d506  jnz     short loc_18002D50F
0x18002d508  xor     eax, eax
0x18002d50a  jmp     loc_18002D635
0x18002d50f  add     rcx, 160h; lpCriticalSection
0x18002d516  mov     [rsp+48h+arg_18], rcx
0x18002d51b  call    cs:__imp_EnterCriticalSection
0x18002d521  nop
0x18002d522  mov     [rsp+48h+arg_0], 0
0x18002d52b  lea     r12, [rdi+118h]
0x18002d532  lea     r8, [rsp+48h+arg_0]
0x18002d537  mov     edx, r14d
0x18002d53a  mov     rcx, r12
0x18002d53d  call    ?Lookup@?$CAtlMap@KPEAVCStoreWatcher@CMapiManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVCStoreWatcher@CMapiManager@@@4@@ATL@@QEBA_NKAEAPEAVCStoreWatcher@CMapiManager@@@Z; ATL::CAtlMap<ulong,CMapiManager::CStoreWatcher *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::Lookup(ulong,CMapiManager::CStoreWatcher * &)
0x18002d542  test    al, al
0x18002d544  jz      short loc_18002D561
0x18002d546  mov     rcx, [rsp+48h+arg_0]
0x18002d54b  add     rcx, 10h
0x18002d54f  mov     rdx, r15
0x18002d552  call    ?Add@?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAHAEBV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@2@@Z; ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::Add(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x18002d557  mov     ebx, 1
0x18002d55c  jmp     loc_18002D629
0x18002d561  mov     ebx, 1
0x18002d566  test    r14d, r14d
0x18002d569  jnz     short loc_18002D58A
0x18002d56b  mov     rsi, [rdi+108h]
0x18002d572  test    rsi, rsi
0x18002d575  jz      loc_18002D627
0x18002d57b  mov     qword ptr [rdi+108h], 0
0x18002d586  mov     ebp, ebx
0x18002d588  jmp     short loc_18002D5A8
0x18002d58a  mov     r8d, r14d; dwProcessId
0x18002d58d  xor     edx, edx; bInheritHandle
0x18002d58f  mov     ecx, 100000h; dwDesiredAccess
0x18002d594  call    cs:__imp_OpenProcess
0x18002d59a  mov     rsi, rax
0x18002d59d  test    rax, rax
0x18002d5a0  jz      loc_18002D627
0x18002d5a6  xor     ebp, ebp
0x18002d5a8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002d5af  mov     ecx, 20h ; ' '; unsigned __int64
0x18002d5b4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002d5b9  mov     [rsp+48h+arg_0], rax
0x18002d5be  test    rax, rax
0x18002d5c1  jz      short loc_18002D609
0x18002d5c3  mov     qword ptr [rax+10h], 0
0x18002d5cb  mov     qword ptr [rax+18h], 0
0x18002d5d3  mov     [rax], rsi
0x18002d5d6  mov     [rax+8], ebp
0x18002d5d9  mov     [rsp+48h+arg_0], rax
0x18002d5de  lea     rcx, [rax+10h]
0x18002d5e2  mov     rdx, r15
0x18002d5e5  call    ?Add@?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@QEAAHAEBV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@2@@Z; ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>::Add(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> const &)
0x18002d5ea  lea     r8, [rsp+48h+arg_0]
0x18002d5ef  mov     edx, r14d
0x18002d5f2  mov     rcx, r12
0x18002d5f5  call    ?SetAt@?$CAtlMap@KPEAVCStoreWatcher@CMapiManager@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVCStoreWatcher@CMapiManager@@@4@@ATL@@QEAAPEAU__POSITION@@KAEBQEAVCStoreWatcher@CMapiManager@@@Z; ATL::CAtlMap<ulong,CMapiManager::CStoreWatcher *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CMapiManager::CStoreWatcher *>>::SetAt(ulong,CMapiManager::CStoreWatcher * const &)
0x18002d5fa  mov     rcx, [rdi+110h]; hEvent
0x18002d601  call    cs:__imp_SetEvent
0x18002d607  jmp     short loc_18002D629
0x18002d609  test    ebp, ebp
0x18002d60b  jnz     short loc_18002D616
0x18002d60d  mov     rcx, rsi; hObject
0x18002d610  call    cs:__imp_CloseHandle
0x18002d616  lea     rdx, aCmapimanagerFa; "CMapiManager failed to create store wat"...
0x18002d61d  mov     ecx, 8007000Eh; int
0x18002d622  call    ?Error@CLogger@@SAXJPEB_WZZ; CLogger::Error(long,wchar_t const *,...)
0x18002d627  xor     ebx, ebx
0x18002d629  lea     rcx, [rsp+48h+arg_18]
0x18002d62e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18002d633  mov     eax, ebx
0x18002d635  mov     rbx, [rsp+48h+arg_8]
0x18002d63a  mov     rbp, [rsp+48h+arg_10]
0x18002d63f  add     rsp, 20h
0x18002d643  pop     r15
0x18002d645  pop     r14
0x18002d647  pop     r12
0x18002d649  pop     rdi
0x18002d64a  pop     rsi
0x18002d64b  retn
```
