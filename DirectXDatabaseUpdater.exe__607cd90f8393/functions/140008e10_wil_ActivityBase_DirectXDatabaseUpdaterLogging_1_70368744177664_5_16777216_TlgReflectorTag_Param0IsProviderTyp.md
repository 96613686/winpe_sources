# wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(wil::FailureInfo const &)

- ea: `0x140008e10`
- end: `0x140009156`
- name: `?NotifyFailure@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@UEAA_NAEBUFailureInfo@2@@Z`
- size: `838`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callees

- `0x140001a3c`
- `0x140001ce0`
- `0x1400022ec`
- `0x140005e18`
- `0x140008578`
- `0x140008e10`
- `0x14000946c`
- `0x14000a7b8`
- `0x14001a010`

## pseudocode

```c
char __fastcall wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(
        _QWORD *a1,
        int *a2)
{
  __int64 v4; // rcx
  const struct _tlgProvider_t *v5; // rax
  int v6; // r9d
  __int64 v7; // rcx
  __int64 v8; // r8
  const struct _tlgProvider_t *v9; // rax
  int v10; // r9d
  __int64 v11; // rcx
  __int64 v12; // r8
  _DWORD *v13; // rax
  int v14; // edx
  int v16; // [rsp+B0h] [rbp-80h] BYREF
  int v17; // [rsp+B4h] [rbp-7Ch] BYREF
  __int64 v18; // [rsp+B8h] [rbp-78h] BYREF
  __int64 v19; // [rsp+C0h] [rbp-70h] BYREF
  __int64 v20; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v21; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v22; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v23; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v24; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v25; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v26; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v27; // [rsp+100h] [rbp-30h] BYREF
  __int64 v28; // [rsp+108h] [rbp-28h] BYREF
  __int64 v29[4]; // [rsp+110h] [rbp-20h] BYREF
  int v30; // [rsp+140h] [rbp+10h] BYREF
  int v31; // [rsp+148h] [rbp+18h] BYREF
  int v32; // [rsp+150h] [rbp+20h] BYREF
  int v33; // [rsp+158h] [rbp+28h] BYREF

  if ( (a2[1] & 2) == 0 )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD *, _QWORD))(*a1 + 16LL))(a1, (unsigned int)a2[4]) )
    {
      v9 = DirectXDatabaseUpdaterLogging::Provider(v4);
      if ( *(_DWORD *)v9 > 2u && (unsigned __int8)tlgKeywordOn(v9, 0x400000000000LL) )
      {
        v30 = a2[17];
        v31 = a2[4];
        v11 = *((_QWORD *)a2 + 6);
        v25 = *((_QWORD *)a2 + 15);
        v12 = a1[34];
        v24 = *((_QWORD *)a2 + 14);
        v32 = a2[26];
        v23 = *((_QWORD *)a2 + 12);
        v22 = *((_QWORD *)a2 + 11);
        v33 = a2[20];
        v21 = *((_QWORD *)a2 + 9);
        v17 = a2[8];
        v20 = *((_QWORD *)a2 + 3);
        v16 = *a2;
        v27 = *((_QWORD *)a2 + 16);
        LODWORD(v18) = a2[16];
        v28 = *((_QWORD *)a2 + 7);
        LODWORD(v19) = a2[2];
        v26 = v11;
        v29[0] = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v10,
          (unsigned int)&word_14001E1BE,
          v12 + 8,
          v10,
          (__int64)v29,
          (__int64)&v19,
          (__int64)&v28,
          (__int64)&v18,
          (__int64)&v27,
          (__int64)&v16,
          (__int64)&v20,
          (__int64)&v17,
          (__int64)&v21,
          (__int64)&v33,
          (__int64)&v22,
          (__int64)&v23,
          (__int64)&v32,
          (__int64)&v24,
          (__int64)&v25,
          (__int64)&v31,
          (__int64)&v30,
          (__int64)&v26);
      }
    }
    else
    {
      v5 = DirectXDatabaseUpdaterLogging::Provider(v4);
      if ( *(_DWORD *)v5 > 2u && (unsigned __int8)tlgKeywordOn(v5, 0x600000000000LL) )
      {
        v7 = *((_QWORD *)a2 + 15);
        v8 = a1[34];
        v18 = *((_QWORD *)a2 + 14);
        v30 = a2[26];
        v20 = *((_QWORD *)a2 + 12);
        v21 = *((_QWORD *)a2 + 11);
        v31 = a2[20];
        v22 = *((_QWORD *)a2 + 9);
        v32 = a2[8];
        v23 = *((_QWORD *)a2 + 3);
        v33 = *a2;
        v24 = *((_QWORD *)a2 + 16);
        v16 = a2[16];
        v25 = *((_QWORD *)a2 + 7);
        v17 = a2[2];
        v19 = v7;
        v26 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v6,
          (unsigned int)&byte_14001EACF,
          v8 + 8,
          v6,
          (__int64)&v26,
          (__int64)&v17,
          (__int64)&v25,
          (__int64)&v16,
          (__int64)&v24,
          (__int64)&v33,
          (__int64)&v23,
          (__int64)&v32,
          (__int64)&v22,
          (__int64)&v31,
          (__int64)&v21,
          (__int64)&v20,
          (__int64)&v30,
          (__int64)&v18,
          (__int64)&v19);
      }
    }
  }
  wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &v30);
  v13 = (_DWORD *)a1[34];
  v14 = a2[2];
  if ( v14 != v13[22] && (v14 != v13[18] || (int)v13[18] >= 0) )
    wil::StoredFailureInfo::SetFailureInfo((wil::StoredFailureInfo *)(v13 + 20), (const struct wil::FailureInfo *)a2);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v30);
  return 1;
}

```

