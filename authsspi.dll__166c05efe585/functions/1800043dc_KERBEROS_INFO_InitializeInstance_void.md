# KERBEROS_INFO::InitializeInstance(void)

- ea: `0x1800043dc`
- end: `0x180004785`
- name: `?InitializeInstance@KERBEROS_INFO@@QEAAJXZ`
- size: `937`
- prototype: `__int64 __fastcall(KERBEROS_INFO *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180003ed4`

## callees

- `0x1800043dc`
- `0x180008b52`
- `0x180008ba0`

## import_xrefs

- `SspiCli!GetUserNameExW` at `0x180004623`
- `SspiCli!GetUserNameExW` at `0x180004662`
- `SspiCli!GetUserNameExW` at `0x180004699`
- `SspiCli!GetUserNameExW` at `0x1800046d8`
- `SspiCli!GetUserNameExW` at `0x180004623`
- `SspiCli!GetUserNameExW` at `0x180004662`
- `SspiCli!GetUserNameExW` at `0x180004699`
- `SspiCli!GetUserNameExW` at `0x1800046d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800045f0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800045f0`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800045b9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800045b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004483`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000462d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004483`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800044c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800045cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000462d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046e2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004554`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004554`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000445c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18000445c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000446f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18000446f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800044b8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004506`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800044b8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180004506`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000451c`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000452c`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000453c`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000451c`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000452c`
- `api-ms-win-security-base-l1-1-0!IsWellKnownSid` at `0x18000453c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180004568`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180004568`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180004440`
- `iisutil!??0BUFFER@@QEAA@PEAEK@Z` at `0x180004440`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800044d6`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800044d6`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004720`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180004720`
- `iisutil!??0STRU_PATH@@QEAA@G@Z` at `0x18000440b`
- `iisutil!??0STRU_PATH@@QEAA@G@Z` at `0x18000440b`
- `iisutil!??1STRU_PATH@@QEAA@XZ` at `0x180004761`
- `iisutil!??1STRU_PATH@@QEAA@XZ` at `0x180004761`
- `iisutil!?RetrieveSystemDir@STRU_PATH@@QEAAJXZ` at `0x180004584`
- `iisutil!?RetrieveSystemDir@STRU_PATH@@QEAAJXZ` at `0x180004584`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000459f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x18000459f`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180004644`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800046b9`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x180004644`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x1800046b9`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180004674`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180004709`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180004674`
- `iisutil!?SyncWithBuffer@STRU@@QEAAXXZ` at `0x180004709`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180004732`
- `iisutil!?Append@STRU@@QEAAJAEBV1@@Z` at `0x180004732`
- `OLEAUT32!__imp_SysAllocString` at `0x180004745`
- `OLEAUT32!__imp_SysAllocString` at `0x180004745`

## string_xrefs

- `0x180004594`: `\activeds.dll`
- `0x18000473e`: `servicePrincipalName`

## pseudocode

