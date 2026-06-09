# RdVhd::Uvhd::CUvhdProfileManager::SetPrivilege(ushort const *,int)

- ea: `0x180048220`
- end: `0x18004837c`
- name: `?SetPrivilege@CUvhdProfileManager@Uvhd@RdVhd@@IEAAJPEBGH@Z`
- size: `348`
- prototype: `int(RdVhd::Uvhd::CUvhdProfileManager *__hidden this, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180045840`
- `0x180046534`

## callees

- `0x18001a280`
- `0x180048220`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048284`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048284`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048356`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180048356`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180048268`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180048268`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004827a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18004827a`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800482ec`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18004833d`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800482ec`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18004833d`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800482ab`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800482ab`

## pseudocode

```c
__int64 __fastcall RdVhd::Uvhd::CUvhdProfileManager::SetPrivilege(
        RdVhd::Uvhd::CUvhdProfileManager *this,
        const unsigned __int16 *a2,
        int a3)
{
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  unsigned int v7; // ebx
  DWORD v8; // ecx
  DWORD v9; // ecx
  DWORD BufferLength; // [rsp+30h] [rbp-40h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-38h] BYREF
  struct _LUID Luid; // [rsp+40h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+48h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+58h] [rbp-18h] BYREF

  Luid = 0;
  NewState = 0;
  PreviousState = 0;
  BufferLength = 16;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
    goto LABEL_2;
  if ( !LookupPrivilegeValueW(0, a2, &Luid) )
    goto LABEL_2;
  NewState.Privileges[0].Luid = Luid;
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Attributes = 0;
  if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &BufferLength) )
    goto LABEL_2;
  v8 = PreviousState.PrivilegeCount ? PreviousState.Privileges[0].Attributes : 0;
  PreviousState.Privileges[0].Luid = Luid;
  PreviousState.PrivilegeCount = 1;
  v9 = a3 ? v8 | 2 : v8 & 0xFFFFFFFD;
  PreviousState.Privileges[0].Attributes = v9;
  if ( AdjustTokenPrivileges(TokenHandle, 0, &PreviousState, BufferLength, 0, 0) )
  {
    v7 = 0;
  }
  else
  {
LABEL_2:
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
  }
  if ( TokenHandle )
    CloseHandle(TokenHandle);
  return v7;
}

```

## disassembly

```asm
0x180048220  mov     [rsp-8+arg_0], rbx
0x180048225  mov     [rsp-8+arg_10], rdi
0x18004822a  push    rbp
0x18004822b  mov     rbp, rsp
0x18004822e  sub     rsp, 70h
0x180048232  mov     rax, cs:__security_cookie
0x180048239  xor     rax, rsp
0x18004823c  mov     [rbp+var_8], rax
0x180048240  xorps   xmm0, xmm0
0x180048243  mov     qword ptr [rbp+Luid.LowPart], 0
0x18004824b  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x18004824f  mov     edi, r8d
0x180048252  mov     rbx, rdx
0x180048255  movups  xmmword ptr [rbp+var_28.PrivilegeCount], xmm0
0x180048259  mov     [rbp+BufferLength], 10h
0x180048260  mov     [rbp+TokenHandle], 0
0x180048268  call    cs:__imp_GetCurrentProcess
0x18004826e  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180048272  mov     edx, 28h ; '('; DesiredAccess
0x180048277  mov     rcx, rax; ProcessHandle
0x18004827a  call    cs:__imp_OpenProcessToken
0x180048280  test    eax, eax
0x180048282  jnz     short loc_1800482A2
0x180048284  call    cs:__imp_GetLastError
0x18004828a  mov     ebx, eax
0x18004828c  test    eax, eax
0x18004828e  jle     loc_18004834D
0x180048294  movzx   ebx, ax
0x180048297  or      ebx, 80070000h
0x18004829d  jmp     loc_18004834D
0x1800482a2  lea     r8, [rbp+Luid]; lpLuid
0x1800482a6  mov     rdx, rbx; lpName
0x1800482a9  xor     ecx, ecx; lpSystemName
0x1800482ab  call    cs:__imp_LookupPrivilegeValueW
0x1800482b1  test    eax, eax
0x1800482b3  jz      short loc_180048284
0x1800482b5  mov     rax, qword ptr [rbp+Luid.LowPart]
0x1800482b9  lea     r8, [rbp+NewState]; NewState
0x1800482bd  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800482c1  mov     ebx, 1
0x1800482c6  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rax
0x1800482ca  xor     edx, edx; DisableAllPrivileges
0x1800482cc  lea     rax, [rbp+BufferLength]
0x1800482d0  mov     [rbp+NewState.PrivilegeCount], ebx
0x1800482d3  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x1800482d8  lea     rax, [rbp+var_28]
0x1800482dc  lea     r9d, [rbx+0Fh]; BufferLength
0x1800482e0  mov     [rsp+70h+PreviousState], rax; PreviousState
0x1800482e5  mov     [rbp+NewState.Privileges.Attributes], 0
0x1800482ec  call    cs:__imp_AdjustTokenPrivileges
0x1800482f2  test    eax, eax
0x1800482f4  jz      short loc_180048284
0x1800482f6  cmp     [rbp+var_28.PrivilegeCount], 0
0x1800482fa  jnz     short loc_180048300
0x1800482fc  xor     ecx, ecx
0x1800482fe  jmp     short loc_180048303
0x180048300  mov     ecx, [rbp+var_28.Privileges.Attributes]
0x180048303  mov     rax, qword ptr [rbp+Luid.LowPart]
0x180048307  mov     qword ptr [rbp+var_28.Privileges.Luid.LowPart], rax
0x18004830b  mov     [rbp+var_28.PrivilegeCount], ebx
0x18004830e  test    edi, edi
0x180048310  jz      short loc_180048317
0x180048312  or      ecx, 2
0x180048315  jmp     short loc_18004831A
0x180048317  and     ecx, 0FFFFFFFDh
0x18004831a  mov     r9d, [rbp+BufferLength]; BufferLength
0x18004831e  lea     r8, [rbp+var_28]; NewState
0x180048322  mov     [rbp+var_28.Privileges.Attributes], ecx
0x180048325  xor     edx, edx; DisableAllPrivileges
0x180048327  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18004832b  mov     [rsp+70h+ReturnLength], 0; ReturnLength
0x180048334  mov     [rsp+70h+PreviousState], 0; PreviousState
0x18004833d  call    cs:__imp_AdjustTokenPrivileges
0x180048343  test    eax, eax
0x180048345  jz      loc_180048284
0x18004834b  xor     ebx, ebx
0x18004834d  mov     rcx, [rbp+TokenHandle]; hObject
0x180048351  test    rcx, rcx
0x180048354  jz      short loc_18004835C
0x180048356  call    cs:__imp_CloseHandle
0x18004835c  mov     eax, ebx
0x18004835e  mov     rcx, [rbp+var_8]
0x180048362  xor     rcx, rsp; StackCookie
0x180048365  call    __security_check_cookie
0x18004836a  lea     r11, [rsp+70h+var_s0]
0x18004836f  mov     rbx, [r11+10h]
0x180048373  mov     rdi, [r11+20h]
0x180048377  mov     rsp, r11
0x18004837a  pop     rbp
0x18004837b  retn
```
