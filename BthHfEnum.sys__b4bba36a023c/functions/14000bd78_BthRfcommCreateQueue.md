# BthRfcommCreateQueue

- ea: `0x14000bd78`
- end: `0x14000be11`
- name: `BthRfcommCreateQueue`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140002b80`

## callees

- `0x14000bd78`
- `0x14001ae00`
- `0x14001b2c0`

## pseudocode

```c
__int64 __fastcall BthRfcommCreateQueue(__int64 a1, _QWORD *a2)
{
  __int64 result; // rax
  int v5; // [rsp+30h] [rbp-68h] BYREF
  __int64 v6; // [rsp+34h] [rbp-64h]
  _BYTE v7[84]; // [rsp+3Ch] [rbp-5Ch] BYREF
  __int64 v8; // [rsp+A8h] [rbp+10h] BYREF

  *a2 = 0;
  v8 = 0;
  memset(v7, 0, sizeof(v7));
  v5 = 96;
  v6 = 3;
  result = (*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, __int64, int *, _QWORD, __int64 *))(WdfFunctions_01015 + 1216))(
             WdfDriverGlobals,
             a1,
             &v5,
             0,
             &v8);
  if ( (int)result >= 0 )
  {
    *a2 = v8;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x14000bd78  mov     rax, rsp
0x14000bd7b  mov     [rax+8], rbx
0x14000bd7f  push    rdi
0x14000bd80  sub     rsp, 90h
0x14000bd87  mov     rdi, rdx
0x14000bd8a  mov     qword ptr [rdx], 0
0x14000bd91  xor     edx, edx; Val
0x14000bd93  mov     qword ptr [rax+10h], 0
0x14000bd9b  mov     rbx, rcx
0x14000bd9e  lea     rcx, [rax-5Ch]; void *
0x14000bda2  lea     r8d, [rdx+54h]; Size
0x14000bda6  call    memset
0x14000bdab  mov     rax, cs:WdfFunctions_01015
0x14000bdb2  lea     rcx, [rsp+98h+arg_8]
0x14000bdba  mov     [rsp+98h+var_68], 60h ; '`'
0x14000bdc2  lea     r8, [rsp+98h+var_68]
0x14000bdc7  mov     [rsp+98h+var_64], 3
0x14000bdd0  xor     r9d, r9d
0x14000bdd3  mov     [rsp+98h+var_78], rcx
0x14000bdd8  mov     rdx, rbx
0x14000bddb  mov     rax, [rax+4C0h]
0x14000bde2  mov     rcx, cs:WdfDriverGlobals
0x14000bde9  call    _guard_dispatch_icall
0x14000bdee  test    eax, eax
0x14000bdf0  js      short loc_14000BDFF
0x14000bdf2  mov     rax, [rsp+98h+arg_8]
0x14000bdfa  mov     [rdi], rax
0x14000bdfd  xor     eax, eax
0x14000bdff  mov     rbx, [rsp+98h+arg_0]
0x14000be07  add     rsp, 90h
0x14000be0e  pop     rdi
0x14000be0f  retn
```
