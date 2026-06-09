# wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(wil::FailureInfo const &)

- ea: `0x18002b8a0`
- end: `0x18002bc0c`
- name: `?NotifyFailure@?$ActivityBase@VPowerGridForecastTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@UEAA_NAEBUFailureInfo@2@@Z`
- size: `876`
- prototype: `char __fastcall(_QWORD *, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x180001658`
- `0x1800018fc`
- `0x18002b340`
- `0x18002b8a0`
- `0x18002befc`
- `0x18002dec8`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bbf9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002bbf9`

## pseudocode

```c
char __fastcall wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(
        _QWORD *a1,
        int *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r9
  __int64 v6; // rax
  __int64 v7; // r8
  const struct _tlgProvider_t *v8; // rax
  __int64 v9; // r9
  __int64 v10; // rax
  __int64 v11; // r8
  _DWORD *v12; // rax
  int v13; // edx
  int v15; // [rsp+B0h] [rbp-80h] BYREF
  int v16; // [rsp+B4h] [rbp-7Ch] BYREF
  const unsigned __int16 *v17; // [rsp+B8h] [rbp-78h] BYREF
  int *v18; // [rsp+C0h] [rbp-70h] BYREF
  int *v19; // [rsp+C8h] [rbp-68h] BYREF
  const unsigned __int16 *v20; // [rsp+D0h] [rbp-60h] BYREF
  const unsigned __int16 *v21; // [rsp+D8h] [rbp-58h] BYREF
  int *v22; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v23; // [rsp+E8h] [rbp-48h] BYREF
  int *v24; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v25; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v26; // [rsp+100h] [rbp-30h] BYREF
  const unsigned __int16 *v27; // [rsp+108h] [rbp-28h] BYREF
  __int64 v28[4]; // [rsp+110h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+140h] [rbp+10h] BYREF
  int v30; // [rsp+148h] [rbp+18h] BYREF
  int v31; // [rsp+150h] [rbp+20h] BYREF
  int v32; // [rsp+158h] [rbp+28h] BYREF

  if ( (a2[1] & 2) == 0 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, _QWORD))(*a1 + 16LL))(a1, (unsigned int)a2[4]) )
    {
      v8 = PowerGridForecastTaskTelemetry::Provider();
      v9 = (__int64)v8;
      if ( *(_DWORD *)v8 > 2u )
      {
        v10 = *((_QWORD *)v8 + 3);
        if ( (*(_QWORD *)(v9 + 16) & 0x200000000000LL) != 0 && (v10 & 0x200000000000LL) == v10 )
        {
          v25 = *((_QWORD *)a2 + 6);
          LODWORD(SRWLock) = a2[17];
          v30 = a2[4];
          v24 = (int *)*((_QWORD *)a2 + 15);
          v11 = a1[34];
          v23 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
          v31 = a2[26];
          v22 = (int *)*((_QWORD *)a2 + 12);
          v21 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
          v32 = a2[20];
          v20 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
          v16 = a2[8];
          v19 = (int *)*((_QWORD *)a2 + 3);
          v15 = *a2;
          v26 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
          LODWORD(v17) = a2[16];
          v27 = (const unsigned __int16 *)*((_QWORD *)a2 + 7);
          LODWORD(v18) = a2[2];
          v28[0] = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v9,
            (__int64)&word_18003E39E,
            v11 + 8,
            v9,
            (__int64)v28,
            (__int64)&v18,
            &v27,
            (__int64)&v17,
            &v26,
            (__int64)&v15,
            &v19,
            (__int64)&v16,
            &v20,
            (__int64)&v32,
            &v21,
            &v22,
            (__int64)&v31,
            &v23,
            &v24,
            (__int64)&v30,
            (__int64)&SRWLock,
            (const unsigned __int16 **)&v25);
        }
      }
    }
    else
    {
      v4 = PowerGridForecastTaskTelemetry::Provider();
      v5 = (__int64)v4;
      if ( *(_DWORD *)v4 > 2u )
      {
        v6 = *((_QWORD *)v4 + 3);
        if ( (*(_QWORD *)(v5 + 16) & 0x200000000000LL) != 0 && (v6 & 0x200000000000LL) == v6 )
        {
          v7 = a1[34];
          v18 = (int *)*((_QWORD *)a2 + 15);
          v17 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
          LODWORD(SRWLock) = a2[26];
          v19 = (int *)*((_QWORD *)a2 + 12);
          v20 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
          v30 = a2[20];
          v21 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
          v31 = a2[8];
          v22 = (int *)*((_QWORD *)a2 + 3);
          v32 = *a2;
          v23 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
          v15 = a2[16];
          v24 = (int *)*((_QWORD *)a2 + 7);
          v16 = a2[2];
          v25 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            v5,
            (__int64)&word_18003E4D6,
            v7 + 8,
            v5,
            (__int64)&v25,
            (__int64)&v16,
            (const unsigned __int16 **)&v24,
            (__int64)&v15,
            &v23,
            (__int64)&v32,
            &v22,
            (__int64)&v31,
            &v21,
            (__int64)&v30,
            &v20,
            &v19,
            (__int64)&SRWLock,
            &v17,
            &v18);
        }
      }
    }
  }
  wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)a1,
    &SRWLock);
  v12 = (_DWORD *)a1[34];
  v13 = a2[2];
  if ( v13 != v12[22] && (v13 != v12[18] || (int)v12[18] >= 0) )
    wil::StoredFailureInfo::SetFailureInfo((wil::StoredFailureInfo *)(v12 + 20), (const struct wil::FailureInfo *)a2);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return 1;
}

