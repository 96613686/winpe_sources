# wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(wil::FailureInfo const &)

- ea: `0x140010140`
- end: `0x140010486`
- name: `?NotifyFailure@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@UEAA_NAEBUFailureInfo@2@@Z`
- size: `838`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting`

## callees

- `0x1400026f4`
- `0x140002998`
- `0x140002f8c`
- `0x140009158`
- `0x14000ed00`
- `0x140010140`
- `0x140011aa0`
- `0x140014120`
- `0x14001f010`

## pseudocode

```c
char __fastcall wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(
        _QWORD *a1,
        int *a2)
{
  const struct _tlgProvider_t *v4; // rax
  __int64 v5; // r8
  __int64 v6; // r9
  const unsigned __int16 *v7; // rcx
  __int64 v8; // r8
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  const unsigned __int16 *v12; // rcx
  __int64 v13; // r8
  _DWORD *v14; // rax
  int v15; // edx
  int v17; // [rsp+B0h] [rbp-80h] BYREF
  int v18; // [rsp+B4h] [rbp-7Ch] BYREF
  const unsigned __int16 *v19; // [rsp+B8h] [rbp-78h] BYREF
  const unsigned __int16 *v20; // [rsp+C0h] [rbp-70h] BYREF
  const unsigned __int16 *v21; // [rsp+C8h] [rbp-68h] BYREF
  const unsigned __int16 *v22; // [rsp+D0h] [rbp-60h] BYREF
  const unsigned __int16 *v23; // [rsp+D8h] [rbp-58h] BYREF
  const unsigned __int16 *v24; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v25; // [rsp+E8h] [rbp-48h] BYREF
  const unsigned __int16 *v26; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v27; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v28; // [rsp+100h] [rbp-30h] BYREF
  const unsigned __int16 *v29; // [rsp+108h] [rbp-28h] BYREF
  __int64 v30[4]; // [rsp+110h] [rbp-20h] BYREF
  RTL_SRWLOCK *v31; // [rsp+140h] [rbp+10h] BYREF
  int v32; // [rsp+148h] [rbp+18h] BYREF
  int v33; // [rsp+150h] [rbp+20h] BYREF
  int v34; // [rsp+158h] [rbp+28h] BYREF

  if ( (a2[1] & 2) == 0 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, _QWORD))(*a1 + 16LL))(a1, (unsigned int)a2[4]) )
    {
      v9 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
      if ( *(_DWORD *)v9 > 2u && (unsigned __int8)tlgKeywordOn(v9, 0x400000000000LL, v10, v9) )
      {
        LODWORD(v31) = a2[17];
        v32 = a2[4];
        v12 = (const unsigned __int16 *)*((_QWORD *)a2 + 6);
        v26 = (const unsigned __int16 *)*((_QWORD *)a2 + 15);
        v13 = a1[34];
        v25 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
        v33 = a2[26];
        v24 = (const unsigned __int16 *)*((_QWORD *)a2 + 12);
        v23 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
        v34 = a2[20];
        v22 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
        v18 = a2[8];
        v21 = (const unsigned __int16 *)*((_QWORD *)a2 + 3);
        v17 = *a2;
        v28 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
        LODWORD(v19) = a2[16];
        v29 = (const unsigned __int16 *)*((_QWORD *)a2 + 7);
        LODWORD(v20) = a2[2];
        v27 = (__int64)v12;
        v30[0] = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v11,
          (__int64)word_140024B62,
          v13 + 8,
          v11,
          (__int64)v30,
          (__int64)&v20,
          &v29,
          (__int64)&v19,
          &v28,
          (__int64)&v17,
          &v21,
          (__int64)&v18,
          &v22,
          (__int64)&v34,
          &v23,
          &v24,
          (__int64)&v33,
          &v25,
          &v26,
          (__int64)&v32,
          (__int64)&v31,
          (const unsigned __int16 **)&v27);
      }
    }
    else
    {
      v4 = Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider();
      if ( *(_DWORD *)v4 > 2u && (unsigned __int8)tlgKeywordOn(v4, 0x600000000000LL, v5, v4) )
      {
        v7 = (const unsigned __int16 *)*((_QWORD *)a2 + 15);
        v8 = a1[34];
        v19 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
        LODWORD(v31) = a2[26];
        v21 = (const unsigned __int16 *)*((_QWORD *)a2 + 12);
        v22 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
        v32 = a2[20];
        v23 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
        v33 = a2[8];
        v24 = (const unsigned __int16 *)*((_QWORD *)a2 + 3);
        v34 = *a2;
        v25 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
        v17 = a2[16];
        v26 = (const unsigned __int16 *)*((_QWORD *)a2 + 7);
        v18 = a2[2];
        v20 = v7;
        v27 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v6,
          (__int64)&dword_140024F2C,
          v8 + 8,
          v6,
          (__int64)&v27,
          (__int64)&v18,
          &v26,
          (__int64)&v17,
          &v25,
          (__int64)&v34,
          &v24,
          (__int64)&v33,
          &v23,
          (__int64)&v32,
          &v22,
          &v21,
          (__int64)&v31,
          &v19,
          &v20);
      }
    }
  }
  wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    (__int64)a1,
    &v31);
  v14 = (_DWORD *)a1[34];
  v15 = a2[2];
  if ( v15 != v14[22] && (v15 != v14[18] || (int)v14[18] >= 0) )
    wil::StoredFailureInfo::SetFailureInfo((wil::StoredFailureInfo *)(v14 + 20), (const struct wil::FailureInfo *)a2);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v31);
  return 1;
}

