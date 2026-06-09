# BaseSrvLaunchCPL

- ea: `0x18000ba74`
- end: `0x18000bcf1`
- name: `BaseSrvLaunchCPL`
- size: `637`
- prototype: `__int64 __fastcall(STRING *Source, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000b984`

## callees

- `0x18000ba74`
- `0x18000bcf8`
- `0x18000db40`

## import_xrefs

- `ntdll!NtClose` at `0x18000bc99`
- `ntdll!NtClose` at `0x18000bcc0`
- `ntdll!NtClose` at `0x18000bc99`
- `ntdll!NtClose` at `0x18000bcc0`
- `ntdll!RtlAppendStringToString` at `0x18000bb5f`
- `ntdll!RtlAppendStringToString` at `0x18000bb81`
- `ntdll!RtlAppendStringToString` at `0x18000bba1`
- `ntdll!RtlAppendStringToString` at `0x18000bbc3`
- `ntdll!RtlAppendStringToString` at `0x18000bbe3`
- `ntdll!RtlAppendStringToString` at `0x18000bc02`
- `ntdll!RtlAppendStringToString` at `0x18000bc20`
- `ntdll!RtlAppendStringToString` at `0x18000bc3f`
- `ntdll!RtlAppendStringToString` at `0x18000bb5f`
- `ntdll!RtlAppendStringToString` at `0x18000bb81`
- `ntdll!RtlAppendStringToString` at `0x18000bba1`
- `ntdll!RtlAppendStringToString` at `0x18000bbc3`
- `ntdll!RtlAppendStringToString` at `0x18000bbe3`
- `ntdll!RtlAppendStringToString` at `0x18000bc02`
- `ntdll!RtlAppendStringToString` at `0x18000bc20`
- `ntdll!RtlAppendStringToString` at `0x18000bc3f`
- `ntdll!NtResumeThread` at `0x18000bc88`
- `ntdll!NtResumeThread` at `0x18000bc88`
- `ntdll!NtWaitForSingleObject` at `0x18000bcaf`
- `ntdll!NtWaitForSingleObject` at `0x18000bcaf`
- `ntdll!RtlInitUnicodeString` at `0x18000bb03`
- `ntdll!RtlInitUnicodeString` at `0x18000bb1b`
- `ntdll!RtlInitUnicodeString` at `0x18000bb32`
- `ntdll!RtlInitUnicodeString` at `0x18000bb49`
- `ntdll!RtlInitUnicodeString` at `0x18000bb03`
- `ntdll!RtlInitUnicodeString` at `0x18000bb1b`
- `ntdll!RtlInitUnicodeString` at `0x18000bb32`
- `ntdll!RtlInitUnicodeString` at `0x18000bb49`

## string_xrefs

