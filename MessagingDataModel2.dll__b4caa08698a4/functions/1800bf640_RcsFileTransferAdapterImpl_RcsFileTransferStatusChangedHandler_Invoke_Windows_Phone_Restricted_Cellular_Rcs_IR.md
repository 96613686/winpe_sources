# RcsFileTransferAdapterImpl::RcsFileTransferStatusChangedHandler::Invoke(Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransfer *,Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferStatusChangedEventArgs *)

- ea: `0x1800bf640`
- end: `0x1800bf837`
- name: `?Invoke@RcsFileTransferStatusChangedHandler@RcsFileTransferAdapterImpl@@UEAAJPEAUIRcsFileTransfer@Rcs@Cellular@Restricted@Phone@Windows@@PEAUIRcsFileTransferStatusChangedEventArgs@45678@@Z`
- size: `503`
- prototype: `__int64 __fastcall(RcsFileTransferAdapterImpl::RcsFileTransferStatusChangedHandler *__hidden this, struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransfer *, struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferStatusChangedEventArgs *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000bae4`
- `0x1800bbc88`
- `0x1800bf640`
- `0x1800c0184`
- `0x1800c026c`
- `0x1800c0578`
- `0x1800c6902`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bf71f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bf78e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bf71f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bf78e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf6c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf80d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf6c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf80d`

## string_xrefs

- `0x1800bf696`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcsfiletransferadapterimpl.cpp`
- `0x1800bf6e9`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcsfiletransferadapterimpl.cpp`
- `0x1800bf742`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcsfiletransferadapterimpl.cpp`

## pseudocode

```c
__int64 __fastcall RcsFileTransferAdapterImpl::RcsFileTransferStatusChangedHandler::Invoke(
        RcsFileTransferAdapterImpl::RcsFileTransferStatusChangedHandler *this,
        struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransfer *a2,
        struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferStatusChangedEventArgs *a3)
{
  __int64 v3; // rax
  int v6; // eax
  unsigned int v7; // ebx
  __int64 v8; // rax
  __int64 (__fastcall *v9)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransfer *, HSTRING *); // rbx
  int v10; // eax
  const wchar_t *StringRawBuffer; // rax
  HRESULT v12; // eax
  unsigned int v13; // ebx
  PCWSTR v14; // rax
  __int64 v15; // rcx
  unsigned int v17; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string; // [rsp+38h] [rbp-C8h] BYREF
  _OWORD v19[9]; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+D0h] [rbp-30h]
  wchar_t pszDest[8]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v22; // [rsp+F0h] [rbp-10h]
  __int128 v23; // [rsp+100h] [rbp+0h]
  __int128 v24; // [rsp+110h] [rbp+10h]
  __int128 v25; // [rsp+120h] [rbp+20h]
  __int128 v26; // [rsp+130h] [rbp+30h]
  __int128 v27; // [rsp+140h] [rbp+40h]
  __int128 v28; // [rsp+150h] [rbp+50h]
  _OWORD v29[2]; // [rsp+160h] [rbp+60h] BYREF

  v3 = *(_QWORD *)a3;
  v17 = 0;
  v6 = (*(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferStatusChangedEventArgs *, unsigned int *))(v3 + 48))(
         a3,
         &v17);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = *(_QWORD *)a2;
    string = 0;
    v9 = *(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransfer *, HSTRING *))(v8 + 80);
    WindowsDeleteString(0);
    string = 0;
    v10 = v9(a2, &string);
    if ( v10 < 0 )
      Log_HREvent_102(
        (unsigned int)v10,
        0,
        "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcsfiletransferadapterimpl.cpp",
        305);
    memset(v29, 0, 20);
    memset_0(pszDest, 0, 0x80u);
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v12 = StringCchCopyW(pszDest, 0x40u, StringRawBuffer);
    v7 = v12;
    if ( v12 >= 0 )
    {
      *(_OWORD *)((char *)v29 + 4) = *((_OWORD *)this + 8);
      v13 = RcsFileTransferStatusToAdapterStatus(v17);
      LODWORD(v29[0]) = v13;
      if ( (Microsoft_Windows_UserDataAccess_RcsServiceAdapterEnableBits & 4) != 0 )
      {
        v14 = WindowsGetStringRawBuffer(string, 0);
        McTemplateU0zq_EventWriteTransfer(v15, FileTransferStatusChanged, v14, v13);
      }
      v19[0] = *(_OWORD *)pszDest;
      v20 = v29[1];
      v19[2] = v23;
      v19[1] = v22;
      v19[4] = v25;
      v19[3] = v24;
      v19[6] = v27;
      v19[5] = v26;
      v19[8] = v29[0];
      v19[7] = v28;
      RcsEventHandler<Windows::Phone::Restricted::Cellular::Rcs::RcsFileTransfer,Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransfer,Windows::Phone::Restricted::Cellular::Rcs::RcsFileTransferStatusChangedEventArgs,RcsFileTransferStatusChangedNotificationArgs>::_PublishNotifications(
        (char *)this - 8,
        v19);
      v7 = 0;
    }
    else
    {
      Log_HREvent_102(
        (unsigned int)v12,
        1,
        "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcsfiletransferadapterimpl.cpp",
        309);
    }
    WindowsDeleteString(string);
  }
  else
  {
    Log_HREvent_102(
      (unsigned int)v6,
      1,
      "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcsfiletransferadapterimpl.cpp",
      302);
  }
  return v7;
}

```

