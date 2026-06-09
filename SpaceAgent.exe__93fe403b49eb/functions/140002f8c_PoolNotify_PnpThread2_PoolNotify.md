# PoolNotify::PnpThread2(PoolNotify *)

- ea: `0x140002f8c`
- end: `0x140003102`
- name: `?PnpThread2@PoolNotify@@CAKPEAV1@@Z`
- size: `374`
- prototype: `__int64 __fastcall(HANDLE *lpParam)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x140003110`

## callees

- `0x140001caf`
- `0x140002f8c`
- `0x1400082e4`
- `0x140008574`
- `0x1400148e8`

## import_xrefs

- `KERNEL32!SetEvent` at `0x140003095`
- `KERNEL32!SetEvent` at `0x140003095`
- `KERNEL32!GetLastError` at `0x140002ff7`
- `KERNEL32!GetLastError` at `0x140003047`
- `KERNEL32!GetLastError` at `0x14000305b`
- `KERNEL32!GetLastError` at `0x140003073`
- `KERNEL32!GetLastError` at `0x140002ff7`
- `KERNEL32!GetLastError` at `0x140003047`
- `KERNEL32!GetLastError` at `0x14000305b`
- `KERNEL32!GetLastError` at `0x140003073`
- `USER32!UnregisterClassW` at `0x1400030df`
- `USER32!UnregisterClassW` at `0x1400030df`
- `USER32!UnregisterDeviceNotification` at `0x1400030c6`
- `USER32!UnregisterDeviceNotification` at `0x1400030c6`
- `USER32!DispatchMessageW` at `0x1400030a1`
- `USER32!DispatchMessageW` at `0x1400030a1`
- `USER32!GetMessageW` at `0x1400030b3`
- `USER32!GetMessageW` at `0x1400030b3`
- `USER32!PeekMessageW` at `0x14000308b`
- `USER32!PeekMessageW` at `0x14000308b`
- `USER32!CreateWindowExW` at `0x140003039`
- `USER32!CreateWindowExW` at `0x140003039`
- `USER32!RegisterClassExW` at `0x140002fec`
- `USER32!RegisterClassExW` at `0x140002fec`
- `USER32!DestroyWindow` at `0x1400030d4`
- `USER32!DestroyWindow` at `0x1400030d4`

## string_xrefs

- `0x140002fd9`: `SPACEAGENT!PNP!MESSAGEWND`
- `0x140003007`: `SpaceAgentPnPWatcher`

## pseudocode

```c
__int64 __fastcall PoolNotify::PnpThread2(HANDLE *lpParam)
{
  HWND Window; // rbx
  tagMSG Msg; // [rsp+60h] [rbp-39h] BYREF
  WNDCLASSEXW v5; // [rsp+90h] [rbp-9h] BYREF
  HDEVNOTIFY Handle; // [rsp+100h] [rbp+67h] BYREF

  Handle = 0;
  memset(&Msg, 0, sizeof(Msg));
  memset_0(&v5, 0, sizeof(v5));
  v5.cbSize = 80;
  v5.lpfnWndProc = (WNDPROC)PoolNotify::PnpWndProc;
  v5.lpszClassName = L"SPACEAGENT!PNP!MESSAGEWND";
  if ( RegisterClassExW(&v5) )
  {
    Window = CreateWindowExW(
               0,
               L"SPACEAGENT!PNP!MESSAGEWND",
               L"SpaceAgentPnPWatcher",
               0,
               0,
               0,
               0,
               0,
               HWND_MESSAGE,
               0,
               0,
               lpParam);
    if ( Window )
    {
      if ( (unsigned int)SuInitialize() )
      {
        if ( (unsigned int)SuRegisterDeviceNotification(Window, &Handle) )
        {
          PeekMessageW(&Msg, 0, 0, 0, 0);
          SetEvent(lpParam[2]);
          while ( GetMessageW(&Msg, 0, 0, 0) )
            DispatchMessageW(&Msg);
        }
        else
        {
          GetLastError();
        }
        if ( Handle )
          UnregisterDeviceNotification(Handle);
        SuCleanup();
      }
      else
      {
        GetLastError();
      }
      DestroyWindow(Window);
    }
    else
    {
      GetLastError();
    }
    UnregisterClassW(L"SPACEAGENT!PNP!MESSAGEWND", 0);
  }
  else
  {
    GetLastError();
  }
  *((_DWORD *)lpParam + 8) = 0;
  return 0;
}

```

## disassembly

