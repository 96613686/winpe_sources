# CCredUIBrokerBase::_IsHWNDFromElevatedProcess(HWND__ *,bool *)

- ea: `0x140017e88`
- end: `0x140017f88`
- name: `?_IsHWNDFromElevatedProcess@CCredUIBrokerBase@@IEAAJPEAUHWND__@@PEA_N@Z`
- size: `256`
- prototype: `__int64 __fastcall(CCredUIBrokerBase *this, HWND, bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140010f10`

## callees

- `0x140013600`
- `0x140017e88`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x140017f44`
- `ADVAPI32!GetTokenInformation` at `0x140017f44`
- `ADVAPI32!OpenProcessToken` at `0x140017f06`
- `ADVAPI32!OpenProcessToken` at `0x140017f06`
- `KERNEL32!OpenProcess` at `0x140017ed5`
- `KERNEL32!OpenProcess` at `0x140017ed5`
- `KERNEL32!CloseHandle` at `0x140017f6a`
- `KERNEL32!CloseHandle` at `0x140017f73`
- `KERNEL32!CloseHandle` at `0x140017f6a`
- `KERNEL32!CloseHandle` at `0x140017f73`
- `USER32!GetWindowThreadProcessId` at `0x140017eb1`
- `USER32!GetWindowThreadProcessId` at `0x140017eb1`

## pseudocode

```c
__int64 __fastcall CCredUIBrokerBase::_IsHWNDFromElevatedProcess(CCredUIBrokerBase *this, HWND a2, bool *a3)
{
  int Error; // ebx
  HANDLE v5; // rdi
  void *TokenHandle; // [rsp+30h] [rbp-10h] BYREF
  DWORD dwProcessId; // [rsp+60h] [rbp+20h] BYREF
  int v9; // [rsp+64h] [rbp+24h]
  int TokenInformation; // [rsp+70h] [rbp+30h] BYREF
  DWORD ReturnLength; // [rsp+78h] [rbp+38h] BYREF

  v9 = HIDWORD(this);
  *a3 = 0;
  dwProcessId = 0;
  if ( GetWindowThreadProcessId(a2, &dwProcessId) || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    v5 = OpenProcess(0x1000u, 0, dwProcessId);
    if ( v5 || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      TokenHandle = 0;
      if ( !OpenProcessToken(v5, 8u, &TokenHandle) )
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
          goto LABEL_12;
      }
      ReturnLength = 0;
      TokenInformation = 0;
      if ( GetTokenInformation(TokenHandle, TokenElevation, &TokenInformation, 4u, &ReturnLength) )
      {
        Error = 0;
      }
      else
      {
        Error = ResultFromKnownLastError();
        if ( Error < 0 )
        {
LABEL_11:
          CloseHandle(TokenHandle);
LABEL_12:
          CloseHandle(v5);
          return (unsigned int)Error;
        }
      }
      *a3 = TokenInformation != 0;
      goto LABEL_11;
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x140017e88  mov     [rsp-18h+arg_8], rbx
0x140017e8d  mov     qword ptr [rsp-18h+dwProcessId], rcx
0x140017e92  push    rbp
0x140017e93  push    rsi
0x140017e94  push    rdi
0x140017e95  mov     rbp, rsp
0x140017e98  sub     rsp, 40h
0x140017e9c  mov     rcx, rdx; hWnd
0x140017e9f  mov     byte ptr [r8], 0
0x140017ea3  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x140017ea7  mov     [rbp+dwProcessId], 0
0x140017eae  mov     rsi, r8
0x140017eb1  call    cs:__imp_GetWindowThreadProcessId
0x140017eb7  test    eax, eax
0x140017eb9  jnz     short loc_140017ECA
0x140017ebb  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x140017ec0  mov     ebx, eax
0x140017ec2  test    eax, eax
0x140017ec4  js      loc_140017F79
0x140017eca  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x140017ece  xor     edx, edx; bInheritHandle
0x140017ed0  mov     ecx, 1000h; dwDesiredAccess
0x140017ed5  call    cs:__imp_OpenProcess
0x140017edb  mov     rdi, rax
0x140017ede  test    rax, rax
0x140017ee1  jnz     short loc_140017EF2
0x140017ee3  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x140017ee8  mov     ebx, eax
0x140017eea  test    eax, eax
0x140017eec  js      loc_140017F79
0x140017ef2  lea     r8, [rbp+TokenHandle]; TokenHandle
0x140017ef6  mov     [rbp+TokenHandle], 0
0x140017efe  mov     edx, 8; DesiredAccess
0x140017f03  mov     rcx, rdi; ProcessHandle
0x140017f06  call    cs:__imp_OpenProcessToken
0x140017f0c  test    eax, eax
0x140017f0e  jnz     short loc_140017F1B
0x140017f10  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x140017f15  mov     ebx, eax
0x140017f17  test    eax, eax
0x140017f19  js      short loc_140017F70
0x140017f1b  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140017f1f  lea     rax, [rbp+arg_18]
0x140017f23  mov     r9d, 4; TokenInformationLength
0x140017f29  mov     [rbp+arg_18], 0
0x140017f30  lea     r8, [rbp+TokenInformation]; TokenInformation
0x140017f34  mov     [rbp+TokenInformation], 0
0x140017f3b  mov     [rsp+40h+ReturnLength], rax; ReturnLength
0x140017f40  lea     edx, [r9+10h]; TokenInformationClass
0x140017f44  call    cs:__imp_GetTokenInformation
0x140017f4a  test    eax, eax
0x140017f4c  jz      short loc_140017F52
0x140017f4e  xor     ebx, ebx
0x140017f50  jmp     short loc_140017F5D
0x140017f52  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x140017f57  mov     ebx, eax
0x140017f59  test    eax, eax
0x140017f5b  js      short loc_140017F66
0x140017f5d  cmp     [rbp+TokenInformation], 0
0x140017f61  setnz   cl
0x140017f64  mov     [rsi], cl
0x140017f66  mov     rcx, [rbp+TokenHandle]; hObject
0x140017f6a  call    cs:__imp_CloseHandle
0x140017f70  mov     rcx, rdi; hObject
0x140017f73  call    cs:__imp_CloseHandle
0x140017f79  mov     eax, ebx
0x140017f7b  mov     rbx, [rsp+40h+arg_8]
0x140017f80  add     rsp, 40h
0x140017f84  pop     rdi
0x140017f85  pop     rsi
0x140017f86  pop     rbp
0x140017f87  retn
```
