# CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)

- ea: `0x180009480`
- end: `0x18000952e`
- name: `?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z`
- size: `174`
- prototype: `__int64 __fastcall(int)`
- caller_count: `99`
- callee_count: `3`
- tags: ``

## callers

- `0x1800092c0`
- `0x180009300`
- `0x180009540`
- `0x180009f30`
- `0x18000a080`
- `0x18000a2cc`
- `0x18000a340`
- `0x18000a4c0`
- `0x18000a620`
- `0x18000a6d0`
- `0x18000a9c0`
- `0x18000aae0`
- `0x18000ac30`
- `0x18000ad40`
- `0x18000af78`
- `0x18000b0b0`
- `0x18000b220`
- `0x18000b310`
- `0x18000b3c0`
- `0x18000b400`
- `0x18000b448`
- `0x18000b57c`
- `0x18000b68c`
- `0x18000b7c0`
- `0x18000b860`
- `0x18000b884`
- `0x18000b984`
- `0x18000bb10`
- `0x18000be7c`
- `0x18000bf00`
- `0x18000c0cc`
- `0x18000c1c0`
- `0x18000c238`
- `0x18000c310`
- `0x18000c394`
- `0x18000c45c`
- `0x18000c55c`
- `0x18000c754`
- `0x18000c870`
- `0x18000cf20`
- `0x18000d124`
- `0x18000d7b4`
- `0x18000d95c`
- `0x18000ee34`
- `0x18000f220`
- `0x18000f264`
- `0x1800117b0`
- `0x180011e90`
- `0x180011fac`
- `0x180012238`

## callees

- `0x180001ac0`
- `0x180009480`
- `0x180023010`

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
    result = ((__int64 (__fastcall *)(__int64, __int128 *))qword_18002FC88)(
               CChkMacroETWLoggerT<CEmptyType>::g_chkMacroETWProvider,
               &v4);
    if ( (_BYTE)result )
      return ((__int64 (__fastcall *)(__int64, __int128 *, _QWORD, _QWORD))qword_18002FC90)(
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
0x180009480  sub     rsp, 58h
0x180009484  mov     rax, cs:__security_cookie
0x18000948b  xor     rax, rsp
0x18000948e  mov     [rsp+58h+var_18], rax
0x180009493  mov     edx, ecx
0x180009495  mov     eax, 1
0x18000949a  xorps   xmm0, xmm0
0x18000949d  movups  [rsp+58h+var_28], xmm0
0x1800094a2  mov     byte ptr [rsp+58h+var_28+2], al
0x1800094a6  mov     byte ptr [rsp+58h+var_28+4], al
0x1800094aa  test    ecx, ecx
0x1800094ac  js      short loc_1800094BC
0x1800094ae  xor     eax, eax
0x1800094b0  mov     rcx, 8000000000000000h
0x1800094ba  jmp     short loc_1800094C6
0x1800094bc  mov     rcx, 4000000000000000h
0x1800094c6  or      rcx, rdx
0x1800094c9  mov     word ptr [rsp+58h+var_28], ax
0x1800094ce  cmp     cs:?g_etwApi@?$CEtwProviderT@X@@1UCETWApiSet@1@A, 0; CEtwProviderT<void>::CETWApiSet CEtwProviderT<void>::g_etwApi
0x1800094d6  mov     qword ptr [rsp+58h+var_28+8], rcx
0x1800094db  jz      short loc_18000951C
0x1800094dd  mov     rcx, cs:?g_chkMacroETWProvider@?$CChkMacroETWLoggerT@VCEmptyType@@@@0V?$CEtwProviderT@X@@A; CEtwProviderT<void> CChkMacroETWLoggerT<CEmptyType>::g_chkMacroETWProvider
0x1800094e4  test    rcx, rcx
0x1800094e7  jz      short loc_18000951C
0x1800094e9  mov     rax, cs:qword_18002FC88
0x1800094f0  lea     rdx, [rsp+58h+var_28]
0x1800094f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094fa  test    al, al
0x1800094fc  jz      short loc_18000951C
0x1800094fe  mov     rcx, cs:?g_chkMacroETWProvider@?$CChkMacroETWLoggerT@VCEmptyType@@@@0V?$CEtwProviderT@X@@A; CEtwProviderT<void> CChkMacroETWLoggerT<CEmptyType>::g_chkMacroETWProvider
0x180009505  lea     rdx, [rsp+58h+var_28]
0x18000950a  mov     rax, cs:qword_18002FC90
0x180009511  xor     r9d, r9d
0x180009514  xor     r8d, r8d
0x180009517  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000951c  mov     rcx, [rsp+58h+var_18]
0x180009521  xor     rcx, rsp; StackCookie
0x180009524  call    __security_check_cookie
0x180009529  add     rsp, 58h
0x18000952d  retn
```
