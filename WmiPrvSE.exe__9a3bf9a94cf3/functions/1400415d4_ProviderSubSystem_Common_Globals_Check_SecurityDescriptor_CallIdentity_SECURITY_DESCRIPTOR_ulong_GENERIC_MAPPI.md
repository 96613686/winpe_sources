# ProviderSubSystem_Common_Globals::Check_SecurityDescriptor_CallIdentity(_SECURITY_DESCRIPTOR *,ulong,_GENERIC_MAPPING *,_SECURITY_DESCRIPTOR *)

- ea: `0x1400415d4`
- end: `0x1400417c3`
- name: `?Check_SecurityDescriptor_CallIdentity@ProviderSubSystem_Common_Globals@@SAJPEAU_SECURITY_DESCRIPTOR@@KPEAU_GENERIC_MAPPING@@0@Z`
- size: `495`
- prototype: `__int64 __fastcall(struct _SECURITY_DESCRIPTOR *, WINBOOL, struct _GENERIC_MAPPING *, struct _SECURITY_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x140024030`

## callees

- `0x14000a0f0`
- `0x14000a530`
- `0x1400415d4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140041697`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140041697`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x1400416d9`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x1400416d9`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x140041715`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x140041776`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x140041715`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x140041776`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14004166b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14004166b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004161f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041729`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14004161f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140041729`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400416a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400417b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400416a6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400417b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14004164d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x14004164d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140041604`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140041675`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140041604`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140041675`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140041617`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140041688`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140041617`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x140041688`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14004165d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x14004165d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ProviderSubSystem_Common_Globals::Check_SecurityDescriptor_CallIdentity(
        struct _SECURITY_DESCRIPTOR *a1,
        WINBOOL a2,
        struct _GENERIC_MAPPING *a3,
        struct _SECURITY_DESCRIPTOR *a4)
{
  struct _SECURITY_DESCRIPTOR *v4; // rsi
  HANDLE CurrentThread; // rax
  BOOL v6; // edi
  DWORD LastError; // eax
  HANDLE CurrentProcess; // rax
  HANDLE v9; // rax
  unsigned int v10; // ebx
  struct _PRIVILEGE_SET *PrivilegeSet; // rdi
  DWORD AccessMask; // [rsp+40h] [rbp-10h] BYREF
  void *TokenHandle; // [rsp+48h] [rbp-8h] BYREF
  DWORD GrantedAccess; // [rsp+80h] [rbp+30h] BYREF
  WINBOOL AccessStatus; // [rsp+88h] [rbp+38h] BYREF
  HANDLE hToken; // [rsp+90h] [rbp+40h] BYREF

  hToken = a3;
  AccessStatus = a2;
  TokenHandle = 0;
  v4 = a1;
  if ( !a1 )
    v4 = a4;
  AccessMask = 1;
  CurrentThread = GetCurrentThread();
  v6 = OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle);
  LastError = GetLastError();
  if ( (LastError == 1309 || LastError == 1008) && !v6 )
  {
    hToken = 0;
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 0xAu, &hToken) )
    {
      if ( ImpersonateLoggedOnUser(hToken) )
      {
        v9 = GetCurrentThread();
        v10 = !OpenThreadToken(v9, 8u, 1, &TokenHandle) ? 0x80041003 : 0;
        RevertToSelf();
      }
      else
      {
        v10 = -2147217405;
      }
      CloseHandle(hToken);
    }
    else
    {
      v10 = -2147217405;
    }
    if ( (v10 & 0x80000000) != 0 )
      return v10;
  }
  else
  {
    v10 = 0;
    if ( !v6 )
      return (unsigned int)-2147217405;
  }
  GrantedAccess = 0;
  AccessStatus = 0;
  LODWORD(hToken) = 0;
  MapGenericMask(&AccessMask, &g_ProviderBindingMapping);
  if ( !AccessCheck(
          v4,
          TokenHandle,
          AccessMask,
          &g_ProviderBindingMapping,
          0,
          (LPDWORD)&hToken,
          &GrantedAccess,
          &AccessStatus)
    || !AccessStatus )
  {
    if ( GetLastError() == 122 )
    {
      PrivilegeSet = (struct _PRIVILEGE_SET *)operator new((unsigned int)hToken);
      if ( PrivilegeSet )
      {
        if ( !AccessCheck(
                v4,
                TokenHandle,
                AccessMask,
                &g_ProviderBindingMapping,
                PrivilegeSet,
                (LPDWORD)&hToken,
                &GrantedAccess,
                &AccessStatus)
          || !AccessStatus )
        {
          v10 = -2147217405;
        }
        operator delete(PrivilegeSet);
      }
      else
      {
        v10 = -2147217402;
      }
    }
    else
    {
      v10 = -2147217405;
    }
  }
  CloseHandle(TokenHandle);
  return v10;
}

```