```asm
0x140002f8c  mov     [rsp-8+arg_8], rbx
0x140002f91  mov     [rsp-8+arg_10], rsi
0x140002f96  push    rbp
0x140002f97  push    rdi
0x140002f98  push    r14
0x140002f9a  lea     rbp, [rsp-47h]
0x140002f9f  sub     rsp, 0E0h
0x140002fa6  xorps   xmm0, xmm0
0x140002fa9  xor     esi, esi
0x140002fab  mov     rdi, rcx
0x140002fae  mov     [rbp+57h+Handle], rsi
0x140002fb2  xor     edx, edx; Val
0x140002fb4  lea     rcx, [rbp+57h+var_60]; void *
0x140002fb8  movups  xmmword ptr [rbp+57h+Msg.hwnd], xmm0
0x140002fbc  lea     ebx, [rsi+50h]
0x140002fbf  mov     r8d, ebx; Size
0x140002fc2  movups  xmmword ptr [rbp+57h+Msg.wParam], xmm0
0x140002fc6  movups  xmmword ptr [rbp+57h+Msg.time], xmm0
0x140002fca  call    memset_0
0x140002fcf  lea     rax, ?PnpWndProc@PoolNotify@@CA_JPEAUHWND__@@I_K_J@Z; PoolNotify::PnpWndProc(HWND__ *,uint,unsigned __int64,__int64)
0x140002fd6  mov     [rbp+57h+var_60.cbSize], ebx
0x140002fd9  lea     r14, ClassName; "SPACEAGENT!PNP!MESSAGEWND"
0x140002fe0  mov     [rbp+57h+var_60.lpfnWndProc], rax
0x140002fe4  lea     rcx, [rbp+57h+var_60]; WNDCLASSEXW *
0x140002fe8  mov     [rbp+57h+var_60.lpszClassName], r14
0x140002fec  call    cs:__imp_RegisterClassExW
0x140002ff2  test    ax, ax
0x140002ff5  jnz     short loc_140003002
0x140002ff7  call    cs:__imp_GetLastError
0x140002ffd  jmp     loc_1400030E5
0x140003002  mov     [rsp+0F0h+lpParam], rdi; lpParam
0x140003007  lea     r8, WindowName; "SpaceAgentPnPWatcher"
0x14000300e  mov     [rsp+0F0h+hInstance], rsi; hInstance
0x140003013  xor     r9d, r9d; dwStyle
0x140003016  mov     [rsp+0F0h+hMenu], rsi; hMenu
0x14000301b  mov     rdx, r14; lpClassName
0x14000301e  mov     [rsp+0F0h+hWndParent], 0FFFFFFFFFFFFFFFDh; hWndParent
0x140003027  xor     ecx, ecx; dwExStyle
0x140003029  mov     [rsp+0F0h+nHeight], esi; nHeight
0x14000302d  mov     [rsp+0F0h+nWidth], esi; nWidth
0x140003031  mov     [rsp+0F0h+Y], esi; Y
0x140003035  mov     [rsp+0F0h+X], esi; X
0x140003039  call    cs:__imp_CreateWindowExW
0x14000303f  mov     rbx, rax
0x140003042  test    rax, rax
0x140003045  jnz     short loc_140003052
0x140003047  call    cs:__imp_GetLastError
0x14000304d  jmp     loc_1400030DA
0x140003052  call    ?SuInitialize@@YAHXZ; SuInitialize(void)
0x140003057  test    eax, eax
0x140003059  jnz     short loc_140003063
0x14000305b  call    cs:__imp_GetLastError
0x140003061  jmp     short loc_1400030D1
0x140003063  lea     rdx, [rbp+57h+Handle]; void **
0x140003067  mov     rcx, rbx; void *
0x14000306a  call    ?SuRegisterDeviceNotification@@YAHPEAXPEAPEAX@Z; SuRegisterDeviceNotification(void *,void * *)
0x14000306f  test    eax, eax
0x140003071  jnz     short loc_14000307B
0x140003073  call    cs:__imp_GetLastError
0x140003079  jmp     short loc_1400030BD
0x14000307b  xor     r9d, r9d; wMsgFilterMax
0x14000307e  mov     [rsp+0F0h+X], esi; wRemoveMsg
0x140003082  xor     r8d, r8d; wMsgFilterMin
0x140003085  lea     rcx, [rbp+57h+Msg]; lpMsg
0x140003089  xor     edx, edx; hWnd
0x14000308b  call    cs:__imp_PeekMessageW
0x140003091  mov     rcx, [rdi+10h]; hEvent
0x140003095  call    cs:__imp_SetEvent
0x14000309b  jmp     short loc_1400030A7
0x14000309d  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1400030a1  call    cs:__imp_DispatchMessageW
0x1400030a7  xor     r9d, r9d; wMsgFilterMax
0x1400030aa  lea     rcx, [rbp+57h+Msg]; lpMsg
0x1400030ae  xor     r8d, r8d; wMsgFilterMin
0x1400030b1  xor     edx, edx; hWnd
0x1400030b3  call    cs:__imp_GetMessageW
0x1400030b9  test    eax, eax
0x1400030bb  jnz     short loc_14000309D
0x1400030bd  mov     rcx, [rbp+57h+Handle]; Handle
0x1400030c1  test    rcx, rcx
0x1400030c4  jz      short loc_1400030CC
0x1400030c6  call    cs:__imp_UnregisterDeviceNotification
0x1400030cc  call    ?SuCleanup@@YAHXZ; SuCleanup(void)
0x1400030d1  mov     rcx, rbx; hWnd
0x1400030d4  call    cs:__imp_DestroyWindow
0x1400030da  xor     edx, edx; hInstance
0x1400030dc  mov     rcx, r14; lpClassName
0x1400030df  call    cs:__imp_UnregisterClassW
0x1400030e5  lea     r11, [rsp+0F0h+var_10]
0x1400030ed  mov     [rdi+20h], esi
0x1400030f0  mov     rbx, [r11+28h]
0x1400030f4  xor     eax, eax
0x1400030f6  mov     rsi, [r11+30h]
0x1400030fa  mov     rsp, r11
0x1400030fd  pop     r14
0x1400030ff  pop     rdi
0x140003100  pop     rbp
0x140003101  retn
```
