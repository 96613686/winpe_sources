# NetSetupOpenAdvancedPropertyKey

- ea: `0x18000f8a0`
- end: `0x18000f8f1`
- name: `NetSetupOpenAdvancedPropertyKey`
- size: `81`
- prototype: `__int64 __fastcall(__int64, int, __int64, int, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000d2dc`

## pseudocode

```c
__int64 __fastcall NetSetupOpenAdvancedPropertyKey(__int64 a1, int a2, __int64 a3, int a4, char a5)
{
  _QWORD v6[6]; // [rsp+20h] [rbp-30h] BYREF
  __int64 v7; // [rsp+60h] [rbp+10h] BYREF
  int v8; // [rsp+68h] [rbp+18h] BYREF
  __int64 v9; // [rsp+70h] [rbp+20h] BYREF
  int v10; // [rsp+78h] [rbp+28h] BYREF

  v10 = a4;
  v9 = a3;
  v8 = a2;
  v7 = a1;
  v6[0] = &v7;
  v6[1] = &v9;
  v6[2] = &v8;
  v6[3] = &a5;
  v6[4] = &v10;
  return NetSetupExecuteInFrame__lambda_4d192a1ee078ff4af3b07e632a08e019_(v6);
}

```

## disassembly

```asm
0x18000f8a0  mov     rax, rsp
0x18000f8a3  mov     [rax+20h], r9d
0x18000f8a7  mov     [rax+18h], r8
0x18000f8ab  mov     [rax+10h], edx
0x18000f8ae  mov     [rax+8], rcx
0x18000f8b2  push    rbp
0x18000f8b3  mov     rbp, rsp
0x18000f8b6  sub     rsp, 50h
0x18000f8ba  lea     rax, [rbp+arg_0]
0x18000f8be  mov     [rbp+var_30], rax
0x18000f8c2  lea     rcx, [rbp+var_30]
0x18000f8c6  lea     rax, [rbp+arg_10]
0x18000f8ca  mov     [rbp+var_28], rax
0x18000f8ce  lea     rax, [rbp+arg_8]
0x18000f8d2  mov     [rbp+var_20], rax
0x18000f8d6  lea     rax, [rbp+arg_20]
0x18000f8da  mov     [rbp+var_18], rax
0x18000f8de  lea     rax, [rbp+arg_18]
0x18000f8e2  mov     [rbp+var_10], rax
0x18000f8e6  call    NetSetupExecuteInFrame__lambda_4d192a1ee078ff4af3b07e632a08e019___; NetSetupExecuteInFrame__lambda_4d192a1ee078ff4af3b07e632a08e019_
0x18000f8eb  add     rsp, 50h
0x18000f8ef  pop     rbp
0x18000f8f0  retn
```
