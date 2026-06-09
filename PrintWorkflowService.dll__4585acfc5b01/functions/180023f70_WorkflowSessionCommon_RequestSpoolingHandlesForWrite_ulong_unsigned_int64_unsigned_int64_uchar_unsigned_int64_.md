# WorkflowSessionCommon::RequestSpoolingHandlesForWrite(ulong *,unsigned __int64 *,unsigned __int64 *,uchar *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x180023f70`
- end: `0x1800242f3`
- name: `?RequestSpoolingHandlesForWrite@WorkflowSessionCommon@@QEAAJPEAKPEA_K1PEAE11@Z`
- size: `899`
- prototype: `__int64 __fastcall(WorkflowSessionCommon *__hidden this, unsigned int *, unsigned __int64 *, unsigned __int64 *, unsigned __int8 *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180019e90`
- `0x180034f14`

## callees

- `0x180001314`
- `0x1800026ec`
- `0x1800127a4`
- `0x1800166a8`
- `0x18001a7c0`
- `0x180021eac`
- `0x1800235a0`
- `0x180023664`
- `0x180023f70`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023fdc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180023fdc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800240b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180024115`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800240b0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180024115`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800240df`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180024144`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x1800240df`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180024144`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180024072`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180024072`

## string_xrefs

- `0x1800242bc`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowsessioncommon.cpp`
- `0x1800242ce`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowsessioncommon.cpp`
- `0x1800242e0`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowsessioncommon.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
__int64 __fastcall WorkflowSessionCommon::RequestSpoolingHandlesForWrite(
        WorkflowSessionCommon *this,
        unsigned int *a2,
        unsigned __int64 *a3,
        char **a4,
        unsigned __int8 *a5,
        unsigned __int64 *a6,
        unsigned __int64 *a7)
{
  HANDLE *v11; // rbx
  HANDLE *v12; // rdi
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  bool v16; // zf
  char v17; // al
  int v18; // r14d
  char *v19; // rbx
  void *v20; // rdi
  HANDLE CurrentProcess; // rax
  const char *v22; // r9
  void *v23; // rdi
  HANDLE v24; // rax
  const char *v25; // r9
  HANDLE v26; // rax
  __int64 v27; // rax
  int dwDesiredAccess; // [rsp+20h] [rbp-78h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  __int64 dwProcessId; // [rsp+A0h] [rbp+8h] BYREF
  HANDLE TargetHandle; // [rsp+A8h] [rbp+10h] BYREF
  char *v33; // [rsp+B0h] [rbp+18h] BYREF
  __int64 v34; // [rsp+B8h] [rbp+20h] BYREF

  if ( (unsigned int)dword_180083038 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_180083038,
      (__int64)word_180072B5A,
      0);
  *a2 = 0;
  *a3 = 0;
  *a4 = 0;
  *a5 = 0;
  v11 = (HANDLE *)a6;
  *a6 = 0;
  v12 = (HANDLE *)a7;
  *a7 = 0;
  *a2 = GetCurrentProcessId();
  *a3 = *((_QWORD *)this + 2);
  *a4 = (char *)*((_QWORD *)this + 1);
  LODWORD(dwProcessId) = 0;
  if ( (int)GetCallerProcessId((unsigned int *)&dwProcessId) < 0 )
  {
    v18 = dwProcessId;
  }
  else
  {
    if ( IsPseudoHandle(*((void **)this + 1)) || (v16 = !IsPseudoHandle(*((void **)this + 2)), v17 = 0, !v16) )
      v17 = 1;
    if ( v17 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC2,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowsessioncommon.cpp",
        (const char *)0x80070006LL,
        dwDesiredAccess);
    if ( (unsigned int)dword_180083038 > 5 )
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
        (__int64)&dword_180083038,
        (__int64)&word_180072B2E,
        0);
    v18 = dwProcessId;
    v19 = (char *)OpenProcess(0x40u, 0, dwProcessId);
    v33 = v19;
    if ( (unsigned __int64)(v19 - 1) > 0xFFFFFFFFFFFFFFFDuLL )
    {
      v11 = (HANDLE *)a6;
    }
    else
    {
      TargetHandle = (HANDLE)-1LL;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &TargetHandle,
        -1);
      v20 = (void *)*((_QWORD *)this + 2);
      CurrentProcess = GetCurrentProcess();
      if ( !DuplicateHandle(CurrentProcess, v20, v19, &TargetHandle, 0, 0, 2u) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0xCC,
          (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowsessioncommon.cpp",
          v22);
      dwProcessId = -1;
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &dwProcessId,
        -1);
      v23 = (void *)*((_QWORD *)this + 1);
      v24 = GetCurrentProcess();
      if ( !DuplicateHandle(v24, v23, v19, (LPHANDLE)&dwProcessId, 0, 0, 2u) )
        wil::details::in1diag3::_Throw_GetLastError(
          retaddr,
          (void *)0xD1,
          (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowsessioncommon.cpp",
          v25);
      v26 = TargetHandle;
      TargetHandle = (HANDLE)-1LL;
      v11 = (HANDLE *)a6;
      *a6 = (unsigned __int64)v26;
      v27 = dwProcessId;
      dwProcessId = -1;
      v12 = (HANDLE *)a7;
      *a7 = v27;
      *a5 = 1;
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&dwProcessId);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TargetHandle);
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v33);
  }
  if ( (unsigned int)dword_180083038 > 5 )
  {
    LODWORD(a6) = *((_DWORD *)this + 18);
    dwProcessId = (__int64)*v12;
    TargetHandle = *v11;
    LODWORD(a7) = *a2;
    v33 = *a4;
    v34 = *a3;
    LODWORD(a5) = v18;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      v13,
      (__int64)&unk_180072A28,
      v14,
      v15,
      (__int64)&a5,
      (__int64)&v34,
      (__int64)&v33,
      (__int64)&a7,
      (__int64)&TargetHandle,
      (__int64)&dwProcessId,
      (__int64)&a6);
  }
  return 0;
}

