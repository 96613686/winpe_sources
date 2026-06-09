# ipx::mtf::CMtfSuggestionClient::~CMtfSuggestionClient(void)

- ea: `0x1800144f0`
- end: `0x1800146aa`
- name: `??1CMtfSuggestionClient@mtf@ipx@@UEAA@XZ`
- size: `442`
- prototype: `void __fastcall(ipx::mtf::CMtfSuggestionClient *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180014980`

## callees

- `0x1800143f4`
- `0x1800144f0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014663`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180014663`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ipx::mtf::CMtfSuggestionClient::~CMtfSuggestionClient(ipx::mtf::CMtfSuggestionClient *this)
{
  __int64 v2; // rax
  _QWORD *v3; // rdi
  __int64 v4; // rcx
  __int64 v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx

  *(_QWORD *)this = &ipx::mtf::CMtfSuggestionClient::`vftable';
  *((_QWORD *)this + 1) = &ipx::mtf::CMtfSuggestionClient::`vftable'{for `IMtfDataSourceManagement2'};
  *((_QWORD *)this + 2) = &ipx::mtf::CMtfSuggestionClient::`vftable'{for `_MtfIUnknownImpl_Helper<IMtfSuggestionSynchronousRequester,IMtfTransportClient,IMtfRoamingWordsClient,void,void>'};
  *((_QWORD *)this + 3) = &ipx::mtf::CMtfSuggestionClient::`vftable'{for `IMtfTransportClient'};
  *((_QWORD *)this + 4) = &ipx::mtf::CMtfSuggestionClient::`vftable'{for `_MtfIUnknownImpl_Helper<IMtfRoamingWordsClient,void,void,void,void>'};
  v2 = *((_QWORD *)this + 17);
  v3 = (_QWORD *)((char *)this + 112);
  if ( v2 )
  {
    *(_QWORD *)(v2 + 16) = 0;
    if ( *v3 )
      (*(void (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v3 + 32LL))(*v3, (char *)this + 48);
  }
  if ( *((_BYTE *)this + 145) == 2 )
  {
    v4 = *v3;
    if ( *v3 )
    {
      *v3 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
    }
  }
  _InterlockedDecrement(&g_cRefDll);
  std::deque<std::unique_ptr<ipx::mtf::CClientDataSource>>::~deque<std::unique_ptr<ipx::mtf::CClientDataSource>>((char *)this + 160);
  v5 = *((_QWORD *)this + 19);
  *((_QWORD *)this + 19) = 0;
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  v6 = *((_QWORD *)this + 17);
  *((_QWORD *)this + 17) = 0;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = *((_QWORD *)this + 16);
  *((_QWORD *)this + 16) = 0;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = *((_QWORD *)this + 15);
  *((_QWORD *)this + 15) = 0;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  v9 = *v3;
  *v3 = 0;
  if ( v9 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  v10 = *((_QWORD *)this + 13);
  *((_QWORD *)this + 13) = 0;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  *(_QWORD *)this = &MtfIUnknownImpl<IMtfSuggestionLatticeClient,IMtfDataSourceManagement2,IMtfSuggestionSynchronousRequester,IMtfTransportClient,IMtfRoamingWordsClient>::`vftable';
  *((_QWORD *)this + 1) = &MtfIUnknownImpl<IMtfSuggestionLatticeClient,IMtfDataSourceManagement2,IMtfSuggestionSynchronousRequester,IMtfTransportClient,IMtfRoamingWordsClient>::`vftable'{for `IMtfDataSourceManagement2'};
  *((_QWORD *)this + 2) = &MtfIUnknownImpl<IMtfSuggestionLatticeClient,IMtfDataSourceManagement2,IMtfSuggestionSynchronousRequester,IMtfTransportClient,IMtfRoamingWordsClient>::`vftable'{for `_MtfIUnknownImpl_Helper<IMtfSuggestionSynchronousRequester,IMtfTransportClient,IMtfRoamingWordsClient,void,void>'};
  *((_QWORD *)this + 3) = &MtfIUnknownImpl<IMtfSuggestionLatticeClient,IMtfDataSourceManagement2,IMtfSuggestionSynchronousRequester,IMtfTransportClient,IMtfRoamingWordsClient>::`vftable'{for `IMtfTransportClient'};
  *((_QWORD *)this + 4) = &MtfIUnknownImpl<IMtfSuggestionLatticeClient,IMtfDataSourceManagement2,IMtfSuggestionSynchronousRequester,IMtfTransportClient,IMtfRoamingWordsClient>::`vftable'{for `_MtfIUnknownImpl_Helper<IMtfRoamingWordsClient,void,void,void,void>'};
}