## disassembly

```asm
0x1800bf640  mov     [rsp-8+arg_18], rbx
0x1800bf645  push    rbp
0x1800bf646  push    rsi
0x1800bf647  push    rdi
0x1800bf648  lea     rbp, [rsp-90h]
0x1800bf650  sub     rsp, 190h
0x1800bf657  mov     rax, cs:__security_cookie
0x1800bf65e  xor     rax, rsp
0x1800bf661  mov     [rbp+0A0h+var_20], rax
0x1800bf668  mov     rax, [r8]
0x1800bf66b  mov     rsi, rdx
0x1800bf66e  mov     rdi, rcx
0x1800bf671  mov     [rsp+1A0h+var_170], 0
0x1800bf679  lea     rdx, [rsp+1A0h+var_170]
0x1800bf67e  mov     rcx, r8
0x1800bf681  mov     rax, [rax+30h]
0x1800bf685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf68a  mov     ebx, eax
0x1800bf68c  test    eax, eax
0x1800bf68e  jns     short loc_1800BF6AE
0x1800bf690  mov     r9d, 12Eh
0x1800bf696  lea     r8, aOnecoreuapBase_121; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800bf69d  mov     edx, 1
0x1800bf6a2  mov     ecx, eax
0x1800bf6a4  call    Log_HREvent_102
0x1800bf6a9  jmp     loc_1800BF813
0x1800bf6ae  mov     rax, [rsi]
0x1800bf6b1  xor     ecx, ecx; string
0x1800bf6b3  mov     [rsp+1A0h+string], 0
0x1800bf6bc  mov     rbx, [rax+50h]
0x1800bf6c0  call    cs:__imp_WindowsDeleteString
0x1800bf6c6  lea     rdx, [rsp+1A0h+string]
0x1800bf6cb  mov     [rsp+1A0h+string], 0
0x1800bf6d4  mov     rcx, rsi
0x1800bf6d7  mov     rax, rbx
0x1800bf6da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf6df  test    eax, eax
0x1800bf6e1  jns     short loc_1800BF6F9
0x1800bf6e3  mov     r9d, 131h
0x1800bf6e9  lea     r8, aOnecoreuapBase_121; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800bf6f0  xor     edx, edx
0x1800bf6f2  mov     ecx, eax
0x1800bf6f4  call    Log_HREvent_102
0x1800bf6f9  xorps   xmm0, xmm0
0x1800bf6fc  mov     dword ptr [rbp+0A0h+var_40], 0
0x1800bf703  xor     edx, edx; Val
0x1800bf705  lea     rcx, [rbp+0A0h+pszDest]; void *
0x1800bf709  mov     r8d, 80h; Size
0x1800bf70f  movups  xmmword ptr [rbp+0A0h+var_40+4], xmm0
0x1800bf713  call    memset_0
0x1800bf718  mov     rcx, [rsp+1A0h+string]; string
0x1800bf71d  xor     edx, edx; length
0x1800bf71f  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bf725  mov     edx, 40h ; '@'; cchDest
0x1800bf72a  lea     rcx, [rbp+0A0h+pszDest]; pszDest
0x1800bf72e  mov     r8, rax; pszSrc
0x1800bf731  call    StringCchCopyW
0x1800bf736  mov     ebx, eax
0x1800bf738  test    eax, eax
0x1800bf73a  jns     short loc_1800BF75A
0x1800bf73c  mov     r9d, 135h
0x1800bf742  lea     r8, aOnecoreuapBase_121; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800bf749  mov     edx, 1
0x1800bf74e  mov     ecx, eax
0x1800bf750  call    Log_HREvent_102
0x1800bf755  jmp     loc_1800BF808
0x1800bf75a  mov     rax, [rdi+80h]
0x1800bf761  mov     ecx, [rsp+1A0h+var_170]
0x1800bf765  mov     qword ptr [rbp+0A0h+var_40+4], rax
0x1800bf769  mov     rax, [rdi+88h]
0x1800bf770  mov     qword ptr [rbp+0A0h+var_40+0Ch], rax
0x1800bf774  call    _RcsFileTransferStatusToAdapterStatus
0x1800bf779  test    cs:Microsoft_Windows_UserDataAccess_RcsServiceAdapterEnableBits, 4
0x1800bf780  mov     ebx, eax
0x1800bf782  mov     dword ptr [rbp+0A0h+var_40], eax
0x1800bf785  jz      short loc_1800BF7A6
0x1800bf787  mov     rcx, [rsp+1A0h+string]; string
0x1800bf78c  xor     edx, edx; length
0x1800bf78e  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bf794  mov     r9d, ebx
0x1800bf797  lea     rdx, FileTransferStatusChanged
0x1800bf79e  mov     r8, rax
0x1800bf7a1  call    McTemplateU0zq_EventWriteTransfer
0x1800bf7a6  movaps  xmm0, xmmword ptr [rbp+0A0h+pszDest]
0x1800bf7aa  lea     rdx, [rsp+1A0h+var_160]
0x1800bf7af  movaps  xmm1, [rbp+0A0h+var_B0]
0x1800bf7b3  lea     rcx, [rdi-8]
0x1800bf7b7  mov     eax, dword ptr [rbp+0A0h+var_40+10h]
0x1800bf7ba  movups  [rsp+1A0h+var_160], xmm0
0x1800bf7bf  mov     [rbp+0A0h+var_D0], eax
0x1800bf7c2  movaps  xmm0, [rbp+0A0h+var_A0]
0x1800bf7c6  movups  [rsp+1A0h+var_140], xmm0
0x1800bf7cb  movaps  xmm0, [rbp+0A0h+var_80]
0x1800bf7cf  movups  [rsp+1A0h+var_150], xmm1
0x1800bf7d4  movaps  xmm1, [rbp+0A0h+var_90]
0x1800bf7d8  movups  [rbp+0A0h+var_120], xmm0
0x1800bf7dc  movaps  xmm0, [rbp+0A0h+var_60]
0x1800bf7e0  movups  [rsp+1A0h+var_130], xmm1
0x1800bf7e5  movaps  xmm1, [rbp+0A0h+var_70]
0x1800bf7e9  movups  [rbp+0A0h+var_100], xmm0
0x1800bf7ed  movaps  xmm0, xmmword ptr [rbp+0A0h+var_40]
0x1800bf7f1  movups  [rbp+0A0h+var_110], xmm1
0x1800bf7f5  movaps  xmm1, [rbp+0A0h+var_50]
0x1800bf7f9  movups  [rbp+0A0h+var_E0], xmm0
0x1800bf7fd  movups  [rbp+0A0h+var_F0], xmm1
0x1800bf801  call    ?_PublishNotifications@?$RcsEventHandler@VRcsFileTransfer@Rcs@Cellular@Restricted@Phone@Windows@@UIRcsFileTransfer@23456@VRcsFileTransferStatusChangedEventArgs@23456@URcsFileTransferStatusChangedNotificationArgs@@@@IEAAXURcsFileTransferStatusChangedNotificationArgs@@@Z; RcsEventHandler<Windows::Phone::Restricted::Cellular::Rcs::RcsFileTransfer,Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransfer,Windows::Phone::Restricted::Cellular::Rcs::RcsFileTransferStatusChangedEventArgs,RcsFileTransferStatusChangedNotificationArgs>::_PublishNotifications(RcsFileTransferStatusChangedNotificationArgs)
0x1800bf806  xor     ebx, ebx
0x1800bf808  mov     rcx, [rsp+1A0h+string]; string
0x1800bf80d  call    cs:__imp_WindowsDeleteString
0x1800bf813  mov     eax, ebx
0x1800bf815  mov     rcx, [rbp+0A0h+var_20]
0x1800bf81c  xor     rcx, rsp; StackCookie
0x1800bf81f  call    __security_check_cookie
0x1800bf824  mov     rbx, [rsp+1A0h+arg_18]
0x1800bf82c  add     rsp, 190h
0x1800bf833  pop     rdi
0x1800bf834  pop     rsi
0x1800bf835  pop     rbp
0x1800bf836  retn
```
