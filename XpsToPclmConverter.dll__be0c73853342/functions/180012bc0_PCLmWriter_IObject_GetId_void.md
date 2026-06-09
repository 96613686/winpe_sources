# PCLmWriter::IObject::GetId(void)

- ea: `0x180012bc0`
- end: `0x180012c33`
- name: `?GetId@IObject@PCLmWriter@@UEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800107c4`
- `0x180011458`
- `0x180011c28`
- `0x180013644`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180012be6`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180012c01`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180012be6`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z` at `0x180012c01`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PCLmWriter::IObject::GetId(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // rax
  _BYTE v7[16]; // [rsp+30h] [rbp-108h] BYREF
  _BYTE v8[8]; // [rsp+40h] [rbp-F8h] BYREF
  _BYTE v9[240]; // [rsp+48h] [rbp-F0h] BYREF

  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v7);
  v4 = std::ostream::operator<<(v8, *(unsigned int *)(a1 + 8));
  v5 = std::operator<<<std::char_traits<char>>(v4, ":");
  std::ostream::operator<<(v5, *(unsigned int *)(a1 + 12));
  std::stringbuf::str(v9, a2);
  std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbase destructor'(v7);
  return a2;
}

```

## disassembly

```asm
0x180012bc0  mov     [rsp+arg_0], rbx
0x180012bc5  push    rdi
0x180012bc6  sub     rsp, 130h
0x180012bcd  mov     rdi, rdx
0x180012bd0  mov     rbx, rcx
0x180012bd3  lea     rcx, [rsp+138h+var_108]
0x180012bd8  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x180012bdd  nop
0x180012bde  mov     edx, [rbx+8]
0x180012be1  lea     rcx, [rsp+138h+var_F8]
0x180012be6  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z; std::ostream::operator<<(uint)
0x180012bec  mov     rcx, rax
0x180012bef  lea     rdx, asc_180025540; ":"
0x180012bf6  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180012bfb  mov     edx, [rbx+0Ch]
0x180012bfe  mov     rcx, rax
0x180012c01  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@I@Z; std::ostream::operator<<(uint)
0x180012c07  mov     rdx, rdi
0x180012c0a  lea     rcx, [rsp+138h+var_F0]
0x180012c0f  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x180012c14  nop
0x180012c15  lea     rcx, [rsp+138h+var_108]
0x180012c1a  call    ??_D?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAXXZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::`vbase destructor'(void)
0x180012c1f  mov     rax, rdi
0x180012c22  mov     rbx, [rsp+138h+arg_0]
0x180012c2a  add     rsp, 130h
0x180012c31  pop     rdi
0x180012c32  retn
```
