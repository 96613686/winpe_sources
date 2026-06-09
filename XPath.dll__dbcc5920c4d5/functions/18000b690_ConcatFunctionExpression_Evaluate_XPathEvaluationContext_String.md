# ConcatFunctionExpression::Evaluate(XPathEvaluationContext *,String &)

- ea: `0x18000b690`
- end: `0x18000b77f`
- name: `?Evaluate@ConcatFunctionExpression@@UEAAJPEAVXPathEvaluationContext@@AEAVString@@@Z`
- size: `239`
- prototype: `__int64 __fastcall(ConcatFunctionExpression *this, struct XPathEvaluationContext *, struct String *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000a640`
- `0x18000a690`
- `0x18000b690`
- `0x180010ee0`
- `0x180010fac`
- `0x180011840`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall ConcatFunctionExpression::Evaluate(
        ConcatFunctionExpression *this,
        struct XPathEvaluationContext *a2,
        struct String *a3)
{
  __int64 v4; // rbx
  __int64 v7; // rax
  int v8; // edi
  unsigned int v9; // r9d
  unsigned __int16 *v10; // rdx
  unsigned __int16 *v12; // [rsp+20h] [rbp-30h] BYREF
  __int16 v13; // [rsp+28h] [rbp-28h] BYREF
  char v14; // [rsp+2Ah] [rbp-26h]
  int v15; // [rsp+2Ch] [rbp-24h]
  unsigned __int16 *v16; // [rsp+30h] [rbp-20h]
  int v17; // [rsp+38h] [rbp-18h]

  v14 = 0;
  v16 = (unsigned __int16 *)&v13;
  v15 = 2;
  v13 = 0;
  v4 = 0;
  v17 = 0;
  while ( (unsigned int)v4 < *((_DWORD *)this + 9) )
  {
    v7 = *((_QWORD *)this + 3);
    v12 = 0;
    v8 = (*(__int64 (__fastcall **)(_QWORD, struct XPathEvaluationContext *, unsigned __int16 **))(**(_QWORD **)(v7 + 8 * v4)
                                                                                                 + 64LL))(
           *(_QWORD *)(v7 + 8 * v4),
           a2,
           &v12);
    if ( v8 < 0 )
      goto LABEL_8;
    v10 = (unsigned __int16 *)&qword_180016F98;
    if ( v12 )
      v10 = v12;
    v8 = STRU::Append((STRU *)&v13, v10, 0, v9);
    if ( v8 < 0 )
    {
LABEL_8:
      String::Reset((String *)&v12);
      goto LABEL_10;
    }
    String::Reset((String *)&v12);
    v4 = (unsigned int)(v4 + 1);
  }
  v8 = String::Initialize(a3, v16);
LABEL_10:
  BUFFER::~BUFFER((BUFFER *)&v13);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000b690  mov     [rsp-28h+arg_18], rbx
0x18000b695  push    rbp
0x18000b696  push    rsi
0x18000b697  push    rdi
0x18000b698  push    r14
0x18000b69a  push    r15
0x18000b69c  mov     rbp, rsp
0x18000b69f  sub     rsp, 50h
0x18000b6a3  mov     rax, cs:__security_cookie
0x18000b6aa  xor     rax, rsp
0x18000b6ad  mov     [rbp+var_10], rax
0x18000b6b1  lea     rax, [rbp+var_28]
0x18000b6b5  mov     [rbp+var_26], 0
0x18000b6b9  mov     [rbp+var_20], rax
0x18000b6bd  mov     r14, r8
0x18000b6c0  xor     eax, eax
0x18000b6c2  mov     [rbp+var_24], 2
0x18000b6c9  mov     [rbp+var_28], ax
0x18000b6cd  xor     ebx, ebx
0x18000b6cf  mov     r15, rdx
0x18000b6d2  mov     [rbp+var_18], 0
0x18000b6d9  mov     rsi, rcx
0x18000b6dc  cmp     ebx, [rsi+24h]
0x18000b6df  jnb     short loc_18000B746
0x18000b6e1  mov     rax, [rsi+18h]
0x18000b6e5  lea     r8, [rbp+var_30]
0x18000b6e9  mov     [rbp+var_30], 0
0x18000b6f1  mov     rdx, r15
0x18000b6f4  mov     rcx, [rax+rbx*8]
0x18000b6f8  mov     rax, [rcx]
0x18000b6fb  mov     rax, [rax+40h]
0x18000b6ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b704  mov     edi, eax
0x18000b706  test    eax, eax
0x18000b708  js      short loc_18000B73B
0x18000b70a  mov     rax, [rbp+var_30]
0x18000b70e  lea     rdx, qword_180016F98
0x18000b715  test    rax, rax
0x18000b718  lea     rcx, [rbp+var_28]; this
0x18000b71c  cmovnz  rdx, rax; unsigned __int16 *
0x18000b720  xor     r8d, r8d; unsigned int
0x18000b723  call    ?Append@STRU@@QEAAJPEBGKK@Z; STRU::Append(ushort const *,ulong,ulong)
0x18000b728  lea     rcx, [rbp+var_30]; this
0x18000b72c  mov     edi, eax
0x18000b72e  test    eax, eax
0x18000b730  js      short loc_18000B73F
0x18000b732  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000b737  inc     ebx
0x18000b739  jmp     short loc_18000B6DC
0x18000b73b  lea     rcx, [rbp+var_30]; this
0x18000b73f  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000b744  jmp     short loc_18000B754
0x18000b746  mov     rdx, [rbp+var_20]; unsigned __int16 *
0x18000b74a  mov     rcx, r14; this
0x18000b74d  call    ?Initialize@String@@QEAAJPEBG@Z; String::Initialize(ushort const *)
0x18000b752  mov     edi, eax
0x18000b754  lea     rcx, [rbp+var_28]; this
0x18000b758  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000b75d  mov     eax, edi
0x18000b75f  mov     rcx, [rbp+var_10]
0x18000b763  xor     rcx, rsp; StackCookie
0x18000b766  call    __security_check_cookie
0x18000b76b  mov     rbx, [rsp+50h+arg_18]
0x18000b773  add     rsp, 50h
0x18000b777  pop     r15
0x18000b779  pop     r14
0x18000b77b  pop     rdi
0x18000b77c  pop     rsi
0x18000b77d  pop     rbp
0x18000b77e  retn
```
