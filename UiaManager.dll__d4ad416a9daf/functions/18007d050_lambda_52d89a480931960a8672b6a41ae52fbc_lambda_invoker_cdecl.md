# _lambda_52d89a480931960a8672b6a41ae52fbc_::_lambda_invoker_cdecl_

- ea: `0x18007d050`
- end: `0x18007d0c3`
- name: `_lambda_52d89a480931960a8672b6a41ae52fbc_::_lambda_invoker_cdecl_`
- size: `115`
- prototype: `void __stdcall(HWINEVENTHOOK hWinEventHook, DWORD event, HWND hwnd, LONG idObject, LONG idChild, DWORD idEventThread, DWORD dwmsEventTime)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180043a8c`
- `0x18007da24`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007d086`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007d086`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostThreadMessageW` at `0x18007d099`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!PostThreadMessageW` at `0x18007d099`

## pseudocode

```c
void __fastcall lambda_52d89a480931960a8672b6a41ae52fbc_::_lambda_invoker_cdecl_(
        HWINEVENTHOOK hWinEventHook,
        DWORD event,
        HWND hwnd,
        LONG idObject,
        LONG idChild)
{
  _QWORD *v8; // rax
  LPARAM v9; // rbx
  DWORD CurrentThreadId; // eax
  _QWORD *v11; // [rsp+50h] [rbp+18h] BYREF

  v8 = operator new(0x18u);
  v11 = v8;
  v9 = (LPARAM)v8;
  *(_DWORD *)v8 = event;
  v8[1] = hwnd;
  *((_DWORD *)v8 + 4) = idObject;
  *((_DWORD *)v8 + 5) = idChild;
  CurrentThreadId = GetCurrentThreadId();
  if ( PostThreadMessageW(CurrentThreadId, 0x8000u, 0, v9) )
    v9 = 0;
  v11 = (_QWORD *)v9;
  std::unique_ptr<WinEventsManager::WinEventHookParams>::~unique_ptr<WinEventsManager::WinEventHookParams>(&v11);
}

```

## disassembly

```asm
0x18007d050  mov     [rsp+arg_0], rbx
0x18007d055  push    rbp
0x18007d056  push    rsi
0x18007d057  push    rdi
0x18007d058  sub     rsp, 20h
0x18007d05c  mov     ecx, 18h; Size
0x18007d061  mov     ebp, r9d
0x18007d064  mov     rsi, r8
0x18007d067  mov     edi, edx
0x18007d069  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007d06e  mov     [rsp+38h+arg_10], rax
0x18007d073  mov     rbx, rax
0x18007d076  mov     [rax], edi
0x18007d078  mov     [rax+8], rsi
0x18007d07c  mov     [rax+10h], ebp
0x18007d07f  mov     eax, [rsp+38h+idChild]
0x18007d083  mov     [rbx+14h], eax
0x18007d086  call    cs:__imp_GetCurrentThreadId
0x18007d08c  mov     r9, rbx; lParam
0x18007d08f  xor     r8d, r8d; wParam
0x18007d092  mov     ecx, eax; idThread
0x18007d094  mov     edx, 8000h; Msg
0x18007d099  call    cs:__imp_PostThreadMessageW
0x18007d09f  xor     ecx, ecx
0x18007d0a1  test    eax, eax
0x18007d0a3  cmovnz  rbx, rcx
0x18007d0a7  lea     rcx, [rsp+38h+arg_10]
0x18007d0ac  mov     [rsp+38h+arg_10], rbx
0x18007d0b1  call    ??1?$unique_ptr@UWinEventHookParams@WinEventsManager@@U?$default_delete@UWinEventHookParams@WinEventsManager@@@std@@@std@@QEAA@XZ; std::unique_ptr<WinEventsManager::WinEventHookParams>::~unique_ptr<WinEventsManager::WinEventHookParams>(void)
0x18007d0b6  mov     rbx, [rsp+38h+arg_0]
0x18007d0bb  add     rsp, 20h
0x18007d0bf  pop     rdi
0x18007d0c0  pop     rsi
0x18007d0c1  pop     rbp
0x18007d0c2  retn
```
