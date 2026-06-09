# ServiceHostTelemetry::ServiceStopActivity::StopActivity(void)

- ea: `0x18000fee0`
- end: `0x1800101be`
- name: `?StopActivity@ServiceStopActivity@ServiceHostTelemetry@@MEAAXXZ`
- size: `734`
- prototype: `void __fastcall(ServiceHostTelemetry::ServiceStopActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x1800015a8`
- `0x180001bdc`
- `0x180002bc0`
- `0x18000a648`
- `0x18000e400`
- `0x18000e47c`
- `0x18000fee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ff4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800100df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000ff4f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800100df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001011e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001011e`

## pseudocode

```c
void __fastcall ServiceHostTelemetry::ServiceStopActivity::StopActivity(
        ServiceHostTelemetry::ServiceStopActivity *this)
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
  int v16; // [rsp+A0h] [rbp-80h] BYREF
  PSRWLOCK SRWLock; // [rsp+A8h] [rbp-78h] BYREF
  PSRWLOCK v18; // [rsp+B0h] [rbp-70h] BYREF
  int v19; // [rsp+B8h] [rbp-68h] BYREF
  int v20; // [rsp+BCh] [rbp-64h] BYREF
  int v21; // [rsp+C0h] [rbp-60h] BYREF
  int v22; // [rsp+C4h] [rbp-5Ch] BYREF
  __int64 *v23; // [rsp+C8h] [rbp-58h] BYREF
  const unsigned __int16 *v24; // [rsp+D0h] [rbp-50h] BYREF
  __int64 *v25; // [rsp+D8h] [rbp-48h] BYREF
  const unsigned __int16 *v26; // [rsp+E0h] [rbp-40h] BYREF
  const unsigned __int16 *v27; // [rsp+E8h] [rbp-38h] BYREF
  __int64 *v28; // [rsp+F0h] [rbp-30h] BYREF
  const unsigned __int16 *v29; // [rsp+F8h] [rbp-28h] BYREF
  const unsigned __int16 *v30; // [rsp+100h] [rbp-20h] BYREF
  __int64 v31; // [rsp+108h] [rbp-18h] BYREF
  _BYTE v32[32]; // [rsp+110h] [rbp-10h] BYREF
  PSRWLOCK *v33; // [rsp+130h] [rbp+10h]
  __int64 v34; // [rsp+138h] [rbp+18h]
  int *v35; // [rsp+140h] [rbp+20h]
  __int64 v36; // [rsp+148h] [rbp+28h]
  PSRWLOCK *p_SRWLock; // [rsp+150h] [rbp+30h]
  __int64 v38; // [rsp+158h] [rbp+38h]

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = ServiceHostLogging::Provider();
    v7 = (__int64)v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      v8 = *((_QWORD *)v6 + 3);
      if ( (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0 && (v8 & 0x400000000000LL) == v8 )
      {
        v9 = *((_QWORD *)this + 34);
        v23 = (__int64 *)*((_QWORD *)v4 + 15);
        v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        v19 = v4[26];
        v25 = (__int64 *)*((_QWORD *)v4 + 12);
        v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
        v20 = v4[20];
        v27 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
        v21 = v4[8];
        v28 = (__int64 *)*((_QWORD *)v4 + 3);
        v22 = *v4;
        v29 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
        v16 = v4[16];
        v30 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
        LODWORD(SRWLock) = v4[2];
        v31 = 0x1000000;
        v18 = (PSRWLOCK)0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v7,
          (__int64)&word_18001579E,
          v9 + 8,
          v7,
          (__int64)&v18,
          (__int64)&v31,
          (__int64)&SRWLock,
          &v30,
          (__int64)&v16,
          &v29,
          (__int64)&v22,
          &v28,
          (__int64)&v21,
          &v27,
          (__int64)&v20,
          &v26,
          &v25,
          (__int64)&v19,
          &v24,
          &v23);
      }
    }
  }
  else
  {
    wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &v18);
    v10 = v18;
    **((_DWORD **)this + 34) = 2;
    if ( v10 )
      ReleaseSRWLockExclusive(v10);
    v11 = ServiceHostLogging::Provider();
    v12 = v11;
    if ( *(_DWORD *)v11 > 5u )
    {
      v13 = *((_QWORD *)v11 + 3);
      if ( (*((_QWORD *)v12 + 2) & 0x400000000000LL) != 0 && (v13 & 0x400000000000LL) == v13 )
      {
        CurrentThreadId = GetCurrentThreadId();
        v15 = *((_QWORD *)this + 34);
        LODWORD(SRWLock) = CurrentThreadId;
        v38 = 4;
        v36 = 4;
        v16 = *(_DWORD *)(v15 + 72);
        v18 = (PSRWLOCK)0x1000000;
        p_SRWLock = &SRWLock;
        v35 = &v16;
        v33 = &v18;
        v34 = 8;
        tlgWriteTransfer_EventWriteTransfer(v12, word_18001574A, v15 + 8, 0, 5, v32);
      }
    }
  }
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000fee0  mov     [rsp-8+arg_8], rbx
0x18000fee5  mov     [rsp-8+arg_10], rdi
0x18000feea  push    rbp
0x18000feeb  lea     rbp, [rsp-50h]
0x18000fef0  sub     rsp, 170h
0x18000fef7  mov     rax, cs:__security_cookie
0x18000fefe  xor     rax, rsp
0x18000ff01  mov     [rbp+50h+var_10], rax
0x18000ff05  mov     rdi, [rcx+110h]
0x18000ff0c  mov     rbx, rcx
0x18000ff0f  mov     eax, [rdi+48h]
0x18000ff12  test    eax, eax
0x18000ff14  jns     loc_1800100C0
0x18000ff1a  add     rdi, 50h ; 'P'
0x18000ff1e  cmp     eax, [rdi+8]
0x18000ff21  jnz     loc_1800100C0
0x18000ff27  test    rdi, rdi
0x18000ff2a  jz      loc_1800100C0
0x18000ff30  lea     rdx, [rbp+50h+SRWLock]
0x18000ff34  call    ?LockExclusive@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000ff39  mov     rax, [rbx+110h]
0x18000ff40  mov     rcx, [rbp+50h+SRWLock]; SRWLock
0x18000ff44  mov     dword ptr [rax], 2
0x18000ff4a  test    rcx, rcx
0x18000ff4d  jz      short loc_18000FF55
0x18000ff4f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ff55  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000ff5a  mov     r9, rax
0x18000ff5d  mov     ecx, [rax]
0x18000ff5f  cmp     ecx, 5
0x18000ff62  jbe     loc_180010195
0x18000ff68  mov     rax, [rax+18h]
0x18000ff6c  mov     rdx, 400000000000h
0x18000ff76  mov     rcx, [r9+10h]
0x18000ff7a  test    rdx, rcx
0x18000ff7d  jz      loc_180010195
0x18000ff83  mov     rcx, rax
0x18000ff86  and     rcx, rdx
0x18000ff89  cmp     rcx, rax
0x18000ff8c  jnz     loc_180010195
0x18000ff92  mov     rax, [rdi+78h]
0x18000ff96  lea     rdx, word_18001579E
0x18000ff9d  mov     r8, [rbx+110h]
0x18000ffa4  mov     rcx, r9
0x18000ffa7  mov     [rbp+50h+var_A8], rax
0x18000ffab  add     r8, 8
0x18000ffaf  mov     rax, [rdi+70h]
0x18000ffb3  mov     [rbp+50h+var_A0], rax
0x18000ffb7  mov     eax, [rdi+68h]
0x18000ffba  mov     [rbp+50h+var_B8], eax
0x18000ffbd  mov     rax, [rdi+60h]
0x18000ffc1  mov     [rbp+50h+var_98], rax
0x18000ffc5  mov     rax, [rdi+58h]
0x18000ffc9  mov     [rbp+50h+var_90], rax
0x18000ffcd  mov     eax, [rdi+50h]
0x18000ffd0  mov     [rbp+50h+var_B4], eax
0x18000ffd3  mov     rax, [rdi+48h]
0x18000ffd7  mov     [rbp+50h+var_88], rax
0x18000ffdb  mov     eax, [rdi+20h]
0x18000ffde  mov     [rbp+50h+var_B0], eax
0x18000ffe1  mov     rax, [rdi+18h]
0x18000ffe5  mov     [rbp+50h+var_80], rax
0x18000ffe9  mov     eax, [rdi]
0x18000ffeb  mov     [rbp+50h+var_AC], eax
0x18000ffee  mov     rax, [rdi+80h]
0x18000fff5  mov     [rbp+50h+var_78], rax
0x18000fff9  mov     eax, [rdi+40h]
0x18000fffc  mov     [rbp+50h+var_D0], eax
0x18000ffff  mov     rax, [rdi+38h]
0x180010003  mov     [rbp+50h+var_70], rax
0x180010007  mov     eax, [rdi+8]
0x18001000a  mov     dword ptr [rbp+50h+SRWLock], eax
0x18001000d  mov     eax, 1000000h
0x180010012  mov     [rbp+50h+var_68], rax
0x180010016  mov     [rbp+50h+var_C0], rax
0x18001001a  lea     rax, [rbp+50h+var_A8]
0x18001001e  mov     [rsp+170h+var_D8], rax
0x180010026  lea     rax, [rbp+50h+var_A0]
0x18001002a  mov     [rsp+170h+var_E0], rax
0x180010032  lea     rax, [rbp+50h+var_B8]
0x180010036  mov     [rsp+170h+var_E8], rax
0x18001003e  lea     rax, [rbp+50h+var_98]
0x180010042  mov     [rsp+170h+var_F0], rax
0x18001004a  lea     rax, [rbp+50h+var_90]
0x18001004e  mov     [rsp+170h+var_F8], rax
0x180010053  lea     rax, [rbp+50h+var_B4]
0x180010057  mov     [rsp+170h+var_100], rax
0x18001005c  lea     rax, [rbp+50h+var_88]
0x180010060  mov     [rsp+170h+var_108], rax
0x180010065  lea     rax, [rbp+50h+var_B0]
0x180010069  mov     [rsp+170h+var_110], rax
0x18001006e  lea     rax, [rbp+50h+var_80]
0x180010072  mov     [rsp+170h+var_118], rax
0x180010077  lea     rax, [rbp+50h+var_AC]
0x18001007b  mov     [rsp+170h+var_120], rax
0x180010080  lea     rax, [rbp+50h+var_78]
0x180010084  mov     [rsp+170h+var_128], rax
0x180010089  lea     rax, [rbp+50h+var_D0]
0x18001008d  mov     [rsp+170h+var_130], rax
0x180010092  lea     rax, [rbp+50h+var_70]
0x180010096  mov     [rsp+170h+var_138], rax
0x18001009b  lea     rax, [rbp+50h+SRWLock]
0x18001009f  mov     [rsp+170h+var_140], rax
0x1800100a4  lea     rax, [rbp+50h+var_68]
0x1800100a8  mov     [rsp+170h+var_148], rax
0x1800100ad  lea     rax, [rbp+50h+var_C0]
0x1800100b1  mov     [rsp+170h+var_150], rax
0x1800100b6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800100bb  jmp     loc_180010195
0x1800100c0  lea     rdx, [rbp+50h+var_C0]
0x1800100c4  call    ?LockExclusive@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800100c9  mov     rax, [rbx+110h]
0x1800100d0  mov     rcx, [rbp+50h+var_C0]; SRWLock
0x1800100d4  mov     dword ptr [rax], 2
0x1800100da  test    rcx, rcx
0x1800100dd  jz      short loc_1800100E5
0x1800100df  call    cs:__imp_ReleaseSRWLockExclusive
0x1800100e5  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x1800100ea  mov     rdi, rax
0x1800100ed  mov     ecx, [rax]
0x1800100ef  cmp     ecx, 5
0x1800100f2  jbe     loc_180010195
0x1800100f8  mov     rax, [rax+18h]
0x1800100fc  mov     rdx, 400000000000h
0x180010106  mov     rcx, [rdi+10h]
0x18001010a  test    rdx, rcx
0x18001010d  jz      loc_180010195
0x180010113  mov     rcx, rax
0x180010116  and     rcx, rdx
0x180010119  cmp     rcx, rax
0x18001011c  jnz     short loc_180010195
0x18001011e  call    cs:__imp_GetCurrentThreadId
0x180010124  mov     r8, [rbx+110h]
0x18001012b  lea     rdx, word_18001574A
0x180010132  mov     dword ptr [rbp+50h+SRWLock], eax
0x180010135  xor     r9d, r9d
0x180010138  mov     rcx, rdi
0x18001013b  mov     [rbp+50h+var_18], 4
0x180010143  mov     [rbp+50h+var_28], 4
0x18001014b  mov     eax, [r8+48h]
0x18001014f  add     r8, 8
0x180010153  mov     [rbp+50h+var_D0], eax
0x180010156  mov     eax, 1000000h
0x18001015b  mov     [rbp+50h+var_C0], rax
0x18001015f  lea     rax, [rbp+50h+SRWLock]
0x180010163  mov     [rbp+50h+var_20], rax
0x180010167  lea     rax, [rbp+50h+var_D0]
0x18001016b  mov     [rbp+50h+var_30], rax
0x18001016f  lea     rax, [rbp+50h+var_C0]
0x180010173  mov     [rbp+50h+var_40], rax
0x180010177  lea     rax, [rbp+50h+var_60]
0x18001017b  mov     [rsp+170h+var_148], rax
0x180010180  mov     dword ptr [rsp+170h+var_150], 5
0x180010188  mov     [rbp+50h+var_38], 8
0x180010190  call    _tlgWriteTransfer_EventWriteTransfer
0x180010195  mov     rcx, rbx
0x180010198  call    ?IgnoreCurrentThread@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18001019d  mov     rcx, [rbp+50h+var_10]
0x1800101a1  xor     rcx, rsp; StackCookie
0x1800101a4  call    __security_check_cookie
0x1800101a9  lea     r11, [rsp+170h+var_s0]
0x1800101b1  mov     rbx, [r11+18h]
0x1800101b5  mov     rdi, [r11+20h]
0x1800101b9  mov     rsp, r11
0x1800101bc  pop     rbp
0x1800101bd  retn
```
