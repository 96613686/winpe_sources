# wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(wil::FailureInfo const &)

- ea: `0x18002be10`
- end: `0x18002c15c`
- name: `?NotifyFailure@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@UEAA_NAEBUFailureInfo@2@@Z`
- size: `844`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task`

## callees

- `0x180001008`
- `0x18000e880`
- `0x180013ef8`
- `0x180017104`
- `0x1800172bc`
- `0x180018430`
- `0x18002be10`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c149`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002c149`

## pseudocode

```c
char __fastcall wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(
        _QWORD *a1,
        int *a2)
{
  __int64 v4; // rcx
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  int *v8; // rcx
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
  int *v21; // [rsp+C0h] [rbp-70h] BYREF
  int *v22; // [rsp+C8h] [rbp-68h] BYREF
  const unsigned __int16 *v23; // [rsp+D0h] [rbp-60h] BYREF
  const unsigned __int16 *v24; // [rsp+D8h] [rbp-58h] BYREF
  int *v25; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v26; // [rsp+E8h] [rbp-48h] BYREF
  int *v27; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v28; // [rsp+F8h] [rbp-38h] BYREF
  const unsigned __int16 *v29; // [rsp+100h] [rbp-30h] BYREF
  const unsigned __int16 *v30; // [rsp+108h] [rbp-28h] BYREF
  __int64 v31[4]; // [rsp+110h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+140h] [rbp+10h] BYREF
  int v33; // [rsp+148h] [rbp+18h] BYREF
  int v34; // [rsp+150h] [rbp+20h] BYREF
  int v35; // [rsp+158h] [rbp+28h] BYREF

  if ( (a2[1] & 2) == 0 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, _QWORD))(*a1 + 16LL))(a1, (unsigned int)a2[4]) )
    {
      v10 = ServiceHostLogging::Provider(v4);
      if ( *(_DWORD *)v10 > 2u && (unsigned __int8)tlgKeywordOn(v10, 0x400000000000LL, v11, v10) )
      {
        LODWORD(SRWLock) = a2[17];
        v33 = a2[4];
        v13 = (const unsigned __int16 *)*((_QWORD *)a2 + 6);
        v27 = (int *)*((_QWORD *)a2 + 15);
        v14 = a1[34];
        v26 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
        v34 = a2[26];
        v25 = (int *)*((_QWORD *)a2 + 12);
        v24 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
        v35 = a2[20];
        v23 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
        v19 = a2[8];
        v22 = (int *)*((_QWORD *)a2 + 3);
        v18 = *a2;
        v29 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
        LODWORD(v20) = a2[16];
        v30 = (const unsigned __int16 *)*((_QWORD *)a2 + 7);
        LODWORD(v21) = a2[2];
        v28 = (__int64)v13;
        v31[0] = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v12,
          (unsigned __int8 *)byte_18003CC2B,
          (const GUID *)(v14 + 8),
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
          (__int64)&SRWLock,
          (const unsigned __int16 **)&v28);
      }
    }
    else
    {
      v5 = ServiceHostLogging::Provider(v4);
      if ( *(_DWORD *)v5 > 2u && (unsigned __int8)tlgKeywordOn(v5, 0x600000000000LL, v6, v5) )
      {
        v8 = (int *)*((_QWORD *)a2 + 15);
        v9 = a1[34];
        v20 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
        LODWORD(SRWLock) = a2[26];
        v22 = (int *)*((_QWORD *)a2 + 12);
        v23 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
        v33 = a2[20];
        v24 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
        v34 = a2[8];
        v25 = (int *)*((_QWORD *)a2 + 3);
        v35 = *a2;
        v26 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
        v18 = a2[16];
        v27 = (int *)*((_QWORD *)a2 + 7);
        v19 = a2[2];
        v21 = v8;
        v28 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v7,
          (unsigned __int8 *)byte_18003CD63,
          (const GUID *)(v9 + 8),
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
          (__int64)&SRWLock,
          &v20,
          &v21);
      }
    }
  }
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v15 = (_DWORD *)a1[34];
  v16 = a2[2];
  if ( v16 != v15[22] && (v16 != v15[18] || (int)v15[18] >= 0) )
    wil::StoredFailureInfo::SetFailureInfo((wil::StoredFailureInfo *)(v15 + 20), (const struct wil::FailureInfo *)a2);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return 1;
}

