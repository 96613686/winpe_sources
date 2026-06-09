# ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry::StopActivity(void)

- ea: `0x180016e50`
- end: `0x1800170d3`
- name: `?StopActivity@AutopilotHardwareDetectionChangeTaskTelemetry@ZeroTouchProvCxhTelemetry@@MEAAXXZ`
- size: `643`
- prototype: `void __fastcall(ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x180001008`
- `0x180001c40`
- `0x1800159d4`
- `0x180015a50`
- `0x180016284`
- `0x180016e50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016eaa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001703d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180016eaa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001703d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017074`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180017074`

## pseudocode

```c
void __fastcall ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry::StopActivity(
        ZeroTouchProvCxhTelemetry::AutopilotHardwareDetectionChangeTaskTelemetry *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  const struct _tlgProvider_t *v7; // r9
  __int64 v8; // rax
  __int64 v9; // r8
  RTL_SRWLOCK *v10; // rcx
  const struct _tlgProvider_t *v11; // rax
  const struct _tlgProvider_t *v12; // rdi
  __int64 v13; // rax
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  int v16; // r9d
  int v17; // [rsp+A0h] [rbp-19h] BYREF
  int v18; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v19; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v20; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v21; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v22; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v23; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v24; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v25; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v26; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v27; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v28[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v30; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v31; // [rsp+130h] [rbp+77h] BYREF
  int v32; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = AutoPilotTelemProvider::Provider();
    v7 = v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      v8 = *((_QWORD *)v6 + 3);
      if ( (*((_QWORD *)v7 + 2) & 0x800000000000LL) != 0 && (v8 & 0x800000000000LL) == v8 )
      {
        v9 = *((_QWORD *)this + 34);
        v19 = *((_QWORD *)v4 + 15);
        v20 = *((_QWORD *)v4 + 14);
        LODWORD(SRWLock) = v4[26];
        v21 = *((_QWORD *)v4 + 12);
        v22 = *((_QWORD *)v4 + 11);
        v30 = v4[20];
        v23 = *((_QWORD *)v4 + 9);
        LODWORD(v31) = v4[8];
        v24 = *((_QWORD *)v4 + 3);
        v32 = *v4;
        v25 = *((_QWORD *)v4 + 16);
        v17 = v4[16];
        v26 = *((_QWORD *)v4 + 7);
        v18 = v4[2];
        v27 = 0x1000000;
        v28[0] = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v7,
          (unsigned int)&word_18003A456,
          v9 + 8,
          (_DWORD)v7,
          (__int64)v28,
          (__int64)&v27,
          (__int64)&v18,
          (__int64)&v26,
          (__int64)&v17,
          (__int64)&v25,
          (__int64)&v32,
          (__int64)&v24,
          (__int64)&v31,
          (__int64)&v23,
          (__int64)&v30,
          (__int64)&v22,
          (__int64)&v21,
          (__int64)&SRWLock,
          (__int64)&v20,
          (__int64)&v19);
      }
    }
  }
  else
  {
    wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v10 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v10 )
      ReleaseSRWLockExclusive(v10);
    v11 = AutoPilotTelemProvider::Provider();
    v12 = v11;
    if ( *(_DWORD *)v11 > 5u )
    {
      v13 = *((_QWORD *)v11 + 3);
      if ( (*((_QWORD *)v12 + 2) & 0x800000000000LL) != 0 && (v13 & 0x800000000000LL) == v13 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v15 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v30 = *(_DWORD *)(v15 + 72);
        v31 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (_DWORD)v12,
          (unsigned int)&unk_18003A2B0,
          v15 + 8,
          v16,
          (__int64)&v31,
          (__int64)&v30,
          (__int64)&SRWLock);
      }
    }
  }
  wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180016e50  push    rbp
