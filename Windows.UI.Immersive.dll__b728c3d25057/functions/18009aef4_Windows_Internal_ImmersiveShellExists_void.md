# Windows::Internal::ImmersiveShellExists(void)

- ea: `0x18009aef4`
- end: `0x18009afad`
- name: `?ImmersiveShellExists@Internal@Windows@@YA_NXZ`
- size: `185`
- prototype: `bool __fastcall(Windows::Internal *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180044ff4`
- `0x18009ad5c`

## callees

- `0x180050ba0`
- `0x18009aef4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009af6a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18009af6a`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18009af82`
- `api-ms-win-core-synch-l1-1-0!OpenMutexW` at `0x18009af82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009af09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009af09`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009af8e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18009af8e`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18009af4f`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetUserObjectInformationW` at `0x18009af4f`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x18009af11`
- `ext-ms-win-ntuser-windowstation-l1-1-0!GetThreadDesktop` at `0x18009af11`

## pseudocode

```c
bool __fastcall Windows::Internal::ImmersiveShellExists(Windows::Internal *this)
{
  DWORD CurrentThreadId; // eax
  HDESK ThreadDesktop; // rax
  int v3; // eax
  HANDLE v4; // rbx
  __int128 v6; // [rsp+30h] [rbp-48h] BYREF
  wchar_t v7; // [rsp+40h] [rbp-38h]
  _BYTE pvInfo[16]; // [rsp+48h] [rbp-30h] BYREF
  __int16 v9; // [rsp+58h] [rbp-20h]

  CurrentThreadId = GetCurrentThreadId();
  ThreadDesktop = GetThreadDesktop(CurrentThreadId);
  if ( !ThreadDesktop
    || (v7 = aWinlogon[8], v6 = *(_OWORD *)L"Winlogon", !GetUserObjectInformationW(ThreadDesktop, 2, pvInfo, 0x12u, 0))
    || (v9 = 0, (v3 = _o__wcsicmp(pvInfo, &v6)) != 0) )
  {
    v4 = OpenMutexW(0x100000u, 0, L"Global\\Windows.Machine.OOBE");
    CloseHandle(v4);
    LOBYTE(v3) = v4 == 0;
  }
  return v3;
}

```

## disassembly

```asm
0x18009aef4  push    rbx
0x18009aef6  sub     rsp, 70h
0x18009aefa  mov     rax, cs:__security_cookie
0x18009af01  xor     rax, rsp
0x18009af04  mov     [rsp+78h+var_18], rax
0x18009af09  call    cs:__imp_GetCurrentThreadId
0x18009af0f  mov     ecx, eax; dwThreadId
0x18009af11  call    cs:__imp_GetThreadDesktop
0x18009af17  test    rax, rax
0x18009af1a  jz      short loc_18009AF74
0x18009af1c  movzx   ecx, word ptr cs:aWinlogon+10h; ""
0x18009af23  lea     r8, [rsp+78h+pvInfo]; pvInfo
0x18009af28  movups  xmm0, xmmword ptr cs:aWinlogon; "Winlogon"
0x18009af2f  mov     r9d, 12h; nLength
0x18009af35  mov     [rsp+78h+var_38], cx
0x18009af3a  mov     rcx, rax; hObj
0x18009af3d  mov     [rsp+78h+lpnLengthNeeded], 0; lpnLengthNeeded
0x18009af46  movups  [rsp+78h+var_48], xmm0
0x18009af4b  lea     edx, [r9-10h]; nIndex
0x18009af4f  call    cs:__imp_GetUserObjectInformationW
0x18009af55  test    eax, eax
0x18009af57  jz      short loc_18009AF74
0x18009af59  xor     eax, eax
0x18009af5b  lea     rdx, [rsp+78h+var_48]
0x18009af60  lea     rcx, [rsp+78h+pvInfo]
0x18009af65  mov     [rsp+78h+var_20], ax
0x18009af6a  call    cs:__imp__o__wcsicmp
0x18009af70  test    eax, eax
0x18009af72  jz      short loc_18009AF9A
0x18009af74  lea     r8, aGlobalWindowsM; "Global\\Windows.Machine.OOBE"
0x18009af7b  xor     edx, edx; bInheritHandle
0x18009af7d  mov     ecx, 100000h; dwDesiredAccess
0x18009af82  call    cs:__imp_OpenMutexW
0x18009af88  mov     rcx, rax; hObject
0x18009af8b  mov     rbx, rax
0x18009af8e  call    cs:__imp_CloseHandle
0x18009af94  test    rbx, rbx
0x18009af97  setz    al
0x18009af9a  mov     rcx, [rsp+78h+var_18]
0x18009af9f  xor     rcx, rsp; StackCookie
0x18009afa2  call    __security_check_cookie
0x18009afa7  add     rsp, 70h
0x18009afab  pop     rbx
0x18009afac  retn
```
