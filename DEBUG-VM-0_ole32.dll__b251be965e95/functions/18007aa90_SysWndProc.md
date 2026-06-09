# SysWndProc

- ea: `0x18007aa90`
- end: `0x18007ac56`
- name: `SysWndProc`
- size: `454`
- prototype: `__int64 __fastcall(HWND__ *hwnd, unsigned int message, unsigned __int64 wParam, __int64 lParam)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180076468`
- `0x1800769dc`
- `0x180076a38`
- `0x18007808c`
- `0x18007a818`
- `0x18007aa90`

## import_xrefs

- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007abc8`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007abda`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007abc8`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x18007abda`
- `USER32!GetWindowLongPtrW` at `0x18007aabc`
- `USER32!GetWindowLongPtrW` at `0x18007ab5f`
- `USER32!GetWindowLongPtrW` at `0x18007aabc`
- `USER32!GetWindowLongPtrW` at `0x18007ab5f`
- `USER32!KillTimer` at `0x18007ac00`
- `USER32!KillTimer` at `0x18007ac00`
- `USER32!DefWindowProcW` at `0x18007ac41`
- `USER32!DefWindowProcW` at `0x18007ac41`
- `USER32!PeekMessageW` at `0x18007ab20`
- `USER32!PeekMessageW` at `0x18007ab50`
- `USER32!PeekMessageW` at `0x18007ab20`
- `USER32!PeekMessageW` at `0x18007ab50`
- `USER32!DispatchMessageW` at `0x18007ab34`
- `USER32!DispatchMessageW` at `0x18007ab34`

## pseudocode

```c
LRESULT __fastcall SysWndProc(HWND hwnd, UINT message, HWND__ *wParam, unsigned __int64 lParam)
{
  LONG_PTR WindowLongPtrW; // rax
  CDdeObject *v9; // rsi
  DDE_CHANNEL *v10; // rbx
  LONG_PTR v11; // rax
  CDdeObject *v12; // rcx
  unsigned __int64 v13; // rdi
  __int64 v14; // r8
  __int64 v15; // r8
  unsigned __int16 wMsg; // dx
  tagMSG msg; // [rsp+30h] [rbp-68h] BYREF

  if ( message - 992 <= 8 )
  {
    WindowLongPtrW = GetWindowLongPtrW(hwnd, 0);
    v9 = (CDdeObject *)WindowLongPtrW;
    if ( WindowLongPtrW )
    {
      v10 = *(DDE_CHANNEL **)(WindowLongPtrW + 336);
      if ( v10 )
      {
        if ( ((v10->iAwaitAck - 4) & 0xFFFFFFFD) != 0 )
          goto LABEL_9;
        memset(&msg, 0, sizeof(msg));
        if ( !PeekMessageW(&msg, hwnd, 0x3E4u, 0x3E4u, 3u) )
          goto LABEL_9;
        do
          DispatchMessageW(&msg);
        while ( PeekMessageW(&msg, hwnd, 0x3E4u, 0x3E4u, 3u) );
        v11 = GetWindowLongPtrW(hwnd, 0);
        v9 = (CDdeObject *)v11;
        if ( !v11 || (v10 = *(DDE_CHANNEL **)(v11 + 336)) != 0 )
        {
LABEL_9:
          switch ( message )
          {
            case 0x113u:
              KillTimer(v10->hwndCli, 1u);
              v15 = v10->lParam;
              wMsg = v10->wMsg;
              v10->wTimer = 0;
              if ( !wPostMessageToServer(v10, wMsg, v15, 0) )
              {
                v14 = v10->lParam;
LABEL_23:
                CDdeObject::OnAck(v9, v10, v14);
              }
              return 0;
            case 0x3E1u:
              CDdeObject::OnTerminate(v9, v10, wParam);
              return 0;
            case 0x3E4u:
              UploadSQMData<enum Ole32SQMFlags>(OLEDDEUsage);
              if ( !v10->bTerminating )
              {
                if ( v10->iAwaitAck != 4 )
                {
                  if ( v10->iAwaitAck == 6 )
                  {
                    CDdeObject::OnInitAck(v12, v10, wParam);
                    if ( (_WORD)lParam )
                      GlobalDeleteAtom(lParam);
                    v13 = lParam >> 16;
                    if ( (_WORD)v13 )
                      GlobalDeleteAtom(v13);
                  }
                  return 0;
                }
                v14 = lParam;
                goto LABEL_23;
              }
              return 0;
          }
        }
      }
    }
  }
  return DefWindowProcW(hwnd, message, (WPARAM)wParam, lParam);
}

```

