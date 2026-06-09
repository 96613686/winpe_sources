# DSService::Initialize(char *,void *,ulong)

- ea: `0x180006730`
- end: `0x1800068d4`
- name: `?Initialize@DSService@@UEAAJPEADPEAXK@Z`
- size: `420`
- prototype: `__int64 __fastcall(char *pv, char *, HANDLE hSourceHandle, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x180001178`
- `0x180001720`
- `0x180006730`
- `0x1800074bc`
- `0x180007e5c`
- `0x180007ec4`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800068b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800068b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006756`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006756`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800067d6`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800067cc`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800067cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006798`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800067a1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180006798`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800067a1`

## string_xrefs

- `0x18000681c`: `onecoreuap\base\diagnosis\pdi\diagsvc\service\dsservice.cpp`
- `0x180006835`: `DSService::Initialize`
- `0x180006843`: `Initializing DSService`

## pseudocode

```c
__int64 __fastcall DSService::Initialize(char *pv, char *a2, HANDLE hSourceHandle, int a4)
{
  struct _RTL_CRITICAL_SECTION *v4; // rsi
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v11; // r8
  bool v12; // zf
  signed int v13; // ebx
  HANDLE CurrentProcess; // rbx
  HANDLE v15; // rax
  signed int LastError; // eax
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  const char *v21; // [rsp+50h] [rbp-20h] BYREF
  const char *v22; // [rsp+58h] [rbp-18h] BYREF
  const char *v23; // [rsp+60h] [rbp-10h] BYREF
  char *v24; // [rsp+68h] [rbp-8h] BYREF
  signed int v25; // [rsp+A0h] [rbp+30h] BYREF
  int v26; // [rsp+B8h] [rbp+48h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)(pv + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)(pv + 16));
  v12 = pv[8] == 0;
  *((_DWORD *)pv + 15) = a4;
  if ( v12 )
  {
    if ( a2 && hSourceHandle )
    {
      v13 = StringCchCopyA(pv + 104, 0x81u, a2);
      if ( v13 >= 0 )
      {
        CurrentProcess = GetCurrentProcess();
        v15 = GetCurrentProcess();
        if ( DuplicateHandle(v15, hSourceHandle, CurrentProcess, (LPHANDLE)pv + 9, 0, 0, 2u) )
          goto LABEL_10;
        LastError = GetLastError();
        v13 = LastError;
        if ( LastError > 0 )
          v13 = (unsigned __int16)LastError | 0x80070000;
        if ( v13 >= 0 )
        {
LABEL_10:
          v13 = DSService::RegisterRpcInterface((DSService *)pv);
          if ( v13 >= 0 )
            pv[8] = 1;
        }
      }
    }
    else
    {
      v13 = -2147024809;
    }
  }
  else
  {
    v13 = -2147467259;
  }
  if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v10, v9, v11) )
  {
    v26 = 209;
    v21 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\service\\dsservice.cpp";
    v25 = v13;
    v22 = "DSService::Initialize";
    v23 = "Initializing DSService";
    v24 = pv + 104;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v17,
      (unsigned int)&word_18002FC36,
      v18,
      v19,
      (__int64)&v24,
      (__int64)&v25,
      (__int64)&v23,
      (__int64)&v22,
      (__int64)&v21,
      (__int64)&v26);
  }
  if ( v13 < 0 )
    (*(void (__fastcall **)(char *))(*(_QWORD *)pv + 48LL))(pv);
  else
    DSService::ToggleShutdownTimer(pv, 1);
  if ( v4 )
    LeaveCriticalSection(v4);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180006730  mov     [rsp-28h+arg_8], rbx
