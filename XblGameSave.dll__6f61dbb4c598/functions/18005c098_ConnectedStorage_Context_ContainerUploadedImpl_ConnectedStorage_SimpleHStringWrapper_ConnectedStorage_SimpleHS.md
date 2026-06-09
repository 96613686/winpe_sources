# ConnectedStorage::Context::ContainerUploadedImpl(ConnectedStorage::SimpleHStringWrapper,ConnectedStorage::SimpleHStringWrapper,bool)

- ea: `0x18005c098`
- end: `0x18005c2e6`
- name: `?ContainerUploadedImpl@Context@ConnectedStorage@@AEAAXVSimpleHStringWrapper@2@0_N@Z`
- size: `590`
- prototype: `void __high(struct ConnectedStorage::SimpleHStringWrapper, struct ConnectedStorage::SimpleHStringWrapper, bool)`
- caller_count: `1`
- callee_count: `22`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800602b0`

## callees

- `0x180003c70`
- `0x18000aae4`
- `0x18000ab18`
- `0x18000cb9c`
- `0x18000d2f4`
- `0x180010f88`
- `0x180012278`
- `0x1800124b0`
- `0x180012ff8`
- `0x18001c8f0`
- `0x180033ab8`
- `0x18005b280`
- `0x18005c098`
- `0x18005c9bc`
- `0x1800644ec`
- `0x180065924`
- `0x18006b6f8`
- `0x18006b8f8`
- `0x180073498`
- `0x1800760cc`
- `0x18007681c`
- `0x180076f34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005c154`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005c154`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c2a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c2b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c2a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005c2b1`

## string_xrefs

- `0x18005c178`: `ContainerUploadedImpl - GetContainer returned a container that's already been removed`
- `0x18005c208`: `ContainerUploadedImpl failed - failing all updates`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
HRESULT __fastcall ConnectedStorage::Context::ContainerUploadedImpl(
        ConnectedStorage::ContainerIndex **a1,
        const struct ConnectedStorage::SimpleHStringWrapper *a2,
        const struct ConnectedStorage::SimpleHStringWrapper *a3,
        bool a4)
{
  const struct ConnectedStorage::SimpleHStringWrapper *v5; // rdi
  HSTRING *v6; // rsi
  ConnectedStorage::Context *v7; // rbx
  ConnectedStorage::ContainerIndex **v8; // r12
  const unsigned __int16 *v9; // r8
  struct ConnectedStorage::ContainerIndexEntry *ExistingContainerIndexEntry; // r15
  char *v11; // r8
  __int64 Container; // rax
  const unsigned __int16 *v13; // r8
  bool v14; // r9
  ConnectedStorage::ContainerIndex *v15; // rax
  ConnectedStorage::Container *v16; // r14
  const unsigned __int16 *v17; // r8
  ConnectedStorage::Container *v18; // rax
  ConnectedStorage::MultiFileWrite *v19; // rax
  HRESULT result; // eax
  int v21; // [rsp+30h] [rbp-D8h]
  LPCRITICAL_SECTION lpCriticalSection[2]; // [rsp+38h] [rbp-D0h] BYREF
  ConnectedStorage::Context *v23[2]; // [rsp+48h] [rbp-C0h] BYREF
  struct ConnectedStorage::MultiFileWrite *v24[2]; // [rsp+58h] [rbp-B0h] BYREF
  HSTRING *v25; // [rsp+68h] [rbp-A0h]
  const struct ConnectedStorage::SimpleHStringWrapper *v26; // [rsp+70h] [rbp-98h]
  _BYTE v27[24]; // [rsp+78h] [rbp-90h] BYREF
  _DWORD v28[16]; // [rsp+90h] [rbp-78h] BYREF

  v5 = a3;
  v6 = (HSTRING *)a2;
  v7 = (ConnectedStorage::Context *)a1;
  v23[0] = (ConnectedStorage::Context *)a1;
  v25 = (HSTRING *)a2;
  v26 = a3;
  v8 = a1 + 38;
  ExistingContainerIndexEntry = ConnectedStorage::ContainerIndex::GetExistingContainerIndexEntry(a1[38], a2, 1);
  if ( !ExistingContainerIndexEntry )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)0x8000FFFFLL,
      (int)L"ContainerUploadedImpl - Entry no longer exists.",
      v9);
  std::weak_ptr<ConnectedStorage::AtomManager>::weak_ptr<ConnectedStorage::AtomManager>(v27);
  ConnectedStorage::Mutex::Lock::Lock(
    (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
    (struct _RTL_CRITICAL_SECTION *)((char *)v7 + 328),
    v11);
  Container = ConnectedStorage::Containers::GetContainer((char *)v7 + 264, v24, ExistingContainerIndexEntry);
  std::weak_ptr<ConnectedStorage::Container>::operator=(v27, Container);
  std::weak_ptr<ConnectedStorage::ActivatingContainer>::~weak_ptr<ConnectedStorage::ActivatingContainer>(v24);
  LeaveCriticalSection(lpCriticalSection[0]);
  std::weak_ptr<ConnectedStorage::UploadingContext>::lock(v27, lpCriticalSection);
  if ( !(unsigned __int8)std::shared_ptr<ConnectedStorage::WebService>::operator bool(lpCriticalSection) )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)0x8000FFFFLL,
      (int)L"ContainerUploadedImpl - GetContainer returned a container that's already been removed",
      v13);
  ConnectedStorage::MultiFileWrite::Create(v24);
  try
  {
    v14 = a4;
    v16 = (ConnectedStorage::Container *)lpCriticalSection[0];
    ConnectedStorage::Container::UpdateAfterUpload((ConnectedStorage::Container *)lpCriticalSection[0], v24[0], v5, v14);
    v15 = (ConnectedStorage::ContainerIndex *)std::shared_ptr<ConnectedStorage::UploadingContext const>::operator-><ConnectedStorage::UploadingContext const,0>(v8);
    ConnectedStorage::ContainerIndex::SaveAfterContainerUpdate(v15, v24[0], 0, (__int64)ExistingContainerIndexEntry);
  }
  catch ( ConnectedStorage::ComError v28 )
  {
    v21 = v28[6];
    ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v28);
    if ( v21 >= 0 )
    {
      v16 = (ConnectedStorage::Container *)lpCriticalSection[0];
      v7 = v23[0];
      v6 = v25;
      v5 = v26;
      goto LABEL_8;
    }
