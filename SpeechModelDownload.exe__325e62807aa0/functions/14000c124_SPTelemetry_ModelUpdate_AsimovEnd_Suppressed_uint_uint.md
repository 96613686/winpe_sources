# SPTelemetry::ModelUpdate::AsimovEnd_Suppressed(uint,uint)

- ea: `0x14000c124`
- end: `0x14000c1f5`
- name: `?AsimovEnd_Suppressed@ModelUpdate@SPTelemetry@@QEAAXII@Z`
- size: `209`
- prototype: `void __fastcall(SPTelemetry::ModelUpdate *this, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14000e340`

## callees

- `0x14000176c`
- `0x140002600`
- `0x1400077b0`
- `0x14000c124`

## pseudocode

```c
void __fastcall SPTelemetry::ModelUpdate::AsimovEnd_Suppressed(SPTelemetry::ModelUpdate *this, int a2, int a3)
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
    tlgWriteTransfer_EventWriteTransfer(v6, &unk_14002A228, (char *)this + 32, v7, 4, v10);
  }
}

```

## disassembly

```asm
0x14000c124  mov     [rsp+arg_8], rbx
0x14000c129  mov     [rsp+arg_10], rsi
0x14000c12e  push    rdi
0x14000c12f  sub     rsp, 90h
0x14000c136  mov     rax, cs:__security_cookie
0x14000c13d  xor     rax, rsp
0x14000c140  mov     [rsp+98h+var_18], rax
0x14000c148  mov     edi, r8d
0x14000c14b  mov     esi, edx
0x14000c14d  mov     rbx, rcx
0x14000c150  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x14000c155  mov     r10d, 4
0x14000c15b  mov     ecx, [rax]
0x14000c15d  cmp     ecx, r10d
0x14000c160  jbe     short loc_14000C1D0
0x14000c162  mov     r9, [rax+18h]
0x14000c166  mov     rdx, 400000000000h
0x14000c170  mov     rcx, [rax+10h]
0x14000c174  test    rdx, rcx
0x14000c177  jz      short loc_14000C1D0
0x14000c179  mov     rcx, r9
0x14000c17c  and     rcx, rdx
0x14000c17f  cmp     rcx, r9
0x14000c182  jnz     short loc_14000C1D0
0x14000c184  mov     r9, [rbx+30h]
0x14000c188  lea     rcx, [rsp+98h+var_68]
0x14000c18d  mov     [rsp+98h+var_28], rcx
0x14000c192  lea     r8, [rbx+20h]
0x14000c196  lea     rcx, [rsp+98h+var_64]
0x14000c19b  mov     [rsp+98h+var_68], edi
0x14000c19f  mov     [rsp+98h+var_38], rcx
0x14000c1a4  lea     rdx, unk_14002A228
0x14000c1ab  lea     rcx, [rsp+98h+var_58]
0x14000c1b0  mov     [rsp+98h+var_64], esi
0x14000c1b4  mov     [rsp+98h+var_70], rcx
0x14000c1b9  mov     rcx, rax
0x14000c1bc  mov     [rsp+98h+var_20], r10
0x14000c1c1  mov     [rsp+98h+var_30], r10
0x14000c1c6  mov     [rsp+98h+var_78], r10d
0x14000c1cb  call    _tlgWriteTransfer_EventWriteTransfer
0x14000c1d0  mov     rcx, [rsp+98h+var_18]
0x14000c1d8  xor     rcx, rsp; StackCookie
0x14000c1db  call    __security_check_cookie
0x14000c1e0  lea     r11, [rsp+98h+var_8]
0x14000c1e8  mov     rbx, [r11+18h]
0x14000c1ec  mov     rsi, [r11+20h]
0x14000c1f0  mov     rsp, r11
0x14000c1f3  pop     rdi
0x14000c1f4  retn
```
