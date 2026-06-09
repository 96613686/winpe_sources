# EnablePrivilegesInProcess(_BACKUP_PRIVILEGE_CONTEXT *)

- ea: `0x14000a700`
- end: `0x14000aae2`
- name: `?EnablePrivilegesInProcess@@YAJPEAU_BACKUP_PRIVILEGE_CONTEXT@@@Z`
- size: `994`
- prototype: `__int64 __fastcall(struct _BACKUP_PRIVILEGE_CONTEXT *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140008e04`
- `0x14001d5a4`

## callees

- `0x140004a40`
- `0x140004a68`
- `0x140004ef0`
- `0x140005420`
- `0x140009c08`
- `0x14000a700`
- `0x14003fbb0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a784`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a85c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a99e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000aa3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a784`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a85c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a99e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000aa3b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a8ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000aaa9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a8ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000aaa9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000a768`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14000a768`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14000a77a`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14000a77a`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x14000a813`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x14000a813`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x14000a843`
- `api-ms-win-security-base-l1-1-0!PrivilegeCheck` at `0x14000a843`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14000a994`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x14000a994`

## string_xrefs

- `0x14000a740`: `EnablePrivilegesInProcess`

## pseudocode

```c
__int64 __fastcall EnablePrivilegesInProcess(struct _BACKUP_PRIVILEGE_CONTEXT *a1)
{
  HANDLE CurrentProcess; // rax
  signed int v3; // eax
  unsigned int v4; // ebx
  _QWORD *v5; // rcx
  __int64 v6; // rdx
  __int64 v7; // rbx
  __int64 v8; // rdi
  __int64 v9; // rsi
  signed int v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  signed int v13; // eax
  signed int LastError; // eax
  void *TokenHandle; // [rsp+30h] [rbp-39h] BYREF
  WINBOOL pfResult; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v18[8]; // [rsp+40h] [rbp-29h] BYREF
  int v19; // [rsp+48h] [rbp-21h]
  _DWORD RequiredPrivileges[2]; // [rsp+50h] [rbp-19h] BYREF
  __int128 RequiredPrivileges_8; // [rsp+58h] [rbp-11h] BYREF
  __int64 v22; // [rsp+68h] [rbp-1h]
  int NewState; // [rsp+70h] [rbp+7h] BYREF
  _TOKEN_PRIVILEGES NewState_4; // [rsp+74h] [rbp+Bh]
  __int64 v25; // [rsp+84h] [rbp+1Bh]

  *(_QWORD *)(*(_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + 8LL) = "EnablePrivilegesInProcess";
  CHResultImp::CHResultImp((CHResultImp *)v18);
  TokenHandle = 0;
  *((_DWORD *)a1 + 2) = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 0x28u, &TokenHandle) )
  {
    v22 = 0;
    RequiredPrivileges_8 = 0;
    RequiredPrivileges[0] = 2;
    v7 = 0;
    RequiredPrivileges[1] = 1;
    do
    {
      v8 = 3 * v7;
      v9 = (unsigned int)v7;
      if ( !LookupPrivilegeValueW(
              0,
              (LPCWSTR)(&RequiredPrivilegeNames)[v7],
              (PLUID)((char *)&RequiredPrivileges_8 + 12 * v7)) )
      {
        LastError = GetLastError();
        v4 = LastError;
        if ( LastError > 0 )
          v4 = (unsigned __int16)LastError | 0x80070000;
        if ( (v4 & 0x80000000) == 0 )
          v4 = -2147467259;
        v19 = v4;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_Sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            (unsigned int)&WPP_58242705c75132cdab80b446e38b4c82_Traceguids,
            (unsigned int)(&RequiredPrivilegeNames)[v9],
            v4);
        }
        goto LABEL_55;
      }
      v7 = (unsigned int)(v7 + 1);
      *((_DWORD *)&RequiredPrivileges_8 + v8 + 2) = 0x80000000;
    }
    while ( (unsigned int)v7 < 2 );
    pfResult = 0;
    if ( PrivilegeCheck(TokenHandle, (PPRIVILEGE_SET)RequiredPrivileges, &pfResult) )
    {
      if ( pfResult )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_58242705c75132cdab80b446e38b4c82_Traceguids);
        }
        v19 = 1;
        if ( TokenHandle )
          CloseHandle(TokenHandle);
        v4 = 1;
        goto LABEL_57;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_58242705c75132cdab80b446e38b4c82_Traceguids);
      }
    }
    else
    {
      v10 = GetLastError();
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      if ( v10 >= 0 )
        v10 = -2147467259;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          &WPP_58242705c75132cdab80b446e38b4c82_Traceguids,
          (unsigned int)v10);
      }
    }
    v25 = 0;
    v11 = 0;
    NewState = 2;
    NewState_4 = 0;
    v12 = 0;
    do
    {
      ++v11;
      *(_QWORD *)((char *)&NewState_4.PrivilegeCount + v12 * 12) = *(_QWORD *)((char *)&RequiredPrivileges_8 + v12 * 12);
      NewState_4.Privileges[v12++].Luid.HighPart = 2;
    }
    while ( v11 != 2 );
    if ( AdjustTokenPrivileges(
           TokenHandle,
           0,
           (PTOKEN_PRIVILEGES)&NewState,
           0x1Cu,
           (PTOKEN_PRIVILEGES)((char *)a1 + 12),
           (PDWORD)a1 + 2) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, &WPP_58242705c75132cdab80b446e38b4c82_Traceguids);
      }
      *(_QWORD *)a1 = TokenHandle;
      TokenHandle = 0;
      v19 = 0;
      CHResultImp::~CHResultImp((CHResultImp *)v18);
      return 0;
    }
    v13 = GetLastError();
    v4 = v13;
    if ( v13 > 0 )
      v4 = (unsigned __int16)v13 | 0x80070000;
    v19 = v4;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 16;
      goto LABEL_41;
    }
  }
  else
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    v19 = v4;
    v5 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v6 = 11;
LABEL_41:
      WPP_SF_d(v5[2], v6, &WPP_58242705c75132cdab80b446e38b4c82_Traceguids, v4);
    }
  }
LABEL_55:
  if ( TokenHandle )
    CloseHandle(TokenHandle);
LABEL_57:
  CHResultImp::~CHResultImp((CHResultImp *)v18);
  return v4;
}

```

