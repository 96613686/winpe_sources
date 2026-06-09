# AuthHostWebInstance::Run(void)

- ea: `0x140005940`
- end: `0x140005d61`
- name: `?Run@AuthHostWebInstance@@QEAAJXZ`
- size: `1057`
- prototype: `__int64 __fastcall(AuthHostWebInstance *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140006418`

## callees

- `0x140002c70`
- `0x140002c98`
- `0x1400055d0`
- `0x140005940`
- `0x140006280`
- `0x14000685c`
- `0x140006bfc`
- `0x140008244`
- `0x140008450`
- `0x14000b6f0`
- `0x14000bb4c`
- `0x140014010`

## import_xrefs

- `ext-ms-win-ntuser-message-l1-1-0!RegisterWindowMessageW` at `0x140005962`
- `ext-ms-win-ntuser-message-l1-1-0!RegisterWindowMessageW` at `0x140005971`
- `ext-ms-win-ntuser-message-l1-1-0!RegisterWindowMessageW` at `0x140005981`
- `ext-ms-win-ntuser-message-l1-1-0!RegisterWindowMessageW` at `0x140005962`
- `ext-ms-win-ntuser-message-l1-1-0!RegisterWindowMessageW` at `0x140005971`
- `ext-ms-win-ntuser-message-l1-1-0!RegisterWindowMessageW` at `0x140005981`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x140005aa5`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x140005b0f`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x140005bd3`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x140005aa5`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x140005b0f`
- `ext-ms-win-ntuser-message-l1-1-0!PeekMessageW` at `0x140005bd3`
- `ext-ms-win-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x1400059b3`
- `ext-ms-win-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x140005a8b`
- `ext-ms-win-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x1400059b3`
- `ext-ms-win-ntuser-synch-l1-1-0!MsgWaitForMultipleObjects` at `0x140005a8b`
- `ext-ms-win-ntuser-window-l1-1-2!KillTimer` at `0x140005b4d`
- `ext-ms-win-ntuser-window-l1-1-2!KillTimer` at `0x140005b4d`

## string_xrefs

- `0x140005968`: `AuthHost_DownloadComplete`

## pseudocode

```c
__int64 __fastcall AuthHostWebInstance::Run(AuthHostWebInstance *this)
{
  UINT v2; // esi
  UINT v3; // r14d
  UINT v4; // eax
  UINT v5; // r15d
  unsigned int v6; // eax
  PVOID *v7; // rcx
  char v8; // di
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  tagMSG Msg; // [rsp+30h] [rbp-38h] BYREF
  HANDLE pHandles; // [rsp+A8h] [rbp+40h] BYREF

  pHandles = 0;
  v2 = RegisterWindowMessageW(L"AuthHost_ScaleChanged");
  v3 = RegisterWindowMessageW(L"AuthHost_DownloadComplete");
  v4 = RegisterWindowMessageW(L"AuthHost_SetFormCredential");
  pHandles = StartNavigationEvent;
  v5 = v4;
  while ( MsgWaitForMultipleObjects(1u, &pHandles, 0, 0xFFFFFFFF, 0x1CFFu) )
  {
    v6 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 88) + 56LL))(*((_QWORD *)this + 88), 0);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 25, &WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids, v6);
    }
  }
  v7 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 24, &WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids);
      v7 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 68) & 2) != 0 && *((_BYTE *)v7 + 65) >= 5u )
      WPP_SF_(v7[7], 26, &WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids);
  }
  AuthHostWebInstance::Navigate(this);
  v8 = 1;
  do
  {
    memset(&Msg, 0, sizeof(Msg));
    MsgWaitForMultipleObjects(0, 0, 0, 0xFFFFFFFF, 0x1CFFu);
    while ( PeekMessageW(&Msg, 0, 0, 0, 0) )
    {
      if ( Msg.message == 18 || Msg.message == v2 || Msg.message == v3 || Msg.message == v5 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
        {
          WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 7), 27);
        }
        if ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
        {
          if ( Msg.message == 18 )
          {
            if ( *((_DWORD *)this + 127) )
            {
              (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 13) + 136LL))(
                *((_QWORD *)this + 13),
                *((_QWORD *)this + 65),
                *((_QWORD *)this + 66),
                *((_QWORD *)this + 67));
            }
            else if ( *((_DWORD *)this + 128) )
            {
              (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 13) + 168LL))(
                *((_QWORD *)this + 13),
                *((_QWORD *)this + 65),
                *((_QWORD *)this + 66));
            }
            v8 = 0;
            break;
          }
          if ( Msg.message == v2 )
          {
            if ( (Msg.wParam & 1) != 0 )
            {
              AuthHostWebInstance::UpdateZoomFromScaleFactor(this);
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                28,
                &WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids,
                LODWORD(Msg.wParam));
            }
          }
          else if ( Msg.message == v3 )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, &WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids);
            }
            AuthHostWebInstance::UpdateBrokerLogo((HSTRING *)this);
          }
          else if ( Msg.message == v5 )
          {
            AuthHostWebInstance::SetFormCredential(this, (struct _SET_FORM_CREDENTIAL_PARAM *)Msg.lParam);
          }
        }
      }
      else if ( Msg.message == 275 && (v9 = *((_QWORD *)this + 62)) != 0 && Msg.wParam == v9 )
      {
        PeekMessageW(&Msg, 0, 0, 0, 1u);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
        {
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 7), v10, v11, *((_QWORD *)this + 62));
        }
        KillTimer(0, *((_QWORD *)this + 62));
        *((_QWORD *)this + 62) = 0;
        AuthHostWebInstance::SetBrokerToFallback(this);
      }
      else
      {
        (*(void (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 88) + 56LL))(*((_QWORD *)this + 88), 1);
      }
    }
  }
  while ( v8 );
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 31, &WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids);
  }
  AuthHostWebInstance::UninitializeWindowEvents(this);
  return 0;
}

