# wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(wil::FailureInfo const &)

- ea: `0x18000e590`
- end: `0x18000e8fc`
- name: `?NotifyFailure@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@UEAA_NAEBUFailureInfo@2@@Z`
- size: `876`
- prototype: `char __fastcall(_QWORD *, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `service_task`

## callees

- `0x18000185c`
- `0x18000221c`
- `0x180006554`
- `0x18000a648`
- `0x18000e47c`
- `0x18000e590`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e8e9`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000e8e9`

## pseudocode

```c
char __fastcall wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(
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
  __int64 *v18; // [rsp+C0h] [rbp-70h] BYREF
  __int64 *v19; // [rsp+C8h] [rbp-68h] BYREF
  const unsigned __int16 *v20; // [rsp+D0h] [rbp-60h] BYREF
  const unsigned __int16 *v21; // [rsp+D8h] [rbp-58h] BYREF
  __int64 *v22; // [rsp+E0h] [rbp-50h] BYREF
  const unsigned __int16 *v23; // [rsp+E8h] [rbp-48h] BYREF
  __int64 *v24; // [rsp+F0h] [rbp-40h] BYREF
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
      v8 = ServiceHostLogging::Provider();
      v9 = (__int64)v8;
      if ( *(_DWORD *)v8 > 2u )
      {
        v10 = *((_QWORD *)v8 + 3);
        if ( (*(_QWORD *)(v9 + 16) & 0x400000000000LL) != 0 && (v10 & 0x400000000000LL) == v10 )
        {
          v25 = *((_QWORD *)a2 + 6);
          LODWORD(SRWLock) = a2[17];
          v30 = a2[4];
          v24 = (__int64 *)*((_QWORD *)a2 + 15);
          v11 = a1[34];
          v23 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
          v31 = a2[26];
          v22 = (__int64 *)*((_QWORD *)a2 + 12);
          v21 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
          v32 = a2[20];
          v20 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
          v16 = a2[8];
          v19 = (__int64 *)*((_QWORD *)a2 + 3);
          v15 = *a2;
          v26 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
          LODWORD(v17) = a2[16];
          v27 = (const unsigned __int16 *)*((_QWORD *)a2 + 7);
          LODWORD(v18) = a2[2];
          v28[0] = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
            v9,
            (__int64)word_1800150FA,
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
      v4 = ServiceHostLogging::Provider();
      v5 = (__int64)v4;
      if ( *(_DWORD *)v4 > 2u )
      {
        v6 = *((_QWORD *)v4 + 3);
        if ( (*(_QWORD *)(v5 + 16) & 0x600000000000LL) != 0 && (v6 & 0x600000000000LL) == v6 )
        {
          v7 = a1[34];
          v18 = (__int64 *)*((_QWORD *)a2 + 15);
          v17 = (const unsigned __int16 *)*((_QWORD *)a2 + 14);
          LODWORD(SRWLock) = a2[26];
          v19 = (__int64 *)*((_QWORD *)a2 + 12);
          v20 = (const unsigned __int16 *)*((_QWORD *)a2 + 11);
          v30 = a2[20];
          v21 = (const unsigned __int16 *)*((_QWORD *)a2 + 9);
          v31 = a2[8];
          v22 = (__int64 *)*((_QWORD *)a2 + 3);
          v32 = *a2;
          v23 = (const unsigned __int16 *)*((_QWORD *)a2 + 16);
          v15 = a2[16];
          v24 = (__int64 *)*((_QWORD *)a2 + 7);
          v16 = a2[2];
          v25 = 0x1000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            v5,
            (__int64)word_180015232,
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
  wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
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
0x18000e590  push    rbp
0x18000e592  push    rbx
0x18000e593  push    rdi
0x18000e594  lea     rbp, [rsp+10h]
0x18000e599  sub     rsp, 120h
0x18000e5a0  test    byte ptr [rdx+4], 2
0x18000e5a4  mov     rbx, rdx
0x18000e5a7  mov     rdi, rcx
0x18000e5aa  jnz     loc_18000E8AE
0x18000e5b0  mov     rax, [rcx]
0x18000e5b3  mov     edx, [rdx+10h]
0x18000e5b6  mov     rax, [rax+10h]
0x18000e5ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5bf  test    al, al
0x18000e5c1  jnz     loc_18000E721
0x18000e5c7  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000e5cc  mov     r9, rax
0x18000e5cf  mov     ecx, [rax]
0x18000e5d1  cmp     ecx, 2
0x18000e5d4  jbe     loc_18000E8AE
0x18000e5da  mov     rax, [rax+18h]
0x18000e5de  mov     rdx, 600000000000h
0x18000e5e8  mov     rcx, [r9+10h]
0x18000e5ec  test    rdx, rcx
0x18000e5ef  jz      loc_18000E8AE
0x18000e5f5  mov     rcx, rax
0x18000e5f8  and     rcx, rdx
0x18000e5fb  cmp     rcx, rax
0x18000e5fe  jnz     loc_18000E8AE
0x18000e604  mov     rax, [rbx+78h]
0x18000e608  lea     rdx, word_180015232
0x18000e60f  mov     r8, [rdi+110h]
0x18000e616  mov     rcx, r9
0x18000e619  mov     [rbp+var_70], rax
0x18000e61d  add     r8, 8
0x18000e621  mov     rax, [rbx+70h]
0x18000e625  mov     [rbp+var_78], rax
0x18000e629  mov     eax, [rbx+68h]
0x18000e62c  mov     dword ptr [rbp+SRWLock], eax
0x18000e62f  mov     rax, [rbx+60h]
0x18000e633  mov     [rbp+var_68], rax
0x18000e637  mov     rax, [rbx+58h]
0x18000e63b  mov     [rbp+var_60], rax
0x18000e63f  mov     eax, [rbx+50h]
0x18000e642  mov     [rbp+arg_8], eax
0x18000e645  mov     rax, [rbx+48h]
0x18000e649  mov     [rbp+var_58], rax
0x18000e64d  mov     eax, [rbx+20h]
0x18000e650  mov     [rbp+arg_10], eax
0x18000e653  mov     rax, [rbx+18h]
0x18000e657  mov     [rbp+var_50], rax
0x18000e65b  mov     eax, [rbx]
0x18000e65d  mov     [rbp+arg_18], eax
0x18000e660  mov     rax, [rbx+80h]
0x18000e667  mov     [rbp+var_48], rax
0x18000e66b  mov     eax, [rbx+40h]
0x18000e66e  mov     [rbp+var_80], eax
0x18000e671  mov     rax, [rbx+38h]
0x18000e675  mov     [rbp+var_40], rax
0x18000e679  mov     eax, [rbx+8]
0x18000e67c  mov     [rbp+var_7C], eax
0x18000e67f  lea     rax, [rbp+var_70]
0x18000e683  mov     [rsp+130h+var_A0], rax
0x18000e68b  lea     rax, [rbp+var_78]
0x18000e68f  mov     [rsp+130h+var_A8], rax
0x18000e697  lea     rax, [rbp+SRWLock]
0x18000e69b  mov     [rsp+130h+var_B0], rax
0x18000e6a3  lea     rax, [rbp+var_68]
0x18000e6a7  mov     [rsp+130h+var_B8], rax
0x18000e6ac  lea     rax, [rbp+var_60]
0x18000e6b0  mov     [rsp+130h+var_C0], rax
0x18000e6b5  lea     rax, [rbp+arg_8]
0x18000e6b9  mov     [rsp+130h+var_C8], rax
0x18000e6be  lea     rax, [rbp+var_58]
0x18000e6c2  mov     [rsp+130h+var_D0], rax
0x18000e6c7  lea     rax, [rbp+arg_10]
0x18000e6cb  mov     [rsp+130h+var_D8], rax
0x18000e6d0  lea     rax, [rbp+var_50]
0x18000e6d4  mov     [rsp+130h+var_E0], rax
0x18000e6d9  lea     rax, [rbp+arg_18]
0x18000e6dd  mov     [rsp+130h+var_E8], rax
0x18000e6e2  lea     rax, [rbp+var_48]
0x18000e6e6  mov     [rsp+130h+var_F0], rax
0x18000e6eb  lea     rax, [rbp+var_80]
0x18000e6ef  mov     [rsp+130h+var_F8], rax
0x18000e6f4  lea     rax, [rbp+var_40]
0x18000e6f8  mov     [rsp+130h+var_100], rax
0x18000e6fd  lea     rax, [rbp+var_7C]
0x18000e701  mov     [rsp+130h+var_108], rax
0x18000e706  lea     rax, [rbp+var_38]
0x18000e70a  mov     [rsp+130h+var_110], rax
0x18000e70f  mov     [rbp+var_38], 1000000h
0x18000e717  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18000e71c  jmp     loc_18000E8AE
0x18000e721  call    ?Provider@ServiceHostLogging@@SAPEBU_tlgProvider_t@@XZ; ServiceHostLogging::Provider(void)
0x18000e726  mov     r9, rax
0x18000e729  mov     ecx, [rax]
0x18000e72b  cmp     ecx, 2
0x18000e72e  jbe     loc_18000E8AE
0x18000e734  mov     rax, [rax+18h]
0x18000e738  mov     rdx, 400000000000h
0x18000e742  mov     rcx, [r9+10h]
0x18000e746  test    rdx, rcx
0x18000e749  jz      loc_18000E8AE
0x18000e74f  mov     rcx, rax
0x18000e752  and     rcx, rdx
0x18000e755  cmp     rcx, rax
0x18000e758  jnz     loc_18000E8AE
0x18000e75e  mov     rax, [rbx+30h]
0x18000e762  lea     rdx, word_1800150FA
0x18000e769  mov     [rbp+var_38], rax
0x18000e76d  mov     rcx, r9
0x18000e770  mov     eax, [rbx+44h]
0x18000e773  mov     dword ptr [rbp+SRWLock], eax
0x18000e776  mov     eax, [rbx+10h]
0x18000e779  mov     [rbp+arg_8], eax
0x18000e77c  mov     rax, [rbx+78h]
0x18000e780  mov     [rbp+var_40], rax
0x18000e784  mov     rax, [rbx+70h]
0x18000e788  mov     r8, [rdi+110h]
0x18000e78f  mov     [rbp+var_48], rax
0x18000e793  add     r8, 8
0x18000e797  mov     eax, [rbx+68h]
0x18000e79a  mov     [rbp+arg_10], eax
0x18000e79d  mov     rax, [rbx+60h]
0x18000e7a1  mov     [rbp+var_50], rax
0x18000e7a5  mov     rax, [rbx+58h]
0x18000e7a9  mov     [rbp+var_58], rax
0x18000e7ad  mov     eax, [rbx+50h]
0x18000e7b0  mov     [rbp+arg_18], eax
0x18000e7b3  mov     rax, [rbx+48h]
0x18000e7b7  mov     [rbp+var_60], rax
0x18000e7bb  mov     eax, [rbx+20h]
0x18000e7be  mov     [rbp+var_7C], eax
0x18000e7c1  mov     rax, [rbx+18h]
0x18000e7c5  mov     [rbp+var_68], rax
0x18000e7c9  mov     eax, [rbx]
0x18000e7cb  mov     [rbp+var_80], eax
0x18000e7ce  mov     rax, [rbx+80h]
0x18000e7d5  mov     [rbp+var_30], rax
0x18000e7d9  mov     eax, [rbx+40h]
0x18000e7dc  mov     dword ptr [rbp+var_78], eax
0x18000e7df  mov     rax, [rbx+38h]
0x18000e7e3  mov     [rbp+var_28], rax
0x18000e7e7  mov     eax, [rbx+8]
0x18000e7ea  mov     dword ptr [rbp+var_70], eax
0x18000e7ed  lea     rax, [rbp+var_38]
0x18000e7f1  mov     [rsp+130h+var_88], rax
0x18000e7f9  lea     rax, [rbp+SRWLock]
0x18000e7fd  mov     [rsp+130h+var_90], rax
0x18000e805  lea     rax, [rbp+arg_8]
0x18000e809  mov     [rsp+130h+var_98], rax
0x18000e811  lea     rax, [rbp+var_40]
0x18000e815  mov     [rsp+130h+var_A0], rax
0x18000e81d  lea     rax, [rbp+var_48]
0x18000e821  mov     [rsp+130h+var_A8], rax
0x18000e829  lea     rax, [rbp+arg_10]
0x18000e82d  mov     [rsp+130h+var_B0], rax
0x18000e835  lea     rax, [rbp+var_50]
0x18000e839  mov     [rsp+130h+var_B8], rax
0x18000e83e  lea     rax, [rbp+var_58]
0x18000e842  mov     [rsp+130h+var_C0], rax
0x18000e847  lea     rax, [rbp+arg_18]
0x18000e84b  mov     [rsp+130h+var_C8], rax
0x18000e850  lea     rax, [rbp+var_60]
0x18000e854  mov     [rsp+130h+var_D0], rax
0x18000e859  lea     rax, [rbp+var_7C]
0x18000e85d  mov     [rsp+130h+var_D8], rax
0x18000e862  lea     rax, [rbp+var_68]
0x18000e866  mov     [rsp+130h+var_E0], rax
0x18000e86b  lea     rax, [rbp+var_80]
0x18000e86f  mov     [rsp+130h+var_E8], rax
0x18000e874  lea     rax, [rbp+var_30]
0x18000e878  mov     [rsp+130h+var_F0], rax
0x18000e87d  lea     rax, [rbp+var_78]
0x18000e881  mov     [rsp+130h+var_F8], rax
0x18000e886  lea     rax, [rbp+var_28]
0x18000e88a  mov     [rsp+130h+var_100], rax
0x18000e88f  lea     rax, [rbp+var_70]
0x18000e893  mov     [rsp+130h+var_108], rax
0x18000e898  lea     rax, [rbp+var_20]
0x18000e89c  mov     [rsp+130h+var_110], rax
0x18000e8a1  mov     [rbp+var_20], 1000000h
0x18000e8a9  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000e8ae  lea     rdx, [rbp+SRWLock]
0x18000e8b2  mov     rcx, rdi
0x18000e8b5  call    ?LockExclusive@?$ActivityBase@VServiceHostLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ServiceHostLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x18000e8ba  mov     rax, [rdi+110h]
0x18000e8c1  mov     edx, [rbx+8]
0x18000e8c4  lea     rcx, [rax+50h]; this
0x18000e8c8  cmp     edx, [rcx+8]
0x18000e8cb  jz      short loc_18000E8E0
0x18000e8cd  cmp     edx, [rax+48h]
0x18000e8d0  jnz     short loc_18000E8D8
0x18000e8d2  cmp     dword ptr [rax+48h], 0
0x18000e8d6  jl      short loc_18000E8E0
0x18000e8d8  mov     rdx, rbx; struct wil::FailureInfo *
0x18000e8db  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x18000e8e0  mov     rcx, [rbp+SRWLock]; SRWLock
0x18000e8e4  test    rcx, rcx
0x18000e8e7  jz      short loc_18000E8EF
0x18000e8e9  call    cs:__imp_ReleaseSRWLockExclusive
0x18000e8ef  mov     al, 1
0x18000e8f1  add     rsp, 120h
0x18000e8f8  pop     rdi
0x18000e8f9  pop     rbx
0x18000e8fa  pop     rbp
0x18000e8fb  retn
```
