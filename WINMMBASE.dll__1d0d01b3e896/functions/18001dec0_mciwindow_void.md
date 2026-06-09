# mciwindow(void *)

- ea: `0x18001dec0`
- end: `0x18001e0ea`
- name: `?mciwindow@@YAXPEAX@Z`
- size: `554`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800106c0`
- `0x1800117b8`
- `0x180011d6c`
- `0x18001dec0`
- `0x18001e138`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001df3f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18001df3f`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x18001e0c7`
- `api-ms-win-core-processthreads-l1-1-0!ExitThread` at `0x18001e0c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001df33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001df33`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001e008`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001e008`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dfce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dfce`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18001df12`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x18001df12`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18001defa`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameA` at `0x18001defa`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001e0bf`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18001e0bf`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001e015`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18001e015`
- `ext-ms-win-ntuser-message-l1-1-0!GetMessageA` at `0x18001e09d`
- `ext-ms-win-ntuser-message-l1-1-0!GetMessageA` at `0x18001e09d`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageA` at `0x18001e08a`
- `ext-ms-win-ntuser-message-l1-1-0!DispatchMessageA` at `0x18001e08a`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExA` at `0x18001df9b`
- `ext-ms-win-ntuser-window-l1-1-0!CreateWindowExA` at `0x18001df9b`
- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x18001e0b9`
- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x18001e0b9`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x18001dffd`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassA` at `0x18001dffd`

## string_xrefs

- `0x18001df4c`: `MCI command handling window`

## pseudocode

```c
ULONG __fastcall mciwindow(PVOID Parameter)
{
  HMODULE Library; // rax
  int v3; // ebx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  HWND v8; // rcx
  MSG Msg; // [rsp+60h] [rbp-A0h] BYREF
  CHAR Filename[1008]; // [rsp+90h] [rbp-70h] BYREF

  LODWORD(Library) = GetModuleFileNameA(ghInst, Filename, 0x3E8u);
  if ( (_DWORD)Library )
  {
    Library = LoadLibraryExA(Filename, 0, 2u);
    if ( Library )
    {
      LODWORD(Library) = IsCreateWindowExWPresent();
      if ( (_BYTE)Library )
      {
        v3 = 1;
        CurrentThread = GetCurrentThread();
        SetThreadPriority(CurrentThread, 2);
        hwndNotify = CreateWindowExA(0, (LPCSTR)0x2C, mciWndName, 0, 0, 0, 0, 0, HWND_MESSAGE, 0, ghInst, 0);
        if ( !hwndNotify )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            LastError = GetLastError();
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              18,
              &WPP_0c7fc82a53b231168ee6f0523baae1e5_Traceguids,
              LastError);
          }
          UnregisterClassA((LPCSTR)0x2C, ghInst);
          v3 = 0;
        }
        SetEvent(Parameter);
        CoInitializeEx(0, 2u);
        if ( v3 )
        {
          memset(&Msg, 0, sizeof(Msg));
          while ( GetMessageA(&Msg, 0, 0, 0) )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
            {
              WPP_SF_DqPP(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, v7, Msg.message, Msg.hwnd, Msg.wParam, Msg.lParam);
            }
            if ( Msg.hwnd )
              DispatchMessageA(&Msg);
          }
          v8 = hwndNotify;
          hwndNotify = 0;
          DestroyWindow(v8);
        }
        CoUninitialize();
        ExitThread(0);
      }
    }
  }
  return (unsigned int)Library;
}

```

## disassembly

