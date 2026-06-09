# CommonUtil::UtilAcquirePrivilege(ushort const *)

- ea: `0x1800def88`
- end: `0x1800df08d`
- name: `?UtilAcquirePrivilege@CommonUtil@@YAJPEBG@Z`
- size: `261`
- prototype: `__int64 __fastcall(LPCWSTR lpName, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b6d8`
- `0x18001f110`
- `0x1800d3350`

## callees

- `0x180004710`
- `0x18000e288`
- `0x1800db5b8`
- `0x1800def88`
- `0x1800e1690`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800df009`
- `KERNEL32!CloseHandle` at `0x1800df050`
- `KERNEL32!CloseHandle` at `0x1800df06d`
- `KERNEL32!CloseHandle` at `0x1800df009`
- `KERNEL32!CloseHandle` at `0x1800df050`
- `KERNEL32!CloseHandle` at `0x1800df06d`
- `KERNEL32!GetCurrentProcess` at `0x1800defe0`
- `KERNEL32!GetCurrentProcess` at `0x1800defe0`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800df037`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x1800df037`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800defbc`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x1800defbc`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilAcquirePrivilege(LPCWSTR lpName, const unsigned __int16 *a2)
{
  void **CurrentProcess; // rax
  unsigned int v4; // r9d
  int v5; // ebx
  HANDLE v6; // rbx
  __int64 v7; // rdx
  __int64 v8; // rcx
  int LastFailure; // edi
  HANDLE hObject; // [rsp+30h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+38h] [rbp-20h] BYREF

  hObject = 0;
  NewState = 0;
  if ( !LookupPrivilegeValueW(0, lpName, &NewState.Privileges[0].Luid) )
    return 2147942487LL;
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Attributes = 2;
  CurrentProcess = (void **)GetCurrentProcess();
  v5 = CommonUtil::UtilOpenProcessToken((CommonUtil *)&hObject, CurrentProcess, (void *)0x28, v4);
  if ( v5 < 0 )
  {
    if ( hObject )
      CloseHandle(hObject);
    return (unsigned int)v5;
  }
  v6 = hObject;
  if ( !AdjustTokenPrivileges(hObject, 0, &NewState, 0, 0, 0) )
  {
    LastFailure = HrGetLastFailure(v8, v7);
LABEL_9:
    if ( v6 )
      CloseHandle(v6);
    return (unsigned int)LastFailure;
  }
  LastFailure = HrGetLastError();
  if ( LastFailure < 0 )
    goto LABEL_9;
  if ( v6 )
    CloseHandle(v6);
  return 0;
}

```

## disassembly

```asm
0x1800def88  mov     [rsp+arg_8], rbx
0x1800def8d  push    rdi
0x1800def8e  sub     rsp, 50h
0x1800def92  mov     rax, cs:__security_cookie
0x1800def99  xor     rax, rsp
0x1800def9c  mov     [rsp+58h+var_10], rax
0x1800defa1  xorps   xmm0, xmm0
0x1800defa4  mov     [rsp+58h+hObject], 0
0x1800defad  mov     rdx, rcx; lpName
0x1800defb0  lea     r8, [rsp+58h+NewState.Privileges]; lpLuid
0x1800defb5  xor     ecx, ecx; lpSystemName
0x1800defb7  movups  xmmword ptr [rsp+38h], xmm0
0x1800defbc  call    cs:__imp_LookupPrivilegeValueW
0x1800defc2  test    eax, eax
0x1800defc4  jnz     short loc_1800DEFD0
0x1800defc6  mov     eax, 80070057h
0x1800defcb  jmp     loc_1800DF075
0x1800defd0  mov     [rsp+58h+NewState.PrivilegeCount], 1
0x1800defd8  mov     [rsp+58h+NewState.Privileges.Attributes], 2
0x1800defe0  call    cs:__imp_GetCurrentProcess
0x1800defe6  mov     r8d, 28h ; '('; void *
0x1800defec  lea     rcx, [rsp+58h+hObject]; this
0x1800deff1  mov     rdx, rax; void **
0x1800deff4  call    ?UtilOpenProcessToken@CommonUtil@@YAJPEAPEAXPEAXK@Z; CommonUtil::UtilOpenProcessToken(void * *,void *,ulong)
0x1800deff9  mov     ebx, eax
0x1800deffb  test    eax, eax
0x1800deffd  jns     short loc_1800DF013
0x1800defff  mov     rcx, [rsp+58h+hObject]; hObject
0x1800df004  test    rcx, rcx
0x1800df007  jz      short loc_1800DF00F
0x1800df009  call    cs:__imp_CloseHandle
0x1800df00f  mov     eax, ebx
0x1800df011  jmp     short loc_1800DF075
0x1800df013  mov     rbx, [rsp+58h+hObject]
0x1800df018  lea     r8, [rsp+58h+NewState]; NewState
0x1800df01d  mov     rcx, rbx; TokenHandle
0x1800df020  mov     [rsp+58h+ReturnLength], 0; ReturnLength
0x1800df029  xor     r9d, r9d; BufferLength
0x1800df02c  mov     [rsp+58h+PreviousState], 0; PreviousState
0x1800df035  xor     edx, edx; DisableAllPrivileges
0x1800df037  call    cs:__imp_AdjustTokenPrivileges
0x1800df03d  test    eax, eax
0x1800df03f  jnz     short loc_1800DF05A
0x1800df041  call    HrGetLastFailure
0x1800df046  mov     edi, eax
0x1800df048  test    rbx, rbx
0x1800df04b  jz      short loc_1800DF056
0x1800df04d  mov     rcx, rbx; hObject
0x1800df050  call    cs:__imp_CloseHandle
0x1800df056  mov     eax, edi
0x1800df058  jmp     short loc_1800DF075
0x1800df05a  call    HrGetLastError
0x1800df05f  mov     edi, eax
0x1800df061  test    eax, eax
0x1800df063  js      short loc_1800DF048
0x1800df065  test    rbx, rbx
0x1800df068  jz      short loc_1800DF073
0x1800df06a  mov     rcx, rbx; hObject
0x1800df06d  call    cs:__imp_CloseHandle
0x1800df073  xor     eax, eax
0x1800df075  mov     rcx, [rsp+58h+var_10]
0x1800df07a  xor     rcx, rsp; StackCookie
0x1800df07d  call    __security_check_cookie
0x1800df082  mov     rbx, [rsp+58h+arg_8]
0x1800df087  add     rsp, 50h
0x1800df08b  pop     rdi
0x1800df08c  retn
```
