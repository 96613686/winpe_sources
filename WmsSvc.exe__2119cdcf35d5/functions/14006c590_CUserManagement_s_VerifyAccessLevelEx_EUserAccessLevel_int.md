# CUserManagement::s_VerifyAccessLevelEx(EUserAccessLevel,int)

- ea: `0x14006c590`
- end: `0x14006c991`
- name: `?s_VerifyAccessLevelEx@CUserManagement@@SAJW4EUserAccessLevel@@H@Z`
- size: `1025`
- prototype: `__int64 __fastcall(unsigned int, int)`
- caller_count: `149`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140008d00`
- `0x140008da0`
- `0x140009380`
- `0x140009af0`
- `0x140009e80`
- `0x14000a1d0`
- `0x14000a330`
- `0x14000a460`
- `0x14000b980`
- `0x14000bfb0`
- `0x14000c3b0`
- `0x140016500`
- `0x140016b40`
- `0x140016d50`
- `0x140017530`
- `0x140017810`
- `0x140017a30`
- `0x140017de0`
- `0x140017ee0`
- `0x140017fc0`
- `0x140018130`
- `0x140018540`
- `0x140018740`
- `0x1400188e0`
- `0x140018b00`
- `0x140018c80`
- `0x140018e10`
- `0x140019100`
- `0x1400192b0`
- `0x140019810`
- `0x140019af0`
- `0x140019e40`
- `0x14001a190`
- `0x14001a210`
- `0x14001a290`
- `0x14001a740`
- `0x14001aa90`
- `0x14001ab70`
- `0x14001ad00`
- `0x14001af00`
- `0x14001b330`
- `0x14001b6e0`
- `0x14001ba30`
- `0x14001bd90`
- `0x14001c110`
- `0x14001c520`
- `0x14001c870`
- `0x14001cbf0`
- `0x14001cf80`
- `0x14001d330`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c290`
- `0x14005c408`
- `0x14006aef0`
- `0x14006b010`
- `0x14006b790`
- `0x14006c590`
- `0x14006c998`
- `0x140076208`
- `0x14007cb9e`
- `0x14007cbd0`

## import_xrefs

- `ADVAPI32!OpenProcessToken` at `0x14006c699`
- `ADVAPI32!OpenProcessToken` at `0x14006c699`
- `ADVAPI32!OpenThreadToken` at `0x14006c80c`
- `ADVAPI32!OpenThreadToken` at `0x14006c80c`
- `ADVAPI32!DuplicateToken` at `0x14006c76b`
- `ADVAPI32!DuplicateToken` at `0x14006c76b`
- `KERNEL32!GetCurrentThread` at `0x14006c7f9`
- `KERNEL32!GetCurrentThread` at `0x14006c7f9`
- `KERNEL32!CloseHandle` at `0x14006c8b4`
- `KERNEL32!CloseHandle` at `0x14006c8d0`
- `KERNEL32!CloseHandle` at `0x14006c8b4`
- `KERNEL32!CloseHandle` at `0x14006c8d0`
- `KERNEL32!GetLastError` at `0x14006c6a7`
- `KERNEL32!GetLastError` at `0x14006c779`
- `KERNEL32!GetLastError` at `0x14006c816`
- `KERNEL32!GetLastError` at `0x14006c6a7`
- `KERNEL32!GetLastError` at `0x14006c779`
- `KERNEL32!GetLastError` at `0x14006c816`
- `KERNEL32!IsDebuggerPresent` at `0x14006c6f7`
- `KERNEL32!IsDebuggerPresent` at `0x14006c7c9`
- `KERNEL32!IsDebuggerPresent` at `0x14006c866`
- `KERNEL32!IsDebuggerPresent` at `0x14006c90f`
- `KERNEL32!IsDebuggerPresent` at `0x14006c6f7`
- `KERNEL32!IsDebuggerPresent` at `0x14006c7c9`
- `KERNEL32!IsDebuggerPresent` at `0x14006c866`
- `KERNEL32!IsDebuggerPresent` at `0x14006c90f`
- `KERNEL32!GetCurrentProcess` at `0x14006c687`
- `KERNEL32!GetCurrentProcess` at `0x14006c687`
- `ole32!CoRevertToSelf` at `0x14006c8e7`
- `ole32!CoRevertToSelf` at `0x14006c8e7`
- `ole32!CoImpersonateClient` at `0x14006c674`
- `ole32!CoImpersonateClient` at `0x14006c674`

