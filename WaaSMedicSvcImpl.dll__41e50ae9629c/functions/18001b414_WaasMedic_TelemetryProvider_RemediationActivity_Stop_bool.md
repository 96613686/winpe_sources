# WaasMedic::TelemetryProvider::RemediationActivity::Stop(bool)

- ea: `0x18001b414`
- end: `0x18001b723`
- name: `?Stop@RemediationActivity@TelemetryProvider@WaasMedic@@QEAAX_N@Z`
- size: `783`
- prototype: `void __fastcall(WaasMedic::TelemetryProvider::RemediationActivity *__hidden this, bool)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180018d3c`

## callees

- `0x180001718`
- `0x180001b54`
- `0x1800050a0`
- `0x18000d04c`
- `0x180014ed4`
- `0x18001575c`
- `0x18001b414`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b483`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b628`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b483`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b628`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b673`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b673`

## pseudocode

```c
void __fastcall WaasMedic::TelemetryProvider::RemediationActivity::Stop(
        WaasMedic::TelemetryProvider::RemediationActivity *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  __int64 v6; // r9
  __int64 v7; // r8
  RTL_SRWLOCK *v8; // rcx
  __int64 v9; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v11; // r8
  int v12; // [rsp+B0h] [rbp-80h] BYREF
  DWORD v13; // [rsp+B4h] [rbp-7Ch] BYREF
  PSRWLOCK SRWLock; // [rsp+B8h] [rbp-78h] BYREF
  PSRWLOCK v15; // [rsp+C0h] [rbp-70h] BYREF
  int v16; // [rsp+C8h] [rbp-68h] BYREF
  int v17; // [rsp+CCh] [rbp-64h] BYREF
  int v18; // [rsp+D0h] [rbp-60h] BYREF
  int v19; // [rsp+D4h] [rbp-5Ch] BYREF
  __int64 v20; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v21; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v22; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v23; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v24; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v25; // [rsp+100h] [rbp-30h] BYREF
  __int64 v26; // [rsp+108h] [rbp-28h] BYREF
  __int64 v27; // [rsp+110h] [rbp-20h] BYREF
  __int64 v28; // [rsp+118h] [rbp-18h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v29; // [rsp+120h] [rbp-10h] BYREF
  PSRWLOCK *v30; // [rsp+140h] [rbp+10h]
  __int64 v31; // [rsp+148h] [rbp+18h]
  int *v32; // [rsp+150h] [rbp+20h]
  __int64 v33; // [rsp+158h] [rbp+28h]
  DWORD *v34; // [rsp+160h] [rbp+30h]
  __int64 v35; // [rsp+168h] [rbp+38h]
  PSRWLOCK *p_SRWLock; // [rsp+170h] [rbp+40h]
  __int64 v37; // [rsp+178h] [rbp+48h]

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v6 > 5u
      && (*(_QWORD *)(v6 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v6 + 24) & 0x400000000000LL) == *(_QWORD *)(v6 + 24) )
    {
      v20 = *((_QWORD *)v4 + 15);
      v7 = *((_QWORD *)this + 34);
      v21 = *((_QWORD *)v4 + 14);
      v17 = v4[26];
      v22 = *((_QWORD *)v4 + 12);
      v23 = *((_QWORD *)v4 + 11);
      v18 = v4[20];
      v24 = *((_QWORD *)v4 + 9);
      v19 = v4[8];
      v25 = *((_QWORD *)v4 + 3);
      v12 = *v4;
      v26 = *((_QWORD *)v4 + 16);
      v13 = v4[16];
      v27 = *((_QWORD *)v4 + 7);
      LODWORD(SRWLock) = v4[2];
      v28 = 0x1000000;
      v15 = (PSRWLOCK)0x1000000;
      v16 = 1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v6,
        (unsigned int)&unk_1800919AA,
        v7 + 8,
        v6,
        (__int64)&v15,
        (__int64)&v28,
        (__int64)&SRWLock,
        (__int64)&v27,
        (__int64)&v13,
        (__int64)&v26,
        (__int64)&v12,
        (__int64)&v25,
        (__int64)&v19,
        (__int64)&v24,
        (__int64)&v18,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v17,
        (__int64)&v21,
        (__int64)&v20,
        (__int64)&v16);
    }
  }
  else
  {
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v15);
    v8 = v15;
    **((_DWORD **)this + 34) = 2;
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
    v9 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v9 > 5u
      && (*(_QWORD *)(v9 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v9 + 24) & 0x400000000000LL) == *(_QWORD *)(v9 + 24) )
    {
      LODWORD(SRWLock) = 1;
      CurrentThreadId = GetCurrentThreadId();
      v11 = *((_QWORD *)this + 34);
      v13 = CurrentThreadId;
      v37 = 4;
      v35 = 4;
      v12 = *(_DWORD *)(v11 + 72);
      v15 = (PSRWLOCK)0x1000000;
      p_SRWLock = &SRWLock;
      v34 = &v13;
      v32 = &v12;
      v30 = &v15;
      v33 = 4;
      v31 = 8;
      tlgWriteTransfer_EventWriteTransfer(v9, byte_180091AE3, (const GUID *)(v11 + 8), 0, 6u, &v29);
    }
  }
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18001b414  mov     [rsp-8+arg_8], rbx
0x18001b419  mov     [rsp-8+arg_10], rdi
0x18001b41e  push    rbp
0x18001b41f  lea     rbp, [rsp-60h]
0x18001b424  sub     rsp, 190h
0x18001b42b  mov     rax, cs:__security_cookie
0x18001b432  xor     rax, rsp
0x18001b435  mov     [rbp+60h+var_10], rax
0x18001b439  mov     rdi, [rcx+110h]
0x18001b440  mov     rbx, rcx
0x18001b443  mov     eax, [rdi+48h]
0x18001b446  test    eax, eax
0x18001b448  jns     loc_18001B609
0x18001b44e  add     rdi, 50h ; 'P'
0x18001b452  cmp     eax, [rdi+8]
0x18001b455  jnz     loc_18001B609
0x18001b45b  test    rdi, rdi
0x18001b45e  jz      loc_18001B609
0x18001b464  lea     rdx, [rbp+60h+SRWLock]
0x18001b468  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001b46d  mov     rax, [rbx+110h]
0x18001b474  mov     rcx, [rbp+60h+SRWLock]; SRWLock
0x18001b478  mov     dword ptr [rax], 2
0x18001b47e  test    rcx, rcx
0x18001b481  jz      short loc_18001B489
0x18001b483  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b489  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18001b48e  mov     r9, [rax+8]
0x18001b492  mov     eax, [r9]
0x18001b495  cmp     eax, 5
0x18001b498  jbe     loc_18001B6FA
0x18001b49e  mov     rdx, [r9+18h]
0x18001b4a2  mov     rcx, 400000000000h
0x18001b4ac  mov     rax, [r9+10h]
0x18001b4b0  test    rcx, rax
0x18001b4b3  jz      loc_18001B6FA
0x18001b4b9  mov     rax, rdx
0x18001b4bc  and     rax, rcx
0x18001b4bf  cmp     rax, rdx
0x18001b4c2  jnz     loc_18001B6FA
0x18001b4c8  mov     rax, [rdi+78h]
0x18001b4cc  lea     rdx, unk_1800919AA
0x18001b4d3  mov     [rbp+60h+var_B8], rax
0x18001b4d7  mov     rcx, r9
0x18001b4da  mov     rax, [rdi+70h]
0x18001b4de  mov     r8, [rbx+110h]
0x18001b4e5  mov     [rbp+60h+var_B0], rax
0x18001b4e9  add     r8, 8
0x18001b4ed  mov     eax, [rdi+68h]
0x18001b4f0  mov     [rbp+60h+var_C4], eax
0x18001b4f3  mov     rax, [rdi+60h]
0x18001b4f7  mov     [rbp+60h+var_A8], rax
0x18001b4fb  mov     rax, [rdi+58h]
0x18001b4ff  mov     [rbp+60h+var_A0], rax
0x18001b503  mov     eax, [rdi+50h]
0x18001b506  mov     [rbp+60h+var_C0], eax
0x18001b509  mov     rax, [rdi+48h]
0x18001b50d  mov     [rbp+60h+var_98], rax
0x18001b511  mov     eax, [rdi+20h]
0x18001b514  mov     [rbp+60h+var_BC], eax
0x18001b517  mov     rax, [rdi+18h]
0x18001b51b  mov     [rbp+60h+var_90], rax
0x18001b51f  mov     eax, [rdi]
0x18001b521  mov     [rbp+60h+var_E0], eax
0x18001b524  mov     rax, [rdi+80h]
0x18001b52b  mov     [rbp+60h+var_88], rax
0x18001b52f  mov     eax, [rdi+40h]
0x18001b532  mov     [rbp+60h+var_DC], eax
0x18001b535  mov     rax, [rdi+38h]
0x18001b539  mov     [rbp+60h+var_80], rax
0x18001b53d  mov     eax, [rdi+8]
0x18001b540  mov     dword ptr [rbp+60h+SRWLock], eax
0x18001b543  mov     eax, 1000000h
0x18001b548  mov     [rbp+60h+var_78], rax
0x18001b54c  mov     [rbp+60h+var_D0], rax
0x18001b550  lea     rax, [rbp+60h+var_C8]
0x18001b554  mov     [rsp+190h+var_F0], rax
0x18001b55c  lea     rax, [rbp+60h+var_B8]
0x18001b560  mov     [rsp+190h+var_F8], rax
0x18001b568  lea     rax, [rbp+60h+var_B0]
0x18001b56c  mov     [rsp+190h+var_100], rax
0x18001b574  lea     rax, [rbp+60h+var_C4]
0x18001b578  mov     [rsp+190h+var_108], rax
0x18001b580  lea     rax, [rbp+60h+var_A8]
0x18001b584  mov     [rsp+190h+var_110], rax
0x18001b58c  lea     rax, [rbp+60h+var_A0]
0x18001b590  mov     [rsp+190h+var_118], rax
0x18001b595  lea     rax, [rbp+60h+var_C0]
0x18001b599  mov     [rsp+190h+var_120], rax
0x18001b59e  lea     rax, [rbp+60h+var_98]
0x18001b5a2  mov     [rsp+190h+var_128], rax
0x18001b5a7  lea     rax, [rbp+60h+var_BC]
0x18001b5ab  mov     [rsp+190h+var_130], rax
0x18001b5b0  lea     rax, [rbp+60h+var_90]
0x18001b5b4  mov     [rsp+190h+var_138], rax
0x18001b5b9  lea     rax, [rbp+60h+var_E0]
0x18001b5bd  mov     [rsp+190h+var_140], rax
0x18001b5c2  lea     rax, [rbp+60h+var_88]
0x18001b5c6  mov     [rsp+190h+var_148], rax
0x18001b5cb  lea     rax, [rbp+60h+var_DC]
0x18001b5cf  mov     [rsp+190h+var_150], rax
0x18001b5d4  lea     rax, [rbp+60h+var_80]
0x18001b5d8  mov     [rsp+190h+var_158], rax
0x18001b5dd  lea     rax, [rbp+60h+SRWLock]
0x18001b5e1  mov     [rsp+190h+var_160], rax
0x18001b5e6  lea     rax, [rbp+60h+var_78]
0x18001b5ea  mov     [rsp+190h+var_168], rax
0x18001b5ef  lea     rax, [rbp+60h+var_D0]
0x18001b5f3  mov     [rsp+190h+var_170], rax
0x18001b5f8  mov     [rbp+60h+var_C8], 1
0x18001b5ff  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18001b604  jmp     loc_18001B6FA
0x18001b609  lea     rdx, [rbp+60h+var_D0]
0x18001b60d  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001b612  mov     rax, [rbx+110h]
0x18001b619  mov     rcx, [rbp+60h+var_D0]; SRWLock
0x18001b61d  mov     dword ptr [rax], 2
0x18001b623  test    rcx, rcx
0x18001b626  jz      short loc_18001B62E
0x18001b628  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b62e  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18001b633  mov     rdi, [rax+8]
0x18001b637  mov     eax, [rdi]
0x18001b639  cmp     eax, 5
0x18001b63c  jbe     loc_18001B6FA
0x18001b642  mov     rdx, [rdi+18h]
0x18001b646  mov     rcx, 400000000000h
0x18001b650  mov     rax, [rdi+10h]
0x18001b654  test    rcx, rax
0x18001b657  jz      loc_18001B6FA
0x18001b65d  mov     rax, rdx
0x18001b660  and     rax, rcx
0x18001b663  cmp     rax, rdx
0x18001b666  jnz     loc_18001B6FA
0x18001b66c  mov     dword ptr [rbp+60h+SRWLock], 1
0x18001b673  call    cs:__imp_GetCurrentThreadId
0x18001b679  mov     r8, [rbx+110h]
0x18001b680  lea     rdx, byte_180091AE3
0x18001b687  mov     [rbp+60h+var_DC], eax
0x18001b68a  xor     r9d, r9d
0x18001b68d  mov     rcx, rdi
0x18001b690  mov     [rbp+60h+var_18], 4
0x18001b698  mov     [rbp+60h+var_28], 4
0x18001b6a0  mov     eax, [r8+48h]
0x18001b6a4  add     r8, 8
0x18001b6a8  mov     [rbp+60h+var_E0], eax
0x18001b6ab  mov     eax, 1000000h
0x18001b6b0  mov     [rbp+60h+var_D0], rax
0x18001b6b4  lea     rax, [rbp+60h+SRWLock]
0x18001b6b8  mov     [rbp+60h+var_20], rax
0x18001b6bc  lea     rax, [rbp+60h+var_DC]
0x18001b6c0  mov     [rbp+60h+var_30], rax
0x18001b6c4  lea     rax, [rbp+60h+var_E0]
0x18001b6c8  mov     [rbp+60h+var_40], rax
0x18001b6cc  lea     rax, [rbp+60h+var_D0]
0x18001b6d0  mov     [rbp+60h+var_50], rax
0x18001b6d4  lea     rax, [rbp+60h+var_70]
0x18001b6d8  mov     [rsp+190h+var_168], rax
0x18001b6dd  mov     dword ptr [rsp+190h+var_170], 6
0x18001b6e5  mov     [rbp+60h+var_38], 4
0x18001b6ed  mov     [rbp+60h+var_48], 8
0x18001b6f5  call    _tlgWriteTransfer_EventWriteTransfer
0x18001b6fa  mov     rcx, rbx
0x18001b6fd  call    ?IgnoreCurrentThread@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18001b702  mov     rcx, [rbp+60h+var_10]
0x18001b706  xor     rcx, rsp; StackCookie
0x18001b709  call    __security_check_cookie
0x18001b70e  lea     r11, [rsp+190h+var_s0]
0x18001b716  mov     rbx, [r11+18h]
0x18001b71a  mov     rdi, [r11+20h]
0x18001b71e  mov     rsp, r11
0x18001b721  pop     rbp
0x18001b722  retn
```
