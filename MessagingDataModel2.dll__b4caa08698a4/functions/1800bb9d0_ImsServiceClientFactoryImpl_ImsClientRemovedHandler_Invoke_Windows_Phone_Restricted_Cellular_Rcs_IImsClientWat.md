# ImsServiceClientFactoryImpl::ImsClientRemovedHandler::Invoke(Windows::Phone::Restricted::Cellular::Rcs::IImsClientWatcher *,Windows::Phone::Restricted::Cellular::Rcs::IImsClientWatcherEventArgs *)

- ea: `0x1800bb9d0`
- end: `0x1800bbc41`
- name: `?Invoke@ImsClientRemovedHandler@ImsServiceClientFactoryImpl@@UEAAJPEAUIImsClientWatcher@Rcs@Cellular@Restricted@Phone@Windows@@PEAUIImsClientWatcherEventArgs@45678@@Z`
- size: `625`
- prototype: `__int64 __fastcall(ImsServiceClientFactoryImpl::ImsClientRemovedHandler *__hidden this, struct Windows::Phone::Restricted::Cellular::Rcs::IImsClientWatcher *, struct Windows::Phone::Restricted::Cellular::Rcs::IImsClientWatcherEventArgs *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000bae4`
- `0x18002cf18`
- `0x1800bb0fc`
- `0x1800bb9d0`
- `0x1800bbc88`
- `0x1800bc610`
- `0x1800c6902`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bbb39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bbb39`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bba46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bba84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bbbf2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bba46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bba84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bbbf2`

## string_xrefs

- `0x1800bba2e`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\imsserviceclientfactory.cpp`
- `0x1800bbafd`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\imsserviceclientfactory.cpp`

## pseudocode

```c
__int64 __fastcall ImsServiceClientFactoryImpl::ImsClientRemovedHandler::Invoke(
        ImsServiceClientFactoryImpl::ImsClientRemovedHandler *this,
        struct Windows::Phone::Restricted::Cellular::Rcs::IImsClientWatcher *a2,
        struct Windows::Phone::Restricted::Cellular::Rcs::IImsClientWatcherEventArgs *a3)
{
  __int64 v3; // rax
  HRESULT v5; // ebx
  __int64 v6; // r9
  __int64 v7; // rcx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  __int64 v11; // r9
  __int64 v12; // rcx
  const wchar_t *StringRawBuffer; // rax
  __int64 v14; // rcx
  __int64 v15; // rcx
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v17; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v19; // [rsp+48h] [rbp-B8h]
  __int128 v20; // [rsp+58h] [rbp-A8h]
  __int128 v21; // [rsp+68h] [rbp-98h]
  __int128 v22; // [rsp+78h] [rbp-88h]
  __int128 v23; // [rsp+88h] [rbp-78h]
  __int128 v24; // [rsp+98h] [rbp-68h]
  __int128 v25; // [rsp+A8h] [rbp-58h]
  __int128 v26; // [rsp+B8h] [rbp-48h]
  __int128 v27; // [rsp+C8h] [rbp-38h]
  __int64 v28; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v29; // [rsp+E8h] [rbp-18h] BYREF
  wchar_t pszDest[8]; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v31; // [rsp+108h] [rbp+8h]
  __int128 v32; // [rsp+118h] [rbp+18h]
  __int128 v33; // [rsp+128h] [rbp+28h]
  __int128 v34; // [rsp+138h] [rbp+38h]
  __int128 v35; // [rsp+148h] [rbp+48h]
  __int128 v36; // [rsp+158h] [rbp+58h]
  __int128 v37; // [rsp+168h] [rbp+68h]

  v3 = *(_QWORD *)a3;
  v17 = 0;
  string = 0;
  v5 = (*(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IImsClientWatcherEventArgs *, __int64 *))(v3 + 48))(
         a3,
         &v17);
  if ( v5 < 0 )
  {
    v6 = 175;
LABEL_3:
    Log_HREvent_102(
      (unsigned int)v5,
      1,
      "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\imsserviceclientfactory.cpp",
      v6);
LABEL_4:
    WindowsDeleteString(string);
    v7 = v17;
    string = 0;
    if ( v17 )
    {
      v17 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return (unsigned int)v5;
  }
  v9 = v17;
  v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v17 + 56LL);
  WindowsDeleteString(string);
  string = 0;
  v5 = v10(v9, &string);
  if ( v5 < 0 )
  {
    v6 = 177;
    goto LABEL_3;
  }
  v28 = 0;
  v29 = 0;
  memset_0(pszDest, 0, 0x80u);
  Microsoft::WRL::ComPtr<Windows::Phone::Restricted::Cellular::Rcs::IImsClient>::operator=(&v28, &v17);
  if ( v17 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v17 + 72LL))(v17, &v29);
    if ( v5 < 0 )
    {
      v11 = 183;
      goto LABEL_12;
    }
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v5 = StringCchCopyW(pszDest, 0x40u, StringRawBuffer);
  if ( v5 < 0 )
  {
    v11 = 186;
LABEL_12:
    Log_HREvent_102(
      (unsigned int)v5,
      1,
      "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\imsserviceclientfactory.cpp",
      v11);
    v12 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
    }
    goto LABEL_4;
  }
  v18 = v28;
  Microsoft::WRL::ComPtr<Windows::Phone::Restricted::Cellular::Rcs::IImsClientWatcher>::InternalAddRef(&v18);
  v19 = v29;
  v20 = *(_OWORD *)pszDest;
  v21 = v31;
  v22 = v32;
  v23 = v33;
  v24 = v34;
  v25 = v35;
  v26 = v36;
  v27 = v37;
  RcsEventHandler<Windows::Phone::Restricted::Cellular::Rcs::ImsClientWatcher,Windows::Phone::Restricted::Cellular::Rcs::IImsClientWatcher,Windows::Phone::Restricted::Cellular::Rcs::ImsClientWatcherEventArgs,ImsClientRemovedEventNotificationArgs>::_PublishNotifications(
    (char *)this - 8,
    &v18);
  v14 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  WindowsDeleteString(string);
  v15 = v17;
  string = 0;
  if ( v17 )
  {
    v17 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  return 0;
}

```

