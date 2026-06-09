# MbbUtilSetupCommandMessage(_MBB_REQUEST_CONTEXT *,_MBB_COMMAND *,_MBB_COMMAND_TYPE,uchar *,ulong)

- ea: `0x140020988`
- end: `0x140020a50`
- name: `?MbbUtilSetupCommandMessage@@YAHPEAU_MBB_REQUEST_CONTEXT@@PEAU_MBB_COMMAND@@W4_MBB_COMMAND_TYPE@@PEAEK@Z`
- size: `200`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD)`
- caller_count: `11`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400026f0`
- `0x140002840`
- `0x140002960`
- `0x140002a40`
- `0x140002bb0`
- `0x140002c90`
- `0x140011070`
- `0x140016c90`
- `0x14001e7b8`
- `0x14001fc2c`
- `0x1400208bc`

## callees

- `0x140008c50`
- `0x140020988`

## pseudocode

```c
__int64 __fastcall MbbUtilSetupCommandMessage(__int64 a1, __int64 a2, int a3, __int64 a4, unsigned int a5)
{
  __int64 v5; // rax
  unsigned int v7; // r15d
  unsigned int v11; // r14d
  __int64 result; // rax
  unsigned int v13[18]; // [rsp+50h] [rbp-48h] BYREF
  int v14; // [rsp+A0h] [rbp+8h] BYREF

  v5 = *(_QWORD *)(a1 + 48);
  v7 = a5;
  v14 = 0;
  v11 = *(_DWORD *)(v5 + 312);
  v13[0] = v11;
  if ( (unsigned int)MbbLibFragmentBufferToCommandMessages(a2, a3, a4, a5, (_DWORD *)(a1 + 20), 0, &v14, v13, 0) )
    return 3221225473LL;
  *(_QWORD *)(a1 + 592) = a4;
  result = 0;
  *(_DWORD *)(a1 + 600) = v7;
  *(_OWORD *)(a1 + 604) = *(_OWORD *)a2;
  *(_DWORD *)(a1 + 620) = *(_DWORD *)(a2 + 16);
  *(_DWORD *)(a1 + 588) = v14;
  *(_DWORD *)(a1 + 624) = a3;
  *(_DWORD *)(a1 + 584) = v11;
  return result;
}

```

## disassembly

```asm
0x140020988  mov     r11, rsp
0x14002098b  push    rbx
0x14002098c  push    rbp
0x14002098d  push    rsi
0x14002098e  push    rdi
0x14002098f  push    r14
0x140020991  push    r15
0x140020993  sub     rsp, 68h
0x140020997  mov     rax, [rcx+30h]
0x14002099b  mov     rbx, rcx
0x14002099e  mov     r15d, [rsp+98h+arg_20]
0x1400209a6  mov     rsi, r9
0x1400209a9  mov     qword ptr [r11-58h], 0
0x1400209b1  mov     ebp, r8d
0x1400209b4  mov     rdi, rdx
0x1400209b7  mov     dword ptr [r11+8], 0
0x1400209bf  mov     r14d, [rax+138h]
0x1400209c6  mov     r9d, r15d
0x1400209c9  lea     rax, [rcx+14h]
0x1400209cd  mov     [r11-48h], r14d
0x1400209d1  lea     rcx, [r11-48h]
0x1400209d5  mov     r8, rsi
0x1400209d8  mov     [r11-60h], rcx
0x1400209dc  mov     edx, ebp
0x1400209de  lea     rcx, [r11+8]
0x1400209e2  mov     [r11-68h], rcx
0x1400209e6  mov     rcx, rdi
0x1400209e9  mov     [rsp+98h+var_70], 0
0x1400209f1  mov     [r11-78h], rax
0x1400209f5  call    MbbLibFragmentBufferToCommandMessages
0x1400209fa  test    eax, eax
0x1400209fc  jz      short loc_140020A05
0x1400209fe  mov     eax, 0C0000001h
0x140020a03  jmp     short loc_140020A42
0x140020a05  mov     [rbx+250h], rsi
0x140020a0c  xor     eax, eax
0x140020a0e  mov     [rbx+258h], r15d
0x140020a15  movups  xmm0, xmmword ptr [rdi]
0x140020a18  movups  xmmword ptr [rbx+25Ch], xmm0
0x140020a1f  mov     ecx, [rdi+10h]
0x140020a22  mov     [rbx+26Ch], ecx
0x140020a28  mov     ecx, [rsp+98h+arg_0]
0x140020a2f  mov     [rbx+24Ch], ecx
0x140020a35  mov     [rbx+270h], ebp
0x140020a3b  mov     [rbx+248h], r14d
0x140020a42  add     rsp, 68h
0x140020a46  pop     r15
0x140020a48  pop     r14
0x140020a4a  pop     rdi
0x140020a4b  pop     rsi
0x140020a4c  pop     rbp
0x140020a4d  pop     rbx
0x140020a4e  retn
```
