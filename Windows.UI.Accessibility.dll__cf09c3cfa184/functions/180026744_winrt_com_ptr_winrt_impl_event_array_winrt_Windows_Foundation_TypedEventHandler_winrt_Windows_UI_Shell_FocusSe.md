# winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(void)

- ea: `0x180026744`
- end: `0x180026781`
- name: `?unconditional_release_ref@?$com_ptr@U?$event_array@U?$TypedEventHandler@UFocusSessionManager@Shell@UI@Windows@winrt@@UIInspectable@Foundation@45@@Foundation@Windows@winrt@@@impl@winrt@@@winrt@@AEAAXXZ`
- size: `61`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x180024f50`
- `0x180025b50`
- `0x180025bb0`
- `0x180025bf4`
- `0x18002624c`
- `0x18002652c`
- `0x180026880`
- `0x1800276b8`

## callees

- `0x180003f50`
- `0x180005cd4`
- `0x180025134`
- `0x180026744`

## pseudocode

```c
void __fastcall winrt::com_ptr<winrt::impl::event_array<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Shell::FocusSessionManager,winrt::Windows::Foundation::IInspectable>>>::unconditional_release_ref(
        unsigned int **a1)
{
  unsigned int *v1; // rbx

  v1 = *a1;
  *a1 = 0;
  if ( !(unsigned int)winrt::impl::atomic_ref_count::operator--(v1) )
  {
    std::_Destroy_range<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs> *,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs> *>(
      v1 + 2,
      &v1[2 * v1[1] + 2]);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x180026744  push    rbx
0x180026746  sub     rsp, 20h
0x18002674a  mov     rbx, [rcx]
0x18002674d  mov     qword ptr [rcx], 0
0x180026754  mov     rcx, rbx
0x180026757  call    ??Fatomic_ref_count@impl@winrt@@QEAAIXZ; winrt::impl::atomic_ref_count::operator--(void)
0x18002675c  test    eax, eax
0x18002675e  jnz     short loc_18002677B
0x180026760  mov     eax, [rbx+4]
0x180026763  lea     rcx, [rbx+8]
0x180026767  inc     rax
0x18002676a  lea     rdx, [rbx+rax*8]
0x18002676e  call    ??$_Destroy_range@PEAU?$TypedEventHandler@UScreenReaderService@Accessibility@UI@Windows@winrt@@UScreenReaderPositionChangedEventArgs@2345@@Foundation@Windows@winrt@@PEAU1234@@std@@YAXPEAU?$TypedEventHandler@UScreenReaderService@Accessibility@UI@Windows@winrt@@UScreenReaderPositionChangedEventArgs@2345@@Foundation@Windows@winrt@@QEAU1234@@Z; std::_Destroy_range<winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs> *,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs> *>(winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs> *,winrt::Windows::Foundation::TypedEventHandler<winrt::Windows::UI::Accessibility::ScreenReaderService,winrt::Windows::UI::Accessibility::ScreenReaderPositionChangedEventArgs> * const)
0x180026773  mov     rcx, rbx; Block
0x180026776  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002677b  add     rsp, 20h
0x18002677f  pop     rbx
0x180026780  retn
```
