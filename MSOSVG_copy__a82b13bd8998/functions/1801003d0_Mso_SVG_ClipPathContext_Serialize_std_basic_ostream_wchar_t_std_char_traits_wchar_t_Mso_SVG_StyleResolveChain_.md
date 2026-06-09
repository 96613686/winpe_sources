# Mso::SVG::ClipPathContext::Serialize(std::basic_ostream<wchar_t,std::char_traits<wchar_t>> &,Mso::SVG::StyleResolveChain const &,Mso::SVG::SVGSaveParams const &)

- ea: `0x1801003d0`
- end: `0x180100546`
- name: `?Serialize@ClipPathContext@SVG@Mso@@UEBAXAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@std@@AEBVStyleResolveChain@23@AEBUSVGSaveParams@23@@Z`
- size: `374`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180016504`
- `0x18001a0c0`
- `0x1801003d0`
- `0x18013f7e8`
- `0x18013f810`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180100531`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010053f`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x180100531`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18010053f`

## string_xrefs

- `0x180100501`: `</clipPath>`
- `0x18010040d`: ` clipPathUnits="`
- `0x1801003f5`: `<clipPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Mso::SVG::ClipPathContext::Serialize(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v8; // rax
  __int64 v9; // rsi
  int v10; // edx
  const wchar_t *v11; // rdx
  __m128i *p_si128; // rsi
  __int64 v13; // rax
  __int64 v14; // rcx
  _QWORD v16[3]; // [rsp+30h] [rbp-38h] BYREF
  __m128i si128; // [rsp+48h] [rbp-20h] BYREF
  double v18; // [rsp+58h] [rbp-10h]

  std::operator<<<wchar_t,std::char_traits<wchar_t>>(a2, L"<clipPath");
  if ( *(_DWORD *)(a1 + 320) )
  {
    v8 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(a2, L" clipPathUnits=\"");
    v9 = v8;
    v10 = *(_DWORD *)(a1 + 320);
    if ( v10 )
    {
      if ( v10 != 1 )
        goto LABEL_15;
      v11 = L"objectBoundingBox";
    }
    else
    {
      v11 = L"userSpaceOnUse";
    }
    std::operator<<<wchar_t,std::char_traits<wchar_t>>(v8, v11);
    std::operator<<<wchar_t,std::char_traits<wchar_t>>(v9, L"\"");
  }
  Mso::SVG::StylableContext::SerializeProperties(a1, a2, a3, a4);
  std::operator<<<wchar_t,std::char_traits<wchar_t>>(a2, L">");
  if ( *(_QWORD *)(a1 + 328) )
  {
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v18 = sqrt_0(1.0);
    if ( *(_DWORD *)(a1 + 320) )
      p_si128 = &si128;
    else
      p_si128 = *(__m128i **)(a3 + 16);
    v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 104LL))(a1);
    v16[0] = 0;
    v16[1] = v13;
    v16[2] = p_si128;
    v14 = *(_QWORD *)(a1 + 328);
    if ( v14 )
    {
      (*(void (__fastcall **)(__int64, __int64, _QWORD *, __int64))(*(_QWORD *)v14 + 128LL))(v14, a2, v16, a4);
      return std::operator<<<wchar_t,std::char_traits<wchar_t>>(a2, L"</clipPath>");
    }
    CrashWithRecovery(0x1E3C3840u, 0);
LABEL_15:
    CrashWithRecovery(0x11CC35Bu, 0);
    JUMPOUT(0x180100545LL);
  }
  return std::operator<<<wchar_t,std::char_traits<wchar_t>>(a2, L"</clipPath>");
}

```

## disassembly

