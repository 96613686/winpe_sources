# TraceLogging::IncomingCallToastHidden(uint)

- ea: `0x180015a7c`
- end: `0x180015b35`
- name: `?IncomingCallToastHidden@TraceLogging@@SAXI@Z`
- size: `185`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011ca0`

## callees

- `0x1800011fc`
- `0x180001dc0`
- `0x180015a7c`

## pseudocode

```c
void __fastcall TraceLogging::IncomingCallToastHidden(int a1)
{
  int v1; // [rsp+30h] [rbp-68h] BYREF
  __int64 v2; // [rsp+38h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v3; // [rsp+40h] [rbp-58h] BYREF
  int *v4; // [rsp+60h] [rbp-38h]
  __int64 v5; // [rsp+68h] [rbp-30h]
  __int64 *v6; // [rsp+70h] [rbp-28h]
  __int64 v7; // [rsp+78h] [rbp-20h]

  if ( (unsigned int)dword_180025000 > 5
    && (qword_180025010 & 0x400000000000LL) != 0
    && (qword_180025018 & 0x400000000000LL) == qword_180025018 )
  {
    v1 = a1;
    v6 = &v2;
    v2 = 0x1000000;
    v4 = &v1;
    v5 = 4;
    v7 = 8;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180025000, (unsigned __int8 *)&byte_180020FF1, 0, 0, 4u, &v3);
  }
}

```

## disassembly

```asm
0x180015a7c  mov     r11, rsp
0x180015a7f  sub     rsp, 98h
0x180015a86  mov     rax, cs:__security_cookie
0x180015a8d  xor     rax, rsp
0x180015a90  mov     [rsp+98h+var_18], rax
0x180015a98  mov     eax, cs:dword_180025000
0x180015a9e  cmp     eax, 5
0x180015aa1  jbe     short loc_180015B1D
0x180015aa3  mov     rdx, cs:qword_180025018
0x180015aaa  mov     r8, 400000000000h
0x180015ab4  mov     rax, cs:qword_180025010
0x180015abb  test    r8, rax
0x180015abe  jz      short loc_180015B1D
0x180015ac0  mov     rax, rdx
0x180015ac3  and     rax, r8
0x180015ac6  cmp     rax, rdx
0x180015ac9  jnz     short loc_180015B1D
0x180015acb  lea     rax, [r11-60h]
0x180015acf  mov     [rsp+98h+var_68], ecx
0x180015ad3  mov     [r11-28h], rax
0x180015ad7  lea     rdx, byte_180020FF1; int
0x180015ade  lea     rax, [r11-68h]
0x180015ae2  mov     qword ptr [r11-60h], 1000000h
0x180015aea  mov     ecx, 4
0x180015aef  mov     [r11-38h], rax
0x180015af3  lea     rax, [r11-58h]
0x180015af7  mov     [r11-30h], rcx
0x180015afb  mov     [r11-70h], rax
0x180015aff  xor     r9d, r9d; int
0x180015b02  mov     [rsp+98h+var_78], ecx; ULONG
0x180015b06  xor     r8d, r8d; int
0x180015b09  lea     rcx, dword_180025000; int
0x180015b10  mov     qword ptr [r11-20h], 8
0x180015b18  call    _tlgWriteTransfer_EventWriteTransfer
0x180015b1d  mov     rcx, [rsp+98h+var_18]
0x180015b25  xor     rcx, rsp; StackCookie
0x180015b28  call    __security_check_cookie
0x180015b2d  add     rsp, 98h
0x180015b34  retn
```