0x180006735  push    rbp
0x180006736  push    rsi
0x180006737  push    rdi
0x180006738  push    r14
0x18000673a  push    r15
0x18000673c  mov     rbp, rsp
0x18000673f  sub     rsp, 70h
0x180006743  lea     rsi, [rcx+10h]
0x180006747  mov     rdi, rcx
0x18000674a  mov     rcx, rsi; lpCriticalSection
0x18000674d  mov     ebx, r9d
0x180006750  mov     r15, r8
0x180006753  mov     r14, rdx
0x180006756  call    cs:__imp_EnterCriticalSection
0x18000675c  cmp     byte ptr [rdi+8], 0
0x180006760  mov     [rdi+3Ch], ebx
0x180006763  jz      short loc_18000676F
0x180006765  mov     ebx, 80004005h
0x18000676a  jmp     loc_180006808
0x18000676f  test    r14, r14
0x180006772  jz      loc_180006803
0x180006778  test    r15, r15
0x18000677b  jz      loc_180006803
0x180006781  lea     rcx, [rdi+68h]; char *
0x180006785  mov     r8, r14; char *
0x180006788  mov     edx, 81h; unsigned __int64
0x18000678d  call    ?StringCchCopyA@@YAJPEAD_KPEBD@Z; StringCchCopyA(char *,unsigned __int64,char const *)
0x180006792  mov     ebx, eax
0x180006794  test    eax, eax
0x180006796  js      short loc_180006808
0x180006798  call    cs:__imp_GetCurrentProcess
0x18000679e  mov     rbx, rax
0x1800067a1  call    cs:__imp_GetCurrentProcess
0x1800067a7  mov     [rsp+70h+dwOptions], 2; dwOptions
0x1800067af  lea     r9, [rdi+48h]; lpTargetHandle
0x1800067b3  mov     rcx, rax; hSourceProcessHandle
0x1800067b6  mov     [rsp+70h+bInheritHandle], 0; bInheritHandle
0x1800067be  mov     r8, rbx; hTargetProcessHandle
0x1800067c1  mov     [rsp+70h+dwDesiredAccess], 0; dwDesiredAccess
0x1800067c9  mov     rdx, r15; hSourceHandle
0x1800067cc  call    cs:__imp_DuplicateHandle
0x1800067d2  test    eax, eax
0x1800067d4  jnz     short loc_1800067EF
0x1800067d6  call    cs:__imp_GetLastError
0x1800067dc  mov     ebx, eax
0x1800067de  test    eax, eax
0x1800067e0  jle     short loc_1800067EB
0x1800067e2  movzx   ebx, ax
0x1800067e5  or      ebx, 80070000h
0x1800067eb  test    ebx, ebx
0x1800067ed  js      short loc_180006808
0x1800067ef  mov     rcx, rdi; this
0x1800067f2  call    ?RegisterRpcInterface@DSService@@IEAAJXZ; DSService::RegisterRpcInterface(void)
0x1800067f7  mov     ebx, eax
0x1800067f9  test    eax, eax
0x1800067fb  js      short loc_180006808
0x1800067fd  mov     byte ptr [rdi+8], 1
0x180006801  jmp     short loc_180006808
0x180006803  mov     ebx, 80070057h
0x180006808  mov     eax, cs:dword_180039000
0x18000680e  cmp     eax, 5
0x180006811  jbe     short loc_180006891
0x180006813  call    _tlgKeywordOn
0x180006818  test    al, al
0x18000681a  jz      short loc_180006891
0x18000681c  lea     rax, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x180006823  mov     [rbp+arg_18], 0D1h
0x18000682a  mov     [rbp+var_20], rax
0x18000682e  lea     rdx, word_18002FC36
0x180006835  lea     rax, aDsserviceIniti; "DSService::Initialize"
0x18000683c  mov     [rbp+arg_0], ebx
0x18000683f  mov     [rbp+var_18], rax
0x180006843  lea     rax, aInitializingDs; "Initializing DSService"
0x18000684a  mov     [rbp+var_10], rax
0x18000684e  lea     rax, [rdi+68h]
0x180006852  mov     [rbp+var_8], rax
0x180006856  lea     rax, [rbp+arg_18]
0x18000685a  mov     [rsp+70h+var_28], rax
0x18000685f  lea     rax, [rbp+var_20]
0x180006863  mov     [rsp+70h+var_30], rax
0x180006868  lea     rax, [rbp+var_18]
0x18000686c  mov     [rsp+70h+var_38], rax
0x180006871  lea     rax, [rbp+var_10]
0x180006875  mov     qword ptr [rsp+70h+dwOptions], rax
0x18000687a  lea     rax, [rbp+arg_0]
0x18000687e  mov     qword ptr [rsp+70h+bInheritHandle], rax
0x180006883  lea     rax, [rbp+var_8]
0x180006887  mov     qword ptr [rsp+70h+dwDesiredAccess], rax
0x18000688c  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180006891  mov     rcx, rdi; pv
0x180006894  test    ebx, ebx
0x180006896  js      short loc_1800068A4
0x180006898  mov     edx, 1; int
0x18000689d  call    ?ToggleShutdownTimer@DSService@@IEAAXH@Z; DSService::ToggleShutdownTimer(int)
0x1800068a2  jmp     short loc_1800068B0
0x1800068a4  mov     rax, [rdi]
0x1800068a7  mov     rax, [rax+30h]
0x1800068ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068b0  test    rsi, rsi
0x1800068b3  jz      short loc_1800068BE
0x1800068b5  mov     rcx, rsi; lpCriticalSection
0x1800068b8  call    cs:__imp_LeaveCriticalSection
0x1800068be  mov     eax, ebx
0x1800068c0  mov     rbx, [rsp+70h+arg_8]
0x1800068c8  add     rsp, 70h
0x1800068cc  pop     r15
0x1800068ce  pop     r14
0x1800068d0  pop     rdi
0x1800068d1  pop     rsi
0x1800068d2  pop     rbp
0x1800068d3  retn
```
