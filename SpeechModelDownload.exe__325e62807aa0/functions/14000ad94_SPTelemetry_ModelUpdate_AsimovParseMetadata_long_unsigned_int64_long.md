# SPTelemetry::ModelUpdate::AsimovParseMetadata<long &>(unsigned __int64,long &)

- ea: `0x14000ad94`
- end: `0x14000ae70`
- name: `??$AsimovParseMetadata@AEAJ@ModelUpdate@SPTelemetry@@QEAAX_KAEAJ@Z`
- size: `220`
- prototype: `__int64 __fastcall(__int64, __int64, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14001028c`

## callees

- `0x14000176c`
- `0x140002600`
- `0x1400077b0`
- `0x14000ad94`

## pseudocode

```c
__int64 __fastcall SPTelemetry::ModelUpdate::AsimovParseMetadata<long &>(__int64 a1, __int64 a2, int *a3)
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
      return tlgWriteTransfer_EventWriteTransfer(v7, &word_140029E76, a1 + 32, v8, 4, v11);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000ad94  mov     [rsp+arg_8], rbx
0x14000ad99  mov     [rsp+arg_10], rsi
0x14000ad9e  push    rdi
0x14000ad9f  sub     rsp, 90h
0x14000ada6  mov     rax, cs:__security_cookie
0x14000adad  xor     rax, rsp
0x14000adb0  mov     [rsp+98h+var_18], rax
0x14000adb8  mov     rdi, r8
0x14000adbb  mov     rsi, rdx
0x14000adbe  mov     rbx, rcx
0x14000adc1  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x14000adc6  mov     r9d, 4
0x14000adcc  mov     r10, rax
0x14000adcf  mov     ecx, [rax]
0x14000add1  cmp     ecx, r9d
0x14000add4  jbe     short loc_14000AE4B
0x14000add6  mov     rax, [rax+18h]
0x14000adda  mov     rdx, 400000000000h
0x14000ade4  mov     rcx, [r10+10h]
0x14000ade8  test    rdx, rcx
0x14000adeb  jz      short loc_14000AE4B
0x14000aded  mov     rcx, rax
0x14000adf0  and     rcx, rdx
0x14000adf3  cmp     rcx, rax
0x14000adf6  jnz     short loc_14000AE4B
0x14000adf8  mov     eax, [rdi]
0x14000adfa  lea     r8, [rbx+20h]
0x14000adfe  mov     [rsp+98h+var_68], eax
0x14000ae02  lea     rdx, word_140029E76
0x14000ae09  lea     rax, [rsp+98h+var_68]
0x14000ae0e  mov     [rsp+98h+var_20], r9
0x14000ae13  mov     [rsp+98h+var_28], rax
0x14000ae18  mov     rcx, r10
0x14000ae1b  lea     rax, [rsp+98h+var_60]
0x14000ae20  mov     [rsp+98h+var_60], rsi
0x14000ae25  mov     [rsp+98h+var_38], rax
0x14000ae2a  lea     rax, [rsp+98h+var_58]
0x14000ae2f  mov     [rsp+98h+var_70], rax
0x14000ae34  mov     [rsp+98h+var_78], r9d
0x14000ae39  mov     r9, [rbx+30h]
0x14000ae3d  mov     [rsp+98h+var_30], 8
0x14000ae46  call    _tlgWriteTransfer_EventWriteTransfer
0x14000ae4b  mov     rcx, [rsp+98h+var_18]
0x14000ae53  xor     rcx, rsp; StackCookie
0x14000ae56  call    __security_check_cookie
0x14000ae5b  lea     r11, [rsp+98h+var_8]
0x14000ae63  mov     rbx, [r11+18h]
0x14000ae67  mov     rsi, [r11+20h]
0x14000ae6b  mov     rsp, r11
0x14000ae6e  pop     rdi
0x14000ae6f  retn
```
