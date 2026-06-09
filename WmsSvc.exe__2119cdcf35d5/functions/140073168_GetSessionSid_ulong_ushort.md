# GetSessionSid(ulong,ushort * *)

- ea: `0x140073168`
- end: `0x1400733aa`
- name: `?GetSessionSid@@YAJKPEAPEAG@Z`
- size: `578`
- prototype: `__int64 __fastcall(ULONG, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14001edf0`

## callees

- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x1400673ac`
- `0x140073168`

## import_xrefs

- `ADVAPI32!ConvertSidToStringSidW` at `0x1400732d8`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1400732d8`
- `KERNEL32!CloseHandle` at `0x140073389`
- `KERNEL32!CloseHandle` at `0x140073389`
- `KERNEL32!LocalFree` at `0x14007336c`
- `KERNEL32!LocalFree` at `0x140073375`
- `KERNEL32!LocalFree` at `0x14007336c`
- `KERNEL32!LocalFree` at `0x140073375`
- `KERNEL32!GetLastError` at `0x1400731a8`
- `KERNEL32!GetLastError` at `0x1400731f3`
- `KERNEL32!GetLastError` at `0x1400732e2`
- `KERNEL32!GetLastError` at `0x1400731a8`
- `KERNEL32!GetLastError` at `0x1400731f3`
- `KERNEL32!GetLastError` at `0x1400732e2`
- `KERNEL32!IsDebuggerPresent` at `0x14007324a`
- `KERNEL32!IsDebuggerPresent` at `0x140073339`
- `KERNEL32!IsDebuggerPresent` at `0x14007324a`
- `KERNEL32!IsDebuggerPresent` at `0x140073339`
- `WTSAPI32!WTSQueryUserToken` at `0x14007319a`
- `WTSAPI32!WTSQueryUserToken` at `0x14007319a`

## string_xrefs

- `0x1400731ce`: `termsrv\wms\src\common\srcutils\rdslistenerconfig.cpp`
- `0x14007321d`: `termsrv\wms\src\common\srcutils\rdslistenerconfig.cpp`
- `0x14007330c`: `termsrv\wms\src\common\srcutils\rdslistenerconfig.cpp`
- `0x1400731b5`: `WTSQueryUserToken returned ERROR_NO_TOKEN - erroring out, but not asserting.`
- `0x1400731c7`: `GetSessionSid`
- `0x140073216`: `GetSessionSid`
- `0x140073305`: `GetSessionSid`

## pseudocode

