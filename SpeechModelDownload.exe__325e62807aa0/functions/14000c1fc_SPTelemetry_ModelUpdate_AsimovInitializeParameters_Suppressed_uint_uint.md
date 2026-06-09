# SPTelemetry::ModelUpdate::AsimovInitializeParameters_Suppressed(uint,uint)

- ea: `0x14000c1fc`
- end: `0x14000c2cd`
- name: `?AsimovInitializeParameters_Suppressed@ModelUpdate@SPTelemetry@@QEAAXII@Z`
- size: `209`
- prototype: `void __fastcall(SPTelemetry::ModelUpdate *this, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14000fdf4`

## callees

- `0x14000176c`
- `0x140002600`
- `0x1400077b0`
- `0x14000c1fc`

## pseudocode

```c
void __fastcall SPTelemetry::ModelUpdate::AsimovInitializeParameters_Suppressed(
        SPTelemetry::ModelUpdate *this,
        int a2,
        int a3)
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
    tlgWriteTransfer_EventWriteTransfer(v6, byte_14002A1CB, (char *)this + 32, v7, 4, v10);
  }
}

```

## disassembly

```asm
0x14000c1fc  mov     [rsp+arg_8], rbx
0x14000c201  mov     [rsp+arg_10], rsi
0x14000c206  push    rdi
0x14000c207  sub     rsp, 90h
0x14000c20e  mov     rax, cs:__security_cookie
0x14000c215  xor     rax, rsp
0x14000c218  mov     [rsp+98h+var_18], rax
0x14000c220  mov     edi, r8d
0x14000c223  mov     esi, edx
0x14000c225  mov     rbx, rcx
0x14000c228  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x14000c22d  mov     r10d, 4
0x14000c233  mov     ecx, [rax]
0x14000c235  cmp     ecx, r10d
0x14000c238  jbe     short loc_14000C2A8
0x14000c23a  mov     r9, [rax+18h]
0x14000c23e  mov     rdx, 400000000000h
0x14000c248  mov     rcx, [rax+10h]
0x14000c24c  test    rdx, rcx
0x14000c24f  jz      short loc_14000C2A8
0x14000c251  mov     rcx, r9
0x14000c254  and     rcx, rdx
0x14000c257  cmp     rcx, r9
0x14000c25a  jnz     short loc_14000C2A8
0x14000c25c  mov     r9, [rbx+30h]
0x14000c260  lea     rcx, [rsp+98h+var_68]
0x14000c265  mov     [rsp+98h+var_28], rcx
0x14000c26a  lea     r8, [rbx+20h]
0x14000c26e  lea     rcx, [rsp+98h+var_64]
0x14000c273  mov     [rsp+98h+var_68], edi
0x14000c277  mov     [rsp+98h+var_38], rcx
0x14000c27c  lea     rdx, byte_14002A1CB
0x14000c283  lea     rcx, [rsp+98h+var_58]
0x14000c288  mov     [rsp+98h+var_64], esi
0x14000c28c  mov     [rsp+98h+var_70], rcx
0x14000c291  mov     rcx, rax
0x14000c294  mov     [rsp+98h+var_20], r10
0x14000c299  mov     [rsp+98h+var_30], r10
0x14000c29e  mov     [rsp+98h+var_78], r10d
0x14000c2a3  call    _tlgWriteTransfer_EventWriteTransfer
0x14000c2a8  mov     rcx, [rsp+98h+var_18]
0x14000c2b0  xor     rcx, rsp; StackCookie
0x14000c2b3  call    __security_check_cookie
0x14000c2b8  lea     r11, [rsp+98h+var_8]
0x14000c2c0  mov     rbx, [r11+18h]
0x14000c2c4  mov     rsi, [r11+20h]
0x14000c2c8  mov     rsp, r11
0x14000c2cb  pop     rdi
0x14000c2cc  retn
```
