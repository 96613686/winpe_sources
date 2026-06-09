# winrt::event<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>>::add_agile(winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>)

- ea: `0x18002624c`
- end: `0x180026363`
- name: `?add_agile@?$event@U?$TypedEventHandler@UScreenReaderService@Accessibility@UI@Windows@winrt@@UScreenReaderPositionChangedEventArgs@2345@@Foundation@Windows@winrt@@@winrt@@AEAA?AUevent_token@2@U?$TypedEventHandler@UScreenReaderService@Accessibility@UI@Windows@winrt@@UScreenReaderPositionChangedEventArgs@2345@@Foundation@Windows@2@@Z`
- size: `279`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800261b4`
- `0x180028454`

## callees

- `0x180004601`
- `0x18000460d`
- `0x180004619`
- `0x1800072d8`
- `0x180007924`
- `0x180025174`
- `0x1800251d4`
- `0x180025484`
- `0x180025bf4`
- `0x18002624c`
- `0x180026744`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
PVOID *__fastcall winrt::event<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>>::add_agile(
        RTL_SRWLOCK *a1,
        PVOID *a2,
        __int64 *a3)
{
  RTL_SRWLOCK *v6; // r14
  __int64 v7; // rdx
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v11; // [rsp+60h] [rbp+38h] BYREF
  __int64 v12; // [rsp+68h] [rbp+40h] BYREF
  __int64 *v13; // [rsp+70h] [rbp+48h] BYREF
  RTL_SRWLOCK *v14; // [rsp+78h] [rbp+50h]

  v13 = a3;
  *a2 = 0;
  v12 = 0;
  v6 = a1 + 2;
  v14 = a1 + 2;
  WINRT_IMPL_AcquireSRWLockExclusive(a1 + 2);
  v7 = 1;
  if ( a1->Ptr )
    v7 = (unsigned int)(*((_DWORD *)a1->Ptr + 1) + 1);
  winrt::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>(
    &v11,
    v7);
  v8 = v11;
  if ( a1->Ptr )
    std::copy_n<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable> *,unsigned int,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable> *>(
      (char *)a1->Ptr + 8,
      *((unsigned int *)a1->Ptr + 1),
      v11 + 8);
  winrt::Windows::Foundation::IUnknown::operator=(v8 + 8LL * *(unsigned int *)(v8 + 4), a3);
  *a2 = WINRT_IMPL_EncodePointer(*(PVOID *)(v8 + 8LL * *(unsigned int *)(v8 + 4)));
  WINRT_IMPL_AcquireSRWLockExclusive(a1 + 1);
  v9 = std::exchange<winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>,winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>>(
         &v13,
         a1,
         &v11);
  winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>::operator=(
    &v12,
    v9);
  if ( v13 )
    winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(&v13);
  ReleaseSRWLockExclusive_0(a1 + 1);
  if ( v11 )
    winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(&v11);
  ReleaseSRWLockExclusive_0(v6);
  if ( v12 )
    winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(&v12);
  if ( *a3 )
    winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(a3);
  return a2;
}

```

## disassembly

```asm
0x18002624c  mov     [rsp-30h+arg_10], r8
0x180026251  push    rbp
0x180026252  push    rbx
0x180026253  push    rsi
0x180026254  push    rdi
0x180026255  push    r14
0x180026257  push    r15
0x180026259  mov     rbp, rsp
0x18002625c  sub     rsp, 28h
0x180026260  mov     rdi, r8
0x180026263  mov     r15, rdx
0x180026266  mov     rsi, rcx
0x180026269  mov     qword ptr [rdx], 0
0x180026270  mov     [rbp+arg_8], 0
0x180026278  lea     r14, [rcx+10h]
0x18002627c  mov     [rbp+arg_18], r14
0x180026280  mov     rcx, r14; SRWLock
0x180026283  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180026288  nop
0x180026289  mov     rax, [rsi]
0x18002628c  mov     edx, 1
0x180026291  test    rax, rax
0x180026294  jz      short loc_180026299
0x180026296  add     edx, [rax+4]
0x180026299  lea     rcx, [rbp+arg_0]
0x18002629d  call    ??$make_event_array@U?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@YA?AU?$com_ptr@U?$event_array@U?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@1@I@Z; winrt::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>(uint)
0x1800262a2  mov     rdx, [rsi]
0x1800262a5  mov     rbx, [rbp+arg_0]
0x1800262a9  test    rdx, rdx
0x1800262ac  jz      short loc_1800262BE
0x1800262ae  lea     r8, [rbx+8]
0x1800262b2  lea     rcx, [rdx+8]
0x1800262b6  mov     edx, [rdx+4]
0x1800262b9  call    ??$copy_n@PEAU?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@IPEAU1234@@std@@YAPEAU?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@PEAU1234@I0@Z; std::copy_n<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable> *,uint,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable> *>(winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable> *,uint,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable> *)
0x1800262be  mov     eax, [rbx+4]
0x1800262c1  lea     rcx, [rbx+rax*8]
0x1800262c5  mov     rdx, rdi
0x1800262c8  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@$$QEAU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown &&)
0x1800262cd  mov     ecx, [rbx+4]
0x1800262d0  mov     rcx, [rbx+rcx*8]; Ptr
0x1800262d4  call    WINRT_IMPL_EncodePointer
0x1800262d9  mov     [r15], rax
0x1800262dc  lea     rcx, [rsi+8]; SRWLock
0x1800262e0  call    WINRT_IMPL_AcquireSRWLockExclusive
0x1800262e5  lea     r8, [rbp+arg_0]
0x1800262e9  mov     rdx, rsi
0x1800262ec  lea     rcx, [rbp+arg_10]
0x1800262f0  call    ??$exchange@U?$com_ptr@U?$event_array@U?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@U12@@std@@YA?AU?$com_ptr@U?$event_array@U?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@AEAU12@$$QEAU12@@Z; std::exchange<winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>,winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>>(winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>> &,winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>> &&)
0x1800262f5  mov     rdx, rax
0x1800262f8  lea     rcx, [rbp+arg_8]
0x1800262fc  call    ??4?$com_ptr@U?$event_array@U?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>::operator=(winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>> &&)
0x180026301  cmp     [rbp+arg_10], 0
0x180026306  jz      short loc_180026311
0x180026308  lea     rcx, [rbp+arg_10]
0x18002630c  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(void)
0x180026311  lea     rcx, [rsi+8]; SRWLock
0x180026315  call    ReleaseSRWLockExclusive_0
0x18002631a  cmp     [rbp+arg_0], 0
0x18002631f  jz      short loc_18002632B
0x180026321  lea     rcx, [rbp+arg_0]
0x180026325  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(void)
0x18002632a  nop
0x18002632b  mov     rcx, r14; SRWLock
0x18002632e  call    ReleaseSRWLockExclusive_0
0x180026333  nop
0x180026334  cmp     [rbp+arg_8], 0
0x180026339  jz      short loc_180026345
0x18002633b  lea     rcx, [rbp+arg_8]
0x18002633f  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(void)
0x180026344  nop
0x180026345  cmp     qword ptr [rdi], 0
0x180026349  jz      short loc_180026353
0x18002634b  mov     rcx, rdi
0x18002634e  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180026353  mov     rax, r15
0x180026356  add     rsp, 28h
0x18002635a  pop     r15
0x18002635c  pop     r14
0x18002635e  pop     rdi
0x18002635f  pop     rsi
0x180026360  pop     rbx
0x180026361  pop     rbp
0x180026362  retn
```