```

## disassembly

```asm
0x18002b8a0  push    rbp
0x18002b8a2  push    rbx
0x18002b8a3  push    rdi
0x18002b8a4  lea     rbp, [rsp+10h]
0x18002b8a9  sub     rsp, 120h
0x18002b8b0  test    byte ptr [rdx+4], 2
0x18002b8b4  mov     rbx, rdx
0x18002b8b7  mov     rdi, rcx
0x18002b8ba  jnz     loc_18002BBBE
0x18002b8c0  mov     rax, [rcx]
0x18002b8c3  mov     edx, [rdx+10h]
0x18002b8c6  mov     rax, [rax+10h]
0x18002b8ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b8cf  test    al, al
0x18002b8d1  jnz     loc_18002BA31
0x18002b8d7  call    ?Provider@PowerGridForecastTaskTelemetry@@SAPEBU_tlgProvider_t@@XZ; PowerGridForecastTaskTelemetry::Provider(void)
0x18002b8dc  mov     r9, rax
0x18002b8df  mov     ecx, [rax]
0x18002b8e1  cmp     ecx, 2
0x18002b8e4  jbe     loc_18002BBBE
0x18002b8ea  mov     rax, [rax+18h]
0x18002b8ee  mov     rdx, 200000000000h
0x18002b8f8  mov     rcx, [r9+10h]
0x18002b8fc  test    rdx, rcx
0x18002b8ff  jz      loc_18002BBBE
0x18002b905  mov     rcx, rax
0x18002b908  and     rcx, rdx
0x18002b90b  cmp     rcx, rax
0x18002b90e  jnz     loc_18002BBBE
0x18002b914  mov     rax, [rbx+78h]
0x18002b918  lea     rdx, word_18003E4D6
0x18002b91f  mov     r8, [rdi+110h]
0x18002b926  mov     rcx, r9
0x18002b929  mov     [rbp+var_70], rax
0x18002b92d  add     r8, 8
0x18002b931  mov     rax, [rbx+70h]
0x18002b935  mov     [rbp+var_78], rax
0x18002b939  mov     eax, [rbx+68h]
0x18002b93c  mov     dword ptr [rbp+SRWLock], eax
0x18002b93f  mov     rax, [rbx+60h]
0x18002b943  mov     [rbp+var_68], rax
0x18002b947  mov     rax, [rbx+58h]
0x18002b94b  mov     [rbp+var_60], rax
0x18002b94f  mov     eax, [rbx+50h]
0x18002b952  mov     [rbp+arg_8], eax
0x18002b955  mov     rax, [rbx+48h]
0x18002b959  mov     [rbp+var_58], rax
0x18002b95d  mov     eax, [rbx+20h]
0x18002b960  mov     [rbp+arg_10], eax
0x18002b963  mov     rax, [rbx+18h]
0x18002b967  mov     [rbp+var_50], rax
0x18002b96b  mov     eax, [rbx]
0x18002b96d  mov     [rbp+arg_18], eax
0x18002b970  mov     rax, [rbx+80h]
0x18002b977  mov     [rbp+var_48], rax
0x18002b97b  mov     eax, [rbx+40h]
0x18002b97e  mov     [rbp+var_80], eax
0x18002b981  mov     rax, [rbx+38h]
0x18002b985  mov     [rbp+var_40], rax
0x18002b989  mov     eax, [rbx+8]
0x18002b98c  mov     [rbp+var_7C], eax
0x18002b98f  lea     rax, [rbp+var_70]
0x18002b993  mov     [rsp+130h+var_A0], rax
0x18002b99b  lea     rax, [rbp+var_78]
0x18002b99f  mov     [rsp+130h+var_A8], rax
0x18002b9a7  lea     rax, [rbp+SRWLock]
0x18002b9ab  mov     [rsp+130h+var_B0], rax
0x18002b9b3  lea     rax, [rbp+var_68]
0x18002b9b7  mov     [rsp+130h+var_B8], rax
0x18002b9bc  lea     rax, [rbp+var_60]
0x18002b9c0  mov     [rsp+130h+var_C0], rax
0x18002b9c5  lea     rax, [rbp+arg_8]
0x18002b9c9  mov     [rsp+130h+var_C8], rax
0x18002b9ce  lea     rax, [rbp+var_58]
0x18002b9d2  mov     [rsp+130h+var_D0], rax
0x18002b9d7  lea     rax, [rbp+arg_10]
0x18002b9db  mov     [rsp+130h+var_D8], rax
0x18002b9e0  lea     rax, [rbp+var_50]
0x18002b9e4  mov     [rsp+130h+var_E0], rax
0x18002b9e9  lea     rax, [rbp+arg_18]
0x18002b9ed  mov     [rsp+130h+var_E8], rax
0x18002b9f2  lea     rax, [rbp+var_48]
0x18002b9f6  mov     [rsp+130h+var_F0], rax
0x18002b9fb  lea     rax, [rbp+var_80]
0x18002b9ff  mov     [rsp+130h+var_F8], rax
0x18002ba04  lea     rax, [rbp+var_40]
0x18002ba08  mov     [rsp+130h+var_100], rax
0x18002ba0d  lea     rax, [rbp+var_7C]
0x18002ba11  mov     [rsp+130h+var_108], rax
0x18002ba16  lea     rax, [rbp+var_38]
0x18002ba1a  mov     [rsp+130h+var_110], rax
0x18002ba1f  mov     [rbp+var_38], 1000000h
0x18002ba27  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18002ba2c  jmp     loc_18002BBBE
0x18002ba31  call    ?Provider@PowerGridForecastTaskTelemetry@@SAPEBU_tlgProvider_t@@XZ; PowerGridForecastTaskTelemetry::Provider(void)
0x18002ba36  mov     r9, rax
0x18002ba39  mov     ecx, [rax]
0x18002ba3b  cmp     ecx, 2
0x18002ba3e  jbe     loc_18002BBBE
0x18002ba44  mov     rax, [rax+18h]
0x18002ba48  mov     rdx, 200000000000h
0x18002ba52  mov     rcx, [r9+10h]
0x18002ba56  test    rdx, rcx
0x18002ba59  jz      loc_18002BBBE
0x18002ba5f  mov     rcx, rax
0x18002ba62  and     rcx, rdx
0x18002ba65  cmp     rcx, rax
0x18002ba68  jnz     loc_18002BBBE
0x18002ba6e  mov     rax, [rbx+30h]
0x18002ba72  lea     rdx, word_18003E39E
0x18002ba79  mov     [rbp+var_38], rax
0x18002ba7d  mov     rcx, r9
0x18002ba80  mov     eax, [rbx+44h]
0x18002ba83  mov     dword ptr [rbp+SRWLock], eax
0x18002ba86  mov     eax, [rbx+10h]
0x18002ba89  mov     [rbp+arg_8], eax
0x18002ba8c  mov     rax, [rbx+78h]
0x18002ba90  mov     [rbp+var_40], rax
0x18002ba94  mov     rax, [rbx+70h]
0x18002ba98  mov     r8, [rdi+110h]
0x18002ba9f  mov     [rbp+var_48], rax
0x18002baa3  add     r8, 8
0x18002baa7  mov     eax, [rbx+68h]
0x18002baaa  mov     [rbp+arg_10], eax
0x18002baad  mov     rax, [rbx+60h]
0x18002bab1  mov     [rbp+var_50], rax
0x18002bab5  mov     rax, [rbx+58h]
0x18002bab9  mov     [rbp+var_58], rax
0x18002babd  mov     eax, [rbx+50h]
0x18002bac0  mov     [rbp+arg_18], eax
0x18002bac3  mov     rax, [rbx+48h]
0x18002bac7  mov     [rbp+var_60], rax
0x18002bacb  mov     eax, [rbx+20h]
0x18002bace  mov     [rbp+var_7C], eax
0x18002bad1  mov     rax, [rbx+18h]
0x18002bad5  mov     [rbp+var_68], rax
0x18002bad9  mov     eax, [rbx]
0x18002badb  mov     [rbp+var_80], eax
0x18002bade  mov     rax, [rbx+80h]
0x18002bae5  mov     [rbp+var_30], rax
0x18002bae9  mov     eax, [rbx+40h]
0x18002baec  mov     dword ptr [rbp+var_78], eax
0x18002baef  mov     rax, [rbx+38h]
0x18002baf3  mov     [rbp+var_28], rax
0x18002baf7  mov     eax, [rbx+8]
0x18002bafa  mov     dword ptr [rbp+var_70], eax
0x18002bafd  lea     rax, [rbp+var_38]
0x18002bb01  mov     [rsp+130h+var_88], rax
0x18002bb09  lea     rax, [rbp+SRWLock]
0x18002bb0d  mov     [rsp+130h+var_90], rax
0x18002bb15  lea     rax, [rbp+arg_8]
0x18002bb19  mov     [rsp+130h+var_98], rax
0x18002bb21  lea     rax, [rbp+var_40]
0x18002bb25  mov     [rsp+130h+var_A0], rax
0x18002bb2d  lea     rax, [rbp+var_48]
0x18002bb31  mov     [rsp+130h+var_A8], rax
0x18002bb39  lea     rax, [rbp+arg_10]
0x18002bb3d  mov     [rsp+130h+var_B0], rax
0x18002bb45  lea     rax, [rbp+var_50]
0x18002bb49  mov     [rsp+130h+var_B8], rax
0x18002bb4e  lea     rax, [rbp+var_58]
0x18002bb52  mov     [rsp+130h+var_C0], rax
0x18002bb57  lea     rax, [rbp+arg_18]
0x18002bb5b  mov     [rsp+130h+var_C8], rax
0x18002bb60  lea     rax, [rbp+var_60]
0x18002bb64  mov     [rsp+130h+var_D0], rax
0x18002bb69  lea     rax, [rbp+var_7C]
0x18002bb6d  mov     [rsp+130h+var_D8], rax
0x18002bb72  lea     rax, [rbp+var_68]
0x18002bb76  mov     [rsp+130h+var_E0], rax
0x18002bb7b  lea     rax, [rbp+var_80]
0x18002bb7f  mov     [rsp+130h+var_E8], rax
0x18002bb84  lea     rax, [rbp+var_30]
0x18002bb88  mov     [rsp+130h+var_F0], rax
0x18002bb8d  lea     rax, [rbp+var_78]
0x18002bb91  mov     [rsp+130h+var_F8], rax
0x18002bb96  lea     rax, [rbp+var_28]
0x18002bb9a  mov     [rsp+130h+var_100], rax
0x18002bb9f  lea     rax, [rbp+var_70]
0x18002bba3  mov     [rsp+130h+var_108], rax
0x18002bba8  lea     rax, [rbp+var_20]
0x18002bbac  mov     [rsp+130h+var_110], rax
0x18002bbb1  mov     [rbp+var_20], 1000000h
0x18002bbb9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002bbbe  lea     rdx, [rbp+SRWLock]
0x18002bbc2  mov     rcx, rdi
0x18002bbc5  call    ?LockExclusive@?$ActivityBase@VPowerGridForecastTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<PowerGridForecastTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002bbca  mov     rax, [rdi+110h]
0x18002bbd1  mov     edx, [rbx+8]
0x18002bbd4  lea     rcx, [rax+50h]; this
0x18002bbd8  cmp     edx, [rcx+8]
0x18002bbdb  jz      short loc_18002BBF0
0x18002bbdd  cmp     edx, [rax+48h]
0x18002bbe0  jnz     short loc_18002BBE8
0x18002bbe2  cmp     dword ptr [rax+48h], 0
0x18002bbe6  jl      short loc_18002BBF0
0x18002bbe8  mov     rdx, rbx; struct wil::FailureInfo *
0x18002bbeb  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x18002bbf0  mov     rcx, [rbp+SRWLock]; SRWLock
0x18002bbf4  test    rcx, rcx
0x18002bbf7  jz      short loc_18002BBFF
0x18002bbf9  call    cs:__imp_ReleaseSRWLockExclusive
0x18002bbff  mov     al, 1
0x18002bc01  add     rsp, 120h
0x18002bc08  pop     rdi
0x18002bc09  pop     rbx
0x18002bc0a  pop     rbp
0x18002bc0b  retn
```
