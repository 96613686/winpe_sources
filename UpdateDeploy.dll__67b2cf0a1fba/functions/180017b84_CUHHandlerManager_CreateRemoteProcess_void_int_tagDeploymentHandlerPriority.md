# CUHHandlerManager::CreateRemoteProcess(void *,int,tagDeploymentHandlerPriority)

- ea: `0x180017b84`
- end: `0x18001811e`
- name: `?CreateRemoteProcess@CUHHandlerManager@@AEAAJPEAXHW4tagDeploymentHandlerPriority@@@Z`
- size: `1434`
- prototype: `__int64 __fastcall(__int64, void *, unsigned int, DWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001858c`

## callees

- `0x180001cb8`
- `0x180002214`
- `0x180003180`
- `0x180009438`
- `0x18000dce4`
- `0x18000dd60`
- `0x1800110fc`
- `0x180016f8c`
- `0x180017b84`
- `0x180019024`
- `0x180019c38`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180018084`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180018084`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180017ea5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180017ea5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180017de3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180017de3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017c79`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017f6d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017c79`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180017f6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017f45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017fe6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018112`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017f45`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180017fe6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018112`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018005`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180018005`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180017f5c`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x180017f5c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180017dc2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180017dc2`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180017ced`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180017ced`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017d15`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017d90`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017d15`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180017d90`

## string_xrefs

- `0x180017c52`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x180017d68`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x180017d9f`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x180017dfa`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x180017f11`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x180017f87`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x180018095`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x1800180f4`: `C:\__w\1\s\src\Client\UpdateDeployment\Lib\uhmgr.cpp`
- `0x1800180bb`: `0x%08x: ERROR: Remote update handler container process created (PID: %d), but exited before signaling event`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CUHHandlerManager::CreateRemoteProcess(__int64 a1, void *a2, unsigned int a3, DWORD a4)
{
  PSID *v6; // rbx
  DWORD LastError; // edi
  __int64 v8; // r14
  __int64 v9; // rdx
  HANDLE *v10; // r15
  const char *v11; // r9
  __int64 v12; // rdx
  DWORD v13; // r9d
  HANDLE EventW; // rax
  HINSTANCE v15; // rcx
  int started; // eax
  __int64 v17; // rdx
  __int64 v18; // r9
  DWORD v19; // edi
  const char *v20; // r9
  DWORD v21; // edi
  wil::details::in1diag3 *v22; // rcx
  __int64 v23; // rdx
  int v24; // eax
  void (__fastcall ***v25)(_QWORD, __int64); // rcx
  unsigned int TokenType; // [rsp+20h] [rbp-E0h]
  _QWORD v29[7]; // [rsp+68h] [rbp-98h] BYREF
  DWORD ExitCode; // [rsp+A0h] [rbp-60h] BYREF
  DWORD ReturnLength; // [rsp+A4h] [rbp-5Ch] BYREF
  struct IContextCallback *v32; // [rsp+A8h] [rbp-58h] BYREF
  int v33; // [rsp+B0h] [rbp-50h] BYREF
  int v34; // [rsp+B4h] [rbp-4Ch] BYREF
  DWORD v35; // [rsp+B8h] [rbp-48h] BYREF
  void (__fastcall ***v36)(_QWORD, __int64); // [rsp+C0h] [rbp-40h]
  tagComCallData v37; // [rsp+C8h] [rbp-38h] BYREF
  HANDLE Handles[3]; // [rsp+D8h] [rbp-28h] BYREF
  WCHAR Filename[264]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+258h]

  ExitCode = a4;
  v6 = 0;
  *(__m128i *)Handles = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  ReturnLength = 0;
  v35 = 0;
  v34 = 1;
  v33 = 0;
  v32 = 0;
  v37 = 0;
  v36 = 0;
  v29[5] = 1;
  v29[0] = &v33;
  v29[1] = a1;
  v29[2] = &v32;
  v29[3] = &v37;
  v29[4] = &v34;
  if ( !*(_BYTE *)(a1 + 40) )
  {
    LastError = -2145124348;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x226,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
      (const char *)0x80240004LL,
      TokenType);
    goto LABEL_56;
  }
  v8 = a1 + 56;
  v29[6] = a1 + 56;
  if ( a1 != -56 )
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 64));
  if ( *(_QWORD *)(a1 + 328) )
  {
    LastError = -2145116157;
    v9 = 555;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
      (const char *)LastError,
      TokenType);
    goto LABEL_69;
  }
  if ( *(_QWORD *)(a1 + 352) )
  {
    v9 = 556;
LABEL_11:
    LastError = -2145120257;
    goto LABEL_20;
  }
  v10 = (HANDLE *)(a1 + 312);
  if ( *(_QWORD *)(a1 + 312) )
  {
    v9 = 557;
    goto LABEL_11;
  }
  if ( a2 )
  {
    if ( !DuplicateTokenEx(a2, 0x20008u, 0, SecurityIdentification, TokenImpersonation, (PHANDLE)(a1 + 312)) )
    {
      v12 = 567;
LABEL_24:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v12,
                    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
                    v11);
      goto LABEL_69;
    }
    if ( GetTokenInformation(*v10, TokenUser, 0, 0, &ReturnLength) )
    {
      LastError = -2145120257;
      v9 = 569;
      goto LABEL_20;
    }
    v13 = ReturnLength;
    if ( ReturnLength )
    {
      v6 = (PSID *)SafeSusAllocArray(ReturnLength, 1u);
      LastError = v6 == 0 ? 0x8007000E : 0;
      if ( !v6 )
      {
        v9 = 570;
        goto LABEL_20;
      }
      v13 = ReturnLength;
    }
    if ( !GetTokenInformation(*v10, TokenUser, v6, v13, &v35) )
    {
      v12 = 571;
      goto LABEL_24;
    }
    if ( !ConvertSidToStringSidW(*v6, (LPWSTR *)(a1 + 352)) )
    {
      v12 = 573;
      goto LABEL_24;
    }
  }
  EventW = CreateEventW(0, 0, 0, 0);
  *(_QWORD *)(a1 + 328) = EventW;
  if ( !EventW )
  {
    v12 = 577;
    goto LABEL_24;
  }
  started = RegisterDeploymentProxyStubCLSIDs(v15, (unsigned int *)(a1 + 380), (struct IUnknown **)(a1 + 576));
  LastError = started;
  if ( started < 0 )
  {
    v17 = 583;
LABEL_41:
    v18 = (unsigned int)started;
    goto LABEL_42;
  }
  if ( v32 )
  {
    ((void (__fastcall *)(struct IContextCallback *))v32->lpVtbl->Release)(v32);
    v32 = 0;
  }
  started = CUHHandlerManager::StartJITCOMServer((CUHHandlerManager *)a1, &v32, &v37);
  LastError = started;
  if ( started < 0 )
  {
    v17 = 587;
    goto LABEL_41;
  }
  v33 = 1;
  if ( *(_QWORD *)(a1 + 320) )
  {
    LastError = -2145120257;
    v18 = 2149847039LL;
    v17 = 590;
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
      (const char *)v18,
      TokenType);
    goto LABEL_69;
  }
  if ( GetModuleFileNameW(g_hInstance, Filename, 0x105u) >= 0x105 )
  {
    LastError = -2147024774;
    v18 = 2147942522LL;
    v17 = 593;
    goto LABEL_42;
  }
  TokenType = a1 + 384;
  started = CreateHandlerProcess(Filename, a2, a3, ExitCode);
  LastError = started;
  if ( started < 0 )
  {
    v17 = 603;
    goto LABEL_41;
  }
  Handles[0] = *(HANDLE *)(a1 + 320);
  Handles[1] = *(HANDLE *)(a1 + 328);
  if ( v8 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
  v19 = WaitForMultipleObjects(2u, Handles, 0, 0x927C0u);
  if ( v8 )
    EnterCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
  if ( v19 )
  {
    v21 = v19 - 1;
    if ( v21 )
    {
      v22 = retaddr;
      if ( v21 == 257 )
      {
        v24 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x270,
                (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
                (const char *)0x102,
                TokenType);
LABEL_66:
        LastError = v24;
        goto LABEL_69;
      }
      v23 = 618;
LABEL_65:
      v24 = wil::details::in1diag3::Return_GetLastError(
              v22,
              (void *)v23,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
              v20);
      goto LABEL_66;
    }
    WUTrace(0, 0, 0x1000000, 5);
    v34 = 0;
  }
  else
  {
    ExitCode = 0;
    if ( !GetExitCodeProcess(*(HANDLE *)(a1 + 320), &ExitCode) )
    {
      v22 = retaddr;
      v23 = 630;
      goto LABEL_65;
    }
    WUTrace(0, 0, 0x1000000, 1);
    LastError = ExitCode;
    if ( (ExitCode & 0x80000000) != 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x27D,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\UpdateDeployment\\Lib\\uhmgr.cpp",
        (const char *)ExitCode,
        0);
LABEL_69:
      if ( v8 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
      goto LABEL_56;
    }
  }
  if ( v8 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v8 + 8));
  LastError = 0;