```c
__int64 __fastcall KERBEROS_INFO::InitializeInstance(KERBEROS_INFO *this)
{
  PSID *v2; // rsi
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  signed int SystemDir; // ebx
  HMODULE Library; // rax
  signed int v7; // eax
  FARPROC ProcAddress; // rax
  WCHAR *v9; // rdx
  WCHAR *v10; // rdx
  signed int v11; // eax
  bool v12; // sf
  BSTR v13; // rax
  DWORD TokenInformationLength; // [rsp+30h] [rbp-D0h] BYREF
  ULONG nSize; // [rsp+34h] [rbp-CCh] BYREF
  ULONG v17; // [rsp+38h] [rbp-C8h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v19[32]; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID TokenInformation; // [rsp+68h] [rbp-98h]
  DWORD v21; // [rsp+70h] [rbp-90h]
  _BYTE v22[32]; // [rsp+80h] [rbp-80h] BYREF
  LPCWSTR lpLibFileName; // [rsp+A0h] [rbp-60h]
  unsigned __int8 v24[96]; // [rsp+C0h] [rbp-40h] BYREF

  STRU_PATH::STRU_PATH((STRU_PATH *)v22, 0x5Cu);
  nSize = 0;
  v17 = 0;
  memset_0(v24, 0, 0x58u);
  BUFFER::BUFFER((BUFFER *)v19, v24, 0x58u);
  v2 = (PSID *)TokenInformation;
  TokenInformationLength = v21;
  TokenHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !OpenProcessToken(CurrentProcess, 0x20008u, &TokenHandle) )
    goto LABEL_2;
  if ( GetTokenInformation(TokenHandle, TokenUser, v2, TokenInformationLength, &TokenInformationLength) )
    goto LABEL_9;
  if ( GetLastError() != 122 )
    goto LABEL_2;
  if ( !BUFFER::Resize((BUFFER *)v19, TokenInformationLength) )
  {
    SystemDir = -2147024888;
    goto LABEL_13;
  }
  v2 = (PSID *)TokenInformation;
  if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength) )
  {
LABEL_9:
    SystemDir = 0;
    if ( !IsWellKnownSid(*v2, WinNetworkServiceSid)
      && !IsWellKnownSid(*v2, WinLocalServiceSid)
      && !IsWellKnownSid(*v2, WinLocalSystemSid) )
    {
      *((_DWORD *)this + 1) = 1;
    }
  }
  else
  {
LABEL_2:
    LastError = GetLastError();
    SystemDir = LastError;
    if ( LastError > 0 )
      SystemDir = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_13:
  if ( TokenHandle )
  {
    CloseHandle(TokenHandle);
    TokenHandle = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v19);
  if ( SystemDir >= 0 )
  {
    if ( *((_DWORD *)this + 1) )
    {
      SystemDir = STRU_PATH::RetrieveSystemDir((STRU_PATH *)v22);
      if ( SystemDir >= 0 )
      {
        SystemDir = STRU::Append((STRU *)v22, L"\\activeds.dll");
        if ( SystemDir >= 0 )
        {
          Library = LoadLibraryExW(lpLibFileName, 0, 8u);
          *((_QWORD *)this + 71) = Library;
          if ( !Library )
            goto LABEL_20;
          ProcAddress = GetProcAddress(Library, "ADsGetObject");
          *((_QWORD *)this + 72) = ProcAddress;
          if ( !ProcAddress )
          {
            SystemDir = -2147024769;
            goto LABEL_40;
          }
          v9 = (WCHAR *)*((_QWORD *)this + 5);
          nSize = *((_DWORD *)this + 12) >> 1;
          if ( GetUserNameExW(NameSamCompatible, v9, &nSize) )
            goto LABEL_28;
          if ( GetLastError() != 234 )
            goto LABEL_20;
          SystemDir = STRU::Resize((KERBEROS_INFO *)((char *)this + 8), 2 * nSize);
          if ( SystemDir < 0 )
            goto LABEL_40;
          if ( GetUserNameExW(NameSamCompatible, *((LPWSTR *)this + 5), &nSize) )
          {
LABEL_28:
            STRU::SyncWithBuffer((KERBEROS_INFO *)((char *)this + 8));
            v10 = (WCHAR *)*((_QWORD *)this + 28);
            v17 = *((_DWORD *)this + 58) >> 1;
            if ( !GetUserNameExW(NameFullyQualifiedDN, v10, &v17) )
            {
              if ( GetLastError() != 234 )
                goto LABEL_32;
              SystemDir = STRU::Resize((KERBEROS_INFO *)((char *)this + 192), 2 * v17);
              if ( SystemDir < 0 )
                goto LABEL_40;
              if ( !GetUserNameExW(NameFullyQualifiedDN, *((LPWSTR *)this + 28), &v17) )
              {
LABEL_32:
                v11 = GetLastError();
                v12 = v11 < 0;
                if ( v11 > 0 )
                  v12 = 1;
                if ( v12 )
                {
                  SystemDir = 0;
                  **((_WORD **)this + 28) = 0;
                  *((_DWORD *)this + 60) = 0;
                  goto LABEL_40;
                }
              }
            }
            STRU::SyncWithBuffer((KERBEROS_INFO *)((char *)this + 192));
            SystemDir = STRU::Copy((KERBEROS_INFO *)((char *)this + 376), L"LDAP://");
            if ( SystemDir >= 0 )
            {
              SystemDir = STRU::Append((KERBEROS_INFO *)((char *)this + 376), (KERBEROS_INFO *)((char *)this + 192));
              if ( SystemDir >= 0 )
              {
                v13 = SysAllocString(L"servicePrincipalName");
                *((_QWORD *)this + 70) = v13;
                if ( !v13 )
                  SystemDir = -2147024888;
              }
            }
          }
          else
          {
LABEL_20:
            v7 = GetLastError();
            SystemDir = v7;
            if ( v7 > 0 )
              SystemDir = (unsigned __int16)v7 | 0x80070000;
          }
        }
      }
    }
  }
LABEL_40:
  STRU_PATH::~STRU_PATH((STRU_PATH *)v22);
  return (unsigned int)SystemDir;
}

```