LABEL_9:
    v7 = v23[0];
    ConnectedStorage::Context::EnterErrorMode(v23[0]);
    ConnectedStorage::ReportErrorNoThrow(
      (ConnectedStorage *)(unsigned int)v21,
      (int)L"ContainerUploadedImpl failed - failing all updates",
      v17);
    v18 = (ConnectedStorage::Container *)std::shared_ptr<ConnectedStorage::UploadingContext const>::operator-><ConnectedStorage::UploadingContext const,0>(lpCriticalSection);
    ConnectedStorage::Container::RollbackUpdate(v18);
    v19 = (ConnectedStorage::MultiFileWrite *)std::shared_ptr<ConnectedStorage::UploadingContext const>::operator-><ConnectedStorage::UploadingContext const,0>(v24);
    ConnectedStorage::MultiFileWrite::Abandon(v19);
    v6 = v25;
    v5 = v26;
LABEL_10:
    std::weak_ptr<ConnectedStorage::UploadingContext>::lock((char *)v7 + 64, v23);
    if ( (unsigned __int8)std::shared_ptr<ConnectedStorage::WebService>::operator bool(v23) )
      ConnectedStorage::Contexts::OnContextWorkComplete(v23[0], (ConnectedStorage::Context *)((char *)v7 + 88));
    std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>(v23);
    std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>(v24);
    std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>(lpCriticalSection);
    std::weak_ptr<ConnectedStorage::ActivatingContainer>::~weak_ptr<ConnectedStorage::ActivatingContainer>(v27);
    WindowsDeleteString(*v6);
    *v6 = 0;
    result = WindowsDeleteString(*(HSTRING *)v5);
    *(_QWORD *)v5 = 0;
  }
  catch ( std::bad_alloc )
  {
    v21 = -2147024882;
    goto LABEL_9;
  }
  catch ( ... )
  {
    v21 = -2147467259;
    goto LABEL_9;
  }
LABEL_8:
  ConnectedStorage::Container::CommitUpdate(v16);
  goto LABEL_10;
}

