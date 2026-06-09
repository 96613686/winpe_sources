# CExternalStream::HrWrite(void const *,ulong,ulong *)

- ea: `0x18002b940`
- end: `0x18002ba7c`
- name: `?HrWrite@CExternalStream@@UEAAJPEBXKPEAK@Z`
- size: `316`
- prototype: `__int64 __fastcall(CExternalStream *__hidden this, const void *, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180011088`
- `0x180012178`
- `0x1800124c8`
- `0x1800171c4`
- `0x18002b940`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CExternalStream::HrWrite(CExternalStream *this, const void *a2, unsigned int a3, unsigned int *a4)
{
  int v8; // ebx
  int v9; // eax
  _DWORD v11[2]; // [rsp+30h] [rbp-38h] BYREF
  _BYTE v12[48]; // [rsp+38h] [rbp-30h] BYREF
  unsigned int v13; // [rsp+78h] [rbp+10h] BYREF
  unsigned int v14; // [rsp+80h] [rbp+18h]
  unsigned int *v15; // [rsp+88h] [rbp+20h]

  v15 = a4;
  v14 = a3;
  CGuard<IGuardableStream>::CGuard<IGuardableStream>(v12, (char *)this + 16);
  v13 = 0;
  if ( !a2 )
  {
    v8 = -2147024809;
LABEL_3:
    if ( g_doStackCaptures )
      DoStackCapture(v8);
    goto LABEL_20;
  }
  if ( *((_QWORD *)this + 14) )
  {
    v8 = 0;
  }
  else
  {
    v8 = -2003292404;
    if ( g_doStackCaptures )
      DoStackCapture(-2003292404);
  }
  if ( v8 >= 0 )
  {
    v11[0] = _mm_getcsr();
    v9 = (*(__int64 (__fastcall **)(_QWORD, const void *, _QWORD, unsigned int *))(**((_QWORD **)this + 14) + 32LL))(
           *((_QWORD *)this + 14),
           a2,
           a3,
           &v13);
    v8 = v9;
    if ( v9 < 0 && g_doStackCaptures )
      DoStackCapture(v9);
    v11[1] = v8;
    FPUStateSandboxSSE::~FPUStateSandboxSSE((FPUStateSandboxSSE *)v11);
    if ( v8 >= 0 )
    {
      if ( a4 )
        *a4 = v13;
      if ( a3 == v13 || a4 )
      {
        *((_DWORD *)this + 50) = 0;
        goto LABEL_20;
      }
      v8 = -2003292303;
      goto LABEL_3;
    }
  }
LABEL_20:
  CGuard<IGuardableStream>::~CGuard<IGuardableStream>(v12);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002b940  mov     rax, rsp
0x18002b943  mov     [rax+20h], r9
0x18002b947  mov     [rax+18h], r8d
0x18002b94b  mov     [rax+8], rcx
0x18002b94f  push    rbx
0x18002b950  push    rsi
0x18002b951  push    r12
0x18002b953  push    r14
0x18002b955  push    r15
0x18002b957  sub     rsp, 40h
0x18002b95b  mov     rsi, r9
0x18002b95e  mov     r15d, r8d
0x18002b961  mov     r12, rdx
0x18002b964  mov     r14, rcx
0x18002b967  lea     rdx, [rcx+10h]
0x18002b96b  lea     rcx, [rax-30h]
0x18002b96f  call    ??0?$CGuard@VIGuardableStream@@@@QEAA@AEAVIGuardableStream@@@Z; CGuard<IGuardableStream>::CGuard<IGuardableStream>(IGuardableStream &)
0x18002b974  mov     [rsp+68h+arg_8], 0
0x18002b97c  test    r12, r12
0x18002b97f  jnz     short loc_18002B99F
0x18002b981  mov     ebx, 80070057h
0x18002b986  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18002b98d  jz      loc_18002BA63
0x18002b993  mov     ecx, ebx; int
0x18002b995  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002b99a  jmp     loc_18002BA63
0x18002b99f  cmp     qword ptr [r14+70h], 0
0x18002b9a4  jnz     short loc_18002B9BD
0x18002b9a6  mov     ebx, 88982F0Ch
0x18002b9ab  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18002b9b2  jz      short loc_18002B9BF
0x18002b9b4  mov     ecx, ebx; int
0x18002b9b6  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002b9bb  jmp     short loc_18002B9BF
0x18002b9bd  xor     ebx, ebx
0x18002b9bf  test    ebx, ebx
0x18002b9c1  js      loc_18002BA63
0x18002b9c7  stmxcsr [rsp+68h+var_38]
0x18002b9cc  mov     eax, [rsp+68h+var_38]
0x18002b9d0  mov     [rsp+68h+var_38], eax
0x18002b9d4  mov     rcx, [r14+70h]
0x18002b9d8  mov     rax, [rcx]
0x18002b9db  lea     r9, [rsp+68h+arg_8]
0x18002b9e0  mov     r8d, r15d
0x18002b9e3  mov     rdx, r12
0x18002b9e6  mov     rax, [rax+20h]
0x18002b9ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9ef  mov     ebx, eax
0x18002b9f1  test    eax, eax
0x18002b9f3  jns     short loc_18002BA05
0x18002b9f5  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18002b9fc  jz      short loc_18002BA05
0x18002b9fe  mov     ecx, eax; int
0x18002ba00  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002ba05  mov     [rsp+68h+var_34], ebx
0x18002ba09  lea     rcx, [rsp+68h+var_38]; this
0x18002ba0e  call    ??1FPUStateSandboxSSE@@QEAA@XZ; FPUStateSandboxSSE::~FPUStateSandboxSSE(void)
0x18002ba13  test    ebx, ebx
0x18002ba15  js      short loc_18002BA63
0x18002ba17  jmp     short loc_18002BA37
0x18002ba19  mov     ebx, 80004005h
0x18002ba1e  mov     [rsp+68h+var_34], ebx
0x18002ba22  mov     r14, [rsp+68h+arg_0]
0x18002ba27  mov     rsi, [rsp+68h+arg_18]
0x18002ba2f  mov     r15d, [rsp+68h+arg_10]
0x18002ba37  test    rsi, rsi
0x18002ba3a  jz      short loc_18002BA42
0x18002ba3c  mov     eax, [rsp+68h+arg_8]
0x18002ba40  mov     [rsi], eax
0x18002ba42  cmp     r15d, [rsp+68h+arg_8]
0x18002ba47  jz      short loc_18002BA58
0x18002ba49  test    rsi, rsi
0x18002ba4c  jnz     short loc_18002BA58
0x18002ba4e  mov     ebx, 88982F71h
0x18002ba53  jmp     loc_18002B986
0x18002ba58  mov     dword ptr [r14+0C8h], 0
0x18002ba63  lea     rcx, [rsp+68h+var_30]
0x18002ba68  call    ??1?$CGuard@VIGuardableStream@@@@QEAA@XZ; CGuard<IGuardableStream>::~CGuard<IGuardableStream>(void)
0x18002ba6d  mov     eax, ebx
0x18002ba6f  add     rsp, 40h
0x18002ba73  pop     r15
0x18002ba75  pop     r14
0x18002ba77  pop     r12
0x18002ba79  pop     rsi
0x18002ba7a  pop     rbx
0x18002ba7b  retn
```
