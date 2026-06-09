# McTemplateU0sq_EtwEventWriteTransfer

- ea: `0x18000c344`
- end: `0x18000c3d8`
- name: `McTemplateU0sq_EtwEventWriteTransfer`
- size: `148`
- prototype: `__int64 __fastcall(__int64, __int64, const char *, int)`
- caller_count: `30`
- callee_count: `3`
- tags: ``

## callers

- `0x180001d90`
- `0x180002560`
- `0x180003000`
- `0x1800030f0`
- `0x180003dc0`
- `0x180003fb0`
- `0x1800043d0`
- `0x1800058e0`
- `0x180005b30`
- `0x180005c20`
- `0x180006600`
- `0x1800066f0`
- `0x180009510`
- `0x18000bb98`
- `0x18000bee0`
- `0x18000c65c`
- `0x18000caa0`
- `0x18000d51c`
- `0x1800131d0`
- `0x18001355c`
- `0x180014088`
- `0x180014750`
- `0x1800148fc`
- `0x180014b54`
- `0x180014c2c`
- `0x1800157d4`
- `0x180015c94`
- `0x18001640c`
- `0x1800167c8`
- `0x180016b9c`

## callees

- `0x180007da0`
- `0x18000c344`
- `0x18001a380`

## pseudocode

```c
__int64 __fastcall McTemplateU0sq_EtwEventWriteTransfer(__int64 a1, __int64 a2, const char *a3, int a4)
{
  __int64 v4; // rax
  int v5; // eax
  _BYTE v7[16]; // [rsp+30h] [rbp-48h] BYREF
  const char *v8; // [rsp+40h] [rbp-38h]
  int v9; // [rsp+48h] [rbp-30h]
  int v10; // [rsp+4Ch] [rbp-2Ch]
  int *v11; // [rsp+50h] [rbp-28h]
  __int64 v12; // [rsp+58h] [rbp-20h]
  int v13; // [rsp+98h] [rbp+20h] BYREF

  v13 = a4;
  if ( a3 )
  {
    v4 = -1;
    do
      ++v4;
    while ( a3[v4] );
    v5 = v4 + 1;
  }
  else
  {
    v5 = 5;
  }
  v9 = v5;
  v10 = 0;
  v11 = &v13;
  v12 = 4;
  if ( !a3 )
    a3 = "NULL";
  v8 = a3;
  return McGenEventWrite_EtwEventWriteTransfer(
           (unsigned int)"NULL",
           (unsigned int)FunctionName_Returned_Error,
           (_DWORD)a3,
           3,
           (__int64)v7);
}

```

## disassembly

```asm
0x18000c344  mov     [rsp+arg_18], r9d
0x18000c349  sub     rsp, 78h
0x18000c34d  mov     rax, cs:__security_cookie
0x18000c354  xor     rax, rsp
0x18000c357  mov     [rsp+78h+var_18], rax
0x18000c35c  xor     edx, edx
0x18000c35e  test    r8, r8
0x18000c361  jz      short loc_18000C374
0x18000c363  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c367  inc     rax
0x18000c36a  cmp     [r8+rax], dl
0x18000c36e  jnz     short loc_18000C367
0x18000c370  inc     eax
0x18000c372  jmp     short loc_18000C379
0x18000c374  mov     eax, 5
0x18000c379  mov     [rsp+78h+var_30], eax
0x18000c37d  lea     rcx, aNull; "NULL"
0x18000c384  lea     rax, [rsp+78h+arg_18]
0x18000c38c  mov     [rsp+78h+var_2C], edx
0x18000c390  test    r8, r8
0x18000c393  mov     [rsp+78h+var_28], rax
0x18000c398  lea     rax, [rsp+78h+var_48]
0x18000c39d  mov     [rsp+78h+var_20], 4
0x18000c3a6  cmovz   r8, rcx
0x18000c3aa  mov     [rsp+78h+var_58], rax
0x18000c3af  mov     r9d, 3
0x18000c3b5  mov     [rsp+78h+var_38], r8
0x18000c3ba  lea     rdx, FunctionName_Returned_Error
0x18000c3c1  call    McGenEventWrite_EtwEventWriteTransfer
0x18000c3c6  mov     rcx, [rsp+78h+var_18]
0x18000c3cb  xor     rcx, rsp; StackCookie
0x18000c3ce  call    __security_check_cookie
0x18000c3d3  add     rsp, 78h
0x18000c3d7  retn
```
