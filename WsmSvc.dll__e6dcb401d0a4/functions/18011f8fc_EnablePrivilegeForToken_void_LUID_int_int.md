# EnablePrivilegeForToken(void *,_LUID,int,int *)

- ea: `0x18011f8fc`
- end: `0x18011faa7`
- name: `?EnablePrivilegeForToken@@YAHPEAXU_LUID@@HPEAH@Z`
- size: `427`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, struct _LUID, int, int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18011f860`
- `0x18011fab0`

## callees

- `0x180005d10`
- `0x1801123a8`
- `0x18011f8fc`
- `0x1801ba1b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011fa35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011fa5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011fa90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011fa35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011fa5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011fa90`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18011f9b7`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18011fa07`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18011f9b7`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18011fa07`

## pseudocode

```c
__int64 __fastcall EnablePrivilegeForToken(HANDLE TokenHandle, LUID a2, int a3, DWORD *a4)
{
  const unsigned __int16 *v8; // r8
  __int64 v9; // rdx
  DWORD Attributes; // ecx
  DWORD v12; // ecx
  DWORD LastError; // eax
  __int64 v14; // rdx
  DWORD BufferLength; // [rsp+30h] [rbp-30h] BYREF
  struct _TOKEN_PRIVILEGES PreviousState; // [rsp+38h] [rbp-28h] BYREF
  struct _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-18h] BYREF

  if ( !TokenHandle )
  {
    v8 = L"1965";
    v9 = 1965;
LABEL_3:
    WSManError((wchar_t *)L"onecore\\admin\\wmi\\wmx\\stdlib\\wsmanutils.cpp", v9, v8, 0x54Fu, 0);
    return 0;
  }
  if ( !a4 )
  {
    v8 = L"1966";
    v9 = 1966;
    goto LABEL_3;
  }
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Luid = a2;
  NewState.Privileges[0].Attributes = 0;
  BufferLength = 16;
  PreviousState = 0;
  if ( !AdjustTokenPrivileges(TokenHandle, 0, &NewState, 0x10u, &PreviousState, &BufferLength) )
    return 0;
  Attributes = PreviousState.Privileges[0].Attributes;
  PreviousState.PrivilegeCount = 1;
  PreviousState.Privileges[0].Luid = a2;
  *a4 = (PreviousState.Privileges[0].Attributes >> 1) & 1;
  if ( a3 )
    v12 = Attributes | 2;
  else
    v12 = Attributes & 0xFFFFFFFD;
  PreviousState.Privileges[0].Attributes = v12;
  if ( !AdjustTokenPrivileges(TokenHandle, 0, &PreviousState, BufferLength, 0, 0) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
      return 0;
    LastError = GetLastError();
    v14 = 42;
    goto LABEL_15;
  }
  if ( GetLastError() == 1300 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) == 0 )
      return 0;
    LastError = GetLastError();
    v14 = 43;
