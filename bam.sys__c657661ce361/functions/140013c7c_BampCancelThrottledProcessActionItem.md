# BampCancelThrottledProcessActionItem

- ea: `0x140013c7c`
- end: `0x140013d2d`
- name: `BampCancelThrottledProcessActionItem`
- size: `177`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1400100b0`
- `0x140010308`

## callees

- `0x140001430`
- `0x1400026d0`
- `0x1400107f0`
- `0x140011520`
- `0x140013c7c`

## pseudocode

```c
void __fastcall BampCancelThrottledProcessActionItem(volatile signed __int64 *P)
{
  int v2; // ecx
  int v3; // [rsp+30h] [rbp-68h] BYREF
  int v4; // [rsp+34h] [rbp-64h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v5; // [rsp+40h] [rbp-58h] BYREF
  int *v6; // [rsp+60h] [rbp-38h]
  __int64 v7; // [rsp+68h] [rbp-30h]
  int *v8; // [rsp+70h] [rbp-28h]
  __int64 v9; // [rsp+78h] [rbp-20h]

  if ( (unsigned int)dword_140007010 > 5 )
  {
    v2 = *(_DWORD *)(*((_QWORD *)P + 1) + 464LL);
    v6 = &v3;
    v3 = v2;
    v8 = &v4;
    v7 = 4;
    v9 = 4;
    v4 = 2;
    tlgWriteTransfer_EtwWriteTransfer((__int64)&dword_140007010, (unsigned __int8 *)&unk_140005400, 0, 0, 4u, &v5);
  }
  BampRemoveThrottlingActionItem((_QWORD *)P + 29);
  BampDereferenceThrottledProcessInformation(P);
}

```

## disassembly

```asm
0x140013c7c  mov     r11, rsp
0x140013c7f  push    rbx
0x140013c80  sub     rsp, 90h
0x140013c87  mov     rax, cs:__security_cookie
0x140013c8e  xor     rax, rsp
0x140013c91  mov     [rsp+98h+var_18], rax
0x140013c99  mov     eax, cs:dword_140007010
0x140013c9f  mov     rbx, rcx
0x140013ca2  cmp     eax, 5
0x140013ca5  jbe     short loc_140013CFF
0x140013ca7  mov     rax, [rcx+8]
0x140013cab  lea     rdx, unk_140005400
0x140013cb2  xor     r9d, r9d
0x140013cb5  xor     r8d, r8d
0x140013cb8  mov     ecx, [rax+1D0h]
0x140013cbe  lea     rax, [r11-68h]
0x140013cc2  mov     [r11-38h], rax
0x140013cc6  lea     rax, [r11-64h]
0x140013cca  mov     [rsp+98h+var_68], ecx
0x140013cce  mov     ecx, 4
0x140013cd3  mov     [r11-28h], rax
0x140013cd7  lea     rax, [r11-58h]
0x140013cdb  mov     [r11-70h], rax
0x140013cdf  mov     [rsp+98h+var_78], ecx
0x140013ce3  mov     [r11-30h], rcx
0x140013ce7  mov     [r11-20h], rcx
0x140013ceb  lea     rcx, dword_140007010
0x140013cf2  mov     [rsp+98h+var_64], 2
0x140013cfa  call    _tlgWriteTransfer_EtwWriteTransfer
0x140013cff  lea     rcx, [rbx+0E8h]
0x140013d06  call    BampRemoveThrottlingActionItem
0x140013d0b  mov     rcx, rbx; P
0x140013d0e  call    BampDereferenceThrottledProcessInformation
0x140013d13  mov     rcx, [rsp+98h+var_18]
0x140013d1b  xor     rcx, rsp; StackCookie
0x140013d1e  call    __security_check_cookie
0x140013d23  add     rsp, 90h
0x140013d2a  pop     rbx
0x140013d2b  retn
```
