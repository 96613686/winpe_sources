# DdcStateController::IntegrityCheck(void)

- ea: `0x18000f35c`
- end: `0x18000f52c`
- name: `?IntegrityCheck@DdcStateController@@SAJXZ`
- size: `464`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180004640`

## callees

- `0x1800024c0`
- `0x180005060`
- `0x1800050b8`
- `0x180005190`
- `0x18000f35c`
- `0x18000f534`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f406`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000f406`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000f3a9`
- `api-ms-win-core-synch-l1-1-0!CreateMutexW` at `0x18000f3a9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000f4e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18000f4e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f3b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f467`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f3b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f467`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f4ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f4ef`

## string_xrefs

- `0x18000f3e8`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcstatecontroller.cpp`
- `0x18000f451`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcstatecontroller.cpp`
- `0x18000f4cb`: `onecoreuap\shell\devicedirectory\devicedirectoryclient\lib\ddcstatecontroller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DdcStateController::IntegrityCheck(__int64 a1, __int64 a2, __int64 a3)
{
  HANDLE MutexW; // rax
  void *v4; // rdi
  signed int v5; // eax
  int v6; // edx
  __int64 v7; // rcx
  signed int v8; // ebx
  DWORD v9; // eax
  int v10; // edx
  int v11; // ecx
  int v12; // esi
  signed int LastError; // eax
  int v14; // edx
  int v15; // ecx
  int v16; // edx
  int v17; // ecx
  __int64 v19; // [rsp+30h] [rbp-28h] BYREF

  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(a1, DEVICE_DIRECTORY_CLIENT_PROCESS_STATE_CHANGE_CALLED, a3, 1, &v19);
  MutexW = CreateMutexW(0, 0, L"Local\\C9E8AF12-FA27-4748-EC04-38CA71239739_RegisterDevice");
  v4 = MutexW;
  if ( MutexW )
  {
    v9 = WaitForSingleObject(MutexW, 0);
    switch ( v9 )
    {
      case 0u:
      case 0x80u:
        v12 = 1;
        break;
      case 0x102u:
        v8 = 0;
LABEL_27:
        CloseHandle(v4);
        goto LABEL_28;
      case 0xFFFFFFFF:
        v12 = 0;
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        if ( v8 < 0 )
        {
          if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
            McTemplateU0dsqs_EventWriteTransfer(
              v15,
              v14,
              v8,
              (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcstatecontroller.cpp",
              62,
              "CHR(HRESULT_FROM_WIN32(GetLastError()))");
          goto LABEL_27;
        }
        break;
      default:
        v8 = -2147418113;
        if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
          McTemplateU0dsqs_EventWriteTransfer(
            v11,
            v10,
            -2147418113,
            (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcstatecontroller.cpp",
            67,
            "CHR(((HRESULT)0x8000FFFFL))");
        goto LABEL_27;
    }
    v8 = DdcStateController::ProcessStateChange();
    if ( v8 < 0 && (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
      McTemplateU0dsqs_EventWriteTransfer(
        v17,
        v16,
        v8,
        (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcstatecontroller.cpp",
        70,
        "CHR(ProcessStateChange())");
    if ( v12 )
      ReleaseMutex(v4);
    goto LABEL_27;
  }
  v5 = GetLastError();
  v8 = v5;
  if ( v5 > 0 )
    v8 = (unsigned __int16)v5 | 0x80070000;
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 1) != 0 )
    McTemplateU0dsqs_EventWriteTransfer(
      v7,
      v6,
      v8,
      (unsigned int)"onecoreuap\\shell\\devicedirectory\\devicedirectoryclient\\lib\\ddcstatecontroller.cpp",
      45,
      "CBR(hMutex != 0)");
LABEL_28:
  if ( (Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits & 2) != 0 )
    McTemplateU0q_EventWriteTransfer(v7, DEVICE_DIRECTORY_CLIENT_PROCESS_STATE_CHANGE_RESULT, (unsigned int)v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000f35c  mov     r11, rsp
0x18000f35f  mov     [r11+8], rbx
0x18000f363  mov     [r11+10h], rsi
0x18000f367  push    rdi
0x18000f368  sub     rsp, 50h
0x18000f36c  mov     rax, cs:__security_cookie
0x18000f373  xor     rax, rsp
0x18000f376  mov     [rsp+58h+var_18], rax
0x18000f37b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 2
0x18000f382  jz      short loc_18000F39E
0x18000f384  lea     rax, [r11-28h]
0x18000f388  mov     r9d, 1
0x18000f38e  lea     rdx, DEVICE_DIRECTORY_CLIENT_PROCESS_STATE_CHANGE_CALLED
0x18000f395  mov     [r11-38h], rax
0x18000f399  call    McGenEventWrite_EventWriteTransfer
0x18000f39e  lea     r8, Name; "Local\\C9E8AF12-FA27-4748-EC04-38CA7123"...
0x18000f3a5  xor     edx, edx; bInitialOwner
0x18000f3a7  xor     ecx, ecx; lpMutexAttributes
0x18000f3a9  call    cs:__imp_CreateMutexW
0x18000f3af  mov     rdi, rax
0x18000f3b2  test    rax, rax
0x18000f3b5  jnz     short loc_18000F401
0x18000f3b7  call    cs:__imp_GetLastError
0x18000f3bd  mov     ebx, eax
0x18000f3bf  test    eax, eax
0x18000f3c1  jle     short loc_18000F3CC
0x18000f3c3  movzx   ebx, ax
0x18000f3c6  or      ebx, 80070000h
0x18000f3cc  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000f3d3  jz      loc_18000F4F5
0x18000f3d9  lea     rax, aCbrHmutex0; "CBR(hMutex != 0)"
0x18000f3e0  mov     r8d, ebx
0x18000f3e3  mov     [rsp+58h+var_30], rax
0x18000f3e8  lea     r9, aOnecoreuapShel; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000f3ef  mov     [rsp+58h+var_38], 2Dh ; '-'
0x18000f3f7  call    McTemplateU0dsqs_EventWriteTransfer
0x18000f3fc  jmp     loc_18000F4F5
0x18000f401  xor     edx, edx; dwMilliseconds
0x18000f403  mov     rcx, rdi; hHandle
0x18000f406  call    cs:__imp_WaitForSingleObject
0x18000f40c  test    eax, eax
0x18000f40e  jz      loc_18000F4A3
0x18000f414  cmp     eax, 80h
0x18000f419  jz      loc_18000F4A3
0x18000f41f  cmp     eax, 102h
0x18000f424  jz      short loc_18000F49F
0x18000f426  cmp     eax, 0FFFFFFFFh
0x18000f429  jz      short loc_18000F465
0x18000f42b  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000f432  mov     ebx, 8000FFFFh
0x18000f437  jz      loc_18000F4EC
0x18000f43d  lea     rax, aChrHresult0x80_1; "CHR(((HRESULT)0x8000FFFFL))"
0x18000f444  mov     [rsp+58h+var_30], rax
0x18000f449  mov     [rsp+58h+var_38], 43h ; 'C'
0x18000f451  lea     r9, aOnecoreuapShel; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000f458  mov     r8d, ebx
0x18000f45b  call    McTemplateU0dsqs_EventWriteTransfer
0x18000f460  jmp     loc_18000F4EC
0x18000f465  xor     esi, esi
0x18000f467  call    cs:__imp_GetLastError
0x18000f46d  mov     ebx, eax
0x18000f46f  test    eax, eax
0x18000f471  jle     short loc_18000F47C
0x18000f473  movzx   ebx, ax
0x18000f476  or      ebx, 80070000h
0x18000f47c  test    ebx, ebx
0x18000f47e  jns     short loc_18000F4A8
0x18000f480  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000f487  jz      short loc_18000F4EC
0x18000f489  lea     rax, aChrHresultFrom_0; "CHR(HRESULT_FROM_WIN32(GetLastError()))"
0x18000f490  mov     [rsp+58h+var_30], rax
0x18000f495  mov     [rsp+58h+var_38], 3Eh ; '>'
0x18000f49d  jmp     short loc_18000F451
0x18000f49f  xor     ebx, ebx
0x18000f4a1  jmp     short loc_18000F4EC
0x18000f4a3  mov     esi, 1
0x18000f4a8  call    ?ProcessStateChange@DdcStateController@@SAJXZ; DdcStateController::ProcessStateChange(void)
0x18000f4ad  mov     ebx, eax
0x18000f4af  test    eax, eax
0x18000f4b1  jns     short loc_18000F4DF
0x18000f4b3  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 1
0x18000f4ba  jz      short loc_18000F4DF
0x18000f4bc  lea     rax, aChrProcessstat; "CHR(ProcessStateChange())"
0x18000f4c3  mov     r8d, ebx
0x18000f4c6  mov     [rsp+58h+var_30], rax
0x18000f4cb  lea     r9, aOnecoreuapShel; "onecoreuap\\shell\\devicedirectory\\dev"...
0x18000f4d2  mov     [rsp+58h+var_38], 46h ; 'F'
0x18000f4da  call    McTemplateU0dsqs_EventWriteTransfer
0x18000f4df  test    esi, esi
0x18000f4e1  jz      short loc_18000F4EC
0x18000f4e3  mov     rcx, rdi; hMutex
0x18000f4e6  call    cs:__imp_ReleaseMutex
0x18000f4ec  mov     rcx, rdi; hObject
0x18000f4ef  call    cs:__imp_CloseHandle
0x18000f4f5  test    cs:Microsoft_Windows_DeviceDirectory_DeviceDirectoryClient_ETWEnableBits, 2
0x18000f4fc  jz      short loc_18000F50D
0x18000f4fe  mov     r8d, ebx
0x18000f501  lea     rdx, DEVICE_DIRECTORY_CLIENT_PROCESS_STATE_CHANGE_RESULT
0x18000f508  call    McTemplateU0q_EventWriteTransfer
0x18000f50d  mov     eax, ebx
0x18000f50f  mov     rcx, [rsp+58h+var_18]
0x18000f514  xor     rcx, rsp; StackCookie
0x18000f517  call    __security_check_cookie
0x18000f51c  mov     rbx, [rsp+58h+arg_0]
0x18000f521  mov     rsi, [rsp+58h+arg_8]
0x18000f526  add     rsp, 50h
0x18000f52a  pop     rdi
0x18000f52b  retn
```
