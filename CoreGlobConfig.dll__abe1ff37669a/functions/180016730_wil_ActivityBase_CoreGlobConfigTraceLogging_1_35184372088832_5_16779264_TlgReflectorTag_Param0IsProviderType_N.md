# wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(wil::FailureInfo const &)

- ea: `0x180016730`
- end: `0x180016a76`
- name: `?NotifyFailure@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@UEAA_NAEBUFailureInfo@2@@Z`
- size: `838`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x1800013cc`
- `0x180001670`
- `0x180001acc`
- `0x1800084b0`
- `0x180011488`
- `0x18001608c`
- `0x180016730`
- `0x180016fcc`
- `0x180025010`

## pseudocode

```c
char __fastcall wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(
        _QWORD *a1,
        int *a2)
{
  __int64 v4; // rcx
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 *v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  const unsigned __int16 *v13; // rcx
  __int64 v14; // r8
  _DWORD *v15; // rax
  int v16; // edx
  int v18; // [rsp+B0h] [rbp-80h] BYREF
  int v19; // [rsp+B4h] [rbp-7Ch] BYREF
  const unsigned __int16 *v20; // [rsp+B8h] [rbp-78h] BYREF
  __int64 *v21; // [rsp+C0h] [rbp-70h] BYREF
  __int64 *v22; // [rsp+C8h] [rbp-68h] BYREF
  const unsigned __int16 *v23; // [rsp+D0h] [rbp-60h] BYREF
  const unsigned __int16 *v24; // [rsp+D8h] [rbp-58h] BYREF
  __int64 *v25; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v26; // [rsp+E8h] [rbp-48h] BYREF
  __int64 *v27; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v28; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v29; // [rsp+100h] [rbp-30h] BYREF
  const unsigned __int16 *v30; // [rsp+108h] [rbp-28h] BYREF
  __int64 v31[4]; // [rsp+110h] [rbp-20h] BYREF
  RTL_SRWLOCK *v32; // [rsp+140h] [rbp+10h] BYREF
  int v33; // [rsp+148h] [rbp+18h] BYREF
  int v34; // [rsp+150h] [rbp+20h] BYREF
  int v35; // [rsp+158h] [rbp+28h] BYREF

  if ( (a2[1] & 2) == 0 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, _QWORD))(*a1 + 16LL))(a1, (unsigned int)a2[4]) )
    {
      v10 = CoreGlobConfigTraceLogging::Provider(v4);
      if ( *(_DWORD *)v10 > 2u && (unsigned __int8)tlgKeywordOn(v10, 0x200000000000LL, v11) )
      {
        LODWORD(v32) = a2[17];
        v33 = a2[4];
        v13 = (const unsigned __int16 *)*((_QWORD *)a2 + 6);
        v27 = (__int64 *)*((_QWORD *)a2 + 15);
        v14 = a1[34];
        v26 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
        v34 = a2[26];
        v25 = (__int64 *)*((_QWORD *)a2 + 12);
        v24 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
        v35 = a2[20];
        v23 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
        v19 = a2[8];
        v22 = (__int64 *)*((_QWORD *)a2 + 3);
        v18 = *a2;
        v29 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
        LODWORD(v20) = a2[16];
        v30 = (const unsigned __int16 *)*((_QWORD *)a2 + 7);
        LODWORD(v21) = a2[2];
        v28 = (__int64)v13;
        v31[0] = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v12,
          (__int64)&word_18002ABE6,
          v14 + 8,
          v12,
          (__int64)v31,
          (__int64)&v21,
          &v30,
          (__int64)&v20,
          &v29,
          (__int64)&v18,
          &v22,
          (__int64)&v19,
          &v23,
          (__int64)&v35,
          &v24,
          &v25,
          (__int64)&v34,
          &v26,
          &v27,
          (__int64)&v33,
          (__int64)&v32,
          (const unsigned __int16 **)&v28);
      }
    }
    else
    {
      v5 = CoreGlobConfigTraceLogging::Provider(v4);
      if ( *(_DWORD *)v5 > 2u && (unsigned __int8)tlgKeywordOn(v5, 0x200000000000LL, v6) )
      {
        v8 = (__int64 *)*((_QWORD *)a2 + 15);
        v9 = a1[34];
        v20 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
        LODWORD(v32) = a2[26];
        v22 = (__int64 *)*((_QWORD *)a2 + 12);
        v23 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
        v33 = a2[20];
        v24 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
        v34 = a2[8];
        v25 = (__int64 *)*((_QWORD *)a2 + 3);
        v35 = *a2;
        v26 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
        v18 = a2[16];
        v27 = (__int64 *)*((_QWORD *)a2 + 7);
        v19 = a2[2];
        v21 = v8;
        v28 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v7,
          (__int64)byte_18002AAD1,
          v9 + 8,
          v7,
          (__int64)&v28,
          (__int64)&v19,
          (const unsigned __int16 **)&v27,
          (__int64)&v18,
          &v26,
          (__int64)&v35,
          &v25,
          (__int64)&v34,
          &v24,
          (__int64)&v33,
          &v23,
          &v22,
          (__int64)&v32,
          &v20,
          &v21);
      }
    }
  }
  wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v32);
  v15 = (_DWORD *)a1[34];
  v16 = a2[2];
  if ( v16 != v15[22] && (v16 != v15[18] || (int)v15[18] >= 0) )
    wil::StoredFailureInfo::SetFailureInfo((wil::StoredFailureInfo *)(v15 + 20), (const struct wil::FailureInfo *)a2);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v32);
  return 1;
}

