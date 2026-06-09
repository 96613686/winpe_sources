# RcsChatAdapterImplBase<Windows::Phone::Restricted::Cellular::Rcs::RcsChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsChat>::RcsChatMultipartMessageFileTransferProgressHandler::Invoke(Windows::Phone::Restricted::Cellular::Rcs::IRcsChat *,Windows::Phone::Restricted::Cellular::Rcs::IRcsChatMultipartMessageFileTransferProgressUpdatedEventArgs *)

- ea: `0x1800c2620`
- end: `0x1800c27e2`
- name: `?Invoke@RcsChatMultipartMessageFileTransferProgressHandler@?$RcsChatAdapterImplBase@VRcsChat@Rcs@Cellular@Restricted@Phone@Windows@@UIRcsChat@23456@@@UEAAJPEAUIRcsChat@Rcs@Cellular@Restricted@Phone@Windows@@PEAUIRcsChatMultipartMessageFileTransferProgressUpdatedEventArgs@45678@@Z`
- size: `450`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x18000bae4`
- `0x1800bbc88`
- `0x1800c0098`
- `0x1800c2620`
- `0x1800c6902`
- `0x1800c6940`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c26d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800c26d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c269e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c27b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c269e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800c27b8`

## string_xrefs

- `0x1800c26f5`: `onecoreuap\base\appmodel\messagingom\utils\rcsserviceadapter\lib\rcschatadapterimpl.cpp`

## pseudocode

```c
__int64 __fastcall RcsChatAdapterImplBase<Windows::Phone::Restricted::Cellular::Rcs::RcsChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsChat>::RcsChatMultipartMessageFileTransferProgressHandler::Invoke(
        __int64 a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v5; // rax
  __int64 (__fastcall *v6)(__int64 *, HSTRING *); // rbx
  HRESULT v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // r9
  const wchar_t *StringRawBuffer; // rax
  HSTRING string[2]; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v13[10]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[8]; // [rsp+E0h] [rbp-20h] BYREF
  __int128 v15; // [rsp+F0h] [rbp-10h]
  __int128 v16; // [rsp+100h] [rbp+0h]
  __int128 v17; // [rsp+110h] [rbp+10h]
  __int128 v18; // [rsp+120h] [rbp+20h]
  __int128 v19; // [rsp+130h] [rbp+30h]
  __int128 v20; // [rsp+140h] [rbp+40h]
  __int128 v21; // [rsp+150h] [rbp+50h]
  __int128 v22; // [rsp+160h] [rbp+60h]
  __int128 v23; // [rsp+170h] [rbp+70h] BYREF

  v23 = 0u;
  v22 = 0;
  memset_0(pszDest, 0, 0x80u);
  v22 = *(_OWORD *)(a1 + 160);
  v5 = *a3;
  string[0] = 0;
  v6 = *(__int64 (__fastcall **)(__int64 *, HSTRING *))(v5 + 56);
  WindowsDeleteString(0);
  string[0] = 0;
  v7 = v6(a3, string);
  v8 = v7;
  if ( v7 >= 0 )
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string[0], 0);
    v7 = StringCchCopyW(pszDest, 0x40u, StringRawBuffer);
    v8 = v7;
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64 *, __int128 *))(*a3 + 64))(a3, &v23);
      v8 = v7;
      if ( v7 >= 0 )
      {
        v7 = (*(__int64 (__fastcall **)(__int64 *, char *))(*a3 + 72))(a3, (char *)&v23 + 8);
        v8 = v7;
        if ( v7 >= 0 )
        {
          v13[0] = *(_OWORD *)pszDest;
          v13[1] = v15;
          v13[2] = v16;
          v13[3] = v17;
          v13[4] = v18;
          v13[5] = v19;
          v13[6] = v20;
          v13[7] = v21;
          v13[8] = v22;
          v13[9] = v23;
          RcsEventHandler<Windows::Phone::Restricted::Cellular::Rcs::RcsChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsChat,Windows::Phone::Restricted::Cellular::Rcs::RcsChatMultipartMessageFileTransferProgressUpdatedEventArgs,RcsChatMultipartMessageFileTransferProgressUpdateNotificationArgs>::_PublishNotifications(
            a1 - 8,
            v13);
          v8 = 0;
          goto LABEL_11;
        }
        v9 = 193;
      }
      else
      {
        v9 = 191;
      }
    }
    else
    {
      v9 = 189;
    }
  }
  else
  {
    v9 = 188;
  }
  Log_HREvent_102(
    (unsigned int)v7,
    1,
    "onecoreuap\\base\\appmodel\\messagingom\\utils\\rcsserviceadapter\\lib\\rcschatadapterimpl.cpp",
    v9);
LABEL_11:
  WindowsDeleteString(string[0]);
  return v8;
}

```

