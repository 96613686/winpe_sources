# StateRepository::Logging::Database::Checkpoint::StopActivity(void)

- ea: `0x1800fc380`
- end: `0x1800fc605`
- name: `?StopActivity@Checkpoint@Database@Logging@StateRepository@@MEAAXXZ`
- size: `645`
- prototype: `void __fastcall(StateRepository::Logging::Database::Checkpoint *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x1800018a4`
- `0x180001e6c`
- `0x1800f9cac`
- `0x1800f9e44`
- `0x1800fb134`
- `0x1800fc380`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800fc3da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800fc56e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800fc3da`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800fc56e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800fc5a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800fc5a6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall StateRepository::Logging::Database::Checkpoint::StopActivity(
        StateRepository::Logging::Database::Checkpoint *this)
{
  __int64 v2; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r9
  __int64 v7; // rax
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // [rsp+A0h] [rbp-19h] BYREF
  int v14; // [rsp+A4h] [rbp-15h] BYREF
  int *v15; // [rsp+A8h] [rbp-11h] BYREF
  const char *v16; // [rsp+B0h] [rbp-9h] BYREF
  int *v17; // [rsp+B8h] [rbp-1h] BYREF
  const char *v18; // [rsp+C0h] [rbp+7h] BYREF
  const char *v19; // [rsp+C8h] [rbp+Fh] BYREF
  int *v20; // [rsp+D0h] [rbp+17h] BYREF
  const char *v21; // [rsp+D8h] [rbp+1Fh] BYREF
  const char *v22; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v23; // [rsp+E8h] [rbp+2Fh] BYREF
  _QWORD v24[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  int v26; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v27; // [rsp+130h] [rbp+77h] BYREF
  int v28; // [rsp+138h] [rbp+7Fh] BYREF

  v2 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v2 + 72);
  if ( v3 < 0 && (v4 = (int *)(v2 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v5 = StateRepository::Tracing::Service::Provider();
    v6 = (__int64)v5;
    if ( *(_DWORD *)v5 > 5u )
    {
      v7 = *((_QWORD *)v5 + 3);
      if ( (*(_QWORD *)(v6 + 16) & 0x200000000000LL) != 0 && (v7 & 0x200000000000LL) == v7 )
      {
        v15 = (int *)*((_QWORD *)v4 + 15);
        v16 = (const char *)*((_QWORD *)v4 + 14);
        LODWORD(SRWLock) = v4[26];
        v17 = (int *)*((_QWORD *)v4 + 12);
        v18 = (const char *)*((_QWORD *)v4 + 11);
        v26 = v4[20];
        v19 = (const char *)*((_QWORD *)v4 + 9);
        LODWORD(v27) = v4[8];
        v20 = (int *)*((_QWORD *)v4 + 3);
        v28 = *v4;
        v21 = (const char *)*((_QWORD *)v4 + 16);
        v13 = v4[16];
        v22 = (const char *)*((_QWORD *)v4 + 7);
        v14 = v4[2];
        v23 = 0x1000000;
        v24[0] = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
          v6,
          (__int64)&word_180129EE6,
          *((_QWORD *)this + 34) + 8LL,
          v6,
          (__int64)v24,
          (__int64)&v23,
          (__int64)&v14,
          &v22,
          (__int64)&v13,
          &v21,
          (__int64)&v28,
          &v20,
          (__int64)&v27,
          &v19,
          (__int64)&v26,
          &v18,
          &v17,
          (__int64)&SRWLock,
          &v16,
          &v15);
      }
    }
  }
  else
  {
    wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    **((_DWORD **)this + 34) = 2;
    if ( SRWLock )
      ReleaseSRWLockExclusive(SRWLock);
    v8 = StateRepository::Tracing::Service::Provider();
    v9 = (__int64)v8;
    if ( *(_DWORD *)v8 > 5u )
    {
      v10 = *((_QWORD *)v8 + 3);
      if ( (*(_QWORD *)(v9 + 16) & 0x200000000000LL) != 0 && (v10 & 0x200000000000LL) == v10 )
      {
        LODWORD(SRWLock) = GetCurrentThreadId();
        v11 = *((_QWORD *)this + 34);
        v26 = *(_DWORD *)(v11 + 72);
        v27 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v9,
          (__int64)qword_18012A008,
          v11 + 8,
          v12,
          (__int64)&v27,
          (__int64)&v26,
          (__int64)&SRWLock);
      }
    }
  }
  wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x1800fc380  push    rbp
0x1800fc382  push    rbx
0x1800fc383  push    rdi
0x1800fc384  lea     rbp, [rsp-47h]
0x1800fc389  sub     rsp, 100h
0x1800fc390  mov     rbx, rcx
0x1800fc393  mov     rdi, [rcx+110h]
0x1800fc39a  mov     eax, [rdi+48h]
0x1800fc39d  test    eax, eax
0x1800fc39f  jns     loc_1800FC54F
0x1800fc3a5  add     rdi, 50h ; 'P'
0x1800fc3a9  cmp     eax, [rdi+8]
0x1800fc3ac  jnz     loc_1800FC54F
0x1800fc3b2  test    rdi, rdi
0x1800fc3b5  jz      loc_1800FC54F
0x1800fc3bb  lea     rdx, [rbp+57h+SRWLock]
0x1800fc3bf  call    ?LockExclusive@?$ActivityBase@VService@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800fc3c4  mov     rax, [rbx+110h]
0x1800fc3cb  mov     dword ptr [rax], 2
0x1800fc3d1  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800fc3d5  test    rcx, rcx
0x1800fc3d8  jz      short loc_1800FC3E1
0x1800fc3da  call    cs:__imp_ReleaseSRWLockExclusive
0x1800fc3e0  nop
0x1800fc3e1  call    ?Provider@Service@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Service::Provider(void)
0x1800fc3e6  mov     r9, rax
0x1800fc3e9  mov     ecx, [rax]
0x1800fc3eb  cmp     ecx, 5
0x1800fc3ee  jbe     loc_1800FC5F3
0x1800fc3f4  mov     rax, [rax+18h]
0x1800fc3f8  mov     rcx, [r9+10h]
0x1800fc3fc  mov     rdx, 200000000000h
0x1800fc406  test    rdx, rcx
0x1800fc409  jz      loc_1800FC5F3
0x1800fc40f  mov     rcx, rax
0x1800fc412  and     rcx, rdx
0x1800fc415  cmp     rcx, rax
0x1800fc418  jnz     loc_1800FC5F3
0x1800fc41e  mov     rax, [rdi+78h]
0x1800fc422  mov     [rbp+57h+var_68], rax
0x1800fc426  mov     rax, [rdi+70h]
0x1800fc42a  mov     [rbp+57h+var_60], rax
0x1800fc42e  mov     eax, [rdi+68h]
0x1800fc431  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800fc434  mov     rax, [rdi+60h]
0x1800fc438  mov     [rbp+57h+var_58], rax
0x1800fc43c  mov     rax, [rdi+58h]
0x1800fc440  mov     [rbp+57h+var_50], rax
0x1800fc444  mov     eax, [rdi+50h]
0x1800fc447  mov     [rbp+57h+arg_8], eax
0x1800fc44a  mov     rax, [rdi+48h]
0x1800fc44e  mov     [rbp+57h+var_48], rax
0x1800fc452  mov     eax, [rdi+20h]
0x1800fc455  mov     dword ptr [rbp+57h+arg_10], eax
0x1800fc458  mov     rax, [rdi+18h]
0x1800fc45c  mov     [rbp+57h+var_40], rax
0x1800fc460  mov     eax, [rdi]
0x1800fc462  mov     [rbp+57h+arg_18], eax
0x1800fc465  mov     rax, [rdi+80h]
0x1800fc46c  mov     [rbp+57h+var_38], rax
0x1800fc470  mov     eax, [rdi+40h]
0x1800fc473  mov     [rbp+57h+var_70], eax
0x1800fc476  mov     rax, [rdi+38h]
0x1800fc47a  mov     [rbp+57h+var_30], rax
0x1800fc47e  mov     eax, [rdi+8]
0x1800fc481  mov     [rbp+57h+var_6C], eax
0x1800fc484  mov     [rbp+57h+var_28], 1000000h
0x1800fc48c  mov     [rbp+57h+var_20], 0
0x1800fc494  mov     r8, [rbx+110h]
0x1800fc49b  add     r8, 8
0x1800fc49f  lea     rax, [rbp+57h+var_68]
0x1800fc4a3  mov     [rsp+110h+var_78], rax
0x1800fc4ab  lea     rax, [rbp+57h+var_60]
0x1800fc4af  mov     [rsp+110h+var_80], rax
0x1800fc4b7  lea     rax, [rbp+57h+SRWLock]
0x1800fc4bb  mov     [rsp+110h+var_88], rax
0x1800fc4c3  lea     rax, [rbp+57h+var_58]
0x1800fc4c7  mov     [rsp+110h+var_90], rax
0x1800fc4cf  lea     rax, [rbp+57h+var_50]
0x1800fc4d3  mov     [rsp+110h+var_98], rax
0x1800fc4d8  lea     rax, [rbp+57h+arg_8]
0x1800fc4dc  mov     [rsp+110h+var_A0], rax
0x1800fc4e1  lea     rax, [rbp+57h+var_48]
0x1800fc4e5  mov     [rsp+110h+var_A8], rax
0x1800fc4ea  lea     rax, [rbp+57h+arg_10]
0x1800fc4ee  mov     [rsp+110h+var_B0], rax
0x1800fc4f3  lea     rax, [rbp+57h+var_40]
0x1800fc4f7  mov     [rsp+110h+var_B8], rax
0x1800fc4fc  lea     rax, [rbp+57h+arg_18]
0x1800fc500  mov     [rsp+110h+var_C0], rax
0x1800fc505  lea     rax, [rbp+57h+var_38]
0x1800fc509  mov     [rsp+110h+var_C8], rax
0x1800fc50e  lea     rax, [rbp+57h+var_70]
0x1800fc512  mov     [rsp+110h+var_D0], rax
0x1800fc517  lea     rax, [rbp+57h+var_30]
0x1800fc51b  mov     [rsp+110h+var_D8], rax
0x1800fc520  lea     rax, [rbp+57h+var_6C]
0x1800fc524  mov     [rsp+110h+var_E0], rax
0x1800fc529  lea     rax, [rbp+57h+var_28]
0x1800fc52d  mov     [rsp+110h+var_E8], rax
0x1800fc532  lea     rax, [rbp+57h+var_20]
0x1800fc536  mov     [rsp+110h+var_F0], rax
0x1800fc53b  lea     rdx, word_180129EE6
0x1800fc542  mov     rcx, r9
0x1800fc545  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x1800fc54a  jmp     loc_1800FC5F3
0x1800fc54f  lea     rdx, [rbp+57h+SRWLock]
0x1800fc553  call    ?LockExclusive@?$ActivityBase@VService@Tracing@StateRepository@@$00$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<StateRepository::Tracing::Service,1,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800fc558  mov     rax, [rbx+110h]
0x1800fc55f  mov     dword ptr [rax], 2
0x1800fc565  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800fc569  test    rcx, rcx
0x1800fc56c  jz      short loc_1800FC575
0x1800fc56e  call    cs:__imp_ReleaseSRWLockExclusive
0x1800fc574  nop
0x1800fc575  call    ?Provider@Service@Tracing@StateRepository@@SAPEBU_tlgProvider_t@@XZ; StateRepository::Tracing::Service::Provider(void)
0x1800fc57a  mov     rdi, rax
0x1800fc57d  mov     ecx, [rax]
0x1800fc57f  cmp     ecx, 5
0x1800fc582  jbe     short loc_1800FC5F3
0x1800fc584  mov     rax, [rax+18h]
0x1800fc588  mov     rcx, [rdi+10h]
0x1800fc58c  mov     rdx, 200000000000h
0x1800fc596  test    rdx, rcx
0x1800fc599  jz      short loc_1800FC5F3
0x1800fc59b  mov     rcx, rax
0x1800fc59e  and     rcx, rdx
0x1800fc5a1  cmp     rcx, rax
0x1800fc5a4  jnz     short loc_1800FC5F3
0x1800fc5a6  call    cs:__imp_GetCurrentThreadId
0x1800fc5ac  mov     dword ptr [rbp+57h+SRWLock], eax
0x1800fc5af  mov     r8, [rbx+110h]
0x1800fc5b6  mov     eax, [r8+48h]
0x1800fc5ba  mov     [rbp+57h+arg_8], eax
0x1800fc5bd  mov     [rbp+57h+arg_10], 0
0x1800fc5c5  add     r8, 8
0x1800fc5c9  lea     rax, [rbp+57h+SRWLock]
0x1800fc5cd  mov     [rsp+110h+var_E0], rax
0x1800fc5d2  lea     rax, [rbp+57h+arg_8]
0x1800fc5d6  mov     [rsp+110h+var_E8], rax
0x1800fc5db  lea     rax, [rbp+57h+arg_10]
0x1800fc5df  mov     [rsp+110h+var_F0], rax
0x1800fc5e4  lea     rdx, qword_18012A008
0x1800fc5eb  mov     rcx, rdi
0x1800fc5ee  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800fc5f3  mov     rcx, rbx
0x1800fc5f6  add     rsp, 100h
0x1800fc5fd  pop     rdi
0x1800fc5fe  pop     rbx
0x1800fc5ff  pop     rbp
0x1800fc600  jmp     ?IgnoreCurrentThread@?$ActivityBase@VService@Tracing@StateRepository@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<StateRepository::Tracing::Service,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
