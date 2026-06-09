# CSpSubsystem::_AddToQueue(ISpWmiIndication *)

- ea: `0x180074f4c`
- end: `0x1800751f9`
- name: `?_AddToQueue@CSpSubsystem@@IEAA?AW4_MI_Result@@PEAVISpWmiIndication@@@Z`
- size: `685`
- prototype: `enum _MI_Result __fastcall(CSpSubsystem *__hidden this, struct ISpWmiIndication *)`
- caller_count: `1`
- callee_count: `12`
- tags: ``

## callers

- `0x180076854`

## callees

- `0x1800011b0`
- `0x1800015b8`
- `0x1800062ec`
- `0x18000c704`
- `0x18000d14c`
- `0x180013938`
- `0x1800191e0`
- `0x180027f18`
- `0x1800288b0`
- `0x18006ce9c`
- `0x180074f4c`
- `0x1801f8010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180074fc2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180074fc2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075049`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180075049`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075025`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180075025`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007518f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007518f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180075164`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007517b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180075164`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007517b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSpSubsystem::_AddToQueue(CSpSubsystem *this, struct ISpWmiIndication *a2, int a3, int a4)
{
  struct _FILETIME v6; // rbx
  CSpSubsystem::_SP_INDICATION_INFO *v7; // rdi
  int v8; // ecx
  DWORD LastError; // ebx
  int v10; // r8d
  int v11; // r9d
  char *v12; // rdx
  enum _MI_Result v13; // esi
  CSpSubsystem::_SP_INDICATION_INFO *v14; // rbx
  unsigned __int64 v15; // rbx
  unsigned __int64 v16; // rcx
  DWORD v17; // eax
  unsigned int v18; // edx
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-19h] BYREF
  const char *v24; // [rsp+48h] [rbp-11h] BYREF
  _QWORD v25[3]; // [rsp+50h] [rbp-9h] BYREF
  int v26; // [rsp+68h] [rbp+Fh]
  _BYTE v27[8]; // [rsp+70h] [rbp+17h] BYREF
  __int64 v28; // [rsp+78h] [rbp+1Fh]
  __int64 v29; // [rsp+80h] [rbp+27h]
  int v30; // [rsp+88h] [rbp+2Fh]
  __int64 v31; // [rsp+D0h] [rbp+77h] BYREF
  const char *v32; // [rsp+D8h] [rbp+7Fh] BYREF

  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v31) = 1322;
    v32 = "CSpSubsystem::_AddToQueue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      (unsigned int)"CSpSubsystem::_AddToQueue",
      (unsigned int)&word_18031086E,
      a3,
      a4,
      (__int64)&v32,
      (__int64)&v31);
  }
  SystemTimeAsFileTime = 0;
  v25[0] = &CSmLinkedListIterator<CSpSubsystem::_SP_INDICATION_INFO *>::`vftable';
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v6 = SystemTimeAsFileTime;
  v7 = (CSpSubsystem::_SP_INDICATION_INFO *)operator new(0x18u);
  *((_QWORD *)v7 + 1) = 0;
  *((_QWORD *)v7 + 2) = 0;
  *(_QWORD *)v7 = 0;
  CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(v7);
  *(_QWORD *)v7 = 0;
  CSmRefPtrBase<CSpWmiAssociation::LocalDataSource<CSpStorageEnclosure::LocalDataSource,CSpPhysicalDisk::LocalDataSource>>::_Assign(
    v7,
    a2);
  *((_QWORD *)v7 + 1) = MISpaceHandle::GetTime(MISpaceHandle::g_MISpaceHandle);
  *((struct _FILETIME *)v7 + 2) = v6;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  if ( !(*(unsigned __int8 (__fastcall **)(char *, CSpSubsystem::_SP_INDICATION_INFO *))(*((_QWORD *)this + 7) + 8LL))(
          (char *)this + 56,
          v7) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError != 122 )
      {
        if ( (unsigned int)dword_180397B68 <= 2 )
          goto LABEL_13;
        LODWORD(v31) = LastError;
        v12 = byte_18031286D;
        goto LABEL_10;
      }
      if ( (unsigned int)dword_180397B68 > 3 )
      {
        LODWORD(v31) = 122;
        v12 = &byte_18031210F;
        goto LABEL_10;
      }
    }
    else
    {
      v8 = dword_180397B68;
      if ( (unsigned int)dword_180397B68 > 4 )
      {
        LODWORD(v31) = 0;
        v12 = (char *)qword_180310BC8;
LABEL_10:
        LODWORD(v32) = 1356;
        v24 = "CSpSubsystem::_AddToQueue";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v8,
          (_DWORD)v12,
          v10,
          v11,
          (__int64)&v24,
          (__int64)&v32,
          (__int64)&v31);
      }
    }
