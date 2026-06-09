# Windows::Internal::AssignedAccess::RegistryDataStoreV1::RunTransacted(std::function<void (Windows::Internal::AssignedAccess::RegistryDataStoreImpl &)>)

- ea: `0x1800579e4`
- end: `0x180057afd`
- name: `?RunTransacted@RegistryDataStoreV1@AssignedAccess@Internal@Windows@@AEAAXV?$function@$$A6AXAEAVRegistryDataStoreImpl@AssignedAccess@Internal@Windows@@@Z@std@@@Z`
- size: `281`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180057670`
- `0x1800576e0`
- `0x1800578c0`
- `0x180057bc0`

## callees

- `0x18000e700`
- `0x180020050`
- `0x18002d9ec`
- `0x18003fc3c`
- `0x180051048`
- `0x1800575cc`
- `0x1800575f8`
- `0x180057748`
- `0x1800579e4`
- `0x180063fbc`
- `0x180096010`

## import_xrefs

- `ktmw32!CommitTransaction` at `0x180057a91`
- `ktmw32!CommitTransaction` at `0x180057a91`

## string_xrefs

- `0x180057a58`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrydatastorev1.cpp`
- `0x180057a9f`: `onecoreuap\base\embedded\sys\lockdown\runtime\worker\registrykeybroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall Windows::Internal::AssignedAccess::RegistryDataStoreV1::RunTransacted(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rdx
  std::_Ref_count_base *v6; // rcx
  int v7; // eax
  const char *v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rcx
  HANDLE *v11; // [rsp+20h] [rbp-40h] BYREF
  std::_Ref_count_base *v12; // [rsp+28h] [rbp-38h]
  _BYTE v13[16]; // [rsp+30h] [rbp-30h] BYREF
  _BYTE v14[16]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v15; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]
  unsigned int v17; // [rsp+80h] [rbp+20h] BYREF
  __int64 v18; // [rsp+88h] [rbp+28h]
  __int64 RegistryDataStoreImplInstance; // [rsp+90h] [rbp+30h] BYREF

  v18 = a2;
  Windows::Internal::AssignedAccess::RegistryDataStoreV1::CreateTransaction(a1, &v11);
  v4 = std::shared_ptr<Windows::Internal::AssignedAccess::EtwEventRecordWrapper const>::shared_ptr<Windows::Internal::AssignedAccess::EtwEventRecordWrapper const>(
         v13,
         &v11);
  std::shared_ptr<Windows::Internal::AssignedAccess::EtwEventRecordWrapper const>::shared_ptr<Windows::Internal::AssignedAccess::EtwEventRecordWrapper const>(
    v14,
    v4);
  v15 = 0;
  v6 = *(std::_Ref_count_base **)(v5 + 8);
  if ( v6 )
    std::_Ref_count_base::_Decref(v6);
  v17 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a1 + 72LL))(a1, &v17);
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x72,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrydatastorev1.cpp",
      (const char *)(unsigned int)v7,
      (int)v11);
  RegistryDataStoreImplInstance = Windows::Internal::AssignedAccess::CreateRegistryDataStoreImplInstance(v17, v14);
  std::_Func_class<void,Windows::Internal::AssignedAccess::RegistryDataStoreImpl &>::operator()(
    a2,
    RegistryDataStoreImplInstance);
  if ( v11 && !CommitTransaction(*v11) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x14,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\worker\\registrykeybroker.cpp",
      v8);
  std::unique_ptr<Windows::Internal::AssignedAccess::StringRegistryValueEntry>::~unique_ptr<Windows::Internal::AssignedAccess::StringRegistryValueEntry>(&RegistryDataStoreImplInstance);
  Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker((Windows::Internal::AssignedAccess::RegistryKeyBroker *)v14);
  if ( v12 )
    std::_Ref_count_base::_Decref(v12);
  v10 = *(_QWORD *)(a2 + 56);
  if ( v10 )
  {
    LOBYTE(v9) = v10 != a2;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 32LL))(v10, v9);
    *(_QWORD *)(a2 + 56) = 0;
  }
}

```

## disassembly

