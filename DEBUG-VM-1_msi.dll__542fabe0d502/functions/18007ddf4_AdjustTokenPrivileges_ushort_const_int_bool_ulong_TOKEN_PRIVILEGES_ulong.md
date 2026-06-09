# AdjustTokenPrivileges(ushort const * *,int,bool,ulong,_TOKEN_PRIVILEGES *,ulong *)

- ea: `0x18007ddf4`
- end: `0x18007df58`
- name: `?AdjustTokenPrivileges@@YA_NPEAPEBGH_NKPEAU_TOKEN_PRIVILEGES@@PEAK@Z`
- size: `356`
- prototype: `bool __fastcall(const unsigned __int16 **, int, bool, unsigned int, PTOKEN_PRIVILEGES NewState, unsigned int *)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18007d8cc`
- `0x18013ae34`
- `0x18014e0d0`
- `0x1801b1940`

## callees

- `0x18007ddf4`
- `0x18025ab80`

## import_xrefs

- `ADVAPI32!OpenThreadToken` at `0x18007de52`
- `ADVAPI32!OpenThreadToken` at `0x18007de52`
- `ADVAPI32!OpenProcessToken` at `0x18007de7c`
- `ADVAPI32!OpenProcessToken` at `0x18007de7c`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18007deb3`
- `ADVAPI32!LookupPrivilegeValueW` at `0x18007deb3`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18007def1`
- `ADVAPI32!AdjustTokenPrivileges` at `0x18007def1`
- `KERNEL32!CloseHandle` at `0x18007defb`
- `KERNEL32!CloseHandle` at `0x18007df4e`
- `KERNEL32!CloseHandle` at `0x18007defb`
- `KERNEL32!CloseHandle` at `0x18007df4e`
- `KERNEL32!GetLastError` at `0x18007de5c`
- `KERNEL32!GetLastError` at `0x18007df01`
- `KERNEL32!GetLastError` at `0x18007de5c`
- `KERNEL32!GetLastError` at `0x18007df01`
- `KERNEL32!GetCurrentThread` at `0x18007de3a`
- `KERNEL32!GetCurrentThread` at `0x18007de3a`
- `KERNEL32!GetCurrentProcess` at `0x18007de6d`
- `KERNEL32!GetCurrentProcess` at `0x18007de6d`

## pseudocode

```c
bool __fastcall AdjustTokenPrivileges(
        const unsigned __int16 **a1,
        signed int a2,
        unsigned __int8 a3,
        DWORD a4,
        PTOKEN_PRIVILEGES NewState,
        unsigned int *ReturnLength)
{
  int v8; // r15d
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  signed int i; // ebx
  void *TokenHandle; // [rsp+30h] [rbp-50h] BYREF
  const unsigned __int16 **v14; // [rsp+38h] [rbp-48h]
  struct _TOKEN_PRIVILEGES v15[3]; // [rsp+40h] [rbp-40h] BYREF

  v8 = a3;
  v14 = a1;
  TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x28u, 1, &TokenHandle) )
  {
    if ( GetLastError() != 1008 )
      return 0;
    CurrentProcess = GetCurrentProcess();
    if ( !OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
      return 0;
  }
  if ( (_BYTE)v8 || !NewState )
  {
    for ( i = 0; ; ++i )
    {
      if ( i >= a2 )
      {
        v15[0].PrivilegeCount = a2;
        AdjustTokenPrivileges(TokenHandle, 0, v15, a4, NewState, ReturnLength);
        goto LABEL_11;
      }
      if ( !LookupPrivilegeValueW(0, v14[i], &v15[0].Privileges[i].Luid) )
        break;
      v15[0].Privileges[i].Attributes = 2 * v8;
    }
    CloseHandle(TokenHandle);
    return 0;
  }
  AdjustTokenPrivileges(TokenHandle, 0, NewState, *ReturnLength, 0, 0);
LABEL_11:
  CloseHandle(TokenHandle);
  return GetLastError() == 0;
}

```

## disassembly

