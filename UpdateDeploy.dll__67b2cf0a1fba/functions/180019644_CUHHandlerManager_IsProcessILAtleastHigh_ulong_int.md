# CUHHandlerManager::IsProcessILAtleastHigh(ulong,int *)

- ea: `0x180019644`
- end: `0x1800197f4`
- name: `?IsProcessILAtleastHigh@CUHHandlerManager@@QEAAJKPEAH@Z`
- size: `432`
- prototype: `__int64 __fastcall(CUHHandlerManager *this, DWORD, int *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180017850`

## callees

- `0x180002214`
- `0x180003180`
- `0x18000dc6c`
- `0x18000dce4`
- `0x180019644`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800196c0`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x1800196c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019701`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019701`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800196ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800197bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800197d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800196ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800197bd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800197d3`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001968d`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001968d`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180019796`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthority` at `0x180019796`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800196eb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001975b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800196eb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001975b`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180019786`
- `api-ms-win-security-base-l1-1-0!GetSidSubAuthorityCount` at `0x180019786`

## string_xrefs

- `0x180019731`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x18001976e`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CUHHandlerManager::IsProcessILAtleastHigh(CUHHandlerManager *this, DWORD a2, int *a3)
{
  HANDLE v3; // rbx
  PSID *v4; // rdi
  unsigned int LastError; // esi
  __int64 v7; // rdx
  const char *v8; // r9
  __int64 v9; // rdx
  PUCHAR SidSubAuthorityCount; // rax
  int ReturnLength; // [rsp+20h] [rbp-30h]
  DWORD TokenInformationLength; // [rsp+38h] [rbp-18h] BYREF
  HANDLE hObject; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  v3 = 0;
  v4 = 0;
  hObject = 0;
  TokenInformationLength = 0;
  if ( !a3 )
  {
    LastError = -2147467261;
    v7 = 1240;
LABEL_13:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
      (const char *)LastError,
      ReturnLength);
    goto LABEL_17;
  }
  v3 = OpenProcess(0x400u, 0, a2);
  if ( !v3 )
  {
    v9 = 1244;
LABEL_16:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v9,
                  (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
                  v8);
LABEL_17:
    if ( !v4 )
      goto LABEL_23;
    goto LABEL_22;
  }
  if ( !OpenProcessToken(v3, 0x18u, &hObject) )
  {
    v9 = 1246;
    goto LABEL_16;
  }
  if ( GetTokenInformation(hObject, TokenIntegrityLevel, 0, 0, &TokenInformationLength) )
  {
    LastError = -2145120257;
    v7 = 1247;
    goto LABEL_13;
  }
  if ( GetLastError() != 122 )
  {
    v9 = 1248;
    goto LABEL_16;
  }
  v4 = (PSID *)SusAlloc(TokenInformationLength);
  if ( !v4 )
  {
    LastError = -2147024882;
    v7 = 1251;
    goto LABEL_13;
  }
  if ( !GetTokenInformation(hObject, TokenIntegrityLevel, v4, TokenInformationLength, &TokenInformationLength) )
  {
    v9 = 1254;
    goto LABEL_16;
  }
  SidSubAuthorityCount = GetSidSubAuthorityCount(*v4);
  if ( *GetSidSubAuthority(*v4, (unsigned __int8)(*SidSubAuthorityCount - 1)) >= 0x3000 )
    *a3 = 1;
  LastError = 0;
LABEL_22:
  SusFree(v4);
LABEL_23:
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( v3 )
    CloseHandle(v3);
  return LastError;
}

```

## disassembly

