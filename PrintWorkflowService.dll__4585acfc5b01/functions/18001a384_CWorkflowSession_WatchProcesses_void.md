# CWorkflowSession::WatchProcesses(void)

- ea: `0x18001a384`
- end: `0x18001a6fd`
- name: `?WatchProcesses@CWorkflowSession@@QEAAJXZ`
- size: `889`
- prototype: `__int64 __fastcall(CWorkflowSession *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a310`

## callees

- `0x180001314`
- `0x180001708`
- `0x180003ca0`
- `0x180010b0c`
- `0x1800166a8`
- `0x180018f90`
- `0x180019da0`
- `0x180019ea4`
- `0x18001a384`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a6b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a6b1`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001a428`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001a443`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001a428`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x18001a443`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001a4b8`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18001a4b8`

## string_xrefs

- `0x18001a404`: `onecoreuap\printscan\print\workflow\broker\lib\workflowsession.cpp`
- `0x18001a5e8`: `onecoreuap\printscan\print\workflow\broker\lib\workflowsession.cpp`
- `0x18001a6c6`: `onecoreuap\printscan\print\workflow\broker\lib\workflowsession.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CWorkflowSession::WatchProcesses(CWorkflowSession *this)
{
  int v2; // eax
  unsigned int v3; // ebx
  HANDLE v4; // rbx
  HANDLE v5; // rax
  unsigned int v6; // r15d
  DWORD v7; // r12d
  DWORD v8; // eax
  __int64 v9; // r8
  __int64 v10; // r9
  DWORD v11; // esi
  __int64 v13; // rdx
  __int64 v14; // r9
  int v15; // eax
  int v16; // eax
  DWORD LastError; // eax
  unsigned int v18; // [rsp+20h] [rbp-49h]
  HANDLE v19; // [rsp+40h] [rbp-29h] BYREF
  HANDLE v20; // [rsp+48h] [rbp-21h] BYREF
  DWORD v21; // [rsp+50h] [rbp-19h] BYREF
  unsigned int v22; // [rsp+54h] [rbp-15h] BYREF
  unsigned int v23; // [rsp+58h] [rbp-11h] BYREF
  _QWORD v24[3]; // [rsp+60h] [rbp-9h] BYREF
  void *v25; // [rsp+78h] [rbp+Fh]
  HANDLE Handles; // [rsp+80h] [rbp+17h] BYREF
  __int128 v27; // [rsp+88h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  if ( (unsigned int)dword_180083038 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_180083038,
      (__int64)byte_1800700C1,
      0);
  v24[0] = &EventList::EventListNode::`vftable';
  v25 = 0;
  v2 = EventList::EventListNode::InitializeAndAddToList(
         (EventList::EventListNode *)v24,
         (CWorkflowSession *)((char *)this + 208));
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3DF,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowsession.cpp",
      (const char *)(unsigned int)v2,
      v18);
    goto LABEL_43;
  }
  while ( 1 )
  {
    v4 = OpenProcess(0x101000u, 0, *((_DWORD *)this + 67));
    v20 = v4;
    v5 = OpenProcess(0x101000u, 0, *((_DWORD *)this + 66));
    v19 = v5;
    if ( !v4 && !v5 )
    {
      v13 = 1004;
      goto LABEL_29;
    }
    v27 = 0;
    Handles = v25;
    if ( v4 )
      *(_QWORD *)&v27 = v4;
    if ( v5 )
    {
      v6 = (v4 != 0) + 1;
      v7 = (v4 != 0) + 2;
      *(&Handles + v6) = v5;
    }
    else
    {
      v6 = -1;
      v7 = (v4 != 0) + 1;
    }
    v8 = WaitForMultipleObjects(v7, &Handles, 0, 0xFFFFFFFF);
    v11 = v8;
    if ( (unsigned int)dword_180083038 > 5 )
    {
      v21 = v8;
      v22 = *((_DWORD *)this + 16);
      v23 = v7;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v22,
        (__int64)&byte_18007005F,
        v9,
        v10,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v21);
    }
    if ( v11 == -1 )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        v3 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x414,
               (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowsession.cpp",
               (const char *)LastError,
               v18);
        goto LABEL_42;
      }
LABEL_19:
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v20);
      EventList::EventListNode::~EventListNode((EventList::EventListNode *)v24);
      return 0;
    }
    if ( !v11 )
    {
      if ( (unsigned int)(*((_DWORD *)this + 16) - 2) <= 1 )
      {
        if ( (unsigned int)dword_180083038 > 5 )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            (__int64)&dword_180083038,
            (__int64)&word_18007000E,
            0);
        goto LABEL_19;
      }
      goto LABEL_27;
    }
    if ( v4 && v11 == (v4 != 0 ? 1 : -1) )
      break;
    if ( v6 == -1 || v11 != v6 )
    {
      v13 = 1093;
LABEL_29:
      v3 = -2147467259;
      v14 = 2147500037LL;
LABEL_30:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v13,
        (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\lib\\workflowsession.cpp",
        (const char *)v14,
        v18);
      goto LABEL_42;
    }
    if ( (unsigned int)(*((_DWORD *)this + 16) - 2) > 1 )
    {
      if ( (unsigned int)dword_180083038 > 5 )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          (__int64)&dword_180083038,
          (__int64)&word_18006FF5E,
          0);
      v16 = (*(__int64 (__fastcall **)(char *, __int64, __int64))(*((_QWORD *)this + 3) + 280LL))(
              (char *)this + 24,
              2,
              2147483674LL);
      v3 = v16;
      if ( v16 < 0 )
      {
        v14 = (unsigned int)v16;
        v13 = 1086;
        goto LABEL_30;
      }
      goto LABEL_42;
    }
LABEL_27:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v20);
  }
  if ( *((_DWORD *)this + 16) )
  {
    *((_DWORD *)this + 67) = 0;
    goto LABEL_27;
  }
  if ( (unsigned int)dword_180083038 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_180083038,
      (__int64)&byte_18006FFB7,
      0);
  LOBYTE(v10) = 1;
  v15 = (*(__int64 (__fastcall **)(char *, __int64, __int64, __int64))(*((_QWORD *)this + 3) + 280LL))(
          (char *)this + 24,
          2,
          2147483674LL,
          v10);
  v3 = v15;
  if ( v15 < 0 )
  {
    v14 = (unsigned int)v15;
    v13 = 1068;
    goto LABEL_30;
  }
LABEL_42:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v19);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v20);
LABEL_43:
  EventList::EventListNode::~EventListNode((EventList::EventListNode *)v24);
  return v3;
}

```

