# D3DCommon::DX9MainLoop(void)

- ea: `0x14007e67c`
- end: `0x14007e907`
- name: `?DX9MainLoop@D3DCommon@@YAJXZ`
- size: `651`
- prototype: `__int64 __fastcall(D3DCommon *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400852f0`

## callees

- `0x14007e67c`
- `0x14007ecbc`
- `0x14007fa4c`
- `0x140081584`
- `0x14008a958`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x14007e73f`
- `KERNEL32!GetTickCount` at `0x14007e73f`
- `KERNEL32!SetWaitableTimer` at `0x14007e7c1`
- `KERNEL32!SetWaitableTimer` at `0x14007e7c1`
- `KERNEL32!CreateWaitableTimerW` at `0x14007e75c`
- `KERNEL32!CreateWaitableTimerW` at `0x14007e75c`
- `KERNEL32!CancelWaitableTimer` at `0x14007e8e5`
- `KERNEL32!CancelWaitableTimer` at `0x14007e8e5`
- `KERNEL32!CloseHandle` at `0x14007e8ef`
- `KERNEL32!CloseHandle` at `0x14007e8ef`
- `KERNEL32!GetLastError` at `0x14007e76e`
- `KERNEL32!GetLastError` at `0x14007e76e`
- `USER32!TranslateMessage` at `0x14007e820`
- `USER32!TranslateMessage` at `0x14007e820`
- `USER32!PeekMessageW` at `0x14007e70e`
- `USER32!PeekMessageW` at `0x14007e812`
- `USER32!PeekMessageW` at `0x14007e70e`
- `USER32!PeekMessageW` at `0x14007e812`
- `USER32!MsgWaitForMultipleObjects` at `0x14007e8cf`
- `USER32!MsgWaitForMultipleObjects` at `0x14007e8cf`
- `USER32!PostMessageW` at `0x14007e7f8`
- `USER32!PostMessageW` at `0x14007e89e`
- `USER32!PostMessageW` at `0x14007e7f8`
- `USER32!PostMessageW` at `0x14007e89e`
- `USER32!DispatchMessageW` at `0x14007e82a`
- `USER32!DispatchMessageW` at `0x14007e82a`

## string_xrefs

- `0x14007e69a`: `D3DCommon::DX9MainLoop`
- `0x14007e6dd`: `D3DCommon::DX9MainLoop`

## pseudocode

```c
__int64 __fastcall D3DCommon::DX9MainLoop(D3DCommon *this)
{
  signed int v2; // ebx
  int v3; // edx
  __int64 v4; // rbx
  signed int LastError; // eax
  char v6; // si
  char v7; // di
  int v8; // edx
  unsigned int *v9; // r9
  tagMSG Msg; // [rsp+30h] [rbp-30h] BYREF
  HANDLE pHandles; // [rsp+80h] [rbp+20h] BYREF
  LARGE_INTEGER DueTime; // [rsp+88h] [rbp+28h] BYREF

  if ( !qword_1401CBA28 )
  {
    D3DCommon::ERR((D3DCommon *)0x6A, (unsigned __int16)L"gs_pState", L"D3DCommon::DX9MainLoop");
    return 2147942487LL;
  }
  memset(&Msg, 0, sizeof(Msg));
  pHandles = 0;
  if ( qword_1401CBA38 )
  {
    PeekMessageW(&Msg, 0, 0, 0, 0);
    dword_1401CBA34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_1401CBA28 + 8LL))(qword_1401CBA28);
    D3DCommon::Render3DEnvironment(0, v3);
    v4 = qword_1401CBA28;
    *(_DWORD *)(v4 + 8) = GetTickCount();
    if ( *(_DWORD *)(qword_1401CBA28 + 56) )
    {
      pHandles = CreateWaitableTimerW(0, 0, 0);
      if ( !pHandles )
      {
        LastError = GetLastError();
        v2 = LastError;
        if ( LastError > 0 )
          v2 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_27;
      }
      DueTime.QuadPart = 0;
      SetWaitableTimer(pHandles, &DueTime, 0x3E8u / *(_DWORD *)(qword_1401CBA28 + 56), 0, 0, 0);
    }
    v6 = 0;
    while ( Msg.message != 18 )
    {
      if ( dword_1401CBAC0 && !v6 )
      {
        v6 = 1;
        PostMessageW(hWnd, 0x8000u, 0, 0);
      }
      if ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
      {
        TranslateMessage(&Msg);
        DispatchMessageW(&Msg);
        v2 = dword_1401C6658;
        if ( dword_1401C6658 < 0 )
          goto LABEL_27;
        v7 = 1;
      }
      else
      {
        v7 = 0;
        if ( D3DCommon::TickTimer::TimeExpired((D3DCommon::TickTimer *)(qword_1401CBA28 + 8)) )
        {
          v2 = D3DCommon::Render3DEnvironment((D3DCommon *)1, v8);
          if ( v2 < 0 )
            goto LABEL_27;
          D3DCommon::LogMessage((D3DCommon *)0x50, dword_1401C0824, 0, v9);
          PostMessageW(hWnd, 0x8000u, 0, 0);
        }
        else
        {
          v2 = D3DCommon::Render3DEnvironment(0, v8);
          if ( v2 < 0 )
            goto LABEL_27;
        }
      }
      if ( pHandles && !v7 )
        MsgWaitForMultipleObjects(1u, &pHandles, 0, 0xFFFFFFFF, 0x1CBFu);
    }
    v2 = 0;
    goto LABEL_27;
  }
  D3DCommon::ERR((D3DCommon *)0x6C, (unsigned __int16)L"gs_pDevice", L"D3DCommon::DX9MainLoop");
  v2 = -2147467261;
