# BaseSrvLaunchCPL

- ea: `0x18000b7ac`
- end: `0x18000ba2f`
- name: `BaseSrvLaunchCPL`
- size: `643`
- prototype: `__int64 __fastcall(STRING *Source, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000b6c0`

## callees

- `0x18000b7ac`
- `0x18000ba38`
- `0x18000d730`

## import_xrefs

- `ntdll!NtClose` at `0x18000b9d2`
- `ntdll!NtClose` at `0x18000b9f9`
- `ntdll!NtClose` at `0x18000b9d2`
- `ntdll!NtClose` at `0x18000b9f9`
- `ntdll!RtlAppendStringToString` at `0x18000b898`
- `ntdll!RtlAppendStringToString` at `0x18000b8ba`
- `ntdll!RtlAppendStringToString` at `0x18000b8da`
- `ntdll!RtlAppendStringToString` at `0x18000b8fc`
- `ntdll!RtlAppendStringToString` at `0x18000b91c`
- `ntdll!RtlAppendStringToString` at `0x18000b93b`
- `ntdll!RtlAppendStringToString` at `0x18000b959`
- `ntdll!RtlAppendStringToString` at `0x18000b978`
- `ntdll!RtlAppendStringToString` at `0x18000b898`
- `ntdll!RtlAppendStringToString` at `0x18000b8ba`
- `ntdll!RtlAppendStringToString` at `0x18000b8da`
- `ntdll!RtlAppendStringToString` at `0x18000b8fc`
- `ntdll!RtlAppendStringToString` at `0x18000b91c`
- `ntdll!RtlAppendStringToString` at `0x18000b93b`
- `ntdll!RtlAppendStringToString` at `0x18000b959`
- `ntdll!RtlAppendStringToString` at `0x18000b978`
- `ntdll!NtResumeThread` at `0x18000b9c1`
- `ntdll!NtResumeThread` at `0x18000b9c1`
- `ntdll!NtWaitForSingleObject` at `0x18000b9e8`
- `ntdll!NtWaitForSingleObject` at `0x18000b9e8`
- `ntdll!RtlInitUnicodeString` at `0x18000b83c`
- `ntdll!RtlInitUnicodeString` at `0x18000b854`
- `ntdll!RtlInitUnicodeString` at `0x18000b86b`
- `ntdll!RtlInitUnicodeString` at `0x18000b882`
- `ntdll!RtlInitUnicodeString` at `0x18000b83c`
- `ntdll!RtlInitUnicodeString` at `0x18000b854`
- `ntdll!RtlInitUnicodeString` at `0x18000b86b`
- `ntdll!RtlInitUnicodeString` at `0x18000b882`

## string_xrefs

- `0x18000b848`: `\RunDll32.exe`
- `0x18000b860`: `  shell32.dll,Control_RunDLL ntvdmcpl.dll,,/originalapp:"`

## pseudocode

