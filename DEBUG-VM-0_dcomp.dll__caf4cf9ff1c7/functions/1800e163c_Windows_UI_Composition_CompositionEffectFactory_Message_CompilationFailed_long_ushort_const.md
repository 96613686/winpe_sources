# Windows::UI::Composition::CompositionEffectFactory::Message_CompilationFailed(long,ushort const *)

- ea: `0x1800e163c`
- end: `0x1800e1731`
- name: `?Message_CompilationFailed@CompositionEffectFactory@Composition@UI@Windows@@QEAAJJPEBG@Z`
- size: `245`
- prototype: `__int64 __fastcall(Windows::UI::Composition::CompositionEffectFactory *__hidden this, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1801520d0`

## callees

- `0x1800b2f8c`
- `0x1800e08a0`
- `0x1800e163c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800e1689`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800e1689`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e166a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e1716`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e166a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e1716`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800e16b4`
- `api-ms-win-core-winrt-error-l1-1-0!RoOriginateError` at `0x1800e16b4`
- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x1800e16c5`
- `api-ms-win-core-winrt-error-l1-1-0!GetRestrictedErrorInfo` at `0x1800e16c5`

## string_xrefs

- `0x1800e1698`: `onecoreuap\windows\dwm\dcomp\winrtnested\wrtcompositioneffectfactory.cpp`

## pseudocode

```c
__int64 __fastcall Windows::UI::Composition::CompositionEffectFactory::Message_CompilationFailed(
        Windows::UI::Composition::CompositionEffectFactory *this,
        unsigned int a2,
        const unsigned __int16 *a3)
{
  __int64 v6; // rdx
  HRESULT v7; // eax
  int v8; // eax
  unsigned int v9; // ecx
  int v10; // edx
  int v12; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  HSTRING string; // [rsp+50h] [rbp+18h] BYREF

  string = 0;
  if ( a3 )
  {
    WindowsDeleteString(0);
    v6 = -1;
    string = 0;
    do
      ++v6;
    while ( a3[v6] );
    v7 = WindowsCreateString(a3, v6, &string);
    if ( v7 < 0 )
      wil::details::in1diag3::FailFast_Hr(
        retaddr,
        (void *)0x144,
        (unsigned int)"onecoreuap\\windows\\dwm\\dcomp\\winrtnested\\wrtcompositioneffectfactory.cpp",
        (const char *)(unsigned int)v7,
        v12);
  }
  if ( (unsigned int)RoOriginateError(a2) )
    GetRestrictedErrorInfo((char *)this + 200);
  v8 = 1;
  if ( a2 == -2147024809 || a2 == -2147483629 )
  {
    v9 = a2;
    v10 = 3;
  }
  else
  {
    v9 = 0;
    v10 = 1;
  }
  *((_DWORD *)this + 48) = v10;
  *((_DWORD *)this + 49) = v9;
  if ( a2 != -2147024809 )
    v8 = -1;
  *((_DWORD *)this + 56) = v8;
  Windows::UI::Composition::CompositionEffectFactory::CompleteLoadResults(this);
  WindowsDeleteString(string);
  return 0;
}

```

## disassembly

```asm
0x1800e163c  mov     [rsp+arg_0], rbx
0x1800e1641  mov     [rsp+arg_8], rbp
0x1800e1646  push    rsi
0x1800e1647  push    rdi
0x1800e1648  push    r14; int
0x1800e164a  sub     rsp, 20h
0x1800e164e  xor     ebp, ebp
0x1800e1650  mov     ebx, edx
0x1800e1652  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800e1656  mov     edx, ebp
0x1800e1658  mov     [rsp+38h+string], rdx
0x1800e165d  mov     rsi, r8
0x1800e1660  mov     rdi, rcx
0x1800e1663  test    r8, r8
0x1800e1666  jz      short loc_1800E16B2
0x1800e1668  xor     ecx, ecx; string
0x1800e166a  call    cs:__imp_WindowsDeleteString
0x1800e1670  mov     rdx, r14
0x1800e1673  mov     [rsp+38h+string], rbp
0x1800e1678  inc     rdx; length
0x1800e167b  cmp     [rsi+rdx*2], bp
0x1800e167f  jnz     short loc_1800E1678
0x1800e1681  lea     r8, [rsp+38h+string]; string
0x1800e1686  mov     rcx, rsi; sourceString
0x1800e1689  call    cs:__imp_WindowsCreateString
0x1800e168f  test    eax, eax
0x1800e1691  jns     short loc_1800E16AD
0x1800e1693  mov     rcx, [rsp+38h]; this
0x1800e1698  lea     r8, aOnecoreuapWind_42; "onecoreuap\\windows\\dwm\\dcomp\\winrtn"...
0x1800e169f  mov     r9d, eax; char *
0x1800e16a2  mov     edx, 144h; void *
0x1800e16a7  call    ?FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::FailFast_Hr(void *,uint,char const *,long)
0x1800e16ad  mov     rdx, [rsp+38h+string]
0x1800e16b2  mov     ecx, ebx
0x1800e16b4  call    cs:__imp_RoOriginateError
0x1800e16ba  test    eax, eax
0x1800e16bc  jz      short loc_1800E16CB
0x1800e16be  lea     rcx, [rdi+0C8h]
0x1800e16c5  call    cs:__imp_GetRestrictedErrorInfo
0x1800e16cb  mov     r8d, 80070057h
0x1800e16d1  mov     eax, 1
0x1800e16d6  cmp     ebx, r8d
0x1800e16d9  jz      short loc_1800E16E9
0x1800e16db  cmp     ebx, 80000013h
0x1800e16e1  jz      short loc_1800E16E9
0x1800e16e3  mov     ecx, ebp
0x1800e16e5  mov     edx, eax
0x1800e16e7  jmp     short loc_1800E16F0
0x1800e16e9  mov     ecx, ebx
0x1800e16eb  mov     edx, 3
0x1800e16f0  mov     [rdi+0C0h], edx
0x1800e16f6  cmp     ebx, r8d
0x1800e16f9  mov     [rdi+0C4h], ecx
0x1800e16ff  mov     rcx, rdi; this
0x1800e1702  cmovnz  eax, r14d
0x1800e1706  mov     [rdi+0E0h], eax
0x1800e170c  call    ?CompleteLoadResults@CompositionEffectFactory@Composition@UI@Windows@@AEAAXXZ; Windows::UI::Composition::CompositionEffectFactory::CompleteLoadResults(void)
0x1800e1711  mov     rcx, [rsp+38h+string]; string
0x1800e1716  call    cs:__imp_WindowsDeleteString
0x1800e171c  mov     rbx, [rsp+38h+arg_0]
0x1800e1721  xor     eax, eax
0x1800e1723  mov     rbp, [rsp+38h+arg_8]
0x1800e1728  add     rsp, 20h
0x1800e172c  pop     r14
0x1800e172e  pop     rdi
0x1800e172f  pop     rsi
0x1800e1730  retn
```
