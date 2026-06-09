# Windows::Telemetry::Art::RebootDowntimeInputBuildActivity::StopActivity(void)

- ea: `0x1800c6000`
- end: `0x1800c6293`
- name: `?StopActivity@RebootDowntimeInputBuildActivity@Art@Telemetry@Windows@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(Windows::Telemetry::Art::RebootDowntimeInputBuildActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task`

## callees

- `0x18000109c`
- `0x180001f10`
- `0x180085644`
- `0x18008c454`
- `0x1800b781c`
- `0x1800c6000`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c606e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c61fa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c606e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800c61fa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c622a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c622a`

## pseudocode

```c
void __fastcall Windows::Telemetry::Art::RebootDowntimeInputBuildActivity::StopActivity(
        Windows::Telemetry::Art::RebootDowntimeInputBuildActivity *this)
{
  _DWORD **v1; // rdi
  __int64 v3; // rbx
  int v4; // eax
  __int64 v5; // rbx
  _DWORD **v6; // r14
  RTL_SRWLOCK *v7; // rcx
  const struct _tlgProvider_t *v8; // rax
  _DWORD *v9; // r8
  RTL_SRWLOCK *v10; // rcx
  const struct _tlgProvider_t *v11; // rax
  int v12; // ebx
  DWORD CurrentThreadId; // eax
  _DWORD *v14; // r8
  int v15; // r9d
  PSRWLOCK SRWLock; // [rsp+A0h] [rbp-80h] BYREF
  int v17; // [rsp+A8h] [rbp-78h] BYREF
  int v18; // [rsp+ACh] [rbp-74h] BYREF
  int v19; // [rsp+B0h] [rbp-70h] BYREF
  int v20; // [rsp+B4h] [rbp-6Ch] BYREF
  __int64 v21; // [rsp+B8h] [rbp-68h] BYREF
  __int64 v22; // [rsp+C0h] [rbp-60h] BYREF
  __int64 v23; // [rsp+C8h] [rbp-58h] BYREF
  __int64 v24; // [rsp+D0h] [rbp-50h] BYREF
  __int64 v25; // [rsp+D8h] [rbp-48h] BYREF
  __int64 v26; // [rsp+E0h] [rbp-40h] BYREF
  __int64 v27; // [rsp+E8h] [rbp-38h] BYREF
  __int64 v28; // [rsp+F0h] [rbp-30h] BYREF
  __int64 v29; // [rsp+F8h] [rbp-28h] BYREF
  __int64 v30; // [rsp+100h] [rbp-20h] BYREF
  __int64 v31; // [rsp+108h] [rbp-18h] BYREF

  v1 = (_DWORD **)((char *)this + 272);
  v3 = *((_QWORD *)this + 34);
  v4 = *(_DWORD *)(v3 + 72);
  if ( v4 < 0 && (v5 = v3 + 80, v4 == *(_DWORD *)(v5 + 8)) )
  {
    v6 = (_DWORD **)((char *)this + 272);
    if ( v5 )
    {
      SRWLock = 0;
      wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
        this,
        &SRWLock);
      v7 = SRWLock;
      **v1 = 2;
      if ( v7 )
        ReleaseSRWLockExclusive(v7);
      v8 = Windows::Telemetry::Base::Provider();
      if ( *(_DWORD *)v8 > 5u
        && (*((_QWORD *)v8 + 2) & 0x400000000000LL) != 0
        && (*((_QWORD *)v8 + 3) & 0x400000000000LL) == *((_QWORD *)v8 + 3) )
      {
        v9 = *v1;
        v23 = *(_QWORD *)(v5 + 120);
        v24 = *(_QWORD *)(v5 + 112);
        v18 = *(_DWORD *)(v5 + 104);
        v25 = *(_QWORD *)(v5 + 96);
        v26 = *(_QWORD *)(v5 + 88);
        v19 = *(_DWORD *)(v5 + 80);
        v27 = *(_QWORD *)(v5 + 72);
        v20 = *(_DWORD *)(v5 + 32);
        v28 = *(_QWORD *)(v5 + 24);
        LODWORD(v21) = *(_DWORD *)v5;
        v29 = *(_QWORD *)(v5 + 128);
        v17 = *(_DWORD *)(v5 + 64);
        v30 = *(_QWORD *)(v5 + 56);
        LODWORD(SRWLock) = *(_DWORD *)(v5 + 8);
        v31 = 0x1000000;
        v22 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(
          (int)v8,
          (int)&word_180132DF2,
          (_DWORD)v9 + 8,
          (__int64)&v22,
          (__int64)&v31,
          (__int64)&SRWLock,
          (__int64)&v30,
          (__int64)&v17,
          (__int64)&v29,
          (__int64)&v21,
          (__int64)&v28,
          (__int64)&v20,
          (__int64)&v27,
          (__int64)&v19,
          (__int64)&v26,
          (__int64)&v25,
          (__int64)&v18,
          (__int64)&v24,
          (__int64)&v23);
      }
      goto LABEL_17;
    }
  }
  else
  {
    v6 = (_DWORD **)((char *)this + 272);
  }
  SRWLock = 0;
  wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    this,
    &SRWLock);
  v10 = SRWLock;
  **v6 = 2;
  if ( v10 )
    ReleaseSRWLockExclusive(v10);
  v11 = Windows::Telemetry::Base::Provider();
  v12 = (int)v11;
  if ( *(_DWORD *)v11 > 5u
    && (*((_QWORD *)v11 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v11 + 3) & 0x400000000000LL) == *((_QWORD *)v11 + 3) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v14 = *v1;
    LODWORD(SRWLock) = CurrentThreadId;
    v17 = v14[18];
    v22 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v12,
      (unsigned int)byte_180132D91,
      (_DWORD)v14 + 8,
      v15,
      (__int64)&v22,
      (__int64)&v17,
      (__int64)&SRWLock);
  }
