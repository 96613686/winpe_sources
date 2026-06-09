# ModernDeployment::Autopilot::Core::AcquireEnvironmentPrivilege::Init(void)

- ea: `0x180021474`
- end: `0x180021515`
- name: `?Init@AcquireEnvironmentPrivilege@Core@Autopilot@ModernDeployment@@QEAAJXZ`
- size: `161`
- prototype: `int __fastcall(PVOID *ReturnedState)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180020d20`

## callees

- `0x180021474`
- `0x1800218c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002148e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002148e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800214ad`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800214ad`
- `ntdll!RtlAcquirePrivilege` at `0x1800214d7`
- `ntdll!RtlAcquirePrivilege` at `0x1800214d7`
- `ntdll!RtlReleasePrivilege` at `0x18002149f`
- `ntdll!RtlReleasePrivilege` at `0x18002149f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall ModernDeployment::Autopilot::Core::AcquireEnvironmentPrivilege::Init(PVOID *ReturnedState)
{
  PVOID v1; // rsi
  DWORD LastError; // ebx
  NTSTATUS v4; // eax
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  ULONG Privilege; // [rsp+30h] [rbp+8h] BYREF

  v1 = *ReturnedState;
  if ( *ReturnedState )
  {
    LastError = GetLastError();
    RtlReleasePrivilege(v1);
    SetLastError(LastError);
  }
  Privilege = 22;
  *ReturnedState = 0;
  v4 = RtlAcquirePrivilege(&Privilege, 1u, 0, ReturnedState);
  if ( v4 >= 0 )
    return 0;
  else
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x30,
             (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\inc\\AutopilotUefi.h",
             (const char *)(unsigned int)v4,
             v6);
}

```

## disassembly

```asm
0x180021474  mov     [rsp+arg_8], rbx
0x180021479  mov     [rsp+arg_10], rsi
0x18002147e  push    rdi; int
0x18002147f  sub     rsp, 20h
0x180021483  mov     rsi, [rcx]
0x180021486  mov     rdi, rcx
0x180021489  test    rsi, rsi
0x18002148c  jz      short loc_1800214B9
0x18002148e  call    cs:__imp_GetLastError
0x180021495  nop     dword ptr [rax+rax+00h]
0x18002149a  mov     rcx, rsi; ReturnedState
0x18002149d  mov     ebx, eax
0x18002149f  call    cs:__imp_RtlReleasePrivilege
0x1800214a6  nop     dword ptr [rax+rax+00h]
0x1800214ab  mov     ecx, ebx; dwErrCode
0x1800214ad  call    cs:__imp_SetLastError
0x1800214b4  nop     dword ptr [rax+rax+00h]
0x1800214b9  xor     r8d, r8d; Flags
0x1800214bc  mov     [rsp+28h+Privilege], 16h
0x1800214c4  mov     r9, rdi; ReturnedState
0x1800214c7  mov     qword ptr [rdi], 0
0x1800214ce  lea     rcx, [rsp+28h+Privilege]; Privilege
0x1800214d3  lea     edx, [r8+1]; NumPriv
0x1800214d7  call    cs:__imp_RtlAcquirePrivilege
0x1800214de  nop     dword ptr [rax+rax+00h]
0x1800214e3  test    eax, eax
0x1800214e5  jns     short loc_180021502
0x1800214e7  mov     rcx, [rsp+28h]; this
0x1800214ec  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800214f3  mov     r9d, eax; char *
0x1800214f6  mov     edx, 30h ; '0'; void *
0x1800214fb  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180021500  jmp     short loc_180021504
0x180021502  xor     eax, eax
0x180021504  mov     rbx, [rsp+28h+arg_8]
0x180021509  mov     rsi, [rsp+28h+arg_10]
0x18002150e  add     rsp, 20h
0x180021512  pop     rdi
0x180021513  retn
```
