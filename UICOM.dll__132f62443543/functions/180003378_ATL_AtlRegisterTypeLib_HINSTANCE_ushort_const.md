# ATL::AtlRegisterTypeLib(HINSTANCE__ *,ushort const *)

- ea: `0x180003378`
- end: `0x180003551`
- name: `?AtlRegisterTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBG@Z`
- size: `473`
- prototype: `__int64 __fastcall(HINSTANCE, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180004f60`

## callees

- `0x180001898`
- `0x180002d14`
- `0x180003378`
- `0x180003558`
- `0x180005f60`
- `0x180007010`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180003422`
- `msvcrt!wcsncpy_s` at `0x180003422`
- `OLEAUT32!__imp_SysFreeString` at `0x1800034e5`
- `OLEAUT32!__imp_SysFreeString` at `0x180003506`
- `OLEAUT32!__imp_SysFreeString` at `0x1800034e5`
- `OLEAUT32!__imp_SysFreeString` at `0x180003506`
- `OLEAUT32!__imp_SysStringLen` at `0x18000340a`
- `OLEAUT32!__imp_SysStringLen` at `0x18000340a`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x1800034d8`
- `OLEAUT32!__imp_RegisterTypeLib` at `0x1800034d8`
- `USER32!CharNextW` at `0x18000346d`
- `USER32!CharNextW` at `0x18000346d`

## pseudocode