## disassembly

```asm
0x1800bb9d0  mov     [rsp-8+arg_8], rbx
0x1800bb9d5  mov     [rsp-8+arg_18], rsi
0x1800bb9da  push    rbp
0x1800bb9db  push    rdi
0x1800bb9dc  push    r14
0x1800bb9de  lea     rbp, [rsp-90h]
0x1800bb9e6  sub     rsp, 190h
0x1800bb9ed  mov     rax, cs:__security_cookie
0x1800bb9f4  xor     rax, rsp
0x1800bb9f7  mov     [rbp+0A0h+var_20], rax
0x1800bb9fe  mov     rax, [r8]
0x1800bba01  lea     rdx, [rsp+1A0h+var_168]
0x1800bba06  mov     rsi, rcx
0x1800bba09  xor     r14d, r14d
0x1800bba0c  mov     rcx, r8
0x1800bba0f  mov     [rsp+1A0h+var_168], r14
0x1800bba14  mov     [rsp+1A0h+string], r14
0x1800bba19  mov     rax, [rax+30h]
0x1800bba1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bba22  mov     ebx, eax
0x1800bba24  test    eax, eax
0x1800bba26  jns     short loc_1800BBA73
0x1800bba28  mov     r9d, 0AFh
0x1800bba2e  lea     r8, aOnecoreuapBase_115; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800bba35  mov     edx, 1
0x1800bba3a  mov     ecx, ebx
0x1800bba3c  call    Log_HREvent_102
0x1800bba41  mov     rcx, [rsp+1A0h+string]; string
0x1800bba46  call    cs:__imp_WindowsDeleteString
0x1800bba4c  mov     rcx, [rsp+1A0h+var_168]
0x1800bba51  mov     [rsp+1A0h+string], r14
0x1800bba56  test    rcx, rcx
0x1800bba59  jz      short loc_1800BBA6C
0x1800bba5b  mov     [rsp+1A0h+var_168], r14
0x1800bba60  mov     rax, [rcx]
0x1800bba63  mov     rax, [rax+10h]
0x1800bba67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bba6c  mov     eax, ebx
0x1800bba6e  jmp     loc_1800BBC1A
0x1800bba73  mov     rdi, [rsp+1A0h+var_168]
0x1800bba78  mov     rcx, [rsp+1A0h+string]; string
0x1800bba7d  mov     rax, [rdi]
0x1800bba80  mov     rbx, [rax+38h]
0x1800bba84  call    cs:__imp_WindowsDeleteString
0x1800bba8a  lea     rdx, [rsp+1A0h+string]
0x1800bba8f  mov     [rsp+1A0h+string], r14
0x1800bba94  mov     rcx, rdi
0x1800bba97  mov     rax, rbx
0x1800bba9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bba9f  mov     ebx, eax
0x1800bbaa1  test    eax, eax
0x1800bbaa3  jns     short loc_1800BBAAD
0x1800bbaa5  mov     r9d, 0B1h
0x1800bbaab  jmp     short loc_1800BBA2E
0x1800bbaad  xorps   xmm0, xmm0
0x1800bbab0  mov     [rbp+0A0h+var_C0], r14
0x1800bbab4  xor     edx, edx; Val
0x1800bbab6  lea     rcx, [rbp+0A0h+pszDest]; void *
0x1800bbaba  mov     r8d, 80h; Size
0x1800bbac0  movups  [rbp+0A0h+var_B8], xmm0
0x1800bbac4  call    memset_0
0x1800bbac9  lea     rdx, [rsp+1A0h+var_168]
0x1800bbace  lea     rcx, [rbp+0A0h+var_C0]
0x1800bbad2  call    ??4?$ComPtr@UIImsClient@Rcs@Cellular@Restricted@Phone@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Phone::Restricted::Cellular::Rcs::IImsClient>::operator=(Microsoft::WRL::ComPtr<Windows::Phone::Restricted::Cellular::Rcs::IImsClient> const &)
0x1800bbad7  mov     rcx, [rsp+1A0h+var_168]
0x1800bbadc  test    rcx, rcx
0x1800bbadf  jz      short loc_1800BBB32
0x1800bbae1  mov     rax, [rcx]
0x1800bbae4  lea     rdx, [rbp+0A0h+var_B8]
0x1800bbae8  mov     rax, [rax+48h]
0x1800bbaec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbaf1  mov     ebx, eax
0x1800bbaf3  test    eax, eax
0x1800bbaf5  jns     short loc_1800BBB32
0x1800bbaf7  mov     r9d, 0B7h
0x1800bbafd  lea     r8, aOnecoreuapBase_115; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800bbb04  mov     edx, 1
0x1800bbb09  mov     ecx, ebx
0x1800bbb0b  call    Log_HREvent_102
0x1800bbb10  mov     rcx, [rbp+0A0h+var_C0]
0x1800bbb14  test    rcx, rcx
0x1800bbb17  jz      loc_1800BBA41
0x1800bbb1d  mov     [rbp+0A0h+var_C0], r14
0x1800bbb21  mov     rax, [rcx]
0x1800bbb24  mov     rax, [rax+10h]
0x1800bbb28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbb2d  jmp     loc_1800BBA41
0x1800bbb32  mov     rcx, [rsp+1A0h+string]; string
0x1800bbb37  xor     edx, edx; length
0x1800bbb39  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bbb3f  mov     edx, 40h ; '@'; cchDest
0x1800bbb44  lea     rcx, [rbp+0A0h+pszDest]; pszDest
0x1800bbb48  mov     r8, rax; pszSrc
0x1800bbb4b  call    StringCchCopyW
0x1800bbb50  mov     ebx, eax
0x1800bbb52  test    eax, eax
0x1800bbb54  jns     short loc_1800BBB5E
0x1800bbb56  mov     r9d, 0BAh
0x1800bbb5c  jmp     short loc_1800BBAFD
0x1800bbb5e  mov     rax, [rbp+0A0h+var_C0]
0x1800bbb62  lea     rcx, [rsp+1A0h+var_160]
0x1800bbb67  mov     [rsp+1A0h+var_160], rax
0x1800bbb6c  call    ?InternalAddRef@?$ComPtr@UIImsClientWatcher@Rcs@Cellular@Restricted@Phone@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Phone::Restricted::Cellular::Rcs::IImsClientWatcher>::InternalAddRef(void)
0x1800bbb71  movups  xmm0, xmmword ptr [rbp+0A0h+pszDest]
0x1800bbb75  mov     rax, qword ptr [rbp+0A0h+var_B8]
0x1800bbb79  lea     rcx, [rsi-8]
0x1800bbb7d  movups  xmm1, [rbp+0A0h+var_98]
0x1800bbb81  mov     qword ptr [rsp+1A0h+var_158], rax
0x1800bbb86  lea     rdx, [rsp+1A0h+var_160]
0x1800bbb8b  mov     rax, qword ptr [rbp+0A0h+var_B8+8]
0x1800bbb8f  movups  [rsp+1A0h+var_148], xmm0
0x1800bbb94  mov     qword ptr [rsp+1A0h+var_158+8], rax
0x1800bbb99  movups  xmm0, [rbp+0A0h+var_88]
0x1800bbb9d  movups  [rsp+1A0h+var_138], xmm1
0x1800bbba2  movups  xmm1, [rbp+0A0h+var_78]
0x1800bbba6  movups  [rsp+1A0h+var_128], xmm0
0x1800bbbab  movups  xmm0, [rbp+0A0h+var_68]
0x1800bbbaf  movups  [rbp+0A0h+var_118], xmm1
0x1800bbbb3  movups  xmm1, [rbp+0A0h+var_58]
0x1800bbbb7  movups  [rbp+0A0h+var_108], xmm0
0x1800bbbbb  movups  xmm0, [rbp+0A0h+var_48]
0x1800bbbbf  movups  [rbp+0A0h+var_F8], xmm1
0x1800bbbc3  movups  xmm1, [rbp+0A0h+var_38]
0x1800bbbc7  movups  [rbp+0A0h+var_E8], xmm0
0x1800bbbcb  movups  [rbp+0A0h+var_D8], xmm1
0x1800bbbcf  call    ?_PublishNotifications@?$RcsEventHandler@VImsClientWatcher@Rcs@Cellular@Restricted@Phone@Windows@@UIImsClientWatcher@23456@VImsClientWatcherEventArgs@23456@UImsClientRemovedEventNotificationArgs@@@@IEAAXUImsClientRemovedEventNotificationArgs@@@Z; RcsEventHandler<Windows::Phone::Restricted::Cellular::Rcs::ImsClientWatcher,Windows::Phone::Restricted::Cellular::Rcs::IImsClientWatcher,Windows::Phone::Restricted::Cellular::Rcs::ImsClientWatcherEventArgs,ImsClientRemovedEventNotificationArgs>::_PublishNotifications(ImsClientRemovedEventNotificationArgs)
0x1800bbbd4  mov     rcx, [rbp+0A0h+var_C0]
0x1800bbbd8  test    rcx, rcx
0x1800bbbdb  jz      short loc_1800BBBED
0x1800bbbdd  mov     [rbp+0A0h+var_C0], r14
0x1800bbbe1  mov     rax, [rcx]
0x1800bbbe4  mov     rax, [rax+10h]
0x1800bbbe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbbed  mov     rcx, [rsp+1A0h+string]; string
0x1800bbbf2  call    cs:__imp_WindowsDeleteString
0x1800bbbf8  mov     rcx, [rsp+1A0h+var_168]
0x1800bbbfd  mov     [rsp+1A0h+string], r14
0x1800bbc02  test    rcx, rcx
0x1800bbc05  jz      short loc_1800BBC18
0x1800bbc07  mov     [rsp+1A0h+var_168], r14
0x1800bbc0c  mov     rax, [rcx]
0x1800bbc0f  mov     rax, [rax+10h]
0x1800bbc13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbc18  xor     eax, eax
0x1800bbc1a  mov     rcx, [rbp+0A0h+var_20]
0x1800bbc21  xor     rcx, rsp; StackCookie
0x1800bbc24  call    __security_check_cookie
0x1800bbc29  lea     r11, [rsp+1A0h+var_10]
0x1800bbc31  mov     rbx, [r11+28h]
0x1800bbc35  mov     rsi, [r11+38h]
0x1800bbc39  mov     rsp, r11
0x1800bbc3c  pop     r14
0x1800bbc3e  pop     rdi
0x1800bbc3f  pop     rbp
0x1800bbc40  retn
```