LABEL_13:
    v13 = MI_FROM_WIN32(LastError);
    v14 = v7;
    goto LABEL_22;
  }
  v13 = MI_RESULT_OK;
  v31 = 0;
  CSmLinkedListIterator<unsigned short *>::CSmLinkedListIterator<unsigned short *>(v27, (char *)this + 56);
  v25[1] = v28;
  v25[2] = v29;
  v26 = v30;
  if ( (unsigned __int8)CSmLinkedListIterator<_SU_TP_CONTEXT *>::GetNext(v25, &v31) )
  {
    v15 = *(_QWORD *)&v6 + 50000000LL;
    v16 = *(_QWORD *)(v31 + 16) + 300000000LL;
    if ( v15 >= v16 )
    {
      v31 = *(_QWORD *)(v31 + 16) + 300000000LL;
      v17 = v16;
    }
    else
    {
      v31 = v15;
      v17 = v15;
    }
    SystemTimeAsFileTime.dwLowDateTime = v17;
    if ( v15 >= v16 )
      HIDWORD(v15) = HIDWORD(v16);
    SystemTimeAsFileTime.dwHighDateTime = HIDWORD(v15);
    SetThreadpoolTimer(*((PTP_TIMER *)this + 16), 0, 0, 0);
    SetThreadpoolTimer(*((PTP_TIMER *)this + 16), &SystemTimeAsFileTime, 0, 0);
  }
  v7 = 0;
  v14 = 0;
