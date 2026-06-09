# WinMain

- ea: `0x140003cf8`
- end: `0x140003ef2`
- name: `WinMain`
- size: `506`
- prototype: `int __stdcall(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nShowCmd)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140001ad8`

## callees

- `0x14000267c`
- `0x140003984`
- `0x140003ab8`
- `0x140003c48`
- `0x140003cf8`

## import_xrefs

- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x140003dc5`
- `api-ms-win-eventing-classicprovider-l1-1-0!RegisterTraceGuidsW` at `0x140003dc5`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x140003ec9`
- `api-ms-win-eventing-classicprovider-l1-1-0!UnregisterTraceGuids` at `0x140003ec9`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140003d2d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x140003d2d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140003e82`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x140003e82`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140003e0c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140003e0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003d1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003d1b`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x140003d11`
- `api-ms-win-core-heap-l1-1-0!HeapSetInformation` at `0x140003d11`
- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x140003e65`
- `ext-ms-win-ntuser-window-l1-1-0!DestroyWindow` at `0x140003e65`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassW` at `0x140003e75`
- `ext-ms-win-ntuser-windowclass-l1-1-0!UnregisterClassW` at `0x140003e75`

## pseudocode

```c
int __stdcall WinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nShowCmd)
{
  ULONG64 *v6; // rbx
  const GUID **v7; // rdi
  const GUID *v8; // r8
  int v9; // edi
  _UNKNOWN **v10; // rbx
  TRACEHANDLE v11; // rcx
  struct _TRACE_GUID_REGISTRATION TraceGuidReg; // [rsp+40h] [rbp-38h] BYREF

  if ( !HeapSetInformation(0, HeapEnableTerminationOnCorruption, 0, 0) )
    return GetLastError();
  InitializeCriticalSection(&g_CriticalSection);
  qword_14000C860 = 0;
  v6 = (ULONG64 *)&WPP_MAIN_CB;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_WinRM;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  v7 = (const GUID **)&WPP_REGISTRATION_GUIDS;
  WPP_MAIN_CB = 0;
  qword_14000C868 = 1;
  do
  {
    v8 = *v7;
    TraceGuidReg.Guid = v8;
    ++v7;
    TraceGuidReg.RegHandle = 0;
    v6[4] = (ULONG64)v8;
    RegisterTraceGuidsW(WppControlCallback, v6, v8, 1u, &TraceGuidReg, 0, 0, v6 + 1);
    v6 = (ULONG64 *)*v6;
  }
  while ( v6 );
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_b31ecff79cb331789948a4f8474fa944_Traceguids);
  g_shutdownEvent = CreateEventW(0, 0, 0, 0);
  if ( !g_shutdownEvent )
    return GetLastError();
  if ( !IsCreateWindowExWPresent() )
  {
    g_Hwnd = (HWND)1;
    goto LABEL_13;
  }
  v9 = 0;
  g_Hwnd = WindowsStart(hInstance);
  if ( g_Hwnd )
  {
LABEL_13:
    v9 = WorkLoop();
    if ( IsCreateWindowExWPresent() )
    {
      DestroyWindow(g_Hwnd);
      UnregisterClassW(L"WSMan Provider Host", hInstance);
    }
  }
  DeleteCriticalSection(&g_CriticalSection);
  v10 = (_UNKNOWN **)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x100) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_b31ecff79cb331789948a4f8474fa944_Traceguids);
      v10 = (_UNKNOWN **)WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control )
    {
      while ( v10 )
      {
        v11 = (TRACEHANDLE)v10[1];
        if ( v11 )
        {
          UnregisterTraceGuids(v11);
          v10[1] = 0;
        }
        v10 = (_UNKNOWN **)*v10;
      }
      WPP_GLOBAL_Control = &WPP_GLOBAL_Control;
    }
  }
  return v9;
}

```

## disassembly

