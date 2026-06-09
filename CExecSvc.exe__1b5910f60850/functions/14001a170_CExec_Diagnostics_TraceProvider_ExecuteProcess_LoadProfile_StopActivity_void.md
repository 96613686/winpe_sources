# CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile::StopActivity(void)

- ea: `0x14001a170`
- end: `0x14001a436`
- name: `?StopActivity@ExecuteProcess_LoadProfile@TraceProvider@Diagnostics@CExec@@MEAAXXZ`
- size: `710`
- prototype: `void __fastcall(CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1400013f0`
- `0x140001704`
- `0x14001837c`
- `0x1400186e0`
- `0x140019190`
- `0x14001a170`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001a1d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001a3a0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001a1d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001a3a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001a3cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14001a3cd`

## pseudocode

```c
void __fastcall CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile::StopActivity(
        CExec::Diagnostics::TraceProvider::ExecuteProcess_LoadProfile *this)
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
          (int)&word_14002A212,
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
          (int)&dword_14002A3BC,
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
0x14001a170  mov     [rsp-8+arg_8], rbx
0x14001a175  mov     [rsp-8+arg_10], rdi
0x14001a17a  push    rbp
0x14001a17b  mov     rbp, rsp
0x14001a17e  sub     rsp, 140h
0x14001a185  mov     rdi, [rcx+110h]
0x14001a18c  mov     rbx, rcx
0x14001a18f  mov     eax, [rdi+48h]
0x14001a192  test    eax, eax
0x14001a194  jns     loc_14001A379
0x14001a19a  add     rdi, 50h ; 'P'
0x14001a19e  cmp     eax, [rdi+8]
0x14001a1a1  jnz     loc_14001A379
0x14001a1a7  test    rdi, rdi
0x14001a1aa  jz      loc_14001A379
0x14001a1b0  lea     rdx, [rbp+SRWLock]
0x14001a1b4  mov     [rbp+SRWLock], 0
0x14001a1bc  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14001a1c1  mov     rax, [rbx+110h]
0x14001a1c8  mov     rcx, [rbp+SRWLock]; SRWLock
0x14001a1cc  mov     dword ptr [rax], 2
0x14001a1d2  test    rcx, rcx
0x14001a1d5  jz      short loc_14001A1DD
0x14001a1d7  call    cs:__imp_ReleaseSRWLockExclusive
0x14001a1dd  call    ?Provider@TraceProvider@Diagnostics@CExec@@SAPEBU_tlgProvider_t@@XZ; CExec::Diagnostics::TraceProvider::Provider(void)
0x14001a1e2  mov     r9, rax
0x14001a1e5  mov     ecx, [rax]
0x14001a1e7  cmp     ecx, 4
0x14001a1ea  jbe     loc_14001A41A
0x14001a1f0  mov     rax, [rax+18h]
0x14001a1f4  mov     rcx, [r9+10h]
0x14001a1f8  test    cl, 2
0x14001a1fb  jz      loc_14001A41A
0x14001a201  mov     rcx, rax
0x14001a204  and     ecx, 2
0x14001a207  cmp     rcx, rax
0x14001a20a  jnz     loc_14001A41A
0x14001a210  mov     rax, [rdi+30h]
0x14001a214  lea     rdx, word_14002A212; int
0x14001a21b  mov     [rbp+var_50], rax
0x14001a21f  mov     rcx, r9; int
0x14001a222  mov     eax, [rdi+44h]
0x14001a225  mov     dword ptr [rbp+var_78+4], eax
0x14001a228  mov     eax, [rdi+10h]
0x14001a22b  mov     dword ptr [rbp+var_70], eax
0x14001a22e  mov     rax, [rdi+78h]
0x14001a232  mov     [rbp+var_48], rax
0x14001a236  mov     rax, [rdi+70h]
0x14001a23a  mov     [rbp+var_40], rax
0x14001a23e  mov     eax, [rdi+68h]
0x14001a241  mov     r8, [rbx+110h]
0x14001a248  mov     dword ptr [rbp+var_70+4], eax
0x14001a24b  add     r8, 8; int
0x14001a24f  mov     rax, [rdi+60h]
0x14001a253  mov     [rbp+var_38], rax
0x14001a257  mov     rax, [rdi+58h]
0x14001a25b  mov     [rbp+var_30], rax
0x14001a25f  mov     eax, [rdi+50h]
0x14001a262  mov     dword ptr [rbp+var_68], eax
0x14001a265  mov     rax, [rdi+48h]
0x14001a269  mov     [rbp+var_28], rax
0x14001a26d  mov     eax, [rdi+20h]
0x14001a270  mov     dword ptr [rbp+var_68+4], eax
0x14001a273  mov     rax, [rdi+18h]
0x14001a277  mov     [rbp+var_20], rax
0x14001a27b  mov     eax, [rdi]
0x14001a27d  mov     [rbp+var_60], eax
0x14001a280  mov     rax, [rdi+80h]
0x14001a287  mov     [rbp+var_18], rax
0x14001a28b  mov     eax, [rdi+40h]
0x14001a28e  mov     dword ptr [rbp+var_78], eax
0x14001a291  mov     rax, [rdi+38h]
0x14001a295  mov     [rbp+var_10], rax
0x14001a299  mov     eax, [rdi+8]
0x14001a29c  mov     dword ptr [rbp+SRWLock], eax
0x14001a29f  lea     rax, [rbp+var_50]
0x14001a2a3  mov     [rsp+140h+var_90], rax; __int64
0x14001a2ab  lea     rax, [rbp+var_78+4]
0x14001a2af  mov     [rsp+140h+var_98], rax; __int64
0x14001a2b7  lea     rax, [rbp+var_70]
0x14001a2bb  mov     [rsp+140h+var_A0], rax; __int64
0x14001a2c3  lea     rax, [rbp+var_48]
0x14001a2c7  mov     [rsp+140h+var_A8], rax; __int64
0x14001a2cf  lea     rax, [rbp+var_40]
0x14001a2d3  mov     [rsp+140h+var_B0], rax; __int64
0x14001a2db  lea     rax, [rbp+var_70+4]
0x14001a2df  mov     [rsp+140h+var_B8], rax; __int64
0x14001a2e7  lea     rax, [rbp+var_38]
0x14001a2eb  mov     [rsp+140h+var_C0], rax; __int64
0x14001a2f3  lea     rax, [rbp+var_30]
0x14001a2f7  mov     [rsp+140h+var_C8], rax; __int64
0x14001a2fc  lea     rax, [rbp+var_68]
0x14001a300  mov     [rsp+140h+var_D0], rax; __int64
0x14001a305  lea     rax, [rbp+var_28]
0x14001a309  mov     [rsp+140h+var_D8], rax; __int64
0x14001a30e  lea     rax, [rbp+var_68+4]
0x14001a312  mov     [rsp+140h+var_E0], rax; __int64
0x14001a317  lea     rax, [rbp+var_20]
0x14001a31b  mov     [rsp+140h+var_E8], rax; __int64
0x14001a320  lea     rax, [rbp+var_60]
0x14001a324  mov     [rsp+140h+var_F0], rax; __int64
0x14001a329  lea     rax, [rbp+var_18]
0x14001a32d  mov     [rsp+140h+var_F8], rax; __int64
0x14001a332  lea     rax, [rbp+var_78]
0x14001a336  mov     [rsp+140h+var_100], rax; __int64
0x14001a33b  lea     rax, [rbp+var_10]
0x14001a33f  mov     [rsp+140h+var_108], rax; __int64
0x14001a344  lea     rax, [rbp+SRWLock]
0x14001a348  mov     [rsp+140h+var_110], rax; __int64
0x14001a34d  lea     rax, [rbp+var_8]
0x14001a351  mov     [rsp+140h+var_118], rax; __int64
0x14001a356  lea     rax, [rbp+var_58]
0x14001a35a  mov     [rsp+140h+var_120], rax; __int64
0x14001a35f  mov     [rbp+var_8], 1000000h
0x14001a367  mov     [rbp+var_58], 0
0x14001a36f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14001a374  jmp     loc_14001A41A
0x14001a379  lea     rdx, [rbp+SRWLock]
0x14001a37d  mov     [rbp+SRWLock], 0
0x14001a385  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14001a38a  mov     rax, [rbx+110h]
0x14001a391  mov     rcx, [rbp+SRWLock]; SRWLock
0x14001a395  mov     dword ptr [rax], 2
0x14001a39b  test    rcx, rcx
0x14001a39e  jz      short loc_14001A3A6
0x14001a3a0  call    cs:__imp_ReleaseSRWLockExclusive
0x14001a3a6  call    ?Provider@TraceProvider@Diagnostics@CExec@@SAPEBU_tlgProvider_t@@XZ; CExec::Diagnostics::TraceProvider::Provider(void)
0x14001a3ab  mov     rdi, rax
0x14001a3ae  mov     ecx, [rax]
0x14001a3b0  cmp     ecx, 4
0x14001a3b3  jbe     short loc_14001A41A
0x14001a3b5  mov     rax, [rax+18h]
0x14001a3b9  mov     rcx, [rdi+10h]
0x14001a3bd  test    cl, 2
0x14001a3c0  jz      short loc_14001A41A
0x14001a3c2  mov     rcx, rax
0x14001a3c5  and     ecx, 2
0x14001a3c8  cmp     rcx, rax
0x14001a3cb  jnz     short loc_14001A41A
0x14001a3cd  call    cs:__imp_GetCurrentThreadId
0x14001a3d3  mov     r8, [rbx+110h]
0x14001a3da  lea     rdx, dword_14002A3BC
0x14001a3e1  mov     dword ptr [rbp+SRWLock], eax
0x14001a3e4  mov     rcx, rdi
0x14001a3e7  mov     eax, [r8+48h]
0x14001a3eb  add     r8, 8
0x14001a3ef  mov     dword ptr [rbp+var_78], eax
0x14001a3f2  lea     rax, [rbp+SRWLock]
0x14001a3f6  mov     [rsp+140h+var_110], rax
0x14001a3fb  lea     rax, [rbp+var_78]
0x14001a3ff  mov     [rsp+140h+var_118], rax
0x14001a404  lea     rax, [rbp+var_58]
0x14001a408  mov     [rsp+140h+var_120], rax
0x14001a40d  mov     [rbp+var_58], 0
0x14001a415  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14001a41a  mov     rcx, rbx
0x14001a41d  lea     r11, [rsp+140h+var_s0]
0x14001a425  mov     rbx, [r11+18h]
0x14001a429  mov     rdi, [r11+20h]
0x14001a42d  mov     rsp, r11
0x14001a430  pop     rbp
0x14001a431  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