## disassembly

```asm
0x1400415d4  mov     [rsp-28h+hToken], r8
0x1400415d9  mov     [rsp-28h+arg_8], edx
0x1400415dd  push    rbp
0x1400415de  push    rbx
0x1400415df  push    rsi
0x1400415e0  push    rdi
0x1400415e1  push    r15
0x1400415e3  mov     rbp, rsp
0x1400415e6  sub     rsp, 50h
0x1400415ea  test    rcx, rcx
0x1400415ed  mov     [rbp+TokenHandle], 0
0x1400415f5  mov     rsi, rcx
0x1400415f8  mov     ebx, 1
0x1400415fd  cmovz   rsi, r9
0x140041601  mov     [rbp+AccessMask], ebx
0x140041604  call    cs:__imp_GetCurrentThread
0x14004160a  lea     r9, [rbp+TokenHandle]; TokenHandle
0x14004160e  mov     r8d, ebx; OpenAsSelf
0x140041611  mov     rcx, rax; ThreadHandle
0x140041614  lea     edx, [rbx+7]; DesiredAccess
0x140041617  call    cs:__imp_OpenThreadToken
0x14004161d  mov     edi, eax
0x14004161f  call    cs:__imp_GetLastError
0x140041625  mov     r15d, 80041003h
0x14004162b  cmp     eax, 51Dh
0x140041630  jz      short loc_14004163D
0x140041632  cmp     eax, 3F0h
0x140041637  jnz     loc_140041793
0x14004163d  test    edi, edi
0x14004163f  jnz     loc_140041793
0x140041645  mov     [rbp+hToken], 0
0x14004164d  call    cs:__imp_GetCurrentProcess
0x140041653  mov     rcx, rax; ProcessHandle
0x140041656  lea     r8, [rbp+hToken]; TokenHandle
0x14004165a  lea     edx, [rdi+0Ah]; DesiredAccess
0x14004165d  call    cs:__imp_OpenProcessToken
0x140041663  test    eax, eax
0x140041665  jz      short loc_1400416AE
0x140041667  mov     rcx, [rbp+hToken]; hToken
0x14004166b  call    cs:__imp_ImpersonateLoggedOnUser
0x140041671  test    eax, eax
0x140041673  jz      short loc_14004169F
0x140041675  call    cs:__imp_GetCurrentThread
0x14004167b  lea     r9, [rbp+TokenHandle]; TokenHandle
0x14004167f  mov     r8d, ebx; OpenAsSelf
0x140041682  mov     rcx, rax; ThreadHandle
0x140041685  lea     edx, [rdi+8]; DesiredAccess
0x140041688  call    cs:__imp_OpenThreadToken
0x14004168e  neg     eax
0x140041690  sbb     ebx, ebx
0x140041692  not     ebx
0x140041694  and     ebx, r15d
0x140041697  call    cs:__imp_RevertToSelf
0x14004169d  jmp     short loc_1400416A2
0x14004169f  mov     ebx, r15d
0x1400416a2  mov     rcx, [rbp+hToken]; hObject
0x1400416a6  call    cs:__imp_CloseHandle
0x1400416ac  jmp     short loc_1400416B1
0x1400416ae  mov     ebx, r15d
0x1400416b1  test    ebx, ebx
0x1400416b3  js      loc_1400417B6
0x1400416b9  lea     rdx, ?g_ProviderBindingMapping@@3U_GENERIC_MAPPING@@A; GenericMapping
0x1400416c0  mov     [rbp+arg_0], 0
0x1400416c7  lea     rcx, [rbp+AccessMask]; AccessMask
0x1400416cb  mov     [rbp+arg_8], 0
0x1400416d2  mov     dword ptr [rbp+hToken], 0
0x1400416d9  call    cs:__imp_MapGenericMask
0x1400416df  mov     r8d, [rbp+AccessMask]; DesiredAccess
0x1400416e3  lea     rax, [rbp+arg_8]
0x1400416e7  mov     rdx, [rbp+TokenHandle]; ClientToken
0x1400416eb  lea     r9, ?g_ProviderBindingMapping@@3U_GENERIC_MAPPING@@A; GenericMapping
0x1400416f2  mov     [rsp+50h+AccessStatus], rax; AccessStatus
0x1400416f7  mov     rcx, rsi; pSecurityDescriptor
0x1400416fa  lea     rax, [rbp+arg_0]
0x1400416fe  mov     [rsp+50h+GrantedAccess], rax; GrantedAccess
0x140041703  lea     rax, [rbp+hToken]
0x140041707  mov     [rsp+50h+PrivilegeSetLength], rax; PrivilegeSetLength
0x14004170c  mov     [rsp+50h+PrivilegeSet], 0; PrivilegeSet
0x140041715  call    cs:__imp_AccessCheck
0x14004171b  test    eax, eax
0x14004171d  jz      short loc_140041729
0x14004171f  cmp     [rbp+arg_8], 0
0x140041723  jnz     loc_1400417AC
0x140041729  call    cs:__imp_GetLastError
0x14004172f  cmp     eax, 7Ah ; 'z'
0x140041732  jnz     short loc_1400417A9
0x140041734  mov     ecx, dword ptr [rbp+hToken]; dwBytes
0x140041737  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14004173c  mov     rdi, rax
0x14004173f  test    rax, rax
0x140041742  jz      short loc_1400417A2
0x140041744  mov     r8d, [rbp+AccessMask]; DesiredAccess
0x140041748  lea     rax, [rbp+arg_8]
0x14004174c  mov     rdx, [rbp+TokenHandle]; ClientToken
0x140041750  lea     r9, ?g_ProviderBindingMapping@@3U_GENERIC_MAPPING@@A; GenericMapping
0x140041757  mov     [rsp+50h+AccessStatus], rax; AccessStatus
0x14004175c  mov     rcx, rsi; pSecurityDescriptor
0x14004175f  lea     rax, [rbp+arg_0]
0x140041763  mov     [rsp+50h+GrantedAccess], rax; GrantedAccess
0x140041768  lea     rax, [rbp+hToken]
0x14004176c  mov     [rsp+50h+PrivilegeSetLength], rax; PrivilegeSetLength
0x140041771  mov     [rsp+50h+PrivilegeSet], rdi; PrivilegeSet
0x140041776  call    cs:__imp_AccessCheck
0x14004177c  test    eax, eax
0x14004177e  jz      short loc_140041786
0x140041780  cmp     [rbp+arg_8], 0
0x140041784  jnz     short loc_140041789
0x140041786  mov     ebx, r15d
0x140041789  mov     rcx, rdi; lpMem
0x14004178c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140041791  jmp     short loc_1400417AC
0x140041793  xor     ebx, ebx
0x140041795  test    edi, edi
0x140041797  jnz     loc_1400416B9
0x14004179d  mov     ebx, r15d
0x1400417a0  jmp     short loc_1400417B6
0x1400417a2  mov     ebx, 80041006h
0x1400417a7  jmp     short loc_1400417AC
0x1400417a9  mov     ebx, r15d
0x1400417ac  mov     rcx, [rbp+TokenHandle]; hObject
0x1400417b0  call    cs:__imp_CloseHandle
0x1400417b6  mov     eax, ebx
0x1400417b8  add     rsp, 50h
0x1400417bc  pop     r15
0x1400417be  pop     rdi
0x1400417bf  pop     rsi
0x1400417c0  pop     rbx
0x1400417c1  pop     rbp
0x1400417c2  retn
```