## disassembly

```asm
0x18001a384  mov     [rsp-8+arg_8], rbx
0x18001a389  mov     [rsp-8+arg_10], rsi
0x18001a38e  push    rbp
0x18001a38f  push    rdi
0x18001a390  push    r12
0x18001a392  push    r14
0x18001a394  push    r15
0x18001a396  lea     rbp, [rsp-37h]
0x18001a39b  sub     rsp, 0A0h
0x18001a3a2  mov     rax, cs:__security_cookie
0x18001a3a9  xor     rax, rsp
0x18001a3ac  mov     [rbp+57h+var_28], rax
0x18001a3b0  mov     rdi, rcx
0x18001a3b3  mov     eax, cs:dword_180083038
0x18001a3b9  cmp     eax, 5
0x18001a3bc  jbe     short loc_18001A3D4
0x18001a3be  xor     r8d, r8d
0x18001a3c1  lea     rdx, byte_1800700C1
0x18001a3c8  lea     rcx, dword_180083038
0x18001a3cf  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001a3d4  lea     rax, ??_7EventListNode@EventList@@6B@; const EventList::EventListNode::`vftable'
0x18001a3db  mov     [rbp+57h+var_60], rax
0x18001a3df  mov     [rbp+57h+var_48], 0
0x18001a3e7  lea     rdx, [rdi+0D0h]; struct EventList *
0x18001a3ee  lea     rcx, [rbp+57h+var_60]; this
0x18001a3f2  call    ?InitializeAndAddToList@EventListNode@EventList@@QEAAJPEAV2@@Z; EventList::EventListNode::InitializeAndAddToList(EventList *)
0x18001a3f7  mov     ebx, eax
0x18001a3f9  test    eax, eax
0x18001a3fb  jns     short loc_18001A41A
0x18001a3fd  mov     rcx, [rbp+5Fh]; this
0x18001a401  mov     r9d, eax; char *
0x18001a404  lea     r8, aOnecoreuapPrin_11; "onecoreuap\\printscan\\print\\workflow"...
0x18001a40b  mov     edx, 3DFh; void *
0x18001a410  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a415  jmp     loc_18001A6ED
0x18001a41a  mov     r8d, [rdi+10Ch]; dwProcessId
0x18001a421  xor     edx, edx; bInheritHandle
0x18001a423  mov     ecx, 101000h; dwDesiredAccess
0x18001a428  call    cs:__imp_OpenProcess
0x18001a42e  mov     rbx, rax
0x18001a431  mov     [rbp+57h+var_78], rax
0x18001a435  mov     r8d, [rdi+108h]; dwProcessId
0x18001a43c  xor     edx, edx; bInheritHandle
0x18001a43e  mov     ecx, 101000h; dwDesiredAccess
0x18001a443  call    cs:__imp_OpenProcess
0x18001a449  mov     [rbp+57h+var_80], rax
0x18001a44d  test    rbx, rbx
0x18001a450  jnz     short loc_18001A45B
0x18001a452  test    rax, rax
0x18001a455  jz      loc_18001A5DB
0x18001a45b  xorps   xmm0, xmm0
0x18001a45e  movdqu  [rbp+57h+var_38], xmm0
0x18001a463  mov     rcx, [rbp+57h+var_48]
0x18001a467  mov     [rbp+57h+Handles], rcx
0x18001a46b  test    rbx, rbx
0x18001a46e  jz      short loc_18001A474
0x18001a470  mov     qword ptr [rbp+57h+var_38], rbx
0x18001a474  mov     rcx, rbx
0x18001a477  neg     rcx
0x18001a47a  sbb     r14d, r14d
0x18001a47d  and     r14d, 2
0x18001a481  dec     r14d
0x18001a484  mov     rcx, rbx
0x18001a487  neg     rcx
0x18001a48a  sbb     edx, edx
0x18001a48c  neg     edx
0x18001a48e  inc     edx
0x18001a490  test    rax, rax
0x18001a493  jz      short loc_18001A4A3
0x18001a495  mov     r15d, edx
0x18001a498  lea     r12d, [rdx+1]
0x18001a49c  mov     [rbp+rdx*8+57h+Handles], rax
0x18001a4a1  jmp     short loc_18001A4AA
0x18001a4a3  or      r15d, 0FFFFFFFFh
0x18001a4a7  mov     r12d, edx
0x18001a4aa  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001a4ae  xor     r8d, r8d; bWaitAll
0x18001a4b1  lea     rdx, [rbp+57h+Handles]; lpHandles
0x18001a4b5  mov     ecx, r12d; nCount
0x18001a4b8  call    cs:__imp_WaitForMultipleObjects
0x18001a4be  mov     esi, eax
0x18001a4c0  mov     ecx, cs:dword_180083038
0x18001a4c6  cmp     ecx, 5
0x18001a4c9  jbe     short loc_18001A4FF
0x18001a4cb  mov     [rbp+57h+var_70], eax
0x18001a4ce  mov     ecx, [rdi+40h]
0x18001a4d1  mov     [rbp+57h+var_6C], ecx
0x18001a4d4  mov     [rbp+57h+var_68], r12d
0x18001a4d8  lea     rax, [rbp+57h+var_70]
0x18001a4dc  mov     [rsp+0C0h+var_90], rax
0x18001a4e1  lea     rax, [rbp+57h+var_6C]
0x18001a4e5  mov     [rsp+0C0h+var_98], rax
0x18001a4ea  lea     rax, [rbp+57h+var_68]
0x18001a4ee  mov     qword ptr [rsp+0C0h+var_A0], rax; unsigned int
0x18001a4f3  lea     rdx, byte_18007005F
0x18001a4fa  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001a4ff  or      eax, 0FFFFFFFFh
0x18001a502  cmp     esi, eax
0x18001a504  jz      loc_18001A6B1
0x18001a50a  test    esi, esi
0x18001a50c  jnz     short loc_18001A586
0x18001a50e  mov     eax, [rdi+40h]
0x18001a511  sub     eax, 2
0x18001a514  cmp     eax, 1
0x18001a517  ja      loc_18001A5C3
0x18001a51d  mov     eax, cs:dword_180083038
0x18001a523  cmp     eax, 5
0x18001a526  jbe     short loc_18001A53F
0x18001a528  xor     r8d, r8d
0x18001a52b  lea     rdx, word_18007000E
0x18001a532  lea     rcx, dword_180083038
0x18001a539  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001a53e  nop
0x18001a53f  lea     rcx, [rbp+57h+var_80]
0x18001a543  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001a548  nop
0x18001a549  lea     rcx, [rbp+57h+var_78]
0x18001a54d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001a552  nop
0x18001a553  lea     rcx, [rbp+57h+var_60]; this
0x18001a557  call    ??1EventListNode@EventList@@UEAA@XZ; EventList::EventListNode::~EventListNode(void)
0x18001a55c  xor     eax, eax
0x18001a55e  mov     rcx, [rbp+57h+var_28]
0x18001a562  xor     rcx, rsp; StackCookie
0x18001a565  call    __security_check_cookie
0x18001a56a  lea     r11, [rsp+0C0h+var_20]
0x18001a572  mov     rbx, [r11+38h]
0x18001a576  mov     rsi, [r11+40h]
0x18001a57a  mov     rsp, r11
0x18001a57d  pop     r15
0x18001a57f  pop     r14
0x18001a581  pop     r12
0x18001a583  pop     rdi
0x18001a584  pop     rbp
0x18001a585  retn
0x18001a586  test    rbx, rbx
0x18001a589  jz      short loc_18001A5A2
0x18001a58b  cmp     esi, r14d
0x18001a58e  jnz     short loc_18001A5A2
0x18001a590  cmp     dword ptr [rdi+40h], 0
0x18001a594  jz      short loc_18001A5FD
0x18001a596  mov     dword ptr [rdi+10Ch], 0
0x18001a5a0  jmp     short loc_18001A5C3
0x18001a5a2  cmp     r15d, eax
0x18001a5a5  jz      loc_18001A6A7
0x18001a5ab  cmp     esi, r15d
0x18001a5ae  jnz     loc_18001A6A7
0x18001a5b4  mov     eax, [rdi+40h]
0x18001a5b7  sub     eax, 2
0x18001a5ba  cmp     eax, 1
0x18001a5bd  ja      loc_18001A653
0x18001a5c3  lea     rcx, [rbp+57h+var_80]
0x18001a5c7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001a5cc  nop
0x18001a5cd  lea     rcx, [rbp+57h+var_78]
0x18001a5d1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001a5d6  jmp     loc_18001A41A
0x18001a5db  mov     edx, 3ECh; void *
0x18001a5e0  mov     ebx, 80004005h
0x18001a5e5  mov     r9d, ebx; char *
0x18001a5e8  lea     r8, aOnecoreuapPrin_11; "onecoreuap\\printscan\\print\\workflow"...
0x18001a5ef  mov     rcx, [rbp+5Fh]; this
0x18001a5f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a5f8  jmp     loc_18001A6D9
0x18001a5fd  mov     eax, cs:dword_180083038
0x18001a603  cmp     eax, 5
0x18001a606  jbe     short loc_18001A61E
0x18001a608  xor     r8d, r8d
0x18001a60b  lea     rdx, byte_18006FFB7
0x18001a612  lea     rcx, dword_180083038
0x18001a619  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001a61e  lea     rcx, [rdi+18h]
0x18001a622  mov     rax, [rcx]
0x18001a625  mov     r9b, 1
0x18001a628  mov     edx, 2
0x18001a62d  mov     r8d, 8000001Ah
0x18001a633  mov     rax, [rax+118h]
0x18001a63a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a63f  mov     ebx, eax
0x18001a641  test    eax, eax
0x18001a643  jns     loc_18001A6D9
0x18001a649  mov     r9d, eax
0x18001a64c  mov     edx, 42Ch
0x18001a651  jmp     short loc_18001A5E8
0x18001a653  mov     eax, cs:dword_180083038
0x18001a659  cmp     eax, 5
0x18001a65c  jbe     short loc_18001A674
0x18001a65e  xor     r8d, r8d
0x18001a661  lea     rdx, word_18006FF5E
0x18001a668  lea     rcx, dword_180083038
0x18001a66f  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18001a674  lea     rcx, [rdi+18h]
0x18001a678  mov     rax, [rcx]
0x18001a67b  xor     r9d, r9d
0x18001a67e  lea     edx, [r9+2]
0x18001a682  mov     r8d, 8000001Ah
0x18001a688  mov     rax, [rax+118h]
0x18001a68f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a694  mov     ebx, eax
0x18001a696  test    eax, eax
0x18001a698  jns     short loc_18001A6D9
0x18001a69a  mov     r9d, eax
0x18001a69d  mov     edx, 43Eh
0x18001a6a2  jmp     loc_18001A5E8
0x18001a6a7  mov     edx, 445h
0x18001a6ac  jmp     loc_18001A5E0
0x18001a6b1  call    cs:__imp_GetLastError
0x18001a6b7  test    eax, eax
0x18001a6b9  jz      loc_18001A53F
0x18001a6bf  mov     rcx, [rbp+5Fh]; this
0x18001a6c3  mov     r9d, eax; char *
0x18001a6c6  lea     r8, aOnecoreuapPrin_11; "onecoreuap\\printscan\\print\\workflow"...
0x18001a6cd  mov     edx, 414h; void *
0x18001a6d2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001a6d7  mov     ebx, eax
0x18001a6d9  lea     rcx, [rbp+57h+var_80]
0x18001a6dd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001a6e2  nop
0x18001a6e3  lea     rcx, [rbp+57h+var_78]
0x18001a6e7  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18001a6ec  nop
0x18001a6ed  lea     rcx, [rbp+57h+var_60]; this
0x18001a6f1  call    ??1EventListNode@EventList@@UEAA@XZ; EventList::EventListNode::~EventListNode(void)
0x18001a6f6  mov     eax, ebx
0x18001a6f8  jmp     loc_18001A55E
```
