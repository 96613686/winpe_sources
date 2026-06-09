# winrt::event<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>>::remove(winrt::event_token)

- ea: `0x18002652c`
- end: `0x1800266bb`
- name: `?remove@?$event@U?$TypedEventHandler@UScreenReaderService@Accessibility@UI@Windows@winrt@@UScreenReaderPositionChangedEventArgs@2345@@Foundation@Windows@winrt@@@winrt@@QEAAXUevent_token@2@@Z`
- size: `399`
- prototype: ``
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180024f50`
- `0x1800266d0`
- `0x180026880`
- `0x180028710`

## callees

- `0x180004601`
- `0x18000460d`
- `0x180004619`
- `0x1800251d4`
- `0x180025484`
- `0x180025bf4`
- `0x180025c38`
- `0x18002652c`
- `0x180026744`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall winrt::event<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>>::remove(
        RTL_SRWLOCK *a1,
        PVOID a2)
{
  __int64 v4; // rsi
  RTL_SRWLOCK *v5; // rdi
  PVOID Ptr; // rcx
  unsigned int v7; // r15d
  __int64 v8; // rbx
  bool v9; // al
  __int64 v10; // rax
  PVOID *v11; // r12
  winrt::Windows::Foundation::IUnknown *v12; // rdi
  __int64 v13; // rax
  _QWORD v14[2]; // [rsp+20h] [rbp-10h] BYREF
  _BOOL8 v15; // [rsp+70h] [rbp+40h] BYREF
  __int64 v16; // [rsp+80h] [rbp+50h] BYREF
  __int64 v17; // [rsp+88h] [rbp+58h] BYREF

  v4 = 0;
  v17 = 0;
  v5 = a1 + 2;
  v14[1] = a1 + 2;
  WINRT_IMPL_AcquireSRWLockExclusive(a1 + 2);
  Ptr = a1->Ptr;
  if ( !a1->Ptr )
  {
    ReleaseSRWLockExclusive_0(v5);
    return;
  }
  v7 = *((_DWORD *)Ptr + 1) - 1;
  v8 = 0;
  v16 = 0;
  if ( !v7 )
  {
    v9 = WINRT_IMPL_EncodePointer(*((PVOID *)Ptr + 1)) == a2;
LABEL_16:
    if ( v9 )
    {
      WINRT_IMPL_AcquireSRWLockExclusive(a1 + 1);
      v13 = std::exchange<winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>,winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>>(
              &v15,
              a1,
              &v16);
      winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>::operator=(
        &v17,
        v13);
      if ( v15 )
        winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(&v15);
      ReleaseSRWLockExclusive_0(a1 + 1);
      v4 = v17;
      v8 = v16;
    }
    goto LABEL_20;
  }
  LOBYTE(v15) = 0;
  v10 = winrt::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>(
          v14,
          v7);
  winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>::operator=(
    &v16,
    v10);
  if ( v14[0] )
    winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(v14);
  v8 = v16;
  v11 = (PVOID *)((char *)a1->Ptr + 8);
  v14[0] = (char *)a1->Ptr + 8 * *((unsigned int *)a1->Ptr + 1) + 8;
  if ( v11 != (PVOID *)v14[0] )
  {
    v9 = v15;
    v12 = (winrt::Windows::Foundation::IUnknown *)(v16 + 8);
    while ( 1 )
    {
      if ( v9 )
        goto LABEL_12;
      if ( a2 != WINRT_IMPL_EncodePointer(*v11) )
        break;
      v9 = 1;
      LOBYTE(v15) = 1;
LABEL_14:
      if ( ++v11 == (PVOID *)v14[0] )
      {
LABEL_15:
        v5 = a1 + 2;
        goto LABEL_16;
      }
    }
    v9 = v15;
LABEL_12:
    if ( !v7 )
      goto LABEL_15;
    winrt::Windows::Foundation::IUnknown::operator=(v12);
    v12 = (winrt::Windows::Foundation::IUnknown *)((char *)v12 + 8);
    --v7;
    v9 = v15;
    goto LABEL_14;
  }
LABEL_20:
  if ( v8 )
    winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(&v16);
  ReleaseSRWLockExclusive_0(v5);
  if ( v4 )
    winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(&v17);
}

```

## disassembly

