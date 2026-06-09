# SPTelemetry::ModelUpdate::AsimovBegin_Suppressed(uint,uint)

- ea: `0x14000be9c`
- end: `0x14000bf6d`
- name: `?AsimovBegin_Suppressed@ModelUpdate@SPTelemetry@@QEAAXII@Z`
- size: `209`
- prototype: `void __fastcall(SPTelemetry::ModelUpdate *this, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x14000c3d8`

## callees

- `0x14000176c`
- `0x140002600`
- `0x1400077b0`
- `0x14000be9c`

## pseudocode

```c
void __fastcall SPTelemetry::ModelUpdate::AsimovBegin_Suppressed(SPTelemetry::ModelUpdate *this, int a2, int a3)
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
    tlgWriteTransfer_EventWriteTransfer(v6, &dword_14002A274, (char *)this + 32, v7, 4, v10);
  }
}

```

## disassembly

```asm
0x14000be9c  mov     [rsp+arg_8], rbx
0x14000bea1  mov     [rsp+arg_10], rsi
0x14000bea6  push    rdi
0x14000bea7  sub     rsp, 90h
0x14000beae  mov     rax, cs:__security_cookie
0x14000beb5  xor     rax, rsp
0x14000beb8  mov     [rsp+98h+var_18], rax
0x14000bec0  mov     edi, r8d
0x14000bec3  mov     esi, edx
0x14000bec5  mov     rbx, rcx
0x14000bec8  call    ?Provider@SPTraceLoggingClass@@SAPEBU_tlgProvider_t@@XZ; SPTraceLoggingClass::Provider(void)
0x14000becd  mov     r10d, 4
0x14000bed3  mov     ecx, [rax]
0x14000bed5  cmp     ecx, r10d
0x14000bed8  jbe     short loc_14000BF48
0x14000beda  mov     r9, [rax+18h]
0x14000bede  mov     rdx, 400000000000h
0x14000bee8  mov     rcx, [rax+10h]
0x14000beec  test    rdx, rcx
0x14000beef  jz      short loc_14000BF48
0x14000bef1  mov     rcx, r9
0x14000bef4  and     rcx, rdx
0x14000bef7  cmp     rcx, r9
0x14000befa  jnz     short loc_14000BF48
0x14000befc  mov     r9, [rbx+30h]
0x14000bf00  lea     rcx, [rsp+98h+var_68]
0x14000bf05  mov     [rsp+98h+var_28], rcx
0x14000bf0a  lea     r8, [rbx+20h]
0x14000bf0e  lea     rcx, [rsp+98h+var_64]
0x14000bf13  mov     [rsp+98h+var_68], edi
0x14000bf17  mov     [rsp+98h+var_38], rcx
0x14000bf1c  lea     rdx, dword_14002A274
0x14000bf23  lea     rcx, [rsp+98h+var_58]
0x14000bf28  mov     [rsp+98h+var_64], esi
0x14000bf2c  mov     [rsp+98h+var_70], rcx
0x14000bf31  mov     rcx, rax
0x14000bf34  mov     [rsp+98h+var_20], r10
0x14000bf39  mov     [rsp+98h+var_30], r10
0x14000bf3e  mov     [rsp+98h+var_78], r10d
0x14000bf43  call    _tlgWriteTransfer_EventWriteTransfer
0x14000bf48  mov     rcx, [rsp+98h+var_18]
0x14000bf50  xor     rcx, rsp; StackCookie
0x14000bf53  call    __security_check_cookie
0x14000bf58  lea     r11, [rsp+98h+var_8]
0x14000bf60  mov     rbx, [r11+18h]
0x14000bf64  mov     rsi, [r11+20h]
0x14000bf68  mov     rsp, r11
0x14000bf6b  pop     rdi
0x14000bf6c  retn
```
