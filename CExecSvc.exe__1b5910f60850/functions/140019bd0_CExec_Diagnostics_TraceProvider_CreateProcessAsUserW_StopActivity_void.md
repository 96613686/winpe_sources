# CExec::Diagnostics::TraceProvider::CreateProcessAsUserW::StopActivity(void)

- ea: `0x140019bd0`
- end: `0x140019e96`
- name: `?StopActivity@CreateProcessAsUserW@TraceProvider@Diagnostics@CExec@@MEAAXXZ`
- size: `710`
- prototype: `void __fastcall(CExec::Diagnostics::TraceProvider::CreateProcessAsUserW *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting`

## callees

- `0x1400013f0`
- `0x140001704`
- `0x14001837c`
- `0x1400186e0`
- `0x140019190`
- `0x140019bd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140019c37`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140019e00`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140019c37`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140019e00`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140019e2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140019e2d`

## pseudocode

```c
void __fastcall CExec::Diagnostics::TraceProvider::CreateProcessAsUserW::StopActivity(
        CExec::Diagnostics::TraceProvider::CreateProcessAsUserW *this)
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
          (int)&byte_140029F8D,
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
          (int)&byte_14002A367,
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
0x140019bd0  mov     [rsp-8+arg_8], rbx
0x140019bd5  mov     [rsp-8+arg_10], rdi
0x140019bda  push    rbp
0x140019bdb  mov     rbp, rsp
0x140019bde  sub     rsp, 140h
0x140019be5  mov     rdi, [rcx+110h]
0x140019bec  mov     rbx, rcx
0x140019bef  mov     eax, [rdi+48h]
0x140019bf2  test    eax, eax
0x140019bf4  jns     loc_140019DD9
0x140019bfa  add     rdi, 50h ; 'P'
0x140019bfe  cmp     eax, [rdi+8]
0x140019c01  jnz     loc_140019DD9
0x140019c07  test    rdi, rdi
0x140019c0a  jz      loc_140019DD9
0x140019c10  lea     rdx, [rbp+SRWLock]
0x140019c14  mov     [rbp+SRWLock], 0
0x140019c1c  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140019c21  mov     rax, [rbx+110h]
0x140019c28  mov     rcx, [rbp+SRWLock]; SRWLock
0x140019c2c  mov     dword ptr [rax], 2
0x140019c32  test    rcx, rcx
0x140019c35  jz      short loc_140019C3D
0x140019c37  call    cs:__imp_ReleaseSRWLockExclusive
0x140019c3d  call    ?Provider@TraceProvider@Diagnostics@CExec@@SAPEBU_tlgProvider_t@@XZ; CExec::Diagnostics::TraceProvider::Provider(void)
0x140019c42  mov     r9, rax
0x140019c45  mov     ecx, [rax]
0x140019c47  cmp     ecx, 4
0x140019c4a  jbe     loc_140019E7A
0x140019c50  mov     rax, [rax+18h]
0x140019c54  mov     rcx, [r9+10h]
0x140019c58  test    cl, 2
0x140019c5b  jz      loc_140019E7A
0x140019c61  mov     rcx, rax
0x140019c64  and     ecx, 2
0x140019c67  cmp     rcx, rax
0x140019c6a  jnz     loc_140019E7A
0x140019c70  mov     rax, [rdi+30h]
0x140019c74  lea     rdx, byte_140029F8D; int
0x140019c7b  mov     [rbp+var_50], rax
0x140019c7f  mov     rcx, r9; int
0x140019c82  mov     eax, [rdi+44h]
0x140019c85  mov     dword ptr [rbp+var_78+4], eax
0x140019c88  mov     eax, [rdi+10h]
0x140019c8b  mov     dword ptr [rbp+var_70], eax
0x140019c8e  mov     rax, [rdi+78h]
0x140019c92  mov     [rbp+var_48], rax
0x140019c96  mov     rax, [rdi+70h]
0x140019c9a  mov     [rbp+var_40], rax
0x140019c9e  mov     eax, [rdi+68h]
0x140019ca1  mov     r8, [rbx+110h]
0x140019ca8  mov     dword ptr [rbp+var_70+4], eax
0x140019cab  add     r8, 8; int
0x140019caf  mov     rax, [rdi+60h]
0x140019cb3  mov     [rbp+var_38], rax
0x140019cb7  mov     rax, [rdi+58h]
0x140019cbb  mov     [rbp+var_30], rax
0x140019cbf  mov     eax, [rdi+50h]
0x140019cc2  mov     dword ptr [rbp+var_68], eax
0x140019cc5  mov     rax, [rdi+48h]
0x140019cc9  mov     [rbp+var_28], rax
0x140019ccd  mov     eax, [rdi+20h]
0x140019cd0  mov     dword ptr [rbp+var_68+4], eax
0x140019cd3  mov     rax, [rdi+18h]
0x140019cd7  mov     [rbp+var_20], rax
0x140019cdb  mov     eax, [rdi]
0x140019cdd  mov     [rbp+var_60], eax
0x140019ce0  mov     rax, [rdi+80h]
0x140019ce7  mov     [rbp+var_18], rax
0x140019ceb  mov     eax, [rdi+40h]
0x140019cee  mov     dword ptr [rbp+var_78], eax
0x140019cf1  mov     rax, [rdi+38h]
0x140019cf5  mov     [rbp+var_10], rax
0x140019cf9  mov     eax, [rdi+8]
0x140019cfc  mov     dword ptr [rbp+SRWLock], eax
0x140019cff  lea     rax, [rbp+var_50]
0x140019d03  mov     [rsp+140h+var_90], rax; __int64
0x140019d0b  lea     rax, [rbp+var_78+4]
0x140019d0f  mov     [rsp+140h+var_98], rax; __int64
0x140019d17  lea     rax, [rbp+var_70]
0x140019d1b  mov     [rsp+140h+var_A0], rax; __int64
0x140019d23  lea     rax, [rbp+var_48]
0x140019d27  mov     [rsp+140h+var_A8], rax; __int64
0x140019d2f  lea     rax, [rbp+var_40]
0x140019d33  mov     [rsp+140h+var_B0], rax; __int64
0x140019d3b  lea     rax, [rbp+var_70+4]
0x140019d3f  mov     [rsp+140h+var_B8], rax; __int64
0x140019d47  lea     rax, [rbp+var_38]
0x140019d4b  mov     [rsp+140h+var_C0], rax; __int64
0x140019d53  lea     rax, [rbp+var_30]
0x140019d57  mov     [rsp+140h+var_C8], rax; __int64
0x140019d5c  lea     rax, [rbp+var_68]
0x140019d60  mov     [rsp+140h+var_D0], rax; __int64
0x140019d65  lea     rax, [rbp+var_28]
0x140019d69  mov     [rsp+140h+var_D8], rax; __int64
0x140019d6e  lea     rax, [rbp+var_68+4]
0x140019d72  mov     [rsp+140h+var_E0], rax; __int64
0x140019d77  lea     rax, [rbp+var_20]
0x140019d7b  mov     [rsp+140h+var_E8], rax; __int64
0x140019d80  lea     rax, [rbp+var_60]
0x140019d84  mov     [rsp+140h+var_F0], rax; __int64
0x140019d89  lea     rax, [rbp+var_18]
0x140019d8d  mov     [rsp+140h+var_F8], rax; __int64
0x140019d92  lea     rax, [rbp+var_78]
0x140019d96  mov     [rsp+140h+var_100], rax; __int64
0x140019d9b  lea     rax, [rbp+var_10]
0x140019d9f  mov     [rsp+140h+var_108], rax; __int64
0x140019da4  lea     rax, [rbp+SRWLock]
0x140019da8  mov     [rsp+140h+var_110], rax; __int64
0x140019dad  lea     rax, [rbp+var_8]
0x140019db1  mov     [rsp+140h+var_118], rax; __int64
0x140019db6  lea     rax, [rbp+var_58]
0x140019dba  mov     [rsp+140h+var_120], rax; __int64
0x140019dbf  mov     [rbp+var_8], 1000000h
0x140019dc7  mov     [rbp+var_58], 0
0x140019dcf  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x140019dd4  jmp     loc_140019E7A
0x140019dd9  lea     rdx, [rbp+SRWLock]
0x140019ddd  mov     [rbp+SRWLock], 0
0x140019de5  call    ?LockExclusive@?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140019dea  mov     rax, [rbx+110h]
0x140019df1  mov     rcx, [rbp+SRWLock]; SRWLock
0x140019df5  mov     dword ptr [rax], 2
0x140019dfb  test    rcx, rcx
0x140019dfe  jz      short loc_140019E06
0x140019e00  call    cs:__imp_ReleaseSRWLockExclusive
0x140019e06  call    ?Provider@TraceProvider@Diagnostics@CExec@@SAPEBU_tlgProvider_t@@XZ; CExec::Diagnostics::TraceProvider::Provider(void)
0x140019e0b  mov     rdi, rax
0x140019e0e  mov     ecx, [rax]
0x140019e10  cmp     ecx, 4
0x140019e13  jbe     short loc_140019E7A
0x140019e15  mov     rax, [rax+18h]
0x140019e19  mov     rcx, [rdi+10h]
0x140019e1d  test    cl, 2
0x140019e20  jz      short loc_140019E7A
0x140019e22  mov     rcx, rax
0x140019e25  and     ecx, 2
0x140019e28  cmp     rcx, rax
0x140019e2b  jnz     short loc_140019E7A
0x140019e2d  call    cs:__imp_GetCurrentThreadId
0x140019e33  mov     r8, [rbx+110h]
0x140019e3a  lea     rdx, byte_14002A367
0x140019e41  mov     dword ptr [rbp+SRWLock], eax
0x140019e44  mov     rcx, rdi
0x140019e47  mov     eax, [r8+48h]
0x140019e4b  add     r8, 8
0x140019e4f  mov     dword ptr [rbp+var_78], eax
0x140019e52  lea     rax, [rbp+SRWLock]
0x140019e56  mov     [rsp+140h+var_110], rax
0x140019e5b  lea     rax, [rbp+var_78]
0x140019e5f  mov     [rsp+140h+var_118], rax
0x140019e64  lea     rax, [rbp+var_58]
0x140019e68  mov     [rsp+140h+var_120], rax
0x140019e6d  mov     [rbp+var_58], 0
0x140019e75  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140019e7a  mov     rcx, rbx
0x140019e7d  lea     r11, [rsp+140h+var_s0]
0x140019e85  mov     rbx, [r11+18h]
0x140019e89  mov     rdi, [r11+20h]
0x140019e8d  mov     rsp, r11
0x140019e90  pop     rbp
0x140019e91  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTraceProvider@Diagnostics@CExec@@$0A@$01$03$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CExec::Diagnostics::TraceProvider,0,2,4,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
