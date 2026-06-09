# _anonymous_namespace_::ActionEvent::Launch

- ea: `0x18000e4e0`
- end: `0x18000e62b`
- name: `_anonymous_namespace_::ActionEvent::Launch`
- size: `331`
- prototype: `__int64 __fastcall(__int64, _OWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000e4e0`
- `0x18000e970`
- `0x18001b334`
- `0x18001b3f4`
- `0x180020c02`

## import_xrefs

- `UBPM!UbpmTriggerConsumerControl` at `0x18000e573`
- `UBPM!UbpmTriggerConsumerControl` at `0x18000e573`
- `UBPM!UbpmOpenTriggerConsumer` at `0x18000e54f`
- `UBPM!UbpmOpenTriggerConsumer` at `0x18000e54f`
- `UBPM!UbpmCloseTriggerConsumer` at `0x18000e58c`
- `UBPM!UbpmCloseTriggerConsumer` at `0x18000e58c`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::ActionEvent::Launch(__int64 a1, _OWORD *a2)
{
  __int64 v4; // rcx
  signed int v5; // eax
  __int64 v6; // rcx
  __int64 v7; // rcx
  __int16 v8; // di
  unsigned __int16 v9; // si
  unsigned __int16 v10; // r14
  __int16 v11; // r15
  __int16 v12; // r12
  __int16 v13; // r13
  int v14; // edx
  int v15; // ecx
  int v17; // [rsp+40h] [rbp-29h] BYREF
  int v18; // [rsp+44h] [rbp-25h]
  int v19; // [rsp+48h] [rbp-21h]
  __int64 v20; // [rsp+D0h] [rbp+67h] BYREF
  __int64 v21; // [rsp+D8h] [rbp+6Fh] BYREF

  memset_0(&v17, 0, 0x48u);
  v21 = 0;
  if ( (byte_180030D01 & 8) != 0 )
    McTemplateU0jz_EventWriteTransfer(v4, Signal, *(_QWORD *)(a1 + 8) + 16LL, *(_QWORD *)(a1 + 168));
  v20 = 0;
  UbpmOpenTriggerConsumer(a1 + 88, 0, &v20);
  v18 |= 1u;
  v17 = 1;
  v19 = -1;
  v5 = UbpmTriggerConsumerControl(v20, &v17, &v21);
  if ( v5 > 0 )
    v5 = (unsigned __int16)v5 | 0x80070000;
  v6 = v20;
  *(_DWORD *)(a1 + 64) = v5;
  UbpmCloseTriggerConsumer(v6);
  *(_OWORD *)(a1 + 16) = *a2;
  *(_OWORD *)(a1 + 32) = a2[1];
  *(_OWORD *)(a1 + 48) = a2[2];
  v8 = *(_WORD *)(a1 + 16);
  v9 = *(_WORD *)(a1 + 18);
  v10 = *(_WORD *)(a1 + 22);
  v11 = *(_WORD *)(a1 + 24);
  v12 = *(_WORD *)(a1 + 26);
  v13 = *(_WORD *)(a1 + 28);
  if ( (byte_180030D01 & 8) != 0 )
  {
    McTemplateU0q_EventWriteTransfer(v7, ActionResults, *(unsigned int *)(a1 + 64));
    if ( (byte_180030D01 & 8) != 0 )
      McTemplateU0hhhhhh_EventWriteTransfer(v15, v14, v9, v10, v8, v11, v12, v13);
  }
  return *(unsigned int *)(a1 + 64);
}

