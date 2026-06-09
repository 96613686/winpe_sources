# CallerIdentity::IsHostedWindow(HWND__ *,int *)

- ea: `0x1800d7e4c`
- end: `0x1800d7fa0`
- name: `?IsHostedWindow@CallerIdentity@@YAJPEAUHWND__@@PEAH@Z`
- size: `340`
- prototype: `__int64 __fastcall(HWND hWnd, HWND, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180081b40`

## callees

- `0x180050ba0`
- `0x1800d7e4c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d7ebc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800d7ebc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800d7ed4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800d7ed4`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800d7f19`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800d7f19`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d7f51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800d7f51`
- `USER32!GetClassNameW` at `0x1800d7e93`
- `USER32!GetClassNameW` at `0x1800d7e93`
- `USER32!GetWindow` at `0x1800d7f67`
- `USER32!GetWindow` at `0x1800d7f67`
- `USER32!GetWindowThreadProcessId` at `0x1800d7f03`
- `USER32!GetWindowThreadProcessId` at `0x1800d7f03`
- `USER32!__imp_GetProcessUIContextInformation` at `0x1800d7ee2`
- `USER32!__imp_GetProcessUIContextInformation` at `0x1800d7f38`
- `USER32!__imp_GetProcessUIContextInformation` at `0x1800d7ee2`
- `USER32!__imp_GetProcessUIContextInformation` at `0x1800d7f38`

## pseudocode

```c
__int64 __fastcall CallerIdentity::IsHostedWindow(HWND hWnd, _DWORD *a2, int *a3)
{
  HANDLE CurrentProcess; // rax
  HANDLE v6; // rax
  void *v7; // rdi
  DWORD dwProcessId; // [rsp+30h] [rbp-248h] BYREF
  __int64 v10; // [rsp+38h] [rbp-240h] BYREF
  __int64 v11; // [rsp+40h] [rbp-238h] BYREF
  WCHAR ClassName[264]; // [rsp+50h] [rbp-228h] BYREF

  *a2 = 0;
  do
  {
    if ( !hWnd )
      break;
    if ( GetClassNameW(hWnd, ClassName, 260) > 0
      && CompareStringOrdinal(ClassName, -1, L"ApplicationHostBridgeWindow", -1, 1) == 2 )
    {
      v10 = 0;
      CurrentProcess = GetCurrentProcess();
      if ( (unsigned int)GetProcessUIContextInformation(CurrentProcess, &v10) && (_DWORD)v10 == 2 )
      {
        dwProcessId = 0;
        if ( GetWindowThreadProcessId(hWnd, &dwProcessId) )
        {
          v6 = OpenProcess(0x1000u, 0, dwProcessId);
          v7 = v6;
          if ( v6 )
          {
            v11 = 0;
            if ( (unsigned int)GetProcessUIContextInformation(v6, &v11) )
              *a2 = v11 == 2;
            CloseHandle(v7);
          }
        }
      }
      else
      {
        *a2 = 1;
      }
    }
    hWnd = GetWindow(hWnd, 4u);
  }
  while ( !*a2 );
  return 0;
}