```

## disassembly

```asm
0x18005c098  mov     [rsp+arg_18], rbx
0x18005c09d  push    rsi
0x18005c09e  push    rdi
0x18005c09f  push    r12
0x18005c0a1  push    r14
0x18005c0a3  push    r15
0x18005c0a5  sub     rsp, 0E0h
0x18005c0ac  mov     rax, cs:__security_cookie
0x18005c0b3  xor     rax, rsp
0x18005c0b6  mov     [rsp+108h+var_38], rax
0x18005c0be  mov     r14b, r9b
0x18005c0c1  mov     rdi, r8
0x18005c0c4  mov     rsi, rdx
0x18005c0c7  mov     rbx, rcx
0x18005c0ca  mov     [rsp+108h+var_C0], rcx
0x18005c0cf  mov     [rsp+108h+var_A0], rdx
0x18005c0d4  mov     [rsp+108h+var_98], r8
0x18005c0d9  lea     r12, [rcx+130h]
0x18005c0e0  mov     r8b, 1; bool
0x18005c0e3  mov     rcx, [r12]; this
0x18005c0e7  call    ?GetExistingContainerIndexEntry@ContainerIndex@ConnectedStorage@@QEBAPEAVContainerIndexEntry@2@AEBVSimpleHStringWrapper@2@_N@Z; ConnectedStorage::ContainerIndex::GetExistingContainerIndexEntry(ConnectedStorage::SimpleHStringWrapper const &,bool)
0x18005c0ec  mov     r15, rax
0x18005c0ef  test    rax, rax
0x18005c0f2  jnz     short loc_18005C106
0x18005c0f4  lea     rdx, aContaineruploa; "ContainerUploadedImpl - Entry no longer"...
0x18005c0fb  mov     ecx, 8000FFFFh; this
0x18005c100  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18005c106  lea     rcx, [rsp+108h+var_90]
0x18005c10b  call    ??0?$weak_ptr@VAtomManager@ConnectedStorage@@@std@@QEAA@XZ; std::weak_ptr<ConnectedStorage::AtomManager>::weak_ptr<ConnectedStorage::AtomManager>(void)
0x18005c110  nop
0x18005c111  lea     rdx, [rbx+148h]; struct ConnectedStorage::Mutex *
0x18005c118  lea     rcx, [rsp+108h+lpCriticalSection]; this
0x18005c11d  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18005c122  nop
0x18005c123  lea     rcx, [rbx+108h]
0x18005c12a  mov     r8, r15
0x18005c12d  lea     rdx, [rsp+108h+var_B0]
0x18005c132  call    ?GetContainer@Containers@ConnectedStorage@@QEAA?AV?$weak_ptr@VContainer@ConnectedStorage@@@std@@PEAVContainerIndexEntry@2@@Z; ConnectedStorage::Containers::GetContainer(ConnectedStorage::ContainerIndexEntry *)
0x18005c137  mov     rdx, rax
0x18005c13a  lea     rcx, [rsp+108h+var_90]
0x18005c13f  call    ??4?$weak_ptr@VContainer@ConnectedStorage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::weak_ptr<ConnectedStorage::Container>::operator=(std::weak_ptr<ConnectedStorage::Container> &&)
0x18005c144  lea     rcx, [rsp+108h+var_B0]
0x18005c149  call    ??1?$weak_ptr@VActivatingContainer@ConnectedStorage@@@std@@QEAA@XZ; std::weak_ptr<ConnectedStorage::ActivatingContainer>::~weak_ptr<ConnectedStorage::ActivatingContainer>(void)
0x18005c14e  nop
0x18005c14f  mov     rcx, [rsp+108h+lpCriticalSection]; lpCriticalSection
0x18005c154  call    cs:__imp_LeaveCriticalSection
0x18005c15a  lea     rdx, [rsp+108h+lpCriticalSection]
0x18005c15f  lea     rcx, [rsp+108h+var_90]
0x18005c164  call    ?lock@?$weak_ptr@VUploadingContext@ConnectedStorage@@@std@@QEBA?AV?$shared_ptr@VUploadingContext@ConnectedStorage@@@2@XZ; std::weak_ptr<ConnectedStorage::UploadingContext>::lock(void)
0x18005c169  nop
0x18005c16a  lea     rcx, [rsp+108h+lpCriticalSection]
0x18005c16f  call    ??B?$shared_ptr@VWebService@ConnectedStorage@@@std@@QEBA_NXZ; std::shared_ptr<ConnectedStorage::WebService>::operator bool(void)
0x18005c174  test    al, al
0x18005c176  jnz     short loc_18005C18A
0x18005c178  lea     rdx, aContaineruploa_1; "ContainerUploadedImpl - GetContainer re"...
0x18005c17f  mov     ecx, 8000FFFFh; this
0x18005c184  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18005c18a  lea     rcx, [rsp+108h+var_B0]
0x18005c18f  call    ?Create@MultiFileWrite@ConnectedStorage@@SA?AV?$shared_ptr@VMultiFileWrite@ConnectedStorage@@@std@@XZ; ConnectedStorage::MultiFileWrite::Create(void)
0x18005c194  nop
0x18005c195  mov     r9b, r14b; bool
0x18005c198  mov     r8, rdi; struct ConnectedStorage::SimpleHStringWrapper *
0x18005c19b  mov     rdx, [rsp+108h+var_B0]; struct ConnectedStorage::MultiFileWrite *
0x18005c1a0  mov     r14, [rsp+108h+lpCriticalSection]
0x18005c1a5  mov     rcx, r14; this
0x18005c1a8  call    ?UpdateAfterUpload@Container@ConnectedStorage@@QEAAXPEAVMultiFileWrite@2@AEBVSimpleHStringWrapper@2@_N@Z; ConnectedStorage::Container::UpdateAfterUpload(ConnectedStorage::MultiFileWrite *,ConnectedStorage::SimpleHStringWrapper const &,bool)
0x18005c1ad  mov     rcx, r12
0x18005c1b0  call    ??$?C$$CBVUploadingContext@ConnectedStorage@@$0A@@?$shared_ptr@$$CBVUploadingContext@ConnectedStorage@@@std@@QEBAPEBVUploadingContext@ConnectedStorage@@XZ; std::shared_ptr<ConnectedStorage::UploadingContext const>::operator-><ConnectedStorage::UploadingContext const,0>(void)
0x18005c1b5  lea     r9, [rbx+0E8h]
0x18005c1bc  mov     [rsp+108h+var_E8], r15; __int64
0x18005c1c1  xor     r8d, r8d; struct ConnectedStorage::CallerInfo *
0x18005c1c4  mov     rdx, [rsp+108h+var_B0]; ConnectedStorage::MultiFileWrite *
0x18005c1c9  mov     rcx, rax; this
0x18005c1cc  call    ?SaveAfterContainerUpdate@ContainerIndex@ConnectedStorage@@QEBAXPEAVMultiFileWrite@2@PEBVCallerInfo@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBVContainerIndexEntry@2@@Z; ConnectedStorage::ContainerIndex::SaveAfterContainerUpdate(ConnectedStorage::MultiFileWrite *,ConnectedStorage::CallerInfo const *,std::wstring const &,ConnectedStorage::ContainerIndexEntry const *)
0x18005c1d1  nop
0x18005c1d2  jmp     short loc_18005C1EF
0x18005c1d4  cmp     dword ptr [rsp+108h+var_D8], 0
0x18005c1d9  jl      short loc_18005C1FB
0x18005c1db  mov     r14, [rsp+108h+lpCriticalSection]
0x18005c1e0  mov     rbx, [rsp+108h+var_C0]
0x18005c1e5  mov     rsi, [rsp+108h+var_A0]
0x18005c1ea  mov     rdi, [rsp+108h+var_98]
0x18005c1ef  mov     rcx, r14; this
0x18005c1f2  call    ?CommitUpdate@Container@ConnectedStorage@@QEAAXXZ; ConnectedStorage::Container::CommitUpdate(void)
0x18005c1f7  jmp     short loc_18005C246
0x18005c1f9  jmp     short $+2
0x18005c1fb  mov     rbx, [rsp+108h+var_C0]
0x18005c200  mov     rcx, rbx; this
0x18005c203  call    ?EnterErrorMode@Context@ConnectedStorage@@AEAAXXZ; ConnectedStorage::Context::EnterErrorMode(void)
0x18005c208  lea     rdx, aContaineruploa_0; "ContainerUploadedImpl failed - failing "...
0x18005c20f  mov     ecx, dword ptr [rsp+108h+var_D8]; this
0x18005c213  call    ?ReportErrorNoThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorNoThrow(long,ushort const *)
0x18005c218  lea     rcx, [rsp+108h+lpCriticalSection]
0x18005c21d  call    ??$?C$$CBVUploadingContext@ConnectedStorage@@$0A@@?$shared_ptr@$$CBVUploadingContext@ConnectedStorage@@@std@@QEBAPEBVUploadingContext@ConnectedStorage@@XZ; std::shared_ptr<ConnectedStorage::UploadingContext const>::operator-><ConnectedStorage::UploadingContext const,0>(void)
0x18005c222  mov     rcx, rax; this
0x18005c225  call    ?RollbackUpdate@Container@ConnectedStorage@@QEAAXXZ; ConnectedStorage::Container::RollbackUpdate(void)
0x18005c22a  lea     rcx, [rsp+108h+var_B0]
0x18005c22f  call    ??$?C$$CBVUploadingContext@ConnectedStorage@@$0A@@?$shared_ptr@$$CBVUploadingContext@ConnectedStorage@@@std@@QEBAPEBVUploadingContext@ConnectedStorage@@XZ; std::shared_ptr<ConnectedStorage::UploadingContext const>::operator-><ConnectedStorage::UploadingContext const,0>(void)
0x18005c234  mov     rcx, rax; this
0x18005c237  call    ?Abandon@MultiFileWrite@ConnectedStorage@@QEAAXXZ; ConnectedStorage::MultiFileWrite::Abandon(void)
0x18005c23c  mov     rsi, [rsp+108h+var_A0]
0x18005c241  mov     rdi, [rsp+108h+var_98]
0x18005c246  lea     rcx, [rbx+40h]
0x18005c24a  lea     rdx, [rsp+108h+var_C0]
0x18005c24f  call    ?lock@?$weak_ptr@VUploadingContext@ConnectedStorage@@@std@@QEBA?AV?$shared_ptr@VUploadingContext@ConnectedStorage@@@2@XZ; std::weak_ptr<ConnectedStorage::UploadingContext>::lock(void)
0x18005c254  nop
0x18005c255  lea     rcx, [rsp+108h+var_C0]
0x18005c25a  call    ??B?$shared_ptr@VWebService@ConnectedStorage@@@std@@QEBA_NXZ; std::shared_ptr<ConnectedStorage::WebService>::operator bool(void)
0x18005c25f  test    al, al
0x18005c261  jz      short loc_18005C272
0x18005c263  lea     rdx, [rbx+58h]; struct ConnectedStorage::ContextDesc *
0x18005c267  mov     rcx, [rsp+108h+var_C0]; this
0x18005c26c  call    ?OnContextWorkComplete@Contexts@ConnectedStorage@@QEBAXAEBVContextDesc@2@@Z; ConnectedStorage::Contexts::OnContextWorkComplete(ConnectedStorage::ContextDesc const &)
0x18005c271  nop
0x18005c272  lea     rcx, [rsp+108h+var_C0]
0x18005c277  call    ??1?$shared_ptr@V?$vector@VContainerQueryInfoWrapper@ConnectedStorage@@V?$allocator@VContainerQueryInfoWrapper@ConnectedStorage@@@std@@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>(void)
0x18005c27c  nop
0x18005c27d  lea     rcx, [rsp+108h+var_B0]
0x18005c282  call    ??1?$shared_ptr@V?$vector@VContainerQueryInfoWrapper@ConnectedStorage@@V?$allocator@VContainerQueryInfoWrapper@ConnectedStorage@@@std@@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>(void)
0x18005c287  nop
0x18005c288  lea     rcx, [rsp+108h+lpCriticalSection]
0x18005c28d  call    ??1?$shared_ptr@V?$vector@VContainerQueryInfoWrapper@ConnectedStorage@@V?$allocator@VContainerQueryInfoWrapper@ConnectedStorage@@@std@@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>::~shared_ptr<std::vector<ConnectedStorage::ContainerQueryInfoWrapper>>(void)
0x18005c292  nop
0x18005c293  lea     rcx, [rsp+108h+var_90]
0x18005c298  call    ??1?$weak_ptr@VActivatingContainer@ConnectedStorage@@@std@@QEAA@XZ; std::weak_ptr<ConnectedStorage::ActivatingContainer>::~weak_ptr<ConnectedStorage::ActivatingContainer>(void)
0x18005c29d  nop
0x18005c29e  mov     rcx, [rsi]; string
0x18005c2a1  call    cs:__imp_WindowsDeleteString
0x18005c2a7  mov     qword ptr [rsi], 0
0x18005c2ae  mov     rcx, [rdi]; string
0x18005c2b1  call    cs:__imp_WindowsDeleteString
0x18005c2b7  mov     qword ptr [rdi], 0
0x18005c2be  mov     rcx, [rsp+108h+var_38]
0x18005c2c6  xor     rcx, rsp; StackCookie
0x18005c2c9  call    __security_check_cookie
0x18005c2ce  mov     rbx, [rsp+108h+arg_18]
0x18005c2d6  add     rsp, 0E0h
0x18005c2dd  pop     r15
0x18005c2df  pop     r14
0x18005c2e1  pop     r12
0x18005c2e3  pop     rdi
0x18005c2e4  pop     rsi
0x18005c2e5  retn
```
