# CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)

- ea: `0x180009978`
- end: `0x180009a26`
- name: `?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z`
- size: `174`
- prototype: `__int64 __fastcall(int)`
- caller_count: `28`
- callee_count: `3`
- tags: ``

## callers

- `0x180008740`
- `0x180008a40`
- `0x180008bb0`
- `0x180008bf0`
- `0x180008dbc`
- `0x180008f10`
- `0x1800090d4`
- `0x180009320`
- `0x1800093c0`
- `0x180009430`
- `0x1800094a0`
- `0x180009560`
- `0x1800096e8`
- `0x180009890`
- `0x180009910`
- `0x180009a84`
- `0x180009cac`
- `0x18000a240`
- `0x18000a340`
- `0x18000a390`
- `0x18000a480`
- `0x18000a4e0`
- `0x18000a510`
- `0x18000ae50`
- `0x18000aed0`
- `0x18000af60`
- `0x18000afc0`
- `0x18000b0a0`

## callees

- `0x1800018e0`
- `0x180009978`
- `0x180027010`

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
    result = ((__int64 (__fastcall *)(__int64, __int128 *))qword_18002F910)(
               CChkMacroETWLoggerT<CEmptyType>::g_chkMacroETWProvider,
               &v4);
    if ( (_BYTE)result )
      return ((__int64 (__fastcall *)(__int64, __int128 *, _QWORD, _QWORD))qword_18002F918)(
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
0x180009978  sub     rsp, 58h
0x18000997c  mov     rax, cs:__security_cookie
0x180009983  xor     rax, rsp
0x180009986  mov     [rsp+58h+var_18], rax
0x18000998b  mov     edx, ecx
0x18000998d  mov     eax, 1
0x180009992  xorps   xmm0, xmm0
0x180009995  movups  [rsp+58h+var_28], xmm0
0x18000999a  mov     byte ptr [rsp+58h+var_28+2], al
0x18000999e  mov     byte ptr [rsp+58h+var_28+4], al
0x1800099a2  test    ecx, ecx
0x1800099a4  js      short loc_1800099B4
0x1800099a6  xor     eax, eax
0x1800099a8  mov     rcx, 8000000000000000h
0x1800099b2  jmp     short loc_1800099BE
0x1800099b4  mov     rcx, 4000000000000000h
0x1800099be  or      rcx, rdx
0x1800099c1  mov     word ptr [rsp+58h+var_28], ax
0x1800099c6  cmp     cs:?g_etwApi@?$CEtwProviderT@X@@1UCETWApiSet@1@A, 0; CEtwProviderT<void>::CETWApiSet CEtwProviderT<void>::g_etwApi
0x1800099ce  mov     qword ptr [rsp+58h+var_28+8], rcx
0x1800099d3  jz      short loc_180009A14
0x1800099d5  mov     rcx, cs:?g_chkMacroETWProvider@?$CChkMacroETWLoggerT@VCEmptyType@@@@0V?$CEtwProviderT@X@@A; CEtwProviderT<void> CChkMacroETWLoggerT<CEmptyType>::g_chkMacroETWProvider
0x1800099dc  test    rcx, rcx
0x1800099df  jz      short loc_180009A14
0x1800099e1  mov     rax, cs:qword_18002F910
0x1800099e8  lea     rdx, [rsp+58h+var_28]
0x1800099ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099f2  test    al, al
0x1800099f4  jz      short loc_180009A14
0x1800099f6  mov     rcx, cs:?g_chkMacroETWProvider@?$CChkMacroETWLoggerT@VCEmptyType@@@@0V?$CEtwProviderT@X@@A; CEtwProviderT<void> CChkMacroETWLoggerT<CEmptyType>::g_chkMacroETWProvider
0x1800099fd  lea     rdx, [rsp+58h+var_28]
0x180009a02  mov     rax, cs:qword_18002F918
0x180009a09  xor     r9d, r9d
0x180009a0c  xor     r8d, r8d
0x180009a0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a14  mov     rcx, [rsp+58h+var_18]
0x180009a19  xor     rcx, rsp; StackCookie
0x180009a1c  call    __security_check_cookie
0x180009a21  add     rsp, 58h
0x180009a25  retn
```
