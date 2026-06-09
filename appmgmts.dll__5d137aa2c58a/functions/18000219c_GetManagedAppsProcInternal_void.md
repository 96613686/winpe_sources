# GetManagedAppsProcInternal(void *)

- ea: `0x18000219c`
- end: `0x18000230a`
- name: `?GetManagedAppsProcInternal@@YAKPEAX@Z`
- size: `366`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180002170`

## callees

- `0x18000219c`
- `0x18000df00`
- `0x18000e4f0`
- `0x18000e69c`
- `0x18000e744`
- `0x18001069c`
- `0x18001af7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002208`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002208`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800022e5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800022e5`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180002228`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180002228`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800022f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800022f7`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800021ed`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800021ed`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002214`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002236`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002214`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002236`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800021fe`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800021fe`

## pseudocode

```c
__int64 __fastcall GetManagedAppsProcInternal(void *a1)
{
  unsigned int LastError; // ebx
  _BYTE v4[144]; // [rsp+50h] [rbp-B0h] BYREF
  const unsigned __int16 *v5[64]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v6; // [rsp+2F0h] [rbp+1F0h] BYREF
  HANDLE hToken; // [rsp+2F8h] [rbp+1F8h] BYREF
  HKEY phkResult; // [rsp+300h] [rbp+200h] BYREF

  hToken = 0;
  phkResult = 0;
  if ( !DuplicateTokenEx(*((HANDLE *)a1 + 2), 0xEu, 0, SecurityImpersonation, TokenImpersonation, &hToken)
    || !ImpersonateLoggedOnUser(hToken) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      RevertToSelf();
LABEL_6:
      *((_DWORD *)a1 + 10) = LastError;
      goto LABEL_10;
    }
  }
  LastError = RegOpenCurrentUser(0x10000000u, &phkResult);
  v6 = LastError;
  RevertToSelf();
  if ( LastError )
    goto LABEL_6;
  LogTime();
  CRsopAppContext::CRsopAppContext((CRsopAppContext *)v4, 2u, *((void **)a1 + 3), 0);
  CManagedAppProcessor::CManagedAppProcessor(
    (CManagedAppProcessor *)v5,
    0,
    hToken,
    phkResult,
    0,
    1,
    0,
    (struct CRsopAppContext *)v4,
    &v6);
  if ( !v6 )
    CManagedAppProcessor::GetManagedApplications(v5, *(struct _GUID **)a1, (struct ARPCONTEXT *)a1);
  CManagedAppProcessor::~CManagedAppProcessor((CManagedAppProcessor *)v5);
  CRsopAppContext::~CRsopAppContext((CRsopAppContext *)v4);
LABEL_10:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( hToken )
    CloseHandle(hToken);
  return 0;
}

```

## disassembly

