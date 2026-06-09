# StorageReserveHelper::Internal::AdjustTokenPrivilege::Enable(ushort const *)

- ea: `0x18002702c`
- end: `0x180027296`
- name: `?Enable@AdjustTokenPrivilege@Internal@StorageReserveHelper@@QEAAJPEBG@Z`
- size: `618`
- prototype: `__int64 __fastcall(StorageReserveHelper::Internal::AdjustTokenPrivilege *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180027414`

## callees

- `0x180003870`
- `0x180003c84`
- `0x1800044e0`
- `0x18000a0cc`
- `0x18000a0f4`
- `0x18002702c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800270ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027241`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800270ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027119`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027241`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800270c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800270c1`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800270df`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800270df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800270ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800270ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800270b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800270b9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180027113`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180027178`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180027113`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180027178`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002723b`
- `api-ms-win-security-base-l1-1-0!AdjustTokenPrivileges` at `0x18002723b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18002707b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupPrivilegeValueW` at `0x18002707b`

## string_xrefs

- `0x180027072`: `SeManageVolumePrivilege`

## pseudocode

```c
__int64 __fastcall StorageReserveHelper::Internal::AdjustTokenPrivilege::Enable(
        StorageReserveHelper::Internal::AdjustTokenPrivilege *this,
        const unsigned __int16 *a2)
{
  const char *v3; // r9
  __int64 v4; // rdx
  void **v6; // rdi
  char *v7; // rsi
  DWORD LastError; // ebx
  HANDLE CurrentProcess; // rax
  DWORD LowPart; // r12d
  LONG HighPart; // r15d
  signed int v12; // eax
  signed int v13; // ebx
  _DWORD *v14; // rsi
  const char *v15; // r9
  __int64 v16; // rdx
  int v17; // ebx
  __int64 v18; // rcx
  signed int v19; // eax
  int ReturnLength; // [rsp+20h] [rbp-40h]
  int ReturnLengtha; // [rsp+20h] [rbp-40h]
  DWORD TokenInformationLength; // [rsp+38h] [rbp-28h] BYREF
  _LUID Luid; // [rsp+40h] [rbp-20h] BYREF
  _TOKEN_PRIVILEGES NewState; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  NewState = 0;
  Luid = 0;
  if ( !LookupPrivilegeValueW(0, L"SeManageVolumePrivilege", &Luid) )
  {
    v4 = 107;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.h",
             v3);
  }
  v6 = (void **)((char *)this + 16);
  v7 = (char *)*((_QWORD *)this + 2);
  if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    LastError = GetLastError();
    CloseHandle(v7);
    SetLastError(LastError);
  }
  *v6 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x28u, v6) )
  {
    v4 = 111;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v4,
             (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.h",
             v3);
  }
  LowPart = Luid.LowPart;
  HighPart = Luid.HighPart;
  TokenInformationLength = 0;
  GetTokenInformation(*v6, TokenPrivileges, 0, 0, &TokenInformationLength);
  v12 = GetLastError();
  v13 = v12;
  if ( v12 == 122 )
  {
    v14 = operator new[](TokenInformationLength);
    if ( GetTokenInformation(*v6, TokenPrivileges, v14, TokenInformationLength, &TokenInformationLength) )
    {
      v17 = 0;
      v18 = 0;
      if ( *v14 )
      {
        while ( v14[3 * v18 + 1] != LowPart || v14[3 * v18 + 2] != HighPart )
        {
          v18 = (unsigned int)(v18 + 1);
          if ( (unsigned int)v18 >= *v14 )
            goto LABEL_25;
        }
        if ( (v14[3 * v18 + 3] & 3) != 0 )
          v17 = 1;
      }
LABEL_25:
      operator delete(v14);
      if ( v17 )
        return 0;
      goto LABEL_26;
    }
    v13 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0xA1,
            (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.h",
            v15);
    operator delete(v14);
    goto LABEL_15;
  }
  if ( v12 > 0 )
    v13 = (unsigned __int16)v12 | 0x80070000;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x97,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.h",
      (const char *)(unsigned int)v13,
      ReturnLength);
LABEL_15:
    if ( v13 < 0 )
    {
      v16 = 113;
LABEL_17:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecore\\drivers\\storage\\storsvc\\storagereserve\\storagereserveinternal.h",
        (const char *)(unsigned int)v13,
        ReturnLengtha);
      return (unsigned int)v13;
    }
  }
