# LanguageComponentsInstallerTelemetry::UninstallationRequest::StopActivity(void)

- ea: `0x1800258e0`
- end: `0x180025b4f`
- name: `?StopActivity@UninstallationRequest@LanguageComponentsInstallerTelemetry@@MEAAXXZ`
- size: `623`
- prototype: `void __fastcall(LanguageComponentsInstallerTelemetry::UninstallationRequest *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180001658`
- `0x18000196c`
- `0x180018580`
- `0x180018b8c`
- `0x1800195c0`
- `0x1800258e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002593a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025adb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18002593a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180025adb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025af0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025af0`

## pseudocode

```c
void __fastcall LanguageComponentsInstallerTelemetry::UninstallationRequest::StopActivity(
        LanguageComponentsInstallerTelemetry::UninstallationRequest *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  const struct _tlgProvider_t *v6; // r9
  __int64 v7; // rcx
  __int64 v8; // r8
  RTL_SRWLOCK *v9; // rcx
  const struct _tlgProvider_t *v10; // rax
  int v11; // edi
  DWORD CurrentThreadId; // eax
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // [rsp+C0h] [rbp-80h] BYREF
  int v16; // [rsp+C4h] [rbp-7Ch] BYREF
  int v17; // [rsp+C8h] [rbp-78h] BYREF
  int v18; // [rsp+CCh] [rbp-74h] BYREF
  __int64 v19; // [rsp+D0h] [rbp-70h] BYREF
  __int64 v20; // [rsp+D8h] [rbp-68h] BYREF
  __int64 v21; // [rsp+E0h] [rbp-60h] BYREF
  __int64 v22; // [rsp+E8h] [rbp-58h] BYREF
  __int64 v23; // [rsp+F0h] [rbp-50h] BYREF
  __int64 v24; // [rsp+F8h] [rbp-48h] BYREF
  __int64 v25; // [rsp+100h] [rbp-40h] BYREF
  __int64 v26; // [rsp+108h] [rbp-38h] BYREF
  __int64 v27; // [rsp+110h] [rbp-30h] BYREF
  __int64 v28; // [rsp+118h] [rbp-28h] BYREF
  __int64 v29[4]; // [rsp+120h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  __int64 v31; // [rsp+158h] [rbp+18h] BYREF
  __int64 v32; // [rsp+160h] [rbp+20h] BYREF
  __int64 v33; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = LanguageComponentsInstallerTelemetryProvider::Provider();
    if ( *(_DWORD *)v6 > 5u )
    {
      v7 = *((_QWORD *)v4 + 6);
      v21 = *((_QWORD *)v4 + 14);
      v8 = *((_QWORD *)this + 34);
      LODWORD(v32) = v4[26];
      v22 = *((_QWORD *)v4 + 12);
      v23 = *((_QWORD *)v4 + 11);
      LODWORD(v33) = v4[20];
      v24 = *((_QWORD *)v4 + 9);
      v15 = v4[8];
      v25 = *((_QWORD *)v4 + 3);
      v16 = *v4;
      v26 = *((_QWORD *)v4 + 16);
      v17 = v4[16];
      v27 = *((_QWORD *)v4 + 7);
      v18 = v4[2];
      v19 = v7;
      LODWORD(SRWLock) = v4[17];
      LODWORD(v31) = v4[4];
      v20 = *((_QWORD *)v4 + 15);
      v28 = 0x1000000;
      v29[0] = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (int)v6,
        (int)&dword_18002FC4C,
        v8 + 8,
        (__int64)v6,
        (__int64)v29,
        (__int64)&v28,
        (__int64)&v18,
        (const unsigned __int16 **)&v27,
        (__int64)&v17,
        (const unsigned __int16 **)&v26,
        (__int64)&v16,
        (__int64 **)&v25,
        (__int64)&v15,
        (const unsigned __int16 **)&v24,
        (__int64)&v33,
        (const unsigned __int16 **)&v23,
        (__int64 **)&v22,
        (__int64)&v32,
        (const unsigned __int16 **)&v21,
        (__int64 **)&v20,
        (__int64)&v31,
        (__int64)&SRWLock,
        (const unsigned __int16 **)&v19);
    }
  }
  else
  {
    wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v9 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v9 )
      ReleaseSRWLockExclusive(v9);
    v10 = LanguageComponentsInstallerTelemetryProvider::Provider();
    v11 = (int)v10;
    if ( *(_DWORD *)v10 > 5u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v13 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      LODWORD(v31) = *(_DWORD *)(v13 + 72);
      v32 = 0;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v11,
        (int)&unk_18002FDC8,
        v13 + 8,
        v14,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x1800258e0  push    rbp
0x1800258e2  push    rbx
0x1800258e3  push    rdi
0x1800258e4  lea     rbp, [rsp+10h]
0x1800258e9  sub     rsp, 130h
0x1800258f0  mov     rdi, [rcx+110h]
0x1800258f7  mov     rbx, rcx
0x1800258fa  mov     eax, [rdi+48h]
0x1800258fd  test    eax, eax
0x1800258ff  jns     loc_180025ABC
0x180025905  add     rdi, 50h ; 'P'
0x180025909  cmp     eax, [rdi+8]
0x18002590c  jnz     loc_180025ABC
0x180025912  test    rdi, rdi
0x180025915  jz      loc_180025ABC
0x18002591b  lea     rdx, [rbp+SRWLock]
0x18002591f  call    ?LockExclusive@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180025924  mov     rax, [rbx+110h]
0x18002592b  mov     rcx, [rbp+SRWLock]; SRWLock
0x18002592f  mov     dword ptr [rax], 2
0x180025935  test    rcx, rcx
0x180025938  jz      short loc_180025940
0x18002593a  call    cs:__imp_ReleaseSRWLockExclusive
0x180025940  call    ?Provider@LanguageComponentsInstallerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; LanguageComponentsInstallerTelemetryProvider::Provider(void)
0x180025945  mov     r9, rax
0x180025948  mov     ecx, [rax]
0x18002594a  cmp     ecx, 5
0x18002594d  jbe     loc_180025B3D
0x180025953  mov     rax, [rdi+70h]
0x180025957  lea     rdx, dword_18002FC4C; int
0x18002595e  mov     rcx, [rdi+30h]
0x180025962  mov     [rbp+var_60], rax
0x180025966  mov     eax, [rdi+68h]
0x180025969  mov     r8, [rbx+110h]
0x180025970  mov     dword ptr [rbp+arg_10], eax
0x180025973  add     r8, 8; int
0x180025977  mov     rax, [rdi+60h]
0x18002597b  mov     [rbp+var_58], rax
0x18002597f  mov     rax, [rdi+58h]
0x180025983  mov     [rbp+var_50], rax
0x180025987  mov     eax, [rdi+50h]
0x18002598a  mov     dword ptr [rbp+arg_18], eax
0x18002598d  mov     rax, [rdi+48h]
0x180025991  mov     [rbp+var_48], rax
0x180025995  mov     eax, [rdi+20h]
0x180025998  mov     dword ptr [rbp+var_80], eax
0x18002599b  mov     rax, [rdi+18h]
0x18002599f  mov     [rbp+var_40], rax
0x1800259a3  mov     eax, [rdi]
0x1800259a5  mov     dword ptr [rbp+var_80+4], eax
0x1800259a8  mov     rax, [rdi+80h]
0x1800259af  mov     [rbp+var_38], rax
0x1800259b3  mov     eax, [rdi+40h]
0x1800259b6  mov     dword ptr [rbp+var_78], eax
0x1800259b9  mov     rax, [rdi+38h]
0x1800259bd  mov     [rbp+var_30], rax
0x1800259c1  mov     eax, [rdi+8]
0x1800259c4  mov     dword ptr [rbp+var_78+4], eax
0x1800259c7  lea     rax, [rbp+var_70]
0x1800259cb  mov     [rsp+140h+var_90], rax; __int64
0x1800259d3  lea     rax, [rbp+SRWLock]
0x1800259d7  mov     [rsp+140h+var_98], rax; __int64
0x1800259df  lea     rax, [rbp+arg_8]
0x1800259e3  mov     [rsp+140h+var_A0], rax; __int64
0x1800259eb  lea     rax, [rbp+var_68]
0x1800259ef  mov     [rsp+140h+var_A8], rax; __int64
0x1800259f7  lea     rax, [rbp+var_60]
0x1800259fb  mov     [rsp+140h+var_B0], rax; __int64
0x180025a03  lea     rax, [rbp+arg_10]
0x180025a07  mov     [rsp+140h+var_B8], rax; __int64
0x180025a0f  lea     rax, [rbp+var_58]
0x180025a13  mov     [rsp+140h+var_C0], rax; __int64
0x180025a1b  lea     rax, [rbp+var_50]
0x180025a1f  mov     [rsp+140h+var_C8], rax; __int64
0x180025a24  lea     rax, [rbp+arg_18]
0x180025a28  mov     [rsp+140h+var_D0], rax; __int64
0x180025a2d  lea     rax, [rbp+var_48]
0x180025a31  mov     [rsp+140h+var_D8], rax; __int64
0x180025a36  lea     rax, [rbp+var_80]
0x180025a3a  mov     [rsp+140h+var_E0], rax; __int64
0x180025a3f  lea     rax, [rbp+var_40]
0x180025a43  mov     [rsp+140h+var_E8], rax; __int64
0x180025a48  lea     rax, [rbp+var_80+4]
0x180025a4c  mov     [rsp+140h+var_F0], rax; __int64
0x180025a51  lea     rax, [rbp+var_38]
0x180025a55  mov     [rsp+140h+var_F8], rax; __int64
0x180025a5a  lea     rax, [rbp+var_78]
0x180025a5e  mov     [rsp+140h+var_100], rax; __int64
0x180025a63  lea     rax, [rbp+var_30]
0x180025a67  mov     [rsp+140h+var_108], rax; __int64
0x180025a6c  lea     rax, [rbp+var_78+4]
0x180025a70  mov     [rbp+var_70], rcx
0x180025a74  mov     ecx, [rdi+44h]
0x180025a77  mov     [rsp+140h+var_110], rax; __int64
0x180025a7c  lea     rax, [rbp+var_28]
0x180025a80  mov     dword ptr [rbp+SRWLock], ecx
0x180025a83  mov     ecx, [rdi+10h]
0x180025a86  mov     dword ptr [rbp+arg_8], ecx
0x180025a89  mov     rcx, [rdi+78h]
0x180025a8d  mov     [rsp+140h+var_118], rax; __int64
0x180025a92  lea     rax, [rbp+var_20]
0x180025a96  mov     [rbp+var_68], rcx
0x180025a9a  mov     rcx, r9; int
0x180025a9d  mov     [rsp+140h+var_120], rax; __int64
0x180025aa2  mov     [rbp+var_28], 1000000h
0x180025aaa  mov     [rbp+var_20], 0
0x180025ab2  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180025ab7  jmp     loc_180025B3D
0x180025abc  lea     rdx, [rbp+SRWLock]
0x180025ac0  call    ?LockExclusive@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180025ac5  mov     rax, [rbx+110h]
0x180025acc  mov     rcx, [rbp+SRWLock]; SRWLock
0x180025ad0  mov     dword ptr [rax], 2
0x180025ad6  test    rcx, rcx
0x180025ad9  jz      short loc_180025AE1
0x180025adb  call    cs:__imp_ReleaseSRWLockExclusive
0x180025ae1  call    ?Provider@LanguageComponentsInstallerTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; LanguageComponentsInstallerTelemetryProvider::Provider(void)
0x180025ae6  mov     rdi, rax
0x180025ae9  mov     ecx, [rax]
0x180025aeb  cmp     ecx, 5
0x180025aee  jbe     short loc_180025B3D
0x180025af0  call    cs:__imp_GetCurrentThreadId
0x180025af6  mov     r8, [rbx+110h]
0x180025afd  lea     rdx, unk_18002FDC8
0x180025b04  mov     dword ptr [rbp+SRWLock], eax
0x180025b07  lea     rax, [rbp+SRWLock]
0x180025b0b  mov     [rsp+140h+var_110], rax
0x180025b10  lea     rax, [rbp+arg_8]
0x180025b14  mov     [rsp+140h+var_118], rax
0x180025b19  lea     rax, [rbp+arg_10]
0x180025b1d  mov     ecx, [r8+48h]
0x180025b21  add     r8, 8
0x180025b25  mov     dword ptr [rbp+arg_8], ecx
0x180025b28  mov     rcx, rdi
0x180025b2b  mov     [rsp+140h+var_120], rax
0x180025b30  mov     [rbp+arg_10], 0
0x180025b38  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180025b3d  mov     rcx, rbx
0x180025b40  add     rsp, 130h
0x180025b47  pop     rdi
0x180025b48  pop     rbx
0x180025b49  pop     rbp
0x180025b4a  jmp     ?IgnoreCurrentThread@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
