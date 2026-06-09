# ModernDeployment::Autopilot::Core::AcquireEnvironmentPrivilege::Init(void)

- ea: `0x180020a84`
- end: `0x180020b0c`
- name: `?Init@AcquireEnvironmentPrivilege@Core@Autopilot@ModernDeployment@@QEAAJXZ`
- size: `136`
- prototype: `__int64 __fastcall(PVOID *ReturnedState)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800203bc`

## callees

- `0x180020a84`
- `0x180020e9c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020a9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020a9e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020ab1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180020ab1`
- `ntdll!RtlAcquirePrivilege` at `0x180020ad5`
- `ntdll!RtlAcquirePrivilege` at `0x180020ad5`
- `ntdll!RtlReleasePrivilege` at `0x180020aa9`
- `ntdll!RtlReleasePrivilege` at `0x180020aa9`

## pseudocode

```c
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
0x180020a84  mov     [rsp+arg_8], rbx
0x180020a89  mov     [rsp+arg_10], rsi
0x180020a8e  push    rdi; int
0x180020a8f  sub     rsp, 20h
0x180020a93  mov     rsi, [rcx]
0x180020a96  mov     rdi, rcx
0x180020a99  test    rsi, rsi
0x180020a9c  jz      short loc_180020AB7
0x180020a9e  call    cs:__imp_GetLastError
0x180020aa4  mov     rcx, rsi; ReturnedState
0x180020aa7  mov     ebx, eax
0x180020aa9  call    cs:__imp_RtlReleasePrivilege
0x180020aaf  mov     ecx, ebx; dwErrCode
0x180020ab1  call    cs:__imp_SetLastError
0x180020ab7  xor     r8d, r8d; Flags
0x180020aba  mov     [rsp+28h+Privilege], 16h
0x180020ac2  mov     r9, rdi; ReturnedState
0x180020ac5  mov     qword ptr [rdi], 0
0x180020acc  lea     rcx, [rsp+28h+Privilege]; Privilege
0x180020ad1  lea     edx, [r8+1]; NumPriv
0x180020ad5  call    cs:__imp_RtlAcquirePrivilege
0x180020adb  test    eax, eax
0x180020add  jns     short loc_180020AFA
0x180020adf  mov     rcx, [rsp+28h]; this
0x180020ae4  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\moderndeployment\\au"...
0x180020aeb  mov     r9d, eax; char *
0x180020aee  mov     edx, 30h ; '0'; void *
0x180020af3  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180020af8  jmp     short loc_180020AFC
0x180020afa  xor     eax, eax
0x180020afc  mov     rbx, [rsp+28h+arg_8]
0x180020b01  mov     rsi, [rsp+28h+arg_10]
0x180020b06  add     rsp, 20h
0x180020b0a  pop     rdi
0x180020b0b  retn
```
