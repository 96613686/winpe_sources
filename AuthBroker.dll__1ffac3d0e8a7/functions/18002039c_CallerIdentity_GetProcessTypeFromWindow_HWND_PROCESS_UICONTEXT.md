# CallerIdentity::GetProcessTypeFromWindow(HWND__ *,PROCESS_UICONTEXT *)

- ea: `0x18002039c`
- end: `0x180020439`
- name: `?GetProcessTypeFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAW4PROCESS_UICONTEXT@@@Z`
- size: `157`
- prototype: `HRESULT __fastcall(HWND__ *hwnd, PROCESS_UICONTEXT *pProcessUIContext)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800127f0`

## callees

- `0x180013b2c`
- `0x18002039c`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020421`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020421`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800203db`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800203db`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x180020405`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x180020405`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800203ba`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x1800203ba`

## pseudocode

```c
__int64 __fastcall CallerIdentity::GetProcessTypeFromWindow(HWND hwnd, PROCESS_UICONTEXT *pProcessUIContext)
{
  int Error; // ebx
  HANDLE v4; // rdi
  unsigned int dwPid; // [rsp+40h] [rbp+18h] BYREF
  PROCESS_UICONTEXT_INFORMATION uicontextInfo; // [rsp+48h] [rbp+20h] BYREF

  dwPid = 0;
  if ( GetWindowThreadProcessId(hwnd, &dwPid) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    v4 = OpenProcess(0x1000u, 0, dwPid);
    if ( v4 || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      uicontextInfo = 0;
      if ( (unsigned int)GetProcessUIContextInformation(v4, &uicontextInfo) )
      {
        Error = 0;
        *pProcessUIContext = uicontextInfo.processUIContext;
      }
      else
      {
        Error = -2147024890;
      }
      CloseHandle(v4);
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18002039c  mov     rax, rsp
0x18002039f  mov     [rax+8], rbx
0x1800203a3  mov     [rax+10h], rsi
0x1800203a7  push    rdi
0x1800203a8  sub     rsp, 20h
0x1800203ac  mov     rsi, pProcessUIContext
0x1800203af  mov     dword ptr [rax+18h], 0
0x1800203b6  lea     pProcessUIContext, [rax+18h]; lpdwProcessId
0x1800203ba  call    cs:__imp_GetWindowThreadProcessId
0x1800203c0  test    eax, eax
0x1800203c2  jnz     short loc_1800203CF
0x1800203c4  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800203c9  mov     ebx, eax
0x1800203cb  test    eax, eax
0x1800203cd  js      short loc_180020427
0x1800203cf  mov     r8d, [rsp+28h+dwPid]; dwProcessId
0x1800203d4  xor     edx, edx; bInheritHandle
0x1800203d6  mov     ecx, 1000h; dwDesiredAccess
0x1800203db  call    cs:__imp_OpenProcess
0x1800203e1  mov     rdi, rax
0x1800203e4  test    rax, rax
0x1800203e7  jnz     short loc_1800203F4
0x1800203e9  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800203ee  mov     ebx, eax
0x1800203f0  test    eax, eax
0x1800203f2  js      short loc_180020427
0x1800203f4  lea     pProcessUIContext, [rsp+28h+uicontextInfo]
0x1800203f9  mov     qword ptr [rsp+28h+uicontextInfo.processUIContext], 0
0x180020402  mov     hwnd, rdi
0x180020405  call    cs:__imp_GetProcessUIContextInformation
0x18002040b  test    eax, eax
0x18002040d  jz      short loc_180020419
0x18002040f  mov     eax, [rsp+28h+uicontextInfo.processUIContext]
0x180020413  xor     ebx, ebx
0x180020415  mov     [rsi], eax
0x180020417  jmp     short loc_18002041E
0x180020419  mov     ebx, 80070006h
0x18002041e  mov     hwnd, rdi; hObject
0x180020421  call    cs:__imp_CloseHandle
0x180020427  mov     rsi, [rsp+28h+arg_8]
0x18002042c  mov     eax, ebx
0x18002042e  mov     rbx, [rsp+28h+arg_0]
0x180020433  add     rsp, 20h
0x180020437  pop     rdi
0x180020438  retn
```
