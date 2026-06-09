# CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentRollbackFailure(long,std::set<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>>> const *,std::set<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>>> const *,std::set<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>> const *,std::set<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>> const *)

- ea: `0x180014624`
- end: `0x18001472d`
- name: `?InstrumentRollbackFailure@ManageCITransaction@ManageCIProvider@Telemetry@Management@CodeIntegrity@@QEAAXJPEBV?$set@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@std@@PEBV?$set@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@7@PEBV?$set@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@7@PEBV?$set@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@7@@Z`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18002aee6`

## callees

- `0x1800019bc`
- `0x180001a88`
- `0x180014624`
- `0x180014ce4`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentRollbackFailure(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  const struct _tlgProvider_t *result; // rax
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // [rsp+50h] [rbp-30h] BYREF
  __int64 v19; // [rsp+58h] [rbp-28h] BYREF
  __int64 v20; // [rsp+60h] [rbp-20h] BYREF
  __int64 v21; // [rsp+68h] [rbp-18h] BYREF
  __int64 v22; // [rsp+70h] [rbp-10h] BYREF
  int v23; // [rsp+A0h] [rbp+20h] BYREF

  result = CodeIntegrity::Management::Telemetry::ManageCIProvider::Provider();
  if ( *(_DWORD *)result > 5u )
  {
    result = (const struct _tlgProvider_t *)tlgKeywordOn(result, 0x400000000000LL, v11);
    if ( (_BYTE)result )
    {
      v13 = a6;
      v23 = a2;
      if ( a6 )
        v13 = *(_QWORD *)(a6 + 8);
      v18 = v13;
      v14 = a5;
      if ( a5 )
        v14 = *(_QWORD *)(a5 + 8);
      v19 = v14;
      if ( a4 )
        v15 = *(_QWORD *)(a4 + 8);
      else
        v15 = 0;
      v20 = v15;
      if ( a3 )
        v16 = *(_QWORD *)(a3 + 8);
      else
        v16 = 0;
      v17 = *(_QWORD *)(a1 + 272);
      v21 = v16;
      v22 = 0x2000000;
      return (const struct _tlgProvider_t *)_tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
                                              v12,
                                              (__int64)byte_180031B71,
                                              v17 + 8,
                                              v12,
                                              (__int64)&v22,
                                              (__int64)&v21,
                                              (__int64)&v20,
                                              (__int64)&v19,
                                              (__int64)&v18,
                                              (__int64)&v23);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180014624  mov     [rsp-18h+arg_8], rbx
0x180014629  mov     [rsp-18h+arg_10], rsi
0x18001462e  push    rbp
0x18001462f  push    rdi
0x180014630  push    r14
0x180014632  mov     rbp, rsp
0x180014635  sub     rsp, 80h
0x18001463c  mov     rdi, r9
0x18001463f  mov     rbx, r8
0x180014642  mov     esi, edx
0x180014644  mov     r14, rcx
0x180014647  call    ?Provider@ManageCIProvider@Telemetry@Management@CodeIntegrity@@SAPEBU_tlgProvider_t@@XZ; CodeIntegrity::Management::Telemetry::ManageCIProvider::Provider(void)
0x18001464c  mov     r9, rax
0x18001464f  mov     r10d, [rax]
0x180014652  cmp     r10d, 5
0x180014656  jbe     loc_180014715
0x18001465c  mov     rdx, 400000000000h
0x180014666  mov     rcx, rax
0x180014669  call    _tlgKeywordOn
0x18001466e  test    al, al
0x180014670  jz      loc_180014715
0x180014676  mov     rax, [rbp+arg_28]
0x18001467a  mov     [rbp+arg_0], esi
0x18001467d  test    rax, rax
0x180014680  jz      short loc_180014686
0x180014682  mov     rax, [rax+8]
0x180014686  mov     [rbp+var_30], rax
0x18001468a  mov     rax, [rbp+arg_20]
0x18001468e  test    rax, rax
0x180014691  jz      short loc_180014697
0x180014693  mov     rax, [rax+8]
0x180014697  mov     [rbp+var_28], rax
0x18001469b  test    rdi, rdi
0x18001469e  jz      short loc_1800146A6
0x1800146a0  mov     rax, [rdi+8]
0x1800146a4  jmp     short loc_1800146A8
0x1800146a6  xor     eax, eax
0x1800146a8  mov     [rbp+var_20], rax
0x1800146ac  test    rbx, rbx
0x1800146af  jz      short loc_1800146B7
0x1800146b1  mov     rax, [rbx+8]
0x1800146b5  jmp     short loc_1800146B9
0x1800146b7  xor     eax, eax
0x1800146b9  mov     r8, [r14+110h]
0x1800146c0  lea     rdx, byte_180031B71
0x1800146c7  mov     [rbp+var_18], rax
0x1800146cb  add     r8, 8
0x1800146cf  lea     rax, [rbp+arg_0]
0x1800146d3  mov     [rbp+var_10], 2000000h
0x1800146db  mov     [rsp+80h+var_38], rax
0x1800146e0  mov     rcx, r9
0x1800146e3  lea     rax, [rbp+var_30]
0x1800146e7  mov     [rsp+80h+var_40], rax
0x1800146ec  lea     rax, [rbp+var_28]
0x1800146f0  mov     [rsp+80h+var_48], rax
0x1800146f5  lea     rax, [rbp+var_20]
0x1800146f9  mov     [rsp+80h+var_50], rax
0x1800146fe  lea     rax, [rbp+var_18]
0x180014702  mov     [rsp+80h+var_58], rax
0x180014707  lea     rax, [rbp+var_10]
0x18001470b  mov     [rsp+80h+var_60], rax
0x180014710  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U1@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3333AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180014715  lea     r11, [rsp+80h+var_s0]
0x18001471d  mov     rbx, [r11+28h]
0x180014721  mov     rsi, [r11+30h]
0x180014725  mov     rsp, r11
0x180014728  pop     r14
0x18001472a  pop     rdi
0x18001472b  pop     rbp
0x18001472c  retn
```
