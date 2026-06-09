# PCLmWriter::Exception::_SetReasonWithErrorCode(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,long)

- ea: `0x180012f34`
- end: `0x180012ff8`
- name: `?_SetReasonWithErrorCode@Exception@PCLmWriter@@AEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@J@Z`
- size: `196`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180011600`

## callees

- `0x1800015f0`
- `0x180010718`
- `0x18001079c`
- `0x1800107c4`
- `0x1800112f0`
- `0x180011b4c`
- `0x180011bfc`
- `0x180012f34`
- `0x180013644`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x180012f91`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x180012f91`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x180012f9c`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x180012f9c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PCLmWriter::Exception::_SetReasonWithErrorCode(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v6; // rax
  __int64 v7; // rax
  _BYTE v9[8]; // [rsp+30h] [rbp-138h] BYREF
  _BYTE v10[232]; // [rsp+38h] [rbp-130h] BYREF
  _BYTE v11[32]; // [rsp+120h] [rbp-48h] BYREF

  std::ostringstream::ostringstream(v9);
  std::operator<<<char>(v9, a2);
  if ( a3 )
  {
    v6 = std::operator<<<std::char_traits<char>>(v9, " 0x");
    v7 = std::ostream::operator<<(v6, std::hex);
    std::ostream::operator<<(v7, a3);
  }
  std::stringbuf::str(v10, v11);
  std::string::operator=(a1 + 32, v11);
  std::string::_Tidy_deallocate(v11);
  return std::ostringstream::`vbase destructor'(v9);
}

```

## disassembly

```asm
0x180012f34  push    rbx
0x180012f36  push    rsi
0x180012f37  push    rdi
0x180012f38  sub     rsp, 150h
0x180012f3f  mov     rax, cs:__security_cookie
0x180012f46  xor     rax, rsp
0x180012f49  mov     [rsp+168h+var_28], rax
0x180012f51  mov     edi, r8d
0x180012f54  mov     rbx, rdx
0x180012f57  mov     rsi, rcx
0x180012f5a  lea     rcx, [rsp+168h+var_138]
0x180012f5f  call    ??0?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::ostringstream::ostringstream(void)
0x180012f64  nop
0x180012f65  mov     rdx, rbx
0x180012f68  lea     rcx, [rsp+168h+var_138]
0x180012f6d  call    ??$?6DU?$char_traits@D@std@@V?$allocator@D@1@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@0@@Z; std::operator<<<char>(std::ostream &,std::string const &)
0x180012f72  test    edi, edi
0x180012f74  jz      short loc_180012FA2
0x180012f76  lea     rdx, a0x; " 0x"
0x180012f7d  lea     rcx, [rsp+168h+var_138]
0x180012f82  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180012f87  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x180012f8e  mov     rcx, rax
0x180012f91  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x180012f97  mov     edx, edi
0x180012f99  mov     rcx, rax
0x180012f9c  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x180012fa2  lea     rdx, [rsp+168h+var_48]
0x180012faa  lea     rcx, [rsp+168h+var_130]
0x180012faf  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x180012fb4  lea     rcx, [rsi+20h]
0x180012fb8  lea     rdx, [rsp+168h+var_48]
0x180012fc0  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x180012fc5  lea     rcx, [rsp+168h+var_48]
0x180012fcd  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180012fd2  nop
0x180012fd3  lea     rcx, [rsp+168h+var_138]
0x180012fd8  call    ??_D?$basic_ostringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::ostringstream::`vbase destructor'(void)
0x180012fdd  mov     rcx, [rsp+168h+var_28]
0x180012fe5  xor     rcx, rsp; StackCookie
0x180012fe8  call    __security_check_cookie
0x180012fed  add     rsp, 150h
0x180012ff4  pop     rdi
0x180012ff5  pop     rsi
0x180012ff6  pop     rbx
0x180012ff7  retn
```
