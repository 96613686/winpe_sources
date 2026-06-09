# wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(wil::FailureInfo const &)

- ea: `0x180024e50`
- end: `0x180025023`
- name: `?NotifyFailure@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@UEAA_NAEBUFailureInfo@2@@Z`
- size: `467`
- prototype: `char __fastcall(__int64, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001ca0`
- `0x1800095b4`
- `0x180018b8c`
- `0x1800195c0`
- `0x180024e50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025010`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025010`

## pseudocode

```c
char __fastcall wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::NotifyFailure(
        __int64 a1,
        int *a2)
{
  const struct _tlgProvider_t *v4; // r9
  __int64 v5; // rcx
  __int64 v6; // r8
  _DWORD *v7; // rax
  int v8; // edx
  int v10; // [rsp+B0h] [rbp-80h] BYREF
  int v11; // [rsp+B4h] [rbp-7Ch] BYREF
  int v12; // [rsp+B8h] [rbp-78h] BYREF
  int v13; // [rsp+BCh] [rbp-74h] BYREF
  __int64 v14; // [rsp+C0h] [rbp-70h] BYREF
  __int64 v15; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v16; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v17; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v18; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v19; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v20; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v21; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v22; // [rsp+100h] [rbp-30h] BYREF
  __int64 v23[3]; // [rsp+108h] [rbp-28h] BYREF
  PSRWLOCK SRWLock; // [rsp+130h] [rbp+0h] BYREF
  __int64 v25; // [rsp+138h] [rbp+8h] BYREF
  __int64 v26; // [rsp+140h] [rbp+10h] BYREF
  __int64 v27; // [rsp+148h] [rbp+18h] BYREF

  if ( (a2[1] & 2) == 0 )
  {
    v4 = LanguageComponentsInstallerTelemetryProvider::Provider();
    if ( *(_DWORD *)v4 > 2u )
    {
      v5 = *((_QWORD *)a2 + 6);
      v6 = *(_QWORD *)(a1 + 272);
      LODWORD(v26) = a2[26];
      v17 = *((_QWORD *)a2 + 12);
      v18 = *((_QWORD *)a2 + 11);
      LODWORD(v27) = a2[20];
      v19 = *((_QWORD *)a2 + 9);
      v10 = a2[8];
      v20 = *((_QWORD *)a2 + 3);
      v11 = *a2;
      v21 = *((_QWORD *)a2 + 16);
      v12 = a2[16];
      v22 = *((_QWORD *)a2 + 7);
      v13 = a2[2];
      v14 = v5;
      LODWORD(SRWLock) = a2[17];
      LODWORD(v25) = a2[4];
      v15 = *((_QWORD *)a2 + 15);
      v16 = *((_QWORD *)a2 + 14);
      v23[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (int)v4,
        (int)&word_18002FECA,
        v6 + 8,
        (__int64)v4,
        (__int64)v23,
        (__int64)&v13,
        (const unsigned __int16 **)&v22,
        (__int64)&v12,
        (const unsigned __int16 **)&v21,
        (__int64)&v11,
        (__int64 **)&v20,
        (__int64)&v10,
        (const unsigned __int16 **)&v19,
        (__int64)&v27,
        (const unsigned __int16 **)&v18,
        (__int64 **)&v17,
        (__int64)&v26,
        (const unsigned __int16 **)&v16,
        (__int64 **)&v15,
        (__int64)&v25,
        (__int64)&SRWLock,
        (const unsigned __int16 **)&v14);
    }
  }
  wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    &SRWLock);
  v7 = *(_DWORD **)(a1 + 272);
  v8 = a2[2];
  if ( v8 != v7[22] && (v8 != v7[18] || (int)v7[18] >= 0) )
    wil::StoredFailureInfo::SetFailureInfo((wil::StoredFailureInfo *)(v7 + 20), (const struct wil::FailureInfo *)a2);
  if ( SRWLock )
    ReleaseSRWLockExclusive(SRWLock);
  return 1;
}

