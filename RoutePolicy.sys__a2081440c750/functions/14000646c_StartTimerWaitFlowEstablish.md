# StartTimerWaitFlowEstablish

- ea: `0x14000646c`
- end: `0x140006567`
- name: `StartTimerWaitFlowEstablish`
- size: `251`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400037a4`
- `0x140007280`

## callees

- `0x1400012f0`
- `0x14000646c`
- `0x14000a680`
- `0x14000a6c0`

## pseudocode

```c
int __fastcall StartTimerWaitFlowEstablish(__int64 a1)
{
  int result; // eax
  char v3; // [rsp+30h] [rbp-9h] BYREF
  __int64 v4; // [rsp+38h] [rbp-1h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+40h] [rbp+7h] BYREF
  __int64 *v6; // [rsp+60h] [rbp+27h]
  __int64 v7; // [rsp+68h] [rbp+2Fh]
  char *v8; // [rsp+70h] [rbp+37h]
  __int64 v9; // [rsp+78h] [rbp+3Fh]

  if ( *(_BYTE *)(a1 + 128) )
  {
    result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64))(WdfFunctions_01015 + 2552))(
               WdfDriverGlobals,
               *(_QWORD *)(a1 + 120),
               -250000000);
    *(_BYTE *)(a1 + 129) = 1;
    if ( (unsigned int)dword_140012050 > 4 )
    {
      v3 = result;
      v4 = *(_QWORD *)(a1 + 120);
      v8 = &v3;
      v6 = &v4;
      v9 = 1;
      v7 = 8;
      return tlgWriteTransfer_EtwWriteTransfer(
               (__int64)&dword_140012050,
               (unsigned __int8 *)&unk_14000F1C8,
               0,
               0,
               4u,
               &v5);
    }
  }
  else
  {
    result = dword_140012050;
    if ( (unsigned int)dword_140012050 > 3 )
      return tlgWriteTransfer_EtwWriteTransfer(
               (__int64)&dword_140012050,
               (unsigned __int8 *)&byte_14000F3EB,
               0,
               0,
               2u,
               &v5);
  }
  return result;
}

```

## disassembly

```asm
0x14000646c  mov     [rsp-8+arg_8], rbx
0x140006471  push    rbp
0x140006472  lea     rbp, [rsp-57h]
0x140006477  sub     rsp, 90h
0x14000647e  mov     rax, cs:__security_cookie
0x140006485  xor     rax, rsp
0x140006488  mov     [rbp+57h+var_10], rax
0x14000648c  cmp     byte ptr [rcx+80h], 0
0x140006493  mov     rbx, rcx
0x140006496  jz      short loc_140006514
0x140006498  mov     rax, cs:WdfFunctions_01015
0x14000649f  mov     r8, 0FFFFFFFFF1194D80h
0x1400064a6  mov     rdx, [rcx+78h]
0x1400064aa  mov     rcx, cs:WdfDriverGlobals
0x1400064b1  mov     rax, [rax+9F8h]
0x1400064b8  call    _guard_dispatch_icall
0x1400064bd  mov     byte ptr [rbx+81h], 1
0x1400064c4  mov     ecx, cs:dword_140012050
0x1400064ca  cmp     ecx, 4
0x1400064cd  jbe     short loc_140006549
0x1400064cf  mov     [rbp+57h+var_60], al
0x1400064d2  lea     rdx, unk_14000F1C8
0x1400064d9  mov     rax, [rbx+78h]
0x1400064dd  mov     [rbp+57h+var_58], rax
0x1400064e1  lea     rax, [rbp+57h+var_60]
0x1400064e5  mov     [rbp+57h+var_20], rax
0x1400064e9  lea     rax, [rbp+57h+var_58]
0x1400064ed  mov     [rbp+57h+var_30], rax
0x1400064f1  lea     rax, [rbp+57h+var_50]
0x1400064f5  mov     [rsp+90h+var_68], rax
0x1400064fa  mov     [rsp+90h+var_70], 4
0x140006502  mov     [rbp+57h+var_18], 1
0x14000650a  mov     [rbp+57h+var_28], 8
0x140006512  jmp     short loc_140006537
0x140006514  mov     eax, cs:dword_140012050
0x14000651a  cmp     eax, 3
0x14000651d  jbe     short loc_140006549
0x14000651f  lea     rax, [rbp+57h+var_50]
0x140006523  mov     [rsp+90h+var_68], rax; PEVENT_DATA_DESCRIPTOR
0x140006528  lea     rdx, byte_14000F3EB; int
0x14000652f  mov     [rsp+90h+var_70], 2; ULONG
0x140006537  xor     r9d, r9d; int
0x14000653a  lea     rcx, dword_140012050; int
0x140006541  xor     r8d, r8d; int
0x140006544  call    _tlgWriteTransfer_EtwWriteTransfer
0x140006549  mov     rcx, [rbp+57h+var_10]
0x14000654d  xor     rcx, rsp; StackCookie
0x140006550  call    __security_check_cookie
0x140006555  mov     rbx, [rsp+90h+arg_8]
0x14000655d  add     rsp, 90h
0x140006564  pop     rbp
0x140006565  retn
```
