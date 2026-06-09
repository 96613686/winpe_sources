# ImsServiceClientFactoryImpl::ImsClientAddedHandler::Invoke(Windows::Phone::Restricted::Cellular::Rcs::IImsClientWatcher *,Windows::Phone::Restricted::Cellular::Rcs::IImsClientWatcherEventArgs *)

- ea: `0x1800bb6e0`
- end: `0x1800bb951`
- name: `?Invoke@ImsClientAddedHandler@ImsServiceClientFactoryImpl@@UEAAJPEAUIImsClientWatcher@Rcs@Cellular@Restricted@Phone@Windows@@PEAUIImsClientWatcherEventArgs@45678@@Z`
- size: `625`
- prototype: `__int64 __fastcall(ImsServiceClientFactoryImpl::ImsClientAddedHandler *__hidden this, struct Windows::Phone::Restricted::Cellular::Rcs::IImsClientWatcher *, struct Windows::Phone::Restricted::Cellular::Rcs::IImsClientWatcherEventArgs *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000bae4`
- `0x18002cf18`
- `0x1800bb0fc`
- `0x1800bb6e0`
- `0x1800bbc88`
- `0x1800bc610`
- `0x1800c6902`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bb849`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bb849`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bb756`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bb794`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bb902`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bb756`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bb794`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bb902`

## string_xrefs

- `0x1800bb73e`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\imsserviceclientfactory.cpp`
- `0x1800bb80d`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\imsserviceclientfactory.cpp`

## pseudocode