## disassembly

```asm
0x1800c2620  mov     [rsp-8+arg_8], rbx
0x1800c2625  push    rbp
0x1800c2626  push    rsi
0x1800c2627  push    rdi
0x1800c2628  lea     rbp, [rsp-90h]
0x1800c2630  sub     rsp, 190h
0x1800c2637  mov     rax, cs:__security_cookie
0x1800c263e  xor     rax, rsp
0x1800c2641  mov     [rbp+0A0h+var_20], rax
0x1800c2648  mov     rdi, r8
0x1800c264b  mov     qword ptr [rbp+0A0h+var_30], 0
0x1800c2653  mov     rsi, rcx
0x1800c2656  mov     qword ptr [rbp+0A0h+var_30+8], 0
0x1800c265e  xorps   xmm0, xmm0
0x1800c2661  lea     rcx, [rbp+0A0h+pszDest]; void *
0x1800c2665  mov     r8d, 80h; Size
0x1800c266b  xor     edx, edx; Val
0x1800c266d  movups  [rbp+0A0h+var_40], xmm0
0x1800c2671  call    memset_0
0x1800c2676  mov     rax, [rsi+0A0h]
0x1800c267d  xor     ecx, ecx; string
0x1800c267f  mov     qword ptr [rbp+0A0h+var_40], rax
0x1800c2683  mov     rax, [rsi+0A8h]
0x1800c268a  mov     qword ptr [rbp+0A0h+var_40+8], rax
0x1800c268e  mov     rax, [rdi]
0x1800c2691  mov     [rsp+1A0h+string], 0
0x1800c269a  mov     rbx, [rax+38h]
0x1800c269e  call    cs:__imp_WindowsDeleteString
0x1800c26a4  lea     rdx, [rsp+1A0h+string]
0x1800c26a9  mov     [rsp+1A0h+string], 0
0x1800c26b2  mov     rcx, rdi
0x1800c26b5  mov     rax, rbx
0x1800c26b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c26bd  mov     ebx, eax
0x1800c26bf  test    eax, eax
0x1800c26c1  jns     short loc_1800C26CB
0x1800c26c3  mov     r9d, 0BCh
0x1800c26c9  jmp     short loc_1800C26F5
0x1800c26cb  mov     rcx, [rsp+1A0h+string]; string
0x1800c26d0  xor     edx, edx; length
0x1800c26d2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800c26d8  mov     edx, 40h ; '@'; cchDest
0x1800c26dd  lea     rcx, [rbp+0A0h+pszDest]; pszDest
0x1800c26e1  mov     r8, rax; pszSrc
0x1800c26e4  call    StringCchCopyW
0x1800c26e9  mov     ebx, eax
0x1800c26eb  test    eax, eax
0x1800c26ed  jns     short loc_1800C270D
0x1800c26ef  mov     r9d, 0BDh
0x1800c26f5  lea     r8, aOnecoreuapBase_35; "onecoreuap\\base\\appmodel\\messagingom"...
0x1800c26fc  mov     edx, 1
0x1800c2701  mov     ecx, eax
0x1800c2703  call    Log_HREvent_102
0x1800c2708  jmp     loc_1800C27B3
0x1800c270d  mov     rax, [rdi]
0x1800c2710  lea     rdx, [rbp+0A0h+var_30]
0x1800c2714  mov     rcx, rdi
0x1800c2717  mov     rax, [rax+40h]
0x1800c271b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2720  mov     ebx, eax
0x1800c2722  test    eax, eax
0x1800c2724  jns     short loc_1800C272E
0x1800c2726  mov     r9d, 0BFh
0x1800c272c  jmp     short loc_1800C26F5
0x1800c272e  mov     rax, [rdi]
0x1800c2731  lea     rdx, [rbp+0A0h+var_30+8]
0x1800c2735  mov     rcx, rdi
0x1800c2738  mov     rax, [rax+48h]
0x1800c273c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c2741  mov     ebx, eax
0x1800c2743  test    eax, eax
0x1800c2745  jns     short loc_1800C274F
0x1800c2747  mov     r9d, 0C1h
0x1800c274d  jmp     short loc_1800C26F5
0x1800c274f  movaps  xmm0, xmmword ptr [rbp+0A0h+pszDest]
0x1800c2753  lea     rcx, [rsi-8]
0x1800c2757  movaps  xmm1, [rbp+0A0h+var_B0]
0x1800c275b  lea     rdx, [rsp+1A0h+var_160]
0x1800c2760  movups  [rsp+1A0h+var_160], xmm0
0x1800c2765  movaps  xmm0, [rbp+0A0h+var_A0]
0x1800c2769  movups  [rsp+1A0h+var_150], xmm1
0x1800c276e  movaps  xmm1, [rbp+0A0h+var_90]
0x1800c2772  movups  [rsp+1A0h+var_140], xmm0
0x1800c2777  movaps  xmm0, [rbp+0A0h+var_80]
0x1800c277b  movups  [rsp+1A0h+var_130], xmm1
0x1800c2780  movaps  xmm1, [rbp+0A0h+var_70]
0x1800c2784  movups  [rbp+0A0h+var_120], xmm0
0x1800c2788  movaps  xmm0, [rbp+0A0h+var_60]
0x1800c278c  movups  [rbp+0A0h+var_110], xmm1
0x1800c2790  movaps  xmm1, [rbp+0A0h+var_50]
0x1800c2794  movups  [rbp+0A0h+var_100], xmm0
0x1800c2798  movaps  xmm0, [rbp+0A0h+var_40]
0x1800c279c  movups  [rbp+0A0h+var_F0], xmm1
0x1800c27a0  movaps  xmm1, [rbp+0A0h+var_30]
0x1800c27a4  movups  [rbp+0A0h+var_E0], xmm0
0x1800c27a8  movups  [rbp+0A0h+var_D0], xmm1
0x1800c27ac  call    ?_PublishNotifications@?$RcsEventHandler@VRcsChat@Rcs@Cellular@Restricted@Phone@Windows@@UIRcsChat@23456@VRcsChatMultipartMessageFileTransferProgressUpdatedEventArgs@23456@URcsChatMultipartMessageFileTransferProgressUpdateNotificationArgs@@@@IEAAXURcsChatMultipartMessageFileTransferProgressUpdateNotificationArgs@@@Z; RcsEventHandler<Windows::Phone::Restricted::Cellular::Rcs::RcsChat,Windows::Phone::Restricted::Cellular::Rcs::IRcsChat,Windows::Phone::Restricted::Cellular::Rcs::RcsChatMultipartMessageFileTransferProgressUpdatedEventArgs,RcsChatMultipartMessageFileTransferProgressUpdateNotificationArgs>::_PublishNotifications(RcsChatMultipartMessageFileTransferProgressUpdateNotificationArgs)
0x1800c27b1  xor     ebx, ebx
0x1800c27b3  mov     rcx, [rsp+1A0h+string]; string
0x1800c27b8  call    cs:__imp_WindowsDeleteString
0x1800c27be  mov     eax, ebx
0x1800c27c0  mov     rcx, [rbp+0A0h+var_20]
0x1800c27c7  xor     rcx, rsp; StackCookie
0x1800c27ca  call    __security_check_cookie
0x1800c27cf  mov     rbx, [rsp+1A0h+arg_8]
0x1800c27d7  add     rsp, 190h
0x1800c27de  pop     rdi
0x1800c27df  pop     rsi
0x1800c27e0  pop     rbp
0x1800c27e1  retn
```