```asm
0x18007ddf4  mov     [rsp-38h+arg_8], rbx
0x18007ddf9  push    rbp
0x18007ddfa  push    rsi
0x18007ddfb  push    rdi
0x18007ddfc  push    r12
0x18007ddfe  push    r13
0x18007de00  push    r14
0x18007de02  push    r15
0x18007de04  mov     rbp, rsp
0x18007de07  sub     rsp, 80h
0x18007de0e  mov     rax, cs:__security_cookie
0x18007de15  xor     rax, rsp
0x18007de18  mov     [rbp+var_10], rax
0x18007de1c  mov     rdi, [rbp+NewState]
0x18007de20  mov     r13d, r9d
0x18007de23  mov     r14, [rbp+arg_28]
0x18007de27  mov     r12d, edx
0x18007de2a  movzx   r15d, r8b
0x18007de2e  mov     [rbp+var_48], rcx
0x18007de32  mov     [rbp+TokenHandle], 0
0x18007de3a  call    cs:__imp_GetCurrentThread
0x18007de40  mov     ebx, 28h ; '('
0x18007de45  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18007de49  mov     rcx, rax; ThreadHandle
0x18007de4c  mov     edx, ebx; DesiredAccess
0x18007de4e  lea     r8d, [rbx-27h]; OpenAsSelf
0x18007de52  call    cs:__imp_OpenThreadToken
0x18007de58  test    eax, eax
0x18007de5a  jnz     short loc_18007DE8A
0x18007de5c  call    cs:__imp_GetLastError
0x18007de62  cmp     eax, 3F0h
0x18007de67  jnz     loc_18007DF54
0x18007de6d  call    cs:__imp_GetCurrentProcess
0x18007de73  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18007de77  mov     edx, ebx; DesiredAccess
0x18007de79  mov     rcx, rax; ProcessHandle
0x18007de7c  call    cs:__imp_OpenProcessToken
0x18007de82  test    eax, eax
0x18007de84  jz      loc_18007DF54
0x18007de8a  test    r15b, r15b
0x18007de8d  jz      short loc_18007DECE
0x18007de8f  xor     ebx, ebx
0x18007de91  cmp     ebx, r12d
0x18007de94  jge     loc_18007DF33
0x18007de9a  mov     rax, [rbp+var_48]
0x18007de9e  lea     r8, [rbp+var_3C]
0x18007dea2  movsxd  rdx, ebx
0x18007dea5  xor     ecx, ecx; lpSystemName
0x18007dea7  lea     rsi, [rdx+rdx*2]
0x18007deab  mov     rdx, [rax+rdx*8]; lpName
0x18007deaf  lea     r8, [r8+rsi*4]; lpLuid
0x18007deb3  call    cs:__imp_LookupPrivilegeValueW
0x18007deb9  test    eax, eax
0x18007debb  jz      loc_18007DF4A
0x18007dec1  mov     eax, r15d
0x18007dec4  add     eax, eax
0x18007dec6  mov     [rbp+rsi*4+var_34], eax
0x18007deca  inc     ebx
0x18007decc  jmp     short loc_18007DE91
0x18007dece  test    rdi, rdi
0x18007ded1  jz      short loc_18007DE8F
0x18007ded3  mov     r9d, [r14]; BufferLength
0x18007ded6  mov     r8, rdi; NewState
0x18007ded9  mov     [rsp+80h+ReturnLength], 0; ReturnLength
0x18007dee2  mov     [rsp+80h+PreviousState], 0; PreviousState
0x18007deeb  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18007deef  xor     edx, edx; DisableAllPrivileges
0x18007def1  call    cs:__imp_AdjustTokenPrivileges
0x18007def7  mov     rcx, [rbp+TokenHandle]; hObject
0x18007defb  call    cs:__imp_CloseHandle
0x18007df01  call    cs:__imp_GetLastError
0x18007df07  test    eax, eax
0x18007df09  setz    al
0x18007df0c  mov     rcx, [rbp+var_10]
0x18007df10  xor     rcx, rsp; StackCookie
0x18007df13  call    __security_check_cookie
0x18007df18  mov     rbx, [rsp+80h+arg_8]
0x18007df20  add     rsp, 80h
0x18007df27  pop     r15
0x18007df29  pop     r14
0x18007df2b  pop     r13
0x18007df2d  pop     r12
0x18007df2f  pop     rdi
0x18007df30  pop     rsi
0x18007df31  pop     rbp
0x18007df32  retn
0x18007df33  mov     [rsp+80h+ReturnLength], r14
0x18007df38  lea     r8, [rbp+var_40]
0x18007df3c  mov     [rsp+80h+PreviousState], rdi
0x18007df41  mov     r9d, r13d
0x18007df44  mov     [rbp+var_40], r12d
0x18007df48  jmp     short loc_18007DEEB
0x18007df4a  mov     rcx, [rbp+TokenHandle]; hObject
0x18007df4e  call    cs:__imp_CloseHandle
0x18007df54  xor     al, al
0x18007df56  jmp     short loc_18007DF0C
```