0x180016e52  push    rbx
0x180016e53  push    rdi
0x180016e54  lea     rbp, [rsp-47h]
0x180016e59  sub     rsp, 100h
0x180016e60  mov     rdi, [rcx+110h]
0x180016e67  mov     rbx, rcx
0x180016e6a  mov     eax, [rdi+48h]
0x180016e6d  test    eax, eax
0x180016e6f  jns     loc_18001701E
0x180016e75  add     rdi, 50h ; 'P'
0x180016e79  cmp     eax, [rdi+8]
0x180016e7c  jnz     loc_18001701E
0x180016e82  test    rdi, rdi
0x180016e85  jz      loc_18001701E
0x180016e8b  lea     rdx, [rbp+57h+SRWLock]
0x180016e8f  call    ?LockExclusive@?$ActivityBase@VAutoPilotTelemProvider@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180016e94  mov     rax, [rbx+110h]
0x180016e9b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180016e9f  mov     dword ptr [rax], 2
0x180016ea5  test    rcx, rcx
0x180016ea8  jz      short loc_180016EB0
0x180016eaa  call    cs:__imp_ReleaseSRWLockExclusive
0x180016eb0  call    ?Provider@AutoPilotTelemProvider@@SAPEBU_tlgProvider_t@@XZ; AutoPilotTelemProvider::Provider(void)
0x180016eb5  mov     r9, rax
0x180016eb8  mov     ecx, [rax]
0x180016eba  cmp     ecx, 5
0x180016ebd  jbe     loc_1800170C1
0x180016ec3  mov     rax, [rax+18h]
0x180016ec7  mov     rdx, 800000000000h
0x180016ed1  mov     rcx, [r9+10h]
0x180016ed5  test    rdx, rcx
0x180016ed8  jz      loc_1800170C1
0x180016ede  mov     rcx, rax
0x180016ee1  and     rcx, rdx
0x180016ee4  cmp     rcx, rax
0x180016ee7  jnz     loc_1800170C1
0x180016eed  mov     rax, [rdi+78h]
0x180016ef1  lea     rdx, word_18003A456
0x180016ef8  mov     r8, [rbx+110h]
0x180016eff  mov     rcx, r9
0x180016f02  mov     [rbp+57h+var_68], rax
0x180016f06  add     r8, 8
0x180016f0a  mov     rax, [rdi+70h]
0x180016f0e  mov     [rbp+57h+var_60], rax
0x180016f12  mov     eax, [rdi+68h]
0x180016f15  mov     dword ptr [rbp+57h+SRWLock], eax
0x180016f18  mov     rax, [rdi+60h]
0x180016f1c  mov     [rbp+57h+var_58], rax
0x180016f20  mov     rax, [rdi+58h]
0x180016f24  mov     [rbp+57h+var_50], rax
0x180016f28  mov     eax, [rdi+50h]
0x180016f2b  mov     [rbp+57h+arg_8], eax
0x180016f2e  mov     rax, [rdi+48h]
0x180016f32  mov     [rbp+57h+var_48], rax
0x180016f36  mov     eax, [rdi+20h]
0x180016f39  mov     dword ptr [rbp+57h+arg_10], eax
0x180016f3c  mov     rax, [rdi+18h]
0x180016f40  mov     [rbp+57h+var_40], rax
0x180016f44  mov     eax, [rdi]
0x180016f46  mov     [rbp+57h+arg_18], eax
0x180016f49  mov     rax, [rdi+80h]
0x180016f50  mov     [rbp+57h+var_38], rax
0x180016f54  mov     eax, [rdi+40h]
0x180016f57  mov     [rbp+57h+var_70], eax
0x180016f5a  mov     rax, [rdi+38h]
0x180016f5e  mov     [rbp+57h+var_30], rax
0x180016f62  mov     eax, [rdi+8]
0x180016f65  mov     [rbp+57h+var_6C], eax
0x180016f68  lea     rax, [rbp+57h+var_68]
0x180016f6c  mov     [rsp+110h+var_78], rax
0x180016f74  lea     rax, [rbp+57h+var_60]
0x180016f78  mov     [rsp+110h+var_80], rax
0x180016f80  lea     rax, [rbp+57h+SRWLock]
0x180016f84  mov     [rsp+110h+var_88], rax
0x180016f8c  lea     rax, [rbp+57h+var_58]
0x180016f90  mov     [rsp+110h+var_90], rax
0x180016f98  lea     rax, [rbp+57h+var_50]
0x180016f9c  mov     [rsp+110h+var_98], rax
0x180016fa1  lea     rax, [rbp+57h+arg_8]
0x180016fa5  mov     [rsp+110h+var_A0], rax
0x180016faa  lea     rax, [rbp+57h+var_48]
0x180016fae  mov     [rsp+110h+var_A8], rax
0x180016fb3  lea     rax, [rbp+57h+arg_10]
0x180016fb7  mov     [rsp+110h+var_B0], rax
0x180016fbc  lea     rax, [rbp+57h+var_40]
0x180016fc0  mov     [rsp+110h+var_B8], rax
0x180016fc5  lea     rax, [rbp+57h+arg_18]
0x180016fc9  mov     [rsp+110h+var_C0], rax
0x180016fce  lea     rax, [rbp+57h+var_38]
0x180016fd2  mov     [rsp+110h+var_C8], rax
0x180016fd7  lea     rax, [rbp+57h+var_70]
0x180016fdb  mov     [rsp+110h+var_D0], rax
0x180016fe0  lea     rax, [rbp+57h+var_30]
0x180016fe4  mov     [rsp+110h+var_D8], rax
0x180016fe9  lea     rax, [rbp+57h+var_6C]
0x180016fed  mov     [rsp+110h+var_E0], rax
0x180016ff2  lea     rax, [rbp+57h+var_28]
0x180016ff6  mov     [rsp+110h+var_E8], rax
0x180016ffb  lea     rax, [rbp+57h+var_20]
0x180016fff  mov     [rsp+110h+var_F0], rax
0x180017004  mov     [rbp+57h+var_28], 1000000h
0x18001700c  mov     [rbp+57h+var_20], 0
0x180017014  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180017019  jmp     loc_1800170C1
0x18001701e  lea     rdx, [rbp+57h+SRWLock]
0x180017022  call    ?LockExclusive@?$ActivityBase@VAutoPilotTelemProvider@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180017027  mov     rax, [rbx+110h]
0x18001702e  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x180017032  mov     dword ptr [rax], 2
0x180017038  test    rcx, rcx
0x18001703b  jz      short loc_180017043
0x18001703d  call    cs:__imp_ReleaseSRWLockExclusive
0x180017043  call    ?Provider@AutoPilotTelemProvider@@SAPEBU_tlgProvider_t@@XZ; AutoPilotTelemProvider::Provider(void)
0x180017048  mov     rdi, rax
0x18001704b  mov     ecx, [rax]
0x18001704d  cmp     ecx, 5
0x180017050  jbe     short loc_1800170C1
0x180017052  mov     rax, [rax+18h]
0x180017056  mov     rdx, 800000000000h
0x180017060  mov     rcx, [rdi+10h]
0x180017064  test    rdx, rcx
0x180017067  jz      short loc_1800170C1
0x180017069  mov     rcx, rax
0x18001706c  and     rcx, rdx
0x18001706f  cmp     rcx, rax
0x180017072  jnz     short loc_1800170C1
0x180017074  call    cs:__imp_GetCurrentThreadId
0x18001707a  mov     r8, [rbx+110h]
0x180017081  lea     rdx, unk_18003A2B0
0x180017088  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001708b  mov     rcx, rdi
0x18001708e  mov     eax, [r8+48h]
0x180017092  add     r8, 8
0x180017096  mov     [rbp+57h+arg_8], eax
0x180017099  lea     rax, [rbp+57h+SRWLock]
0x18001709d  mov     [rsp+110h+var_E0], rax
0x1800170a2  lea     rax, [rbp+57h+arg_8]
0x1800170a6  mov     [rsp+110h+var_E8], rax
0x1800170ab  lea     rax, [rbp+57h+arg_10]
0x1800170af  mov     [rsp+110h+var_F0], rax
0x1800170b4  mov     [rbp+57h+arg_10], 0
0x1800170bc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800170c1  mov     rcx, rbx
0x1800170c4  add     rsp, 100h
0x1800170cb  pop     rdi
0x1800170cc  pop     rbx
0x1800170cd  pop     rbp
0x1800170ce  jmp     ?IgnoreCurrentThread@?$ActivityBase@VAutoPilotTelemProvider@@$00$0IAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<AutoPilotTelemProvider,1,140737488355328,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