```

## disassembly

```asm
0x18000e4e0  mov     [rsp-8+arg_10], rbx
0x18000e4e5  push    rbp
0x18000e4e6  push    rsi
0x18000e4e7  push    rdi
0x18000e4e8  push    r12
0x18000e4ea  push    r13
0x18000e4ec  push    r14
0x18000e4ee  push    r15
0x18000e4f0  lea     rbp, [rsp-27h]
0x18000e4f5  sub     rsp, 90h
0x18000e4fc  mov     rdi, rdx
0x18000e4ff  mov     rbx, rcx
0x18000e502  xor     edx, edx; Val
0x18000e504  lea     rcx, [rbp+57h+var_80]; void *
0x18000e508  lea     r8d, [rdx+48h]; Size
0x18000e50c  call    memset_0
0x18000e511  test    cs:byte_180030D01, 8
0x18000e518  mov     [rbp+57h+arg_8], 0
0x18000e520  jz      short loc_18000E53D
0x18000e522  mov     r8, [rbx+8]
0x18000e526  lea     rdx, Signal
0x18000e52d  mov     r9, [rbx+0A8h]
0x18000e534  add     r8, 10h
0x18000e538  call    McTemplateU0jz_EventWriteTransfer
0x18000e53d  lea     rcx, [rbx+58h]
0x18000e541  mov     [rbp+57h+arg_0], 0
0x18000e549  lea     r8, [rbp+57h+arg_0]
0x18000e54d  xor     edx, edx
0x18000e54f  call    cs:__imp_UbpmOpenTriggerConsumer
0x18000e555  mov     rcx, [rbp+57h+arg_0]
0x18000e559  lea     r8, [rbp+57h+arg_8]
0x18000e55d  or      [rbp+57h+var_7C], 1
0x18000e561  lea     rdx, [rbp+57h+var_80]
0x18000e565  mov     [rbp+57h+var_80], 1
0x18000e56c  mov     [rbp+57h+var_78], 0FFFFFFFFh
0x18000e573  call    cs:__imp_UbpmTriggerConsumerControl
0x18000e579  test    eax, eax
0x18000e57b  jle     short loc_18000E585
0x18000e57d  movzx   eax, ax
0x18000e580  or      eax, 80070000h
0x18000e585  mov     rcx, [rbp+57h+arg_0]
0x18000e589  mov     [rbx+40h], eax
0x18000e58c  call    cs:__imp_UbpmCloseTriggerConsumer
0x18000e592  movups  xmm0, xmmword ptr [rdi]
0x18000e595  movups  xmmword ptr [rbx+10h], xmm0
0x18000e599  movups  xmm1, xmmword ptr [rdi+10h]
0x18000e59d  movups  xmmword ptr [rbx+20h], xmm1
0x18000e5a1  movups  xmm0, xmmword ptr [rdi+20h]
0x18000e5a5  movups  xmmword ptr [rbx+30h], xmm0
0x18000e5a9  mov     al, cs:byte_180030D01
0x18000e5af  movzx   edi, word ptr [rbx+10h]
0x18000e5b3  movzx   esi, word ptr [rbx+12h]
0x18000e5b7  movzx   r14d, word ptr [rbx+16h]
0x18000e5bc  movzx   r15d, word ptr [rbx+18h]
0x18000e5c1  movzx   r12d, word ptr [rbx+1Ah]
0x18000e5c6  movzx   r13d, word ptr [rbx+1Ch]
0x18000e5cb  test    al, 8
0x18000e5cd  jz      short loc_18000E60D
0x18000e5cf  mov     r8d, [rbx+40h]
0x18000e5d3  lea     rdx, ActionResults
0x18000e5da  call    McTemplateU0q_EventWriteTransfer
0x18000e5df  mov     al, cs:byte_180030D01
0x18000e5e5  test    al, 8
0x18000e5e7  jz      short loc_18000E60D
0x18000e5e9  mov     [rsp+0C0h+var_88], r13w
0x18000e5ef  movzx   r9d, r14w
0x18000e5f3  mov     [rsp+0C0h+var_90], r12w
0x18000e5f9  movzx   r8d, si
0x18000e5fd  mov     [rsp+0C0h+var_98], r15w
0x18000e603  mov     [rsp+0C0h+var_A0], di
0x18000e608  call    McTemplateU0hhhhhh_EventWriteTransfer
0x18000e60d  mov     eax, [rbx+40h]
0x18000e610  mov     rbx, [rsp+0C0h+arg_10]
0x18000e618  add     rsp, 90h
0x18000e61f  pop     r15
0x18000e621  pop     r14
0x18000e623  pop     r13
0x18000e625  pop     r12
0x18000e627  pop     rdi
0x18000e628  pop     rsi
0x18000e629  pop     rbp
0x18000e62a  retn
```