```

## disassembly

```asm
0x1800144f0  mov     [rsp+arg_0], rbx
0x1800144f5  push    rdi
0x1800144f6  sub     rsp, 20h
0x1800144fa  mov     rbx, rcx
0x1800144fd  lea     rax, ??_7CMtfSuggestionClient@mtf@ipx@@6B@; const ipx::mtf::CMtfSuggestionClient::`vftable'
0x180014504  mov     [rcx], rax
0x180014507  lea     rax, ??_7CMtfSuggestionClient@mtf@ipx@@6BIMtfDataSourceManagement2@@@; const ipx::mtf::CMtfSuggestionClient::`vftable'{for `IMtfDataSourceManagement2'}
0x18001450e  mov     [rcx+8], rax
0x180014512  lea     rax, ??_7CMtfSuggestionClient@mtf@ipx@@6B?$_MtfIUnknownImpl_Helper@UIMtfSuggestionSynchronousRequester@@UIMtfTransportClient@@UIMtfRoamingWordsClient@@XX@@@; const ipx::mtf::CMtfSuggestionClient::`vftable'{for `_MtfIUnknownImpl_Helper<IMtfSuggestionSynchronousRequester,IMtfTransportClient,IMtfRoamingWordsClient,void,void>'}
0x180014519  mov     [rcx+10h], rax
0x18001451d  lea     rax, ??_7CMtfSuggestionClient@mtf@ipx@@6BIMtfTransportClient@@@; const ipx::mtf::CMtfSuggestionClient::`vftable'{for `IMtfTransportClient'}
0x180014524  mov     [rcx+18h], rax
0x180014528  lea     rax, ??_7CMtfSuggestionClient@mtf@ipx@@6B?$_MtfIUnknownImpl_Helper@UIMtfRoamingWordsClient@@XXXX@@@; const ipx::mtf::CMtfSuggestionClient::`vftable'{for `_MtfIUnknownImpl_Helper<IMtfRoamingWordsClient,void,void,void,void>'}
0x18001452f  mov     [rcx+20h], rax
0x180014533  mov     rax, [rcx+88h]
0x18001453a  lea     rdi, [rcx+70h]
0x18001453e  test    rax, rax
0x180014541  jz      short loc_180014563
0x180014543  mov     qword ptr [rax+10h], 0
0x18001454b  mov     rcx, [rdi]
0x18001454e  test    rcx, rcx
0x180014551  jz      short loc_180014563
0x180014553  mov     rax, [rcx]
0x180014556  lea     rdx, [rbx+30h]
0x18001455a  mov     rax, [rax+20h]
0x18001455e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014563  cmp     byte ptr [rbx+91h], 2
0x18001456a  jnz     short loc_180014587
0x18001456c  mov     rcx, [rdi]
0x18001456f  test    rcx, rcx
0x180014572  jz      short loc_180014587
0x180014574  mov     qword ptr [rdi], 0
0x18001457b  mov     rax, [rcx]
0x18001457e  mov     rax, [rax+10h]
0x180014582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014587  lock dec cs:?g_cRefDll@@3JA; long g_cRefDll
0x18001458e  lea     rcx, [rbx+0A0h]
0x180014595  call    ??1?$deque@V?$unique_ptr@VCClientDataSource@mtf@ipx@@U?$default_delete@VCClientDataSource@mtf@ipx@@@std@@@std@@V?$allocator@V?$unique_ptr@VCClientDataSource@mtf@ipx@@U?$default_delete@VCClientDataSource@mtf@ipx@@@std@@@std@@@2@@std@@QEAA@XZ; std::deque<std::unique_ptr<ipx::mtf::CClientDataSource>>::~deque<std::unique_ptr<ipx::mtf::CClientDataSource>>(void)
0x18001459a  nop
0x18001459b  mov     rcx, [rbx+98h]
0x1800145a2  mov     qword ptr [rbx+98h], 0
0x1800145ad  test    rcx, rcx
0x1800145b0  jz      short loc_1800145BF
0x1800145b2  mov     rax, [rcx]
0x1800145b5  mov     rax, [rax+10h]
0x1800145b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145be  nop
0x1800145bf  mov     rcx, [rbx+88h]
0x1800145c6  mov     qword ptr [rbx+88h], 0
0x1800145d1  test    rcx, rcx
0x1800145d4  jz      short loc_1800145E3
0x1800145d6  mov     rax, [rcx]
0x1800145d9  mov     rax, [rax+10h]
0x1800145dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145e2  nop
0x1800145e3  mov     rcx, [rbx+80h]
0x1800145ea  mov     qword ptr [rbx+80h], 0
0x1800145f5  test    rcx, rcx
0x1800145f8  jz      short loc_180014607
0x1800145fa  mov     rax, [rcx]
0x1800145fd  mov     rax, [rax+10h]
0x180014601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014606  nop
0x180014607  mov     rcx, [rbx+78h]
0x18001460b  mov     qword ptr [rbx+78h], 0
0x180014613  test    rcx, rcx
0x180014616  jz      short loc_180014625
0x180014618  mov     rax, [rcx]
0x18001461b  mov     rax, [rax+10h]
0x18001461f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014624  nop
0x180014625  mov     rcx, [rdi]
0x180014628  mov     qword ptr [rdi], 0
0x18001462f  test    rcx, rcx
0x180014632  jz      short loc_180014641
0x180014634  mov     rax, [rcx]
0x180014637  mov     rax, [rax+10h]
0x18001463b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014640  nop
0x180014641  mov     rcx, [rbx+68h]
0x180014645  mov     qword ptr [rbx+68h], 0
0x18001464d  test    rcx, rcx
0x180014650  jz      short loc_18001465F
0x180014652  mov     rax, [rcx]
0x180014655  mov     rax, [rax+10h]
0x180014659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001465e  nop
0x18001465f  lea     rcx, [rbx+40h]; lpCriticalSection
0x180014663  call    cs:__imp_DeleteCriticalSection
0x180014669  lea     rax, ??_7?$MtfIUnknownImpl@UIMtfSuggestionLatticeClient@@UIMtfDataSourceManagement2@@UIMtfSuggestionSynchronousRequester@@UIMtfTransportClient@@UIMtfRoamingWordsClient@@@@6B@; const MtfIUnknownImpl<IMtfSuggestionLatticeClient,IMtfDataSourceManagement2,IMtfSuggestionSynchronousRequester,IMtfTransportClient,IMtfRoamingWordsClient>::`vftable'
0x180014670  mov     [rbx], rax
0x180014673  lea     rax, ??_7?$MtfIUnknownImpl@UIMtfSuggestionLatticeClient@@UIMtfDataSourceManagement2@@UIMtfSuggestionSynchronousRequester@@UIMtfTransportClient@@UIMtfRoamingWordsClient@@@@6BIMtfDataSourceManagement2@@@; const MtfIUnknownImpl<IMtfSuggestionLatticeClient,IMtfDataSourceManagement2,IMtfSuggestionSynchronousRequester,IMtfTransportClient,IMtfRoamingWordsClient>::`vftable'{for `IMtfDataSourceManagement2'}
0x18001467a  mov     [rbx+8], rax
0x18001467e  lea     rax, ??_7?$MtfIUnknownImpl@UIMtfSuggestionLatticeClient@@UIMtfDataSourceManagement2@@UIMtfSuggestionSynchronousRequester@@UIMtfTransportClient@@UIMtfRoamingWordsClient@@@@6B?$_MtfIUnknownImpl_Helper@UIMtfSuggestionSynchronousRequester@@UIMtfTransportClient@@UIMtfRoamingWordsClient@@XX@@@; const MtfIUnknownImpl<IMtfSuggestionLatticeClient,IMtfDataSourceManagement2,IMtfSuggestionSynchronousRequester,IMtfTransportClient,IMtfRoamingWordsClient>::`vftable'{for `_MtfIUnknownImpl_Helper<IMtfSuggestionSynchronousRequester,IMtfTransportClient,IMtfRoamingWordsClient,void,void>'}
0x180014685  mov     [rbx+10h], rax
0x180014689  lea     rax, ??_7?$MtfIUnknownImpl@UIMtfSuggestionLatticeClient@@UIMtfDataSourceManagement2@@UIMtfSuggestionSynchronousRequester@@UIMtfTransportClient@@UIMtfRoamingWordsClient@@@@6BIMtfTransportClient@@@; const MtfIUnknownImpl<IMtfSuggestionLatticeClient,IMtfDataSourceManagement2,IMtfSuggestionSynchronousRequester,IMtfTransportClient,IMtfRoamingWordsClient>::`vftable'{for `IMtfTransportClient'}
0x180014690  mov     [rbx+18h], rax
0x180014694  lea     rax, ??_7?$MtfIUnknownImpl@UIMtfSuggestionLatticeClient@@UIMtfDataSourceManagement2@@UIMtfSuggestionSynchronousRequester@@UIMtfTransportClient@@UIMtfRoamingWordsClient@@@@6B?$_MtfIUnknownImpl_Helper@UIMtfRoamingWordsClient@@XXXX@@@; const MtfIUnknownImpl<IMtfSuggestionLatticeClient,IMtfDataSourceManagement2,IMtfSuggestionSynchronousRequester,IMtfTransportClient,IMtfRoamingWordsClient>::`vftable'{for `_MtfIUnknownImpl_Helper<IMtfRoamingWordsClient,void,void,void,void>'}
0x18001469b  mov     [rbx+20h], rax
0x18001469f  mov     rbx, [rsp+28h+arg_0]
0x1800146a4  add     rsp, 20h
0x1800146a8  pop     rdi
0x1800146a9  retn
```