```

## disassembly

```asm
0x180023f70  push    rbx
0x180023f72  push    rsi
0x180023f73  push    rdi
0x180023f74  push    r12
0x180023f76  push    r13
0x180023f78  push    r14
0x180023f7a  push    r15
0x180023f7c  sub     rsp, 60h
0x180023f80  mov     r15, r9
0x180023f83  mov     r12, r8
0x180023f86  mov     r13, rdx
0x180023f89  mov     rsi, rcx
0x180023f8c  mov     eax, cs:dword_180083038
0x180023f92  cmp     eax, 5
0x180023f95  jbe     short loc_180023FAD
0x180023f97  xor     r8d, r8d
0x180023f9a  lea     rdx, word_180072B5A
0x180023fa1  lea     rcx, dword_180083038
0x180023fa8  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180023fad  xor     r14d, r14d
0x180023fb0  mov     [r13+0], r14d
0x180023fb4  mov     [r12], r14
0x180023fb8  mov     [r15], r14
0x180023fbb  mov     rax, [rsp+98h+arg_20]
0x180023fc3  mov     [rax], r14b
0x180023fc6  mov     rbx, [rsp+98h+arg_28]
0x180023fce  mov     [rbx], r14
0x180023fd1  mov     rdi, [rsp+98h+arg_30]
0x180023fd9  mov     [rdi], r14
0x180023fdc  call    cs:__imp_GetCurrentProcessId
0x180023fe2  mov     [r13+0], eax
0x180023fe6  mov     rax, [rsi+10h]
0x180023fea  mov     [r12], rax
0x180023fee  mov     rax, [rsi+8]
0x180023ff2  mov     [r15], rax
0x180023ff5  mov     dword ptr [rsp+98h+dwProcessId], r14d
0x180023ffd  lea     rcx, [rsp+98h+dwProcessId]; unsigned int *
0x180024005  call    ?GetCallerProcessId@@YAJPEAK@Z; GetCallerProcessId(ulong *)
0x18002400a  test    eax, eax
0x18002400c  js      loc_1800241D3
0x180024012  mov     rcx, [rsi+8]; void *
0x180024016  call    ?IsPseudoHandle@@YA_NPEAX@Z; IsPseudoHandle(void *)
0x18002401b  test    al, al
0x18002401d  jnz     short loc_18002402F
0x18002401f  mov     rcx, [rsi+10h]; void *
0x180024023  call    ?IsPseudoHandle@@YA_NPEAX@Z; IsPseudoHandle(void *)
0x180024028  test    al, al
0x18002402a  mov     al, r14b
0x18002402d  jz      short loc_180024031
0x18002402f  mov     al, 1
0x180024031  mov     rcx, [rsp+98h]; this
0x180024039  test    al, al
0x18002403b  jnz     loc_1800242B6
0x180024041  mov     eax, cs:dword_180083038
0x180024047  cmp     eax, 5
0x18002404a  jbe     short loc_180024062
0x18002404c  xor     r8d, r8d
0x18002404f  lea     rdx, word_180072B2E
0x180024056  lea     rcx, dword_180083038
0x18002405d  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180024062  mov     r14d, dword ptr [rsp+98h+dwProcessId]
0x18002406a  mov     r8d, r14d; dwProcessId
0x18002406d  xor     edx, edx; bInheritHandle
0x18002406f  lea     ecx, [rdx+40h]; dwDesiredAccess
0x180024072  call    cs:__imp_OpenProcess
0x180024078  mov     rbx, rax
0x18002407b  mov     [rsp+98h+arg_10], rax
0x180024083  dec     rax
0x180024086  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002408a  ja      loc_1800241BC
0x180024090  or      rax, 0FFFFFFFFFFFFFFFFh
0x180024094  mov     [rsp+98h+TargetHandle], rax
0x18002409c  mov     rdx, rax
0x18002409f  lea     rcx, [rsp+98h+TargetHandle]
0x1800240a7  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800240ac  mov     rdi, [rsi+10h]
0x1800240b0  call    cs:__imp_GetCurrentProcess
0x1800240b6  mov     [rsp+98h+dwOptions], 2; dwOptions
0x1800240be  mov     [rsp+98h+bInheritHandle], 0; bInheritHandle
0x1800240c6  mov     [rsp+98h+dwDesiredAccess], 0; dwDesiredAccess
0x1800240ce  lea     r9, [rsp+98h+TargetHandle]; lpTargetHandle
0x1800240d6  mov     r8, rbx; hTargetProcessHandle
0x1800240d9  mov     rdx, rdi; hSourceHandle
0x1800240dc  mov     rcx, rax; hSourceProcessHandle
0x1800240df  call    cs:__imp_DuplicateHandle
0x1800240e5  mov     rcx, [rsp+98h]; this
0x1800240ed  test    eax, eax
0x1800240ef  jz      loc_1800242CE
0x1800240f5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800240f9  mov     [rsp+98h+dwProcessId], rax
0x180024101  mov     rdx, rax
0x180024104  lea     rcx, [rsp+98h+dwProcessId]
0x18002410c  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180024111  mov     rdi, [rsi+8]
0x180024115  call    cs:__imp_GetCurrentProcess
0x18002411b  mov     [rsp+98h+dwOptions], 2; dwOptions
0x180024123  mov     [rsp+98h+bInheritHandle], 0; bInheritHandle
0x18002412b  mov     [rsp+98h+dwDesiredAccess], 0; dwDesiredAccess
0x180024133  lea     r9, [rsp+98h+dwProcessId]; lpTargetHandle
0x18002413b  mov     r8, rbx; hTargetProcessHandle
0x18002413e  mov     rdx, rdi; hSourceHandle
0x180024141  mov     rcx, rax; hSourceProcessHandle
0x180024144  call    cs:__imp_DuplicateHandle
0x18002414a  mov     rcx, [rsp+98h]; this
0x180024152  test    eax, eax
0x180024154  jz      loc_1800242E0
0x18002415a  mov     rax, [rsp+98h+TargetHandle]
0x180024162  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180024166  mov     [rsp+98h+TargetHandle], rcx
0x18002416e  mov     rbx, [rsp+98h+arg_28]
0x180024176  mov     [rbx], rax
0x180024179  mov     rax, [rsp+98h+dwProcessId]
0x180024181  mov     [rsp+98h+dwProcessId], rcx
0x180024189  mov     rdi, [rsp+98h+arg_30]
0x180024191  mov     [rdi], rax
0x180024194  mov     rax, [rsp+98h+arg_20]
0x18002419c  mov     byte ptr [rax], 1
0x18002419f  lea     rcx, [rsp+98h+dwProcessId]
0x1800241a7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800241ac  nop
0x1800241ad  lea     rcx, [rsp+98h+TargetHandle]
0x1800241b5  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800241ba  jmp     short loc_1800241C4
0x1800241bc  mov     rbx, [rsp+98h+arg_28]
0x1800241c4  lea     rcx, [rsp+98h+arg_10]
0x1800241cc  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800241d1  jmp     short loc_1800241DB
0x1800241d3  mov     r14d, dword ptr [rsp+98h+dwProcessId]
0x1800241db  mov     eax, cs:dword_180083038
0x1800241e1  cmp     eax, 5
0x1800241e4  jbe     loc_18002429B
0x1800241ea  mov     eax, [rsi+48h]
0x1800241ed  mov     dword ptr [rsp+98h+arg_28], eax
0x1800241f4  mov     rax, [rdi]
0x1800241f7  mov     [rsp+98h+dwProcessId], rax
0x1800241ff  mov     rax, [rbx]
0x180024202  mov     [rsp+98h+TargetHandle], rax
0x18002420a  mov     eax, [r13+0]
0x18002420e  mov     dword ptr [rsp+98h+arg_30], eax
0x180024215  mov     rax, [r15]
0x180024218  mov     [rsp+98h+arg_10], rax
0x180024220  mov     rax, [r12]
0x180024224  mov     [rsp+98h+arg_18], rax
0x18002422c  mov     dword ptr [rsp+98h+arg_20], r14d
0x180024234  lea     rax, [rsp+98h+arg_28]
0x18002423c  mov     [rsp+98h+var_48], rax
0x180024241  lea     rax, [rsp+98h+dwProcessId]
0x180024249  mov     [rsp+98h+var_50], rax
0x18002424e  lea     rax, [rsp+98h+TargetHandle]
0x180024256  mov     [rsp+98h+var_58], rax
0x18002425b  lea     rax, [rsp+98h+arg_30]
0x180024263  mov     [rsp+98h+var_60], rax
0x180024268  lea     rax, [rsp+98h+arg_10]
0x180024270  mov     qword ptr [rsp+98h+dwOptions], rax
0x180024275  lea     rax, [rsp+98h+arg_18]
0x18002427d  mov     qword ptr [rsp+98h+bInheritHandle], rax
0x180024282  lea     rax, [rsp+98h+arg_20]
0x18002428a  mov     qword ptr [rsp+98h+dwDesiredAccess], rax
0x18002428f  lea     rdx, unk_180072A28
0x180024296  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@U1@U2@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@43443@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x18002429b  xor     eax, eax
0x18002429d  jmp     short loc_1800242A6
0x18002429f  mov     eax, dword ptr [rsp+98h+arg_28]
0x1800242a6  add     rsp, 60h
0x1800242aa  pop     r15
0x1800242ac  pop     r14
0x1800242ae  pop     r13
0x1800242b0  pop     r12
0x1800242b2  pop     rdi
0x1800242b3  pop     rsi
0x1800242b4  pop     rbx
0x1800242b5  retn
0x1800242b6  mov     r9d, 80070006h; char *
0x1800242bc  lea     r8, aOnecoreuapPrin_19; "onecoreuap\\printscan\\print\\workflow"...
0x1800242c3  mov     edx, 0C2h; void *
0x1800242c8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800242ce  lea     r8, aOnecoreuapPrin_19; "onecoreuap\\printscan\\print\\workflow"...
0x1800242d5  mov     edx, 0CCh; void *
0x1800242da  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800242e0  lea     r8, aOnecoreuapPrin_19; "onecoreuap\\printscan\\print\\workflow"...
0x1800242e7  mov     edx, 0D1h; void *
0x1800242ec  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
