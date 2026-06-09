# OException::OException(et::exceptionType,uint,wchar_t const (&)[63],std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &)

- ea: `0x1800060f4`
- end: `0x180006269`
- name: `??$?0$0DP@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V01@@OException@@QEAA@W4exceptionType@et@@IAEAY0DP@$$CB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000626c`

## callees

- `0x1800045ec`
- `0x1800046d8`
- `0x180005eb0`
- `0x1800060f4`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000620b`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x18000620b`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180006212`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180006212`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x18000615e`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180006233`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x18000615e`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180006233`

## string_xrefs

- `0x180006152`: `ORegistryKey.GetValue failure: Cannot get registry %s value %s`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OException::OException(__int64 a1, __int64 a2, int a3, __int64 a4, _QWORD *a5, __int64 a6)
{
  _WORD *v7; // rax
  __int64 v8; // rdx
  void *v9; // rcx
  const wchar_t *v10; // r8
  __int64 v12; // [rsp+30h] [rbp-50h] BYREF
  void *Block[2]; // [rsp+38h] [rbp-48h] BYREF
  __int64 v14; // [rsp+48h] [rbp-38h]
  unsigned __int64 v15; // [rsp+50h] [rbp-30h]
  wchar_t *Source[4]; // [rsp+58h] [rbp-28h] BYREF

  *(_DWORD *)a1 = 15;
  *(_DWORD *)(a1 + 516) = a3;
  *(_DWORD *)(a1 + 904) = 808464432;
  *(_WORD *)(a1 + 776) = 0;
  wcsncpy_s(
    (wchar_t *)(a1 + 520),
    0x80u,
    L"ORegistryKey.GetValue failure: Cannot get registry %s value %s",
    0xFFFFFFFFFFFFFFFFuLL);
  *(_OWORD *)Block = 0;
  v14 = 0;
  v15 = 7;
  LOWORD(Block[0]) = 0;
  v12 = 127;
  v7 = (_WORD *)std::wstring::_Allocate_for_capacity<0>(Block, &v12);
  v15 = v12;
  *v7 = Block[0];
  Block[0] = v7;
  v14 = 0;
  ArgumentWriter::FormatArguments<std::wstring,std::wstring>((__int64)Source, v8, L"", Block, a5, a6);
  if ( v15 > 7 )
  {
    v9 = Block[0];
    if ( 2 * v15 + 2 >= 0x1000 )
    {
      v9 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v9 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v9);
  }
  v10 = (const wchar_t *)Source;
  if ( Source[3] > (wchar_t *)7 )
    v10 = Source[0];
  wcsncpy_s((wchar_t *)(a1 + 4), 0x100u, v10, 0xFFFFFFFFFFFFFFFFuLL);
  std::wstring::_Tidy_deallocate(Source);
  return a1;
}

```

## disassembly

```asm
0x1800060f4  mov     [rsp-18h+arg_8], rbx
0x1800060f9  mov     [rsp-18h+arg_10], rsi
0x1800060fe  push    rbp
0x1800060ff  push    rdi
0x180006100  push    r14
0x180006102  mov     rbp, rsp
0x180006105  sub     rsp, 80h
0x18000610c  mov     rax, cs:__security_cookie
0x180006113  xor     rax, rsp
0x180006116  mov     [rbp+var_8], rax
0x18000611a  mov     rsi, rcx
0x18000611d  mov     rdi, [rbp+arg_20]
0x180006121  mov     rbx, [rbp+arg_28]
0x180006125  xor     r14d, r14d
0x180006128  mov     dword ptr [rcx], 0Fh
0x18000612e  mov     [rcx+204h], r8d
0x180006135  mov     dword ptr [rcx+388h], 30303030h
0x18000613f  mov     [rcx+308h], r14w
0x180006147  add     rcx, 208h; Destination
0x18000614e  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180006152  lea     r8, aOregistrykeyGe; "ORegistryKey.GetValue failure: Cannot g"...
0x180006159  mov     edx, 80h; SizeInWords
0x18000615e  call    cs:__imp_wcsncpy_s
0x180006164  xorps   xmm0, xmm0
0x180006167  movups  xmmword ptr [rbp+Block], xmm0
0x18000616b  mov     [rbp+var_38], r14
0x18000616f  mov     [rbp+var_30], 7
0x180006177  mov     word ptr [rbp+Block], r14w
0x18000617c  mov     [rbp+var_50], 7Fh
0x180006184  lea     rdx, [rbp+var_50]
0x180006188  lea     rcx, [rbp+Block]
0x18000618c  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)
0x180006191  mov     rcx, rax
0x180006194  mov     rax, [rbp+var_50]
0x180006198  mov     [rbp+var_30], rax
0x18000619c  movzx   eax, word ptr [rbp+Block]
0x1800061a0  mov     [rcx], ax
0x1800061a3  mov     [rbp+Block], rcx
0x1800061a7  mov     [rbp+var_38], r14
0x1800061ab  mov     [rsp+80h+var_58], rbx
0x1800061b0  mov     [rsp+80h+Reserved], rdi
0x1800061b5  lea     r9, [rbp+Block]
0x1800061b9  lea     r8, aOregistrykeyGe+7Ch; ""
0x1800061c0  lea     rcx, [rbp+Source]
0x1800061c4  call    ??$FormatArguments@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBV12@2@Z; ArgumentWriter::FormatArguments<std::wstring,std::wstring>(wchar_t const *,wchar_t const *,std::wstring &,std::wstring const &,std::wstring const &)
0x1800061c9  nop
0x1800061ca  mov     rax, [rbp+var_30]
0x1800061ce  cmp     rax, 7
0x1800061d2  jbe     short loc_180006218
0x1800061d4  mov     rcx, [rbp+Block]; Block
0x1800061d8  mov     rdx, rcx
0x1800061db  lea     rax, ds:2[rax*2]
0x1800061e3  cmp     rax, 1000h
0x1800061e9  jb      short loc_180006212
0x1800061eb  mov     rcx, [rcx-8]
0x1800061ef  sub     rdx, rcx
0x1800061f2  lea     rax, [rdx-8]
0x1800061f6  cmp     rax, 1Fh
0x1800061fa  jbe     short loc_180006212
0x1800061fc  mov     [rsp+80h+Reserved], r14; Reserved
0x180006201  xor     r9d, r9d; LineNo
0x180006204  xor     r8d, r8d; FileName
0x180006207  xor     edx, edx; FunctionName
0x180006209  xor     ecx, ecx; Expression
0x18000620b  call    cs:__imp__invoke_watson
0x180006212  call    cs:__imp_free
0x180006218  lea     r8, [rbp+Source]
0x18000621c  cmp     [rbp+var_10], 7
0x180006221  cmova   r8, [rbp+Source]; Source
0x180006226  lea     rcx, [rsi+4]; Destination
0x18000622a  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x18000622e  mov     edx, 100h; SizeInWords
0x180006233  call    cs:__imp_wcsncpy_s
0x180006239  lea     rcx, [rbp+Source]
0x18000623d  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180006242  mov     rax, rsi
0x180006245  mov     rcx, [rbp+var_8]
0x180006249  xor     rcx, rsp; StackCookie
0x18000624c  call    __security_check_cookie
0x180006251  lea     r11, [rsp+80h+var_s0]
0x180006259  mov     rbx, [r11+28h]
0x18000625d  mov     rsi, [r11+30h]
0x180006261  mov     rsp, r11
0x180006264  pop     r14
0x180006266  pop     rdi
0x180006267  pop     rbp
0x180006268  retn
```
