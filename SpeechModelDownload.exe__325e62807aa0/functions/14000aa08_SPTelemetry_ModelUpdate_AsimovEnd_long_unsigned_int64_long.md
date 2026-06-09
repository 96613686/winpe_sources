# SPTelemetry::ModelUpdate::AsimovEnd<long &>(unsigned __int64,long &)

- ea: `0x14000aa08`
- end: `0x14000aae4`
- name: `??$AsimovEnd@AEAJ@ModelUpdate@SPTelemetry@@QEAAX_KAEAJ@Z`
- size: `220`
- prototype: `__int64 __fastcall(__int64, __int64, int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14000e340`

## callees

- `0x14000176c`
- `0x140002600`
- `0x1400077b0`
- `0x14000aa08`

## pseudocode

```c
__int64 __fastcall SPTelemetry::ModelUpdate::AsimovEnd<long &>(__int64 a1, __int64 a2, int *a3)
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
      return tlgWriteTransfer_EventWriteTransfer(v7, word_14002A032, a1 + 32, v8, 4, v11);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000aa08  mov     [rsp+arg_8], rbx
0x14000aa0d  mov     [rsp+arg_10], rsi
0x14000aa12  push    rdi
0x14000aa13  sub     rsp, 90h
0x14000aa1a  mov     rax, cs:__security_cookie
0x14000aa21  xor     rax, rsp
0x14000aa24  mov     [rsp+98h+var_18], rax
0x14000aa2c  mov     rdi, r8
0x14000aa2f  mov     rsi, rdx
0x14000aa32  mov     rbx, rcx
0x14000aa35  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x14000aa3a  mov     r9d, 4
0x14000aa40  mov     r10, rax
0x14000aa43  mov     ecx, [rax]
0x14000aa45  cmp     ecx, r9d
0x14000aa48  jbe     short loc_14000AABF
0x14000aa4a  mov     rax, [rax+18h]
0x14000aa4e  mov     rdx, 400000000000h
0x14000aa58  mov     rcx, [r10+10h]
0x14000aa5c  test    rdx, rcx
0x14000aa5f  jz      short loc_14000AABF
0x14000aa61  mov     rcx, rax
0x14000aa64  and     rcx, rdx
0x14000aa67  cmp     rcx, rax
0x14000aa6a  jnz     short loc_14000AABF
0x14000aa6c  mov     eax, [rdi]
0x14000aa6e  lea     r8, [rbx+20h]
0x14000aa72  mov     [rsp+98h+var_68], eax
0x14000aa76  lea     rdx, word_14002A032
0x14000aa7d  lea     rax, [rsp+98h+var_68]
0x14000aa82  mov     [rsp+98h+var_20], r9
0x14000aa87  mov     [rsp+98h+var_28], rax
0x14000aa8c  mov     rcx, r10
0x14000aa8f  lea     rax, [rsp+98h+var_60]
0x14000aa94  mov     [rsp+98h+var_60], rsi
0x14000aa99  mov     [rsp+98h+var_38], rax
0x14000aa9e  lea     rax, [rsp+98h+var_58]
0x14000aaa3  mov     [rsp+98h+var_70], rax
0x14000aaa8  mov     [rsp+98h+var_78], r9d
0x14000aaad  mov     r9, [rbx+30h]
0x14000aab1  mov     [rsp+98h+var_30], 8
0x14000aaba  call    _tlgWriteTransfer_EventWriteTransfer
0x14000aabf  mov     rcx, [rsp+98h+var_18]
0x14000aac7  xor     rcx, rsp; StackCookie
0x14000aaca  call    __security_check_cookie
0x14000aacf  lea     r11, [rsp+98h+var_8]
0x14000aad7  mov     rbx, [r11+18h]
0x14000aadb  mov     rsi, [r11+20h]
0x14000aadf  mov     rsp, r11
0x14000aae2  pop     rdi
0x14000aae3  retn
```