```asm
0x18001dec0  push    rbp
0x18001dec2  push    rbx
0x18001dec3  push    rdi
0x18001dec4  push    r12
0x18001dec6  lea     rbp, [rsp-398h]
0x18001dece  sub     rsp, 498h
0x18001ded5  mov     rax, cs:__security_cookie
0x18001dedc  xor     rax, rsp
0x18001dedf  mov     [rbp+3B0h+var_30], rax
0x18001dee6  mov     rdi, rcx
0x18001dee9  lea     rdx, [rbp+3B0h+Filename]; lpFilename
0x18001deed  mov     rcx, cs:ghInst; hModule
0x18001def4  mov     r8d, 3E8h; nSize
0x18001defa  call    cs:__imp_GetModuleFileNameA
0x18001df00  test    eax, eax
0x18001df02  jz      loc_18001E0CE
0x18001df08  xor     edx, edx; hFile
0x18001df0a  lea     rcx, [rbp+3B0h+Filename]; lpLibFileName
0x18001df0e  lea     r8d, [rdx+2]; dwFlags
0x18001df12  call    cs:__imp_LoadLibraryExA
0x18001df18  test    rax, rax
0x18001df1b  jz      loc_18001E0CE
0x18001df21  call    IsCreateWindowExWPresent
0x18001df26  test    al, al
0x18001df28  jz      loc_18001E0CE
0x18001df2e  mov     ebx, 1
0x18001df33  call    cs:__imp_GetCurrentThread
0x18001df39  mov     rcx, rax; hThread
0x18001df3c  lea     edx, [rbx+1]; nPriority
0x18001df3f  call    cs:__imp_SetThreadPriority
0x18001df45  mov     rax, cs:ghInst
0x18001df4c  lea     r8, ?mciWndName@@3PADA; "MCI command handling window"
0x18001df53  mov     [rsp+4B0h+lpParam], 0; lpParam
0x18001df5c  lea     edx, [rbx+2Bh]; lpClassName
0x18001df5f  mov     [rsp+4B0h+hInstance], rax; hInstance
0x18001df64  xor     r9d, r9d; dwStyle
0x18001df67  mov     [rsp+4B0h+hMenu], 0; hMenu
0x18001df70  xor     ecx, ecx; dwExStyle
0x18001df72  mov     [rsp+4B0h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x18001df7b  mov     [rsp+4B0h+nHeight], 0; nHeight
0x18001df83  mov     [rsp+4B0h+nWidth], 0; nWidth
0x18001df8b  mov     [rsp+4B0h+Y], 0; Y
0x18001df93  mov     [rsp+4B0h+X], 0; X
0x18001df9b  call    cs:__imp_CreateWindowExA
0x18001dfa1  mov     cs:?hwndNotify@@3PEAUHWND__@@EA, rax; HWND__ * hwndNotify
0x18001dfa8  lea     r12, WPP_GLOBAL_Control
0x18001dfaf  test    rax, rax
0x18001dfb2  jnz     short loc_18001E005
0x18001dfb4  mov     rax, cs:WPP_GLOBAL_Control
0x18001dfbb  cmp     rax, r12
0x18001dfbe  jz      short loc_18001DFF1
0x18001dfc0  test    dword ptr [rax+1Ch], 400000h
0x18001dfc7  jz      short loc_18001DFF1
0x18001dfc9  cmp     [rax+19h], bl
0x18001dfcc  jb      short loc_18001DFF1
0x18001dfce  call    cs:__imp_GetLastError
0x18001dfd4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dfdb  lea     edx, [rbx+11h]
0x18001dfde  mov     r9d, eax
0x18001dfe1  lea     r8, WPP_0c7fc82a53b231168ee6f0523baae1e5_Traceguids
0x18001dfe8  mov     rcx, [rcx+10h]
0x18001dfec  call    WPP_SF_d
0x18001dff1  mov     rdx, cs:ghInst; hInstance
0x18001dff8  mov     ecx, 2Ch ; ','; lpClassName
0x18001dffd  call    cs:__imp_UnregisterClassA
0x18001e003  xor     ebx, ebx
0x18001e005  mov     rcx, rdi; hEvent
0x18001e008  call    cs:__imp_SetEvent
0x18001e00e  mov     edx, 2; dwCoInit
0x18001e013  xor     ecx, ecx; pvReserved
0x18001e015  call    cs:__imp_CoInitializeEx
0x18001e01b  test    ebx, ebx
0x18001e01d  jz      loc_18001E0BF
0x18001e023  xorps   xmm0, xmm0
0x18001e026  movups  xmmword ptr [rsp+4B0h+Msg.hwnd], xmm0
0x18001e02b  movups  xmmword ptr [rsp+4B0h+Msg.wParam], xmm0
0x18001e030  movups  xmmword ptr [rbp+3B0h+Msg.time], xmm0
0x18001e034  jmp     short loc_18001E090
0x18001e036  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e03d  cmp     rcx, r12
0x18001e040  jz      short loc_18001E07D
0x18001e042  test    dword ptr [rcx+1Ch], 400000h
0x18001e049  jz      short loc_18001E07D
0x18001e04b  cmp     byte ptr [rcx+19h], 5
0x18001e04f  jb      short loc_18001E07D
0x18001e051  mov     rax, [rsp+4B0h+Msg.lParam]
0x18001e056  mov     r9d, [rsp+4B0h+Msg.message]
0x18001e05b  mov     rcx, [rcx+10h]
0x18001e05f  mov     qword ptr [rsp+4B0h+nWidth], rax
0x18001e064  mov     rax, [rsp+4B0h+Msg.wParam]
0x18001e069  mov     qword ptr [rsp+4B0h+Y], rax
0x18001e06e  mov     rax, [rsp+4B0h+Msg.hwnd]
0x18001e073  mov     qword ptr [rsp+4B0h+X], rax
0x18001e078  call    WPP_SF_DqPP
0x18001e07d  cmp     [rsp+4B0h+Msg.hwnd], 0
0x18001e083  jz      short loc_18001E090
0x18001e085  lea     rcx, [rsp+4B0h+Msg]; lpMsg
0x18001e08a  call    cs:__imp_DispatchMessageA
0x18001e090  xor     r9d, r9d; wMsgFilterMax
0x18001e093  lea     rcx, [rsp+4B0h+Msg]; lpMsg
0x18001e098  xor     r8d, r8d; wMsgFilterMin
0x18001e09b  xor     edx, edx; hWnd
0x18001e09d  call    cs:__imp_GetMessageA
0x18001e0a3  test    eax, eax
0x18001e0a5  jnz     short loc_18001E036
0x18001e0a7  mov     rcx, cs:?hwndNotify@@3PEAUHWND__@@EA; hWnd
0x18001e0ae  mov     cs:?hwndNotify@@3PEAUHWND__@@EA, 0; HWND__ * hwndNotify
0x18001e0b9  call    cs:__imp_DestroyWindow
0x18001e0bf  call    cs:__imp_CoUninitialize
0x18001e0c5  xor     ecx, ecx; dwExitCode
0x18001e0c7  call    cs:__imp_ExitThread
0x18001e0ce  mov     rcx, [rbp+3B0h+var_30]
0x18001e0d5  xor     rcx, rsp; StackCookie
0x18001e0d8  call    __security_check_cookie
0x18001e0dd  add     rsp, 498h
0x18001e0e4  pop     r12
0x18001e0e6  pop     rdi
0x18001e0e7  pop     rbx
0x18001e0e8  pop     rbp
0x18001e0e9  retn
```
