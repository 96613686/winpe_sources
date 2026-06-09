# WinREUpdateWinREHashInternal

- ea: `0x18002028c`
- end: `0x1800203f3`
- name: `WinREUpdateWinREHashInternal`
- size: `359`
- prototype: `__int64 __fastcall(BYTE *lpData)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180020220`

## callees

- `0x1800059fc`
- `0x18002028c`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!SetLastError` at `0x1800203cc`
- `KERNEL32!SetLastError` at `0x1800203cc`
- `ADVAPI32!RegOpenKeyExW` at `0x180020301`
- `ADVAPI32!RegOpenKeyExW` at `0x180020301`
- `ADVAPI32!RegSetValueExW` at `0x180020362`
- `ADVAPI32!RegSetValueExW` at `0x180020399`
- `ADVAPI32!RegSetValueExW` at `0x180020362`
- `ADVAPI32!RegSetValueExW` at `0x180020399`

## string_xrefs

- `0x18002030d`: `base\diagnosis\srt\reagent2\reagent\reagent.cpp`
- `0x180020324`: `failed to open key`
- `0x180020330`: `WinREUpdateWinREHashInternal %s (0x%x) in file %S line %d`
- `0x1800203b9`: `WinREUpdateWinREHashInternal failed: 0x%x`

## pseudocode

```c
__int64 __fastcall WinREUpdateWinREHashInternal(BYTE *lpData, unsigned int a2)
{
  unsigned int v3; // ebx
  unsigned int v4; // eax
  unsigned int v5; // eax
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  __int64 Data; // [rsp+38h] [rbp-20h] BYREF

  hKey = 0;
  LODWORD(Data) = 1;
  if ( !lpData )
    goto LABEL_2;
  if ( a2 != 32 )
  {
    UnattendLogW(0, L"Invalid hash length: %d", a2);
LABEL_2:
    v3 = 87;
LABEL_11:
    UnattendLogW(2, L"WinREUpdateWinREHashInternal failed: 0x%x", v3);
    SetLastError(v3);
    return 0;
  }
  v3 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Reliability\\WinRE",
         0,
         2u,
         &hKey);
  if ( v3 )
  {
    UnattendLogW(
      2,
      L"WinREUpdateWinREHashInternal %s (0x%x) in file %S line %d",
      L"failed to open key",
      v3,
      "base\\diagnosis\\srt\\reagent2\\reagent\\reagent.cpp",
      3992,
      hKey,
      Data);
    goto LABEL_11;
  }
  v4 = RegSetValueExW(hKey, L"WimValidated", 0, 4u, (const BYTE *)&Data, 4u);
  v3 = v4;
  if ( v4 )
  {
    UnattendLogW(0, L"Failed to store WIM file trusted state: 0x%x", v4);
    goto LABEL_11;
  }
  v5 = RegSetValueExW(hKey, L"WimHash", 0, 3u, lpData, 0x20u);
  v3 = v5;
  if ( v5 )
  {
    UnattendLogW(0, L"Failed to store WIM file hash: 0x%x", v5);
    goto LABEL_11;
  }
  return 1;
}

