# Mso::SVG::operator<<(std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &,Mso::SVG::UnescapedString const &)

- ea: `0x180016410`
- end: `0x180016501`
- name: `??6SVG@Mso@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@std@@AEAV23@AEBVUnescapedString@01@@Z`
- size: `241`
- prototype: ``
- caller_count: `17`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180016504`
- `0x1800f63fc`
- `0x1800f69e0`
- `0x1800fc310`
- `0x1800ff740`
- `0x180100c60`
- `0x180101290`
- `0x18010fc80`
- `0x18010ff10`
- `0x180110110`
- `0x180120dc0`
- `0x180123ce0`
- `0x180124c80`
- `0x180125654`
- `0x180125d34`
- `0x180127244`
- `0x18012d850`

## callees

- `0x180016410`
- `0x18001c888`
- `0x18013d650`

## import_xrefs

- `Mso20Win32Client!__imp_?EscapeXml@Xml@Mso@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@4@W4Version@12@@Z` at `0x180016471`
- `Mso20Win32Client!__imp_?EscapeXml@Xml@Mso@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@4@W4Version@12@@Z` at `0x180016471`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800164d9`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800164d9`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800164d2`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x1800164d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Mso::SVG::operator<<(__int64 a1, _QWORD *a2)
{
  _QWORD *v3; // rcx
  __int64 v4; // rax
  void **v5; // rdx
  void *v6; // rcx
  _QWORD v8[2]; // [rsp+30h] [rbp-40h] BYREF
  void *Block[2]; // [rsp+40h] [rbp-30h] BYREF
  __m128i si128; // [rsp+50h] [rbp-20h]

  v3 = a2;
  if ( a2[3] > 7u )
    v3 = (_QWORD *)*a2;
  v4 = a2[2];
  v8[0] = v3;
  v8[1] = v4;
  *(_OWORD *)Block = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(Block[0]) = 0;
  Mso::Xml::EscapeXml(Block, v8, 0);
  v5 = Block;
  if ( si128.m128i_i64[1] > 7uLL )
    v5 = (void **)Block[0];
  std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(a1, v5, si128.m128i_i64[0]);
  if ( si128.m128i_i64[1] > 7uLL )
  {
    v6 = Block[0];
    if ( (unsigned __int64)(2 * si128.m128i_i64[1] + 2) >= 0x1000 )
    {
      v6 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v6 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v6);
  }
  return a1;
}

```

## disassembly

```asm
0x180016410  mov     [rsp-8+arg_8], rbx
0x180016415  mov     [rsp-8+arg_10], rdi
0x18001641a  push    rbp
0x18001641b  mov     rbp, rsp
0x18001641e  sub     rsp, 70h
0x180016422  mov     rax, cs:__security_cookie
0x180016429  xor     rax, rsp
0x18001642c  mov     [rbp+var_10], rax
0x180016430  mov     rbx, rcx
0x180016433  mov     rcx, rdx
0x180016436  cmp     qword ptr [rdx+18h], 7
0x18001643b  jbe     short loc_180016440
0x18001643d  mov     rcx, [rdx]
0x180016440  mov     rax, [rdx+10h]
0x180016444  mov     [rbp+var_40], rcx
0x180016448  mov     [rbp+var_38], rax
0x18001644c  xorps   xmm0, xmm0
0x18001644f  movups  xmmword ptr [rbp+Block], xmm0
0x180016453  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001645b  movdqu  [rbp+var_20], xmm1
0x180016460  xor     edi, edi
0x180016462  mov     word ptr [rbp+Block], di
0x180016466  xor     r8d, r8d
0x180016469  lea     rdx, [rbp+var_40]
0x18001646d  lea     rcx, [rbp+Block]
0x180016471  call    cs:__imp_?EscapeXml@Xml@Mso@@YAXAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@4@W4Version@12@@Z; Mso::Xml::EscapeXml(std::wstring &,std::wstring_view const &,Mso::Xml::Version)
0x180016477  lea     rdx, [rbp+Block]
0x18001647b  cmp     qword ptr [rbp+var_20+8], 7
0x180016480  cmova   rdx, [rbp+Block]
0x180016485  mov     r8, qword ptr [rbp+var_20]
0x180016489  mov     rcx, rbx
0x18001648c  call    ??$_Insert_string@_WU?$char_traits@_W@std@@_K@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@QEB_W_K@Z; std::_Insert_string<wchar_t,std::char_traits<wchar_t>,unsigned __int64>(std::wostream &,wchar_t const * const,unsigned __int64)
0x180016491  mov     rax, qword ptr [rbp+var_20+8]
0x180016495  cmp     rax, 7
0x180016499  jbe     short loc_1800164E0
0x18001649b  mov     rcx, [rbp+Block]; Block
0x18001649f  mov     rdx, rcx
0x1800164a2  lea     rax, ds:2[rax*2]
0x1800164aa  cmp     rax, 1000h
0x1800164b0  jb      short loc_1800164D9
0x1800164b2  mov     rcx, [rcx-8]
0x1800164b6  sub     rdx, rcx
0x1800164b9  lea     rax, [rdx-8]
0x1800164bd  cmp     rax, 1Fh
0x1800164c1  jbe     short loc_1800164D9
0x1800164c3  mov     [rsp+70h+Reserved], rdi; Reserved
0x1800164c8  xor     r9d, r9d; LineNo
0x1800164cb  xor     r8d, r8d; FileName
0x1800164ce  xor     edx, edx; FunctionName
0x1800164d0  xor     ecx, ecx; Expression
0x1800164d2  call    cs:__imp__invoke_watson
0x1800164d9  call    cs:__imp_free
0x1800164df  nop
0x1800164e0  mov     rax, rbx
0x1800164e3  mov     rcx, [rbp+var_10]
0x1800164e7  xor     rcx, rsp; StackCookie
0x1800164ea  call    __security_check_cookie
0x1800164ef  lea     r11, [rsp+70h+var_s0]
0x1800164f4  mov     rbx, [r11+18h]
0x1800164f8  mov     rdi, [r11+20h]
0x1800164fc  mov     rsp, r11
0x1800164ff  pop     rbp
0x180016500  retn
```
