# Windows::Internal::ShouldUseRestrictedModeKeyboard(void)

- ea: `0x180030348`
- end: `0x180030405`
- name: `?ShouldUseRestrictedModeKeyboard@Internal@Windows@@YA_NXZ`
- size: `189`
- prototype: `bool __fastcall(Windows::Internal *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180044ff4`
- `0x180045ae4`
- `0x1800a7100`

## callees

- `0x180030348`
- `0x180050ba0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800303be`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800303be`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x1800303da`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x1800303da`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003035d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003035d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800303e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800303e6`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1800303a3`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x1800303a3`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x180030365`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x180030365`

## pseudocode

```c
bool __fastcall Windows::Internal::ShouldUseRestrictedModeKeyboard(Windows::Internal *this)
{
  DWORD CurrentThreadId; // eax
  HDESK ThreadDesktop; // rax
  HANDLE v4; // rbx
  __int128 v5; // [rsp+30h] [rbp-48h] BYREF
  wchar_t v6; // [rsp+40h] [rbp-38h]
  _BYTE pvInfo[16]; // [rsp+48h] [rbp-30h] BYREF
  __int16 v8; // [rsp+58h] [rbp-20h]

  CurrentThreadId = GetCurrentThreadId();
  ThreadDesktop = GetThreadDesktop(CurrentThreadId);
  if ( ThreadDesktop )
  {
    v6 = aWinlogon[8];
    v5 = *(_OWORD *)L"Winlogon";
    if ( GetUserObjectInformationW(ThreadDesktop, 2, pvInfo, 0x12u, 0) )
    {
      v8 = 0;
      if ( !(unsigned int)_o__wcsicmp(pvInfo, &v5) )
        return 1;
    }
  }
  v4 = OpenMutexW(0x100000u, 0, L"Global\\Windows.Machine.OOBE");
  CloseHandle(v4);
  return v4 != 0;
}

```

## disassembly

```asm
0x180030348  push    rbx
0x18003034a  sub     rsp, 70h
0x18003034e  mov     rax, cs:__security_cookie
0x180030355  xor     rax, rsp
0x180030358  mov     [rsp+78h+var_18], rax
0x18003035d  call    cs:__imp_GetCurrentThreadId
0x180030363  mov     ecx, eax; dwThreadId
0x180030365  call    cs:__imp_GetThreadDesktop
0x18003036b  test    rax, rax
0x18003036e  jz      short loc_1800303CC
0x180030370  movzx   ecx, word ptr cs:aWinlogon+10h; ""
0x180030377  lea     r8, [rsp+78h+pvInfo]; pvInfo
0x18003037c  movups  xmm0, xmmword ptr cs:aWinlogon; "Winlogon"
0x180030383  mov     r9d, 12h; nLength
0x180030389  mov     [rsp+78h+var_38], cx
0x18003038e  mov     rcx, rax; hObj
0x180030391  mov     [rsp+78h+lpnLengthNeeded], 0; lpnLengthNeeded
0x18003039a  movups  [rsp+78h+var_48], xmm0
0x18003039f  lea     edx, [r9-10h]; nIndex
0x1800303a3  call    cs:__imp_GetUserObjectInformationW
0x1800303a9  test    eax, eax
0x1800303ab  jz      short loc_1800303CC
0x1800303ad  xor     eax, eax
0x1800303af  lea     rdx, [rsp+78h+var_48]
0x1800303b4  lea     rcx, [rsp+78h+pvInfo]
0x1800303b9  mov     [rsp+78h+var_20], ax
0x1800303be  call    cs:__imp__o__wcsicmp
0x1800303c4  test    eax, eax
0x1800303c6  jnz     short loc_1800303CC
0x1800303c8  mov     al, 1
0x1800303ca  jmp     short loc_1800303F2
0x1800303cc  lea     r8, aGlobalWindowsM; "Global\\Windows.Machine.OOBE"
0x1800303d3  xor     edx, edx; bInheritHandle
0x1800303d5  mov     ecx, 100000h; dwDesiredAccess
0x1800303da  call    cs:__imp_OpenMutexW
0x1800303e0  mov     rcx, rax; hObject
0x1800303e3  mov     rbx, rax
0x1800303e6  call    cs:__imp_CloseHandle
0x1800303ec  test    rbx, rbx
0x1800303ef  setnz   al
0x1800303f2  mov     rcx, [rsp+78h+var_18]
0x1800303f7  xor     rcx, rsp; StackCookie
0x1800303fa  call    __security_check_cookie
0x1800303ff  add     rsp, 70h
0x180030403  pop     rbx
0x180030404  retn
```
