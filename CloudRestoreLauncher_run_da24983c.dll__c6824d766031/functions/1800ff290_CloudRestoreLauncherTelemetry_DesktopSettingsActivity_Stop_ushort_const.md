# CloudRestoreLauncherTelemetry::DesktopSettingsActivity::Stop(ushort const *)

- ea: `0x1800ff290`
- end: `0x1800ff4e4`
- name: `?Stop@DesktopSettingsActivity@CloudRestoreLauncherTelemetry@@QEAAXPEBG@Z`
- size: `596`
- prototype: `void __fastcall(CloudRestoreLauncherTelemetry::DesktopSettingsActivity *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800fec70`

## callees

- `0x180001edc`
- `0x180003ab0`
- `0x180003d9c`
- `0x180018674`
- `0x1800195cc`
- `0x18001e020`
- `0x1800ff290`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800ff47b`
- `KERNEL32!GetCurrentThreadId` at `0x1800ff47b`

## string_xrefs

- `0x1800ff308`: `Restore Completed`
- `0x1800ff470`: `Restore Completed`

## pseudocode

```c
void __fastcall CloudRestoreLauncherTelemetry::DesktopSettingsActivity::Stop(
        CloudRestoreLauncherTelemetry::DesktopSettingsActivity *this,
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
        (unsigned int)&unk_18015F6ED,
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
        (unsigned int)&unk_18015F686,
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
0x1800ff290  mov     [rsp-8+arg_8], rdx
0x1800ff295  push    rbp
0x1800ff296  push    rbx
0x1800ff297  push    rdi
0x1800ff298  lea     rbp, [rsp+20h]
0x1800ff29d  sub     rsp, 110h
0x1800ff2a4  mov     rdi, [rcx+110h]
0x1800ff2ab  mov     rbx, rcx
0x1800ff2ae  mov     eax, [rdi+48h]
0x1800ff2b1  test    eax, eax
0x1800ff2b3  jns     loc_1800FF446
0x1800ff2b9  add     rdi, 50h ; 'P'
0x1800ff2bd  cmp     eax, [rdi+8]
0x1800ff2c0  jnz     loc_1800FF446
0x1800ff2c6  test    rdi, rdi
0x1800ff2c9  jz      loc_1800FF446
0x1800ff2cf  call    ?zInternalStop@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800ff2d4  call    ?Provider@CloudRestoreLauncherTelemetry@@SAPEBU_tlgProvider_t@@XZ; CloudRestoreLauncherTelemetry::Provider(void)
0x1800ff2d9  mov     r9, rax
0x1800ff2dc  mov     ecx, [rax]
0x1800ff2de  cmp     ecx, 5
0x1800ff2e1  jbe     loc_1800FF4D2
0x1800ff2e7  mov     rdx, 400000000000h
0x1800ff2f1  mov     rcx, rax
0x1800ff2f4  call    _tlgKeywordOn
0x1800ff2f9  test    al, al
0x1800ff2fb  jz      loc_1800FF4D2
0x1800ff301  mov     r8, [rbx+110h]
0x1800ff308  lea     rax, aRestoreComplet; "Restore Completed"
0x1800ff30f  mov     [rbp-10h+var_68], rax
0x1800ff313  lea     rdx, unk_18015F6ED
0x1800ff31a  mov     rax, [rdi+78h]
0x1800ff31e  add     r8, 8
0x1800ff322  mov     [rbp-10h+var_60], rax
0x1800ff326  mov     rcx, r9
0x1800ff329  mov     rax, [rdi+70h]
0x1800ff32d  mov     [rbp-10h+var_58], rax
0x1800ff331  mov     eax, [rdi+68h]
0x1800ff334  mov     dword ptr [rbp-10h+arg_8], eax
0x1800ff337  mov     rax, [rdi+60h]
0x1800ff33b  mov     [rbp-10h+var_50], rax
0x1800ff33f  mov     rax, [rdi+58h]
0x1800ff343  mov     [rbp-10h+var_48], rax
0x1800ff347  mov     eax, [rdi+50h]
0x1800ff34a  mov     [rbp-10h+arg_0], eax
0x1800ff34d  mov     rax, [rdi+48h]
0x1800ff351  mov     [rbp-10h+var_40], rax
0x1800ff355  mov     eax, [rdi+20h]
0x1800ff358  mov     dword ptr [rbp-10h+arg_10], eax
0x1800ff35b  mov     rax, [rdi+18h]
0x1800ff35f  mov     [rbp-10h+var_38], rax
0x1800ff363  mov     eax, [rdi]
0x1800ff365  mov     dword ptr [rbp-10h+arg_18], eax
0x1800ff368  mov     rax, [rdi+80h]
0x1800ff36f  mov     [rbp-10h+var_30], rax
0x1800ff373  mov     eax, [rdi+40h]
0x1800ff376  mov     [rbp-10h+var_70], eax
0x1800ff379  mov     rax, [rdi+38h]
0x1800ff37d  mov     [rbp-10h+var_28], rax
0x1800ff381  mov     eax, [rdi+8]
0x1800ff384  mov     [rbp-10h+var_6C], eax
0x1800ff387  mov     eax, 1000000h
0x1800ff38c  mov     [rbp-10h+var_20], rax
0x1800ff390  mov     [rbp-10h+var_18], rax
0x1800ff394  lea     rax, [rbp-10h+var_68]
0x1800ff398  mov     [rsp+120h+var_80], rax
0x1800ff3a0  lea     rax, [rbp-10h+var_60]
0x1800ff3a4  mov     [rsp+120h+var_88], rax
0x1800ff3ac  lea     rax, [rbp-10h+var_58]
0x1800ff3b0  mov     [rsp+120h+var_90], rax
0x1800ff3b8  lea     rax, [rbp-10h+arg_8]
0x1800ff3bc  mov     [rsp+120h+var_98], rax
0x1800ff3c4  lea     rax, [rbp-10h+var_50]
0x1800ff3c8  mov     [rsp+120h+var_A0], rax
0x1800ff3d0  lea     rax, [rbp-10h+var_48]
0x1800ff3d4  mov     [rsp+120h+var_A8], rax
0x1800ff3d9  lea     rax, [rbp-10h+arg_0]
0x1800ff3dd  mov     [rsp+120h+var_B0], rax
0x1800ff3e2  lea     rax, [rbp-10h+var_40]
0x1800ff3e6  mov     [rsp+120h+var_B8], rax
0x1800ff3eb  lea     rax, [rbp-10h+arg_10]
0x1800ff3ef  mov     [rsp+120h+var_C0], rax
0x1800ff3f4  lea     rax, [rbp-10h+var_38]
0x1800ff3f8  mov     [rsp+120h+var_C8], rax
0x1800ff3fd  lea     rax, [rbp-10h+arg_18]
0x1800ff401  mov     [rsp+120h+var_D0], rax
0x1800ff406  lea     rax, [rbp-10h+var_30]
0x1800ff40a  mov     [rsp+120h+var_D8], rax
0x1800ff40f  lea     rax, [rbp-10h+var_70]
0x1800ff413  mov     [rsp+120h+var_E0], rax
0x1800ff418  lea     rax, [rbp-10h+var_28]
0x1800ff41c  mov     [rsp+120h+var_E8], rax
0x1800ff421  lea     rax, [rbp-10h+var_6C]
0x1800ff425  mov     [rsp+120h+var_F0], rax
0x1800ff42a  lea     rax, [rbp-10h+var_20]
0x1800ff42e  mov     [rsp+120h+var_F8], rax
0x1800ff433  lea     rax, [rbp-10h+var_18]
0x1800ff437  mov     [rsp+120h+var_100], rax
0x1800ff43c  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@454564566@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800ff441  jmp     loc_1800FF4D2
0x1800ff446  call    ?zInternalStop@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800ff44b  call    ?Provider@CloudRestoreLauncherTelemetry@@SAPEBU_tlgProvider_t@@XZ; CloudRestoreLauncherTelemetry::Provider(void)
0x1800ff450  mov     rdi, rax
0x1800ff453  mov     ecx, [rax]
0x1800ff455  cmp     ecx, 5
0x1800ff458  jbe     short loc_1800FF4D2
0x1800ff45a  mov     rdx, 400000000000h
0x1800ff464  mov     rcx, rax
0x1800ff467  call    _tlgKeywordOn
0x1800ff46c  test    al, al
0x1800ff46e  jz      short loc_1800FF4D2
0x1800ff470  lea     rax, aRestoreComplet; "Restore Completed"
0x1800ff477  mov     [rbp-10h+arg_10], rax
0x1800ff47b  call    cs:__imp_GetCurrentThreadId
0x1800ff481  mov     r8, [rbx+110h]
0x1800ff488  lea     rdx, unk_18015F686
0x1800ff48f  mov     dword ptr [rbp-10h+arg_8], eax
0x1800ff492  mov     rcx, rdi
0x1800ff495  mov     eax, [r8+48h]
0x1800ff499  add     r8, 8
0x1800ff49d  mov     [rbp-10h+arg_0], eax
0x1800ff4a0  mov     eax, 1000000h
0x1800ff4a5  mov     [rbp-10h+arg_18], rax
0x1800ff4a9  lea     rax, [rbp-10h+arg_10]
0x1800ff4ad  mov     [rsp+120h+var_E8], rax
0x1800ff4b2  lea     rax, [rbp-10h+arg_8]
0x1800ff4b6  mov     [rsp+120h+var_F0], rax
0x1800ff4bb  lea     rax, [rbp-10h+arg_0]
0x1800ff4bf  mov     [rsp+120h+var_F8], rax
0x1800ff4c4  lea     rax, [rbp-10h+arg_18]
0x1800ff4c8  mov     [rsp+120h+var_100], rax
0x1800ff4cd  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x1800ff4d2  mov     rcx, rbx
0x1800ff4d5  add     rsp, 110h
0x1800ff4dc  pop     rdi
0x1800ff4dd  pop     rbx
0x1800ff4de  pop     rbp
0x1800ff4df  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
