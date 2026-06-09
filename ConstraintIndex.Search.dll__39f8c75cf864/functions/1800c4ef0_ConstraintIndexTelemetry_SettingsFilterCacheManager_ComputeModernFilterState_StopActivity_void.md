# ConstraintIndexTelemetry::SettingsFilterCacheManager_ComputeModernFilterState::StopActivity(void)

- ea: `0x1800c4ef0`
- end: `0x1800c5142`
- name: `?StopActivity@SettingsFilterCacheManager_ComputeModernFilterState@ConstraintIndexTelemetry@@MEAAXXZ`
- size: `594`
- prototype: `void __fastcall(ConstraintIndexTelemetry::SettingsFilterCacheManager_ComputeModernFilterState *__hidden this)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180001314`
- `0x1800019ec`
- `0x18000243c`
- `0x18003bf74`
- `0x18003c9b8`
- `0x180040bb8`
- `0x1800c4ef0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c50e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800c50e3`

## pseudocode

```c
void __fastcall ConstraintIndexTelemetry::SettingsFilterCacheManager_ComputeModernFilterState::StopActivity(
        ConstraintIndexTelemetry::SettingsFilterCacheManager_ComputeModernFilterState *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  const struct _tlgProvider_t *v5; // rax
  __int64 v6; // r8
  int v7; // r9d
  __int64 v8; // r8
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  int v12; // edi
  DWORD CurrentThreadId; // eax
  __int64 v14; // r8
  int v15; // r9d
  int v16; // [rsp+C0h] [rbp-80h] BYREF
  int v17; // [rsp+C4h] [rbp-7Ch] BYREF
  int v18; // [rsp+C8h] [rbp-78h] BYREF
  int v19; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v20; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v21; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v22; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v23; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v24; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v25; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v26; // [rsp+100h] [rbp-40h] BYREF
  __int64 v27; // [rsp+108h] [rbp-38h] BYREF
  __int64 v28; // [rsp+110h] [rbp-30h] BYREF
  __int64 v29; // [rsp+118h] [rbp-28h] BYREF
  __int64 v30[4]; // [rsp+120h] [rbp-20h] BYREF
  __int64 v31; // [rsp+150h] [rbp+10h] BYREF
  __int64 v32; // [rsp+158h] [rbp+18h] BYREF
  __int64 v33; // [rsp+160h] [rbp+20h] BYREF
  __int64 v34; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v5 = CortanaSearchTelemetryLogging::Provider();
    if ( *(_DWORD *)v5 > 5u && (unsigned __int8)tlgKeywordOn(v5, 1, v6, v5) )
    {
      v20 = *((_QWORD *)v4 + 6);
      LODWORD(v31) = v4[17];
      LODWORD(v32) = v4[4];
      v21 = *((_QWORD *)v4 + 15);
      v22 = *((_QWORD *)v4 + 14);
      v8 = *((_QWORD *)this + 34);
      LODWORD(v33) = v4[26];
      v23 = *((_QWORD *)v4 + 12);
      v24 = *((_QWORD *)v4 + 11);
      LODWORD(v34) = v4[20];
      v25 = *((_QWORD *)v4 + 9);
      v16 = v4[8];
      v26 = *((_QWORD *)v4 + 3);
      v17 = *v4;
      v27 = *((_QWORD *)v4 + 16);
      v18 = v4[16];
      v28 = *((_QWORD *)v4 + 7);
      v19 = v4[2];
      v29 = 0x1000000;
      v30[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        v7,
        (int)&dword_180114054,
        v8 + 8,
        (__int64)v30,
        (__int64)&v29,
        (__int64)&v19,
        (__int64)&v28,
        (__int64)&v18,
        (__int64)&v27,
        (__int64)&v17,
        (__int64)&v26,
        (__int64)&v16,
        (__int64)&v25,
        (__int64)&v34,
        (__int64)&v24,
        (__int64)&v23,
        (__int64)&v33,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&v20);
    }
  }
  else
  {
    wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop();
    v9 = CortanaSearchTelemetryLogging::Provider();
    v12 = (int)v9;
    if ( *(_DWORD *)v9 > 5u && (unsigned __int8)tlgKeywordOn(v9, 1, v10, v11) )
    {
      CurrentThreadId = GetCurrentThreadId();
      v14 = *((_QWORD *)this + 34);
      LODWORD(v31) = CurrentThreadId;
      LODWORD(v32) = *(_DWORD *)(v14 + 72);
      v33 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v12,
        (unsigned int)&unk_180113FE0,
        v14 + 8,
        v15,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v31);
    }
  }
  wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(this);
}

```

