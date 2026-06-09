# PrinterCleanUpUtil::Activate(ushort const *)

- ea: `0x180011d8c`
- end: `0x180011e46`
- name: `?Activate@PrinterCleanUpUtil@@YAJPEBG@Z`
- size: `186`
- prototype: `__int64 __fastcall(PrinterCleanUpUtil *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task`

## callers

- `0x180011954`

## callees

- `0x180002020`
- `0x18000670c`
- `0x1800085e8`
- `0x180009a78`
- `0x18000f0d0`
- `0x18000f26c`
- `0x18000f88c`
- `0x180011d8c`
- `0x1800142e4`
- `0x1800151d0`

## string_xrefs

- `0x180011deb`: `printscan\print\shared\printercleanuptask\lib\printercleanuputil.cpp`
- `0x180011e0f`: `printscan\print\shared\printercleanuptask\lib\printercleanuputil.cpp`

## pseudocode

```c
__int64 __fastcall PrinterCleanUpUtil::Activate(PrinterCleanUpUtil *this, const unsigned __int16 *a2)
{
  __int64 v2; // rax
  PrinterCleanUpUtil *v3; // rcx
  int v4; // eax
  int v5; // eax
  const char *v6; // r9
  __int64 result; // rax
  int v8; // [rsp+20h] [rbp-38h]
  _BYTE v9[16]; // [rsp+28h] [rbp-30h] BYREF
  __int64 v10; // [rsp+38h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  try
  {
    std::wstring::wstring(v9, this);
    std::_WChar_traits<unsigned short>::length(L"dismiss");
    v2 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v9);
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v2, v10) )
    {
      v4 = PrinterCleanUpUtil::SnoozePrinterCleanUpTask(v3);
      if ( v4 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x12D,
          (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
          (const char *)(unsigned int)v4,
          v8);
      v5 = EnablePrinterCleanUpTask(0);
      if ( v5 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x12E,
          (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
          (const char *)(unsigned int)v5,
          v8);
    }
    std::wstring::_Tidy_deallocate(v9);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x133,
                           (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printercleanuputil.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x180011d8c  sub     rsp, 58h
0x180011d90  mov     rax, cs:__security_cookie
0x180011d97  xor     rax, rsp
0x180011d9a  mov     [rsp+58h+var_10], rax
0x180011d9f  mov     rdx, rcx
0x180011da2  lea     rcx, [rsp+58h+var_30]
0x180011da7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180011dac  nop
0x180011dad  lea     r8, aDismiss; "dismiss"
0x180011db4  mov     rcx, r8
0x180011db7  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x180011dbc  mov     r9, rax
0x180011dbf  lea     rcx, [rsp+58h+var_30]
0x180011dc4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180011dc9  mov     rcx, rax
0x180011dcc  mov     rdx, [rsp+58h+var_20]
0x180011dd1  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180011dd6  test    al, al
0x180011dd8  jz      short loc_180011E21
0x180011dda  call    ?SnoozePrinterCleanUpTask@PrinterCleanUpUtil@@YAJXZ; PrinterCleanUpUtil::SnoozePrinterCleanUpTask(void)
0x180011ddf  mov     rcx, [rsp+58h]; this
0x180011de4  test    eax, eax
0x180011de6  jns     short loc_180011DFC
0x180011de8  mov     r9d, eax; char *
0x180011deb  lea     r8, aPrintscanPrint_1; "printscan\\print\\shared\\printercleanu"...
0x180011df2  mov     edx, 12Dh; void *
0x180011df7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180011dfc  xor     ecx, ecx
0x180011dfe  call    EnablePrinterCleanUpTask
0x180011e03  mov     rcx, [rsp+58h]; this
0x180011e08  test    eax, eax
0x180011e0a  jns     short loc_180011E21
0x180011e0c  mov     r9d, eax; char *
0x180011e0f  lea     r8, aPrintscanPrint_1; "printscan\\print\\shared\\printercleanu"...
0x180011e16  mov     edx, 12Eh; void *
0x180011e1b  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180011e21  lea     rcx, [rsp+58h+var_30]
0x180011e26  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180011e2b  xor     eax, eax
0x180011e2d  jmp     short loc_180011E33
0x180011e2f  mov     eax, [rsp+58h+var_38]
0x180011e33  mov     rcx, [rsp+58h+var_10]
0x180011e38  xor     rcx, rsp; StackCookie
0x180011e3b  call    __security_check_cookie
0x180011e40  add     rsp, 58h
0x180011e44  retn
```
