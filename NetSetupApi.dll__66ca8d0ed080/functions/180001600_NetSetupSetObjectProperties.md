# NetSetupSetObjectProperties

- ea: `0x180001600`
- end: `0x1800016c5`
- name: `NetSetupSetObjectProperties`
- size: `197`
- prototype: `__int64 __fastcall(void *, GUID *, __int64, int, __int64)`
- caller_count: `8`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000c354`
- `0x18000c4a8`
- `0x18000eec0`
- `0x18000efe8`
- `0x18000f140`
- `0x18000f268`
- `0x18000f378`
- `0x18000fd78`

## callees

- `0x180001600`
- `0x1800016d0`
- `0x180001730`
- `0x18000d260`
- `0x18000d530`
- `0x18000f5a0`
- `0x1800119f0`

## pseudocode

```c
__int64 __fastcall NetSetupSetObjectProperties(void *a1, GUID *a2, __int64 a3, int a4, __int64 a5)
{
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // rax
  __int128 v11; // xmm0
  unsigned int v12; // ebx
  int v14; // [rsp+30h] [rbp-41h] BYREF
  int v15; // [rsp+38h] [rbp-39h] BYREF
  _OWORD v16[2]; // [rsp+40h] [rbp-31h] BYREF
  __int64 v17; // [rsp+60h] [rbp-11h]
  char v18; // [rsp+70h] [rbp-1h] BYREF
  void *v19; // [rsp+98h] [rbp+27h] BYREF
  __int64 v20; // [rsp+A0h] [rbp+2Fh] BYREF

  v20 = a5;
  v19 = a1;
  v15 = (int)a2;
  v14 = a4;
  LODWORD(v7) = GetTransactionId(a1, a2);
  if ( (Microsoft_Windows_Network_SetupEnableBits & 1) != 0 )
    McTemplateU0jq_EventWriteTransfer(v9, v8, v7, 10);
  v10 = lambda_331cf59cd0e0259273c77695b4bcfe7c_::_lambda_331cf59cd0e0259273c77695b4bcfe7c_(
          (unsigned int)&v18,
          (unsigned int)&v15,
          (unsigned int)&v14,
          (unsigned int)&v20,
          (__int64)&v19,
          a3);
  v11 = *(_OWORD *)(v10 + 16);
  v16[0] = *(_OWORD *)v10;
  v17 = *(_QWORD *)(v10 + 32);
  v16[1] = v11;
  v12 = NetSetupExecuteInFrame__lambda_331cf59cd0e0259273c77695b4bcfe7c_(v16);
  EtwApiEnd(a1, 10, v12);
  return v12;
}

```

## disassembly

```asm
0x180001600  push    rbp
0x180001602  push    rbx
0x180001603  push    rdi
0x180001604  lea     rbp, [rsp-3Fh]
0x180001609  sub     rsp, 0B0h
0x180001610  mov     rax, cs:__security_cookie
0x180001617  xor     rax, rsp
0x18000161a  mov     [rbp+4Fh+var_18], rax
0x18000161e  mov     rax, [rbp+4Fh+arg_20]
0x180001622  mov     rbx, r8
0x180001625  mov     [rbp+4Fh+var_20], rax
0x180001629  mov     rdi, rcx
0x18000162c  mov     [rbp+4Fh+var_28], rcx
0x180001630  mov     [rbp+4Fh+var_88], edx
0x180001633  mov     [rbp+4Fh+var_90], r9d
0x180001637  call    GetTransactionId
0x18000163c  test    cs:Microsoft_Windows_Network_SetupEnableBits, 1
0x180001643  jnz     short loc_1800016B5
0x180001645  lea     rax, [rbp+4Fh+var_28]
0x180001649  mov     [rsp+0C0h+var_98], rbx
0x18000164e  lea     r9, [rbp+4Fh+var_20]
0x180001652  mov     [rsp+0C0h+var_A0], rax
0x180001657  lea     r8, [rbp+4Fh+var_90]
0x18000165b  lea     rdx, [rbp+4Fh+var_88]
0x18000165f  lea     rcx, [rbp+4Fh+var_50]
0x180001663  call    _lambda_331cf59cd0e0259273c77695b4bcfe7c____lambda_331cf59cd0e0259273c77695b4bcfe7c_
0x180001668  lea     rcx, [rbp+4Fh+var_80]
0x18000166c  movups  xmm1, xmmword ptr [rax]
0x18000166f  movups  xmm0, xmmword ptr [rax+10h]
0x180001673  movaps  [rbp+4Fh+var_80], xmm1
0x180001677  movsd   xmm1, qword ptr [rax+20h]
0x18000167c  movsd   [rbp+4Fh+var_60], xmm1
0x180001681  movaps  [rbp+4Fh+var_70], xmm0
0x180001685  call    NetSetupExecuteInFrame__lambda_331cf59cd0e0259273c77695b4bcfe7c___; NetSetupExecuteInFrame__lambda_331cf59cd0e0259273c77695b4bcfe7c_
0x18000168a  mov     r8d, eax
0x18000168d  mov     edx, 0Ah
0x180001692  mov     rcx, rdi
0x180001695  mov     ebx, eax
0x180001697  call    EtwApiEnd
0x18000169c  mov     eax, ebx
0x18000169e  mov     rcx, [rbp+4Fh+var_18]
0x1800016a2  xor     rcx, rsp; StackCookie
0x1800016a5  call    __security_check_cookie
0x1800016aa  add     rsp, 0B0h
0x1800016b1  pop     rdi
0x1800016b2  pop     rbx
0x1800016b3  pop     rbp
0x1800016b4  retn
0x1800016b5  mov     r9d, 0Ah
0x1800016bb  mov     r8, rax
0x1800016be  call    McTemplateU0jq_EventWriteTransfer
0x1800016c3  jmp     short loc_180001645
```
