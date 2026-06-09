# ATL::AtlRegisterTypeLib(HINSTANCE__ *,ushort const *)

- ea: `0x1800023d0`
- end: `0x1800025ec`
- name: `?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z`
- size: `540`
- prototype: `__int64 __fastcall(HINSTANCE, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180001510`

## callees

- `0x1800023d0`
- `0x180002c24`
- `0x180004484`
- `0x18000cdb0`
- `0x18000cf24`
- `0x18000e4a0`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180002545`
- `KERNEL32!GetProcAddress` at `0x180002545`
- `KERNEL32!GetModuleHandleW` at `0x180002530`
- `KERNEL32!GetModuleHandleW` at `0x180002530`
- `ucrtbase_clr0400!wcsncpy_s` at `0x180002483`
- `ucrtbase_clr0400!wcsncpy_s` at `0x180002483`
- `OLEAUT32!__imp_SysFreeString` at `0x180002571`
- `OLEAUT32!__imp_SysFreeString` at `0x180002595`
- `OLEAUT32!__imp_SysFreeString` at `0x180002571`
- `OLEAUT32!__imp_SysFreeString` at `0x180002595`
- `OLEAUT32!__imp_SysStringLen` at `0x18000246b`
- `OLEAUT32!__imp_SysStringLen` at `0x18000246b`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x180002550`
- `USER32!CharNextW` at `0x1800024cc`
- `USER32!CharNextW` at `0x1800024cc`

## string_xrefs

