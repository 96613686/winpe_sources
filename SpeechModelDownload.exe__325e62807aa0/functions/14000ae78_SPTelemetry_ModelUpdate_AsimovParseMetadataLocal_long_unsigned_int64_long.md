# SPTelemetry::ModelUpdate::AsimovParseMetadataLocal<long &>(unsigned __int64,long &)

- ea: `0x14000ae78`
- end: `0x14000af47`
- name: `??$AsimovParseMetadataLocal@AEAJ@ModelUpdate@SPTelemetry@@QEAAX_KAEAJ@Z`
- size: `207`
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
- `0x14000ae78`

## pseudocode

```c
__int64 __fastcall SPTelemetry::ModelUpdate::AsimovParseMetadataLocal<long &>(__int64 a1, __int64 a2, int *a3)
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
      return tlgWriteTransfer_EventWriteTransfer(v7, &word_140029E3E, a1 + 32, v8, 4, v11);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000ae78  mov     [rsp+arg_8], rbx
0x14000ae7d  mov     [rsp+arg_10], rsi
0x14000ae82  push    rdi
0x14000ae83  sub     rsp, 90h
0x14000ae8a  mov     rax, cs:__security_cookie
0x14000ae91  xor     rax, rsp
0x14000ae94  mov     [rsp+98h+var_18], rax
0x14000ae9c  mov     rdi, r8
0x14000ae9f  mov     rsi, rdx
0x14000aea2  mov     rbx, rcx
0x14000aea5  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x14000aeaa  mov     edx, 4
0x14000aeaf  mov     r10, rax
0x14000aeb2  mov     ecx, [rax]
0x14000aeb4  cmp     ecx, edx
0x14000aeb6  jbe     short loc_14000AF22
0x14000aeb8  mov     rax, [rax+18h]
0x14000aebc  mov     rcx, [r10+10h]
0x14000aec0  test    cl, 1
0x14000aec3  jz      short loc_14000AF22
0x14000aec5  mov     rcx, rax
0x14000aec8  and     ecx, 1
0x14000aecb  cmp     rcx, rax
0x14000aece  jnz     short loc_14000AF22
0x14000aed0  mov     eax, [rdi]
0x14000aed2  lea     r8, [rbx+20h]
0x14000aed6  mov     r9, [rbx+30h]
0x14000aeda  mov     rcx, r10
0x14000aedd  mov     [rsp+98h+var_68], eax
0x14000aee1  lea     rax, [rsp+98h+var_68]
0x14000aee6  mov     [rsp+98h+var_28], rax
0x14000aeeb  lea     rax, [rsp+98h+var_60]
0x14000aef0  mov     [rsp+98h+var_38], rax
0x14000aef5  lea     rax, [rsp+98h+var_58]
0x14000aefa  mov     [rsp+98h+var_70], rax
0x14000aeff  mov     [rsp+98h+var_78], edx
0x14000af03  mov     [rsp+98h+var_20], rdx
0x14000af08  lea     rdx, word_140029E3E
0x14000af0f  mov     [rsp+98h+var_60], rsi
0x14000af14  mov     [rsp+98h+var_30], 8
0x14000af1d  call    _tlgWriteTransfer_EventWriteTransfer
0x14000af22  mov     rcx, [rsp+98h+var_18]
0x14000af2a  xor     rcx, rsp; StackCookie
0x14000af2d  call    __security_check_cookie
0x14000af32  lea     r11, [rsp+98h+var_8]
0x14000af3a  mov     rbx, [r11+18h]
0x14000af3e  mov     rsi, [r11+20h]
0x14000af42  mov     rsp, r11
0x14000af45  pop     rdi
0x14000af46  retn
```
