# CallerIdentity::IsHostedWindow(HWND__ *,int *)

- ea: `0x1803593bc`
- end: `0x180359510`
- name: `?IsHostedWindow@CallerIdentity@@YAJPEAUHWND__@@PEAH@Z`
- size: `340`
- prototype: `HRESULT __fastcall(HWND__ *hwnd, int *pfHostedWindow)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180358b84`

## callees

- `0x1803593bc`
- `0x18076e110`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180359475`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180359475`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803594fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1803594fa`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180359461`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180359461`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1803594be`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1803594be`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassNameW` at `0x1803593ff`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetClassNameW` at `0x1803593ff`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1803594a4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1803594a4`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindow` at `0x180359411`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindow` at `0x180359411`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x180359483`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x1803594e1`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x180359483`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x1803594e1`

## pseudocode

```c
__int64 __fastcall CallerIdentity::IsHostedWindow(HWND hwnd, int *pfHostedWindow)
{
  HANDLE CurrentProcess; // rax
  HANDLE v6; // rax
  void *v7; // rdi
  unsigned int dwProcess; // [rsp+30h] [rbp-248h] BYREF
  PROCESS_UICONTEXT_INFORMATION uicontextInfoSelf; // [rsp+38h] [rbp-240h] BYREF
  PROCESS_UICONTEXT_INFORMATION uicontextInfo; // [rsp+40h] [rbp-238h] BYREF
  wchar_t szClassName[264]; // [rsp+50h] [rbp-228h] BYREF

  *pfHostedWindow = 0;
  do
  {
    if ( !hwnd )
      break;
    if ( GetClassNameW(hwnd, szClassName, 260) > 0
      && CompareStringOrdinal(szClassName, -1, L"ApplicationHostBridgeWindow", -1, 1) == 2 )
    {
      uicontextInfoSelf = 0;
      CurrentProcess = GetCurrentProcess();
      if ( (unsigned int)GetProcessUIContextInformation(CurrentProcess, &uicontextInfoSelf)
        && uicontextInfoSelf.processUIContext == PROCESS_UICONTEXT_IMMERSIVE_BROKER )
      {
        dwProcess = 0;
        if ( GetWindowThreadProcessId(hwnd, &dwProcess) )
        {
          v6 = OpenProcess(0x1000u, 0, dwProcess);
          v7 = v6;
          if ( v6 )
          {
            uicontextInfo = 0;
            if ( (unsigned int)GetProcessUIContextInformation(v6, &uicontextInfo) )
              *pfHostedWindow = uicontextInfo.processUIContext == PROCESS_UICONTEXT_IMMERSIVE_BROKER;
            CloseHandle(v7);
          }
        }
      }
      else
      {
        *pfHostedWindow = 1;
      }
    }
    hwnd = GetWindow(hwnd, 4u);
  }
  while ( !*pfHostedWindow );
  return 0;
}

```

## disassembly

```asm
0x1803593bc  mov     [rsp+arg_10], rbx
0x1803593c1  mov     [rsp+arg_18], rsi
0x1803593c6  push    rdi
0x1803593c7  sub     rsp, 270h
0x1803593ce  mov     rax, cs:__security_cookie
0x1803593d5  xor     rax, rsp
0x1803593d8  mov     [rsp+278h+var_18], rax
0x1803593e0  mov     rsi, pfHostedWindow
0x1803593e3  mov     dword ptr [pfHostedWindow], 0
0x1803593e9  mov     rbx, hwnd
0x1803593ec  test    rbx, rbx
0x1803593ef  jz      short loc_18035941F
0x1803593f1  mov     r8d, 104h; nMaxCount
0x1803593f7  lea     pfHostedWindow, [rsp+278h+szClassName]; lpClassName
0x1803593fc  mov     hwnd, rbx; hWnd
0x1803593ff  call    cs:__imp_GetClassNameW
0x180359405  test    eax, eax
0x180359407  jg      short loc_180359446
0x180359409  mov     edx, 4; uCmd
0x18035940e  mov     hwnd, rbx; hWnd
0x180359411  call    cs:__imp_GetWindow
0x180359417  cmp     dword ptr [rsi], 0
0x18035941a  mov     rbx, rax
0x18035941d  jz      short loc_1803593EC
0x18035941f  xor     eax, eax
0x180359421  mov     hwnd, [rsp+278h+var_18]
0x180359429  xor     hwnd, rsp; StackCookie
0x18035942c  call    __security_check_cookie
0x180359431  lea     r11, [rsp+278h+var_8]
0x180359439  mov     rbx, [r11+20h]
0x18035943d  mov     rsi, [r11+28h]
0x180359441  mov     rsp, r11
0x180359444  pop     rdi
0x180359445  retn
0x180359446  or      r9d, 0FFFFFFFFh; cchCount2
0x18035944a  mov     [rsp+278h+bIgnoreCase], 1; bIgnoreCase
0x180359452  or      edx, r9d; cchCount1
0x180359455  lea     r8, aApplicationhos; "ApplicationHostBridgeWindow"
0x18035945c  lea     hwnd, [rsp+278h+szClassName]; lpString1
0x180359461  call    cs:__imp_CompareStringOrdinal
0x180359467  cmp     eax, 2
0x18035946a  jnz     short loc_180359409
0x18035946c  mov     qword ptr [rsp+278h+uicontextInfoSelf.processUIContext], 0
0x180359475  call    cs:__imp_GetCurrentProcess
0x18035947b  mov     hwnd, rax
0x18035947e  lea     pfHostedWindow, [rsp+278h+uicontextInfoSelf]
0x180359483  call    cs:__imp_GetProcessUIContextInformation
0x180359489  test    eax, eax
0x18035948b  jz      short loc_180359505
0x18035948d  cmp     [rsp+278h+uicontextInfoSelf.processUIContext], 2
0x180359492  jnz     short loc_180359505
0x180359494  lea     pfHostedWindow, [rsp+278h+dwProcess]; lpdwProcessId
0x180359499  mov     [rsp+278h+dwProcess], 0
0x1803594a1  mov     hwnd, rbx; hWnd
0x1803594a4  call    cs:__imp_GetWindowThreadProcessId
0x1803594aa  test    eax, eax
0x1803594ac  jz      loc_180359409
0x1803594b2  mov     r8d, [rsp+278h+dwProcess]; dwProcessId
0x1803594b7  xor     edx, edx; bInheritHandle
0x1803594b9  mov     ecx, 1000h; dwDesiredAccess
0x1803594be  call    cs:__imp_OpenProcess
0x1803594c4  mov     rdi, rax
0x1803594c7  test    rax, rax
0x1803594ca  jz      loc_180359409
0x1803594d0  lea     pfHostedWindow, [rsp+278h+uicontextInfo]
0x1803594d5  mov     qword ptr [rsp+278h+uicontextInfo.processUIContext], 0
0x1803594de  mov     hwnd, rax
0x1803594e1  call    cs:__imp_GetProcessUIContextInformation
0x1803594e7  test    eax, eax
0x1803594e9  jz      short loc_1803594F7
0x1803594eb  xor     ecx, ecx
0x1803594ed  cmp     [rsp+278h+uicontextInfo.processUIContext], 2
0x1803594f2  setz    cl
0x1803594f5  mov     [rsi], ecx
0x1803594f7  mov     hwnd, rdi; hObject
0x1803594fa  call    cs:__imp_CloseHandle
0x180359500  jmp     loc_180359409
0x180359505  mov     dword ptr [rsi], 1
0x18035950b  jmp     loc_180359409
```