```

## disassembly

```asm
0x180016730  push    rbp
0x180016732  push    rbx
0x180016733  push    rdi
0x180016734  lea     rbp, [rsp+10h]
0x180016739  sub     rsp, 120h
0x180016740  test    byte ptr [rdx+4], 2
0x180016744  mov     rbx, rdx
0x180016747  mov     rdi, rcx
0x18001674a  jnz     loc_180016A2E
0x180016750  mov     rax, [rcx]
0x180016753  mov     edx, [rdx+10h]
0x180016756  mov     rax, [rax+10h]
0x18001675a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001675f  test    al, al
0x180016761  jnz     loc_1800168B1
0x180016767  call    ?Provider@CoreGlobConfigTraceLogging@@SAPEBU_tlgProvider_t@@XZ; CoreGlobConfigTraceLogging::Provider(void)
0x18001676c  mov     r9, rax
0x18001676f  mov     ecx, [rax]
0x180016771  cmp     ecx, 2
0x180016774  jbe     loc_180016A2E
0x18001677a  mov     rdx, 200000000000h
0x180016784  mov     rcx, rax
0x180016787  call    _tlgKeywordOn
0x18001678c  test    al, al
0x18001678e  jz      loc_180016A2E
0x180016794  mov     rax, [rbx+70h]
0x180016798  lea     rdx, byte_18002AAD1
0x18001679f  mov     rcx, [rbx+78h]
0x1800167a3  mov     r8, [rdi+110h]
0x1800167aa  mov     [rbp+var_78], rax
0x1800167ae  add     r8, 8
0x1800167b2  mov     eax, [rbx+68h]
0x1800167b5  mov     dword ptr [rbp+arg_0], eax
0x1800167b8  mov     rax, [rbx+60h]
0x1800167bc  mov     [rbp+var_68], rax
0x1800167c0  mov     rax, [rbx+58h]
0x1800167c4  mov     [rbp+var_60], rax
0x1800167c8  mov     eax, [rbx+50h]
0x1800167cb  mov     [rbp+arg_8], eax
0x1800167ce  mov     rax, [rbx+48h]
0x1800167d2  mov     [rbp+var_58], rax
0x1800167d6  mov     eax, [rbx+20h]
0x1800167d9  mov     [rbp+arg_10], eax
0x1800167dc  mov     rax, [rbx+18h]
0x1800167e0  mov     [rbp+var_50], rax
0x1800167e4  mov     eax, [rbx]
0x1800167e6  mov     [rbp+arg_18], eax
0x1800167e9  mov     rax, [rbx+80h]
0x1800167f0  mov     [rbp+var_48], rax
0x1800167f4  mov     eax, [rbx+40h]
0x1800167f7  mov     [rbp+var_80], eax
0x1800167fa  mov     rax, [rbx+38h]
0x1800167fe  mov     [rbp+var_40], rax
0x180016802  mov     eax, [rbx+8]
0x180016805  mov     [rbp+var_7C], eax
0x180016808  lea     rax, [rbp+var_70]
0x18001680c  mov     [rsp+130h+var_A0], rax
0x180016814  lea     rax, [rbp+var_78]
0x180016818  mov     [rsp+130h+var_A8], rax
0x180016820  lea     rax, [rbp+arg_0]
0x180016824  mov     [rsp+130h+var_B0], rax
0x18001682c  lea     rax, [rbp+var_68]
0x180016830  mov     [rsp+130h+var_B8], rax
0x180016835  lea     rax, [rbp+var_60]
0x180016839  mov     [rsp+130h+var_C0], rax
0x18001683e  lea     rax, [rbp+arg_8]
0x180016842  mov     [rsp+130h+var_C8], rax
0x180016847  lea     rax, [rbp+var_58]
0x18001684b  mov     [rsp+130h+var_D0], rax
0x180016850  lea     rax, [rbp+arg_10]
0x180016854  mov     [rsp+130h+var_D8], rax
0x180016859  lea     rax, [rbp+var_50]
0x18001685d  mov     [rsp+130h+var_E0], rax
0x180016862  lea     rax, [rbp+arg_18]
0x180016866  mov     [rsp+130h+var_E8], rax
0x18001686b  lea     rax, [rbp+var_48]
0x18001686f  mov     [rsp+130h+var_F0], rax
0x180016874  lea     rax, [rbp+var_80]
0x180016878  mov     [rsp+130h+var_F8], rax
0x18001687d  lea     rax, [rbp+var_40]
0x180016881  mov     [rsp+130h+var_100], rax
0x180016886  lea     rax, [rbp+var_7C]
0x18001688a  mov     [rsp+130h+var_108], rax
0x18001688f  lea     rax, [rbp+var_38]
0x180016893  mov     [rbp+var_70], rcx
0x180016897  mov     rcx, r9
0x18001689a  mov     [rsp+130h+var_110], rax
0x18001689f  mov     [rbp+var_38], 1000000h
0x1800168a7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x1800168ac  jmp     loc_180016A2E
0x1800168b1  call    ?Provider@CoreGlobConfigTraceLogging@@SAPEBU_tlgProvider_t@@XZ; CoreGlobConfigTraceLogging::Provider(void)
0x1800168b6  mov     r9, rax
0x1800168b9  mov     ecx, [rax]
0x1800168bb  cmp     ecx, 2
0x1800168be  jbe     loc_180016A2E
0x1800168c4  mov     rdx, 200000000000h
0x1800168ce  mov     rcx, rax
0x1800168d1  call    _tlgKeywordOn
0x1800168d6  test    al, al
0x1800168d8  jz      loc_180016A2E
0x1800168de  mov     eax, [rbx+44h]
0x1800168e1  lea     rdx, word_18002ABE6
0x1800168e8  mov     dword ptr [rbp+arg_0], eax
0x1800168eb  mov     eax, [rbx+10h]
0x1800168ee  mov     [rbp+arg_8], eax
0x1800168f1  mov     rax, [rbx+78h]
0x1800168f5  mov     rcx, [rbx+30h]
0x1800168f9  mov     [rbp+var_40], rax
0x1800168fd  mov     rax, [rbx+70h]
0x180016901  mov     r8, [rdi+110h]
0x180016908  mov     [rbp+var_48], rax
0x18001690c  add     r8, 8
0x180016910  mov     eax, [rbx+68h]
0x180016913  mov     [rbp+arg_10], eax
0x180016916  mov     rax, [rbx+60h]
0x18001691a  mov     [rbp+var_50], rax
0x18001691e  mov     rax, [rbx+58h]
0x180016922  mov     [rbp+var_58], rax
0x180016926  mov     eax, [rbx+50h]
0x180016929  mov     [rbp+arg_18], eax
0x18001692c  mov     rax, [rbx+48h]
0x180016930  mov     [rbp+var_60], rax
0x180016934  mov     eax, [rbx+20h]
0x180016937  mov     [rbp+var_7C], eax
0x18001693a  mov     rax, [rbx+18h]
0x18001693e  mov     [rbp+var_68], rax
0x180016942  mov     eax, [rbx]
0x180016944  mov     [rbp+var_80], eax
0x180016947  mov     rax, [rbx+80h]
0x18001694e  mov     [rbp+var_30], rax
0x180016952  mov     eax, [rbx+40h]
0x180016955  mov     dword ptr [rbp+var_78], eax
0x180016958  mov     rax, [rbx+38h]
0x18001695c  mov     [rbp+var_28], rax
0x180016960  mov     eax, [rbx+8]
0x180016963  mov     dword ptr [rbp+var_70], eax
0x180016966  lea     rax, [rbp+var_38]
0x18001696a  mov     [rsp+130h+var_88], rax
0x180016972  lea     rax, [rbp+arg_0]
0x180016976  mov     [rsp+130h+var_90], rax
0x18001697e  lea     rax, [rbp+arg_8]
0x180016982  mov     [rsp+130h+var_98], rax
0x18001698a  lea     rax, [rbp+var_40]
0x18001698e  mov     [rsp+130h+var_A0], rax
0x180016996  lea     rax, [rbp+var_48]
0x18001699a  mov     [rsp+130h+var_A8], rax
0x1800169a2  lea     rax, [rbp+arg_10]
0x1800169a6  mov     [rsp+130h+var_B0], rax
0x1800169ae  lea     rax, [rbp+var_50]
0x1800169b2  mov     [rsp+130h+var_B8], rax
0x1800169b7  lea     rax, [rbp+var_58]
0x1800169bb  mov     [rsp+130h+var_C0], rax
0x1800169c0  lea     rax, [rbp+arg_18]
0x1800169c4  mov     [rsp+130h+var_C8], rax
0x1800169c9  lea     rax, [rbp+var_60]
0x1800169cd  mov     [rsp+130h+var_D0], rax
0x1800169d2  lea     rax, [rbp+var_7C]
0x1800169d6  mov     [rsp+130h+var_D8], rax
0x1800169db  lea     rax, [rbp+var_68]
0x1800169df  mov     [rsp+130h+var_E0], rax
0x1800169e4  lea     rax, [rbp+var_80]
0x1800169e8  mov     [rsp+130h+var_E8], rax
0x1800169ed  lea     rax, [rbp+var_30]
0x1800169f1  mov     [rsp+130h+var_F0], rax
0x1800169f6  lea     rax, [rbp+var_78]
0x1800169fa  mov     [rsp+130h+var_F8], rax
0x1800169ff  lea     rax, [rbp+var_28]
0x180016a03  mov     [rsp+130h+var_100], rax
0x180016a08  lea     rax, [rbp+var_70]
0x180016a0c  mov     [rsp+130h+var_108], rax
0x180016a11  lea     rax, [rbp+var_20]
0x180016a15  mov     [rbp+var_38], rcx
0x180016a19  mov     rcx, r9
0x180016a1c  mov     [rsp+130h+var_110], rax
0x180016a21  mov     [rbp+var_20], 1000000h
0x180016a29  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180016a2e  lea     rdx, [rbp+arg_0]
0x180016a32  mov     rcx, rdi
0x180016a35  call    ?LockExclusive@?$ActivityBase@VCoreGlobConfigTraceLogging@@$00$0CAAAAAAAAAAA@$04$0BAAAIAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<CoreGlobConfigTraceLogging,1,35184372088832,5,16779264,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180016a3a  mov     rax, [rdi+110h]
0x180016a41  mov     edx, [rbx+8]
0x180016a44  lea     rcx, [rax+50h]; this
0x180016a48  cmp     edx, [rcx+8]
0x180016a4b  jz      short loc_180016A60
0x180016a4d  cmp     edx, [rax+48h]
0x180016a50  jnz     short loc_180016A58
0x180016a52  cmp     dword ptr [rax+48h], 0
0x180016a56  jl      short loc_180016A60
0x180016a58  mov     rdx, rbx; struct wil::FailureInfo *
0x180016a5b  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x180016a60  lea     rcx, [rbp+arg_0]
0x180016a64  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180016a69  mov     al, 1
0x180016a6b  add     rsp, 120h
0x180016a72  pop     rdi
0x180016a73  pop     rbx
0x180016a74  pop     rbp
0x180016a75  retn
```
