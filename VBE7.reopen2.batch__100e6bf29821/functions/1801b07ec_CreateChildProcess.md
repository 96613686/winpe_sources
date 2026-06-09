# CreateChildProcess

- ea: `0x1801b07ec`
- end: `0x1801b0b23`
- name: `CreateChildProcess`
- size: `823`
- prototype: `__int64 __fastcall(int, int, int, int, LPPROCESS_INFORMATION)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1801b0398`

## callees

- `0x1800fc26c`
- `0x180142894`
- `0x180142948`
- `0x1801487bc`
- `0x1801b07ec`
- `0x180379520`

## import_xrefs

- `KERNEL32!DuplicateHandle` at `0x1801b091d`
- `KERNEL32!DuplicateHandle` at `0x1801b091d`
- `KERNEL32!GetLastError` at `0x1801b08a1`
- `KERNEL32!GetLastError` at `0x1801b0932`
- `KERNEL32!GetLastError` at `0x1801b08a1`
- `KERNEL32!GetLastError` at `0x1801b0932`
- `KERNEL32!CloseHandle` at `0x1801b092c`
- `KERNEL32!CloseHandle` at `0x1801b09fa`
- `KERNEL32!CloseHandle` at `0x1801b0a08`
- `KERNEL32!CloseHandle` at `0x1801b092c`
- `KERNEL32!CloseHandle` at `0x1801b09fa`
- `KERNEL32!CloseHandle` at `0x1801b0a08`
- `KERNEL32!CreateFileA` at `0x1801b088e`
- `KERNEL32!CreateFileA` at `0x1801b088e`
- `KERNEL32!MultiByteToWideChar` at `0x1801b0ad3`
- `KERNEL32!MultiByteToWideChar` at `0x1801b0ad3`
- `KERNEL32!CreateProcessA` at `0x1801b09e8`
- `KERNEL32!CreateProcessA` at `0x1801b09e8`
- `KERNEL32!GetCurrentProcess` at `0x1801b08db`
- `KERNEL32!GetCurrentProcess` at `0x1801b08db`

## pseudocode

```c
__int64 __fastcall CreateChildProcess(
        const CHAR *a1,
        CHAR *a2,
        const CHAR *a3,
        void *a4,
        LPPROCESS_INFORMATION lpProcessInformation)
{
  signed int LastError; // [rsp+58h] [rbp-1A8h]
  signed int v7; // [rsp+60h] [rbp-1A0h]
  __int64 v10; // [rsp+70h] [rbp-190h]
  HANDLE hObject; // [rsp+78h] [rbp-188h]
  BOOL v12; // [rsp+80h] [rbp-180h]
  char v13[128]; // [rsp+90h] [rbp-170h] BYREF
  unsigned int v14; // [rsp+110h] [rbp-F0h]
  LPWSTR lpWideCharStr; // [rsp+118h] [rbp-E8h]
  HANDLE TargetHandle; // [rsp+120h] [rbp-E0h] BYREF
  HANDLE hSourceProcessHandle; // [rsp+128h] [rbp-D8h]
  const CHAR *v18; // [rsp+130h] [rbp-D0h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+138h] [rbp-C8h] BYREF
  _BYTE v20[32]; // [rsp+150h] [rbp-B0h] BYREF
  struct _STARTUPINFOA StartupInfo; // [rsp+170h] [rbp-90h] BYREF

  SecurityAttributes.nLength = 24;
  SecurityAttributes.lpSecurityDescriptor = 0;
  SecurityAttributes.bInheritHandle = 1;
  memset(&StartupInfo, 0, sizeof(StartupInfo));
  StartupInfo.cb = 104;
  hObject = CreateFileA("NUL", 0x80000000, 3u, &SecurityAttributes, 4u, 0, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  if ( hObject == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
    else
      return (unsigned int)LastError;
  }
  else
  {
    hSourceProcessHandle = GetCurrentProcess();
    if ( DuplicateHandle(hSourceProcessHandle, a4, hSourceProcessHandle, &TargetHandle, 2u, 1, 2u) )
    {
      StartupInfo.dwFlags = 257;
      StartupInfo.lpReserved = 0;
      StartupInfo.hStdInput = hObject;
      StartupInfo.hStdOutput = a4;
      StartupInfo.hStdError = TargetHandle;
      StartupInfo.wShowWindow = 0;
      v12 = CreateProcessA(a1, a2, 0, 0, 1, 0x8000000u, 0, a3, &StartupInfo, lpProcessInformation);
      CloseHandle(hObject);
      CloseHandle(TargetHandle);
      if ( v12 )
      {
        return 0;
      }
      else
      {
        v18 = a1;
        v10 = -1;
        do
          ++v10;
        while ( v18[v10] );
        TempBufferEx::TempBufferEx((TempBufferEx *)v20, 0x78u, 0, 2LL * (unsigned int)(v10 + 1), v13, 0, 1u);
        lpWideCharStr = (LPWSTR)NAMMGR::Pgenproj((NAMMGR *)v20);
        if ( lpWideCharStr )
          MultiByteToWideChar(0, 0, a1, v10 + 1, lpWideCharStr, v10 + 1);
        SaveErrText(0xE357u, lpWideCharStr, 0);
        v14 = -2146770089;
        TempBufferEx::~TempBufferEx((TempBufferEx *)v20);
        return v14;
      }
    }
    else
    {
      CloseHandle(hObject);
      v7 = GetLastError();
      if ( v7 > 0 )
        return (unsigned __int16)v7 | 0x80070000;
      else
        return (unsigned int)v7;
    }
  }
}

```

