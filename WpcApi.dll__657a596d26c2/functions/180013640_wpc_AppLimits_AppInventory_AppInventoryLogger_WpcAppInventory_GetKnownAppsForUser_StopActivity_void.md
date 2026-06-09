# wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_GetKnownAppsForUser::StopActivity(void)

- ea: `0x180013640`
- end: `0x1800138ad`
- name: `?StopActivity@WpcAppInventory_GetKnownAppsForUser@AppInventoryLogger@AppInventory@AppLimits@wpc@@MEAAXXZ`
- size: `621`
- prototype: `void __fastcall(wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_GetKnownAppsForUser *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800012bc`
- `0x1800015d0`
- `0x180010794`
- `0x180010810`
- `0x180010d90`
- `0x180013640`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001369a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013838`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001369a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180013838`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001384d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001384d`

## pseudocode

```c
void __fastcall wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_GetKnownAppsForUser::StopActivity(
        wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_GetKnownAppsForUser *this)
{
  __int64 v1; // rdi
  int v3; // eax
  int *v4; // rdi
  RTL_SRWLOCK *v5; // rcx
  const struct _tlgProvider_t *v6; // r9
  const unsigned __int16 *v7; // rcx
  __int64 v8; // r8
  RTL_SRWLOCK *v9; // rcx
  const struct _tlgProvider_t *v10; // rdi
  DWORD CurrentThreadId; // eax
  __int64 v12; // r8
  int v13; // ecx
  __int64 v14; // r9
  int v15; // [rsp+C0h] [rbp-80h] BYREF
  int v16; // [rsp+C4h] [rbp-7Ch] BYREF
  int v17; // [rsp+C8h] [rbp-78h] BYREF
  int v18; // [rsp+CCh] [rbp-74h] BYREF
  const unsigned __int16 *v19; // [rsp+D0h] [rbp-70h] BYREF
  const WCHAR *v20; // [rsp+D8h] [rbp-68h] BYREF
  const unsigned __int16 *v21; // [rsp+E0h] [rbp-60h] BYREF
  const WCHAR *v22; // [rsp+E8h] [rbp-58h] BYREF
  const unsigned __int16 *v23; // [rsp+F0h] [rbp-50h] BYREF
  const unsigned __int16 *v24; // [rsp+F8h] [rbp-48h] BYREF
  const WCHAR *v25; // [rsp+100h] [rbp-40h] BYREF
  const unsigned __int16 *v26; // [rsp+108h] [rbp-38h] BYREF
  const unsigned __int16 *v27; // [rsp+110h] [rbp-30h] BYREF
  __int64 v28; // [rsp+118h] [rbp-28h] BYREF
  __int64 v29[4]; // [rsp+120h] [rbp-20h] BYREF
  PSRWLOCK SRWLock; // [rsp+150h] [rbp+10h] BYREF
  int v31; // [rsp+158h] [rbp+18h] BYREF
  __int64 v32; // [rsp+160h] [rbp+20h] BYREF
  int v33; // [rsp+168h] [rbp+28h] BYREF

  v1 = *((_QWORD *)this + 34);
  v3 = *(_DWORD *)(v1 + 72);
  if ( v3 < 0 && (v4 = (int *)(v1 + 80), v3 == v4[2]) && v4 )
  {
    wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v5 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v5 )
      ReleaseSRWLockExclusive(v5);
    v6 = wpc::Logging::WpcBaseLogger::Provider();
    if ( *(_DWORD *)v6 > 4u )
    {
      v7 = (const unsigned __int16 *)*((_QWORD *)v4 + 6);
      v21 = (const unsigned __int16 *)*((_QWORD *)v4 + 14);
      LODWORD(v32) = v4[26];
      v8 = *((_QWORD *)this + 34);
      v22 = (const WCHAR *)*((_QWORD *)v4 + 12);
      v23 = (const unsigned __int16 *)*((_QWORD *)v4 + 11);
      v33 = v4[20];
      v24 = (const unsigned __int16 *)*((_QWORD *)v4 + 9);
      v15 = v4[8];
      v25 = (const WCHAR *)*((_QWORD *)v4 + 3);
      v16 = *v4;
      v26 = (const unsigned __int16 *)*((_QWORD *)v4 + 16);
      v17 = v4[16];
      v27 = (const unsigned __int16 *)*((_QWORD *)v4 + 7);
      v18 = v4[2];
      v28 = 0x1000000;
      v29[0] = 0x1000000;
      v19 = v7;
      LODWORD(SRWLock) = v4[17];
      v31 = v4[4];
      v20 = (const WCHAR *)*((_QWORD *)v4 + 15);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
        (__int64)v6,
        (__int64)byte_18003C75B,
        v8 + 8,
        (__int64)v6,
        (__int64)v29,
        (__int64)&v28,
        (__int64)&v18,
        &v27,
        (__int64)&v17,
        &v26,
        (__int64)&v16,
        &v25,
        (__int64)&v15,
        &v24,
        (__int64)&v33,
        &v23,
        &v22,
        (__int64)&v32,
        &v21,
        &v20,
        (__int64)&v31,
        (__int64)&SRWLock,
        &v19);
    }
  }
  else
  {
    wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
      (__int64)this,
      &SRWLock);
    v9 = SRWLock;
    **((_DWORD **)this + 34) = 2;
    if ( v9 )
      ReleaseSRWLockExclusive(v9);
    v10 = wpc::Logging::WpcBaseLogger::Provider();
    if ( *(_DWORD *)v10 > 4u )
    {
      CurrentThreadId = GetCurrentThreadId();
      v12 = *((_QWORD *)this + 34);
      LODWORD(SRWLock) = CurrentThreadId;
      v13 = *(_DWORD *)(v12 + 72);
      v32 = 0x1000000;
      v31 = v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (__int64)v10,
        (__int64)&unk_18003CB68,
        v12 + 8,
        v14,
        (__int64)&v32,
        (__int64)&v31,
        (__int64)&SRWLock);
    }
  }
  wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread((__int64)this);
}