LABEL_27:
  if ( pHandles )
  {
    CancelWaitableTimer(pHandles);
    CloseHandle(pHandles);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14007e67c  mov     [rsp-18h+arg_10], rbx
0x14007e681  push    rbp
0x14007e682  push    rsi
0x14007e683  push    rdi
0x14007e684  mov     rbp, rsp
0x14007e687  sub     rsp, 60h
0x14007e68b  cmp     cs:qword_1401CBA28, 0
0x14007e693  jnz     short loc_14007E6B7
0x14007e695  mov     ecx, 6Ah ; 'j'; this
0x14007e69a  lea     r8, aD3dcommonDx9ma; "D3DCommon::DX9MainLoop"
0x14007e6a1  lea     rdx, aGsPstate; "gs_pState"
0x14007e6a8  call    ?ERR@D3DCommon@@YAXGZZ; D3DCommon::ERR(ushort,...)
0x14007e6ad  mov     eax, 80070057h
0x14007e6b2  jmp     loc_14007E8F7
0x14007e6b7  cmp     cs:qword_1401CBA38, 0
0x14007e6bf  xorps   xmm0, xmm0
0x14007e6c2  movups  xmmword ptr [rbp+Msg.hwnd], xmm0
0x14007e6c6  mov     [rbp+pHandles], 0
0x14007e6ce  movups  xmmword ptr [rbp+Msg.wParam], xmm0
0x14007e6d2  movups  xmmword ptr [rbp+Msg.time], xmm0
0x14007e6d6  jnz     short loc_14007E6FA
0x14007e6d8  mov     ecx, 6Ch ; 'l'; this
0x14007e6dd  lea     r8, aD3dcommonDx9ma; "D3DCommon::DX9MainLoop"
0x14007e6e4  lea     rdx, aGsPdevice; "gs_pDevice"
0x14007e6eb  call    ?ERR@D3DCommon@@YAXGZZ; D3DCommon::ERR(ushort,...)
0x14007e6f0  mov     ebx, 80004003h
0x14007e6f5  jmp     loc_14007E8DC
0x14007e6fa  xor     r9d, r9d; wMsgFilterMax
0x14007e6fd  mov     [rsp+60h+wRemoveMsg], 0; wRemoveMsg
0x14007e705  xor     r8d, r8d; wMsgFilterMin
0x14007e708  lea     rcx, [rbp+Msg]; lpMsg
0x14007e70c  xor     edx, edx; hWnd
0x14007e70e  call    cs:__imp_PeekMessageW
0x14007e714  mov     rcx, cs:qword_1401CBA28
0x14007e71b  mov     cs:dword_1401CBA34, 0
0x14007e725  mov     rax, [rcx]
0x14007e728  mov     rax, [rax+8]
0x14007e72c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14007e731  xor     ecx, ecx; this
0x14007e733  call    ?Render3DEnvironment@D3DCommon@@YAJH@Z; D3DCommon::Render3DEnvironment(int)
0x14007e738  mov     rbx, cs:qword_1401CBA28
0x14007e73f  call    cs:__imp_GetTickCount
0x14007e745  mov     [rbx+8], eax
0x14007e748  mov     rax, cs:qword_1401CBA28
0x14007e74f  cmp     dword ptr [rax+38h], 0
0x14007e753  jbe     short loc_14007E7C7
0x14007e755  xor     r8d, r8d; lpTimerName
0x14007e758  xor     edx, edx; bManualReset
0x14007e75a  xor     ecx, ecx; lpTimerAttributes
0x14007e75c  call    cs:__imp_CreateWaitableTimerW
0x14007e762  mov     [rbp+pHandles], rax
0x14007e766  mov     rcx, rax; hTimer
0x14007e769  test    rax, rax
0x14007e76c  jnz     short loc_14007E78C
0x14007e76e  call    cs:__imp_GetLastError
0x14007e774  mov     ebx, eax
0x14007e776  test    eax, eax
0x14007e778  jle     loc_14007E8DC
0x14007e77e  movzx   ebx, ax
0x14007e781  or      ebx, 80070000h
0x14007e787  jmp     loc_14007E8DC
0x14007e78c  mov     r8, cs:qword_1401CBA28
0x14007e793  xor     edx, edx
0x14007e795  mov     eax, 3E8h
0x14007e79a  mov     qword ptr [rbp+DueTime], 0
0x14007e7a2  mov     [rsp+60h+fResume], 0; fResume
0x14007e7aa  xor     r9d, r9d; pfnCompletionRoutine
0x14007e7ad  mov     qword ptr [rsp+60h+wRemoveMsg], 0; lpArgToCompletionRoutine
0x14007e7b6  div     dword ptr [r8+38h]
0x14007e7ba  lea     rdx, [rbp+DueTime]; lpDueTime
0x14007e7be  mov     r8d, eax; lPeriod
0x14007e7c1  call    cs:__imp_SetWaitableTimer
0x14007e7c7  xor     sil, sil
0x14007e7ca  cmp     [rbp+Msg.message], 12h
0x14007e7ce  jz      loc_14007E8DA
0x14007e7d4  mov     eax, cs:dword_1401CBAC0
0x14007e7da  test    eax, eax
0x14007e7dc  jz      short loc_14007E7FE
0x14007e7de  test    sil, sil
0x14007e7e1  jnz     short loc_14007E7FE
0x14007e7e3  mov     rcx, cs:hWnd; hWnd
0x14007e7ea  xor     r9d, r9d; lParam
0x14007e7ed  xor     r8d, r8d; wParam
0x14007e7f0  mov     edx, 8000h; Msg
0x14007e7f5  mov     sil, 1
0x14007e7f8  call    cs:__imp_PostMessageW
0x14007e7fe  xor     r9d, r9d; wMsgFilterMax
0x14007e801  mov     [rsp+60h+wRemoveMsg], 1; wRemoveMsg
0x14007e809  xor     r8d, r8d; wMsgFilterMin
0x14007e80c  lea     rcx, [rbp+Msg]; lpMsg
0x14007e810  xor     edx, edx; hWnd
0x14007e812  call    cs:__imp_PeekMessageW
0x14007e818  test    eax, eax
0x14007e81a  jz      short loc_14007E843
0x14007e81c  lea     rcx, [rbp+Msg]; lpMsg
0x14007e820  call    cs:__imp_TranslateMessage
0x14007e826  lea     rcx, [rbp+Msg]; lpMsg
0x14007e82a  call    cs:__imp_DispatchMessageW
0x14007e830  mov     ebx, cs:dword_1401C6658
0x14007e836  test    ebx, ebx
0x14007e838  js      loc_14007E8DC
0x14007e83e  mov     dil, 1
0x14007e841  jmp     short loc_14007E8A4
0x14007e843  mov     rcx, cs:qword_1401CBA28
0x14007e84a  xor     dil, dil
0x14007e84d  add     rcx, 8; this
0x14007e851  call    ?TimeExpired@TickTimer@D3DCommon@@QEAA_NXZ; D3DCommon::TickTimer::TimeExpired(void)
0x14007e856  test    al, al
0x14007e858  jnz     short loc_14007E869
0x14007e85a  xor     ecx, ecx; this
0x14007e85c  call    ?Render3DEnvironment@D3DCommon@@YAJH@Z; D3DCommon::Render3DEnvironment(int)
0x14007e861  mov     ebx, eax
0x14007e863  test    eax, eax
0x14007e865  js      short loc_14007E8DC
0x14007e867  jmp     short loc_14007E8A4
0x14007e869  mov     ecx, 1; this
0x14007e86e  call    ?Render3DEnvironment@D3DCommon@@YAJH@Z; D3DCommon::Render3DEnvironment(int)
0x14007e873  mov     ebx, eax
0x14007e875  test    eax, eax
0x14007e877  js      short loc_14007E8DC
0x14007e879  mov     edx, cs:dword_1401C0824; unsigned __int16
0x14007e87f  mov     ecx, 50h ; 'P'; this
0x14007e884  xor     r8d, r8d; unsigned int
0x14007e887  call    ?LogMessage@D3DCommon@@YAJGKPEAI@Z; D3DCommon::LogMessage(ushort,ulong,uint *)
0x14007e88c  mov     rcx, cs:hWnd; hWnd
0x14007e893  xor     r9d, r9d; lParam
0x14007e896  xor     r8d, r8d; wParam
0x14007e899  mov     edx, 8000h; Msg
0x14007e89e  call    cs:__imp_PostMessageW
0x14007e8a4  cmp     [rbp+pHandles], 0
0x14007e8a9  jz      loc_14007E7CA
0x14007e8af  test    dil, dil
0x14007e8b2  jnz     loc_14007E7CA
0x14007e8b8  xor     r8d, r8d; fWaitAll
0x14007e8bb  mov     [rsp+60h+wRemoveMsg], 1CBFh; dwWakeMask
0x14007e8c3  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x14007e8c7  lea     rdx, [rbp+pHandles]; pHandles
0x14007e8cb  lea     ecx, [r8+1]; nCount
0x14007e8cf  call    cs:__imp_MsgWaitForMultipleObjects
0x14007e8d5  jmp     loc_14007E7CA
0x14007e8da  xor     ebx, ebx
0x14007e8dc  mov     rcx, [rbp+pHandles]; hTimer
0x14007e8e0  test    rcx, rcx
0x14007e8e3  jz      short loc_14007E8F5
0x14007e8e5  call    cs:__imp_CancelWaitableTimer
0x14007e8eb  mov     rcx, [rbp+pHandles]; hObject
0x14007e8ef  call    cs:__imp_CloseHandle
0x14007e8f5  mov     eax, ebx
0x14007e8f7  mov     rbx, [rsp+60h+arg_10]
0x14007e8ff  add     rsp, 60h
0x14007e903  pop     rdi
0x14007e904  pop     rsi
0x14007e905  pop     rbp
0x14007e906  retn
```
