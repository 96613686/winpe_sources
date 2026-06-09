# sub_18008BEEC

- ea: `0x18008beec`
- end: `0x18008c026`
- name: `sub_18008BEEC`
- size: `314`
- prototype: `__int64 __fastcall(int, int, int, int, int, Concurrency::details::TaskStack *, __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x18008bcf0`

## callees

- `0x180003bc0`
- `0x1800040cc`
- `0x180004710`
- `0x180085d30`
- `0x180086100`
- `0x18008beec`
- `0x18008f154`
- `0x18008f438`
- `0x180096870`
- `0x18009882c`
- `0x180098a0c`
- `0x180098cc8`

## string_xrefs

- `0x18008bf3b`: `then() cannot be called on a default constructed task.`

## pseudocode

```c
_QWORD *__fastcall sub_18008BEEC(
        __int64 *a1,
        _QWORD *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        Concurrency::details::TaskStack *a6,
        __int64 a7)
{
  __int64 v10; // rbx
  __int64 v11; // rbx
  __int64 v12; // rax
  void *v14; // [rsp+38h] [rbp-71h]
  _QWORD v15[6]; // [rsp+40h] [rbp-69h] BYREF
  _BYTE pExceptionObject[56]; // [rsp+70h] [rbp-39h] BYREF

  v15[3] = a2;
  v15[4] = a6;
  v15[5] = a7;
  if ( !*a1 )
  {
    sub_18008F154(pExceptionObject, "then() cannot be called on a default constructed task.");
    throw (pplx::invalid_operation *)pExceptionObject;
  }
  v10 = 2;
  if ( a4 )
    v10 = a4;
  *a2 = 0;
  a2[1] = 0;
  sub_180086100(v15, a6);
  v15[2] = *((_QWORD *)a6 + 2);
  sub_180096870(a2, v10, v15);
  *(_BYTE *)(*a2 + 12LL) = *(_BYTE *)(*a1 + 12) != 0;
  *(_BYTE *)(*a2 + 13LL) = 1;
  sub_180098A0C(a2, a7);
  v11 = *a1;
  v14 = sub_1800040CC(0x90u);
  v12 = sub_180085D30(v14, a1, a2, a3);
  sub_18009882C(v11, v12);
  Concurrency::details::TaskStack::~TaskStack(a6);
  sub_180098CC8(a7 + 8);
  return a2;
}

```

## disassembly

```asm
0x18008beec  push    rbp
0x18008beee  push    rbx
0x18008beef  push    rsi
0x18008bef0  push    rdi
0x18008bef1  push    r12
0x18008bef3  push    r14
0x18008bef5  push    r15
0x18008bef7  lea     rbp, [rsp-7]
0x18008befc  sub     rsp, 0B0h
0x18008bf03  mov     rax, cs:__security_cookie
0x18008bf0a  xor     rax, rsp
0x18008bf0d  mov     [rbp+37h+var_38], rax
0x18008bf11  mov     r12, r8
0x18008bf14  mov     rdi, rdx
0x18008bf17  mov     rsi, rcx
0x18008bf1a  mov     [rbp+37h+var_88], rdx
0x18008bf1e  mov     r14, [rbp+37h+arg_28]
0x18008bf22  mov     [rbp+37h+var_80], r14
0x18008bf26  mov     r15, [rbp+37h+arg_30]
0x18008bf2a  mov     [rbp+37h+var_78], r15
0x18008bf2e  mov     [rbp+37h+var_B0], 0
0x18008bf35  cmp     qword ptr [rcx], 0
0x18008bf39  jnz     short loc_18008BF5C
0x18008bf3b  lea     rdx, aThenCannotBeCa; "then() cannot be called on a default co"...
0x18008bf42  lea     rcx, [rbp+37h+pExceptionObject]
0x18008bf46  call    sub_18008F154
0x18008bf4b  lea     rdx, __TI2?AVinvalid_operation@pplx@@; pThrowInfo
0x18008bf52  lea     rcx, [rbp+37h+pExceptionObject]; pExceptionObject
0x18008bf56  call    _CxxThrowException
0x18008bf5c  mov     ebx, 2
0x18008bf61  test    r9, r9
0x18008bf64  cmovnz  rbx, r9
0x18008bf68  mov     qword ptr [rdx], 0
0x18008bf6f  mov     qword ptr [rdx+8], 0
0x18008bf77  mov     [rbp+37h+var_B0], 1
0x18008bf7e  mov     rdx, r14
0x18008bf81  lea     rcx, [rbp+37h+var_A0]
0x18008bf85  call    sub_180086100
0x18008bf8a  mov     rax, [r14+10h]
0x18008bf8e  mov     [rbp+37h+var_90], rax
0x18008bf92  lea     r8, [rbp+37h+var_A0]
0x18008bf96  mov     rdx, rbx
0x18008bf99  mov     rcx, rdi
0x18008bf9c  call    sub_180096870
0x18008bfa1  mov     rax, [rsi]
0x18008bfa4  cmp     byte ptr [rax+0Ch], 0
0x18008bfa8  setnz   cl
0x18008bfab  mov     rax, [rdi]
0x18008bfae  mov     [rax+0Ch], cl
0x18008bfb1  mov     rax, [rdi]
0x18008bfb4  mov     byte ptr [rax+0Dh], 1
0x18008bfb8  mov     rdx, r15
0x18008bfbb  mov     rcx, rdi
0x18008bfbe  call    sub_180098A0C
0x18008bfc3  mov     rbx, [rsi]
0x18008bfc6  mov     ecx, 90h; Size
0x18008bfcb  call    sub_1800040CC
0x18008bfd0  mov     [rbp+37h+var_A8], rax
0x18008bfd4  mov     r9, r12
0x18008bfd7  mov     r8, rdi
0x18008bfda  mov     rdx, rsi
0x18008bfdd  mov     rcx, rax
0x18008bfe0  call    sub_180085D30
0x18008bfe5  nop
0x18008bfe6  mov     rdx, rax
0x18008bfe9  mov     rcx, rbx
0x18008bfec  call    sub_18009882C
0x18008bff1  nop
0x18008bff2  mov     rcx, r14; this
0x18008bff5  call    ??1TaskStack@details@Concurrency@@QEAA@XZ; Concurrency::details::TaskStack::~TaskStack(void)
0x18008bffa  nop
0x18008bffb  lea     rcx, [r15+8]
0x18008bfff  call    sub_180098CC8
0x18008c004  mov     rax, rdi
0x18008c007  mov     rcx, [rbp+37h+var_38]
0x18008c00b  xor     rcx, rsp; StackCookie
0x18008c00e  call    __security_check_cookie
0x18008c013  add     rsp, 0B0h
0x18008c01a  pop     r15
0x18008c01c  pop     r14
0x18008c01e  pop     r12
0x18008c020  pop     rdi
0x18008c021  pop     rsi
0x18008c022  pop     rbx
0x18008c023  pop     rbp
0x18008c024  retn
```
