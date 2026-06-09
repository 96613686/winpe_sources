# RcsChatAdapterImplBase<Windows::Phone::Restricted::Cellular::Rcs::RcsGroupChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsGroupChat>::~RcsChatAdapterImplBase<Windows::Phone::Restricted::Cellular::Rcs::RcsGroupChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsGroupChat>(void)

- ea: `0x1800c1614`
- end: `0x1800c1702`
- name: `??1?$RcsChatAdapterImplBase@VRcsGroupChat@Rcs@Cellular@Restricted@Phone@Windows@@UIRcsGroupChat@23456@@@UEAA@XZ`
- size: `238`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800c1ae0`

## callees

- `0x180004c58`
- `0x180008870`
- `0x180030bd0`
- `0x1800595d4`
- `0x1800c1614`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c164d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c16d0`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c164d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800c16d0`

## pseudocode

```c
void **__fastcall RcsChatAdapterImplBase<Windows::Phone::Restricted::Cellular::Rcs::RcsGroupChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsGroupChat>::~RcsChatAdapterImplBase<Windows::Phone::Restricted::Cellular::Rcs::RcsGroupChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsGroupChat>(
        __int64 a1)
{
  __int64 **v2; // rsi
  __int64 *v3; // rdi
  __int64 *v4; // rdx
  __int64 v5; // rax
  utl::_RefCountBase *v6; // rcx
  __int64 v7; // rcx
  void **result; // rax

  *(_QWORD *)a1 = &RcsChatAdapterImplBase<Windows::Phone::Restricted::Cellular::Rcs::RcsGroupChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsGroupChat>::`vftable'{for `RcsChatAdapter'};
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
0x1800c1614  mov     [rsp+arg_0], rbx
0x1800c1619  mov     [rsp+arg_8], rsi
0x1800c161e  push    rdi
0x1800c161f  sub     rsp, 20h
0x1800c1623  lea     rax, ??_7?$RcsChatAdapterImplBase@VRcsGroupChat@Rcs@Cellular@Restricted@Phone@Windows@@UIRcsGroupChat@23456@@@6BRcsChatAdapter@@@; const RcsChatAdapterImplBase<Windows::Phone::Restricted::Cellular::Rcs::RcsGroupChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsGroupChat>::`vftable'{for `RcsChatAdapter'}
0x1800c162a  mov     rbx, rcx
0x1800c162d  mov     [rcx], rax
0x1800c1630  lea     rax, ??_7RcsChatAdapterImpl@@6B?$RcsEventNotification@URcsRemoteContactComposingNotificationArgs@@@@@; const RcsChatAdapterImpl::`vftable'{for `RcsEventNotification<RcsRemoteContactComposingNotificationArgs>'}
0x1800c1637  mov     [rcx+8], rax
0x1800c163b  lea     rax, ??_7?$RcsChatAdapterImplBase@VRcsChat@Rcs@Cellular@Restricted@Phone@Windows@@UIRcsChat@23456@@@6B?$RcsEventNotification@URcsChatMultipartMessageFileTransferProgressUpdateNotificationArgs@@@@@; const RcsChatAdapterImplBase<Windows::Phone::Restricted::Cellular::Rcs::RcsChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsChat>::`vftable'{for `RcsEventNotification<RcsChatMultipartMessageFileTransferProgressUpdateNotificationArgs>'}
0x1800c1642  mov     [rcx+10h], rax
0x1800c1646  add     rcx, 0A8h; lpCriticalSection
0x1800c164d  call    cs:__imp_DeleteCriticalSection
0x1800c1653  lea     rsi, [rbx+90h]
0x1800c165a  mov     rdi, [rsi]
0x1800c165d  cmp     rdi, rsi
0x1800c1660  jz      short loc_1800C168F
0x1800c1662  mov     rdx, [rdi+8]
0x1800c1666  mov     rax, [rdi]
0x1800c1669  mov     [rdx], rax
0x1800c166c  mov     [rax+8], rdx
0x1800c1670  mov     rcx, [rdi+18h]; this
0x1800c1674  test    rcx, rcx
0x1800c1677  jz      short loc_1800C167E
0x1800c1679  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800c167e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800c1685  mov     rcx, rdi; void *
0x1800c1688  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c168d  jmp     short loc_1800C165A
0x1800c168f  lea     rcx, [rbx+88h]
0x1800c1696  mov     qword ptr [rsi+10h], 0
0x1800c169e  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c16a3  lea     rcx, [rbx+80h]
0x1800c16aa  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c16af  mov     rcx, [rbx+68h]
0x1800c16b3  test    rcx, rcx
0x1800c16b6  jz      short loc_1800C16CC
0x1800c16b8  mov     qword ptr [rbx+68h], 0
0x1800c16c0  mov     rax, [rcx]
0x1800c16c3  mov     rax, [rax+10h]
0x1800c16c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c16cc  lea     rcx, [rbx+40h]; lpCriticalSection
0x1800c16d0  call    cs:__imp_DeleteCriticalSection
0x1800c16d6  lea     rcx, [rbx+20h]
0x1800c16da  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x1800c16df  lea     rcx, [rbx+18h]
0x1800c16e3  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800c16e8  mov     rsi, [rsp+28h+arg_8]
0x1800c16ed  lea     rax, ??_7RcsChatAdapter@@6B@; const RcsChatAdapter::`vftable'
0x1800c16f4  mov     [rbx], rax
0x1800c16f7  mov     rbx, [rsp+28h+arg_0]
0x1800c16fc  add     rsp, 20h
0x1800c1700  pop     rdi
0x1800c1701  retn
```
