# ShutdownControlHandler::WindowThreadProc(void *)

- ea: `0x1400058a0`
- end: `0x140005930`
- name: `?WindowThreadProc@ShutdownControlHandler@@CAKPEAX@Z`
- size: `144`
- prototype: `__int64 __fastcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update`

## callees

- `0x140005038`
- `0x1400058a0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005912`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140005912`
- `ext-ms-win-ntuser-message-l1-1-0!GetMessageW` at `0x1400058d6`
- `ext-ms-win-ntuser-message-l1-1-0!GetMessageW` at `0x140005906`
- `ext-ms-win-ntuser-message-l1-1-0!GetMessageW` at `0x1400058d6`
- `ext-ms-win-ntuser-message-l1-1-0!GetMessageW` at `0x140005906`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x1400058e8`
- `ext-ms-win-ntuser-message-l1-1-0!TranslateMessage` at `0x1400058e8`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageW` at `0x1400058f3`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageW` at `0x1400058f3`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassW` at `0x140005922`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassW` at `0x140005922`

## pseudocode

```c
__int64 __fastcall ShutdownControlHandler::WindowThreadProc(PVOID Parameter)
{
  unsigned int v1; // ebx
  BOOL MessageW; // eax
  HMODULE ModuleHandleW; // rax
  tagMSG Msg; // [rsp+20h] [rbp-38h] BYREF

  v1 = 0;
  ShutdownControlHandler::mg_hrInit = ShutdownControlHandler::CreateMsgWindow();
  if ( ShutdownControlHandler::mg_hrInit >= 0 )
  {
    memset(&Msg, 0, sizeof(Msg));
    MessageW = GetMessageW(&Msg, 0, 0, 0);
    v1 = 1;
    while ( MessageW )
    {
      TranslateMessage(&Msg);
      DispatchMessageW(&Msg);
      MessageW = GetMessageW(&Msg, 0, 0, 0);
    }
  }
  ModuleHandleW = GetModuleHandleW(0);
  UnregisterClassW(L"WinMSGWMIADAP", ModuleHandleW);
  return v1;
}

```

## disassembly

```asm
0x1400058a0  push    rbx
0x1400058a2  sub     rsp, 50h
0x1400058a6  xor     ebx, ebx
0x1400058a8  call    ?CreateMsgWindow@ShutdownControlHandler@@CAJXZ; ShutdownControlHandler::CreateMsgWindow(void)
0x1400058ad  mov     cs:?mg_hrInit@ShutdownControlHandler@@0JA, eax; long ShutdownControlHandler::mg_hrInit
0x1400058b3  test    eax, eax
0x1400058b5  js      short loc_140005910
0x1400058b7  xorps   xmm0, xmm0
0x1400058ba  lea     rcx, [rsp+58h+Msg]; lpMsg
0x1400058bf  xor     r9d, r9d; wMsgFilterMax
0x1400058c2  xor     r8d, r8d; wMsgFilterMin
0x1400058c5  xor     edx, edx; hWnd
0x1400058c7  movups  xmmword ptr [rsp+58h+Msg.hwnd], xmm0
0x1400058cc  movups  xmmword ptr [rsp+58h+Msg.wParam], xmm0
0x1400058d1  movups  xmmword ptr [rsp+58h+Msg.time], xmm0
0x1400058d6  call    cs:__imp_GetMessageW
0x1400058dc  mov     ebx, 1
0x1400058e1  jmp     short loc_14000590C
0x1400058e3  lea     rcx, [rsp+58h+Msg]; lpMsg
0x1400058e8  call    cs:__imp_TranslateMessage
0x1400058ee  lea     rcx, [rsp+58h+Msg]; lpMsg
0x1400058f3  call    cs:__imp_DispatchMessageW
0x1400058f9  xor     r9d, r9d; wMsgFilterMax
0x1400058fc  lea     rcx, [rsp+58h+Msg]; lpMsg
0x140005901  xor     r8d, r8d; wMsgFilterMin
0x140005904  xor     edx, edx; hWnd
0x140005906  call    cs:__imp_GetMessageW
0x14000590c  cmp     eax, ebx
0x14000590e  jz      short loc_1400058E3
0x140005910  xor     ecx, ecx; lpModuleName
0x140005912  call    cs:__imp_GetModuleHandleW
0x140005918  mov     rdx, rax; hInstance
0x14000591b  lea     rcx, ClassName; "WinMSGWMIADAP"
0x140005922  call    cs:__imp_UnregisterClassW
0x140005928  mov     eax, ebx
0x14000592a  add     rsp, 50h
0x14000592e  pop     rbx
0x14000592f  retn
```
