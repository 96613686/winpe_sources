# IsMemberOf(WELL_KNOWN_SID_TYPE,void *,int *)

- ea: `0x180140f60`
- end: `0x180141189`
- name: `?IsMemberOf@@YAJW4WELL_KNOWN_SID_TYPE@@PEAXPEAH@Z`
- size: `553`
- prototype: `__int64 __fastcall(enum WELL_KNOWN_SID_TYPE, void *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180141190`

## callees

- `0x180008290`
- `0x180140cec`
- `0x180140f60`
- `0x180144882`
- `0x1801448c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180140fc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801410b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180140fc6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801410b1`
- `KERNEL32!CloseHandle` at `0x18014115b`
- `KERNEL32!CloseHandle` at `0x18014115b`
- `KERNEL32!GetCurrentThread` at `0x180141116`
- `KERNEL32!GetCurrentThread` at `0x180141116`
- `ADVAPI32!OpenThreadToken` at `0x18014112c`
- `ADVAPI32!OpenThreadToken` at `0x18014112c`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180140fb8`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180140fb8`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1801410a3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180141142`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1801410a3`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180141142`

## pseudocode

```c
__int64 __fastcall IsMemberOf(enum WELL_KNOWN_SID_TYPE a1, void *a2, int *a3)
{
  unsigned int WellKnownSidForAccount; // ebx
  signed int LastError; // eax
  enum WELL_KNOWN_SID_TYPE v6; // edx
  CHostedCacheMsgEncoding *v7; // rcx
  __int64 v8; // rdx
  signed int v9; // eax
  HANDLE CurrentThread; // rax
  WINBOOL IsMember[4]; // [rsp+20h] [rbp-39h] BYREF
  HANDLE TokenHandle; // [rsp+30h] [rbp-29h] BYREF
  DWORD cbSid[4]; // [rsp+40h] [rbp-19h] BYREF
  _BYTE pSid[80]; // [rsp+50h] [rbp-9h] BYREF

  WellKnownSidForAccount = 0;
  TokenHandle = 0;
  IsMember[0] = 0;
  memset_0(pSid, 0, 0x44u);
  cbSid[0] = 68;
  if ( CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, cbSid) )
    goto LABEL_35;
  LastError = GetLastError();
  WellKnownSidForAccount = LastError;
  if ( LastError > 0 )
    WellKnownSidForAccount = (unsigned __int16)LastError | 0x80070000;
  if ( (int)(WellKnownSidForAccount + 0x80000000) >= 0 && WellKnownSidForAccount != -2147024809 )
  {
    v7 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      v8 = 48;
LABEL_10:
      WPP_SF_d(*((_QWORD *)v7 + 12), v8, WPP_b3b735cb11f534e0475daff91a8d2871_Traceguids, WellKnownSidForAccount);
      goto LABEL_32;
    }
    goto LABEL_32;
  }
  WellKnownSidForAccount = CreateWellKnownSidForAccount(TokenHandle, v6, pSid, cbSid);
  if ( WellKnownSidForAccount == -2147023639 )
  {
    WellKnownSidForAccount = 0;
    IsMember[0] = 0;
    goto LABEL_32;
  }
  if ( (WellKnownSidForAccount & 0x80000000) == 0 )
  {
LABEL_35:
    if ( !CheckTokenMembership(TokenHandle, pSid, IsMember) )
    {
      v9 = GetLastError();
      WellKnownSidForAccount = v9;
      if ( v9 > 0 )
        WellKnownSidForAccount = (unsigned __int16)v9 | 0x80070000;
      if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 105) )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 12),
          50,
          WPP_b3b735cb11f534e0475daff91a8d2871_Traceguids,
          WellKnownSidForAccount);
      }
      IsMember[0] = 0;
      if ( WellKnownSidForAccount == -2147024891 && !TokenHandle )
      {
        CurrentThread = GetCurrentThread();
        if ( OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
        {
          if ( CheckTokenMembership(TokenHandle, pSid, IsMember) )
            WellKnownSidForAccount = 0;
          else
            IsMember[0] = 0;
          CloseHandle(TokenHandle);
        }
      }
    }
    goto LABEL_32;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x8000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 105) )
  {
    v8 = 49;
    goto LABEL_10;
  }
