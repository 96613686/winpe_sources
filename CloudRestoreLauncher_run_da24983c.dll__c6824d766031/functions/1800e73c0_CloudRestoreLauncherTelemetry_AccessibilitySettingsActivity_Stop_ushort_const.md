# CloudRestoreLauncherTelemetry::AccessibilitySettingsActivity::Stop(ushort const *)

- ea: `0x1800e73c0`
- end: `0x1800e7614`
- name: `?Stop@AccessibilitySettingsActivity@CloudRestoreLauncherTelemetry@@QEAAXPEBG@Z`
- size: `596`
- prototype: `void __fastcall(CloudRestoreLauncherTelemetry::AccessibilitySettingsActivity *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800e6490`

## callees

- `0x180001edc`
- `0x180003ab0`
- `0x180003d9c`
- `0x180018674`
- `0x1800195cc`
- `0x18001e020`
- `0x1800e73c0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800e75ab`
- `KERNEL32!GetCurrentThreadId` at `0x1800e75ab`

## string_xrefs

- `0x1800e7438`: `Restore Completed`
- `0x1800e75a0`: `Restore Completed`

## pseudocode

```c
void __fastcall CloudRestoreLauncherTelemetry::AccessibilitySettingsActivity::Stop(
        CloudRestoreLauncherTelemetry::AccessibilitySettingsActivity *this,
        const unsigned __int16 *a2)
{
  __int64 v2; // rdi
  int v4; // eax
  __int64 v5; // rdi
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // r8
  const struct _tlgProvider_t *v9; // r9
  __int64 v10; // r8
  const struct _tlgProvider_t *v11; // rax
  int v12; // edi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // r9d
  int v16; // [rsp+B0h] [rbp-80h] BYREF
  int v17; // [rsp+B4h] [rbp-7Ch] BYREF
  const unsigned __int16 *v18; // [rsp+B8h] [rbp-78h] BYREF
  __int64 v19; // [rsp+C0h] [rbp-70h] BYREF
  __int64 v20; // [rsp+C8h] [rbp-68h] BYREF
  __int64 v21; // [rsp+D0h] [rbp-60h] BYREF
  __int64 v22; // [rsp+D8h] [rbp-58h] BYREF
  __int64 v23; // [rsp+E0h] [rbp-50h] BYREF
  __int64 v24; // [rsp+E8h] [rbp-48h] BYREF
  __int64 v25; // [rsp+F0h] [rbp-40h] BYREF
  __int64 v26; // [rsp+F8h] [rbp-38h] BYREF
  __int64 v27; // [rsp+100h] [rbp-30h] BYREF
  __int64 v28[3]; // [rsp+108h] [rbp-28h] BYREF
  int v29; // [rsp+130h] [rbp+0h] BYREF
  const unsigned __int16 *v30; // [rsp+138h] [rbp+8h] BYREF
  const unsigned __int16 *v31; // [rsp+140h] [rbp+10h] BYREF
  __int64 v32; // [rsp+148h] [rbp+18h] BYREF

  v30 = a2;
  v2 = *((_QWORD *)this + 34);
  v4 = *(_DWORD *)(v2 + 72);
  if ( v4 < 0 && (v5 = v2 + 80, v4 == *(_DWORD *)(v5 + 8)) && v5 )
  {
    wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v6 = CloudRestoreLauncherTelemetry::Provider();
    v9 = v6;
    if ( *(_DWORD *)v6 > 5u && (unsigned __int8)tlgKeywordOn(v6, 0x400000000000LL) )
    {
      v10 = *((_QWORD *)this + 34);
      v18 = L"Restore Completed";
      v19 = *(_QWORD *)(v5 + 120);
      v20 = *(_QWORD *)(v5 + 112);
      LODWORD(v30) = *(_DWORD *)(v5 + 104);
      v21 = *(_QWORD *)(v5 + 96);
      v22 = *(_QWORD *)(v5 + 88);
      v29 = *(_DWORD *)(v5 + 80);
      v23 = *(_QWORD *)(v5 + 72);
      LODWORD(v31) = *(_DWORD *)(v5 + 32);
      v24 = *(_QWORD *)(v5 + 24);
      LODWORD(v32) = *(_DWORD *)v5;
      v25 = *(_QWORD *)(v5 + 128);
      v16 = *(_DWORD *)(v5 + 64);
      v26 = *(_QWORD *)(v5 + 56);
      v17 = *(_DWORD *)(v5 + 8);
      v27 = 0x1000000;
      v28[0] = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        (_DWORD)v9,
        (unsigned int)&unk_18015C12E,
        v10 + 8,
        (_DWORD)v9,
        (__int64)v28,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v16,
        (__int64)&v25,
        (__int64)&v32,
        (__int64)&v24,
        (__int64)&v31,
        (__int64)&v23,
        (__int64)&v29,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v30,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v18);
    }
  }
  else
  {
    wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v11 = CloudRestoreLauncherTelemetry::Provider();
    v12 = (int)v11;
    if ( *(_DWORD *)v11 > 5u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL) )
    {
      v31 = L"Restore Completed";
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      LODWORD(v30) = CurrentThreadId;
      v29 = *(_DWORD *)(v14 + 72);
      v32 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        v12,
        (unsigned int)&unk_18015C2D6,
        v14 + 8,
        v15,
        (__int64)&v32,
        (__int64)&v29,
        (__int64)&v30,
        (__int64)&v31);
    }
  }
  wil::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v7,
    v8,
    v9);
}

```

