# ConnectedStorage::Context::DeleteContainerImpl(std::shared_ptr<ConnectedStorage::ContextOperationToken>,ConnectedStorage::SimpleHStringWrapper,std::shared_ptr<ConnectedStorage::DeleteData>)

- ea: `0x18005c3dc`
- end: `0x18005c66f`
- name: `?DeleteContainerImpl@Context@ConnectedStorage@@AEAAXV?$shared_ptr@VContextOperationToken@ConnectedStorage@@@std@@VSimpleHStringWrapper@2@V?$shared_ptr@UDeleteData@ConnectedStorage@@@4@@Z`
- size: `659`
- prototype: `__int64 __fastcall(ConnectedStorage::Context *this)`
- caller_count: `2`
- callee_count: `22`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18005b6b0`
- `0x18005c678`

## callees

- `0x180003c70`
- `0x18000aae4`
- `0x18000cb9c`
- `0x18000d2b8`
- `0x18001253c`
- `0x1800190f0`
- `0x180019128`
- `0x18001c8f0`
- `0x18005b280`
- `0x18005bdec`
- `0x18005c3dc`
- `0x18005e420`
- `0x18005e6b4`
- `0x18005e7fc`
- `0x18005ea20`
- `0x1800644ec`
- `0x1800658c0`
- `0x18006b7c8`
- `0x18006b8f8`
- `0x180073498`
- `0x180076ca8`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005c4b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005c4b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c620`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c620`

## string_xrefs

- `0x18005c65c`: `DeleteContainer - GetContainer returned a container that's already been removed`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall ConnectedStorage::Context::DeleteContainerImpl(
        ConnectedStorage::Context *this,
        __int64 a2,
        const struct ConnectedStorage::SimpleHStringWrapper *a3,
        _QWORD *a4)
{
  _QWORD *v4; // rdi
  const struct ConnectedStorage::SimpleHStringWrapper *v5; // rbx
  std::_Ref_count_base *v8; // rcx
  struct ConnectedStorage::ContainerIndexEntry *ExistingContainerIndexEntry; // rax
  char *v10; // r8
  struct ConnectedStorage::ContainerIndexEntry *v11; // r15
  __int64 Container; // rax
  const unsigned __int16 *v13; // r8
  __int64 v14; // r14
  const struct ConnectedStorage::CallerInfo *v15; // r8
  _QWORD *v16; // rax
  std::_Ref_count_base *v17; // rcx
  unsigned int v18; // [rsp+20h] [rbp-118h]
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+38h] [rbp-100h] BYREF
  std::_Ref_count_base *v22[2]; // [rsp+48h] [rbp-F0h] BYREF
  ConnectedStorage::Container *v23; // [rsp+58h] [rbp-E0h] BYREF
  std::_Ref_count_base *v24; // [rsp+60h] [rbp-D8h]
  __int64 v25; // [rsp+68h] [rbp-D0h]
  ConnectedStorage::MultiFileWrite *v26; // [rsp+70h] [rbp-C8h] BYREF
  std::_Ref_count_base *v27; // [rsp+78h] [rbp-C0h]
  HSTRING v28[3]; // [rsp+80h] [rbp-B8h] BYREF
  int v29; // [rsp+98h] [rbp-A0h]
  __int64 v30; // [rsp+A0h] [rbp-98h]
  int v31; // [rsp+B8h] [rbp-80h]
  int v32; // [rsp+BCh] [rbp-7Ch]
  _DWORD v33[16]; // [rsp+C0h] [rbp-78h] BYREF

  v4 = a4;
  v5 = a3;
  v25 = a2;
  ConnectedStorage::Context::ResetActivatingContainer(this);
  if ( *v4
    && (unsigned __int8)ConnectedStorage::OperationData<IStorageReadHandler,AsyncIStorageReadHandler>::CheckCanceled(*v4) )
  {
    v8 = *(std::_Ref_count_base **)(a2 + 8);
  }
  else
  {
    try
    {
      v18 = 0;
      ExistingContainerIndexEntry = ConnectedStorage::ContainerIndex::GetExistingContainerIndexEntry(
                                      *((ConnectedStorage::ContainerIndex **)this + 38),
                                      v5,
                                      0);
      v11 = ExistingContainerIndexEntry;
      if ( ExistingContainerIndexEntry && *((_DWORD *)ExistingContainerIndexEntry + 7) != 3 )
      {
        *(_OWORD *)v22 = 0;
        ConnectedStorage::Mutex::Lock::Lock(
          (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
          (struct _RTL_CRITICAL_SECTION *)((char *)this + 328),
          v10);
        Container = ConnectedStorage::Containers::GetContainer((char *)this + 264, &v23, v11);
        std::weak_ptr<ConnectedStorage::Container>::operator=(v22, Container);
        if ( v24 )
          std::_Ref_count_base::_Decwref(v24);
        LeaveCriticalSection(lpCriticalSection[0]);
        std::weak_ptr<ConnectedStorage::UploadingContext>::lock(v22, &v23);
        if ( !v23 )
          ConnectedStorage::ReportErrorAndThrow(
            (ConnectedStorage *)0x8000FFFFLL,
            (int)L"DeleteContainer - GetContainer returned a container that's already been removed",
            v13);
        v14 = *((_QWORD *)v23 + 21);
        ConnectedStorage::Container::SetDeleted(v23);
        ConnectedStorage::Context::UpdateBytes(this, -v14, 0);
        ConnectedStorage::MultiFileWrite::Create(&v26);
        ConnectedStorage::ContainerIndex::SetLastModifiedTimeToNow(*((ConnectedStorage::ContainerIndex **)this + 38));
        *(_OWORD *)v28 = 0;
        v29 = 0;
        v30 = 0;
        v31 = 5000;
        v32 = 15000;
        if ( *v4 )
          v15 = (const struct ConnectedStorage::CallerInfo *)(*v4 + 32LL);
        else
          v15 = (const struct ConnectedStorage::CallerInfo *)v28;
        ConnectedStorage::ContainerIndex::Save(*((ConnectedStorage::ContainerIndex **)this + 38), v26, v15);
        ConnectedStorage::MultiFileWrite::Commit(v26);
        (*(void (__fastcall **)(ConnectedStorage::Context *, struct ConnectedStorage::ContainerIndexEntry *))(*(_QWORD *)this + 64LL))(
          this,
          v11);
        v16 = std::weak_ptr<ConnectedStorage::Context>::weak_ptr<ConnectedStorage::Context>(lpCriticalSection, v22);
        ConnectedStorage::Context::ScheduleUploadForDeleteContainer(this, v16);
        ConnectedStorage::CallerInfo::~CallerInfo(v28);
        if ( v27 )
          std::_Ref_count_base::_Decref(v27);
        if ( v24 )
          std::_Ref_count_base::_Decref(v24);
        if ( v22[1] )
          std::_Ref_count_base::_Decwref(v22[1]);
      }
    }
    catch ( ConnectedStorage::ComError v33 )
    {
      v18 = v33[6];
      ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v33);
      v5 = a3;
      v4 = a4;
    }
    catch ( std::bad_alloc )
    {
      v18 = -2147024882;
      v5 = a3;
      v4 = a4;
    }
    catch ( ... )
    {
      v18 = -2147467259;
      v5 = a3;
      v4 = a4;
    }
    if ( *v4 )
      (**(void (__fastcall ***)(_QWORD, _QWORD))*v4)(*v4, v18);
    v8 = *(std::_Ref_count_base **)(v25 + 8);
  }
  if ( v8 )
    std::_Ref_count_base::_Decref(v8);
  WindowsDeleteString(*(HSTRING *)v5);
  *(_QWORD *)v5 = 0;
  v17 = (std::_Ref_count_base *)v4[1];
  if ( v17 )
    std::_Ref_count_base::_Decref(v17);
}