```c
__int64 __fastcall GetSessionSid(ULONG a1, unsigned __int16 **a2)
{
  void *v3; // rdi
  signed int v4; // ebx
  signed int LastError; // eax
  __int64 v6; // r9
  __int64 v7; // r8
  int TokenInformationWithLocalAlloc; // eax
  signed int v9; // eax
  signed int v11; // [rsp+30h] [rbp-20h]
  signed int v12; // [rsp+38h] [rbp-18h]
  void *phToken; // [rsp+40h] [rbp-10h] BYREF
  LPWSTR StringSid; // [rsp+90h] [rbp+40h] BYREF
  void *v15; // [rsp+98h] [rbp+48h] BYREF

  phToken = 0;
  v3 = 0;
  v15 = 0;
  StringSid = 0;
  if ( !WTSQueryUserToken(a1, &phToken) )
  {
    if ( GetLastError() == 1008 )
    {
      v4 = -2147023888;
      DEBUGMSGLEVEL(
        4u,
        L"%s(%d) - %s - Test failed:  %s\n",
        L"termsrv\\wms\\src\\common\\srcutils\\rdslistenerconfig.cpp",
        354,
        L"GetSessionSid",
        L"WTSQueryUserToken returned ERROR_NO_TOKEN - erroring out, but not asserting.");
      goto LABEL_23;
    }
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
      v4 = -2147467259;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\common\\srcutils\\rdslistenerconfig.cpp",
      0x163u,
      L"GetSessionSid",
      L"CBRAEx",
      L"fSuccess",
      v4);
    if ( IsDebuggerPresent() )
    {
      v6 = 355;
LABEL_10:
      v12 = v4;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\common\\srcutils\\rdslistenerconfig.cpp",
        v6,
        L"GetSessionSid",
        L"CBRAEx",
        L"fSuccess",
        v12);
      goto LABEL_23;
    }
    v7 = 355;
LABEL_12:
    v11 = v4;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\common\\srcutils\\rdslistenerconfig.cpp",
      v7,
      L"GetSessionSid",
      L"CBRAEx",
      L"fSuccess",
      v11);
    goto LABEL_23;
  }
  TokenInformationWithLocalAlloc = GetTokenInformationWithLocalAlloc(phToken, TokenUser, &v15);
  v3 = v15;
  v4 = TokenInformationWithLocalAlloc;
  if ( TokenInformationWithLocalAlloc >= 0 )
  {
    if ( !ConvertSidToStringSidW(*(PSID *)v15, &StringSid) )
    {
      v9 = GetLastError();
      v4 = v9;
      if ( v9 > 0 )
        v4 = (unsigned __int16)v9 | 0x80070000;
      if ( v4 >= 0 )
        v4 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\common\\srcutils\\rdslistenerconfig.cpp",
        0x171u,
        L"GetSessionSid",
        L"CBRAEx",
        L"fSuccess",
        v4);
      if ( IsDebuggerPresent() )
      {
        v6 = 369;
        goto LABEL_10;
      }
      v7 = 369;
      goto LABEL_12;
    }
    *a2 = StringSid;
    StringSid = 0;
  }
LABEL_23:
  LocalFree(StringSid);
  LocalFree(v3);
  if ( (char *)phToken - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(phToken);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140073168  mov     [rsp-28h+arg_0], rbx
0x14007316d  mov     [rsp-28h+arg_8], rsi
0x140073172  push    rbp
0x140073173  push    rdi
0x140073174  push    r12
0x140073176  push    r14
0x140073178  push    r15
0x14007317a  mov     rbp, rsp
0x14007317d  sub     rsp, 50h
0x140073181  mov     rsi, rdx
0x140073184  mov     [rbp+phToken], 0
0x14007318c  xor     edi, edi
0x14007318e  lea     rdx, [rbp+phToken]; phToken
0x140073192  mov     [rbp+arg_18], rdi
0x140073196  mov     [rbp+StringSid], rdi
0x14007319a  call    cs:__imp_WTSQueryUserToken
0x1400731a0  test    eax, eax
0x1400731a2  jnz     loc_1400732B1
0x1400731a8  call    cs:__imp_GetLastError
0x1400731ae  cmp     eax, 3F0h
0x1400731b3  jnz     short loc_1400731F3
0x1400731b5  lea     rax, aWtsqueryuserto; "WTSQueryUserToken returned ERROR_NO_TOK"...
0x1400731bc  mov     r9d, 162h
0x1400731c2  mov     qword ptr [rsp+50h+var_28], rax
0x1400731c7  lea     r14, aGetsessionsid; "GetSessionSid"
0x1400731ce  lea     r8, aTermsrvWmsSrcC_20; "termsrv\\wms\\src\\common\\srcutils\\rd"...
0x1400731d5  mov     [rsp+50h+var_30], r14
0x1400731da  lea     rdx, aSDSTestFailedS; "%s(%d) - %s - Test failed:  %s\n"
0x1400731e1  mov     ebx, 800703F0h
0x1400731e6  lea     ecx, [rdi+4]; unsigned __int8
0x1400731e9  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400731ee  jmp     loc_140073368
0x1400731f3  call    cs:__imp_GetLastError
0x1400731f9  mov     ebx, eax
0x1400731fb  test    eax, eax
0x1400731fd  jle     short loc_140073208
0x1400731ff  movzx   ebx, ax
0x140073202  or      ebx, 80070000h
0x140073208  mov     eax, 80004005h
0x14007320d  lea     r12, aCbraex; "CBRAEx"
0x140073214  test    ebx, ebx
0x140073216  lea     r14, aGetsessionsid; "GetSessionSid"
0x14007321d  lea     rsi, aTermsrvWmsSrcC_20; "termsrv\\wms\\src\\common\\srcutils\\rd"...
0x140073224  mov     r9, r12; unsigned __int16 *
0x140073227  cmovns  ebx, eax
0x14007322a  lea     r15, aFsuccess; "fSuccess"
0x140073231  mov     [rsp+50h+var_28], ebx; int
0x140073235  mov     r8, r14; unsigned __int16 *
0x140073238  mov     edx, 163h; unsigned int
0x14007323d  mov     [rsp+50h+var_30], r15; unsigned __int16 *
0x140073242  mov     rcx, rsi; unsigned __int16 *
0x140073245  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14007324a  call    cs:__imp_IsDebuggerPresent
0x140073250  test    eax, eax
0x140073252  jz      short loc_140073286
0x140073254  mov     r9d, 163h
0x14007325a  mov     [rsp+50h+var_18], ebx
0x14007325e  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x140073265  mov     [rsp+50h+var_20], r15
0x14007326a  mov     r8, rsi
0x14007326d  mov     qword ptr [rsp+50h+var_28], r12
0x140073272  mov     ecx, 2; unsigned __int8
0x140073277  mov     [rsp+50h+var_30], r14
0x14007327c  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140073281  jmp     loc_140073368
0x140073286  mov     r8d, 163h
0x14007328c  mov     dword ptr [rsp+50h+var_20], ebx
0x140073290  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140073297  mov     qword ptr [rsp+50h+var_28], r15
0x14007329c  mov     r9, r14
0x14007329f  mov     rdx, rsi
0x1400732a2  mov     [rsp+50h+var_30], r12
0x1400732a7  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x1400732ac  jmp     loc_140073368
0x1400732b1  mov     rcx, [rbp+phToken]; TokenHandle
0x1400732b5  lea     r8, [rbp+arg_18]; void **
0x1400732b9  mov     edx, 1; TokenInformationClass
0x1400732be  call    ?GetTokenInformationWithLocalAlloc@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@PEAPEAX@Z; GetTokenInformationWithLocalAlloc(void *,_TOKEN_INFORMATION_CLASS,void * *)
0x1400732c3  mov     rdi, [rbp+arg_18]
0x1400732c7  mov     ebx, eax
0x1400732c9  test    eax, eax
0x1400732cb  js      loc_140073368
0x1400732d1  mov     rcx, [rdi]; Sid
0x1400732d4  lea     rdx, [rbp+StringSid]; StringSid
0x1400732d8  call    cs:__imp_ConvertSidToStringSidW
0x1400732de  test    eax, eax
0x1400732e0  jnz     short loc_140073359
0x1400732e2  call    cs:__imp_GetLastError
0x1400732e8  mov     ebx, eax
0x1400732ea  test    eax, eax
0x1400732ec  jle     short loc_1400732F7
0x1400732ee  movzx   ebx, ax
0x1400732f1  or      ebx, 80070000h
0x1400732f7  mov     eax, 80004005h
0x1400732fc  lea     r12, aCbraex; "CBRAEx"
0x140073303  test    ebx, ebx
0x140073305  lea     r14, aGetsessionsid; "GetSessionSid"
0x14007330c  lea     rsi, aTermsrvWmsSrcC_20; "termsrv\\wms\\src\\common\\srcutils\\rd"...
0x140073313  mov     r9, r12; unsigned __int16 *
0x140073316  cmovns  ebx, eax
0x140073319  lea     r15, aFsuccess; "fSuccess"
0x140073320  mov     [rsp+50h+var_28], ebx; int
0x140073324  mov     r8, r14; unsigned __int16 *
0x140073327  mov     edx, 171h; unsigned int
0x14007332c  mov     [rsp+50h+var_30], r15; unsigned __int16 *
0x140073331  mov     rcx, rsi; unsigned __int16 *
0x140073334  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140073339  call    cs:__imp_IsDebuggerPresent
0x14007333f  test    eax, eax
0x140073341  jz      short loc_14007334E
0x140073343  mov     r9d, 171h
0x140073349  jmp     loc_14007325A
0x14007334e  mov     r8d, 171h
0x140073354  jmp     loc_14007328C
0x140073359  mov     rax, [rbp+StringSid]
0x14007335d  mov     [rsi], rax
0x140073360  mov     [rbp+StringSid], 0
0x140073368  mov     rcx, [rbp+StringSid]; hMem
0x14007336c  call    cs:__imp_LocalFree
0x140073372  mov     rcx, rdi; hMem
0x140073375  call    cs:__imp_LocalFree
0x14007337b  mov     rcx, [rbp+phToken]; hObject
0x14007337f  lea     rax, [rcx-1]
0x140073383  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140073387  ja      short loc_14007338F
0x140073389  call    cs:__imp_CloseHandle
0x14007338f  lea     r11, [rsp+50h+var_s0]
0x140073394  mov     eax, ebx
0x140073396  mov     rbx, [r11+30h]
0x14007339a  mov     rsi, [r11+38h]
0x14007339e  mov     rsp, r11
0x1400733a1  pop     r15
0x1400733a3  pop     r14
0x1400733a5  pop     r12
0x1400733a7  pop     rdi
0x1400733a8  pop     rbp
0x1400733a9  retn
```
