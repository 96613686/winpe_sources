# Windows::Telemetry::Worker::RefreshSettings::StopActivity(void)

- ea: `0x18003e2a0`
- end: `0x18003e533`
- name: `?StopActivity@RefreshSettings@Worker@Telemetry@Windows@@MEAAXXZ`
- size: `659`
- prototype: `void __fastcall(Windows::Telemetry::Worker::RefreshSettings *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180001c1c`
- `0x180001cac`
- `0x18001a1bc`
- `0x18003e044`
- `0x18003e2a0`
- `0x1800434ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e30e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e49a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e30e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003e49a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e4ca`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003e4ca`

## pseudocode

```c
void __fastcall Windows::Telemetry::Worker::RefreshSettings::StopActivity(
        Windows::Telemetry::Worker::RefreshSettings *this)
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
      wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
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
          (int)&byte_18009191D,
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
  wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
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
      (unsigned int)byte_1800918CD,
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
0x18003e2a0  mov     [rsp-8+arg_8], rbx
0x18003e2a5  mov     [rsp-8+arg_10], rsi
0x18003e2aa  push    rbp
0x18003e2ab  push    rdi
0x18003e2ac  push    r14
0x18003e2ae  lea     rbp, [rsp+10h]
0x18003e2b3  sub     rsp, 110h
0x18003e2ba  lea     rdi, [rcx+110h]
0x18003e2c1  mov     rsi, rcx
0x18003e2c4  mov     rbx, [rdi]
0x18003e2c7  mov     eax, [rbx+48h]
0x18003e2ca  test    eax, eax
0x18003e2cc  jns     loc_18003E474
0x18003e2d2  add     rbx, 50h ; 'P'
0x18003e2d6  cmp     eax, [rbx+8]
0x18003e2d9  jnz     loc_18003E474
0x18003e2df  mov     r14, rdi
0x18003e2e2  test    rbx, rbx
0x18003e2e5  jz      loc_18003E477
0x18003e2eb  lea     rdx, [rbp+SRWLock]
0x18003e2ef  mov     [rbp+SRWLock], 0
0x18003e2f7  call    ?LockExclusive@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003e2fc  mov     rax, [rdi]
0x18003e2ff  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003e303  mov     dword ptr [rax], 2
0x18003e309  test    rcx, rcx
0x18003e30c  jz      short loc_18003E314
0x18003e30e  call    cs:__imp_ReleaseSRWLockExclusive
0x18003e314  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x18003e319  mov     r9, rax
0x18003e31c  cmp     dword ptr [rax], 5
0x18003e31f  jbe     loc_18003E514
0x18003e325  mov     rdx, 400000000000h
0x18003e32f  test    [rax+10h], rdx
0x18003e333  jz      loc_18003E514
0x18003e339  mov     rcx, [rax+18h]
0x18003e33d  and     rcx, rdx
0x18003e340  cmp     rcx, [rax+18h]
0x18003e344  jnz     loc_18003E514
0x18003e34a  mov     rax, [rbx+78h]
0x18003e34e  lea     rdx, byte_18009191D; int
0x18003e355  mov     r8, [rdi]
0x18003e358  mov     rcx, r9; int
0x18003e35b  mov     [rbp+var_58], rax
0x18003e35f  add     r8, 8; int
0x18003e363  mov     rax, [rbx+70h]
0x18003e367  mov     [rbp+var_50], rax
0x18003e36b  mov     eax, [rbx+68h]
0x18003e36e  mov     dword ptr [rbp+var_78+4], eax
0x18003e371  mov     rax, [rbx+60h]
0x18003e375  mov     [rbp+var_48], rax
0x18003e379  mov     rax, [rbx+58h]
0x18003e37d  mov     [rbp+var_40], rax
0x18003e381  mov     eax, [rbx+50h]
0x18003e384  mov     dword ptr [rbp+var_70], eax
0x18003e387  mov     rax, [rbx+48h]
0x18003e38b  mov     [rbp+var_38], rax
0x18003e38f  mov     eax, [rbx+20h]
0x18003e392  mov     dword ptr [rbp+var_70+4], eax
0x18003e395  mov     rax, [rbx+18h]
0x18003e399  mov     [rbp+var_30], rax
0x18003e39d  mov     eax, [rbx]
0x18003e39f  mov     dword ptr [rbp+var_68], eax
0x18003e3a2  mov     rax, [rbx+80h]
0x18003e3a9  mov     [rbp+var_28], rax
0x18003e3ad  mov     eax, [rbx+40h]
0x18003e3b0  mov     dword ptr [rbp+var_78], eax
0x18003e3b3  mov     rax, [rbx+38h]
0x18003e3b7  mov     [rbp+var_20], rax
0x18003e3bb  mov     eax, [rbx+8]
0x18003e3be  mov     dword ptr [rbp+SRWLock], eax
0x18003e3c1  mov     eax, 1000000h
0x18003e3c6  mov     [rbp+var_18], rax
0x18003e3ca  mov     [rbp+var_60], rax
0x18003e3ce  lea     rax, [rbp+var_58]
0x18003e3d2  mov     [rsp+120h+var_88], rax; __int64
0x18003e3da  lea     rax, [rbp+var_50]
0x18003e3de  mov     [rsp+120h+var_90], rax; __int64
0x18003e3e6  lea     rax, [rbp+var_78+4]
0x18003e3ea  mov     [rsp+120h+var_98], rax; __int64
0x18003e3f2  lea     rax, [rbp+var_48]
0x18003e3f6  mov     [rsp+120h+var_A0], rax; __int64
0x18003e3fe  lea     rax, [rbp+var_40]
0x18003e402  mov     [rsp+120h+var_A8], rax; __int64
0x18003e407  lea     rax, [rbp+var_70]
0x18003e40b  mov     [rsp+120h+var_B0], rax; __int64
0x18003e410  lea     rax, [rbp+var_38]
0x18003e414  mov     [rsp+120h+var_B8], rax; __int64
0x18003e419  lea     rax, [rbp+var_70+4]
0x18003e41d  mov     [rsp+120h+var_C0], rax; __int64
0x18003e422  lea     rax, [rbp+var_30]
0x18003e426  mov     [rsp+120h+var_C8], rax; __int64
0x18003e42b  lea     rax, [rbp+var_68]
0x18003e42f  mov     [rsp+120h+var_D0], rax; __int64
0x18003e434  lea     rax, [rbp+var_28]
0x18003e438  mov     [rsp+120h+var_D8], rax; __int64
0x18003e43d  lea     rax, [rbp+var_78]
0x18003e441  mov     [rsp+120h+var_E0], rax; __int64
0x18003e446  lea     rax, [rbp+var_20]
0x18003e44a  mov     [rsp+120h+var_E8], rax; __int64
0x18003e44f  lea     rax, [rbp+SRWLock]
0x18003e453  mov     [rsp+120h+var_F0], rax; __int64
0x18003e458  lea     rax, [rbp+var_18]
0x18003e45c  mov     [rsp+120h+var_F8], rax; __int64
0x18003e461  lea     rax, [rbp+var_60]
0x18003e465  mov     [rsp+120h+var_100], rax; __int64
0x18003e46a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &)
0x18003e46f  jmp     loc_18003E514
0x18003e474  mov     r14, rdi
0x18003e477  lea     rdx, [rbp+SRWLock]
0x18003e47b  mov     [rbp+SRWLock], 0
0x18003e483  call    ?LockExclusive@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003e488  mov     rax, [r14]
0x18003e48b  mov     rcx, [rbp+SRWLock]; SRWLock
0x18003e48f  mov     dword ptr [rax], 2
0x18003e495  test    rcx, rcx
0x18003e498  jz      short loc_18003E4A0
0x18003e49a  call    cs:__imp_ReleaseSRWLockExclusive
0x18003e4a0  call    ?Provider@Base@Telemetry@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Telemetry::Base::Provider(void)
0x18003e4a5  mov     rbx, rax
0x18003e4a8  cmp     dword ptr [rax], 5
0x18003e4ab  jbe     short loc_18003E514
0x18003e4ad  mov     rdx, 400000000000h
0x18003e4b7  test    [rax+10h], rdx
0x18003e4bb  jz      short loc_18003E514
0x18003e4bd  mov     rcx, [rax+18h]
0x18003e4c1  and     rcx, rdx
0x18003e4c4  cmp     rcx, [rax+18h]
0x18003e4c8  jnz     short loc_18003E514
0x18003e4ca  call    cs:__imp_GetCurrentThreadId
0x18003e4d0  mov     r8, [rdi]
0x18003e4d3  lea     rdx, byte_1800918CD
0x18003e4da  mov     dword ptr [rbp+SRWLock], eax
0x18003e4dd  mov     rcx, rbx
0x18003e4e0  mov     eax, [r8+48h]
0x18003e4e4  add     r8, 8
0x18003e4e8  mov     dword ptr [rbp+var_78], eax
0x18003e4eb  mov     eax, 1000000h
0x18003e4f0  mov     [rbp+var_60], rax
0x18003e4f4  lea     rax, [rbp+SRWLock]
0x18003e4f8  mov     [rsp+120h+var_F0], rax
0x18003e4fd  lea     rax, [rbp+var_78]
0x18003e501  mov     [rsp+120h+var_F8], rax
0x18003e506  lea     rax, [rbp+var_60]
0x18003e50a  mov     [rsp+120h+var_100], rax
0x18003e50f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003e514  mov     rcx, rsi
0x18003e517  lea     r11, [rsp+120h+var_10]
0x18003e51f  mov     rbx, [r11+28h]
0x18003e523  mov     rsi, [r11+30h]
0x18003e527  mov     rsp, r11
0x18003e52a  pop     r14
0x18003e52c  pop     rdi
0x18003e52d  pop     rbp
0x18003e52e  jmp     ?IgnoreCurrentThread@?$ActivityBase@VBase@Telemetry@Windows@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<Windows::Telemetry::Base,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
