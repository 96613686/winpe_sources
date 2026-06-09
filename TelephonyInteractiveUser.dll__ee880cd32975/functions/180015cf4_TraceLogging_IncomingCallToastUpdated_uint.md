# TraceLogging::IncomingCallToastUpdated(uint)

- ea: `0x180015cf4`
- end: `0x180015dad`
- name: `?IncomingCallToastUpdated@TraceLogging@@SAXI@Z`
- size: `185`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180012330`

## callees

- `0x1800011fc`
- `0x180001dc0`
- `0x180015cf4`

## pseudocode

```c
void __fastcall TraceLogging::IncomingCallToastUpdated(int a1)
{
  int v1; // [rsp+30h] [rbp-68h] BYREF
  __int64 v2; // [rsp+38h] [rbp-60h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v3; // [rsp+40h] [rbp-58h] BYREF
  __int64 *v4; // [rsp+60h] [rbp-38h]
  __int64 v5; // [rsp+68h] [rbp-30h]
  int *v6; // [rsp+70h] [rbp-28h]
  __int64 v7; // [rsp+78h] [rbp-20h]

  if ( (unsigned int)dword_180025000 > 5
    && (qword_180025010 & 0x400000000000LL) != 0
    && (qword_180025018 & 0x400000000000LL) == qword_180025018 )
  {
    v1 = a1;
    v6 = &v1;
    v2 = 0x1000000;
    v4 = &v2;
    v7 = 4;
    v5 = 8;
    tlgWriteTransfer_EventWriteTransfer((__int64)&dword_180025000, (unsigned __int8 *)&byte_18002102D, 0, 0, 4u, &v3);
  }
}

```

## disassembly

```asm
0x180015cf4  mov     r11, rsp
0x180015cf7  sub     rsp, 98h
0x180015cfe  mov     rax, cs:__security_cookie
0x180015d05  xor     rax, rsp
0x180015d08  mov     [rsp+98h+var_18], rax
0x180015d10  mov     eax, cs:dword_180025000
0x180015d16  cmp     eax, 5
0x180015d19  jbe     short loc_180015D95
0x180015d1b  mov     rdx, cs:qword_180025018
0x180015d22  mov     r8, 400000000000h
0x180015d2c  mov     rax, cs:qword_180025010
0x180015d33  test    r8, rax
0x180015d36  jz      short loc_180015D95
0x180015d38  mov     rax, rdx
0x180015d3b  and     rax, r8
0x180015d3e  cmp     rax, rdx
0x180015d41  jnz     short loc_180015D95
0x180015d43  lea     rax, [r11-68h]
0x180015d47  mov     [rsp+98h+var_68], ecx
0x180015d4b  mov     [r11-28h], rax
0x180015d4f  lea     rdx, byte_18002102D; int
0x180015d56  lea     rax, [r11-60h]
0x180015d5a  mov     qword ptr [r11-60h], 1000000h
0x180015d62  mov     ecx, 4
0x180015d67  mov     [r11-38h], rax
0x180015d6b  lea     rax, [r11-58h]
0x180015d6f  mov     [r11-20h], rcx
0x180015d73  mov     [r11-70h], rax
0x180015d77  xor     r9d, r9d; int
0x180015d7a  mov     [rsp+98h+var_78], ecx; ULONG
0x180015d7e  xor     r8d, r8d; int
0x180015d81  lea     rcx, dword_180025000; int
0x180015d88  mov     qword ptr [r11-30h], 8
0x180015d90  call    _tlgWriteTransfer_EventWriteTransfer
0x180015d95  mov     rcx, [rsp+98h+var_18]
0x180015d9d  xor     rcx, rsp; StackCookie
0x180015da0  call    __security_check_cookie
0x180015da5  add     rsp, 98h
0x180015dac  retn
```