```c
__int64 __fastcall BaseSrvLaunchCPL(STRING *Source, __int64 a2)
{
  int appended; // ebx
  struct _STRING v6; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE ThreadHandle; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE Handle; // [rsp+48h] [rbp-B8h] BYREF
  struct _STRING Destination; // [rsp+50h] [rbp-B0h] BYREF
  struct _UNICODE_STRING v10; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING v12; // [rsp+80h] [rbp-80h] BYREF
  struct _UNICODE_STRING v13; // [rsp+90h] [rbp-70h] BYREF
  __int128 v14; // [rsp+A0h] [rbp-60h] BYREF
  char v15; // [rsp+B0h] [rbp-50h] BYREF
  char v16; // [rsp+2C0h] [rbp+1C0h] BYREF

  *(_QWORD *)&v6.Length = 75890688;
  *(_QWORD *)&Destination.Length = 34078720;
  v6.Buffer = &v16;
  Destination.Buffer = &v15;
  ThreadHandle = 0;
  v14 = 0;
  Handle = 0;
  v10 = 0;
  DestinationString = 0;
  v12 = 0;
  v13 = 0;
  RtlInitUnicodeString(&DestinationString, L"\\??\\");
  RtlInitUnicodeString(&v10, L"\\RunDll32.exe");
  RtlInitUnicodeString(&v12, L"  shell32.dll,Control_RunDLL ntvdmcpl.dll,,/originalapp:\"");
  RtlInitUnicodeString(&v13, L"\"");
  appended = RtlAppendStringToString(&Destination, (const STRING *)&DestinationString);
  if ( appended >= 0 )
  {
    appended = RtlAppendStringToString(&Destination, &BaseSrvWindowsSystemDirectory);
    if ( appended >= 0 )
    {
      appended = RtlAppendStringToString(&Destination, (const STRING *)&v10);
      if ( appended >= 0 )
      {
        appended = RtlAppendStringToString(&v6, &BaseSrvWindowsSystemDirectory);
        if ( appended >= 0 )
        {
          appended = RtlAppendStringToString(&v6, (const STRING *)&v10);
          if ( appended >= 0 )
          {
            appended = RtlAppendStringToString(&v6, (const STRING *)&v12);
            if ( appended >= 0 )
            {
              appended = RtlAppendStringToString(&v6, Source);
              if ( appended >= 0 )
              {
                appended = RtlAppendStringToString(&v6, (const STRING *)&v13);
                if ( appended >= 0 )
                {
                  appended = BaseSrvLaunchProcess(
                               &Destination.Length,
                               (__int64)&v6,
                               a2,
                               (__int64)&v14,
                               &ThreadHandle,
                               &Handle);
                  if ( appended >= 0 )
                  {
                    NtResumeThread(ThreadHandle, 0);
                    NtClose(ThreadHandle);
                    NtWaitForSingleObject(Handle, 0, 0);
                    NtClose(Handle);
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18000b7ac  mov     [rsp-8+arg_10], rbx
0x18000b7b1  mov     [rsp-8+arg_18], rsi
0x18000b7b6  push    rbp
0x18000b7b7  push    rdi
0x18000b7b8  push    r14
0x18000b7ba  lea     rbp, [rsp-660h]
0x18000b7c2  sub     rsp, 760h
0x18000b7c9  mov     rax, cs:__security_cookie
0x18000b7d0  xor     rax, rsp
0x18000b7d3  mov     [rbp+670h+var_20], rax
0x18000b7da  xorps   xmm0, xmm0
0x18000b7dd  mov     qword ptr [rsp+770h+var_740.Length], 4860000h
0x18000b7e6  xorps   xmm1, xmm1
0x18000b7e9  mov     qword ptr [rsp+770h+Destination.Length], 2080000h
0x18000b7f2  lea     rax, [rbp+670h+var_4B0]
0x18000b7f9  mov     rsi, rdx
0x18000b7fc  mov     [rsp+770h+var_740.Buffer], rax
0x18000b801  lea     rdx, asc_180010AD8; "\\??\\"
0x18000b808  lea     rax, [rbp+670h+var_6C0]
0x18000b80c  mov     rdi, rcx
0x18000b80f  xor     r14d, r14d
0x18000b812  mov     [rsp+770h+Destination.Buffer], rax
0x18000b817  lea     rcx, [rsp+770h+DestinationString]; DestinationString
0x18000b81c  mov     [rsp+770h+ThreadHandle], r14
0x18000b821  movups  [rbp+670h+var_6D0], xmm0
0x18000b825  mov     [rsp+770h+Handle], r14
0x18000b82a  movups  xmmword ptr [rsp+770h+var_710.Length], xmm1
0x18000b82f  movups  xmmword ptr [rsp+770h+DestinationString.Length], xmm0
0x18000b834  movups  xmmword ptr [rbp+670h+var_6F0.Length], xmm1
0x18000b838  movups  xmmword ptr [rbp+670h+var_6E0.Length], xmm0
0x18000b83c  call    cs:__imp_RtlInitUnicodeString
0x18000b843  nop     dword ptr [rax+rax+00h]
0x18000b848  lea     rdx, aRundll32Exe; "\\RunDll32.exe"
0x18000b84f  lea     rcx, [rsp+770h+var_710]; DestinationString
0x18000b854  call    cs:__imp_RtlInitUnicodeString
0x18000b85b  nop     dword ptr [rax+rax+00h]
0x18000b860  lea     rdx, aShell32DllCont; "  shell32.dll,Control_RunDLL ntvdmcpl.d"...
0x18000b867  lea     rcx, [rbp+670h+var_6F0]; DestinationString
0x18000b86b  call    cs:__imp_RtlInitUnicodeString
0x18000b872  nop     dword ptr [rax+rax+00h]
0x18000b877  lea     rdx, asc_180010B84; "\""
0x18000b87e  lea     rcx, [rbp+670h+var_6E0]; DestinationString
0x18000b882  call    cs:__imp_RtlInitUnicodeString
0x18000b889  nop     dword ptr [rax+rax+00h]
0x18000b88e  lea     rdx, [rsp+770h+DestinationString]; Source
0x18000b893  lea     rcx, [rsp+770h+Destination]; Destination
0x18000b898  call    cs:__imp_RtlAppendStringToString
0x18000b89f  nop     dword ptr [rax+rax+00h]
0x18000b8a4  mov     ebx, eax
0x18000b8a6  test    eax, eax
0x18000b8a8  js      loc_18000BA05
0x18000b8ae  lea     rdx, BaseSrvWindowsSystemDirectory; Source
0x18000b8b5  lea     rcx, [rsp+770h+Destination]; Destination
0x18000b8ba  call    cs:__imp_RtlAppendStringToString
0x18000b8c1  nop     dword ptr [rax+rax+00h]
0x18000b8c6  mov     ebx, eax
0x18000b8c8  test    eax, eax
0x18000b8ca  js      loc_18000BA05
0x18000b8d0  lea     rdx, [rsp+770h+var_710]; Source
0x18000b8d5  lea     rcx, [rsp+770h+Destination]; Destination
0x18000b8da  call    cs:__imp_RtlAppendStringToString
0x18000b8e1  nop     dword ptr [rax+rax+00h]
0x18000b8e6  mov     ebx, eax
0x18000b8e8  test    eax, eax
0x18000b8ea  js      loc_18000BA05
0x18000b8f0  lea     rdx, BaseSrvWindowsSystemDirectory; Source
0x18000b8f7  lea     rcx, [rsp+770h+var_740]; Destination
0x18000b8fc  call    cs:__imp_RtlAppendStringToString
0x18000b903  nop     dword ptr [rax+rax+00h]
0x18000b908  mov     ebx, eax
0x18000b90a  test    eax, eax
0x18000b90c  js      loc_18000BA05
0x18000b912  lea     rdx, [rsp+770h+var_710]; Source
0x18000b917  lea     rcx, [rsp+770h+var_740]; Destination
0x18000b91c  call    cs:__imp_RtlAppendStringToString
0x18000b923  nop     dword ptr [rax+rax+00h]
0x18000b928  mov     ebx, eax
0x18000b92a  test    eax, eax
0x18000b92c  js      loc_18000BA05
0x18000b932  lea     rdx, [rbp+670h+var_6F0]; Source
0x18000b936  lea     rcx, [rsp+770h+var_740]; Destination
0x18000b93b  call    cs:__imp_RtlAppendStringToString
0x18000b942  nop     dword ptr [rax+rax+00h]
0x18000b947  mov     ebx, eax
0x18000b949  test    eax, eax
0x18000b94b  js      loc_18000BA05
0x18000b951  mov     rdx, rdi; Source
0x18000b954  lea     rcx, [rsp+770h+var_740]; Destination
0x18000b959  call    cs:__imp_RtlAppendStringToString
0x18000b960  nop     dword ptr [rax+rax+00h]
0x18000b965  mov     ebx, eax
0x18000b967  test    eax, eax
0x18000b969  js      loc_18000BA05
0x18000b96f  lea     rdx, [rbp+670h+var_6E0]; Source
0x18000b973  lea     rcx, [rsp+770h+var_740]; Destination
0x18000b978  call    cs:__imp_RtlAppendStringToString
0x18000b97f  nop     dword ptr [rax+rax+00h]
0x18000b984  mov     ebx, eax
0x18000b986  test    eax, eax
0x18000b988  js      short loc_18000BA05
0x18000b98a  lea     rax, [rsp+770h+Handle]
0x18000b98f  mov     r8, rsi
0x18000b992  mov     [rsp+770h+var_748], rax
0x18000b997  lea     r9, [rbp+670h+var_6D0]
0x18000b99b  lea     rax, [rsp+770h+ThreadHandle]
0x18000b9a0  lea     rdx, [rsp+770h+var_740]
0x18000b9a5  mov     [rsp+770h+var_750], rax
0x18000b9aa  lea     rcx, [rsp+770h+Destination]
0x18000b9af  call    BaseSrvLaunchProcess
0x18000b9b4  mov     ebx, eax
0x18000b9b6  test    eax, eax
0x18000b9b8  js      short loc_18000BA05
0x18000b9ba  mov     rcx, [rsp+770h+ThreadHandle]; ThreadHandle
0x18000b9bf  xor     edx, edx; SuspendCount
0x18000b9c1  call    cs:__imp_NtResumeThread
0x18000b9c8  nop     dword ptr [rax+rax+00h]
0x18000b9cd  mov     rcx, [rsp+770h+ThreadHandle]; Handle
0x18000b9d2  call    cs:__imp_NtClose
0x18000b9d9  nop     dword ptr [rax+rax+00h]
0x18000b9de  mov     rcx, [rsp+770h+Handle]; Handle
0x18000b9e3  xor     r8d, r8d; Timeout
0x18000b9e6  xor     edx, edx; Alertable
0x18000b9e8  call    cs:__imp_NtWaitForSingleObject
0x18000b9ef  nop     dword ptr [rax+rax+00h]
0x18000b9f4  mov     rcx, [rsp+770h+Handle]; Handle
0x18000b9f9  call    cs:__imp_NtClose
0x18000ba00  nop     dword ptr [rax+rax+00h]
0x18000ba05  mov     eax, ebx
0x18000ba07  mov     rcx, [rbp+670h+var_20]
0x18000ba0e  xor     rcx, rsp; StackCookie
0x18000ba11  call    __security_check_cookie
0x18000ba16  lea     r11, [rsp+770h+var_10]
0x18000ba1e  mov     rbx, [r11+30h]
0x18000ba22  mov     rsi, [r11+38h]
0x18000ba26  mov     rsp, r11
0x18000ba29  pop     r14
0x18000ba2b  pop     rdi
0x18000ba2c  pop     rbp
0x18000ba2d  retn
```
