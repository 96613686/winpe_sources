# SPTelemetry::ModelUpdate::AsimovEndLocal<long &>(unsigned __int64,long &)

- ea: `0x14000aaec`
- end: `0x14000abbb`
- name: `??$AsimovEndLocal@AEAJ@ModelUpdate@SPTelemetry@@QEAAX_KAEAJ@Z`
- size: `207`
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
- `0x14000aaec`

## pseudocode

```c
__int64 __fastcall SPTelemetry::ModelUpdate::AsimovEndLocal<long &>(__int64 a1, __int64 a2, int *a3)
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
    if ( (*(_QWORD *)(v7 + 16) & 1) != 0 && (result & 1) == result )
    {
      v8 = *(_QWORD *)(a1 + 48);
      v9 = *a3;
      v14 = &v9;
      v12 = &v10;
      v15 = 4;
      v10 = a2;
      v13 = 8;
      return tlgWriteTransfer_EventWriteTransfer(v7, &dword_14002A004, a1 + 32, v8, 4, v11);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000aaec  mov     [rsp+arg_8], rbx
0x14000aaf1  mov     [rsp+arg_10], rsi
0x14000aaf6  push    rdi
0x14000aaf7  sub     rsp, 90h
0x14000aafe  mov     rax, cs:__security_cookie
0x14000ab05  xor     rax, rsp
0x14000ab08  mov     [rsp+98h+var_18], rax
0x14000ab10  mov     rdi, r8
0x14000ab13  mov     rsi, rdx
0x14000ab16  mov     rbx, rcx
0x14000ab19  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x14000ab1e  mov     edx, 4
0x14000ab23  mov     r10, rax
0x14000ab26  mov     ecx, [rax]
0x14000ab28  cmp     ecx, edx
0x14000ab2a  jbe     short loc_14000AB96
0x14000ab2c  mov     rax, [rax+18h]
0x14000ab30  mov     rcx, [r10+10h]
0x14000ab34  test    cl, 1
0x14000ab37  jz      short loc_14000AB96
0x14000ab39  mov     rcx, rax
0x14000ab3c  and     ecx, 1
0x14000ab3f  cmp     rcx, rax
0x14000ab42  jnz     short loc_14000AB96
0x14000ab44  mov     eax, [rdi]
0x14000ab46  lea     r8, [rbx+20h]
0x14000ab4a  mov     r9, [rbx+30h]
0x14000ab4e  mov     rcx, r10
0x14000ab51  mov     [rsp+98h+var_68], eax
0x14000ab55  lea     rax, [rsp+98h+var_68]
0x14000ab5a  mov     [rsp+98h+var_28], rax
0x14000ab5f  lea     rax, [rsp+98h+var_60]
0x14000ab64  mov     [rsp+98h+var_38], rax
0x14000ab69  lea     rax, [rsp+98h+var_58]
0x14000ab6e  mov     [rsp+98h+var_70], rax
0x14000ab73  mov     [rsp+98h+var_78], edx
0x14000ab77  mov     [rsp+98h+var_20], rdx
0x14000ab7c  lea     rdx, dword_14002A004
0x14000ab83  mov     [rsp+98h+var_60], rsi
0x14000ab88  mov     [rsp+98h+var_30], 8
0x14000ab91  call    _tlgWriteTransfer_EventWriteTransfer
0x14000ab96  mov     rcx, [rsp+98h+var_18]
0x14000ab9e  xor     rcx, rsp; StackCookie
0x14000aba1  call    __security_check_cookie
0x14000aba6  lea     r11, [rsp+98h+var_8]
0x14000abae  mov     rbx, [r11+18h]
0x14000abb2  mov     rsi, [r11+20h]
0x14000abb6  mov     rsp, r11
0x14000abb9  pop     rdi
0x14000abba  retn
```
