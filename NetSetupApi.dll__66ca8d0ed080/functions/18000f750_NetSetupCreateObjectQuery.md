# NetSetupCreateObjectQuery

- ea: `0x18000f750`
- end: `0x18000f860`
- name: `NetSetupCreateObjectQuery`
- size: `272`
- prototype: `__int64 __fastcall(__int64, int, __int64, int, char, __int64, char, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update`

## callees

- `0x18000d4d4`
- `0x18000d664`
- `0x1800119f0`

## pseudocode

```c
__int64 __fastcall NetSetupCreateObjectQuery(
        __int64 a1,
        int a2,
        __int64 a3,
        int a4,
        char a5,
        __int64 a6,
        char a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11)
{
  _OWORD *v11; // rax
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  int v17; // [rsp+60h] [rbp-A0h] BYREF
  int v18; // [rsp+68h] [rbp-98h] BYREF
  _OWORD v19[5]; // [rsp+70h] [rbp-90h] BYREF
  char v20; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v21; // [rsp+110h] [rbp+10h] BYREF
  __int64 v22; // [rsp+118h] [rbp+18h] BYREF
  __int64 v23; // [rsp+120h] [rbp+20h] BYREF
  __int64 v24; // [rsp+128h] [rbp+28h] BYREF
  __int64 v25; // [rsp+130h] [rbp+30h] BYREF
  __int64 v26; // [rsp+138h] [rbp+38h] BYREF
  __int64 v27; // [rsp+140h] [rbp+40h] BYREF

  v27 = a6;
  v26 = a8;
  v25 = a9;
  v21 = a10;
  v24 = a11;
  v23 = a1;
  v18 = a2;
  v22 = a3;
  v17 = a4;
  v11 = (_OWORD *)lambda_e30f95433a35718952289cf6812254ec_::_lambda_e30f95433a35718952289cf6812254ec_(
                    (unsigned int)&v20,
                    (unsigned int)&v18,
                    (unsigned int)&v17,
                    (unsigned int)&v27,
                    (__int64)&a5,
                    (__int64)&v26,
                    (__int64)&a7,
                    (__int64)&v25,
                    (__int64)&v24,
                    (__int64)&v23,
                    (__int64)&v22,
                    (__int64)&v21);
  v12 = v11[1];
  v19[0] = *v11;
  v13 = v11[2];
  v19[1] = v12;
  v14 = v11[3];
  v19[2] = v13;
  v15 = v11[4];
  v19[3] = v14;
  v19[4] = v15;
  return NetSetupExecuteInFrame__lambda_e30f95433a35718952289cf6812254ec_(v19);
}

```

## disassembly

```asm
0x18000f750  push    rbp
0x18000f752  lea     rbp, [rsp-50h]
0x18000f757  sub     rsp, 150h
0x18000f75e  mov     rax, cs:__security_cookie
0x18000f765  xor     rax, rsp
0x18000f768  mov     [rbp+50h+var_8], rax
0x18000f76c  mov     rax, [rbp+50h+arg_28]
0x18000f773  mov     [rbp+50h+var_10], rax
0x18000f777  mov     rax, [rbp+50h+arg_38]
0x18000f77e  mov     [rbp+50h+var_18], rax
0x18000f782  mov     rax, [rbp+50h+arg_40]
0x18000f789  mov     [rbp+50h+var_20], rax
0x18000f78d  mov     rax, [rbp+50h+arg_48]
0x18000f794  mov     [rbp+50h+var_40], rax
0x18000f798  mov     rax, [rbp+50h+arg_50]
0x18000f79f  mov     [rbp+50h+var_28], rax
0x18000f7a3  lea     rax, [rbp+50h+var_40]
0x18000f7a7  mov     [rsp+150h+var_F8], rax
0x18000f7ac  lea     rax, [rbp+50h+var_38]
0x18000f7b0  mov     [rsp+150h+var_100], rax
0x18000f7b5  lea     rax, [rbp+50h+var_30]
0x18000f7b9  mov     [rsp+150h+var_108], rax
0x18000f7be  lea     rax, [rbp+50h+var_28]
0x18000f7c2  mov     [rsp+150h+var_110], rax
0x18000f7c7  lea     rax, [rbp+50h+var_20]
0x18000f7cb  mov     [rsp+150h+var_118], rax
0x18000f7d0  lea     rax, [rbp+50h+arg_30]
0x18000f7d7  mov     [rsp+150h+var_120], rax
0x18000f7dc  lea     rax, [rbp+50h+var_18]
0x18000f7e0  mov     [rsp+150h+var_128], rax
0x18000f7e5  lea     rax, [rbp+50h+arg_20]
0x18000f7ec  mov     [rbp+50h+var_30], rcx
0x18000f7f0  lea     rcx, [rbp+50h+var_90]
0x18000f7f4  mov     [rsp+150h+var_E8], edx
0x18000f7f8  lea     rdx, [rsp+150h+var_E8]
0x18000f7fd  mov     [rbp+50h+var_38], r8
0x18000f801  lea     r8, [rsp+150h+var_F0]
0x18000f806  mov     [rsp+150h+var_F0], r9d
0x18000f80b  lea     r9, [rbp+50h+var_10]
0x18000f80f  mov     [rsp+150h+var_130], rax
0x18000f814  call    _lambda_e30f95433a35718952289cf6812254ec____lambda_e30f95433a35718952289cf6812254ec_
0x18000f819  lea     rcx, [rsp+150h+var_E0]
0x18000f81e  movups  xmm0, xmmword ptr [rax]
0x18000f821  movups  xmm1, xmmword ptr [rax+10h]
0x18000f825  movaps  [rsp+150h+var_E0], xmm0
0x18000f82a  movups  xmm0, xmmword ptr [rax+20h]
0x18000f82e  movaps  [rbp+50h+var_D0], xmm1
0x18000f832  movups  xmm1, xmmword ptr [rax+30h]
0x18000f836  movaps  [rbp+50h+var_C0], xmm0
0x18000f83a  movups  xmm0, xmmword ptr [rax+40h]
0x18000f83e  movaps  [rbp+50h+var_B0], xmm1
0x18000f842  movaps  [rbp+50h+var_A0], xmm0
0x18000f846  call    NetSetupExecuteInFrame__lambda_e30f95433a35718952289cf6812254ec___; NetSetupExecuteInFrame__lambda_e30f95433a35718952289cf6812254ec_
0x18000f84b  mov     rcx, [rbp+50h+var_8]
0x18000f84f  xor     rcx, rsp; StackCookie
0x18000f852  call    __security_check_cookie
0x18000f857  add     rsp, 150h
0x18000f85e  pop     rbp
0x18000f85f  retn
```
