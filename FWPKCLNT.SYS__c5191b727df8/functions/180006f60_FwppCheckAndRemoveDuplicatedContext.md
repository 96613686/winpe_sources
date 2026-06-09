# FwppCheckAndRemoveDuplicatedContext

- ea: `0x180006f60`
- end: `0x180007076`
- name: `FwppCheckAndRemoveDuplicatedContext`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180004c10`

## callees

- `0x180006a1c`
- `0x180006c10`
- `0x180006ce0`
- `0x180006dd4`
- `0x180006e74`
- `0x180006f60`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x180006fd9`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x180006fd9`

## pseudocode

```c
__int64 __fastcall FwppCheckAndRemoveDuplicatedContext(__int64 a1, _QWORD *a2, __int64 a3)
{
  _QWORD *v3; // rsi
  _QWORD *v4; // rbx
  unsigned int v6; // ebp
  _QWORD *v7; // rdi
  _QWORD *v9; // r15
  _QWORD *v11; // rbx
  struct _KLOCK_QUEUE_HANDLE v12; // [rsp+20h] [rbp-48h] BYREF
  _QWORD *v13; // [rsp+78h] [rbp+10h] BYREF
  _QWORD *v14; // [rsp+88h] [rbp+20h] BYREF

  v3 = a2 + 16;
  v4 = a2;
  v13 = a2 + 16;
  v14 = a2 + 16;
  memset(&v12, 0, sizeof(v12));
  v6 = 0;
  v7 = 0;
  v9 = a2 + 16;
  WfpAcquireSpinLock(&SpinLock, &v12);
  while ( *((_BYTE *)v4 + 184) || v4[2] != a1 )
  {
    v11 = (_QWORD *)*v3;
    v13 = v11;
    v3 = v11;
    if ( v11 == v9 )
      goto LABEL_5;
    v4 = v11 - 16;
  }
  RtlRemoveEntryHashTable(&HashTable, (PRTL_DYNAMIC_HASH_TABLE_ENTRY)v4 + 4, 0);
  WfpObjectDereference(v4 + 9);
  FwppRemoveTaggedContextFromNetBufferList(a3, v4, &v14, &v13);
  v7 = v4;
LABEL_5:
  WfpObjectManagerUnlock(&unk_180048680, &v12);
  if ( v7 )
  {
    FwppInvokeTaggedContextNotifyFn(v7, a3, 0, 5);
    WfpObjectDereference(v7 + 9);
    return 1;
  }
  return v6;
}

```

## disassembly

```asm
0x180006f60  mov     r11, rsp
0x180006f63  mov     [r11+8], rbx
0x180006f67  mov     [r11+18h], rbp
0x180006f6b  push    rsi
0x180006f6c  push    rdi
0x180006f6d  push    r12
0x180006f6f  push    r14
0x180006f71  push    r15
0x180006f73  sub     rsp, 40h
0x180006f77  lea     rsi, [rdx+80h]
0x180006f7e  xorps   xmm0, xmm0
0x180006f81  mov     rbx, rdx
0x180006f84  mov     [r11+10h], rsi
0x180006f88  mov     r12, rcx
0x180006f8b  mov     [r11+20h], rsi
0x180006f8f  xor     eax, eax
0x180006f91  lea     rdx, [r11-48h]; LockHandle
0x180006f95  movups  xmmword ptr [rsp+68h+var_48.LockQueue.Next], xmm0
0x180006f9a  xor     ebp, ebp
0x180006f9c  mov     [r11-38h], rax
0x180006fa0  xor     edi, edi
0x180006fa2  lea     rcx, SpinLock; SpinLock
0x180006fa9  mov     r14, r8
0x180006fac  mov     r15, rsi
0x180006faf  call    WfpAcquireSpinLock
0x180006fb4  cmp     [rbx+0B8h], dil
0x180006fbb  jnz     loc_18000705D
0x180006fc1  cmp     [rbx+10h], r12
0x180006fc5  jnz     loc_18000705D
0x180006fcb  lea     rdx, [rbx+60h]; Entry
0x180006fcf  xor     r8d, r8d; Context
0x180006fd2  lea     rcx, HashTable; HashTable
0x180006fd9  call    cs:__imp_RtlRemoveEntryHashTable
0x180006fe0  nop     dword ptr [rax+rax+00h]
0x180006fe5  lea     rcx, [rbx+48h]
0x180006fe9  call    WfpObjectDereference
0x180006fee  lea     r9, [rsp+68h+arg_8]
0x180006ff3  mov     rdx, rbx
0x180006ff6  lea     r8, [rsp+68h+arg_18]
0x180006ffe  mov     rcx, r14
0x180007001  call    FwppRemoveTaggedContextFromNetBufferList
0x180007006  mov     rdi, rbx
0x180007009  lea     rdx, [rsp+68h+var_48]
0x18000700e  lea     rcx, unk_180048680
0x180007015  call    WfpObjectManagerUnlock
0x18000701a  test    rdi, rdi
0x18000701d  jz      short loc_180007041
0x18000701f  mov     r9d, 5
0x180007025  xor     r8d, r8d
0x180007028  mov     rdx, r14
0x18000702b  mov     rcx, rdi
0x18000702e  call    FwppInvokeTaggedContextNotifyFn
0x180007033  lea     rcx, [rdi+48h]
0x180007037  call    WfpObjectDereference
0x18000703c  mov     ebp, 1
0x180007041  lea     r11, [rsp+68h+var_28]
0x180007046  mov     eax, ebp
0x180007048  mov     rbx, [r11+30h]
0x18000704c  mov     rbp, [r11+40h]
0x180007050  mov     rsp, r11
0x180007053  pop     r15
0x180007055  pop     r14
0x180007057  pop     r12
0x180007059  pop     rdi
0x18000705a  pop     rsi
0x18000705b  retn
0x18000705d  mov     rbx, [rsi]
0x180007060  mov     [rsp+68h+arg_8], rbx
0x180007065  mov     rsi, rbx
0x180007068  cmp     rbx, r15
0x18000706b  jz      short loc_180007009
0x18000706d  add     rbx, 0FFFFFFFFFFFFFF80h
0x180007071  jmp     loc_180006FB4
```
