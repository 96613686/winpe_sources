# CUserSettingChangeMonitor::_MonitorThreadProc(void)

- ea: `0x1800347d0`
- end: `0x180034bde`
- name: `?_MonitorThreadProc@CUserSettingChangeMonitor@@AEAAXXZ`
- size: `1038`
- prototype: `void __fastcall(LONG_PTR dwNewLong)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180060cf0`

## callees

- `0x1800347d0`
- `0x18009d010`

## import_xrefs

- `KERNEL32!OpenEventW` at `0x1800349fc`
- `KERNEL32!OpenEventW` at `0x1800349fc`
- `KERNEL32!ReleaseSRWLockShared` at `0x180034b47`
- `KERNEL32!ReleaseSRWLockShared` at `0x180034b47`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180034bb5`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180034bb5`
- `KERNEL32!AcquireSRWLockShared` at `0x180034b16`
- `KERNEL32!AcquireSRWLockShared` at `0x180034b16`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180034b9a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180034b9a`
- `KERNEL32!CloseHandle` at `0x180034bd3`
- `KERNEL32!CloseHandle` at `0x180034bd3`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x180034ae0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DispatchMessageW` at `0x180034ae0`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!UnregisterClassW` at `0x180034980`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!UnregisterClassW` at `0x180034980`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x180034973`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!DestroyWindow` at `0x180034973`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x180034ac8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x180034afa`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x180034ac8`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x180034afa`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassInfoW` at `0x180034871`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassInfoW` at `0x180034871`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassW` at `0x180034bc5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!RegisterClassW` at `0x180034bc5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x1800348af`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x1800348af`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x1800348c9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x18003496a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x1800348c9`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowLongPtrW` at `0x18003496a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!TranslateMessage` at `0x180034ad6`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!TranslateMessage` at `0x180034ad6`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjectsEx` at `0x180034a8d`
- `api-ms-win-rtcore-ntuser-synch-l1-1-0!MsgWaitForMultipleObjectsEx` at `0x180034a8d`
- `api-ms-win-rtcore-ntuser-powermanagement-l1-1-0!RegisterPowerSettingNotification` at `0x1800348fe`
- `api-ms-win-rtcore-ntuser-powermanagement-l1-1-0!RegisterPowerSettingNotification` at `0x18003491e`
- `api-ms-win-rtcore-ntuser-powermanagement-l1-1-0!RegisterPowerSettingNotification` at `0x180034939`
- `api-ms-win-rtcore-ntuser-powermanagement-l1-1-0!RegisterPowerSettingNotification` at `0x1800349a7`
- `api-ms-win-rtcore-ntuser-powermanagement-l1-1-0!RegisterPowerSettingNotification` at `0x1800348fe`
- `api-ms-win-rtcore-ntuser-powermanagement-l1-1-0!RegisterPowerSettingNotification` at `0x18003491e`
- `api-ms-win-rtcore-ntuser-powermanagement-l1-1-0!RegisterPowerSettingNotification` at `0x180034939`
- `api-ms-win-rtcore-ntuser-powermanagement-l1-1-0!RegisterPowerSettingNotification` at `0x1800349a7`
- `api-ms-win-rtcore-ntuser-powermanagement-l1-1-0!UnregisterPowerSettingNotification` at `0x18003494a`
- `api-ms-win-rtcore-ntuser-powermanagement-l1-1-0!UnregisterPowerSettingNotification` at `0x180034953`
- `api-ms-win-rtcore-ntuser-powermanagement-l1-1-0!UnregisterPowerSettingNotification` at `0x180034a38`
- `api-ms-win-rtcore-ntuser-powermanagement-l1-1-0!UnregisterPowerSettingNotification` at `0x180034a41`
- `api-ms-win-rtcore-ntuser-powermanagement-l1-1-0!UnregisterPowerSettingNotification` at `0x18003494a`
- `api-ms-win-rtcore-ntuser-powermanagement-l1-1-0!UnregisterPowerSettingNotification` at `0x180034953`
- `api-ms-win-rtcore-ntuser-powermanagement-l1-1-0!UnregisterPowerSettingNotification` at `0x180034a38`
- `api-ms-win-rtcore-ntuser-powermanagement-l1-1-0!UnregisterPowerSettingNotification` at `0x180034a41`
- `api-ms-win-power-base-l1-1-0!PowerRegisterSuspendResumeNotification` at `0x1800349e4`
- `api-ms-win-power-base-l1-1-0!PowerRegisterSuspendResumeNotification` at `0x1800349e4`
- `api-ms-win-power-base-l1-1-0!PowerUnregisterSuspendResumeNotification` at `0x180034a20`
- `api-ms-win-power-base-l1-1-0!PowerUnregisterSuspendResumeNotification` at `0x180034a20`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSRegisterSessionNotification` at `0x1800348d4`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSRegisterSessionNotification` at `0x1800348d4`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSUnRegisterSessionNotification` at `0x18003495c`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSUnRegisterSessionNotification` at `0x18003495c`
- `USER32!RegisterBSDRWindow` at `0x1800348e7`
- `USER32!RegisterBSDRWindow` at `0x1800348e7`
- `USER32!LoadCursorW` at `0x180034833`
- `USER32!LoadCursorW` at `0x180034833`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CUserSettingChangeMonitor::_MonitorThreadProc(LONG_PTR dwNewLong)
{
  HWND Window; // rax
  HWND v3; // rsi
  HPOWERNOTIFY v4; // r15
  HPOWERNOTIFY v5; // r12
  HPOWERNOTIFY v6; // r13
  HPOWERNOTIFY v7; // rbx
  char *v8; // rdi
  RTL_SRWLOCK *v9; // rdi
  DWORD v10; // eax
  __int64 v11; // rbx
  __int64 v12; // r14
  HPOWERNOTIFY v13; // [rsp+68h] [rbp-98h]
  WNDCLASSW v14; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v15[2]; // [rsp+C0h] [rbp-40h] BYREF
  HANDLE pHandles[2]; // [rsp+D0h] [rbp-30h] BYREF
  tagMSG Msg; // [rsp+E0h] [rbp-20h] BYREF
  tagWNDCLASSW WndClass; // [rsp+110h] [rbp+10h] BYREF
  __int64 v20; // [rsp+1B8h] [rbp+B8h] BYREF
  __int64 v21; // [rsp+1C0h] [rbp+C0h]
  char *v22; // [rsp+1C8h] [rbp+C8h]

  *(_QWORD *)&v14.style = 0;
  v14.cbClsExtra = 0;
  v14.hIcon = 0;
  *(_OWORD *)&v14.hbrBackground = 0;
  v14.lpfnWndProc = (WNDPROC)CUserSettingChangeMonitor::s_WndProc;
  v14.cbWndExtra = 8;
  v14.hInstance = &_ImageBase;
  v14.hCursor = LoadCursorW(0, (LPCWSTR)0x7F00);
  v14.hbrBackground = (HBRUSH)16;
  v14.lpszClassName = L"LogonUI worker window";
  memset(&WndClass, 0, sizeof(WndClass));
  if ( !GetClassInfoW(&_ImageBase, L"LogonUI worker window", &WndClass) )
    RegisterClassW(&v14);
  Window = CreateWindowExW(0, v14.lpszClassName, 0, 0, 0, 0, 0, 0, 0, 0, &_ImageBase, 0);
  v3 = Window;
  if ( Window )
  {
    SetWindowLongPtrW(Window, 0, dwNewLong);
    if ( WTSRegisterSessionNotification(v3, 0) )
    {
      if ( (unsigned int)RegisterBSDRWindow(v3, 0) )
      {
        v4 = RegisterPowerSettingNotification(v3, &GUID_CONSOLE_DISPLAY_STATE, 0);
        if ( v4 )
        {
          v5 = RegisterPowerSettingNotification(v3, &GUID_LOW_POWER_EPOCH, 0);
          if ( v5 )
          {
            v6 = RegisterPowerSettingNotification(v3, &GUID_SESSION_USER_PRESENCE, 0);
            if ( v6 )
            {
              v7 = RegisterPowerSettingNotification(v3, &GUID_LIDSWITCH_STATE_CHANGE, 0);
              v13 = v7;
              if ( v7 )
              {
                v15[0] = CUserSettingChangeMonitor::s_PowerSuspendResumeCallback;
                v15[1] = dwNewLong;
                v20 = 0;
                if ( !(unsigned int)PowerRegisterSuspendResumeNotification(2, v15, &v20) )
                {
                  v8 = (char *)OpenEventW(0x100000u, 0, L"WinSta0_DesktopSwitch");
                  v22 = v8;
                  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
                  {
                    AcquireSRWLockExclusive((PSRWLOCK)(dwNewLong + 56));
                    *(_BYTE *)(dwNewLong + 80) = 1;
                    *(_QWORD *)(dwNewLong + 88) = v3;
                    if ( dwNewLong != -56 )
                      ReleaseSRWLockExclusive((PSRWLOCK)(dwNewLong + 56));
                    pHandles[0] = *(HANDLE *)(dwNewLong + 40);
                    pHandles[1] = v8;
                    v9 = (RTL_SRWLOCK *)(dwNewLong + 56);
                    while ( 1 )
                    {
                      v10 = MsgWaitForMultipleObjectsEx(2u, pHandles, 0xFFFFFFFF, 0x1CFFu, 6u);
                      if ( !v10 )
                        break;
                      if ( v10 == 1 )
                      {
                        v11 = 0;
                        v21 = 0;
                        AcquireSRWLockShared(v9);
                        v12 = *(_QWORD *)(dwNewLong + 48);
                        if ( v12 )
                        {
                          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v12 + 8LL))(*(_QWORD *)(dwNewLong + 48));
                          v11 = v12;
                          v21 = v12;
                        }
                        if ( v9 )
                          ReleaseSRWLockShared(v9);
                        if ( v11 )
                        {
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 104LL))(v11);
                          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
                        }
                      }
                      else if ( v10 == 2 )
                      {
                        memset(&Msg, 0, sizeof(Msg));
                        while ( PeekMessageW(&Msg, 0, 0, 0, 1u) )
                        {
                          TranslateMessage(&Msg);
                          DispatchMessageW(&Msg);
                        }
                      }
                    }
                    v8 = v22;
                    v7 = v13;
                  }
                  PowerUnregisterSuspendResumeNotification(v20);
                  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
                    CloseHandle(v8);
                }
                UnregisterPowerSettingNotification(v7);
              }
              UnregisterPowerSettingNotification(v6);
            }
            UnregisterPowerSettingNotification(v5);
          }
          UnregisterPowerSettingNotification(v4);
        }
      }
      WTSUnRegisterSessionNotification(v3);
    }
    SetWindowLongPtrW(v3, 0, 0);
    DestroyWindow(v3);
    UnregisterClassW(v14.lpszClassName, &_ImageBase);
  }
}

```