- `0x18000bb0f`: `\RunDll32.exe`
- `0x18000bb27`: `  shell32.dll,Control_RunDLL ntvdmcpl.dll,,/originalapp:"`

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
  ThreadHandle = 0;
  v6.Buffer = &v16;
  Handle = 0;
  Destination.Buffer = &v15;
  v14 = 0;
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
0x18000ba74  mov     [rsp-8+arg_10], rbx
0x18000ba79  push    rbp
0x18000ba7a  push    rsi
0x18000ba7b  push    rdi
0x18000ba7c  lea     rbp, [rsp-660h]
0x18000ba84  sub     rsp, 760h
0x18000ba8b  mov     rax, cs:__security_cookie
0x18000ba92  xor     rax, rsp
0x18000ba95  mov     [rbp+670h+var_20], rax
0x18000ba9c  xorps   xmm0, xmm0
0x18000ba9f  mov     qword ptr [rsp+770h+var_740.Length], 4860000h
0x18000baa8  xorps   xmm1, xmm1
0x18000baab  mov     qword ptr [rsp+770h+Destination.Length], 2080000h
0x18000bab4  lea     rax, [rbp+670h+var_4B0]
0x18000babb  mov     [rsp+770h+ThreadHandle], 0
0x18000bac4  mov     [rsp+770h+var_740.Buffer], rax
0x18000bac9  mov     rsi, rdx
0x18000bacc  lea     rax, [rbp+670h+var_6C0]
0x18000bad0  mov     [rsp+770h+Handle], 0
0x18000bad9  mov     rdi, rcx
0x18000badc  mov     [rsp+770h+Destination.Buffer], rax
0x18000bae1  lea     rdx, asc_180010AD8; "\\??\\"
0x18000bae8  lea     rcx, [rsp+770h+DestinationString]; DestinationString
0x18000baed  movups  [rbp+670h+var_6D0], xmm0
0x18000baf1  movups  xmmword ptr [rsp+770h+var_710.Length], xmm1
0x18000baf6  movups  xmmword ptr [rsp+770h+DestinationString.Length], xmm0
0x18000bafb  movups  xmmword ptr [rbp+670h+var_6F0.Length], xmm1
0x18000baff  movups  xmmword ptr [rbp+670h+var_6E0.Length], xmm0
0x18000bb03  call    cs:__imp_RtlInitUnicodeString
0x18000bb0a  nop     dword ptr [rax+rax+00h]
0x18000bb0f  lea     rdx, aRundll32Exe; "\\RunDll32.exe"
0x18000bb16  lea     rcx, [rsp+770h+var_710]; DestinationString
0x18000bb1b  call    cs:__imp_RtlInitUnicodeString
0x18000bb22  nop     dword ptr [rax+rax+00h]
0x18000bb27  lea     rdx, aShell32DllCont; "  shell32.dll,Control_RunDLL ntvdmcpl.d"...
0x18000bb2e  lea     rcx, [rbp+670h+var_6F0]; DestinationString
0x18000bb32  call    cs:__imp_RtlInitUnicodeString
0x18000bb39  nop     dword ptr [rax+rax+00h]
0x18000bb3e  lea     rdx, asc_180010B84; "\""
0x18000bb45  lea     rcx, [rbp+670h+var_6E0]; DestinationString
0x18000bb49  call    cs:__imp_RtlInitUnicodeString
0x18000bb50  nop     dword ptr [rax+rax+00h]
0x18000bb55  lea     rdx, [rsp+770h+DestinationString]; Source
0x18000bb5a  lea     rcx, [rsp+770h+Destination]; Destination
0x18000bb5f  call    cs:__imp_RtlAppendStringToString
0x18000bb66  nop     dword ptr [rax+rax+00h]
0x18000bb6b  mov     ebx, eax
0x18000bb6d  test    eax, eax
0x18000bb6f  js      loc_18000BCCC
0x18000bb75  lea     rdx, BaseSrvWindowsSystemDirectory; Source
0x18000bb7c  lea     rcx, [rsp+770h+Destination]; Destination
0x18000bb81  call    cs:__imp_RtlAppendStringToString
0x18000bb88  nop     dword ptr [rax+rax+00h]
0x18000bb8d  mov     ebx, eax
0x18000bb8f  test    eax, eax
0x18000bb91  js      loc_18000BCCC
0x18000bb97  lea     rdx, [rsp+770h+var_710]; Source
0x18000bb9c  lea     rcx, [rsp+770h+Destination]; Destination
0x18000bba1  call    cs:__imp_RtlAppendStringToString
0x18000bba8  nop     dword ptr [rax+rax+00h]
0x18000bbad  mov     ebx, eax
0x18000bbaf  test    eax, eax
0x18000bbb1  js      loc_18000BCCC
0x18000bbb7  lea     rdx, BaseSrvWindowsSystemDirectory; Source
0x18000bbbe  lea     rcx, [rsp+770h+var_740]; Destination
0x18000bbc3  call    cs:__imp_RtlAppendStringToString
0x18000bbca  nop     dword ptr [rax+rax+00h]
0x18000bbcf  mov     ebx, eax
0x18000bbd1  test    eax, eax
0x18000bbd3  js      loc_18000BCCC
0x18000bbd9  lea     rdx, [rsp+770h+var_710]; Source
0x18000bbde  lea     rcx, [rsp+770h+var_740]; Destination
0x18000bbe3  call    cs:__imp_RtlAppendStringToString
0x18000bbea  nop     dword ptr [rax+rax+00h]
0x18000bbef  mov     ebx, eax
0x18000bbf1  test    eax, eax
0x18000bbf3  js      loc_18000BCCC
0x18000bbf9  lea     rdx, [rbp+670h+var_6F0]; Source
0x18000bbfd  lea     rcx, [rsp+770h+var_740]; Destination
0x18000bc02  call    cs:__imp_RtlAppendStringToString
0x18000bc09  nop     dword ptr [rax+rax+00h]
0x18000bc0e  mov     ebx, eax
0x18000bc10  test    eax, eax
0x18000bc12  js      loc_18000BCCC
0x18000bc18  mov     rdx, rdi; Source
0x18000bc1b  lea     rcx, [rsp+770h+var_740]; Destination
0x18000bc20  call    cs:__imp_RtlAppendStringToString
0x18000bc27  nop     dword ptr [rax+rax+00h]
0x18000bc2c  mov     ebx, eax
0x18000bc2e  test    eax, eax
0x18000bc30  js      loc_18000BCCC
0x18000bc36  lea     rdx, [rbp+670h+var_6E0]; Source
0x18000bc3a  lea     rcx, [rsp+770h+var_740]; Destination
0x18000bc3f  call    cs:__imp_RtlAppendStringToString
0x18000bc46  nop     dword ptr [rax+rax+00h]
0x18000bc4b  mov     ebx, eax
0x18000bc4d  test    eax, eax
0x18000bc4f  js      short loc_18000BCCC
0x18000bc51  lea     rax, [rsp+770h+Handle]
0x18000bc56  mov     r8, rsi
0x18000bc59  mov     [rsp+770h+var_748], rax
0x18000bc5e  lea     r9, [rbp+670h+var_6D0]
0x18000bc62  lea     rax, [rsp+770h+ThreadHandle]
0x18000bc67  lea     rdx, [rsp+770h+var_740]
0x18000bc6c  mov     [rsp+770h+var_750], rax
0x18000bc71  lea     rcx, [rsp+770h+Destination]
0x18000bc76  call    BaseSrvLaunchProcess
0x18000bc7b  mov     ebx, eax
0x18000bc7d  test    eax, eax
0x18000bc7f  js      short loc_18000BCCC
0x18000bc81  mov     rcx, [rsp+770h+ThreadHandle]; ThreadHandle
0x18000bc86  xor     edx, edx; SuspendCount
0x18000bc88  call    cs:__imp_NtResumeThread
0x18000bc8f  nop     dword ptr [rax+rax+00h]
0x18000bc94  mov     rcx, [rsp+770h+ThreadHandle]; Handle
0x18000bc99  call    cs:__imp_NtClose
0x18000bca0  nop     dword ptr [rax+rax+00h]
0x18000bca5  mov     rcx, [rsp+770h+Handle]; Handle
0x18000bcaa  xor     r8d, r8d; Timeout
0x18000bcad  xor     edx, edx; Alertable
0x18000bcaf  call    cs:__imp_NtWaitForSingleObject
0x18000bcb6  nop     dword ptr [rax+rax+00h]
0x18000bcbb  mov     rcx, [rsp+770h+Handle]; Handle
0x18000bcc0  call    cs:__imp_NtClose
0x18000bcc7  nop     dword ptr [rax+rax+00h]
0x18000bccc  mov     eax, ebx
0x18000bcce  mov     rcx, [rbp+670h+var_20]
0x18000bcd5  xor     rcx, rsp; StackCookie
0x18000bcd8  call    __security_check_cookie
0x18000bcdd  mov     rbx, [rsp+770h+arg_10]
0x18000bce5  add     rsp, 760h
0x18000bcec  pop     rdi
0x18000bced  pop     rsi
0x18000bcee  pop     rbp
0x18000bcef  retn
```
