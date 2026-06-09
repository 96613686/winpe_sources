# FileOperationBroker::GetUserProfilePath(ushort *,ulong *)

- ea: `0x180028be0`
- end: `0x180028c72`
- name: `?GetUserProfilePath@FileOperationBroker@@AEAAJPEAGPEAK@Z`
- size: `146`
- prototype: `int(FileOperationBroker *__hidden this, unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180027cc0`
- `0x1800280a0`

## callees

- `0x18001c770`
- `0x180028be0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028c36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028c36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180028c02`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180028c02`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180028c15`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180028c15`
- `USERENV!GetUserProfileDirectoryW` at `0x180028c2c`
- `USERENV!GetUserProfileDirectoryW` at `0x180028c2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall FileOperationBroker::GetUserProfilePath(
        FileOperationBroker *this,
        unsigned __int16 *a2,
        unsigned int *a3)
{
  HANDLE CurrentProcess; // rax
  signed int v6; // ebx
  signed int LastError; // eax
  void *TokenHandle; // [rsp+30h] [rbp+8h] BYREF

  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) || (v6 = 0, !GetUserProfileDirectoryW(TokenHandle, a2, a3)) )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( v6 < 0 )
    {
      *a2 = 0;
      *a3 = 0;
    }
  }
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180028be0  mov     rax, rsp
0x180028be3  mov     [rax+10h], rbx
0x180028be7  mov     [rax+18h], rsi
0x180028beb  mov     [rax+8], rcx
0x180028bef  push    rdi
0x180028bf0  sub     rsp, 20h
0x180028bf4  mov     rdi, r8
0x180028bf7  mov     rsi, rdx
0x180028bfa  mov     qword ptr [rax+8], 0
0x180028c02  call    cs:__imp_GetCurrentProcess
0x180028c08  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x180028c0d  mov     edx, 8; DesiredAccess
0x180028c12  mov     rcx, rax; ProcessHandle
0x180028c15  call    cs:__imp_OpenProcessToken
0x180028c1b  test    eax, eax
0x180028c1d  jz      short loc_180028C36
0x180028c1f  xor     ebx, ebx
0x180028c21  mov     r8, rdi; lpcchSize
0x180028c24  mov     rdx, rsi; lpProfileDir
0x180028c27  mov     rcx, [rsp+28h+TokenHandle]; hToken
0x180028c2c  call    cs:__imp_GetUserProfileDirectoryW
0x180028c32  test    eax, eax
0x180028c34  jnz     short loc_180028C56
0x180028c36  call    cs:__imp_GetLastError
0x180028c3c  test    eax, eax
0x180028c3e  mov     ebx, eax
0x180028c40  jle     short loc_180028C4B
0x180028c42  movzx   ebx, ax
0x180028c45  or      ebx, 80070000h
0x180028c4b  test    ebx, ebx
0x180028c4d  jns     short loc_180028C56
0x180028c4f  xor     ecx, ecx
0x180028c51  mov     [rsi], cx
0x180028c54  mov     [rdi], ecx
0x180028c56  lea     rcx, [rsp+28h+TokenHandle]
0x180028c5b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180028c60  mov     eax, ebx
0x180028c62  mov     rbx, [rsp+28h+arg_8]
0x180028c67  mov     rsi, [rsp+28h+arg_10]
0x180028c6c  add     rsp, 20h
0x180028c70  pop     rdi
0x180028c71  retn
```
