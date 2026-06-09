# CMidiSessionTracker::RemoveClientSessionInternal(void *)

- ea: `0x14003bc20`
- end: `0x14003be64`
- name: `?RemoveClientSessionInternal@CMidiSessionTracker@@UEAAJPEAX@Z`
- size: `580`
- prototype: `__int64 __fastcall(CMidiSessionTracker *__hidden this, void *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x140001ad4`
- `0x1400060ec`
- `0x14000984c`
- `0x14000a6b4`
- `0x14000c598`
- `0x140016484`
- `0x14003a6e0`
- `0x14003bc20`
- `0x14003c664`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003be44`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14003be44`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003bccb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14003bccb`

## string_xrefs

- `0x14003bca4`: `avcore\midi2\service\exe\midisessiontracker.cpp`
- `0x14003bd6e`: `avcore\midi2\service\exe\midisessiontracker.cpp`
- `0x14003bc42`: `CMidiSessionTracker::RemoveClientSessionInternal`
- `0x14003bd93`: `CMidiSessionTracker::RemoveClientSessionInternal`

## pseudocode

```c
__int64 __fastcall CMidiSessionTracker::RemoveClientSessionInternal(CMidiSessionTracker *this, RTL_SRWLOCK *a2)
{
  _DWORD *v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  struct _RTL_CRITICAL_SECTION *v8; // r12
  __int64 v9; // rdx
  volatile signed __int32 *v10; // rsi
  signed __int32 v11; // eax
  signed __int32 v12; // ett
  const wchar_t *v13; // rbx
  unsigned __int64 *v14; // rcx
  RTL_SRWLOCK *v15; // r12
  unsigned __int64 v16; // rdi
  int v17; // eax
  _DWORD *v18; // rcx
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // [rsp+20h] [rbp-30h]
  int v22[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  PSRWLOCK SRWLock; // [rsp+98h] [rbp+48h] BYREF
  const wchar_t *v25; // [rsp+A0h] [rbp+50h] BYREF
  CMidiSessionTracker *v26; // [rsp+A8h] [rbp+58h] BYREF

  v4 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
  if ( *v4 > 4u )
  {
    SRWLock = a2;
    v25 = L"Enter";
    v26 = this;
    *(_QWORD *)v22 = "CMidiSessionTracker::RemoveClientSessionInternal";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      (__int64)v4,
      (__int64)&byte_14008AB57,
      v5,
      v6,
      v22,
      (__int64)&v26,
      &v25);
  }
  if ( a2 )
  {
    v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
    v9 = *((_QWORD *)this + 2);
    v10 = 0;
    SRWLock = 0;
    if ( v9 )
    {
      v11 = *(_DWORD *)(v9 + 8);
      while ( v11 )
      {
        v12 = v11;
        v11 = _InterlockedCompareExchange((volatile signed __int32 *)(v9 + 8), v11 + 1, v11);
        if ( v12 == v11 )
        {
          v10 = (volatile signed __int32 *)*((_QWORD *)this + 2);
          SRWLock = (PSRWLOCK)*((_QWORD *)this + 1);
          break;
        }
      }
    }
    CMidiSessionTracker::FindSessionForContextHandle(this, &v25, a2);
    v13 = v25;
    if ( v25 != *((const wchar_t **)this + 4) )
    {
      v14 = (unsigned __int64 *)*((_QWORD *)v25 + 15);
      if ( (__int64)(*((_QWORD *)v25 + 16) - (_QWORD)v14) >> 3 )
      {
        v15 = SRWLock;
        do
        {
          v16 = *v14;
          memmove_0(v14, v14 + 1, *((_QWORD *)v13 + 16) - (_QWORD)(v14 + 1));
          *((_QWORD *)v13 + 16) -= 8LL;
          v17 = CMidiClientManager::DestroyMidiClient(v15, v16);
          if ( v17 < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x175,
              (int)"avcore\\midi2\\service\\exe\\midisessiontracker.cpp",
              (const char *)(unsigned int)v17);
          v14 = (unsigned __int64 *)*((_QWORD *)v13 + 15);
        }
        while ( *((unsigned __int64 **)v13 + 16) != v14 );
        v8 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 48);
      }
      std::vector<MidiSessionEntry>::erase((char *)this + 24, &SRWLock, v13);
    }
    v18 = (_DWORD *)*((_QWORD *)MidiSrvTelemetryProvider::Instance() + 1);
    if ( *v18 > 4u )
    {
      SRWLock = a2;
      v25 = L"Exit success";
      v26 = this;
      *(_QWORD *)v22 = "CMidiSessionTracker::RemoveClientSessionInternal";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
        (__int64)v18,
        (__int64)byte_14008A9DB,
        v19,
        v20,
        v22,
        (__int64)&v26,
        &v25);
    }
    if ( v10 )
    {
      if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
    }
    if ( v8 )
      LeaveCriticalSection(v8);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x165,
      (unsigned int)"avcore\\midi2\\service\\exe\\midisessiontracker.cpp",
      (const char *)0x80070057LL,
      v21);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x14003bc20  mov     [rsp-38h+arg_0], rbx
