# IsRunningInSystemContext(bool &)

- ea: `0x140017a88`
- end: `0x140017b87`
- name: `?IsRunningInSystemContext@@YAJAEA_N@Z`
- size: `255`
- prototype: `__int64 __fastcall(bool *)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000cd78`
- `0x14001584c`
- `0x140017610`

## callees

- `0x140016ca0`
- `0x140017a88`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x140017aba`
- `ADVAPI32!OpenThreadToken` at `0x140017aba`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140017b30`
- `ADVAPI32!ConvertSidToStringSidW` at `0x140017b30`
- `ADVAPI32!OpenProcessToken` at `0x140017ae4`
- `ADVAPI32!OpenProcessToken` at `0x140017ae4`
- `KERNEL32!GetCurrentThread` at `0x140017aa3`
- `KERNEL32!GetCurrentThread` at `0x140017aa3`
- `KERNEL32!LocalFree` at `0x140017b74`
- `KERNEL32!LocalFree` at `0x140017b74`
- `KERNEL32!GetCurrentProcess` at `0x140017ad1`
- `KERNEL32!GetCurrentProcess` at `0x140017ad1`
- `KERNEL32!GetLastError` at `0x140017ac4`
- `KERNEL32!GetLastError` at `0x140017aee`
- `KERNEL32!GetLastError` at `0x140017b55`
- `KERNEL32!GetLastError` at `0x140017ac4`
- `KERNEL32!GetLastError` at `0x140017aee`
- `KERNEL32!GetLastError` at `0x140017b55`
- `msvcrt!_wcsicmp` at `0x140017b46`
- `msvcrt!_wcsicmp` at `0x140017b46`

## pseudocode

```c
__int64 __fastcall IsRunningInSystemContext(bool *a1)
{
  unsigned int TokenSids; // ebx
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int v6; // eax
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF
  LPWSTR StringSid; // [rsp+38h] [rbp+10h] BYREF
  PSID Sid; // [rsp+40h] [rbp+18h] BYREF

  TokenSids = 0;
  TokenHandle = 0;
  Sid = 0;
  *a1 = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x20008u, 1, &TokenHandle) && GetLastError() == 1008 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
    {
      LastError = GetLastError();
      TokenSids = LastError;
      if ( LastError > 0 )
        TokenSids = (unsigned __int16)LastError | 0x80070000;
    }
  }
  StringSid = 0;
  if ( TokenHandle )
  {
    TokenSids = GetTokenSids(TokenHandle, &Sid);
    if ( !TokenSids )
    {
      if ( ConvertSidToStringSidW(Sid, &StringSid) )
      {
        if ( !_wcsicmp(StringSid, L"S-1-5-18") )
          *a1 = 1;
      }
      else
      {
        v6 = GetLastError();
        TokenSids = v6;
        if ( v6 > 0 )
          TokenSids = (unsigned __int16)v6 | 0x80070000;
      }
    }
    if ( StringSid )
      LocalFree(StringSid);
  }
  return TokenSids;
}

```

## disassembly

```asm
0x140017a88  mov     [rsp+arg_18], rbx
0x140017a8d  push    rdi
0x140017a8e  sub     rsp, 20h
0x140017a92  xor     ebx, ebx
0x140017a94  mov     rdi, rcx
0x140017a97  mov     [rsp+28h+TokenHandle], rbx
0x140017a9c  mov     [rsp+28h+Sid], rbx
0x140017aa1  mov     [rcx], bl
0x140017aa3  call    cs:__imp_GetCurrentThread
0x140017aa9  lea     r9, [rsp+28h+TokenHandle]; TokenHandle
0x140017aae  mov     edx, 20008h; DesiredAccess
0x140017ab3  mov     rcx, rax; ThreadHandle
0x140017ab6  lea     r8d, [rbx+1]; OpenAsSelf
0x140017aba  call    cs:__imp_OpenThreadToken
0x140017ac0  test    eax, eax
0x140017ac2  jnz     short loc_140017B03
0x140017ac4  call    cs:__imp_GetLastError
0x140017aca  cmp     eax, 3F0h
0x140017acf  jnz     short loc_140017B03
0x140017ad1  call    cs:__imp_GetCurrentProcess
0x140017ad7  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x140017adc  mov     edx, 20008h; DesiredAccess
0x140017ae1  mov     rcx, rax; ProcessHandle
0x140017ae4  call    cs:__imp_OpenProcessToken
0x140017aea  test    eax, eax
0x140017aec  jnz     short loc_140017B03
0x140017aee  call    cs:__imp_GetLastError
0x140017af4  mov     ebx, eax
0x140017af6  test    eax, eax
0x140017af8  jle     short loc_140017B03
0x140017afa  movzx   ebx, ax
0x140017afd  or      ebx, 80070000h
0x140017b03  mov     rcx, [rsp+28h+TokenHandle]; TokenHandle
0x140017b08  mov     [rsp+28h+StringSid], 0
0x140017b11  test    rcx, rcx
0x140017b14  jz      short loc_140017B7A
0x140017b16  lea     rdx, [rsp+28h+Sid]; void **
0x140017b1b  call    ?GetTokenSids@@YAJPEAXPEAPEAX@Z; GetTokenSids(void *,void * *)
0x140017b20  mov     ebx, eax
0x140017b22  test    eax, eax
0x140017b24  jnz     short loc_140017B6A
0x140017b26  mov     rcx, [rsp+28h+Sid]; Sid
0x140017b2b  lea     rdx, [rsp+28h+StringSid]; StringSid
0x140017b30  call    cs:__imp_ConvertSidToStringSidW
0x140017b36  test    eax, eax
0x140017b38  jz      short loc_140017B55
0x140017b3a  mov     rcx, [rsp+28h+StringSid]; String1
0x140017b3f  lea     rdx, aS1518; "S-1-5-18"
0x140017b46  call    cs:__imp__wcsicmp
0x140017b4c  test    eax, eax
0x140017b4e  jnz     short loc_140017B6A
0x140017b50  mov     byte ptr [rdi], 1
0x140017b53  jmp     short loc_140017B6A
0x140017b55  call    cs:__imp_GetLastError
0x140017b5b  mov     ebx, eax
0x140017b5d  test    eax, eax
0x140017b5f  jle     short loc_140017B6A
0x140017b61  movzx   ebx, ax
0x140017b64  or      ebx, 80070000h
0x140017b6a  mov     rcx, [rsp+28h+StringSid]; hMem
0x140017b6f  test    rcx, rcx
0x140017b72  jz      short loc_140017B7A
0x140017b74  call    cs:__imp_LocalFree
0x140017b7a  mov     eax, ebx
0x140017b7c  mov     rbx, [rsp+28h+arg_18]
0x140017b81  add     rsp, 20h
0x140017b85  pop     rdi
0x140017b86  retn
```
