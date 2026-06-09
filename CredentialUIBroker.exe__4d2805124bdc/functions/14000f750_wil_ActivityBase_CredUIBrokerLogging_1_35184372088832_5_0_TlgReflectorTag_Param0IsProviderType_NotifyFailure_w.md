# wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(wil::FailureInfo const &)

- ea: `0x14000f750`
- end: `0x14000fa96`
- name: `?NotifyFailure@?$ActivityBase@VCredUIBrokerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@UEAA_NAEBUFailureInfo@2@@Z`
- size: `838`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1400026f4`
- `0x140002998`
- `0x140002f8c`
- `0x140009158`
- `0x14000ed00`
- `0x14000f750`
- `0x140011a40`
- `0x140014120`
- `0x14001f010`

## pseudocode

```c
char __fastcall wil::ActivityBase<CredUIBrokerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(
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
      v9 = CredUIBrokerLogging::Provider();
      if ( *(_DWORD *)v9 > 2u && (unsigned __int8)tlgKeywordOn(v9, 0x200000000000LL, v10, v9) )
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
          (__int64)word_140025B8A,
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
      v4 = CredUIBrokerLogging::Provider();
      if ( *(_DWORD *)v4 > 2u && (unsigned __int8)tlgKeywordOn(v4, 0x200000000000LL, v5, v4) )
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
          (__int64)&word_140025346,
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
0x14000f750  push    rbp
0x14000f752  push    rbx
0x14000f753  push    rdi
0x14000f754  lea     rbp, [rsp+10h]
0x14000f759  sub     rsp, 120h
0x14000f760  test    byte ptr [rdx+4], 2
0x14000f764  mov     rbx, rdx
0x14000f767  mov     rdi, rcx
0x14000f76a  jnz     loc_14000FA4E
0x14000f770  mov     rax, [rcx]
0x14000f773  mov     edx, [rdx+10h]
0x14000f776  mov     rax, [rax+10h]
0x14000f77a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f77f  test    al, al
0x14000f781  jnz     loc_14000F8D1
0x14000f787  call    ?Provider@CredUIBrokerLogging@@SAPEBU_tlgProvider_t@@XZ; CredUIBrokerLogging::Provider(void)
0x14000f78c  mov     r9, rax
0x14000f78f  mov     ecx, [rax]
0x14000f791  cmp     ecx, 2
0x14000f794  jbe     loc_14000FA4E
0x14000f79a  mov     rdx, 200000000000h
0x14000f7a4  mov     rcx, rax
0x14000f7a7  call    _tlgKeywordOn
0x14000f7ac  test    al, al
0x14000f7ae  jz      loc_14000FA4E
0x14000f7b4  mov     rax, [rbx+70h]
0x14000f7b8  lea     rdx, word_140025346
0x14000f7bf  mov     rcx, [rbx+78h]
0x14000f7c3  mov     r8, [rdi+110h]
0x14000f7ca  mov     [rbp+var_78], rax
0x14000f7ce  add     r8, 8
0x14000f7d2  mov     eax, [rbx+68h]
0x14000f7d5  mov     dword ptr [rbp+arg_0], eax
0x14000f7d8  mov     rax, [rbx+60h]
0x14000f7dc  mov     [rbp+var_68], rax
0x14000f7e0  mov     rax, [rbx+58h]
0x14000f7e4  mov     [rbp+var_60], rax
0x14000f7e8  mov     eax, [rbx+50h]
0x14000f7eb  mov     [rbp+arg_8], eax
0x14000f7ee  mov     rax, [rbx+48h]
0x14000f7f2  mov     [rbp+var_58], rax
0x14000f7f6  mov     eax, [rbx+20h]
0x14000f7f9  mov     [rbp+arg_10], eax
0x14000f7fc  mov     rax, [rbx+18h]
0x14000f800  mov     [rbp+var_50], rax
0x14000f804  mov     eax, [rbx]
0x14000f806  mov     [rbp+arg_18], eax
0x14000f809  mov     rax, [rbx+80h]
0x14000f810  mov     [rbp+var_48], rax
0x14000f814  mov     eax, [rbx+40h]
0x14000f817  mov     [rbp+var_80], eax
0x14000f81a  mov     rax, [rbx+38h]
0x14000f81e  mov     [rbp+var_40], rax
0x14000f822  mov     eax, [rbx+8]
0x14000f825  mov     [rbp+var_7C], eax
0x14000f828  lea     rax, [rbp+var_70]
0x14000f82c  mov     [rsp+130h+var_A0], rax
0x14000f834  lea     rax, [rbp+var_78]
0x14000f838  mov     [rsp+130h+var_A8], rax
0x14000f840  lea     rax, [rbp+arg_0]
0x14000f844  mov     [rsp+130h+var_B0], rax
0x14000f84c  lea     rax, [rbp+var_68]
0x14000f850  mov     [rsp+130h+var_B8], rax
0x14000f855  lea     rax, [rbp+var_60]
0x14000f859  mov     [rsp+130h+var_C0], rax
0x14000f85e  lea     rax, [rbp+arg_8]
0x14000f862  mov     [rsp+130h+var_C8], rax
0x14000f867  lea     rax, [rbp+var_58]
0x14000f86b  mov     [rsp+130h+var_D0], rax
0x14000f870  lea     rax, [rbp+arg_10]
0x14000f874  mov     [rsp+130h+var_D8], rax
0x14000f879  lea     rax, [rbp+var_50]
0x14000f87d  mov     [rsp+130h+var_E0], rax
0x14000f882  lea     rax, [rbp+arg_18]
0x14000f886  mov     [rsp+130h+var_E8], rax
0x14000f88b  lea     rax, [rbp+var_48]
0x14000f88f  mov     [rsp+130h+var_F0], rax
0x14000f894  lea     rax, [rbp+var_80]
0x14000f898  mov     [rsp+130h+var_F8], rax
0x14000f89d  lea     rax, [rbp+var_40]
0x14000f8a1  mov     [rsp+130h+var_100], rax
0x14000f8a6  lea     rax, [rbp+var_7C]
0x14000f8aa  mov     [rsp+130h+var_108], rax
0x14000f8af  lea     rax, [rbp+var_38]
0x14000f8b3  mov     [rbp+var_70], rcx
0x14000f8b7  mov     rcx, r9
0x14000f8ba  mov     [rsp+130h+var_110], rax
0x14000f8bf  mov     [rbp+var_38], 1000000h
0x14000f8c7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x14000f8cc  jmp     loc_14000FA4E
0x14000f8d1  call    ?Provider@CredUIBrokerLogging@@SAPEBU_tlgProvider_t@@XZ; CredUIBrokerLogging::Provider(void)
0x14000f8d6  mov     r9, rax
0x14000f8d9  mov     ecx, [rax]
0x14000f8db  cmp     ecx, 2
0x14000f8de  jbe     loc_14000FA4E
0x14000f8e4  mov     rdx, 200000000000h
0x14000f8ee  mov     rcx, rax
0x14000f8f1  call    _tlgKeywordOn
0x14000f8f6  test    al, al
0x14000f8f8  jz      loc_14000FA4E
0x14000f8fe  mov     eax, [rbx+44h]
0x14000f901  lea     rdx, word_140025B8A
0x14000f908  mov     dword ptr [rbp+arg_0], eax
0x14000f90b  mov     eax, [rbx+10h]
0x14000f90e  mov     [rbp+arg_8], eax
0x14000f911  mov     rax, [rbx+78h]
0x14000f915  mov     rcx, [rbx+30h]
0x14000f919  mov     [rbp+var_40], rax
0x14000f91d  mov     rax, [rbx+70h]
0x14000f921  mov     r8, [rdi+110h]
0x14000f928  mov     [rbp+var_48], rax
0x14000f92c  add     r8, 8
0x14000f930  mov     eax, [rbx+68h]
0x14000f933  mov     [rbp+arg_10], eax
0x14000f936  mov     rax, [rbx+60h]
0x14000f93a  mov     [rbp+var_50], rax
0x14000f93e  mov     rax, [rbx+58h]
0x14000f942  mov     [rbp+var_58], rax
0x14000f946  mov     eax, [rbx+50h]
0x14000f949  mov     [rbp+arg_18], eax
0x14000f94c  mov     rax, [rbx+48h]
0x14000f950  mov     [rbp+var_60], rax
0x14000f954  mov     eax, [rbx+20h]
0x14000f957  mov     [rbp+var_7C], eax
0x14000f95a  mov     rax, [rbx+18h]
0x14000f95e  mov     [rbp+var_68], rax
0x14000f962  mov     eax, [rbx]
0x14000f964  mov     [rbp+var_80], eax
0x14000f967  mov     rax, [rbx+80h]
0x14000f96e  mov     [rbp+var_30], rax
0x14000f972  mov     eax, [rbx+40h]
0x14000f975  mov     dword ptr [rbp+var_78], eax
0x14000f978  mov     rax, [rbx+38h]
0x14000f97c  mov     [rbp+var_28], rax
0x14000f980  mov     eax, [rbx+8]
0x14000f983  mov     dword ptr [rbp+var_70], eax
0x14000f986  lea     rax, [rbp+var_38]
0x14000f98a  mov     [rsp+130h+var_88], rax
0x14000f992  lea     rax, [rbp+arg_0]
0x14000f996  mov     [rsp+130h+var_90], rax
0x14000f99e  lea     rax, [rbp+arg_8]
0x14000f9a2  mov     [rsp+130h+var_98], rax
0x14000f9aa  lea     rax, [rbp+var_40]
0x14000f9ae  mov     [rsp+130h+var_A0], rax
0x14000f9b6  lea     rax, [rbp+var_48]
0x14000f9ba  mov     [rsp+130h+var_A8], rax
0x14000f9c2  lea     rax, [rbp+arg_10]
0x14000f9c6  mov     [rsp+130h+var_B0], rax
0x14000f9ce  lea     rax, [rbp+var_50]
0x14000f9d2  mov     [rsp+130h+var_B8], rax
0x14000f9d7  lea     rax, [rbp+var_58]
0x14000f9db  mov     [rsp+130h+var_C0], rax
0x14000f9e0  lea     rax, [rbp+arg_18]
0x14000f9e4  mov     [rsp+130h+var_C8], rax
0x14000f9e9  lea     rax, [rbp+var_60]
0x14000f9ed  mov     [rsp+130h+var_D0], rax
0x14000f9f2  lea     rax, [rbp+var_7C]
0x14000f9f6  mov     [rsp+130h+var_D8], rax
0x14000f9fb  lea     rax, [rbp+var_68]
0x14000f9ff  mov     [rsp+130h+var_E0], rax
0x14000fa04  lea     rax, [rbp+var_80]
0x14000fa08  mov     [rsp+130h+var_E8], rax
0x14000fa0d  lea     rax, [rbp+var_30]
0x14000fa11  mov     [rsp+130h+var_F0], rax
0x14000fa16  lea     rax, [rbp+var_78]
0x14000fa1a  mov     [rsp+130h+var_F8], rax
0x14000fa1f  lea     rax, [rbp+var_28]
0x14000fa23  mov     [rsp+130h+var_100], rax
0x14000fa28  lea     rax, [rbp+var_70]
0x14000fa2c  mov     [rsp+130h+var_108], rax
0x14000fa31  lea     rax, [rbp+var_20]
0x14000fa35  mov     [rbp+var_38], rcx
0x14000fa39  mov     rcx, r9
0x14000fa3c  mov     [rsp+130h+var_110], rax
0x14000fa41  mov     [rbp+var_20], 1000000h
0x14000fa49  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14000fa4e  lea     rdx, [rbp+arg_0]
0x14000fa52  mov     rcx, rdi
0x14000fa55  call    ?LockExclusive@?$ActivityBase@VPlatformExtensionsTelemetry@Details@PlatformExtensions@Internal@Windows@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<Windows::Internal::PlatformExtensions::Details::PlatformExtensionsTelemetry,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000fa5a  mov     rax, [rdi+110h]
0x14000fa61  mov     edx, [rbx+8]
0x14000fa64  lea     rcx, [rax+50h]; this
0x14000fa68  cmp     edx, [rcx+8]
0x14000fa6b  jz      short loc_14000FA80
0x14000fa6d  cmp     edx, [rax+48h]
0x14000fa70  jnz     short loc_14000FA78
0x14000fa72  cmp     dword ptr [rax+48h], 0
0x14000fa76  jl      short loc_14000FA80
0x14000fa78  mov     rdx, rbx; struct wil::FailureInfo *
0x14000fa7b  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x14000fa80  lea     rcx, [rbp+arg_0]
0x14000fa84  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000fa89  mov     al, 1
0x14000fa8b  add     rsp, 120h
0x14000fa92  pop     rdi
0x14000fa93  pop     rbx
0x14000fa94  pop     rbp
0x14000fa95  retn
```
