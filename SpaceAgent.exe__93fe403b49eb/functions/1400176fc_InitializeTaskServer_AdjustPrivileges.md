# InitializeTaskServer_AdjustPrivileges

- ea: `0x1400176fc`
- end: `0x1400177ce`
- name: `InitializeTaskServer_AdjustPrivileges`
- size: `210`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task`

## callers

- `0x1400174bc`

## callees

- `0x1400176fc`
- `0x14001edc0`

## import_xrefs

- `ADVAPI32!LookupPrivilegeValueW` at `0x140017759`
- `ADVAPI32!LookupPrivilegeValueW` at `0x140017759`
- `ADVAPI32!OpenProcessToken` at `0x140017740`
- `ADVAPI32!OpenProcessToken` at `0x140017740`
- `ADVAPI32!AdjustTokenPrivileges` at `0x14001779d`
- `ADVAPI32!AdjustTokenPrivileges` at `0x14001779d`
- `KERNEL32!GetCurrentProcess` at `0x14001772e`
- `KERNEL32!GetCurrentProcess` at `0x14001772e`
- `KERNEL32!CloseHandle` at `0x1400177af`
- `KERNEL32!CloseHandle` at `0x1400177af`

## string_xrefs

- `0x140017752`: `SeDebugPrivilege`

## pseudocode

```c
__int64 InitializeTaskServer_AdjustPrivileges()
{
  HANDLE CurrentProcess; // rax
  unsigned int v1; // ebx
  void *TokenHandle; // [rsp+30h] [rbp-30h] BYREF
  _LUID Luid; // [rsp+38h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+40h] [rbp-20h] BYREF

  TokenHandle = (void *)-1LL;
  NewState = 0;
  Luid = 0;
  CurrentProcess = GetCurrentProcess();
  v1 = OpenProcessToken(CurrentProcess, 0x20u, &TokenHandle);
  if ( v1 )
  {
    v1 = LookupPrivilegeValueW(0, L"SeDebugPrivilege", &Luid);
    if ( v1 )
    {
      NewState.Privileges[0].Luid = Luid;
      NewState.PrivilegeCount = 1;
      NewState.Privileges[0].Attributes = 2;
      v1 = AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, 0, 0);
    }
  }
  if ( TokenHandle != (void *)-1LL )
    CloseHandle(TokenHandle);
  return v1;
}

```

## disassembly

```asm
0x1400176fc  mov     [rsp-8+arg_0], rbx
0x140017701  push    rbp
0x140017702  mov     rbp, rsp
0x140017705  sub     rsp, 60h
0x140017709  mov     rax, cs:__security_cookie
0x140017710  xor     rax, rsp
0x140017713  mov     [rbp+var_10], rax
0x140017717  xorps   xmm0, xmm0
0x14001771a  mov     [rbp+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x140017722  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x140017726  mov     qword ptr [rbp+Luid.LowPart], 0
0x14001772e  call    cs:__imp_GetCurrentProcess
0x140017734  lea     r8, [rbp+TokenHandle]; TokenHandle
0x140017738  mov     edx, 20h ; ' '; DesiredAccess
0x14001773d  mov     rcx, rax; ProcessHandle
0x140017740  call    cs:__imp_OpenProcessToken
0x140017746  mov     ebx, eax
0x140017748  test    eax, eax
0x14001774a  jz      short loc_1400177A5
0x14001774c  lea     r8, [rbp+Luid]; lpLuid
0x140017750  xor     ecx, ecx; lpSystemName
0x140017752  lea     rdx, aSedebugprivile; "SeDebugPrivilege"
0x140017759  call    cs:__imp_LookupPrivilegeValueW
0x14001775f  mov     ebx, eax
0x140017761  test    eax, eax
0x140017763  jz      short loc_1400177A5
0x140017765  mov     rax, qword ptr [rbp+Luid.LowPart]
0x140017769  lea     r8, [rbp+NewState]; NewState
0x14001776d  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x140017771  mov     r9d, 10h; BufferLength
0x140017777  mov     [rsp+60h+ReturnLength], 0; ReturnLength
0x140017780  xor     edx, edx; DisableAllPrivileges
0x140017782  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x140017786  mov     [rbp+NewState.PrivilegeCount], 1
0x14001778d  mov     [rbp+NewState.Privileges.Attributes], 2
0x140017794  mov     [rsp+60h+PreviousState], 0; PreviousState
0x14001779d  call    cs:__imp_AdjustTokenPrivileges
0x1400177a3  mov     ebx, eax
0x1400177a5  mov     rcx, [rbp+TokenHandle]; hObject
0x1400177a9  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400177ad  jz      short loc_1400177B5
0x1400177af  call    cs:__imp_CloseHandle
0x1400177b5  mov     eax, ebx
0x1400177b7  mov     rcx, [rbp+var_10]
0x1400177bb  xor     rcx, rsp; StackCookie
0x1400177be  call    __security_check_cookie
0x1400177c3  mov     rbx, [rsp+60h+arg_0]
0x1400177c8  add     rsp, 60h
0x1400177cc  pop     rbp
0x1400177cd  retn
```