- `0x180002529`: `OLEAUT32.DLL`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ATL::AtlRegisterTypeLib(HINSTANCE a1, const unsigned __int16 *a2)
{
  int v2; // ebx
  wchar_t *v3; // rbx
  UINT v4; // eax
  errno_t v5; // eax
  __int64 v6; // rdx
  unsigned __int64 v7; // rcx
  __int64 v8; // r8
  __int64 v9; // r9
  wchar_t *v10; // rbx
  wchar_t *v11; // rdi
  LPWSTR v12; // rax
  __int64 v13; // rbx
  HMODULE ModuleHandleW; // rax
  __int64 (__fastcall *ProcAddress)(struct ITypeLib *, BSTR, wchar_t *); // rax
  BSTR pbstr; // [rsp+48h] [rbp-C0h] BYREF
  struct ITypeLib *v18; // [rsp+50h] [rbp-B8h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-B0h] BYREF
  wchar_t Destination[264]; // [rsp+68h] [rbp-A0h] BYREF

  bstrString = 0;
  v18 = 0;
  v2 = ATL::AtlLoadTypeLib(a1, a2, &bstrString, &v18);
  if ( v2 >= 0 )
  {
    v3 = 0;
    pbstr = 0;
    if ( ((int (__fastcall *)(struct ITypeLib *, __int64, _QWORD, _QWORD, _QWORD, BSTR *))v18->lpVtbl->GetDocumentation)(
           v18,
           0xFFFFFFFFLL,
           0,
           0,
           0,
           &pbstr) >= 0
      && pbstr )
    {
      v4 = SysStringLen(pbstr);
      v5 = wcsncpy_s(Destination, 0x104u, pbstr, v4);
      if ( v5 )
      {
        if ( v5 == 12 )
          ATL::AtlThrowImpl(-2147024882);
        if ( v5 == 22 || v5 == 34 )
          ATL::AtlThrowImpl(-2147024809);
        if ( v5 != 80 )
          ATL::AtlThrowImpl(-2147467259);
      }
      Destination[259] = 0;
      v10 = Destination;
      v11 = Destination;
      if ( Destination[0] )
      {
        do
        {
          v12 = CharNextW(v11);
          v7 = *v11;
          LOWORD(v7) = v7 - 47;
          if ( (unsigned __int16)v7 <= 0x2Du )
          {
            v6 = 0x200000000801LL;
            if ( _bittest64(&v6, v7) )
              v10 = v12;
          }
          v11 = v12;
        }
        while ( *v12 );
      }
      v13 = v10 - Destination;
      if ( 2 * (unsigned __int64)(unsigned int)v13 >= 0x208 )
        _report_rangecheckfailure(v7, v6, v8, v9);
      Destination[(unsigned int)v13] = 0;
      v3 = Destination;
    }
    if ( !ATL::_AtlRegisterPerUser
      || (ModuleHandleW = GetModuleHandleW(L"OLEAUT32.DLL")) == 0
      || (ProcAddress = (__int64 (__fastcall *)(struct ITypeLib *, BSTR, wchar_t *))GetProcAddress(
                                                                                      ModuleHandleW,
                                                                                      "RegisterTypeLibForUser")) == 0 )
    {
      ProcAddress = (__int64 (__fastcall *)(struct ITypeLib *, BSTR, wchar_t *))RegisterTypeLib;
    }
    v2 = ProcAddress(v18, bstrString, v3);
    SysFreeString(pbstr);
  }
  if ( v18 )
    ((void (__fastcall *)(struct ITypeLib *))v18->lpVtbl->Release)(v18);
  SysFreeString(bstrString);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x1800023d0  mov     rax, rsp
0x1800023d3  mov     [rax+10h], rbx
0x1800023d7  mov     [rax+18h], rsi
0x1800023db  mov     [rax+20h], rdi
0x1800023df  push    rbp
0x1800023e0  lea     rbp, [rax-188h]
0x1800023e7  sub     rsp, 280h
0x1800023ee  mov     rax, cs:__security_cookie
0x1800023f5  xor     rax, rsp
0x1800023f8  mov     [rbp+180h+var_10], rax
0x1800023ff  xor     esi, esi
0x180002401  mov     [rsp+280h+bstrString], rsi
0x180002406  mov     [rsp+280h+var_238], rsi
0x18000240b  lea     r9, [rsp+280h+var_238]; struct ITypeLib **
0x180002410  lea     r8, [rsp+280h+bstrString]; unsigned __int16 **
0x180002415  call    ?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBGPEAPEAGPEAPEAUITypeLib@@@Z
0x18000241a  mov     ebx, eax
0x18000241c  test    eax, eax
0x18000241e  js      loc_180002578
0x180002424  mov     ebx, esi
0x180002426  mov     [rsp+280h+pbstr], rsi
0x18000242b  mov     rcx, [rsp+280h+var_238]
0x180002430  mov     rax, [rcx]
0x180002433  lea     rdx, [rsp+280h+pbstr]
0x180002438  mov     [rsp+280h+var_258], rdx
0x18000243d  mov     [rsp+280h+var_260], rsi
0x180002442  xor     r9d, r9d
0x180002445  xor     r8d, r8d
0x180002448  or      edx, 0FFFFFFFFh
0x18000244b  mov     rax, [rax+48h]
0x18000244f  call    cs:__guard_dispatch_icall_fptr
0x180002455  test    eax, eax
0x180002457  js      loc_180002520
0x18000245d  mov     rcx, [rsp+280h+pbstr]; pbstr
0x180002462  test    rcx, rcx
0x180002465  jz      loc_180002520
0x18000246b  call    cs:__imp_SysStringLen
0x180002471  mov     r9d, eax; MaxCount
0x180002474  mov     r8, [rsp+280h+pbstr]; Source
0x180002479  mov     edx, 104h; SizeInWords
0x18000247e  lea     rcx, [rsp+280h+Destination]; Destination
0x180002483  call    cs:__imp_wcsncpy_s
0x180002489  test    eax, eax
0x18000248b  jz      short loc_1800024B1
0x18000248d  cmp     eax, 0Ch
0x180002490  jz      loc_1800025C5
0x180002496  cmp     eax, 16h
0x180002499  jz      loc_1800025E1
0x18000249f  cmp     eax, 22h ; '"'
0x1800024a2  jz      loc_1800025E1
0x1800024a8  cmp     eax, 50h ; 'P'
0x1800024ab  jnz     loc_1800025D6
0x1800024b1  mov     [rbp+180h+var_1A], si
0x1800024b8  lea     rbx, [rsp+280h+Destination]
0x1800024bd  lea     rdi, [rsp+280h+Destination]
0x1800024c2  cmp     [rsp+280h+Destination], si
0x1800024c7  jz      short loc_1800024FA
0x1800024c9  mov     rcx, rdi; lpsz
0x1800024cc  call    cs:__imp_CharNextW
0x1800024d2  movzx   ecx, word ptr [rdi]
0x1800024d5  sub     cx, 2Fh ; '/'
0x1800024d9  cmp     cx, 2Dh ; '-'
0x1800024dd  ja      short loc_1800024F2
0x1800024df  mov     rdx, 200000000801h
0x1800024e9  bt      rdx, rcx
0x1800024ed  jnb     short loc_1800024F2
0x1800024ef  mov     rbx, rax
0x1800024f2  mov     rdi, rax
0x1800024f5  cmp     [rax], si
0x1800024f8  jnz     short loc_1800024C9
0x1800024fa  lea     rax, [rsp+280h+Destination]
0x1800024ff  sub     rbx, rax
0x180002502  sar     rbx, 1
0x180002505  mov     eax, ebx
0x180002507  add     rax, rax
0x18000250a  cmp     rax, 208h
0x180002510  jnb     loc_1800025D0
0x180002516  mov     [rsp+rax+280h+Destination], si
0x18000251b  lea     rbx, [rsp+280h+Destination]
0x180002520  cmp     cs:?_AtlRegisterPerUser@ATL@@3_NA, 1
0x180002527  jnz     short loc_180002550
0x180002529  lea     rcx, ModuleName
0x180002530  call    cs:__imp_GetModuleHandleW
0x180002536  test    rax, rax
0x180002539  jz      short loc_180002550
0x18000253b  lea     rdx, ProcName
0x180002542  mov     rcx, rax; hModule
0x180002545  call    cs:__imp_GetProcAddress
0x18000254b  test    rax, rax
0x18000254e  jnz     short loc_180002557
0x180002550  mov     rax, cs:__imp_RegisterTypeLib
0x180002557  mov     r8, rbx
0x18000255a  mov     rdx, [rsp+280h+bstrString]
0x18000255f  mov     rcx, [rsp+280h+var_238]
0x180002564  call    cs:__guard_dispatch_icall_fptr
0x18000256a  mov     ebx, eax
0x18000256c  mov     rcx, [rsp+280h+pbstr]; bstrString
0x180002571  call    cs:__imp_SysFreeString
0x180002577  nop
0x180002578  mov     rcx, [rsp+280h+var_238]
0x18000257d  test    rcx, rcx
0x180002580  jz      short loc_180002590
0x180002582  mov     rax, [rcx]
0x180002585  mov     rax, [rax+10h]
0x180002589  call    cs:__guard_dispatch_icall_fptr
0x18000258f  nop
0x180002590  mov     rcx, [rsp+280h+bstrString]; bstrString
0x180002595  call    cs:__imp_SysFreeString
0x18000259b  mov     eax, ebx
0x18000259d  mov     rcx, [rbp+180h+var_10]
0x1800025a4  xor     rcx, rsp; StackCookie
0x1800025a7  call    __security_check_cookie
0x1800025ac  lea     r11, [rsp+280h+var_s0]
0x1800025b4  mov     rbx, [r11+18h]
0x1800025b8  mov     rsi, [r11+20h]
0x1800025bc  mov     rdi, [r11+28h]
0x1800025c0  mov     rsp, r11
0x1800025c3  pop     rbp
0x1800025c4  retn
0x1800025c5  mov     ecx, 8007000Eh; int
0x1800025ca  call    ?AtlThrowImpl@ATL@@YAXJ@Z
0x1800025d0  call    __report_rangecheckfailure
0x1800025d6  mov     ecx, 80004005h; int
0x1800025db  call    ?AtlThrowImpl@ATL@@YAXJ@Z
0x1800025e1  mov     ecx, 80070057h; int
0x1800025e6  call    ?AtlThrowImpl@ATL@@YAXJ@Z
```
