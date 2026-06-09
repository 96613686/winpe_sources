# CChangePKBaseWindow::sOnCommand(IPopupWindow *,IPopupCommand *,void *)

- ea: `0x18000b0b0`
- end: `0x18000b1e9`
- name: `?sOnCommand@CChangePKBaseWindow@@SAJPEAUIPopupWindow@@PEAUIPopupCommand@@PEAX@Z`
- size: `313`
- prototype: `__int64 __fastcall(struct IPopupWindow *, struct IPopupCommand *, void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180001008`
- `0x180001ac0`
- `0x1800090dc`
- `0x180009480`
- `0x18000b0b0`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall CChangePKBaseWindow::sOnCommand(struct IPopupWindow *a1, struct IPopupCommand *a2, void *a3)
{
  int v4; // ecx
  unsigned int v5; // ebx
  int v6; // eax
  int v8; // [rsp+30h] [rbp-9h] BYREF
  unsigned int v9; // [rsp+34h] [rbp-5h] BYREF
  int v10; // [rsp+38h] [rbp-1h] BYREF
  char v11[32]; // [rsp+40h] [rbp+7h] BYREF
  int *v12; // [rsp+60h] [rbp+27h]
  __int64 v13; // [rsp+68h] [rbp+2Fh]
  unsigned int *v14; // [rsp+70h] [rbp+37h]
  __int64 v15; // [rsp+78h] [rbp+3Fh]

  v8 = 0;
  if ( a1 && a2 && a3 )
  {
    v6 = (*(__int64 (__fastcall **)(struct IPopupCommand *, int *))(*(_QWORD *)a2 + 32LL))(a2, &v8);
    v5 = v6;
    if ( v6 >= 0 )
    {
      if ( v8 != 101 && v8 != 102 )
        goto LABEL_11;
      v6 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)a3 + 48LL))(a3);
      v5 = v6;
      if ( v6 >= 0 )
        goto LABEL_11;
    }
    v4 = v6;
  }
  else
  {
    v4 = -2147024809;
    v5 = -2147024809;
  }
  CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
LABEL_11:
  if ( (unsigned int)dword_18002F1D0 > 5
    && (qword_18002F1E0 & 0x400000000000LL) != 0
    && (qword_18002F1E8 & 0x400000000000LL) == qword_18002F1E8 )
  {
    v10 = v8;
    v9 = v5;
    v15 = 4;
    v14 = &v9;
    v13 = 4;
    v12 = &v10;
    tlgWriteTransfer_EventWriteTransfer(&dword_18002F1D0, byte_18002B03B, &stru_18002FC00, 0, 4, v11);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  return v5;
}

```

## disassembly

```asm
0x18000b0b0  mov     [rsp-8+arg_0], rbx
0x18000b0b5  mov     [rsp-8+arg_18], rdi
0x18000b0ba  push    rbp
0x18000b0bb  lea     rbp, [rsp-57h]
0x18000b0c0  sub     rsp, 90h
0x18000b0c7  mov     rax, cs:__security_cookie
0x18000b0ce  xor     rax, rsp
0x18000b0d1  mov     [rbp+57h+var_10], rax
0x18000b0d5  mov     [rbp+57h+var_60], 0
0x18000b0dc  mov     rdi, r8
0x18000b0df  mov     r8, rdx
0x18000b0e2  test    rcx, rcx
0x18000b0e5  jnz     short loc_18000B0F0
0x18000b0e7  mov     ecx, 80070057h
0x18000b0ec  mov     ebx, ecx
0x18000b0ee  jmp     short loc_18000B137
0x18000b0f0  test    r8, r8
0x18000b0f3  jz      short loc_18000B0E7
0x18000b0f5  test    rdi, rdi
0x18000b0f8  jz      short loc_18000B0E7
0x18000b0fa  mov     rax, [rdx]
0x18000b0fd  mov     rcx, r8
0x18000b100  lea     rdx, [rbp+57h+var_60]
0x18000b104  mov     rax, [rax+20h]
0x18000b108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b10d  mov     ebx, eax
0x18000b10f  test    eax, eax
0x18000b111  js      short loc_18000B135
0x18000b113  mov     eax, [rbp+57h+var_60]
0x18000b116  sub     eax, 65h ; 'e'
0x18000b119  jz      short loc_18000B120
0x18000b11b  cmp     eax, 1
0x18000b11e  jnz     short loc_18000B13C
0x18000b120  mov     rax, [rdi]
0x18000b123  mov     rcx, rdi
0x18000b126  mov     rax, [rax+30h]
0x18000b12a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b12f  mov     ebx, eax
0x18000b131  test    eax, eax
0x18000b133  jns     short loc_18000B13C
0x18000b135  mov     ecx, eax
0x18000b137  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18000b13c  mov     eax, cs:dword_18002F1D0
0x18000b142  cmp     eax, 5
0x18000b145  jbe     short loc_18000B1BF
0x18000b147  mov     rcx, cs:qword_18002F1E8
0x18000b14e  mov     rdx, 400000000000h
0x18000b158  mov     rax, cs:qword_18002F1E0
0x18000b15f  test    rdx, rax
0x18000b162  jz      short loc_18000B1BF
0x18000b164  mov     rax, rcx
0x18000b167  and     rax, rdx
0x18000b16a  cmp     rax, rcx
0x18000b16d  jnz     short loc_18000B1BF
0x18000b16f  mov     eax, [rbp+57h+var_60]
0x18000b172  lea     r8, stru_18002FC00
0x18000b179  mov     [rbp+57h+var_58], eax
0x18000b17c  lea     rdx, byte_18002B03B
0x18000b183  mov     ecx, 4
0x18000b188  mov     [rbp+57h+var_5C], ebx
0x18000b18b  lea     rax, [rbp+57h+var_5C]
0x18000b18f  mov     [rbp+57h+var_18], rcx
0x18000b193  mov     [rbp+57h+var_20], rax
0x18000b197  xor     r9d, r9d
0x18000b19a  lea     rax, [rbp+57h+var_58]
0x18000b19e  mov     [rbp+57h+var_28], rcx
0x18000b1a2  mov     [rbp+57h+var_30], rax
0x18000b1a6  lea     rax, [rbp+57h+var_50]
0x18000b1aa  mov     [rsp+90h+var_68], rax
0x18000b1af  mov     [rsp+90h+var_70], ecx
0x18000b1b3  lea     rcx, dword_18002F1D0
0x18000b1ba  call    _tlgWriteTransfer_EventWriteTransfer
0x18000b1bf  mov     ecx, ebx
0x18000b1c1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18000b1c6  mov     eax, ebx
0x18000b1c8  mov     rcx, [rbp+57h+var_10]
0x18000b1cc  xor     rcx, rsp; StackCookie
0x18000b1cf  call    __security_check_cookie
0x18000b1d4  lea     r11, [rsp+90h+var_s0]
0x18000b1dc  mov     rbx, [r11+10h]
0x18000b1e0  mov     rdi, [r11+28h]
0x18000b1e4  mov     rsp, r11
0x18000b1e7  pop     rbp
0x18000b1e8  retn
```
