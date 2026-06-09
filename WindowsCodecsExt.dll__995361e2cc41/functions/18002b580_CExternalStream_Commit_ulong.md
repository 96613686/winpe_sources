# CExternalStream::Commit(ulong)

- ea: `0x18002b580`
- end: `0x18002b633`
- name: `?Commit@CExternalStream@@UEAAJK@Z`
- size: `179`
- prototype: `__int64 __fastcall(CExternalStream *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180011088`
- `0x180012178`
- `0x1800124c8`
- `0x1800171c4`
- `0x18002b580`
- `0x180033010`

## pseudocode

```c
__int64 __fastcall CExternalStream::Commit(CExternalStream *this, unsigned int a2)
{
  int v4; // ebx
  int v5; // eax
  int v7; // [rsp+40h] [rbp+8h] BYREF
  char v8; // [rsp+50h] [rbp+18h] BYREF

  CGuard<IGuardableStream>::CGuard<IGuardableStream>(&v8, this);
  if ( *((_QWORD *)this + 12) )
  {
    v4 = 0;
  }
  else
  {
    v4 = -2003292404;
    if ( g_doStackCaptures )
      DoStackCapture(-2003292404);
  }
  if ( v4 >= 0 )
  {
    v7 = _mm_getcsr();
    v5 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 12) + 64LL))(*((_QWORD *)this + 12), a2);
    v4 = v5;
    if ( v5 < 0 && g_doStackCaptures )
      DoStackCapture(v5);
    FPUStateSandboxSSE::~FPUStateSandboxSSE((FPUStateSandboxSSE *)&v7);
  }
  CGuard<IGuardableStream>::~CGuard<IGuardableStream>(&v8);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002b580  mov     [rsp+arg_8], rbx
0x18002b585  mov     [rsp+arg_18], rsi
0x18002b58a  push    rdi
0x18002b58b  sub     rsp, 30h
0x18002b58f  mov     esi, edx
0x18002b591  mov     rdi, rcx
0x18002b594  mov     rdx, rcx
0x18002b597  lea     rcx, [rsp+38h+arg_10]
0x18002b59c  call    ??0?$CGuard@VIGuardableStream@@@@QEAA@AEAVIGuardableStream@@@Z; CGuard<IGuardableStream>::CGuard<IGuardableStream>(IGuardableStream &)
0x18002b5a1  cmp     qword ptr [rdi+60h], 0
0x18002b5a6  jnz     short loc_18002B5BF
0x18002b5a8  mov     ebx, 88982F0Ch
0x18002b5ad  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18002b5b4  jz      short loc_18002B5C1
0x18002b5b6  mov     ecx, ebx; int
0x18002b5b8  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002b5bd  jmp     short loc_18002B5C1
0x18002b5bf  xor     ebx, ebx
0x18002b5c1  test    ebx, ebx
0x18002b5c3  js      short loc_18002B617
0x18002b5c5  stmxcsr [rsp+38h+arg_0]
0x18002b5ca  mov     eax, [rsp+38h+arg_0]
0x18002b5ce  mov     [rsp+38h+arg_0], eax
0x18002b5d2  mov     rcx, [rdi+60h]
0x18002b5d6  mov     rax, [rcx]
0x18002b5d9  mov     edx, esi
0x18002b5db  mov     rax, [rax+40h]
0x18002b5df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b5e4  mov     ebx, eax
0x18002b5e6  test    eax, eax
0x18002b5e8  jns     short loc_18002B5FA
0x18002b5ea  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18002b5f1  jz      short loc_18002B5FA
0x18002b5f3  mov     ecx, eax; int
0x18002b5f5  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18002b5fa  mov     [rsp+38h+var_18], ebx
0x18002b5fe  lea     rcx, [rsp+38h+arg_0]; this
0x18002b603  call    ??1FPUStateSandboxSSE@@QEAA@XZ; FPUStateSandboxSSE::~FPUStateSandboxSSE(void)
0x18002b608  test    ebx, ebx
0x18002b60a  js      short loc_18002B617
0x18002b60c  jmp     short loc_18002B617
0x18002b60e  mov     ebx, 80004005h
0x18002b613  mov     [rsp+38h+var_18], ebx
0x18002b617  lea     rcx, [rsp+38h+arg_10]
0x18002b61c  call    ??1?$CGuard@VIGuardableStream@@@@QEAA@XZ; CGuard<IGuardableStream>::~CGuard<IGuardableStream>(void)
0x18002b621  mov     eax, ebx
0x18002b623  mov     rbx, [rsp+38h+arg_8]
0x18002b628  mov     rsi, [rsp+38h+arg_18]
0x18002b62d  add     rsp, 30h
0x18002b631  pop     rdi
0x18002b632  retn
```
