# _anonymous_namespace_::ActionLaunch::Launch

- ea: `0x18001a510`
- end: `0x18001a661`
- name: `_anonymous_namespace_::ActionLaunch::Launch`
- size: `337`
- prototype: `__int64 __fastcall(__int64, _OWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task`

## callees

- `0x18000e970`
- `0x18001a510`
- `0x18001b334`
- `0x18001b484`
- `0x180020c02`

## import_xrefs

- `UBPM!UbpmTriggerConsumerControl` at `0x18001a5a9`
- `UBPM!UbpmTriggerConsumerControl` at `0x18001a5a9`
- `UBPM!UbpmOpenTriggerConsumer` at `0x18001a585`
- `UBPM!UbpmOpenTriggerConsumer` at `0x18001a585`
- `UBPM!UbpmCloseTriggerConsumer` at `0x18001a5c2`
- `UBPM!UbpmCloseTriggerConsumer` at `0x18001a5c2`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::ActionLaunch::Launch(__int64 a1, _OWORD *a2)
{
  int v4; // ecx
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
    McTemplateU0jzz_EventWriteTransfer(
      v4,
      (unsigned int)LaunchTask,
      *(_QWORD *)(a1 + 8) + 16,
      *(_QWORD *)(a1 + 112),
      *(_QWORD *)(a1 + 120));
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
0x18001a510  mov     [rsp-8+arg_10], rbx
0x18001a515  push    rbp
0x18001a516  push    rsi
0x18001a517  push    rdi
0x18001a518  push    r12
0x18001a51a  push    r13
0x18001a51c  push    r14
0x18001a51e  push    r15
0x18001a520  lea     rbp, [rsp-27h]
0x18001a525  sub     rsp, 90h
0x18001a52c  mov     rdi, rdx
0x18001a52f  mov     rbx, rcx
0x18001a532  xor     edx, edx; Val
0x18001a534  lea     rcx, [rbp+57h+var_80]; void *
0x18001a538  lea     r8d, [rdx+48h]; Size
0x18001a53c  call    memset_0
0x18001a541  test    cs:byte_180030D01, 8
0x18001a548  mov     [rbp+57h+arg_8], 0
0x18001a550  jz      short loc_18001A573
0x18001a552  mov     r8, [rbx+8]
0x18001a556  lea     rdx, LaunchTask
0x18001a55d  mov     rax, [rbx+78h]
0x18001a561  add     r8, 10h
0x18001a565  mov     r9, [rbx+70h]
0x18001a569  mov     [rsp+0C0h+var_A0], rax
0x18001a56e  call    McTemplateU0jzz_EventWriteTransfer
0x18001a573  lea     rcx, [rbx+58h]
0x18001a577  mov     [rbp+57h+arg_0], 0
0x18001a57f  lea     r8, [rbp+57h+arg_0]
0x18001a583  xor     edx, edx
0x18001a585  call    cs:__imp_UbpmOpenTriggerConsumer
0x18001a58b  mov     rcx, [rbp+57h+arg_0]
0x18001a58f  lea     r8, [rbp+57h+arg_8]
0x18001a593  or      [rbp+57h+var_7C], 1
0x18001a597  lea     rdx, [rbp+57h+var_80]
0x18001a59b  mov     [rbp+57h+var_80], 1
0x18001a5a2  mov     [rbp+57h+var_78], 0FFFFFFFFh
0x18001a5a9  call    cs:__imp_UbpmTriggerConsumerControl
0x18001a5af  test    eax, eax
0x18001a5b1  jle     short loc_18001A5BB
0x18001a5b3  movzx   eax, ax
0x18001a5b6  or      eax, 80070000h
0x18001a5bb  mov     rcx, [rbp+57h+arg_0]
0x18001a5bf  mov     [rbx+40h], eax
0x18001a5c2  call    cs:__imp_UbpmCloseTriggerConsumer
0x18001a5c8  movups  xmm0, xmmword ptr [rdi]
0x18001a5cb  movups  xmmword ptr [rbx+10h], xmm0
0x18001a5cf  movups  xmm1, xmmword ptr [rdi+10h]
0x18001a5d3  movups  xmmword ptr [rbx+20h], xmm1
0x18001a5d7  movups  xmm0, xmmword ptr [rdi+20h]
0x18001a5db  movups  xmmword ptr [rbx+30h], xmm0
0x18001a5df  mov     al, cs:byte_180030D01
0x18001a5e5  movzx   edi, word ptr [rbx+10h]
0x18001a5e9  movzx   esi, word ptr [rbx+12h]
0x18001a5ed  movzx   r14d, word ptr [rbx+16h]
0x18001a5f2  movzx   r15d, word ptr [rbx+18h]
0x18001a5f7  movzx   r12d, word ptr [rbx+1Ah]
0x18001a5fc  movzx   r13d, word ptr [rbx+1Ch]
0x18001a601  test    al, 8
0x18001a603  jz      short loc_18001A643
0x18001a605  mov     r8d, [rbx+40h]
0x18001a609  lea     rdx, ActionResults
0x18001a610  call    McTemplateU0q_EventWriteTransfer
0x18001a615  mov     al, cs:byte_180030D01
0x18001a61b  test    al, 8
0x18001a61d  jz      short loc_18001A643
0x18001a61f  mov     [rsp+0C0h+var_88], r13w
0x18001a625  movzx   r9d, r14w
0x18001a629  mov     [rsp+0C0h+var_90], r12w
0x18001a62f  movzx   r8d, si
0x18001a633  mov     [rsp+0C0h+var_98], r15w
0x18001a639  mov     word ptr [rsp+0C0h+var_A0], di
0x18001a63e  call    McTemplateU0hhhhhh_EventWriteTransfer
0x18001a643  mov     eax, [rbx+40h]
0x18001a646  mov     rbx, [rsp+0C0h+arg_10]
0x18001a64e  add     rsp, 90h
0x18001a655  pop     r15
0x18001a657  pop     r14
0x18001a659  pop     r13
0x18001a65b  pop     r12
0x18001a65d  pop     rdi
0x18001a65e  pop     rsi
0x18001a65f  pop     rbp
0x18001a660  retn
```
