# SPTelemetry::ModelUpdate::AsimovAbort_Suppressed(uint,uint)

- ea: `0x140005668`
- end: `0x140005739`
- name: `?AsimovAbort_Suppressed@ModelUpdate@SPTelemetry@@QEAAXII@Z`
- size: `209`
- prototype: `void __fastcall(SPTelemetry::ModelUpdate *this, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x140004f38`

## callees

- `0x14000176c`
- `0x140002600`
- `0x140005668`
- `0x1400077b0`

## pseudocode

```c
void __fastcall SPTelemetry::ModelUpdate::AsimovAbort_Suppressed(SPTelemetry::ModelUpdate *this, int a2, int a3)
{
  const struct _tlgProvider_t *v6; // rax
  __int64 v7; // r9
  int v8; // [rsp+30h] [rbp-68h] BYREF
  int v9; // [rsp+34h] [rbp-64h] BYREF
  _BYTE v10[32]; // [rsp+40h] [rbp-58h] BYREF
  int *v11; // [rsp+60h] [rbp-38h]
  __int64 v12; // [rsp+68h] [rbp-30h]
  int *v13; // [rsp+70h] [rbp-28h]
  __int64 v14; // [rsp+78h] [rbp-20h]

  v6 = SPTraceLoggingClass::Provider();
  if ( *(_DWORD *)v6 > 4u
    && (*((_QWORD *)v6 + 2) & 0x400000000000LL) != 0
    && (*((_QWORD *)v6 + 3) & 0x400000000000LL) == *((_QWORD *)v6 + 3) )
  {
    v7 = *((_QWORD *)this + 6);
    v13 = &v8;
    v8 = a3;
    v11 = &v9;
    v9 = a2;
    v14 = 4;
    v12 = 4;
    tlgWriteTransfer_EventWriteTransfer(v6, &word_140029A46, (char *)this + 32, v7, 4, v10);
  }
}

```

## disassembly

```asm
0x140005668  mov     [rsp+arg_8], rbx
0x14000566d  mov     [rsp+arg_10], rsi
0x140005672  push    rdi
0x140005673  sub     rsp, 90h
0x14000567a  mov     rax, cs:__security_cookie
0x140005681  xor     rax, rsp
0x140005684  mov     [rsp+98h+var_18], rax
0x14000568c  mov     edi, r8d
0x14000568f  mov     esi, edx
0x140005691  mov     rbx, rcx
0x140005694  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x140005699  mov     r10d, 4
0x14000569f  mov     ecx, [rax]
0x1400056a1  cmp     ecx, r10d
0x1400056a4  jbe     short loc_140005714
0x1400056a6  mov     r9, [rax+18h]
0x1400056aa  mov     rdx, 400000000000h
0x1400056b4  mov     rcx, [rax+10h]
0x1400056b8  test    rdx, rcx
0x1400056bb  jz      short loc_140005714
0x1400056bd  mov     rcx, r9
0x1400056c0  and     rcx, rdx
0x1400056c3  cmp     rcx, r9
0x1400056c6  jnz     short loc_140005714
0x1400056c8  mov     r9, [rbx+30h]
0x1400056cc  lea     rcx, [rsp+98h+var_68]
0x1400056d1  mov     [rsp+98h+var_28], rcx
0x1400056d6  lea     r8, [rbx+20h]
0x1400056da  lea     rcx, [rsp+98h+var_64]
0x1400056df  mov     [rsp+98h+var_68], edi
0x1400056e3  mov     [rsp+98h+var_38], rcx
0x1400056e8  lea     rdx, word_140029A46
0x1400056ef  lea     rcx, [rsp+98h+var_58]
0x1400056f4  mov     [rsp+98h+var_64], esi
0x1400056f8  mov     [rsp+98h+var_70], rcx
0x1400056fd  mov     rcx, rax
0x140005700  mov     [rsp+98h+var_20], r10
0x140005705  mov     [rsp+98h+var_30], r10
0x14000570a  mov     [rsp+98h+var_78], r10d
0x14000570f  call    _tlgWriteTransfer_EventWriteTransfer
0x140005714  mov     rcx, [rsp+98h+var_18]
0x14000571c  xor     rcx, rsp; StackCookie
0x14000571f  call    __security_check_cookie
0x140005724  lea     r11, [rsp+98h+var_8]
0x14000572c  mov     rbx, [r11+18h]
0x140005730  mov     rsi, [r11+20h]
0x140005734  mov     rsp, r11
0x140005737  pop     rdi
0x140005738  retn
```
