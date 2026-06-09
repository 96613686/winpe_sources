# CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)

- ea: `0x140004780`
- end: `0x14000482e`
- name: `?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z`
- size: `174`
- prototype: `__int64 __fastcall(int)`
- caller_count: `17`
- callee_count: `3`
- tags: ``

## callers

- `0x140003744`
- `0x140004a08`
- `0x140005524`
- `0x140006230`
- `0x14000678c`
- `0x1400067f4`
- `0x140006924`
- `0x140006ab8`
- `0x1400077fc`
- `0x140007a34`
- `0x140007ae0`
- `0x140007dcc`
- `0x140011354`
- `0x1400113b0`
- `0x1400128a0`
- `0x140012938`
- `0x140012a38`

## callees

- `0x140004780`
- `0x1400134a0`
- `0x140014010`

## pseudocode

```c
__int64 __fastcall CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(int a1)
{
  __int64 v1; // rdx
  __int64 result; // rax
  unsigned __int64 v3; // rcx
  __int128 v4; // [rsp+30h] [rbp-28h] BYREF

  v1 = (unsigned int)a1;
  result = 1;
  v4 = 0;
  BYTE2(v4) = 1;
  BYTE4(v4) = 1;
  if ( a1 < 0 )
  {
    v3 = 0x4000000000000000LL;
  }
  else
  {
    result = 0;
    v3 = 0x8000000000000000uLL;
  }
  LOWORD(v4) = result;
  *((_QWORD *)&v4 + 1) = v1 | v3;
  if ( CEtwProviderT<void>::g_etwApi && CChkMacroETWLoggerT<CEmptyType>::g_chkMacroETWProvider )
  {
    result = ((__int64 (__fastcall *)(__int64, __int128 *))qword_140019D88)(
               CChkMacroETWLoggerT<CEmptyType>::g_chkMacroETWProvider,
               &v4);
    if ( (_BYTE)result )
      return ((__int64 (__fastcall *)(__int64, __int128 *, _QWORD, _QWORD))qword_140019D90)(
               CChkMacroETWLoggerT<CEmptyType>::g_chkMacroETWProvider,
               &v4,
               0,
               0);
  }
  return result;
}

```

## disassembly

```asm
0x140004780  sub     rsp, 58h
0x140004784  mov     rax, cs:__security_cookie
0x14000478b  xor     rax, rsp
0x14000478e  mov     [rsp+58h+var_18], rax
0x140004793  mov     edx, ecx
0x140004795  mov     eax, 1
0x14000479a  xorps   xmm0, xmm0
0x14000479d  movups  [rsp+58h+var_28], xmm0
0x1400047a2  mov     byte ptr [rsp+58h+var_28+2], al
0x1400047a6  mov     byte ptr [rsp+58h+var_28+4], al
0x1400047aa  test    ecx, ecx
0x1400047ac  js      short loc_1400047BC
0x1400047ae  xor     eax, eax
0x1400047b0  mov     rcx, 8000000000000000h
0x1400047ba  jmp     short loc_1400047C6
0x1400047bc  mov     rcx, 4000000000000000h
0x1400047c6  or      rcx, rdx
0x1400047c9  mov     word ptr [rsp+58h+var_28], ax
0x1400047ce  cmp     cs:?g_etwApi@?$CEtwProviderT@X@@1UCETWApiSet@1@A, 0; CEtwProviderT<void>::CETWApiSet CEtwProviderT<void>::g_etwApi
0x1400047d6  mov     qword ptr [rsp+58h+var_28+8], rcx
0x1400047db  jz      short loc_14000481C
0x1400047dd  mov     rcx, cs:?g_chkMacroETWProvider@?$CChkMacroETWLoggerT@VCEmptyType@@@@0V?$CEtwProviderT@X@@A; CEtwProviderT<void> CChkMacroETWLoggerT<CEmptyType>::g_chkMacroETWProvider
0x1400047e4  test    rcx, rcx
0x1400047e7  jz      short loc_14000481C
0x1400047e9  mov     rax, cs:qword_140019D88
0x1400047f0  lea     rdx, [rsp+58h+var_28]
0x1400047f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400047fa  test    al, al
0x1400047fc  jz      short loc_14000481C
0x1400047fe  mov     rcx, cs:?g_chkMacroETWProvider@?$CChkMacroETWLoggerT@VCEmptyType@@@@0V?$CEtwProviderT@X@@A; CEtwProviderT<void> CChkMacroETWLoggerT<CEmptyType>::g_chkMacroETWProvider
0x140004805  lea     rdx, [rsp+58h+var_28]
0x14000480a  mov     rax, cs:qword_140019D90
0x140004811  xor     r9d, r9d
0x140004814  xor     r8d, r8d
0x140004817  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000481c  mov     rcx, [rsp+58h+var_18]
0x140004821  xor     rcx, rsp; StackCookie
0x140004824  call    __security_check_cookie
0x140004829  add     rsp, 58h
0x14000482d  retn
```