## disassembly

```asm
0x1800043dc  push    rbp
0x1800043de  push    rbx
0x1800043df  push    rsi
0x1800043e0  push    rdi
0x1800043e1  push    r12
0x1800043e3  push    r14
0x1800043e5  lea     rbp, [rsp-38h]
0x1800043ea  sub     rsp, 138h
0x1800043f1  mov     rax, cs:__security_cookie
0x1800043f8  xor     rax, rsp
0x1800043fb  mov     [rbp+60h+var_40], rax
0x1800043ff  mov     rdi, rcx
0x180004402  mov     edx, 5Ch ; '\'
0x180004407  lea     rcx, [rbp+60h+var_E0]
0x18000440b  call    cs:__imp_??0STRU_PATH@@QEAA@G@Z; STRU_PATH::STRU_PATH(ushort)
0x180004411  mov     ebx, 58h ; 'X'
0x180004416  mov     [rsp+160h+nSize], 0
0x18000441e  mov     r8d, ebx; Size
0x180004421  mov     [rsp+160h+var_128], 0
0x180004429  xor     edx, edx; Val
0x18000442b  lea     rcx, [rbp+60h+var_A0]; void *
0x18000442f  call    memset_0
0x180004434  mov     r8d, ebx
0x180004437  lea     rdx, [rbp+60h+var_A0]
0x18000443b  lea     rcx, [rsp+160h+var_118]
0x180004440  call    cs:__imp_??0BUFFER@@QEAA@PEAEK@Z; BUFFER::BUFFER(uchar *,ulong)
0x180004446  mov     eax, [rsp+160h+var_F0]
0x18000444a  mov     rsi, [rsp+160h+TokenInformation]
0x18000444f  mov     [rsp+160h+TokenInformationLength], eax
0x180004453  mov     [rsp+160h+TokenHandle], 0
0x18000445c  call    cs:__imp_GetCurrentProcess
0x180004462  lea     r8, [rsp+160h+TokenHandle]; TokenHandle
0x180004467  mov     edx, 20008h; DesiredAccess
0x18000446c  mov     rcx, rax; ProcessHandle
0x18000446f  call    cs:__imp_OpenProcessToken
0x180004475  lea     r12d, [rbx-57h]
0x180004479  mov     r14d, 80070000h
0x18000447f  test    eax, eax
0x180004481  jnz     short loc_18000449E
0x180004483  call    cs:__imp_GetLastError
0x180004489  mov     ebx, eax
0x18000448b  test    eax, eax
0x18000448d  jle     loc_18000454A
0x180004493  movzx   ebx, ax
0x180004496  or      ebx, r14d
0x180004499  jmp     loc_18000454A
0x18000449e  mov     r9d, [rsp+160h+TokenInformationLength]; TokenInformationLength
0x1800044a3  lea     rax, [rsp+160h+TokenInformationLength]
0x1800044a8  mov     rcx, [rsp+160h+TokenHandle]; TokenHandle
0x1800044ad  mov     r8, rsi; TokenInformation
0x1800044b0  mov     edx, r12d; TokenInformationClass
0x1800044b3  mov     [rsp+160h+ReturnLength], rax; ReturnLength
0x1800044b8  call    cs:__imp_GetTokenInformation
0x1800044be  test    eax, eax
0x1800044c0  jnz     short loc_180004514
0x1800044c2  call    cs:__imp_GetLastError
0x1800044c8  cmp     eax, 7Ah ; 'z'
0x1800044cb  jnz     short loc_180004483
0x1800044cd  mov     edx, [rsp+160h+TokenInformationLength]
0x1800044d1  lea     rcx, [rsp+160h+var_118]
0x1800044d6  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x1800044dc  test    al, al
0x1800044de  jnz     short loc_1800044E7
0x1800044e0  mov     ebx, 80070008h
0x1800044e5  jmp     short loc_18000454A
0x1800044e7  mov     rsi, [rsp+160h+TokenInformation]
0x1800044ec  lea     rax, [rsp+160h+TokenInformationLength]
0x1800044f1  mov     r9d, [rsp+160h+TokenInformationLength]; TokenInformationLength
0x1800044f6  mov     r8, rsi; TokenInformation
0x1800044f9  mov     rcx, [rsp+160h+TokenHandle]; TokenHandle
0x1800044fe  mov     edx, r12d; TokenInformationClass
0x180004501  mov     [rsp+160h+ReturnLength], rax; ReturnLength
0x180004506  call    cs:__imp_GetTokenInformation
0x18000450c  test    eax, eax
0x18000450e  jz      loc_180004483
0x180004514  mov     rcx, [rsi]; pSid
0x180004517  xor     ebx, ebx
0x180004519  lea     edx, [rbx+18h]; WellKnownSidType
0x18000451c  call    cs:__imp_IsWellKnownSid
0x180004522  test    eax, eax
0x180004524  jnz     short loc_18000454A
0x180004526  mov     rcx, [rsi]; pSid
0x180004529  lea     edx, [rbx+17h]; WellKnownSidType
0x18000452c  call    cs:__imp_IsWellKnownSid
0x180004532  test    eax, eax
0x180004534  jnz     short loc_18000454A
0x180004536  mov     rcx, [rsi]; pSid
0x180004539  lea     edx, [rbx+16h]; WellKnownSidType
0x18000453c  call    cs:__imp_IsWellKnownSid
0x180004542  test    eax, eax
0x180004544  jnz     short loc_18000454A
0x180004546  mov     [rdi+4], r12d
0x18000454a  mov     rcx, [rsp+160h+TokenHandle]; hObject
0x18000454f  test    rcx, rcx
0x180004552  jz      short loc_180004563
0x180004554  call    cs:__imp_CloseHandle
0x18000455a  mov     [rsp+160h+TokenHandle], 0
0x180004563  lea     rcx, [rsp+160h+var_118]
0x180004568  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000456e  test    ebx, ebx
0x180004570  js      loc_18000475D
0x180004576  cmp     dword ptr [rdi+4], 0
0x18000457a  jz      loc_18000475D
0x180004580  lea     rcx, [rbp+60h+var_E0]
0x180004584  call    cs:__imp_?RetrieveSystemDir@STRU_PATH@@QEAAJXZ; STRU_PATH::RetrieveSystemDir(void)
0x18000458a  mov     ebx, eax
0x18000458c  test    eax, eax
0x18000458e  js      loc_18000475D
0x180004594  lea     rdx, aActivedsDll; "\\activeds.dll"
0x18000459b  lea     rcx, [rbp+60h+var_E0]
0x18000459f  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800045a5  mov     ebx, eax
0x1800045a7  test    eax, eax
0x1800045a9  js      loc_18000475D
0x1800045af  mov     rcx, [rbp+60h+lpLibFileName]; lpLibFileName
0x1800045b3  xor     edx, edx; hFile
0x1800045b5  lea     r8d, [rdx+8]; dwFlags
0x1800045b9  call    cs:__imp_LoadLibraryExW
0x1800045bf  mov     [rdi+238h], rax
0x1800045c6  test    rax, rax
0x1800045c9  jnz     short loc_1800045E6
0x1800045cb  call    cs:__imp_GetLastError
0x1800045d1  mov     ebx, eax
0x1800045d3  test    eax, eax
0x1800045d5  jle     loc_18000475D
0x1800045db  movzx   ebx, ax
0x1800045de  or      ebx, r14d
0x1800045e1  jmp     loc_18000475D
0x1800045e6  lea     rdx, ProcName; "ADsGetObject"
0x1800045ed  mov     rcx, rax; hModule
0x1800045f0  call    cs:__imp_GetProcAddress
0x1800045f6  mov     [rdi+240h], rax
0x1800045fd  test    rax, rax
0x180004600  jnz     short loc_18000460C
0x180004602  mov     ebx, 8007007Fh
0x180004607  jmp     loc_18000475D
0x18000460c  mov     eax, [rdi+30h]
0x18000460f  lea     r8, [rsp+160h+nSize]; nSize
0x180004614  mov     rdx, [rdi+28h]; lpNameBuffer
0x180004618  mov     ecx, 2; NameFormat
0x18000461d  shr     eax, 1
0x18000461f  mov     [rsp+160h+nSize], eax
0x180004623  call    cs:__imp_GetUserNameExW
0x180004629  test    al, al
0x18000462b  jnz     short loc_180004670
0x18000462d  call    cs:__imp_GetLastError
0x180004633  cmp     eax, 0EAh
0x180004638  jnz     short loc_1800045CB
0x18000463a  mov     edx, [rsp+160h+nSize]
0x18000463e  lea     rcx, [rdi+8]
0x180004642  add     edx, edx
0x180004644  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x18000464a  mov     ebx, eax
0x18000464c  test    eax, eax
0x18000464e  js      loc_18000475D
0x180004654  mov     rdx, [rdi+28h]; lpNameBuffer
0x180004658  lea     r8, [rsp+160h+nSize]; nSize
0x18000465d  mov     ecx, 2; NameFormat
0x180004662  call    cs:__imp_GetUserNameExW
0x180004668  test    al, al
0x18000466a  jz      loc_1800045CB
0x180004670  lea     rcx, [rdi+8]
0x180004674  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18000467a  mov     rdx, [rdi+0E0h]; lpNameBuffer
0x180004681  lea     rsi, [rdi+0C0h]
0x180004688  mov     eax, [rsi+28h]
0x18000468b  lea     r8, [rsp+160h+var_128]; nSize
0x180004690  shr     eax, 1
0x180004692  mov     ecx, r12d; NameFormat
0x180004695  mov     [rsp+160h+var_128], eax
0x180004699  call    cs:__imp_GetUserNameExW
0x18000469f  test    al, al
0x1800046a1  jnz     short loc_180004706
0x1800046a3  call    cs:__imp_GetLastError
0x1800046a9  cmp     eax, 0EAh
0x1800046ae  jnz     short loc_1800046E2
0x1800046b0  mov     edx, [rsp+160h+var_128]
0x1800046b4  mov     rcx, rsi
0x1800046b7  add     edx, edx
0x1800046b9  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x1800046bf  mov     ebx, eax
0x1800046c1  test    eax, eax
0x1800046c3  js      loc_18000475D
0x1800046c9  mov     rdx, [rdi+0E0h]; lpNameBuffer
0x1800046d0  lea     r8, [rsp+160h+var_128]; nSize
0x1800046d5  mov     ecx, r12d; NameFormat
0x1800046d8  call    cs:__imp_GetUserNameExW
0x1800046de  test    al, al
0x1800046e0  jnz     short loc_180004706
0x1800046e2  call    cs:__imp_GetLastError
0x1800046e8  test    eax, eax
0x1800046ea  jle     short loc_1800046F4
0x1800046ec  movzx   eax, ax
0x1800046ef  or      eax, r14d
0x1800046f2  test    eax, eax
0x1800046f4  jns     short loc_180004706
0x1800046f6  mov     rcx, [rsi+20h]
0x1800046fa  xor     eax, eax
0x1800046fc  xor     ebx, ebx
0x1800046fe  mov     [rcx], ax
0x180004701  mov     [rsi+30h], eax
0x180004704  jmp     short loc_18000475D
0x180004706  mov     rcx, rsi
0x180004709  call    cs:__imp_?SyncWithBuffer@STRU@@QEAAXXZ; STRU::SyncWithBuffer(void)
0x18000470f  lea     r14, [rdi+178h]
0x180004716  mov     rcx, r14
0x180004719  lea     rdx, aLdap; "LDAP://"
0x180004720  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180004726  mov     ebx, eax
0x180004728  test    eax, eax
0x18000472a  js      short loc_18000475D
0x18000472c  mov     rdx, rsi
0x18000472f  mov     rcx, r14
0x180004732  call    cs:__imp_?Append@STRU@@QEAAJAEBV1@@Z; STRU::Append(STRU const &)
0x180004738  mov     ebx, eax
0x18000473a  test    eax, eax
0x18000473c  js      short loc_18000475D
0x18000473e  lea     rcx, psz; "servicePrincipalName"
0x180004745  call    cs:__imp_SysAllocString
0x18000474b  test    rax, rax
0x18000474e  mov     [rdi+230h], rax
0x180004755  mov     eax, 80070008h
0x18000475a  cmovz   ebx, eax
0x18000475d  lea     rcx, [rbp+60h+var_E0]
0x180004761  call    cs:__imp_??1STRU_PATH@@QEAA@XZ; STRU_PATH::~STRU_PATH(void)
0x180004767  mov     eax, ebx
0x180004769  mov     rcx, [rbp+60h+var_40]
0x18000476d  xor     rcx, rsp; StackCookie
0x180004770  call    __security_check_cookie
0x180004775  add     rsp, 138h
0x18000477c  pop     r14
0x18000477e  pop     r12
0x180004780  pop     rdi
0x180004781  pop     rsi
0x180004782  pop     rbx
0x180004783  pop     rbp
0x180004784  retn
```