```

## disassembly

```asm
0x18005c3dc  push    rbx
0x18005c3de  push    rsi
0x18005c3df  push    rdi
0x18005c3e0  push    r14
0x18005c3e2  push    r15
0x18005c3e4  sub     rsp, 110h
0x18005c3eb  mov     rax, cs:__security_cookie
0x18005c3f2  xor     rax, rsp
0x18005c3f5  mov     [rsp+138h+var_38], rax
0x18005c3fd  mov     rdi, r9
0x18005c400  mov     rbx, r8
0x18005c403  mov     r14, rdx
0x18005c406  mov     rsi, rcx
0x18005c409  mov     [rsp+138h+var_D0], rdx
0x18005c40e  mov     [rsp+138h+var_110], rbx
0x18005c413  mov     [rsp+138h+var_108], r9
0x18005c418  call    ?ResetActivatingContainer@Context@ConnectedStorage@@AEBAXXZ; ConnectedStorage::Context::ResetActivatingContainer(void)
0x18005c41d  mov     rcx, [rdi]
0x18005c420  test    rcx, rcx
0x18005c423  jz      short loc_18005C437
0x18005c425  call    ?CheckCanceled@?$OperationData@UIStorageReadHandler@@UAsyncIStorageReadHandler@@@ConnectedStorage@@QEAA_NXZ; ConnectedStorage::OperationData<IStorageReadHandler,AsyncIStorageReadHandler>::CheckCanceled(void)
0x18005c42a  test    al, al
0x18005c42c  jz      short loc_18005C437
0x18005c42e  mov     rcx, [r14+8]
0x18005c432  jmp     loc_18005C612
0x18005c437  mov     [rsp+138h+var_118], 0
0x18005c43f  xor     r8d, r8d; bool
0x18005c442  mov     rdx, rbx; struct ConnectedStorage::SimpleHStringWrapper *
0x18005c445  mov     rcx, [rsi+130h]; this
0x18005c44c  call    ?GetExistingContainerIndexEntry@ContainerIndex@ConnectedStorage@@QEBAPEAVContainerIndexEntry@2@AEBVSimpleHStringWrapper@2@_N@Z; ConnectedStorage::ContainerIndex::GetExistingContainerIndexEntry(ConnectedStorage::SimpleHStringWrapper const &,bool)
0x18005c451  mov     r15, rax
0x18005c454  test    rax, rax
0x18005c457  jz      loc_18005C5E5
0x18005c45d  cmp     dword ptr [rax+1Ch], 3
0x18005c461  jz      loc_18005C5E5
0x18005c467  xorps   xmm0, xmm0
0x18005c46a  movdqu  xmmword ptr [rsp+138h+var_F0], xmm0
0x18005c470  lea     rdx, [rsi+148h]; struct ConnectedStorage::Mutex *
0x18005c477  lea     rcx, [rsp+138h+lpCriticalSection]; this
0x18005c47c  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18005c481  nop
0x18005c482  lea     rcx, [rsi+108h]
0x18005c489  mov     r8, r15
0x18005c48c  lea     rdx, [rsp+138h+var_E0]
0x18005c491  call    ?GetContainer@Containers@ConnectedStorage@@QEAA?AV?$weak_ptr@VContainer@ConnectedStorage@@@std@@PEAVContainerIndexEntry@2@@Z; ConnectedStorage::Containers::GetContainer(ConnectedStorage::ContainerIndexEntry *)
0x18005c496  mov     rdx, rax
0x18005c499  lea     rcx, [rsp+138h+var_F0]
0x18005c49e  call    ??4?$weak_ptr@VContainer@ConnectedStorage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::weak_ptr<ConnectedStorage::Container>::operator=(std::weak_ptr<ConnectedStorage::Container> &&)
0x18005c4a3  mov     rcx, [rsp+138h+var_D8]; this
0x18005c4a8  test    rcx, rcx
0x18005c4ab  jz      short loc_18005C4B3
0x18005c4ad  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18005c4b2  nop
0x18005c4b3  mov     rcx, [rsp+138h+lpCriticalSection]; lpCriticalSection
0x18005c4b8  call    cs:__imp_LeaveCriticalSection
0x18005c4be  lea     rdx, [rsp+138h+var_E0]
0x18005c4c3  lea     rcx, [rsp+138h+var_F0]
0x18005c4c8  call    ?lock@?$weak_ptr@VUploadingContext@ConnectedStorage@@@std@@QEBA?AV?$shared_ptr@VUploadingContext@ConnectedStorage@@@2@XZ; std::weak_ptr<ConnectedStorage::UploadingContext>::lock(void)
0x18005c4cd  nop
0x18005c4ce  mov     rcx, [rsp+138h+var_E0]; this
0x18005c4d3  test    rcx, rcx
0x18005c4d6  jz      loc_18005C65C
0x18005c4dc  mov     r14, [rcx+0A8h]
0x18005c4e3  call    ?SetDeleted@Container@ConnectedStorage@@QEAAXXZ; ConnectedStorage::Container::SetDeleted(void)
0x18005c4e8  neg     r14
0x18005c4eb  xor     r8d, r8d; __int64
0x18005c4ee  mov     rdx, r14; __int64
0x18005c4f1  mov     rcx, rsi; this
0x18005c4f4  call    ?UpdateBytes@Context@ConnectedStorage@@AEBAX_J0@Z; ConnectedStorage::Context::UpdateBytes(__int64,__int64)
0x18005c4f9  lea     rcx, [rsp+138h+var_C8]
0x18005c4fe  call    ?Create@MultiFileWrite@ConnectedStorage@@SA?AV?$shared_ptr@VMultiFileWrite@ConnectedStorage@@@std@@XZ; ConnectedStorage::MultiFileWrite::Create(void)
0x18005c503  nop
0x18005c504  mov     rcx, [rsi+130h]; this
0x18005c50b  call    ?SetLastModifiedTimeToNow@ContainerIndex@ConnectedStorage@@QEBAXXZ; ConnectedStorage::ContainerIndex::SetLastModifiedTimeToNow(void)
0x18005c510  xorps   xmm0, xmm0
0x18005c513  movdqa  xmmword ptr [rsp+138h+var_B8], xmm0
0x18005c51c  mov     [rsp+138h+var_A0], 0
0x18005c527  mov     [rsp+138h+var_98], 0
0x18005c533  mov     [rsp+138h+var_80], 1388h
0x18005c53e  mov     [rsp+138h+var_7C], 3A98h
0x18005c549  mov     r8, [rdi]
0x18005c54c  test    r8, r8
0x18005c54f  jz      short loc_18005C557
0x18005c551  add     r8, 20h ; ' '
0x18005c555  jmp     short loc_18005C55F
0x18005c557  lea     r8, [rsp+138h+var_B8]; struct ConnectedStorage::CallerInfo *
0x18005c55f  mov     rdx, [rsp+138h+var_C8]; struct ConnectedStorage::MultiFileWrite *
0x18005c564  mov     rcx, [rsi+130h]; this
0x18005c56b  call    ?Save@ContainerIndex@ConnectedStorage@@QEBAXPEAVMultiFileWrite@2@AEBVCallerInfo@2@@Z; ConnectedStorage::ContainerIndex::Save(ConnectedStorage::MultiFileWrite *,ConnectedStorage::CallerInfo const &)
0x18005c570  mov     rcx, [rsp+138h+var_C8]; this
0x18005c575  call    ?Commit@MultiFileWrite@ConnectedStorage@@QEAAXXZ; ConnectedStorage::MultiFileWrite::Commit(void)
0x18005c57a  mov     rax, [rsi]
0x18005c57d  mov     rdx, r15
0x18005c580  mov     rcx, rsi
0x18005c583  mov     rax, [rax+40h]
0x18005c587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c58c  lea     rdx, [rsp+138h+var_F0]
0x18005c591  lea     rcx, [rsp+138h+lpCriticalSection]
0x18005c596  call    ??$?0VContext@ConnectedStorage@@$0A@@?$weak_ptr@VContext@ConnectedStorage@@@std@@QEAA@AEBV?$shared_ptr@VContext@ConnectedStorage@@@1@@Z; std::weak_ptr<ConnectedStorage::Context>::weak_ptr<ConnectedStorage::Context>(std::shared_ptr<ConnectedStorage::Context> const &)
0x18005c59b  mov     rdx, rax
0x18005c59e  mov     rcx, rsi
0x18005c5a1  call    ?ScheduleUploadForDeleteContainer@Context@ConnectedStorage@@AEAAXV?$weak_ptr@VContainer@ConnectedStorage@@@std@@@Z; ConnectedStorage::Context::ScheduleUploadForDeleteContainer(std::weak_ptr<ConnectedStorage::Container>)
0x18005c5a6  nop
0x18005c5a7  lea     rcx, [rsp+138h+var_B8]; this
0x18005c5af  call    ??1CallerInfo@ConnectedStorage@@QEAA@XZ; ConnectedStorage::CallerInfo::~CallerInfo(void)
0x18005c5b4  nop
0x18005c5b5  mov     rcx, [rsp+138h+var_C0]; this
0x18005c5ba  test    rcx, rcx
0x18005c5bd  jz      short loc_18005C5C5
0x18005c5bf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005c5c4  nop
0x18005c5c5  mov     rcx, [rsp+138h+var_D8]; this
0x18005c5ca  test    rcx, rcx
0x18005c5cd  jz      short loc_18005C5D5
0x18005c5cf  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005c5d4  nop
0x18005c5d5  mov     rcx, [rsp+138h+var_F0+8]; this
0x18005c5da  test    rcx, rcx
0x18005c5dd  jz      short loc_18005C5E5
0x18005c5df  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18005c5e4  nop
0x18005c5e5  jmp     short loc_18005C5F1
0x18005c5e7  mov     rbx, [rsp+138h+var_110]
0x18005c5ec  mov     rdi, [rsp+138h+var_108]
0x18005c5f1  mov     rcx, [rdi]
0x18005c5f4  test    rcx, rcx
0x18005c5f7  jz      short loc_18005C609
0x18005c5f9  mov     rax, [rcx]
0x18005c5fc  mov     edx, [rsp+138h+var_118]
0x18005c600  mov     rax, [rax]
0x18005c603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005c608  nop
0x18005c609  mov     rax, [rsp+138h+var_D0]
0x18005c60e  mov     rcx, [rax+8]; this
0x18005c612  test    rcx, rcx
0x18005c615  jz      short loc_18005C61D
0x18005c617  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005c61c  nop
0x18005c61d  mov     rcx, [rbx]; string
0x18005c620  call    cs:__imp_WindowsDeleteString
0x18005c626  mov     qword ptr [rbx], 0
0x18005c62d  mov     rcx, [rdi+8]; this
0x18005c631  test    rcx, rcx
0x18005c634  jz      short loc_18005C63B
0x18005c636  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005c63b  mov     rcx, [rsp+138h+var_38]
0x18005c643  xor     rcx, rsp; StackCookie
0x18005c646  call    __security_check_cookie
0x18005c64b  add     rsp, 110h
0x18005c652  pop     r15
0x18005c654  pop     r14
0x18005c656  pop     rdi
0x18005c657  pop     rsi
0x18005c658  pop     rbx
0x18005c659  retn
0x18005c65a  jmp     short loc_18005C5E7
0x18005c65c  lea     rdx, aDeletecontaine; "DeleteContainer - GetContainer returned"...
0x18005c663  mov     ecx, 8000FFFFh; this
0x18005c668  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
```
