# KERNEL_USER_CONTEXT::Initialize(_HTTP_REQUEST_AUTH_INFO *)

- ea: `0x18000417c`
- end: `0x1800043d3`
- name: `?Initialize@KERNEL_USER_CONTEXT@@QEAAJPEAU_HTTP_REQUEST_AUTH_INFO@@@Z`
- size: `599`
- prototype: `__int64 __fastcall(KERNEL_USER_CONTEXT *__hidden this, struct _HTTP_REQUEST_AUTH_INFO *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1800021f0`

## callees

- `0x18000417c`
- `0x180007d34`
- `0x180008ba0`

## import_xrefs

- `SspiCli!QuerySecurityContextToken` at `0x18000436a`
- `SspiCli!QuerySecurityContextToken` at `0x18000436a`
- `SspiCli!QueryContextAttributesA` at `0x1800042f9`
- `SspiCli!QueryContextAttributesA` at `0x1800042f9`
- `SspiCli!ImportSecurityContextW` at `0x180004292`
- `SspiCli!ImportSecurityContextW` at `0x180004292`
- `SspiCli!FreeContextBuffer` at `0x1800042df`
- `SspiCli!FreeContextBuffer` at `0x180004359`
- `SspiCli!FreeContextBuffer` at `0x1800042df`
- `SspiCli!FreeContextBuffer` at `0x180004359`
- `SspiCli!QueryContextAttributesW` at `0x1800042b6`
- `SspiCli!QueryContextAttributesW` at `0x1800042b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000424b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000424b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004395`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004395`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180004241`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180004241`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004209`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004216`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004209`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180004216`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800043a7`
- `iisutil!??1STRA@@QEAA@XZ` at `0x1800043a7`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800041c5`
- `iisutil!??0STRA@@QEAA@XZ` at `0x1800041c5`
- `iisutil!PuDbgPrint` at `0x180004339`
- `iisutil!PuDbgPrint` at `0x180004339`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800042d3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800042d3`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBG@Z` at `0x1800041df`
- `iisutil!?CopyWTruncate@STRA@@QEAAJPEBG@Z` at `0x1800041df`
- `iisutil!DisableTokenBackupPrivilege` at `0x18000437a`
- `iisutil!DisableTokenBackupPrivilege` at `0x18000437a`
- `iisutil!AdjustTokenIntegrityLevel` at `0x180004384`
- `iisutil!AdjustTokenIntegrityLevel` at `0x180004384`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000434d`
- `iisutil!?Copy@STRA@@QEAAJPEBD@Z` at `0x18000434d`

## string_xrefs

- `0x180004320`: `servercommon\inetsrv\iis\iisrearc\iis70\auth_modules\sspi_auth\sspi_auth.cxx`

## pseudocode

