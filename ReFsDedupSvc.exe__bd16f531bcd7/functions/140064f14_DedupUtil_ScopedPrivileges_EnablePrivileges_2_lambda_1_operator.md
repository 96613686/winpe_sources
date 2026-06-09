# _DedupUtil::ScopedPrivileges::EnablePrivileges_::_2_::_lambda_1_::operator()

- ea: `0x140064f14`
- end: `0x140064f8a`
- name: `_DedupUtil::ScopedPrivileges::EnablePrivileges_::_2_::_lambda_1_::operator()`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140065e44`

## callees

- `0x1400635dc`
- `0x140064f14`
- `0x140069aa0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140064f51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140064f51`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140064f41`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x140064f41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140064f2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x140064f2a`

## string_xrefs

- `0x140064f6f`: `Failed to acquire required security privileges, error 0x%x\n`

## pseudocode

```c
__int64 __fastcall DedupUtil::ScopedPrivileges::EnablePrivileges_::_2_::_lambda_1_::operator()(void ***a1, DWORD a2)
{
  void **v2; // rbx
  HANDLE CurrentProcess; // rax
  DWORD LastError; // [rsp+38h] [rbp+10h] BYREF

  LastError = a2;
  v2 = *a1;
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    *a1,
    0);
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, v2) )
    return 0;
  LastError = GetLastError();
  if ( !LastError )
    return 0;
  DedupUtil::Print<unsigned long &>(6, L"Failed to acquire required security privileges, error 0x%x\n", &LastError);
  return LastError;
}

```

## disassembly

```asm
0x140064f14  mov     [rsp+arg_8], edx
0x140064f18  push    rbx
0x140064f19  sub     rsp, 20h
0x140064f1d  mov     rbx, [rcx]
0x140064f20  xor     edx, edx
0x140064f22  mov     rcx, rbx
0x140064f25  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140064f2a  call    cs:__imp_GetCurrentProcess
0x140064f31  nop     dword ptr [rax+rax+00h]
0x140064f36  mov     r8, rbx; TokenHandle
0x140064f39  mov     edx, 28h ; '('; DesiredAccess
0x140064f3e  mov     rcx, rax; ProcessHandle
0x140064f41  call    cs:__imp_OpenProcessToken
0x140064f48  nop     dword ptr [rax+rax+00h]
0x140064f4d  test    eax, eax
0x140064f4f  jnz     short loc_140064F81
0x140064f51  call    cs:__imp_GetLastError
0x140064f58  nop     dword ptr [rax+rax+00h]
0x140064f5d  mov     [rsp+28h+arg_8], eax
0x140064f61  test    eax, eax
0x140064f63  jz      short loc_140064F81
0x140064f65  lea     r8, [rsp+28h+arg_8]
0x140064f6a  mov     ecx, 6
0x140064f6f  lea     rdx, aFailedToAcquir; "Failed to acquire required security pri"...
0x140064f76  call    ??$Print@AEAK@DedupUtil@@YAXW4MessageType@0@PEBGAEAK@Z; DedupUtil::Print<ulong &>(DedupUtil::MessageType,ushort const *,ulong &)
0x140064f7b  mov     eax, [rsp+28h+arg_8]
0x140064f7f  jmp     short loc_140064F83
0x140064f81  xor     eax, eax
0x140064f83  add     rsp, 20h
0x140064f87  pop     rbx
0x140064f88  retn
```