## disassembly

```asm
0x18007aa90  push    rbx
0x18007aa92  push    rbp
0x18007aa93  push    rsi
0x18007aa94  push    rdi
0x18007aa95  push    r12
0x18007aa97  push    r14
0x18007aa99  push    r15
0x18007aa9b  sub     rsp, 60h
0x18007aa9f  lea     eax, [rdx-3E0h]
0x18007aaa5  mov     rdi, lParam
0x18007aaa8  mov     r14, wParam
0x18007aaab  mov     r15d, message
0x18007aaae  mov     rbp, hwnd
0x18007aab1  cmp     eax, 8
0x18007aab4  ja      loc_18007AC35
0x18007aaba  xor     message, message; nIndex
0x18007aabc  call    cs:__imp_GetWindowLongPtrW
0x18007aac2  xor     r12d, r12d
0x18007aac5  mov     rsi, rax
0x18007aac8  test    rax, rax
0x18007aacb  jz      loc_18007AC35
0x18007aad1  mov     rbx, [rax+150h]
0x18007aad8  test    rbx, rbx
0x18007aadb  jz      loc_18007AC35
0x18007aae1  mov     ecx, [rbx+58h]
0x18007aae4  sub     ecx, 4
0x18007aae7  test    ecx, 0FFFFFFFDh
0x18007aaed  jnz     loc_18007AB7D
0x18007aaf3  xorps   xmm0, xmm0
0x18007aaf6  mov     [rsp+98h+wRemoveMsg], 3; wRemoveMsg
0x18007aafe  mov     eax, 3E4h
0x18007ab03  lea     hwnd, [rsp+98h+msg]; lpMsg
0x18007ab08  mov     r9d, eax; wMsgFilterMax
0x18007ab0b  mov     r8d, eax; wMsgFilterMin
0x18007ab0e  mov     rdx, rbp; hWnd
0x18007ab11  movups  xmmword ptr [rsp+98h+msg.hwnd], xmm0
0x18007ab16  movups  xmmword ptr [rsp+98h+msg.wParam], xmm0
0x18007ab1b  movups  xmmword ptr [rsp+98h+msg.time], xmm0
0x18007ab20  call    cs:__imp_PeekMessageW
0x18007ab26  test    eax, eax
0x18007ab28  jz      short loc_18007AB7D
0x18007ab2a  mov     esi, 3E4h
0x18007ab2f  lea     hwnd, [rsp+98h+msg]; lpMsg
0x18007ab34  call    cs:__imp_DispatchMessageW
0x18007ab3a  mov     r9d, esi; wMsgFilterMax
0x18007ab3d  mov     [rsp+98h+wRemoveMsg], 3; wRemoveMsg
0x18007ab45  mov     r8d, esi; wMsgFilterMin
0x18007ab48  lea     hwnd, [rsp+98h+msg]; lpMsg
0x18007ab4d  mov     rdx, rbp; hWnd
0x18007ab50  call    cs:__imp_PeekMessageW
0x18007ab56  test    eax, eax
0x18007ab58  jnz     short loc_18007AB2F
0x18007ab5a  xor     message, message; nIndex
0x18007ab5c  mov     hwnd, rbp; hWnd
0x18007ab5f  call    cs:__imp_GetWindowLongPtrW
0x18007ab65  mov     rsi, rax
0x18007ab68  test    rax, rax
0x18007ab6b  jz      short loc_18007AB7D
0x18007ab6d  mov     rbx, [rax+150h]
0x18007ab74  test    rbx, rbx
0x18007ab77  jz      loc_18007AC35
0x18007ab7d  mov     eax, r15d
0x18007ab80  sub     eax, 113h
0x18007ab85  jz      short loc_18007ABF7
0x18007ab87  sub     eax, 2CEh
0x18007ab8c  jz      short loc_18007ABE7
0x18007ab8e  cmp     eax, 3
0x18007ab91  jnz     loc_18007AC35
0x18007ab97  lea     ecx, [rax-1]; flags
0x18007ab9a  call    ??$UploadSQMData@W4Ole32SQMFlags@@@@YAXW4Ole32SQMFlags@@@Z; UploadSQMData<Ole32SQMFlags>(Ole32SQMFlags)
0x18007ab9f  cmp     [rbx+28h], r12d
0x18007aba3  jnz     loc_18007AC31
0x18007aba9  cmp     dword ptr [rbx+58h], 4
0x18007abad  jz      short loc_18007ABE2
0x18007abaf  cmp     dword ptr [rbx+58h], 6
0x18007abb3  jnz     short loc_18007AC31
0x18007abb5  mov     wParam, r14; hwndSvr
0x18007abb8  mov     rdx, rbx; pChannel
0x18007abbb  call    ?OnInitAck@CDdeObject@@QEAAXPEAVDDE_CHANNEL@@PEAUHWND__@@@Z; CDdeObject::OnInitAck(DDE_CHANNEL *,HWND__ *)
0x18007abc0  test    di, di
0x18007abc3  jz      short loc_18007ABCE
0x18007abc5  movzx   ecx, di; nAtom
0x18007abc8  call    cs:__imp_GlobalDeleteAtom
0x18007abce  shr     rdi, 10h
0x18007abd2  test    di, di
0x18007abd5  jz      short loc_18007AC31
0x18007abd7  movzx   ecx, di; nAtom
0x18007abda  call    cs:__imp_GlobalDeleteAtom
0x18007abe0  jmp     short loc_18007AC31
0x18007abe2  mov     wParam, rdi
0x18007abe5  jmp     short loc_18007AC26
0x18007abe7  mov     wParam, r14; hwndPost
0x18007abea  mov     rdx, rbx; pChannel
0x18007abed  mov     hwnd, rsi; this
0x18007abf0  call    ?OnTerminate@CDdeObject@@QEAAJPEAVDDE_CHANNEL@@PEAUHWND__@@@Z; CDdeObject::OnTerminate(DDE_CHANNEL *,HWND__ *)
0x18007abf5  jmp     short loc_18007AC31
0x18007abf7  mov     hwnd, [rbx+18h]; hWnd
0x18007abfb  mov     message, 1; uIDEvent
0x18007ac00  call    cs:__imp_KillTimer
0x18007ac06  mov     wParam, [rbx+50h]; lParam
0x18007ac0a  xor     r9d, r9d; fFreeOnError
0x18007ac0d  movzx   message, word ptr [rbx+4Ch]; wMsg
0x18007ac11  mov     hwnd, rbx; pChannel
0x18007ac14  mov     [rbx+30h], r12w
0x18007ac19  call    ?wPostMessageToServer@@YAHPEAVDDE_CHANNEL@@G_JH@Z; wPostMessageToServer(DDE_CHANNEL *,ushort,__int64,int)
0x18007ac1e  test    eax, eax
0x18007ac20  jnz     short loc_18007AC31
0x18007ac22  mov     wParam, [rbx+50h]; lParam
0x18007ac26  mov     rdx, rbx; pChannel
0x18007ac29  mov     hwnd, rsi; this
0x18007ac2c  call    ?OnAck@CDdeObject@@QEAAHPEAVDDE_CHANNEL@@_J@Z; CDdeObject::OnAck(DDE_CHANNEL *,__int64)
0x18007ac31  xor     eax, eax
0x18007ac33  jmp     short loc_18007AC47
0x18007ac35  mov     lParam, rdi; lParam
0x18007ac38  mov     wParam, r14; wParam
0x18007ac3b  mov     message, r15d; Msg
0x18007ac3e  mov     hwnd, rbp; hWnd
0x18007ac41  call    cs:__imp_DefWindowProcW
0x18007ac47  add     rsp, 60h
0x18007ac4b  pop     r15
0x18007ac4d  pop     r14
0x18007ac4f  pop     r12
0x18007ac51  pop     rdi
0x18007ac52  pop     rsi
0x18007ac53  pop     rbp
0x18007ac54  pop     rbx
0x18007ac55  retn
```
