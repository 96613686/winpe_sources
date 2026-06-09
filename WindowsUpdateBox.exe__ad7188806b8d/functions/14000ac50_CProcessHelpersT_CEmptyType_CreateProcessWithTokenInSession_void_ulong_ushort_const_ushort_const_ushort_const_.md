# CProcessHelpersT<CEmptyType>::CreateProcessWithTokenInSession(void *,ulong,ushort const *,ushort const *,ushort const *,int,int,void * *,void * *,int)

- ea: `0x14000ac50`
- end: `0x14000afbe`
- name: `?CreateProcessWithTokenInSession@?$CProcessHelpersT@VCEmptyType@@@@SAJPEAXKPEBG11HHPEAPEAX2H@Z`
- size: `878`
- prototype: `__int64 __fastcall(HANDLE hExistingToken, int, unsigned __int16 *, _WORD *, WCHAR *, int, int, HANDLE *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140012124`

## callees

- `0x140002116`
- `0x1400076c8`
- `0x14000ac50`
- `0x1400135b8`
- `0x14001d4ac`
- `0x140080d70`

## import_xrefs

- `ADVAPI32!DuplicateTokenEx` at `0x14000acfa`
- `ADVAPI32!DuplicateTokenEx` at `0x14000acfa`
- `ADVAPI32!CreateProcessAsUserW` at `0x14000aebb`
- `ADVAPI32!CreateProcessAsUserW` at `0x14000aebb`
- `ADVAPI32!SetTokenInformation` at `0x14000ae31`
- `ADVAPI32!SetTokenInformation` at `0x14000ae61`
- `ADVAPI32!SetTokenInformation` at `0x14000ae31`
- `ADVAPI32!SetTokenInformation` at `0x14000ae61`
- `KERNEL32!CloseHandle` at `0x14000aee5`
- `KERNEL32!CloseHandle` at `0x14000aef5`
- `KERNEL32!CloseHandle` at `0x14000af5a`
- `KERNEL32!CloseHandle` at `0x14000aee5`
- `KERNEL32!CloseHandle` at `0x14000aef5`
- `KERNEL32!CloseHandle` at `0x14000af5a`
- `KERNEL32!HeapFree` at `0x14000af22`
- `KERNEL32!HeapFree` at `0x14000af85`
- `KERNEL32!HeapFree` at `0x14000af22`
- `KERNEL32!HeapFree` at `0x14000af85`
- `KERNEL32!GetProcessHeap` at `0x14000af0d`
- `KERNEL32!GetProcessHeap` at `0x14000af70`
- `KERNEL32!GetProcessHeap` at `0x14000af0d`
- `KERNEL32!GetProcessHeap` at `0x14000af70`
- `KERNEL32!GetLastError` at `0x14000ad0c`
- `KERNEL32!GetLastError` at `0x14000ad0c`
- `KERNEL32!GetSystemDirectoryW` at `0x14000ad76`
- `KERNEL32!GetSystemDirectoryW` at `0x14000ad76`
- `USERENV!DestroyEnvironmentBlock` at `0x14000af3f`
- `USERENV!DestroyEnvironmentBlock` at `0x14000af3f`
- `USERENV!CreateEnvironmentBlock` at `0x14000ad5d`
- `USERENV!CreateEnvironmentBlock` at `0x14000ad5d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CProcessHelpersT<CEmptyType>::CreateProcessWithTokenInSession(
        HANDLE hExistingToken,
        int a2,
        unsigned __int16 *a3,
        _WORD *a4,
        WCHAR *a5,
        int a6,
        int a7,
        HANDLE *a8)
{
  unsigned int v8; // esi
  WCHAR *lpCurrentDirectory; // r13
  int v12; // r12d
  unsigned __int16 *v13; // rbx
  unsigned __int16 *v14; // r15
  signed int LastError; // eax
  int v16; // eax
  int v17; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v19; // rax
  HANDLE hToken; // [rsp+60h] [rbp-A0h] BYREF
  int v22; // [rsp+68h] [rbp-98h] BYREF
  LPVOID Environment; // [rsp+70h] [rbp-90h] BYREF
  int TokenInformation; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v25; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 *v26; // [rsp+88h] [rbp-78h] BYREF
  _WORD *v27; // [rsp+90h] [rbp-70h]
  HANDLE *v28; // [rsp+98h] [rbp-68h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+A0h] [rbp-60h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Buffer[264]; // [rsp+130h] [rbp+30h] BYREF

  v8 = 0;
  lpCurrentDirectory = a5;
  TokenInformation = a2;
  v27 = a4;
  v28 = a8;
  v12 = 0;
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  hToken = 0;
  Environment = 0;
  v13 = 0;
  v25 = 0;
  v22 = 0;
  v26 = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v14 = 0;
  if ( !DuplicateTokenEx(hExistingToken, 0x2000000u, 0, SecurityImpersonation, TokenPrimary, &hToken) )
    goto LABEL_2;
  StartupInfo.cb = 104;
  StartupInfo.wShowWindow = 5;
  StartupInfo.lpDesktop = 0;
  if ( !CreateEnvironmentBlock(&Environment, hToken, 0) || !GetSystemDirectoryW(Buffer, 0x104u) )
    goto LABEL_2;
  if ( !a5 || !*a5 )
    lpCurrentDirectory = Buffer;
  if ( !a3 || !*a3 )
  {
    v16 = STRAPI_Format(&v25, L"%s\\%s", Buffer, L"cmd.exe");
    v8 = v16;
    if ( v16 < 0 )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v16);
      v13 = v25;
      goto LABEL_29;
    }
    v13 = v25;
    v12 = 1;
    a3 = v25;
  }
  if ( v27 && *v27 )
  {
    v17 = STRAPI_Format(&v26, L"\"%s\" %s", a3, v27);
    v8 = v17;
    if ( v17 < 0 )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v17);
      v14 = v26;
      goto LABEL_29;
    }
    v14 = v26;
  }
  if ( SetTokenInformation(hToken, TokenSessionId, &TokenInformation, 4u)
    && (v22 = 1, SetTokenInformation(hToken, TokenUIAccess, &v22, 4u))
    && CreateProcessAsUserW(
         hToken,
         a3,
         v14,
         0,
         0,
         0,
         (16 * v12) | 0x400,
         Environment,
         lpCurrentDirectory,
         &StartupInfo,
         &ProcessInformation) )
  {
    if ( v28 )
      *v28 = ProcessInformation.hProcess;
    else
      CloseHandle(ProcessInformation.hProcess);
    CloseHandle(ProcessInformation.hThread);
  }
  else
  {
LABEL_2:
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v8 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
  }
LABEL_29:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v8);
  if ( v14 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v14 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( Environment )
  {
    DestroyEnvironmentBlock(Environment);
    Environment = 0;
  }
  if ( hToken )
  {
    CloseHandle(hToken);
    hToken = 0;
  }
  if ( v13 )
  {
    v19 = GetProcessHeap();
    HeapFree(v19, 0, v13 - 2);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v8;
}

```