```

## disassembly

```asm
0x180024e50  push    rbp
0x180024e52  push    rbx
0x180024e53  push    rdi
0x180024e54  lea     rbp, [rsp+20h]
0x180024e59  sub     rsp, 110h
0x180024e60  test    byte ptr [rdx+4], 2
0x180024e64  mov     rbx, rdx
0x180024e67  mov     rdi, rcx
0x180024e6a  jnz     loc_180024FD5
0x180024e70  call    ?Provider@LanguageComponentsInstallerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; LanguageComponentsInstallerTelemetryProvider::Provider(void)
0x180024e75  mov     r9, rax
0x180024e78  mov     r8d, [rax]
0x180024e7b  cmp     r8d, 2
0x180024e7f  jbe     loc_180024FD5
0x180024e85  mov     eax, [rbx+68h]
0x180024e88  lea     rdx, word_18002FECA; int
0x180024e8f  mov     rcx, [rbx+30h]
0x180024e93  mov     r8, [rdi+110h]
0x180024e9a  mov     dword ptr [rbp-10h+arg_10], eax
0x180024e9d  add     r8, 8; int
0x180024ea1  mov     rax, [rbx+60h]
0x180024ea5  mov     [rbp-10h+var_48], rax
0x180024ea9  mov     rax, [rbx+58h]
0x180024ead  mov     [rbp-10h+var_40], rax
0x180024eb1  mov     eax, [rbx+50h]
0x180024eb4  mov     dword ptr [rbp-10h+arg_18], eax
0x180024eb7  mov     rax, [rbx+48h]
0x180024ebb  mov     [rbp-10h+var_38], rax
0x180024ebf  mov     eax, [rbx+20h]
0x180024ec2  mov     dword ptr [rbp-10h+var_70], eax
0x180024ec5  mov     rax, [rbx+18h]
0x180024ec9  mov     [rbp-10h+var_30], rax
0x180024ecd  mov     eax, [rbx]
0x180024ecf  mov     dword ptr [rbp-10h+var_70+4], eax
0x180024ed2  mov     rax, [rbx+80h]
0x180024ed9  mov     [rbp-10h+var_28], rax
0x180024edd  mov     eax, [rbx+40h]
0x180024ee0  mov     dword ptr [rbp-10h+var_68], eax
0x180024ee3  mov     rax, [rbx+38h]
0x180024ee7  mov     [rbp-10h+var_20], rax
0x180024eeb  mov     eax, [rbx+8]
0x180024eee  mov     dword ptr [rbp-10h+var_68+4], eax
0x180024ef1  lea     rax, [rbp-10h+var_60]
0x180024ef5  mov     [rsp+120h+var_78], rax; __int64
0x180024efd  lea     rax, [rbp-10h+SRWLock]
0x180024f01  mov     [rsp+120h+var_80], rax; __int64
0x180024f09  lea     rax, [rbp-10h+arg_8]
0x180024f0d  mov     [rsp+120h+var_88], rax; __int64
0x180024f15  lea     rax, [rbp-10h+var_58]
0x180024f19  mov     [rsp+120h+var_90], rax; __int64
0x180024f21  lea     rax, [rbp-10h+var_50]
0x180024f25  mov     [rsp+120h+var_98], rax; __int64
0x180024f2d  lea     rax, [rbp-10h+arg_10]
0x180024f31  mov     [rsp+120h+var_A0], rax; __int64
0x180024f39  lea     rax, [rbp-10h+var_48]
0x180024f3d  mov     [rsp+120h+var_A8], rax; __int64
0x180024f42  lea     rax, [rbp-10h+var_40]
0x180024f46  mov     [rsp+120h+var_B0], rax; __int64
0x180024f4b  lea     rax, [rbp-10h+arg_18]
0x180024f4f  mov     [rsp+120h+var_B8], rax; __int64
0x180024f54  lea     rax, [rbp-10h+var_38]
0x180024f58  mov     [rsp+120h+var_C0], rax; __int64
0x180024f5d  lea     rax, [rbp-10h+var_70]
0x180024f61  mov     [rsp+120h+var_C8], rax; __int64
0x180024f66  lea     rax, [rbp-10h+var_30]
0x180024f6a  mov     [rsp+120h+var_D0], rax; __int64
0x180024f6f  lea     rax, [rbp-10h+var_70+4]
0x180024f73  mov     [rsp+120h+var_D8], rax; __int64
0x180024f78  lea     rax, [rbp-10h+var_28]
0x180024f7c  mov     [rsp+120h+var_E0], rax; __int64
0x180024f81  lea     rax, [rbp-10h+var_68]
0x180024f85  mov     [rsp+120h+var_E8], rax; __int64
0x180024f8a  lea     rax, [rbp-10h+var_20]
0x180024f8e  mov     [rbp-10h+var_60], rcx
0x180024f92  mov     ecx, [rbx+44h]
0x180024f95  mov     dword ptr [rbp-10h+SRWLock], ecx
0x180024f98  mov     ecx, [rbx+10h]
0x180024f9b  mov     [rsp+120h+var_F0], rax; __int64
0x180024fa0  lea     rax, [rbp-10h+var_68+4]
0x180024fa4  mov     dword ptr [rbp-10h+arg_8], ecx
0x180024fa7  mov     rcx, [rbx+78h]
0x180024fab  mov     [rbp-10h+var_58], rcx
0x180024faf  mov     rcx, [rbx+70h]
0x180024fb3  mov     [rsp+120h+var_F8], rax; __int64
0x180024fb8  lea     rax, [rbp-10h+var_18]
0x180024fbc  mov     [rbp-10h+var_50], rcx
0x180024fc0  mov     rcx, r9; int
0x180024fc3  mov     [rsp+120h+var_100], rax; __int64
0x180024fc8  mov     [rbp-10h+var_18], 1000000h
0x180024fd0  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180024fd5  lea     rdx, [rbp-10h+SRWLock]
0x180024fd9  mov     rcx, rdi
0x180024fdc  call    ?LockExclusive@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180024fe1  mov     rax, [rdi+110h]
0x180024fe8  mov     edx, [rbx+8]
0x180024feb  lea     rcx, [rax+50h]; this
0x180024fef  cmp     edx, [rcx+8]
0x180024ff2  jz      short loc_180025007
0x180024ff4  cmp     edx, [rax+48h]
0x180024ff7  jnz     short loc_180024FFF
0x180024ff9  cmp     dword ptr [rax+48h], 0
0x180024ffd  jl      short loc_180025007
0x180024fff  mov     rdx, rbx; struct wil::FailureInfo *
0x180025002  call    ?SetFailureInfo@StoredFailureInfo@wil@@QEAAXAEBUFailureInfo@2@@Z; wil::StoredFailureInfo::SetFailureInfo(wil::FailureInfo const &)
0x180025007  mov     rcx, [rbp-10h+SRWLock]; SRWLock
0x18002500b  test    rcx, rcx
0x18002500e  jz      short loc_180025016
0x180025010  call    cs:__imp_ReleaseSRWLockExclusive
0x180025016  mov     al, 1
0x180025018  add     rsp, 110h
0x18002501f  pop     rdi
0x180025020  pop     rbx
0x180025021  pop     rbp
0x180025022  retn
```
