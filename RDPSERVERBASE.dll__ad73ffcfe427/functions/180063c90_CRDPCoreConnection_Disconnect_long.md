# CRDPCoreConnection::Disconnect(long)

- ea: `0x180063c90`
- end: `0x180063fa1`
- name: `?Disconnect@CRDPCoreConnection@@UEAAJJ@Z`
- size: `785`
- prototype: `__int64 __fastcall(CRDPCoreConnection *__hidden this, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18010bc50`

## callees

- `0x18000116c`
- `0x18000d340`
- `0x18002aafc`
- `0x18002b14c`
- `0x18004f5bc`
- `0x180063c90`
- `0x180076090`
- `0x180079770`
- `0x18007a404`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063f54`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180063f54`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180063edf`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180063edf`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180063f30`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x180063f30`

## string_xrefs

- `0x180063dd6`: `UMTSCommandPlugin`
- `0x180063e13`: `Failed to get command plugin property form core connection`
- `0x180063ea1`: `Failed ScheduleDisconnect`
- `0x180063d5d`: `Disconnect has already been scheduled`

## pseudocode

```c
__int64 __fastcall CRDPCoreConnection::Disconnect(void **this, unsigned int a2)
{
  signed int v4; // esi
  unsigned int CurrentThreadActivityIdPrefix; // eax
  CTSCriticalSection *v6; // rbx
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  void *v10; // rcx
  int v11; // eax
  char v12; // si
  unsigned int v13; // eax
  unsigned int v14; // eax
  HANDLE EventW; // rdi
  BOOL v16; // edi
  signed int LastError; // eax
  __int64 v18; // rcx
  char *v20; // [rsp+50h] [rbp-20h] BYREF
  const char *v21; // [rsp+58h] [rbp-18h] BYREF
  const char *v22; // [rsp+60h] [rbp-10h] BYREF
  const char *v23; // [rsp+68h] [rbp-8h] BYREF
  int v24; // [rsp+A8h] [rbp+38h] BYREF
  int v25; // [rsp+B0h] [rbp+40h] BYREF
  __int64 v26; // [rsp+B8h] [rbp+48h] BYREF

  v26 = 0;
  if ( a2 == 268435457 )
  {
    v4 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        WPP_f3582f31437831a1a4f9d3b74ce86f9d_Traceguids,
        CurrentThreadActivityIdPrefix);
    }
    CRDPCoreConnection::AbortConnection((CRDPCoreConnection *)this);
    goto LABEL_29;
  }
  v6 = (CTSCriticalSection *)(this + 27);
  v20 = (char *)(this + 27);
  CTSCriticalSection::Lock((CTSCriticalSection *)(this + 27));
  if ( *((_DWORD *)this + 62) )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v24 = 447;
      v21 = "Disconnect";
      v25 = -2147467259;
      v22 = "onecore\\termsrv\\rdpplatform\\rdpenc\\enccore\\coreconnection.cpp";
      v23 = "Disconnect has already been scheduled";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v7,
        (unsigned int)byte_180287561,
        v8,
        v9,
        (__int64)&v23,
        (__int64)&v25,
        (__int64)&v22,
        (__int64)&v24,
        (__int64)&v21);
    }
    v4 = 0;
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v20);
    goto LABEL_29;
  }
  v10 = this[16];
  *((_DWORD *)this + 52) = a2;
  *((_DWORD *)this + 62) = 1;
  *((_DWORD *)this + 50) = 1;
  v11 = (*(__int64 (__fastcall **)(void *, const wchar_t *, GUID *, __int64 *))(*(_QWORD *)v10 + 48LL))(
          v10,
          L"UMTSCommandPlugin",
          &IID_IUMTSCommandMgr,
          &v26);
  v12 = v11;
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v13 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        33,
        (unsigned int)WPP_f3582f31437831a1a4f9d3b74ce86f9d_Traceguids,
        v13,
        (__int64)"Failed to get command plugin property form core connection",
        v12);
    }
    CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v20);
LABEL_28:
    v4 = CRDPCoreConnection::AbortConnection((CRDPCoreConnection *)this);
    goto LABEL_29;
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v20);
  v4 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v26 + 64LL))(v26, a2);
  if ( v4 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v14 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        34,
        (unsigned int)WPP_f3582f31437831a1a4f9d3b74ce86f9d_Traceguids,
        v14,
        (__int64)"Failed ScheduleDisconnect",
        v4);
    }
    goto LABEL_28;
  }
  EventW = CreateEventW(0, 0, 0, 0);
  if ( EventW )
  {
    (*(void (__fastcall **)(void *))(*(_QWORD *)this[6] + 8LL))(this[6]);
    CTSCriticalSection::Lock(v6);
    this[21] = EventW;
    v16 = RegisterWaitForSingleObject(this + 19, EventW, CRDPCoreConnection::STATIC_WaitCallback, this, 0x1388u, 8u);
    CTSCriticalSection::UnLock(v6);
    if ( v16 )
      goto LABEL_29;
    (*(void (__fastcall **)(void *))(*(_QWORD *)this[6] + 16LL))(this[6]);
  }
  LastError = GetLastError();
  v4 = LastError;
  if ( LastError > 0 )
    v4 = (unsigned __int16)LastError | 0x80070000;
  if ( v4 < 0 )
    goto LABEL_28;
LABEL_29:
  v18 = v26;
  if ( v26 )
  {
    v26 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180063c90  push    rbp
0x180063c92  push    rbx
0x180063c93  push    rsi
0x180063c94  push    rdi
0x180063c95  push    r14
0x180063c97  mov     rbp, rsp
0x180063c9a  sub     rsp, 70h
0x180063c9e  mov     [rbp+arg_18], 0
0x180063ca6  mov     edi, edx
0x180063ca8  mov     r14, rcx
0x180063cab  cmp     edx, 10000001h
0x180063cb1  jnz     short loc_180063D06
0x180063cb3  xor     esi, esi
0x180063cb5  mov     rcx, cs:WPP_GLOBAL_Control
0x180063cbc  lea     rax, WPP_GLOBAL_Control
0x180063cc3  cmp     rcx, rax
0x180063cc6  jz      short loc_180063CF9
0x180063cc8  test    dword ptr [rcx+1Ch], 400h
0x180063ccf  jz      short loc_180063CF9
0x180063cd1  cmp     byte ptr [rcx+19h], 4
0x180063cd5  jb      short loc_180063CF9
0x180063cd7  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180063cdc  mov     rcx, cs:WPP_GLOBAL_Control
0x180063ce3  lea     edx, [rsi+20h]
0x180063ce6  mov     r9d, eax
0x180063ce9  lea     r8, WPP_f3582f31437831a1a4f9d3b74ce86f9d_Traceguids
0x180063cf0  mov     rcx, [rcx+10h]
0x180063cf4  call    WPP_SF_d
0x180063cf9  mov     rcx, r14; this
0x180063cfc  call    ?AbortConnection@CRDPCoreConnection@@UEAAJXZ; CRDPCoreConnection::AbortConnection(void)
0x180063d01  jmp     loc_180063F77
0x180063d06  lea     rbx, [rcx+0D8h]
0x180063d0d  mov     rcx, rbx; this
0x180063d10  mov     [rbp+var_20], rbx
0x180063d14  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180063d19  cmp     dword ptr [r14+0F8h], 0
0x180063d21  jz      loc_180063DAA
0x180063d27  mov     eax, cs:CallbackContext
0x180063d2d  cmp     eax, 2
0x180063d30  jbe     short loc_180063D9A
0x180063d32  lea     rax, aDisconnect; "Disconnect"
0x180063d39  mov     [rbp+arg_8], 1BFh
0x180063d40  mov     [rbp+var_18], rax
0x180063d44  lea     rdx, byte_180287561
0x180063d4b  lea     rax, aOnecoreTermsrv_11; "onecore\\termsrv\\rdpplatform\\rdpenc\\"...
0x180063d52  mov     [rbp+arg_10], 80004005h
0x180063d59  mov     [rbp+var_10], rax
0x180063d5d  lea     rax, aDisconnectHasA; "Disconnect has already been scheduled"
0x180063d64  mov     [rbp+var_8], rax
0x180063d68  lea     rax, [rbp+var_18]
0x180063d6c  mov     [rsp+70h+var_30], rax
0x180063d71  lea     rax, [rbp+arg_8]
0x180063d75  mov     [rsp+70h+var_38], rax
0x180063d7a  lea     rax, [rbp+var_10]
0x180063d7e  mov     [rsp+70h+var_40], rax
0x180063d83  lea     rax, [rbp+arg_10]
0x180063d87  mov     qword ptr [rsp+70h+dwFlags], rax
0x180063d8c  lea     rax, [rbp+var_8]
0x180063d90  mov     qword ptr [rsp+70h+dwMilliseconds], rax
0x180063d95  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180063d9a  xor     esi, esi
0x180063d9c  lea     rcx, [rbp+var_20]; this
0x180063da0  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180063da5  jmp     loc_180063F77
0x180063daa  mov     rcx, [r14+80h]
0x180063db1  lea     r9, [rbp+arg_18]
0x180063db5  mov     eax, 1
0x180063dba  mov     [r14+0D0h], edi
0x180063dc1  mov     [r14+0F8h], eax
0x180063dc8  lea     r8, IID_IUMTSCommandMgr
0x180063dcf  mov     [r14+0C8h], eax
0x180063dd6  lea     rdx, aUmtscommandplu; "UMTSCommandPlugin"
0x180063ddd  mov     rax, [rcx]
0x180063de0  mov     rax, [rax+30h]
0x180063de4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063de9  mov     esi, eax
0x180063deb  test    eax, eax
0x180063ded  jns     short loc_180063E50
0x180063def  mov     rcx, cs:WPP_GLOBAL_Control
0x180063df6  lea     rax, WPP_GLOBAL_Control
0x180063dfd  cmp     rcx, rax
0x180063e00  jz      short loc_180063E42
0x180063e02  test    byte ptr [rcx+1Ch], 8
0x180063e06  jz      short loc_180063E42
0x180063e08  cmp     byte ptr [rcx+19h], 2
0x180063e0c  jb      short loc_180063E42
0x180063e0e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180063e13  lea     rcx, aFailedToGetCom_3; "Failed to get command plugin property f"...
0x180063e1a  mov     [rsp+70h+dwFlags], esi
0x180063e1e  mov     qword ptr [rsp+70h+dwMilliseconds], rcx
0x180063e23  lea     r8, WPP_f3582f31437831a1a4f9d3b74ce86f9d_Traceguids
0x180063e2a  mov     rcx, cs:WPP_GLOBAL_Control
0x180063e31  mov     edx, 21h ; '!'
0x180063e36  mov     r9d, eax
0x180063e39  mov     rcx, [rcx+10h]
0x180063e3d  call    WPP_SF_DsD
0x180063e42  lea     rcx, [rbp+var_20]; this
0x180063e46  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180063e4b  jmp     loc_180063F6D
0x180063e50  lea     rcx, [rbp+var_20]; this
0x180063e54  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180063e59  mov     rcx, [rbp+arg_18]
0x180063e5d  mov     edx, edi
0x180063e5f  mov     rax, [rcx]
0x180063e62  mov     rax, [rax+40h]
0x180063e66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063e6b  mov     esi, eax
0x180063e6d  test    eax, eax
0x180063e6f  jns     short loc_180063ED5
0x180063e71  mov     rcx, cs:WPP_GLOBAL_Control
0x180063e78  lea     rax, WPP_GLOBAL_Control
0x180063e7f  cmp     rcx, rax
0x180063e82  jz      loc_180063F6D
0x180063e88  test    byte ptr [rcx+1Ch], 8
0x180063e8c  jz      loc_180063F6D
0x180063e92  cmp     byte ptr [rcx+19h], 2
0x180063e96  jb      loc_180063F6D
0x180063e9c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180063ea1  lea     rcx, aFailedSchedule; "Failed ScheduleDisconnect"
0x180063ea8  mov     [rsp+70h+dwFlags], esi
0x180063eac  mov     qword ptr [rsp+70h+dwMilliseconds], rcx
0x180063eb1  lea     r8, WPP_f3582f31437831a1a4f9d3b74ce86f9d_Traceguids
0x180063eb8  mov     rcx, cs:WPP_GLOBAL_Control
0x180063ebf  mov     edx, 22h ; '"'
0x180063ec4  mov     r9d, eax
0x180063ec7  mov     rcx, [rcx+10h]
0x180063ecb  call    WPP_SF_DsD
0x180063ed0  jmp     loc_180063F6D
0x180063ed5  xor     r9d, r9d; lpName
0x180063ed8  xor     r8d, r8d; bInitialState
0x180063edb  xor     edx, edx; bManualReset
0x180063edd  xor     ecx, ecx; lpEventAttributes
0x180063edf  call    cs:__imp_CreateEventW
0x180063ee5  mov     rdi, rax
0x180063ee8  test    rax, rax
0x180063eeb  jz      short loc_180063F54
0x180063eed  mov     rcx, [r14+30h]
0x180063ef1  mov     rax, [rcx]
0x180063ef4  mov     rax, [rax+8]
0x180063ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063efd  mov     rcx, rbx; this
0x180063f00  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180063f05  lea     rcx, [r14+98h]; phNewWaitObject
0x180063f0c  mov     [rsp+70h+dwFlags], 8; dwFlags
0x180063f14  mov     r9, r14; Context
0x180063f17  mov     [r14+0A8h], rdi
0x180063f1e  lea     r8, ?STATIC_WaitCallback@CRDPCoreConnection@@KAXPEAXE@Z; Callback
0x180063f25  mov     [rsp+70h+dwMilliseconds], 1388h; dwMilliseconds
0x180063f2d  mov     rdx, rdi; hObject
0x180063f30  call    cs:__imp_RegisterWaitForSingleObject
0x180063f36  mov     rcx, rbx; this
0x180063f39  mov     edi, eax
0x180063f3b  call    ?UnLock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::UnLock(void)
0x180063f40  test    edi, edi
0x180063f42  jnz     short loc_180063F77
0x180063f44  mov     rcx, [r14+30h]
0x180063f48  mov     rax, [rcx]
0x180063f4b  mov     rax, [rax+10h]
0x180063f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063f54  call    cs:__imp_GetLastError
0x180063f5a  mov     esi, eax
0x180063f5c  test    eax, eax
0x180063f5e  jle     short loc_180063F69
0x180063f60  movzx   esi, ax
0x180063f63  or      esi, 80070000h
0x180063f69  test    esi, esi
0x180063f6b  jns     short loc_180063F77
0x180063f6d  mov     rcx, r14; this
0x180063f70  call    ?AbortConnection@CRDPCoreConnection@@UEAAJXZ; CRDPCoreConnection::AbortConnection(void)
0x180063f75  mov     esi, eax
0x180063f77  mov     rcx, [rbp+arg_18]
0x180063f7b  test    rcx, rcx
0x180063f7e  jz      short loc_180063F94
0x180063f80  mov     [rbp+arg_18], 0
0x180063f88  mov     rax, [rcx]
0x180063f8b  mov     rax, [rax+10h]
0x180063f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180063f94  mov     eax, esi
0x180063f96  add     rsp, 70h
0x180063f9a  pop     r14
0x180063f9c  pop     rdi
0x180063f9d  pop     rsi
0x180063f9e  pop     rbx
0x180063f9f  pop     rbp
0x180063fa0  retn
```
