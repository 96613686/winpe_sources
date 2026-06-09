# ConnectedStorage::NtmWebService::MakeHeadersWithContext(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ConnectedStorage::ContextDesc const &)

- ea: `0x180043580`
- end: `0x180043750`
- name: `?MakeHeadersWithContext@NtmWebService@ConnectedStorage@@AEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@AEBVContextDesc@2@@Z`
- size: `464`
- prototype: ``
- caller_count: `9`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x180040858`
- `0x1800416e0`
- `0x180041a50`
- `0x18004208c`
- `0x180042c1c`
- `0x180044670`
- `0x18004510c`
- `0x180045530`
- `0x180046bec`

## callees

- `0x180003c70`
- `0x18000aae4`
- `0x18000d6bc`
- `0x180010e30`
- `0x180011b94`
- `0x180011c0c`
- `0x18001c090`
- `0x180043580`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004360b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043716`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18004360b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180043716`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004363e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043690`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800436bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004363e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180043690`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800436bc`

## string_xrefs

- `0x18004373e`: `NtmWebService::MakeHeadersWithContext UserManager is not present`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
HSTRING __fastcall ConnectedStorage::NtmWebService::MakeHeadersWithContext(
        __int64 a1,
        HSTRING a2,
        const unsigned __int16 *a3,
        HSTRING *a4)
{
  __int64 v6; // rdi
  void (__fastcall *v7)(__int64, HSTRING, HSTRING *, HSTRING *, HSTRING *); // r14
  HSTRING *v8; // rax
  PCWSTR StringRawBuffer; // rax
  __int64 v10; // rdi
  __int64 v11; // r8
  PCWSTR v12; // rax
  PCWSTR v13; // rax
  HSTRING string; // [rsp+38h] [rbp-48h] BYREF
  HSTRING newString[2]; // [rsp+40h] [rbp-40h] BYREF
  _QWORD Src[2]; // [rsp+50h] [rbp-30h] BYREF

  newString[1] = a2;
  v6 = *(_QWORD *)(a1 + 32);
  if ( !v6 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)0x8000FFFFLL,
      (int)L"NtmWebService::MakeHeadersWithContext UserManager is not present",
      a3);
  v7 = *(void (__fastcall **)(__int64, HSTRING, HSTRING *, HSTRING *, HSTRING *))(*(_QWORD *)v6 + 40LL);
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(const unsigned __int16 **)a3;
  v8 = ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(&string, a3);
  v7(v6, a2, v8, a4, a4 + 2);
  WindowsDeleteString(string);
  string = 0;
  std::wstring::_Append<unsigned short>(a2);
  ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(newString, a4 + 4);
  StringRawBuffer = WindowsGetStringRawBuffer(newString[0], 0);
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( StringRawBuffer[v11] );
  std::wstring::_Append<unsigned short>(a2);
  std::wstring::_Append<unsigned short>(a2);
  std::wstring::_Append<unsigned short>(a2);
  v12 = WindowsGetStringRawBuffer(*a4, 0);
  std::wstring::wstring((__int64)Src, (__int64)v12);
  std::wstring::_Append<unsigned short>(Src);
  v13 = WindowsGetStringRawBuffer(a4[2], 0);
  do
    ++v10;
  while ( v13[v10] );
  std::wstring::_Append<unsigned short>(Src);
  std::wstring::_Append<unsigned short>(a2);
  std::wstring::_Append<unsigned short>(a2);
  std::wstring::_Tidy_deallocate(Src);
  WindowsDeleteString(newString[0]);
  return a2;
}

