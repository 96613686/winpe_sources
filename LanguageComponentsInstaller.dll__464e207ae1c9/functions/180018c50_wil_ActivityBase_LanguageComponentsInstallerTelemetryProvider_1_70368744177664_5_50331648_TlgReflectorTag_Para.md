# wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(wil::FailureInfo const &)

- ea: `0x180018c50`
- end: `0x180018fbc`
- name: `?NotifyFailure@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@UEAA_NAEBUFailureInfo@2@@Z`
- size: `876`
- prototype: `char __fastcall(_QWORD *, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1800019fc`
- `0x180001ca0`
- `0x1800095b4`
- `0x180018b8c`
- `0x180018c50`
- `0x1800195c0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018fa9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180018fa9`

## pseudocode

```c
char __fastcall wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(
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
  __int64 v17; // [rsp+B8h] [rbp-78h] BYREF
  __int64 v18; // [rsp+C0h] [rbp-70h] BYREF
  __int64 v19; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v20; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v21; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v22; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v23; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v24; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v25; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v26; // [rsp+100h] [rbp-30h] BYREF
  __int64 v27; // [rsp+108h] [rbp-28h] BYREF
  __int64 v28[4]; // [rsp+110h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+140h] [rbp+10h] BYREF
  __int64 v30; // [rsp+148h] [rbp+18h] BYREF
  __int64 v31; // [rsp+150h] [rbp+20h] BYREF
  __int64 v32; // [rsp+158h] [rbp+28h] BYREF

  if ( (a2[1] & 2) == 0 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, _QWORD))(*a1 + 16LL))(a1, (unsigned int)a2[4]) )
    {
      v8 = LanguageComponentsInstallerTelemetryProvider::Provider();
      v9 = (__int64)v8;
      if ( *(_DWORD *)v8 > 2u )
      {
        v10 = *((_QWORD *)v8 + 3);
        if ( (*(_QWORD *)(v9 + 16) & 0x400000000000LL) != 0 && (v10 & 0x400000000000LL) == v10 )
        {
          v25 = *((_QWORD *)a2 + 6);
          LODWORD(SRWLock) = a2[17];
          LODWORD(v30) = a2[4];
          v24 = *((_QWORD *)a2 + 15);
          v11 = a1[34];
          v23 = *((_QWORD *)a2 + 14);
          LODWORD(v31) = a2[26];
          v22 = *((_QWORD *)a2 + 12);
          v21 = *((_QWORD *)a2 + 11);
          LODWORD(v32) = a2[20];
          v20 = *((_QWORD *)a2 + 9);
          v16 = a2[8];
          v19 = *((_QWORD *)a2 + 3);
          v15 = *a2;
          v26 = *((_QWORD *)a2 + 16);
          LODWORD(v17) = a2[16];
          v27 = *((_QWORD *)a2 + 7);
          LODWORD(v18) = a2[2];
          v28[0] = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v9,
            (int)&byte_18002EF29,
            v11 + 8,
            v9,
            (__int64)v28,
            (__int64)&v18,
            (const unsigned __int16 **)&v27,
            (__int64)&v17,
            (const unsigned __int16 **)&v26,
            (__int64)&v15,
            (__int64 **)&v19,
            (__int64)&v16,
            (const unsigned __int16 **)&v20,
            (__int64)&v32,
            (const unsigned __int16 **)&v21,
            (__int64 **)&v22,
            (__int64)&v31,
            (const unsigned __int16 **)&v23,
            (__int64 **)&v24,
            (__int64)&v30,
            (__int64)&SRWLock,
            (const unsigned __int16 **)&v25);
        }
      }
    }
    else
    {
      v4 = LanguageComponentsInstallerTelemetryProvider::Provider();
      v5 = (__int64)v4;
      if ( *(_DWORD *)v4 > 2u )
      {
        v6 = *((_QWORD *)v4 + 3);
        if ( (*(_QWORD *)(v5 + 16) & 0x600000000000LL) != 0 && (v6 & 0x600000000000LL) == v6 )
        {
          v7 = a1[34];
          v18 = *((_QWORD *)a2 + 15);
          v17 = *((_QWORD *)a2 + 14);
          LODWORD(SRWLock) = a2[26];
          v19 = *((_QWORD *)a2 + 12);
          v20 = *((_QWORD *)a2 + 11);
          LODWORD(v30) = a2[20];
          v21 = *((_QWORD *)a2 + 9);
          LODWORD(v31) = a2[8];
          v22 = *((_QWORD *)a2 + 3);
          LODWORD(v32) = *a2;
          v23 = *((_QWORD *)a2 + 16);
          v15 = a2[16];
          v24 = *((_QWORD *)a2 + 7);
          v16 = a2[2];
          v25 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            v5,
            (int)&dword_18002F40C,
            v7 + 8,
            v5,
            (__int64)&v25,
            (__int64)&v16,
            (const unsigned __int16 **)&v24,
            (__int64)&v15,
            (const unsigned __int16 **)&v23,
            (__int64)&v32,
            (__int64 **)&v22,
            (__int64)&v31,
            (const unsigned __int16 **)&v21,
            (__int64)&v30,
            (const unsigned __int16 **)&v20,
            (__int64 **)&v19,
            (__int64)&SRWLock,
            (const unsigned __int16 **)&v17,
            (__int64 **)&v18);
        }
      }
    }
  }
  wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
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
0x180018c50  push    rbp
0x180018c52  push    rbx
0x180018c53  push    rdi
0x180018c54  lea     rbp, [rsp+10h]
0x180018c59  sub     rsp, 120h
0x180018c60  test    byte ptr [rdx+4], 2
0x180018c64  mov     rbx, rdx
0x180018c67  mov     rdi, rcx
0x180018c6a  jnz     loc_180018F6E
0x180018c70  mov     rax, [rcx]
0x180018c73  mov     edx, [rdx+10h]
0x180018c76  mov     rax, [rax+10h]
0x180018c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c7f  test    al, al
0x180018c81  jnz     loc_180018DE1
0x180018c87  call    ?Provider@LanguageComponentsInstallerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; LanguageComponentsInstallerTelemetryProvider::Provider(void)
0x180018c8c  mov     r9, rax
0x180018c8f  mov     ecx, [rax]
0x180018c91  cmp     ecx, 2
0x180018c94  jbe     loc_180018F6E
0x180018c9a  mov     rax, [rax+18h]
0x180018c9e  mov     rdx, 600000000000h
0x180018ca8  mov     rcx, [r9+10h]
0x180018cac  test    rdx, rcx
0x180018caf  jz      loc_180018F6E
0x180018cb5  mov     rcx, rax
0x180018cb8  and     rcx, rdx
0x180018cbb  cmp     rcx, rax
0x180018cbe  jnz     loc_180018F6E
0x180018cc4  mov     rax, [rbx+78h]
0x180018cc8  lea     rdx, dword_18002F40C; int
0x180018ccf  mov     r8, [rdi+110h]
0x180018cd6  mov     rcx, r9; int
0x180018cd9  mov     [rbp+var_70], rax
0x180018cdd  add     r8, 8; int
0x180018ce1  mov     rax, [rbx+70h]
0x180018ce5  mov     [rbp+var_78], rax
0x180018ce9  mov     eax, [rbx+68h]
0x180018cec  mov     dword ptr [rbp+SRWLock], eax
0x180018cef  mov     rax, [rbx+60h]
0x180018cf3  mov     [rbp+var_68], rax
0x180018cf7  mov     rax, [rbx+58h]
0x180018cfb  mov     [rbp+var_60], rax
0x180018cff  mov     eax, [rbx+50h]
0x180018d02  mov     dword ptr [rbp+arg_8], eax
0x180018d05  mov     rax, [rbx+48h]
0x180018d09  mov     [rbp+var_58], rax
0x180018d0d  mov     eax, [rbx+20h]
0x180018d10  mov     dword ptr [rbp+arg_10], eax
0x180018d13  mov     rax, [rbx+18h]
0x180018d17  mov     [rbp+var_50], rax
0x180018d1b  mov     eax, [rbx]
0x180018d1d  mov     dword ptr [rbp+arg_18], eax
0x180018d20  mov     rax, [rbx+80h]
0x180018d27  mov     [rbp+var_48], rax
0x180018d2b  mov     eax, [rbx+40h]
0x180018d2e  mov     dword ptr [rbp+var_80], eax
0x180018d31  mov     rax, [rbx+38h]
0x180018d35  mov     [rbp+var_40], rax
0x180018d39  mov     eax, [rbx+8]
0x180018d3c  mov     dword ptr [rbp+var_80+4], eax
0x180018d3f  lea     rax, [rbp+var_70]
0x180018d43  mov     [rsp+130h+var_A0], rax; __int64
0x180018d4b  lea     rax, [rbp+var_78]
0x180018d4f  mov     [rsp+130h+var_A8], rax; __int64
0x180018d57  lea     rax, [rbp+SRWLock]
0x180018d5b  mov     [rsp+130h+var_B0], rax; __int64
0x180018d63  lea     rax, [rbp+var_68]
0x180018d67  mov     [rsp+130h+var_B8], rax; __int64
0x180018d6c  lea     rax, [rbp+var_60]
0x180018d70  mov     [rsp+130h+var_C0], rax; __int64
0x180018d75  lea     rax, [rbp+arg_8]
0x180018d79  mov     [rsp+130h+var_C8], rax; __int64
0x180018d7e  lea     rax, [rbp+var_58]
0x180018d82  mov     [rsp+130h+var_D0], rax; __int64
0x180018d87  lea     rax, [rbp+arg_10]
0x180018d8b  mov     [rsp+130h+var_D8], rax; __int64
0x180018d90  lea     rax, [rbp+var_50]
0x180018d94  mov     [rsp+130h+var_E0], rax; __int64
0x180018d99  lea     rax, [rbp+arg_18]
0x180018d9d  mov     [rsp+130h+var_E8], rax; __int64
0x180018da2  lea     rax, [rbp+var_48]
0x180018da6  mov     [rsp+130h+var_F0], rax; __int64
0x180018dab  lea     rax, [rbp+var_80]
0x180018daf  mov     [rsp+130h+var_F8], rax; __int64
0x180018db4  lea     rax, [rbp+var_40]
0x180018db8  mov     [rsp+130h+var_100], rax; __int64
0x180018dbd  lea     rax, [rbp+var_80+4]
0x180018dc1  mov     [rsp+130h+var_108], rax; __int64
0x180018dc6  lea     rax, [rbp+var_38]
0x180018dca  mov     [rsp+130h+var_110], rax; __int64
0x180018dcf  mov     [rbp+var_38], 1000000h
0x180018dd7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180018ddc  jmp     loc_180018F6E
0x180018de1  call    ?Provider@LanguageComponentsInstallerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; LanguageComponentsInstallerTelemetryProvider::Provider(void)
0x180018de6  mov     r9, rax
0x180018de9  mov     ecx, [rax]
0x180018deb  cmp     ecx, 2
0x180018dee  jbe     loc_180018F6E
0x180018df4  mov     rax, [rax+18h]
0x180018df8  mov     rdx, 400000000000h
0x180018e02  mov     rcx, [r9+10h]
0x180018e06  test    rdx, rcx
0x180018e09  jz      loc_180018F6E
0x180018e0f  mov     rcx, rax
0x180018e12  and     rcx, rdx
0x180018e15  cmp     rcx, rax
0x180018e18  jnz     loc_180018F6E
0x180018e1e  mov     rax, [rbx+30h]
0x180018e22  lea     rdx, byte_18002EF29; int
0x180018e29  mov     [rbp+var_38], rax
0x180018e2d  mov     rcx, r9; int
0x180018e30  mov     eax, [rbx+44h]
0x180018e33  mov     dword ptr [rbp+SRWLock], eax
0x180018e36  mov     eax, [rbx+10h]
0x180018e39  mov     dword ptr [rbp+arg_8], eax
0x180018e3c  mov     rax, [rbx+78h]
0x180018e40  mov     [rbp+var_40], rax
0x180018e44  mov     rax, [rbx+70h]
0x180018e48  mov     r8, [rdi+110h]
0x180018e4f  mov     [rbp+var_48], rax
0x180018e53  add     r8, 8; int
0x180018e57  mov     eax, [rbx+68h]
0x180018e5a  mov     dword ptr [rbp+arg_10], eax
0x180018e5d  mov     rax, [rbx+60h]
0x180018e61  mov     [rbp+var_50], rax
0x180018e65  mov     rax, [rbx+58h]
0x180018e69  mov     [rbp+var_58], rax
0x180018e6d  mov     eax, [rbx+50h]
0x180018e70  mov     dword ptr [rbp+arg_18], eax
0x180018e73  mov     rax, [rbx+48h]
0x180018e77  mov     [rbp+var_60], rax
0x180018e7b  mov     eax, [rbx+20h]
0x180018e7e  mov     dword ptr [rbp+var_80+4], eax
0x180018e81  mov     rax, [rbx+18h]
0x180018e85  mov     [rbp+var_68], rax
0x180018e89  mov     eax, [rbx]
0x180018e8b  mov     dword ptr [rbp+var_80], eax
0x180018e8e  mov     rax, [rbx+80h]
0x180018e95  mov     [rbp+var_30], rax
0x180018e99  mov     eax, [rbx+40h]
0x180018e9c  mov     dword ptr [rbp+var_78], eax
0x180018e9f  mov     rax, [rbx+38h]
0x180018ea3  mov     [rbp+var_28], rax
0x180018ea7  mov     eax, [rbx+8]
0x180018eaa  mov     dword ptr [rbp+var_70], eax
0x180018ead  lea     rax, [rbp+var_38]
0x180018eb1  mov     [rsp+130h+var_88], rax; __int64
0x180018eb9  lea     rax, [rbp+SRWLock]
0x180018ebd  mov     [rsp+130h+var_90], rax; __int64
0x180018ec5  lea     rax, [rbp+arg_8]
0x180018ec9  mov     [rsp+130h+var_98], rax; __int64
0x180018ed1  lea     rax, [rbp+var_40]
0x180018ed5  mov     [rsp+130h+var_A0], rax; __int64
0x180018edd  lea     rax, [rbp+var_48]
0x180018ee1  mov     [rsp+130h+var_A8], rax; __int64
0x180018ee9  lea     rax, [rbp+arg_10]
0x180018eed  mov     [rsp+130h+var_B0], rax; __int64
0x180018ef5  lea     rax, [rbp+var_50]
0x180018ef9  mov     [rsp+130h+var_B8], rax; __int64
0x180018efe  lea     rax, [rbp+var_58]
0x180018f02  mov     [rsp+130h+var_C0], rax; __int64
0x180018f07  lea     rax, [rbp+arg_18]
0x180018f0b  mov     [rsp+130h+var_C8], rax; __int64
0x180018f10  lea     rax, [rbp+var_60]
0x180018f14  mov     [rsp+130h+var_D0], rax; __int64
0x180018f19  lea     rax, [rbp+var_80+4]
0x180018f1d  mov     [rsp+130h+var_D8], rax; __int64
0x180018f22  lea     rax, [rbp+var_68]
0x180018f26  mov     [rsp+130h+var_E0], rax; __int64
0x180018f2b  lea     rax, [rbp+var_80]
0x180018f2f  mov     [rsp+130h+var_E8], rax; __int64
0x180018f34  lea     rax, [rbp+var_30]
0x180018f38  mov     [rsp+130h+var_F0], rax; __int64
0x180018f3d  lea     rax, [rbp+var_78]
0x180018f41  mov     [rsp+130h+var_F8], rax; __int64
0x180018f46  lea     rax, [rbp+var_28]
0x180018f4a  mov     [rsp+130h+var_100], rax; __int64
0x180018f4f  lea     rax, [rbp+var_70]
0x180018f53  mov     [rsp+130h+var_108], rax; __int64
0x180018f58  lea     rax, [rbp+var_20]
0x180018f5c  mov     [rsp+130h+var_110], rax; __int64
0x180018f61  mov     [rbp+var_20], 1000000h
0x180018f69  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180018f6e  lea     rdx, [rbp+SRWLock]
0x180018f72  mov     rcx, rdi
0x180018f75  call    ?LockExclusive@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180018f7a  mov     rax, [rdi+110h]
0x180018f81  mov     edx, [rbx+8]
0x180018f84  lea     rcx, [rax+50h]; this
0x180018f88  cmp     edx, [rcx+8]
0x180018f8b  jz      short loc_180018FA0
0x180018f8d  cmp     edx, [rax+48h]
0x180018f90  jnz     short loc_180018F98
0x180018f92  cmp     dword ptr [rax+48h], 0
0x180018f96  jl      short loc_180018FA0
0x180018f98  mov     rdx, rbx; struct wil::FailureInfo *
0x180018f9b  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x180018fa0  mov     rcx, [rbp+SRWLock]; SRWLock
0x180018fa4  test    rcx, rcx
0x180018fa7  jz      short loc_180018FAF
0x180018fa9  call    cs:__imp_ReleaseSRWLockExclusive
0x180018faf  mov     al, 1
0x180018fb1  add     rsp, 120h
0x180018fb8  pop     rdi
0x180018fb9  pop     rbx
0x180018fba  pop     rbp
0x180018fbb  retn
```
