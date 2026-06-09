# Microsoft::CoreUI::Dispatch::UserAdapter::NoContext_CreateWindow(void)

- ea: `0x18005c2ec`
- end: `0x18005c383`
- name: `?NoContext_CreateWindow@UserAdapter@Dispatch@CoreUI@Microsoft@@CAPEAUHWND__@@XZ`
- size: `151`
- prototype: `HWND(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18005c190`

## callees

- `0x18005c2ec`
- `0x18005c38c`
- `0x18008f584`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18005c30a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18005c30a`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!CreateWindowExW` at `0x18005c372`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!CreateWindowExW` at `0x18005c372`

## pseudocode

```c
HWND Microsoft::CoreUI::Dispatch::UserAdapter::NoContext_CreateWindow(void)
{
  HMODULE phModule; // [rsp+70h] [rbp+8h] BYREF

  phModule = 0;
  if ( !GetModuleHandleExW(6u, (LPCWSTR)Microsoft::CoreUI::Dispatch::UserAdapter::WindowProc, &phModule) )
    Cn::FailFast::ForWin32();
  Microsoft::CoreUI::Dispatch::UserAdapter::NoContext_InitializeWindowClass(phModule);
  return CreateWindowExW(0, L"SystemUserAdapterWindowClass", 0, 0, 0, 0, 0, 0, HWND_MESSAGE, 0, phModule, 0);
}

```

## disassembly

```asm
0x18005c2ec  sub     rsp, 68h
0x18005c2f0  lea     r8, [rsp+68h+phModule]; phModule
0x18005c2f5  mov     [rsp+68h+phModule], 0
0x18005c2fe  lea     rdx, ?WindowProc@UserAdapter@Dispatch@CoreUI@Microsoft@@CA_JPEAUHWND__@@I_K_J@Z; lpModuleName
0x18005c305  mov     ecx, 6; dwFlags
0x18005c30a  call    cs:__imp_GetModuleHandleExW
0x18005c310  test    eax, eax
0x18005c312  jz      short loc_18005C37D
0x18005c314  mov     rcx, [rsp+68h+phModule]; hInstance
0x18005c319  call    ?NoContext_InitializeWindowClass@UserAdapter@Dispatch@CoreUI@Microsoft@@CAXPEAUHINSTANCE__@@@Z; Microsoft::CoreUI::Dispatch::UserAdapter::NoContext_InitializeWindowClass(HINSTANCE__ *)
0x18005c31e  mov     rax, [rsp+68h+phModule]
0x18005c323  lea     rdx, szClass; "SystemUserAdapterWindowClass"
0x18005c32a  mov     [rsp+68h+lpParam], 0; lpParam
0x18005c333  xor     r9d, r9d; dwStyle
0x18005c336  mov     [rsp+68h+hInstance], rax; hInstance
0x18005c33b  xor     r8d, r8d; lpWindowName
0x18005c33e  mov     [rsp+68h+hMenu], 0; hMenu
0x18005c347  xor     ecx, ecx; dwExStyle
0x18005c349  mov     [rsp+68h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x18005c352  mov     [rsp+68h+nHeight], 0; nHeight
0x18005c35a  mov     [rsp+68h+nWidth], 0; nWidth
0x18005c362  mov     [rsp+68h+Y], 0; Y
0x18005c36a  mov     [rsp+68h+X], 0; X
0x18005c372  call    cs:__imp_CreateWindowExW
0x18005c378  add     rsp, 68h
0x18005c37c  retn
0x18005c37d  call    ?ForWin32@FailFast@Cn@@SAXXZ; Cn::FailFast::ForWin32(void)
```