## string_xrefs

- `0x14006c5f0`: `termsrv\wms\src\common\srcutils\usermanagement.cpp`
- `0x14006c6ca`: `CUserManagement::s_VerifyAccessLevelEx`
- `0x14006c79c`: `CUserManagement::s_VerifyAccessLevelEx`
- `0x14006c839`: `CUserManagement::s_VerifyAccessLevelEx`
- `0x14006c89f`: `CUserManagement::s_VerifyAccessLevelEx`

## pseudocode

```c
__int64 __fastcall CUserManagement::s_VerifyAccessLevelEx(unsigned int a1, int a2)
{
  int v2; // r15d
  int *v5; // rdx
  signed int IsConnector; // ebx
  unsigned __int64 v7; // r8
  unsigned int v8; // edi
  HRESULT v9; // eax
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  __int64 v12; // r9
  __int64 v13; // r8
  signed int v14; // eax
  HANDLE CurrentThread; // rax
  signed int v16; // eax
  const unsigned __int16 *v17; // r9
  unsigned int v19; // [rsp+40h] [rbp-49h] BYREF
  int v20; // [rsp+44h] [rbp-45h] BYREF
  void *DuplicateTokenHandle; // [rsp+48h] [rbp-41h] BYREF
  void *TokenHandle; // [rsp+50h] [rbp-39h] BYREF
  _BYTE v23[80]; // [rsp+60h] [rbp-29h] BYREF

  v2 = 0;
  TokenHandle = 0;
  DuplicateTokenHandle = 0;
  memset_0(v23, 0, 0x44u);
  v20 = 0;
  v19 = 0;
  IsConnector = PlatformSkuUtils::IsConnector((PlatformSkuUtils *)&v19, v5);
  if ( IsConnector >= 0 )
  {
    v8 = v19;
    if ( CUserManagement::s_pWmsShellUserSID
      || v19
      || (IsConnector = CUserManagement::s_DoesUserExist(L"WmsShell", &v20), IsConnector >= 0)
      && (!v20
       || (IsConnector = CUserManagement::s_GetUserSIDEx(L"WmsShell", 1, &CUserManagement::s_pWmsShellUserSID),
           IsConnector >= 0)) )
    {
      if ( a1 != 1
        || v8
        || (IsConnector = CUserManagement::s_GetLocalGroupSid(L"WmsOperators", v23, v7), IsConnector >= 0) )
      {
        v9 = CoImpersonateClient();
        IsConnector = v9;
        if ( v9 == -2147417833 )
        {
          CurrentProcess = GetCurrentProcess();
          if ( !OpenProcessToken(CurrentProcess, 0xAu, &TokenHandle) )
          {
            LastError = GetLastError();
            IsConnector = LastError;
            if ( LastError > 0 )
              IsConnector = (unsigned __int16)LastError | 0x80070000;
            if ( IsConnector >= 0 )
              IsConnector = -2147467259;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
              0x6DBu,
              L"CUserManagement::s_VerifyAccessLevelEx",
              L"CBRAEx",
              L"fSuccess",
              IsConnector);
            if ( IsDebuggerPresent() )
            {
              v12 = 1755;
LABEL_18:
              DEBUGMSGLEVEL(
                2u,
                L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
                L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
                v12,
                L"CUserManagement::s_VerifyAccessLevelEx",
                L"CBRAEx",
                L"fSuccess",
                IsConnector);
              goto LABEL_39;
            }
            v13 = 1755;
            goto LABEL_20;
          }
          if ( !DuplicateToken(TokenHandle, SecurityIdentification, &DuplicateTokenHandle) )
          {
            v14 = GetLastError();
            IsConnector = v14;
            if ( v14 > 0 )
              IsConnector = (unsigned __int16)v14 | 0x80070000;
            if ( IsConnector >= 0 )
              IsConnector = -2147467259;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
              0x6DFu,
              L"CUserManagement::s_VerifyAccessLevelEx",
              L"CBRAEx",
              L"fSuccess",
              IsConnector);
            if ( IsDebuggerPresent() )
            {
              v12 = 1759;
              goto LABEL_18;
            }
            v13 = 1759;
            goto LABEL_20;
          }
        }
        else
        {
          if ( v9 < 0 )
            goto LABEL_39;
          v2 = 1;
          CurrentThread = GetCurrentThread();
          if ( !OpenThreadToken(CurrentThread, 8u, 1, &DuplicateTokenHandle) )
          {
            v16 = GetLastError();
            IsConnector = v16;
            if ( v16 > 0 )
              IsConnector = (unsigned __int16)v16 | 0x80070000;
            if ( IsConnector >= 0 )
              IsConnector = -2147467259;
            LOGASSERTHR(
              L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
              0x6E6u,
              L"CUserManagement::s_VerifyAccessLevelEx",
              L"CBRAEx",
              L"fSuccess",
              IsConnector);
            if ( IsDebuggerPresent() )
            {
              v12 = 1766;
              goto LABEL_18;
            }
            v13 = 1766;
LABEL_20:
            DEBUGMSGBOX(
              L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
              L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
              v13,
              L"CUserManagement::s_VerifyAccessLevelEx",
              L"CBRAEx",
              L"fSuccess",
              IsConnector);
            goto LABEL_39;
          }
        }
        IsConnector = CUserManagement::s_VerifyTokenAccessLevel(DuplicateTokenHandle, a1, v23, v8, a2);
      }
    }
  }
LABEL_39:
  if ( (char *)DuplicateTokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(DuplicateTokenHandle);
    DuplicateTokenHandle = 0;
  }
  if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  if ( v2 && CoRevertToSelf() < 0 )
  {
    LOGASSERT(
      L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
      0x6F5u,
      L"CUserManagement::s_VerifyAccessLevelEx",
      v17,
      L"SUCCEEDED (hr2)");
    if ( IsDebuggerPresent() )
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)\n",
        L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
        1781,
        L"CUserManagement::s_VerifyAccessLevelEx",
        L"ASSERT",
        L"SUCCEEDED (hr2)");
    else
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)\n",
        L"termsrv\\wms\\src\\common\\srcutils\\usermanagement.cpp",
        1781,
        L"CUserManagement::s_VerifyAccessLevelEx",
        L"ASSERT",
        L"SUCCEEDED (hr2)");
  }
  return (unsigned int)IsConnector;
}

```