```asm
0x140003cf8  push    rbx
0x140003cfa  push    rsi
0x140003cfb  push    rdi
0x140003cfc  push    r14
0x140003cfe  sub     rsp, 58h
0x140003d02  xor     r9d, r9d; HeapInformationLength
0x140003d05  mov     rsi, rcx
0x140003d08  xor     r8d, r8d; HeapInformation
0x140003d0b  xor     ecx, ecx; HeapHandle
0x140003d0d  lea     edx, [r9+1]; HeapInformationClass
0x140003d11  call    cs:__imp_HeapSetInformation
0x140003d17  test    eax, eax
0x140003d19  jnz     short loc_140003D26
0x140003d1b  call    cs:__imp_GetLastError
0x140003d21  jmp     loc_140003EE8
0x140003d26  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140003d2d  call    cs:__imp_InitializeCriticalSection
0x140003d33  lea     rax, WPP_ThisDir_CTLGUID_WinRM
0x140003d3a  mov     cs:qword_14000C860, 0
0x140003d45  lea     rbx, WPP_MAIN_CB
0x140003d4c  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x140003d53  mov     cs:WPP_GLOBAL_Control, rbx
0x140003d5a  lea     rdi, WPP_REGISTRATION_GUIDS
0x140003d61  mov     cs:WPP_MAIN_CB, 0
0x140003d6c  mov     cs:qword_14000C868, 1
0x140003d77  mov     r8, [rdi]; ControlGuid
0x140003d7a  lea     rax, [rbx+8]
0x140003d7e  mov     [rsp+78h+RegistrationHandle], rax; RegistrationHandle
0x140003d83  lea     rcx, WppControlCallback; RequestAddress
0x140003d8a  mov     [rsp+78h+MofResourceName], 0; MofResourceName
0x140003d93  lea     rax, [rsp+78h+var_38]
0x140003d98  mov     [rsp+78h+var_38.Guid], r8
0x140003d9d  lea     rdi, [rdi+8]
0x140003da1  mov     [rsp+78h+var_38.RegHandle], 0
0x140003daa  mov     r9d, 1; GuidCount
0x140003db0  mov     [rsp+78h+MofImagePath], 0; MofImagePath
0x140003db9  mov     rdx, rbx; RequestContext
0x140003dbc  mov     [rsp+78h+TraceGuidReg], rax; TraceGuidReg
0x140003dc1  mov     [rbx+20h], r8
0x140003dc5  call    cs:__imp_RegisterTraceGuidsW
0x140003dcb  mov     rbx, [rbx]
0x140003dce  test    rbx, rbx
0x140003dd1  jnz     short loc_140003D77
0x140003dd3  mov     rcx, cs:WPP_GLOBAL_Control
0x140003dda  lea     r14, WPP_GLOBAL_Control
0x140003de1  cmp     rcx, r14
0x140003de4  jz      short loc_140003E02
0x140003de6  test    dword ptr [rcx+1Ch], 100h
0x140003ded  jz      short loc_140003E02
0x140003def  mov     rcx, [rcx+10h]
0x140003df3  lea     edx, [rbx+15h]
0x140003df6  lea     r8, WPP_b31ecff79cb331789948a4f8474fa944_Traceguids
0x140003dfd  call    WPP_SF_
0x140003e02  xor     r9d, r9d; lpName
0x140003e05  xor     r8d, r8d; bInitialState
0x140003e08  xor     edx, edx; bManualReset
0x140003e0a  xor     ecx, ecx; lpEventAttributes
0x140003e0c  call    cs:__imp_CreateEventW
0x140003e12  mov     cs:?g_shutdownEvent@@3PEAXEA, rax; void * g_shutdownEvent
0x140003e19  test    rax, rax
0x140003e1c  jz      loc_140003D1B
0x140003e22  call    IsCreateWindowExWPresent
0x140003e27  test    al, al
0x140003e29  jz      short loc_140003E43
0x140003e2b  mov     rcx, rsi; hInstance
0x140003e2e  xor     edi, edi
0x140003e30  call    ?WindowsStart@@YAPEAUHWND__@@PEAUHINSTANCE__@@@Z; WindowsStart(HINSTANCE__ *)
0x140003e35  mov     cs:?g_Hwnd@@3PEAUHWND__@@EA, rax; HWND__ * g_Hwnd
0x140003e3c  test    rax, rax
0x140003e3f  jz      short loc_140003E7B
0x140003e41  jmp     short loc_140003E4E
0x140003e43  mov     cs:?g_Hwnd@@3PEAUHWND__@@EA, 1; HWND__ * g_Hwnd
0x140003e4e  call    ?WorkLoop@@YAKXZ; WorkLoop(void)
0x140003e53  mov     edi, eax
0x140003e55  call    IsCreateWindowExWPresent
0x140003e5a  test    al, al
0x140003e5c  jz      short loc_140003E7B
0x140003e5e  mov     rcx, cs:?g_Hwnd@@3PEAUHWND__@@EA; hWnd
0x140003e65  call    cs:__imp_DestroyWindow
0x140003e6b  mov     rdx, rsi; hInstance
0x140003e6e  lea     rcx, ClassName; "WSMan Provider Host"
0x140003e75  call    cs:__imp_UnregisterClassW
0x140003e7b  lea     rcx, ?g_CriticalSection@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x140003e82  call    cs:__imp_DeleteCriticalSection
0x140003e88  mov     rbx, cs:WPP_GLOBAL_Control
0x140003e8f  cmp     rbx, r14
0x140003e92  jz      short loc_140003EE6
0x140003e94  test    dword ptr [rbx+1Ch], 100h
0x140003e9b  jz      short loc_140003EB9
0x140003e9d  mov     rcx, [rbx+10h]
0x140003ea1  lea     r8, WPP_b31ecff79cb331789948a4f8474fa944_Traceguids
0x140003ea8  mov     edx, 16h
0x140003ead  call    WPP_SF_
0x140003eb2  mov     rbx, cs:WPP_GLOBAL_Control
0x140003eb9  cmp     rbx, r14
0x140003ebc  jz      short loc_140003EE6
0x140003ebe  jmp     short loc_140003EDA
0x140003ec0  mov     rcx, [rbx+8]; RegistrationHandle
0x140003ec4  test    rcx, rcx
0x140003ec7  jz      short loc_140003ED7
0x140003ec9  call    cs:__imp_UnregisterTraceGuids
0x140003ecf  mov     qword ptr [rbx+8], 0
0x140003ed7  mov     rbx, [rbx]
0x140003eda  test    rbx, rbx
0x140003edd  jnz     short loc_140003EC0
0x140003edf  mov     cs:WPP_GLOBAL_Control, r14
0x140003ee6  mov     eax, edi
0x140003ee8  add     rsp, 58h
0x140003eec  pop     r14
0x140003eee  pop     rdi
0x140003eef  pop     rsi
0x140003ef0  pop     rbx
0x140003ef1  retn
```
