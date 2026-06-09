# NetSetupCreateObject

- ea: `0x18000f690`
- end: `0x18000f746`
- name: `NetSetupCreateObject`
- size: `182`
- prototype: `__int64 __fastcall(__int64, int, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18000bd18`

## callees

- `0x1800015b0`
- `0x1800016d0`
- `0x18000d310`
- `0x18000d564`
- `0x1800119f0`

## pseudocode

```c
__int64 __fastcall NetSetupCreateObject(__int64 a1, int a2, int a3, __int64 a4, __int64 a5)
{
  __int64 v6; // rax
  __int128 v7; // xmm1
  __int64 v8; // rbx
  int v10; // [rsp+30h] [rbp-51h] BYREF
  int v11; // [rsp+38h] [rbp-49h] BYREF
  _OWORD v12[2]; // [rsp+40h] [rbp-41h] BYREF
  __int64 v13; // [rsp+60h] [rbp-21h]
  char v14; // [rsp+70h] [rbp-11h] BYREF
  __int64 v15; // [rsp+98h] [rbp+17h] BYREF
  __int64 v16; // [rsp+A0h] [rbp+1Fh] BYREF
  __int64 v17; // [rsp+A8h] [rbp+27h] BYREF

  v11 = a2;
  v16 = a5;
  v15 = a1;
  v10 = a3;
  v17 = a4;
  EtwApiBegin(a1, 5);
  v6 = lambda_6e0480777e5e4dfd72512a56b503d635_::_lambda_6e0480777e5e4dfd72512a56b503d635_(
         (unsigned int)&v14,
         (unsigned int)&v11,
         (unsigned int)&v17,
         (unsigned int)&v10,
         (__int64)&v16,
         (__int64)&v15);
  v7 = *(_OWORD *)(v6 + 16);
  v12[0] = *(_OWORD *)v6;
  v13 = *(_QWORD *)(v6 + 32);
  v12[1] = v7;
  v8 = (unsigned int)NetSetupExecuteInFrame__lambda_6e0480777e5e4dfd72512a56b503d635_(v12);
  EtwApiEnd(a1, 5, v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000f690  push    rbp
0x18000f692  push    rbx
0x18000f693  push    rdi
0x18000f694  lea     rbp, [rsp-3Fh]
0x18000f699  sub     rsp, 0C0h
0x18000f6a0  mov     rax, cs:__security_cookie
0x18000f6a7  xor     rax, rsp
0x18000f6aa  mov     [rbp+4Fh+var_20], rax
0x18000f6ae  mov     rax, [rbp+4Fh+arg_20]
0x18000f6b2  mov     rdi, rcx
0x18000f6b5  mov     [rbp+4Fh+var_98], edx
0x18000f6b8  mov     edx, 5
0x18000f6bd  mov     [rbp+4Fh+var_30], rax
0x18000f6c1  mov     [rbp+4Fh+var_38], rcx
0x18000f6c5  mov     [rbp+4Fh+var_A0], r8d
0x18000f6c9  mov     [rbp+4Fh+var_28], r9
0x18000f6cd  call    EtwApiBegin
0x18000f6d2  lea     rax, [rbp+4Fh+var_38]
0x18000f6d6  mov     [rsp+0D0h+var_A8], rax
0x18000f6db  lea     r9, [rbp+4Fh+var_A0]
0x18000f6df  lea     rax, [rbp+4Fh+var_30]
0x18000f6e3  lea     r8, [rbp+4Fh+var_28]
0x18000f6e7  mov     [rsp+0D0h+var_B0], rax
0x18000f6ec  lea     rdx, [rbp+4Fh+var_98]
0x18000f6f0  lea     rcx, [rbp+4Fh+var_60]
0x18000f6f4  call    _lambda_6e0480777e5e4dfd72512a56b503d635____lambda_6e0480777e5e4dfd72512a56b503d635_
0x18000f6f9  lea     rcx, [rbp+4Fh+var_90]
0x18000f6fd  movups  xmm0, xmmword ptr [rax]
0x18000f700  movups  xmm1, xmmword ptr [rax+10h]
0x18000f704  movaps  [rbp+4Fh+var_90], xmm0
0x18000f708  movsd   xmm0, qword ptr [rax+20h]
0x18000f70d  movsd   [rbp+4Fh+var_70], xmm0
0x18000f712  movaps  [rbp+4Fh+var_80], xmm1
0x18000f716  call    NetSetupExecuteInFrame__lambda_6e0480777e5e4dfd72512a56b503d635___; NetSetupExecuteInFrame__lambda_6e0480777e5e4dfd72512a56b503d635_
0x18000f71b  mov     r8d, eax
0x18000f71e  mov     edx, 5
0x18000f723  mov     rcx, rdi
0x18000f726  mov     ebx, eax
0x18000f728  call    EtwApiEnd
0x18000f72d  mov     eax, ebx
0x18000f72f  mov     rcx, [rbp+4Fh+var_20]
0x18000f733  xor     rcx, rsp; StackCookie
0x18000f736  call    __security_check_cookie
0x18000f73b  add     rsp, 0C0h
0x18000f742  pop     rdi
0x18000f743  pop     rbx
0x18000f744  pop     rbp
0x18000f745  retn
```