```

## disassembly

```asm
0x140005940  push    rbp
0x140005942  push    rbx
0x140005943  push    rsi
0x140005944  push    rdi
0x140005945  push    r14
0x140005947  push    r15
0x140005949  mov     rbp, rsp
0x14000594c  sub     rsp, 68h
0x140005950  mov     rbx, rcx
0x140005953  mov     [rbp+pHandles], 0
0x14000595b  lea     rcx, aAuthhostScalec; "AuthHost_ScaleChanged"
0x140005962  call    cs:__imp_RegisterWindowMessageW
0x140005968  lea     rcx, aAuthhostDownlo; "AuthHost_DownloadComplete"
0x14000596f  mov     esi, eax
0x140005971  call    cs:__imp_RegisterWindowMessageW
0x140005977  lea     rcx, String; "AuthHost_SetFormCredential"
0x14000597e  mov     r14d, eax
0x140005981  call    cs:__imp_RegisterWindowMessageW
0x140005987  mov     rdx, cs:?StartNavigationEvent@@3PEAXEA; void * StartNavigationEvent
0x14000598e  lea     rdi, WPP_GLOBAL_Control
0x140005995  mov     [rbp+pHandles], rdx
0x140005999  mov     r15d, eax
0x14000599c  xor     r8d, r8d; fWaitAll
0x14000599f  mov     [rsp+68h+dwWakeMask], 1CFFh; dwWakeMask
0x1400059a7  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1400059ab  lea     rdx, [rbp+pHandles]; pHandles
0x1400059af  lea     ecx, [r8+1]; nCount
0x1400059b3  call    cs:__imp_MsgWaitForMultipleObjects
0x1400059b9  test    eax, eax
0x1400059bb  jz      short loc_140005A04
0x1400059bd  mov     rcx, [rbx+2C0h]
0x1400059c4  xor     edx, edx
0x1400059c6  mov     rax, [rcx]
0x1400059c9  mov     rax, [rax+38h]
0x1400059cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400059d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400059d9  cmp     rcx, rdi
0x1400059dc  jz      short loc_14000599C
0x1400059de  test    byte ptr [rcx+44h], 2
0x1400059e2  jz      short loc_14000599C
0x1400059e4  cmp     byte ptr [rcx+41h], 5
0x1400059e8  jb      short loc_14000599C
0x1400059ea  mov     rcx, [rcx+38h]
0x1400059ee  lea     r8, WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids
0x1400059f5  mov     edx, 19h
0x1400059fa  mov     r9d, eax
0x1400059fd  call    WPP_SF_d
0x140005a02  jmp     short loc_14000599C
0x140005a04  mov     rcx, cs:WPP_GLOBAL_Control
0x140005a0b  cmp     rcx, rdi
0x140005a0e  jz      short loc_140005A5E
0x140005a10  test    byte ptr [rcx+44h], 2
0x140005a14  jz      short loc_140005A38
0x140005a16  cmp     byte ptr [rcx+41h], 4
0x140005a1a  jb      short loc_140005A38
0x140005a1c  mov     rcx, [rcx+38h]
0x140005a20  lea     r8, WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids
0x140005a27  mov     edx, 18h
0x140005a2c  call    WPP_SF_
0x140005a31  mov     rcx, cs:WPP_GLOBAL_Control
0x140005a38  cmp     rcx, rdi
0x140005a3b  jz      short loc_140005A5E
0x140005a3d  test    byte ptr [rcx+44h], 2
0x140005a41  jz      short loc_140005A5E
0x140005a43  cmp     byte ptr [rcx+41h], 5
0x140005a47  jb      short loc_140005A5E
0x140005a49  mov     rcx, [rcx+38h]
0x140005a4d  lea     r8, WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids
0x140005a54  mov     edx, 1Ah
0x140005a59  call    WPP_SF_
0x140005a5e  mov     rcx, rbx; this
0x140005a61  call    ?Navigate@AuthHostWebInstance@@QEAAJXZ; AuthHostWebInstance::Navigate(void)
0x140005a66  mov     dil, 1
0x140005a69  xorps   xmm0, xmm0
0x140005a6c  mov     [rsp+68h+dwWakeMask], 1CFFh; dwWakeMask
0x140005a74  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x140005a78  xor     r8d, r8d; fWaitAll
0x140005a7b  xor     edx, edx; pHandles
0x140005a7d  xor     ecx, ecx; nCount
0x140005a7f  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x140005a83  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x140005a87  movups  xmmword ptr [rbp+Msg.time], xmm0
0x140005a8b  call    cs:__imp_MsgWaitForMultipleObjects
0x140005a91  xor     r9d, r9d; wMsgFilterMax
0x140005a94  mov     [rsp+68h+dwWakeMask], 0; wRemoveMsg
0x140005a9c  xor     r8d, r8d; wMsgFilterMin
0x140005a9f  lea     rcx, [rbp+Msg]; lpMsg
0x140005aa3  xor     edx, edx; hWnd
0x140005aa5  call    cs:__imp_PeekMessageW
0x140005aab  test    eax, eax
0x140005aad  jz      loc_140005D0D
0x140005ab3  mov     r9d, [rbp+Msg.message]
0x140005ab7  cmp     r9d, 12h
0x140005abb  jz      loc_140005B88
0x140005ac1  cmp     r9d, esi
0x140005ac4  jz      loc_140005B88
0x140005aca  cmp     r9d, r14d
0x140005acd  jz      loc_140005B88
0x140005ad3  cmp     r9d, r15d
0x140005ad6  jz      loc_140005B88
0x140005adc  cmp     r9d, 113h
0x140005ae3  jnz     loc_140005B6B
0x140005ae9  mov     rax, [rbx+1F0h]
0x140005af0  test    rax, rax
0x140005af3  jz      short loc_140005B6B
0x140005af5  cmp     [rbp+Msg.wParam], rax
0x140005af9  jnz     short loc_140005B6B
0x140005afb  xor     r9d, r9d; wMsgFilterMax
0x140005afe  mov     [rsp+68h+dwWakeMask], 1; wRemoveMsg
0x140005b06  xor     r8d, r8d; wMsgFilterMin
0x140005b09  lea     rcx, [rbp+Msg]; lpMsg
0x140005b0d  xor     edx, edx; hWnd
0x140005b0f  call    cs:__imp_PeekMessageW
0x140005b15  mov     rcx, cs:WPP_GLOBAL_Control
0x140005b1c  lea     rax, WPP_GLOBAL_Control
0x140005b23  cmp     rcx, rax
0x140005b26  jz      short loc_140005B44
0x140005b28  test    byte ptr [rcx+44h], 2
0x140005b2c  jz      short loc_140005B44
0x140005b2e  cmp     byte ptr [rcx+41h], 4
0x140005b32  jb      short loc_140005B44
0x140005b34  mov     r9, [rbx+1F0h]
0x140005b3b  mov     rcx, [rcx+38h]
0x140005b3f  call    WPP_SF_q
0x140005b44  mov     rdx, [rbx+1F0h]; uIDEvent
0x140005b4b  xor     ecx, ecx; hWnd
0x140005b4d  call    cs:__imp_KillTimer
0x140005b53  mov     rcx, rbx; this
0x140005b56  mov     qword ptr [rbx+1F0h], 0
0x140005b61  call    ?SetBrokerToFallback@AuthHostWebInstance@@AEAAXXZ; AuthHostWebInstance::SetBrokerToFallback(void)
0x140005b66  jmp     loc_140005A91
0x140005b6b  mov     rcx, [rbx+2C0h]
0x140005b72  mov     edx, 1
0x140005b77  mov     rax, [rcx]
0x140005b7a  mov     rax, [rax+38h]
0x140005b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b83  jmp     loc_140005A91
0x140005b88  mov     rcx, cs:WPP_GLOBAL_Control
0x140005b8f  lea     rax, WPP_GLOBAL_Control
0x140005b96  cmp     rcx, rax
0x140005b99  jz      short loc_140005BBF
0x140005b9b  test    byte ptr [rcx+44h], 2
0x140005b9f  jz      short loc_140005BBF
0x140005ba1  cmp     byte ptr [rcx+41h], 5
0x140005ba5  jb      short loc_140005BBF
0x140005ba7  mov     eax, [rbx+1FCh]
0x140005bad  mov     edx, 1Bh
0x140005bb2  mov     rcx, [rcx+38h]
0x140005bb6  mov     [rsp+68h+dwWakeMask], eax
0x140005bba  call    WPP_SF_DD
0x140005bbf  xor     r9d, r9d; wMsgFilterMax
0x140005bc2  mov     [rsp+68h+dwWakeMask], 1; wRemoveMsg
0x140005bca  xor     r8d, r8d; wMsgFilterMin
0x140005bcd  lea     rcx, [rbp+Msg]; lpMsg
0x140005bd1  xor     edx, edx; hWnd
0x140005bd3  call    cs:__imp_PeekMessageW
0x140005bd9  test    eax, eax
0x140005bdb  jz      loc_140005A91
0x140005be1  mov     eax, [rbp+Msg.message]
0x140005be4  cmp     eax, 12h
0x140005be7  jz      loc_140005CAD
0x140005bed  cmp     eax, esi
0x140005bef  jnz     short loc_140005C4D
0x140005bf1  mov     r9d, dword ptr [rbp+Msg.wParam]
0x140005bf5  test    r9b, 1
0x140005bf9  jz      short loc_140005C08
0x140005bfb  mov     rcx, rbx; this
0x140005bfe  call    ?UpdateZoomFromScaleFactor@AuthHostWebInstance@@AEAAXXZ; AuthHostWebInstance::UpdateZoomFromScaleFactor(void)
0x140005c03  jmp     loc_140005A91
0x140005c08  mov     rcx, cs:WPP_GLOBAL_Control
0x140005c0f  lea     rax, WPP_GLOBAL_Control
0x140005c16  cmp     rcx, rax
0x140005c19  jz      loc_140005A91
0x140005c1f  test    byte ptr [rcx+44h], 2
0x140005c23  jz      loc_140005A91
0x140005c29  cmp     byte ptr [rcx+41h], 5
0x140005c2d  jb      loc_140005A91
0x140005c33  mov     rcx, [rcx+38h]
0x140005c37  lea     r8, WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids
0x140005c3e  mov     edx, 1Ch
0x140005c43  call    WPP_SF_d
0x140005c48  jmp     loc_140005A91
0x140005c4d  cmp     eax, r14d
0x140005c50  jnz     short loc_140005C93
0x140005c52  mov     rcx, cs:WPP_GLOBAL_Control
0x140005c59  lea     rax, WPP_GLOBAL_Control
0x140005c60  cmp     rcx, rax
0x140005c63  jz      short loc_140005C86
0x140005c65  test    byte ptr [rcx+44h], 2
0x140005c69  jz      short loc_140005C86
0x140005c6b  cmp     byte ptr [rcx+41h], 4
0x140005c6f  jb      short loc_140005C86
0x140005c71  mov     rcx, [rcx+38h]
0x140005c75  lea     r8, WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids
0x140005c7c  mov     edx, 1Dh
0x140005c81  call    WPP_SF_
0x140005c86  mov     rcx, rbx; this
0x140005c89  call    ?UpdateBrokerLogo@AuthHostWebInstance@@AEAAXXZ; AuthHostWebInstance::UpdateBrokerLogo(void)
0x140005c8e  jmp     loc_140005A91
0x140005c93  cmp     eax, r15d
0x140005c96  jnz     loc_140005A91
0x140005c9c  mov     rdx, [rbp+Msg.lParam]; struct _SET_FORM_CREDENTIAL_PARAM *
0x140005ca0  mov     rcx, rbx; this
0x140005ca3  call    ?SetFormCredential@AuthHostWebInstance@@QEAAJPEAU_SET_FORM_CREDENTIAL_PARAM@@@Z; AuthHostWebInstance::SetFormCredential(_SET_FORM_CREDENTIAL_PARAM *)
0x140005ca8  jmp     loc_140005A91
0x140005cad  cmp     dword ptr [rbx+1FCh], 0
0x140005cb4  jz      short loc_140005CE0
0x140005cb6  mov     rcx, [rbx+68h]
0x140005cba  mov     r9, [rbx+218h]
0x140005cc1  mov     r8, [rbx+210h]
0x140005cc8  mov     rdx, [rbx+208h]
0x140005ccf  mov     rax, [rcx]
0x140005cd2  mov     rax, [rax+88h]
0x140005cd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005cde  jmp     short loc_140005D0A
0x140005ce0  cmp     dword ptr [rbx+200h], 0
0x140005ce7  jz      short loc_140005D0A
0x140005ce9  mov     rcx, [rbx+68h]
0x140005ced  mov     r8, [rbx+210h]
0x140005cf4  mov     rdx, [rbx+208h]
0x140005cfb  mov     rax, [rcx]
0x140005cfe  mov     rax, [rax+0A8h]
0x140005d05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005d0a  xor     dil, dil
0x140005d0d  test    dil, dil
0x140005d10  jnz     loc_140005A69
0x140005d16  mov     rcx, cs:WPP_GLOBAL_Control
0x140005d1d  lea     rax, WPP_GLOBAL_Control
0x140005d24  cmp     rcx, rax
0x140005d27  jz      short loc_140005D4A
0x140005d29  test    byte ptr [rcx+44h], 2
0x140005d2d  jz      short loc_140005D4A
0x140005d2f  cmp     byte ptr [rcx+41h], 5
0x140005d33  jb      short loc_140005D4A
0x140005d35  mov     rcx, [rcx+38h]
0x140005d39  lea     r8, WPP_0796d3d6e744321e50f715e8d649e99c_Traceguids
0x140005d40  mov     edx, 1Fh
0x140005d45  call    WPP_SF_
0x140005d4a  mov     rcx, rbx; this
0x140005d4d  call    ?UninitializeWindowEvents@AuthHostWebInstance@@AEAAXXZ; AuthHostWebInstance::UninitializeWindowEvents(void)
0x140005d52  xor     eax, eax
0x140005d54  add     rsp, 68h
0x140005d58  pop     r15
0x140005d5a  pop     r14
0x140005d5c  pop     rdi
0x140005d5d  pop     rsi
0x140005d5e  pop     rbx
0x140005d5f  pop     rbp
0x140005d60  retn
```
