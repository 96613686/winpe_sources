# ServiceHostTelemetry::ServiceStartActivity::StopActivity(void)

- ea: `0x18000fbf0`
- end: `0x18000fece`
- name: `?StopActivity@ServiceStartActivity@ServiceHostTelemetry@@MEAAXXZ`
- size: `734`
- prototype: `void __fastcall(ServiceHostTelemetry::ServiceStartActivity *__hidden this)`
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
- `0x18000fbf0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fc5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fdef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fc5f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fdef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fe2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000fe2e`

## pseudocode

```c
void __fastcall ServiceHostTelemetry::ServiceStartActivity::StopActivity(
        ServiceHostTelemetry::ServiceStartActivity *this)
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
          (__int64)&dword_180015B3C,
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
        tlgWriteTransfer_EventWriteTransfer(v12, &byte_180015AE7, v15 + 8, 0, 5, v32);
      }
    }
  }
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18000fbf0  mov     [rsp-8+arg_8], rbx
0x18000fbf5  mov     [rsp-8+arg_10], rdi
0x18000fbfa  push    rbp
0x18000fbfb  lea     rbp, [rsp-50h]
0x18000fc00  sub     rsp, 170h
0x18000fc07  mov     rax, cs:__security_cookie
0x18000fc0e  xor     rax, rsp
0x18000fc11  mov     [rbp+50h+var_10], rax
0x18000fc15  mov     rdi, [rcx+110h]
0x18000fc1c  mov     rbx, rcx
0x18000fc1f  mov     eax, [rdi+48h]
0x18000fc22  test    eax, eax
0x18000fc24  jns     loc_18000FDD0
0x18000fc2a  add     rdi, 50h ; 'P'
0x18000fc2e  cmp     eax, [rdi+8]
0x18000fc31  jnz     loc_18000FDD0
0x18000fc37  test    rdi, rdi
0x18000fc3a  jz      loc_18000FDD0
0x18000fc40  lea     rdx, [rbp+50h+SRWLock]
0x18000fc44  call    ?LockExclusive@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000fc49  mov     rax, [rbx+110h]
0x18000fc50  mov     rcx, [rbp+50h+SRWLock]; SRWLock
0x18000fc54  mov     dword ptr [rax], 2
0x18000fc5a  test    rcx, rcx
0x18000fc5d  jz      short loc_18000FC65
0x18000fc5f  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fc65  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000fc6a  mov     r9, rax
0x18000fc6d  mov     ecx, [rax]
0x18000fc6f  cmp     ecx, 5
0x18000fc72  jbe     loc_18000FEA5
0x18000fc78  mov     rax, [rax+18h]
0x18000fc7c  mov     rdx, 400000000000h
0x18000fc86  mov     rcx, [r9+10h]
0x18000fc8a  test    rdx, rcx
0x18000fc8d  jz      loc_18000FEA5
0x18000fc93  mov     rcx, rax
0x18000fc96  and     rcx, rdx
0x18000fc99  cmp     rcx, rax
0x18000fc9c  jnz     loc_18000FEA5
0x18000fca2  mov     rax, [rdi+78h]
0x18000fca6  lea     rdx, dword_180015B3C
0x18000fcad  mov     r8, [rbx+110h]
0x18000fcb4  mov     rcx, r9
0x18000fcb7  mov     [rbp+50h+var_A8], rax
0x18000fcbb  add     r8, 8
0x18000fcbf  mov     rax, [rdi+70h]
0x18000fcc3  mov     [rbp+50h+var_A0], rax
0x18000fcc7  mov     eax, [rdi+68h]
0x18000fcca  mov     [rbp+50h+var_B8], eax
0x18000fccd  mov     rax, [rdi+60h]
0x18000fcd1  mov     [rbp+50h+var_98], rax
0x18000fcd5  mov     rax, [rdi+58h]
0x18000fcd9  mov     [rbp+50h+var_90], rax
0x18000fcdd  mov     eax, [rdi+50h]
0x18000fce0  mov     [rbp+50h+var_B4], eax
0x18000fce3  mov     rax, [rdi+48h]
0x18000fce7  mov     [rbp+50h+var_88], rax
0x18000fceb  mov     eax, [rdi+20h]
0x18000fcee  mov     [rbp+50h+var_B0], eax
0x18000fcf1  mov     rax, [rdi+18h]
0x18000fcf5  mov     [rbp+50h+var_80], rax
0x18000fcf9  mov     eax, [rdi]
0x18000fcfb  mov     [rbp+50h+var_AC], eax
0x18000fcfe  mov     rax, [rdi+80h]
0x18000fd05  mov     [rbp+50h+var_78], rax
0x18000fd09  mov     eax, [rdi+40h]
0x18000fd0c  mov     [rbp+50h+var_D0], eax
0x18000fd0f  mov     rax, [rdi+38h]
0x18000fd13  mov     [rbp+50h+var_70], rax
0x18000fd17  mov     eax, [rdi+8]
0x18000fd1a  mov     dword ptr [rbp+50h+SRWLock], eax
0x18000fd1d  mov     eax, 1000000h
0x18000fd22  mov     [rbp+50h+var_68], rax
0x18000fd26  mov     [rbp+50h+var_C0], rax
0x18000fd2a  lea     rax, [rbp+50h+var_A8]
0x18000fd2e  mov     [rsp+170h+var_D8], rax
0x18000fd36  lea     rax, [rbp+50h+var_A0]
0x18000fd3a  mov     [rsp+170h+var_E0], rax
0x18000fd42  lea     rax, [rbp+50h+var_B8]
0x18000fd46  mov     [rsp+170h+var_E8], rax
0x18000fd4e  lea     rax, [rbp+50h+var_98]
0x18000fd52  mov     [rsp+170h+var_F0], rax
0x18000fd5a  lea     rax, [rbp+50h+var_90]
0x18000fd5e  mov     [rsp+170h+var_F8], rax
0x18000fd63  lea     rax, [rbp+50h+var_B4]
0x18000fd67  mov     [rsp+170h+var_100], rax
0x18000fd6c  lea     rax, [rbp+50h+var_88]
0x18000fd70  mov     [rsp+170h+var_108], rax
0x18000fd75  lea     rax, [rbp+50h+var_B0]
0x18000fd79  mov     [rsp+170h+var_110], rax
0x18000fd7e  lea     rax, [rbp+50h+var_80]
0x18000fd82  mov     [rsp+170h+var_118], rax
0x18000fd87  lea     rax, [rbp+50h+var_AC]
0x18000fd8b  mov     [rsp+170h+var_120], rax
0x18000fd90  lea     rax, [rbp+50h+var_78]
0x18000fd94  mov     [rsp+170h+var_128], rax
0x18000fd99  lea     rax, [rbp+50h+var_D0]
0x18000fd9d  mov     [rsp+170h+var_130], rax
0x18000fda2  lea     rax, [rbp+50h+var_70]
0x18000fda6  mov     [rsp+170h+var_138], rax
0x18000fdab  lea     rax, [rbp+50h+SRWLock]
0x18000fdaf  mov     [rsp+170h+var_140], rax
0x18000fdb4  lea     rax, [rbp+50h+var_68]
0x18000fdb8  mov     [rsp+170h+var_148], rax
0x18000fdbd  lea     rax, [rbp+50h+var_C0]
0x18000fdc1  mov     [rsp+170h+var_150], rax
0x18000fdc6  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000fdcb  jmp     loc_18000FEA5
0x18000fdd0  lea     rdx, [rbp+50h+var_C0]
0x18000fdd4  call    ?LockExclusive@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000fdd9  mov     rax, [rbx+110h]
0x18000fde0  mov     rcx, [rbp+50h+var_C0]; SRWLock
0x18000fde4  mov     dword ptr [rax], 2
0x18000fdea  test    rcx, rcx
0x18000fded  jz      short loc_18000FDF5
0x18000fdef  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fdf5  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000fdfa  mov     rdi, rax
0x18000fdfd  mov     ecx, [rax]
0x18000fdff  cmp     ecx, 5
0x18000fe02  jbe     loc_18000FEA5
0x18000fe08  mov     rax, [rax+18h]
0x18000fe0c  mov     rdx, 400000000000h
0x18000fe16  mov     rcx, [rdi+10h]
0x18000fe1a  test    rdx, rcx
0x18000fe1d  jz      loc_18000FEA5
0x18000fe23  mov     rcx, rax
0x18000fe26  and     rcx, rdx
0x18000fe29  cmp     rcx, rax
0x18000fe2c  jnz     short loc_18000FEA5
0x18000fe2e  call    cs:__imp_GetCurrentThreadId
0x18000fe34  mov     r8, [rbx+110h]
0x18000fe3b  lea     rdx, byte_180015AE7
0x18000fe42  mov     dword ptr [rbp+50h+SRWLock], eax
0x18000fe45  xor     r9d, r9d
0x18000fe48  mov     rcx, rdi
0x18000fe4b  mov     [rbp+50h+var_18], 4
0x18000fe53  mov     [rbp+50h+var_28], 4
0x18000fe5b  mov     eax, [r8+48h]
0x18000fe5f  add     r8, 8
0x18000fe63  mov     [rbp+50h+var_D0], eax
0x18000fe66  mov     eax, 1000000h
0x18000fe6b  mov     [rbp+50h+var_C0], rax
0x18000fe6f  lea     rax, [rbp+50h+SRWLock]
0x18000fe73  mov     [rbp+50h+var_20], rax
0x18000fe77  lea     rax, [rbp+50h+var_D0]
0x18000fe7b  mov     [rbp+50h+var_30], rax
0x18000fe7f  lea     rax, [rbp+50h+var_C0]
0x18000fe83  mov     [rbp+50h+var_40], rax
0x18000fe87  lea     rax, [rbp+50h+var_60]
0x18000fe8b  mov     [rsp+170h+var_148], rax
0x18000fe90  mov     dword ptr [rsp+170h+var_150], 5
0x18000fe98  mov     [rbp+50h+var_38], 8
0x18000fea0  call    _tlgWriteTransfer_EventWriteTransfer
0x18000fea5  mov     rcx, rbx
0x18000fea8  call    ?IgnoreCurrentThread@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18000fead  mov     rcx, [rbp+50h+var_10]
0x18000feb1  xor     rcx, rsp; StackCookie
0x18000feb4  call    __security_check_cookie
0x18000feb9  lea     r11, [rsp+170h+var_s0]
0x18000fec1  mov     rbx, [r11+18h]
0x18000fec5  mov     rdi, [r11+20h]
0x18000fec9  mov     rsp, r11
0x18000fecc  pop     rbp
0x18000fecd  retn
```
