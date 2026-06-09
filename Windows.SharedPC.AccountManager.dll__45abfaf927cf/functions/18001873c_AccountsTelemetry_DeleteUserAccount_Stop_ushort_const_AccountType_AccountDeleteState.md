# AccountsTelemetry::DeleteUserAccount::Stop(ushort const *,AccountType,AccountDeleteState)

- ea: `0x18001873c`
- end: `0x1800189cd`
- name: `?Stop@DeleteUserAccount@AccountsTelemetry@@QEAAXPEBGW4AccountType@@W4AccountDeleteState@@@Z`
- size: `657`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180015ee0`

## callees

- `0x180001b0c`
- `0x180001cc8`
- `0x180001fe0`
- `0x18000db78`
- `0x18000e00c`
- `0x18000ed9c`
- `0x18001873c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001894d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001894d`

## pseudocode

```c
__int64 __fastcall AccountsTelemetry::DeleteUserAccount::Stop(__int64 a1, const WCHAR *a2, int a3, int a4)
{
  __int64 v4; // rdi
  int v9; // eax
  int *v10; // rdi
  const struct _tlgProvider_t *v11; // rax
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // r8
  const struct _tlgProvider_t *v16; // rax
  __int64 v17; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v19; // r8
  __int64 v20; // r9
  int v22; // [rsp+C0h] [rbp-80h] BYREF
  DWORD v23; // [rsp+C4h] [rbp-7Ch] BYREF
  int v24; // [rsp+C8h] [rbp-78h] BYREF
  int v25; // [rsp+CCh] [rbp-74h] BYREF
  int v26; // [rsp+D0h] [rbp-70h] BYREF
  int v27; // [rsp+D4h] [rbp-6Ch] BYREF
  int v28; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v29; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v30; // [rsp+E8h] [rbp-58h] BYREF
  const WCHAR *v31; // [rsp+F0h] [rbp-50h] BYREF
  const WCHAR *v32; // [rsp+F8h] [rbp-48h] BYREF
  const unsigned __int16 *v33; // [rsp+100h] [rbp-40h] BYREF
  const WCHAR *v34; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v35; // [rsp+110h] [rbp-30h] BYREF
  const unsigned __int16 *v36; // [rsp+118h] [rbp-28h] BYREF
  const WCHAR *v37; // [rsp+120h] [rbp-20h] BYREF
  const unsigned __int16 *v38; // [rsp+128h] [rbp-18h] BYREF
  const unsigned __int16 *v39; // [rsp+130h] [rbp-10h] BYREF
  int v40; // [rsp+180h] [rbp+40h] BYREF

  v4 = *(_QWORD *)(a1 + 272);
  v9 = *(_DWORD *)(v4 + 72);
  if ( v9 < 0 && (v10 = (int *)(v4 + 80), v9 == v10[2]) && v10 )
  {
    wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = SharedPCAccountManagerLogging::Provider();
    v14 = (__int64)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL, v13, v11) )
    {
      v32 = (const WCHAR *)*((_QWORD *)v10 + 15);
      v33 = (const unsigned __int16 *)*((_QWORD *)v10 + 14);
      v26 = v10[26];
      v15 = *(_QWORD *)(a1 + 272);
      v34 = (const WCHAR *)*((_QWORD *)v10 + 12);
      v35 = (const unsigned __int16 *)*((_QWORD *)v10 + 11);
      v27 = v10[20];
      v36 = (const unsigned __int16 *)*((_QWORD *)v10 + 9);
      v28 = v10[8];
      v37 = (const WCHAR *)*((_QWORD *)v10 + 3);
      v22 = *v10;
      v38 = (const unsigned __int16 *)*((_QWORD *)v10 + 16);
      v23 = v10[16];
      v39 = (const unsigned __int16 *)*((_QWORD *)v10 + 7);
      v24 = v10[2];
      v29 = 0x1000000;
      v30 = 0x1000000;
      v40 = a4;
      v25 = a3;
      v31 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v14,
        (__int64)byte_18002CCD3,
        v15 + 8,
        v14,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v24,
        &v39,
        (__int64)&v23,
        &v38,
        (__int64)&v22,
        &v37,
        (__int64)&v28,
        &v36,
        (__int64)&v27,
        &v35,
        &v34,
        (__int64)&v26,
        &v33,
        &v32,
        &v31,
        (__int64)&v25,
        (__int64)&v40);
    }
  }
  else
  {
    wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v16 = SharedPCAccountManagerLogging::Provider();
    v17 = (__int64)v16;
    if ( *(_DWORD *)v16 > 5u && (unsigned __int8)tlgKeywordOn(v16, 0x400000000000LL, v13, v14) )
    {
      v40 = a4;
      v24 = a3;
      v30 = (__int64)a2;
      CurrentThreadId = GetCurrentThreadId();
      v19 = *(_QWORD *)(a1 + 272);
      v23 = CurrentThreadId;
      v22 = *(_DWORD *)(v19 + 72);
      v29 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v17,
        (__int64)&dword_18002D3F4,
        v19 + 8,
        v20,
        (__int64)&v29,
        (__int64)&v22,
        (__int64)&v23,
        (const WCHAR **)&v30,
        (__int64)&v24,
        (__int64)&v40);
    }
  }
  return wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
           a1,
           v12,
           v13,
           v14);
}

