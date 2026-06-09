# NpGetUserName

- ea: `0x1800357b0`
- end: `0x1800358dc`
- name: `NpGetUserName`
- size: `300`
- prototype: `__int64 __fastcall(HANDLE hNamedPipe, LPWSTR lpNameBuffer)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800357b0`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x1800357f2`
- `ntdll!NtOpenThreadToken` at `0x1800357f2`
- `ntdll!NtSetInformationThread` at `0x180035855`
- `ntdll!NtSetInformationThread` at `0x180035855`
- `api-ms-win-core-namedpipe-l1-1-0!ImpersonateNamedPipeClient` at `0x18003580f`
- `api-ms-win-core-namedpipe-l1-1-0!ImpersonateNamedPipeClient` at `0x18003580f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180035837`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180035837`
- `KERNEL32!GetLastError` at `0x180035875`
- `KERNEL32!GetLastError` at `0x180035875`
- `KERNEL32!BaseSetLastNTError` at `0x1800358b2`
- `KERNEL32!BaseSetLastNTError` at `0x1800358b2`
- `KERNEL32!CloseHandle` at `0x180035862`
- `KERNEL32!CloseHandle` at `0x1800358c3`
- `KERNEL32!CloseHandle` at `0x180035862`
- `KERNEL32!CloseHandle` at `0x1800358c3`
- `SspiCli!GetUserNameExW` at `0x18003582a`
- `SspiCli!GetUserNameExW` at `0x18003589c`
- `SspiCli!GetUserNameExW` at `0x18003582a`
- `SspiCli!GetUserNameExW` at `0x18003589c`

## pseudocode

```c
__int64 __fastcall NpGetUserName(HANDLE hNamedPipe, LPWSTR lpNameBuffer, ULONG a3)
{
  int i; // edi
  NTSTATUS v7; // eax
  int v8; // ebx
  unsigned int UserName; // esi
  NTSTATUS v10; // ebx
  DWORD LastError; // eax
  ULONG nSize; // [rsp+60h] [rbp+18h] BYREF
  HANDLE TokenHandle; // [rsp+68h] [rbp+20h] BYREF

  TokenHandle = 0;
  for ( i = 0; ; i = 1 )
  {
    nSize = a3;
    v7 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 4u, 1u, &TokenHandle);
    v8 = v7;
    if ( ((v7 + 0x80000000) & 0x80000000) == 0 && v7 != -1073741700 )
      break;
    if ( !ImpersonateNamedPipeClient(hNamedPipe) )
    {
      if ( v8 >= 0 )
        CloseHandle(TokenHandle);
      return 0;
    }
    UserName = GetUserNameExW((EXTENDED_NAME_FORMAT)65538, lpNameBuffer, &nSize);
    if ( v8 >= 0 )
    {
      v10 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &TokenHandle, 8u);
      CloseHandle(TokenHandle);
      if ( v10 < 0 )
      {
        BaseSetLastNTError((unsigned int)v10);
        return 0;
      }
    }
    else
    {
      RevertToSelf();
    }
    if ( (_BYTE)UserName )
      return UserName;
    if ( i )
      return UserName;
    LastError = GetLastError();
    if ( LastError != 127 && LastError != 1285 )
      return UserName;
    nSize = 0;
    GetUserNameExW((EXTENDED_NAME_FORMAT)65538, lpNameBuffer, &nSize);
  }
  return 0;
}

```

## disassembly

```asm
0x1800357b0  mov     [rsp+arg_0], rbx
0x1800357b5  push    rbp
0x1800357b6  push    rsi
0x1800357b7  push    rdi
0x1800357b8  push    r14
0x1800357ba  push    r15
0x1800357bc  sub     rsp, 20h
0x1800357c0  mov     r15d, r8d
0x1800357c3  mov     [rsp+48h+TokenHandle], 0
0x1800357cc  mov     rbp, rdx
0x1800357cf  mov     r14, rcx
0x1800357d2  xor     edi, edi
0x1800357d4  mov     esi, 80000000h
0x1800357d9  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x1800357de  mov     [rsp+48h+nSize], r15d
0x1800357e3  mov     r8b, 1; OpenAsSelf
0x1800357e6  mov     edx, 4; DesiredAccess
0x1800357eb  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800357f2  call    cs:__imp_NtOpenThreadToken
0x1800357f8  mov     ebx, eax
0x1800357fa  lea     ecx, [rax+rsi]
0x1800357fd  test    esi, ecx
0x1800357ff  jnz     short loc_18003580C
0x180035801  cmp     eax, 0C000007Ch
0x180035806  jnz     loc_1800358C9
0x18003580c  mov     rcx, r14; hNamedPipe
0x18003580f  call    cs:__imp_ImpersonateNamedPipeClient
0x180035815  test    eax, eax
0x180035817  jz      loc_1800358BA
0x18003581d  lea     r8, [rsp+48h+nSize]; nSize
0x180035822  mov     rdx, rbp; lpNameBuffer
0x180035825  mov     ecx, 10002h; NameFormat
0x18003582a  call    cs:__imp_GetUserNameExW
0x180035830  movzx   esi, al
0x180035833  test    ebx, ebx
0x180035835  jns     short loc_18003583F
0x180035837  call    cs:__imp_RevertToSelf
0x18003583d  jmp     short loc_18003586C
0x18003583f  mov     r9d, 8; ThreadInformationLength
0x180035845  lea     r8, [rsp+48h+TokenHandle]; ThreadInformation
0x18003584a  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180035851  lea     edx, [r9-3]; ThreadInformationClass
0x180035855  call    cs:__imp_NtSetInformationThread
0x18003585b  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x180035860  mov     ebx, eax
0x180035862  call    cs:__imp_CloseHandle
0x180035868  test    ebx, ebx
0x18003586a  js      short loc_1800358B0
0x18003586c  test    sil, sil
0x18003586f  jnz     short loc_1800358AC
0x180035871  test    edi, edi
0x180035873  jnz     short loc_1800358AC
0x180035875  call    cs:__imp_GetLastError
0x18003587b  cmp     eax, 7Fh
0x18003587e  jz      short loc_180035887
0x180035880  cmp     eax, 505h
0x180035885  jnz     short loc_1800358AC
0x180035887  lea     r8, [rsp+48h+nSize]; nSize
0x18003588c  mov     [rsp+48h+nSize], 0
0x180035894  mov     rdx, rbp; lpNameBuffer
0x180035897  mov     ecx, 10002h; NameFormat
0x18003589c  call    cs:__imp_GetUserNameExW
0x1800358a2  mov     edi, 1
0x1800358a7  jmp     loc_1800357D4
0x1800358ac  mov     eax, esi
0x1800358ae  jmp     short loc_1800358CB
0x1800358b0  mov     ecx, ebx
0x1800358b2  call    cs:__imp_BaseSetLastNTError
0x1800358b8  jmp     short loc_1800358C9
0x1800358ba  test    ebx, ebx
0x1800358bc  js      short loc_1800358C9
0x1800358be  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x1800358c3  call    cs:__imp_CloseHandle
0x1800358c9  xor     eax, eax
0x1800358cb  mov     rbx, [rsp+48h+arg_0]
0x1800358d0  add     rsp, 20h
0x1800358d4  pop     r15
0x1800358d6  pop     r14
0x1800358d8  pop     rdi
0x1800358d9  pop     rsi
0x1800358da  pop     rbp
0x1800358db  retn
```
