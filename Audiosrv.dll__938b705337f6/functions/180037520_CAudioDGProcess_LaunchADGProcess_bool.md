# CAudioDGProcess::LaunchADGProcess(bool)

- ea: `0x180037520`
- end: `0x18003781e`
- name: `?LaunchADGProcess@CAudioDGProcess@@AEAAJ_N@Z`
- size: `766`
- prototype: `__int64 __fastcall(CAudioDGProcess *__hidden this, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180073134`

## callees

- `0x18000abd0`
- `0x1800126bc`
- `0x180037520`
- `0x180037824`
- `0x1800378b0`
- `0x18005621c`
- `0x18006534c`
- `0x1800b6978`
- `0x1800b745c`
- `0x1800cf8c0`
- `0x1800d0764`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800375b6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800377dd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800375b6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x1800377dd`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180037738`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x180037738`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037790`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180037790`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18003757d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18003757d`

## string_xrefs

- `0x180037591`: `avcore\audiocore\server\audiosrv\dll\adgprocess.cpp`
- `0x18003767e`: `avcore\audiocore\server\audiosrv\dll\adgprocess.cpp`
- `0x180037749`: `avcore\audiocore\server\audiosrv\dll\adgprocess.cpp`
- `0x1800377b8`: `avcore\audiocore\server\audiosrv\dll\adgprocess.cpp`

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
0x180037520  mov     [rsp-8+arg_8], rbx
0x180037525  mov     [rsp-8+arg_10], rsi
0x18003752a  push    rbp
0x18003752b  push    rdi
0x18003752c  push    r12
0x18003752e  push    r14
0x180037530  push    r15
0x180037532  lea     rbp, [rsp-230h]
0x18003753a  sub     rsp, 330h
0x180037541  mov     rax, cs:__security_cookie
0x180037548  xor     rax, rsp
0x18003754b  mov     [rbp+250h+var_30], rax
0x180037552  movzx   r15d, dl
0x180037556  mov     rdi, rcx
0x180037559  mov     [rbp+250h+var_2C8], rcx
0x18003755d  mov     [rbp+250h+var_2C0], 1
0x180037561  xor     edx, edx; Val
0x180037563  mov     r8d, 208h; Size
0x180037569  lea     rcx, [rbp+250h+Buffer]; void *
0x18003756d  call    memset_0
0x180037572  mov     ebx, 104h
0x180037577  mov     edx, ebx; uSize
0x180037579  lea     rcx, [rbp+250h+Buffer]; lpBuffer
0x18003757d  call    cs:__imp_GetSystemDirectoryW
0x180037583  xor     r12d, r12d
0x180037586  test    eax, eax
0x180037588  jnz     short loc_1800375D2
0x18003758a  mov     rcx, [rbp+258h]; this
0x180037591  lea     r8, aAvcoreAudiocor_21; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180037598  lea     edx, [rax+62h]; void *
0x18003759b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800375a0  mov     ebx, eax
0x1800375a2  mov     rcx, [rdi+58h]; hHandle
0x1800375a6  lea     rdx, [rcx-1]
0x1800375aa  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800375ae  ja      short loc_1800375CB
0x1800375b0  xor     r8d, r8d; bAlertable
0x1800375b3  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800375b6  call    cs:__imp_WaitForSingleObjectEx
0x1800375bc  xor     edx, edx
0x1800375be  lea     rcx, [rdi+58h]
0x1800375c2  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800375c7  mov     [rdi+60h], r12d
0x1800375cb  mov     eax, ebx
0x1800375cd  jmp     loc_1800377F3
0x1800375d2  mov     [rsp+350h+pcchLength], r12
0x1800375d7  lea     r8, [rsp+350h+pcchLength]; pcchLength
0x1800375dc  lea     rcx, [rbp+250h+Buffer]; psz
0x1800375e0  call    StringLengthWorkerW_0
0x1800375e5  mov     esi, eax
0x1800375e7  test    eax, eax
0x1800375e9  js      loc_1800377AA
0x1800375ef  mov     rax, [rsp+350h+pcchLength]
0x1800375f4  lea     r14, [rbp+250h+Buffer]
0x1800375f8  lea     r14, [r14+rax*2]
0x1800375fc  sub     rbx, rax
0x1800375ff  cmp     rbx, 1
0x180037603  ja      short loc_18003760C
0x180037605  mov     esi, 8007007Ah
0x18003760a  jmp     short loc_180037647
0x18003760c  mov     [rsp+350h+pcchLength], r12
0x180037611  lea     r9, aAudiodgExe; "\\AUDIODG.EXE"
0x180037618  lea     r8, [rsp+350h+pcchLength]; pcchNewDestLength
0x18003761d  mov     rdx, rbx; cchDest
0x180037620  mov     rcx, r14; pszDest
0x180037623  call    StringCopyWorkerW
0x180037628  mov     esi, eax
0x18003762a  mov     rcx, [rsp+350h+pcchLength]
0x18003762f  lea     r14, [r14+rcx*2]
0x180037633  sub     rbx, rcx
0x180037636  test    eax, eax
0x180037638  jns     short loc_180037647
0x18003763a  mov     rcx, r12
0x18003763d  mov     rdx, r12
0x180037640  cmp     eax, 8007007Ah
0x180037645  jnz     short loc_18003764E
0x180037647  lea     rdx, [rbx+rbx]; unsigned __int64
0x18003764b  mov     rcx, r14; unsigned __int16 *
0x18003764e  lea     rbx, [rdi+58h]
0x180037652  test    esi, esi
0x180037654  js      loc_1800377AE
0x18003765a  mov     rax, [rdi+78h]
0x18003765e  mov     qword ptr [rsp+350h+bInheritHandles], rax; int
0x180037663  mov     r9, [rdi+70h]
0x180037667  lea     r8, a0xP0xP; " 0x%p 0x%p"
0x18003766e  call    ?StringCbPrintfW@@YAJPEAG_KPEBGZZ; StringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180037673  mov     esi, eax
0x180037675  test    eax, eax
0x180037677  jns     short loc_1800376A5
0x180037679  mov     edx, 68h ; 'h'; void *
0x18003767e  lea     r8, aAvcoreAudiocor_21; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180037685  mov     r9d, esi; char *
0x180037688  mov     rcx, [rbp+258h]; this
0x18003768f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180037694  nop
0x180037695  mov     rcx, [rbx]
0x180037698  lea     rdx, [rcx-1]
0x18003769c  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x1800376a0  jmp     loc_1800377D5
0x1800376a5  xor     edx, edx; Val
0x1800376a7  lea     r8d, [rdx+64h]; Size
0x1800376ab  lea     rcx, [rbp+250h+StartupInfo+4]; void *
0x1800376af  call    memset_0
0x1800376b4  mov     [rbp+250h+StartupInfo.cb], 68h ; 'h'
0x1800376bb  xorps   xmm0, xmm0
0x1800376be  xor     eax, eax
0x1800376c0  movups  xmmword ptr [rsp+350h+ProcessAttributes.nLength], xmm0
0x1800376c5  mov     qword ptr [rsp+350h+ProcessAttributes.bInheritHandle], rax
0x1800376ca  mov     [rsp+350h+ProcessAttributes.nLength], 18h
0x1800376d2  mov     [rsp+350h+ProcessAttributes.bInheritHandle], r12d
0x1800376d7  lea     rcx, [rsp+350h+ProcessAttributes.lpSecurityDescriptor]; void **
0x1800376dc  call    ?GetADGProcessSD@CAudioDGProcess@@CAJPEAPEAX@Z; CAudioDGProcess::GetADGProcessSD(void * *)
0x1800376e1  mov     esi, eax
0x1800376e3  test    eax, eax
0x1800376e5  jns     short loc_1800376EE
0x1800376e7  mov     edx, 71h ; 'q'
0x1800376ec  jmp     short loc_18003767E
0x1800376ee  xorps   xmm0, xmm0
0x1800376f1  xor     eax, eax
0x1800376f3  movups  xmmword ptr [rsp+350h+ProcessInformation.hProcess], xmm0
0x1800376f8  mov     qword ptr [rbp+250h+ProcessInformation.dwProcessId], rax
0x1800376fc  shl     r15d, 12h
0x180037700  lea     rcx, [rsp+350h+ProcessInformation]
0x180037705  mov     [rsp+350h+lpProcessInformation], rcx; lpProcessInformation
0x18003770a  lea     rcx, [rbp+250h+StartupInfo]
0x18003770e  mov     [rsp+350h+lpStartupInfo], rcx; lpStartupInfo
0x180037713  mov     [rsp+350h+lpCurrentDirectory], r12; lpCurrentDirectory
0x180037718  mov     [rsp+350h+lpEnvironment], r12; lpEnvironment
0x18003771d  mov     [rsp+350h+dwCreationFlags], r15d; dwCreationFlags
0x180037722  mov     [rsp+350h+bInheritHandles], 1; bInheritHandles
0x18003772a  xor     r9d, r9d; lpThreadAttributes
0x18003772d  lea     r8, [rsp+350h+ProcessAttributes]; lpProcessAttributes
0x180037732  lea     rdx, [rbp+250h+Buffer]; lpCommandLine
0x180037736  xor     ecx, ecx; lpApplicationName
0x180037738  call    cs:__imp_CreateProcessW
0x18003773e  test    eax, eax
0x180037740  jnz     short loc_18003776E
0x180037742  mov     rcx, [rbp+258h]; this
0x180037749  lea     r8, aAvcoreAudiocor_21; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x180037750  lea     edx, [rax+76h]; void *
0x180037753  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180037758  mov     esi, eax
0x18003775a  mov     rcx, [rsp+350h+ProcessAttributes.lpSecurityDescriptor]; void *
0x18003775f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180037764  mov     [rsp+350h+ProcessAttributes.lpSecurityDescriptor], r12
0x180037769  jmp     loc_180037695
0x18003776e  mov     rdx, [rsp+350h+ProcessInformation.hProcess]
0x180037773  mov     rcx, rbx
0x180037776  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18003777b  mov     eax, [rbp+250h+ProcessInformation.dwProcessId]
0x18003777e  mov     [rdi+60h], eax
0x180037781  mov     rcx, [rsp+350h+ProcessInformation.hThread]; hObject
0x180037786  lea     rax, [rcx-1]
0x18003778a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18003778e  ja      short loc_18003779B
0x180037790  call    cs:__imp_CloseHandle
0x180037796  mov     [rsp+350h+ProcessInformation.hThread], r12
0x18003779b  mov     rcx, [rsp+350h+ProcessAttributes.lpSecurityDescriptor]; void *
0x1800377a0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800377a5  nop
0x1800377a6  xor     eax, eax
0x1800377a8  jmp     short loc_1800377F3
0x1800377aa  lea     rbx, [rdi+58h]
0x1800377ae  mov     rcx, [rbp+258h]; this
0x1800377b5  mov     r9d, esi; char *
0x1800377b8  lea     r8, aAvcoreAudiocor_21; "avcore\\audiocore\\server\\audiosrv\\dl"...
0x1800377bf  mov     edx, 66h ; 'f'; void *
0x1800377c4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800377c9  nop
0x1800377ca  mov     rcx, [rbx]; hHandle
0x1800377cd  lea     rax, [rcx-1]
0x1800377d1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800377d5  ja      short loc_1800377F1
0x1800377d7  xor     r8d, r8d; bAlertable
0x1800377da  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800377dd  call    cs:__imp_WaitForSingleObjectEx
0x1800377e3  xor     edx, edx
0x1800377e5  mov     rcx, rbx
0x1800377e8  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800377ed  mov     [rdi+60h], r12d
0x1800377f1  mov     eax, esi
0x1800377f3  mov     rcx, [rbp+250h+var_30]
0x1800377fa  xor     rcx, rsp; StackCookie
0x1800377fd  call    __security_check_cookie
0x180037802  lea     r11, [rsp+350h+var_20]
0x18003780a  mov     rbx, [r11+38h]
0x18003780e  mov     rsi, [r11+40h]
0x180037812  mov     rsp, r11
0x180037815  pop     r15
0x180037817  pop     r14
0x180037819  pop     r12
0x18003781b  pop     rdi
0x18003781c  pop     rbp
0x18003781d  retn
```