## disassembly

```asm
0x1800347d0  mov     [rsp-8+arg_0], rcx
0x1800347d5  push    rbp
0x1800347d6  push    rbx
0x1800347d7  push    rsi
0x1800347d8  push    rdi
0x1800347d9  push    r12
0x1800347db  push    r13
0x1800347dd  push    r14
0x1800347df  push    r15
0x1800347e1  lea     rbp, [rsp-68h]
0x1800347e6  sub     rsp, 168h
0x1800347ed  mov     r14, rcx
0x1800347f0  xor     edi, edi
0x1800347f2  mov     qword ptr [rsp+1A0h+var_130.style], rdi
0x1800347f7  mov     [rbp+0A0h+var_130.cbClsExtra], edi
0x1800347fa  xorps   xmm0, xmm0
0x1800347fd  movdqa  xmmword ptr [rbp+0A0h+var_130.hIcon], xmm0
0x180034802  xorps   xmm1, xmm1
0x180034805  movdqa  xmmword ptr [rbp+0A0h+var_130.hbrBackground], xmm1
0x18003480a  mov     [rbp+0A0h+var_130.lpszClassName], rdi
0x18003480e  lea     rax, ?s_WndProc@CUserSettingChangeMonitor@@CA_JPEAUHWND__@@I_K_J@Z; CUserSettingChangeMonitor::s_WndProc(HWND__ *,uint,unsigned __int64,__int64)
0x180034815  mov     [rsp+1A0h+var_130.lpfnWndProc], rax
0x18003481a  mov     [rbp+0A0h+var_130.cbWndExtra], 8
0x180034821  lea     rbx, __ImageBase
0x180034828  mov     [rbp+0A0h+var_130.hInstance], rbx
0x18003482c  mov     edx, 7F00h; lpCursorName
0x180034831  xor     ecx, ecx; hInstance
0x180034833  call    cs:__imp_LoadCursorW
0x180034839  mov     [rbp+0A0h+var_130.hCursor], rax
0x18003483d  mov     [rbp+0A0h+var_130.hbrBackground], 10h
0x180034845  lea     rdx, aLogonuiWorkerW; "LogonUI worker window"
0x18003484c  mov     [rbp+0A0h+var_130.lpszClassName], rdx
0x180034850  xorps   xmm0, xmm0
0x180034853  xor     eax, eax
0x180034855  movups  xmmword ptr [rbp+0A0h+WndClass.style], xmm0
0x180034859  movups  xmmword ptr [rbp+0A0h+WndClass.cbClsExtra], xmm0
0x18003485d  movups  xmmword ptr [rbp+0A0h+WndClass.hIcon], xmm0
0x180034861  movups  xmmword ptr [rbp+0A0h+WndClass.hbrBackground], xmm0
0x180034865  mov     [rbp+0A0h+WndClass.lpszClassName], rax
0x180034869  lea     r8, [rbp+0A0h+WndClass]; lpWndClass
0x18003486d  mov     rcx, [rbp+0A0h+var_130.hInstance]; hInstance
0x180034871  call    cs:__imp_GetClassInfoW
0x180034877  test    eax, eax
0x180034879  jz      loc_180034BC0
0x18003487f  mov     [rsp+1A0h+lpParam], rdi; lpParam
0x180034884  mov     [rsp+1A0h+var_150], rbx; hInstance
0x180034889  mov     [rsp+1A0h+hMenu], rdi; hMenu
0x18003488e  mov     [rsp+1A0h+hWndParent], rdi; hWndParent
0x180034893  mov     [rsp+1A0h+nHeight], edi; nHeight
0x180034897  mov     [rsp+1A0h+nWidth], edi; nWidth
0x18003489b  mov     [rsp+1A0h+Y], edi; Y
0x18003489f  mov     [rsp+1A0h+X], edi; X
0x1800348a3  xor     r9d, r9d; dwStyle
0x1800348a6  xor     r8d, r8d; lpWindowName
0x1800348a9  mov     rdx, [rbp+0A0h+var_130.lpszClassName]; lpClassName
0x1800348ad  xor     ecx, ecx; dwExStyle
0x1800348af  call    cs:__imp_CreateWindowExW
0x1800348b5  mov     rsi, rax
0x1800348b8  test    rax, rax
0x1800348bb  jz      loc_180034986
0x1800348c1  mov     r8, r14; dwNewLong
0x1800348c4  xor     edx, edx; nIndex
0x1800348c6  mov     rcx, rax; hWnd
0x1800348c9  call    cs:__imp_SetWindowLongPtrW
0x1800348cf  xor     edx, edx; dwFlags
0x1800348d1  mov     rcx, rsi; hWnd
0x1800348d4  call    cs:__imp_WTSRegisterSessionNotification
0x1800348da  test    eax, eax
0x1800348dc  jz      loc_180034962
0x1800348e2  xor     edx, edx
0x1800348e4  mov     rcx, rsi
0x1800348e7  call    cs:__imp_RegisterBSDRWindow
0x1800348ed  test    eax, eax
0x1800348ef  jz      short loc_180034959
0x1800348f1  xor     r8d, r8d; Flags
0x1800348f4  lea     rdx, GUID_CONSOLE_DISPLAY_STATE; PowerSettingGuid
0x1800348fb  mov     rcx, rsi; hRecipient
0x1800348fe  call    cs:__imp_RegisterPowerSettingNotification
0x180034904  mov     r15, rax
0x180034907  mov     [rsp+1A0h+var_140], rax
0x18003490c  test    rax, rax
0x18003490f  jz      short loc_180034959
0x180034911  xor     r8d, r8d; Flags
0x180034914  lea     rdx, GUID_LOW_POWER_EPOCH; PowerSettingGuid
0x18003491b  mov     rcx, rsi; hRecipient
0x18003491e  call    cs:__imp_RegisterPowerSettingNotification
0x180034924  mov     r12, rax
0x180034927  test    rax, rax
0x18003492a  jz      short loc_180034950
0x18003492c  xor     r8d, r8d; Flags
0x18003492f  lea     rdx, GUID_SESSION_USER_PRESENCE; PowerSettingGuid
0x180034936  mov     rcx, rsi; hRecipient
0x180034939  call    cs:__imp_RegisterPowerSettingNotification
0x18003493f  mov     r13, rax
0x180034942  test    rax, rax
0x180034945  jnz     short loc_18003499A
0x180034947  mov     rcx, r12; Handle
0x18003494a  call    cs:__imp_UnregisterPowerSettingNotification
0x180034950  mov     rcx, r15; Handle
0x180034953  call    cs:__imp_UnregisterPowerSettingNotification
0x180034959  mov     rcx, rsi; hWnd
0x18003495c  call    cs:__imp_WTSUnRegisterSessionNotification
0x180034962  xor     r8d, r8d; dwNewLong
0x180034965  xor     edx, edx; nIndex
0x180034967  mov     rcx, rsi; hWnd
0x18003496a  call    cs:__imp_SetWindowLongPtrW
0x180034970  mov     rcx, rsi; hWnd
0x180034973  call    cs:__imp_DestroyWindow
0x180034979  mov     rdx, rbx; hInstance
0x18003497c  mov     rcx, [rbp+0A0h+var_130.lpszClassName]; lpClassName
0x180034980  call    cs:__imp_UnregisterClassW
0x180034986  add     rsp, 168h
0x18003498d  pop     r15
0x18003498f  pop     r14
0x180034991  pop     r13
0x180034993  pop     r12
0x180034995  pop     rdi
0x180034996  pop     rsi
0x180034997  pop     rbx
0x180034998  pop     rbp
0x180034999  retn
0x18003499a  xor     r8d, r8d; Flags
0x18003499d  lea     rdx, GUID_LIDSWITCH_STATE_CHANGE; PowerSettingGuid
0x1800349a4  mov     rcx, rsi; hRecipient
0x1800349a7  call    cs:__imp_RegisterPowerSettingNotification
0x1800349ad  mov     rbx, rax
0x1800349b0  mov     [rsp+1A0h+var_138], rax
0x1800349b5  test    rax, rax
0x1800349b8  jz      loc_180034A3E
0x1800349be  lea     rax, ?s_PowerSuspendResumeCallback@CUserSettingChangeMonitor@@CAKPEAXK0@Z; CUserSettingChangeMonitor::s_PowerSuspendResumeCallback(void *,ulong,void *)
0x1800349c5  mov     [rbp+0A0h+var_E0], rax
0x1800349c9  mov     [rbp+0A0h+var_D8], r14
0x1800349cd  mov     [rbp+0A0h+arg_8], rdi
0x1800349d4  lea     r8, [rbp+0A0h+arg_8]
0x1800349db  lea     rdx, [rbp+0A0h+var_E0]
0x1800349df  mov     ecx, 2
0x1800349e4  call    cs:__imp_PowerRegisterSuspendResumeNotification
0x1800349ea  test    eax, eax
0x1800349ec  jnz     short loc_180034A35
0x1800349ee  lea     r8, aWinsta0Desktop; "WinSta0_DesktopSwitch"
0x1800349f5  xor     edx, edx; bInheritHandle
0x1800349f7  mov     ecx, 100000h; dwDesiredAccess
0x1800349fc  call    cs:__imp_OpenEventW
0x180034a02  mov     rdi, rax
0x180034a05  mov     [rbp+0A0h+arg_18], rax
0x180034a0c  dec     rax
0x180034a0f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180034a13  jbe     loc_180034B93
0x180034a19  mov     rcx, [rbp+0A0h+arg_8]
0x180034a20  call    cs:__imp_PowerUnregisterSuspendResumeNotification
0x180034a26  nop
0x180034a27  lea     rax, [rdi-1]
0x180034a2b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180034a2f  jbe     loc_180034BD0
0x180034a35  mov     rcx, rbx; Handle
0x180034a38  call    cs:__imp_UnregisterPowerSettingNotification
0x180034a3e  mov     rcx, r13; Handle
0x180034a41  call    cs:__imp_UnregisterPowerSettingNotification
0x180034a47  lea     rbx, __ImageBase
0x180034a4e  jmp     loc_180034947
0x180034a53  mov     r15, [rbp+0A0h+arg_0]
0x180034a5a  mov     rax, [r15+28h]
0x180034a5e  mov     [rbp+0A0h+pHandles], rax
0x180034a62  mov     [rbp+0A0h+var_C8], rdi
0x180034a66  mov     rdi, rbx
0x180034a69  nop     dword ptr [rax+00000000h]
0x180034a70  mov     [rsp+1A0h+X], 6; dwFlags
0x180034a78  mov     r9d, 1CFFh; dwWakeMask
0x180034a7e  mov     r8d, 0FFFFFFFFh; dwMilliseconds
0x180034a84  lea     rdx, [rbp+0A0h+pHandles]; pHandles
0x180034a88  mov     ecx, 2; nCount
0x180034a8d  call    cs:__imp_MsgWaitForMultipleObjectsEx
0x180034a93  test    eax, eax
0x180034a95  jz      loc_180034B7D
0x180034a9b  cmp     eax, 1
0x180034a9e  jz      short loc_180034B0A
0x180034aa0  cmp     eax, 2
0x180034aa3  jnz     short loc_180034A70
0x180034aa5  xorps   xmm0, xmm0
0x180034aa8  movups  xmmword ptr [rbp+0A0h+Msg.hwnd], xmm0
0x180034aac  movups  xmmword ptr [rbp+0A0h+Msg.wParam], xmm0
0x180034ab0  movups  xmmword ptr [rbp+0A0h+Msg.time], xmm0
0x180034ab4  mov     [rsp+1A0h+X], 1; wRemoveMsg
0x180034abc  xor     r9d, r9d; wMsgFilterMax
0x180034abf  xor     r8d, r8d; wMsgFilterMin
0x180034ac2  xor     edx, edx; hWnd
0x180034ac4  lea     rcx, [rbp+0A0h+Msg]; lpMsg
0x180034ac8  call    cs:__imp_PeekMessageW
0x180034ace  test    eax, eax
0x180034ad0  jz      short loc_180034A70
0x180034ad2  lea     rcx, [rbp+0A0h+Msg]; lpMsg
0x180034ad6  call    cs:__imp_TranslateMessage
0x180034adc  lea     rcx, [rbp+0A0h+Msg]; lpMsg
0x180034ae0  call    cs:__imp_DispatchMessageW
0x180034ae6  mov     [rsp+1A0h+X], 1; wRemoveMsg
0x180034aee  xor     r9d, r9d; wMsgFilterMax
0x180034af1  xor     r8d, r8d; wMsgFilterMin
0x180034af4  xor     edx, edx; hWnd
0x180034af6  lea     rcx, [rbp+0A0h+Msg]; lpMsg
0x180034afa  call    cs:__imp_PeekMessageW
0x180034b00  test    eax, eax
0x180034b02  jz      loc_180034A70
0x180034b08  jmp     short loc_180034AD2
0x180034b0a  xor     ebx, ebx
0x180034b0c  mov     [rbp+0A0h+arg_10], rbx
0x180034b13  mov     rcx, rdi; SRWLock
0x180034b16  call    cs:__imp_AcquireSRWLockShared
0x180034b1c  mov     r14, [r15+30h]
0x180034b20  test    r14, r14
0x180034b23  jz      short loc_180034B3F
0x180034b25  mov     rax, [r14]
0x180034b28  mov     rcx, r14
0x180034b2b  mov     rax, [rax+8]
0x180034b2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b34  nop
0x180034b35  mov     rbx, r14
0x180034b38  mov     [rbp+0A0h+arg_10], rbx
0x180034b3f  test    rdi, rdi
0x180034b42  jz      short loc_180034B4D
0x180034b44  mov     rcx, rdi; SRWLock
0x180034b47  call    cs:__imp_ReleaseSRWLockShared
0x180034b4d  test    rbx, rbx
0x180034b50  jnz     short loc_180034B6C
0x180034b52  test    rbx, rbx
0x180034b55  jz      short loc_180034B67
0x180034b57  mov     rax, [rbx]
0x180034b5a  mov     rcx, rbx
0x180034b5d  mov     rax, [rax+10h]
0x180034b61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b66  nop
0x180034b67  jmp     loc_180034A70
0x180034b6c  mov     rax, [rbx]
0x180034b6f  mov     rcx, rbx
0x180034b72  mov     rax, [rax+68h]
0x180034b76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034b7b  jmp     short loc_180034B52
0x180034b7d  mov     rdi, [rbp+0A0h+arg_18]
0x180034b84  mov     r15, [rsp+1A0h+var_140]
0x180034b89  mov     rbx, [rsp+1A0h+var_138]
0x180034b8e  jmp     loc_180034A19
0x180034b93  lea     rbx, [r14+38h]
0x180034b97  mov     rcx, rbx; SRWLock
0x180034b9a  call    cs:__imp_AcquireSRWLockExclusive
0x180034ba0  mov     byte ptr [r14+50h], 1
0x180034ba5  mov     [r14+58h], rsi
0x180034ba9  test    rbx, rbx
0x180034bac  jz      loc_180034A53
0x180034bb2  mov     rcx, rbx; SRWLock
0x180034bb5  call    cs:__imp_ReleaseSRWLockExclusive
0x180034bbb  jmp     loc_180034A53
0x180034bc0  lea     rcx, [rsp+1A0h+var_130]; lpWndClass
0x180034bc5  call    cs:__imp_RegisterClassW
0x180034bcb  jmp     loc_18003487F
0x180034bd0  mov     rcx, rdi; hObject
0x180034bd3  call    cs:__imp_CloseHandle
0x180034bd9  jmp     loc_180034A35
```
