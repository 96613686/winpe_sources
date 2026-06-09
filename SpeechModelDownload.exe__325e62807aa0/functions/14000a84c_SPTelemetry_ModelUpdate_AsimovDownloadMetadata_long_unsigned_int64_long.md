# SPTelemetry::ModelUpdate::AsimovDownloadMetadata<long &>(unsigned __int64,long &)

- ea: `0x14000a84c`
- end: `0x14000a928`
- name: `??$AsimovDownloadMetadata@AEAJ@ModelUpdate@SPTelemetry@@QEAAX_KAEAJ@Z`
- size: `220`
- prototype: `__int64 __fastcall(__int64, __int64, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14000d41c`

## callees

- `0x14000176c`
- `0x140002600`
- `0x1400077b0`
- `0x14000a84c`

## pseudocode

```c
__int64 __fastcall SPTelemetry::ModelUpdate::AsimovDownloadMetadata<long &>(__int64 a1, __int64 a2, int *a3)
{
  __int64 result; // rax
  __int64 v7; // r10
  __int64 v8; // r9
  int v9; // [rsp+30h] [rbp-68h] BYREF
  __int64 v10; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v11[32]; // [rsp+40h] [rbp-58h] BYREF
  __int64 *v12; // [rsp+60h] [rbp-38h]
  __int64 v13; // [rsp+68h] [rbp-30h]
  int *v14; // [rsp+70h] [rbp-28h]
  __int64 v15; // [rsp+78h] [rbp-20h]

  result = (__int64)SPTraceLoggingClass::Provider();
  v7 = result;
  if ( *(_DWORD *)result > 4u )
  {
    result = *(_QWORD *)(result + 24);
    if ( (*(_QWORD *)(v7 + 16) & 0x400000000000LL) != 0 && (result & 0x400000000000LL) == result )
    {
      v9 = *a3;
      v15 = 4;
      v14 = &v9;
      v10 = a2;
      v12 = &v10;
      v8 = *(_QWORD *)(a1 + 48);
      v13 = 8;
      return tlgWriteTransfer_EventWriteTransfer(v7, byte_140029EE9, a1 + 32, v8, 4, v11);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000a84c  mov     [rsp+arg_8], rbx
0x14000a851  mov     [rsp+arg_10], rsi
0x14000a856  push    rdi
0x14000a857  sub     rsp, 90h
0x14000a85e  mov     rax, cs:__security_cookie
0x14000a865  xor     rax, rsp
0x14000a868  mov     [rsp+98h+var_18], rax
0x14000a870  mov     rdi, r8
0x14000a873  mov     rsi, rdx
0x14000a876  mov     rbx, rcx
0x14000a879  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x14000a87e  mov     r9d, 4
0x14000a884  mov     r10, rax
0x14000a887  mov     ecx, [rax]
0x14000a889  cmp     ecx, r9d
0x14000a88c  jbe     short loc_14000A903
0x14000a88e  mov     rax, [rax+18h]
0x14000a892  mov     rdx, 400000000000h
0x14000a89c  mov     rcx, [r10+10h]
0x14000a8a0  test    rdx, rcx
0x14000a8a3  jz      short loc_14000A903
0x14000a8a5  mov     rcx, rax
0x14000a8a8  and     rcx, rdx
0x14000a8ab  cmp     rcx, rax
0x14000a8ae  jnz     short loc_14000A903
0x14000a8b0  mov     eax, [rdi]
0x14000a8b2  lea     r8, [rbx+20h]
0x14000a8b6  mov     [rsp+98h+var_68], eax
0x14000a8ba  lea     rdx, byte_140029EE9
0x14000a8c1  lea     rax, [rsp+98h+var_68]
0x14000a8c6  mov     [rsp+98h+var_20], r9
0x14000a8cb  mov     [rsp+98h+var_28], rax
0x14000a8d0  mov     rcx, r10
0x14000a8d3  lea     rax, [rsp+98h+var_60]
0x14000a8d8  mov     [rsp+98h+var_60], rsi
0x14000a8dd  mov     [rsp+98h+var_38], rax
0x14000a8e2  lea     rax, [rsp+98h+var_58]
0x14000a8e7  mov     [rsp+98h+var_70], rax
0x14000a8ec  mov     [rsp+98h+var_78], r9d
0x14000a8f1  mov     r9, [rbx+30h]
0x14000a8f5  mov     [rsp+98h+var_30], 8
0x14000a8fe  call    _tlgWriteTransfer_EventWriteTransfer
0x14000a903  mov     rcx, [rsp+98h+var_18]
0x14000a90b  xor     rcx, rsp; StackCookie
0x14000a90e  call    __security_check_cookie
0x14000a913  lea     r11, [rsp+98h+var_8]
0x14000a91b  mov     rbx, [r11+18h]
0x14000a91f  mov     rsi, [r11+20h]
0x14000a923  mov     rsp, r11
0x14000a926  pop     rdi
0x14000a927  retn
```
