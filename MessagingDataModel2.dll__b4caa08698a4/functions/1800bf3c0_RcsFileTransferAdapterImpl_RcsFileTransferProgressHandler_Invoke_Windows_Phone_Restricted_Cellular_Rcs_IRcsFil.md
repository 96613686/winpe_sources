# RcsFileTransferAdapterImpl::RcsFileTransferProgressHandler::Invoke(Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransfer *,Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferProgressUpdatedEventArgs *)

- ea: `0x1800bf3c0`
- end: `0x1800bf62e`
- name: `?Invoke@RcsFileTransferProgressHandler@RcsFileTransferAdapterImpl@@UEAAJPEAUIRcsFileTransfer@Rcs@Cellular@Restricted@Phone@Windows@@PEAUIRcsFileTransferProgressUpdatedEventArgs@45678@@Z`
- size: `622`
- prototype: `__int64 __fastcall(RcsFileTransferAdapterImpl::RcsFileTransferProgressHandler *__hidden this, struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransfer *, struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferProgressUpdatedEventArgs *)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000bae4`
- `0x1800bbc88`
- `0x1800bf3c0`
- `0x1800c0098`
- `0x1800c061c`
- `0x1800c4b98`
- `0x1800c6902`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bf4d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bf52d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bf4d8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800bf52d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf485`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf601`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf485`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800bf601`

## string_xrefs

- `0x1800bf41e`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcsfiletransferadapterimpl.cpp`
- `0x1800bf4ae`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcsfiletransferadapterimpl.cpp`
- `0x1800bf550`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcsfiletransferadapterimpl.cpp`

## pseudocode

```c
__int64 __fastcall RcsFileTransferAdapterImpl::RcsFileTransferProgressHandler::Invoke(
        RcsFileTransferAdapterImpl::RcsFileTransferProgressHandler *this,
        struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransfer *a2,
        struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferProgressUpdatedEventArgs *a3)
{
  __int64 v3; // rax
  int v7; // ebx
  __int64 v8; // r9
  __int64 v9; // rax
  double v10; // xmm0_8
  __int64 v11; // rax
  __int64 (__fastcall *v12)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransfer *, HSTRING *); // rbx
  int v13; // eax
  char v14; // bl
  int v15; // edi
  unsigned int StringRawBuffer; // eax
  int v17; // ecx
  const wchar_t *v18; // rax
  HRESULT v19; // eax
  __int64 v20; // rax
  __int64 v21; // rax
  HSTRING string; // [rsp+38h] [rbp-D0h] BYREF
  __int128 v24; // [rsp+40h] [rbp-C8h] BYREF
  _OWORD v25[10]; // [rsp+58h] [rbp-B0h] BYREF
  wchar_t pszDest[8]; // [rsp+F8h] [rbp-10h] BYREF
  __int128 v27; // [rsp+108h] [rbp+0h]
  __int128 v28; // [rsp+118h] [rbp+10h]
  __int128 v29; // [rsp+128h] [rbp+20h]
  __int128 v30; // [rsp+138h] [rbp+30h]
  __int128 v31; // [rsp+148h] [rbp+40h]
  __int128 v32; // [rsp+158h] [rbp+50h]
  __int128 v33; // [rsp+168h] [rbp+60h]
  __int128 v34; // [rsp+178h] [rbp+70h]
  __int128 v35; // [rsp+188h] [rbp+80h]

  v3 = *(_QWORD *)a3;
  *(_QWORD *)&v24 = 0;
  v7 = (*(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferProgressUpdatedEventArgs *, __int128 *))(v3 + 56))(
         a3,
         &v24);
  if ( v7 < 0 )
  {
    v8 = 261;
LABEL_3:
    Log_HREvent_102(
      (unsigned int)v7,
      1,
      "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcsfiletransferadapterimpl.cpp",
      v8);
    return (unsigned int)v7;
  }
  v9 = *(_QWORD *)a3;
  *((_QWORD *)&v24 + 1) = 0;
  v7 = (*(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransferProgressUpdatedEventArgs *, char *))(v9 + 48))(
         a3,
         (char *)&v24 + 8);
  if ( v7 < 0 )
  {
    v8 = 264;
    goto LABEL_3;
  }
  v10 = CalculateFileTransferProgress(v24, *((unsigned __int64 *)&v24 + 1));
  v11 = *(_QWORD *)a2;
  string = 0;
  v12 = *(__int64 (__fastcall **)(struct Windows::Phone::Restricted::Cellular::Rcs::IRcsFileTransfer *, HSTRING *))(v11 + 80);
  WindowsDeleteString(0);
  string = 0;
  v13 = v12(a2, &string);
  if ( v13 < 0 )
    Log_HREvent_102(
      (unsigned int)v13,
      0,
      "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcsfiletransferadapterimpl.cpp",
      269);
  if ( (Microsoft_Windows_UserDataAccess_RcsServiceAdapterEnableBits & 4) != 0 )
  {
    v14 = BYTE8(v24);
    v15 = v24;
    StringRawBuffer = (unsigned int)WindowsGetStringRawBuffer(string, 0);
    McTemplateU0zxxg_EventWriteTransfer(
      v17,
      (unsigned int)FileTransferProgressUpdated,
      StringRawBuffer,
      v15,
      v14,
      SLOBYTE(v10));
  }
  v34 = 0u;
  v35 = 0;
  memset_0(pszDest, 0, 0x80u);
  v18 = WindowsGetStringRawBuffer(string, 0);
  v19 = StringCchCopyW(pszDest, 0x40u, v18);
  v7 = v19;
  if ( v19 >= 0 )
  {
    v34 = v24;
    v25[0] = *(_OWORD *)pszDest;
    v20 = *((_QWORD *)this + 16);
    v25[1] = v27;
    *(_QWORD *)&v35 = v20;
    v21 = *((_QWORD *)this + 17);
    v25[2] = v28;
    *((_QWORD *)&v35 + 1) = v21;
    v25[3] = v29;
    v25[4] = v30;
    v25[5] = v31;
    v25[6] = v32;
    v25[7] = v33;
    v25[8] = v24;
    v25[9] = v35;
    RcsEventHandler<Windows::Phone::Restricted::Cellular::Rcs::RcsChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsChat,Windows::Phone::Restricted::Cellular::Rcs::RcsChatMultipartMessageFileTransferProgressUpdatedEventArgs,RcsChatMultipartMessageFileTransferProgressUpdateNotificationArgs>::_PublishNotifications(
      (char *)this - 8,
      v25);
    v7 = 0;
  }
  else
  {
    Log_HREvent_102(
      (unsigned int)v19,
      1,
      "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcsfiletransferadapterimpl.cpp",
      274);
  }
  WindowsDeleteString(string);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800bf3c0  mov     rax, rsp
