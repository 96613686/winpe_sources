# ShutdownControlHandler::MsgWndProc(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x140005730`
- end: `0x140005809`
- name: `?MsgWndProc@ShutdownControlHandler@@CA_JPEAUHWND__@@I_K_J@Z`
- size: `217`
- prototype: `LRESULT __fastcall(HWND, UINT, WPARAM, LPARAM)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140005730`
- `0x140005938`

## import_xrefs

- `wbemcomn!GetMemLogObject` at `0x140005773`
- `wbemcomn!GetMemLogObject` at `0x140005773`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000577f`
- `wbemcomn!?Write@CMemoryLog@@QEAAXJ@Z` at `0x14000577f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400057bd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1400057bd`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x1400057f3`
- `ext-ms-win-ntuser-message-l1-1-0!PostMessageW` at `0x1400057f3`
- `ext-ms-win-ntuser-window-l1-1-0!DefWindowProcW` at `0x14000575f`
- `ext-ms-win-ntuser-window-l1-1-0!DefWindowProcW` at `0x1400057ca`
- `ext-ms-win-ntuser-window-l1-1-0!DefWindowProcW` at `0x14000575f`
- `ext-ms-win-ntuser-window-l1-1-0!DefWindowProcW` at `0x1400057ca`

## pseudocode

```c
LRESULT __fastcall ShutdownControlHandler::MsgWndProc(HWND a1, UINT a2, WPARAM a3, LPARAM a4)
{
  LRESULT v5; // rbx
  CMemoryLog *MemLogObject; // rax

  v5 = 1;
  switch ( a2 )
  {
    case 2u:
      PostMessageW(a1, 0x12u, 0, 0);
      return 0;
    case 0x10u:
      v5 = DefWindowProcW(a1, 0x10u, a3, a4);
      if ( ShutdownControlHandler::mg_hWnd == a1 )
        ShutdownControlHandler::mg_hWnd = 0;
      break;
    case 0x11u:
      ShutdownControlHandler::g_bShuttingDown = 1;
      MemLogObject = GetMemLogObject();
      CMemoryLog::Write(MemLogObject, -1);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15);
      }
      WaitForSingleObject(ShutdownControlHandler::mg_hReadyEvent, 0x7D0u);
      break;
    case 0x16u:
      break;
    default:
      return DefWindowProcW(a1, a2, a3, a4);
  }
  return v5;
}

```

## disassembly

```asm
0x140005730  mov     [rsp+arg_0], rbx
0x140005735  push    rdi
0x140005736  sub     rsp, 20h
0x14000573a  mov     eax, edx
0x14000573c  mov     rdi, rcx
0x14000573f  mov     ebx, 1
0x140005744  sub     eax, 2
0x140005747  jz      loc_1400057E9
0x14000574d  sub     eax, 0Eh
0x140005750  jz      short loc_1400057C5
0x140005752  sub     eax, ebx
0x140005754  jz      short loc_14000576D
0x140005756  cmp     eax, 5
0x140005759  jz      loc_1400057FB
0x14000575f  call    cs:__imp_DefWindowProcW
0x140005765  mov     rbx, rax
0x140005768  jmp     loc_1400057FB
0x14000576d  mov     cs:?g_bShuttingDown@ShutdownControlHandler@@0HC, ebx; int volatile ShutdownControlHandler::g_bShuttingDown
0x140005773  call    cs:__imp_?GetMemLogObject@@YAPEAVCMemoryLog@@XZ; GetMemLogObject(void)
0x140005779  mov     rcx, rax
0x14000577c  or      edx, 0FFFFFFFFh
0x14000577f  call    cs:__imp_?Write@CMemoryLog@@QEAAXJ@Z; CMemoryLog::Write(long)
0x140005785  mov     rcx, cs:WPP_GLOBAL_Control
0x14000578c  lea     rax, WPP_GLOBAL_Control
0x140005793  cmp     rcx, rax
0x140005796  jz      short loc_1400057B1
0x140005798  test    [rcx+1Ch], bl
0x14000579b  jz      short loc_1400057B1
0x14000579d  cmp     byte ptr [rcx+19h], 2
0x1400057a1  jb      short loc_1400057B1
0x1400057a3  mov     rcx, [rcx+10h]
0x1400057a7  mov     edx, 0Fh
0x1400057ac  call    WPP_SF_
0x1400057b1  mov     rcx, cs:?mg_hReadyEvent@ShutdownControlHandler@@0PEAXEA; hHandle
0x1400057b8  mov     edx, 7D0h; dwMilliseconds
0x1400057bd  call    cs:__imp_WaitForSingleObject
0x1400057c3  jmp     short loc_1400057FB
0x1400057c5  mov     edx, 10h; Msg
0x1400057ca  call    cs:__imp_DefWindowProcW
0x1400057d0  cmp     cs:?mg_hWnd@ShutdownControlHandler@@0PEAUHWND__@@EA, rdi; HWND__ * ShutdownControlHandler::mg_hWnd
0x1400057d7  mov     rbx, rax
0x1400057da  jnz     short loc_1400057FB
0x1400057dc  mov     cs:?mg_hWnd@ShutdownControlHandler@@0PEAUHWND__@@EA, 0; HWND__ * ShutdownControlHandler::mg_hWnd
0x1400057e7  jmp     short loc_1400057FB
0x1400057e9  xor     r9d, r9d; lParam
0x1400057ec  xor     r8d, r8d; wParam
0x1400057ef  lea     edx, [r9+12h]; Msg
0x1400057f3  call    cs:__imp_PostMessageW
0x1400057f9  xor     ebx, ebx
0x1400057fb  mov     rax, rbx
0x1400057fe  mov     rbx, [rsp+28h+arg_0]
0x140005803  add     rsp, 20h
0x140005807  pop     rdi
0x140005808  retn
```