LABEL_32:
  *a3 = IsMember[0];
  return WellKnownSidForAccount;
}

```

## disassembly

```asm
0x180140f60  mov     [rsp-8+arg_0], rbx
0x180140f65  mov     [rsp-8+arg_8], rdi
0x180140f6a  push    rbp
0x180140f6b  lea     rbp, [rsp-57h]
0x180140f70  sub     rsp, 0B0h
0x180140f77  mov     rax, cs:__security_cookie
0x180140f7e  xor     rax, rsp
0x180140f81  mov     [rbp+57h+var_10], rax
0x180140f85  xor     ebx, ebx
0x180140f87  mov     [rbp+57h+TokenHandle], 0
0x180140f8f  mov     rdi, r8
0x180140f92  mov     [rbp+57h+IsMember], ebx
0x180140f95  xor     edx, edx; Val
0x180140f97  lea     rcx, [rbp+57h+pSid]; void *
0x180140f9b  lea     r8d, [rbx+44h]; Size
0x180140f9f  call    memset_0
0x180140fa4  lea     r9, [rbp+57h+cbSid]; cbSid
0x180140fa8  mov     [rbp+57h+cbSid], 44h ; 'D'
0x180140faf  lea     r8, [rbp+57h+pSid]; pSid
0x180140fb3  xor     edx, edx; DomainSid
0x180140fb5  lea     ecx, [rbx+1Ah]; WellKnownSidType
0x180140fb8  call    cs:__imp_CreateWellKnownSid
0x180140fbe  test    eax, eax
0x180140fc0  jnz     loc_180141097
0x180140fc6  call    cs:__imp_GetLastError
0x180140fcc  mov     ebx, eax
0x180140fce  test    eax, eax
0x180140fd0  jle     short loc_180140FDB
0x180140fd2  movzx   ebx, ax
0x180140fd5  or      ebx, 80070000h
0x180140fdb  mov     ecx, 80000000h
0x180140fe0  lea     eax, [rbx+rcx]
0x180140fe3  test    ecx, eax
0x180140fe5  jnz     short loc_18014103A
0x180140fe7  cmp     ebx, 80070057h
0x180140fed  jz      short loc_18014103A
0x180140fef  mov     rcx, cs:WPP_GLOBAL_Control
0x180140ff6  lea     rax, WPP_GLOBAL_Control
0x180140ffd  cmp     rcx, rax
0x180141000  jz      loc_180141161
0x180141006  test    dword ptr [rcx+6Ch], 8000h
0x18014100d  jz      loc_180141161
0x180141013  cmp     byte ptr [rcx+69h], 1
0x180141017  jb      loc_180141161
0x18014101d  mov     edx, 30h ; '0'
0x180141022  mov     rcx, [rcx+60h]
0x180141026  lea     r8, WPP_b3b735cb11f534e0475daff91a8d2871_Traceguids
0x18014102d  mov     r9d, ebx
0x180141030  call    WPP_SF_d
0x180141035  jmp     loc_180141161
0x18014103a  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18014103e  lea     r9, [rbp+57h+cbSid]; unsigned int *
0x180141042  lea     r8, [rbp+57h+pSid]; void *
0x180141046  call    ?CreateWellKnownSidForAccount@@YAJPEAXW4WELL_KNOWN_SID_TYPE@@0PEAK@Z; CreateWellKnownSidForAccount(void *,WELL_KNOWN_SID_TYPE,void *,ulong *)
0x18014104b  mov     ebx, eax
0x18014104d  cmp     eax, 800704E9h
0x180141052  jnz     short loc_18014105E
0x180141054  xor     ebx, ebx
0x180141056  mov     [rbp+57h+IsMember], ebx
0x180141059  jmp     loc_180141161
0x18014105e  test    ebx, ebx
0x180141060  jns     short loc_180141097
0x180141062  mov     rcx, cs:WPP_GLOBAL_Control
0x180141069  lea     rax, WPP_GLOBAL_Control
0x180141070  cmp     rcx, rax
0x180141073  jz      loc_180141161
0x180141079  test    dword ptr [rcx+6Ch], 8000h
0x180141080  jz      loc_180141161
0x180141086  cmp     byte ptr [rcx+69h], 1
0x18014108a  jb      loc_180141161
0x180141090  mov     edx, 31h ; '1'
0x180141095  jmp     short loc_180141022
0x180141097  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18014109b  lea     r8, [rbp+57h+IsMember]; IsMember
0x18014109f  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x1801410a3  call    cs:__imp_CheckTokenMembership
0x1801410a9  test    eax, eax
0x1801410ab  jnz     loc_180141161
0x1801410b1  call    cs:__imp_GetLastError
0x1801410b7  mov     ebx, eax
0x1801410b9  test    eax, eax
0x1801410bb  jle     short loc_1801410C6
0x1801410bd  movzx   ebx, ax
0x1801410c0  or      ebx, 80070000h
0x1801410c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1801410cd  lea     rax, WPP_GLOBAL_Control
0x1801410d4  cmp     rcx, rax
0x1801410d7  jz      short loc_180141100
0x1801410d9  test    dword ptr [rcx+6Ch], 8000h
0x1801410e0  jz      short loc_180141100
0x1801410e2  cmp     byte ptr [rcx+69h], 1
0x1801410e6  jb      short loc_180141100
0x1801410e8  mov     rcx, [rcx+60h]
0x1801410ec  lea     r8, WPP_b3b735cb11f534e0475daff91a8d2871_Traceguids
0x1801410f3  mov     edx, 32h ; '2'
0x1801410f8  mov     r9d, ebx
0x1801410fb  call    WPP_SF_d
0x180141100  mov     [rbp+57h+IsMember], 0
0x180141107  cmp     ebx, 80070005h
0x18014110d  jnz     short loc_180141161
0x18014110f  cmp     [rbp+57h+TokenHandle], 0
0x180141114  jnz     short loc_180141161
0x180141116  call    cs:__imp_GetCurrentThread
0x18014111c  mov     edx, 8; DesiredAccess
0x180141121  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x180141125  mov     rcx, rax; ThreadHandle
0x180141128  lea     r8d, [rdx-7]; OpenAsSelf
0x18014112c  call    cs:__imp_OpenThreadToken
0x180141132  test    eax, eax
0x180141134  jz      short loc_180141161
0x180141136  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18014113a  lea     r8, [rbp+57h+IsMember]; IsMember
0x18014113e  lea     rdx, [rbp+57h+pSid]; SidToCheck
0x180141142  call    cs:__imp_CheckTokenMembership
0x180141148  test    eax, eax
0x18014114a  jz      short loc_180141150
0x18014114c  xor     ebx, ebx
0x18014114e  jmp     short loc_180141157
0x180141150  mov     [rbp+57h+IsMember], 0
0x180141157  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x18014115b  call    cs:__imp_CloseHandle
0x180141161  mov     eax, [rbp+57h+IsMember]
0x180141164  mov     [rdi], eax
0x180141166  mov     eax, ebx
0x180141168  mov     rcx, [rbp+57h+var_10]
0x18014116c  xor     rcx, rsp; StackCookie
0x18014116f  call    __security_check_cookie
0x180141174  lea     r11, [rsp+0B0h+var_s0]
0x18014117c  mov     rbx, [r11+10h]
0x180141180  mov     rdi, [r11+18h]
0x180141184  mov     rsp, r11
0x180141187  pop     rbp
0x180141188  retn
```
