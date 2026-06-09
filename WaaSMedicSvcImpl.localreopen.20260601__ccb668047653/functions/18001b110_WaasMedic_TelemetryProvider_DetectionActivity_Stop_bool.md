# WaasMedic::TelemetryProvider::DetectionActivity::Stop(bool)

- ea: `0x18001b110`
- end: `0x18001b40b`
- name: `?Stop@DetectionActivity@TelemetryProvider@WaasMedic@@QEAAX_N@Z`
- size: `763`
- prototype: `void __fastcall(WaasMedic::TelemetryProvider::DetectionActivity *__hidden this, bool)`
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
- `0x18001b110`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b17c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b31d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b17c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001b31d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b364`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b364`

## pseudocode

```c
void __fastcall WaasMedic::TelemetryProvider::DetectionActivity::Stop(
        WaasMedic::TelemetryProvider::DetectionActivity *this,
        unsigned __int8 a2)
{
  __int64 v2; // rdi
  int v4; // esi
  int v5; // eax
  int *v6; // rdi
  RTL_SRWLOCK *v7; // rcx
  __int64 v8; // r9
  __int64 v9; // r8
  RTL_SRWLOCK *v10; // rcx
  __int64 v11; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  int v14; // [rsp+B0h] [rbp-80h] BYREF
  DWORD v15; // [rsp+B4h] [rbp-7Ch] BYREF
  PSRWLOCK SRWLock; // [rsp+B8h] [rbp-78h] BYREF
  PSRWLOCK v17; // [rsp+C0h] [rbp-70h] BYREF
  int v18; // [rsp+C8h] [rbp-68h] BYREF
  int v19; // [rsp+CCh] [rbp-64h] BYREF
  int v20; // [rsp+D0h] [rbp-60h] BYREF
  int v21; // [rsp+D4h] [rbp-5Ch] BYREF
  __int64 v22; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v23; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v24; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v25; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v26; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v27; // [rsp+100h] [rbp-30h] BYREF
  __int64 v28; // [rsp+108h] [rbp-28h] BYREF
  __int64 v29; // [rsp+110h] [rbp-20h] BYREF
  __int64 v30; // [rsp+118h] [rbp-18h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v31; // [rsp+120h] [rbp-10h] BYREF
  PSRWLOCK *v32; // [rsp+140h] [rbp+10h]
  __int64 v33; // [rsp+148h] [rbp+18h]
  int *v34; // [rsp+150h] [rbp+20h]
  __int64 v35; // [rsp+158h] [rbp+28h]
  DWORD *v36; // [rsp+160h] [rbp+30h]
  __int64 v37; // [rsp+168h] [rbp+38h]
  PSRWLOCK *p_SRWLock; // [rsp+170h] [rbp+40h]
  __int64 v39; // [rsp+178h] [rbp+48h]

  v2 = *((_QWORD *)this + 34);
  v4 = a2;
  v5 = *(_DWORD *)(v2 + 72);
  if ( v5 < 0 && (v6 = (int *)(v2 + 80), v5 == v6[2]) && v6 )
  {
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v7 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v7 )
      ReleaseSRWLockExclusive(v7);
    v8 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v8 > 5u
      && (*(_QWORD *)(v8 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v8 + 24) & 0x400000000000LL) == *(_QWORD *)(v8 + 24) )
    {
      v22 = *((_QWORD *)v6 + 15);
      v9 = *((_QWORD *)this + 34);
      v23 = *((_QWORD *)v6 + 14);
      v19 = v6[26];
      v24 = *((_QWORD *)v6 + 12);
      v25 = *((_QWORD *)v6 + 11);
      v20 = v6[20];
      v26 = *((_QWORD *)v6 + 9);
      v21 = v6[8];
      v27 = *((_QWORD *)v6 + 3);
      v14 = *v6;
      v28 = *((_QWORD *)v6 + 16);
      v15 = v6[16];
      v29 = *((_QWORD *)v6 + 7);
      LODWORD(SRWLock) = v6[2];
      v30 = 0x1000000;
      v17 = (PSRWLOCK)0x1000000;
      v18 = v4;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v8,
        (unsigned int)&unk_180092000,
        v9 + 8,
        v8,
        (__int64)&v17,
        (__int64)&v30,
        (__int64)&SRWLock,
        (__int64)&v29,
        (__int64)&v15,
        (__int64)&v28,
        (__int64)&v14,
        (__int64)&v27,
        (__int64)&v21,
        (__int64)&v26,
        (__int64)&v20,
        (__int64)&v25,
        (__int64)&v24,
        (__int64)&v19,
        (__int64)&v23,
        (__int64)&v22,
        (__int64)&v18);
    }
  }
  else
  {
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &v17);
    v10 = v17;
    **((_DWORD **)this + 34) = 2;
    if ( v10 )
      ReleaseSRWLockExclusive(v10);
    v11 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v11 > 5u
      && (*(_QWORD *)(v11 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v11 + 24) & 0x400000000000LL) == *(_QWORD *)(v11 + 24) )
    {
      LODWORD(SRWLock) = v4;
      CurrentThreadId = GetCurrentThreadId();
      v13 = *((_QWORD *)this + 34);
      v15 = CurrentThreadId;
      v39 = 4;
      v37 = 4;
      v14 = *(_DWORD *)(v13 + 72);
      v17 = (PSRWLOCK)0x1000000;
      p_SRWLock = &SRWLock;
      v36 = &v15;
      v34 = &v14;
      v32 = &v17;
      v35 = 4;
      v33 = 8;
      tlgWriteTransfer_EventWriteTransfer(v11, (unsigned __int8 *)&unk_180092518, (const GUID *)(v13 + 8), 0, 6u, &v31);
    }
  }
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18001b110  push    rbp
0x18001b112  push    rbx
0x18001b113  push    rsi
0x18001b114  push    rdi
0x18001b115  lea     rbp, [rsp-68h]
0x18001b11a  sub     rsp, 198h
0x18001b121  mov     rax, cs:__security_cookie
0x18001b128  xor     rax, rsp
0x18001b12b  mov     [rbp+80h+var_30], rax
0x18001b12f  mov     rdi, [rcx+110h]
0x18001b136  mov     rbx, rcx
0x18001b139  movzx   esi, dl
0x18001b13c  mov     eax, [rdi+48h]
0x18001b13f  test    eax, eax
0x18001b141  jns     loc_18001B2FE
0x18001b147  add     rdi, 50h ; 'P'
0x18001b14b  cmp     eax, [rdi+8]
0x18001b14e  jnz     loc_18001B2FE
0x18001b154  test    rdi, rdi
0x18001b157  jz      loc_18001B2FE
0x18001b15d  lea     rdx, [rbp+80h+SRWLock]
0x18001b161  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001b166  mov     rax, [rbx+110h]
0x18001b16d  mov     rcx, [rbp+80h+SRWLock]; SRWLock
0x18001b171  mov     dword ptr [rax], 2
0x18001b177  test    rcx, rcx
0x18001b17a  jz      short loc_18001B182
0x18001b17c  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b182  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18001b187  mov     r9, [rax+8]
0x18001b18b  mov     eax, [r9]
0x18001b18e  cmp     eax, 5
0x18001b191  jbe     loc_18001B3EB
0x18001b197  mov     rdx, [r9+18h]
0x18001b19b  mov     rcx, 400000000000h
0x18001b1a5  mov     rax, [r9+10h]
0x18001b1a9  test    rcx, rax
0x18001b1ac  jz      loc_18001B3EB
0x18001b1b2  mov     rax, rdx
0x18001b1b5  and     rax, rcx
0x18001b1b8  cmp     rax, rdx
0x18001b1bb  jnz     loc_18001B3EB
0x18001b1c1  mov     rax, [rdi+78h]
0x18001b1c5  lea     rdx, unk_180092000
0x18001b1cc  mov     [rbp+80h+var_D8], rax
0x18001b1d0  mov     rcx, r9
0x18001b1d3  mov     rax, [rdi+70h]
0x18001b1d7  mov     r8, [rbx+110h]
0x18001b1de  mov     [rbp+80h+var_D0], rax
0x18001b1e2  add     r8, 8
0x18001b1e6  mov     eax, [rdi+68h]
0x18001b1e9  mov     [rbp+80h+var_E4], eax
0x18001b1ec  mov     rax, [rdi+60h]
0x18001b1f0  mov     [rbp+80h+var_C8], rax
0x18001b1f4  mov     rax, [rdi+58h]
0x18001b1f8  mov     [rbp+80h+var_C0], rax
0x18001b1fc  mov     eax, [rdi+50h]
0x18001b1ff  mov     [rbp+80h+var_E0], eax
0x18001b202  mov     rax, [rdi+48h]
0x18001b206  mov     [rbp+80h+var_B8], rax
0x18001b20a  mov     eax, [rdi+20h]
0x18001b20d  mov     [rbp+80h+var_DC], eax
0x18001b210  mov     rax, [rdi+18h]
0x18001b214  mov     [rbp+80h+var_B0], rax
0x18001b218  mov     eax, [rdi]
0x18001b21a  mov     [rbp+80h+var_100], eax
0x18001b21d  mov     rax, [rdi+80h]
0x18001b224  mov     [rbp+80h+var_A8], rax
0x18001b228  mov     eax, [rdi+40h]
0x18001b22b  mov     [rbp+80h+var_FC], eax
0x18001b22e  mov     rax, [rdi+38h]
0x18001b232  mov     [rbp+80h+var_A0], rax
0x18001b236  mov     eax, [rdi+8]
0x18001b239  mov     dword ptr [rbp+80h+SRWLock], eax
0x18001b23c  mov     eax, 1000000h
0x18001b241  mov     [rbp+80h+var_98], rax
0x18001b245  mov     [rbp+80h+var_F0], rax
0x18001b249  lea     rax, [rbp+80h+var_E8]
0x18001b24d  mov     [rsp+1B0h+var_110], rax
0x18001b255  lea     rax, [rbp+80h+var_D8]
0x18001b259  mov     [rsp+1B0h+var_118], rax
0x18001b261  lea     rax, [rbp+80h+var_D0]
0x18001b265  mov     [rsp+1B0h+var_120], rax
0x18001b26d  lea     rax, [rbp+80h+var_E4]
0x18001b271  mov     [rsp+1B0h+var_128], rax
0x18001b279  lea     rax, [rbp+80h+var_C8]
0x18001b27d  mov     [rsp+1B0h+var_130], rax
0x18001b285  lea     rax, [rbp+80h+var_C0]
0x18001b289  mov     [rsp+1B0h+var_138], rax
0x18001b28e  lea     rax, [rbp+80h+var_E0]
0x18001b292  mov     [rsp+1B0h+var_140], rax
0x18001b297  lea     rax, [rbp+80h+var_B8]
0x18001b29b  mov     [rsp+1B0h+var_148], rax
0x18001b2a0  lea     rax, [rbp+80h+var_DC]
0x18001b2a4  mov     [rsp+1B0h+var_150], rax
0x18001b2a9  lea     rax, [rbp+80h+var_B0]
0x18001b2ad  mov     [rsp+1B0h+var_158], rax
0x18001b2b2  lea     rax, [rbp+80h+var_100]
0x18001b2b6  mov     [rsp+1B0h+var_160], rax
0x18001b2bb  lea     rax, [rbp+80h+var_A8]
0x18001b2bf  mov     [rsp+1B0h+var_168], rax
0x18001b2c4  lea     rax, [rbp+80h+var_FC]
0x18001b2c8  mov     [rsp+1B0h+var_170], rax
0x18001b2cd  lea     rax, [rbp+80h+var_A0]
0x18001b2d1  mov     [rsp+1B0h+var_178], rax
0x18001b2d6  lea     rax, [rbp+80h+SRWLock]
0x18001b2da  mov     [rsp+1B0h+var_180], rax
0x18001b2df  lea     rax, [rbp+80h+var_98]
0x18001b2e3  mov     [rsp+1B0h+var_188], rax
0x18001b2e8  lea     rax, [rbp+80h+var_F0]
0x18001b2ec  mov     [rsp+1B0h+var_190], rax
0x18001b2f1  mov     [rbp+80h+var_E8], esi
0x18001b2f4  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564564@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18001b2f9  jmp     loc_18001B3EB
0x18001b2fe  lea     rdx, [rbp+80h+var_F0]
0x18001b302  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001b307  mov     rax, [rbx+110h]
0x18001b30e  mov     rcx, [rbp+80h+var_F0]; SRWLock
0x18001b312  mov     dword ptr [rax], 2
0x18001b318  test    rcx, rcx
0x18001b31b  jz      short loc_18001B323
0x18001b31d  call    cs:__imp_ReleaseSRWLockExclusive
0x18001b323  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18001b328  mov     rdi, [rax+8]
0x18001b32c  mov     eax, [rdi]
0x18001b32e  cmp     eax, 5
0x18001b331  jbe     loc_18001B3EB
0x18001b337  mov     rdx, [rdi+18h]
0x18001b33b  mov     rcx, 400000000000h
0x18001b345  mov     rax, [rdi+10h]
0x18001b349  test    rcx, rax
0x18001b34c  jz      loc_18001B3EB
0x18001b352  mov     rax, rdx
0x18001b355  and     rax, rcx
0x18001b358  cmp     rax, rdx
0x18001b35b  jnz     loc_18001B3EB
0x18001b361  mov     dword ptr [rbp+80h+SRWLock], esi
0x18001b364  call    cs:__imp_GetCurrentThreadId
0x18001b36a  mov     r8, [rbx+110h]
0x18001b371  lea     rdx, unk_180092518
0x18001b378  mov     [rbp+80h+var_FC], eax
0x18001b37b  xor     r9d, r9d
0x18001b37e  mov     rcx, rdi
0x18001b381  mov     [rbp+80h+var_38], 4
0x18001b389  mov     [rbp+80h+var_48], 4
0x18001b391  mov     eax, [r8+48h]
0x18001b395  add     r8, 8
0x18001b399  mov     [rbp+80h+var_100], eax
0x18001b39c  mov     eax, 1000000h
0x18001b3a1  mov     [rbp+80h+var_F0], rax
0x18001b3a5  lea     rax, [rbp+80h+SRWLock]
0x18001b3a9  mov     [rbp+80h+var_40], rax
0x18001b3ad  lea     rax, [rbp+80h+var_FC]
0x18001b3b1  mov     [rbp+80h+var_50], rax
0x18001b3b5  lea     rax, [rbp+80h+var_100]
0x18001b3b9  mov     [rbp+80h+var_60], rax
0x18001b3bd  lea     rax, [rbp+80h+var_F0]
0x18001b3c1  mov     [rbp+80h+var_70], rax
0x18001b3c5  lea     rax, [rbp+80h+var_90]
0x18001b3c9  mov     [rsp+1B0h+var_188], rax
0x18001b3ce  mov     dword ptr [rsp+1B0h+var_190], 6
0x18001b3d6  mov     [rbp+80h+var_58], 4
0x18001b3de  mov     [rbp+80h+var_68], 8
0x18001b3e6  call    _tlgWriteTransfer_EventWriteTransfer
0x18001b3eb  mov     rcx, rbx
0x18001b3ee  call    ?IgnoreCurrentThread@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x18001b3f3  mov     rcx, [rbp+80h+var_30]
0x18001b3f7  xor     rcx, rsp; StackCookie
0x18001b3fa  call    __security_check_cookie
0x18001b3ff  add     rsp, 198h
0x18001b406  pop     rdi
0x18001b407  pop     rsi
0x18001b408  pop     rbx
0x18001b409  pop     rbp
0x18001b40a  retn
```