```

## disassembly

```asm
0x18002be10  push    rbp
0x18002be12  push    rbx
0x18002be13  push    rdi
0x18002be14  lea     rbp, [rsp+10h]
0x18002be19  sub     rsp, 120h
0x18002be20  test    byte ptr [rdx+4], 2
0x18002be24  mov     rbx, rdx
0x18002be27  mov     rdi, rcx
0x18002be2a  jnz     loc_18002C10E
0x18002be30  mov     rax, [rcx]
0x18002be33  mov     edx, [rdx+10h]
0x18002be36  mov     rax, [rax+10h]
0x18002be3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002be3f  test    al, al
0x18002be41  jnz     loc_18002BF91
0x18002be47  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18002be4c  mov     r9, rax
0x18002be4f  mov     ecx, [rax]
0x18002be51  cmp     ecx, 2
0x18002be54  jbe     loc_18002C10E
0x18002be5a  mov     rdx, 600000000000h
0x18002be64  mov     rcx, rax
0x18002be67  call    _tlgKeywordOn
0x18002be6c  test    al, al
0x18002be6e  jz      loc_18002C10E
0x18002be74  mov     rax, [rbx+70h]
0x18002be78  lea     rdx, byte_18003CD63
0x18002be7f  mov     rcx, [rbx+78h]
0x18002be83  mov     r8, [rdi+110h]
0x18002be8a  mov     [rbp+var_78], rax
0x18002be8e  add     r8, 8
0x18002be92  mov     eax, [rbx+68h]
0x18002be95  mov     dword ptr [rbp+SRWLock], eax
0x18002be98  mov     rax, [rbx+60h]
0x18002be9c  mov     [rbp+var_68], rax
0x18002bea0  mov     rax, [rbx+58h]
0x18002bea4  mov     [rbp+var_60], rax
0x18002bea8  mov     eax, [rbx+50h]
0x18002beab  mov     [rbp+arg_8], eax
0x18002beae  mov     rax, [rbx+48h]
0x18002beb2  mov     [rbp+var_58], rax
0x18002beb6  mov     eax, [rbx+20h]
0x18002beb9  mov     [rbp+arg_10], eax
0x18002bebc  mov     rax, [rbx+18h]
0x18002bec0  mov     [rbp+var_50], rax
0x18002bec4  mov     eax, [rbx]
0x18002bec6  mov     [rbp+arg_18], eax
0x18002bec9  mov     rax, [rbx+80h]
0x18002bed0  mov     [rbp+var_48], rax
0x18002bed4  mov     eax, [rbx+40h]
0x18002bed7  mov     [rbp+var_80], eax
0x18002beda  mov     rax, [rbx+38h]
0x18002bede  mov     [rbp+var_40], rax
0x18002bee2  mov     eax, [rbx+8]
0x18002bee5  mov     [rbp+var_7C], eax
0x18002bee8  lea     rax, [rbp+var_70]
0x18002beec  mov     [rsp+130h+var_A0], rax
0x18002bef4  lea     rax, [rbp+var_78]
0x18002bef8  mov     [rsp+130h+var_A8], rax
0x18002bf00  lea     rax, [rbp+SRWLock]
0x18002bf04  mov     [rsp+130h+var_B0], rax
0x18002bf0c  lea     rax, [rbp+var_68]
0x18002bf10  mov     [rsp+130h+var_B8], rax
0x18002bf15  lea     rax, [rbp+var_60]
0x18002bf19  mov     [rsp+130h+var_C0], rax
0x18002bf1e  lea     rax, [rbp+arg_8]
0x18002bf22  mov     [rsp+130h+var_C8], rax
0x18002bf27  lea     rax, [rbp+var_58]
0x18002bf2b  mov     [rsp+130h+var_D0], rax
0x18002bf30  lea     rax, [rbp+arg_10]
0x18002bf34  mov     [rsp+130h+var_D8], rax
0x18002bf39  lea     rax, [rbp+var_50]
0x18002bf3d  mov     [rsp+130h+var_E0], rax
0x18002bf42  lea     rax, [rbp+arg_18]
0x18002bf46  mov     [rsp+130h+var_E8], rax
0x18002bf4b  lea     rax, [rbp+var_48]
0x18002bf4f  mov     [rsp+130h+var_F0], rax
0x18002bf54  lea     rax, [rbp+var_80]
0x18002bf58  mov     [rsp+130h+var_F8], rax
0x18002bf5d  lea     rax, [rbp+var_40]
0x18002bf61  mov     [rsp+130h+var_100], rax
0x18002bf66  lea     rax, [rbp+var_7C]
0x18002bf6a  mov     [rsp+130h+var_108], rax
0x18002bf6f  lea     rax, [rbp+var_38]
0x18002bf73  mov     [rbp+var_70], rcx
0x18002bf77  mov     rcx, r9
0x18002bf7a  mov     [rsp+130h+var_110], rax
0x18002bf7f  mov     [rbp+var_38], 1000000h
0x18002bf87  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18002bf8c  jmp     loc_18002C10E
0x18002bf91  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18002bf96  mov     r9, rax
0x18002bf99  mov     ecx, [rax]
0x18002bf9b  cmp     ecx, 2
0x18002bf9e  jbe     loc_18002C10E
0x18002bfa4  mov     rdx, 400000000000h
0x18002bfae  mov     rcx, rax
0x18002bfb1  call    _tlgKeywordOn
0x18002bfb6  test    al, al
0x18002bfb8  jz      loc_18002C10E
0x18002bfbe  mov     eax, [rbx+44h]
0x18002bfc1  lea     rdx, byte_18003CC2B
0x18002bfc8  mov     dword ptr [rbp+SRWLock], eax
0x18002bfcb  mov     eax, [rbx+10h]
0x18002bfce  mov     [rbp+arg_8], eax
0x18002bfd1  mov     rax, [rbx+78h]
0x18002bfd5  mov     rcx, [rbx+30h]
0x18002bfd9  mov     [rbp+var_40], rax
0x18002bfdd  mov     rax, [rbx+70h]
0x18002bfe1  mov     r8, [rdi+110h]
0x18002bfe8  mov     [rbp+var_48], rax
0x18002bfec  add     r8, 8
0x18002bff0  mov     eax, [rbx+68h]
0x18002bff3  mov     [rbp+arg_10], eax
0x18002bff6  mov     rax, [rbx+60h]
0x18002bffa  mov     [rbp+var_50], rax
0x18002bffe  mov     rax, [rbx+58h]
0x18002c002  mov     [rbp+var_58], rax
0x18002c006  mov     eax, [rbx+50h]
0x18002c009  mov     [rbp+arg_18], eax
0x18002c00c  mov     rax, [rbx+48h]
0x18002c010  mov     [rbp+var_60], rax
0x18002c014  mov     eax, [rbx+20h]
0x18002c017  mov     [rbp+var_7C], eax
0x18002c01a  mov     rax, [rbx+18h]
0x18002c01e  mov     [rbp+var_68], rax
0x18002c022  mov     eax, [rbx]
0x18002c024  mov     [rbp+var_80], eax
0x18002c027  mov     rax, [rbx+80h]
0x18002c02e  mov     [rbp+var_30], rax
0x18002c032  mov     eax, [rbx+40h]
0x18002c035  mov     dword ptr [rbp+var_78], eax
0x18002c038  mov     rax, [rbx+38h]
0x18002c03c  mov     [rbp+var_28], rax
0x18002c040  mov     eax, [rbx+8]
0x18002c043  mov     dword ptr [rbp+var_70], eax
0x18002c046  lea     rax, [rbp+var_38]
0x18002c04a  mov     [rsp+130h+var_88], rax
0x18002c052  lea     rax, [rbp+SRWLock]
0x18002c056  mov     [rsp+130h+var_90], rax
0x18002c05e  lea     rax, [rbp+arg_8]
0x18002c062  mov     [rsp+130h+var_98], rax
0x18002c06a  lea     rax, [rbp+var_40]
0x18002c06e  mov     [rsp+130h+var_A0], rax
0x18002c076  lea     rax, [rbp+var_48]
0x18002c07a  mov     [rsp+130h+var_A8], rax
0x18002c082  lea     rax, [rbp+arg_10]
0x18002c086  mov     [rsp+130h+var_B0], rax
0x18002c08e  lea     rax, [rbp+var_50]
0x18002c092  mov     [rsp+130h+var_B8], rax
0x18002c097  lea     rax, [rbp+var_58]
0x18002c09b  mov     [rsp+130h+var_C0], rax
0x18002c0a0  lea     rax, [rbp+arg_18]
0x18002c0a4  mov     [rsp+130h+var_C8], rax
0x18002c0a9  lea     rax, [rbp+var_60]
0x18002c0ad  mov     [rsp+130h+var_D0], rax
0x18002c0b2  lea     rax, [rbp+var_7C]
0x18002c0b6  mov     [rsp+130h+var_D8], rax
0x18002c0bb  lea     rax, [rbp+var_68]
0x18002c0bf  mov     [rsp+130h+var_E0], rax
0x18002c0c4  lea     rax, [rbp+var_80]
0x18002c0c8  mov     [rsp+130h+var_E8], rax
0x18002c0cd  lea     rax, [rbp+var_30]
0x18002c0d1  mov     [rsp+130h+var_F0], rax
0x18002c0d6  lea     rax, [rbp+var_78]
0x18002c0da  mov     [rsp+130h+var_F8], rax
0x18002c0df  lea     rax, [rbp+var_28]
0x18002c0e3  mov     [rsp+130h+var_100], rax
0x18002c0e8  lea     rax, [rbp+var_70]
0x18002c0ec  mov     [rsp+130h+var_108], rax
0x18002c0f1  lea     rax, [rbp+var_20]
0x18002c0f5  mov     [rbp+var_38], rcx
0x18002c0f9  mov     rcx, r9
0x18002c0fc  mov     [rsp+130h+var_110], rax
0x18002c101  mov     [rbp+var_20], 1000000h
0x18002c109  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18002c10e  lea     rdx, [rbp+SRWLock]
0x18002c112  mov     rcx, rdi
0x18002c115  call    ?LockExclusive@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18002c11a  mov     rax, [rdi+110h]
0x18002c121  mov     edx, [rbx+8]
0x18002c124  lea     rcx, [rax+50h]; this
0x18002c128  cmp     edx, [rcx+8]
0x18002c12b  jz      short loc_18002C140
0x18002c12d  cmp     edx, [rax+48h]
0x18002c130  jnz     short loc_18002C138
0x18002c132  cmp     dword ptr [rax+48h], 0
0x18002c136  jl      short loc_18002C140
0x18002c138  mov     rdx, rbx; struct wil::FailureInfo *
0x18002c13b  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x18002c140  mov     rcx, [rbp+SRWLock]; SRWLock
0x18002c144  test    rcx, rcx
0x18002c147  jz      short loc_18002C14F
0x18002c149  call    cs:__imp_ReleaseSRWLockExclusive
0x18002c14f  mov     al, 1
0x18002c151  add     rsp, 120h
0x18002c158  pop     rdi
0x18002c159  pop     rbx
0x18002c15a  pop     rbp
0x18002c15b  retn
```