LABEL_15:
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids, LastError);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18011f8fc  push    rbp
0x18011f8fe  push    rbx
0x18011f8ff  push    rsi
0x18011f900  push    rdi
0x18011f901  push    r14
0x18011f903  mov     rbp, rsp
0x18011f906  sub     rsp, 60h
0x18011f90a  mov     rax, cs:__security_cookie
0x18011f911  xor     rax, rsp
0x18011f914  mov     [rbp+var_8], rax
0x18011f918  mov     rdi, r9
0x18011f91b  mov     r14d, r8d
0x18011f91e  mov     rbx, rdx
0x18011f921  mov     rsi, rcx
0x18011f924  test    rcx, rcx
0x18011f927  jnz     short loc_18011F969
0x18011f929  lea     r8, a1965; "1965"
0x18011f930  mov     edx, 7ADh; unsigned int
0x18011f935  mov     r9d, 54Fh; unsigned int
0x18011f93b  mov     [rsp+60h+PreviousState], 0; struct IRequestContext *
0x18011f944  lea     rcx, aOnecoreAdminWm_90; "onecore\\admin\\wmi\\wmx\\stdlib\\wsman"...
0x18011f94b  call    ?WSManError@@YAXPEBGK0KPEAVIRequestContext@@@Z; WSManError(ushort const *,ulong,ushort const *,ulong,IRequestContext *)
0x18011f950  xor     eax, eax
0x18011f952  mov     rcx, [rbp+var_8]
0x18011f956  xor     rcx, rsp; StackCookie
0x18011f959  call    __security_check_cookie
0x18011f95e  add     rsp, 60h
0x18011f962  pop     r14
0x18011f964  pop     rdi
0x18011f965  pop     rsi
0x18011f966  pop     rbx
0x18011f967  pop     rbp
0x18011f968  retn
0x18011f969  test    rdi, rdi
0x18011f96c  jnz     short loc_18011F97C
0x18011f96e  lea     r8, a1966; "1966"
0x18011f975  mov     edx, 7AEh
0x18011f97a  jmp     short loc_18011F935
0x18011f97c  lea     rax, [rbp+BufferLength]
0x18011f980  mov     [rbp+NewState.PrivilegeCount], 1
0x18011f987  mov     [rsp+60h+ReturnLength], rax; ReturnLength
0x18011f98c  lea     r8, [rbp+NewState]; NewState
0x18011f990  lea     rax, [rbp+var_28]
0x18011f994  mov     qword ptr [rbp+NewState.Privileges.Luid.LowPart], rbx
0x18011f998  xorps   xmm0, xmm0
0x18011f99b  mov     [rsp+60h+PreviousState], rax; PreviousState
0x18011f9a0  mov     r9d, 10h; BufferLength
0x18011f9a6  mov     [rbp+NewState.Privileges.Attributes], 0
0x18011f9ad  xor     edx, edx; DisableAllPrivileges
0x18011f9af  mov     [rbp+BufferLength], r9d
0x18011f9b3  movups  xmmword ptr [rbp+var_28.PrivilegeCount], xmm0
0x18011f9b7  call    cs:__imp_AdjustTokenPrivileges
0x18011f9bd  test    eax, eax
0x18011f9bf  jz      short loc_18011F950
0x18011f9c1  mov     ecx, [rbp+var_28.Privileges.Attributes]
0x18011f9c4  mov     eax, ecx
0x18011f9c6  shr     eax, 1
0x18011f9c8  and     eax, 1
0x18011f9cb  mov     [rbp+var_28.PrivilegeCount], 1
0x18011f9d2  mov     qword ptr [rbp+var_28.Privileges.Luid.LowPart], rbx
0x18011f9d6  mov     [rdi], eax
0x18011f9d8  test    r14d, r14d
0x18011f9db  jz      short loc_18011F9E2
0x18011f9dd  or      ecx, 2
0x18011f9e0  jmp     short loc_18011F9E5
0x18011f9e2  and     ecx, 0FFFFFFFDh
0x18011f9e5  mov     r9d, [rbp+BufferLength]; BufferLength
0x18011f9e9  lea     r8, [rbp+var_28]; NewState
0x18011f9ed  mov     [rbp+var_28.Privileges.Attributes], ecx
0x18011f9f0  xor     edx, edx; DisableAllPrivileges
0x18011f9f2  mov     rcx, rsi; TokenHandle
0x18011f9f5  mov     [rsp+60h+ReturnLength], 0; ReturnLength
0x18011f9fe  mov     [rsp+60h+PreviousState], 0; PreviousState
0x18011fa07  call    cs:__imp_AdjustTokenPrivileges
0x18011fa0d  test    eax, eax
0x18011fa0f  jnz     short loc_18011FA5F
0x18011fa11  mov     rcx, cs:WPP_GLOBAL_Control
0x18011fa18  lea     rax, WPP_GLOBAL_Control
0x18011fa1f  cmp     rcx, rax
0x18011fa22  jz      loc_18011F950
0x18011fa28  test    dword ptr [rcx+1Ch], 800h
0x18011fa2f  jz      loc_18011F950
0x18011fa35  call    cs:__imp_GetLastError
0x18011fa3b  mov     edx, 2Ah ; '*'
0x18011fa40  mov     rcx, cs:WPP_GLOBAL_Control
0x18011fa47  lea     r8, WPP_06af4c8933ac363c12ded1360bf8d182_Traceguids
0x18011fa4e  mov     r9d, eax
0x18011fa51  mov     rcx, [rcx+10h]
0x18011fa55  call    WPP_SF_d
0x18011fa5a  jmp     loc_18011F950
0x18011fa5f  call    cs:__imp_GetLastError
0x18011fa65  cmp     eax, 514h
0x18011fa6a  jnz     short loc_18011FA9D
0x18011fa6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18011fa73  lea     rax, WPP_GLOBAL_Control
0x18011fa7a  cmp     rcx, rax
0x18011fa7d  jz      loc_18011F950
0x18011fa83  test    dword ptr [rcx+1Ch], 800h
0x18011fa8a  jz      loc_18011F950
0x18011fa90  call    cs:__imp_GetLastError
0x18011fa96  mov     edx, 2Bh ; '+'
0x18011fa9b  jmp     short loc_18011FA40
0x18011fa9d  mov     eax, 1
0x18011faa2  jmp     loc_18011F952
```
