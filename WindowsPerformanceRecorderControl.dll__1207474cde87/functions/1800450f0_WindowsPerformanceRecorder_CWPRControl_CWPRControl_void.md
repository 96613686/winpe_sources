# WindowsPerformanceRecorder::CWPRControl::~CWPRControl(void)

- ea: `0x1800450f0`
- end: `0x180045215`
- name: `??1CWPRControl@WindowsPerformanceRecorder@@QEAA@XZ`
- size: `293`
- prototype: `void __fastcall(WindowsPerformanceRecorder::CWPRControl *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180056a84`

## callees

- `0x180021810`
- `0x1800419e8`
- `0x1800450f0`
- `0x18004521c`
- `0x180045250`
- `0x180047a58`
- `0x180051100`
- `0x180051214`
- `0x180056a58`
- `0x180056a6c`
- `0x180056c3c`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800451cd`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800451cd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800451ef`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800451ef`
- `OLEAUT32!__imp_SysFreeString` at `0x1800451da`
- `OLEAUT32!__imp_SysFreeString` at `0x1800451da`

## pseudocode

```c
void __fastcall WindowsPerformanceRecorder::CWPRControl::~CWPRControl(WindowsPerformanceRecorder::CWPRControl *this)
{
  char *v2; // rsi
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  const void **v6; // rbx
  volatile signed __int32 *v7; // rbx
  HMODULE v8; // rcx
  __int64 v9; // [rsp+28h] [rbp-20h] BYREF
  __int64 v10; // [rsp+30h] [rbp-18h] BYREF
  volatile signed __int32 *v11; // [rsp+38h] [rbp-10h]
  char v12; // [rsp+50h] [rbp+8h] BYREF

  v2 = (char *)this + 168;
  std::_Tree<std::_Tset_traits<unsigned short const *,std::less<unsigned short const *>,std::allocator<unsigned short const *>,0>>::_Unchecked_begin(
    (char *)this + 168,
    &v12);
  while ( (unsigned __int8)std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>>>,std::_Iterator_base0>::operator!=(
                             &v12,
                             v3,
                             v4,
                             v5) )
  {
    v6 = (const void **)std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CEventProviderInfo *>>,std::_Iterator_base0>::operator*(&v12);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v9,
      v6);
    std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>(
      &v10,
      v6 + 1);
    v10 = 0;
    v7 = v11;
    v11 = 0;
    if ( v7 )
    {
      if ( _InterlockedExchangeAdd(v7 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v7)(v7);
        if ( _InterlockedExchangeAdd(v7 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v7 + 8LL))(v7);
      }
    }
    std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>::~pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>((WindowsPerformanceRecorder::Status::CSessionInfo *)&v9);
    std::_Tree_unchecked_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WindowsPerformanceRecorder::CBaseProfileElement const * const,std::set<WindowsPerformanceRecorder::CBaseProfileElement const *>>>>>::operator++(&v12);
  }
  v8 = (HMODULE)*((_QWORD *)this + 8);
  if ( v8 )
    FreeLibrary(v8);
  SysFreeString(*((BSTR *)this + 23));
  std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>>,0>>(v2);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 128));
  WindowsPerformanceRecorder::CEventProvidersCollection::~CEventProvidersCollection((WindowsPerformanceRecorder::CWPRControl *)((char *)this + 80));
  Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(this);
}

