# HrCopyStream

- ea: `0x18000ed40`
- end: `0x18000edfc`
- name: `HrCopyStream`
- size: `188`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000f9a0`

## callees

- `0x18000ed40`
- `0x180012fc0`
- `0x180013050`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall HrCopyStream(__int64 a1, __int64 a2, _DWORD *a3)
{
  int v6; // ebx
  __int64 result; // rax
  _DWORD v8[4]; // [rsp+30h] [rbp-1038h] BYREF
  _BYTE v9[4096]; // [rsp+40h] [rbp-1028h] BYREF

  v8[0] = 0;
  v6 = 0;
  do
  {
    result = (*(__int64 (__fastcall **)(__int64, _BYTE *, __int64, _DWORD *))(*(_QWORD *)a1 + 24LL))(a1, v9, 4096, v8);
    if ( (int)result < 0 )
      break;
    if ( !v8[0] )
      break;
    result = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, _QWORD))(*(_QWORD *)a2 + 32LL))(a2, v9, v8[0], 0);
    if ( (int)result < 0 )
      break;
    v6 += v8[0];
  }
  while ( v8[0] == 4096 );
  if ( a3 )
    *a3 = v6;
  return result;
}

```

## disassembly

```asm
0x18000ed40  mov     [rsp+arg_18], rbx
0x18000ed45  push    rsi
0x18000ed46  push    rdi
0x18000ed47  push    r14
0x18000ed49  mov     eax, 1050h
0x18000ed4e  call    _alloca_probe
0x18000ed53  sub     rsp, rax
0x18000ed56  mov     rax, cs:__security_cookie
0x18000ed5d  xor     rax, rsp
0x18000ed60  mov     [rsp+1068h+var_28], rax
0x18000ed68  mov     rdi, r8
0x18000ed6b  mov     [rsp+1068h+var_1038], 0
0x18000ed73  mov     r14, rdx
0x18000ed76  mov     rsi, rcx
0x18000ed79  xor     ebx, ebx
0x18000ed7b  mov     rax, [rsi]
0x18000ed7e  lea     r9, [rsp+1068h+var_1038]
0x18000ed83  mov     r8d, 1000h
0x18000ed89  lea     rdx, [rsp+1068h+var_1028]
0x18000ed8e  mov     rcx, rsi
0x18000ed91  mov     rax, [rax+18h]
0x18000ed95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ed9a  test    eax, eax
0x18000ed9c  js      short loc_18000EDD1
0x18000ed9e  mov     r8d, [rsp+1068h+var_1038]
0x18000eda3  test    r8d, r8d
0x18000eda6  jz      short loc_18000EDD1
0x18000eda8  mov     rax, [r14]
0x18000edab  lea     rdx, [rsp+1068h+var_1028]
0x18000edb0  xor     r9d, r9d
0x18000edb3  mov     rcx, r14
0x18000edb6  mov     rax, [rax+20h]
0x18000edba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000edbf  test    eax, eax
0x18000edc1  js      short loc_18000EDD1
0x18000edc3  add     ebx, [rsp+1068h+var_1038]
0x18000edc7  cmp     [rsp+1068h+var_1038], 1000h
0x18000edcf  jz      short loc_18000ED7B
0x18000edd1  test    rdi, rdi
0x18000edd4  jz      short loc_18000EDD8
0x18000edd6  mov     [rdi], ebx
0x18000edd8  mov     rcx, [rsp+1068h+var_28]
0x18000ede0  xor     rcx, rsp; StackCookie
0x18000ede3  call    __security_check_cookie
0x18000ede8  mov     rbx, [rsp+1068h+arg_18]
0x18000edf0  add     rsp, 1050h
0x18000edf7  pop     r14
0x18000edf9  pop     rdi
0x18000edfa  pop     rsi
0x18000edfb  retn
```