LABEL_56:
  wil::details::lambda_call__lambda_5cfca67a974a7add9dec3db2742dcc1c___::_lambda_call__lambda_5cfca67a974a7add9dec3db2742dcc1c___(v29);
  v25 = v36;
  v36 = 0;
  if ( v25 )
    (**v25)(v25, 1);
  if ( v32 )
  {
    ((void (__fastcall *)(struct IContextCallback *))v32->lpVtbl->Release)(v32);
    v32 = 0;
  }
  if ( v6 )
    SusFree(v6);
  return LastError;
}

```

## disassembly

```asm
0x180017b84  push    rbp
0x180017b86  push    rbx
0x180017b87  push    rsi
0x180017b88  push    rdi
0x180017b89  push    r12
0x180017b8b  push    r13
0x180017b8d  push    r14
0x180017b8f  push    r15
0x180017b91  lea     rbp, [rsp-218h]
0x180017b99  sub     rsp, 318h
0x180017ba0  mov     rax, cs:__security_cookie
0x180017ba7  xor     rax, rsp
0x180017baa  mov     [rbp+250h+var_50], rax
0x180017bb1  mov     [rbp+250h+ExitCode], r9d
0x180017bb5  mov     [rsp+350h+var_300], r8d
0x180017bba  mov     r13, rdx
0x180017bbd  mov     rsi, rcx
0x180017bc0  xor     r12d, r12d
0x180017bc3  mov     ebx, r12d
0x180017bc6  mov     [rsp+350h+var_2F0], rbx
0x180017bcb  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x180017bd3  movdqu  xmmword ptr [rbp+250h+Handles], xmm0
0x180017bd8  mov     [rbp+250h+ReturnLength], r12d
0x180017bdc  mov     [rbp+250h+var_298], r12d
0x180017be0  lea     edi, [r12+1]
0x180017be5  mov     [rbp+250h+var_29C], edi
0x180017be8  mov     [rbp+250h+var_2A0], r12d
0x180017bec  mov     [rbp+250h+var_2A8], r12
0x180017bf0  xorps   xmm0, xmm0
0x180017bf3  movups  xmmword ptr [rbp+250h+var_288.dwDispid], xmm0
0x180017bf7  mov     [rbp+250h+var_290], r12
0x180017bfb  mov     [rsp+350h+hObject], 0FFFFFFFFFFFFFFFFh
0x180017c04  movups  [rsp+350h+var_2E8], xmm0
0x180017c09  movups  [rsp+350h+var_2D8], xmm0
0x180017c0e  movups  [rbp+250h+var_2C8], xmm0
0x180017c12  lea     rax, [rbp+250h+var_2A0]
0x180017c16  mov     qword ptr [rsp+350h+var_2E8], rax
0x180017c1b  mov     qword ptr [rsp+350h+var_2E8+8], rcx
0x180017c20  lea     rax, [rbp+250h+var_2A8]
0x180017c24  mov     qword ptr [rsp+350h+var_2D8], rax
0x180017c29  lea     rax, [rbp+250h+var_288]
0x180017c2d  mov     qword ptr [rbp+250h+var_2D8+8], rax
0x180017c31  lea     rax, [rbp+250h+var_29C]
0x180017c35  mov     qword ptr [rbp+250h+var_2C8], rax
0x180017c39  mov     byte ptr [rbp+250h+var_2C8+8], dil
0x180017c3d  cmp     [rcx+28h], r12b
0x180017c41  jnz     short loc_180017C68
0x180017c43  mov     rcx, [rbp+258h]; this
0x180017c4a  mov     edi, 80240004h
0x180017c4f  mov     r9d, edi; char *
0x180017c52  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180017c59  mov     edx, 226h; void *
0x180017c5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017c63  jmp     loc_180017FEF
0x180017c68  lea     r14, [rcx+38h]
0x180017c6c  mov     [rbp+250h+var_2B8], r14
0x180017c70  test    r14, r14
0x180017c73  jz      short loc_180017C80
0x180017c75  lea     rcx, [r14+8]; lpCriticalSection
0x180017c79  call    cs:__imp_EnterCriticalSection
0x180017c7f  nop
0x180017c80  cmp     [rsi+148h], r12
0x180017c87  jz      short loc_180017C98
0x180017c89  mov     edi, 80242003h
0x180017c8e  mov     edx, 22Bh
0x180017c93  jmp     loc_180017D5E
0x180017c98  lea     r12, [rsi+160h]
0x180017c9f  cmp     qword ptr [r12], 0
0x180017ca4  jz      short loc_180017CAD
0x180017ca6  mov     edx, 22Ch
0x180017cab  jmp     short loc_180017CBF
0x180017cad  lea     r15, [rsi+138h]
0x180017cb4  cmp     qword ptr [r15], 0
0x180017cb8  jz      short loc_180017CC9
0x180017cba  mov     edx, 22Dh
0x180017cbf  mov     edi, 80240FFFh
0x180017cc4  jmp     loc_180017D5E
0x180017cc9  test    r13, r13
0x180017ccc  jz      loc_180017DD6
0x180017cd2  mov     [rsp+350h+phNewToken], r15; phNewToken
0x180017cd7  mov     [rsp+350h+TokenType], 2; TokenType
0x180017cdf  mov     r9d, edi; ImpersonationLevel
0x180017ce2  xor     r8d, r8d; lpTokenAttributes
0x180017ce5  mov     edx, 20008h; dwDesiredAccess
0x180017cea  mov     rcx, r13; hExistingToken
0x180017ced  call    cs:__imp_DuplicateTokenEx
0x180017cf3  test    eax, eax
0x180017cf5  jnz     short loc_180017D01
0x180017cf7  mov     edx, 237h
0x180017cfc  jmp     loc_180017D9F
0x180017d01  lea     rax, [rbp+250h+ReturnLength]
0x180017d05  mov     qword ptr [rsp+350h+TokenType], rax; int
0x180017d0a  xor     r9d, r9d; TokenInformationLength
0x180017d0d  xor     r8d, r8d; TokenInformation
0x180017d10  mov     edx, edi; TokenInformationClass
0x180017d12  mov     rcx, [r15]; TokenHandle
0x180017d15  call    cs:__imp_GetTokenInformation
0x180017d1b  test    eax, eax
0x180017d1d  jz      short loc_180017D2B
0x180017d1f  mov     edi, 80240FFFh
0x180017d24  mov     edx, 239h
0x180017d29  jmp     short loc_180017D5E
0x180017d2b  mov     r9d, [rbp+250h+ReturnLength]
0x180017d2f  mov     ecx, r9d; unsigned __int64
0x180017d32  test    r9d, r9d
0x180017d35  jz      short loc_180017D7F
0x180017d37  mov     rdx, rdi; unsigned __int64
0x180017d3a  call    ?SafeSusAllocArray@@YAPEAX_K0@Z; SafeSusAllocArray(unsigned __int64,unsigned __int64)
0x180017d3f  mov     rbx, rax
0x180017d42  mov     [rsp+350h+var_2F0], rax
0x180017d47  neg     rax
0x180017d4a  sbb     edi, edi
0x180017d4c  not     edi
0x180017d4e  and     edi, 8007000Eh
0x180017d54  test    rbx, rbx
0x180017d57  jnz     short loc_180017D76
0x180017d59  mov     edx, 23Ah; void *
0x180017d5e  mov     rcx, [rbp+258h]; this
0x180017d65  mov     r9d, edi; char *
0x180017d68  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180017d6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017d74  jmp     short loc_180017DB4
0x180017d76  mov     r9d, [rbp+250h+ReturnLength]; TokenInformationLength
0x180017d7a  mov     edi, 1
0x180017d7f  lea     rax, [rbp+250h+var_298]
0x180017d83  mov     qword ptr [rsp+350h+TokenType], rax; ReturnLength
0x180017d88  mov     r8, rbx; TokenInformation
0x180017d8b  mov     edx, edi; TokenInformationClass
0x180017d8d  mov     rcx, [r15]; TokenHandle
0x180017d90  call    cs:__imp_GetTokenInformation
0x180017d96  test    eax, eax
0x180017d98  jnz     short loc_180017DBC
0x180017d9a  mov     edx, 23Bh; void *
0x180017d9f  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180017da6  mov     rcx, [rbp+258h]; this
0x180017dad  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180017db2  mov     edi, eax
0x180017db4  xor     r12d, r12d
0x180017db7  jmp     loc_180017F25
0x180017dbc  mov     rdx, r12; StringSid
0x180017dbf  mov     rcx, [rbx]; Sid
0x180017dc2  call    cs:__imp_ConvertSidToStringSidW
0x180017dc8  xor     r12d, r12d
0x180017dcb  test    eax, eax
0x180017dcd  jnz     short loc_180017DD9
0x180017dcf  mov     edx, 23Dh
0x180017dd4  jmp     short loc_180017DFA
0x180017dd6  xor     r12d, r12d
0x180017dd9  xor     r9d, r9d; lpName
0x180017ddc  xor     r8d, r8d; bInitialState
0x180017ddf  xor     edx, edx; bManualReset
0x180017de1  xor     ecx, ecx; lpEventAttributes
0x180017de3  call    cs:__imp_CreateEventW
0x180017de9  mov     [rsi+148h], rax
0x180017df0  test    rax, rax
0x180017df3  jnz     short loc_180017E14
0x180017df5  mov     edx, 241h; void *
0x180017dfa  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180017e01  mov     rcx, [rbp+258h]; this
0x180017e08  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180017e0d  mov     edi, eax
0x180017e0f  jmp     loc_180017F25
0x180017e14  lea     r8, [rsi+240h]; struct IUnknown **
0x180017e1b  lea     rdx, [rsi+17Ch]; unsigned int *
0x180017e22  call    ?RegisterDeploymentProxyStubCLSIDs@@YAJPEAUHINSTANCE__@@PEAKPEAPEAUIUnknown@@@Z; RegisterDeploymentProxyStubCLSIDs(HINSTANCE__ *,ulong *,IUnknown * *)
0x180017e27  mov     edi, eax
0x180017e29  test    eax, eax
0x180017e2b  jns     short loc_180017E37
0x180017e2d  mov     edx, 247h
0x180017e32  jmp     loc_180017F0E
0x180017e37  mov     rcx, [rbp+250h+var_2A8]
0x180017e3b  test    rcx, rcx
0x180017e3e  jz      short loc_180017E50
0x180017e40  mov     rax, [rcx]
0x180017e43  mov     rax, [rax+10h]
0x180017e47  call    _guard_dispatch_icall
0x180017e4c  mov     [rbp+250h+var_2A8], r12
0x180017e50  lea     r8, [rbp+250h+var_288]; struct tagComCallData *
0x180017e54  lea     rdx, [rbp+250h+var_2A8]; struct IContextCallback **
0x180017e58  mov     rcx, rsi; this
0x180017e5b  call    ?StartJITCOMServer@CUHHandlerManager@@QEAAJPEAPEAUIContextCallback@@PEAUtagComCallData@@@Z; CUHHandlerManager::StartJITCOMServer(IContextCallback * *,tagComCallData *)
0x180017e60  mov     edi, eax
0x180017e62  test    eax, eax
0x180017e64  jns     short loc_180017E70
0x180017e66  mov     edx, 24Bh
0x180017e6b  jmp     loc_180017F0E
0x180017e70  mov     [rbp+250h+var_2A0], 1
0x180017e77  lea     r15, [rsi+140h]
0x180017e7e  cmp     [r15], r12
0x180017e81  jz      short loc_180017E92
0x180017e83  mov     edi, 80240FFFh
0x180017e88  mov     r9d, edi
0x180017e8b  mov     edx, 24Eh
0x180017e90  jmp     short loc_180017F11
0x180017e92  mov     edi, 105h
0x180017e97  mov     r8d, edi; nSize
0x180017e9a  lea     rdx, [rbp+250h+Filename]; lpFilename
0x180017e9e  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hModule
0x180017ea5  call    cs:__imp_GetModuleFileNameW
0x180017eab  cmp     eax, edi
0x180017ead  jb      short loc_180017EBE
0x180017eaf  mov     edi, 8007007Ah
0x180017eb4  mov     r9d, edi
0x180017eb7  mov     edx, 251h
0x180017ebc  jmp     short loc_180017F11
0x180017ebe  lea     rax, [rsi+158h]
0x180017ec5  lea     rcx, [rsi+180h]
0x180017ecc  lea     rdx, [rsp+350h+hObject]
0x180017ed1  mov     [rsp+350h+var_310], rdx
0x180017ed6  lea     rdx, [rbp+250h+var_290]
0x180017eda  mov     [rsp+350h+var_318], rdx
0x180017edf  mov     [rsp+350h+var_320], rax
0x180017ee4  mov     [rsp+350h+phNewToken], r15
0x180017ee9  mov     qword ptr [rsp+350h+TokenType], rcx; unsigned int
0x180017eee  mov     r9d, [rbp+250h+ExitCode]
0x180017ef2  mov     r8d, [rsp+350h+var_300]
0x180017ef7  mov     rdx, r13
0x180017efa  lea     rcx, [rbp+250h+Filename]
0x180017efe  call    CreateHandlerProcess
0x180017f03  mov     edi, eax
0x180017f05  test    eax, eax
0x180017f07  jns     short loc_180017F2A
0x180017f09  mov     edx, 25Bh; void *
0x180017f0e  mov     r9d, eax; char *
0x180017f11  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180017f18  mov     rcx, [rbp+258h]; this
0x180017f1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017f24  nop
0x180017f25  jmp     loc_180018105
0x180017f2a  mov     rax, [r15]
0x180017f2d  mov     [rbp+250h+Handles], rax
0x180017f31  mov     rax, [rsi+148h]
0x180017f38  mov     [rbp+250h+Handles+8], rax
0x180017f3c  test    r14, r14
0x180017f3f  jz      short loc_180017F4B
0x180017f41  lea     rcx, [r14+8]; lpCriticalSection
0x180017f45  call    cs:__imp_LeaveCriticalSection
0x180017f4b  mov     r9d, 927C0h; dwMilliseconds
0x180017f51  xor     r8d, r8d; bWaitAll
0x180017f54  lea     rdx, [rbp+250h+Handles]; lpHandles
0x180017f58  lea     ecx, [r8+2]; nCount
0x180017f5c  call    cs:__imp_WaitForMultipleObjects
0x180017f62  mov     edi, eax
0x180017f64  test    r14, r14
0x180017f67  jz      short loc_180017F73
0x180017f69  lea     rcx, [r14+8]; lpCriticalSection
0x180017f6d  call    cs:__imp_EnterCriticalSection
0x180017f73  test    edi, edi
0x180017f75  jz      loc_180018075
0x180017f7b  sub     edi, 1
0x180017f7e  jz      short loc_180017FB5
0x180017f80  mov     rcx, [rbp+258h]; this
0x180017f87  lea     r8, aCW1SSrcClientU_4; "C:\\__w\\1\\s\\src\\Client\\UpdateDeplo"...
0x180017f8e  cmp     edi, 101h
0x180017f94  jz      short loc_180017FA0
0x180017f96  mov     edx, 26Ah
0x180017f9b  jmp     loc_1800180A1
0x180017fa0  mov     r9d, 102h; char *
0x180017fa6  mov     edx, 270h; void *
0x180017fab  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180017fb0  jmp     loc_1800180A6
0x180017fb5  lea     rax, aUhHandlerProce_0; "UH: Handler process successfully launch"...
0x180017fbc  mov     [rsp+350h+phNewToken], rax
0x180017fc1  mov     qword ptr [rsp+350h+TokenType], r12
0x180017fc6  xor     edx, edx
0x180017fc8  xor     ecx, ecx
0x180017fca  lea     r9d, [rdx+5]
0x180017fce  mov     r8d, 1000000h
0x180017fd4  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180017fd9  mov     [rbp+250h+var_29C], r12d
0x180017fdd  test    r14, r14
0x180017fe0  jz      short loc_180017FEC
0x180017fe2  lea     rcx, [r14+8]; lpCriticalSection
0x180017fe6  call    cs:__imp_LeaveCriticalSection
0x180017fec  mov     edi, r12d
0x180017fef  lea     rcx, [rsp+350h+var_2E8]
0x180017ff4  call    wil__details__lambda_call__lambda_5cfca67a974a7add9dec3db2742dcc1c______lambda_call__lambda_5cfca67a974a7add9dec3db2742dcc1c___
0x180017ff9  nop
0x180017ffa  mov     rcx, [rsp+350h+hObject]; hObject
0x180017fff  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180018003  jz      short loc_18001800C
0x180018005  call    cs:__imp_CloseHandle
0x18001800b  nop
0x18001800c  mov     rcx, [rbp+250h+var_290]
0x180018010  mov     [rbp+250h+var_290], r12
0x180018014  test    rcx, rcx
0x180018017  jz      short loc_18001802A
0x180018019  mov     rax, [rcx]
0x18001801c  mov     edx, 1
0x180018021  mov     rax, [rax]
0x180018024  call    _guard_dispatch_icall
0x180018029  nop
0x18001802a  mov     rcx, [rbp+250h+var_2A8]
0x18001802e  test    rcx, rcx
0x180018031  jz      short loc_180018043
0x180018033  mov     rax, [rcx]
0x180018036  mov     rax, [rax+10h]
0x18001803a  call    _guard_dispatch_icall
0x18001803f  mov     [rbp+250h+var_2A8], r12
0x180018043  test    rbx, rbx
  ... truncated ...
```