LABEL_17:
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x1800c6000  mov     [rsp-8+arg_8], rbx
0x1800c6005  mov     [rsp-8+arg_10], rsi
0x1800c600a  push    rbp
0x1800c600b  push    rdi
0x1800c600c  push    r14
0x1800c600e  lea     rbp, [rsp+10h]
0x1800c6013  sub     rsp, 110h
0x1800c601a  lea     rdi, [rcx+110h]
0x1800c6021  mov     rsi, rcx
0x1800c6024  mov     rbx, [rdi]
0x1800c6027  mov     eax, [rbx+48h]
0x1800c602a  test    eax, eax
0x1800c602c  jns     loc_1800C61D4
0x1800c6032  add     rbx, 50h ; 'P'
0x1800c6036  cmp     eax, [rbx+8]
0x1800c6039  jnz     loc_1800C61D4
0x1800c603f  mov     r14, rdi
0x1800c6042  test    rbx, rbx
0x1800c6045  jz      loc_1800C61D7
0x1800c604b  lea     rdx, [rbp+SRWLock]
0x1800c604f  mov     [rbp+SRWLock], 0
0x1800c6057  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800c605c  mov     rax, [rdi]
0x1800c605f  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800c6063  mov     dword ptr [rax], 2
0x1800c6069  test    rcx, rcx
0x1800c606c  jz      short loc_1800C6074
0x1800c606e  call    cs:__imp_ReleaseSRWLockExclusive
0x1800c6074  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x1800c6079  mov     r9, rax
0x1800c607c  cmp     dword ptr [rax], 5
0x1800c607f  jbe     loc_1800C6274
0x1800c6085  mov     rdx, 400000000000h
0x1800c608f  test    [rax+10h], rdx
0x1800c6093  jz      loc_1800C6274
0x1800c6099  mov     rcx, [rax+18h]
0x1800c609d  and     rcx, rdx
0x1800c60a0  cmp     rcx, [rax+18h]
0x1800c60a4  jnz     loc_1800C6274
0x1800c60aa  mov     rax, [rbx+78h]
0x1800c60ae  lea     rdx, word_180132DF2; int
0x1800c60b5  mov     r8, [rdi]
0x1800c60b8  mov     rcx, r9; int
0x1800c60bb  mov     [rbp+var_58], rax
0x1800c60bf  add     r8, 8; int
0x1800c60c3  mov     rax, [rbx+70h]
0x1800c60c7  mov     [rbp+var_50], rax
0x1800c60cb  mov     eax, [rbx+68h]
0x1800c60ce  mov     dword ptr [rbp+var_78+4], eax
0x1800c60d1  mov     rax, [rbx+60h]
0x1800c60d5  mov     [rbp+var_48], rax
0x1800c60d9  mov     rax, [rbx+58h]
0x1800c60dd  mov     [rbp+var_40], rax
0x1800c60e1  mov     eax, [rbx+50h]
0x1800c60e4  mov     dword ptr [rbp+var_70], eax
0x1800c60e7  mov     rax, [rbx+48h]
0x1800c60eb  mov     [rbp+var_38], rax
0x1800c60ef  mov     eax, [rbx+20h]
0x1800c60f2  mov     dword ptr [rbp+var_70+4], eax
0x1800c60f5  mov     rax, [rbx+18h]
0x1800c60f9  mov     [rbp+var_30], rax
0x1800c60fd  mov     eax, [rbx]
0x1800c60ff  mov     dword ptr [rbp+var_68], eax
0x1800c6102  mov     rax, [rbx+80h]
0x1800c6109  mov     [rbp+var_28], rax
0x1800c610d  mov     eax, [rbx+40h]
0x1800c6110  mov     dword ptr [rbp+var_78], eax
0x1800c6113  mov     rax, [rbx+38h]
0x1800c6117  mov     [rbp+var_20], rax
0x1800c611b  mov     eax, [rbx+8]
0x1800c611e  mov     dword ptr [rbp+SRWLock], eax
0x1800c6121  mov     eax, 1000000h
0x1800c6126  mov     [rbp+var_18], rax
0x1800c612a  mov     [rbp+var_60], rax
0x1800c612e  lea     rax, [rbp+var_58]
0x1800c6132  mov     [rsp+120h+var_88], rax; __int64
0x1800c613a  lea     rax, [rbp+var_50]
0x1800c613e  mov     [rsp+120h+var_90], rax; __int64
0x1800c6146  lea     rax, [rbp+var_78+4]
0x1800c614a  mov     [rsp+120h+var_98], rax; __int64
0x1800c6152  lea     rax, [rbp+var_48]
0x1800c6156  mov     [rsp+120h+var_A0], rax; __int64
0x1800c615e  lea     rax, [rbp+var_40]
0x1800c6162  mov     [rsp+120h+var_A8], rax; __int64
0x1800c6167  lea     rax, [rbp+var_70]
0x1800c616b  mov     [rsp+120h+var_B0], rax; __int64
0x1800c6170  lea     rax, [rbp+var_38]
0x1800c6174  mov     [rsp+120h+var_B8], rax; __int64
0x1800c6179  lea     rax, [rbp+var_70+4]
0x1800c617d  mov     [rsp+120h+var_C0], rax; __int64
0x1800c6182  lea     rax, [rbp+var_30]
0x1800c6186  mov     [rsp+120h+var_C8], rax; __int64
0x1800c618b  lea     rax, [rbp+var_68]
0x1800c618f  mov     [rsp+120h+var_D0], rax; __int64
0x1800c6194  lea     rax, [rbp+var_28]
0x1800c6198  mov     [rsp+120h+var_D8], rax; __int64
0x1800c619d  lea     rax, [rbp+var_78]
0x1800c61a1  mov     [rsp+120h+var_E0], rax; __int64
0x1800c61a6  lea     rax, [rbp+var_20]
0x1800c61aa  mov     [rsp+120h+var_E8], rax; __int64
0x1800c61af  lea     rax, [rbp+SRWLock]
0x1800c61b3  mov     [rsp+120h+var_F0], rax; __int64
0x1800c61b8  lea     rax, [rbp+var_18]
0x1800c61bc  mov     [rsp+120h+var_F8], rax; __int64
0x1800c61c1  lea     rax, [rbp+var_60]
0x1800c61c5  mov     [rsp+120h+var_100], rax; __int64
0x1800c61ca  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x1800c61cf  jmp     loc_1800C6274
0x1800c61d4  mov     r14, rdi
0x1800c61d7  lea     rdx, [rbp+SRWLock]
0x1800c61db  mov     [rbp+SRWLock], 0
0x1800c61e3  call    ?LockExclusive@?$ActivityBase@VServiceBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::ServiceBase,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800c61e8  mov     rax, [r14]
0x1800c61eb  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800c61ef  mov     dword ptr [rax], 2
0x1800c61f5  test    rcx, rcx
0x1800c61f8  jz      short loc_1800C6200
0x1800c61fa  call    cs:__imp_ReleaseSRWLockExclusive
0x1800c6200  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x1800c6205  mov     rbx, rax
0x1800c6208  cmp     dword ptr [rax], 5
0x1800c620b  jbe     short loc_1800C6274
0x1800c620d  mov     rdx, 400000000000h
0x1800c6217  test    [rax+10h], rdx
0x1800c621b  jz      short loc_1800C6274
0x1800c621d  mov     rcx, [rax+18h]
0x1800c6221  and     rcx, rdx
0x1800c6224  cmp     rcx, [rax+18h]
0x1800c6228  jnz     short loc_1800C6274
0x1800c622a  call    cs:__imp_GetCurrentThreadId
0x1800c6230  mov     r8, [rdi]
0x1800c6233  lea     rdx, byte_180132D91
0x1800c623a  mov     dword ptr [rbp+SRWLock], eax
0x1800c623d  mov     rcx, rbx
0x1800c6240  mov     eax, [r8+48h]
0x1800c6244  add     r8, 8
0x1800c6248  mov     dword ptr [rbp+var_78], eax
0x1800c624b  mov     eax, 1000000h
0x1800c6250  mov     [rbp+var_60], rax
0x1800c6254  lea     rax, [rbp+SRWLock]
0x1800c6258  mov     [rsp+120h+var_F0], rax
0x1800c625d  lea     rax, [rbp+var_78]
0x1800c6261  mov     [rsp+120h+var_F8], rax
0x1800c6266  lea     rax, [rbp+var_60]
0x1800c626a  mov     [rsp+120h+var_100], rax
0x1800c626f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800c6274  mov     rcx, rsi
0x1800c6277  lea     r11, [rsp+120h+var_10]
0x1800c627f  mov     rbx, [r11+28h]
0x1800c6283  mov     rsi, [r11+30h]
0x1800c6287  mov     rsp, r11
0x1800c628a  pop     r14
0x1800c628c  pop     rdi
0x1800c628d  pop     rbp
0x1800c628e  jmp     ?IgnoreCurrentThread@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
