# SPTelemetry::ModelUpdate::AsimovParseMetadata_Suppressed(uint,uint)

- ea: `0x14000c2d4`
- end: `0x14000c3a5`
- name: `?AsimovParseMetadata_Suppressed@ModelUpdate@SPTelemetry@@QEAAXII@Z`
- size: `209`
- prototype: `void __fastcall(SPTelemetry::ModelUpdate *this, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14001028c`

## callees

- `0x14000176c`
- `0x140002600`
- `0x1400077b0`
- `0x14000c2d4`

## pseudocode

```c
void __fastcall SPTelemetry::ModelUpdate::AsimovParseMetadata_Suppressed(
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
    tlgWriteTransfer_EventWriteTransfer(v6, &dword_14002A11C, (char *)this + 32, v7, 4, v10);
  }
}

```

## disassembly

```asm
0x14000c2d4  mov     [rsp+arg_8], rbx
0x14000c2d9  mov     [rsp+arg_10], rsi
0x14000c2de  push    rdi
0x14000c2df  sub     rsp, 90h
0x14000c2e6  mov     rax, cs:__security_cookie
0x14000c2ed  xor     rax, rsp
0x14000c2f0  mov     [rsp+98h+var_18], rax
0x14000c2f8  mov     edi, r8d
0x14000c2fb  mov     esi, edx
0x14000c2fd  mov     rbx, rcx
0x14000c300  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x14000c305  mov     r10d, 4
0x14000c30b  mov     ecx, [rax]
0x14000c30d  cmp     ecx, r10d
0x14000c310  jbe     short loc_14000C380
0x14000c312  mov     r9, [rax+18h]
0x14000c316  mov     rdx, 400000000000h
0x14000c320  mov     rcx, [rax+10h]
0x14000c324  test    rdx, rcx
0x14000c327  jz      short loc_14000C380
0x14000c329  mov     rcx, r9
0x14000c32c  and     rcx, rdx
0x14000c32f  cmp     rcx, r9
0x14000c332  jnz     short loc_14000C380
0x14000c334  mov     r9, [rbx+30h]
0x14000c338  lea     rcx, [rsp+98h+var_68]
0x14000c33d  mov     [rsp+98h+var_28], rcx
0x14000c342  lea     r8, [rbx+20h]
0x14000c346  lea     rcx, [rsp+98h+var_64]
0x14000c34b  mov     [rsp+98h+var_68], edi
0x14000c34f  mov     [rsp+98h+var_38], rcx
0x14000c354  lea     rdx, dword_14002A11C
0x14000c35b  lea     rcx, [rsp+98h+var_58]
0x14000c360  mov     [rsp+98h+var_64], esi
0x14000c364  mov     [rsp+98h+var_70], rcx
0x14000c369  mov     rcx, rax
0x14000c36c  mov     [rsp+98h+var_20], r10
0x14000c371  mov     [rsp+98h+var_30], r10
0x14000c376  mov     [rsp+98h+var_78], r10d
0x14000c37b  call    _tlgWriteTransfer_EventWriteTransfer
0x14000c380  mov     rcx, [rsp+98h+var_18]
0x14000c388  xor     rcx, rsp; StackCookie
0x14000c38b  call    __security_check_cookie
0x14000c390  lea     r11, [rsp+98h+var_8]
0x14000c398  mov     rbx, [r11+18h]
0x14000c39c  mov     rsi, [r11+20h]
0x14000c3a0  mov     rsp, r11
0x14000c3a3  pop     rdi
0x14000c3a4  retn
```
