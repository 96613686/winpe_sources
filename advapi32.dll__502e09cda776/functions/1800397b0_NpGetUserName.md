# NpGetUserName

- ea: `0x1800397b0`
- end: `0x180039919`
- name: `NpGetUserName`
- size: `361`
- prototype: `__int64 __fastcall(HANDLE hNamedPipe, LPWSTR lpNameBuffer)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800397b0`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x1800397f2`
- `ntdll!NtOpenThreadToken` at `0x1800397f2`
- `ntdll!NtSetInformationThread` at `0x18003986d`
- `ntdll!NtSetInformationThread` at `0x18003986d`
- `api-ms-win-core-namedpipe-l1-1-0!ImpersonateNamedPipeClient` at `0x180039815`
- `api-ms-win-core-namedpipe-l1-1-0!ImpersonateNamedPipeClient` at `0x180039815`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180039849`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180039849`
- `KERNEL32!GetLastError` at `0x180039899`
- `KERNEL32!GetLastError` at `0x180039899`
- `KERNEL32!BaseSetLastNTError` at `0x1800398e2`
- `KERNEL32!BaseSetLastNTError` at `0x1800398e2`
- `KERNEL32!CloseHandle` at `0x180039880`
- `KERNEL32!CloseHandle` at `0x1800398f9`
- `KERNEL32!CloseHandle` at `0x180039880`
- `KERNEL32!CloseHandle` at `0x1800398f9`
- `SspiCli!GetUserNameExW` at `0x180039836`
- `SspiCli!GetUserNameExW` at `0x1800398c6`
- `SspiCli!GetUserNameExW` at `0x180039836`
- `SspiCli!GetUserNameExW` at `0x1800398c6`

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
0x1800397b0  mov     [rsp+arg_0], rbx
0x1800397b5  push    rbp
0x1800397b6  push    rsi
0x1800397b7  push    rdi
0x1800397b8  push    r14
0x1800397ba  push    r15
0x1800397bc  sub     rsp, 20h
0x1800397c0  mov     r15d, r8d
0x1800397c3  mov     [rsp+48h+TokenHandle], 0
0x1800397cc  mov     rbp, rdx
0x1800397cf  mov     r14, rcx
0x1800397d2  xor     edi, edi
0x1800397d4  mov     esi, 80000000h
0x1800397d9  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x1800397de  mov     [rsp+48h+nSize], r15d
0x1800397e3  mov     r8b, 1; OpenAsSelf
0x1800397e6  mov     edx, 4; DesiredAccess
0x1800397eb  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1800397f2  call    cs:__imp_NtOpenThreadToken
0x1800397f9  nop     dword ptr [rax+rax+00h]
0x1800397fe  mov     ebx, eax
0x180039800  lea     ecx, [rax+rsi]
0x180039803  test    esi, ecx
0x180039805  jnz     short loc_180039812
0x180039807  cmp     eax, 0C000007Ch
0x18003980c  jnz     loc_180039905
0x180039812  mov     rcx, r14; hNamedPipe
0x180039815  call    cs:__imp_ImpersonateNamedPipeClient
0x18003981c  nop     dword ptr [rax+rax+00h]
0x180039821  test    eax, eax
0x180039823  jz      loc_1800398F0
0x180039829  lea     r8, [rsp+48h+nSize]; nSize
0x18003982e  mov     rdx, rbp; lpNameBuffer
0x180039831  mov     ecx, 10002h; NameFormat
0x180039836  call    cs:__imp_GetUserNameExW
0x18003983d  nop     dword ptr [rax+rax+00h]
0x180039842  movzx   esi, al
0x180039845  test    ebx, ebx
0x180039847  jns     short loc_180039857
0x180039849  call    cs:__imp_RevertToSelf
0x180039850  nop     dword ptr [rax+rax+00h]
0x180039855  jmp     short loc_180039890
0x180039857  mov     r9d, 8; ThreadInformationLength
0x18003985d  lea     r8, [rsp+48h+TokenHandle]; ThreadInformation
0x180039862  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180039869  lea     edx, [r9-3]; ThreadInformationClass
0x18003986d  call    cs:__imp_NtSetInformationThread
0x180039874  nop     dword ptr [rax+rax+00h]
0x180039879  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18003987e  mov     ebx, eax
0x180039880  call    cs:__imp_CloseHandle
0x180039887  nop     dword ptr [rax+rax+00h]
0x18003988c  test    ebx, ebx
0x18003988e  js      short loc_1800398E0
0x180039890  test    sil, sil
0x180039893  jnz     short loc_1800398DC
0x180039895  test    edi, edi
0x180039897  jnz     short loc_1800398DC
0x180039899  call    cs:__imp_GetLastError
0x1800398a0  nop     dword ptr [rax+rax+00h]
0x1800398a5  cmp     eax, 7Fh
0x1800398a8  jz      short loc_1800398B1
0x1800398aa  cmp     eax, 505h
0x1800398af  jnz     short loc_1800398DC
0x1800398b1  lea     r8, [rsp+48h+nSize]; nSize
0x1800398b6  mov     [rsp+48h+nSize], 0
0x1800398be  mov     rdx, rbp; lpNameBuffer
0x1800398c1  mov     ecx, 10002h; NameFormat
0x1800398c6  call    cs:__imp_GetUserNameExW
0x1800398cd  nop     dword ptr [rax+rax+00h]
0x1800398d2  mov     edi, 1
0x1800398d7  jmp     loc_1800397D4
0x1800398dc  mov     eax, esi
0x1800398de  jmp     short loc_180039907
0x1800398e0  mov     ecx, ebx
0x1800398e2  call    cs:__imp_BaseSetLastNTError
0x1800398e9  nop     dword ptr [rax+rax+00h]
0x1800398ee  jmp     short loc_180039905
0x1800398f0  test    ebx, ebx
0x1800398f2  js      short loc_180039905
0x1800398f4  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x1800398f9  call    cs:__imp_CloseHandle
0x180039900  nop     dword ptr [rax+rax+00h]
0x180039905  xor     eax, eax
0x180039907  mov     rbx, [rsp+48h+arg_0]
0x18003990c  add     rsp, 20h
0x180039910  pop     r15
0x180039912  pop     r14
0x180039914  pop     rdi
0x180039915  pop     rsi
0x180039916  pop     rbp
0x180039917  retn
```
