# CloudRestoreLauncherTelemetry::RegistryListener_ProcessInstalledProducts::StopActivity(void)

- ea: `0x180081d70`
- end: `0x180081f9f`
- name: `?StopActivity@RegistryListener_ProcessInstalledProducts@CloudRestoreLauncherTelemetry@@MEAAXXZ`
- size: `559`
- prototype: `void __fastcall(CloudRestoreLauncherTelemetry::RegistryListener_ProcessInstalledProducts *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callees

- `0x180001314`
- `0x180001698`
- `0x180018674`
- `0x1800195cc`
- `0x18001e020`
- `0x180081d70`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180081f3d`
- `KERNEL32!GetCurrentThreadId` at `0x180081f3d`

## pseudocode

```c
void __fastcall CloudRestoreLauncherTelemetry::RegistryListener_ProcessInstalledProducts::StopActivity(
        CloudRestoreLauncherTelemetry::RegistryListener_ProcessInstalledProducts *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  __int64 v5; // rdx
  __int64 v6; // r8
  const struct _tlgProvider_t *v7; // r9
  __int64 v8; // rcx
  __int64 v9; // r8
  const struct _tlgProvider_t *v10; // rax
  int v11; // edi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  int v14; // [rsp+C0h] [rbp-80h] BYREF
  int v15; // [rsp+C4h] [rbp-7Ch] BYREF
  int v16; // [rsp+C8h] [rbp-78h] BYREF
  int v17; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v18; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v19; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v20; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v21; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v22; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v23; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v24; // [rsp+100h] [rbp-40h] BYREF
  __int64 v25; // [rsp+108h] [rbp-38h] BYREF
  __int64 v26; // [rsp+110h] [rbp-30h] BYREF
  __int64 v27; // [rsp+118h] [rbp-28h] BYREF
  _QWORD v28[4]; // [rsp+120h] [rbp-20h] BYREF
  DWORD v29; // [rsp+150h] [rbp+10h] BYREF
  int v30; // [rsp+158h] [rbp+18h] BYREF
  __int64 v31; // [rsp+160h] [rbp+20h] BYREF
  int v32; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v7 = CloudRestoreLauncherTelemetry::Provider();
    if ( *(_DWORD *)v7 > 5u )
    {
      v8 = *((_QWORD *)v4 + 6);
      v20 = *((_QWORD *)v4 + 14);
      v9 = *((_QWORD *)this + 34);
      LODWORD(v31) = v4[26];
      v21 = *((_QWORD *)v4 + 12);
      v22 = *((_QWORD *)v4 + 11);
      v32 = v4[20];
      v23 = *((_QWORD *)v4 + 9);
      v14 = v4[8];
      v24 = *((_QWORD *)v4 + 3);
      v15 = *v4;
      v25 = *((_QWORD *)v4 + 16);
      v16 = v4[16];
      v26 = *((_QWORD *)v4 + 7);
      v17 = v4[2];
      v18 = v8;
      v29 = v4[17];
      v30 = v4[4];
      v19 = *((_QWORD *)v4 + 15);
      v27 = 0x1000000;
      v28[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (_DWORD)v7,
        (unsigned int)&byte_180156087,
        v9 + 8,
        (_DWORD)v7,
        (__int64)v28,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v16,
        (__int64)&v25,
        (__int64)&v15,
        (__int64)&v24,
        (__int64)&v14,
        (__int64)&v23,
        (__int64)&v32,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v31,
        (__int64)&v20,
        (__int64)&v19,
        (__int64)&v30,
        (__int64)&v29,
        (__int64)&v18);
    }
  }
  else
  {
    wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v10 = CloudRestoreLauncherTelemetry::Provider();
    v11 = (int)v10;
    if ( *(_DWORD *)v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v13 = *((_QWORD *)this + 34);
      v29 = CurrentThreadId;
      v30 = *(_DWORD *)(v13 + 72);
      v31 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        (unsigned int)byte_1801561EB,
        v13 + 8,
        0,
        (__int64)&v31,
        (__int64)&v30,
        (__int64)&v29);
    }
  }
  wil::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(
    this,
    v5,
    v6,
    v7);
}

```

