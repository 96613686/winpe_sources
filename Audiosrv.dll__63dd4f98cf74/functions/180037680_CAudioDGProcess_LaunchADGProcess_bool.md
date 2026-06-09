# CAudioDGProcess::LaunchADGProcess(bool)

- ea: `0x180037680`
- end: `0x18003797e`
- name: `?LaunchADGProcess@CAudioDGProcess@@AEAAJ_N@Z`
- size: `766`
- prototype: `__int64 __fastcall(CAudioDGProcess *__hidden this, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180072c34`

## callees

- `0x18000ad20`
- `0x18001280c`
- `0x180037680`
- `0x180037984`
- `0x180037a10`
- `0x180055d8c`
- `0x180064ebc`
- `0x1800b4c88`
- `0x1800b590c`
- `0x1800cd8d0`
- `0x1800ce774`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180037716`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18003793d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180037716`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18003793d`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180037898`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180037898`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800378f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800378f0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800376dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800376dd`

## string_xrefs

- `0x1800376f1`: `avcore\audiocore\server\audiosrv\dll\adgprocess.cpp`
- `0x1800377de`: `avcore\audiocore\server\audiosrv\dll\adgprocess.cpp`
- `0x1800378a9`: `avcore\audiocore\server\audiosrv\dll\adgprocess.cpp`
- `0x180037918`: `avcore\audiocore\server\audiosrv\dll\adgprocess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CAudioDGProcess::LaunchADGProcess(CAudioDGProcess *this, unsigned __int8 a2)
{
  int v2; // r15d
  size_t v4; // rdx
  const char *v5; // r9
  unsigned int LastError; // ebx
  char *v7; // rcx
  HRESULT ADGProcessSD; // esi
  wchar_t *v10; // r14
  size_t v11; // rbx
  HRESULT v12; // eax
  unsigned __int16 *v13; // rcx
  unsigned __int64 v14; // rdx
  void **v15; // rbx
  __int64 v16; // rdx
  void *v17; // rcx
  bool v18; // cc
  const char *v19; // r9
  size_t bInheritHandles; // [rsp+20h] [rbp-E0h]
  BOOL bInheritHandlesa[2]; // [rsp+20h] [rbp-E0h]
  size_t pcchLength; // [rsp+50h] [rbp-B0h] BYREF
  _SECURITY_ATTRIBUTES ProcessAttributes; // [rsp+58h] [rbp-A8h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+70h] [rbp-90h] BYREF
  CAudioDGProcess *v25; // [rsp+88h] [rbp-78h]
  char v26; // [rsp+90h] [rbp-70h]
  struct _STARTUPINFOW StartupInfo; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Buffer[264]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+258h]

  v2 = a2;
  v25 = this;
  v26 = 1;
  memset_0(Buffer, 0, 0x208u);
  if ( !GetSystemDirectoryW(Buffer, 0x104u) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x62,
                  (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\adgprocess.cpp",
                  v5);
    v7 = (char *)*((_QWORD *)this + 11);
    if ( (unsigned __int64)(v7 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      WaitForSingleObjectEx(v7, 0xFFFFFFFF, 0);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        (char *)this + 88,
        0);
      *((_DWORD *)this + 24) = 0;
    }
    return LastError;
  }
  pcchLength = 0;
  ADGProcessSD = StringLengthWorkerW_0(Buffer, v4, &pcchLength);
  if ( ADGProcessSD < 0 )
  {
    v15 = (void **)((char *)this + 88);
    goto LABEL_24;
  }
  v10 = &Buffer[pcchLength];
  v11 = 260 - pcchLength;
  if ( pcchLength == 260 || pcchLength == 259 )
  {
    ADGProcessSD = -2147024774;
LABEL_10:
    v14 = 2 * v11;
    v13 = v10;
    goto LABEL_11;
  }
  pcchLength = 0;
  v12 = StringCopyWorkerW(v10, v11, &pcchLength, L"\\AUDIODG.EXE", bInheritHandles);
  ADGProcessSD = v12;
  v10 += pcchLength;
  v11 -= pcchLength;
  if ( v12 >= 0 )
    goto LABEL_10;
  v13 = 0;
  v14 = 0;
  if ( v12 == -2147024774 )
    goto LABEL_10;
LABEL_11:
  v15 = (void **)((char *)this + 88);
  if ( ADGProcessSD < 0 )
  {
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x66,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\adgprocess.cpp",
      (const char *)(unsigned int)ADGProcessSD,
      bInheritHandles);
    v17 = *v15;
    v18 = (char *)*v15 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
    goto LABEL_25;
  }
  *(_QWORD *)bInheritHandlesa = *((_QWORD *)this + 15);
  ADGProcessSD = StringCbPrintfW(v13, v14, L" 0x%p 0x%p", *((_QWORD *)this + 14));
  if ( ADGProcessSD < 0 )
  {
    v16 = 104;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v16,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\adgprocess.cpp",
      (const char *)(unsigned int)ADGProcessSD,
      bInheritHandlesa[0]);
LABEL_15:
    v17 = *v15;
    v18 = (char *)*v15 - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL;
LABEL_25:
    if ( v18 )
    {
      WaitForSingleObjectEx(v17, 0xFFFFFFFF, 0);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        v15,
        0);
      *((_DWORD *)this + 24) = 0;
    }
    return (unsigned int)ADGProcessSD;
  }
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  memset(&ProcessAttributes, 0, sizeof(ProcessAttributes));
  ProcessAttributes.nLength = 24;
  ADGProcessSD = CAudioDGProcess::GetADGProcessSD(&ProcessAttributes.lpSecurityDescriptor);
  if ( ADGProcessSD < 0 )
  {
    v16 = 113;
    goto LABEL_14;
  }
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  if ( !CreateProcessW(0, Buffer, &ProcessAttributes, 0, 1, v2 << 18, 0, 0, &StartupInfo, &ProcessInformation) )
  {
    ADGProcessSD = wil::details::in1diag3::Return_GetLastError(
                     retaddr,
                     (void *)0x76,
                     (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\adgprocess.cpp",
                     v19);
    operator delete(ProcessAttributes.lpSecurityDescriptor);
    ProcessAttributes.lpSecurityDescriptor = 0;
    goto LABEL_15;
  }
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    (char *)this + 88,
    ProcessInformation.hProcess);
  *((_DWORD *)this + 24) = ProcessInformation.dwProcessId;
  if ( (unsigned __int64)ProcessInformation.hThread - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    CloseHandle(ProcessInformation.hThread);
    ProcessInformation.hThread = 0;
  }
  operator delete(ProcessAttributes.lpSecurityDescriptor);
  return 0;
}

```

