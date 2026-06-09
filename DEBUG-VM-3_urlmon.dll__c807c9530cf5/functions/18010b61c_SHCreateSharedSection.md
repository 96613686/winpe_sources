# SHCreateSharedSection

- ea: `0x18010b61c`
- end: `0x18010b6ff`
- name: `SHCreateSharedSection`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18010bdb8`

## callees

- `0x18009d920`
- `0x18010b240`
- `0x18010b61c`

## import_xrefs

- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18010b654`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18010b663`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18010b654`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18010b663`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18010b67a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18010b683`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18010b67a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18010b683`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010b6c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010b6c6`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18010b6af`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18010b6af`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18010b63f`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18010b6dd`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18010b63f`
- `api-ms-win-core-memory-l1-1-0!OpenFileMappingW` at `0x18010b6dd`

## pseudocode

```c
__int64 __fastcall SHCreateSharedSection(__int64 a1, __int64 a2, void *a3, _QWORD *a4)
{
  HANDLE v5; // rax
  void *NamedSection; // rdi
  HANDLE CurrentProcess; // rbx
  HANDLE v8; // rax
  HANDLE TargetHandle; // [rsp+60h] [rbp+18h] BYREF

  TargetHandle = a3;
  v5 = OpenFileMappingW(6u, 0, L"Local\\windows_ie_global_counters");
  TargetHandle = v5;
  if ( v5 )
    goto LABEL_7;
  if ( !(unsigned __int8)IEConfiguration_GetBool(536870913) && (unsigned __int8)IEConfiguration_GetBool(536870916) )
    goto LABEL_6;
  NamedSection = (void *)CreateNamedSection();
  if ( NamedSection )
  {
    CurrentProcess = GetCurrentProcess();
    v8 = GetCurrentProcess();
    DuplicateHandle(v8, NamedSection, CurrentProcess, &TargetHandle, 6u, 0, 1u);
LABEL_6:
    v5 = TargetHandle;
    goto LABEL_7;
  }
  if ( GetLastError() != 5 )
    goto LABEL_6;
  v5 = OpenFileMappingW(6u, 0, L"Local\\windows_ie_global_counters");
  TargetHandle = v5;
LABEL_7:
  *a4 = v5;
  if ( v5 )
    return 0;
  else
    return ResultFromKnownLastError();
}

```

## disassembly

```asm
0x18010b61c  mov     [rsp+arg_0], rbx
0x18010b621  mov     [rsp+arg_8], rsi
0x18010b626  mov     [rsp+TargetHandle], r8
0x18010b62b  push    rdi
0x18010b62c  sub     rsp, 40h
0x18010b630  xor     edx, edx; bInheritHandle
0x18010b632  lea     r8, aLocalWindowsIe; "Local\\windows_ie_global_counters"
0x18010b639  mov     rsi, r9
0x18010b63c  lea     ecx, [rdx+6]; dwDesiredAccess
0x18010b63f  call    cs:__imp_OpenFileMappingW
0x18010b645  mov     [rsp+48h+TargetHandle], rax
0x18010b64a  test    rax, rax
0x18010b64d  jnz     short loc_18010B6BA
0x18010b64f  mov     ecx, 20000001h
0x18010b654  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18010b65a  test    al, al
0x18010b65c  jnz     short loc_18010B66D
0x18010b65e  mov     ecx, 20000004h
0x18010b663  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18010b669  test    al, al
0x18010b66b  jnz     short loc_18010B6B5
0x18010b66d  call    _CreateNamedSection
0x18010b672  mov     rdi, rax
0x18010b675  test    rax, rax
0x18010b678  jz      short loc_18010B6C6
0x18010b67a  call    cs:__imp_GetCurrentProcess
0x18010b680  mov     rbx, rax
0x18010b683  call    cs:__imp_GetCurrentProcess
0x18010b689  mov     [rsp+48h+dwOptions], 1; dwOptions
0x18010b691  lea     r9, [rsp+48h+TargetHandle]; lpTargetHandle
0x18010b696  mov     rcx, rax; hSourceProcessHandle
0x18010b699  mov     [rsp+48h+bInheritHandle], 0; bInheritHandle
0x18010b6a1  mov     r8, rbx; hTargetProcessHandle
0x18010b6a4  mov     [rsp+48h+dwDesiredAccess], 6; dwDesiredAccess
0x18010b6ac  mov     rdx, rdi; hSourceHandle
0x18010b6af  call    cs:__imp_DuplicateHandle
0x18010b6b5  mov     rax, [rsp+48h+TargetHandle]
0x18010b6ba  mov     [rsi], rax
0x18010b6bd  test    rax, rax
0x18010b6c0  jz      short loc_18010B6EA
0x18010b6c2  xor     eax, eax
0x18010b6c4  jmp     short loc_18010B6EF
0x18010b6c6  call    cs:__imp_GetLastError
0x18010b6cc  cmp     eax, 5
0x18010b6cf  jnz     short loc_18010B6B5
0x18010b6d1  lea     r8, aLocalWindowsIe; "Local\\windows_ie_global_counters"
0x18010b6d8  xor     edx, edx; bInheritHandle
0x18010b6da  lea     ecx, [rax+1]; dwDesiredAccess
0x18010b6dd  call    cs:__imp_OpenFileMappingW
0x18010b6e3  mov     [rsp+48h+TargetHandle], rax
0x18010b6e8  jmp     short loc_18010B6BA
0x18010b6ea  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18010b6ef  mov     rbx, [rsp+48h+arg_0]
0x18010b6f4  mov     rsi, [rsp+48h+arg_8]
0x18010b6f9  add     rsp, 40h
0x18010b6fd  pop     rdi
0x18010b6fe  retn
```
