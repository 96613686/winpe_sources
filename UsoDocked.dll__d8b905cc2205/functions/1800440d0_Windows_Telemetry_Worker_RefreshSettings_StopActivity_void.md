# Windows::Telemetry::Worker::RefreshSettings::StopActivity(void)

- ea: `0x1800440d0`
- end: `0x180044354`
- name: `?StopActivity@RefreshSettings@Worker@Telemetry@Windows@@MEAAXXZ`
- size: `644`
- prototype: `void __fastcall(Windows::Telemetry::Worker::RefreshSettings *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x1800013a4`
- `0x1800020d8`
- `0x180041ba0`
- `0x180041c1c`
- `0x180041cd8`
- `0x1800440d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004412a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800442bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18004412a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800442bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800442f4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800442f4`

## pseudocode

```c
void __fastcall Windows::Telemetry::Worker::RefreshSettings::StopActivity(
        Windows::Telemetry::Worker::RefreshSettings *this)
{
  __int64 v1; // rdi
  int v3; // eax
  __int64 v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  __int64 v6; // r9
  __int64 v7; // r8
  RTL_SRWLOCK *v8; // rcx
  __int64 v9; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  int v12; // r9d
  int v13; // [rsp+A0h] [rbp-19h] BYREF
  int v14; // [rsp+A4h] [rbp-15h] BYREF
  __int64 v15; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v16; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v17; // [rsp+B8h] [rbp-1h] BYREF
  __int64 v18; // [rsp+C0h] [rbp+7h] BYREF
  __int64 v19; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v20; // [rsp+D0h] [rbp+17h] BYREF
  __int64 v21; // [rsp+D8h] [rbp+1Fh] BYREF
  __int64 v22; // [rsp+E0h] [rbp+27h] BYREF
  __int64 v23; // [rsp+E8h] [rbp+2Fh] BYREF
  __int64 v24[4]; // [rsp+F0h] [rbp+37h] BYREF
  PSRWLOCK SRWLock; // [rsp+120h] [rbp+67h] BYREF
  __int64 v26; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v27; // [rsp+130h] [rbp+77h] BYREF
  __int64 v28; // [rsp+138h] [rbp+7Fh] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = v1 + 80, v3 == *(_DWORD *)(v4 + 8)) && v4 )
  {
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = *((_QWORD *)Windows::Telemetry::Base::Instance() + 1);
    if ( *(_DWORD *)v6 > 5u
      && (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x400000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      v7 = *((_QWORD *)this + 34);
      v15 = *(_QWORD *)(v4 + 120);
      v16 = *(_QWORD *)(v4 + 112);
      LODWORD(SRWLock) = *(_DWORD *)(v4 + 104);
      v17 = *(_QWORD *)(v4 + 96);
      v18 = *(_QWORD *)(v4 + 88);
      LODWORD(v26) = *(_DWORD *)(v4 + 80);
      v19 = *(_QWORD *)(v4 + 72);
      LODWORD(v27) = *(_DWORD *)(v4 + 32);
      v20 = *(_QWORD *)(v4 + 24);
      LODWORD(v28) = *(_DWORD *)v4;
      v21 = *(_QWORD *)(v4 + 128);
      v13 = *(_DWORD *)(v4 + 64);
      v22 = *(_QWORD *)(v4 + 56);
      v14 = *(_DWORD *)(v4 + 8);
      v23 = 0x1000000;
      v24[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v6,
        (int)&word_180081D6A,
        v7 + 8,
        (__int64)v24,
        (__int64)&v23,
        (__int64)&v14,
        (__int64)&v22,
        (__int64)&v13,
        (__int64)&v21,
        (__int64)&v28,
        (__int64)&v20,
        (__int64)&v27,
        (__int64)&v19,
        (__int64)&v26,
        (__int64)&v18,
        (__int64)&v17,
        (__int64)&SRWLock,
        (__int64)&v16,
        (__int64)&v15);
    }
  }
  else
  {
    wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v8 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
    v9 = *((_QWORD *)Windows::Telemetry::Base::Instance() + 1);
    if ( *(_DWORD *)v9 > 5u
      && (*(_QWORD *)(v9 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v9 + 24) & 0x400000000000LL) == *(_QWORD *)(v9 + 24) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      LODWORD(v26) = *(_DWORD *)(v11 + 72);
      v27 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)word_180081D1A,
        v11 + 8,
        v12,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x1800440d0  push    rbp
0x1800440d2  push    rbx
0x1800440d3  push    rdi
0x1800440d4  lea     rbp, [rsp-47h]
0x1800440d9  sub     rsp, 100h
0x1800440e0  mov     rdi, [rcx+110h]
0x1800440e7  mov     rbx, rcx
0x1800440ea  mov     eax, [rdi+48h]
0x1800440ed  test    eax, eax
0x1800440ef  jns     loc_18004429D
0x1800440f5  add     rdi, 50h ; 'P'
0x1800440f9  cmp     eax, [rdi+8]
0x1800440fc  jnz     loc_18004429D
0x180044102  test    rdi, rdi
0x180044105  jz      loc_18004429D
0x18004410b  lea     rdx, [rbp+57h+SRWLock]
0x18004410f  call    ?LockExclusive@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180044114  mov     rax, [rbx+110h]
0x18004411b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18004411f  mov     dword ptr [rax], 2
0x180044125  test    rcx, rcx
0x180044128  jz      short loc_180044130
0x18004412a  call    cs:__imp_ReleaseSRWLockExclusive
0x180044130  call    ?Instance@Base@Telemetry@Windows@@KAPEAV123@XZ; Windows::Telemetry::Base::Instance(void)
0x180044135  mov     r9, [rax+8]
0x180044139  mov     eax, [r9]
0x18004413c  cmp     eax, 5
0x18004413f  jbe     loc_180044342
0x180044145  mov     rdx, [r9+18h]
0x180044149  mov     rcx, 400000000000h
0x180044153  mov     rax, [r9+10h]
0x180044157  test    rcx, rax
0x18004415a  jz      loc_180044342
0x180044160  mov     rax, rdx
0x180044163  and     rax, rcx
0x180044166  cmp     rax, rdx
0x180044169  jnz     loc_180044342
0x18004416f  mov     rax, [rdi+78h]
0x180044173  lea     rdx, word_180081D6A; int
0x18004417a  mov     r8, [rbx+110h]
0x180044181  mov     rcx, r9; int
0x180044184  mov     [rbp+57h+var_68], rax
0x180044188  add     r8, 8; int
0x18004418c  mov     rax, [rdi+70h]
0x180044190  mov     [rbp+57h+var_60], rax
0x180044194  mov     eax, [rdi+68h]
0x180044197  mov     dword ptr [rbp+57h+SRWLock], eax
0x18004419a  mov     rax, [rdi+60h]
0x18004419e  mov     [rbp+57h+var_58], rax
0x1800441a2  mov     rax, [rdi+58h]
0x1800441a6  mov     [rbp+57h+var_50], rax
0x1800441aa  mov     eax, [rdi+50h]
0x1800441ad  mov     dword ptr [rbp+57h+arg_8], eax
0x1800441b0  mov     rax, [rdi+48h]
0x1800441b4  mov     [rbp+57h+var_48], rax
0x1800441b8  mov     eax, [rdi+20h]
0x1800441bb  mov     dword ptr [rbp+57h+arg_10], eax
0x1800441be  mov     rax, [rdi+18h]
0x1800441c2  mov     [rbp+57h+var_40], rax
0x1800441c6  mov     eax, [rdi]
0x1800441c8  mov     dword ptr [rbp+57h+arg_18], eax
0x1800441cb  mov     rax, [rdi+80h]
0x1800441d2  mov     [rbp+57h+var_38], rax
0x1800441d6  mov     eax, [rdi+40h]
0x1800441d9  mov     dword ptr [rbp+57h+var_70], eax
0x1800441dc  mov     rax, [rdi+38h]
0x1800441e0  mov     [rbp+57h+var_30], rax
0x1800441e4  mov     eax, [rdi+8]
0x1800441e7  mov     dword ptr [rbp+57h+var_70+4], eax
0x1800441ea  mov     eax, 1000000h
0x1800441ef  mov     [rbp+57h+var_28], rax
0x1800441f3  mov     [rbp+57h+var_20], rax
0x1800441f7  lea     rax, [rbp+57h+var_68]
0x1800441fb  mov     [rsp+110h+var_78], rax; __int64
0x180044203  lea     rax, [rbp+57h+var_60]
0x180044207  mov     [rsp+110h+var_80], rax; __int64
0x18004420f  lea     rax, [rbp+57h+SRWLock]
0x180044213  mov     [rsp+110h+var_88], rax; __int64
0x18004421b  lea     rax, [rbp+57h+var_58]
0x18004421f  mov     [rsp+110h+var_90], rax; __int64
0x180044227  lea     rax, [rbp+57h+var_50]
0x18004422b  mov     [rsp+110h+var_98], rax; __int64
0x180044230  lea     rax, [rbp+57h+arg_8]
0x180044234  mov     [rsp+110h+var_A0], rax; __int64
0x180044239  lea     rax, [rbp+57h+var_48]
0x18004423d  mov     [rsp+110h+var_A8], rax; __int64
0x180044242  lea     rax, [rbp+57h+arg_10]
0x180044246  mov     [rsp+110h+var_B0], rax; __int64
0x18004424b  lea     rax, [rbp+57h+var_40]
0x18004424f  mov     [rsp+110h+var_B8], rax; __int64
0x180044254  lea     rax, [rbp+57h+arg_18]
0x180044258  mov     [rsp+110h+var_C0], rax; __int64
0x18004425d  lea     rax, [rbp+57h+var_38]
0x180044261  mov     [rsp+110h+var_C8], rax; __int64
0x180044266  lea     rax, [rbp+57h+var_70]
0x18004426a  mov     [rsp+110h+var_D0], rax; __int64
0x18004426f  lea     rax, [rbp+57h+var_30]
0x180044273  mov     [rsp+110h+var_D8], rax; __int64
0x180044278  lea     rax, [rbp+57h+var_70+4]
0x18004427c  mov     [rsp+110h+var_E0], rax; __int64
0x180044281  lea     rax, [rbp+57h+var_28]
0x180044285  mov     [rsp+110h+var_E8], rax; __int64
0x18004428a  lea     rax, [rbp+57h+var_20]
0x18004428e  mov     [rsp+110h+var_F0], rax; __int64
0x180044293  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180044298  jmp     loc_180044342
0x18004429d  lea     rdx, [rbp+57h+SRWLock]
0x1800442a1  call    ?LockExclusive@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800442a6  mov     rax, [rbx+110h]
0x1800442ad  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x1800442b1  mov     dword ptr [rax], 2
0x1800442b7  test    rcx, rcx
0x1800442ba  jz      short loc_1800442C2
0x1800442bc  call    cs:__imp_ReleaseSRWLockExclusive
0x1800442c2  call    ?Instance@Base@Telemetry@Windows@@KAPEAV123@XZ; Windows::Telemetry::Base::Instance(void)
0x1800442c7  mov     rdi, [rax+8]
0x1800442cb  mov     eax, [rdi]
0x1800442cd  cmp     eax, 5
0x1800442d0  jbe     short loc_180044342
0x1800442d2  mov     rdx, [rdi+18h]
0x1800442d6  mov     rcx, 400000000000h
0x1800442e0  mov     rax, [rdi+10h]
0x1800442e4  test    rcx, rax
0x1800442e7  jz      short loc_180044342
0x1800442e9  mov     rax, rdx
0x1800442ec  and     rax, rcx
0x1800442ef  cmp     rax, rdx
0x1800442f2  jnz     short loc_180044342
0x1800442f4  call    cs:__imp_GetCurrentThreadId
0x1800442fa  mov     r8, [rbx+110h]
0x180044301  lea     rdx, word_180081D1A
0x180044308  mov     dword ptr [rbp+57h+SRWLock], eax
0x18004430b  mov     rcx, rdi
0x18004430e  mov     eax, [r8+48h]
0x180044312  add     r8, 8
0x180044316  mov     dword ptr [rbp+57h+arg_8], eax
0x180044319  mov     eax, 1000000h
0x18004431e  mov     [rbp+57h+arg_10], rax
0x180044322  lea     rax, [rbp+57h+SRWLock]
0x180044326  mov     [rsp+110h+var_E0], rax
0x18004432b  lea     rax, [rbp+57h+arg_8]
0x18004432f  mov     [rsp+110h+var_E8], rax
0x180044334  lea     rax, [rbp+57h+arg_10]
0x180044338  mov     [rsp+110h+var_F0], rax
0x18004433d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180044342  mov     rcx, rbx
0x180044345  add     rsp, 100h
0x18004434c  pop     rdi
0x18004434d  pop     rbx
0x18004434e  pop     rbp
0x18004434f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
