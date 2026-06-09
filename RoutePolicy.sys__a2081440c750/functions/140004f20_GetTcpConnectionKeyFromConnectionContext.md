# GetTcpConnectionKeyFromConnectionContext

- ea: `0x140004f20`
- end: `0x14000502d`
- name: `GetTcpConnectionKeyFromConnectionContext`
- size: `269`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000607c`
- `0x14000664c`

## callees

- `0x1400012f0`
- `0x140004f20`
- `0x14000a680`

## pseudocode

```c
NTSTATUS __fastcall GetTcpConnectionKeyFromConnectionContext(__int64 a1, __int64 a2)
{
  int v3; // edx
  NTSTATUS result; // eax
  int v5; // [rsp+30h] [rbp-48h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v6; // [rsp+38h] [rbp-40h] BYREF
  int *v7; // [rsp+58h] [rbp-20h]
  __int64 v8; // [rsp+60h] [rbp-18h]

  v3 = *(unsigned __int16 *)(a1 + 92);
  if ( (_WORD)v3 == 2 )
  {
    *(_OWORD *)a2 = *(_OWORD *)(a1 + 64);
    *(_OWORD *)(a2 + 28) = *(_OWORD *)(a1 + 92);
    goto LABEL_5;
  }
  if ( v3 == 23 )
  {
    *(_OWORD *)a2 = *(_OWORD *)(a1 + 64);
    *(_OWORD *)(a2 + 12) = *(_OWORD *)(a1 + 76);
    *(_OWORD *)(a2 + 28) = *(_OWORD *)(a1 + 92);
    *(_OWORD *)(a2 + 40) = *(_OWORD *)(a1 + 104);
LABEL_5:
    result = dword_140012050;
    if ( (unsigned int)dword_140012050 > 5 )
      return tlgWriteTransfer_EtwWriteTransfer(
               (__int64)&dword_140012050,
               (unsigned __int8 *)&word_140010422,
               0,
               0,
               2u,
               &v6);
    return result;
  }
  if ( (unsigned int)dword_140012050 > 2 )
  {
    v5 = *(unsigned __int16 *)(a1 + 92);
    v7 = &v5;
    v8 = 4;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140012050, (unsigned __int8 *)&byte_14000F429, 0, 0, 3u, &v6);
  }
  result = 0;
  *(_OWORD *)a2 = 0;
  *(_OWORD *)(a2 + 16) = 0;
  *(_OWORD *)(a2 + 32) = 0;
  *(_QWORD *)(a2 + 48) = 0;
  return result;
}

```

## disassembly

```asm
0x140004f20  push    rbx
0x140004f22  sub     rsp, 70h
0x140004f26  mov     rax, cs:__security_cookie
0x140004f2d  xor     rax, rsp
0x140004f30  mov     [rsp+78h+var_10], rax
0x140004f35  mov     rbx, rdx
0x140004f38  mov     r8d, 2
0x140004f3e  movzx   edx, word ptr [rcx+5Ch]
0x140004f42  cmp     dx, r8w
0x140004f46  jnz     short loc_140004F5B
0x140004f48  movups  xmm0, xmmword ptr [rcx+40h]
0x140004f4c  movdqu  xmmword ptr [rbx], xmm0
0x140004f50  movups  xmm1, xmmword ptr [rcx+5Ch]
0x140004f54  movdqu  xmmword ptr [rbx+1Ch], xmm1
0x140004f59  jmp     short loc_140004F7F
0x140004f5b  cmp     edx, 17h
0x140004f5e  jnz     short loc_140004FB8
0x140004f60  movups  xmm0, xmmword ptr [rcx+40h]
0x140004f64  movups  xmmword ptr [rbx], xmm0
0x140004f67  movups  xmm1, xmmword ptr [rcx+4Ch]
0x140004f6b  movups  xmmword ptr [rbx+0Ch], xmm1
0x140004f6f  movups  xmm0, xmmword ptr [rcx+5Ch]
0x140004f73  movups  xmmword ptr [rbx+1Ch], xmm0
0x140004f77  movups  xmm1, xmmword ptr [rcx+68h]
0x140004f7b  movups  xmmword ptr [rbx+28h], xmm1
0x140004f7f  mov     eax, cs:dword_140012050
0x140004f85  cmp     eax, 5
0x140004f88  jbe     loc_140005019
0x140004f8e  lea     rax, [rsp+78h+var_40]
0x140004f93  xor     r9d, r9d; int
0x140004f96  mov     [rsp+78h+var_50], rax; PEVENT_DATA_DESCRIPTOR
0x140004f9b  lea     rdx, word_140010422; int
0x140004fa2  mov     [rsp+78h+var_58], r8d; ULONG
0x140004fa7  lea     rcx, dword_140012050; int
0x140004fae  xor     r8d, r8d; int
0x140004fb1  call    _tlgWriteTransfer_EtwWriteTransfer
0x140004fb6  jmp     short loc_140005019
0x140004fb8  mov     eax, cs:dword_140012050
0x140004fbe  cmp     eax, r8d
0x140004fc1  jbe     short loc_140005005
0x140004fc3  lea     rax, [rsp+78h+var_48]
0x140004fc8  mov     [rsp+78h+var_48], edx
0x140004fcc  mov     [rsp+78h+var_20], rax
0x140004fd1  lea     rdx, byte_14000F429; int
0x140004fd8  lea     rax, [rsp+78h+var_40]
0x140004fdd  mov     [rsp+78h+var_18], 4
0x140004fe6  mov     [rsp+78h+var_50], rax; PEVENT_DATA_DESCRIPTOR
0x140004feb  lea     rcx, dword_140012050; int
0x140004ff2  xor     r9d, r9d; int
0x140004ff5  mov     [rsp+78h+var_58], 3; ULONG
0x140004ffd  xor     r8d, r8d; int
0x140005000  call    _tlgWriteTransfer_EtwWriteTransfer
0x140005005  xorps   xmm0, xmm0
0x140005008  xor     eax, eax
0x14000500a  movups  xmmword ptr [rbx], xmm0
0x14000500d  movups  xmmword ptr [rbx+10h], xmm0
0x140005011  movups  xmmword ptr [rbx+20h], xmm0
0x140005015  mov     [rbx+30h], rax
0x140005019  mov     rcx, [rsp+78h+var_10]
0x14000501e  xor     rcx, rsp; StackCookie
0x140005021  call    __security_check_cookie
0x140005026  add     rsp, 70h
0x14000502a  pop     rbx
0x14000502b  retn
```
