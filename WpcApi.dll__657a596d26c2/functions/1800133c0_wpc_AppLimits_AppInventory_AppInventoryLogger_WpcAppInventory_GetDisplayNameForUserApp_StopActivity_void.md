# wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_GetDisplayNameForUserApp::StopActivity(void)

- ea: `0x1800133c0`
- end: `0x18001362d`
- name: `?StopActivity@WpcAppInventory_GetDisplayNameForUserApp@AppInventoryLogger@AppInventory@AppLimits@wpc@@MEAAXXZ`
- size: `621`
- prototype: `void __fastcall(wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_GetDisplayNameForUserApp *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800012bc`
- `0x1800015d0`
- `0x180010794`
- `0x180010810`
- `0x180010d90`
- `0x1800133c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001341a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800135b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001341a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800135b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800135cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800135cd`

## pseudocode

```c
void __fastcall wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_GetDisplayNameForUserApp::StopActivity(
        wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_GetDisplayNameForUserApp *this)
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
        (__int64)byte_18003C57D,
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
        (__int64)&dword_18003CE74,
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
0x1800133c0  push    rbp
0x1800133c2  push    rbx
0x1800133c3  push    rdi
0x1800133c4  lea     rbp, [rsp+10h]
0x1800133c9  sub     rsp, 130h
0x1800133d0  mov     rdi, [rcx+110h]
0x1800133d7  mov     rbx, rcx
0x1800133da  mov     eax, [rdi+48h]
0x1800133dd  test    eax, eax
0x1800133df  jns     loc_180013599
0x1800133e5  add     rdi, 50h ; 'P'
0x1800133e9  cmp     eax, [rdi+8]
0x1800133ec  jnz     loc_180013599
0x1800133f2  test    rdi, rdi
0x1800133f5  jz      loc_180013599
0x1800133fb  lea     rdx, [rbp+SRWLock]
0x1800133ff  call    ?LockExclusive@?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x180013404  mov     rax, [rbx+110h]
0x18001340b  mov     rcx, [rbp+SRWLock]; SRWLock
0x18001340f  mov     dword ptr [rax], 2
0x180013415  test    rcx, rcx
0x180013418  jz      short loc_180013420
0x18001341a  call    cs:__imp_ReleaseSRWLockExclusive
0x180013420  call    ?Provider@WpcBaseLogger@Logging@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Logging::WpcBaseLogger::Provider(void)
0x180013425  mov     r9, rax
0x180013428  mov     ecx, [rax]
0x18001342a  cmp     ecx, 4
0x18001342d  jbe     loc_18001361B
0x180013433  mov     rax, [rdi+70h]
0x180013437  lea     rdx, byte_18003C57D
0x18001343e  mov     rcx, [rdi+30h]
0x180013442  mov     [rbp+var_60], rax
0x180013446  mov     eax, [rdi+68h]
0x180013449  mov     dword ptr [rbp+arg_10], eax
0x18001344c  mov     rax, [rdi+60h]
0x180013450  mov     r8, [rbx+110h]
0x180013457  mov     [rbp+var_58], rax
0x18001345b  add     r8, 8
0x18001345f  mov     rax, [rdi+58h]
0x180013463  mov     [rbp+var_50], rax
0x180013467  mov     eax, [rdi+50h]
0x18001346a  mov     [rbp+arg_18], eax
0x18001346d  mov     rax, [rdi+48h]
0x180013471  mov     [rbp+var_48], rax
0x180013475  mov     eax, [rdi+20h]
0x180013478  mov     [rbp+var_80], eax
0x18001347b  mov     rax, [rdi+18h]
0x18001347f  mov     [rbp+var_40], rax
0x180013483  mov     eax, [rdi]
0x180013485  mov     [rbp+var_7C], eax
0x180013488  mov     rax, [rdi+80h]
0x18001348f  mov     [rbp+var_38], rax
0x180013493  mov     eax, [rdi+40h]
0x180013496  mov     [rbp+var_78], eax
0x180013499  mov     rax, [rdi+38h]
0x18001349d  mov     [rbp+var_30], rax
0x1800134a1  mov     eax, [rdi+8]
0x1800134a4  mov     [rbp+var_74], eax
0x1800134a7  mov     eax, 1000000h
0x1800134ac  mov     [rbp+var_28], rax
0x1800134b0  mov     [rbp+var_20], rax
0x1800134b4  lea     rax, [rbp+var_70]
0x1800134b8  mov     [rsp+140h+var_90], rax
0x1800134c0  lea     rax, [rbp+SRWLock]
0x1800134c4  mov     [rsp+140h+var_98], rax
0x1800134cc  lea     rax, [rbp+arg_8]
0x1800134d0  mov     [rsp+140h+var_A0], rax
0x1800134d8  lea     rax, [rbp+var_68]
0x1800134dc  mov     [rsp+140h+var_A8], rax
0x1800134e4  lea     rax, [rbp+var_60]
0x1800134e8  mov     [rsp+140h+var_B0], rax
0x1800134f0  lea     rax, [rbp+arg_10]
0x1800134f4  mov     [rsp+140h+var_B8], rax
0x1800134fc  lea     rax, [rbp+var_58]
0x180013500  mov     [rsp+140h+var_C0], rax
0x180013508  lea     rax, [rbp+var_50]
0x18001350c  mov     [rsp+140h+var_C8], rax
0x180013511  lea     rax, [rbp+arg_18]
0x180013515  mov     [rsp+140h+var_D0], rax
0x18001351a  lea     rax, [rbp+var_48]
0x18001351e  mov     [rsp+140h+var_D8], rax
0x180013523  lea     rax, [rbp+var_80]
0x180013527  mov     [rsp+140h+var_E0], rax
0x18001352c  lea     rax, [rbp+var_40]
0x180013530  mov     [rsp+140h+var_E8], rax
0x180013535  lea     rax, [rbp+var_7C]
0x180013539  mov     [rsp+140h+var_F0], rax
0x18001353e  lea     rax, [rbp+var_38]
0x180013542  mov     [rsp+140h+var_F8], rax
0x180013547  lea     rax, [rbp+var_78]
0x18001354b  mov     [rsp+140h+var_100], rax
0x180013550  lea     rax, [rbp+var_30]
0x180013554  mov     [rsp+140h+var_108], rax
0x180013559  lea     rax, [rbp+var_74]
0x18001355d  mov     [rbp+var_70], rcx
0x180013561  mov     ecx, [rdi+44h]
0x180013564  mov     [rsp+140h+var_110], rax
0x180013569  lea     rax, [rbp+var_28]
0x18001356d  mov     dword ptr [rbp+SRWLock], ecx
0x180013570  mov     ecx, [rdi+10h]
0x180013573  mov     [rbp+arg_8], ecx
0x180013576  mov     rcx, [rdi+78h]
0x18001357a  mov     [rsp+140h+var_118], rax
0x18001357f  lea     rax, [rbp+var_20]
0x180013583  mov     [rbp+var_68], rcx
0x180013587  mov     rcx, r9
0x18001358a  mov     [rsp+140h+var_120], rax
0x18001358f  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@U2@U3@U2@U?$_tlgWrapSz@G@@U2@U3@U2@U3@U4@U2@U3@U4@U2@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@454AEBU?$_tlgWrapSz@G@@45456456445@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180013594  jmp     loc_18001361B
0x180013599  lea     rdx, [rbp+SRWLock]
0x18001359d  call    ?LockExclusive@?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800135a2  mov     rax, [rbx+110h]
0x1800135a9  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800135ad  mov     dword ptr [rax], 2
0x1800135b3  test    rcx, rcx
0x1800135b6  jz      short loc_1800135BE
0x1800135b8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800135be  call    ?Provider@WpcBaseLogger@Logging@wpc@@SAPEBU_tlgProvider_t@@XZ; wpc::Logging::WpcBaseLogger::Provider(void)
0x1800135c3  mov     rdi, rax
0x1800135c6  mov     ecx, [rax]
0x1800135c8  cmp     ecx, 4
0x1800135cb  jbe     short loc_18001361B
0x1800135cd  call    cs:__imp_GetCurrentThreadId
0x1800135d3  mov     r8, [rbx+110h]
0x1800135da  lea     rdx, dword_18003CE74
0x1800135e1  mov     dword ptr [rbp+SRWLock], eax
0x1800135e4  mov     eax, 1000000h
0x1800135e9  mov     ecx, [r8+48h]
0x1800135ed  add     r8, 8
0x1800135f1  mov     [rbp+arg_10], rax
0x1800135f5  lea     rax, [rbp+SRWLock]
0x1800135f9  mov     [rsp+140h+var_110], rax
0x1800135fe  lea     rax, [rbp+arg_8]
0x180013602  mov     [rsp+140h+var_118], rax
0x180013607  lea     rax, [rbp+arg_10]
0x18001360b  mov     [rbp+arg_8], ecx
0x18001360e  mov     rcx, rdi
0x180013611  mov     [rsp+140h+var_120], rax
0x180013616  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18001361b  mov     rcx, rbx
0x18001361e  add     rsp, 130h
0x180013625  pop     rdi
0x180013626  pop     rbx
0x180013627  pop     rbp
0x180013628  jmp     ?IgnoreCurrentThread@?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
```
