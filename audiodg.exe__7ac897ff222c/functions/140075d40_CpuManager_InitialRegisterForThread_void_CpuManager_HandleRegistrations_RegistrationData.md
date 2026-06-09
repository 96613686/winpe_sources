# CpuManager::InitialRegisterForThread(void *,CpuManager::HandleRegistrations::RegistrationData *)

- ea: `0x140075d40`
- end: `0x140075e6d`
- name: `?InitialRegisterForThread@CpuManager@@EEAAJPEAXPEAURegistrationData@HandleRegistrations@1@@Z`
- size: `301`
- prototype: `int(CpuManager *__hidden this, void *, struct CpuManager::HandleRegistrations::RegistrationData *)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x14005d0e0`
- `0x14005e168`
- `0x140075d40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140075dca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140075dca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140075d8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140075d94`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140075d8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140075d94`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140075dc0`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140075dc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140075e48`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140075e48`
- `ntdll!NtSetInformationThread` at `0x140075e20`
- `ntdll!NtSetInformationThread` at `0x140075e20`

## pseudocode

```c
__int64 __fastcall CpuManager::InitialRegisterForThread(
        CpuManager *this,
        void *a2,
        struct CpuManager::HandleRegistrations::RegistrationData *a3)
{
  HANDLE CurrentProcess; // rbx
  HANDLE v7; // rax
  signed int LastError; // eax
  unsigned int v9; // ebx
  HANDLE v10; // rcx
  __int64 v11; // rdx
  HANDLE v12; // rcx
  unsigned int v13; // r9d
  unsigned int v14; // edx
  NTSTATUS v15; // ebx
  HANDLE TargetHandle; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v18; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD ThreadInformation[65]; // [rsp+58h] [rbp-A8h] BYREF

  TargetHandle = 0;
  memset_0(&v18, 0, 0x208u);
  CurrentProcess = GetCurrentProcess();
  v7 = GetCurrentProcess();
  if ( !DuplicateHandle(v7, a2, CurrentProcess, &TargetHandle, 0x400u, 0, 0) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_4;
  }
  v11 = *((unsigned __int16 *)this + 400);
  v12 = TargetHandle;
  ThreadInformation[v11] |= *((_QWORD *)this + 101);
  v13 = v18;
  v14 = v11 + 1;
  if ( v18 <= v14 )
    v13 = v14;
  v18 = v13;
  v15 = NtSetInformationThread(v12, ThreadEnableAlignmentFaultFixup|0x20, ThreadInformation, 8 * v13);
  if ( v15 < 0 )
  {
    v9 = v15 | 0x10000000;
LABEL_4:
    v10 = TargetHandle;
    goto LABEL_10;
  }
  v10 = 0;
  *(_QWORD *)a3 = TargetHandle;
  v9 = 0;
  TargetHandle = 0;
LABEL_10:
  if ( v10 )
    CloseHandle(v10);
  return v9;
}

```

## disassembly

```asm
0x140075d40  push    rbp
0x140075d42  push    rbx
0x140075d43  push    rsi
0x140075d44  push    rdi
0x140075d45  push    r14
0x140075d47  lea     rbp, [rsp-170h]
0x140075d4f  sub     rsp, 270h
0x140075d56  mov     rax, cs:__security_cookie
0x140075d5d  xor     rax, rsp
0x140075d60  mov     [rbp+190h+var_30], rax
0x140075d67  mov     rsi, r8
0x140075d6a  mov     [rsp+290h+TargetHandle], 0
0x140075d73  mov     rdi, rdx
0x140075d76  mov     r14, rcx
0x140075d79  xor     edx, edx; Val
0x140075d7b  lea     rcx, [rsp+290h+var_240]; void *
0x140075d80  mov     r8d, 208h; Size
0x140075d86  call    memset_0
0x140075d8b  call    cs:__imp_GetCurrentProcess
0x140075d91  mov     rbx, rax
0x140075d94  call    cs:__imp_GetCurrentProcess
0x140075d9a  mov     [rsp+290h+dwOptions], 0; dwOptions
0x140075da2  lea     r9, [rsp+290h+TargetHandle]; lpTargetHandle
0x140075da7  mov     rcx, rax; hSourceProcessHandle
0x140075daa  mov     [rsp+290h+bInheritHandle], 0; bInheritHandle
0x140075db2  mov     r8, rbx; hTargetProcessHandle
0x140075db5  mov     [rsp+290h+dwDesiredAccess], 400h; dwDesiredAccess
0x140075dbd  mov     rdx, rdi; hSourceHandle
0x140075dc0  call    cs:__imp_DuplicateHandle
0x140075dc6  test    eax, eax
0x140075dc8  jnz     short loc_140075DE6
0x140075dca  call    cs:__imp_GetLastError
0x140075dd0  mov     ebx, eax
0x140075dd2  test    eax, eax
0x140075dd4  jle     short loc_140075DDF
0x140075dd6  movzx   ebx, ax
0x140075dd9  or      ebx, 80070000h
0x140075ddf  mov     rcx, [rsp+290h+TargetHandle]
0x140075de4  jmp     short loc_140075E43
0x140075de6  movzx   edx, word ptr [r14+320h]
0x140075dee  lea     r8, [rsp+290h+ThreadInformation]; ThreadInformation
0x140075df3  mov     rax, [r14+328h]
0x140075dfa  mov     rcx, [rsp+290h+TargetHandle]; ThreadHandle
0x140075dff  or      [rsp+rdx*8+290h+ThreadInformation], rax
0x140075e04  mov     r9d, [rsp+290h+var_240]
0x140075e09  inc     edx
0x140075e0b  cmp     r9d, edx
0x140075e0e  cmovbe  r9d, edx
0x140075e12  mov     edx, 27h ; '''; ThreadInformationClass
0x140075e17  mov     [rsp+290h+var_240], r9d
0x140075e1c  shl     r9d, 3; ThreadInformationLength
0x140075e20  call    cs:__imp_NtSetInformationThread
0x140075e26  mov     ebx, eax
0x140075e28  test    eax, eax
0x140075e2a  jns     short loc_140075E32
0x140075e2c  bts     ebx, 1Ch
0x140075e30  jmp     short loc_140075DDF
0x140075e32  mov     rax, [rsp+290h+TargetHandle]
0x140075e37  xor     ecx, ecx; hObject
0x140075e39  mov     [rsi], rax
0x140075e3c  xor     ebx, ebx
0x140075e3e  mov     [rsp+290h+TargetHandle], rcx
0x140075e43  test    rcx, rcx
0x140075e46  jz      short loc_140075E4E
0x140075e48  call    cs:__imp_CloseHandle
0x140075e4e  mov     eax, ebx
0x140075e50  mov     rcx, [rbp+190h+var_30]
0x140075e57  xor     rcx, rsp; StackCookie
0x140075e5a  call    __security_check_cookie
0x140075e5f  add     rsp, 270h
0x140075e66  pop     r14
0x140075e68  pop     rdi
0x140075e69  pop     rsi
0x140075e6a  pop     rbx
0x140075e6b  pop     rbp
0x140075e6c  retn
```
