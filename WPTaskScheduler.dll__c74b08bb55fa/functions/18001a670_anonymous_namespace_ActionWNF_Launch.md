# _anonymous_namespace_::ActionWNF::Launch

- ea: `0x18001a670`
- end: `0x18001a7cf`
- name: `_anonymous_namespace_::ActionWNF::Launch`
- size: `351`
- prototype: `__int64 __fastcall(__int64, _OWORD *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000e970`
- `0x180019a9c`
- `0x18001a670`
- `0x18001b334`
- `0x180020c02`

## import_xrefs

- `UBPM!UbpmTriggerConsumerControl` at `0x18001a717`
- `UBPM!UbpmTriggerConsumerControl` at `0x18001a717`
- `UBPM!UbpmOpenTriggerConsumer` at `0x18001a6f3`
- `UBPM!UbpmOpenTriggerConsumer` at `0x18001a6f3`
- `UBPM!UbpmCloseTriggerConsumer` at `0x18001a730`
- `UBPM!UbpmCloseTriggerConsumer` at `0x18001a730`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::ActionWNF::Launch(__int64 a1, _OWORD *a2)
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
    McTemplateU0jqqq_EventWriteTransfer(
      v4,
      (unsigned int)Publish,
      *(_QWORD *)(a1 + 8) + 16,
      *(_DWORD *)(a1 + 160),
      *(_DWORD *)(a1 + 164),
      *(_DWORD *)(a1 + 168));
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
0x18001a670  mov     [rsp-8+arg_10], rbx
0x18001a675  push    rbp
0x18001a676  push    rsi
0x18001a677  push    rdi
0x18001a678  push    r12
0x18001a67a  push    r13
0x18001a67c  push    r14
0x18001a67e  push    r15
0x18001a680  lea     rbp, [rsp-27h]
0x18001a685  sub     rsp, 90h
0x18001a68c  mov     rdi, rdx
0x18001a68f  mov     rbx, rcx
0x18001a692  xor     edx, edx; Val
0x18001a694  lea     rcx, [rbp+57h+var_80]; void *
0x18001a698  lea     r8d, [rdx+48h]; Size
0x18001a69c  call    memset_0
0x18001a6a1  test    cs:byte_180030D01, 8
0x18001a6a8  mov     [rbp+57h+arg_8], 0
0x18001a6b0  jz      short loc_18001A6E1
0x18001a6b2  mov     eax, [rbx+0A8h]
0x18001a6b8  lea     rdx, Publish
0x18001a6bf  mov     r8, [rbx+8]
0x18001a6c3  mov     r9d, [rbx+0A0h]
0x18001a6ca  add     r8, 10h
0x18001a6ce  mov     [rsp+0C0h+var_98], eax
0x18001a6d2  mov     eax, [rbx+0A4h]
0x18001a6d8  mov     [rsp+0C0h+var_A0], eax
0x18001a6dc  call    McTemplateU0jqqq_EventWriteTransfer
0x18001a6e1  lea     rcx, [rbx+58h]
0x18001a6e5  mov     [rbp+57h+arg_0], 0
0x18001a6ed  lea     r8, [rbp+57h+arg_0]
0x18001a6f1  xor     edx, edx
0x18001a6f3  call    cs:__imp_UbpmOpenTriggerConsumer
0x18001a6f9  mov     rcx, [rbp+57h+arg_0]
0x18001a6fd  lea     r8, [rbp+57h+arg_8]
0x18001a701  or      [rbp+57h+var_7C], 1
0x18001a705  lea     rdx, [rbp+57h+var_80]
0x18001a709  mov     [rbp+57h+var_80], 1
0x18001a710  mov     [rbp+57h+var_78], 0FFFFFFFFh
0x18001a717  call    cs:__imp_UbpmTriggerConsumerControl
0x18001a71d  test    eax, eax
0x18001a71f  jle     short loc_18001A729
0x18001a721  movzx   eax, ax
0x18001a724  or      eax, 80070000h
0x18001a729  mov     rcx, [rbp+57h+arg_0]
0x18001a72d  mov     [rbx+40h], eax
0x18001a730  call    cs:__imp_UbpmCloseTriggerConsumer
0x18001a736  movups  xmm0, xmmword ptr [rdi]
0x18001a739  movups  xmmword ptr [rbx+10h], xmm0
0x18001a73d  movups  xmm1, xmmword ptr [rdi+10h]
0x18001a741  movups  xmmword ptr [rbx+20h], xmm1
0x18001a745  movups  xmm0, xmmword ptr [rdi+20h]
0x18001a749  movups  xmmword ptr [rbx+30h], xmm0
0x18001a74d  mov     al, cs:byte_180030D01
0x18001a753  movzx   edi, word ptr [rbx+10h]
0x18001a757  movzx   esi, word ptr [rbx+12h]
0x18001a75b  movzx   r14d, word ptr [rbx+16h]
0x18001a760  movzx   r15d, word ptr [rbx+18h]
0x18001a765  movzx   r12d, word ptr [rbx+1Ah]
0x18001a76a  movzx   r13d, word ptr [rbx+1Ch]
0x18001a76f  test    al, 8
0x18001a771  jz      short loc_18001A7B1
0x18001a773  mov     r8d, [rbx+40h]
0x18001a777  lea     rdx, ActionResults
0x18001a77e  call    McTemplateU0q_EventWriteTransfer
0x18001a783  mov     al, cs:byte_180030D01
0x18001a789  test    al, 8
0x18001a78b  jz      short loc_18001A7B1
0x18001a78d  mov     [rsp+0C0h+var_88], r13w
0x18001a793  movzx   r9d, r14w
0x18001a797  mov     [rsp+0C0h+var_90], r12w
0x18001a79d  movzx   r8d, si
0x18001a7a1  mov     word ptr [rsp+0C0h+var_98], r15w
0x18001a7a7  mov     word ptr [rsp+0C0h+var_A0], di
0x18001a7ac  call    McTemplateU0hhhhhh_EventWriteTransfer
0x18001a7b1  mov     eax, [rbx+40h]
0x18001a7b4  mov     rbx, [rsp+0C0h+arg_10]
0x18001a7bc  add     rsp, 90h
0x18001a7c3  pop     r15
0x18001a7c5  pop     r14
0x18001a7c7  pop     r13
0x18001a7c9  pop     r12
0x18001a7cb  pop     rdi
0x18001a7cc  pop     rsi
0x18001a7cd  pop     rbp
0x18001a7ce  retn
```
