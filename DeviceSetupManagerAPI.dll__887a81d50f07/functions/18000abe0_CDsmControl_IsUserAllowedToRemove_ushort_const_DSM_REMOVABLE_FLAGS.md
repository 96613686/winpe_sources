# CDsmControl::IsUserAllowedToRemove(ushort const *,DSM_REMOVABLE_FLAGS *)

- ea: `0x18000abe0`
- end: `0x18000accf`
- name: `?IsUserAllowedToRemove@CDsmControl@@UEAAJPEBGPEAW4DSM_REMOVABLE_FLAGS@@@Z`
- size: `239`
- prototype: `__int64 __fastcall(CDsmControl *this, const unsigned __int16 *, enum DSM_REMOVABLE_FLAGS *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800017c0`
- `0x180009d20`
- `0x18000a934`
- `0x18000abe0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac6f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ac28`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000ac28`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000ac3b`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000ac3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ac45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ac45`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac67`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac67`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000ac13`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18000ac13`

## pseudocode

```c
__int64 __fastcall CDsmControl::IsUserAllowedToRemove(
        CDsmControl *this,
        const unsigned __int16 *a2,
        enum DSM_REMOVABLE_FLAGS *a3)
{
  int v4; // ebx
  HANDLE CurrentProcess; // rax
  DWORD CurrentProcessId; // eax
  signed int LastError; // eax
  void *TokenHandle; // [rsp+20h] [rbp-28h] BYREF
  GUID pclsid; // [rsp+28h] [rbp-20h] BYREF

  *(_DWORD *)a3 = 0;
  pclsid = 0;
  v4 = CLSIDFromString(a2, &pclsid);
  if ( v4 >= 0 )
  {
    TokenHandle = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 2u, &TokenHandle) )
    {
      CurrentProcessId = GetCurrentProcessId();
      v4 = CDsmAccessCheck::IsUserAllowedToRemove(&pclsid, TokenHandle, CurrentProcessId, a3);
      CloseHandle(TokenHandle);
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      &WPP_6c51682e99e93bfa9299cbf564496992_Traceguids,
      (unsigned int)v4);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000abe0  mov     [rsp+arg_0], rbx
0x18000abe5  push    rdi
0x18000abe6  sub     rsp, 40h
0x18000abea  mov     rax, cs:__security_cookie
0x18000abf1  xor     rax, rsp
0x18000abf4  mov     [rsp+48h+var_10], rax
0x18000abf9  mov     rcx, rdx; lpsz
0x18000abfc  mov     dword ptr [r8], 0
0x18000ac03  xorps   xmm0, xmm0
0x18000ac06  lea     rdx, [rsp+48h+pclsid]; pclsid
0x18000ac0b  movups  xmmword ptr [rsp+48h+pclsid.Data1], xmm0
0x18000ac10  mov     rdi, r8
0x18000ac13  call    cs:__imp_CLSIDFromString
0x18000ac19  mov     ebx, eax
0x18000ac1b  test    eax, eax
0x18000ac1d  js      short loc_18000AC84
0x18000ac1f  mov     [rsp+48h+TokenHandle], 0
0x18000ac28  call    cs:__imp_GetCurrentProcess
0x18000ac2e  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x18000ac33  mov     edx, 2; DesiredAccess
0x18000ac38  mov     rcx, rax; ProcessHandle
0x18000ac3b  call    cs:__imp_OpenProcessToken
0x18000ac41  test    eax, eax
0x18000ac43  jz      short loc_18000AC6F
0x18000ac45  call    cs:__imp_GetCurrentProcessId
0x18000ac4b  mov     rdx, [rsp+48h+TokenHandle]; void *
0x18000ac50  lea     rcx, [rsp+48h+pclsid]; struct _GUID *
0x18000ac55  mov     r8d, eax; dwProcessId
0x18000ac58  mov     r9, rdi; enum DSM_REMOVABLE_FLAGS *
0x18000ac5b  call    ?IsUserAllowedToRemove@CDsmAccessCheck@@SAJAEBU_GUID@@PEAXKPEAW4DSM_REMOVABLE_FLAGS@@@Z; CDsmAccessCheck::IsUserAllowedToRemove(_GUID const &,void *,ulong,DSM_REMOVABLE_FLAGS *)
0x18000ac60  mov     rcx, [rsp+48h+TokenHandle]; hObject
0x18000ac65  mov     ebx, eax
0x18000ac67  call    cs:__imp_CloseHandle
0x18000ac6d  jmp     short loc_18000AC84
0x18000ac6f  call    cs:__imp_GetLastError
0x18000ac75  mov     ebx, eax
0x18000ac77  test    eax, eax
0x18000ac79  jle     short loc_18000AC84
0x18000ac7b  movzx   ebx, ax
0x18000ac7e  or      ebx, 80070000h
0x18000ac84  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac8b  lea     rax, WPP_GLOBAL_Control
0x18000ac92  cmp     rcx, rax
0x18000ac95  jz      short loc_18000ACB5
0x18000ac97  test    byte ptr [rcx+1Ch], 1
0x18000ac9b  jz      short loc_18000ACB5
0x18000ac9d  mov     rcx, [rcx+10h]
0x18000aca1  lea     r8, WPP_6c51682e99e93bfa9299cbf564496992_Traceguids
0x18000aca8  mov     edx, 0Dh
0x18000acad  mov     r9d, ebx
0x18000acb0  call    WPP_SF_D
0x18000acb5  mov     eax, ebx
0x18000acb7  mov     rcx, [rsp+48h+var_10]
0x18000acbc  xor     rcx, rsp; StackCookie
0x18000acbf  call    __security_check_cookie
0x18000acc4  mov     rbx, [rsp+48h+arg_0]
0x18000acc9  add     rsp, 40h
0x18000accd  pop     rdi
0x18000acce  retn
```
