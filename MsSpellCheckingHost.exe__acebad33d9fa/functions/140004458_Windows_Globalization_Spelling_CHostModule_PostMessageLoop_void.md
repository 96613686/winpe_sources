# Windows::Globalization::Spelling::CHostModule::PostMessageLoop(void)

- ea: `0x140004458`
- end: `0x1400046e1`
- name: `?PostMessageLoop@CHostModule@Spelling@Globalization@Windows@@QEAAJXZ`
- size: `649`
- prototype: `__int64 __fastcall(Windows::Globalization::Spelling::CHostModule *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14000584c`

## callees

- `0x140004458`
- `0x140005ba4`
- `0x140006af0`
- `0x140013010`

## import_xrefs

- `USER32!DispatchMessageW` at `0x1400044ea`
- `USER32!DispatchMessageW` at `0x14000456b`
- `USER32!DispatchMessageW` at `0x1400045de`
- `USER32!DispatchMessageW` at `0x1400044ea`
- `USER32!DispatchMessageW` at `0x14000456b`
- `USER32!DispatchMessageW` at `0x1400045de`
- `USER32!TranslateMessage` at `0x1400044e0`
- `USER32!TranslateMessage` at `0x140004561`
- `USER32!TranslateMessage` at `0x1400045d4`
- `USER32!TranslateMessage` at `0x1400044e0`
- `USER32!TranslateMessage` at `0x140004561`
- `USER32!TranslateMessage` at `0x1400045d4`
- `USER32!GetMessageW` at `0x1400044fc`
- `USER32!GetMessageW` at `0x14000457d`
- `USER32!GetMessageW` at `0x1400045f0`
- `USER32!GetMessageW` at `0x1400044fc`
- `USER32!GetMessageW` at `0x14000457d`
- `USER32!GetMessageW` at `0x1400045f0`
- `USER32!PostThreadMessageW` at `0x140004525`
- `USER32!PostThreadMessageW` at `0x140004525`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140004635`
- `api-ms-win-core-com-l1-1-0!CoRevokeClassObject` at `0x140004635`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000449e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000452f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400046a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000449e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000452f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400046a3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000466e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000467b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004688`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400046bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000466e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000467b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140004688`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400046bf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400045ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004695`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1400045ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x140004695`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004472`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004472`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000465c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400046d0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x14000465c`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400046d0`

## pseudocode

```c
__int64 __fastcall Windows::Globalization::Spelling::CHostModule::PostMessageLoop(
        Windows::Globalization::Spelling::CHostModule *this)
{
  signed int started; // ebx
  char v2; // di
  DWORD v3; // eax
  Windows::Globalization::Spelling::CHostModule *v4; // rcx
  signed int LastError; // eax
  signed int v6; // eax
  Windows::Globalization::Spelling::CHostModule *v7; // rcx
  char v8; // cl
  struct ATL::_ATL_OBJMAP_ENTRY30 **v9; // rsi
  int v10; // edi
  __int64 *v11; // rax
  DWORD v12; // ecx
  signed int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  MSG Msg; // [rsp+20h] [rbp-38h] BYREF

  started = 0;
LABEL_2:
  v2 = 0;
  do
  {
    v3 = WaitForSingleObject(hMutex, 0);
    if ( v3 )
    {
      switch ( v3 )
      {
        case 0x80u:
          started = -2147024161;
          goto LABEL_2;
        case 0x102u:
          started = Windows::Globalization::Spelling::CHostModule::StartTimeoutMonitor(v4);
          if ( started >= 0 )
          {
            memset(&Msg, 0, sizeof(Msg));
            while ( GetMessageW(&Msg, 0, 0, 0) > 0 )
            {
              TranslateMessage(&Msg);
              DispatchMessageW(&Msg);
            }
          }
          break;
        case 0xFFFFFFFF:
          LastError = GetLastError();
          started = LastError;
          if ( LastError > 0 )
            started = (unsigned __int16)LastError | 0x80070000;
          break;
        default:
          started = -2147418113;
          goto LABEL_2;
      }
    }
    else
    {
      if ( !PostThreadMessageW(idThread, 0x12u, 0, 0) )
      {
        v6 = GetLastError();
        started = v6;
        if ( v6 > 0 )
          started = (unsigned __int16)v6 | 0x80070000;
      }
      if ( started >= 0 )
      {
        memset(&Msg, 0, sizeof(Msg));
        while ( GetMessageW(&Msg, 0, 0, 0) > 0 )
        {
          TranslateMessage(&Msg);
          DispatchMessageW(&Msg);
        }
        if ( (*(unsigned int (__fastcall **)(void *))(Windows::Globalization::Spelling::_AtlModule + 24LL))(&Windows::Globalization::Spelling::_AtlModule) )
        {
          ReleaseMutex(hMutex);
          started = Windows::Globalization::Spelling::CHostModule::StartTimeoutMonitor(v7);
          if ( started >= 0 )
          {
            memset(&Msg, 0, sizeof(Msg));
            while ( GetMessageW(&Msg, 0, 0, 0) > 0 )
            {
              TranslateMessage(&Msg);
              DispatchMessageW(&Msg);
            }
          }
        }
        else
        {
          v2 = 1;
        }
      }
    }
    v8 = 0;
    if ( started >= 0 )
      v8 = v2;
    v2 = v8;
  }
  while ( !v8 );
  v9 = off_14001B2E0;
  v10 = 0;
  v11 = off_14001B2E8;
  while ( v9 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v11 && !v10 )
  {
    if ( *v9 )
    {
      v12 = *((_DWORD *)*v9 + 10);
      if ( v12 )
      {
        v10 = CoRevokeClassObject(v12);
        v11 = off_14001B2E8;
      }
    }
    ++v9;
  }
  if ( byte_14001C030 )
    Sleep(dwMilliseconds);
  if ( started < 0 )
    v10 = started;
  CloseHandle(*(&xmmword_14001C040 + 1));
  CloseHandle(hObject);
  CloseHandle(xmmword_14001C040);
  if ( !ReleaseMutex(hMutex) && v10 >= 0 )
  {
    v13 = GetLastError();
    v10 = v13;
    if ( v13 > 0 )
      v10 = (unsigned __int16)v13 | 0x80070000;
  }
  CloseHandle(hMutex);
  McGenEventUnregister_EventUnregister(v15, v14, v16, v17, Msg.hwnd, *(_QWORD *)&Msg.message);
  Sleep(dword_14001C06C);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x140004458  push    rbp
0x14000445a  push    rbx
0x14000445b  push    rsi
0x14000445c  push    rdi
0x14000445d  mov     rbp, rsp
0x140004460  sub     rsp, 58h
0x140004464  xor     ebx, ebx
0x140004466  xor     dil, dil
0x140004469  mov     rcx, cs:hMutex; hHandle
0x140004470  xor     edx, edx; dwMilliseconds
0x140004472  call    cs:__imp_WaitForSingleObject
0x140004478  test    eax, eax
0x14000447a  jz      loc_140004515
0x140004480  cmp     eax, 80h
0x140004485  jz      loc_14000450B
0x14000448b  cmp     eax, 102h
0x140004490  jz      short loc_1400044BC
0x140004492  cmp     eax, 0FFFFFFFFh
0x140004495  jz      short loc_14000449E
0x140004497  mov     ebx, 8000FFFFh
0x14000449c  jmp     short loc_140004466
0x14000449e  call    cs:__imp_GetLastError
0x1400044a4  mov     ebx, eax
0x1400044a6  test    eax, eax
0x1400044a8  jle     loc_1400045FA
0x1400044ae  movzx   ebx, ax
0x1400044b1  or      ebx, 80070000h
0x1400044b7  jmp     loc_1400045FA
0x1400044bc  call    ?StartTimeoutMonitor@CHostModule@Spelling@Globalization@Windows@@QEAAJXZ; Windows::Globalization::Spelling::CHostModule::StartTimeoutMonitor(void)
0x1400044c1  mov     ebx, eax
0x1400044c3  test    eax, eax
0x1400044c5  js      loc_1400045FA
0x1400044cb  xorps   xmm0, xmm0
0x1400044ce  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x1400044d2  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x1400044d6  movups  xmmword ptr [rbp+Msg.time], xmm0
0x1400044da  jmp     short loc_1400044F0
0x1400044dc  lea     rcx, [rbp+Msg]; lpMsg
0x1400044e0  call    cs:__imp_TranslateMessage
0x1400044e6  lea     rcx, [rbp+Msg]; lpMsg
0x1400044ea  call    cs:__imp_DispatchMessageW
0x1400044f0  xor     r9d, r9d; wMsgFilterMax
0x1400044f3  lea     rcx, [rbp+Msg]; lpMsg
0x1400044f7  xor     r8d, r8d; wMsgFilterMin
0x1400044fa  xor     edx, edx; hWnd
0x1400044fc  call    cs:__imp_GetMessageW
0x140004502  test    eax, eax
0x140004504  jg      short loc_1400044DC
0x140004506  jmp     loc_1400045FA
0x14000450b  mov     ebx, 800702DFh
0x140004510  jmp     loc_140004466
0x140004515  mov     ecx, cs:idThread; idThread
0x14000451b  xor     r9d, r9d; lParam
0x14000451e  xor     r8d, r8d; wParam
0x140004521  lea     edx, [r9+12h]; Msg
0x140004525  call    cs:__imp_PostThreadMessageW
0x14000452b  test    eax, eax
0x14000452d  jnz     short loc_140004544
0x14000452f  call    cs:__imp_GetLastError
0x140004535  mov     ebx, eax
0x140004537  test    eax, eax
0x140004539  jle     short loc_140004544
0x14000453b  movzx   ebx, ax
0x14000453e  or      ebx, 80070000h
0x140004544  test    ebx, ebx
0x140004546  js      loc_1400045FA
0x14000454c  xorps   xmm0, xmm0
0x14000454f  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x140004553  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x140004557  movups  xmmword ptr [rbp+Msg.time], xmm0
0x14000455b  jmp     short loc_140004571
0x14000455d  lea     rcx, [rbp+Msg]; lpMsg
0x140004561  call    cs:__imp_TranslateMessage
0x140004567  lea     rcx, [rbp+Msg]; lpMsg
0x14000456b  call    cs:__imp_DispatchMessageW
0x140004571  xor     r9d, r9d; wMsgFilterMax
0x140004574  lea     rcx, [rbp+Msg]; lpMsg
0x140004578  xor     r8d, r8d; wMsgFilterMin
0x14000457b  xor     edx, edx; hWnd
0x14000457d  call    cs:__imp_GetMessageW
0x140004583  test    eax, eax
0x140004585  jg      short loc_14000455D
0x140004587  mov     rax, cs:?_AtlModule@Spelling@Globalization@Windows@@3VCHostModule@123@A; Windows::Globalization::Spelling::CHostModule Windows::Globalization::Spelling::_AtlModule
0x14000458e  lea     rcx, ?_AtlModule@Spelling@Globalization@Windows@@3VCHostModule@123@A; Windows::Globalization::Spelling::CHostModule Windows::Globalization::Spelling::_AtlModule
0x140004595  mov     rax, [rax+18h]
0x140004599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000459e  test    eax, eax
0x1400045a0  jnz     short loc_1400045A7
0x1400045a2  mov     dil, 1
0x1400045a5  jmp     short loc_1400045FA
0x1400045a7  mov     rcx, cs:hMutex; hMutex
0x1400045ae  call    cs:__imp_ReleaseMutex
0x1400045b4  call    ?StartTimeoutMonitor@CHostModule@Spelling@Globalization@Windows@@QEAAJXZ; Windows::Globalization::Spelling::CHostModule::StartTimeoutMonitor(void)
0x1400045b9  mov     ebx, eax
0x1400045bb  test    eax, eax
0x1400045bd  js      short loc_1400045FA
0x1400045bf  xorps   xmm0, xmm0
0x1400045c2  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x1400045c6  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x1400045ca  movups  xmmword ptr [rbp+Msg.time], xmm0
0x1400045ce  jmp     short loc_1400045E4
0x1400045d0  lea     rcx, [rbp+Msg]; lpMsg
0x1400045d4  call    cs:__imp_TranslateMessage
0x1400045da  lea     rcx, [rbp+Msg]; lpMsg
0x1400045de  call    cs:__imp_DispatchMessageW
0x1400045e4  xor     r9d, r9d; wMsgFilterMax
0x1400045e7  lea     rcx, [rbp+Msg]; lpMsg
0x1400045eb  xor     r8d, r8d; wMsgFilterMin
0x1400045ee  xor     edx, edx; hWnd
0x1400045f0  call    cs:__imp_GetMessageW
0x1400045f6  test    eax, eax
0x1400045f8  jg      short loc_1400045D0
0x1400045fa  xor     ecx, ecx
0x1400045fc  movzx   eax, dil
0x140004600  test    ebx, ebx
0x140004602  cmovns  ecx, eax
0x140004605  mov     dil, cl
0x140004608  test    cl, cl
0x14000460a  jz      loc_140004469
0x140004610  mov     rsi, cs:off_14001B2E0
0x140004617  xor     edi, edi
0x140004619  mov     rax, cs:off_14001B2E8
0x140004620  jmp     short loc_140004648
0x140004622  test    edi, edi
0x140004624  jnz     short loc_14000464D
0x140004626  mov     rcx, [rsi]
0x140004629  test    rcx, rcx
0x14000462c  jz      short loc_140004644
0x14000462e  mov     ecx, [rcx+28h]; dwRegister
0x140004631  test    ecx, ecx
0x140004633  jz      short loc_140004644
0x140004635  call    cs:__imp_CoRevokeClassObject
0x14000463b  mov     edi, eax
0x14000463d  mov     rax, cs:off_14001B2E8
0x140004644  add     rsi, 8
0x140004648  cmp     rsi, rax
0x14000464b  jb      short loc_140004622
0x14000464d  cmp     cs:byte_14001C030, 0
0x140004654  jz      short loc_140004662
0x140004656  mov     ecx, cs:dwMilliseconds; dwMilliseconds
0x14000465c  call    cs:__imp_Sleep
0x140004662  mov     rcx, qword ptr cs:xmmword_14001C040+8; hObject
0x140004669  test    ebx, ebx
0x14000466b  cmovs   edi, ebx
0x14000466e  call    cs:__imp_CloseHandle
0x140004674  mov     rcx, cs:hObject; hObject
0x14000467b  call    cs:__imp_CloseHandle
0x140004681  mov     rcx, qword ptr cs:xmmword_14001C040; hObject
0x140004688  call    cs:__imp_CloseHandle
0x14000468e  mov     rcx, cs:hMutex; hMutex
0x140004695  call    cs:__imp_ReleaseMutex
0x14000469b  test    eax, eax
0x14000469d  jnz     short loc_1400046B8
0x14000469f  test    edi, edi
0x1400046a1  js      short loc_1400046B8
0x1400046a3  call    cs:__imp_GetLastError
0x1400046a9  mov     edi, eax
0x1400046ab  test    eax, eax
0x1400046ad  jle     short loc_1400046B8
0x1400046af  movzx   edi, ax
0x1400046b2  or      edi, 80070000h
0x1400046b8  mov     rcx, cs:hMutex; hObject
0x1400046bf  call    cs:__imp_CloseHandle
0x1400046c5  call    McGenEventUnregister_EventUnregister
0x1400046ca  mov     ecx, cs:dword_14001C06C; dwMilliseconds
0x1400046d0  call    cs:__imp_Sleep
0x1400046d6  mov     eax, edi
0x1400046d8  add     rsp, 58h
0x1400046dc  pop     rdi
0x1400046dd  pop     rsi
0x1400046de  pop     rbx
0x1400046df  pop     rbp
0x1400046e0  retn
```