## disassembly

```asm
0x14000ac50  push    rbp
0x14000ac52  push    rbx
0x14000ac53  push    rsi
0x14000ac54  push    rdi
0x14000ac55  push    r12
0x14000ac57  push    r13
0x14000ac59  push    r14
0x14000ac5b  push    r15
0x14000ac5d  lea     rbp, [rsp-258h]
0x14000ac65  sub     rsp, 358h
0x14000ac6c  mov     rax, cs:__security_cookie
0x14000ac73  xor     rax, rsp
0x14000ac76  mov     [rbp+290h+var_50], rax
0x14000ac7d  mov     rax, [rbp+290h+arg_38]
0x14000ac84  xor     esi, esi
0x14000ac86  mov     r13, [rbp+290h+arg_20]
0x14000ac8d  mov     r14, r8
0x14000ac90  mov     rdi, rcx
0x14000ac93  mov     [rsp+390h+TokenInformation], edx
0x14000ac97  xor     edx, edx; Val
0x14000ac99  mov     [rbp+290h+var_300], r9
0x14000ac9d  lea     r8d, [rsi+68h]; Size
0x14000aca1  mov     [rbp+290h+var_2F8], rax
0x14000aca5  lea     rcx, [rbp+290h+StartupInfo]; void *
0x14000aca9  mov     r12d, esi
0x14000acac  call    memset_0
0x14000acb1  xor     eax, eax
0x14000acb3  mov     [rsp+390h+hToken], rsi
0x14000acb8  mov     qword ptr [rbp+290h+ProcessInformation.dwProcessId], rax
0x14000acbc  lea     r9d, [rsi+2]; ImpersonationLevel
0x14000acc0  lea     rax, [rsp+390h+hToken]
0x14000acc5  mov     [rsp+390h+Environment], rsi
0x14000acca  xorps   xmm0, xmm0
0x14000accd  mov     [rsp+390h+phNewToken], rax; phNewToken
0x14000acd2  mov     ebx, esi
0x14000acd4  mov     [rsp+390h+TokenType], 1; TokenType
0x14000acdc  xor     r8d, r8d; lpTokenAttributes
0x14000acdf  mov     [rbp+290h+var_310], rbx
0x14000ace3  mov     edx, 2000000h; dwDesiredAccess
0x14000ace8  mov     [rsp+390h+var_328], esi
0x14000acec  mov     rcx, rdi; hExistingToken
0x14000acef  mov     [rbp+290h+var_308], rsi
0x14000acf3  movups  xmmword ptr [rbp+290h+ProcessInformation.hProcess], xmm0
0x14000acf7  mov     r15d, esi
0x14000acfa  call    cs:__imp_DuplicateTokenEx
0x14000ad01  nop     dword ptr [rax+rax+00h]
0x14000ad06  xor     edi, edi
0x14000ad08  test    eax, eax
0x14000ad0a  jnz     short loc_14000AD3C
0x14000ad0c  call    cs:__imp_GetLastError
0x14000ad13  nop     dword ptr [rax+rax+00h]
0x14000ad18  mov     esi, eax
0x14000ad1a  test    eax, eax
0x14000ad1c  jnz     short loc_14000AD25
0x14000ad1e  mov     esi, 80004005h
0x14000ad23  jmp     short loc_14000AD30
0x14000ad25  jle     short loc_14000AD30
0x14000ad27  movzx   esi, ax
0x14000ad2a  or      esi, 80070000h
0x14000ad30  mov     ecx, esi
0x14000ad32  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000ad37  jmp     loc_14000AF01
0x14000ad3c  mov     rdx, [rsp+390h+hToken]; hToken
0x14000ad41  lea     rcx, [rsp+390h+Environment]; lpEnvironment
0x14000ad46  mov     eax, 5
0x14000ad4b  mov     [rbp+290h+StartupInfo.cb], 68h ; 'h'
0x14000ad52  xor     r8d, r8d; bInherit
0x14000ad55  mov     [rbp+290h+StartupInfo.wShowWindow], ax
0x14000ad59  mov     [rbp+290h+StartupInfo.lpDesktop], rdi
0x14000ad5d  call    cs:__imp_CreateEnvironmentBlock
0x14000ad64  nop     dword ptr [rax+rax+00h]
0x14000ad69  test    eax, eax
0x14000ad6b  jz      short loc_14000AD0C
0x14000ad6d  mov     edx, 104h; uSize
0x14000ad72  lea     rcx, [rbp+290h+Buffer]; lpBuffer
0x14000ad76  call    cs:__imp_GetSystemDirectoryW
0x14000ad7d  nop     dword ptr [rax+rax+00h]
0x14000ad82  test    eax, eax
0x14000ad84  jz      short loc_14000AD0C
0x14000ad86  test    r13, r13
0x14000ad89  jz      short loc_14000AD92
0x14000ad8b  cmp     di, [r13+0]
0x14000ad90  jnz     short loc_14000AD96
0x14000ad92  lea     r13, [rbp+290h+Buffer]
0x14000ad96  test    r14, r14
0x14000ad99  jz      short loc_14000ADA1
0x14000ad9b  cmp     di, [r14]
0x14000ad9f  jnz     short loc_14000ADDF
0x14000ada1  lea     r9, aCmdExe; "cmd.exe"
0x14000ada8  lea     r8, [rbp+290h+Buffer]
0x14000adac  lea     rdx, aSS_0; "%s\\%s"
0x14000adb3  lea     rcx, [rbp+290h+var_310]; unsigned __int16 **
0x14000adb7  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x14000adbc  mov     esi, eax
0x14000adbe  test    eax, eax
0x14000adc0  jns     short loc_14000ADD2
0x14000adc2  mov     ecx, eax
0x14000adc4  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000adc9  mov     rbx, [rbp+290h+var_310]
0x14000adcd  jmp     loc_14000AF01
0x14000add2  mov     rbx, [rbp+290h+var_310]
0x14000add6  mov     r12d, 1
0x14000addc  mov     r14, rbx
0x14000addf  mov     rax, [rbp+290h+var_300]
0x14000ade3  test    rax, rax
0x14000ade6  jz      short loc_14000AE1D
0x14000ade8  cmp     [rax], di
0x14000adeb  jz      short loc_14000AE1D
0x14000aded  mov     r9, rax
0x14000adf0  lea     rdx, aSS_6; "\"%s\" %s"
0x14000adf7  mov     r8, r14
0x14000adfa  lea     rcx, [rbp+290h+var_308]; unsigned __int16 **
0x14000adfe  call    ?STRAPI_Format@@YAJPEAPEAGPEBGZZ; STRAPI_Format(ushort * *,ushort const *,...)
0x14000ae03  mov     esi, eax
0x14000ae05  test    eax, eax
0x14000ae07  jns     short loc_14000AE19
0x14000ae09  mov     ecx, eax
0x14000ae0b  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000ae10  mov     r15, [rbp+290h+var_308]
0x14000ae14  jmp     loc_14000AF01
0x14000ae19  mov     r15, [rbp+290h+var_308]
0x14000ae1d  mov     rcx, [rsp+390h+hToken]; TokenHandle
0x14000ae22  lea     r8, [rsp+390h+TokenInformation]; TokenInformation
0x14000ae27  mov     r9d, 4; TokenInformationLength
0x14000ae2d  lea     edx, [r9+8]; TokenInformationClass
0x14000ae31  call    cs:__imp_SetTokenInformation
0x14000ae38  nop     dword ptr [rax+rax+00h]
0x14000ae3d  test    eax, eax
0x14000ae3f  jz      loc_14000AD0C
0x14000ae45  mov     rcx, [rsp+390h+hToken]; TokenHandle
0x14000ae4a  lea     r8, [rsp+390h+var_328]; TokenInformation
0x14000ae4f  mov     r9d, 4; TokenInformationLength
0x14000ae55  mov     [rsp+390h+var_328], 1
0x14000ae5d  lea     edx, [r9+16h]; TokenInformationClass
0x14000ae61  call    cs:__imp_SetTokenInformation
0x14000ae68  nop     dword ptr [rax+rax+00h]
0x14000ae6d  test    eax, eax
0x14000ae6f  jz      loc_14000AD0C
0x14000ae75  mov     rax, [rsp+390h+Environment]
0x14000ae7a  lea     rcx, [rbp+290h+ProcessInformation]
0x14000ae7e  mov     [rsp+390h+lpProcessInformation], rcx; lpProcessInformation
0x14000ae83  xor     r9d, r9d; lpProcessAttributes
0x14000ae86  lea     rcx, [rbp+290h+StartupInfo]
0x14000ae8a  shl     r12d, 4
0x14000ae8e  mov     [rsp+390h+lpStartupInfo], rcx; lpStartupInfo
0x14000ae93  bts     r12d, 0Ah
0x14000ae98  mov     rcx, [rsp+390h+hToken]; hToken
0x14000ae9d  mov     r8, r15; lpCommandLine
0x14000aea0  mov     [rsp+390h+lpCurrentDirectory], r13; lpCurrentDirectory
0x14000aea5  mov     rdx, r14; lpApplicationName
0x14000aea8  mov     [rsp+390h+lpEnvironment], rax; lpEnvironment
0x14000aead  mov     [rsp+390h+dwCreationFlags], r12d; dwCreationFlags
0x14000aeb2  mov     dword ptr [rsp+390h+phNewToken], edi; bInheritHandles
0x14000aeb6  mov     qword ptr [rsp+390h+TokenType], rdi; lpThreadAttributes
0x14000aebb  call    cs:__imp_CreateProcessAsUserW
0x14000aec2  nop     dword ptr [rax+rax+00h]
0x14000aec7  test    eax, eax
0x14000aec9  jz      loc_14000AD0C
0x14000aecf  mov     rcx, [rbp+290h+var_2F8]
0x14000aed3  test    rcx, rcx
0x14000aed6  jz      short loc_14000AEE1
0x14000aed8  mov     rax, [rbp+290h+ProcessInformation.hProcess]
0x14000aedc  mov     [rcx], rax
0x14000aedf  jmp     short loc_14000AEF1
0x14000aee1  mov     rcx, [rbp+290h+ProcessInformation.hProcess]; hObject
0x14000aee5  call    cs:__imp_CloseHandle
0x14000aeec  nop     dword ptr [rax+rax+00h]
0x14000aef1  mov     rcx, [rbp+290h+ProcessInformation.hThread]; hObject
0x14000aef5  call    cs:__imp_CloseHandle
0x14000aefc  nop     dword ptr [rax+rax+00h]
0x14000af01  mov     ecx, esi
0x14000af03  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000af08  test    r15, r15
0x14000af0b  jz      short loc_14000AF35
0x14000af0d  call    cs:__imp_GetProcessHeap
0x14000af14  nop     dword ptr [rax+rax+00h]
0x14000af19  lea     r8, [r15-4]; lpMem
0x14000af1d  xor     edx, edx; dwFlags
0x14000af1f  mov     rcx, rax; hHeap
0x14000af22  call    cs:__imp_HeapFree
0x14000af29  nop     dword ptr [rax+rax+00h]
0x14000af2e  xor     ecx, ecx
0x14000af30  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000af35  mov     rcx, [rsp+390h+Environment]; lpEnvironment
0x14000af3a  test    rcx, rcx
0x14000af3d  jz      short loc_14000AF50
0x14000af3f  call    cs:__imp_DestroyEnvironmentBlock
0x14000af46  nop     dword ptr [rax+rax+00h]
0x14000af4b  mov     [rsp+390h+Environment], rdi
0x14000af50  mov     rcx, [rsp+390h+hToken]; hObject
0x14000af55  test    rcx, rcx
0x14000af58  jz      short loc_14000AF6B
0x14000af5a  call    cs:__imp_CloseHandle
0x14000af61  nop     dword ptr [rax+rax+00h]
0x14000af66  mov     [rsp+390h+hToken], rdi
0x14000af6b  test    rbx, rbx
0x14000af6e  jz      short loc_14000AF98
0x14000af70  call    cs:__imp_GetProcessHeap
0x14000af77  nop     dword ptr [rax+rax+00h]
0x14000af7c  lea     r8, [rbx-4]; lpMem
0x14000af80  xor     edx, edx; dwFlags
0x14000af82  mov     rcx, rax; hHeap
0x14000af85  call    cs:__imp_HeapFree
0x14000af8c  nop     dword ptr [rax+rax+00h]
0x14000af91  xor     ecx, ecx
0x14000af93  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000af98  mov     eax, esi
0x14000af9a  mov     rcx, [rbp+290h+var_50]
0x14000afa1  xor     rcx, rsp; StackCookie
0x14000afa4  call    __security_check_cookie
0x14000afa9  add     rsp, 358h
0x14000afb0  pop     r15
0x14000afb2  pop     r14
0x14000afb4  pop     r13
0x14000afb6  pop     r12
0x14000afb8  pop     rdi
0x14000afb9  pop     rsi
0x14000afba  pop     rbx
0x14000afbb  pop     rbp
0x14000afbc  retn
```