## disassembly

```asm
0x1800e73c0  mov     [rsp-8+arg_8], rdx
0x1800e73c5  push    rbp
0x1800e73c6  push    rbx
0x1800e73c7  push    rdi
0x1800e73c8  lea     rbp, [rsp+20h]
0x1800e73cd  sub     rsp, 110h
0x1800e73d4  mov     rdi, [rcx+110h]
0x1800e73db  mov     rbx, rcx
0x1800e73de  mov     eax, [rdi+48h]
0x1800e73e1  test    eax, eax
0x1800e73e3  jns     loc_1800E7576
0x1800e73e9  add     rdi, 50h ; 'P'
0x1800e73ed  cmp     eax, [rdi+8]
0x1800e73f0  jnz     loc_1800E7576
0x1800e73f6  test    rdi, rdi
0x1800e73f9  jz      loc_1800E7576
0x1800e73ff  call    ?zInternalStop@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800e7404  call    ?Provider@CloudRestoreLauncherTelemetry@@SAPEBU_tlgProvider_t@@XZ; CloudRestoreLauncherTelemetry::Provider(void)
0x1800e7409  mov     r9, rax
0x1800e740c  mov     ecx, [rax]
0x1800e740e  cmp     ecx, 5
0x1800e7411  jbe     loc_1800E7602
0x1800e7417  mov     rdx, 400000000000h
0x1800e7421  mov     rcx, rax
0x1800e7424  call    _tlgKeywordOn
0x1800e7429  test    al, al
0x1800e742b  jz      loc_1800E7602
0x1800e7431  mov     r8, [rbx+110h]
0x1800e7438  lea     rax, aRestoreComplet; "Restore Completed"
0x1800e743f  mov     [rbp-10h+var_68], rax
0x1800e7443  lea     rdx, unk_18015C12E
0x1800e744a  mov     rax, [rdi+78h]
0x1800e744e  add     r8, 8
0x1800e7452  mov     [rbp-10h+var_60], rax
0x1800e7456  mov     rcx, r9
0x1800e7459  mov     rax, [rdi+70h]
0x1800e745d  mov     [rbp-10h+var_58], rax
0x1800e7461  mov     eax, [rdi+68h]
0x1800e7464  mov     dword ptr [rbp-10h+arg_8], eax
0x1800e7467  mov     rax, [rdi+60h]
0x1800e746b  mov     [rbp-10h+var_50], rax
0x1800e746f  mov     rax, [rdi+58h]
0x1800e7473  mov     [rbp-10h+var_48], rax
0x1800e7477  mov     eax, [rdi+50h]
0x1800e747a  mov     [rbp-10h+arg_0], eax
0x1800e747d  mov     rax, [rdi+48h]
0x1800e7481  mov     [rbp-10h+var_40], rax
0x1800e7485  mov     eax, [rdi+20h]
0x1800e7488  mov     dword ptr [rbp-10h+arg_10], eax
0x1800e748b  mov     rax, [rdi+18h]
0x1800e748f  mov     [rbp-10h+var_38], rax
0x1800e7493  mov     eax, [rdi]
0x1800e7495  mov     dword ptr [rbp-10h+arg_18], eax
0x1800e7498  mov     rax, [rdi+80h]
0x1800e749f  mov     [rbp-10h+var_30], rax
0x1800e74a3  mov     eax, [rdi+40h]
0x1800e74a6  mov     [rbp-10h+var_70], eax
0x1800e74a9  mov     rax, [rdi+38h]
0x1800e74ad  mov     [rbp-10h+var_28], rax
0x1800e74b1  mov     eax, [rdi+8]
0x1800e74b4  mov     [rbp-10h+var_6C], eax
0x1800e74b7  mov     eax, 1000000h
0x1800e74bc  mov     [rbp-10h+var_20], rax
0x1800e74c0  mov     [rbp-10h+var_18], rax
0x1800e74c4  lea     rax, [rbp-10h+var_68]
0x1800e74c8  mov     [rsp+120h+var_80], rax
0x1800e74d0  lea     rax, [rbp-10h+var_60]
0x1800e74d4  mov     [rsp+120h+var_88], rax
0x1800e74dc  lea     rax, [rbp-10h+var_58]
0x1800e74e0  mov     [rsp+120h+var_90], rax
0x1800e74e8  lea     rax, [rbp-10h+arg_8]
0x1800e74ec  mov     [rsp+120h+var_98], rax
0x1800e74f4  lea     rax, [rbp-10h+var_50]
0x1800e74f8  mov     [rsp+120h+var_A0], rax
0x1800e7500  lea     rax, [rbp-10h+var_48]
0x1800e7504  mov     [rsp+120h+var_A8], rax
0x1800e7509  lea     rax, [rbp-10h+arg_0]
0x1800e750d  mov     [rsp+120h+var_B0], rax
0x1800e7512  lea     rax, [rbp-10h+var_40]
0x1800e7516  mov     [rsp+120h+var_B8], rax
0x1800e751b  lea     rax, [rbp-10h+arg_10]
0x1800e751f  mov     [rsp+120h+var_C0], rax
0x1800e7524  lea     rax, [rbp-10h+var_38]
0x1800e7528  mov     [rsp+120h+var_C8], rax
0x1800e752d  lea     rax, [rbp-10h+arg_18]
0x1800e7531  mov     [rsp+120h+var_D0], rax
0x1800e7536  lea     rax, [rbp-10h+var_30]
0x1800e753a  mov     [rsp+120h+var_D8], rax
0x1800e753f  lea     rax, [rbp-10h+var_70]
0x1800e7543  mov     [rsp+120h+var_E0], rax
0x1800e7548  lea     rax, [rbp-10h+var_28]
0x1800e754c  mov     [rsp+120h+var_E8], rax
0x1800e7551  lea     rax, [rbp-10h+var_6C]
0x1800e7555  mov     [rsp+120h+var_F0], rax
0x1800e755a  lea     rax, [rbp-10h+var_20]
0x1800e755e  mov     [rsp+120h+var_F8], rax
0x1800e7563  lea     rax, [rbp-10h+var_18]
0x1800e7567  mov     [rsp+120h+var_100], rax
0x1800e756c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564566@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800e7571  jmp     loc_1800E7602
0x1800e7576  call    ?zInternalStop@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800e757b  call    ?Provider@CloudRestoreLauncherTelemetry@@SAPEBU_tlgProvider_t@@XZ; CloudRestoreLauncherTelemetry::Provider(void)
0x1800e7580  mov     rdi, rax
0x1800e7583  mov     ecx, [rax]
0x1800e7585  cmp     ecx, 5
0x1800e7588  jbe     short loc_1800E7602
0x1800e758a  mov     rdx, 400000000000h
0x1800e7594  mov     rcx, rax
0x1800e7597  call    _tlgKeywordOn
0x1800e759c  test    al, al
0x1800e759e  jz      short loc_1800E7602
0x1800e75a0  lea     rax, aRestoreComplet; "Restore Completed"
0x1800e75a7  mov     [rbp-10h+arg_10], rax
0x1800e75ab  call    cs:__imp_GetCurrentThreadId
0x1800e75b1  mov     r8, [rbx+110h]
0x1800e75b8  lea     rdx, unk_18015C2D6
0x1800e75bf  mov     dword ptr [rbp-10h+arg_8], eax
0x1800e75c2  mov     rcx, rdi
0x1800e75c5  mov     eax, [r8+48h]
0x1800e75c9  add     r8, 8
0x1800e75cd  mov     [rbp-10h+arg_0], eax
0x1800e75d0  mov     eax, 1000000h
0x1800e75d5  mov     [rbp-10h+arg_18], rax
0x1800e75d9  lea     rax, [rbp-10h+arg_10]
0x1800e75dd  mov     [rsp+120h+var_E8], rax
0x1800e75e2  lea     rax, [rbp-10h+arg_8]
0x1800e75e6  mov     [rsp+120h+var_F0], rax
0x1800e75eb  lea     rax, [rbp-10h+arg_0]
0x1800e75ef  mov     [rsp+120h+var_F8], rax
0x1800e75f4  lea     rax, [rbp-10h+arg_18]
0x1800e75f8  mov     [rsp+120h+var_100], rax
0x1800e75fd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800e7602  mov     rcx, rbx
0x1800e7605  add     rsp, 110h
0x1800e760c  pop     rdi
0x1800e760d  pop     rbx
0x1800e760e  pop     rbp
0x1800e760f  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
