# winrt::event<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>>::operator()<winrt::Windows::UI::Accessibility::implementation::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>(winrt::Windows::UI::Accessibility::implementation::ScreenReaderService const &,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs const &)

- ea: `0x180024f50`
- end: `0x180024ff2`
- name: `??$?RUScreenReaderService@implementation@Accessibility@UI@Windows@winrt@@UScreenReaderPositionChangedEventArgs@2345@@?$event@U?$TypedEventHandler@UScreenReaderService@Accessibility@UI@Windows@winrt@@UScreenReaderPositionChangedEventArgs@2345@@Foundation@Windows@winrt@@@winrt@@QEAAXAEBUScreenReaderService@implementation@Accessibility@UI@Windows@1@AEBUScreenReaderPositionChangedEventArgs@4561@@Z`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180025c7c`

## callees

- `0x180004601`
- `0x18000460d`
- `0x180004619`
- `0x180024f50`
- `0x180025278`
- `0x18002652c`
- `0x180026744`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall winrt::event<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>>::operator()<winrt::Windows::UI::Accessibility::implementation::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>(
        RTL_SRWLOCK *a1,
        __int64 a2,
        __int64 a3)
{
  PVOID v6; // rbx
  unsigned int *Ptr; // rax
  unsigned int *v8; // rdi
  unsigned int *v9; // rsi
  PVOID v10; // rax
  unsigned int *v11; // [rsp+60h] [rbp+8h] BYREF

  v6 = 0;
  v11 = 0;
  WINRT_IMPL_AcquireSRWLockExclusive(a1 + 1);
  Ptr = (unsigned int *)a1->Ptr;
  v8 = 0;
  if ( a1->Ptr )
  {
    v6 = a1->Ptr;
    v11 = (unsigned int *)a1->Ptr;
    _InterlockedIncrement((volatile signed __int32 *)Ptr);
    v8 = Ptr;
  }
  ReleaseSRWLockExclusive_0(a1 + 1);
  if ( v8 )
  {
    v9 = &v8[2 * v8[1] + 2];
    while ( 1 )
    {
      v8 += 2;
      if ( v8 == v9 )
        break;
      if ( !(unsigned __int8)winrt::impl::invoke<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>,winrt::Windows::UI::Accessibility::implementation::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>(
                               v8,
                               a2,
                               a3) )
      {
        v10 = WINRT_IMPL_EncodePointer(*(PVOID *)v8);
        winrt::event<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>>::remove(
          a1,
          v10);
      }
    }
  }
  if ( v6 )
    winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(&v11);
}

```

## disassembly

```asm
0x180024f50  push    rbx
0x180024f52  push    rbp
0x180024f53  push    rsi
0x180024f54  push    rdi
0x180024f55  push    r14
0x180024f57  push    r15
0x180024f59  sub     rsp, 28h
0x180024f5d  mov     rbp, r8
0x180024f60  mov     r15, rdx
0x180024f63  mov     r14, rcx
0x180024f66  xor     ebx, ebx
0x180024f68  mov     [rsp+58h+arg_0], rbx
0x180024f6d  add     rcx, 8; SRWLock
0x180024f71  call    WINRT_IMPL_AcquireSRWLockExclusive
0x180024f76  mov     rax, [r14]
0x180024f79  xor     edi, edi
0x180024f7b  test    rax, rax
0x180024f7e  jz      short loc_180024F8E
0x180024f80  mov     rbx, rax
0x180024f83  mov     [rsp+58h+arg_0], rax
0x180024f88  lock inc dword ptr [rax]
0x180024f8b  mov     rdi, rax
0x180024f8e  lea     rcx, [r14+8]; SRWLock
0x180024f92  call    ReleaseSRWLockExclusive_0
0x180024f97  test    rdi, rdi
0x180024f9a  jz      short loc_180024FD6
0x180024f9c  mov     esi, [rdi+4]
0x180024f9f  inc     rsi
0x180024fa2  lea     rsi, [rdi+rsi*8]
0x180024fa6  jmp     short loc_180024FCD
0x180024fa8  mov     r8, rbp
0x180024fab  mov     rdx, r15
0x180024fae  mov     rcx, rdi
0x180024fb1  call    ??$invoke@U?$TypedEventHandler@UScreenReaderService@Accessibility@UI@Windows@winrt@@UScreenReaderPositionChangedEventArgs@2345@@Foundation@Windows@winrt@@UScreenReaderService@implementation@Accessibility@UI@34@UScreenReaderPositionChangedEventArgs@7834@@impl@winrt@@YA_NAEBU?$TypedEventHandler@UScreenReaderService@Accessibility@UI@Windows@winrt@@UScreenReaderPositionChangedEventArgs@2345@@Foundation@Windows@1@AEBUScreenReaderService@implementation@Accessibility@UI@41@AEBUScreenReaderPositionChangedEventArgs@7841@@Z; winrt::impl::invoke<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>,winrt::Windows::UI::Accessibility::implementation::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>(winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs> const &,winrt::Windows::UI::Accessibility::implementation::ScreenReaderService const &,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs const &)
0x180024fb6  test    al, al
0x180024fb8  jnz     short loc_180024FCD
0x180024fba  mov     rcx, [rdi]; Ptr
0x180024fbd  call    WINRT_IMPL_EncodePointer
0x180024fc2  mov     rdx, rax
0x180024fc5  mov     rcx, r14
0x180024fc8  call    ?remove@?$event@U?$TypedEventHandler@UScreenReaderService@Accessibility@UI@Windows@winrt@@UScreenReaderPositionChangedEventArgs@2345@@Foundation@Windows@winrt@@@winrt@@QEAAXUevent_token@2@@Z; winrt::event<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs>>::remove(winrt::event_token)
0x180024fcd  add     rdi, 8
0x180024fd1  cmp     rdi, rsi
0x180024fd4  jnz     short loc_180024FA8
0x180024fd6  test    rbx, rbx
0x180024fd9  jz      short loc_180024FE5
0x180024fdb  lea     rcx, [rsp+58h+arg_0]
0x180024fe0  call    ?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(void)
0x180024fe5  add     rsp, 28h
0x180024fe9  pop     r15
0x180024feb  pop     r14
0x180024fed  pop     rdi
0x180024fee  pop     rsi
0x180024fef  pop     rbp
0x180024ff0  pop     rbx
0x180024ff1  retn
```