```c
__int64 __fastcall KERNEL_USER_CONTEXT::Initialize(KERNEL_USER_CONTEXT *this, struct _HTTP_REQUEST_AUTH_INFO *a2)
{
  const unsigned __int16 *pPackageName; // rdx
  int ReferencedCredential; // ebx
  HANDLE CurrentProcess; // rax
  HANDLE AccessToken; // rdi
  void *v8; // rbx
  HANDLE v9; // rax
  signed int LastError; // eax
  WCHAR *v11; // rcx
  SECURITY_STATUS v12; // eax
  HANDLE TargetHandle; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int16 *pBuffer; // [rsp+48h] [rbp-21h] BYREF
  PVOID pvContextBuffer; // [rsp+50h] [rbp-19h] BYREF
  struct _SecBuffer pPackedContext; // [rsp+58h] [rbp-11h] BYREF
  _BYTE v18[32]; // [rsp+68h] [rbp-1h] BYREF
  char *v19; // [rsp+88h] [rbp+1Fh]

  pBuffer = 0;
  TargetHandle = 0;
  pPackedContext = 0;
  STRA::STRA((STRA *)v18);
  *((_QWORD *)this + 2) = a2;
  pPackageName = a2->pPackageName;
  pvContextBuffer = 0;
  ReferencedCredential = STRA::CopyWTruncate((STRA *)v18, pPackageName);
  if ( ReferencedCredential >= 0 )
  {
    ReferencedCredential = SSPI_CREDENTIAL::GetReferencedCredential(v19, (struct SSPI_CREDENTIAL **)this + 14, 0);
    if ( ReferencedCredential >= 0 )
    {
      CurrentProcess = GetCurrentProcess();
      AccessToken = a2->AccessToken;
      v8 = CurrentProcess;
      v9 = GetCurrentProcess();
      if ( DuplicateHandle(v9, AccessToken, v8, &TargetHandle, 0, 0, 2u) )
      {
        v11 = a2->pPackageName;
        pPackedContext.BufferType = a2->PackedContextType;
        pPackedContext.cbBuffer = a2->PackedContextLength;
        pPackedContext.pvBuffer = a2->PackedContext;
        ReferencedCredential = ImportSecurityContextW(v11, &pPackedContext, TargetHandle, (PCtxtHandle)this + 6);
        if ( ReferencedCredential >= 0 )
        {
          TargetHandle = 0;
          ReferencedCredential = QueryContextAttributesW((PCtxtHandle)this + 6, 1u, &pBuffer);
          if ( ReferencedCredential >= 0 )
          {
            if ( !pBuffer
              || (ReferencedCredential = STRU::Copy((KERNEL_USER_CONTEXT *)((char *)this + 40), pBuffer),
                  FreeContextBuffer(pBuffer),
                  ReferencedCredential >= 0) )
            {
              v12 = QueryContextAttributesA((PCtxtHandle)this + 6, 0xAu, &pvContextBuffer);
              ReferencedCredential = v12;
              if ( v12 >= 0 )
              {
                ReferencedCredential = STRA::Copy(
                                         (KERNEL_USER_CONTEXT *)((char *)this + 120),
                                         *((const char **)pvContextBuffer + 2));
                FreeContextBuffer(pvContextBuffer);
                if ( ReferencedCredential >= 0 )
                {
                  ReferencedCredential = QuerySecurityContextToken((PCtxtHandle)this + 6, (void **)this + 3);
                  if ( ReferencedCredential >= 0 )
                  {
                    DisableTokenBackupPrivilege(*((void **)this + 3));
                    ReferencedCredential = AdjustTokenIntegrityLevel(*((void **)this + 3));
                  }
                }
              }
              else if ( (g_dwDebugFlags & 3) != 0 )
              {
                PuDbgPrint(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\auth_modules\\sspi_auth\\sspi_auth.cxx",
                  2031,
                  "KERNEL_USER_CONTEXT::Initialize",
                  "QueryContextAttributes() failed with ss = 0x%x.\n",
                  v12);
              }
            }
          }
        }
      }
      else
      {
        LastError = GetLastError();
        ReferencedCredential = LastError;
        if ( LastError > 0 )
          ReferencedCredential = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  if ( TargetHandle )
  {
    CloseHandle(TargetHandle);
    TargetHandle = 0;
  }
  STRA::~STRA((STRA *)v18);
  return (unsigned int)ReferencedCredential;
}

```

## disassembly

