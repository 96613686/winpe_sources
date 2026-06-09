# HardwareCheck::CommandSearchHardwareRequirementsTelemetry::HardWareCheckResult<HardwareCheck::HardWareCheckResult>(HardwareCheck::HardWareCheckResult &&)

- ea: `0x18000d4f4`
- end: `0x18000d5b2`
- name: `??$HardWareCheckResult@W40HardwareCheck@@@CommandSearchHardwareRequirementsTelemetry@HardwareCheck@@SAX$$QEAW4HardWareCheckResult@1@@Z`
- size: `190`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180017fb8`
- `0x180018008`
- `0x180018cfc`

## callees

- `0x18000170c`
- `0x180001738`
- `0x1800021d0`
- `0x18000d4f4`
- `0x18001ecfc`

## pseudocode

```c
__int64 __fastcall HardwareCheck::CommandSearchHardwareRequirementsTelemetry::HardWareCheckResult<enum HardwareCheck::HardWareCheckResult>(
        int *a1)
{
  unsigned int *v2; // r10
  __int64 result; // rax
  __int64 v4; // r10
  int v5; // [rsp+30h] [rbp-68h] BYREF
  __int64 v6; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v7[32]; // [rsp+40h] [rbp-58h] BYREF
  int *v8; // [rsp+60h] [rbp-38h]
  __int64 v9; // [rsp+68h] [rbp-30h]
  __int64 *v10; // [rsp+70h] [rbp-28h]
  __int64 v11; // [rsp+78h] [rbp-20h]

  v2 = *(unsigned int **)(wil::details::static_lazy<HardwareCheck::CommandSearchHardwareRequirementsTelemetry>::get(
                            a1,
                            _lambda_4905595ceb02703b21f7bc9dd5a7837a_::_lambda_invoker_cdecl_)
                        + 8);
  result = *v2;
  if ( (unsigned int)result > 5 )
  {
    result = tlgKeywordOn(v2, 0x400000000000LL);
    if ( (_BYTE)result )
    {
      v5 = *a1;
      v9 = 4;
      v10 = &v6;
      v8 = &v5;
      v11 = 8;
      return tlgWriteTransfer_EventWriteTransfer(v4, byte_18002875D, 0, 0, 4, v7, v5, 0x1000000);
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000d4f4  push    rbx
0x18000d4f6  sub     rsp, 90h
0x18000d4fd  mov     rax, cs:__security_cookie
0x18000d504  xor     rax, rsp
0x18000d507  mov     [rsp+98h+var_18], rax
0x18000d50f  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_4905595ceb02703b21f7bc9dd5a7837a_@@CA@XZ; _lambda_4905595ceb02703b21f7bc9dd5a7837a_::_lambda_invoker_cdecl_(void)
0x18000d516  mov     rbx, rcx
0x18000d519  call    ?get@?$static_lazy@VCommandSearchHardwareRequirementsTelemetry@HardwareCheck@@@details@wil@@QEAAPEAVCommandSearchHardwareRequirementsTelemetry@HardwareCheck@@P6AXXZ@Z; wil::details::static_lazy<HardwareCheck::CommandSearchHardwareRequirementsTelemetry>::get(void (*)(void))
0x18000d51e  mov     r10, [rax+8]
0x18000d522  mov     eax, [r10]
0x18000d525  cmp     eax, 5
0x18000d528  jbe     short loc_18000D599
0x18000d52a  mov     rdx, 400000000000h
0x18000d534  mov     rcx, r10
0x18000d537  call    _tlgKeywordOn
0x18000d53c  test    al, al
0x18000d53e  jz      short loc_18000D599
0x18000d540  mov     eax, [rbx]
0x18000d542  lea     rdx, byte_18002875D
0x18000d549  mov     [rsp+98h+var_68], eax
0x18000d54d  mov     ecx, 4
0x18000d552  lea     rax, [rsp+98h+var_60]
0x18000d557  mov     [rsp+98h+var_30], rcx
0x18000d55c  mov     [rsp+98h+var_28], rax
0x18000d561  xor     r9d, r9d
0x18000d564  lea     rax, [rsp+98h+var_68]
0x18000d569  mov     [rsp+98h+var_60], 1000000h
0x18000d572  mov     [rsp+98h+var_38], rax
0x18000d577  xor     r8d, r8d
0x18000d57a  lea     rax, [rsp+98h+var_58]
0x18000d57f  mov     [rsp+98h+var_20], 8
0x18000d588  mov     [rsp+98h+var_70], rax
0x18000d58d  mov     [rsp+98h+var_78], ecx
0x18000d591  mov     rcx, r10
0x18000d594  call    _tlgWriteTransfer_EventWriteTransfer
0x18000d599  mov     rcx, [rsp+98h+var_18]
0x18000d5a1  xor     rcx, rsp; StackCookie
0x18000d5a4  call    __security_check_cookie
0x18000d5a9  add     rsp, 90h
0x18000d5b0  pop     rbx
0x18000d5b1  retn
```
