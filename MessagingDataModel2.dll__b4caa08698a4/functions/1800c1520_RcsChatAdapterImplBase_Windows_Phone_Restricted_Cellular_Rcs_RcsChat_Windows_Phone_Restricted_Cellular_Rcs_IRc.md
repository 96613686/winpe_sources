# RcsChatAdapterImplBase<Windows::Phone::Restricted::Cellular::Rcs::RcsChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsChat>::~RcsChatAdapterImplBase<Windows::Phone::Restricted::Cellular::Rcs::RcsChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsChat>(void)

- ea: `0x1800c1520`
- end: `0x1800c160e`
- name: `??1?$RcsChatAdapterImplBase@VRcsChat@Rcs@Cellular@Restricted@Phone@Windows@@UIRcsChat@23456@@@UEAA@XZ`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800c1aa0`

## callees

- `0x180004c58`
- `0x180008870`
- `0x180030bd0`
- `0x1800595d4`
- `0x1800c1520`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c1559`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c15dc`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c1559`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c15dc`

## pseudocode

```c
void **__fastcall RcsChatAdapterImplBase<Windows::Phone::Restricted::Cellular::Rcs::RcsChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsChat>::~RcsChatAdapterImplBase<Windows::Phone::Restricted::Cellular::Rcs::RcsChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsChat>(
        __int64 a1)
{
  __int64 **v2; // rsi
  __int64 *v3; // rdi
  __int64 *v4; // rdx
  __int64 v5; // rax
  utl::_RefCountBase *v6; // rcx
  __int64 v7; // rcx
  void **result; // rax

  *(_QWORD *)a1 = &RcsChatAdapterImplBase<Windows::Phone::Restricted::Cellular::Rcs::RcsChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsChat>::`vftable'{for `RcsChatAdapter'};
  *(_QWORD *)(a1 + 8) = &RcsChatAdapterImpl::`vftable'{for `RcsEventNotification<RcsRemoteContactComposingNotificationArgs>'};
  *(_QWORD *)(a1 + 16) = &RcsChatAdapterImplBase<Windows::Phone::Restricted::Cellular::Rcs::RcsChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsChat>::`vftable'{for `RcsEventNotification<RcsChatMultipartMessageFileTransferProgressUpdateNotificationArgs>'};
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 168));
  v2 = (__int64 **)(a1 + 144);
  while ( 1 )
  {
    v3 = *v2;
    if ( *v2 == (__int64 *)v2 )
      break;
    v4 = (__int64 *)v3[1];
    v5 = *v3;
    *v4 = *v3;
    *(_QWORD *)(v5 + 8) = v4;
    v6 = (utl::_RefCountBase *)v3[3];
    if ( v6 )
      utl::_RefCountBase::_DecStrong(v6);
    operator delete(v3, (const struct std::nothrow_t *)&std::nothrow);
  }
  *(_QWORD *)(a1 + 160) = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 136);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 128);
  v7 = *(_QWORD *)(a1 + 104);
  if ( v7 )
  {
    *(_QWORD *)(a1 + 104) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(a1 + 32);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 24);
  result = &RcsChatAdapter::`vftable';
  *(_QWORD *)a1 = &RcsChatAdapter::`vftable';
  return result;
}

```

## disassembly

```asm
0x1800c1520  mov     [rsp+arg_0], rbx
0x1800c1525  mov     [rsp+arg_8], rsi
0x1800c152a  push    rdi
0x1800c152b  sub     rsp, 20h
0x1800c152f  lea     rax, ??_7?$RcsChatAdapterImplBase@VRcsChat@Rcs@Cellular@Restricted@Phone@Windows@@UIRcsChat@23456@@@6BRcsChatAdapter@@@; const RcsChatAdapterImplBase<Windows::Phone::Restricted::Cellular::Rcs::RcsChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsChat>::`vftable'{for `RcsChatAdapter'}
0x1800c1536  mov     rbx, rcx
0x1800c1539  mov     [rcx], rax
0x1800c153c  lea     rax, ??_7RcsChatAdapterImpl@@6B?$RcsEventNotification@URcsRemoteContactComposingNotificationArgs@@@@@; const RcsChatAdapterImpl::`vftable'{for `RcsEventNotification<RcsRemoteContactComposingNotificationArgs>'}
0x1800c1543  mov     [rcx+8], rax
0x1800c1547  lea     rax, ??_7?$RcsChatAdapterImplBase@VRcsChat@Rcs@Cellular@Restricted@Phone@Windows@@UIRcsChat@23456@@@6B?$RcsEventNotification@URcsChatMultipartMessageFileTransferProgressUpdateNotificationArgs@@@@@; const RcsChatAdapterImplBase<Windows::Phone::Restricted::Cellular::Rcs::RcsChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsChat>::`vftable'{for `RcsEventNotification<RcsChatMultipartMessageFileTransferProgressUpdateNotificationArgs>'}
0x1800c154e  mov     [rcx+10h], rax
0x1800c1552  add     rcx, 0A8h; lpCriticalSection
0x1800c1559  call    cs:__imp_DeleteCriticalSection
0x1800c155f  lea     rsi, [rbx+90h]
0x1800c1566  mov     rdi, [rsi]
0x1800c1569  cmp     rdi, rsi
0x1800c156c  jz      short loc_1800C159B
0x1800c156e  mov     rdx, [rdi+8]
0x1800c1572  mov     rax, [rdi]
0x1800c1575  mov     [rdx], rax
0x1800c1578  mov     [rax+8], rdx
0x1800c157c  mov     rcx, [rdi+18h]; this
0x1800c1580  test    rcx, rcx
0x1800c1583  jz      short loc_1800C158A
0x1800c1585  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800c158a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800c1591  mov     rcx, rdi; void *
0x1800c1594  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c1599  jmp     short loc_1800C1566
0x1800c159b  lea     rcx, [rbx+88h]
0x1800c15a2  mov     qword ptr [rsi+10h], 0
0x1800c15aa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c15af  lea     rcx, [rbx+80h]
0x1800c15b6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c15bb  mov     rcx, [rbx+68h]
0x1800c15bf  test    rcx, rcx
0x1800c15c2  jz      short loc_1800C15D8
0x1800c15c4  mov     qword ptr [rbx+68h], 0
0x1800c15cc  mov     rax, [rcx]
0x1800c15cf  mov     rax, [rax+10h]
0x1800c15d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c15d8  lea     rcx, [rbx+40h]; lpCriticalSection
0x1800c15dc  call    cs:__imp_DeleteCriticalSection
0x1800c15e2  lea     rcx, [rbx+20h]
0x1800c15e6  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800c15eb  lea     rcx, [rbx+18h]
0x1800c15ef  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c15f4  mov     rsi, [rsp+28h+arg_8]
0x1800c15f9  lea     rax, ??_7RcsChatAdapter@@6B@; const RcsChatAdapter::`vftable'
0x1800c1600  mov     [rbx], rax
0x1800c1603  mov     rbx, [rsp+28h+arg_0]
0x1800c1608  add     rsp, 20h
0x1800c160c  pop     rdi
0x1800c160d  retn
```
