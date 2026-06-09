# OException::OException(et::exceptionType,uint,wchar_t const (&)[42],std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,ulong const &)

- ea: `0x180003c70`
- end: `0x180003dfa`
- name: `??$?0$0CK@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V01@K@OException@@QEAA@W4exceptionType@et@@IAEAY0CK@$$CB_WAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2AEBK@Z`
- size: `394`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800035bc`

## callees

- `0x180003c70`
- `0x1800045ec`
- `0x1800046d8`
- `0x180004fd0`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180003d97`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180003d97`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180003d9e`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180003d9e`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180003ce5`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180003dbf`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180003ce5`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x180003dbf`

## string_xrefs

- `0x180003cd9`: `Failed to create registry key "%s\%s": %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OException::OException(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        _QWORD *a5,
        __int64 a6,
        __int64 a7)
{
  _WORD *v8; // rax
  __int64 v9; // rdx
  void *v10; // rcx
  const wchar_t *v11; // r8
  __int64 v13; // [rsp+48h] [rbp-21h] BYREF
  void *Block[2]; // [rsp+50h] [rbp-19h] BYREF
  __int64 v15; // [rsp+60h] [rbp-9h]
  unsigned __int64 v16; // [rsp+68h] [rbp-1h]
  wchar_t *Source[4]; // [rsp+70h] [rbp+7h] BYREF

  *(_DWORD *)a1 = 15;
  *(_DWORD *)(a1 + 516) = a3;
  *(_DWORD *)(a1 + 904) = 808464432;
  *(_WORD *)(a1 + 776) = 0;
  wcsncpy_s((wchar_t *)(a1 + 520), 0x80u, L"Failed to create registry key \"%s\\%s\": %d", 0xFFFFFFFFFFFFFFFFuLL);
  *(_OWORD *)Block = 0;
  v15 = 0;
  v16 = 7;
  LOWORD(Block[0]) = 0;
  v13 = 87;
  v8 = (_WORD *)std::wstring::_Allocate_for_capacity<0>(Block, &v13);
  v16 = v13;
  *v8 = Block[0];
  Block[0] = v8;
  v15 = 0;
  ArgumentWriter::FormatArguments<std::wstring,std::wstring,unsigned long>((__int64)Source, v9, L"", Block, a5, a6, a7);
  if ( v16 > 7 )
  {
    v10 = Block[0];
    if ( 2 * v16 + 2 >= 0x1000 )
    {
      v10 = (void *)*((_QWORD *)Block[0] - 1);
      if ( (unsigned __int64)((char *)Block[0] - (char *)v10 - 8) > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
    }
    free(v10);
  }
  v11 = (const wchar_t *)Source;
  if ( Source[3] > (wchar_t *)7 )
    v11 = Source[0];
  wcsncpy_s((wchar_t *)(a1 + 4), 0x100u, v11, 0xFFFFFFFFFFFFFFFFuLL);
  std::wstring::_Tidy_deallocate(Source);
  return a1;
}

```

## disassembly

```asm
0x180003c70  mov     rax, rsp
0x180003c73  mov     [rax+10h], rbx
0x180003c77  mov     [rax+18h], rsi
0x180003c7b  mov     [rax+20h], rdi
0x180003c7f  push    rbp
0x180003c80  push    r14
0x180003c82  push    r15
0x180003c84  lea     rbp, [rax-47h]
0x180003c88  sub     rsp, 90h
0x180003c8f  mov     rax, cs:__security_cookie
0x180003c96  xor     rax, rsp
0x180003c99  mov     [rbp+3Fh+var_18], rax
0x180003c9d  mov     r14, rcx
0x180003ca0  mov     rsi, [rbp+3Fh+arg_20]
0x180003ca4  mov     rdi, [rbp+3Fh+arg_28]
0x180003ca8  mov     rbx, [rbp+3Fh+arg_30]
0x180003cac  xor     r15d, r15d
0x180003caf  mov     dword ptr [rcx], 0Fh
0x180003cb5  mov     [rcx+204h], r8d
0x180003cbc  mov     dword ptr [rcx+388h], 30303030h
0x180003cc6  mov     [rcx+308h], r15w
0x180003cce  add     rcx, 208h; Destination
0x180003cd5  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180003cd9  lea     r8, aFailedToCreate_0; "Failed to create registry key \"%s\\%s"...
0x180003ce0  mov     edx, 80h; SizeInWords
0x180003ce5  call    cs:__imp_wcsncpy_s
0x180003ceb  xorps   xmm0, xmm0
0x180003cee  movups  xmmword ptr [rbp+3Fh+Block], xmm0
0x180003cf2  mov     [rbp+3Fh+var_48], r15
0x180003cf6  mov     [rbp+3Fh+var_40], 7
0x180003cfe  mov     word ptr [rbp+3Fh+Block], r15w
0x180003d03  mov     [rbp+3Fh+var_60], 57h ; 'W'
0x180003d0b  lea     rdx, [rbp+3Fh+var_60]
0x180003d0f  lea     rcx, [rbp+3Fh+Block]
0x180003d13  call    ??$_Allocate_for_capacity@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@CAPEA_WAEAV?$allocator@_W@1@AEA_K@Z; std::wstring::_Allocate_for_capacity<0>(std::allocator<wchar_t> &,unsigned __int64 &)
0x180003d18  mov     rcx, rax
0x180003d1b  mov     rax, [rbp+3Fh+var_60]
0x180003d1f  mov     [rbp+3Fh+var_40], rax
0x180003d23  movzx   eax, word ptr [rbp+3Fh+Block]
0x180003d27  mov     [rcx], ax
0x180003d2a  mov     [rbp+3Fh+Block], rcx
0x180003d2e  mov     [rbp+3Fh+var_48], r15
0x180003d32  mov     [rsp+0A0h+var_70], rbx
0x180003d37  mov     [rsp+0A0h+var_78], rdi
0x180003d3c  mov     [rsp+0A0h+Reserved], rsi
0x180003d41  lea     r9, [rbp+3Fh+Block]
0x180003d45  lea     r8, aFailedToCreate_0+52h; ""
0x180003d4c  lea     rcx, [rbp+3Fh+Source]
0x180003d50  call    ??$FormatArguments@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V12@K@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV12@AEBV12@2AEBK@Z; ArgumentWriter::FormatArguments<std::wstring,std::wstring,ulong>(wchar_t const *,wchar_t const *,std::wstring &,std::wstring const &,std::wstring const &,ulong const &)
0x180003d55  nop
0x180003d56  mov     rax, [rbp+3Fh+var_40]
0x180003d5a  cmp     rax, 7
0x180003d5e  jbe     short loc_180003DA4
0x180003d60  mov     rcx, [rbp+3Fh+Block]; Block
0x180003d64  mov     rdx, rcx
0x180003d67  lea     rax, ds:2[rax*2]
0x180003d6f  cmp     rax, 1000h
0x180003d75  jb      short loc_180003D9E
0x180003d77  mov     rcx, [rcx-8]
0x180003d7b  sub     rdx, rcx
0x180003d7e  lea     rax, [rdx-8]
0x180003d82  cmp     rax, 1Fh
0x180003d86  jbe     short loc_180003D9E
0x180003d88  mov     [rsp+0A0h+Reserved], r15; Reserved
0x180003d8d  xor     r9d, r9d; LineNo
0x180003d90  xor     r8d, r8d; FileName
0x180003d93  xor     edx, edx; FunctionName
0x180003d95  xor     ecx, ecx; Expression
0x180003d97  call    cs:__imp__invoke_watson
0x180003d9e  call    cs:__imp_free
0x180003da4  lea     r8, [rbp+3Fh+Source]
0x180003da8  cmp     [rbp+3Fh+var_20], 7
0x180003dad  cmova   r8, [rbp+3Fh+Source]; Source
0x180003db2  lea     rcx, [r14+4]; Destination
0x180003db6  or      r9, 0FFFFFFFFFFFFFFFFh; MaxCount
0x180003dba  mov     edx, 100h; SizeInWords
0x180003dbf  call    cs:__imp_wcsncpy_s
0x180003dc5  lea     rcx, [rbp+3Fh+Source]
0x180003dc9  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180003dce  mov     rax, r14
0x180003dd1  mov     rcx, [rbp+3Fh+var_18]
0x180003dd5  xor     rcx, rsp; StackCookie
0x180003dd8  call    __security_check_cookie
0x180003ddd  lea     r11, [rsp+0A0h+var_10]
0x180003de5  mov     rbx, [r11+28h]
0x180003de9  mov     rsi, [r11+30h]
0x180003ded  mov     rdi, [r11+38h]
0x180003df1  mov     rsp, r11
0x180003df4  pop     r15
0x180003df6  pop     r14
0x180003df8  pop     rbp
0x180003df9  retn
```