```asm
0x1801003d0  mov     rax, rsp
0x1801003d3  mov     [rax+8], rbx
0x1801003d7  mov     [rax+10h], rbp
0x1801003db  mov     [rax+18h], rsi
0x1801003df  mov     [rax+20h], rdi
0x1801003e3  push    r14
0x1801003e5  sub     rsp, 60h
0x1801003e9  mov     r14, r9
0x1801003ec  mov     rbp, r8
0x1801003ef  mov     rdi, rdx
0x1801003f2  mov     rbx, rcx
0x1801003f5  lea     rdx, aClippath; "<clipPath"
0x1801003fc  mov     rcx, rdi
0x1801003ff  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x180100404  cmp     dword ptr [rbx+140h], 0
0x18010040b  jz      short loc_180100459
0x18010040d  lea     rdx, aClippathunits_0; " clipPathUnits=\""
0x180100414  mov     rcx, rdi
0x180100417  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x18010041c  mov     rsi, rax
0x18010041f  mov     edx, [rbx+140h]
0x180100425  test    edx, edx
0x180100427  jz      short loc_18010043B
0x180100429  cmp     edx, 1
0x18010042c  jnz     loc_180100538
0x180100432  lea     rdx, aObjectbounding; "objectBoundingBox"
0x180100439  jmp     short loc_180100442
0x18010043b  lea     rdx, aUserspaceonuse; "userSpaceOnUse"
0x180100442  mov     rcx, rsi
0x180100445  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x18010044a  lea     rdx, asc_18014DE74; "\""
0x180100451  mov     rcx, rsi
0x180100454  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x180100459  mov     r9, r14
0x18010045c  mov     r8, rbp
0x18010045f  mov     rdx, rdi
0x180100462  mov     rcx, rbx
0x180100465  call    ?SerializeProperties@StylableContext@SVG@Mso@@QEBAXAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@std@@AEBVStyleResolveChain@23@AEBUSVGSaveParams@23@@Z; Mso::SVG::StylableContext::SerializeProperties(std::wostream &,Mso::SVG::StyleResolveChain const &,Mso::SVG::SVGSaveParams const &)
0x18010046a  lea     rdx, asc_18014E1DC; ">"
0x180100471  mov     rcx, rdi
0x180100474  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x180100479  cmp     qword ptr [rbx+148h], 0
0x180100481  jz      short loc_180100501
0x180100483  movdqa  xmm0, cs:__xmm@3ff00000000000003ff0000000000000
0x18010048b  movups  [rsp+68h+var_20], xmm0
0x180100490  movsd   xmm0, cs:__real@3ff0000000000000; X
0x180100498  call    sqrt_0
0x18010049d  movsd   [rsp+68h+var_10], xmm0
0x1801004a3  cmp     dword ptr [rbx+140h], 0
0x1801004aa  jnz     short loc_1801004B2
0x1801004ac  mov     rsi, [rbp+10h]
0x1801004b0  jmp     short loc_1801004B7
0x1801004b2  lea     rsi, [rsp+68h+var_20]
0x1801004b7  mov     rax, [rbx]
0x1801004ba  mov     rcx, rbx
0x1801004bd  mov     rax, [rax+68h]
0x1801004c1  call    cs:__guard_dispatch_icall_fptr
0x1801004c7  mov     [rsp+68h+var_38], 0
0x1801004d0  mov     [rsp+68h+var_30], rax
0x1801004d5  mov     [rsp+68h+var_28], rsi
0x1801004da  mov     rcx, [rbx+148h]
0x1801004e1  test    rcx, rcx
0x1801004e4  jz      short loc_18010052A
0x1801004e6  mov     rax, [rcx]
0x1801004e9  mov     r9, r14
0x1801004ec  lea     r8, [rsp+68h+var_38]
0x1801004f1  mov     rdx, rdi
0x1801004f4  mov     rax, [rax+80h]
0x1801004fb  call    cs:__guard_dispatch_icall_fptr
0x180100501  lea     rdx, aClippath_1; "</clipPath>"
0x180100508  mov     rcx, rdi
0x18010050b  lea     r11, [rsp+68h+var_8]
0x180100510  mov     rbx, [r11+10h]
0x180100514  mov     rbp, [r11+18h]
0x180100518  mov     rsi, [r11+20h]
0x18010051c  mov     rdi, [r11+28h]
0x180100520  mov     rsp, r11
0x180100523  pop     r14
0x180100525  jmp     ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x18010052a  xor     edx, edx
0x18010052c  mov     ecx, 1E3C3840h
0x180100531  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x180100537  nop
0x180100538  xor     edx, edx
0x18010053a  mov     ecx, 11CC35Bh
0x18010053f  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
```