## disassembly

```asm
0x140008e10  push    rbp
0x140008e12  push    rbx
0x140008e13  push    rdi
0x140008e14  lea     rbp, [rsp+10h]
0x140008e19  sub     rsp, 120h
0x140008e20  test    byte ptr [rdx+4], 2
0x140008e24  mov     rbx, rdx
0x140008e27  mov     rdi, rcx
0x140008e2a  jnz     loc_14000910E
0x140008e30  mov     rax, [rcx]
0x140008e33  mov     edx, [rdx+10h]
0x140008e36  mov     rax, [rax+10h]
0x140008e3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008e3f  test    al, al
0x140008e41  jnz     loc_140008F91
0x140008e47  call    ?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ; DirectXDatabaseUpdaterLogging::Provider(void)
0x140008e4c  mov     r9, rax
0x140008e4f  mov     ecx, [rax]
0x140008e51  cmp     ecx, 2
0x140008e54  jbe     loc_14000910E
0x140008e5a  mov     rdx, 600000000000h
0x140008e64  mov     rcx, rax
0x140008e67  call    _tlgKeywordOn
0x140008e6c  test    al, al
0x140008e6e  jz      loc_14000910E
0x140008e74  mov     rax, [rbx+70h]
0x140008e78  lea     rdx, byte_14001EACF
0x140008e7f  mov     rcx, [rbx+78h]
0x140008e83  mov     r8, [rdi+110h]
0x140008e8a  mov     [rbp+var_78], rax
0x140008e8e  add     r8, 8
0x140008e92  mov     eax, [rbx+68h]
0x140008e95  mov     [rbp+arg_0], eax
0x140008e98  mov     rax, [rbx+60h]
0x140008e9c  mov     [rbp+var_68], rax
0x140008ea0  mov     rax, [rbx+58h]
0x140008ea4  mov     [rbp+var_60], rax
0x140008ea8  mov     eax, [rbx+50h]
0x140008eab  mov     [rbp+arg_8], eax
0x140008eae  mov     rax, [rbx+48h]
0x140008eb2  mov     [rbp+var_58], rax
0x140008eb6  mov     eax, [rbx+20h]
0x140008eb9  mov     [rbp+arg_10], eax
0x140008ebc  mov     rax, [rbx+18h]
0x140008ec0  mov     [rbp+var_50], rax
0x140008ec4  mov     eax, [rbx]
0x140008ec6  mov     [rbp+arg_18], eax
0x140008ec9  mov     rax, [rbx+80h]
0x140008ed0  mov     [rbp+var_48], rax
0x140008ed4  mov     eax, [rbx+40h]
0x140008ed7  mov     [rbp+var_80], eax
0x140008eda  mov     rax, [rbx+38h]
0x140008ede  mov     [rbp+var_40], rax
0x140008ee2  mov     eax, [rbx+8]
0x140008ee5  mov     [rbp+var_7C], eax
0x140008ee8  lea     rax, [rbp+var_70]
0x140008eec  mov     [rsp+130h+var_A0], rax
0x140008ef4  lea     rax, [rbp+var_78]
0x140008ef8  mov     [rsp+130h+var_A8], rax
0x140008f00  lea     rax, [rbp+arg_0]
0x140008f04  mov     [rsp+130h+var_B0], rax
0x140008f0c  lea     rax, [rbp+var_68]
0x140008f10  mov     [rsp+130h+var_B8], rax
0x140008f15  lea     rax, [rbp+var_60]
0x140008f19  mov     [rsp+130h+var_C0], rax
0x140008f1e  lea     rax, [rbp+arg_8]
0x140008f22  mov     [rsp+130h+var_C8], rax
0x140008f27  lea     rax, [rbp+var_58]
0x140008f2b  mov     [rsp+130h+var_D0], rax
0x140008f30  lea     rax, [rbp+arg_10]
0x140008f34  mov     [rsp+130h+var_D8], rax
0x140008f39  lea     rax, [rbp+var_50]
0x140008f3d  mov     [rsp+130h+var_E0], rax
0x140008f42  lea     rax, [rbp+arg_18]
0x140008f46  mov     [rsp+130h+var_E8], rax
0x140008f4b  lea     rax, [rbp+var_48]
0x140008f4f  mov     [rsp+130h+var_F0], rax
0x140008f54  lea     rax, [rbp+var_80]
0x140008f58  mov     [rsp+130h+var_F8], rax
0x140008f5d  lea     rax, [rbp+var_40]
0x140008f61  mov     [rsp+130h+var_100], rax
0x140008f66  lea     rax, [rbp+var_7C]
0x140008f6a  mov     [rsp+130h+var_108], rax
0x140008f6f  lea     rax, [rbp+var_38]
0x140008f73  mov     [rbp+var_70], rcx
0x140008f77  mov     rcx, r9
0x140008f7a  mov     [rsp+130h+var_110], rax
0x140008f7f  mov     [rbp+var_38], 1000000h
0x140008f87  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x140008f8c  jmp     loc_14000910E
0x140008f91  call    ?Provider@DirectXDatabaseUpdaterLogging@@SAPEBU_tlgProvider_t@@XZ; DirectXDatabaseUpdaterLogging::Provider(void)
0x140008f96  mov     r9, rax
0x140008f99  mov     ecx, [rax]
0x140008f9b  cmp     ecx, 2
0x140008f9e  jbe     loc_14000910E
0x140008fa4  mov     rdx, 400000000000h
0x140008fae  mov     rcx, rax
0x140008fb1  call    _tlgKeywordOn
0x140008fb6  test    al, al
0x140008fb8  jz      loc_14000910E
0x140008fbe  mov     eax, [rbx+44h]
0x140008fc1  lea     rdx, word_14001E1BE
0x140008fc8  mov     [rbp+arg_0], eax
0x140008fcb  mov     eax, [rbx+10h]
0x140008fce  mov     [rbp+arg_8], eax
0x140008fd1  mov     rax, [rbx+78h]
0x140008fd5  mov     rcx, [rbx+30h]
0x140008fd9  mov     [rbp+var_40], rax
0x140008fdd  mov     rax, [rbx+70h]
0x140008fe1  mov     r8, [rdi+110h]
0x140008fe8  mov     [rbp+var_48], rax
0x140008fec  add     r8, 8
0x140008ff0  mov     eax, [rbx+68h]
0x140008ff3  mov     [rbp+arg_10], eax
0x140008ff6  mov     rax, [rbx+60h]
0x140008ffa  mov     [rbp+var_50], rax
0x140008ffe  mov     rax, [rbx+58h]
0x140009002  mov     [rbp+var_58], rax
0x140009006  mov     eax, [rbx+50h]
0x140009009  mov     [rbp+arg_18], eax
0x14000900c  mov     rax, [rbx+48h]
0x140009010  mov     [rbp+var_60], rax
0x140009014  mov     eax, [rbx+20h]
0x140009017  mov     [rbp+var_7C], eax
0x14000901a  mov     rax, [rbx+18h]
0x14000901e  mov     [rbp+var_68], rax
0x140009022  mov     eax, [rbx]
0x140009024  mov     [rbp+var_80], eax
0x140009027  mov     rax, [rbx+80h]
0x14000902e  mov     [rbp+var_30], rax
0x140009032  mov     eax, [rbx+40h]
0x140009035  mov     dword ptr [rbp+var_78], eax
0x140009038  mov     rax, [rbx+38h]
0x14000903c  mov     [rbp+var_28], rax
0x140009040  mov     eax, [rbx+8]
0x140009043  mov     dword ptr [rbp+var_70], eax
0x140009046  lea     rax, [rbp+var_38]
0x14000904a  mov     [rsp+130h+var_88], rax
0x140009052  lea     rax, [rbp+arg_0]
0x140009056  mov     [rsp+130h+var_90], rax
0x14000905e  lea     rax, [rbp+arg_8]
0x140009062  mov     [rsp+130h+var_98], rax
0x14000906a  lea     rax, [rbp+var_40]
0x14000906e  mov     [rsp+130h+var_A0], rax
0x140009076  lea     rax, [rbp+var_48]
0x14000907a  mov     [rsp+130h+var_A8], rax
0x140009082  lea     rax, [rbp+arg_10]
0x140009086  mov     [rsp+130h+var_B0], rax
0x14000908e  lea     rax, [rbp+var_50]
0x140009092  mov     [rsp+130h+var_B8], rax
0x140009097  lea     rax, [rbp+var_58]
0x14000909b  mov     [rsp+130h+var_C0], rax
0x1400090a0  lea     rax, [rbp+arg_18]
0x1400090a4  mov     [rsp+130h+var_C8], rax
0x1400090a9  lea     rax, [rbp+var_60]
0x1400090ad  mov     [rsp+130h+var_D0], rax
0x1400090b2  lea     rax, [rbp+var_7C]
0x1400090b6  mov     [rsp+130h+var_D8], rax
0x1400090bb  lea     rax, [rbp+var_68]
0x1400090bf  mov     [rsp+130h+var_E0], rax
0x1400090c4  lea     rax, [rbp+var_80]
0x1400090c8  mov     [rsp+130h+var_E8], rax
0x1400090cd  lea     rax, [rbp+var_30]
0x1400090d1  mov     [rsp+130h+var_F0], rax
0x1400090d6  lea     rax, [rbp+var_78]
0x1400090da  mov     [rsp+130h+var_F8], rax
0x1400090df  lea     rax, [rbp+var_28]
0x1400090e3  mov     [rsp+130h+var_100], rax
0x1400090e8  lea     rax, [rbp+var_70]
0x1400090ec  mov     [rsp+130h+var_108], rax
0x1400090f1  lea     rax, [rbp+var_20]
0x1400090f5  mov     [rbp+var_38], rcx
0x1400090f9  mov     rcx, r9
0x1400090fc  mov     [rsp+130h+var_110], rax
0x140009101  mov     [rbp+var_20], 1000000h
0x140009109  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x14000910e  lea     rdx, [rbp+arg_0]
0x140009112  mov     rcx, rdi
0x140009115  call    ?LockExclusive@?$ActivityBase@VDirectXDatabaseUpdaterLogging@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<DirectXDatabaseUpdaterLogging,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x14000911a  mov     rax, [rdi+110h]
0x140009121  mov     edx, [rbx+8]
0x140009124  lea     rcx, [rax+50h]; this
0x140009128  cmp     edx, [rcx+8]
0x14000912b  jz      short loc_140009140
0x14000912d  cmp     edx, [rax+48h]
0x140009130  jnz     short loc_140009138
0x140009132  cmp     dword ptr [rax+48h], 0
0x140009136  jl      short loc_140009140
0x140009138  mov     rdx, rbx; struct wil::FailureInfo *
0x14000913b  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x140009140  lea     rcx, [rbp+arg_0]
0x140009144  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140009149  mov     al, 1
0x14000914b  add     rsp, 120h
0x140009152  pop     rdi
0x140009153  pop     rbx
0x140009154  pop     rbp
0x140009155  retn
```
