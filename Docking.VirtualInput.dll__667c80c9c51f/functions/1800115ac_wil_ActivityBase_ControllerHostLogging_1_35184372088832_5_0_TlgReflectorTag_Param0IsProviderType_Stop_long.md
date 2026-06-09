# wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)

- ea: `0x1800115ac`
- end: `0x1800117a0`
- name: `?Stop@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z`
- size: `500`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1800117a8`

## callees

- `0x180001a44`
- `0x180001a54`
- `0x180001c6c`
- `0x180002c84`
- `0x180007ccc`
- `0x18000ea48`
- `0x18000ea88`
- `0x18000f140`
- `0x1800102f8`
- `0x18001097c`
- `0x180011214`
- `0x1800115ac`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001169c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001169c`

## pseudocode

```c
__int64 __fastcall wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
        __int64 a1,
        unsigned int a2)
{
  char v3; // [rsp+40h] [rbp-88h]
  int v4; // [rsp+44h] [rbp-84h] BYREF
  unsigned int v5; // [rsp+48h] [rbp-80h]
  unsigned int v6; // [rsp+4Ch] [rbp-7Ch]
  DWORD CurrentThreadId; // [rsp+50h] [rbp-78h] BYREF
  _BYTE v8[4]; // [rsp+54h] [rbp-74h] BYREF
  unsigned int v9; // [rsp+58h] [rbp-70h] BYREF
  _BYTE v10[4]; // [rsp+5Ch] [rbp-6Ch] BYREF
  const struct _tlgProvider_t *v11; // [rsp+60h] [rbp-68h]
  __int64 v12; // [rsp+68h] [rbp-60h]
  _BYTE v13[8]; // [rsp+70h] [rbp-58h] BYREF
  const struct _tlgProvider_t *v14; // [rsp+78h] [rbp-50h]
  __int64 v15; // [rsp+80h] [rbp-48h] BYREF
  _BYTE v16[8]; // [rsp+88h] [rbp-40h] BYREF
  __int64 v17; // [rsp+90h] [rbp-38h]
  _BYTE *v18; // [rsp+98h] [rbp-30h]
  _BYTE *v19; // [rsp+A0h] [rbp-28h]
  _BYTE *v20; // [rsp+A8h] [rbp-20h]
  __int64 v21; // [rsp+B0h] [rbp-18h]

  v4 = 0;
  wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(
    a1,
    v13);
  v12 = *(_QWORD *)(a1 + 272);
  v3 = wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ControllerHostLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(
         v12,
         a2,
         &v4);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(v13);
  if ( v3 )
  {
    wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(a1);
  }
  else
  {
    v17 = a1;
    v11 = ControllerHostLogging::Provider();
    v14 = v11;
    v5 = 0;
    v5 = *(_DWORD *)v11;
    v6 = v5;
    if ( v5 > 5 && (unsigned __int8)tlgKeywordOn(v11, 0x200000000000LL) )
    {
      CurrentThreadId = GetCurrentThreadId();
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v8, &CurrentThreadId);
      v18 = v8;
      v9 = a2;
      _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(v10, &v9);
      v19 = v10;
      v15 = 0x1000000;
      _tlgWrapperByVal<8>::_tlgWrapperByVal<8>(v16, &v15);
      v20 = v16;
      v21 = wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(v17);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        (_DWORD)v11,
        (unsigned int)byte_180020808,
        v21,
        0,
        (__int64)v20,
        (__int64)v19,
        (__int64)v18);
    }
  }
  return wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(a1);
}

```

## disassembly