## disassembly

```asm
0x1800c4ef0  push    rbp
0x1800c4ef2  push    rbx
0x1800c4ef3  push    rdi
0x1800c4ef4  lea     rbp, [rsp+10h]
0x1800c4ef9  sub     rsp, 130h
0x1800c4f00  mov     rdi, [rcx+110h]
0x1800c4f07  mov     rbx, rcx
0x1800c4f0a  mov     eax, [rdi+48h]
0x1800c4f0d  test    eax, eax
0x1800c4f0f  jns     loc_1800C50BE
0x1800c4f15  add     rdi, 50h ; 'P'
0x1800c4f19  cmp     eax, [rdi+8]
0x1800c4f1c  jnz     loc_1800C50BE
0x1800c4f22  test    rdi, rdi
0x1800c4f25  jz      loc_1800C50BE
0x1800c4f2b  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800c4f30  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x1800c4f35  mov     r9, rax
0x1800c4f38  mov     ecx, [rax]
0x1800c4f3a  cmp     ecx, 5
0x1800c4f3d  jbe     loc_1800C5130
0x1800c4f43  mov     edx, 1
0x1800c4f48  mov     rcx, rax
0x1800c4f4b  call    _tlgKeywordOn
0x1800c4f50  test    al, al
0x1800c4f52  jz      loc_1800C5130
0x1800c4f58  mov     rax, [rdi+30h]
0x1800c4f5c  lea     rdx, dword_180114054; int
0x1800c4f63  mov     [rbp+var_70], rax
0x1800c4f67  mov     rcx, r9; int
0x1800c4f6a  mov     eax, [rdi+44h]
0x1800c4f6d  mov     dword ptr [rbp+arg_0], eax
0x1800c4f70  mov     eax, [rdi+10h]
0x1800c4f73  mov     dword ptr [rbp+arg_8], eax
0x1800c4f76  mov     rax, [rdi+78h]
0x1800c4f7a  mov     [rbp+var_68], rax
0x1800c4f7e  mov     rax, [rdi+70h]
0x1800c4f82  mov     [rbp+var_60], rax
0x1800c4f86  mov     eax, [rdi+68h]
0x1800c4f89  mov     r8, [rbx+110h]
0x1800c4f90  mov     dword ptr [rbp+arg_10], eax
0x1800c4f93  add     r8, 8; int
0x1800c4f97  mov     rax, [rdi+60h]
0x1800c4f9b  mov     [rbp+var_58], rax
0x1800c4f9f  mov     rax, [rdi+58h]
0x1800c4fa3  mov     [rbp+var_50], rax
0x1800c4fa7  mov     eax, [rdi+50h]
0x1800c4faa  mov     dword ptr [rbp+arg_18], eax
0x1800c4fad  mov     rax, [rdi+48h]
0x1800c4fb1  mov     [rbp+var_48], rax
0x1800c4fb5  mov     eax, [rdi+20h]
0x1800c4fb8  mov     dword ptr [rbp+var_80], eax
0x1800c4fbb  mov     rax, [rdi+18h]
0x1800c4fbf  mov     [rbp+var_40], rax
0x1800c4fc3  mov     eax, [rdi]
0x1800c4fc5  mov     dword ptr [rbp+var_80+4], eax
0x1800c4fc8  mov     rax, [rdi+80h]
0x1800c4fcf  mov     [rbp+var_38], rax
0x1800c4fd3  mov     eax, [rdi+40h]
0x1800c4fd6  mov     dword ptr [rbp+var_78], eax
0x1800c4fd9  mov     rax, [rdi+38h]
0x1800c4fdd  mov     [rbp+var_30], rax
0x1800c4fe1  mov     eax, [rdi+8]
0x1800c4fe4  mov     dword ptr [rbp+var_78+4], eax
0x1800c4fe7  lea     rax, [rbp+var_70]
0x1800c4feb  mov     [rsp+140h+var_90], rax; __int64
0x1800c4ff3  lea     rax, [rbp+arg_0]
0x1800c4ff7  mov     [rsp+140h+var_98], rax; __int64
0x1800c4fff  lea     rax, [rbp+arg_8]
0x1800c5003  mov     [rsp+140h+var_A0], rax; __int64
0x1800c500b  lea     rax, [rbp+var_68]
0x1800c500f  mov     [rsp+140h+var_A8], rax; __int64
0x1800c5017  lea     rax, [rbp+var_60]
0x1800c501b  mov     [rsp+140h+var_B0], rax; __int64
0x1800c5023  lea     rax, [rbp+arg_10]
0x1800c5027  mov     [rsp+140h+var_B8], rax; __int64
0x1800c502f  lea     rax, [rbp+var_58]
0x1800c5033  mov     [rsp+140h+var_C0], rax; __int64
0x1800c503b  lea     rax, [rbp+var_50]
0x1800c503f  mov     [rsp+140h+var_C8], rax; __int64
0x1800c5044  lea     rax, [rbp+arg_18]
0x1800c5048  mov     [rsp+140h+var_D0], rax; __int64
0x1800c504d  lea     rax, [rbp+var_48]
0x1800c5051  mov     [rsp+140h+var_D8], rax; __int64
0x1800c5056  lea     rax, [rbp+var_80]
0x1800c505a  mov     [rsp+140h+var_E0], rax; __int64
0x1800c505f  lea     rax, [rbp+var_40]
0x1800c5063  mov     [rsp+140h+var_E8], rax; __int64
0x1800c5068  lea     rax, [rbp+var_80+4]
0x1800c506c  mov     [rsp+140h+var_F0], rax; __int64
0x1800c5071  lea     rax, [rbp+var_38]
0x1800c5075  mov     [rsp+140h+var_F8], rax; __int64
0x1800c507a  lea     rax, [rbp+var_78]
0x1800c507e  mov     [rsp+140h+var_100], rax; __int64
0x1800c5083  lea     rax, [rbp+var_30]
0x1800c5087  mov     [rsp+140h+var_108], rax; __int64
0x1800c508c  lea     rax, [rbp+var_78+4]
0x1800c5090  mov     [rsp+140h+var_110], rax; __int64
0x1800c5095  lea     rax, [rbp+var_28]
0x1800c5099  mov     [rsp+140h+var_118], rax; __int64
0x1800c509e  lea     rax, [rbp+var_20]
0x1800c50a2  mov     [rsp+140h+var_120], rax; __int64
0x1800c50a7  mov     [rbp+var_28], 1000000h
0x1800c50af  mov     [rbp+var_20], 0
0x1800c50b7  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@_W@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@_W@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800c50bc  jmp     short loc_1800C5130
0x1800c50be  call    ?zInternalStop@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::zInternalStop(void)
0x1800c50c3  call    ?Provider@CortanaSearchTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; CortanaSearchTelemetryLogging::Provider(void)
0x1800c50c8  mov     rdi, rax
0x1800c50cb  mov     ecx, [rax]
0x1800c50cd  cmp     ecx, 5
0x1800c50d0  jbe     short loc_1800C5130
0x1800c50d2  mov     edx, 1
0x1800c50d7  mov     rcx, rax
0x1800c50da  call    _tlgKeywordOn
0x1800c50df  test    al, al
0x1800c50e1  jz      short loc_1800C5130
0x1800c50e3  call    cs:__imp_GetCurrentThreadId
0x1800c50e9  mov     r8, [rbx+110h]
0x1800c50f0  lea     rdx, unk_180113FE0
0x1800c50f7  mov     dword ptr [rbp+arg_0], eax
0x1800c50fa  mov     rcx, rdi
0x1800c50fd  mov     eax, [r8+48h]
0x1800c5101  add     r8, 8
0x1800c5105  mov     dword ptr [rbp+arg_8], eax
0x1800c5108  lea     rax, [rbp+arg_0]
0x1800c510c  mov     [rsp+140h+var_110], rax
0x1800c5111  lea     rax, [rbp+arg_8]
0x1800c5115  mov     [rsp+140h+var_118], rax
0x1800c511a  lea     rax, [rbp+arg_10]
0x1800c511e  mov     [rsp+140h+var_120], rax
0x1800c5123  mov     [rbp+arg_10], 0
0x1800c512b  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800c5130  mov     rcx, rbx
0x1800c5133  add     rsp, 130h
0x1800c513a  pop     rdi
0x1800c513b  pop     rbx
0x1800c513c  pop     rbp
0x1800c513d  jmp     ?IgnoreCurrentThread@?$ActivityBase@VCortanaSearchTelemetryLogging@@$00$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<CortanaSearchTelemetryLogging,1,1,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
