# ipx::mtf::MtfTransportClientCoreUI::_CreateClientMessagePortName(ushort const *,_CLIENT_KEY const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> *)

- ea: `0x180021ee8`
- end: `0x180021f9a`
- name: `?_CreateClientMessagePortName@MtfTransportClientCoreUI@mtf@ipx@@IEAAJPEBGPEBU_CLIENT_KEY@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18001e914`

## callees

- `0x1800068a4`
- `0x18001031c`
- `0x18001e068`
- `0x180021ee8`
- `0x18002bca0`

## string_xrefs

- `0x180021f20`: `System\MTFSuggestionReady:%08X:%08X:%04X`

## pseudocode

```c
__int64 __fastcall ipx::mtf::MtfTransportClientCoreUI::_CreateClientMessagePortName(
        __int64 a1,
        __int64 a2,
        unsigned int *a3,
        void *a4)
{
  int v5; // eax
  __int64 v6; // r8
  int v8; // [rsp+20h] [rbp-238h]
  unsigned __int16 Src[264]; // [rsp+30h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  v8 = a3[1];
  v5 = StringCchPrintfW(Src, 0x104u, L"System\\MTFSuggestionReady:%08X:%08X:%04X", *a3);
  if ( v5 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x2AB,
      (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
      (const char *)(unsigned int)v5,
      v8);
  if ( Src[0] )
  {
    v6 = -1;
    do
      ++v6;
    while ( Src[v6] );
  }
  std::wstring::assign(a4, Src);
  return 0;
}

```

## disassembly

```asm
0x180021ee8  push    rbx
0x180021eea  sub     rsp, 250h
0x180021ef1  mov     rax, cs:__security_cookie
0x180021ef8  xor     rax, rsp
0x180021efb  mov     [rsp+258h+var_18], rax
0x180021f03  movzx   eax, word ptr [r8+8]
0x180021f08  lea     rcx, [rsp+258h+Src]; unsigned __int16 *
0x180021f0d  mov     [rsp+258h+var_230], eax
0x180021f11  mov     rbx, r9
0x180021f14  mov     eax, [r8+4]
0x180021f18  mov     edx, 104h; unsigned __int64
0x180021f1d  mov     r9d, [r8]
0x180021f20  lea     r8, aSystemMtfsugge; "System\\MTFSuggestionReady:%08X:%08X:%0"...
0x180021f27  mov     [rsp+258h+var_238], eax; int
0x180021f2b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180021f30  xor     ecx, ecx
0x180021f32  test    eax, eax
0x180021f34  js      short loc_180021F7D
0x180021f36  cmp     [rsp+258h+Src], cx
0x180021f3b  jnz     short loc_180021F42
0x180021f3d  mov     r8d, ecx
0x180021f40  jmp     short loc_180021F55
0x180021f42  lea     rax, [rsp+258h+Src]
0x180021f47  or      r8, 0FFFFFFFFFFFFFFFFh
0x180021f4b  inc     r8
0x180021f4e  cmp     [rax+r8*2], cx
0x180021f53  jnz     short loc_180021F4B
0x180021f55  lea     rdx, [rsp+258h+Src]; Src
0x180021f5a  mov     rcx, rbx; void *
0x180021f5d  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180021f62  xor     eax, eax
0x180021f64  mov     rcx, [rsp+258h+var_18]
0x180021f6c  xor     rcx, rsp; StackCookie
0x180021f6f  call    __security_check_cookie
0x180021f74  add     rsp, 250h
0x180021f7b  pop     rbx
0x180021f7c  retn
0x180021f7d  mov     rcx, [rsp+258h]; this
0x180021f85  lea     r8, aMincoreTextinp_2; "mincore\\textinput\\dev\\mtf\\internal"...
0x180021f8c  mov     r9d, eax; char *
0x180021f8f  mov     edx, 2ABh; void *
0x180021f94  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