## disassembly

```asm
0x180081d70  push    rbp
0x180081d72  push    rbx
0x180081d73  push    rdi
0x180081d74  lea     rbp, [rsp+10h]
0x180081d79  sub     rsp, 130h
0x180081d80  mov     rdi, [rcx+110h]
0x180081d87  mov     rbx, rcx
0x180081d8a  mov     eax, [rdi+48h]
0x180081d8d  test    eax, eax
0x180081d8f  jns     loc_180081F29
0x180081d95  add     rdi, 50h ; 'P'
0x180081d99  cmp     eax, [rdi+8]
0x180081d9c  jnz     loc_180081F29
0x180081da2  test    rdi, rdi
0x180081da5  jz      loc_180081F29
0x180081dab  call    ?zInternalStop@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180081db0  call    ?Provider@CloudRestoreLauncherTelemetry@@SAPEBU_tlgProvider_t@@XZ; CloudRestoreLauncherTelemetry::Provider(void)
0x180081db5  mov     r9, rax
0x180081db8  mov     ecx, [rax]
0x180081dba  cmp     ecx, 5
0x180081dbd  jbe     loc_180081F8D
0x180081dc3  mov     rax, [rdi+70h]
0x180081dc7  lea     rdx, byte_180156087
0x180081dce  mov     rcx, [rdi+30h]
0x180081dd2  mov     [rbp+var_60], rax
0x180081dd6  mov     eax, [rdi+68h]
0x180081dd9  mov     r8, [rbx+110h]
0x180081de0  mov     dword ptr [rbp+arg_10], eax
0x180081de3  add     r8, 8
0x180081de7  mov     rax, [rdi+60h]
0x180081deb  mov     [rbp+var_58], rax
0x180081def  mov     rax, [rdi+58h]
0x180081df3  mov     [rbp+var_50], rax
0x180081df7  mov     eax, [rdi+50h]
0x180081dfa  mov     [rbp+arg_18], eax
0x180081dfd  mov     rax, [rdi+48h]
0x180081e01  mov     [rbp+var_48], rax
0x180081e05  mov     eax, [rdi+20h]
0x180081e08  mov     [rbp+var_80], eax
0x180081e0b  mov     rax, [rdi+18h]
0x180081e0f  mov     [rbp+var_40], rax
0x180081e13  mov     eax, [rdi]
0x180081e15  mov     [rbp+var_7C], eax
0x180081e18  mov     rax, [rdi+80h]
0x180081e1f  mov     [rbp+var_38], rax
0x180081e23  mov     eax, [rdi+40h]
0x180081e26  mov     [rbp+var_78], eax
0x180081e29  mov     rax, [rdi+38h]
0x180081e2d  mov     [rbp+var_30], rax
0x180081e31  mov     eax, [rdi+8]
0x180081e34  mov     [rbp+var_74], eax
0x180081e37  lea     rax, [rbp+var_70]
0x180081e3b  mov     [rsp+140h+var_90], rax
0x180081e43  lea     rax, [rbp+arg_0]
0x180081e47  mov     [rsp+140h+var_98], rax
0x180081e4f  lea     rax, [rbp+arg_8]
0x180081e53  mov     [rsp+140h+var_A0], rax
0x180081e5b  lea     rax, [rbp+var_68]
0x180081e5f  mov     [rsp+140h+var_A8], rax
0x180081e67  lea     rax, [rbp+var_60]
0x180081e6b  mov     [rsp+140h+var_B0], rax
0x180081e73  lea     rax, [rbp+arg_10]
0x180081e77  mov     [rsp+140h+var_B8], rax
0x180081e7f  lea     rax, [rbp+var_58]
0x180081e83  mov     [rsp+140h+var_C0], rax
0x180081e8b  lea     rax, [rbp+var_50]
0x180081e8f  mov     [rsp+140h+var_C8], rax
0x180081e94  lea     rax, [rbp+arg_18]
0x180081e98  mov     [rsp+140h+var_D0], rax
0x180081e9d  lea     rax, [rbp+var_48]
0x180081ea1  mov     [rsp+140h+var_D8], rax
0x180081ea6  lea     rax, [rbp+var_80]
0x180081eaa  mov     [rsp+140h+var_E0], rax
0x180081eaf  lea     rax, [rbp+var_40]
0x180081eb3  mov     [rsp+140h+var_E8], rax
0x180081eb8  lea     rax, [rbp+var_7C]
0x180081ebc  mov     [rsp+140h+var_F0], rax
0x180081ec1  lea     rax, [rbp+var_38]
0x180081ec5  mov     [rsp+140h+var_F8], rax
0x180081eca  lea     rax, [rbp+var_78]
0x180081ece  mov     [rsp+140h+var_100], rax
0x180081ed3  lea     rax, [rbp+var_30]
0x180081ed7  mov     [rsp+140h+var_108], rax
0x180081edc  lea     rax, [rbp+var_74]
0x180081ee0  mov     [rbp+var_70], rcx
0x180081ee4  mov     ecx, [rdi+44h]
0x180081ee7  mov     [rsp+140h+var_110], rax
0x180081eec  lea     rax, [rbp+var_28]
0x180081ef0  mov     [rbp+arg_0], ecx
0x180081ef3  mov     ecx, [rdi+10h]
0x180081ef6  mov     [rbp+arg_8], ecx
0x180081ef9  mov     rcx, [rdi+78h]
0x180081efd  mov     [rsp+140h+var_118], rax
0x180081f02  lea     rax, [rbp+var_20]
0x180081f06  mov     [rbp+var_68], rcx
0x180081f0a  mov     rcx, r9
0x180081f0d  mov     [rsp+140h+var_120], rax
0x180081f12  mov     [rbp+var_28], 1000000h
0x180081f1a  mov     [rbp+var_20], 0
0x180081f22  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180081f27  jmp     short loc_180081F8D
0x180081f29  call    ?zInternalStop@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0IAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,140737488355328,5,16777216,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x180081f2e  call    ?Provider@CloudRestoreLauncherTelemetry@@SAPEBU_tlgProvider_t@@XZ; CloudRestoreLauncherTelemetry::Provider(void)
0x180081f33  mov     rdi, rax
0x180081f36  mov     ecx, [rax]
0x180081f38  cmp     ecx, 5
0x180081f3b  jbe     short loc_180081F8D
0x180081f3d  call    cs:__imp_GetCurrentThreadId
0x180081f43  mov     r8, [rbx+110h]
0x180081f4a  lea     rdx, byte_1801561EB
0x180081f51  mov     [rbp+arg_0], eax
0x180081f54  xor     r9d, r9d
0x180081f57  lea     rax, [rbp+arg_0]
0x180081f5b  mov     [rsp+140h+var_110], rax
0x180081f60  lea     rax, [rbp+arg_8]
0x180081f64  mov     ecx, [r8+48h]
0x180081f68  add     r8, 8
0x180081f6c  mov     [rsp+140h+var_118], rax
0x180081f71  lea     rax, [rbp+arg_10]
0x180081f75  mov     [rbp+arg_8], ecx
0x180081f78  mov     rcx, rdi
0x180081f7b  mov     [rsp+140h+var_120], rax
0x180081f80  mov     [rbp+arg_10], 0
0x180081f88  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180081f8d  mov     rcx, rbx
0x180081f90  add     rsp, 130h
0x180081f97  pop     rdi
0x180081f98  pop     rbx
0x180081f99  pop     rbp
0x180081f9a  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCloudRestoreLauncherTelemetry@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CloudRestoreLauncherTelemetry,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
