# SPTelemetry::ModelUpdate::AsimovDownloadMetadataLocal<long &>(unsigned __int64,long &)

- ea: `0x14000a930`
- end: `0x14000a9ff`
- name: `??$AsimovDownloadMetadataLocal@AEAJ@ModelUpdate@SPTelemetry@@QEAAX_KAEAJ@Z`
- size: `207`
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
- `0x14000a930`

## pseudocode

```c
__int64 __fastcall SPTelemetry::ModelUpdate::AsimovDownloadMetadataLocal<long &>(__int64 a1, __int64 a2, int *a3)
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
      return tlgWriteTransfer_EventWriteTransfer(v7, &word_140029EAE, a1 + 32, v8, 4, v11);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000a930  mov     [rsp+arg_8], rbx
0x14000a935  mov     [rsp+arg_10], rsi
0x14000a93a  push    rdi
0x14000a93b  sub     rsp, 90h
0x14000a942  mov     rax, cs:__security_cookie
0x14000a949  xor     rax, rsp
0x14000a94c  mov     [rsp+98h+var_18], rax
0x14000a954  mov     rdi, r8
0x14000a957  mov     rsi, rdx
0x14000a95a  mov     rbx, rcx
0x14000a95d  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x14000a962  mov     edx, 4
0x14000a967  mov     r10, rax
0x14000a96a  mov     ecx, [rax]
0x14000a96c  cmp     ecx, edx
0x14000a96e  jbe     short loc_14000A9DA
0x14000a970  mov     rax, [rax+18h]
0x14000a974  mov     rcx, [r10+10h]
0x14000a978  test    cl, 1
0x14000a97b  jz      short loc_14000A9DA
0x14000a97d  mov     rcx, rax
0x14000a980  and     ecx, 1
0x14000a983  cmp     rcx, rax
0x14000a986  jnz     short loc_14000A9DA
0x14000a988  mov     eax, [rdi]
0x14000a98a  lea     r8, [rbx+20h]
0x14000a98e  mov     r9, [rbx+30h]
0x14000a992  mov     rcx, r10
0x14000a995  mov     [rsp+98h+var_68], eax
0x14000a999  lea     rax, [rsp+98h+var_68]
0x14000a99e  mov     [rsp+98h+var_28], rax
0x14000a9a3  lea     rax, [rsp+98h+var_60]
0x14000a9a8  mov     [rsp+98h+var_38], rax
0x14000a9ad  lea     rax, [rsp+98h+var_58]
0x14000a9b2  mov     [rsp+98h+var_70], rax
0x14000a9b7  mov     [rsp+98h+var_78], edx
0x14000a9bb  mov     [rsp+98h+var_20], rdx
0x14000a9c0  lea     rdx, word_140029EAE
0x14000a9c7  mov     [rsp+98h+var_60], rsi
0x14000a9cc  mov     [rsp+98h+var_30], 8
0x14000a9d5  call    _tlgWriteTransfer_EventWriteTransfer
0x14000a9da  mov     rcx, [rsp+98h+var_18]
0x14000a9e2  xor     rcx, rsp; StackCookie
0x14000a9e5  call    __security_check_cookie
0x14000a9ea  lea     r11, [rsp+98h+var_8]
0x14000a9f2  mov     rbx, [r11+18h]
0x14000a9f6  mov     rsi, [r11+20h]
0x14000a9fa  mov     rsp, r11
0x14000a9fd  pop     rdi
0x14000a9fe  retn
```