```c
__int64 __fastcall ATL::AtlRegisterTypeLib(HINSTANCE a1, const unsigned __int16 *a2)
{
  HRESULT v2; // edi
  UINT v3; // eax
  errno_t v4; // eax
  wchar_t *v5; // rdi
  wchar_t *v6; // rsi
  LPWSTR v7; // rax
  unsigned __int64 v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // rdi
  wchar_t *v11; // r8
  BSTR pbstr; // [rsp+40h] [rbp-C0h] BYREF
  ITypeLib *ptlib; // [rsp+48h] [rbp-B8h] BYREF
  BSTR bstrString[2]; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t Destination[264]; // [rsp+60h] [rbp-A0h] BYREF

  pbstr = 0;
  ptlib = 0;
  v2 = ATL::AtlLoadTypeLib(a1, a2, &pbstr, &ptlib);
  if ( v2 >= 0 )
  {
    bstrString[0] = 0;
    if ( ((int (__fastcall *)(ITypeLib *, __int64, _QWORD, _QWORD, _QWORD, BSTR *))ptlib->lpVtbl->GetDocumentation)(
           ptlib,
           0xFFFFFFFFLL,
           0,
           0,
           0,
           bstrString) >= 0
      && bstrString[0] )
    {
      v3 = SysStringLen(pbstr);
      v4 = wcsncpy_s(Destination, 0x104u, pbstr, v3);
      if ( v4 )
      {
        if ( v4 == 12 )
          ATL::AtlThrowImpl(-2147024882);
        if ( v4 == 22 || v4 == 34 )
          ATL::AtlThrowImpl(-2147024809);
        if ( v4 != 80 )
          ATL::AtlThrowImpl(-2147467259);
      }
      v5 = Destination;
      Destination[259] = 0;
      v6 = Destination;
      if ( Destination[0] )
      {
        do
        {
          v7 = CharNextW(v6);
          v8 = *v6;
          LOWORD(v8) = v8 - 47;
          if ( (unsigned __int16)v8 <= 0x2Du )
          {
            v9 = 0x200000000801LL;
            if ( _bittest64(&v9, v8) )
              v5 = v7;
          }
          v6 = v7;
        }
        while ( *v7 );
      }
      v10 = v5 - Destination;
      if ( (unsigned int)v10 < 0x104 )
      {
        if ( 2 * (unsigned __int64)(unsigned int)v10 >= 0x208 )
          _report_rangecheckfailure();
        Destination[(unsigned int)v10] = 0;
      }
      v11 = Destination;
    }
    else
    {
      v11 = 0;
    }
    v2 = RegisterTypeLib(ptlib, pbstr, v11);
    SysFreeString(bstrString[0]);
  }
  if ( ptlib )
    ((void (__fastcall *)(ITypeLib *))ptlib->lpVtbl->Release)(ptlib);
  SysFreeString(pbstr);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180003378  push    rbp
0x18000337a  push    rsi
0x18000337b  push    rdi
0x18000337c  push    r14
0x18000337e  lea     rbp, [rsp-188h]
0x180003386  sub     rsp, 288h
0x18000338d  mov     rax, cs:__security_cookie
0x180003394  xor     rax, rsp
0x180003397  mov     [rbp+1A0h+var_30], rax
0x18000339e  xor     r14d, r14d
0x1800033a1  lea     r9, [rsp+2A0h+ptlib]; struct ITypeLib **
0x1800033a6  lea     r8, [rsp+2A0h+pbstr]; unsigned __int16 **
0x1800033ab  mov     [rsp+2A0h+pbstr], r14
0x1800033b0  mov     [rsp+2A0h+ptlib], r14
0x1800033b5  call    ?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBGPEAPEAGPEAPEAUITypeLib@@@Z; ATL::AtlLoadTypeLib(HINSTANCE__ *,ushort const *,ushort * *,ITypeLib * *)
0x1800033ba  mov     edi, eax
0x1800033bc  test    eax, eax
0x1800033be  js      loc_1800034EB
0x1800033c4  mov     rcx, [rsp+2A0h+ptlib]
0x1800033c9  lea     rdx, [rsp+2A0h+bstrString]
0x1800033ce  mov     [rsp+2A0h+var_278], rdx
0x1800033d3  xor     r9d, r9d
0x1800033d6  mov     [rsp+2A0h+bstrString], r14
0x1800033db  xor     r8d, r8d
0x1800033de  or      edx, 0FFFFFFFFh
0x1800033e1  mov     [rsp+2A0h+var_280], r14
0x1800033e6  mov     rax, [rcx]
0x1800033e9  mov     rax, [rax+48h]
0x1800033ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800033f2  test    eax, eax
0x1800033f4  js      loc_1800034CB
0x1800033fa  cmp     [rsp+2A0h+bstrString], r14
0x1800033ff  jz      loc_1800034CB
0x180003405  mov     rcx, [rsp+2A0h+pbstr]; pbstr
0x18000340a  call    cs:__imp_SysStringLen
0x180003410  mov     r8, [rsp+2A0h+pbstr]; Source
0x180003415  lea     rcx, [rsp+2A0h+Destination]; Destination
0x18000341a  mov     r9d, eax; MaxCount
0x18000341d  mov     edx, 104h; SizeInWords
0x180003422  call    cs:__imp_wcsncpy_s
0x180003428  test    eax, eax
0x18000342a  jz      short loc_180003450
0x18000342c  cmp     eax, 0Ch
0x18000342f  jz      loc_180003546
0x180003435  cmp     eax, 16h
0x180003438  jz      loc_18000353B
0x18000343e  cmp     eax, 22h ; '"'
0x180003441  jz      loc_18000353B
0x180003447  cmp     eax, 50h ; 'P'
0x18000344a  jnz     loc_180003530
0x180003450  lea     rdi, [rsp+2A0h+Destination]
0x180003455  mov     [rbp+1A0h+var_3A], r14w
0x18000345d  lea     rsi, [rsp+2A0h+Destination]
0x180003462  cmp     [rsp+2A0h+Destination], r14w
0x180003468  jz      short loc_18000349C
0x18000346a  mov     rcx, rsi; lpsz
0x18000346d  call    cs:__imp_CharNextW
0x180003473  movzx   ecx, word ptr [rsi]
0x180003476  sub     cx, 2Fh ; '/'
0x18000347a  cmp     cx, 2Dh ; '-'
0x18000347e  ja      short loc_180003493
0x180003480  mov     rdx, 200000000801h
0x18000348a  bt      rdx, rcx
0x18000348e  jnb     short loc_180003493
0x180003490  mov     rdi, rax
0x180003493  mov     rsi, rax
0x180003496  cmp     [rax], r14w
0x18000349a  jnz     short loc_18000346A
0x18000349c  lea     rax, [rsp+2A0h+Destination]
0x1800034a1  sub     rdi, rax
0x1800034a4  sar     rdi, 1
0x1800034a7  cmp     edi, 104h
0x1800034ad  jnb     short loc_1800034C4
0x1800034af  mov     eax, edi
0x1800034b1  lea     rcx, [rax+rax]
0x1800034b5  cmp     rcx, 208h
0x1800034bc  jnb     short loc_18000352A
0x1800034be  mov     [rsp+rcx+2A0h+Destination], r14w
0x1800034c4  lea     r8, [rsp+2A0h+Destination]
0x1800034c9  jmp     short loc_1800034CE
0x1800034cb  xor     r8d, r8d; szHelpDir
0x1800034ce  mov     rdx, [rsp+2A0h+pbstr]; szFullPath
0x1800034d3  mov     rcx, [rsp+2A0h+ptlib]; ptlib
0x1800034d8  call    cs:__imp_RegisterTypeLib
0x1800034de  mov     rcx, [rsp+2A0h+bstrString]; bstrString
0x1800034e3  mov     edi, eax
0x1800034e5  call    cs:__imp_SysFreeString
0x1800034eb  mov     rcx, [rsp+2A0h+ptlib]
0x1800034f0  test    rcx, rcx
0x1800034f3  jz      short loc_180003501
0x1800034f5  mov     rax, [rcx]
0x1800034f8  mov     rax, [rax+10h]
0x1800034fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003501  mov     rcx, [rsp+2A0h+pbstr]; bstrString
0x180003506  call    cs:__imp_SysFreeString
0x18000350c  mov     eax, edi
0x18000350e  mov     rcx, [rbp+1A0h+var_30]
0x180003515  xor     rcx, rsp; StackCookie
0x180003518  call    __security_check_cookie
0x18000351d  add     rsp, 288h
0x180003524  pop     r14
0x180003526  pop     rdi
0x180003527  pop     rsi
0x180003528  pop     rbp
0x180003529  retn
0x18000352a  call    __report_rangecheckfailure
0x180003530  mov     ecx, 80004005h; int
0x180003535  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000353b  mov     ecx, 80070057h; int
0x180003540  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180003546  mov     ecx, 8007000Eh; int
0x18000354b  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