```

## disassembly

```asm
0x180043580  push    rbp
0x180043582  push    rbx
0x180043583  push    rsi
0x180043584  push    rdi
0x180043585  push    r12
0x180043587  push    r14
0x180043589  push    r15
0x18004358b  mov     rbp, rsp
0x18004358e  sub     rsp, 80h
0x180043595  mov     rax, cs:__security_cookie
0x18004359c  xor     rax, rsp
0x18004359f  mov     [rbp+var_10], rax
0x1800435a3  mov     rsi, r9
0x1800435a6  mov     rbx, rdx
0x1800435a9  mov     [rbp+var_38], rdx
0x1800435ad  mov     [rbp+var_50], 1
0x1800435b4  mov     rdi, [rcx+20h]
0x1800435b8  xor     r12d, r12d
0x1800435bb  test    rdi, rdi
0x1800435be  jz      loc_18004373E
0x1800435c4  mov     rax, [rdi]
0x1800435c7  mov     r14, [rax+28h]
0x1800435cb  cmp     qword ptr [r8+18h], 7
0x1800435d0  jbe     short loc_1800435D5
0x1800435d2  mov     r8, [r8]
0x1800435d5  mov     rdx, r8; sourceString
0x1800435d8  lea     rcx, [rbp+string]; string
0x1800435dc  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@PEBG@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ushort const *)
0x1800435e1  nop
0x1800435e2  lea     r15, [rsi+10h]
0x1800435e6  mov     [rsp+80h+var_60], r15
0x1800435eb  mov     r9, rsi
0x1800435ee  mov     r8, rax
0x1800435f1  mov     rdx, rbx
0x1800435f4  mov     rcx, rdi
0x1800435f7  mov     rax, r14
0x1800435fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800435ff  nop
0x180043600  mov     [rbp+var_50], 1
0x180043607  mov     rcx, [rbp+string]; string
0x18004360b  call    cs:__imp_WindowsDeleteString
0x180043611  mov     [rbp+string], r12
0x180043615  mov     r8d, 0Bh
0x18004361b  lea     rdx, aXXblPfn; "x-xbl-pfn: "
0x180043622  mov     rcx, rbx; Src
0x180043625  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004362a  lea     rdx, [rsi+20h]; struct ConnectedStorage::SimpleHStringWrapper *
0x18004362e  lea     rcx, [rbp+newString]; newString
0x180043632  call    ??0SimpleHStringWrapper@ConnectedStorage@@QEAA@AEBV01@@Z; ConnectedStorage::SimpleHStringWrapper::SimpleHStringWrapper(ConnectedStorage::SimpleHStringWrapper const &)
0x180043637  nop
0x180043638  xor     edx, edx; length
0x18004363a  mov     rcx, [rbp+newString]; string
0x18004363e  call    cs:__imp_WindowsGetStringRawBuffer
0x180043644  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180043648  mov     r8, rdi
0x18004364b  inc     r8
0x18004364e  cmp     [rax+r8*2], r12w
0x180043653  jnz     short loc_18004364B
0x180043655  mov     rdx, rax
0x180043658  mov     rcx, rbx; Src
0x18004365b  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180043660  mov     r14d, 2
0x180043666  mov     r8d, r14d
0x180043669  lea     rdx, SubStr; "\r\n"
0x180043670  mov     rcx, rbx; Src
0x180043673  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180043678  lea     r8d, [r14+0Eh]
0x18004367c  lea     rdx, aXXblLockExt; "x-xbl-lock-ext: "
0x180043683  mov     rcx, rbx; Src
0x180043686  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004368b  xor     edx, edx; length
0x18004368d  mov     rcx, [rsi]; string
0x180043690  call    cs:__imp_WindowsGetStringRawBuffer
0x180043696  mov     rdx, rax
0x180043699  lea     rcx, [rbp+Src]
0x18004369d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800436a2  nop
0x1800436a3  lea     r8d, [r14-1]
0x1800436a7  lea     rdx, asc_18009BF94; "_"
0x1800436ae  lea     rcx, [rbp+Src]; Src
0x1800436b2  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800436b7  xor     edx, edx; length
0x1800436b9  mov     rcx, [r15]; string
0x1800436bc  call    cs:__imp_WindowsGetStringRawBuffer
0x1800436c2  inc     rdi
0x1800436c5  cmp     [rax+rdi*2], r12w
0x1800436ca  jnz     short loc_1800436C2
0x1800436cc  mov     r8, rdi
0x1800436cf  mov     rdx, rax
0x1800436d2  lea     rcx, [rbp+Src]; Src
0x1800436d6  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800436db  lea     rdx, [rbp+Src]
0x1800436df  cmp     [rbp+var_18], 7
0x1800436e4  cmova   rdx, [rbp+Src]
0x1800436e9  mov     r8, [rbp+var_20]
0x1800436ed  mov     rcx, rbx; Src
0x1800436f0  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800436f5  mov     r8, r14
0x1800436f8  lea     rdx, SubStr; "\r\n"
0x1800436ff  mov     rcx, rbx; Src
0x180043702  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x180043707  nop
0x180043708  lea     rcx, [rbp+Src]
0x18004370c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180043711  nop
0x180043712  mov     rcx, [rbp+newString]; string
0x180043716  call    cs:__imp_WindowsDeleteString
0x18004371c  nop
0x18004371d  mov     rax, rbx
0x180043720  mov     rcx, [rbp+var_10]
0x180043724  xor     rcx, rsp; StackCookie
0x180043727  call    __security_check_cookie
0x18004372c  add     rsp, 80h
0x180043733  pop     r15
0x180043735  pop     r14
0x180043737  pop     r12
0x180043739  pop     rdi
0x18004373a  pop     rsi
0x18004373b  pop     rbx
0x18004373c  pop     rbp
0x18004373d  retn
0x18004373e  lea     rdx, aNtmwebserviceM; "NtmWebService::MakeHeadersWithContext U"...
0x180043745  mov     ecx, 8000FFFFh; this
0x18004374a  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
```