0x1800bf3c3  push    rbp
0x1800bf3c4  push    rbx
0x1800bf3c5  push    rsi
0x1800bf3c6  push    rdi
0x1800bf3c7  push    r14
0x1800bf3c9  lea     rbp, [rax-0D8h]
0x1800bf3d0  sub     rsp, 1B0h
0x1800bf3d7  movaps  xmmword ptr [rax-38h], xmm6
0x1800bf3db  mov     rax, cs:__security_cookie
0x1800bf3e2  xor     rax, rsp
0x1800bf3e5  mov     [rbp+0D0h+var_40], rax
0x1800bf3ec  mov     rax, [r8]
0x1800bf3ef  mov     rsi, rdx
0x1800bf3f2  mov     r14, rcx
0x1800bf3f5  mov     qword ptr [rsp+1D0h+var_198], 0
0x1800bf3fe  lea     rdx, [rsp+1D0h+var_198]
0x1800bf403  mov     rcx, r8
0x1800bf406  mov     rdi, r8
0x1800bf409  mov     rax, [rax+38h]
0x1800bf40d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf412  mov     ebx, eax
0x1800bf414  test    eax, eax
0x1800bf416  jns     short loc_1800BF436
0x1800bf418  mov     r9d, 105h
0x1800bf41e  lea     r8, aOnecoreuapBase_121; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800bf425  mov     edx, 1
0x1800bf42a  mov     ecx, ebx
0x1800bf42c  call    Log_HREvent_102
0x1800bf431  jmp     loc_1800BF607
0x1800bf436  mov     rax, [rdi]
0x1800bf439  lea     rdx, [rsp+1D0h+var_198+8]
0x1800bf43e  mov     rcx, rdi
0x1800bf441  mov     qword ptr [rsp+1D0h+var_198+8], 0
0x1800bf44a  mov     rax, [rax+30h]
0x1800bf44e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf453  mov     ebx, eax
0x1800bf455  test    eax, eax
0x1800bf457  jns     short loc_1800BF461
0x1800bf459  mov     r9d, 108h
0x1800bf45f  jmp     short loc_1800BF41E
0x1800bf461  mov     rdx, qword ptr [rsp+1D0h+var_198+8]; unsigned __int64
0x1800bf466  mov     rcx, qword ptr [rsp+1D0h+var_198]; unsigned __int64
0x1800bf46b  call    ?CalculateFileTransferProgress@@YAN_K0@Z; CalculateFileTransferProgress(unsigned __int64,unsigned __int64)
0x1800bf470  mov     rax, [rsi]
0x1800bf473  xor     ecx, ecx; string
0x1800bf475  movaps  xmm6, xmm0
0x1800bf478  mov     [rsp+1D0h+string], 0
0x1800bf481  mov     rbx, [rax+50h]
0x1800bf485  call    cs:__imp_WindowsDeleteString
0x1800bf48b  lea     rdx, [rsp+1D0h+string]
0x1800bf490  mov     [rsp+1D0h+string], 0
0x1800bf499  mov     rcx, rsi
0x1800bf49c  mov     rax, rbx
0x1800bf49f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf4a4  test    eax, eax
0x1800bf4a6  jns     short loc_1800BF4BE
0x1800bf4a8  mov     r9d, 10Dh
0x1800bf4ae  lea     r8, aOnecoreuapBase_121; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800bf4b5  xor     edx, edx
0x1800bf4b7  mov     ecx, eax
0x1800bf4b9  call    Log_HREvent_102
0x1800bf4be  test    cs:Microsoft_Windows_UserDataAccess_RcsServiceAdapterEnableBits, 4
0x1800bf4c5  jz      short loc_1800BF4FB
0x1800bf4c7  mov     rcx, [rsp+1D0h+string]; string
0x1800bf4cc  xor     edx, edx; length
0x1800bf4ce  mov     rbx, qword ptr [rsp+1D0h+var_198+8]
0x1800bf4d3  mov     rdi, qword ptr [rsp+1D0h+var_198]
0x1800bf4d8  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bf4de  movsd   [rsp+1D0h+var_1A8], xmm6
0x1800bf4e4  lea     rdx, FileTransferProgressUpdated
0x1800bf4eb  mov     r8, rax
0x1800bf4ee  mov     [rsp+1D0h+var_1B0], rbx
0x1800bf4f3  mov     r9, rdi
0x1800bf4f6  call    McTemplateU0zxxg_EventWriteTransfer
0x1800bf4fb  xorps   xmm0, xmm0
0x1800bf4fe  mov     qword ptr [rbp+0D0h+var_60], 0
0x1800bf506  xor     edx, edx; Val
0x1800bf508  mov     qword ptr [rbp+0D0h+var_60+8], 0
0x1800bf510  mov     r8d, 80h; Size
0x1800bf516  lea     rcx, [rbp+0D0h+pszDest]; void *
0x1800bf51a  movups  [rbp+0D0h+var_50], xmm0
0x1800bf521  call    memset_0
0x1800bf526  mov     rcx, [rsp+1D0h+string]; string
0x1800bf52b  xor     edx, edx; length
0x1800bf52d  call    cs:__imp_WindowsGetStringRawBuffer
0x1800bf533  mov     edx, 40h ; '@'; cchDest
0x1800bf538  lea     rcx, [rbp+0D0h+pszDest]; pszDest
0x1800bf53c  mov     r8, rax; pszSrc
0x1800bf53f  call    StringCchCopyW
0x1800bf544  mov     ebx, eax
0x1800bf546  test    eax, eax
0x1800bf548  jns     short loc_1800BF568
0x1800bf54a  mov     r9d, 112h
0x1800bf550  lea     r8, aOnecoreuapBase_121; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800bf557  mov     edx, 1
0x1800bf55c  mov     ecx, eax
0x1800bf55e  call    Log_HREvent_102
0x1800bf563  jmp     loc_1800BF5FC
0x1800bf568  mov     rax, qword ptr [rsp+1D0h+var_198]
0x1800bf56d  lea     rcx, [r14-8]
0x1800bf571  movaps  xmm0, xmmword ptr [rbp+0D0h+pszDest]
0x1800bf575  lea     rdx, [rsp+1D0h+var_188+8]
0x1800bf57a  movaps  xmm1, [rbp+0D0h+var_D0]
0x1800bf57e  mov     qword ptr [rbp+0D0h+var_60], rax
0x1800bf582  mov     rax, qword ptr [rsp+1D0h+var_198+8]
0x1800bf587  movups  [rsp+1D0h+var_188+8], xmm0
0x1800bf58c  mov     qword ptr [rbp+0D0h+var_60+8], rax
0x1800bf590  movaps  xmm0, [rbp+0D0h+var_C0]
0x1800bf594  mov     rax, [r14+80h]
0x1800bf59b  movups  [rsp+1D0h+var_178+8], xmm1
0x1800bf5a0  mov     qword ptr [rbp+0D0h+var_50], rax
0x1800bf5a7  movaps  xmm1, [rbp+0D0h+var_B0]
0x1800bf5ab  mov     rax, [r14+88h]
0x1800bf5b2  movups  [rsp+1D0h+var_168+8], xmm0
0x1800bf5b7  mov     qword ptr [rbp+0D0h+var_50+8], rax
0x1800bf5be  movaps  xmm0, [rbp+0D0h+var_A0]
0x1800bf5c2  movups  [rbp+0D0h+var_150], xmm1
0x1800bf5c6  movaps  xmm1, [rbp+0D0h+var_90]
0x1800bf5ca  movups  [rbp+0D0h+var_140], xmm0
0x1800bf5ce  movaps  xmm0, [rbp+0D0h+var_80]
0x1800bf5d2  movups  [rbp+0D0h+var_130], xmm1
0x1800bf5d6  movaps  xmm1, [rbp+0D0h+var_70]
0x1800bf5da  movups  [rbp+0D0h+var_120], xmm0
0x1800bf5de  movaps  xmm0, [rbp+0D0h+var_60]
0x1800bf5e2  movups  [rbp+0D0h+var_110], xmm1
0x1800bf5e6  movaps  xmm1, [rbp+0D0h+var_50]
0x1800bf5ed  movups  [rbp+0D0h+var_100], xmm0
0x1800bf5f1  movups  [rbp+0D0h+var_F0], xmm1
0x1800bf5f5  call    ?_PublishNotifications@?$RcsEventHandler@VRcsChat@Rcs@Cellular@Restricted@Phone@Windows@@UIRcsChat@23456@VRcsChatMultipartMessageFileTransferProgressUpdatedEventArgs@23456@URcsChatMultipartMessageFileTransferProgressUpdateNotificationArgs@@@@IEAAXURcsChatMultipartMessageFileTransferProgressUpdateNotificationArgs@@@Z; RcsEventHandler<Windows::Phone::Restricted::Cellular::Rcs::RcsChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsChat,Windows::Phone::Restricted::Cellular::Rcs::RcsChatMultipartMessageFileTransferProgressUpdatedEventArgs,RcsChatMultipartMessageFileTransferProgressUpdateNotificationArgs>::_PublishNotifications(RcsChatMultipartMessageFileTransferProgressUpdateNotificationArgs)
0x1800bf5fa  xor     ebx, ebx
0x1800bf5fc  mov     rcx, [rsp+1D0h+string]; string
0x1800bf601  call    cs:__imp_WindowsDeleteString
0x1800bf607  mov     eax, ebx
0x1800bf609  mov     rcx, [rbp+0D0h+var_40]
0x1800bf610  xor     rcx, rsp; StackCookie
0x1800bf613  call    __security_check_cookie
0x1800bf618  movaps  xmm6, [rsp+1D0h+var_38+8]
0x1800bf620  add     rsp, 1B0h
0x1800bf627  pop     r14
0x1800bf629  pop     rdi
0x1800bf62a  pop     rsi
0x1800bf62b  pop     rbx
0x1800bf62c  pop     rbp
0x1800bf62d  retn
```
