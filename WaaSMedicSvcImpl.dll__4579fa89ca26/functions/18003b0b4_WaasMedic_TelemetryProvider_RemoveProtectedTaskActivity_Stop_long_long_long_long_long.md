# WaasMedic::TelemetryProvider::RemoveProtectedTaskActivity::Stop(long,long,long,long,long)

- ea: `0x18003b0b4`
- end: `0x18003b3ee`
- name: `?Stop@RemoveProtectedTaskActivity@TelemetryProvider@WaasMedic@@QEAAXJJJJJ@Z`
- size: `826`
- prototype: `void __fastcall(WaasMedic::TelemetryProvider::RemoveProtectedTaskActivity *__hidden this, int, int, int, int, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update`

## callers

- `0x18003a7d0`

## callees

- `0x180003178`
- `0x1800034a0`
- `0x18000d04c`
- `0x180014ed4`
- `0x18001575c`
- `0x18003b0b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b11c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b301`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b11c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18003b301`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b35c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b35c`

## pseudocode

```c
void __fastcall WaasMedic::TelemetryProvider::RemoveProtectedTaskActivity::Stop(
        WaasMedic::TelemetryProvider::RemoveProtectedTaskActivity *this,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6)
{
  __int64 v6; // rdi
  int v11; // eax
  int *v12; // rdi
  RTL_SRWLOCK *v13; // rcx
  __int64 v14; // r9
  __int64 v15; // r8
  RTL_SRWLOCK *v16; // rcx
  __int64 v17; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v19; // r8
  int v20; // r9d
  int v21; // [rsp+D0h] [rbp-80h] BYREF
  DWORD v22; // [rsp+D4h] [rbp-7Ch] BYREF
  int v23; // [rsp+D8h] [rbp-78h] BYREF
  int v24; // [rsp+DCh] [rbp-74h] BYREF
  int v25; // [rsp+E0h] [rbp-70h] BYREF
  int v26; // [rsp+E4h] [rbp-6Ch] BYREF
  int v27; // [rsp+E8h] [rbp-68h] BYREF
  int v28; // [rsp+ECh] [rbp-64h] BYREF
  int v29; // [rsp+F0h] [rbp-60h] BYREF
  int v30; // [rsp+F4h] [rbp-5Ch] BYREF
  __int64 v31; // [rsp+F8h] [rbp-58h] BYREF
  __int64 v32; // [rsp+100h] [rbp-50h] BYREF
  __int64 v33; // [rsp+108h] [rbp-48h] BYREF
  __int64 v34; // [rsp+110h] [rbp-40h] BYREF
  __int64 v35; // [rsp+118h] [rbp-38h] BYREF
  __int64 v36; // [rsp+120h] [rbp-30h] BYREF
  __int64 v37; // [rsp+128h] [rbp-28h] BYREF
  __int64 v38; // [rsp+130h] [rbp-20h] BYREF
  __int64 v39; // [rsp+138h] [rbp-18h] BYREF
  __int64 v40[8]; // [rsp+140h] [rbp-10h] BYREF
  PSRWLOCK SRWLock; // [rsp+190h] [rbp+40h] BYREF

  v6 = *((_QWORD *)this + 34);
  v11 = *(_DWORD *)(v6 + 72);
  if ( v11 < 0 && (v12 = (int *)(v6 + 80), v11 == v12[2]) && v12 )
  {
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v13 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v13 )
      ReleaseSRWLockExclusive(v13);
    v14 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v14 > 5u
      && (*(_QWORD *)(v14 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v14 + 24) & 0x200000000000LL) == *(_QWORD *)(v14 + 24) )
    {
      LODWORD(SRWLock) = a6;
      v27 = a5;
      v32 = *((_QWORD *)v12 + 15);
      v33 = *((_QWORD *)v12 + 14);
      v21 = v12[26];
      v34 = *((_QWORD *)v12 + 12);
      v35 = *((_QWORD *)v12 + 11);
      v15 = *((_QWORD *)this + 34);
      v22 = v12[20];
      v36 = *((_QWORD *)v12 + 9);
      v23 = v12[8];
      v37 = *((_QWORD *)v12 + 3);
      v24 = *v12;
      v38 = *((_QWORD *)v12 + 16);
      v25 = v12[16];
      v39 = *((_QWORD *)v12 + 7);
      v26 = v12[2];
      v40[0] = 0x1000000;
      v31 = 0x1000000;
      v28 = a4;
      v29 = a3;
      v30 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v14,
        (unsigned int)byte_180094025,
        v15 + 8,
        v14,
        (__int64)&v31,
        (__int64)v40,
        (__int64)&v26,
        (__int64)&v39,
        (__int64)&v25,
        (__int64)&v38,
        (__int64)&v24,
        (__int64)&v37,
        (__int64)&v23,
        (__int64)&v36,
        (__int64)&v22,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v21,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v28,
        (__int64)&v27,
        (__int64)&SRWLock);
    }
  }
  else
  {
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v16 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v16 )
      ReleaseSRWLockExclusive(v16);
    v17 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v17 > 5u
      && (*(_QWORD *)(v17 + 16) & 0x200000000000LL) != 0
      && (*(_QWORD *)(v17 + 24) & 0x200000000000LL) == *(_QWORD *)(v17 + 24) )
    {
      LODWORD(SRWLock) = a6;
      v26 = a5;
      v25 = a4;
      v24 = a3;
      v23 = a2;
      CurrentThreadId = GetCurrentThreadId();
      v19 = *((_QWORD *)this + 34);
      v22 = CurrentThreadId;
      v21 = *(_DWORD *)(v19 + 72);
      v31 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v17,
        (unsigned int)byte_1800941E9,
        v19 + 8,
        v20,
        (__int64)&v31,
        (__int64)&v21,
        (__int64)&v22,
        (__int64)&v23,
        (__int64)&v24,
        (__int64)&v25,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18003b0b4  push    rbp
0x18003b0b6  push    rbx
0x18003b0b7  push    rsi
0x18003b0b8  push    rdi
0x18003b0b9  push    r14
0x18003b0bb  push    r15
0x18003b0bd  lea     rbp, [rsp-8]
0x18003b0c2  sub     rsp, 158h
0x18003b0c9  mov     rdi, [rcx+110h]
0x18003b0d0  mov     esi, r9d
0x18003b0d3  mov     r14d, r8d
0x18003b0d6  mov     r15d, edx
0x18003b0d9  mov     rbx, rcx
0x18003b0dc  mov     eax, [rdi+48h]
0x18003b0df  test    eax, eax
0x18003b0e1  jns     loc_18003B2E2
0x18003b0e7  add     rdi, 50h ; 'P'
0x18003b0eb  cmp     eax, [rdi+8]
0x18003b0ee  jnz     loc_18003B2E2
0x18003b0f4  test    rdi, rdi
0x18003b0f7  jz      loc_18003B2E2
0x18003b0fd  lea     rdx, [rbp+30h+SRWLock]
0x18003b101  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003b106  mov     rax, [rbx+110h]
0x18003b10d  mov     rcx, [rbp+30h+SRWLock]; SRWLock
0x18003b111  mov     dword ptr [rax], 2
0x18003b117  test    rcx, rcx
0x18003b11a  jz      short loc_18003B122
0x18003b11c  call    cs:__imp_ReleaseSRWLockExclusive
0x18003b122  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18003b127  mov     r9, [rax+8]
0x18003b12b  mov     eax, [r9]
0x18003b12e  cmp     eax, 5
0x18003b131  jbe     loc_18003B3D7
0x18003b137  mov     rdx, [r9+18h]
0x18003b13b  mov     rcx, 200000000000h
0x18003b145  mov     rax, [r9+10h]
0x18003b149  test    rcx, rax
0x18003b14c  jz      loc_18003B3D7
0x18003b152  mov     rax, rdx
0x18003b155  and     rax, rcx
0x18003b158  cmp     rax, rdx
0x18003b15b  jnz     loc_18003B3D7
0x18003b161  mov     eax, [rbp+30h+arg_28]
0x18003b164  mov     dword ptr [rbp+30h+SRWLock], eax
0x18003b167  mov     eax, [rbp+30h+arg_20]
0x18003b16a  mov     [rbp+30h+var_98], eax
0x18003b16d  mov     rax, [rdi+78h]
0x18003b171  mov     [rbp+30h+var_80], rax
0x18003b175  mov     rax, [rdi+70h]
0x18003b179  mov     [rbp+30h+var_78], rax
0x18003b17d  mov     eax, [rdi+68h]
0x18003b180  mov     [rbp+30h+var_B0], eax
0x18003b183  mov     rax, [rdi+60h]
0x18003b187  mov     [rbp+30h+var_70], rax
0x18003b18b  mov     rax, [rdi+58h]
0x18003b18f  mov     [rbp+30h+var_68], rax
0x18003b193  mov     eax, [rdi+50h]
0x18003b196  mov     r8, [rbx+110h]
0x18003b19d  mov     [rbp+30h+var_AC], eax
0x18003b1a0  add     r8, 8
0x18003b1a4  mov     rax, [rdi+48h]
0x18003b1a8  mov     [rbp+30h+var_60], rax
0x18003b1ac  mov     eax, [rdi+20h]
0x18003b1af  mov     [rbp+30h+var_A8], eax
0x18003b1b2  mov     rax, [rdi+18h]
0x18003b1b6  mov     [rbp+30h+var_58], rax
0x18003b1ba  mov     eax, [rdi]
0x18003b1bc  mov     [rbp+30h+var_A4], eax
0x18003b1bf  mov     rax, [rdi+80h]
0x18003b1c6  mov     [rbp+30h+var_50], rax
0x18003b1ca  mov     eax, [rdi+40h]
0x18003b1cd  mov     [rbp+30h+var_A0], eax
0x18003b1d0  mov     rax, [rdi+38h]
0x18003b1d4  mov     [rbp+30h+var_48], rax
0x18003b1d8  mov     eax, [rdi+8]
0x18003b1db  mov     [rbp+30h+var_9C], eax
0x18003b1de  mov     eax, 1000000h
0x18003b1e3  mov     [rbp+30h+var_40], rax
0x18003b1e7  mov     [rbp+30h+var_88], rax
0x18003b1eb  lea     rax, [rbp+30h+SRWLock]
0x18003b1ef  mov     [rsp+180h+var_C0], rax
0x18003b1f7  lea     rax, [rbp+30h+var_98]
0x18003b1fb  mov     [rsp+180h+var_C8], rax
0x18003b203  lea     rax, [rbp+30h+var_94]
0x18003b207  mov     [rsp+180h+var_D0], rax
0x18003b20f  lea     rax, [rbp+30h+var_90]
0x18003b213  mov     [rsp+180h+var_D8], rax
0x18003b21b  lea     rax, [rbp+30h+var_8C]
0x18003b21f  mov     [rsp+180h+var_E0], rax
0x18003b227  lea     rax, [rbp+30h+var_80]
0x18003b22b  mov     [rsp+180h+var_E8], rax
0x18003b233  lea     rax, [rbp+30h+var_78]
0x18003b237  mov     [rsp+180h+var_F0], rax
0x18003b23f  lea     rax, [rbp+30h+var_B0]
0x18003b243  mov     [rsp+180h+var_F8], rax
0x18003b24b  lea     rax, [rbp+30h+var_70]
0x18003b24f  mov     [rsp+180h+var_100], rax
0x18003b257  lea     rax, [rbp+30h+var_68]
0x18003b25b  mov     [rsp+180h+var_108], rax
0x18003b260  lea     rax, [rbp+30h+var_AC]
0x18003b264  mov     [rsp+180h+var_110], rax
0x18003b269  lea     rax, [rbp+30h+var_60]
0x18003b26d  mov     [rsp+180h+var_118], rax
0x18003b272  lea     rax, [rbp+30h+var_A8]
0x18003b276  mov     [rsp+180h+var_120], rax
0x18003b27b  lea     rax, [rbp+30h+var_58]
0x18003b27f  mov     [rsp+180h+var_128], rax
0x18003b284  lea     rax, [rbp+30h+var_A4]
0x18003b288  mov     [rsp+180h+var_130], rax
0x18003b28d  lea     rax, [rbp+30h+var_50]
0x18003b291  mov     [rsp+180h+var_138], rax
0x18003b296  lea     rax, [rbp+30h+var_A0]
0x18003b29a  mov     [rsp+180h+var_140], rax
0x18003b29f  lea     rax, [rbp+30h+var_48]
0x18003b2a3  mov     [rsp+180h+var_148], rax
0x18003b2a8  lea     rax, [rbp+30h+var_9C]
0x18003b2ac  mov     [rsp+180h+var_150], rax
0x18003b2b1  lea     rax, [rbp+30h+var_40]
0x18003b2b5  mov     [rsp+180h+var_158], rax
0x18003b2ba  lea     rax, [rbp+30h+var_88]
0x18003b2be  mov     [rbp+30h+var_94], esi
0x18003b2c1  mov     [rbp+30h+var_90], r14d
0x18003b2c5  mov     [rbp+30h+var_8C], r15d
0x18003b2c9  lea     rdx, byte_180094025
0x18003b2d0  mov     [rsp+180h+var_160], rax
0x18003b2d5  mov     rcx, r9
0x18003b2d8  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@4545645644444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003b2dd  jmp     loc_18003B3D7
0x18003b2e2  lea     rdx, [rbp+30h+SRWLock]
0x18003b2e6  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18003b2eb  mov     rax, [rbx+110h]
0x18003b2f2  mov     rcx, [rbp+30h+SRWLock]; SRWLock
0x18003b2f6  mov     dword ptr [rax], 2
0x18003b2fc  test    rcx, rcx
0x18003b2ff  jz      short loc_18003B307
0x18003b301  call    cs:__imp_ReleaseSRWLockExclusive
0x18003b307  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18003b30c  mov     rdi, [rax+8]
0x18003b310  mov     eax, [rdi]
0x18003b312  cmp     eax, 5
0x18003b315  jbe     loc_18003B3D7
0x18003b31b  mov     rdx, [rdi+18h]
0x18003b31f  mov     rcx, 200000000000h
0x18003b329  mov     rax, [rdi+10h]
0x18003b32d  test    rcx, rax
0x18003b330  jz      loc_18003B3D7
0x18003b336  mov     rax, rdx
0x18003b339  and     rax, rcx
0x18003b33c  cmp     rax, rdx
0x18003b33f  jnz     loc_18003B3D7
0x18003b345  mov     eax, [rbp+30h+arg_28]
0x18003b348  mov     dword ptr [rbp+30h+SRWLock], eax
0x18003b34b  mov     eax, [rbp+30h+arg_20]
0x18003b34e  mov     [rbp+30h+var_9C], eax
0x18003b351  mov     [rbp+30h+var_A0], esi
0x18003b354  mov     [rbp+30h+var_A4], r14d
0x18003b358  mov     [rbp+30h+var_A8], r15d
0x18003b35c  call    cs:__imp_GetCurrentThreadId
0x18003b362  mov     r8, [rbx+110h]
0x18003b369  lea     rdx, byte_1800941E9
0x18003b370  mov     [rbp+30h+var_AC], eax
0x18003b373  mov     rcx, rdi
0x18003b376  mov     eax, [r8+48h]
0x18003b37a  add     r8, 8
0x18003b37e  mov     [rbp+30h+var_B0], eax
0x18003b381  mov     eax, 1000000h
0x18003b386  mov     [rbp+30h+var_88], rax
0x18003b38a  lea     rax, [rbp+30h+SRWLock]
0x18003b38e  mov     [rsp+180h+var_128], rax
0x18003b393  lea     rax, [rbp+30h+var_9C]
0x18003b397  mov     [rsp+180h+var_130], rax
0x18003b39c  lea     rax, [rbp+30h+var_A0]
0x18003b3a0  mov     [rsp+180h+var_138], rax
0x18003b3a5  lea     rax, [rbp+30h+var_A4]
0x18003b3a9  mov     [rsp+180h+var_140], rax
0x18003b3ae  lea     rax, [rbp+30h+var_A8]
0x18003b3b2  mov     [rsp+180h+var_148], rax
0x18003b3b7  lea     rax, [rbp+30h+var_AC]
0x18003b3bb  mov     [rsp+180h+var_150], rax
0x18003b3c0  lea     rax, [rbp+30h+var_B0]
0x18003b3c4  mov     [rsp+180h+var_158], rax
0x18003b3c9  lea     rax, [rbp+30h+var_88]
0x18003b3cd  mov     [rsp+180h+var_160], rax
0x18003b3d2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003b3d7  mov     rcx, rbx
0x18003b3da  add     rsp, 158h
0x18003b3e1  pop     r15
0x18003b3e3  pop     r14
0x18003b3e5  pop     rdi
0x18003b3e6  pop     rsi
0x18003b3e7  pop     rbx
0x18003b3e8  pop     rbp
0x18003b3e9  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