```asm
0x1800579e4  mov     [rsp-18h+arg_8], rdx
0x1800579e9  push    rbp
0x1800579ea  push    rbx
0x1800579eb  push    rdi
0x1800579ec  mov     rbp, rsp
0x1800579ef  sub     rsp, 60h
0x1800579f3  mov     rbx, rdx
0x1800579f6  mov     rdi, rcx
0x1800579f9  lea     rdx, [rbp+var_40]
0x1800579fd  call    ?CreateTransaction@RegistryDataStoreV1@AssignedAccess@Internal@Windows@@AEAA?AV?$shared_ptr@VTransaction@AssignedAccess@Internal@Windows@@@std@@XZ; Windows::Internal::AssignedAccess::RegistryDataStoreV1::CreateTransaction(void)
0x180057a02  nop
0x180057a03  lea     rdx, [rbp+var_40]
0x180057a07  lea     rcx, [rbp+var_30]
0x180057a0b  call    ??0?$shared_ptr@$$CBVEtwEventRecordWrapper@AssignedAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::AssignedAccess::EtwEventRecordWrapper const>::shared_ptr<Windows::Internal::AssignedAccess::EtwEventRecordWrapper const>(std::shared_ptr<Windows::Internal::AssignedAccess::EtwEventRecordWrapper const> const &)
0x180057a10  mov     rdx, rax
0x180057a13  lea     rcx, [rbp+var_20]
0x180057a17  call    ??0?$shared_ptr@$$CBVEtwEventRecordWrapper@AssignedAccess@Internal@Windows@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Windows::Internal::AssignedAccess::EtwEventRecordWrapper const>::shared_ptr<Windows::Internal::AssignedAccess::EtwEventRecordWrapper const>(std::shared_ptr<Windows::Internal::AssignedAccess::EtwEventRecordWrapper const> const &)
0x180057a1c  mov     [rbp+var_10], 0
0x180057a24  mov     rcx, [rdx+8]; this
0x180057a28  test    rcx, rcx
0x180057a2b  jz      short loc_180057A33
0x180057a2d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180057a32  nop
0x180057a33  mov     [rbp+arg_0], 0
0x180057a3a  mov     rax, [rdi]
0x180057a3d  lea     rdx, [rbp+arg_0]
0x180057a41  mov     rcx, rdi
0x180057a44  mov     rax, [rax+48h]
0x180057a48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057a4d  mov     rcx, [rbp+18h]; this
0x180057a51  test    eax, eax
0x180057a53  jns     short loc_180057A6A
0x180057a55  mov     r9d, eax; char *
0x180057a58  lea     r8, aOnecoreuapBase_46; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180057a5f  mov     edx, 72h ; 'r'; void *
0x180057a64  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180057a6a  lea     rdx, [rbp+var_20]
0x180057a6e  mov     ecx, [rbp+arg_0]
0x180057a71  call    ?CreateRegistryDataStoreImplInstance@AssignedAccess@Internal@Windows@@YAPEAVRegistryDataStoreImpl@123@W4StoreVersion@@AEAVRegistryKeyBroker@123@@Z; Windows::Internal::AssignedAccess::CreateRegistryDataStoreImplInstance(StoreVersion,Windows::Internal::AssignedAccess::RegistryKeyBroker &)
0x180057a76  mov     [rbp+arg_10], rax
0x180057a7a  mov     rdx, rax
0x180057a7d  mov     rcx, rbx
0x180057a80  call    ??R?$_Func_class@XAEAVRegistryDataStoreImpl@AssignedAccess@Internal@Windows@@@std@@QEBAXAEAVRegistryDataStoreImpl@AssignedAccess@Internal@Windows@@@Z; std::_Func_class<void,Windows::Internal::AssignedAccess::RegistryDataStoreImpl &>::operator()(Windows::Internal::AssignedAccess::RegistryDataStoreImpl &)
0x180057a85  mov     rcx, [rbp+var_40]
0x180057a89  test    rcx, rcx
0x180057a8c  jz      short loc_180057AAF
0x180057a8e  mov     rcx, [rcx]; TransactionHandle
0x180057a91  call    cs:__imp_CommitTransaction
0x180057a97  mov     rcx, [rbp+18h]; this
0x180057a9b  test    eax, eax
0x180057a9d  jnz     short loc_180057AAF
0x180057a9f  lea     r8, aOnecoreuapBase_80; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180057aa6  lea     edx, [rax+14h]; void *
0x180057aa9  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180057aaf  lea     rcx, [rbp+arg_10]
0x180057ab3  call    ??1?$unique_ptr@VStringRegistryValueEntry@AssignedAccess@Internal@Windows@@U?$default_delete@VStringRegistryValueEntry@AssignedAccess@Internal@Windows@@@std@@@std@@QEAA@XZ; std::unique_ptr<Windows::Internal::AssignedAccess::StringRegistryValueEntry>::~unique_ptr<Windows::Internal::AssignedAccess::StringRegistryValueEntry>(void)
0x180057ab8  nop
0x180057ab9  lea     rcx, [rbp+var_20]; this
0x180057abd  call    ??1RegistryKeyBroker@AssignedAccess@Internal@Windows@@QEAA@XZ; Windows::Internal::AssignedAccess::RegistryKeyBroker::~RegistryKeyBroker(void)
0x180057ac2  nop
0x180057ac3  mov     rcx, [rbp+var_38]; this
0x180057ac7  test    rcx, rcx
0x180057aca  jz      short loc_180057AD2
0x180057acc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180057ad1  nop
0x180057ad2  mov     rcx, [rbx+38h]
0x180057ad6  test    rcx, rcx
0x180057ad9  jz      short loc_180057AF5
0x180057adb  mov     rax, [rcx]
0x180057ade  cmp     rcx, rbx
0x180057ae1  setnz   dl
0x180057ae4  mov     rax, [rax+20h]
0x180057ae8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057aed  mov     qword ptr [rbx+38h], 0
0x180057af5  add     rsp, 60h
0x180057af9  pop     rdi
0x180057afa  pop     rbx
0x180057afb  pop     rbp
0x180057afc  retn
```