LABEL_22:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
  if ( v7 && v14 )
    CSpSubsystem::_SP_INDICATION_INFO::`scalar deleting destructor'(v14, v18);
  if ( (unsigned int)dword_180397B68 > 5 )
  {
    LODWORD(v31) = 1408;
    v32 = "CSpSubsystem::_AddToQueue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v19,
      (unsigned int)byte_18030E021,
      v20,
      v21,
      (__int64)&v32,
      (__int64)&v31);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180074f4c  mov     [rsp-8+arg_0], rbx
0x180074f51  mov     [rsp-8+arg_8], rsi
0x180074f56  push    rbp
0x180074f57  push    rdi
0x180074f58  push    r12
0x180074f5a  push    r14
0x180074f5c  push    r15
0x180074f5e  lea     rbp, [rsp-37h]
0x180074f63  sub     rsp, 90h
0x180074f6a  mov     rsi, rdx
0x180074f6d  mov     r14, rcx
0x180074f70  mov     eax, cs:dword_180397B68
0x180074f76  lea     rcx, aCspsubsystemAd; "CSpSubsystem::_AddToQueue"
0x180074f7d  cmp     eax, 5
0x180074f80  jbe     short loc_180074FAB
0x180074f82  mov     dword ptr [rbp+57h+arg_10], 52Ah
0x180074f89  mov     [rbp+57h+arg_18], rcx
0x180074f8d  lea     rax, [rbp+57h+arg_10]
0x180074f91  mov     [rsp+0B0h+var_88], rax
0x180074f96  lea     rax, [rbp+57h+arg_18]
0x180074f9a  mov     [rsp+0B0h+var_90], rax
0x180074f9f  lea     rdx, word_18031086E
0x180074fa6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180074fab  mov     qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180074fb3  lea     rax, ??_7?$CSmLinkedListIterator@PEAU_SP_INDICATION_INFO@CSpSubsystem@@@@6B@; const CSmLinkedListIterator<CSpSubsystem::_SP_INDICATION_INFO *>::`vftable'
0x180074fba  mov     [rbp+57h+var_60], rax
0x180074fbe  lea     rcx, [rbp+57h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180074fc2  call    cs:__imp_GetSystemTimeAsFileTime
0x180074fc8  mov     rbx, qword ptr [rbp+57h+SystemTimeAsFileTime.dwLowDateTime]
0x180074fcc  mov     ecx, 18h; Size
0x180074fd1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180074fd6  mov     rdi, rax
0x180074fd9  mov     qword ptr [rax+8], 0
0x180074fe1  mov     qword ptr [rax+10h], 0
0x180074fe9  mov     qword ptr [rax], 0
0x180074ff0  mov     rcx, rax
0x180074ff3  call    ?Release@?$CSmRefPtrBase@VToStorageEnclosure@CSpSubsystem@@@@QEAAXXZ; CSmRefPtrBase<CSpSubsystem::ToStorageEnclosure>::Release(void)
0x180074ff8  mov     qword ptr [rdi], 0
0x180074fff  mov     rdx, rsi
0x180075002  mov     rcx, rdi
0x180075005  call    ?_Assign@?$CSmRefPtrBase@V?$LocalDataSource@V0CSpStorageEnclosure@@V0CSpPhysicalDisk@@@CSpWmiAssociation@@@@IEAAXPEAV?$LocalDataSource@V0CSpStorageEnclosure@@V0CSpPhysicalDisk@@@CSpWmiAssociation@@@Z; CSmRefPtrBase<CSpWmiAssociation::LocalDataSource<CSpStorageEnclosure::LocalDataSource,CSpPhysicalDisk::LocalDataSource>>::_Assign(CSpWmiAssociation::LocalDataSource<CSpStorageEnclosure::LocalDataSource,CSpPhysicalDisk::LocalDataSource> *)
0x18007500a  mov     rcx, cs:?g_MISpaceHandle@MISpaceHandle@@0PEAV1@EA; lpCriticalSection
0x180075011  call    ?GetTime@MISpaceHandle@@QEAA_KXZ; MISpaceHandle::GetTime(void)
0x180075016  mov     [rdi+8], rax
0x18007501a  mov     [rdi+10h], rbx
0x18007501e  lea     r12, [r14+58h]
0x180075022  mov     rcx, r12; lpCriticalSection
0x180075025  call    cs:__imp_EnterCriticalSection
0x18007502b  lea     r15, [r14+38h]
0x18007502f  mov     rax, [r15]
0x180075032  mov     rdx, rdi
0x180075035  mov     rcx, r15
0x180075038  mov     rax, [rax+8]
0x18007503c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075041  test    al, al
0x180075043  jnz     loc_1800750E3
0x180075049  call    cs:__imp_GetLastError
0x18007504f  mov     ebx, eax
0x180075051  test    eax, eax
0x180075053  jnz     short loc_18007506C
0x180075055  mov     ecx, cs:dword_180397B68
0x18007505b  cmp     ecx, 4
0x18007505e  jbe     short loc_1800750CB
0x180075060  mov     dword ptr [rbp+57h+arg_10], eax
0x180075063  lea     rdx, qword_180310BC8
0x18007506a  jmp     short loc_180075086
0x18007506c  mov     eax, cs:dword_180397B68
0x180075072  cmp     ebx, 7Ah ; 'z'
0x180075075  jnz     short loc_1800750BA
0x180075077  cmp     eax, 3
0x18007507a  jbe     short loc_1800750CB
0x18007507c  mov     dword ptr [rbp+57h+arg_10], ebx
0x18007507f  lea     rdx, byte_18031210F
0x180075086  lea     rax, [rbp+57h+arg_10]
0x18007508a  mov     [rsp+0B0h+var_80], rax
0x18007508f  lea     rax, [rbp+57h+arg_18]
0x180075093  mov     [rsp+0B0h+var_88], rax
0x180075098  lea     r14, aCspsubsystemAd; "CSpSubsystem::_AddToQueue"
0x18007509f  lea     rax, [rbp+57h+var_68]
0x1800750a3  mov     dword ptr [rbp+57h+arg_18], 54Ch
0x1800750aa  mov     [rbp+57h+var_68], r14
0x1800750ae  mov     [rsp+0B0h+var_90], rax
0x1800750b3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800750b8  jmp     short loc_1800750D2
0x1800750ba  cmp     eax, 2
0x1800750bd  jbe     short loc_1800750CB
0x1800750bf  mov     dword ptr [rbp+57h+arg_10], ebx
0x1800750c2  lea     rdx, byte_18031286D
0x1800750c9  jmp     short loc_180075086
0x1800750cb  lea     r14, aCspsubsystemAd; "CSpSubsystem::_AddToQueue"
0x1800750d2  mov     ecx, ebx; unsigned int
0x1800750d4  call    ?MI_FROM_WIN32@@YA?AW4_MI_Result@@K@Z; MI_FROM_WIN32(ulong)
0x1800750d9  mov     esi, eax
0x1800750db  mov     rbx, rdi
0x1800750de  jmp     loc_18007518C
0x1800750e3  xor     esi, esi
0x1800750e5  mov     [rbp+57h+arg_10], rsi
0x1800750e9  mov     rdx, r15
0x1800750ec  lea     rcx, [rbp+57h+var_40]
0x1800750f0  call    ??0?$CSmLinkedListIterator@PEAG@@QEAA@PEAV?$CSmLinkedList@PEAG@@@Z; CSmLinkedListIterator<ushort *>::CSmLinkedListIterator<ushort *>(CSmLinkedList<ushort *> *)
0x1800750f5  mov     rcx, [rbp+57h+var_38]
0x1800750f9  mov     [rbp+57h+var_58], rcx
0x1800750fd  mov     rax, [rbp+57h+var_30]
0x180075101  mov     [rbp+57h+var_50], rax
0x180075105  mov     eax, [rbp+57h+var_28]
0x180075108  mov     [rbp+57h+var_48], eax
0x18007510b  lea     rdx, [rbp+57h+arg_10]
0x18007510f  lea     rcx, [rbp+57h+var_60]
0x180075113  call    ?GetNext@?$CSmLinkedListIterator@PEAU_SU_TP_CONTEXT@@@@UEAA_NPEAPEAU_SU_TP_CONTEXT@@@Z; CSmLinkedListIterator<_SU_TP_CONTEXT *>::GetNext(_SU_TP_CONTEXT * *)
0x180075118  test    al, al
0x18007511a  jz      short loc_180075181
0x18007511c  add     rbx, 2FAF080h
0x180075123  mov     rax, [rbp+57h+arg_10]
0x180075127  mov     rcx, [rax+10h]
0x18007512b  add     rcx, 11E1A300h
0x180075132  cmp     rbx, rcx
0x180075135  jnb     short loc_180075140
0x180075137  mov     [rbp+57h+arg_10], rbx
0x18007513b  mov     rax, rbx
0x18007513e  jmp     short loc_180075147
0x180075140  mov     [rbp+57h+arg_10], rcx
0x180075144  mov     rax, rcx
0x180075147  mov     [rbp+57h+SystemTimeAsFileTime.dwLowDateTime], eax
0x18007514a  cmovnb  rbx, rcx
0x18007514e  shr     rbx, 20h
0x180075152  mov     [rbp+57h+SystemTimeAsFileTime.dwHighDateTime], ebx
0x180075155  xor     r9d, r9d; msWindowLength
0x180075158  xor     r8d, r8d; msPeriod
0x18007515b  xor     edx, edx; pftDueTime
0x18007515d  mov     rcx, [r14+80h]; pti
0x180075164  call    cs:__imp_SetThreadpoolTimer
0x18007516a  xor     r9d, r9d; msWindowLength
0x18007516d  xor     r8d, r8d; msPeriod
0x180075170  lea     rdx, [rbp+57h+SystemTimeAsFileTime]; pftDueTime
0x180075174  mov     rcx, [r14+80h]; pti
0x18007517b  call    cs:__imp_SetThreadpoolTimer
0x180075181  xor     edi, edi
0x180075183  xor     ebx, ebx
0x180075185  lea     r14, aCspsubsystemAd; "CSpSubsystem::_AddToQueue"
0x18007518c  mov     rcx, r12; lpCriticalSection
0x18007518f  call    cs:__imp_LeaveCriticalSection
0x180075195  test    rdi, rdi
0x180075198  jz      short loc_1800751A7
0x18007519a  test    rbx, rbx
0x18007519d  jz      short loc_1800751A7
0x18007519f  mov     rcx, rbx; this
0x1800751a2  call    ??_G_SP_INDICATION_INFO@CSpSubsystem@@QEAAPEAXI@Z; CSpSubsystem::_SP_INDICATION_INFO::`scalar deleting destructor'(uint)
0x1800751a7  mov     eax, cs:dword_180397B68
0x1800751ad  cmp     eax, 5
0x1800751b0  jbe     short loc_1800751DB
0x1800751b2  mov     dword ptr [rbp+57h+arg_10], 580h
0x1800751b9  mov     [rbp+57h+arg_18], r14
0x1800751bd  lea     rax, [rbp+57h+arg_10]
0x1800751c1  mov     [rsp+0B0h+var_88], rax
0x1800751c6  lea     rax, [rbp+57h+arg_18]
0x1800751ca  mov     [rsp+0B0h+var_90], rax
0x1800751cf  lea     rdx, byte_18030E021
0x1800751d6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800751db  mov     eax, esi
0x1800751dd  lea     r11, [rsp+0B0h+var_20]
0x1800751e5  mov     rbx, [r11+30h]
0x1800751e9  mov     rsi, [r11+38h]
0x1800751ed  mov     rsp, r11
0x1800751f0  pop     r15
0x1800751f2  pop     r14
0x1800751f4  pop     r12
0x1800751f6  pop     rdi
0x1800751f7  pop     rbp
0x1800751f8  retn
```
