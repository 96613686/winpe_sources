# JpnStringUtils::GetNormalizedString(ushort const *,unsigned __int64)

- ea: `0x180009898`
- end: `0x1800099c4`
- name: `?GetNormalizedString@JpnStringUtils@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG_K@Z`
- size: `300`
- prototype: `_QWORD *__fastcall(_QWORD *, LPCWSTR lpSrcStr, __int64 cchSrc)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, reparse_path`

## callers

- `0x180008ce0`
- `0x180009a78`

## callees

- `0x180002b94`
- `0x180009898`
- `0x18000ac70`
- `0x18000afa0`
- `0x18000c4f2`
- `0x18000c530`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000993c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009992`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000993c`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009992`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000996e`
- `api-ms-win-core-localization-l1-2-0!LCMapStringW` at `0x18000996e`

## pseudocode

```c
_QWORD *__fastcall JpnStringUtils::GetNormalizedString(_QWORD *a1, LPCWSTR lpSrcStr, __int64 cchSrc)
{
  void *v6; // rbx
  unsigned __int64 v7; // r14
  void *v8; // rbp
  WCHAR *lpDestStr; // rsi
  int v10; // eax
  void *v11; // rdx
  unsigned int v12; // r8d
  const char *v13; // r9
  _BYTE v15[64]; // [rsp+50h] [rbp-88h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  a1[3] = 7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
  if ( cchSrc )
  {
    memset_0(v15, 0, sizeof(v15));
    v6 = 0;
    v7 = 2 * cchSrc + 2;
    if ( v7 <= 0x20 )
    {
      lpDestStr = (WCHAR *)v15;
    }
    else
    {
      v8 = operator new[](saturated_mul(v7, 2u));
      lpDestStr = 0;
      if ( v8 )
      {
        operator delete[](0);
        v6 = v8;
        lpDestStr = (WCHAR *)v8;
      }
    }
    v10 = LCMapStringW(0x411u, 0x800100u, lpSrcStr, cchSrc, lpDestStr, 2 * cchSrc + 2);
    if ( !v10 )
      wil::details::in1diag3::_Throw_GetLastError(retaddr, v11, v12, v13);
    std::wstring::assign(a1, (char *)lpDestStr, v10);
    operator delete[](v6);
  }
  return a1;
}

```

## disassembly

```asm
0x180009898  push    rbx
0x18000989a  push    rbp
0x18000989b  push    rsi
0x18000989c  push    rdi
0x18000989d  push    r12
0x18000989f  push    r14
0x1800098a1  push    r15
0x1800098a3  sub     rsp, 0A0h
0x1800098aa  mov     rax, cs:__security_cookie
0x1800098b1  xor     rax, rsp
0x1800098b4  mov     [rsp+0D8h+var_48], rax
0x1800098bc  mov     r15, r8
0x1800098bf  mov     r12, rdx
0x1800098c2  mov     rdi, rcx
0x1800098c5  mov     [rsp+0D8h+var_98], rcx
0x1800098ca  mov     eax, 1
0x1800098cf  mov     [rsp+0D8h+var_A8], eax
0x1800098d3  mov     qword ptr [rcx+18h], 7
0x1800098db  mov     qword ptr [rcx+10h], 0
0x1800098e3  xor     ecx, ecx
0x1800098e5  mov     [rdi], cx
0x1800098e8  mov     [rsp+0D8h+var_A8], eax
0x1800098ec  test    r8, r8
0x1800098ef  jz      loc_180009999
0x1800098f5  xor     edx, edx; Val
0x1800098f7  lea     r8d, [rax+3Fh]; Size
0x1800098fb  lea     rcx, [rsp+0D8h+var_88]; void *
0x180009900  call    memset_0
0x180009905  xor     ebx, ebx
0x180009907  mov     [rsp+0D8h+var_A0], rbx
0x18000990c  lea     r14, ds:2[r15*2]
0x180009914  cmp     r14, 20h ; ' '
0x180009918  jbe     short loc_18000994F
0x18000991a  lea     eax, [rbx+2]
0x18000991d  mul     r14
0x180009920  lea     rcx, [rbx-1]
0x180009924  cmovb   rax, rcx
0x180009928  mov     rcx, rax; unsigned __int64
0x18000992b  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180009930  mov     rbp, rax
0x180009933  xor     esi, esi
0x180009935  test    rax, rax
0x180009938  jz      short loc_180009954
0x18000993a  xor     ecx, ecx
0x18000993c  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180009942  mov     rbx, rbp
0x180009945  mov     [rsp+0D8h+var_A0], rbx
0x18000994a  mov     rsi, rbp
0x18000994d  jmp     short loc_180009954
0x18000994f  lea     rsi, [rsp+0D8h+var_88]
0x180009954  mov     r9d, r15d; cchSrc
0x180009957  mov     [rsp+0D8h+cchDest], r14d; cchDest
0x18000995c  mov     [rsp+0D8h+lpDestStr], rsi; lpDestStr
0x180009961  mov     r8, r12; lpSrcStr
0x180009964  mov     edx, 800100h; dwMapFlags
0x180009969  mov     ecx, 411h; Locale
0x18000996e  call    cs:__imp_LCMapStringW
0x180009974  mov     rcx, [rsp+0D8h]; this
0x18000997c  test    eax, eax
0x18000997e  jz      short loc_1800099BE
0x180009980  movsxd  r8, eax
0x180009983  mov     rdx, rsi; Src
0x180009986  mov     rcx, rdi; void *
0x180009989  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18000998e  nop
0x18000998f  mov     rcx, rbx
0x180009992  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180009998  nop
0x180009999  mov     rax, rdi
0x18000999c  mov     rcx, [rsp+0D8h+var_48]
0x1800099a4  xor     rcx, rsp; StackCookie
0x1800099a7  call    __security_check_cookie
0x1800099ac  add     rsp, 0A0h
0x1800099b3  pop     r15
0x1800099b5  pop     r14
0x1800099b7  pop     r12
0x1800099b9  pop     rdi
0x1800099ba  pop     rsi
0x1800099bb  pop     rbp
0x1800099bc  pop     rbx
0x1800099bd  retn
0x1800099be  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
