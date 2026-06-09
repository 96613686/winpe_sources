# Windows::Networking::UX::Internal::WlanInterface::GetPendingNotificationProfileName(HSTRING__ * *)

- ea: `0x18003f6c8`
- end: `0x18003f7b5`
- name: `?GetPendingNotificationProfileName@WlanInterface@Internal@UX@Networking@Windows@@QEAAJPEAPEAUHSTRING__@@@Z`
- size: `237`
- prototype: `int(Windows::Networking::UX::Internal::WlanInterface *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180026bb0`

## callees

- `0x18000de4c`
- `0x18001d4d4`
- `0x18001d8f4`
- `0x18003f6c8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003f76b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003f76b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f709`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f73d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f7a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f709`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f73d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003f7a3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Networking::UX::Internal::WlanInterface::GetPendingNotificationProfileName(
        Windows::Networking::UX::Internal::WlanInterface *this,
        HSTRING *a2)
{
  Windows::Networking::UX::Internal::WiFiSenseClient *v4; // rcx
  HRESULT NotificationTargetProfile; // ebx
  Windows::Networking::UX::Internal::WiFiSenseClient *v6; // rcx
  HSTRING string; // [rsp+50h] [rbp+8h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids);
  WindowsDeleteString(0);
  string = 0;
  NotificationTargetProfile = Windows::Networking::UX::Internal::WiFiSenseClient::GetNotificationTargetProfile(
                                v4,
                                (struct _GUID *)((char *)this + 1204),
                                &string);
  if ( NotificationTargetProfile >= 0
    || *((_BYTE *)this + 1186)
    && (WindowsDeleteString(string),
        string = 0,
        NotificationTargetProfile = Windows::Networking::UX::Internal::WiFiSenseClient::GetNotificationTargetProfile(
                                      v6,
                                      (struct _GUID *)((char *)this + 1188),
                                      &string),
        NotificationTargetProfile >= 0) )
  {
    NotificationTargetProfile = WindowsDuplicateString(string, a2);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      100,
      &WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids,
      (unsigned int)NotificationTargetProfile);
  WindowsDeleteString(string);
  return (unsigned int)NotificationTargetProfile;
}

```

## disassembly

```asm
0x18003f6c8  push    rbx
0x18003f6ca  push    rsi
0x18003f6cb  push    rdi
0x18003f6cc  push    r14
0x18003f6ce  sub     rsp, 28h
0x18003f6d2  mov     rsi, rdx
0x18003f6d5  mov     rdi, rcx
0x18003f6d8  lea     r14, WPP_GLOBAL_Control
0x18003f6df  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f6e6  cmp     rcx, r14
0x18003f6e9  jz      short loc_18003F707
0x18003f6eb  test    byte ptr [rcx+1Ch], 8
0x18003f6ef  jz      short loc_18003F707
0x18003f6f1  mov     edx, 63h ; 'c'
0x18003f6f6  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18003f6fd  mov     rcx, [rcx+10h]
0x18003f701  call    WPP_SF_
0x18003f706  nop
0x18003f707  xor     ecx, ecx; string
0x18003f709  call    cs:__imp_WindowsDeleteString
0x18003f70f  mov     [rsp+48h+string], 0
0x18003f718  lea     rdx, [rdi+4B4h]; struct _GUID *
0x18003f71f  lea     r8, [rsp+48h+string]; HSTRING *
0x18003f724  call    ?GetNotificationTargetProfile@WiFiSenseClient@Internal@UX@Networking@Windows@@QEAAJPEAU_GUID@@PEAPEAUHSTRING__@@@Z; Windows::Networking::UX::Internal::WiFiSenseClient::GetNotificationTargetProfile(_GUID *,HSTRING__ * *)
0x18003f729  mov     ebx, eax
0x18003f72b  test    eax, eax
0x18003f72d  jns     short loc_18003F763
0x18003f72f  cmp     byte ptr [rdi+4A2h], 0
0x18003f736  jz      short loc_18003F773
0x18003f738  mov     rcx, [rsp+48h+string]; string
0x18003f73d  call    cs:__imp_WindowsDeleteString
0x18003f743  mov     [rsp+48h+string], 0
0x18003f74c  lea     rdx, [rdi+4A4h]; struct _GUID *
0x18003f753  lea     r8, [rsp+48h+string]; HSTRING *
0x18003f758  call    ?GetNotificationTargetProfile@WiFiSenseClient@Internal@UX@Networking@Windows@@QEAAJPEAU_GUID@@PEAPEAUHSTRING__@@@Z; Windows::Networking::UX::Internal::WiFiSenseClient::GetNotificationTargetProfile(_GUID *,HSTRING__ * *)
0x18003f75d  mov     ebx, eax
0x18003f75f  test    eax, eax
0x18003f761  js      short loc_18003F773
0x18003f763  mov     rdx, rsi; newString
0x18003f766  mov     rcx, [rsp+48h+string]; string
0x18003f76b  call    cs:__imp_WindowsDuplicateString
0x18003f771  mov     ebx, eax
0x18003f773  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f77a  cmp     rcx, r14
0x18003f77d  jz      short loc_18003F79E
0x18003f77f  test    byte ptr [rcx+1Ch], 8
0x18003f783  jz      short loc_18003F79E
0x18003f785  mov     edx, 64h ; 'd'
0x18003f78a  mov     r9d, ebx
0x18003f78d  lea     r8, WPP_1d38a1f9e6943a38c061f6c5b3807675_Traceguids
0x18003f794  mov     rcx, [rcx+10h]
0x18003f798  call    WPP_SF_d
0x18003f79d  nop
0x18003f79e  mov     rcx, [rsp+48h+string]; string
0x18003f7a3  call    cs:__imp_WindowsDeleteString
0x18003f7a9  mov     eax, ebx
0x18003f7ab  add     rsp, 28h
0x18003f7af  pop     r14
0x18003f7b1  pop     rdi
0x18003f7b2  pop     rsi
0x18003f7b3  pop     rbx
0x18003f7b4  retn
```