```

## disassembly

```asm
0x18002028c  mov     [rsp+arg_10], rbx
0x180020291  push    rdi
0x180020292  sub     rsp, 50h
0x180020296  mov     rax, cs:__security_cookie
0x18002029d  xor     rax, rsp
0x1800202a0  mov     [rsp+58h+var_18], rax
0x1800202a5  mov     [rsp+58h+hKey], 0
0x1800202ae  mov     rdi, rcx
0x1800202b1  mov     dword ptr [rsp+58h+Data], 1
0x1800202b9  test    rcx, rcx
0x1800202bc  jnz     short loc_1800202C8
0x1800202be  mov     ebx, 57h ; 'W'
0x1800202c3  jmp     loc_1800203B6
0x1800202c8  cmp     edx, 20h ; ' '
0x1800202cb  jz      short loc_1800202E0
0x1800202cd  mov     r8d, edx
0x1800202d0  xor     ecx, ecx
0x1800202d2  lea     rdx, aInvalidHashLen; "Invalid hash length: %d"
0x1800202d9  call    UnattendLogW
0x1800202de  jmp     short loc_1800202BE
0x1800202e0  lea     rax, [rsp+58h+hKey]
0x1800202e5  mov     r9d, 2; samDesired
0x1800202eb  xor     r8d, r8d; ulOptions
0x1800202ee  mov     [rsp+58h+phkResult], rax; phkResult
0x1800202f3  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800202fa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180020301  call    cs:__imp_RegOpenKeyExW
0x180020307  mov     ebx, eax
0x180020309  test    eax, eax
0x18002030b  jz      short loc_18002033E
0x18002030d  lea     rax, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180020314  mov     [rsp+58h+cbData], 0F98h
0x18002031c  mov     r9d, ebx
0x18002031f  mov     [rsp+58h+phkResult], rax
0x180020324  lea     r8, aFailedToOpenKe; "failed to open key"
0x18002032b  mov     ecx, 2
0x180020330  lea     rdx, aWinreupdatewin_1; "WinREUpdateWinREHashInternal %s (0x%x) "...
0x180020337  call    UnattendLogW
0x18002033c  jmp     short loc_1800203B6
0x18002033e  mov     rcx, [rsp+58h+hKey]; hKey
0x180020343  lea     rax, [rsp+58h+Data]
0x180020348  mov     r9d, 4; dwType
0x18002034e  lea     rdx, aWimvalidated_0; "WimValidated"
0x180020355  mov     [rsp+58h+cbData], r9d; cbData
0x18002035a  xor     r8d, r8d; Reserved
0x18002035d  mov     [rsp+58h+phkResult], rax; lpData
0x180020362  call    cs:__imp_RegSetValueExW
0x180020368  mov     ebx, eax
0x18002036a  test    eax, eax
0x18002036c  jz      short loc_180020377
0x18002036e  lea     rdx, aFailedToStoreW_1; "Failed to store WIM file trusted state:"...
0x180020375  jmp     short loc_1800203AC
0x180020377  mov     rcx, [rsp+58h+hKey]; hKey
0x18002037c  lea     rdx, aWimhash_0; "WimHash"
0x180020383  mov     [rsp+58h+cbData], 20h ; ' '; cbData
0x18002038b  mov     r9d, 3; dwType
0x180020391  xor     r8d, r8d; Reserved
0x180020394  mov     [rsp+58h+phkResult], rdi; lpData
0x180020399  call    cs:__imp_RegSetValueExW
0x18002039f  mov     ebx, eax
0x1800203a1  test    eax, eax
0x1800203a3  jz      short loc_1800203D6
0x1800203a5  lea     rdx, aFailedToStoreW_2; "Failed to store WIM file hash: 0x%x"
0x1800203ac  mov     r8d, eax
0x1800203af  xor     ecx, ecx
0x1800203b1  call    UnattendLogW
0x1800203b6  mov     r8d, ebx
0x1800203b9  lea     rdx, aWinreupdatewin_0; "WinREUpdateWinREHashInternal failed: 0x"...
0x1800203c0  mov     ecx, 2
0x1800203c5  call    UnattendLogW
0x1800203ca  mov     ecx, ebx; dwErrCode
0x1800203cc  call    cs:__imp_SetLastError
0x1800203d2  xor     eax, eax
0x1800203d4  jmp     short loc_1800203DB
0x1800203d6  mov     eax, 1
0x1800203db  mov     rcx, [rsp+58h+var_18]
0x1800203e0  xor     rcx, rsp; StackCookie
0x1800203e3  call    __security_check_cookie
0x1800203e8  mov     rbx, [rsp+58h+arg_10]
0x1800203ed  add     rsp, 50h
0x1800203f1  pop     rdi
0x1800203f2  retn
```