```

## disassembly

```asm
0x180013640  push    rbp
0x180013642  push    rbx
0x180013643  push    rdi
0x180013644  lea     rbp, [rsp+10h]
0x180013649  sub     rsp, 130h
0x180013650  mov     rdi, [rcx+110h]
0x180013657  mov     rbx, rcx
0x18001365a  mov     eax, [rdi+48h]
0x18001365d  test    eax, eax
0x18001365f  jns     loc_180013819
0x180013665  add     rdi, 50h ; 'P'
0x180013669  cmp     eax, [rdi+8]
0x18001366c  jnz     loc_180013819
0x180013672  test    rdi, rdi
0x180013675  jz      loc_180013819
0x18001367b  lea     rdx, [rbp+SRWLock]
0x18001367f  call    ?LockExclusive@?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180013684  mov     rax, [rbx+110h]
0x18001368b  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001368f  mov     dword ptr [rax], 2
0x180013695  test    rcx, rcx
0x180013698  jz      short loc_1800136A0
0x18001369a  call    cs:__imp_ReleaseSRWLockExclusive
0x1800136a0  call    ?Provider@WpcBaseLogger@Logging@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Logging::WpcBaseLogger::Provider(void)
0x1800136a5  mov     r9, rax
0x1800136a8  mov     ecx, [rax]
0x1800136aa  cmp     ecx, 4
0x1800136ad  jbe     loc_18001389B
0x1800136b3  mov     rax, [rdi+70h]
0x1800136b7  lea     rdx, byte_18003C75B
0x1800136be  mov     rcx, [rdi+30h]
0x1800136c2  mov     [rbp+var_60], rax
0x1800136c6  mov     eax, [rdi+68h]
0x1800136c9  mov     dword ptr [rbp+arg_10], eax
0x1800136cc  mov     rax, [rdi+60h]
0x1800136d0  mov     r8, [rbx+110h]
0x1800136d7  mov     [rbp+var_58], rax
0x1800136db  add     r8, 8
0x1800136df  mov     rax, [rdi+58h]
0x1800136e3  mov     [rbp+var_50], rax
0x1800136e7  mov     eax, [rdi+50h]
0x1800136ea  mov     [rbp+arg_18], eax
0x1800136ed  mov     rax, [rdi+48h]
0x1800136f1  mov     [rbp+var_48], rax
0x1800136f5  mov     eax, [rdi+20h]
0x1800136f8  mov     [rbp+var_80], eax
0x1800136fb  mov     rax, [rdi+18h]
0x1800136ff  mov     [rbp+var_40], rax
0x180013703  mov     eax, [rdi]
0x180013705  mov     [rbp+var_7C], eax
0x180013708  mov     rax, [rdi+80h]
0x18001370f  mov     [rbp+var_38], rax
0x180013713  mov     eax, [rdi+40h]
0x180013716  mov     [rbp+var_78], eax
0x180013719  mov     rax, [rdi+38h]
0x18001371d  mov     [rbp+var_30], rax
0x180013721  mov     eax, [rdi+8]
0x180013724  mov     [rbp+var_74], eax
0x180013727  mov     eax, 1000000h
0x18001372c  mov     [rbp+var_28], rax
0x180013730  mov     [rbp+var_20], rax
0x180013734  lea     rax, [rbp+var_70]
0x180013738  mov     [rsp+140h+var_90], rax
0x180013740  lea     rax, [rbp+SRWLock]
0x180013744  mov     [rsp+140h+var_98], rax
0x18001374c  lea     rax, [rbp+arg_8]
0x180013750  mov     [rsp+140h+var_A0], rax
0x180013758  lea     rax, [rbp+var_68]
0x18001375c  mov     [rsp+140h+var_A8], rax
0x180013764  lea     rax, [rbp+var_60]
0x180013768  mov     [rsp+140h+var_B0], rax
0x180013770  lea     rax, [rbp+arg_10]
0x180013774  mov     [rsp+140h+var_B8], rax
0x18001377c  lea     rax, [rbp+var_58]
0x180013780  mov     [rsp+140h+var_C0], rax
0x180013788  lea     rax, [rbp+var_50]
0x18001378c  mov     [rsp+140h+var_C8], rax
0x180013791  lea     rax, [rbp+arg_18]
0x180013795  mov     [rsp+140h+var_D0], rax
0x18001379a  lea     rax, [rbp+var_48]
0x18001379e  mov     [rsp+140h+var_D8], rax
0x1800137a3  lea     rax, [rbp+var_80]
0x1800137a7  mov     [rsp+140h+var_E0], rax
0x1800137ac  lea     rax, [rbp+var_40]
0x1800137b0  mov     [rsp+140h+var_E8], rax
0x1800137b5  lea     rax, [rbp+var_7C]
0x1800137b9  mov     [rsp+140h+var_F0], rax
0x1800137be  lea     rax, [rbp+var_38]
0x1800137c2  mov     [rsp+140h+var_F8], rax
0x1800137c7  lea     rax, [rbp+var_78]
0x1800137cb  mov     [rsp+140h+var_100], rax
0x1800137d0  lea     rax, [rbp+var_30]
0x1800137d4  mov     [rsp+140h+var_108], rax
0x1800137d9  lea     rax, [rbp+var_74]
0x1800137dd  mov     [rbp+var_70], rcx
0x1800137e1  mov     ecx, [rdi+44h]
0x1800137e4  mov     [rsp+140h+var_110], rax
0x1800137e9  lea     rax, [rbp+var_28]
0x1800137ed  mov     dword ptr [rbp+SRWLock], ecx
0x1800137f0  mov     ecx, [rdi+10h]
0x1800137f3  mov     [rbp+arg_8], ecx
0x1800137f6  mov     rcx, [rdi+78h]
0x1800137fa  mov     [rsp+140h+var_118], rax
0x1800137ff  lea     rax, [rbp+var_20]
0x180013803  mov     [rbp+var_68], rcx
0x180013807  mov     rcx, r9
0x18001380a  mov     [rsp+140h+var_120], rax
0x18001380f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180013814  jmp     loc_18001389B
0x180013819  lea     rdx, [rbp+SRWLock]
0x18001381d  call    ?LockExclusive@?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180013822  mov     rax, [rbx+110h]
0x180013829  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001382d  mov     dword ptr [rax], 2
0x180013833  test    rcx, rcx
0x180013836  jz      short loc_18001383E
0x180013838  call    cs:__imp_ReleaseSRWLockExclusive
0x18001383e  call    ?Provider@WpcBaseLogger@Logging@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Logging::WpcBaseLogger::Provider(void)
0x180013843  mov     rdi, rax
0x180013846  mov     ecx, [rax]
0x180013848  cmp     ecx, 4
0x18001384b  jbe     short loc_18001389B
0x18001384d  call    cs:__imp_GetCurrentThreadId
0x180013853  mov     r8, [rbx+110h]
0x18001385a  lea     rdx, unk_18003CB68
0x180013861  mov     dword ptr [rbp+SRWLock], eax
0x180013864  mov     eax, 1000000h
0x180013869  mov     ecx, [r8+48h]
0x18001386d  add     r8, 8
0x180013871  mov     [rbp+arg_10], rax
0x180013875  lea     rax, [rbp+SRWLock]
0x180013879  mov     [rsp+140h+var_110], rax
0x18001387e  lea     rax, [rbp+arg_8]
0x180013882  mov     [rsp+140h+var_118], rax
0x180013887  lea     rax, [rbp+arg_10]
0x18001388b  mov     [rbp+arg_8], ecx
0x18001388e  mov     rcx, rdi
0x180013891  mov     [rsp+140h+var_120], rax
0x180013896  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001389b  mov     rcx, rbx
0x18001389e  add     rsp, 130h
0x1800138a5  pop     rdi
0x1800138a6  pop     rbx
0x1800138a7  pop     rbp
0x1800138a8  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
