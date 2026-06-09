# McpService::SearchCloudPrinters(_McpPrinterSearchParams *,_McpPrinterSearchResult * *)

- ea: `0x180026f10`
- end: `0x18002722d`
- name: `?SearchCloudPrinters@McpService@@UEAAJPEAU_McpPrinterSearchParams@@PEAPEAU_McpPrinterSearchResult@@@Z`
- size: `797`
- prototype: `__int64 __fastcall(McpService *__hidden this, struct _McpPrinterSearchParams *, struct _McpPrinterSearchResult **)`
- caller_count: `0`
- callee_count: `16`
- tags: `service_task`

## callees

- `0x180003a60`
- `0x180004590`
- `0x180006b70`
- `0x18000c4cc`
- `0x18000e164`
- `0x18000e208`
- `0x18000e2dc`
- `0x18001ddb4`
- `0x18001dee0`
- `0x18001df58`
- `0x18001e4c4`
- `0x180025400`
- `0x1800256ac`
- `0x1800268a0`
- `0x180026f10`
- `0x180027234`

## string_xrefs

- `0x180026f50`: `onecoreuap\printscan\print\mcp\managementsvc\lib\mcpservice.cpp`

## pseudocode

```c
__int64 __fastcall McpService::SearchCloudPrinters(
        McpService *this,
        struct _McpPrinterSearchParams *a2,
        struct _McpPrinterSearchResult **a3)
{
  __int64 result; // rax
  __int64 v7; // rdx
  _WORD *v8; // rax
  _WORD *v9; // rax
  _WORD *v10; // rax
  _WORD *v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  unsigned int v14; // ebx
  __int64 v15; // rax
  __int64 v16; // rax
  unsigned int v17; // ebx
  const char *v18; // r9
  double v19; // [rsp+20h] [rbp-78h] BYREF
  double X; // [rsp+28h] [rbp-70h] BYREF
  double v21; // [rsp+30h] [rbp-68h] BYREF
  _BYTE v22[32]; // [rsp+38h] [rbp-60h] BYREF
  _BYTE v23[32]; // [rsp+58h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  if ( a2 )
  {
    std::wstring::wstring(v22);
    try
    {
      v8 = *(_WORD **)(v7 + 16);
      if ( v8 && *v8 )
      {
        std::wstring::append(v22, L"&location_tree_type=");
        std::wstring::append(v22, *((_QWORD *)a2 + 2));
      }
      if ( *((_DWORD *)a2 + 10) )
      {
        std::wstring::append(v22, L"&offset=");
        std::_Integral_to_string<unsigned short,unsigned long>(v23, *((unsigned int *)a2 + 10));
        std::wstring::append(v22, v23);
        std::wstring::_Tidy_deallocate(v23);
      }
      if ( *((_DWORD *)a2 + 11) )
      {
        std::wstring::append(v22, L"&limit=");
        std::_Integral_to_string<unsigned short,unsigned long>(v23, *((unsigned int *)a2 + 11));
        std::wstring::append(v22, v23);
        std::wstring::_Tidy_deallocate(v23);
      }
      v9 = (_WORD *)*((_QWORD *)a2 + 1);
      if ( v9 && *v9 )
      {
        std::wstring::append(v22, L"&");
        std::wstring::append(v22, *((_QWORD *)a2 + 1));
      }
      v10 = (_WORD *)*((_QWORD *)a2 + 3);
      if ( v10 && *v10 )
      {
        std::wstring::append(v22, L"&keywords=");
        std::wstring::append(v22, *((_QWORD *)a2 + 3));
      }
      v11 = (_WORD *)*((_QWORD *)a2 + 4);
      if ( v11 && *v11 )
      {
        std::wstring::append(v22, L"&sort=");
        std::wstring::append(v22, *((_QWORD *)a2 + 4));
      }
      if ( *(_DWORD *)a2 )
      {
        v19 = 0.0;
        v21 = 0.0;
        X = 0.0;
        if ( (int)McpService::FindLatLongAlt(this, &v19, &v21, &X) >= 0 )
        {
          std::wstring::append(v22, L"&latitude=");
          v12 = std::to_wstring(v23);
          std::wstring::append(v22, v12);
          std::wstring::_Tidy_deallocate(v23);
          std::wstring::append(v22, L"&longitude=");
          v13 = std::to_wstring(v23);
          std::wstring::append(v22, v13);
          std::wstring::_Tidy_deallocate(v23);
          v14 = (int)floor(X);
          if ( v14 )
          {
            std::wstring::append(v22, L"&altitude=");
            v15 = std::to_wstring(v23, v14);
            std::wstring::append(v22, v15);
            std::wstring::_Tidy_deallocate(v23);
          }
          std::wstring::append(v22, L"&mostrelevant=true");
        }
      }
      if ( !std::wstring::find(v22, 38, 0) )
      {
        v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v22);
        std::wstring::erase(v22, &X, v16);
      }
      v17 = McpService::SearchCloudPrinters(this, v22, a3);
      std::wstring::_Tidy_deallocate(v22);
      result = v17;
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x14D,
                             (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
                             v18);
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x101,
      (unsigned int)"onecoreuap\\printscan\\print\\mcp\\managementsvc\\lib\\mcpservice.cpp",
      (const char *)0x80070057LL,
      SLODWORD(v19));
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x180026f10  mov     [rsp+arg_18], rbx
0x180026f15  push    rsi
0x180026f16  push    rdi
0x180026f17  push    r14
0x180026f19  sub     rsp, 80h
0x180026f20  mov     rax, cs:__security_cookie
0x180026f27  xor     rax, rsp
0x180026f2a  mov     [rsp+98h+var_20], rax
0x180026f2f  mov     rsi, r8
0x180026f32  mov     rbx, rdx
0x180026f35  mov     rdi, rcx
0x180026f38  xor     r14d, r14d
0x180026f3b  test    rdx, rdx
0x180026f3e  jnz     short loc_180026F68
0x180026f40  mov     rcx, [rsp+98h]; this
0x180026f48  mov     ebx, 80070057h
0x180026f4d  mov     r9d, ebx; char *
0x180026f50  lea     r8, aOnecoreuapPrin_7; "onecoreuap\\printscan\\print\\mcp\\mana"...
0x180026f57  mov     edx, 101h; void *
0x180026f5c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026f61  mov     eax, ebx
0x180026f63  jmp     loc_18002720B
0x180026f68  lea     rcx, [rsp+98h+var_60]
0x180026f6d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180026f72  nop
0x180026f73  mov     rax, [rdx+10h]
0x180026f77  test    rax, rax
0x180026f7a  jz      short loc_180026FA1
0x180026f7c  cmp     [rax], r14w
0x180026f80  jz      short loc_180026FA1
0x180026f82  lea     rdx, aLocationTreeTy; "&location_tree_type="
0x180026f89  lea     rcx, [rsp+98h+var_60]
0x180026f8e  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180026f93  mov     rdx, [rbx+10h]
0x180026f97  lea     rcx, [rsp+98h+var_60]
0x180026f9c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180026fa1  cmp     [rbx+28h], r14d
0x180026fa5  jz      short loc_180026FE0
0x180026fa7  lea     rdx, aOffset; "&offset="
0x180026fae  lea     rcx, [rsp+98h+var_60]
0x180026fb3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180026fb8  mov     edx, [rbx+28h]
0x180026fbb  lea     rcx, [rsp+98h+var_40]
0x180026fc0  call    ??$_Integral_to_string@GK@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@K@Z; std::_Integral_to_string<ushort,ulong>(ulong)
0x180026fc5  nop
0x180026fc6  lea     rdx, [rsp+98h+var_40]
0x180026fcb  lea     rcx, [rsp+98h+var_60]
0x180026fd0  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180026fd5  nop
0x180026fd6  lea     rcx, [rsp+98h+var_40]
0x180026fdb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180026fe0  cmp     [rbx+2Ch], r14d
0x180026fe4  jz      short loc_18002701F
0x180026fe6  lea     rdx, aLimit; "&limit="
0x180026fed  lea     rcx, [rsp+98h+var_60]
0x180026ff2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180026ff7  mov     edx, [rbx+2Ch]
0x180026ffa  lea     rcx, [rsp+98h+var_40]
0x180026fff  call    ??$_Integral_to_string@GK@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@K@Z; std::_Integral_to_string<ushort,ulong>(ulong)
0x180027004  nop
0x180027005  lea     rdx, [rsp+98h+var_40]
0x18002700a  lea     rcx, [rsp+98h+var_60]
0x18002700f  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180027014  nop
0x180027015  lea     rcx, [rsp+98h+var_40]
0x18002701a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002701f  mov     rax, [rbx+8]
0x180027023  test    rax, rax
0x180027026  jz      short loc_18002704D
0x180027028  cmp     [rax], r14w
0x18002702c  jz      short loc_18002704D
0x18002702e  lea     rdx, asc_180030D38; "&"
0x180027035  lea     rcx, [rsp+98h+var_60]
0x18002703a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002703f  mov     rdx, [rbx+8]
0x180027043  lea     rcx, [rsp+98h+var_60]
0x180027048  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002704d  mov     rax, [rbx+18h]
0x180027051  test    rax, rax
0x180027054  jz      short loc_18002707B
0x180027056  cmp     [rax], r14w
0x18002705a  jz      short loc_18002707B
0x18002705c  lea     rdx, aKeywords; "&keywords="
0x180027063  lea     rcx, [rsp+98h+var_60]
0x180027068  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002706d  mov     rdx, [rbx+18h]
0x180027071  lea     rcx, [rsp+98h+var_60]
0x180027076  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002707b  mov     rax, [rbx+20h]
0x18002707f  test    rax, rax
0x180027082  jz      short loc_1800270A9
0x180027084  cmp     [rax], r14w
0x180027088  jz      short loc_1800270A9
0x18002708a  lea     rdx, aSort; "&sort="
0x180027091  lea     rcx, [rsp+98h+var_60]
0x180027096  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002709b  mov     rdx, [rbx+20h]
0x18002709f  lea     rcx, [rsp+98h+var_60]
0x1800270a4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800270a9  cmp     [rbx], r14d
0x1800270ac  jz      loc_1800271B4
0x1800270b2  xorps   xmm0, xmm0
0x1800270b5  movsd   [rsp+98h+var_78], xmm0
0x1800270bb  movsd   [rsp+98h+var_68], xmm0
0x1800270c1  movsd   [rsp+98h+X], xmm0
0x1800270c7  lea     r9, [rsp+98h+X]; double *
0x1800270cc  lea     r8, [rsp+98h+var_68]; double *
0x1800270d1  lea     rdx, [rsp+98h+var_78]; double *
0x1800270d6  mov     rcx, rdi; this
0x1800270d9  call    ?FindLatLongAlt@McpService@@AEAAJAEAN00@Z; McpService::FindLatLongAlt(double &,double &,double &)
0x1800270de  test    eax, eax
0x1800270e0  js      loc_1800271B4
0x1800270e6  lea     rdx, aLatitude; "&latitude="
0x1800270ed  lea     rcx, [rsp+98h+var_60]
0x1800270f2  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800270f7  movsd   xmm1, [rsp+98h+var_78]
0x1800270fd  lea     rcx, [rsp+98h+var_40]
0x180027102  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@N@Z; std::to_wstring(double)
0x180027107  nop
0x180027108  mov     rdx, rax
0x18002710b  lea     rcx, [rsp+98h+var_60]
0x180027110  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180027115  nop
0x180027116  lea     rcx, [rsp+98h+var_40]
0x18002711b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027120  lea     rdx, aLongitude; "&longitude="
0x180027127  lea     rcx, [rsp+98h+var_60]
0x18002712c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180027131  movsd   xmm1, [rsp+98h+var_68]
0x180027137  lea     rcx, [rsp+98h+var_40]
0x18002713c  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@N@Z; std::to_wstring(double)
0x180027141  nop
0x180027142  mov     rdx, rax
0x180027145  lea     rcx, [rsp+98h+var_60]
0x18002714a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x18002714f  nop
0x180027150  lea     rcx, [rsp+98h+var_40]
0x180027155  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002715a  movsd   xmm0, [rsp+98h+X]; X
0x180027160  call    floor
0x180027165  cvttsd2si ebx, xmm0
0x180027169  test    ebx, ebx
0x18002716b  jz      short loc_1800271A3
0x18002716d  lea     rdx, aAltitude; "&altitude="
0x180027174  lea     rcx, [rsp+98h+var_60]
0x180027179  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x18002717e  mov     edx, ebx
0x180027180  lea     rcx, [rsp+98h+var_40]
0x180027185  call    ?to_wstring@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@H@Z; std::to_wstring(int)
0x18002718a  nop
0x18002718b  mov     rdx, rax
0x18002718e  lea     rcx, [rsp+98h+var_60]
0x180027193  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@@Z; std::wstring::append(std::wstring const &)
0x180027198  nop
0x180027199  lea     rcx, [rsp+98h+var_40]
0x18002719e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800271a3  lea     rdx, aMostrelevantTr; "&mostrelevant=true"
0x1800271aa  lea     rcx, [rsp+98h+var_60]
0x1800271af  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800271b4  mov     edx, 26h ; '&'
0x1800271b9  xor     r8d, r8d
0x1800271bc  lea     rcx, [rsp+98h+var_60]
0x1800271c1  call    ?find@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBA_KG_K@Z; std::wstring::find(ushort,unsigned __int64)
0x1800271c6  test    rax, rax
0x1800271c9  jnz     short loc_1800271E7
0x1800271cb  lea     rcx, [rsp+98h+var_60]
0x1800271d0  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800271d5  mov     r8, rax
0x1800271d8  lea     rdx, [rsp+98h+X]
0x1800271dd  lea     rcx, [rsp+98h+var_60]
0x1800271e2  call    ?erase@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@V?$_String_const_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@@Z; std::wstring::erase(std::_String_const_iterator<std::_String_val<std::_Simple_types<ushort>>>)
0x1800271e7  mov     r8, rsi
0x1800271ea  lea     rdx, [rsp+98h+var_60]
0x1800271ef  mov     rcx, rdi
0x1800271f2  call    ?SearchCloudPrinters@McpService@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAU_McpPrinterSearchResult@@@Z; McpService::SearchCloudPrinters(std::wstring const &,_McpPrinterSearchResult * *)
0x1800271f7  mov     ebx, eax
0x1800271f9  lea     rcx, [rsp+98h+var_60]
0x1800271fe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180027203  mov     eax, ebx
0x180027205  jmp     short loc_18002720B
0x180027207  mov     eax, dword ptr [rsp+98h+var_78]
0x18002720b  mov     rcx, [rsp+98h+var_20]
0x180027210  xor     rcx, rsp; StackCookie
0x180027213  call    __security_check_cookie
0x180027218  mov     rbx, [rsp+98h+arg_18]
0x180027220  add     rsp, 80h
0x180027227  pop     r14
0x180027229  pop     rdi
0x18002722a  pop     rsi
0x18002722b  retn
```
