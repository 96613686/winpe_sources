# GetCurrentUserToken(void * &,bool &)

- ea: `0x1800a9a90`
- end: `0x1800a9d41`
- name: `?GetCurrentUserToken@@YAKAEAPEAXAEA_N@Z`
- size: `689`
- prototype: `unsigned int __fastcall(PHANDLE TokenHandle, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1800a99b0`
- `0x180155b64`

## callees

- `0x180025a18`
- `0x1800a9a90`
- `0x1800a9d48`
- `0x1800b7800`
- `0x180146568`
- `0x18015238c`
- `0x180157094`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x1800a9cb3`
- `ADVAPI32!SetThreadToken` at `0x1800a9cd9`
- `ADVAPI32!SetThreadToken` at `0x1800a9cb3`
- `ADVAPI32!SetThreadToken` at `0x1800a9cd9`
- `ADVAPI32!OpenThreadToken` at `0x1800a9b5e`
- `ADVAPI32!OpenThreadToken` at `0x1800a9bc5`
- `ADVAPI32!OpenThreadToken` at `0x1800a9b5e`
- `ADVAPI32!OpenThreadToken` at `0x1800a9bc5`
- `ADVAPI32!OpenProcessToken` at `0x1800a9b88`
- `ADVAPI32!OpenProcessToken` at `0x1800a9c01`
- `ADVAPI32!OpenProcessToken` at `0x1800a9b88`
- `ADVAPI32!OpenProcessToken` at `0x1800a9c01`
- `KERNEL32!CloseHandle` at `0x1800a9ca0`
- `KERNEL32!CloseHandle` at `0x1800a9cca`
- `KERNEL32!CloseHandle` at `0x1800a9ca0`
- `KERNEL32!CloseHandle` at `0x1800a9cca`
- `KERNEL32!LeaveCriticalSection` at `0x1800a9af1`
- `KERNEL32!LeaveCriticalSection` at `0x1800a9af1`
- `KERNEL32!GetLastError` at `0x1800a9b68`
- `KERNEL32!GetLastError` at `0x1800a9c7b`
- `KERNEL32!GetLastError` at `0x1800a9b68`
- `KERNEL32!GetLastError` at `0x1800a9c7b`
- `KERNEL32!EnterCriticalSection` at `0x1800a9acd`
- `KERNEL32!EnterCriticalSection` at `0x1800a9acd`
- `KERNEL32!GetCurrentThread` at `0x1800a9b4b`
- `KERNEL32!GetCurrentThread` at `0x1800a9bab`
- `KERNEL32!GetCurrentThread` at `0x1800a9b4b`
- `KERNEL32!GetCurrentThread` at `0x1800a9bab`
- `KERNEL32!GetCurrentProcess` at `0x1800a9b79`
- `KERNEL32!GetCurrentProcess` at `0x1800a9beb`
- `KERNEL32!GetCurrentProcess` at `0x1800a9b79`
- `KERNEL32!GetCurrentProcess` at `0x1800a9beb`
- `KERNEL32!TlsGetValue` at `0x1800a9ade`
- `KERNEL32!TlsGetValue` at `0x1800a9ade`

## pseudocode

```c
__int64 __fastcall GetCurrentUserToken(PHANDLE TokenHandle, bool *a2)
{
  int v2; // eax
  bool *v3; // rsi
  int v5; // ecx
  unsigned int v6; // ebx
  struct IUnknownVtbl *lpVtbl; // rax
  DWORD LastError; // ebx
  HANDLE v10; // rax
  HANDLE v11; // rax
  HANDLE CurrentThread; // rax
  HANDLE CurrentProcess; // rax
  bool *v14; // rdx
  BOOL v15; // ebx
  void *TokenHandlea; // [rsp+80h] [rbp+18h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp+20h] BYREF

  v2 = dword_180306D40;
  v3 = a2;
  if ( dword_180306D40 != -1 )
    goto LABEL_2;
  TokenHandlea = (void *)-1LL;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 4u, 1, &TokenHandlea) )
  {
    if ( !SetThreadToken(0, 0) )
      ExitProcessIfNotClient();
  }
  else
  {
    TokenHandlea = (void *)-1LL;
  }
  hObject = 0;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, &hObject) )
  {
    v15 = IsLocalSystemToken(hObject);
    CloseHandle(hObject);
    dword_180306D40 = v15;
  }
  else if ( g_dmDiagnosticMode )
  {
    DebugString(
      9,
      0,
      0,
      L"Could not determine if the process is running as local system or not.",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      L"(NULL)",
      0,
      0);
  }
  LOBYTE(a2) = (_BYTE)TokenHandlea;
  if ( TokenHandlea != (void *)-1LL )
  {
    if ( !SetThreadToken(0, TokenHandlea) )
      ExitProcessIfNotClient();
    CloseHandle(TokenHandlea);
  }
  v2 = dword_180306D40;
  if ( dword_180306D40 != -1 )
  {
LABEL_2:
    v5 = g_scServerContext;
    v6 = 0;
    if ( g_scServerContext == 2 || v2 == 1 )
    {
      EnterCriticalSection(&g_csImpersonationLock);
      if ( g_dwImpersonationSlot != -1 )
        v6 = (unsigned int)TlsGetValue(g_dwImpersonationSlot) >> 29;
      LeaveCriticalSection(&g_csImpersonationLock);
      v5 = g_scServerContext;
    }
    *v3 = 0;
    if ( v5 == 2 && v6 == 1 )
    {
      CCoImpersonate::CCoImpersonate((CCoImpersonate *)&TokenHandlea, (bool)a2);
      LastError = OpenUserToken(TokenHandle, v14);
      if ( !LastError )
        *v3 = 1;
      CCoImpersonate::~CCoImpersonate((CCoImpersonate *)&TokenHandlea);
      return LastError;
    }
    lpVtbl = (struct IUnknownVtbl *)Token;
    if ( !Token && v5 == 2 )
    {
      if ( !CMsiTransaction::m_pMsiTransaction )
      {
        *TokenHandle = 0;
        goto LABEL_14;
      }
      lpVtbl = CMsiTransaction::m_pMsiTransaction[5].lpVtbl;
    }
    LastError = 0;
    *TokenHandle = lpVtbl;
    if ( lpVtbl )
      return LastError;
LABEL_14:
    LastError = 0;
    v10 = GetCurrentThread();
    if ( !OpenThreadToken(v10, 0xCu, 1, TokenHandle) )
    {
      LastError = GetLastError();
      if ( LastError == 1008 )
      {
        LastError = 0;
        v11 = GetCurrentProcess();
        if ( !OpenProcessToken(v11, 0xCu, TokenHandle) )
          LastError = GetLastError();
      }
    }
    if ( !LastError )
      *v3 = 1;
    return LastError;
  }
  return 5;
}

