# wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(wil::FailureInfo const &)

- ea: `0x1800052b0`
- end: `0x18000561c`
- name: `?NotifyFailure@?$ActivityBase@VEcoScoreTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@UEAA_NAEBUFailureInfo@2@@Z`
- size: `876`
- prototype: `char __fastcall(_QWORD *, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x1800012bc`
- `0x180001560`
- `0x180004d4c`
- `0x1800052b0`
- `0x180005760`
- `0x180005ef0`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005609`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005609`

## pseudocode

```c
char __fastcall wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(
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
      v8 = EcoScoreTaskTelemetry::Provider();
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
            (__int64)&word_18000B03E,
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
      v4 = EcoScoreTaskTelemetry::Provider();
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
            (__int64)&word_18000B176,
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
  wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
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
0x1800052b0  push    rbp
0x1800052b2  push    rbx
0x1800052b3  push    rdi
0x1800052b4  lea     rbp, [rsp+10h]
0x1800052b9  sub     rsp, 120h
0x1800052c0  test    byte ptr [rdx+4], 2
0x1800052c4  mov     rbx, rdx
0x1800052c7  mov     rdi, rcx
0x1800052ca  jnz     loc_1800055CE
0x1800052d0  mov     rax, [rcx]
0x1800052d3  mov     edx, [rdx+10h]
0x1800052d6  mov     rax, [rax+10h]
0x1800052da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052df  test    al, al
0x1800052e1  jnz     loc_180005441
0x1800052e7  call    ?Provider@EcoScoreTaskTelemetry@@SAPEBU_tlgProvider_t@@XZ; EcoScoreTaskTelemetry::Provider(void)
0x1800052ec  mov     r9, rax
0x1800052ef  mov     ecx, [rax]
0x1800052f1  cmp     ecx, 2
0x1800052f4  jbe     loc_1800055CE
0x1800052fa  mov     rax, [rax+18h]
0x1800052fe  mov     rdx, 200000000000h
0x180005308  mov     rcx, [r9+10h]
0x18000530c  test    rdx, rcx
0x18000530f  jz      loc_1800055CE
0x180005315  mov     rcx, rax
0x180005318  and     rcx, rdx
0x18000531b  cmp     rcx, rax
0x18000531e  jnz     loc_1800055CE
0x180005324  mov     rax, [rbx+78h]
0x180005328  lea     rdx, word_18000B176
0x18000532f  mov     r8, [rdi+110h]
0x180005336  mov     rcx, r9
0x180005339  mov     [rbp+var_70], rax
0x18000533d  add     r8, 8
0x180005341  mov     rax, [rbx+70h]
0x180005345  mov     [rbp+var_78], rax
0x180005349  mov     eax, [rbx+68h]
0x18000534c  mov     dword ptr [rbp+SRWLock], eax
0x18000534f  mov     rax, [rbx+60h]
0x180005353  mov     [rbp+var_68], rax
0x180005357  mov     rax, [rbx+58h]
0x18000535b  mov     [rbp+var_60], rax
0x18000535f  mov     eax, [rbx+50h]
0x180005362  mov     [rbp+arg_8], eax
0x180005365  mov     rax, [rbx+48h]
0x180005369  mov     [rbp+var_58], rax
0x18000536d  mov     eax, [rbx+20h]
0x180005370  mov     [rbp+arg_10], eax
0x180005373  mov     rax, [rbx+18h]
0x180005377  mov     [rbp+var_50], rax
0x18000537b  mov     eax, [rbx]
0x18000537d  mov     [rbp+arg_18], eax
0x180005380  mov     rax, [rbx+80h]
0x180005387  mov     [rbp+var_48], rax
0x18000538b  mov     eax, [rbx+40h]
0x18000538e  mov     [rbp+var_80], eax
0x180005391  mov     rax, [rbx+38h]
0x180005395  mov     [rbp+var_40], rax
0x180005399  mov     eax, [rbx+8]
0x18000539c  mov     [rbp+var_7C], eax
0x18000539f  lea     rax, [rbp+var_70]
0x1800053a3  mov     [rsp+130h+var_A0], rax
0x1800053ab  lea     rax, [rbp+var_78]
0x1800053af  mov     [rsp+130h+var_A8], rax
0x1800053b7  lea     rax, [rbp+SRWLock]
0x1800053bb  mov     [rsp+130h+var_B0], rax
0x1800053c3  lea     rax, [rbp+var_68]
0x1800053c7  mov     [rsp+130h+var_B8], rax
0x1800053cc  lea     rax, [rbp+var_60]
0x1800053d0  mov     [rsp+130h+var_C0], rax
0x1800053d5  lea     rax, [rbp+arg_8]
0x1800053d9  mov     [rsp+130h+var_C8], rax
0x1800053de  lea     rax, [rbp+var_58]
0x1800053e2  mov     [rsp+130h+var_D0], rax
0x1800053e7  lea     rax, [rbp+arg_10]
0x1800053eb  mov     [rsp+130h+var_D8], rax
0x1800053f0  lea     rax, [rbp+var_50]
0x1800053f4  mov     [rsp+130h+var_E0], rax
0x1800053f9  lea     rax, [rbp+arg_18]
0x1800053fd  mov     [rsp+130h+var_E8], rax
0x180005402  lea     rax, [rbp+var_48]
0x180005406  mov     [rsp+130h+var_F0], rax
0x18000540b  lea     rax, [rbp+var_80]
0x18000540f  mov     [rsp+130h+var_F8], rax
0x180005414  lea     rax, [rbp+var_40]
0x180005418  mov     [rsp+130h+var_100], rax
0x18000541d  lea     rax, [rbp+var_7C]
0x180005421  mov     [rsp+130h+var_108], rax
0x180005426  lea     rax, [rbp+var_38]
0x18000542a  mov     [rsp+130h+var_110], rax
0x18000542f  mov     [rbp+var_38], 1000000h
0x180005437  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000543c  jmp     loc_1800055CE
0x180005441  call    ?Provider@EcoScoreTaskTelemetry@@SAPEBU_tlgProvider_t@@XZ; EcoScoreTaskTelemetry::Provider(void)
0x180005446  mov     r9, rax
0x180005449  mov     ecx, [rax]
0x18000544b  cmp     ecx, 2
0x18000544e  jbe     loc_1800055CE
0x180005454  mov     rax, [rax+18h]
0x180005458  mov     rdx, 200000000000h
0x180005462  mov     rcx, [r9+10h]
0x180005466  test    rdx, rcx
0x180005469  jz      loc_1800055CE
0x18000546f  mov     rcx, rax
0x180005472  and     rcx, rdx
0x180005475  cmp     rcx, rax
0x180005478  jnz     loc_1800055CE
0x18000547e  mov     rax, [rbx+30h]
0x180005482  lea     rdx, word_18000B03E
0x180005489  mov     [rbp+var_38], rax
0x18000548d  mov     rcx, r9
0x180005490  mov     eax, [rbx+44h]
0x180005493  mov     dword ptr [rbp+SRWLock], eax
0x180005496  mov     eax, [rbx+10h]
0x180005499  mov     [rbp+arg_8], eax
0x18000549c  mov     rax, [rbx+78h]
0x1800054a0  mov     [rbp+var_40], rax
0x1800054a4  mov     rax, [rbx+70h]
0x1800054a8  mov     r8, [rdi+110h]
0x1800054af  mov     [rbp+var_48], rax
0x1800054b3  add     r8, 8
0x1800054b7  mov     eax, [rbx+68h]
0x1800054ba  mov     [rbp+arg_10], eax
0x1800054bd  mov     rax, [rbx+60h]
0x1800054c1  mov     [rbp+var_50], rax
0x1800054c5  mov     rax, [rbx+58h]
0x1800054c9  mov     [rbp+var_58], rax
0x1800054cd  mov     eax, [rbx+50h]
0x1800054d0  mov     [rbp+arg_18], eax
0x1800054d3  mov     rax, [rbx+48h]
0x1800054d7  mov     [rbp+var_60], rax
0x1800054db  mov     eax, [rbx+20h]
0x1800054de  mov     [rbp+var_7C], eax
0x1800054e1  mov     rax, [rbx+18h]
0x1800054e5  mov     [rbp+var_68], rax
0x1800054e9  mov     eax, [rbx]
0x1800054eb  mov     [rbp+var_80], eax
0x1800054ee  mov     rax, [rbx+80h]
0x1800054f5  mov     [rbp+var_30], rax
0x1800054f9  mov     eax, [rbx+40h]
0x1800054fc  mov     dword ptr [rbp+var_78], eax
0x1800054ff  mov     rax, [rbx+38h]
0x180005503  mov     [rbp+var_28], rax
0x180005507  mov     eax, [rbx+8]
0x18000550a  mov     dword ptr [rbp+var_70], eax
0x18000550d  lea     rax, [rbp+var_38]
0x180005511  mov     [rsp+130h+var_88], rax
0x180005519  lea     rax, [rbp+SRWLock]
0x18000551d  mov     [rsp+130h+var_90], rax
0x180005525  lea     rax, [rbp+arg_8]
0x180005529  mov     [rsp+130h+var_98], rax
0x180005531  lea     rax, [rbp+var_40]
0x180005535  mov     [rsp+130h+var_A0], rax
0x18000553d  lea     rax, [rbp+var_48]
0x180005541  mov     [rsp+130h+var_A8], rax
0x180005549  lea     rax, [rbp+arg_10]
0x18000554d  mov     [rsp+130h+var_B0], rax
0x180005555  lea     rax, [rbp+var_50]
0x180005559  mov     [rsp+130h+var_B8], rax
0x18000555e  lea     rax, [rbp+var_58]
0x180005562  mov     [rsp+130h+var_C0], rax
0x180005567  lea     rax, [rbp+arg_18]
0x18000556b  mov     [rsp+130h+var_C8], rax
0x180005570  lea     rax, [rbp+var_60]
0x180005574  mov     [rsp+130h+var_D0], rax
0x180005579  lea     rax, [rbp+var_7C]
0x18000557d  mov     [rsp+130h+var_D8], rax
0x180005582  lea     rax, [rbp+var_68]
0x180005586  mov     [rsp+130h+var_E0], rax
0x18000558b  lea     rax, [rbp+var_80]
0x18000558f  mov     [rsp+130h+var_E8], rax
0x180005594  lea     rax, [rbp+var_30]
0x180005598  mov     [rsp+130h+var_F0], rax
0x18000559d  lea     rax, [rbp+var_78]
0x1800055a1  mov     [rsp+130h+var_F8], rax
0x1800055a6  lea     rax, [rbp+var_28]
0x1800055aa  mov     [rsp+130h+var_100], rax
0x1800055af  lea     rax, [rbp+var_70]
0x1800055b3  mov     [rsp+130h+var_108], rax
0x1800055b8  lea     rax, [rbp+var_20]
0x1800055bc  mov     [rsp+130h+var_110], rax
0x1800055c1  mov     [rbp+var_20], 1000000h
0x1800055c9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800055ce  lea     rdx, [rbp+SRWLock]
0x1800055d2  mov     rcx, rdi
0x1800055d5  call    ?LockExclusive@?$ActivityBase@VEcoScoreTaskTelemetry@@$00$0CAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<EcoScoreTaskTelemetry,1,35184372088832,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800055da  mov     rax, [rdi+110h]
0x1800055e1  mov     edx, [rbx+8]
0x1800055e4  lea     rcx, [rax+50h]; this
0x1800055e8  cmp     edx, [rcx+8]
0x1800055eb  jz      short loc_180005600
0x1800055ed  cmp     edx, [rax+48h]
0x1800055f0  jnz     short loc_1800055F8
0x1800055f2  cmp     dword ptr [rax+48h], 0
0x1800055f6  jl      short loc_180005600
0x1800055f8  mov     rdx, rbx; struct wil::FailureInfo *
0x1800055fb  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x180005600  mov     rcx, [rbp+SRWLock]; SRWLock
0x180005604  test    rcx, rcx
0x180005607  jz      short loc_18000560F
0x180005609  call    cs:__imp_ReleaseSRWLockExclusive
0x18000560f  mov     al, 1
0x180005611  add     rsp, 120h
0x180005618  pop     rdi
0x180005619  pop     rbx
0x18000561a  pop     rbp
0x18000561b  retn
```