## disassembly

```asm
0x180037680  mov     [rsp-8+arg_8], rbx
0x180037685  mov     [rsp-8+arg_10], rsi
0x18003768a  push    rbp
0x18003768b  push    rdi
0x18003768c  push    r12
0x18003768e  push    r14
0x180037690  push    r15
0x180037692  lea     rbp, [rsp-230h]
0x18003769a  sub     rsp, 330h
0x1800376a1  mov     rax, cs:__security_cookie
0x1800376a8  xor     rax, rsp
0x1800376ab  mov     [rbp+250h+var_30], rax
0x1800376b2  movzx   r15d, dl
0x1800376b6  mov     rdi, rcx
0x1800376b9  mov     [rbp+250h+var_2C8], rcx
0x1800376bd  mov     [rbp+250h+var_2C0], 1
0x1800376c1  xor     edx, edx; Val
0x1800376c3  mov     r8d, 208h; Size
0x1800376c9  lea     rcx, [rbp+250h+Buffer]; void *
0x1800376cd  call    memset_0
0x1800376d2  mov     ebx, 104h
0x1800376d7  mov     edx, ebx; uSize
0x1800376d9  lea     rcx, [rbp+250h+Buffer]; lpBuffer
0x1800376dd  call    cs:__imp_GetSystemDirectoryW
0x1800376e3  xor     r12d, r12d
0x1800376e6  test    eax, eax
0x1800376e8  jnz     short loc_180037732
0x1800376ea  mov     rcx, [rbp+258h]; this
0x1800376f1  lea     r8, aAvcoreAudiocor_21; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800376f8  lea     edx, [rax+62h]; void *
0x1800376fb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180037700  mov     ebx, eax
0x180037702  mov     rcx, [rdi+58h]; hHandle
0x180037706  lea     rdx, [rcx-1]
0x18003770a  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18003770e  ja      short loc_18003772B
0x180037710  xor     r8d, r8d; bAlertable
0x180037713  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180037716  call    cs:__imp_WaitForSingleObjectEx
0x18003771c  xor     edx, edx
0x18003771e  lea     rcx, [rdi+58h]
0x180037722  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180037727  mov     [rdi+60h], r12d
0x18003772b  mov     eax, ebx
0x18003772d  jmp     loc_180037953
0x180037732  mov     [rsp+350h+pcchLength], r12
0x180037737  lea     r8, [rsp+350h+pcchLength]; pcchLength
0x18003773c  lea     rcx, [rbp+250h+Buffer]; psz
0x180037740  call    StringLengthWorkerW_0
0x180037745  mov     esi, eax
0x180037747  test    eax, eax
0x180037749  js      loc_18003790A
0x18003774f  mov     rax, [rsp+350h+pcchLength]
0x180037754  lea     r14, [rbp+250h+Buffer]
0x180037758  lea     r14, [r14+rax*2]
0x18003775c  sub     rbx, rax
0x18003775f  cmp     rbx, 1
0x180037763  ja      short loc_18003776C
0x180037765  mov     esi, 8007007Ah
0x18003776a  jmp     short loc_1800377A7
0x18003776c  mov     [rsp+350h+pcchLength], r12
0x180037771  lea     r9, aAudiodgExe; "\\AUDIODG.EXE"
0x180037778  lea     r8, [rsp+350h+pcchLength]; pcchNewDestLength
0x18003777d  mov     rdx, rbx; cchDest
0x180037780  mov     rcx, r14; pszDest
0x180037783  call    StringCopyWorkerW
0x180037788  mov     esi, eax
0x18003778a  mov     rcx, [rsp+350h+pcchLength]
0x18003778f  lea     r14, [r14+rcx*2]
0x180037793  sub     rbx, rcx
0x180037796  test    eax, eax
0x180037798  jns     short loc_1800377A7
0x18003779a  mov     rcx, r12
0x18003779d  mov     rdx, r12
0x1800377a0  cmp     eax, 8007007Ah
0x1800377a5  jnz     short loc_1800377AE
0x1800377a7  lea     rdx, [rbx+rbx]; unsigned __int64
0x1800377ab  mov     rcx, r14; unsigned __int16 *
0x1800377ae  lea     rbx, [rdi+58h]
0x1800377b2  test    esi, esi
0x1800377b4  js      loc_18003790E
0x1800377ba  mov     rax, [rdi+78h]
0x1800377be  mov     qword ptr [rsp+350h+bInheritHandles], rax; int
0x1800377c3  mov     r9, [rdi+70h]
0x1800377c7  lea     r8, a0xP0xP; " 0x%p 0x%p"
0x1800377ce  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800377d3  mov     esi, eax
0x1800377d5  test    eax, eax
0x1800377d7  jns     short loc_180037805
0x1800377d9  mov     edx, 68h ; 'h'; void *
0x1800377de  lea     r8, aAvcoreAudiocor_21; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800377e5  mov     r9d, esi; char *
0x1800377e8  mov     rcx, [rbp+258h]; this
0x1800377ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800377f4  nop
0x1800377f5  mov     rcx, [rbx]
0x1800377f8  lea     rdx, [rcx-1]
0x1800377fc  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180037800  jmp     loc_180037935
0x180037805  xor     edx, edx; Val
0x180037807  lea     r8d, [rdx+64h]; Size
0x18003780b  lea     rcx, [rbp+250h+StartupInfo+4]; void *
0x18003780f  call    memset_0
0x180037814  mov     [rbp+250h+StartupInfo.cb], 68h ; 'h'
0x18003781b  xorps   xmm0, xmm0
0x18003781e  xor     eax, eax
0x180037820  movups  xmmword ptr [rsp+350h+ProcessAttributes.nLength], xmm0
0x180037825  mov     qword ptr [rsp+350h+ProcessAttributes.bInheritHandle], rax
0x18003782a  mov     [rsp+350h+ProcessAttributes.nLength], 18h
0x180037832  mov     [rsp+350h+ProcessAttributes.bInheritHandle], r12d
0x180037837  lea     rcx, [rsp+350h+ProcessAttributes.lpSecurityDescriptor]; void **
0x18003783c  call    ?GetADGProcessSD@CAudioDGProcess@@CAJPEAPEAX@Z; CAudioDGProcess::GetADGProcessSD(void * *)
0x180037841  mov     esi, eax
0x180037843  test    eax, eax
0x180037845  jns     short loc_18003784E
0x180037847  mov     edx, 71h ; 'q'
0x18003784c  jmp     short loc_1800377DE
0x18003784e  xorps   xmm0, xmm0
0x180037851  xor     eax, eax
0x180037853  movups  xmmword ptr [rsp+350h+ProcessInformation.hProcess], xmm0
0x180037858  mov     qword ptr [rbp+250h+ProcessInformation.dwProcessId], rax
0x18003785c  shl     r15d, 12h
0x180037860  lea     rcx, [rsp+350h+ProcessInformation]
0x180037865  mov     [rsp+350h+lpProcessInformation], rcx; lpProcessInformation
0x18003786a  lea     rcx, [rbp+250h+StartupInfo]
0x18003786e  mov     [rsp+350h+lpStartupInfo], rcx; lpStartupInfo
0x180037873  mov     [rsp+350h+lpCurrentDirectory], r12; lpCurrentDirectory
0x180037878  mov     [rsp+350h+lpEnvironment], r12; lpEnvironment
0x18003787d  mov     [rsp+350h+dwCreationFlags], r15d; dwCreationFlags
0x180037882  mov     [rsp+350h+bInheritHandles], 1; bInheritHandles
0x18003788a  xor     r9d, r9d; lpThreadAttributes
0x18003788d  lea     r8, [rsp+350h+ProcessAttributes]; lpProcessAttributes
0x180037892  lea     rdx, [rbp+250h+Buffer]; lpCommandLine
0x180037896  xor     ecx, ecx; lpApplicationName
0x180037898  call    cs:__imp_CreateProcessW
0x18003789e  test    eax, eax
0x1800378a0  jnz     short loc_1800378CE
0x1800378a2  mov     rcx, [rbp+258h]; this
0x1800378a9  lea     r8, aAvcoreAudiocor_21; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800378b0  lea     edx, [rax+76h]; void *
0x1800378b3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800378b8  mov     esi, eax
0x1800378ba  mov     rcx, [rsp+350h+ProcessAttributes.lpSecurityDescriptor]; void *
0x1800378bf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800378c4  mov     [rsp+350h+ProcessAttributes.lpSecurityDescriptor], r12
0x1800378c9  jmp     loc_1800377F5
0x1800378ce  mov     rdx, [rsp+350h+ProcessInformation.hProcess]
0x1800378d3  mov     rcx, rbx
0x1800378d6  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800378db  mov     eax, [rbp+250h+ProcessInformation.dwProcessId]
0x1800378de  mov     [rdi+60h], eax
0x1800378e1  mov     rcx, [rsp+350h+ProcessInformation.hThread]; hObject
0x1800378e6  lea     rax, [rcx-1]
0x1800378ea  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800378ee  ja      short loc_1800378FB
0x1800378f0  call    cs:__imp_CloseHandle
0x1800378f6  mov     [rsp+350h+ProcessInformation.hThread], r12
0x1800378fb  mov     rcx, [rsp+350h+ProcessAttributes.lpSecurityDescriptor]; void *
0x180037900  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180037905  nop
0x180037906  xor     eax, eax
0x180037908  jmp     short loc_180037953
0x18003790a  lea     rbx, [rdi+58h]
0x18003790e  mov     rcx, [rbp+258h]; this
0x180037915  mov     r9d, esi; char *
0x180037918  lea     r8, aAvcoreAudiocor_21; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x18003791f  mov     edx, 66h ; 'f'; void *
0x180037924  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037929  nop
0x18003792a  mov     rcx, [rbx]; hHandle
0x18003792d  lea     rax, [rcx-1]
0x180037931  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180037935  ja      short loc_180037951
0x180037937  xor     r8d, r8d; bAlertable
0x18003793a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003793d  call    cs:__imp_WaitForSingleObjectEx
0x180037943  xor     edx, edx
0x180037945  mov     rcx, rbx
0x180037948  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003794d  mov     [rdi+60h], r12d
0x180037951  mov     eax, esi
0x180037953  mov     rcx, [rbp+250h+var_30]
0x18003795a  xor     rcx, rsp; StackCookie
0x18003795d  call    __security_check_cookie
0x180037962  lea     r11, [rsp+350h+var_20]
0x18003796a  mov     rbx, [r11+38h]
0x18003796e  mov     rsi, [r11+40h]
0x180037972  mov     rsp, r11
0x180037975  pop     r15
0x180037977  pop     r14
0x180037979  pop     r12
0x18003797b  pop     rdi
0x18003797c  pop     rbp
0x18003797d  retn
```