## disassembly

```asm
0x14000a700  mov     [rsp-8+arg_8], rbx
0x14000a705  mov     [rsp-8+arg_10], rsi
0x14000a70a  push    rbp
0x14000a70b  push    rdi
0x14000a70c  push    r12
0x14000a70e  push    r14
0x14000a710  push    r15
0x14000a712  lea     rbp, [rsp-37h]
0x14000a717  sub     rsp, 0A0h
0x14000a71e  mov     rax, cs:__security_cookie
0x14000a725  xor     rax, rsp
0x14000a728  mov     [rbp+57h+var_30], rax
0x14000a72c  mov     rax, gs:58h
0x14000a735  mov     r15, rcx
0x14000a738  mov     ecx, 8
0x14000a73d  mov     rdx, [rax]
0x14000a740  lea     rax, aEnableprivileg; "EnablePrivilegesInProcess"
0x14000a747  mov     [rcx+rdx], rax
0x14000a74b  lea     rcx, [rbp+57h+var_80]; this
0x14000a74f  call    ??0CHResultImp@@QEAA@XZ; CHResultImp::CHResultImp(void)
0x14000a754  lea     r12, [r15+8]
0x14000a758  mov     [rbp+57h+TokenHandle], 0
0x14000a760  mov     dword ptr [r12], 0
0x14000a768  call    cs:__imp_GetCurrentProcess
0x14000a76e  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x14000a772  mov     edx, 28h ; '('; DesiredAccess
0x14000a777  mov     rcx, rax; ProcessHandle
0x14000a77a  call    cs:__imp_OpenProcessToken
0x14000a780  test    eax, eax
0x14000a782  jnz     short loc_14000A7D8
0x14000a784  call    cs:__imp_GetLastError
0x14000a78a  mov     ebx, eax
0x14000a78c  test    eax, eax
0x14000a78e  jle     short loc_14000A799
0x14000a790  movzx   ebx, ax
0x14000a793  or      ebx, 80070000h
0x14000a799  mov     [rbp+57h+var_78], ebx
0x14000a79c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a7a3  lea     rdi, WPP_GLOBAL_Control
0x14000a7aa  cmp     rcx, rdi
0x14000a7ad  jz      loc_14000AAA0
0x14000a7b3  test    byte ptr [rcx+1Ch], 1
0x14000a7b7  jz      loc_14000AAA0
0x14000a7bd  cmp     byte ptr [rcx+19h], 2
0x14000a7c1  jb      loc_14000AAA0
0x14000a7c7  mov     edx, 0Bh
0x14000a7cc  lea     r8, WPP_58242705c75132cdab80b446e38b4c82_Traceguids
0x14000a7d3  jmp     loc_14000A9DF
0x14000a7d8  xorps   xmm0, xmm0
0x14000a7db  mov     [rbp+57h+var_58], 0
0x14000a7e3  movdqu  xmmword ptr [rbp+57h+RequiredPrivileges.Privilege.Luid.LowPart], xmm0
0x14000a7e8  mov     [rbp+57h+RequiredPrivileges.PrivilegeCount], 2
0x14000a7ef  xor     ebx, ebx
0x14000a7f1  mov     [rbp+57h+RequiredPrivileges.Control], 1
0x14000a7f8  lea     rdi, [rbx+rbx*2]
0x14000a7fc  mov     esi, ebx
0x14000a7fe  lea     r14, ?RequiredPrivilegeNames@@3PAPEBGA; ushort const * near * RequiredPrivilegeNames
0x14000a805  xor     ecx, ecx; lpSystemName
0x14000a807  mov     rdx, [r14+rbx*8]; lpName
0x14000a80b  lea     r8, [rbp+57h+RequiredPrivileges.Privilege]
0x14000a80f  lea     r8, [r8+rdi*4]; lpLuid
0x14000a813  call    cs:__imp_LookupPrivilegeValueW
0x14000a819  test    eax, eax
0x14000a81b  jz      loc_14000AA3B
0x14000a821  inc     ebx
0x14000a823  mov     [rbp+rdi*4+57h+RequiredPrivileges.Privilege.Attributes], 80000000h
0x14000a82b  cmp     ebx, 2
0x14000a82e  jb      short loc_14000A7F8
0x14000a830  mov     rcx, [rbp+57h+TokenHandle]; ClientToken
0x14000a834  lea     r8, [rbp+57h+pfResult]; pfResult
0x14000a838  lea     rdx, [rbp+57h+RequiredPrivileges]; RequiredPrivileges
0x14000a83c  mov     [rbp+57h+pfResult], 0
0x14000a843  call    cs:__imp_PrivilegeCheck
0x14000a849  mov     r14d, 80070000h
0x14000a84f  lea     rsi, WPP_58242705c75132cdab80b446e38b4c82_Traceguids
0x14000a856  mov     bl, 4
0x14000a858  test    eax, eax
0x14000a85a  jnz     short loc_14000A8BA
0x14000a85c  call    cs:__imp_GetLastError
0x14000a862  test    eax, eax
0x14000a864  jle     short loc_14000A86C
0x14000a866  movzx   eax, ax
0x14000a869  or      eax, r14d
0x14000a86c  test    eax, eax
0x14000a86e  mov     ecx, 80004005h
0x14000a873  cmovns  eax, ecx
0x14000a876  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a87d  lea     rdi, WPP_GLOBAL_Control
0x14000a884  cmp     rcx, rdi
0x14000a887  jz      loc_14000A93E
0x14000a88d  test    byte ptr [rcx+1Ch], 1
0x14000a891  jz      loc_14000A93E
0x14000a897  cmp     byte ptr [rcx+19h], 2
0x14000a89b  jb      loc_14000A93E
0x14000a8a1  mov     rcx, [rcx+10h]
0x14000a8a5  mov     edx, 0Dh
0x14000a8aa  mov     r9d, eax
0x14000a8ad  mov     r8, rsi
0x14000a8b0  call    WPP_SF_d
0x14000a8b5  jmp     loc_14000A93E
0x14000a8ba  cmp     [rbp+57h+pfResult], 0
0x14000a8be  jz      short loc_14000A90F
0x14000a8c0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a8c7  lea     rdi, WPP_GLOBAL_Control
0x14000a8ce  cmp     rcx, rdi
0x14000a8d1  jz      short loc_14000A8EF
0x14000a8d3  test    byte ptr [rcx+1Ch], 1
0x14000a8d7  jz      short loc_14000A8EF
0x14000a8d9  cmp     [rcx+19h], bl
0x14000a8dc  jb      short loc_14000A8EF
0x14000a8de  mov     rcx, [rcx+10h]
0x14000a8e2  mov     edx, 0Eh
0x14000a8e7  mov     r8, rsi
0x14000a8ea  call    WPP_SF_
0x14000a8ef  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x14000a8f3  mov     [rbp+57h+var_78], 1
0x14000a8fa  test    rcx, rcx
0x14000a8fd  jz      short loc_14000A905
0x14000a8ff  call    cs:__imp_CloseHandle
0x14000a905  mov     ebx, 1
0x14000a90a  jmp     loc_14000AAAF
0x14000a90f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a916  lea     rdi, WPP_GLOBAL_Control
0x14000a91d  cmp     rcx, rdi
0x14000a920  jz      short loc_14000A93E
0x14000a922  test    byte ptr [rcx+1Ch], 1
0x14000a926  jz      short loc_14000A93E
0x14000a928  cmp     [rcx+19h], bl
0x14000a92b  jb      short loc_14000A93E
0x14000a92d  mov     rcx, [rcx+10h]
0x14000a931  mov     edx, 0Fh
0x14000a936  mov     r8, rsi
0x14000a939  call    WPP_SF_
0x14000a93e  xorps   xmm0, xmm0
0x14000a941  mov     [rbp+57h+var_3C], 0
0x14000a949  xor     edx, edx
0x14000a94b  mov     [rbp+57h+NewState.PrivilegeCount], 2
0x14000a952  movdqu  xmmword ptr [rbp+57h+NewState.Privileges.Luid.LowPart], xmm0
0x14000a957  xor     ecx, ecx
0x14000a959  mov     rax, qword ptr [rbp+rcx+57h+RequiredPrivileges.Privilege.Luid.LowPart]
0x14000a95e  inc     rdx
0x14000a961  mov     qword ptr [rbp+rcx+57h+NewState.Privileges.Luid.LowPart], rax
0x14000a966  mov     [rbp+rcx+57h+NewState.Privileges.Attributes], 2
0x14000a96e  lea     rcx, [rcx+0Ch]
0x14000a972  cmp     rdx, 2
0x14000a976  jnz     short loc_14000A959
0x14000a978  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x14000a97c  lea     rax, [r15+0Ch]
0x14000a980  lea     r9d, [rdx+1Ah]; BufferLength
0x14000a984  mov     [rsp+0C0h+ReturnLength], r12; ReturnLength
0x14000a989  xor     edx, edx; DisableAllPrivileges
0x14000a98b  mov     [rsp+0C0h+PreviousState], rax; PreviousState
0x14000a990  lea     r8, [rbp+57h+NewState]; NewState
0x14000a994  call    cs:__imp_AdjustTokenPrivileges
0x14000a99a  test    eax, eax
0x14000a99c  jnz     short loc_14000A9F0
0x14000a99e  call    cs:__imp_GetLastError
0x14000a9a4  mov     ebx, eax
0x14000a9a6  test    eax, eax
0x14000a9a8  jle     short loc_14000A9B0
0x14000a9aa  movzx   ebx, ax
0x14000a9ad  or      ebx, r14d
0x14000a9b0  mov     [rbp+57h+var_78], ebx
0x14000a9b3  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a9ba  cmp     rcx, rdi
0x14000a9bd  jz      loc_14000AAA0
0x14000a9c3  test    byte ptr [rcx+1Ch], 1
0x14000a9c7  jz      loc_14000AAA0
0x14000a9cd  cmp     byte ptr [rcx+19h], 2
0x14000a9d1  jb      loc_14000AAA0
0x14000a9d7  mov     edx, 10h
0x14000a9dc  mov     r8, rsi
0x14000a9df  mov     rcx, [rcx+10h]
0x14000a9e3  mov     r9d, ebx
0x14000a9e6  call    WPP_SF_d
0x14000a9eb  jmp     loc_14000AAA0
0x14000a9f0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000a9f7  cmp     rcx, rdi
0x14000a9fa  jz      short loc_14000AA18
0x14000a9fc  test    byte ptr [rcx+1Ch], 1
0x14000aa00  jz      short loc_14000AA18
0x14000aa02  cmp     [rcx+19h], bl
0x14000aa05  jb      short loc_14000AA18
0x14000aa07  mov     rcx, [rcx+10h]
0x14000aa0b  mov     edx, 11h
0x14000aa10  mov     r8, rsi
0x14000aa13  call    WPP_SF_
0x14000aa18  mov     rax, [rbp+57h+TokenHandle]
0x14000aa1c  lea     rcx, [rbp+57h+var_80]; this
0x14000aa20  mov     [r15], rax
0x14000aa23  mov     [rbp+57h+TokenHandle], 0
0x14000aa2b  mov     [rbp+57h+var_78], 0
0x14000aa32  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x14000aa37  xor     eax, eax
0x14000aa39  jmp     short loc_14000AABA
0x14000aa3b  call    cs:__imp_GetLastError
0x14000aa41  mov     ebx, eax
0x14000aa43  test    eax, eax
0x14000aa45  jle     short loc_14000AA57
0x14000aa47  movzx   ebx, ax
0x14000aa4a  lea     r14, ?RequiredPrivilegeNames@@3PAPEBGA; ushort const * near * RequiredPrivilegeNames
0x14000aa51  or      ebx, 80070000h
0x14000aa57  test    ebx, ebx
0x14000aa59  mov     ecx, 80004005h
0x14000aa5e  cmovns  ebx, ecx
0x14000aa61  mov     [rbp+57h+var_78], ebx
0x14000aa64  mov     rcx, cs:WPP_GLOBAL_Control
0x14000aa6b  lea     rdi, WPP_GLOBAL_Control
0x14000aa72  cmp     rcx, rdi
0x14000aa75  jz      short loc_14000AAA0
0x14000aa77  test    byte ptr [rcx+1Ch], 1
0x14000aa7b  jz      short loc_14000AAA0
0x14000aa7d  cmp     byte ptr [rcx+19h], 2
0x14000aa81  jb      short loc_14000AAA0
0x14000aa83  mov     r9, [r14+rsi*8]
0x14000aa87  lea     r8, WPP_58242705c75132cdab80b446e38b4c82_Traceguids
0x14000aa8e  mov     rcx, [rcx+10h]
0x14000aa92  mov     edx, 0Ch
0x14000aa97  mov     dword ptr [rsp+0C0h+PreviousState], ebx
0x14000aa9b  call    WPP_SF_Sd
0x14000aaa0  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x14000aaa4  test    rcx, rcx
0x14000aaa7  jz      short loc_14000AAAF
0x14000aaa9  call    cs:__imp_CloseHandle
0x14000aaaf  lea     rcx, [rbp+57h+var_80]; this
0x14000aab3  call    ??1CHResultImp@@QEAA@XZ; CHResultImp::~CHResultImp(void)
0x14000aab8  mov     eax, ebx
0x14000aaba  mov     rcx, [rbp+57h+var_30]
0x14000aabe  xor     rcx, rsp; StackCookie
0x14000aac1  call    __security_check_cookie
0x14000aac6  lea     r11, [rsp+0C0h+var_20]
0x14000aace  mov     rbx, [r11+38h]
0x14000aad2  mov     rsi, [r11+40h]
0x14000aad6  mov     rsp, r11
0x14000aad9  pop     r15
0x14000aadb  pop     r14
0x14000aadd  pop     r12
0x14000aadf  pop     rdi
0x14000aae0  pop     rbp
0x14000aae1  retn
```