## disassembly

```asm
0x14006c590  mov     [rsp-8+arg_10], rbx
0x14006c595  mov     [rsp-8+arg_18], rsi
0x14006c59a  push    rbp
0x14006c59b  push    rdi
0x14006c59c  push    r13
0x14006c59e  push    r14
0x14006c5a0  push    r15
0x14006c5a2  lea     rbp, [rsp-37h]
0x14006c5a7  sub     rsp, 0C0h
0x14006c5ae  mov     rax, cs:__security_cookie
0x14006c5b5  xor     rax, rsp
0x14006c5b8  mov     [rbp+57h+var_30], rax
0x14006c5bc  xor     r15d, r15d
0x14006c5bf  mov     [rbp+57h+TokenHandle], 0
0x14006c5c7  mov     r14d, edx
0x14006c5ca  mov     [rbp+57h+DuplicateTokenHandle], r15
0x14006c5ce  mov     esi, ecx
0x14006c5d0  xor     edx, edx; Val
0x14006c5d2  lea     rcx, [rbp+57h+var_80]; void *
0x14006c5d6  lea     r8d, [r15+44h]; Size
0x14006c5da  call    memset_0
0x14006c5df  lea     rcx, [rbp+57h+var_A0]; this
0x14006c5e3  mov     [rbp+57h+var_9C], r15d
0x14006c5e7  mov     [rbp+57h+var_A0], r15d
0x14006c5eb  call    ?IsConnector@PlatformSkuUtils@@YAJPEAH@Z; PlatformSkuUtils::IsConnector(int *)
0x14006c5f0  lea     r13, aTermsrvWmsSrcC_11; "termsrv\\wms\\src\\common\\srcutils\\us"...
0x14006c5f7  mov     ebx, eax
0x14006c5f9  test    eax, eax
0x14006c5fb  js      loc_14006C89F
0x14006c601  cmp     cs:?s_pWmsShellUserSID@CUserManagement@@0PEAXEA, r15; void * CUserManagement::s_pWmsShellUserSID
0x14006c608  mov     edi, [rbp+57h+var_A0]
0x14006c60b  jnz     short loc_14006C651
0x14006c60d  test    edi, edi
0x14006c60f  jnz     short loc_14006C651
0x14006c611  lea     rdx, [rbp+57h+var_9C]; int *
0x14006c615  lea     rcx, aWmsshell_1; "WmsShell"
0x14006c61c  call    ?s_DoesUserExist@CUserManagement@@SAJPEBGPEAH@Z; CUserManagement::s_DoesUserExist(ushort const *,int *)
0x14006c621  mov     ebx, eax
0x14006c623  test    eax, eax
0x14006c625  js      loc_14006C89F
0x14006c62b  cmp     [rbp+57h+var_9C], r15d
0x14006c62f  jz      short loc_14006C651
0x14006c631  lea     r8, ?s_pWmsShellUserSID@CUserManagement@@0PEAXEA; void * CUserManagement::s_pWmsShellUserSID
0x14006c638  lea     edx, [rdi+1]
0x14006c63b  lea     rcx, aWmsshell_1; "WmsShell"
0x14006c642  call    ?s_GetUserSIDEx@CUserManagement@@SAJPEBGW4EAccountExists@1@PEAPEAX@Z; CUserManagement::s_GetUserSIDEx(ushort const *,CUserManagement::EAccountExists,void * *)
0x14006c647  mov     ebx, eax
0x14006c649  test    eax, eax
0x14006c64b  js      loc_14006C89F
0x14006c651  cmp     esi, 1
0x14006c654  jnz     short loc_14006C674
0x14006c656  test    edi, edi
0x14006c658  jnz     short loc_14006C674
0x14006c65a  lea     rdx, [rbp+57h+var_80]; void *
0x14006c65e  lea     rcx, aWmsoperators_0; "WmsOperators"
0x14006c665  call    ?s_GetLocalGroupSid@CUserManagement@@SAJPEBGPEAX_K@Z; CUserManagement::s_GetLocalGroupSid(ushort const *,void *,unsigned __int64)
0x14006c66a  mov     ebx, eax
0x14006c66c  test    eax, eax
0x14006c66e  js      loc_14006C89F
0x14006c674  call    cs:__imp_CoImpersonateClient
0x14006c67a  mov     ebx, eax
0x14006c67c  cmp     eax, 80010117h
0x14006c681  jnz     loc_14006C7E9
0x14006c687  call    cs:__imp_GetCurrentProcess
0x14006c68d  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x14006c691  mov     edx, 0Ah; DesiredAccess
0x14006c696  mov     rcx, rax; ProcessHandle
0x14006c699  call    cs:__imp_OpenProcessToken
0x14006c69f  test    eax, eax
0x14006c6a1  jnz     loc_14006C75E
0x14006c6a7  call    cs:__imp_GetLastError
0x14006c6ad  mov     ebx, eax
0x14006c6af  test    eax, eax
0x14006c6b1  jle     short loc_14006C6BC
0x14006c6b3  movzx   ebx, ax
0x14006c6b6  or      ebx, 80070000h
0x14006c6bc  mov     eax, 80004005h
0x14006c6c1  lea     rsi, aCbraex; "CBRAEx"
0x14006c6c8  test    ebx, ebx
0x14006c6ca  lea     r14, aCusermanagemen_6; "CUserManagement::s_VerifyAccessLevelEx"
0x14006c6d1  lea     rdi, aFsuccess; "fSuccess"
0x14006c6d8  mov     r9, rsi; unsigned __int16 *
0x14006c6db  cmovns  ebx, eax
0x14006c6de  mov     r8, r14; unsigned __int16 *
0x14006c6e1  mov     [rsp+0E0h+var_B8], ebx; int
0x14006c6e5  mov     edx, 6DBh; unsigned int
0x14006c6ea  mov     rcx, r13; unsigned __int16 *
0x14006c6ed  mov     [rsp+0E0h+var_C0], rdi; unsigned __int16 *
0x14006c6f2  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006c6f7  call    cs:__imp_IsDebuggerPresent
0x14006c6fd  test    eax, eax
0x14006c6ff  jz      short loc_14006C733
0x14006c701  mov     r9d, 6DBh
0x14006c707  mov     [rsp+0E0h+var_A8], ebx
0x14006c70b  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14006c712  mov     [rsp+0E0h+var_B0], rdi
0x14006c717  mov     r8, r13
0x14006c71a  mov     qword ptr [rsp+0E0h+var_B8], rsi
0x14006c71f  mov     ecx, 2; unsigned __int8
0x14006c724  mov     [rsp+0E0h+var_C0], r14
0x14006c729  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14006c72e  jmp     loc_14006C8A6
0x14006c733  mov     r8d, 6DBh
0x14006c739  mov     dword ptr [rsp+0E0h+var_B0], ebx
0x14006c73d  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14006c744  mov     qword ptr [rsp+0E0h+var_B8], rdi
0x14006c749  mov     r9, r14
0x14006c74c  mov     rdx, r13
0x14006c74f  mov     [rsp+0E0h+var_C0], rsi
0x14006c754  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14006c759  jmp     loc_14006C8A6
0x14006c75e  mov     rcx, [rbp+57h+TokenHandle]; ExistingTokenHandle
0x14006c762  lea     r8, [rbp+57h+DuplicateTokenHandle]; DuplicateTokenHandle
0x14006c766  mov     edx, 1; ImpersonationLevel
0x14006c76b  call    cs:__imp_DuplicateToken
0x14006c771  test    eax, eax
0x14006c773  jnz     loc_14006C886
0x14006c779  call    cs:__imp_GetLastError
0x14006c77f  mov     ebx, eax
0x14006c781  test    eax, eax
0x14006c783  jle     short loc_14006C78E
0x14006c785  movzx   ebx, ax
0x14006c788  or      ebx, 80070000h
0x14006c78e  mov     eax, 80004005h
0x14006c793  lea     rsi, aCbraex; "CBRAEx"
0x14006c79a  test    ebx, ebx
0x14006c79c  lea     r14, aCusermanagemen_6; "CUserManagement::s_VerifyAccessLevelEx"
0x14006c7a3  lea     rdi, aFsuccess; "fSuccess"
0x14006c7aa  mov     r9, rsi; unsigned __int16 *
0x14006c7ad  cmovns  ebx, eax
0x14006c7b0  mov     r8, r14; unsigned __int16 *
0x14006c7b3  mov     [rsp+0E0h+var_B8], ebx; int
0x14006c7b7  mov     edx, 6DFh; unsigned int
0x14006c7bc  mov     rcx, r13; unsigned __int16 *
0x14006c7bf  mov     [rsp+0E0h+var_C0], rdi; unsigned __int16 *
0x14006c7c4  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006c7c9  call    cs:__imp_IsDebuggerPresent
0x14006c7cf  test    eax, eax
0x14006c7d1  jz      short loc_14006C7DE
0x14006c7d3  mov     r9d, 6DFh
0x14006c7d9  jmp     loc_14006C707
0x14006c7de  mov     r8d, 6DFh
0x14006c7e4  jmp     loc_14006C739
0x14006c7e9  test    eax, eax
0x14006c7eb  js      loc_14006C89F
0x14006c7f1  mov     ebx, 1
0x14006c7f6  mov     r15d, ebx
0x14006c7f9  call    cs:__imp_GetCurrentThread
0x14006c7ff  lea     r9, [rbp+57h+DuplicateTokenHandle]; TokenHandle
0x14006c803  mov     r8d, ebx; OpenAsSelf
0x14006c806  mov     rcx, rax; ThreadHandle
0x14006c809  lea     edx, [rbx+7]; DesiredAccess
0x14006c80c  call    cs:__imp_OpenThreadToken
0x14006c812  test    eax, eax
0x14006c814  jnz     short loc_14006C886
0x14006c816  call    cs:__imp_GetLastError
0x14006c81c  mov     ebx, eax
0x14006c81e  test    eax, eax
0x14006c820  jle     short loc_14006C82B
0x14006c822  movzx   ebx, ax
0x14006c825  or      ebx, 80070000h
0x14006c82b  mov     eax, 80004005h
0x14006c830  lea     rsi, aCbraex; "CBRAEx"
0x14006c837  test    ebx, ebx
0x14006c839  lea     r14, aCusermanagemen_6; "CUserManagement::s_VerifyAccessLevelEx"
0x14006c840  lea     rdi, aFsuccess; "fSuccess"
0x14006c847  mov     r9, rsi; unsigned __int16 *
0x14006c84a  cmovns  ebx, eax
0x14006c84d  mov     r8, r14; unsigned __int16 *
0x14006c850  mov     [rsp+0E0h+var_B8], ebx; int
0x14006c854  mov     edx, 6E6h; unsigned int
0x14006c859  mov     rcx, r13; unsigned __int16 *
0x14006c85c  mov     [rsp+0E0h+var_C0], rdi; unsigned __int16 *
0x14006c861  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14006c866  call    cs:__imp_IsDebuggerPresent
0x14006c86c  test    eax, eax
0x14006c86e  jz      short loc_14006C87B
0x14006c870  mov     r9d, 6E6h
0x14006c876  jmp     loc_14006C707
0x14006c87b  mov     r8d, 6E6h
0x14006c881  jmp     loc_14006C739
0x14006c886  mov     rcx, [rbp+57h+DuplicateTokenHandle]
0x14006c88a  lea     r8, [rbp+57h+var_80]
0x14006c88e  mov     r9d, edi
0x14006c891  mov     dword ptr [rsp+0E0h+var_C0], r14d
0x14006c896  mov     edx, esi
0x14006c898  call    ?s_VerifyTokenAccessLevel@CUserManagement@@SAJPEAXW4EUserAccessLevel@@0HH@Z; CUserManagement::s_VerifyTokenAccessLevel(void *,EUserAccessLevel,void *,int,int)
0x14006c89d  mov     ebx, eax
0x14006c89f  lea     r14, aCusermanagemen_6; "CUserManagement::s_VerifyAccessLevelEx"
0x14006c8a6  mov     rcx, [rbp+57h+DuplicateTokenHandle]; hObject
0x14006c8aa  lea     rax, [rcx-1]
0x14006c8ae  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14006c8b2  ja      short loc_14006C8C2
0x14006c8b4  call    cs:__imp_CloseHandle
0x14006c8ba  mov     [rbp+57h+DuplicateTokenHandle], 0
0x14006c8c2  mov     rcx, [rbp+57h+TokenHandle]; hObject
0x14006c8c6  lea     rax, [rcx-1]
0x14006c8ca  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14006c8ce  ja      short loc_14006C8DE
0x14006c8d0  call    cs:__imp_CloseHandle
0x14006c8d6  mov     [rbp+57h+TokenHandle], 0
0x14006c8de  test    r15d, r15d
0x14006c8e1  jz      loc_14006C967
0x14006c8e7  call    cs:__imp_CoRevertToSelf
0x14006c8ed  test    eax, eax
0x14006c8ef  jns     short loc_14006C967
0x14006c8f1  mov     edi, 6F5h
0x14006c8f6  lea     rsi, aSucceededHr2; "SUCCEEDED (hr2)"
0x14006c8fd  mov     edx, edi; unsigned int
0x14006c8ff  mov     [rsp+0E0h+var_C0], rsi; unsigned __int16 *
0x14006c904  mov     r8, r14; unsigned __int16 *
0x14006c907  mov     rcx, r13; unsigned __int16 *
0x14006c90a  call    ?LOGASSERT@@YAXPEBGK000@Z; LOGASSERT(ushort const *,ulong,ushort const *,ushort const *,ushort const *)
0x14006c90f  call    cs:__imp_IsDebuggerPresent
0x14006c915  test    eax, eax
0x14006c917  lea     rax, aAssert; "ASSERT"
0x14006c91e  jz      short loc_14006C948
0x14006c920  mov     [rsp+0E0h+var_B0], rsi
0x14006c925  lea     rdx, aSDSAssertionFa; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14006c92c  mov     qword ptr [rsp+0E0h+var_B8], rax
0x14006c931  mov     r9d, edi
0x14006c934  mov     r8, r13
0x14006c937  mov     [rsp+0E0h+var_C0], r14
0x14006c93c  mov     ecx, 2; unsigned __int8
0x14006c941  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14006c946  jmp     short loc_14006C967
0x14006c948  mov     qword ptr [rsp+0E0h+var_B8], rsi
0x14006c94d  lea     rcx, aAssertionFaile_0; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14006c954  mov     r9, r14
0x14006c957  mov     [rsp+0E0h+var_C0], rax
0x14006c95c  mov     r8d, edi
0x14006c95f  mov     rdx, r13
0x14006c962  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14006c967  mov     eax, ebx
0x14006c969  mov     rcx, [rbp+57h+var_30]
0x14006c96d  xor     rcx, rsp; StackCookie
0x14006c970  call    __security_check_cookie
0x14006c975  lea     r11, [rsp+0E0h+var_20]
0x14006c97d  mov     rbx, [r11+40h]
0x14006c981  mov     rsi, [r11+48h]
0x14006c985  mov     rsp, r11
0x14006c988  pop     r15
0x14006c98a  pop     r14
0x14006c98c  pop     r13
0x14006c98e  pop     rdi
0x14006c98f  pop     rbp
0x14006c990  retn
```