```asm
0x18002652c  mov     [rsp-38h+arg_8], rbx
0x180026531  push    rbp
0x180026532  push    rsi
0x180026533  push    rdi
0x180026534  push    r12
0x180026536  push    r13
0x180026538  push    r14
0x18002653a  push    r15
0x18002653c  mov     rbp, rsp
0x18002653f  sub     rsp, 30h
0x180026543  mov     r14, rdx
0x180026546  mov     r13, rcx
0x180026549  xor     esi, esi
0x18002654b  mov     [rbp+arg_18], rsi
0x18002654f  lea     rdi, [rcx+10h]
0x180026553  mov     [rbp+var_8], rdi
0x180026557  mov     rcx, rdi; SRWLock
0x18002655a  call    WINRT_IMPL_AcquireSRWLockExclusive
0x18002655f  nop
0x180026560  mov     rcx, [r13+0]
0x180026564  test    rcx, rcx
0x180026567  jz      loc_18002669D
0x18002656d  mov     r15d, [rcx+4]
0x180026571  sub     r15d, 1
0x180026575  mov     ebx, esi
0x180026577  mov     [rbp+arg_10], rbx
0x18002657b  jnz     short loc_180026591
0x18002657d  mov     rcx, [rcx+8]; Ptr
0x180026581  call    WINRT_IMPL_EncodePointer
0x180026586  cmp     rax, r14
0x180026589  setz    al
0x18002658c  jmp     loc_18002662B
0x180026591  mov     byte ptr [rbp+arg_0], 0
0x180026595  mov     edx, r15d
0x180026598  lea     rcx, [rbp+var_10]
0x18002659c  call    ??$make_event_array@U?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@YA?AU?$com_ptr@U?$event_array@U?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@1@I@Z; winrt::impl::make_event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>(uint)
0x1800265a1  mov     rdx, rax
0x1800265a4  lea     rcx, [rbp+arg_10]
0x1800265a8  call    ??4?$com_ptr@U?$event_array@U?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>::operator=(winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>> &&)
0x1800265ad  cmp     [rbp+var_10], 0
0x1800265b2  jz      short loc_1800265BD
0x1800265b4  lea     rcx, [rbp+var_10]
0x1800265b8  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(void)
0x1800265bd  mov     rbx, [rbp+arg_10]
0x1800265c1  mov     rcx, [r13+0]
0x1800265c5  lea     r12, [rcx+8]
0x1800265c9  mov     eax, [rcx+4]
0x1800265cc  inc     rax
0x1800265cf  lea     rax, [rcx+rax*8]
0x1800265d3  mov     [rbp+var_10], rax
0x1800265d7  cmp     r12, rax
0x1800265da  jz      loc_180026675
0x1800265e0  mov     al, byte ptr [rbp+arg_0]
0x1800265e3  lea     rdi, [rbx+8]
0x1800265e7  test    al, al
0x1800265e9  jnz     short loc_180026603
0x1800265eb  mov     rcx, [r12]; Ptr
0x1800265ef  call    WINRT_IMPL_EncodePointer
0x1800265f4  cmp     r14, rax
0x1800265f7  jnz     short loc_180026600
0x1800265f9  mov     al, 1
0x1800265fb  mov     byte ptr [rbp+arg_0], al
0x1800265fe  jmp     short loc_18002661D
0x180026600  mov     al, byte ptr [rbp+arg_0]
0x180026603  test    r15d, r15d
0x180026606  jz      short loc_180026627
0x180026608  mov     rdx, r12
0x18002660b  mov     rcx, rdi; this
0x18002660e  call    ??4IUnknown@Foundation@Windows@winrt@@QEAAAEAU0123@AEBU0123@@Z; winrt::Windows::Foundation::IUnknown::operator=(winrt::Windows::Foundation::IUnknown const &)
0x180026613  add     rdi, 8
0x180026617  dec     r15d
0x18002661a  mov     al, byte ptr [rbp+arg_0]
0x18002661d  add     r12, 8
0x180026621  cmp     r12, [rbp+var_10]
0x180026625  jnz     short loc_1800265E7
0x180026627  lea     rdi, [r13+10h]
0x18002662b  test    al, al
0x18002662d  jz      short loc_180026675
0x18002662f  lea     rcx, [r13+8]; SRWLock
0x180026633  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180026638  lea     r8, [rbp+arg_10]
0x18002663c  mov     rdx, r13
0x18002663f  lea     rcx, [rbp+arg_0]
0x180026643  call    ??$exchange@U?$com_ptr@U?$event_array@U?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@U12@@std@@YA?AU?$com_ptr@U?$event_array@U?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@AEAU12@$$QEAU12@@Z; std::exchange<winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>,winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>>(winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>> &,winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>> &&)
0x180026648  mov     rdx, rax
0x18002664b  lea     rcx, [rbp+arg_18]
0x18002664f  call    ??4?$com_ptr@U?$event_array@U?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@QEAAAEAU01@$$QEAU01@@Z; winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>::operator=(winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>> &&)
0x180026654  cmp     [rbp+arg_0], 0
0x180026659  jz      short loc_180026664
0x18002665b  lea     rcx, [rbp+arg_0]
0x18002665f  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(void)
0x180026664  lea     rcx, [r13+8]; SRWLock
0x180026668  call    ReleaseSRWLockExclusive_0
0x18002666d  mov     rsi, [rbp+arg_18]
0x180026671  mov     rbx, [rbp+arg_10]
0x180026675  test    rbx, rbx
0x180026678  jz      short loc_180026684
0x18002667a  lea     rcx, [rbp+arg_10]
0x18002667e  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(void)
0x180026683  nop
0x180026684  mov     rcx, rdi; SRWLock
0x180026687  call    ReleaseSRWLockExclusive_0
0x18002668c  nop
0x18002668d  test    rsi, rsi
0x180026690  jz      short loc_1800266A6
0x180026692  lea     rcx, [rbp+arg_18]
0x180026696  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(void)
0x18002669b  jmp     short loc_1800266A6
0x18002669d  mov     rcx, rdi; SRWLock
0x1800266a0  call    ReleaseSRWLockExclusive_0
0x1800266a5  nop
0x1800266a6  mov     rbx, [rsp+30h+arg_8]
0x1800266ab  add     rsp, 30h
0x1800266af  pop     r15
0x1800266b1  pop     r14
0x1800266b3  pop     r13
0x1800266b5  pop     r12
0x1800266b7  pop     rdi
0x1800266b8  pop     rsi
0x1800266b9  pop     rbp
0x1800266ba  retn
```