```asm
0x1800115ac  mov     [rsp+arg_8], edx
0x1800115b0  mov     [rsp+arg_0], rcx
0x1800115b5  sub     rsp, 0C8h
0x1800115bc  mov     [rsp+0C8h+var_88], 0
0x1800115c1  mov     [rsp+0C8h+var_84], 0
0x1800115c9  lea     rdx, [rsp+0C8h+var_58]
0x1800115ce  mov     rcx, [rsp+0C8h+arg_0]
0x1800115d6  call    ?LockExclusive@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::LockExclusive(void)
0x1800115db  mov     rax, [rsp+0C8h+arg_0]
0x1800115e3  mov     rax, [rax+110h]
0x1800115ea  mov     [rsp+0C8h+var_60], rax
0x1800115ef  lea     r8, [rsp+0C8h+var_84]
0x1800115f4  mov     edx, [rsp+0C8h+arg_8]
0x1800115fb  mov     rcx, [rsp+0C8h+var_60]
0x180011600  call    ?SetStopResult@?$ActivityData@VControllerHostLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA_NJPEAJ@Z; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<ControllerHostLogging,_TlgReflectorTag_Param0IsProviderType>::SetStopResult(long,long *)
0x180011605  mov     [rsp+0C8h+var_88], al
0x180011609  lea     rcx, [rsp+0C8h+var_58]
0x18001160e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180011613  nop
0x180011614  movzx   eax, [rsp+0C8h+var_88]
0x180011619  test    eax, eax
0x18001161b  jz      short loc_180011634
0x18001161d  mov     edx, [rsp+0C8h+var_84]
0x180011621  mov     rcx, [rsp+0C8h+arg_0]
0x180011629  call    ?ReportStopActivity@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@AEAAXJ@Z; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::ReportStopActivity(long)
0x18001162e  nop
0x18001162f  jmp     loc_18001178A
0x180011634  mov     rax, [rsp+0C8h+arg_0]
0x18001163c  mov     [rsp+0C8h+var_38], rax
0x180011644  call    ?Provider@ControllerHostLogging@@SAPEBU_tlgProvider_t@@XZ; ControllerHostLogging::Provider(void)
0x180011649  mov     [rsp+0C8h+var_68], rax
0x18001164e  mov     rax, [rsp+0C8h+var_68]
0x180011653  mov     [rsp+0C8h+var_50], rax
0x180011658  mov     [rsp+0C8h+var_80], 0
0x180011660  mov     rax, [rsp+0C8h+var_50]
0x180011665  mov     eax, [rax]
0x180011667  mov     [rsp+0C8h+var_80], eax
0x18001166b  mov     eax, [rsp+0C8h+var_80]
0x18001166f  mov     [rsp+0C8h+var_7C], eax
0x180011673  mov     eax, [rsp+0C8h+var_7C]
0x180011677  cmp     eax, 5
0x18001167a  jbe     loc_180011776
0x180011680  mov     rdx, cs:qword_18002080B
0x180011687  mov     rcx, [rsp+0C8h+var_68]
0x18001168c  call    _tlgKeywordOn
0x180011691  movzx   eax, al
0x180011694  test    eax, eax
0x180011696  jz      loc_180011776
0x18001169c  call    cs:__imp_GetCurrentThreadId
0x1800116a2  mov     [rsp+0C8h+var_78], eax
0x1800116a6  lea     rdx, [rsp+0C8h+var_78]
0x1800116ab  lea     rcx, [rsp+0C8h+var_74]
0x1800116b0  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x1800116b5  nop
0x1800116b6  lea     rax, [rsp+0C8h+var_74]
0x1800116bb  mov     [rsp+0C8h+var_30], rax
0x1800116c3  mov     eax, [rsp+0C8h+arg_8]
0x1800116ca  mov     [rsp+0C8h+var_70], eax
0x1800116ce  lea     rdx, [rsp+0C8h+var_70]
0x1800116d3  lea     rcx, [rsp+0C8h+var_6C]
0x1800116d8  call    ??0?$_tlgWrapperByVal@$03@@QEAA@PEBX@Z; _tlgWrapperByVal<4>::_tlgWrapperByVal<4>(void const *)
0x1800116dd  nop
0x1800116de  lea     rax, [rsp+0C8h+var_6C]
0x1800116e3  mov     [rsp+0C8h+var_28], rax
0x1800116eb  mov     [rsp+0C8h+var_48], 1000000h
0x1800116f7  lea     rdx, [rsp+0C8h+var_48]
0x1800116ff  lea     rcx, [rsp+0C8h+var_40]
0x180011707  call    ??0?$_tlgWrapperByVal@$07@@QEAA@PEBX@Z; _tlgWrapperByVal<8>::_tlgWrapperByVal<8>(void const *)
0x18001170c  nop
0x18001170d  lea     rax, [rsp+0C8h+var_40]
0x180011715  mov     [rsp+0C8h+var_20], rax
0x18001171d  mov     rcx, [rsp+0C8h+var_38]
0x180011725  call    ?Id@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEBAPEBU_GUID@@XZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::Id(void)
0x18001172a  mov     [rsp+0C8h+var_18], rax
0x180011732  mov     rax, [rsp+0C8h+var_30]
0x18001173a  mov     [rsp+0C8h+var_98], rax
0x18001173f  mov     rax, [rsp+0C8h+var_28]
0x180011747  mov     [rsp+0C8h+var_A0], rax
0x18001174c  mov     rax, [rsp+0C8h+var_20]
0x180011754  mov     [rsp+0C8h+var_A8], rax
0x180011759  xor     r9d, r9d
0x18001175c  mov     r8, [rsp+0C8h+var_18]
0x180011764  lea     rdx, byte_180020808
0x18001176b  mov     rcx, [rsp+0C8h+var_68]
0x180011770  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180011775  nop
0x180011776  xor     eax, eax
0x180011778  test    eax, eax
0x18001177a  jnz     loc_180011644
0x180011780  xor     eax, eax
0x180011782  test    eax, eax
0x180011784  jnz     loc_180011634
0x18001178a  mov     rcx, [rsp+0C8h+arg_0]
0x180011792  call    ?IgnoreCurrentThread@?$ActivityBase@VControllerHostLogging@@$00$0CAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXXZ; wil::ActivityBase<ControllerHostLogging,1,35184372088832,5,0,_TlgReflectorTag_Param0IsProviderType>::IgnoreCurrentThread(void)
0x180011797  nop
0x180011798  add     rsp, 0C8h
0x18001179f  retn
```