```

## disassembly

```asm
0x140010140  push    rbp
0x140010142  push    rbx
0x140010143  push    rdi
0x140010144  lea     rbp, [rsp+10h]
0x140010149  sub     rsp, 120h
0x140010150  test    byte ptr [rdx+4], 2
0x140010154  mov     rbx, rdx
0x140010157  mov     rdi, rcx
0x14001015a  jnz     loc_14001043E
0x140010160  mov     rax, [rcx]
0x140010163  mov     edx, [rdx+10h]
0x140010166  mov     rax, [rax+10h]
0x14001016a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001016f  test    al, al
0x140010171  jnz     loc_1400102C1
0x140010177  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x14001017c  mov     r9, rax
0x14001017f  mov     ecx, [rax]
0x140010181  cmp     ecx, 2
0x140010184  jbe     loc_14001043E
0x14001018a  mov     rdx, 600000000000h
0x140010194  mov     rcx, rax
0x140010197  call    _tlgKeywordOn
0x14001019c  test    al, al
0x14001019e  jz      loc_14001043E
0x1400101a4  mov     rax, [rbx+70h]
0x1400101a8  lea     rdx, dword_140024F2C
0x1400101af  mov     rcx, [rbx+78h]
0x1400101b3  mov     r8, [rdi+110h]
0x1400101ba  mov     [rbp+var_78], rax
0x1400101be  add     r8, 8
0x1400101c2  mov     eax, [rbx+68h]
0x1400101c5  mov     dword ptr [rbp+arg_0], eax
0x1400101c8  mov     rax, [rbx+60h]
0x1400101cc  mov     [rbp+var_68], rax
0x1400101d0  mov     rax, [rbx+58h]
0x1400101d4  mov     [rbp+var_60], rax
0x1400101d8  mov     eax, [rbx+50h]
0x1400101db  mov     [rbp+arg_8], eax
0x1400101de  mov     rax, [rbx+48h]
0x1400101e2  mov     [rbp+var_58], rax
0x1400101e6  mov     eax, [rbx+20h]
0x1400101e9  mov     [rbp+arg_10], eax
0x1400101ec  mov     rax, [rbx+18h]
0x1400101f0  mov     [rbp+var_50], rax
0x1400101f4  mov     eax, [rbx]
0x1400101f6  mov     [rbp+arg_18], eax
0x1400101f9  mov     rax, [rbx+80h]
0x140010200  mov     [rbp+var_48], rax
0x140010204  mov     eax, [rbx+40h]
0x140010207  mov     [rbp+var_80], eax
0x14001020a  mov     rax, [rbx+38h]
0x14001020e  mov     [rbp+var_40], rax
0x140010212  mov     eax, [rbx+8]
0x140010215  mov     [rbp+var_7C], eax
0x140010218  lea     rax, [rbp+var_70]
0x14001021c  mov     [rsp+130h+var_A0], rax
0x140010224  lea     rax, [rbp+var_78]
0x140010228  mov     [rsp+130h+var_A8], rax
0x140010230  lea     rax, [rbp+arg_0]
0x140010234  mov     [rsp+130h+var_B0], rax
0x14001023c  lea     rax, [rbp+var_68]
0x140010240  mov     [rsp+130h+var_B8], rax
0x140010245  lea     rax, [rbp+var_60]
0x140010249  mov     [rsp+130h+var_C0], rax
0x14001024e  lea     rax, [rbp+arg_8]
0x140010252  mov     [rsp+130h+var_C8], rax
0x140010257  lea     rax, [rbp+var_58]
0x14001025b  mov     [rsp+130h+var_D0], rax
0x140010260  lea     rax, [rbp+arg_10]
0x140010264  mov     [rsp+130h+var_D8], rax
0x140010269  lea     rax, [rbp+var_50]
0x14001026d  mov     [rsp+130h+var_E0], rax
0x140010272  lea     rax, [rbp+arg_18]
0x140010276  mov     [rsp+130h+var_E8], rax
0x14001027b  lea     rax, [rbp+var_48]
0x14001027f  mov     [rsp+130h+var_F0], rax
0x140010284  lea     rax, [rbp+var_80]
0x140010288  mov     [rsp+130h+var_F8], rax
0x14001028d  lea     rax, [rbp+var_40]
0x140010291  mov     [rsp+130h+var_100], rax
0x140010296  lea     rax, [rbp+var_7C]
0x14001029a  mov     [rsp+130h+var_108], rax
0x14001029f  lea     rax, [rbp+var_38]
0x1400102a3  mov     [rbp+var_70], rcx
0x1400102a7  mov     rcx, r9
0x1400102aa  mov     [rsp+130h+var_110], rax
0x1400102af  mov     [rbp+var_38], 1000000h
0x1400102b7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1400102bc  jmp     loc_14001043E
0x1400102c1  call    ?Provider@PlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@SAPEBU_tlgProvider_t@@XZ; Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry::Provider(void)
0x1400102c6  mov     r9, rax
0x1400102c9  mov     ecx, [rax]
0x1400102cb  cmp     ecx, 2
0x1400102ce  jbe     loc_14001043E
0x1400102d4  mov     rdx, 400000000000h
0x1400102de  mov     rcx, rax
0x1400102e1  call    _tlgKeywordOn
0x1400102e6  test    al, al
0x1400102e8  jz      loc_14001043E
0x1400102ee  mov     eax, [rbx+44h]
0x1400102f1  lea     rdx, word_140024B62
0x1400102f8  mov     dword ptr [rbp+arg_0], eax
0x1400102fb  mov     eax, [rbx+10h]
0x1400102fe  mov     [rbp+arg_8], eax
0x140010301  mov     rax, [rbx+78h]
0x140010305  mov     rcx, [rbx+30h]
0x140010309  mov     [rbp+var_40], rax
0x14001030d  mov     rax, [rbx+70h]
0x140010311  mov     r8, [rdi+110h]
0x140010318  mov     [rbp+var_48], rax
0x14001031c  add     r8, 8
0x140010320  mov     eax, [rbx+68h]
0x140010323  mov     [rbp+arg_10], eax
0x140010326  mov     rax, [rbx+60h]
0x14001032a  mov     [rbp+var_50], rax
0x14001032e  mov     rax, [rbx+58h]
0x140010332  mov     [rbp+var_58], rax
0x140010336  mov     eax, [rbx+50h]
0x140010339  mov     [rbp+arg_18], eax
0x14001033c  mov     rax, [rbx+48h]
0x140010340  mov     [rbp+var_60], rax
0x140010344  mov     eax, [rbx+20h]
0x140010347  mov     [rbp+var_7C], eax
0x14001034a  mov     rax, [rbx+18h]
0x14001034e  mov     [rbp+var_68], rax
0x140010352  mov     eax, [rbx]
0x140010354  mov     [rbp+var_80], eax
0x140010357  mov     rax, [rbx+80h]
0x14001035e  mov     [rbp+var_30], rax
0x140010362  mov     eax, [rbx+40h]
0x140010365  mov     dword ptr [rbp+var_78], eax
0x140010368  mov     rax, [rbx+38h]
0x14001036c  mov     [rbp+var_28], rax
0x140010370  mov     eax, [rbx+8]
0x140010373  mov     dword ptr [rbp+var_70], eax
0x140010376  lea     rax, [rbp+var_38]
0x14001037a  mov     [rsp+130h+var_88], rax
0x140010382  lea     rax, [rbp+arg_0]
0x140010386  mov     [rsp+130h+var_90], rax
0x14001038e  lea     rax, [rbp+arg_8]
0x140010392  mov     [rsp+130h+var_98], rax
0x14001039a  lea     rax, [rbp+var_40]
0x14001039e  mov     [rsp+130h+var_A0], rax
0x1400103a6  lea     rax, [rbp+var_48]
0x1400103aa  mov     [rsp+130h+var_A8], rax
0x1400103b2  lea     rax, [rbp+arg_10]
0x1400103b6  mov     [rsp+130h+var_B0], rax
0x1400103be  lea     rax, [rbp+var_50]
0x1400103c2  mov     [rsp+130h+var_B8], rax
0x1400103c7  lea     rax, [rbp+var_58]
0x1400103cb  mov     [rsp+130h+var_C0], rax
0x1400103d0  lea     rax, [rbp+arg_18]
0x1400103d4  mov     [rsp+130h+var_C8], rax
0x1400103d9  lea     rax, [rbp+var_60]
0x1400103dd  mov     [rsp+130h+var_D0], rax
0x1400103e2  lea     rax, [rbp+var_7C]
0x1400103e6  mov     [rsp+130h+var_D8], rax
0x1400103eb  lea     rax, [rbp+var_68]
0x1400103ef  mov     [rsp+130h+var_E0], rax
0x1400103f4  lea     rax, [rbp+var_80]
0x1400103f8  mov     [rsp+130h+var_E8], rax
0x1400103fd  lea     rax, [rbp+var_30]
0x140010401  mov     [rsp+130h+var_F0], rax
0x140010406  lea     rax, [rbp+var_78]
0x14001040a  mov     [rsp+130h+var_F8], rax
0x14001040f  lea     rax, [rbp+var_28]
0x140010413  mov     [rsp+130h+var_100], rax
0x140010418  lea     rax, [rbp+var_70]
0x14001041c  mov     [rsp+130h+var_108], rax
0x140010421  lea     rax, [rbp+var_20]
0x140010425  mov     [rbp+var_38], rcx
0x140010429  mov     rcx, r9
0x14001042c  mov     [rsp+130h+var_110], rax
0x140010431  mov     [rbp+var_20], 1000000h
0x140010439  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14001043e  lea     rdx, [rbp+arg_0]
0x140010442  mov     rcx, rdi
0x140010445  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14001044a  mov     rax, [rdi+110h]
0x140010451  mov     edx, [rbx+8]
0x140010454  lea     rcx, [rax+50h]; this
0x140010458  cmp     edx, [rcx+8]
0x14001045b  jz      short loc_140010470
0x14001045d  cmp     edx, [rax+48h]
0x140010460  jnz     short loc_140010468
0x140010462  cmp     dword ptr [rax+48h], 0
0x140010466  jl      short loc_140010470
0x140010468  mov     rdx, rbx; struct wil::FailureInfo *
0x14001046b  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x140010470  lea     rcx, [rbp+arg_0]
0x140010474  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140010479  mov     al, 1
0x14001047b  add     rsp, 120h
0x140010482  pop     rdi
0x140010483  pop     rbx
0x140010484  pop     rbp
0x140010485  retn
```
