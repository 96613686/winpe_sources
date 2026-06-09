# HrCopyLockBytesToStream

- ea: `0x18000ec70`
- end: `0x18000ed2f`
- name: `HrCopyLockBytesToStream`
- size: `191`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000ec70`
- `0x180012fc0`
- `0x180013050`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall HrCopyLockBytesToStream(__int64 a1, __int64 a2, _DWORD *a3)
{
  __int64 i; // rbx
  __int64 result; // rax
  _DWORD v8[4]; // [rsp+30h] [rbp-1038h] BYREF
  _BYTE v9[4096]; // [rsp+40h] [rbp-1028h] BYREF

  v8[0] = 0;
  for ( i = 0; ; i += v8[0] )
  {
    result = (*(__int64 (__fastcall **)(__int64, __int64, _BYTE *, __int64, _DWORD *))(*(_QWORD *)a1 + 24LL))(
               a1,
               i,
               v9,
               4096,
               v8);
    if ( (int)result < 0 )
      break;
    if ( !v8[0] )
    {
      if ( a3 )
        *a3 = i;
      return result;
    }
    result = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, _QWORD))(*(_QWORD *)a2 + 32LL))(a2, v9, v8[0], 0);
    if ( (int)result < 0 )
      return result;
  }
  return result;
}

```

## disassembly

```asm
0x18000ec70  mov     [rsp+arg_18], rbx
0x18000ec75  push    rsi
0x18000ec76  push    rdi
0x18000ec77  push    r14
0x18000ec79  mov     eax, 1050h
0x18000ec7e  call    _alloca_probe
0x18000ec83  sub     rsp, rax
0x18000ec86  mov     rax, cs:__security_cookie
0x18000ec8d  xor     rax, rsp
0x18000ec90  mov     [rsp+1068h+var_28], rax
0x18000ec98  mov     rdi, r8
0x18000ec9b  mov     [rsp+1068h+var_1038], 0
0x18000eca3  mov     r14, rdx
0x18000eca6  mov     rsi, rcx
0x18000eca9  xor     ebx, ebx
0x18000ecab  mov     rax, [rsi]
0x18000ecae  lea     rcx, [rsp+1068h+var_1038]
0x18000ecb3  mov     [rsp+1068h+var_1048], rcx
0x18000ecb8  lea     r8, [rsp+1068h+var_1028]
0x18000ecbd  mov     r9d, 1000h
0x18000ecc3  mov     rdx, rbx
0x18000ecc6  mov     rcx, rsi
0x18000ecc9  mov     rax, [rax+18h]
0x18000eccd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecd2  test    eax, eax
0x18000ecd4  js      short loc_18000ED0B
0x18000ecd6  mov     r8d, [rsp+1068h+var_1038]
0x18000ecdb  test    r8d, r8d
0x18000ecde  jz      short loc_18000ED04
0x18000ece0  mov     rax, [r14]
0x18000ece3  lea     rdx, [rsp+1068h+var_1028]
0x18000ece8  xor     r9d, r9d
0x18000eceb  mov     rcx, r14
0x18000ecee  mov     rax, [rax+20h]
0x18000ecf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecf7  test    eax, eax
0x18000ecf9  js      short loc_18000ED0B
0x18000ecfb  mov     eax, [rsp+1068h+var_1038]
0x18000ecff  add     rbx, rax
0x18000ed02  jmp     short loc_18000ECAB
0x18000ed04  test    rdi, rdi
0x18000ed07  jz      short loc_18000ED0B
0x18000ed09  mov     [rdi], ebx
0x18000ed0b  mov     rcx, [rsp+1068h+var_28]
0x18000ed13  xor     rcx, rsp; StackCookie
0x18000ed16  call    __security_check_cookie
0x18000ed1b  mov     rbx, [rsp+1068h+arg_18]
0x18000ed23  add     rsp, 1050h
0x18000ed2a  pop     r14
0x18000ed2c  pop     rdi
0x18000ed2d  pop     rsi
0x18000ed2e  retn
```