```

## disassembly

```asm
0x18001873c  push    rbp
0x18001873e  push    rbx
0x18001873f  push    rsi
0x180018740  push    rdi
0x180018741  push    r14
0x180018743  push    r15
0x180018745  lea     rbp, [rsp-8]
0x18001874a  sub     rsp, 148h
0x180018751  mov     rdi, [rcx+110h]
0x180018758  mov     esi, r9d
0x18001875b  mov     r14d, r8d
0x18001875e  mov     r15, rdx
0x180018761  mov     rbx, rcx
0x180018764  mov     eax, [rdi+48h]
0x180018767  test    eax, eax
0x180018769  jns     loc_180018914
0x18001876f  add     rdi, 50h ; 'P'
0x180018773  cmp     eax, [rdi+8]
0x180018776  jnz     loc_180018914
0x18001877c  test    rdi, rdi
0x18001877f  jz      loc_180018914
0x180018785  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x18001878a  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x18001878f  mov     r9, rax
0x180018792  mov     ecx, [rax]
0x180018794  cmp     ecx, 5
0x180018797  jbe     loc_1800189B6
0x18001879d  mov     rdx, 400000000000h
0x1800187a7  mov     rcx, rax
0x1800187aa  call    _tlgKeywordOn
0x1800187af  test    al, al
0x1800187b1  jz      loc_1800189B6
0x1800187b7  mov     rax, [rdi+78h]
0x1800187bb  lea     rdx, byte_18002CCD3
0x1800187c2  mov     [rbp+30h+var_78], rax
0x1800187c6  mov     rcx, r9
0x1800187c9  mov     rax, [rdi+70h]
0x1800187cd  mov     [rbp+30h+var_70], rax
0x1800187d1  mov     eax, [rdi+68h]
0x1800187d4  mov     [rbp+30h+var_A0], eax
0x1800187d7  mov     rax, [rdi+60h]
0x1800187db  mov     r8, [rbx+110h]
0x1800187e2  mov     [rbp+30h+var_68], rax
0x1800187e6  add     r8, 8
0x1800187ea  mov     rax, [rdi+58h]
0x1800187ee  mov     [rbp+30h+var_60], rax
0x1800187f2  mov     eax, [rdi+50h]
0x1800187f5  mov     [rbp+30h+var_9C], eax
0x1800187f8  mov     rax, [rdi+48h]
0x1800187fc  mov     [rbp+30h+var_58], rax
0x180018800  mov     eax, [rdi+20h]
0x180018803  mov     [rbp+30h+var_98], eax
0x180018806  mov     rax, [rdi+18h]
0x18001880a  mov     [rbp+30h+var_50], rax
0x18001880e  mov     eax, [rdi]
0x180018810  mov     [rbp+30h+var_B0], eax
0x180018813  mov     rax, [rdi+80h]
0x18001881a  mov     [rbp+30h+var_48], rax
0x18001881e  mov     eax, [rdi+40h]
0x180018821  mov     [rbp+30h+var_AC], eax
0x180018824  mov     rax, [rdi+38h]
0x180018828  mov     [rbp+30h+var_40], rax
0x18001882c  mov     eax, [rdi+8]
0x18001882f  mov     [rbp+30h+var_A8], eax
0x180018832  mov     eax, 1000000h
0x180018837  mov     [rbp+30h+var_90], rax
0x18001883b  mov     [rbp+30h+var_88], rax
0x18001883f  lea     rax, [rbp+30h+arg_0]
0x180018843  mov     [rsp+170h+var_C0], rax
0x18001884b  lea     rax, [rbp+30h+var_A4]
0x18001884f  mov     [rsp+170h+var_C8], rax
0x180018857  lea     rax, [rbp+30h+var_80]
0x18001885b  mov     [rsp+170h+var_D0], rax
0x180018863  lea     rax, [rbp+30h+var_78]
0x180018867  mov     [rsp+170h+var_D8], rax
0x18001886f  lea     rax, [rbp+30h+var_70]
0x180018873  mov     [rsp+170h+var_E0], rax
0x18001887b  lea     rax, [rbp+30h+var_A0]
0x18001887f  mov     [rsp+170h+var_E8], rax
0x180018887  lea     rax, [rbp+30h+var_68]
0x18001888b  mov     [rsp+170h+var_F0], rax
0x180018893  lea     rax, [rbp+30h+var_60]
0x180018897  mov     [rsp+170h+var_F8], rax
0x18001889c  lea     rax, [rbp+30h+var_9C]
0x1800188a0  mov     [rsp+170h+var_100], rax
0x1800188a5  lea     rax, [rbp+30h+var_58]
0x1800188a9  mov     [rsp+170h+var_108], rax
0x1800188ae  lea     rax, [rbp+30h+var_98]
0x1800188b2  mov     [rsp+170h+var_110], rax
0x1800188b7  lea     rax, [rbp+30h+var_50]
0x1800188bb  mov     [rsp+170h+var_118], rax
0x1800188c0  lea     rax, [rbp+30h+var_B0]
0x1800188c4  mov     [rsp+170h+var_120], rax
0x1800188c9  lea     rax, [rbp+30h+var_48]
0x1800188cd  mov     [rsp+170h+var_128], rax
0x1800188d2  lea     rax, [rbp+30h+var_AC]
0x1800188d6  mov     [rsp+170h+var_130], rax
0x1800188db  lea     rax, [rbp+30h+var_40]
0x1800188df  mov     [rsp+170h+var_138], rax
0x1800188e4  lea     rax, [rbp+30h+var_A8]
0x1800188e8  mov     [rsp+170h+var_140], rax
0x1800188ed  lea     rax, [rbp+30h+var_90]
0x1800188f1  mov     [rsp+170h+var_148], rax
0x1800188f6  lea     rax, [rbp+30h+var_88]
0x1800188fa  mov     [rsp+170h+var_150], rax
0x1800188ff  mov     [rbp+30h+arg_0], esi
0x180018902  mov     [rbp+30h+var_A4], r14d
0x180018906  mov     [rbp+30h+var_80], r15
0x18001890a  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456644@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001890f  jmp     loc_1800189B6
0x180018914  call    ?zInternalStop@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180018919  call    ?Provider@SharedPCAccountManagerLogging@@SAPEBU_tlgProvider_t@@XZ; SharedPCAccountManagerLogging::Provider(void)
0x18001891e  mov     rdi, rax
0x180018921  mov     ecx, [rax]
0x180018923  cmp     ecx, 5
0x180018926  jbe     loc_1800189B6
0x18001892c  mov     rdx, 400000000000h
0x180018936  mov     rcx, rax
0x180018939  call    _tlgKeywordOn
0x18001893e  test    al, al
0x180018940  jz      short loc_1800189B6
0x180018942  mov     [rbp+30h+arg_0], esi
0x180018945  mov     [rbp+30h+var_A8], r14d
0x180018949  mov     [rbp+30h+var_88], r15
0x18001894d  call    cs:__imp_GetCurrentThreadId
0x180018953  mov     r8, [rbx+110h]
0x18001895a  lea     rdx, dword_18002D3F4
0x180018961  mov     [rbp+30h+var_AC], eax
0x180018964  mov     rcx, rdi
0x180018967  mov     eax, [r8+48h]
0x18001896b  add     r8, 8
0x18001896f  mov     [rbp+30h+var_B0], eax
0x180018972  mov     eax, 1000000h
0x180018977  mov     [rbp+30h+var_90], rax
0x18001897b  lea     rax, [rbp+30h+arg_0]
0x18001897f  mov     [rsp+170h+var_128], rax
0x180018984  lea     rax, [rbp+30h+var_A8]
0x180018988  mov     [rsp+170h+var_130], rax
0x18001898d  lea     rax, [rbp+30h+var_88]
0x180018991  mov     [rsp+170h+var_138], rax
0x180018996  lea     rax, [rbp+30h+var_AC]
0x18001899a  mov     [rsp+170h+var_140], rax
0x18001899f  lea     rax, [rbp+30h+var_B0]
0x1800189a3  mov     [rsp+170h+var_148], rax
0x1800189a8  lea     rax, [rbp+30h+var_90]
0x1800189ac  mov     [rsp+170h+var_150], rax
0x1800189b1  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@44@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800189b6  mov     rcx, rbx
0x1800189b9  add     rsp, 148h
0x1800189c0  pop     r15
0x1800189c2  pop     r14
0x1800189c4  pop     rdi
0x1800189c5  pop     rsi
0x1800189c6  pop     rbx
0x1800189c7  pop     rbp
0x1800189c8  jmp     ?IgnoreCurrentThread@?$ActivityBase@VSharedPCAccountManagerLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<SharedPCAccountManagerLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
