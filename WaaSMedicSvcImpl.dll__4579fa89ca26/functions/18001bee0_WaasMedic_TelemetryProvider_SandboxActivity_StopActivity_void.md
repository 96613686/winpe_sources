# WaasMedic::TelemetryProvider::SandboxActivity::StopActivity(void)

- ea: `0x18001bee0`
- end: `0x18001c164`
- name: `?StopActivity@SandboxActivity@TelemetryProvider@WaasMedic@@MEAAXXZ`
- size: `644`
- prototype: `void __fastcall(WaasMedic::TelemetryProvider::SandboxActivity *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update`

## callees

- `0x180001008`
- `0x180001e18`
- `0x18000d04c`
- `0x180014ed4`
- `0x18001575c`
- `0x18001bee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bf3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c0cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001bf3a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001c0cc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c104`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c104`

## pseudocode

```c
void __fastcall WaasMedic::TelemetryProvider::SandboxActivity::StopActivity(
        WaasMedic::TelemetryProvider::SandboxActivity *this)
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
  int v26; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v27; // [rsp+130h] [rbp+77h] BYREF
  int v28; // [rsp+138h] [rbp+7Fh] BYREF

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
      v7 = *((_QWORD *)this + 34);
      v15 = *((_QWORD *)v4 + 15);
      v16 = *((_QWORD *)v4 + 14);
      LODWORD(SRWLock) = v4[26];
      v17 = *((_QWORD *)v4 + 12);
      v18 = *((_QWORD *)v4 + 11);
      v26 = v4[20];
      v19 = *((_QWORD *)v4 + 9);
      LODWORD(v27) = v4[8];
      v20 = *((_QWORD *)v4 + 3);
      v28 = *v4;
      v21 = *((_QWORD *)v4 + 16);
      v13 = v4[16];
      v22 = *((_QWORD *)v4 + 7);
      v14 = v4[2];
      v23 = 0x1000000;
      v24[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
        v6,
        (unsigned int)byte_180091B45,
        v7 + 8,
        v6,
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
    wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      this,
      &SRWLock);
    v8 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
    v9 = *((_QWORD *)WaasMedic::TelemetryProvider::Instance() + 1);
    if ( *(_DWORD *)v9 > 5u
      && (*(_QWORD *)(v9 + 16) & 0x400000000000LL) != 0
      && (*(_QWORD *)(v9 + 24) & 0x400000000000LL) == *(_QWORD *)(v9 + 24) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v11 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v26 = *(_DWORD *)(v11 + 72);
      v27 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v9,
        (unsigned int)&dword_180091F0C,
        v11 + 8,
        v12,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x18001bee0  push    rbp
0x18001bee2  push    rbx
0x18001bee3  push    rdi
0x18001bee4  lea     rbp, [rsp-47h]
0x18001bee9  sub     rsp, 100h
0x18001bef0  mov     rdi, [rcx+110h]
0x18001bef7  mov     rbx, rcx
0x18001befa  mov     eax, [rdi+48h]
0x18001befd  test    eax, eax
0x18001beff  jns     loc_18001C0AD
0x18001bf05  add     rdi, 50h ; 'P'
0x18001bf09  cmp     eax, [rdi+8]
0x18001bf0c  jnz     loc_18001C0AD
0x18001bf12  test    rdi, rdi
0x18001bf15  jz      loc_18001C0AD
0x18001bf1b  lea     rdx, [rbp+57h+SRWLock]
0x18001bf1f  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001bf24  mov     rax, [rbx+110h]
0x18001bf2b  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001bf2f  mov     dword ptr [rax], 2
0x18001bf35  test    rcx, rcx
0x18001bf38  jz      short loc_18001BF40
0x18001bf3a  call    cs:__imp_ReleaseSRWLockExclusive
0x18001bf40  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18001bf45  mov     r9, [rax+8]
0x18001bf49  mov     eax, [r9]
0x18001bf4c  cmp     eax, 5
0x18001bf4f  jbe     loc_18001C152
0x18001bf55  mov     rdx, [r9+18h]
0x18001bf59  mov     rcx, 400000000000h
0x18001bf63  mov     rax, [r9+10h]
0x18001bf67  test    rcx, rax
0x18001bf6a  jz      loc_18001C152
0x18001bf70  mov     rax, rdx
0x18001bf73  and     rax, rcx
0x18001bf76  cmp     rax, rdx
0x18001bf79  jnz     loc_18001C152
0x18001bf7f  mov     rax, [rdi+78h]
0x18001bf83  lea     rdx, byte_180091B45
0x18001bf8a  mov     r8, [rbx+110h]
0x18001bf91  mov     rcx, r9
0x18001bf94  mov     [rbp+57h+var_68], rax
0x18001bf98  add     r8, 8
0x18001bf9c  mov     rax, [rdi+70h]
0x18001bfa0  mov     [rbp+57h+var_60], rax
0x18001bfa4  mov     eax, [rdi+68h]
0x18001bfa7  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001bfaa  mov     rax, [rdi+60h]
0x18001bfae  mov     [rbp+57h+var_58], rax
0x18001bfb2  mov     rax, [rdi+58h]
0x18001bfb6  mov     [rbp+57h+var_50], rax
0x18001bfba  mov     eax, [rdi+50h]
0x18001bfbd  mov     [rbp+57h+arg_8], eax
0x18001bfc0  mov     rax, [rdi+48h]
0x18001bfc4  mov     [rbp+57h+var_48], rax
0x18001bfc8  mov     eax, [rdi+20h]
0x18001bfcb  mov     dword ptr [rbp+57h+arg_10], eax
0x18001bfce  mov     rax, [rdi+18h]
0x18001bfd2  mov     [rbp+57h+var_40], rax
0x18001bfd6  mov     eax, [rdi]
0x18001bfd8  mov     [rbp+57h+arg_18], eax
0x18001bfdb  mov     rax, [rdi+80h]
0x18001bfe2  mov     [rbp+57h+var_38], rax
0x18001bfe6  mov     eax, [rdi+40h]
0x18001bfe9  mov     [rbp+57h+var_70], eax
0x18001bfec  mov     rax, [rdi+38h]
0x18001bff0  mov     [rbp+57h+var_30], rax
0x18001bff4  mov     eax, [rdi+8]
0x18001bff7  mov     [rbp+57h+var_6C], eax
0x18001bffa  mov     eax, 1000000h
0x18001bfff  mov     [rbp+57h+var_28], rax
0x18001c003  mov     [rbp+57h+var_20], rax
0x18001c007  lea     rax, [rbp+57h+var_68]
0x18001c00b  mov     [rsp+110h+var_78], rax
0x18001c013  lea     rax, [rbp+57h+var_60]
0x18001c017  mov     [rsp+110h+var_80], rax
0x18001c01f  lea     rax, [rbp+57h+SRWLock]
0x18001c023  mov     [rsp+110h+var_88], rax
0x18001c02b  lea     rax, [rbp+57h+var_58]
0x18001c02f  mov     [rsp+110h+var_90], rax
0x18001c037  lea     rax, [rbp+57h+var_50]
0x18001c03b  mov     [rsp+110h+var_98], rax
0x18001c040  lea     rax, [rbp+57h+arg_8]
0x18001c044  mov     [rsp+110h+var_A0], rax
0x18001c049  lea     rax, [rbp+57h+var_48]
0x18001c04d  mov     [rsp+110h+var_A8], rax
0x18001c052  lea     rax, [rbp+57h+arg_10]
0x18001c056  mov     [rsp+110h+var_B0], rax
0x18001c05b  lea     rax, [rbp+57h+var_40]
0x18001c05f  mov     [rsp+110h+var_B8], rax
0x18001c064  lea     rax, [rbp+57h+arg_18]
0x18001c068  mov     [rsp+110h+var_C0], rax
0x18001c06d  lea     rax, [rbp+57h+var_38]
0x18001c071  mov     [rsp+110h+var_C8], rax
0x18001c076  lea     rax, [rbp+57h+var_70]
0x18001c07a  mov     [rsp+110h+var_D0], rax
0x18001c07f  lea     rax, [rbp+57h+var_30]
0x18001c083  mov     [rsp+110h+var_D8], rax
0x18001c088  lea     rax, [rbp+57h+var_6C]
0x18001c08c  mov     [rsp+110h+var_E0], rax
0x18001c091  lea     rax, [rbp+57h+var_28]
0x18001c095  mov     [rsp+110h+var_E8], rax
0x18001c09a  lea     rax, [rbp+57h+var_20]
0x18001c09e  mov     [rsp+110h+var_F0], rax
0x18001c0a3  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18001c0a8  jmp     loc_18001C152
0x18001c0ad  lea     rdx, [rbp+57h+SRWLock]
0x18001c0b1  call    ?LockExclusive@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18001c0b6  mov     rax, [rbx+110h]
0x18001c0bd  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001c0c1  mov     dword ptr [rax], 2
0x18001c0c7  test    rcx, rcx
0x18001c0ca  jz      short loc_18001C0D2
0x18001c0cc  call    cs:__imp_ReleaseSRWLockExclusive
0x18001c0d2  call    ?Instance@TelemetryProvider@WaasMedic@@KAPEAV12@XZ; WaasMedic::TelemetryProvider::Instance(void)
0x18001c0d7  mov     rdi, [rax+8]
0x18001c0db  mov     eax, [rdi]
0x18001c0dd  cmp     eax, 5
0x18001c0e0  jbe     short loc_18001C152
0x18001c0e2  mov     rdx, [rdi+18h]
0x18001c0e6  mov     rcx, 400000000000h
0x18001c0f0  mov     rax, [rdi+10h]
0x18001c0f4  test    rcx, rax
0x18001c0f7  jz      short loc_18001C152
0x18001c0f9  mov     rax, rdx
0x18001c0fc  and     rax, rcx
0x18001c0ff  cmp     rax, rdx
0x18001c102  jnz     short loc_18001C152
0x18001c104  call    cs:__imp_GetCurrentThreadId
0x18001c10a  mov     r8, [rbx+110h]
0x18001c111  lea     rdx, dword_180091F0C
0x18001c118  mov     dword ptr [rbp+57h+SRWLock], eax
0x18001c11b  mov     rcx, rdi
0x18001c11e  mov     eax, [r8+48h]
0x18001c122  add     r8, 8
0x18001c126  mov     [rbp+57h+arg_8], eax
0x18001c129  mov     eax, 1000000h
0x18001c12e  mov     [rbp+57h+arg_10], rax
0x18001c132  lea     rax, [rbp+57h+SRWLock]
0x18001c136  mov     [rsp+110h+var_E0], rax
0x18001c13b  lea     rax, [rbp+57h+arg_8]
0x18001c13f  mov     [rsp+110h+var_E8], rax
0x18001c144  lea     rax, [rbp+57h+arg_10]
0x18001c148  mov     [rsp+110h+var_F0], rax
0x18001c14d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001c152  mov     rcx, rbx
0x18001c155  add     rsp, 100h
0x18001c15c  pop     rdi
0x18001c15d  pop     rbx
0x18001c15e  pop     rbp
0x18001c15f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VTelemetryProvider@WaasMedic@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<WaasMedic::TelemetryProvider,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
