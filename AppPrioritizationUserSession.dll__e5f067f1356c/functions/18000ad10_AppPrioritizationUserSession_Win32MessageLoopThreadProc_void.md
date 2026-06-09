# AppPrioritizationUserSession::Win32MessageLoopThreadProc(void *)

- ea: `0x18000ad10`
- end: `0x18000ae04`
- name: `?Win32MessageLoopThreadProc@AppPrioritizationUserSession@@CAKPEAX@Z`
- size: `244`
- prototype: `DWORD __fastcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180001304`
- `0x180002650`
- `0x1800048d4`
- `0x18000ad10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000ad82`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000ad9b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000ad82`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18000ad9b`
- `USER32!DispatchMessageW` at `0x18000ade8`
- `USER32!DispatchMessageW` at `0x18000ade8`
- `USER32!GetMessageW` at `0x18000add1`
- `USER32!GetMessageW` at `0x18000add1`

## pseudocode

```c
DWORD __fastcall AppPrioritizationUserSession::Win32MessageLoopThreadProc(LPVOID lpThreadParameter)
{
  HANDLE v1; // rbx
  DWORD v2; // eax
  unsigned int v3; // r8d
  const char *v4; // r9
  DWORD result; // eax
  tagMSG Msg; // [rsp+38h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v7; // [rsp+68h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  if ( (unsigned int)dword_180014000 > 4 )
    tlgWriteTransfer_EventWriteTransfer((int)&dword_180014000, (int)&word_18001021A, 0, 0, 2u, &v7);
  memset(&Msg, 0, sizeof(Msg));
  while ( 1 )
  {
    v1 = AppPrioritizationUserSession::m_stopWin32MessageEvent;
    v2 = WaitForSingleObjectEx(AppPrioritizationUserSession::m_stopWin32MessageEvent, 0, 0);
    if ( v2 != 258 )
      break;
    if ( GetMessageW(&Msg, 0, 0, 0) > 0 && Msg.hwnd )
      DispatchMessageW(&Msg);
  }
  if ( v2 || (result = WaitForSingleObjectEx(v1, 0, 0)) != 0 )
    wil::details::in1diag3::FailFast_Unexpected(retaddr, (void *)0xB07, v3, v4);
  while ( 2 )
  {
    try
    {
    }
    catch ( ... )
    {
      result = wil::details::in1diag3::Return_CaughtException(retaddr, (void *)0x51, v3, v4);
      continue;
    }
    break;
  }
  return result;
}

```

## disassembly

```asm
0x18000ad10  push    rbx
0x18000ad12  sub     rsp, 90h
0x18000ad19  mov     rax, cs:__security_cookie
0x18000ad20  xor     rax, rsp
0x18000ad23  mov     [rsp+98h+var_10], rax
0x18000ad2b  mov     eax, cs:dword_180014000
0x18000ad31  cmp     eax, 4
0x18000ad34  jbe     short loc_18000AD61
0x18000ad36  lea     rax, [rsp+98h+var_30]
0x18000ad3b  mov     [rsp+98h+var_70], rax; PEVENT_DATA_DESCRIPTOR
0x18000ad40  mov     [rsp+98h+var_78], 2; ULONG
0x18000ad48  xor     r9d, r9d; int
0x18000ad4b  xor     r8d, r8d; int
0x18000ad4e  lea     rdx, word_18001021A; int
0x18000ad55  lea     rcx, dword_180014000; int
0x18000ad5c  call    _tlgWriteTransfer_EventWriteTransfer
0x18000ad61  xorps   xmm0, xmm0
0x18000ad64  movups  xmmword ptr [rsp+98h+Msg.hwnd], xmm0
0x18000ad69  movups  xmmword ptr [rsp+98h+Msg.wParam], xmm0
0x18000ad6e  movups  xmmword ptr [rsp+98h+Msg.time], xmm0
0x18000ad73  mov     rbx, cs:?m_stopWin32MessageEvent@AppPrioritizationUserSession@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A
0x18000ad7a  xor     r8d, r8d; bAlertable
0x18000ad7d  xor     edx, edx; dwMilliseconds
0x18000ad7f  mov     rcx, rbx; hHandle
0x18000ad82  call    cs:__imp_WaitForSingleObjectEx
0x18000ad88  cmp     eax, 102h
0x18000ad8d  jz      short loc_18000ADC4
0x18000ad8f  test    eax, eax
0x18000ad91  jnz     short loc_18000ADF0
0x18000ad93  xor     r8d, r8d; bAlertable
0x18000ad96  xor     edx, edx; dwMilliseconds
0x18000ad98  mov     rcx, rbx; hHandle
0x18000ad9b  call    cs:__imp_WaitForSingleObjectEx
0x18000ada1  test    eax, eax
0x18000ada3  jnz     short loc_18000ADF0
0x18000ada5  jmp     short loc_18000ADAB
0x18000ada7  mov     eax, [rsp+98h+var_68]
0x18000adab  mov     rcx, [rsp+98h+var_10]
0x18000adb3  xor     rcx, rsp; StackCookie
0x18000adb6  call    __security_check_cookie
0x18000adbb  add     rsp, 90h
0x18000adc2  pop     rbx
0x18000adc3  retn
0x18000adc4  xor     r9d, r9d; wMsgFilterMax
0x18000adc7  xor     r8d, r8d; wMsgFilterMin
0x18000adca  xor     edx, edx; hWnd
0x18000adcc  lea     rcx, [rsp+98h+Msg]; lpMsg
0x18000add1  call    cs:__imp_GetMessageW
0x18000add7  test    eax, eax
0x18000add9  jle     short loc_18000AD73
0x18000addb  cmp     [rsp+98h+Msg.hwnd], 0
0x18000ade1  jz      short loc_18000AD73
0x18000ade3  lea     rcx, [rsp+98h+Msg]; lpMsg
0x18000ade8  call    cs:__imp_DispatchMessageW
0x18000adee  jmp     short loc_18000AD73
0x18000adf0  mov     rcx, [rsp+98h]; this
0x18000adf8  mov     edx, 0B07h; void *
0x18000adfd  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
```