```asm
0x180019644  mov     [rsp-18h+arg_0], rbx
0x180019649  push    rbp
0x18001964a  push    rsi
0x18001964b  push    rdi
0x18001964c  mov     rbp, rsp
0x18001964f  sub     rsp, 50h
0x180019653  mov     rax, cs:__security_cookie
0x18001965a  xor     rax, rsp
0x18001965d  mov     [rbp+var_8], rax
0x180019661  xor     ebx, ebx
0x180019663  xor     edi, edi
0x180019665  mov     [rbp+hObject], rbx
0x180019669  mov     rsi, r8
0x18001966c  mov     [rbp+TokenInformationLength], ebx
0x18001966f  test    r8, r8
0x180019672  jnz     short loc_180019683
0x180019674  mov     esi, 80004003h
0x180019679  mov     edx, 4D8h
0x18001967e  jmp     loc_18001972D
0x180019683  mov     r8d, edx; dwProcessId
0x180019686  mov     ecx, 400h; dwDesiredAccess
0x18001968b  xor     edx, edx; bInheritHandle
0x18001968d  call    cs:__imp_OpenProcess
0x180019693  mov     rbx, rax
0x180019696  test    rax, rax
0x180019699  jnz     short loc_1800196A5
0x18001969b  mov     edx, 4DCh
0x1800196a0  jmp     loc_18001976A
0x1800196a5  mov     rcx, [rbp+hObject]; hObject
0x1800196a9  test    rcx, rcx
0x1800196ac  jz      short loc_1800196B4
0x1800196ae  call    cs:__imp_CloseHandle
0x1800196b4  lea     r8, [rbp+hObject]; TokenHandle
0x1800196b8  mov     edx, 18h; DesiredAccess
0x1800196bd  mov     rcx, rbx; ProcessHandle
0x1800196c0  call    cs:__imp_OpenProcessToken
0x1800196c6  test    eax, eax
0x1800196c8  jnz     short loc_1800196D4
0x1800196ca  mov     edx, 4DEh
0x1800196cf  jmp     loc_18001976A
0x1800196d4  mov     rcx, [rbp+hObject]; TokenHandle
0x1800196d8  lea     rax, [rbp+TokenInformationLength]
0x1800196dc  xor     r9d, r9d; TokenInformationLength
0x1800196df  mov     qword ptr [rsp+50h+ReturnLength], rax; int
0x1800196e4  xor     r8d, r8d; TokenInformation
0x1800196e7  lea     edx, [r9+19h]; TokenInformationClass
0x1800196eb  call    cs:__imp_GetTokenInformation
0x1800196f1  test    eax, eax
0x1800196f3  jz      short loc_180019701
0x1800196f5  mov     esi, 80240FFFh
0x1800196fa  mov     edx, 4DFh
0x1800196ff  jmp     short loc_18001972D
0x180019701  call    cs:__imp_GetLastError
0x180019707  cmp     eax, 7Ah ; 'z'
0x18001970a  jz      short loc_180019713
0x18001970c  mov     edx, 4E0h
0x180019711  jmp     short loc_18001976A
0x180019713  mov     ecx, [rbp+TokenInformationLength]; unsigned __int64
0x180019716  call    ?SusAlloc@@YAPEAX_K@Z; SusAlloc(unsigned __int64)
0x18001971b  mov     rdi, rax
0x18001971e  test    rax, rax
0x180019721  jnz     short loc_180019742
0x180019723  mov     esi, 8007000Eh
0x180019728  mov     edx, 4E3h; void *
0x18001972d  mov     rcx, [rbp+18h]; this
0x180019731  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180019738  mov     r9d, esi; char *
0x18001973b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019740  jmp     short loc_18001977C
0x180019742  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x180019746  lea     rax, [rbp+TokenInformationLength]
0x18001974a  mov     rcx, [rbp+hObject]; TokenHandle
0x18001974e  mov     r8, rdi; TokenInformation
0x180019751  mov     edx, 19h; TokenInformationClass
0x180019756  mov     qword ptr [rsp+50h+ReturnLength], rax; ReturnLength
0x18001975b  call    cs:__imp_GetTokenInformation
0x180019761  test    eax, eax
0x180019763  jnz     short loc_180019783
0x180019765  mov     edx, 4E6h; void *
0x18001976a  mov     rcx, [rbp+18h]; this
0x18001976e  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180019775  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001977a  mov     esi, eax
0x18001977c  test    rdi, rdi
0x18001977f  jz      short loc_1800197B4
0x180019781  jmp     short loc_1800197AC
0x180019783  mov     rcx, [rdi]; pSid
0x180019786  call    cs:__imp_GetSidSubAuthorityCount
0x18001978c  mov     cl, [rax]
0x18001978e  dec     cl
0x180019790  movzx   edx, cl; nSubAuthority
0x180019793  mov     rcx, [rdi]; pSid
0x180019796  call    cs:__imp_GetSidSubAuthority
0x18001979c  cmp     dword ptr [rax], 3000h
0x1800197a2  jb      short loc_1800197AA
0x1800197a4  mov     dword ptr [rsi], 1
0x1800197aa  xor     esi, esi
0x1800197ac  mov     rcx, rdi; lpMem
0x1800197af  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800197b4  mov     rcx, [rbp+hObject]; hObject
0x1800197b8  test    rcx, rcx
0x1800197bb  jz      short loc_1800197CB
0x1800197bd  call    cs:__imp_CloseHandle
0x1800197c3  mov     [rbp+hObject], 0
0x1800197cb  test    rbx, rbx
0x1800197ce  jz      short loc_1800197D9
0x1800197d0  mov     rcx, rbx; hObject
0x1800197d3  call    cs:__imp_CloseHandle
0x1800197d9  mov     eax, esi
0x1800197db  mov     rcx, [rbp+var_8]
0x1800197df  xor     rcx, rsp; StackCookie
0x1800197e2  call    __security_check_cookie
0x1800197e7  mov     rbx, [rsp+50h+arg_0]
0x1800197ec  add     rsp, 50h
0x1800197f0  pop     rdi
0x1800197f1  pop     rsi
0x1800197f2  pop     rbp
0x1800197f3  retn
```