## disassembly

```asm
0x1801b07ec  mov     [rsp-8+hSourceHandle], r9
0x1801b07f1  mov     [rsp-8+arg_10], r8
0x1801b07f6  mov     [rsp-8+lpCommandLine], rdx
0x1801b07fb  mov     [rsp-8+lpApplicationName], rcx
0x1801b0800  push    rbp
0x1801b0801  mov     rbp, rsp
0x1801b0804  push    rdi
0x1801b0805  sub     rsp, 1F8h
0x1801b080c  mov     rax, cs:__security_cookie
0x1801b0813  xor     rax, rsp
0x1801b0816  mov     [rbp+var_20], rax
0x1801b081a  mov     [rsp+200h+SecurityAttributes.nLength], 18h
0x1801b0825  mov     [rsp+200h+SecurityAttributes.lpSecurityDescriptor], 0
0x1801b0831  mov     [rsp+200h+SecurityAttributes.bInheritHandle], 1
0x1801b083c  lea     rax, [rsp+200h+StartupInfo]
0x1801b0844  mov     rdi, rax
0x1801b0847  xor     eax, eax
0x1801b0849  mov     ecx, 68h ; 'h'
0x1801b084e  rep stosb
0x1801b0850  mov     [rsp+200h+StartupInfo.cb], 68h ; 'h'
0x1801b085b  mov     [rsp+200h+hTemplateFile], 0FFFFFFFFFFFFFFFFh; hTemplateFile
0x1801b0864  mov     [rsp+200h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x1801b086c  mov     [rsp+200h+dwCreationDisposition], 4; dwCreationDisposition
0x1801b0874  lea     r9, [rsp+200h+SecurityAttributes]; lpSecurityAttributes
0x1801b087c  mov     r8d, 3; dwShareMode
0x1801b0882  mov     edx, 80000000h; dwDesiredAccess
0x1801b0887  lea     rcx, aNul; "NUL"
0x1801b088e  call    cs:__imp_CreateFileA
0x1801b0894  mov     [rsp+200h+hObject], rax
0x1801b0899  cmp     [rsp+200h+hObject], 0FFFFFFFFFFFFFFFFh
0x1801b089f  jnz     short loc_1801B08DB
0x1801b08a1  call    cs:__imp_GetLastError
0x1801b08a7  mov     [rsp+200h+var_1A8], eax
0x1801b08ab  cmp     [rsp+200h+var_1A8], 0
0x1801b08b0  jg      short loc_1801B08BC
0x1801b08b2  mov     eax, [rsp+200h+var_1A8]
0x1801b08b6  mov     [rsp+200h+var_198], eax
0x1801b08ba  jmp     short loc_1801B08D2
0x1801b08bc  mov     eax, [rsp+200h+var_1A8]
0x1801b08c0  and     eax, 0FFFFh
0x1801b08c5  or      eax, 70000h
0x1801b08ca  bts     eax, 1Fh
0x1801b08ce  mov     [rsp+200h+var_198], eax
0x1801b08d2  mov     eax, [rsp+200h+var_198]
0x1801b08d6  jmp     loc_1801B0B0D
0x1801b08db  call    cs:__imp_GetCurrentProcess
0x1801b08e1  mov     [rsp+200h+hSourceProcessHandle], rax
0x1801b08e9  mov     dword ptr [rsp+200h+hTemplateFile], 2; dwOptions
0x1801b08f1  mov     [rsp+200h+dwFlagsAndAttributes], 1; bInheritHandle
0x1801b08f9  mov     [rsp+200h+dwCreationDisposition], 2; dwDesiredAccess
0x1801b0901  lea     r9, [rsp+200h+TargetHandle]; lpTargetHandle
0x1801b0909  mov     r8, [rsp+200h+hSourceProcessHandle]; hTargetProcessHandle
0x1801b0911  mov     rdx, [rbp+hSourceHandle]; hSourceHandle
0x1801b0915  mov     rcx, [rsp+200h+hSourceProcessHandle]; hSourceProcessHandle
0x1801b091d  call    cs:__imp_DuplicateHandle
0x1801b0923  test    eax, eax
0x1801b0925  jnz     short loc_1801B096C
0x1801b0927  mov     rcx, [rsp+200h+hObject]; hObject
0x1801b092c  call    cs:__imp_CloseHandle
0x1801b0932  call    cs:__imp_GetLastError
0x1801b0938  mov     [rsp+200h+var_1A0], eax
0x1801b093c  cmp     [rsp+200h+var_1A0], 0
0x1801b0941  jg      short loc_1801B094D
0x1801b0943  mov     eax, [rsp+200h+var_1A0]
0x1801b0947  mov     [rsp+200h+var_194], eax
0x1801b094b  jmp     short loc_1801B0963
0x1801b094d  mov     eax, [rsp+200h+var_1A0]
0x1801b0951  and     eax, 0FFFFh
0x1801b0956  or      eax, 70000h
0x1801b095b  bts     eax, 1Fh
0x1801b095f  mov     [rsp+200h+var_194], eax
0x1801b0963  mov     eax, [rsp+200h+var_194]
0x1801b0967  jmp     loc_1801B0B0D
0x1801b096c  mov     [rbp+StartupInfo.dwFlags], 101h
0x1801b0973  mov     [rsp+200h+StartupInfo.lpReserved], 0
0x1801b097f  mov     rax, [rsp+200h+hObject]
0x1801b0984  mov     [rbp+StartupInfo.hStdInput], rax
0x1801b0988  mov     rax, [rbp+hSourceHandle]
0x1801b098c  mov     [rbp+StartupInfo.hStdOutput], rax
0x1801b0990  mov     rax, [rsp+200h+TargetHandle]
0x1801b0998  mov     [rbp+StartupInfo.hStdError], rax
0x1801b099c  xor     eax, eax
0x1801b099e  mov     [rbp+StartupInfo.wShowWindow], ax
0x1801b09a2  mov     rax, [rbp+arg_20]
0x1801b09a6  mov     [rsp+200h+lpProcessInformation], rax; lpProcessInformation
0x1801b09ab  lea     rax, [rsp+200h+StartupInfo]
0x1801b09b3  mov     [rsp+200h+lpStartupInfo], rax; lpStartupInfo
0x1801b09b8  mov     rax, [rbp+arg_10]
0x1801b09bc  mov     [rsp+200h+lpCurrentDirectory], rax; lpCurrentDirectory
0x1801b09c1  mov     [rsp+200h+hTemplateFile], 0; lpEnvironment
0x1801b09ca  mov     [rsp+200h+dwFlagsAndAttributes], 8000000h; dwCreationFlags
0x1801b09d2  mov     [rsp+200h+dwCreationDisposition], 1; bInheritHandles
0x1801b09da  xor     r9d, r9d; lpThreadAttributes
0x1801b09dd  xor     r8d, r8d; lpProcessAttributes
0x1801b09e0  mov     rdx, [rbp+lpCommandLine]; lpCommandLine
0x1801b09e4  mov     rcx, [rbp+lpApplicationName]; lpApplicationName
0x1801b09e8  call    cs:__imp_CreateProcessA
0x1801b09ee  mov     [rsp+200h+var_180], eax
0x1801b09f5  mov     rcx, [rsp+200h+hObject]; hObject
0x1801b09fa  call    cs:__imp_CloseHandle
0x1801b0a00  mov     rcx, [rsp+200h+TargetHandle]; hObject
0x1801b0a08  call    cs:__imp_CloseHandle
0x1801b0a0e  cmp     [rsp+200h+var_180], 0
0x1801b0a16  jz      short loc_1801B0A1F
0x1801b0a18  xor     eax, eax
0x1801b0a1a  jmp     loc_1801B0B0D
0x1801b0a1f  mov     rax, [rbp+lpApplicationName]
0x1801b0a23  mov     [rsp+200h+var_D0], rax
0x1801b0a2b  mov     [rsp+200h+var_190], 0FFFFFFFFFFFFFFFFh
0x1801b0a34  inc     [rsp+200h+var_190]
0x1801b0a39  mov     rax, [rsp+200h+var_D0]
0x1801b0a41  mov     rcx, [rsp+200h+var_190]
0x1801b0a46  cmp     byte ptr [rax+rcx], 0
0x1801b0a4a  jnz     short loc_1801B0A34
0x1801b0a4c  mov     rax, [rsp+200h+var_190]
0x1801b0a51  inc     eax
0x1801b0a53  mov     [rsp+200h+cbMultiByte], eax
0x1801b0a57  mov     eax, [rsp+200h+cbMultiByte]
0x1801b0a5b  shl     rax, 1
0x1801b0a5e  mov     byte ptr [rsp+200h+hTemplateFile], 1; unsigned __int8
0x1801b0a63  mov     qword ptr [rsp+200h+dwFlagsAndAttributes], 0; unsigned __int64 *
0x1801b0a6c  lea     rcx, [rsp+200h+var_170]
0x1801b0a74  mov     qword ptr [rsp+200h+dwCreationDisposition], rcx; char *
0x1801b0a79  mov     r9, rax; unsigned __int64
0x1801b0a7c  xor     r8d, r8d; unsigned __int64
0x1801b0a7f  mov     edx, 78h ; 'x'; unsigned __int64
0x1801b0a84  lea     rcx, [rsp+200h+var_B0]; this
0x1801b0a8c  call    ??0TempBufferEx@@QEAA@_K00PEADPEA_KE@Z; TempBufferEx::TempBufferEx(unsigned __int64,unsigned __int64,unsigned __int64,char *,unsigned __int64 *,uchar)
0x1801b0a91  lea     rcx, [rsp+200h+var_B0]; this
0x1801b0a99  call    ?Pgenproj@NAMMGR@@QEAAPEAVGEN_PROJECT@@XZ; NAMMGR::Pgenproj(void)
0x1801b0a9e  mov     [rsp+200h+lpWideCharStr], rax
0x1801b0aa6  cmp     [rsp+200h+lpWideCharStr], 0
0x1801b0aaf  jz      short loc_1801B0AD9
0x1801b0ab1  mov     eax, [rsp+200h+cbMultiByte]
0x1801b0ab5  mov     [rsp+200h+dwFlagsAndAttributes], eax; cchWideChar
0x1801b0ab9  mov     rax, [rsp+200h+lpWideCharStr]
0x1801b0ac1  mov     qword ptr [rsp+200h+dwCreationDisposition], rax; lpWideCharStr
0x1801b0ac6  mov     r9d, [rsp+200h+cbMultiByte]; cbMultiByte
0x1801b0acb  mov     r8, [rbp+lpApplicationName]; lpMultiByteStr
0x1801b0acf  xor     edx, edx; dwFlags
0x1801b0ad1  xor     ecx, ecx; CodePage
0x1801b0ad3  call    cs:__imp_MultiByteToWideChar
0x1801b0ad9  xor     r8d, r8d; wchar_t *
0x1801b0adc  mov     rdx, [rsp+200h+lpWideCharStr]; wchar_t *
0x1801b0ae4  mov     ecx, 0E357h; unsigned int
0x1801b0ae9  call    ?SaveErrText@@YAXIPEA_W0@Z; SaveErrText(uint,wchar_t *,wchar_t *)
0x1801b0aee  mov     [rsp+200h+var_F0], 800AE357h
0x1801b0af9  lea     rcx, [rsp+200h+var_B0]; this
0x1801b0b01  call    ??1TempBufferEx@@QEAA@XZ; TempBufferEx::~TempBufferEx(void)
0x1801b0b06  mov     eax, [rsp+200h+var_F0]
0x1801b0b0d  mov     rcx, [rbp+var_20]
0x1801b0b11  xor     rcx, rsp; StackCookie
0x1801b0b14  call    __security_check_cookie
0x1801b0b19  add     rsp, 1F8h
0x1801b0b20  pop     rdi
0x1801b0b21  pop     rbp
0x1801b0b22  retn
```
