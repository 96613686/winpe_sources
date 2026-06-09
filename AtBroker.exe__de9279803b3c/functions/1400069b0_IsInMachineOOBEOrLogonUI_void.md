# IsInMachineOOBEOrLogonUI(void)

- ea: `0x1400069b0`
- end: `0x140006a6f`
- name: `?IsInMachineOOBEOrLogonUI@@YA_NXZ`
- size: `191`
- prototype: `char(void)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b250`
- `0x140015644`

## callees

- `0x1400069b0`
- `0x140015b00`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400069c7`
- `KERNEL32!GetCurrentThreadId` at `0x1400069c7`
- `KERNEL32!CloseHandle` at `0x140006a54`
- `KERNEL32!CloseHandle` at `0x140006a54`
- `KERNEL32!OpenMutexW` at `0x140006a44`
- `KERNEL32!OpenMutexW` at `0x140006a44`
- `USER32!GetUserObjectInformationW` at `0x140006a0d`
- `USER32!GetUserObjectInformationW` at `0x140006a0d`
- `USER32!GetThreadDesktop` at `0x1400069cf`
- `USER32!GetThreadDesktop` at `0x1400069cf`
- `msvcrt!_wcsicmp` at `0x140006a28`
- `msvcrt!_wcsicmp` at `0x140006a28`

## pseudocode

```c
char IsInMachineOOBEOrLogonUI(void)
{
  char v0; // bl
  DWORD CurrentThreadId; // eax
  HDESK ThreadDesktop; // rax
  HANDLE v3; // rax
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
      if ( !_wcsicmp(pvInfo, String2) )
        return 1;
    }
  }
  v3 = OpenMutexW(0x100000u, 0, L"Global\\Windows.Machine.OOBE");
  if ( v3 )
  {
    v0 = 1;
    CloseHandle(v3);
  }
  return v0;
}

```

## disassembly

```asm
0x1400069b0  push    rbx
0x1400069b2  sub     rsp, 70h
0x1400069b6  mov     rax, cs:__security_cookie
0x1400069bd  xor     rax, rsp
0x1400069c0  mov     [rsp+78h+var_18], rax
0x1400069c5  xor     bl, bl
0x1400069c7  call    cs:__imp_GetCurrentThreadId
0x1400069cd  mov     ecx, eax; dwThreadId
0x1400069cf  call    cs:__imp_GetThreadDesktop
0x1400069d5  test    rax, rax
0x1400069d8  jz      short loc_140006A36
0x1400069da  movzx   ecx, word ptr cs:aWinlogon+10h; ""
0x1400069e1  lea     r8, [rsp+78h+pvInfo]; pvInfo
0x1400069e6  movups  xmm0, xmmword ptr cs:aWinlogon; "Winlogon"
0x1400069ed  mov     r9d, 12h; nLength
0x1400069f3  mov     [rsp+78h+var_38], cx
0x1400069f8  mov     rcx, rax; hObj
0x1400069fb  mov     [rsp+78h+lpnLengthNeeded], 0; lpnLengthNeeded
0x140006a04  movups  xmmword ptr [rsp+78h+String2], xmm0
0x140006a09  lea     edx, [r9-10h]; nIndex
0x140006a0d  call    cs:__imp_GetUserObjectInformationW
0x140006a13  test    eax, eax
0x140006a15  jz      short loc_140006A36
0x140006a17  xor     eax, eax
0x140006a19  lea     rdx, [rsp+78h+String2]; String2
0x140006a1e  lea     rcx, [rsp+78h+pvInfo]; String1
0x140006a23  mov     [rsp+78h+var_20], ax
0x140006a28  call    cs:__imp__wcsicmp
0x140006a2e  test    eax, eax
0x140006a30  jnz     short loc_140006A36
0x140006a32  mov     bl, 1
0x140006a34  jmp     short loc_140006A5A
0x140006a36  lea     r8, Name; "Global\\Windows.Machine.OOBE"
0x140006a3d  xor     edx, edx; bInheritHandle
0x140006a3f  mov     ecx, 100000h; dwDesiredAccess
0x140006a44  call    cs:__imp_OpenMutexW
0x140006a4a  test    rax, rax
0x140006a4d  jz      short loc_140006A5A
0x140006a4f  mov     rcx, rax; hObject
0x140006a52  mov     bl, 1
0x140006a54  call    cs:__imp_CloseHandle
0x140006a5a  mov     al, bl
0x140006a5c  mov     rcx, [rsp+78h+var_18]
0x140006a61  xor     rcx, rsp; StackCookie
0x140006a64  call    __security_check_cookie
0x140006a69  add     rsp, 70h
0x140006a6d  pop     rbx
0x140006a6e  retn
```
