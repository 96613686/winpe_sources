# CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentCommitFailure(long,std::set<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::UpsertTag>>> const *,std::set<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>,std::less<void>,std::allocator<CodeIntegrity::Management::AuthorizationTokenTransaction<CodeIntegrity::Management::detail::DeleteTag>>> const *,std::set<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::UpsertTag>>> const *,std::set<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>,std::less<void>,std::allocator<CodeIntegrity::Management::SiPolicyTransaction<CodeIntegrity::Management::detail::DeleteTag>>> const *)

- ea: `0x180013df0`
- end: `0x180013ef9`
- name: `?InstrumentCommitFailure@ManageCITransaction@ManageCIProvider@Telemetry@Management@CodeIntegrity@@QEAAXJPEBV?$set@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$AuthorizationTokenTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@std@@PEBV?$set@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$AuthorizationTokenTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@7@PEBV?$set@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$SiPolicyTransaction@UUpsertTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@7@PEBV?$set@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@U?$less@X@std@@V?$allocator@V?$SiPolicyTransaction@UDeleteTag@detail@Management@CodeIntegrity@@@Management@CodeIntegrity@@@5@@7@@Z`
- size: `265`
- prototype: `const struct _tlgProvider_t *__fastcall(__int64, int, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002a9ed`

## callees

- `0x1800019bc`
- `0x180001a88`
- `0x180013df0`
- `0x180014ce4`

## pseudocode

```c
const struct _tlgProvider_t *__fastcall CodeIntegrity::Management::Telemetry::ManageCIProvider::ManageCITransaction::InstrumentCommitFailure(
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
                                              (__int64)&unk_180031830,
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
0x180013df0  mov     [rsp-18h+arg_8], rbx
0x180013df5  mov     [rsp-18h+arg_10], rsi
0x180013dfa  push    rbp
0x180013dfb  push    rdi
0x180013dfc  push    r14
0x180013dfe  mov     rbp, rsp
0x180013e01  sub     rsp, 80h
0x180013e08  mov     rdi, r9
0x180013e0b  mov     rbx, r8
0x180013e0e  mov     esi, edx
0x180013e10  mov     r14, rcx
0x180013e13  call    ?Provider@ManageCIProvider@Telemetry@Management@CodeIntegrity@@SAPEBU_tlgProvider_t@@XZ; CodeIntegrity::Management::Telemetry::ManageCIProvider::Provider(void)
0x180013e18  mov     r9, rax
0x180013e1b  mov     r10d, [rax]
0x180013e1e  cmp     r10d, 5
0x180013e22  jbe     loc_180013EE1
0x180013e28  mov     rdx, 400000000000h
0x180013e32  mov     rcx, rax
0x180013e35  call    _tlgKeywordOn
0x180013e3a  test    al, al
0x180013e3c  jz      loc_180013EE1
0x180013e42  mov     rax, [rbp+arg_28]
0x180013e46  mov     [rbp+arg_0], esi
0x180013e49  test    rax, rax
0x180013e4c  jz      short loc_180013E52
0x180013e4e  mov     rax, [rax+8]
0x180013e52  mov     [rbp+var_30], rax
0x180013e56  mov     rax, [rbp+arg_20]
0x180013e5a  test    rax, rax
0x180013e5d  jz      short loc_180013E63
0x180013e5f  mov     rax, [rax+8]
0x180013e63  mov     [rbp+var_28], rax
0x180013e67  test    rdi, rdi
0x180013e6a  jz      short loc_180013E72
0x180013e6c  mov     rax, [rdi+8]
0x180013e70  jmp     short loc_180013E74
0x180013e72  xor     eax, eax
0x180013e74  mov     [rbp+var_20], rax
0x180013e78  test    rbx, rbx
0x180013e7b  jz      short loc_180013E83
0x180013e7d  mov     rax, [rbx+8]
0x180013e81  jmp     short loc_180013E85
0x180013e83  xor     eax, eax
0x180013e85  mov     r8, [r14+110h]
0x180013e8c  lea     rdx, unk_180031830
0x180013e93  mov     [rbp+var_18], rax
0x180013e97  add     r8, 8
0x180013e9b  lea     rax, [rbp+arg_0]
0x180013e9f  mov     [rbp+var_10], 2000000h
0x180013ea7  mov     [rsp+80h+var_38], rax
0x180013eac  mov     rcx, r9
0x180013eaf  lea     rax, [rbp+var_30]
0x180013eb3  mov     [rsp+80h+var_40], rax
0x180013eb8  lea     rax, [rbp+var_28]
0x180013ebc  mov     [rsp+80h+var_48], rax
0x180013ec1  lea     rax, [rbp+var_20]
0x180013ec5  mov     [rsp+80h+var_50], rax
0x180013eca  lea     rax, [rbp+var_18]
0x180013ece  mov     [rsp+80h+var_58], rax
0x180013ed3  lea     rax, [rbp+var_10]
0x180013ed7  mov     [rsp+80h+var_60], rax
0x180013edc  call    ??$Write@U?$_tlgWrapperByVal@$07@@U1@U1@U1@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@3333AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180013ee1  lea     r11, [rsp+80h+var_s0]
0x180013ee9  mov     rbx, [r11+28h]
0x180013eed  mov     rsi, [r11+30h]
0x180013ef1  mov     rsp, r11
0x180013ef4  pop     r14
0x180013ef6  pop     rdi
0x180013ef7  pop     rbp
0x180013ef8  retn
```