```asm
0x18000219c  push    rbp
0x18000219e  push    rbx
0x18000219f  push    rdi
0x1800021a0  lea     rbp, [rsp-1D0h]
0x1800021a8  sub     rsp, 2D0h
0x1800021af  mov     rdi, rcx
0x1800021b2  mov     [rbp+1E0h+hToken], 0
0x1800021bd  mov     [rbp+1E0h+phkResult], 0
0x1800021c8  lea     rax, [rbp+1E0h+hToken]
0x1800021cf  mov     [rsp+2E0h+phNewToken], rax; phNewToken
0x1800021d4  mov     [rsp+2E0h+TokenType], 2; TokenType
0x1800021dc  mov     r9d, 2; ImpersonationLevel
0x1800021e2  xor     r8d, r8d; lpTokenAttributes
0x1800021e5  lea     edx, [r9+0Ch]; dwDesiredAccess
0x1800021e9  mov     rcx, [rcx+10h]; hExistingToken
0x1800021ed  call    cs:__imp_DuplicateTokenEx
0x1800021f3  test    eax, eax
0x1800021f5  jz      short loc_180002208
0x1800021f7  mov     rcx, [rbp+1E0h+hToken]; hToken
0x1800021fe  call    cs:__imp_ImpersonateLoggedOnUser
0x180002204  test    eax, eax
0x180002206  jnz     short loc_18000221C
0x180002208  call    cs:__imp_GetLastError
0x18000220e  mov     ebx, eax
0x180002210  test    eax, eax
0x180002212  jz      short loc_18000221C
0x180002214  call    cs:__imp_RevertToSelf
0x18000221a  jmp     short loc_180002240
0x18000221c  lea     rdx, [rbp+1E0h+phkResult]; phkResult
0x180002223  mov     ecx, 10000000h; samDesired
0x180002228  call    cs:__imp_RegOpenCurrentUser
0x18000222e  mov     ebx, eax
0x180002230  mov     [rbp+1E0h+arg_0], eax
0x180002236  call    cs:__imp_RevertToSelf
0x18000223c  test    ebx, ebx
0x18000223e  jz      short loc_180002248
0x180002240  mov     [rdi+28h], ebx
0x180002243  jmp     loc_1800022D9
0x180002248  call    ?LogTime@@YAXXZ; LogTime(void)
0x18000224d  xor     r9d, r9d; struct _APPKEY *
0x180002250  mov     r8, [rdi+18h]; void *
0x180002254  lea     edx, [r9+2]; unsigned int
0x180002258  lea     rcx, [rsp+2E0h+var_290]; this
0x18000225d  call    ??0CRsopAppContext@@QEAA@KPEAXPEAU_APPKEY@@@Z; CRsopAppContext::CRsopAppContext(ulong,void *,_APPKEY *)
0x180002262  nop
0x180002263  lea     rax, [rbp+1E0h+arg_0]
0x18000226a  mov     [rsp+2E0h+var_2A0], rax; unsigned int *
0x18000226f  lea     rax, [rsp+2E0h+var_290]
0x180002274  mov     [rsp+2E0h+var_2A8], rax; struct CRsopAppContext *
0x180002279  mov     [rsp+2E0h+var_2B0], 0; int
0x180002281  mov     dword ptr [rsp+2E0h+phNewToken], 1; int
0x180002289  mov     qword ptr [rsp+2E0h+TokenType], 0; cbData
0x180002292  mov     r9, [rbp+1E0h+phkResult]; HKEY
0x180002299  mov     r8, [rbp+1E0h+hToken]; void *
0x1800022a0  xor     edx, edx; unsigned int
0x1800022a2  lea     rcx, [rbp+1E0h+var_200]; this
0x1800022a6  call    ??0CManagedAppProcessor@@QEAA@KPEAXPEAUHKEY__@@P6AKHPEAG@ZHHPEAVCRsopAppContext@@AEAK@Z; CManagedAppProcessor::CManagedAppProcessor(ulong,void *,HKEY__ *,ulong (*)(int,ushort *),int,int,CRsopAppContext *,ulong &)
0x1800022ab  nop
0x1800022ac  cmp     [rbp+1E0h+arg_0], 0
0x1800022b3  jnz     short loc_1800022C5
0x1800022b5  mov     r8, rdi; struct ARPCONTEXT *
0x1800022b8  mov     rdx, [rdi]; struct _GUID *
0x1800022bb  lea     rcx, [rbp+1E0h+var_200]; this
0x1800022bf  call    ?GetManagedApplications@CManagedAppProcessor@@QEAAKPEAU_GUID@@PEAUARPCONTEXT@@@Z; CManagedAppProcessor::GetManagedApplications(_GUID *,ARPCONTEXT *)
0x1800022c4  nop
0x1800022c5  lea     rcx, [rbp+1E0h+var_200]; this
0x1800022c9  call    ??1CManagedAppProcessor@@QEAA@XZ; CManagedAppProcessor::~CManagedAppProcessor(void)
0x1800022ce  nop
0x1800022cf  lea     rcx, [rsp+2E0h+var_290]; this
0x1800022d4  call    ??1CRsopAppContext@@QEAA@XZ; CRsopAppContext::~CRsopAppContext(void)
0x1800022d9  mov     rcx, [rbp+1E0h+phkResult]; hKey
0x1800022e0  test    rcx, rcx
0x1800022e3  jz      short loc_1800022EB
0x1800022e5  call    cs:__imp_RegCloseKey
0x1800022eb  mov     rcx, [rbp+1E0h+hToken]; hObject
0x1800022f2  test    rcx, rcx
0x1800022f5  jz      short loc_1800022FD
0x1800022f7  call    cs:__imp_CloseHandle
0x1800022fd  xor     eax, eax
0x1800022ff  add     rsp, 2D0h
0x180002306  pop     rdi
0x180002307  pop     rbx
0x180002308  pop     rbp
0x180002309  retn
```