```

## disassembly

```asm
0x1800d7e4c  mov     [rsp+arg_10], rbx
0x1800d7e51  mov     [rsp+arg_18], rsi
0x1800d7e56  push    rdi
0x1800d7e57  sub     rsp, 270h
0x1800d7e5e  mov     rax, cs:__security_cookie
0x1800d7e65  xor     rax, rsp
0x1800d7e68  mov     [rsp+278h+var_18], rax
0x1800d7e70  mov     rsi, rdx
0x1800d7e73  mov     dword ptr [rdx], 0
0x1800d7e79  mov     rbx, rcx
0x1800d7e7c  test    rbx, rbx
0x1800d7e7f  jz      loc_1800D7F79
0x1800d7e85  mov     r8d, 104h; nMaxCount
0x1800d7e8b  lea     rdx, [rsp+278h+ClassName]; lpClassName
0x1800d7e90  mov     rcx, rbx; hWnd
0x1800d7e93  call    cs:__imp_GetClassNameW
0x1800d7e99  test    eax, eax
0x1800d7e9b  jle     loc_1800D7F5F
0x1800d7ea1  or      r9d, 0FFFFFFFFh; cchCount2
0x1800d7ea5  mov     [rsp+278h+bIgnoreCase], 1; bIgnoreCase
0x1800d7ead  or      edx, r9d; cchCount1
0x1800d7eb0  lea     r8, aApplicationhos; "ApplicationHostBridgeWindow"
0x1800d7eb7  lea     rcx, [rsp+278h+ClassName]; lpString1
0x1800d7ebc  call    cs:__imp_CompareStringOrdinal
0x1800d7ec2  cmp     eax, 2
0x1800d7ec5  jnz     loc_1800D7F5F
0x1800d7ecb  mov     [rsp+278h+var_240], 0
0x1800d7ed4  call    cs:__imp_GetCurrentProcess
0x1800d7eda  mov     rcx, rax
0x1800d7edd  lea     rdx, [rsp+278h+var_240]
0x1800d7ee2  call    cs:__imp_GetProcessUIContextInformation
0x1800d7ee8  test    eax, eax
0x1800d7eea  jz      short loc_1800D7F59
0x1800d7eec  cmp     dword ptr [rsp+278h+var_240], 2
0x1800d7ef1  jnz     short loc_1800D7F59
0x1800d7ef3  lea     rdx, [rsp+278h+dwProcessId]; lpdwProcessId
0x1800d7ef8  mov     [rsp+278h+dwProcessId], 0
0x1800d7f00  mov     rcx, rbx; hWnd
0x1800d7f03  call    cs:__imp_GetWindowThreadProcessId
0x1800d7f09  test    eax, eax
0x1800d7f0b  jz      short loc_1800D7F5F
0x1800d7f0d  mov     r8d, [rsp+278h+dwProcessId]; dwProcessId
0x1800d7f12  xor     edx, edx; bInheritHandle
0x1800d7f14  mov     ecx, 1000h; dwDesiredAccess
0x1800d7f19  call    cs:__imp_OpenProcess
0x1800d7f1f  mov     rdi, rax
0x1800d7f22  test    rax, rax
0x1800d7f25  jz      short loc_1800D7F5F
0x1800d7f27  lea     rdx, [rsp+278h+var_238]
0x1800d7f2c  mov     [rsp+278h+var_238], 0
0x1800d7f35  mov     rcx, rax
0x1800d7f38  call    cs:__imp_GetProcessUIContextInformation
0x1800d7f3e  test    eax, eax
0x1800d7f40  jz      short loc_1800D7F4E
0x1800d7f42  xor     ecx, ecx
0x1800d7f44  cmp     dword ptr [rsp+278h+var_238], 2
0x1800d7f49  setz    cl
0x1800d7f4c  mov     [rsi], ecx
0x1800d7f4e  mov     rcx, rdi; hObject
0x1800d7f51  call    cs:__imp_CloseHandle
0x1800d7f57  jmp     short loc_1800D7F5F
0x1800d7f59  mov     dword ptr [rsi], 1
0x1800d7f5f  mov     edx, 4; uCmd
0x1800d7f64  mov     rcx, rbx; hWnd
0x1800d7f67  call    cs:__imp_GetWindow
0x1800d7f6d  cmp     dword ptr [rsi], 0
0x1800d7f70  mov     rbx, rax
0x1800d7f73  jz      loc_1800D7E7C
0x1800d7f79  xor     eax, eax
0x1800d7f7b  mov     rcx, [rsp+278h+var_18]
0x1800d7f83  xor     rcx, rsp; StackCookie
0x1800d7f86  call    __security_check_cookie
0x1800d7f8b  lea     r11, [rsp+278h+var_8]
0x1800d7f93  mov     rbx, [r11+20h]
0x1800d7f97  mov     rsi, [r11+28h]
0x1800d7f9b  mov     rsp, r11
0x1800d7f9e  pop     rdi
0x1800d7f9f  retn
```
