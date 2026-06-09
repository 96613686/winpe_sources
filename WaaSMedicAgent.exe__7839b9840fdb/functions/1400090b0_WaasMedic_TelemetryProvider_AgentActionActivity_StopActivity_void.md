# WaasMedic::TelemetryProvider::AgentActionActivity::StopActivity(void)

- ea: `0x1400090b0`
- end: `0x14000938e`
- name: `?StopActivity@AgentActionActivity@TelemetryProvider@WaasMedic@@MEAAXXZ`
- size: `734`
- prototype: `void __fastcall(WaasMedic::TelemetryProvider::AgentActionActivity *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update`

## callees

- `0x140001008`
- `0x14000198c`
- `0x140002a30`
- `0x14000827c`
- `0x14000830c`
- `0x14000885c`
- `0x1400090b0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000911f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400092af`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14000911f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400092af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400092ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400092ee`

## pseudocode

```c
void __fastcall WaasMedic::TelemetryProvider::AgentActionActivity::StopActivity(
        WaasMedic::TelemetryProvider::AgentActionActivity *this)
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
  const unsigned __int16 *v23; // [rsp+C8h] [rbp-58h] BYREF
  const unsigned __int16 *v24; // [rsp+D0h] [rbp-50h] BYREF
  const unsigned __int16 *v25; // [rsp+D8h] [rbp-48h] BYREF
  const unsigned __int16 *v26; // [rsp+E0h] [rbp-40h] BYREF
  const unsigned __int16 *v27; // [rsp+E8h] [rbp-38h] BYREF
  const unsigned __int16 *v28; // [rsp+F0h] [rbp-30h] BYREF
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
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = WaasMedic::TelemetryProvider::Provider();
    v7 = (__int64)v6;
    if ( *(_DWORD *)v6 > 5u )
    {
      v8 = *((_QWORD *)v6 + 3);
      if ( (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0 && (v8 & 0x400000000000LL) == v8 )
      {
        v9 = *((_QWORD *)this + 34);
        v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 15);
        v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
        v19 = v4[26];
        v25 = (const unsigned __int16 *)*((_QWORD *)v4 + 12);
        v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
        v20 = v4[20];
        v27 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
        v21 = v4[8];
        v28 = (const unsigned __int16 *)*((_QWORD *)v4 + 3);
        v22 = *v4;
        v29 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
        v16 = v4[16];
        v30 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
        LODWORD(SRWLock) = v4[2];
        v31 = 0x1000000;
        v18 = (PSRWLOCK)0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v7,
          (__int64)&word_14001983E,
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
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &v18);
    v10 = v18;
    **((_DWORD **)this + 34) = 2;
    if ( v10 )
      ReleaseSRWLockExclusive(v10);
    v11 = WaasMedic::TelemetryProvider::Provider();
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
        tlgWriteTransfer_EventWriteTransfer(v12, byte_140019969, v15 + 8, 0, 5, v32);
      }
    }
  }
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x1400090b0  mov     [rsp-8+arg_8], rbx
0x1400090b5  mov     [rsp-8+arg_10], rdi
0x1400090ba  push    rbp
0x1400090bb  lea     rbp, [rsp-50h]
0x1400090c0  sub     rsp, 170h
0x1400090c7  mov     rax, cs:__security_cookie
0x1400090ce  xor     rax, rsp
0x1400090d1  mov     [rbp+50h+var_10], rax
0x1400090d5  mov     rdi, [rcx+110h]
0x1400090dc  mov     rbx, rcx
0x1400090df  mov     eax, [rdi+48h]
0x1400090e2  test    eax, eax
0x1400090e4  jns     loc_140009290
0x1400090ea  add     rdi, 50h ; 'P'
0x1400090ee  cmp     eax, [rdi+8]
0x1400090f1  jnz     loc_140009290
0x1400090f7  test    rdi, rdi
0x1400090fa  jz      loc_140009290
0x140009100  lea     rdx, [rbp+50h+SRWLock]
0x140009104  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140009109  mov     rax, [rbx+110h]
0x140009110  mov     rcx, [rbp+50h+SRWLock]; SRWLock
0x140009114  mov     dword ptr [rax], 2
0x14000911a  test    rcx, rcx
0x14000911d  jz      short loc_140009125
0x14000911f  call    cs:__imp_ReleaseSRWLockExclusive
0x140009125  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x14000912a  mov     r9, rax
0x14000912d  mov     ecx, [rax]
0x14000912f  cmp     ecx, 5
0x140009132  jbe     loc_140009365
0x140009138  mov     rax, [rax+18h]
0x14000913c  mov     rdx, 400000000000h
0x140009146  mov     rcx, [r9+10h]
0x14000914a  test    rdx, rcx
0x14000914d  jz      loc_140009365
0x140009153  mov     rcx, rax
0x140009156  and     rcx, rdx
0x140009159  cmp     rcx, rax
0x14000915c  jnz     loc_140009365
0x140009162  mov     rax, [rdi+78h]
0x140009166  lea     rdx, word_14001983E
0x14000916d  mov     r8, [rbx+110h]
0x140009174  mov     rcx, r9
0x140009177  mov     [rbp+50h+var_A8], rax
0x14000917b  add     r8, 8
0x14000917f  mov     rax, [rdi+70h]
0x140009183  mov     [rbp+50h+var_A0], rax
0x140009187  mov     eax, [rdi+68h]
0x14000918a  mov     [rbp+50h+var_B8], eax
0x14000918d  mov     rax, [rdi+60h]
0x140009191  mov     [rbp+50h+var_98], rax
0x140009195  mov     rax, [rdi+58h]
0x140009199  mov     [rbp+50h+var_90], rax
0x14000919d  mov     eax, [rdi+50h]
0x1400091a0  mov     [rbp+50h+var_B4], eax
0x1400091a3  mov     rax, [rdi+48h]
0x1400091a7  mov     [rbp+50h+var_88], rax
0x1400091ab  mov     eax, [rdi+20h]
0x1400091ae  mov     [rbp+50h+var_B0], eax
0x1400091b1  mov     rax, [rdi+18h]
0x1400091b5  mov     [rbp+50h+var_80], rax
0x1400091b9  mov     eax, [rdi]
0x1400091bb  mov     [rbp+50h+var_AC], eax
0x1400091be  mov     rax, [rdi+80h]
0x1400091c5  mov     [rbp+50h+var_78], rax
0x1400091c9  mov     eax, [rdi+40h]
0x1400091cc  mov     [rbp+50h+var_D0], eax
0x1400091cf  mov     rax, [rdi+38h]
0x1400091d3  mov     [rbp+50h+var_70], rax
0x1400091d7  mov     eax, [rdi+8]
0x1400091da  mov     dword ptr [rbp+50h+SRWLock], eax
0x1400091dd  mov     eax, 1000000h
0x1400091e2  mov     [rbp+50h+var_68], rax
0x1400091e6  mov     [rbp+50h+var_C0], rax
0x1400091ea  lea     rax, [rbp+50h+var_A8]
0x1400091ee  mov     [rsp+170h+var_D8], rax
0x1400091f6  lea     rax, [rbp+50h+var_A0]
0x1400091fa  mov     [rsp+170h+var_E0], rax
0x140009202  lea     rax, [rbp+50h+var_B8]
0x140009206  mov     [rsp+170h+var_E8], rax
0x14000920e  lea     rax, [rbp+50h+var_98]
0x140009212  mov     [rsp+170h+var_F0], rax
0x14000921a  lea     rax, [rbp+50h+var_90]
0x14000921e  mov     [rsp+170h+var_F8], rax
0x140009223  lea     rax, [rbp+50h+var_B4]
0x140009227  mov     [rsp+170h+var_100], rax
0x14000922c  lea     rax, [rbp+50h+var_88]
0x140009230  mov     [rsp+170h+var_108], rax
0x140009235  lea     rax, [rbp+50h+var_B0]
0x140009239  mov     [rsp+170h+var_110], rax
0x14000923e  lea     rax, [rbp+50h+var_80]
0x140009242  mov     [rsp+170h+var_118], rax
0x140009247  lea     rax, [rbp+50h+var_AC]
0x14000924b  mov     [rsp+170h+var_120], rax
0x140009250  lea     rax, [rbp+50h+var_78]
0x140009254  mov     [rsp+170h+var_128], rax
0x140009259  lea     rax, [rbp+50h+var_D0]
0x14000925d  mov     [rsp+170h+var_130], rax
0x140009262  lea     rax, [rbp+50h+var_70]
0x140009266  mov     [rsp+170h+var_138], rax
0x14000926b  lea     rax, [rbp+50h+SRWLock]
0x14000926f  mov     [rsp+170h+var_140], rax
0x140009274  lea     rax, [rbp+50h+var_68]
0x140009278  mov     [rsp+170h+var_148], rax
0x14000927d  lea     rax, [rbp+50h+var_C0]
0x140009281  mov     [rsp+170h+var_150], rax
0x140009286  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000928b  jmp     loc_140009365
0x140009290  lea     rdx, [rbp+50h+var_C0]
0x140009294  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x140009299  mov     rax, [rbx+110h]
0x1400092a0  mov     rcx, [rbp+50h+var_C0]; SRWLock
0x1400092a4  mov     dword ptr [rax], 2
0x1400092aa  test    rcx, rcx
0x1400092ad  jz      short loc_1400092B5
0x1400092af  call    cs:__imp_ReleaseSRWLockExclusive
0x1400092b5  call    ?Provider@TelemetryProvider@WaasMedic@@SAPEBU_tlgProvider_t@@XZ; WaasMedic::TelemetryProvider::Provider(void)
0x1400092ba  mov     rdi, rax
0x1400092bd  mov     ecx, [rax]
0x1400092bf  cmp     ecx, 5
0x1400092c2  jbe     loc_140009365
0x1400092c8  mov     rax, [rax+18h]
0x1400092cc  mov     rdx, 400000000000h
0x1400092d6  mov     rcx, [rdi+10h]
0x1400092da  test    rdx, rcx
0x1400092dd  jz      loc_140009365
0x1400092e3  mov     rcx, rax
0x1400092e6  and     rcx, rdx
0x1400092e9  cmp     rcx, rax
0x1400092ec  jnz     short loc_140009365
0x1400092ee  call    cs:__imp_GetCurrentThreadId
0x1400092f4  mov     r8, [rbx+110h]
0x1400092fb  lea     rdx, byte_140019969
0x140009302  mov     dword ptr [rbp+50h+SRWLock], eax
0x140009305  xor     r9d, r9d
0x140009308  mov     rcx, rdi
0x14000930b  mov     [rbp+50h+var_18], 4
0x140009313  mov     [rbp+50h+var_28], 4
0x14000931b  mov     eax, [r8+48h]
0x14000931f  add     r8, 8
0x140009323  mov     [rbp+50h+var_D0], eax
0x140009326  mov     eax, 1000000h
0x14000932b  mov     [rbp+50h+var_C0], rax
0x14000932f  lea     rax, [rbp+50h+SRWLock]
0x140009333  mov     [rbp+50h+var_20], rax
0x140009337  lea     rax, [rbp+50h+var_D0]
0x14000933b  mov     [rbp+50h+var_30], rax
0x14000933f  lea     rax, [rbp+50h+var_C0]
0x140009343  mov     [rbp+50h+var_40], rax
0x140009347  lea     rax, [rbp+50h+var_60]
0x14000934b  mov     [rsp+170h+var_148], rax
0x140009350  mov     dword ptr [rsp+170h+var_150], 5
0x140009358  mov     [rbp+50h+var_38], 8
0x140009360  call    _tlgWriteTransfer_EventWriteTransfer
0x140009365  mov     rcx, rbx
0x140009368  call    ?IgnoreCurrentThread@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x14000936d  mov     rcx, [rbp+50h+var_10]
0x140009371  xor     rcx, rsp; StackCookie
0x140009374  call    __security_check_cookie
0x140009379  lea     r11, [rsp+170h+var_s0]
0x140009381  mov     rbx, [r11+18h]
0x140009385  mov     rdi, [r11+20h]
0x140009389  mov     rsp, r11
0x14000938c  pop     rbp
0x14000938d  retn
```
