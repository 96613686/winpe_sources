# PrintJobCleanUpUtil::Activate(ushort const *)

- ea: `0x18000aeb4`
- end: `0x18000afa2`
- name: `?Activate@PrintJobCleanUpUtil@@YAJPEBG@Z`
- size: `238`
- prototype: `__int64 __fastcall(PrintJobCleanUpUtil *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, service_task`

## callers

- `0x180015bc4`

## callees

- `0x180002020`
- `0x18000670c`
- `0x180007a04`
- `0x1800085e8`
- `0x180009a78`
- `0x18000aeb4`
- `0x18000b11c`
- `0x18000b308`
- `0x18000f0d0`
- `0x18000f26c`
- `0x18000f88c`
- `0x180010470`

## string_xrefs

- `0x18000af3e`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`
- `0x18000af6b`: `printscan\print\shared\printercleanuptask\lib\printjobcleanuputil.cpp`
- `0x18000aeee`: `delete`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall PrintJobCleanUpUtil::Activate(PrintJobCleanUpUtil *this, const unsigned __int16 *a2)
{
  __int64 v2; // rax
  PrintJobCleanUpUtil *v3; // rcx
  unsigned __int64 *v4; // r9
  int v5; // eax
  int v6; // eax
  const char *v7; // r9
  __int64 result; // rax
  struct PrintJobCleanUpUtil::StalePrintJobInfo *v9; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v10[16]; // [rsp+28h] [rbp-30h] BYREF
  __int64 v11; // [rsp+38h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  try
  {
    std::wstring::wstring(v10, this);
    v9 = (struct PrintJobCleanUpUtil::StalePrintJobInfo *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v10);
    PrinterCleanUpTelemetry::StalePrintJobCleanupToastButtonPress<unsigned short const *>(&v9);
    std::_WChar_traits<unsigned short>::length(L"delete");
    v2 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v10);
    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v2, v11) )
    {
      v9 = 0;
      LOBYTE(v3) = 1;
      v5 = PrintJobCleanUpUtil::CheckForStalePrintJobs(v3, 0, &v9, v4);
      if ( v5 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x17D,
          (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
          (const char *)(unsigned int)v5,
          (int)v9);
    }
    if ( AreAllPrintQueueEmpty() )
    {
      v6 = EnablePrintJobCleanupTask(0);
      if ( v6 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x183,
          (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
          (const char *)(unsigned int)v6,
          (int)v9);
    }
    std::wstring::_Tidy_deallocate(v10);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x188,
                           (unsigned int)"printscan\\print\\shared\\printercleanuptask\\lib\\printjobcleanuputil.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x18000aeb4  sub     rsp, 58h
0x18000aeb8  mov     rax, cs:__security_cookie
0x18000aebf  xor     rax, rsp
0x18000aec2  mov     [rsp+58h+var_10], rax
0x18000aec7  mov     rdx, rcx
0x18000aeca  lea     rcx, [rsp+58h+var_30]
0x18000aecf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18000aed4  nop
0x18000aed5  lea     rcx, [rsp+58h+var_30]
0x18000aeda  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000aedf  mov     [rsp+58h+var_38], rax; int
0x18000aee4  lea     rcx, [rsp+58h+var_38]
0x18000aee9  call    ??$StalePrintJobCleanupToastButtonPress@PEBG@PrinterCleanUpTelemetry@@SAX$$QEAPEBG@Z; PrinterCleanUpTelemetry::StalePrintJobCleanupToastButtonPress<ushort const *>(ushort const * &&)
0x18000aeee  lea     r8, aDelete; "delete"
0x18000aef5  mov     rcx, r8
0x18000aef8  call    ?length@?$_WChar_traits@G@std@@SA_KPEBG@Z; std::_WChar_traits<ushort>::length(ushort const *)
0x18000aefd  mov     r9, rax
0x18000af00  lea     rcx, [rsp+58h+var_30]
0x18000af05  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18000af0a  mov     rcx, rax
0x18000af0d  mov     rdx, [rsp+58h+var_20]
0x18000af12  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18000af17  test    al, al
0x18000af19  jz      short loc_18000AF4F
0x18000af1b  mov     [rsp+58h+var_38], 0; int
0x18000af24  lea     r8, [rsp+58h+var_38]; struct PrintJobCleanUpUtil::StalePrintJobInfo **
0x18000af29  xor     edx, edx; bool
0x18000af2b  mov     cl, 1; this
0x18000af2d  call    ?CheckForStalePrintJobs@PrintJobCleanUpUtil@@YAJ_NPEAPEAUStalePrintJobInfo@1@PEA_K@Z; PrintJobCleanUpUtil::CheckForStalePrintJobs(bool,PrintJobCleanUpUtil::StalePrintJobInfo * *,unsigned __int64 *)
0x18000af32  mov     rcx, [rsp+58h]; this
0x18000af37  test    eax, eax
0x18000af39  jns     short loc_18000AF4F
0x18000af3b  mov     r9d, eax; char *
0x18000af3e  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x18000af45  mov     edx, 17Dh; void *
0x18000af4a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000af4f  call    ?AreAllPrintQueueEmpty@@YA_NXZ; AreAllPrintQueueEmpty(void)
0x18000af54  test    al, al
0x18000af56  jz      short loc_18000AF7D
0x18000af58  xor     ecx, ecx
0x18000af5a  call    EnablePrintJobCleanupTask
0x18000af5f  mov     rcx, [rsp+58h]; this
0x18000af64  test    eax, eax
0x18000af66  jns     short loc_18000AF7D
0x18000af68  mov     r9d, eax; char *
0x18000af6b  lea     r8, aPrintscanPrint_4; "printscan\\print\\shared\\printercleanu"...
0x18000af72  mov     edx, 183h; void *
0x18000af77  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000af7d  lea     rcx, [rsp+58h+var_30]
0x18000af82  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000af87  xor     eax, eax
0x18000af89  jmp     short loc_18000AF8F
0x18000af8b  mov     eax, dword ptr [rsp+58h+var_38]
0x18000af8f  mov     rcx, [rsp+58h+var_10]
0x18000af94  xor     rcx, rsp; StackCookie
0x18000af97  call    __security_check_cookie
0x18000af9c  add     rsp, 58h
0x18000afa0  retn
```