LABEL_26:
  NewState.PrivilegeCount = 1;
  NewState.Privileges[0].Luid = Luid;
  NewState.Privileges[0].Attributes = 2;
  AdjustTokenPrivileges(*v6, 0, &NewState, 0, 0, 0);
  v19 = GetLastError();
  v13 = v19;
  if ( v19 > 0 )
    v13 = (unsigned __int16)v19 | 0x80070000;
  if ( v13 < 0 )
  {
    v16 = 133;
    goto LABEL_17;
  }
  *(_DWORD *)this = 1;
  *(_LUID *)((char *)this + 4) = Luid;
  return 0;
}

```

## disassembly

```asm
0x18002702c  mov     rax, rsp
0x18002702f  push    rbp
0x180027030  push    rdi
0x180027031  push    r12
0x180027033  push    r14
0x180027035  push    r15
0x180027037  mov     rbp, rsp
0x18002703a  sub     rsp, 60h
0x18002703e  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x180027046  mov     [rax+10h], rbx
0x18002704a  mov     [rax+18h], rsi
0x18002704e  mov     rax, cs:__security_cookie
0x180027055  xor     rax, rsp
0x180027058  mov     [rbp+var_8], rax
0x18002705c  mov     r14, rcx
0x18002705f  xorps   xmm0, xmm0
0x180027062  movups  xmmword ptr [rbp+NewState.PrivilegeCount], xmm0
0x180027066  mov     qword ptr [rbp+Luid.LowPart], 0
0x18002706e  lea     r8, [rbp+Luid]; lpLuid
0x180027072  lea     rdx, Name; "SeManageVolumePrivilege"
0x180027079  xor     ecx, ecx; lpSystemName
0x18002707b  call    cs:__imp_LookupPrivilegeValueW
0x180027081  test    eax, eax
0x180027083  jnz     short loc_18002709D
0x180027085  lea     edx, [rax+6Bh]; void *
0x180027088  lea     r8, aOnecoreDrivers_0; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18002708f  mov     rcx, [rbp+28h]; this
0x180027093  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180027098  jmp     loc_180027271
0x18002709d  lea     rdi, [r14+10h]
0x1800270a1  mov     rsi, [rdi]
0x1800270a4  lea     rax, [rsi-1]
0x1800270a8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800270ac  ja      short loc_1800270C7
0x1800270ae  call    cs:__imp_GetLastError
0x1800270b4  mov     ebx, eax
0x1800270b6  mov     rcx, rsi; hObject
0x1800270b9  call    cs:__imp_CloseHandle
0x1800270bf  mov     ecx, ebx; dwErrCode
0x1800270c1  call    cs:__imp_SetLastError
0x1800270c7  mov     qword ptr [rdi], 0
0x1800270ce  call    cs:__imp_GetCurrentProcess
0x1800270d4  mov     r8, rdi; TokenHandle
0x1800270d7  mov     edx, 28h ; '('; DesiredAccess
0x1800270dc  mov     rcx, rax; ProcessHandle
0x1800270df  call    cs:__imp_OpenProcessToken
0x1800270e5  test    eax, eax
0x1800270e7  jnz     short loc_1800270EE
0x1800270e9  lea     edx, [rax+6Fh]
0x1800270ec  jmp     short loc_180027088
0x1800270ee  mov     r12d, [rbp+Luid.LowPart]
0x1800270f2  mov     r15d, [rbp+Luid.HighPart]
0x1800270f6  mov     [rbp+TokenInformationLength], 0
0x1800270fd  lea     rax, [rbp+TokenInformationLength]
0x180027101  mov     [rsp+60h+ReturnLength], rax; int
0x180027106  xor     r9d, r9d; TokenInformationLength
0x180027109  xor     r8d, r8d; TokenInformation
0x18002710c  lea     edx, [r9+3]; TokenInformationClass
0x180027110  mov     rcx, [rdi]; TokenHandle
0x180027113  call    cs:__imp_GetTokenInformation
0x180027119  call    cs:__imp_GetLastError
0x18002711f  mov     ebx, eax
0x180027121  cmp     eax, 7Ah ; 'z'
0x180027124  jz      short loc_180027155
0x180027126  test    eax, eax
0x180027128  jle     short loc_180027133
0x18002712a  movzx   ebx, ax
0x18002712d  or      ebx, 80070000h
0x180027133  test    ebx, ebx
0x180027135  jns     loc_180027202
0x18002713b  mov     rcx, [rbp+28h]; this
0x18002713f  mov     r9d, ebx; char *
0x180027142  lea     r8, aOnecoreDrivers_0; "onecore\\drivers\\storage\\storsvc\\sto"...
0x180027149  mov     edx, 97h; void *
0x18002714e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027153  jmp     short loc_1800271A2
0x180027155  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x180027158  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002715d  mov     rsi, rax
0x180027160  lea     rax, [rbp+TokenInformationLength]
0x180027164  mov     [rsp+60h+ReturnLength], rax; int
0x180027169  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x18002716d  mov     r8, rsi; TokenInformation
0x180027170  mov     edx, 3; TokenInformationClass
0x180027175  mov     rcx, [rdi]; TokenHandle
0x180027178  call    cs:__imp_GetTokenInformation
0x18002717e  test    eax, eax
0x180027180  jnz     short loc_1800271C5
0x180027182  mov     rcx, [rbp+28h]; this
0x180027186  lea     r8, aOnecoreDrivers_0; "onecore\\drivers\\storage\\storsvc\\sto"...
0x18002718d  mov     edx, 0A1h; void *
0x180027192  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180027197  mov     ebx, eax
0x180027199  mov     rcx, rsi; void *
0x18002719c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800271a1  nop
0x1800271a2  test    ebx, ebx
0x1800271a4  jns     short loc_180027202
0x1800271a6  mov     edx, 71h ; 'q'; void *
0x1800271ab  lea     r8, aOnecoreDrivers_0; "onecore\\drivers\\storage\\storsvc\\sto"...
0x1800271b2  mov     r9d, ebx; char *
0x1800271b5  mov     rcx, [rbp+28h]; this
0x1800271b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800271be  mov     eax, ebx
0x1800271c0  jmp     loc_180027271
0x1800271c5  xor     ebx, ebx
0x1800271c7  xor     ecx, ecx
0x1800271c9  cmp     [rsi], ecx
0x1800271cb  jbe     short loc_1800271F5
0x1800271cd  lea     r8d, [rbx+1]
0x1800271d1  lea     rdx, [rcx+rcx*2]; unsigned __int64
0x1800271d5  cmp     [rsi+rdx*4+4], r12d
0x1800271da  jnz     short loc_1800271E3
0x1800271dc  cmp     [rsi+rdx*4+8], r15d
0x1800271e1  jz      short loc_1800271EC
0x1800271e3  add     ecx, r8d
0x1800271e6  cmp     ecx, [rsi]
0x1800271e8  jb      short loc_1800271D1
0x1800271ea  jmp     short loc_1800271F5
0x1800271ec  test    byte ptr [rsi+rdx*4+0Ch], 3
0x1800271f1  cmovnz  ebx, r8d
0x1800271f5  mov     rcx, rsi; void *
0x1800271f8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800271fd  nop
0x1800271fe  test    ebx, ebx
0x180027200  jnz     short loc_18002726F
0x180027202  mov     esi, 1
0x180027207  mov     [rbp+NewState.PrivilegeCount], esi
0x18002720a  mov     eax, [rbp+Luid.LowPart]
0x18002720d  mov     [rbp+NewState.Privileges.Luid.LowPart], eax
0x180027210  mov     eax, [rbp+Luid.HighPart]
0x180027213  mov     [rbp+NewState.Privileges.Luid.HighPart], eax
0x180027216  mov     [rbp+NewState.Privileges.Attributes], 2
0x18002721d  mov     [rsp+60h+var_38], 0; ReturnLength
0x180027226  mov     [rsp+60h+ReturnLength], 0; PreviousState
0x18002722f  xor     r9d, r9d; BufferLength
0x180027232  lea     r8, [rbp+NewState]; NewState
0x180027236  xor     edx, edx; DisableAllPrivileges
0x180027238  mov     rcx, [rdi]; TokenHandle
0x18002723b  call    cs:__imp_AdjustTokenPrivileges
0x180027241  call    cs:__imp_GetLastError
0x180027247  mov     ebx, eax
0x180027249  test    eax, eax
0x18002724b  jle     short loc_180027256
0x18002724d  movzx   ebx, ax
0x180027250  or      ebx, 80070000h
0x180027256  test    ebx, ebx
0x180027258  jns     short loc_180027264
0x18002725a  mov     edx, 85h
0x18002725f  jmp     loc_1800271AB
0x180027264  mov     [r14], esi
0x180027267  mov     rax, qword ptr [rbp+Luid.LowPart]
0x18002726b  mov     [r14+4], rax
0x18002726f  xor     eax, eax
0x180027271  mov     rcx, [rbp+var_8]
0x180027275  xor     rcx, rsp; StackCookie
0x180027278  call    __security_check_cookie
0x18002727d  lea     r11, [rsp+60h+var_s0]
0x180027282  mov     rbx, [r11+38h]
0x180027286  mov     rsi, [r11+40h]
0x18002728a  mov     rsp, r11
0x18002728d  pop     r15
0x18002728f  pop     r14
0x180027291  pop     r12
0x180027293  pop     rdi
0x180027294  pop     rbp
0x180027295  retn
```
