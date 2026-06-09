# ConnectedStorage::Context::ReadContainerImpl(std::shared_ptr<ConnectedStorage::ContextOperationToken>,ConnectedStorage::SimpleHStringWrapper,std::shared_ptr<ConnectedStorage::ReadData>)

- ea: `0x18005df14`
- end: `0x18005e0de`
- name: `?ReadContainerImpl@Context@ConnectedStorage@@AEAAXV?$shared_ptr@VContextOperationToken@ConnectedStorage@@@std@@VSimpleHStringWrapper@2@V?$shared_ptr@UReadData@ConnectedStorage@@@4@@Z`
- size: `458`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18005b714`
- `0x18005e0e4`

## callees

- `0x180003c70`
- `0x18000aae4`
- `0x18000cb9c`
- `0x180010f28`
- `0x1800190f0`
- `0x180019128`
- `0x18001c8f0`
- `0x18002a1dc`
- `0x18005bdec`
- `0x18005df14`
- `0x18005e420`
- `0x1800644ec`
- `0x180073498`
- `0x180076524`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005dff0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005dff0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e080`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005e080`

## string_xrefs

- `0x18005e0ba`: `Context::ReadContainerImpl - no container found`
- `0x18005e0cb`: `ReadContainer - GetContainer returned a container that's already been removed`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall ConnectedStorage::Context::ReadContainerImpl(
        __int64 a1,
        _QWORD *a2,
        const struct ConnectedStorage::SimpleHStringWrapper *a3,
        _QWORD *a4)
{
  _QWORD *v4; // rdi
  const struct ConnectedStorage::SimpleHStringWrapper *v5; // rbx
  _QWORD *v6; // rsi
  unsigned __int16 *v8; // r8
  struct ConnectedStorage::ContainerIndexEntry *ExistingContainerIndexEntry; // r15
  __int64 Container; // rax
  __int64 v11; // rax
  const unsigned __int16 *v12; // r8
  ConnectedStorage::Container *v13; // r9
  std::_Ref_count_base *v14; // rcx
  std::_Ref_count_base *v15; // rcx
  int v16; // [rsp+20h] [rbp-D8h] BYREF
  std::_Ref_count_base *v17; // [rsp+28h] [rbp-D0h]
  _QWORD *v18; // [rsp+30h] [rbp-C8h]
  _QWORD *v19; // [rsp+38h] [rbp-C0h]
  const struct ConnectedStorage::SimpleHStringWrapper *v20; // [rsp+40h] [rbp-B8h]
  std::_Ref_count_base *v21[2]; // [rsp+48h] [rbp-B0h] BYREF
  __int64 v22; // [rsp+58h] [rbp-A0h] BYREF
  std::_Ref_count_base *v23; // [rsp+60h] [rbp-98h]
  LPCRITICAL_SECTION lpCriticalSection[3]; // [rsp+68h] [rbp-90h] BYREF
  _DWORD v25[16]; // [rsp+80h] [rbp-78h] BYREF

  v4 = a4;
  v5 = a3;
  v6 = a2;
  v19 = a2;
  v20 = a3;
  v18 = a4;
  ConnectedStorage::Context::ResetActivatingContainer((ConnectedStorage::Context *)a1);
  if ( (unsigned __int8)ConnectedStorage::OperationData<IStorageReadHandler,AsyncIStorageReadHandler>::CheckCanceled(*v4) )
    goto LABEL_16;
  try
  {
    *(_OWORD *)v21 = 0;
    ExistingContainerIndexEntry = ConnectedStorage::ContainerIndex::GetExistingContainerIndexEntry(
                                    *(ConnectedStorage::ContainerIndex **)(a1 + 304),
                                    v5,
                                    0);
    if ( !ExistingContainerIndexEntry )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)0x80830008LL,
        (int)L"Context::ReadContainerImpl - no container found",
        v8);
    ConnectedStorage::Mutex::Lock::Lock(
      (ConnectedStorage::Mutex::Lock *)lpCriticalSection,
      (struct _RTL_CRITICAL_SECTION *)(a1 + 328),
      (char *)v8);
    Container = ConnectedStorage::Containers::GetContainer(a1 + 264, &v22, ExistingContainerIndexEntry);
    v11 = std::weak_ptr<ConnectedStorage::UploadingContext>::lock(Container, &v16);
    std::shared_ptr<ConnectedStorage::ActivatingContainer const>::operator=(v21, v11);
    if ( v17 )
      std::_Ref_count_base::_Decref(v17);
    if ( v23 )
      std::_Ref_count_base::_Decwref(v23);
    LeaveCriticalSection(lpCriticalSection[0]);
    if ( !v21[0] )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)0x8000FFFFLL,
        (int)L"ReadContainer - GetContainer returned a container that's already been removed",
        v12);
    std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(lpCriticalSection, v4);
    std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(&v22, v6);
    ConnectedStorage::Container::Read(v13);
  }
  catch ( ConnectedStorage::ComError v25 )
  {
    v16 = v25[6];
    ConnectedStorage::ComError::~ComError((ConnectedStorage::ComError *)v25);
    if ( v16 < 0 )
    {
LABEL_12:
      v4 = v18;
      (**(void (__fastcall ***)(_QWORD, _QWORD))*v18)(*v18, (unsigned int)v16);
    }
    else
    {
      v4 = v18;
    }
    v5 = v20;
    v6 = v19;
  }
  catch ( std::bad_alloc )
  {
    v16 = -2147024882;
    goto LABEL_12;
  }
  catch ( ... )
  {
    v16 = -2147467259;
    goto LABEL_12;
  }
  if ( v21[1] )
    std::_Ref_count_base::_Decref(v21[1]);
