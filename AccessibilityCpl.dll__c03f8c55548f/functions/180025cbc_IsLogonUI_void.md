# IsLogonUI(void)

- ea: `0x180025cbc`
- end: `0x180025d5c`
- name: `?IsLogonUI@@YA_NXZ`
- size: `160`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180025c78`

## callees

- `0x180025cbc`
- `0x18002d220`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180025d34`
- `msvcrt!_wcsicmp` at `0x180025d34`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025cd3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025cd3`
- `USER32!GetThreadDesktop` at `0x180025cdb`
- `USER32!GetThreadDesktop` at `0x180025cdb`
- `USER32!GetUserObjectInformationW` at `0x180025d19`
- `USER32!GetUserObjectInformationW` at `0x180025d19`

## pseudocode

```c
char IsLogonUI(void)
{
  char v0; // bl
  DWORD CurrentThreadId; // eax
  HDESK ThreadDesktop; // rax
  wchar_t String2[12]; // [rsp+30h] [rbp-48h] BYREF
  wchar_t pvInfo[12]; // [rsp+48h] [rbp-30h] BYREF

  v0 = 0;
  CurrentThreadId = GetCurrentThreadId();
  ThreadDesktop = GetThreadDesktop(CurrentThreadId);
  if ( ThreadDesktop )
  {
    wcscpy(String2, L"Winlogon");
    if ( GetUserObjectInformationW(ThreadDesktop, 2, pvInfo, 0x12u, 0) )
    {
      pvInfo[8] = 0;
      return _wcsicmp(pvInfo, String2) == 0;
    }
  }
  return v0;
}

```

## disassembly

```asm
0x180025cbc  push    rbx
0x180025cbe  sub     rsp, 70h
0x180025cc2  mov     rax, cs:__security_cookie
0x180025cc9  xor     rax, rsp
0x180025ccc  mov     [rsp+78h+var_18], rax
0x180025cd1  xor     bl, bl
0x180025cd3  call    cs:__imp_GetCurrentThreadId
0x180025cd9  mov     ecx, eax; dwThreadId
0x180025cdb  call    cs:__imp_GetThreadDesktop
0x180025ce1  test    rax, rax
0x180025ce4  jz      short loc_180025D47
0x180025ce6  movzx   ecx, word ptr cs:aWinlogon+10h; ""
0x180025ced  lea     r8, [rsp+78h+pvInfo]; pvInfo
0x180025cf2  movups  xmm0, xmmword ptr cs:aWinlogon; "Winlogon"
0x180025cf9  mov     r9d, 12h; nLength
0x180025cff  mov     [rsp+78h+var_38], cx
0x180025d04  mov     rcx, rax; hObj
0x180025d07  mov     [rsp+78h+lpnLengthNeeded], 0; lpnLengthNeeded
0x180025d10  movups  xmmword ptr [rsp+78h+String2], xmm0
0x180025d15  lea     edx, [r9-10h]; nIndex
0x180025d19  call    cs:__imp_GetUserObjectInformationW
0x180025d1f  test    eax, eax
0x180025d21  jz      short loc_180025D47
0x180025d23  xor     ecx, ecx
0x180025d25  lea     rdx, [rsp+78h+String2]; String2
0x180025d2a  mov     [rsp+78h+var_20], cx
0x180025d2f  lea     rcx, [rsp+78h+pvInfo]; String1
0x180025d34  call    cs:__imp__wcsicmp
0x180025d3a  movzx   ebx, bl
0x180025d3d  mov     ecx, 1
0x180025d42  test    eax, eax
0x180025d44  cmovz   ebx, ecx
0x180025d47  mov     al, bl
0x180025d49  mov     rcx, [rsp+78h+var_18]
0x180025d4e  xor     rcx, rsp; StackCookie
0x180025d51  call    __security_check_cookie
0x180025d56  add     rsp, 70h
0x180025d5a  pop     rbx
0x180025d5b  retn
```
