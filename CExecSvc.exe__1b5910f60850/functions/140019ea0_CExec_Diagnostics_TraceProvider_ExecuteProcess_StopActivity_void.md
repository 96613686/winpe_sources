# CExec::Diagnostics::TraceProvider::ExecuteProcess::StopActivity(void)

- ea: `0x140019ea0`
- end: `0x14001a166`
- name: `?StopActivity@ExecuteProcess@TraceProvider@Diagnostics@CExec@@MEAAXXZ`
- size: `710`
- prototype: `void __fastcall(CExec::Diagnostics::TraceProvider::ExecuteProcess *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400013f0`
- `0x140001704`
- `0x14001837c`
- `0x1400186e0`
- `0x140019190`
- `0x140019ea0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140019f07`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001a0d0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140019f07`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001a0d0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001a0fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001a0fd`

## pseudocode

```c
void __fastcall CExec::Diagnostics::TraceProvider::ExecuteProcess::StopActivity(
        CExec::Diagnostics::TraceProvider::ExecuteProcess *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r9
  __int64 v8; // rax
  __int64 v9; // r8
  RTL_SRWLOCK *v10; // rcx
  const struct _tlgProvider_t *v11; // rax
  const struct _tlgProvider_t *v12; // rdi
  __int64 v13; // rax
  DWORD CurrentThreadId; // eax
  __int64 v15; // r8
  __int64 v16; // r9
  PSRWLOCK SRWLock; // [rsp+C0h] [rbp-80h] BYREF
  int v18; // [rsp+C8h] [rbp-78h] BYREF
  int v19; // [rsp+CCh] [rbp-74h] BYREF
  int v20; // [rsp+D0h] [rbp-70h] BYREF
  int v21; // [rsp+D4h] [rbp-6Ch] BYREF
  int v22; // [rsp+D8h] [rbp-68h] BYREF
  int v23; // [rsp+DCh] [rbp-64h] BYREF
  int v24; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v25; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v26; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v27; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v28; // [rsp+100h] [rbp-40h] BYREF
  __int64 v29; // [rsp+108h] [rbp-38h] BYREF
  __int64 v30; // [rsp+110h] [rbp-30h] BYREF
  __int64 v31; // [rsp+118h] [rbp-28h] BYREF
  __int64 v32; // [rsp+120h] [rbp-20h] BYREF
  __int64 v33; // [rsp+128h] [rbp-18h] BYREF
  __int64 v34; // [rsp+130h] [rbp-10h] BYREF
  __int64 v35; // [rsp+138h] [rbp-8h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    SRWLock = 0;
    wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = CExec::Diagnostics::TraceProvider::Provider();
    v7 = (__int64)v6;
    if ( *(_DWORD *)v6 > 4u )
    {
      v8 = *((_QWORD *)v6 + 3);
      if ( (*(_QWORD *)(v7 + 16) & 2) != 0 && (v8 & 2) == v8 )
      {
        v26 = *((_QWORD *)v4 + 6);
        v19 = v4[17];
        v20 = v4[4];
        v27 = *((_QWORD *)v4 + 15);
        v28 = *((_QWORD *)v4 + 14);
        v9 = *((_QWORD *)this + 34);
        v21 = v4[26];
        v29 = *((_QWORD *)v4 + 12);
        v30 = *((_QWORD *)v4 + 11);
        v22 = v4[20];
        v31 = *((_QWORD *)v4 + 9);
        v23 = v4[8];
        v32 = *((_QWORD *)v4 + 3);
        v24 = *v4;
        v33 = *((_QWORD *)v4 + 16);
        v18 = v4[16];
        v34 = *((_QWORD *)v4 + 7);
        LODWORD(SRWLock) = v4[2];
        v35 = 0x1000000;
        v25 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v7,
          (int)&word_14002A6BE,
          v9 + 8,
          v7,
          (__int64)&v25,
          (__int64)&v35,
          (__int64)&SRWLock,
          (const unsigned __int16 **)&v34,
          (__int64)&v18,
          (const unsigned __int16 **)&v33,
          (__int64)&v24,
          (const WCHAR **)&v32,
          (__int64)&v23,
          (const unsigned __int16 **)&v31,
          (__int64)&v22,
          (const unsigned __int16 **)&v30,
          (const WCHAR **)&v29,
          (__int64)&v21,
          (const unsigned __int16 **)&v28,
          (const WCHAR **)&v27,
          (__int64)&v20,
          (__int64)&v19,
          (const unsigned __int16 **)&v26);
      }
    }
  }
  else
  {
    SRWLock = 0;
    wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v10 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v10 )
      ReleaseSRWLockExclusive(v10);
    v11 = CExec::Diagnostics::TraceProvider::Provider();
    v12 = v11;
    if ( *(_DWORD *)v11 > 4u )
    {
      v13 = *((_QWORD *)v11 + 3);
      if ( (*((_QWORD *)v12 + 2) & 2) != 0 && (v13 & 2) == v13 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v15 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v18 = *(_DWORD *)(v15 + 72);
        v25 = 0;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          (int)v12,
          (int)qword_14002A860,
          v15 + 8,
          v16,
          (__int64)&v25,
          (__int64)&v18,
          (__int64)&SRWLock);
      }
    }
  }
  wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x140019ea0  mov     [rsp-8+arg_8], rbx
0x140019ea5  mov     [rsp-8+arg_10], rdi
0x140019eaa  push    rbp
0x140019eab  mov     rbp, rsp
0x140019eae  sub     rsp, 140h
0x140019eb5  mov     rdi, [rcx+110h]
0x140019ebc  mov     rbx, rcx
0x140019ebf  mov     eax, [rdi+48h]
0x140019ec2  test    eax, eax
0x140019ec4  jns     loc_14001A0A9
0x140019eca  add     rdi, 50h ; 'P'
0x140019ece  cmp     eax, [rdi+8]
0x140019ed1  jnz     loc_14001A0A9
0x140019ed7  test    rdi, rdi
0x140019eda  jz      loc_14001A0A9
0x140019ee0  lea     rdx, [rbp+SRWLock]
0x140019ee4  mov     [rbp+SRWLock], 0
0x140019eec  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140019ef1  mov     rax, [rbx+110h]
0x140019ef8  mov     rcx, [rbp+SRWLock]; SRWLock
0x140019efc  mov     dword ptr [rax], 2
0x140019f02  test    rcx, rcx
0x140019f05  jz      short loc_140019F0D
0x140019f07  call    cs:__imp_ReleaseSRWLockExclusive
0x140019f0d  call    ?Provider@TraceProvider@Diagnostics@CExec@@SAPEBU_tlgProvider_t@@XZ; CExec::Diagnostics::TraceProvider::Provider(void)
0x140019f12  mov     r9, rax
0x140019f15  mov     ecx, [rax]
0x140019f17  cmp     ecx, 4
0x140019f1a  jbe     loc_14001A14A
0x140019f20  mov     rax, [rax+18h]
0x140019f24  mov     rcx, [r9+10h]
0x140019f28  test    cl, 2
0x140019f2b  jz      loc_14001A14A
0x140019f31  mov     rcx, rax
0x140019f34  and     ecx, 2
0x140019f37  cmp     rcx, rax
0x140019f3a  jnz     loc_14001A14A
0x140019f40  mov     rax, [rdi+30h]
0x140019f44  lea     rdx, word_14002A6BE; int
0x140019f4b  mov     [rbp+var_50], rax
0x140019f4f  mov     rcx, r9; int
0x140019f52  mov     eax, [rdi+44h]
0x140019f55  mov     dword ptr [rbp+var_78+4], eax
0x140019f58  mov     eax, [rdi+10h]
0x140019f5b  mov     dword ptr [rbp+var_70], eax
0x140019f5e  mov     rax, [rdi+78h]
0x140019f62  mov     [rbp+var_48], rax
0x140019f66  mov     rax, [rdi+70h]
0x140019f6a  mov     [rbp+var_40], rax
0x140019f6e  mov     eax, [rdi+68h]
0x140019f71  mov     r8, [rbx+110h]
0x140019f78  mov     dword ptr [rbp+var_70+4], eax
0x140019f7b  add     r8, 8; int
0x140019f7f  mov     rax, [rdi+60h]
0x140019f83  mov     [rbp+var_38], rax
0x140019f87  mov     rax, [rdi+58h]
0x140019f8b  mov     [rbp+var_30], rax
0x140019f8f  mov     eax, [rdi+50h]
0x140019f92  mov     dword ptr [rbp+var_68], eax
0x140019f95  mov     rax, [rdi+48h]
0x140019f99  mov     [rbp+var_28], rax
0x140019f9d  mov     eax, [rdi+20h]
0x140019fa0  mov     dword ptr [rbp+var_68+4], eax
0x140019fa3  mov     rax, [rdi+18h]
0x140019fa7  mov     [rbp+var_20], rax
0x140019fab  mov     eax, [rdi]
0x140019fad  mov     [rbp+var_60], eax
0x140019fb0  mov     rax, [rdi+80h]
0x140019fb7  mov     [rbp+var_18], rax
0x140019fbb  mov     eax, [rdi+40h]
0x140019fbe  mov     dword ptr [rbp+var_78], eax
0x140019fc1  mov     rax, [rdi+38h]
0x140019fc5  mov     [rbp+var_10], rax
0x140019fc9  mov     eax, [rdi+8]
0x140019fcc  mov     dword ptr [rbp+SRWLock], eax
0x140019fcf  lea     rax, [rbp+var_50]
0x140019fd3  mov     [rsp+140h+var_90], rax; __int64
0x140019fdb  lea     rax, [rbp+var_78+4]
0x140019fdf  mov     [rsp+140h+var_98], rax; __int64
0x140019fe7  lea     rax, [rbp+var_70]
0x140019feb  mov     [rsp+140h+var_A0], rax; __int64
0x140019ff3  lea     rax, [rbp+var_48]
0x140019ff7  mov     [rsp+140h+var_A8], rax; __int64
0x140019fff  lea     rax, [rbp+var_40]
0x14001a003  mov     [rsp+140h+var_B0], rax; __int64
0x14001a00b  lea     rax, [rbp+var_70+4]
0x14001a00f  mov     [rsp+140h+var_B8], rax; __int64
0x14001a017  lea     rax, [rbp+var_38]
0x14001a01b  mov     [rsp+140h+var_C0], rax; __int64
0x14001a023  lea     rax, [rbp+var_30]
0x14001a027  mov     [rsp+140h+var_C8], rax; __int64
0x14001a02c  lea     rax, [rbp+var_68]
0x14001a030  mov     [rsp+140h+var_D0], rax; __int64
0x14001a035  lea     rax, [rbp+var_28]
0x14001a039  mov     [rsp+140h+var_D8], rax; __int64
0x14001a03e  lea     rax, [rbp+var_68+4]
0x14001a042  mov     [rsp+140h+var_E0], rax; __int64
0x14001a047  lea     rax, [rbp+var_20]
0x14001a04b  mov     [rsp+140h+var_E8], rax; __int64
0x14001a050  lea     rax, [rbp+var_60]
0x14001a054  mov     [rsp+140h+var_F0], rax; __int64
0x14001a059  lea     rax, [rbp+var_18]
0x14001a05d  mov     [rsp+140h+var_F8], rax; __int64
0x14001a062  lea     rax, [rbp+var_78]
0x14001a066  mov     [rsp+140h+var_100], rax; __int64
0x14001a06b  lea     rax, [rbp+var_10]
0x14001a06f  mov     [rsp+140h+var_108], rax; __int64
0x14001a074  lea     rax, [rbp+SRWLock]
0x14001a078  mov     [rsp+140h+var_110], rax; __int64
0x14001a07d  lea     rax, [rbp+var_8]
0x14001a081  mov     [rsp+140h+var_118], rax; __int64
0x14001a086  lea     rax, [rbp+var_58]
0x14001a08a  mov     [rsp+140h+var_120], rax; __int64
0x14001a08f  mov     [rbp+var_8], 1000000h
0x14001a097  mov     [rbp+var_58], 0
0x14001a09f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14001a0a4  jmp     loc_14001A14A
0x14001a0a9  lea     rdx, [rbp+SRWLock]
0x14001a0ad  mov     [rbp+SRWLock], 0
0x14001a0b5  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14001a0ba  mov     rax, [rbx+110h]
0x14001a0c1  mov     rcx, [rbp+SRWLock]; SRWLock
0x14001a0c5  mov     dword ptr [rax], 2
0x14001a0cb  test    rcx, rcx
0x14001a0ce  jz      short loc_14001A0D6
0x14001a0d0  call    cs:__imp_ReleaseSRWLockExclusive
0x14001a0d6  call    ?Provider@TraceProvider@Diagnostics@CExec@@SAPEBU_tlgProvider_t@@XZ; CExec::Diagnostics::TraceProvider::Provider(void)
0x14001a0db  mov     rdi, rax
0x14001a0de  mov     ecx, [rax]
0x14001a0e0  cmp     ecx, 4
0x14001a0e3  jbe     short loc_14001A14A
0x14001a0e5  mov     rax, [rax+18h]
0x14001a0e9  mov     rcx, [rdi+10h]
0x14001a0ed  test    cl, 2
0x14001a0f0  jz      short loc_14001A14A
0x14001a0f2  mov     rcx, rax
0x14001a0f5  and     ecx, 2
0x14001a0f8  cmp     rcx, rax
0x14001a0fb  jnz     short loc_14001A14A
0x14001a0fd  call    cs:__imp_GetCurrentThreadId
0x14001a103  mov     r8, [rbx+110h]
0x14001a10a  lea     rdx, qword_14002A860
0x14001a111  mov     dword ptr [rbp+SRWLock], eax
0x14001a114  mov     rcx, rdi
0x14001a117  mov     eax, [r8+48h]
0x14001a11b  add     r8, 8
0x14001a11f  mov     dword ptr [rbp+var_78], eax
0x14001a122  lea     rax, [rbp+SRWLock]
0x14001a126  mov     [rsp+140h+var_110], rax
0x14001a12b  lea     rax, [rbp+var_78]
0x14001a12f  mov     [rsp+140h+var_118], rax
0x14001a134  lea     rax, [rbp+var_58]
0x14001a138  mov     [rsp+140h+var_120], rax
0x14001a13d  mov     [rbp+var_58], 0
0x14001a145  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14001a14a  mov     rcx, rbx
0x14001a14d  lea     r11, [rsp+140h+var_s0]
0x14001a155  mov     rbx, [r11+18h]
0x14001a159  mov     rdi, [r11+20h]
0x14001a15d  mov     rsp, r11
0x14001a160  pop     rbp
0x14001a161  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