0x14003bc25  push    rbp
0x14003bc26  push    rsi
0x14003bc27  push    rdi
0x14003bc28  push    r12
0x14003bc2a  push    r13
0x14003bc2c  push    r14
0x14003bc2e  push    r15
0x14003bc30  mov     rbp, rsp
0x14003bc33  sub     rsp, 50h
0x14003bc37  mov     r15, rdx
0x14003bc3a  mov     r14, rcx
0x14003bc3d  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003bc42  lea     rdi, aCmidisessiontr_4; "CMidiSessionTracker::RemoveClientSessio"...
0x14003bc49  mov     rcx, [rax+8]
0x14003bc4d  mov     eax, [rcx]
0x14003bc4f  cmp     eax, 4
0x14003bc52  jbe     short loc_14003BC9B
0x14003bc54  lea     rax, aEnter; "Enter"
0x14003bc5b  mov     [rbp+SRWLock], r15
0x14003bc5f  mov     [rbp+arg_10], rax
0x14003bc63  lea     rdx, byte_14008AB57
0x14003bc6a  lea     rax, [rbp+SRWLock]
0x14003bc6e  mov     [rbp+arg_18], r14
0x14003bc72  mov     [rsp+50h+var_18], rax
0x14003bc77  lea     rax, [rbp+arg_10]
0x14003bc7b  mov     [rsp+50h+var_20], rax
0x14003bc80  lea     rax, [rbp+arg_18]
0x14003bc84  mov     [rsp+50h+var_28], rax
0x14003bc89  lea     rax, [rbp+var_10]
0x14003bc8d  mov     qword ptr [rsp+50h+var_30], rax; int
0x14003bc92  mov     qword ptr [rbp+var_10], rdi
0x14003bc96  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x14003bc9b  test    r15, r15
0x14003bc9e  jnz     short loc_14003BCC4
0x14003bca0  mov     rcx, [rbp+38h]; this
0x14003bca4  lea     r8, aAvcoreMidi2Ser_5; "avcore\\midi2\\service\\exe\\midisessio"...
0x14003bcab  mov     ebx, 80070057h
0x14003bcb0  mov     edx, 165h; void *
0x14003bcb5  mov     r9d, ebx; char *
0x14003bcb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14003bcbd  mov     eax, ebx
0x14003bcbf  jmp     loc_14003BE4C
0x14003bcc4  lea     r12, [r14+30h]
0x14003bcc8  mov     rcx, r12; lpCriticalSection
0x14003bccb  call    cs:__imp_EnterCriticalSection
0x14003bcd1  mov     rdx, [r14+10h]
0x14003bcd5  xor     esi, esi
0x14003bcd7  mov     [rbp+SRWLock], 0
0x14003bcdf  test    rdx, rdx
0x14003bce2  jz      short loc_14003BD05
0x14003bce4  mov     eax, [rdx+8]
0x14003bce7  jmp     short loc_14003BCF3
0x14003bce9  lea     ecx, [rax+1]
0x14003bcec  lock cmpxchg [rdx+8], ecx
0x14003bcf1  jz      short loc_14003BCF9
0x14003bcf3  test    eax, eax
0x14003bcf5  jnz     short loc_14003BCE9
0x14003bcf7  jmp     short loc_14003BD05
0x14003bcf9  mov     rax, [r14+8]
0x14003bcfd  mov     rsi, [r14+10h]
0x14003bd01  mov     [rbp+SRWLock], rax
0x14003bd05  mov     r8, r15
0x14003bd08  lea     rdx, [rbp+arg_10]
0x14003bd0c  mov     rcx, r14
0x14003bd0f  call    ?FindSessionForContextHandle@CMidiSessionTracker@@AEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UMidiSessionEntry@@@std@@@std@@@std@@PEAX@Z; CMidiSessionTracker::FindSessionForContextHandle(void *)
0x14003bd14  mov     rbx, [rbp+arg_10]
0x14003bd18  cmp     rbx, [r14+20h]
0x14003bd1c  jz      loc_14003BDAA
0x14003bd22  mov     rcx, [rbx+78h]; void *
0x14003bd26  mov     rax, [rbx+80h]
0x14003bd2d  sub     rax, rcx
0x14003bd30  sar     rax, 3
0x14003bd34  test    rax, rax
0x14003bd37  jz      short loc_14003BD9A
0x14003bd39  mov     r12, [rbp+SRWLock]
0x14003bd3d  mov     r8, [rbx+80h]
0x14003bd44  lea     rdx, [rcx+8]; Src
0x14003bd48  mov     rdi, [rcx]
0x14003bd4b  sub     r8, rdx; Size
0x14003bd4e  call    memmove_0
0x14003bd53  add     qword ptr [rbx+80h], 0FFFFFFFFFFFFFFF8h
0x14003bd5b  mov     rdx, rdi; unsigned __int64
0x14003bd5e  mov     rcx, r12; SRWLock
0x14003bd61  call    ?DestroyMidiClient@CMidiClientManager@@QEAAJ_K@Z; CMidiClientManager::DestroyMidiClient(unsigned __int64)
0x14003bd66  test    eax, eax
0x14003bd68  jns     short loc_14003BD82
0x14003bd6a  mov     rcx, [rbp+38h]; this
0x14003bd6e  lea     r8, aAvcoreMidi2Ser_5; "avcore\\midi2\\service\\exe\\midisessio"...
0x14003bd75  mov     r9d, eax; char *
0x14003bd78  mov     edx, 175h; void *
0x14003bd7d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14003bd82  mov     rcx, [rbx+78h]
0x14003bd86  cmp     [rbx+80h], rcx
0x14003bd8d  jnz     short loc_14003BD3D
0x14003bd8f  lea     r12, [r14+30h]
0x14003bd93  lea     rdi, aCmidisessiontr_4; "CMidiSessionTracker::RemoveClientSessio"...
0x14003bd9a  mov     r8, rbx
0x14003bd9d  lea     rdx, [rbp+SRWLock]
0x14003bda1  lea     rcx, [r14+18h]
0x14003bda5  call    ?erase@?$vector@UMidiSessionEntry@@V?$allocator@UMidiSessionEntry@@@std@@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UMidiSessionEntry@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@UMidiSessionEntry@@@std@@@std@@@2@@Z; std::vector<MidiSessionEntry>::erase(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<MidiSessionEntry>>>)
0x14003bdaa  call    ?Instance@MidiSrvTelemetryProvider@@KAPEAV1@XZ; MidiSrvTelemetryProvider::Instance(void)
0x14003bdaf  mov     rcx, [rax+8]
0x14003bdb3  mov     eax, [rcx]
0x14003bdb5  cmp     eax, 4
0x14003bdb8  jbe     short loc_14003BE01
0x14003bdba  lea     rax, aExitSuccess_0; "Exit success"
0x14003bdc1  mov     [rbp+SRWLock], r15
0x14003bdc5  mov     [rbp+arg_10], rax
0x14003bdc9  lea     rdx, byte_14008A9DB
0x14003bdd0  lea     rax, [rbp+SRWLock]
0x14003bdd4  mov     [rbp+arg_18], r14
0x14003bdd8  mov     [rsp+50h+var_18], rax
0x14003bddd  lea     rax, [rbp+arg_10]
0x14003bde1  mov     [rsp+50h+var_20], rax
0x14003bde6  lea     rax, [rbp+arg_18]
0x14003bdea  mov     [rsp+50h+var_28], rax
0x14003bdef  lea     rax, [rbp+var_10]
0x14003bdf3  mov     qword ptr [rsp+50h+var_30], rax
0x14003bdf8  mov     qword ptr [rbp+var_10], rdi
0x14003bdfc  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<8> const &)
0x14003be01  test    rsi, rsi
0x14003be04  jz      short loc_14003BE3C
0x14003be06  or      ebx, 0FFFFFFFFh
0x14003be09  mov     eax, ebx
0x14003be0b  lock xadd [rsi+8], eax
0x14003be10  add     eax, ebx
0x14003be12  jnz     short loc_14003BE3C
0x14003be14  mov     rax, [rsi]
0x14003be17  mov     rcx, rsi
0x14003be1a  mov     rax, [rax]
0x14003be1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003be22  mov     eax, ebx
0x14003be24  lock xadd [rsi+0Ch], eax
0x14003be29  add     eax, ebx
0x14003be2b  jnz     short loc_14003BE3C
0x14003be2d  mov     rax, [rsi]
0x14003be30  mov     rcx, rsi
0x14003be33  mov     rax, [rax+8]
0x14003be37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003be3c  test    r12, r12
0x14003be3f  jz      short loc_14003BE4A
0x14003be41  mov     rcx, r12; lpCriticalSection
0x14003be44  call    cs:__imp_LeaveCriticalSection
0x14003be4a  xor     eax, eax
0x14003be4c  mov     rbx, [rsp+50h+arg_0]
0x14003be54  add     rsp, 50h
0x14003be58  pop     r15
0x14003be5a  pop     r14
0x14003be5c  pop     r13
0x14003be5e  pop     r12
0x14003be60  pop     rdi
0x14003be61  pop     rsi
0x14003be62  pop     rbp
0x14003be63  retn
```