```asm
0x18000417c  mov     [rsp-8+arg_10], rbx
0x180004181  mov     [rsp-8+arg_18], rsi
0x180004186  push    rbp
0x180004187  push    rdi
0x180004188  push    r14
0x18000418a  lea     rbp, [rsp-47h]
0x18000418f  sub     rsp, 0B0h
0x180004196  mov     rax, cs:__security_cookie
0x18000419d  xor     rax, rsp
0x1800041a0  mov     [rbp+57h+var_20], rax
0x1800041a4  mov     rsi, rcx
0x1800041a7  mov     [rbp+57h+pBuffer], 0
0x1800041af  xorps   xmm0, xmm0
0x1800041b2  mov     [rbp+57h+TargetHandle], 0
0x1800041ba  lea     rcx, [rbp+57h+var_58]
0x1800041be  mov     r14, rdx
0x1800041c1  movups  xmmword ptr [rbp+57h+pPackedContext.cbBuffer], xmm0
0x1800041c5  call    cs:__imp_??0STRA@@QEAA@XZ; STRA::STRA(void)
0x1800041cb  mov     [rsi+10h], r14
0x1800041cf  lea     rcx, [rbp+57h+var_58]
0x1800041d3  mov     rdx, [r14+48h]
0x1800041d7  mov     [rbp+57h+pvContextBuffer], 0
0x1800041df  call    cs:__imp_?CopyWTruncate@STRA@@QEAAJPEBG@Z; STRA::CopyWTruncate(ushort const *)
0x1800041e5  mov     ebx, eax
0x1800041e7  test    eax, eax
0x1800041e9  js      loc_18000438C
0x1800041ef  mov     rcx, [rbp+57h+var_38]; char *
0x1800041f3  lea     rdx, [rsi+70h]; struct SSPI_CREDENTIAL **
0x1800041f7  xor     r8d, r8d; struct MULTISZ *
0x1800041fa  call    ?GetReferencedCredential@SSPI_CREDENTIAL@@SAJPEBDPEAPEAV1@PEAVMULTISZ@@@Z; SSPI_CREDENTIAL::GetReferencedCredential(char const *,SSPI_CREDENTIAL * *,MULTISZ *)
0x1800041ff  mov     ebx, eax
0x180004201  test    eax, eax
0x180004203  js      loc_18000438C
0x180004209  call    cs:__imp_GetCurrentProcess
0x18000420f  mov     rdi, [r14+10h]
0x180004213  mov     rbx, rax
0x180004216  call    cs:__imp_GetCurrentProcess
0x18000421c  mov     [rsp+0C0h+dwOptions], 2; dwOptions
0x180004224  lea     r9, [rbp+57h+TargetHandle]; lpTargetHandle
0x180004228  mov     rcx, rax; hSourceProcessHandle
0x18000422b  mov     [rsp+0C0h+bInheritHandle], 0; bInheritHandle
0x180004233  mov     r8, rbx; hTargetProcessHandle
0x180004236  mov     [rsp+0C0h+dwDesiredAccess], 0; dwDesiredAccess
0x18000423e  mov     rdx, rdi; hSourceHandle
0x180004241  call    cs:__imp_DuplicateHandle
0x180004247  test    eax, eax
0x180004249  jnz     short loc_180004269
0x18000424b  call    cs:__imp_GetLastError
0x180004251  mov     ebx, eax
0x180004253  test    eax, eax
0x180004255  jle     loc_18000438C
0x18000425b  movzx   ebx, ax
0x18000425e  or      ebx, 80070000h
0x180004264  jmp     loc_18000438C
0x180004269  mov     eax, [r14+20h]
0x18000426d  lea     rdi, [rsi+60h]
0x180004271  mov     r8, [rbp+57h+TargetHandle]; Token
0x180004275  lea     rdx, [rbp+57h+pPackedContext]; pPackedContext
0x180004279  mov     rcx, [r14+48h]; pszPackage
0x18000427d  mov     r9, rdi; phContext
0x180004280  mov     [rbp+57h+pPackedContext.BufferType], eax
0x180004283  mov     eax, [r14+1Ch]
0x180004287  mov     [rbp+57h+pPackedContext.cbBuffer], eax
0x18000428a  mov     rax, [r14+28h]
0x18000428e  mov     [rbp+57h+pPackedContext.pvBuffer], rax
0x180004292  call    cs:__imp_ImportSecurityContextW
0x180004298  mov     ebx, eax
0x18000429a  test    eax, eax
0x18000429c  js      loc_18000438C
0x1800042a2  lea     r8, [rbp+57h+pBuffer]; pBuffer
0x1800042a6  mov     [rbp+57h+TargetHandle], 0
0x1800042ae  mov     edx, 1; ulAttribute
0x1800042b3  mov     rcx, rdi; phContext
0x1800042b6  call    cs:__imp_QueryContextAttributesW
0x1800042bc  mov     ebx, eax
0x1800042be  test    eax, eax
0x1800042c0  js      loc_18000438C
0x1800042c6  mov     rdx, [rbp+57h+pBuffer]
0x1800042ca  test    rdx, rdx
0x1800042cd  jz      short loc_1800042ED
0x1800042cf  lea     rcx, [rsi+28h]
0x1800042d3  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800042d9  mov     rcx, [rbp+57h+pBuffer]; pvContextBuffer
0x1800042dd  mov     ebx, eax
0x1800042df  call    cs:__imp_FreeContextBuffer
0x1800042e5  test    ebx, ebx
0x1800042e7  js      loc_18000438C
0x1800042ed  lea     r8, [rbp+57h+pvContextBuffer]; pBuffer
0x1800042f1  mov     edx, 0Ah; ulAttribute
0x1800042f6  mov     rcx, rdi; phContext
0x1800042f9  call    cs:__imp_QueryContextAttributesA
0x1800042ff  mov     ebx, eax
0x180004301  test    eax, eax
0x180004303  jns     short loc_180004341
0x180004305  test    byte ptr cs:g_dwDebugFlags, 3
0x18000430c  jz      short loc_18000438C
0x18000430e  mov     rcx, cs:g_pDebug
0x180004315  lea     r9, aKernelUserCont; "KERNEL_USER_CONTEXT::Initialize"
0x18000431c  mov     [rsp+0C0h+bInheritHandle], eax
0x180004320  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004327  lea     rax, aQuerycontextat; "QueryContextAttributes() failed with ss"...
0x18000432e  mov     r8d, 7EFh
0x180004334  mov     qword ptr [rsp+0C0h+dwDesiredAccess], rax
0x180004339  call    cs:__imp_PuDbgPrint
0x18000433f  jmp     short loc_18000438C
0x180004341  mov     rdx, [rbp+57h+pvContextBuffer]
0x180004345  lea     rcx, [rsi+78h]
0x180004349  mov     rdx, [rdx+10h]
0x18000434d  call    cs:__imp_?Copy@STRA@@QEAAJPEBD@Z; STRA::Copy(char const *)
0x180004353  mov     rcx, [rbp+57h+pvContextBuffer]; pvContextBuffer
0x180004357  mov     ebx, eax
0x180004359  call    cs:__imp_FreeContextBuffer
0x18000435f  test    ebx, ebx
0x180004361  js      short loc_18000438C
0x180004363  lea     rdx, [rsi+18h]; Token
0x180004367  mov     rcx, rdi; phContext
0x18000436a  call    cs:__imp_QuerySecurityContextToken
0x180004370  mov     ebx, eax
0x180004372  test    eax, eax
0x180004374  js      short loc_18000438C
0x180004376  mov     rcx, [rsi+18h]
0x18000437a  call    cs:__imp_?DisableTokenBackupPrivilege@@YAXPEAX@Z; DisableTokenBackupPrivilege(void *)
0x180004380  mov     rcx, [rsi+18h]
0x180004384  call    cs:__imp_?AdjustTokenIntegrityLevel@@YAJPEAX@Z; AdjustTokenIntegrityLevel(void *)
0x18000438a  mov     ebx, eax
0x18000438c  mov     rcx, [rbp+57h+TargetHandle]; hObject
0x180004390  test    rcx, rcx
0x180004393  jz      short loc_1800043A3
0x180004395  call    cs:__imp_CloseHandle
0x18000439b  mov     [rbp+57h+TargetHandle], 0
0x1800043a3  lea     rcx, [rbp+57h+var_58]
0x1800043a7  call    cs:__imp_??1STRA@@QEAA@XZ; STRA::~STRA(void)
0x1800043ad  mov     eax, ebx
0x1800043af  mov     rcx, [rbp+57h+var_20]
0x1800043b3  xor     rcx, rsp; StackCookie
0x1800043b6  call    __security_check_cookie
0x1800043bb  lea     r11, [rsp+0C0h+var_10]
0x1800043c3  mov     rbx, [r11+30h]
0x1800043c7  mov     rsi, [r11+38h]
0x1800043cb  mov     rsp, r11
0x1800043ce  pop     r14
0x1800043d0  pop     rdi
0x1800043d1  pop     rbp
0x1800043d2  retn
```