```

## disassembly

```asm
0x1800450f0  mov     rax, rsp
0x1800450f3  push    rdi
0x1800450f4  sub     rsp, 40h
0x1800450f8  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x180045100  mov     [rax+10h], rbx
0x180045104  mov     [rax+18h], rsi
0x180045108  mov     rdi, rcx
0x18004510b  lea     rsi, [rcx+0A8h]
0x180045112  lea     rdx, [rax+8]
0x180045116  mov     rcx, rsi
0x180045119  call    ?_Unchecked_begin@?$_Tree@V?$_Tset_traits@PEBGU?$less@PEBG@std@@V?$allocator@PEBG@2@$0A@@std@@@std@@QEAA?AV?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEBG@std@@@std@@U_Iterator_base0@2@@2@XZ; std::_Tree<std::_Tset_traits<ushort const *,std::less<ushort const *>,std::allocator<ushort const *>,0>>::_Unchecked_begin(void)
0x18004511e  jmp     loc_1800451B2
0x180045123  lea     rcx, [rsp+48h+arg_0]
0x180045128  call    ??D?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@PEAUCEventProviderInfo@WindowsPerformanceRecorder@@@std@@@std@@U_Iterator_base0@2@@std@@QEBAAEBQEAUCEventProviderInfo@WindowsPerformanceRecorder@@XZ; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<WindowsPerformanceRecorder::CEventProviderInfo *>>,std::_Iterator_base0>::operator*(void)
0x18004512d  mov     rbx, rax
0x180045130  mov     rdx, rax; void *
0x180045133  lea     rcx, [rsp+48h+var_20]; void *
0x180045138  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18004513d  lea     rdx, [rbx+8]
0x180045141  lea     rcx, [rsp+48h+var_18]
0x180045146  call    ??0?$shared_ptr@UCInstanceNameScopedData@WindowsPerformanceRecorder@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>(std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData> const &)
0x18004514b  mov     [rsp+48h+var_18], 0
0x180045154  mov     rbx, [rsp+48h+var_10]
0x180045159  mov     [rsp+48h+var_10], 0
0x180045162  test    rbx, rbx
0x180045165  jz      short loc_18004519E
0x180045167  or      eax, 0FFFFFFFFh
0x18004516a  lock xadd [rbx+8], eax
0x18004516f  cmp     eax, 1
0x180045172  jnz     short loc_18004519E
0x180045174  mov     rax, [rbx]
0x180045177  mov     rcx, rbx
0x18004517a  mov     rax, [rax]
0x18004517d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045182  or      eax, 0FFFFFFFFh
0x180045185  lock xadd [rbx+0Ch], eax
0x18004518a  cmp     eax, 1
0x18004518d  jnz     short loc_18004519E
0x18004518f  mov     rax, [rbx]
0x180045192  mov     rcx, rbx
0x180045195  mov     rax, [rax+8]
0x180045199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004519e  lea     rcx, [rsp+48h+var_20]; this
0x1800451a3  call    ??1?$pair@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$shared_ptr@UCInstanceNameScopedData@WindowsPerformanceRecorder@@@std@@@std@@QEAA@XZ; std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>::~pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>(void)
0x1800451a8  lea     rcx, [rsp+48h+arg_0]
0x1800451ad  call    ??E?$_Tree_unchecked_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEBVCBaseProfileElement@WindowsPerformanceRecorder@@V?$set@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@U?$less@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@std@@V?$allocator@PEBVCBaseProfileElement@WindowsPerformanceRecorder@@@4@@std@@@std@@@std@@@std@@@std@@QEAAAEAV01@XZ; std::_Tree_unchecked_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<WindowsPerformanceRecorder::CBaseProfileElement const * const,std::set<WindowsPerformanceRecorder::CBaseProfileElement const *>>>>>::operator++(void)
0x1800451b2  lea     rcx, [rsp+48h+arg_0]
0x1800451b7  call    ??9?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$shared_ptr@UCInstanceNameScopedData@WindowsPerformanceRecorder@@@std@@@std@@@std@@@std@@U_Iterator_base0@2@@std@@QEBA_NU_Default_sentinel@1@@Z; std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>>>,std::_Iterator_base0>::operator!=(std::_Default_sentinel)
0x1800451bc  test    al, al
0x1800451be  jnz     loc_180045123
0x1800451c4  mov     rcx, [rdi+40h]; hLibModule
0x1800451c8  test    rcx, rcx
0x1800451cb  jz      short loc_1800451D3
0x1800451cd  call    cs:__imp_FreeLibrary
0x1800451d3  mov     rcx, [rdi+0B8h]; bstrString
0x1800451da  call    cs:__imp_SysFreeString
0x1800451e0  mov     rcx, rsi
0x1800451e3  call    ??1?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$shared_ptr@UCInstanceNameScopedData@WindowsPerformanceRecorder@@@std@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@4@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$shared_ptr@UCInstanceNameScopedData@WindowsPerformanceRecorder@@@std@@@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>>,0>>::~_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,std::shared_ptr<WindowsPerformanceRecorder::CInstanceNameScopedData>>>,0>>(void)
0x1800451e8  lea     rcx, [rdi+80h]; lpCriticalSection
0x1800451ef  call    cs:__imp_DeleteCriticalSection
0x1800451f5  lea     rcx, [rdi+50h]; this
0x1800451f9  call    ??1CEventProvidersCollection@WindowsPerformanceRecorder@@QEAA@XZ; WindowsPerformanceRecorder::CEventProvidersCollection::~CEventProvidersCollection(void)
0x1800451fe  mov     rcx, rdi
0x180045201  mov     rbx, [rsp+48h+arg_8]
0x180045206  mov     rsi, [rsp+48h+arg_10]
0x18004520b  add     rsp, 40h
0x18004520f  pop     rdi
0x180045210  jmp     ??1?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAA@XZ; Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(void)
```