```

## disassembly

```asm
0x1800a9a90  mov     [rsp+arg_0], rbx
0x1800a9a95  mov     [rsp+arg_8], rsi
0x1800a9a9a  push    rdi
0x1800a9a9b  sub     rsp, 60h
0x1800a9a9f  mov     eax, cs:dword_180306D40
0x1800a9aa5  mov     rsi, rdx
0x1800a9aa8  mov     rdi, rcx
0x1800a9aab  cmp     eax, 0FFFFFFFFh
0x1800a9aae  jz      loc_1800A9B9F
0x1800a9ab4  mov     ecx, cs:?g_scServerContext@@3W4scEnum@@A; scEnum g_scServerContext
0x1800a9aba  xor     ebx, ebx
0x1800a9abc  cmp     ecx, 2
0x1800a9abf  jz      short loc_1800A9AC6
0x1800a9ac1  cmp     eax, 1
0x1800a9ac4  jnz     short loc_1800A9AFD
0x1800a9ac6  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800a9acd  call    cs:__imp_EnterCriticalSection
0x1800a9ad3  mov     ecx, cs:?g_dwImpersonationSlot@@3KA; dwTlsIndex
0x1800a9ad9  cmp     ecx, 0FFFFFFFFh
0x1800a9adc  jz      short loc_1800A9AEA
0x1800a9ade  call    cs:__imp_TlsGetValue
0x1800a9ae4  mov     rbx, rax
0x1800a9ae7  shr     ebx, 1Dh
0x1800a9aea  lea     rcx, ?g_csImpersonationLock@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800a9af1  call    cs:__imp_LeaveCriticalSection
0x1800a9af7  mov     ecx, cs:?g_scServerContext@@3W4scEnum@@A; scEnum g_scServerContext
0x1800a9afd  mov     byte ptr [rsi], 0
0x1800a9b00  cmp     ecx, 2
0x1800a9b03  jz      loc_1800A9C42
0x1800a9b09  mov     rax, cs:Token
0x1800a9b10  test    rax, rax
0x1800a9b13  jnz     short loc_1800A9B1A
0x1800a9b15  cmp     ecx, 2
0x1800a9b18  jz      short loc_1800A9B36
0x1800a9b1a  xor     ebx, ebx
0x1800a9b1c  mov     [rdi], rax
0x1800a9b1f  test    rax, rax
0x1800a9b22  jz      short loc_1800A9B49
0x1800a9b24  mov     eax, ebx
0x1800a9b26  mov     rbx, [rsp+68h+arg_0]
0x1800a9b2b  mov     rsi, [rsp+68h+arg_8]
0x1800a9b30  add     rsp, 60h
0x1800a9b34  pop     rdi
0x1800a9b35  retn
0x1800a9b36  mov     rax, cs:?m_pMsiTransaction@CMsiTransaction@@0PEAV1@EA; CMsiTransaction * CMsiTransaction::m_pMsiTransaction
0x1800a9b3d  test    rax, rax
0x1800a9b40  jnz     loc_1800A9D38
0x1800a9b46  mov     [rdi], rax
0x1800a9b49  xor     ebx, ebx
0x1800a9b4b  call    cs:__imp_GetCurrentThread
0x1800a9b51  mov     r9, rdi; TokenHandle
0x1800a9b54  lea     edx, [rbx+0Ch]; DesiredAccess
0x1800a9b57  mov     rcx, rax; ThreadHandle
0x1800a9b5a  lea     r8d, [rbx+1]; OpenAsSelf
0x1800a9b5e  call    cs:__imp_OpenThreadToken
0x1800a9b64  test    eax, eax
0x1800a9b66  jnz     short loc_1800A9B96
0x1800a9b68  call    cs:__imp_GetLastError
0x1800a9b6e  mov     ebx, eax
0x1800a9b70  cmp     eax, 3F0h
0x1800a9b75  jnz     short loc_1800A9B96
0x1800a9b77  xor     ebx, ebx
0x1800a9b79  call    cs:__imp_GetCurrentProcess
0x1800a9b7f  mov     r8, rdi; TokenHandle
0x1800a9b82  lea     edx, [rbx+0Ch]; DesiredAccess
0x1800a9b85  mov     rcx, rax; ProcessHandle
0x1800a9b88  call    cs:__imp_OpenProcessToken
0x1800a9b8e  test    eax, eax
0x1800a9b90  jz      loc_1800A9C7B
0x1800a9b96  test    ebx, ebx
0x1800a9b98  jnz     short loc_1800A9B24
0x1800a9b9a  mov     byte ptr [rsi], 1
0x1800a9b9d  jmp     short loc_1800A9B24
0x1800a9b9f  mov     [rsp+68h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1800a9bab  call    cs:__imp_GetCurrentThread
0x1800a9bb1  mov     edx, 4; DesiredAccess
0x1800a9bb6  lea     r9, [rsp+68h+TokenHandle]; TokenHandle
0x1800a9bbe  mov     rcx, rax; ThreadHandle
0x1800a9bc1  lea     r8d, [rdx-3]; OpenAsSelf
0x1800a9bc5  call    cs:__imp_OpenThreadToken
0x1800a9bcb  test    eax, eax
0x1800a9bcd  jnz     loc_1800A9CD5
0x1800a9bd3  mov     [rsp+68h+TokenHandle], 0FFFFFFFFFFFFFFFFh
0x1800a9bdf  mov     [rsp+68h+hObject], 0
0x1800a9beb  call    cs:__imp_GetCurrentProcess
0x1800a9bf1  lea     r8, [rsp+68h+hObject]; TokenHandle
0x1800a9bf9  mov     edx, 8; DesiredAccess
0x1800a9bfe  mov     rcx, rax; ProcessHandle
0x1800a9c01  call    cs:__imp_OpenProcessToken
0x1800a9c07  test    eax, eax
0x1800a9c09  jnz     short loc_1800A9C88
0x1800a9c0b  cmp     cs:?g_dmDiagnosticMode@@3HA, eax; int g_dmDiagnosticMode
0x1800a9c11  jnz     loc_1800A9CF1
0x1800a9c17  mov     rdx, [rsp+68h+TokenHandle]; Token
0x1800a9c1f  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x1800a9c23  jnz     loc_1800A9CB1
0x1800a9c29  mov     eax, cs:dword_180306D40
0x1800a9c2f  cmp     eax, 0FFFFFFFFh
0x1800a9c32  jnz     loc_1800A9AB4
0x1800a9c38  mov     eax, 5
0x1800a9c3d  jmp     loc_1800A9B26
0x1800a9c42  cmp     ebx, 1
0x1800a9c45  jnz     loc_1800A9B09
0x1800a9c4b  lea     rcx, [rsp+68h+TokenHandle]; this
0x1800a9c53  call    ??0CCoImpersonate@@QEAA@_N@Z; CCoImpersonate::CCoImpersonate(bool)
0x1800a9c58  mov     rcx, rdi; TokenHandle
0x1800a9c5b  call    ?OpenUserToken@@YAKAEAPEAXPEA_N@Z; OpenUserToken(void * &,bool *)
0x1800a9c60  mov     ebx, eax
0x1800a9c62  test    eax, eax
0x1800a9c64  jnz     short loc_1800A9C69
0x1800a9c66  mov     byte ptr [rsi], 1
0x1800a9c69  lea     rcx, [rsp+68h+TokenHandle]; this
0x1800a9c71  call    ??1CCoImpersonate@@QEAA@XZ; CCoImpersonate::~CCoImpersonate(void)
0x1800a9c76  jmp     loc_1800A9B24
0x1800a9c7b  call    cs:__imp_GetLastError
0x1800a9c81  mov     ebx, eax
0x1800a9c83  jmp     loc_1800A9B96
0x1800a9c88  mov     rcx, [rsp+68h+hObject]; void *
0x1800a9c90  call    ?IsLocalSystemToken@@YA_NPEAX@Z; IsLocalSystemToken(void *)
0x1800a9c95  mov     rcx, [rsp+68h+hObject]; hObject
0x1800a9c9d  movzx   ebx, al
0x1800a9ca0  call    cs:__imp_CloseHandle
0x1800a9ca6  mov     cs:dword_180306D40, ebx
0x1800a9cac  jmp     loc_1800A9C17
0x1800a9cb1  xor     ecx, ecx; Thread
0x1800a9cb3  call    cs:__imp_SetThreadToken
0x1800a9cb9  test    eax, eax
0x1800a9cbb  jnz     short loc_1800A9CC2
0x1800a9cbd  call    ExitProcessIfNotClient
0x1800a9cc2  mov     rcx, [rsp+68h+TokenHandle]; hObject
0x1800a9cca  call    cs:__imp_CloseHandle
0x1800a9cd0  jmp     loc_1800A9C29
0x1800a9cd5  xor     edx, edx; Token
0x1800a9cd7  xor     ecx, ecx; Thread
0x1800a9cd9  call    cs:__imp_SetThreadToken
0x1800a9cdf  test    eax, eax
0x1800a9ce1  jnz     loc_1800A9BDF
0x1800a9ce7  call    ExitProcessIfNotClient
0x1800a9cec  jmp     loc_1800A9BDF
0x1800a9cf1  lea     rax, aNull; "(NULL)"
0x1800a9cf8  xor     edx, edx; unsigned __int16
0x1800a9cfa  mov     [rsp+68h+var_10], rdx; void *
0x1800a9cff  lea     r9, aCouldNotDeterm_1; "Could not determine if the process is r"...
0x1800a9d06  mov     [rsp+68h+var_18], edx; unsigned int
0x1800a9d0a  xor     r8d, r8d; int
0x1800a9d0d  mov     [rsp+68h+var_20], rax; unsigned __int16 *
0x1800a9d12  mov     [rsp+68h+var_28], rax; unsigned __int16 *
0x1800a9d17  lea     ecx, [rdx+9]; int
0x1800a9d1a  mov     [rsp+68h+var_30], rax; unsigned __int16 *
0x1800a9d1f  mov     [rsp+68h+var_38], rax; unsigned __int16 *
0x1800a9d24  mov     [rsp+68h+var_40], rax; unsigned __int16 *
0x1800a9d29  mov     [rsp+68h+var_48], rax; unsigned __int16 *
0x1800a9d2e  call    ?DebugString@@YAXHGHPEBG000000KPEAX@Z; DebugString(int,ushort,int,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong,void *)
0x1800a9d33  jmp     loc_1800A9C17
0x1800a9d38  mov     rax, [rax+28h]
0x1800a9d3c  jmp     loc_1800A9B1A
```