```c
__int64 __fastcall ImsServiceClientFactoryImpl::ImsClientAddedHandler::Invoke(
        ImsServiceClientFactoryImpl::ImsClientAddedHandler *this,
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
    v6 = 137;
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
    v6 = 139;
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
      v11 = 145;
      goto LABEL_12;
    }
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v5 = StringCchCopyW(pszDest, 0x40u, StringRawBuffer);
  if ( v5 < 0 )
  {
    v11 = 148;
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
0x1800bb6e0  mov     [rsp-8+arg_8], rbx
0x1800bb6e5  mov     [rsp-8+arg_18], rsi
0x1800bb6ea  push    rbp
0x1800bb6eb  push    rdi
0x1800bb6ec  push    r14
0x1800bb6ee  lea     rbp, [rsp-90h]
0x1800bb6f6  sub     rsp, 190h
0x1800bb6fd  mov     rax, cs:__security_cookie
0x1800bb704  xor     rax, rsp
0x1800bb707  mov     [rbp+0A0h+var_20], rax
0x1800bb70e  mov     rax, [r8]
0x1800bb711  lea     rdx, [rsp+1A0h+var_168]
0x1800bb716  mov     rsi, rcx
0x1800bb719  xor     r14d, r14d
0x1800bb71c  mov     rcx, r8
0x1800bb71f  mov     [rsp+1A0h+var_168], r14
0x1800bb724  mov     [rsp+1A0h+string], r14
0x1800bb729  mov     rax, [rax+30h]
0x1800bb72d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb732  mov     ebx, eax
0x1800bb734  test    eax, eax
0x1800bb736  jns     short loc_1800BB783
0x1800bb738  mov     r9d, 89h
0x1800bb73e  lea     r8, aOnecoreuapBase_115; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800bb745  mov     edx, 1
0x1800bb74a  mov     ecx, ebx
0x1800bb74c  call    Log_HREvent_102
0x1800bb751  mov     rcx, [rsp+1A0h+string]; string
0x1800bb756  call    cs:__imp_WindowsDeleteString
0x1800bb75c  mov     rcx, [rsp+1A0h+var_168]
0x1800bb761  mov     [rsp+1A0h+string], r14
0x1800bb766  test    rcx, rcx
0x1800bb769  jz      short loc_1800BB77C
0x1800bb76b  mov     [rsp+1A0h+var_168], r14
0x1800bb770  mov     rax, [rcx]
0x1800bb773  mov     rax, [rax+10h]
0x1800bb777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb77c  mov     eax, ebx
0x1800bb77e  jmp     loc_1800BB92A
0x1800bb783  mov     rdi, [rsp+1A0h+var_168]
0x1800bb788  mov     rcx, [rsp+1A0h+string]; string
0x1800bb78d  mov     rax, [rdi]
0x1800bb790  mov     rbx, [rax+38h]
0x1800bb794  call    cs:__imp_WindowsDeleteString
0x1800bb79a  lea     rdx, [rsp+1A0h+string]
0x1800bb79f  mov     [rsp+1A0h+string], r14
0x1800bb7a4  mov     rcx, rdi
0x1800bb7a7  mov     rax, rbx
0x1800bb7aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb7af  mov     ebx, eax
0x1800bb7b1  test    eax, eax
0x1800bb7b3  jns     short loc_1800BB7BD
0x1800bb7b5  mov     r9d, 8Bh
0x1800bb7bb  jmp     short loc_1800BB73E
0x1800bb7bd  xorps   xmm0, xmm0
0x1800bb7c0  mov     [rbp+0A0h+var_C0], r14
0x1800bb7c4  xor     edx, edx; Val
0x1800bb7c6  lea     rcx, [rbp+0A0h+pszDest]; void *
0x1800bb7ca  mov     r8d, 80h; Size
0x1800bb7d0  movups  [rbp+0A0h+var_B8], xmm0
0x1800bb7d4  call    memset_0
0x1800bb7d9  lea     rdx, [rsp+1A0h+var_168]
0x1800bb7de  lea     rcx, [rbp+0A0h+var_C0]
0x1800bb7e2  call    ??4?$ComPtr@UIImsClient@Rcs@Cellular@Restricted@Phone@Windows@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<Windows::Phone::Restricted::Cellular::Rcs::IImsClient>::operator=(Microsoft::WRL::ComPtr<Windows::Phone::Restricted::Cellular::Rcs::IImsClient> const &)
0x1800bb7e7  mov     rcx, [rsp+1A0h+var_168]
0x1800bb7ec  test    rcx, rcx
0x1800bb7ef  jz      short loc_1800BB842
0x1800bb7f1  mov     rax, [rcx]
0x1800bb7f4  lea     rdx, [rbp+0A0h+var_B8]
0x1800bb7f8  mov     rax, [rax+48h]
0x1800bb7fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb801  mov     ebx, eax
0x1800bb803  test    eax, eax
0x1800bb805  jns     short loc_1800BB842
0x1800bb807  mov     r9d, 91h
0x1800bb80d  lea     r8, aOnecoreuapBase_115; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800bb814  mov     edx, 1
0x1800bb819  mov     ecx, ebx
0x1800bb81b  call    Log_HREvent_102
0x1800bb820  mov     rcx, [rbp+0A0h+var_C0]
0x1800bb824  test    rcx, rcx
0x1800bb827  jz      loc_1800BB751
0x1800bb82d  mov     [rbp+0A0h+var_C0], r14
0x1800bb831  mov     rax, [rcx]
0x1800bb834  mov     rax, [rax+10h]
0x1800bb838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb83d  jmp     loc_1800BB751
0x1800bb842  mov     rcx, [rsp+1A0h+string]; string
0x1800bb847  xor     edx, edx; length
0x1800bb849  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bb84f  mov     edx, 40h ; '@'; cchDest
0x1800bb854  lea     rcx, [rbp+0A0h+pszDest]; pszDest
0x1800bb858  mov     r8, rax; pszSrc
0x1800bb85b  call    StringCchCopyW
0x1800bb860  mov     ebx, eax
0x1800bb862  test    eax, eax
0x1800bb864  jns     short loc_1800BB86E
0x1800bb866  mov     r9d, 94h
0x1800bb86c  jmp     short loc_1800BB80D
0x1800bb86e  mov     rax, [rbp+0A0h+var_C0]
0x1800bb872  lea     rcx, [rsp+1A0h+var_160]
0x1800bb877  mov     [rsp+1A0h+var_160], rax
0x1800bb87c  call    ?InternalAddRef@?$ComPtr@UIImsClientWatcher@Rcs@Cellular@Restricted@Phone@Windows@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<Windows::Phone::Restricted::Cellular::Rcs::IImsClientWatcher>::InternalAddRef(void)
0x1800bb881  movups  xmm0, xmmword ptr [rbp+0A0h+pszDest]
0x1800bb885  mov     rax, qword ptr [rbp+0A0h+var_B8]
0x1800bb889  lea     rcx, [rsi-8]
0x1800bb88d  movups  xmm1, [rbp+0A0h+var_98]
0x1800bb891  mov     qword ptr [rsp+1A0h+var_158], rax
0x1800bb896  lea     rdx, [rsp+1A0h+var_160]
0x1800bb89b  mov     rax, qword ptr [rbp+0A0h+var_B8+8]
0x1800bb89f  movups  [rsp+1A0h+var_148], xmm0
0x1800bb8a4  mov     qword ptr [rsp+1A0h+var_158+8], rax
0x1800bb8a9  movups  xmm0, [rbp+0A0h+var_88]
0x1800bb8ad  movups  [rsp+1A0h+var_138], xmm1
0x1800bb8b2  movups  xmm1, [rbp+0A0h+var_78]
0x1800bb8b6  movups  [rsp+1A0h+var_128], xmm0
0x1800bb8bb  movups  xmm0, [rbp+0A0h+var_68]
0x1800bb8bf  movups  [rbp+0A0h+var_118], xmm1
0x1800bb8c3  movups  xmm1, [rbp+0A0h+var_58]
0x1800bb8c7  movups  [rbp+0A0h+var_108], xmm0
0x1800bb8cb  movups  xmm0, [rbp+0A0h+var_48]
0x1800bb8cf  movups  [rbp+0A0h+var_F8], xmm1
0x1800bb8d3  movups  xmm1, [rbp+0A0h+var_38]
0x1800bb8d7  movups  [rbp+0A0h+var_E8], xmm0
0x1800bb8db  movups  [rbp+0A0h+var_D8], xmm1
0x1800bb8df  call    ?_PublishNotifications@?$RcsEventHandler@VImsClientWatcher@Rcs@Cellular@Restricted@Phone@Windows@@UIImsClientWatcher@23456@VImsClientWatcherEventArgs@23456@UImsClientRemovedEventNotificationArgs@@@@IEAAXUImsClientRemovedEventNotificationArgs@@@Z; RcsEventHandler<Windows::Phone::Restricted::Cellular::Rcs::ImsClientWatcher,Windows::Phone::Restricted::Cellular::Rcs::IImsClientWatcher,Windows::Phone::Restricted::Cellular::Rcs::ImsClientWatcherEventArgs,ImsClientRemovedEventNotificationArgs>::_PublishNotifications(ImsClientRemovedEventNotificationArgs)
0x1800bb8e4  mov     rcx, [rbp+0A0h+var_C0]
0x1800bb8e8  test    rcx, rcx
0x1800bb8eb  jz      short loc_1800BB8FD
0x1800bb8ed  mov     [rbp+0A0h+var_C0], r14
0x1800bb8f1  mov     rax, [rcx]
0x1800bb8f4  mov     rax, [rax+10h]
0x1800bb8f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb8fd  mov     rcx, [rsp+1A0h+string]; string
0x1800bb902  call    cs:__imp_WindowsDeleteString
0x1800bb908  mov     rcx, [rsp+1A0h+var_168]
0x1800bb90d  mov     [rsp+1A0h+string], r14
0x1800bb912  test    rcx, rcx
0x1800bb915  jz      short loc_1800BB928
0x1800bb917  mov     [rsp+1A0h+var_168], r14
0x1800bb91c  mov     rax, [rcx]
0x1800bb91f  mov     rax, [rax+10h]
0x1800bb923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bb928  xor     eax, eax
0x1800bb92a  mov     rcx, [rbp+0A0h+var_20]
0x1800bb931  xor     rcx, rsp; StackCookie
0x1800bb934  call    __security_check_cookie
0x1800bb939  lea     r11, [rsp+1A0h+var_10]
0x1800bb941  mov     rbx, [r11+28h]
0x1800bb945  mov     rsi, [r11+38h]
0x1800bb949  mov     rsp, r11
0x1800bb94c  pop     r14
0x1800bb94e  pop     rdi
0x1800bb94f  pop     rbp
0x1800bb950  retn
```