LABEL_16:
  v14 = (std::_Ref_count_base *)v6[1];
  if ( v14 )
    std::_Ref_count_base::_Decref(v14);
  WindowsDeleteString(*(HSTRING *)v5);
  *(_QWORD *)v5 = 0;
  v15 = (std::_Ref_count_base *)v4[1];
  if ( v15 )
    std::_Ref_count_base::_Decref(v15);
}

```

## disassembly

```asm
0x18005df14  push    rbx
0x18005df16  push    rsi
0x18005df17  push    rdi
0x18005df18  push    r14
0x18005df1a  push    r15
0x18005df1c  sub     rsp, 0D0h
0x18005df23  mov     rax, cs:__security_cookie
0x18005df2a  xor     rax, rsp
0x18005df2d  mov     [rsp+0F8h+var_38], rax
0x18005df35  mov     rdi, r9
0x18005df38  mov     rbx, r8
0x18005df3b  mov     rsi, rdx
0x18005df3e  mov     r14, rcx
0x18005df41  mov     [rsp+0F8h+var_C0], rdx
0x18005df46  mov     [rsp+0F8h+var_B8], rbx
0x18005df4b  mov     [rsp+0F8h+var_C8], r9
0x18005df50  call    ?ResetActivatingContainer@Context@ConnectedStorage@@AEBAXXZ; ConnectedStorage::Context::ResetActivatingContainer(void)
0x18005df55  mov     rcx, [rdi]
0x18005df58  call    ?CheckCanceled@?$OperationData@UIStorageReadHandler@@UAsyncIStorageReadHandler@@@ConnectedStorage@@QEAA_NXZ; ConnectedStorage::OperationData<IStorageReadHandler,AsyncIStorageReadHandler>::CheckCanceled(void)
0x18005df5d  test    al, al
0x18005df5f  jnz     loc_18005E06E
0x18005df65  xorps   xmm0, xmm0
0x18005df68  movdqu  xmmword ptr [rsp+0F8h+var_B0], xmm0
0x18005df6e  xor     r8d, r8d; bool
0x18005df71  mov     rdx, rbx; struct ConnectedStorage::SimpleHStringWrapper *
0x18005df74  mov     rcx, [r14+130h]; this
0x18005df7b  call    ?GetExistingContainerIndexEntry@ContainerIndex@ConnectedStorage@@QEBAPEAVContainerIndexEntry@2@AEBVSimpleHStringWrapper@2@_N@Z; ConnectedStorage::ContainerIndex::GetExistingContainerIndexEntry(ConnectedStorage::SimpleHStringWrapper const &,bool)
0x18005df80  mov     r15, rax
0x18005df83  test    rax, rax
0x18005df86  jz      loc_18005E0BA
0x18005df8c  lea     rdx, [r14+148h]; struct ConnectedStorage::Mutex *
0x18005df93  lea     rcx, [rsp+0F8h+lpCriticalSection]; this
0x18005df98  call    ??0Lock@Mutex@ConnectedStorage@@QEAA@AEAV12@PEAD@Z; ConnectedStorage::Mutex::Lock::Lock(ConnectedStorage::Mutex &,char *)
0x18005df9d  nop
0x18005df9e  lea     rcx, [r14+108h]
0x18005dfa5  mov     r8, r15
0x18005dfa8  lea     rdx, [rsp+0F8h+var_A0]
0x18005dfad  call    ?GetContainer@Containers@ConnectedStorage@@QEAA?AV?$weak_ptr@VContainer@ConnectedStorage@@@std@@PEAVContainerIndexEntry@2@@Z; ConnectedStorage::Containers::GetContainer(ConnectedStorage::ContainerIndexEntry *)
0x18005dfb2  lea     rdx, [rsp+0F8h+var_D8]
0x18005dfb7  mov     rcx, rax
0x18005dfba  call    ?lock@?$weak_ptr@VUploadingContext@ConnectedStorage@@@std@@QEBA?AV?$shared_ptr@VUploadingContext@ConnectedStorage@@@2@XZ; std::weak_ptr<ConnectedStorage::UploadingContext>::lock(void)
0x18005dfbf  mov     rdx, rax
0x18005dfc2  lea     rcx, [rsp+0F8h+var_B0]
0x18005dfc7  call    ??4?$shared_ptr@$$CBVActivatingContainer@ConnectedStorage@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<ConnectedStorage::ActivatingContainer const>::operator=(std::shared_ptr<ConnectedStorage::ActivatingContainer const> &&)
0x18005dfcc  mov     rcx, [rsp+0F8h+var_D0]; this
0x18005dfd1  test    rcx, rcx
0x18005dfd4  jz      short loc_18005DFDB
0x18005dfd6  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005dfdb  mov     rcx, [rsp+0F8h+var_98]; this
0x18005dfe0  test    rcx, rcx
0x18005dfe3  jz      short loc_18005DFEB
0x18005dfe5  call    ?_Decwref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decwref(void)
0x18005dfea  nop
0x18005dfeb  mov     rcx, [rsp+0F8h+lpCriticalSection]; lpCriticalSection
0x18005dff0  call    cs:__imp_LeaveCriticalSection
0x18005dff6  mov     r9, [rsp+0F8h+var_B0]
0x18005dffb  test    r9, r9
0x18005dffe  jz      loc_18005E0CB
0x18005e004  mov     rdx, rdi
0x18005e007  lea     rcx, [rsp+0F8h+lpCriticalSection]
0x18005e00c  call    ??0?$shared_ptr@UGetQuotaData@ConnectedStorage@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(std::shared_ptr<ConnectedStorage::GetQuotaData> const &)
0x18005e011  mov     r8, rax
0x18005e014  mov     rdx, rsi
0x18005e017  lea     rcx, [rsp+0F8h+var_A0]
0x18005e01c  call    ??0?$shared_ptr@UGetQuotaData@ConnectedStorage@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<ConnectedStorage::GetQuotaData>::shared_ptr<ConnectedStorage::GetQuotaData>(std::shared_ptr<ConnectedStorage::GetQuotaData> const &)
0x18005e021  mov     rdx, rax
0x18005e024  mov     rcx, r9; this
0x18005e027  call    ?Read@Container@ConnectedStorage@@QEAAXV?$shared_ptr@VContextOperationToken@ConnectedStorage@@@std@@V?$shared_ptr@UReadData@ConnectedStorage@@@4@@Z; ConnectedStorage::Container::Read(std::shared_ptr<ConnectedStorage::ContextOperationToken>,std::shared_ptr<ConnectedStorage::ReadData>)
0x18005e02c  nop
0x18005e02d  jmp     short loc_18005E05E
0x18005e02f  cmp     [rsp+0F8h+var_D8], 0
0x18005e034  jl      short loc_18005E03D
0x18005e036  mov     rdi, [rsp+0F8h+var_C8]
0x18005e03b  jmp     short loc_18005E054
0x18005e03d  mov     rdi, [rsp+0F8h+var_C8]
0x18005e042  mov     rcx, [rdi]
0x18005e045  mov     rax, [rcx]
0x18005e048  mov     edx, [rsp+0F8h+var_D8]
0x18005e04c  mov     rax, [rax]
0x18005e04f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e054  mov     rbx, [rsp+0F8h+var_B8]
0x18005e059  mov     rsi, [rsp+0F8h+var_C0]
0x18005e05e  mov     rcx, [rsp+0F8h+var_B0+8]; this
0x18005e063  test    rcx, rcx
0x18005e066  jz      short loc_18005E06E
0x18005e068  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005e06d  nop
0x18005e06e  mov     rcx, [rsi+8]; this
0x18005e072  test    rcx, rcx
0x18005e075  jz      short loc_18005E07D
0x18005e077  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005e07c  nop
0x18005e07d  mov     rcx, [rbx]; string
0x18005e080  call    cs:__imp_WindowsDeleteString
0x18005e086  mov     qword ptr [rbx], 0
0x18005e08d  mov     rcx, [rdi+8]; this
0x18005e091  test    rcx, rcx
0x18005e094  jz      short loc_18005E09B
0x18005e096  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18005e09b  mov     rcx, [rsp+0F8h+var_38]
0x18005e0a3  xor     rcx, rsp; StackCookie
0x18005e0a6  call    __security_check_cookie
0x18005e0ab  add     rsp, 0D0h
0x18005e0b2  pop     r15
0x18005e0b4  pop     r14
0x18005e0b6  pop     rdi
0x18005e0b7  pop     rsi
0x18005e0b8  pop     rbx
0x18005e0b9  retn
0x18005e0ba  lea     rdx, aContextReadcon; "Context::ReadContainerImpl - no contain"...
0x18005e0c1  mov     ecx, 80830008h; this
0x18005e0c6  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18005e0cb  lea     rdx, aReadcontainerG; "ReadContainer - GetContainer returned a"...
0x18005e0d2  mov     ecx, 8000FFFFh; this
0x18005e0d7  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
```
