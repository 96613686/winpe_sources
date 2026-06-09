# PCLmWriter::PDFDocumentWriter::StartDocW(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &)

- ea: `0x1800158e4`
- end: `0x1800159c9`
- name: `?StartDocW@PDFDocumentWriter@PCLmWriter@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000f924`

## callees

- `0x1800015f0`
- `0x18000efa8`
- `0x18000f41c`
- `0x180010618`
- `0x18001583c`
- `0x18001f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PCLmWriter::PDFDocumentWriter::StartDocW(__int64 a1, __int64 a2)
{
  __int64 v4; // rax
  __int64 v5; // r10
  __int64 v7; // [rsp+20h] [rbp-30h] BYREF
  _QWORD v8[2]; // [rsp+28h] [rbp-28h] BYREF
  char v9[16]; // [rsp+38h] [rbp-18h] BYREF

  std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>(v8);
  PCLmWriter::PDFDocumentWriter::GenerateObjectIdentifier(a1, &v7);
  *(_QWORD *)(a1 + 84) = v7;
  v7 = *(_QWORD *)PCLmWriter::PDFDocumentWriter::GenerateObjectIdentifier(a1, &v7);
  *(_QWORD *)(a1 + 76) = v7;
  strcpy(v9, "%PDF-1.7\n");
  (*(void (__fastcall **)(_QWORD, char *, __int64))(**(_QWORD **)(a1 + 16) + 24LL))(*(_QWORD *)(a1 + 16), v9, 9);
  v4 = std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
  (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v5 + 24LL))(v5, v4, *(unsigned int *)(a2 + 16));
  return std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(
           v8,
           (__int64)v8);
}

```

## disassembly

```asm
0x1800158e4  mov     [rsp-8+arg_10], rbx
0x1800158e9  mov     [rsp-8+arg_18], rdi
0x1800158ee  push    rbp
0x1800158ef  mov     rbp, rsp
0x1800158f2  sub     rsp, 50h
0x1800158f6  mov     rax, cs:__security_cookie
0x1800158fd  xor     rax, rsp
0x180015900  mov     [rbp+var_8], rax
0x180015904  mov     rdi, rdx
0x180015907  mov     rbx, rcx
0x18001590a  lea     rcx, [rbp+var_28]
0x18001590e  call    ??0?$map@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@U?$less@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@2@@std@@QEAA@XZ; std::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>>::map<std::string const,std::shared_ptr<PCLmWriter::IObject const>,std::less<std::string const>,std::allocator<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>(void)
0x180015913  nop
0x180015914  lea     rdx, [rbp+var_30]
0x180015918  mov     rcx, rbx
0x18001591b  call    ?GenerateObjectIdentifier@PDFDocumentWriter@PCLmWriter@@QEAA?AU?$pair@II@std@@XZ; PCLmWriter::PDFDocumentWriter::GenerateObjectIdentifier(void)
0x180015920  mov     eax, dword ptr [rbp+var_30]
0x180015923  mov     [rbx+54h], eax
0x180015926  mov     eax, dword ptr [rbp+var_30+4]
0x180015929  mov     [rbx+58h], eax
0x18001592c  lea     rdx, [rbp+var_30]
0x180015930  mov     rcx, rbx
0x180015933  call    ?GenerateObjectIdentifier@PDFDocumentWriter@PCLmWriter@@QEAA?AU?$pair@II@std@@XZ; PCLmWriter::PDFDocumentWriter::GenerateObjectIdentifier(void)
0x180015938  mov     rax, [rax]
0x18001593b  mov     [rbp+var_30], rax
0x18001593f  mov     [rbx+4Ch], eax
0x180015942  mov     eax, dword ptr [rbp+var_30+4]
0x180015945  mov     [rbx+50h], eax
0x180015948  movsd   xmm0, qword ptr cs:aPdf17; "%PDF-1.7\n"
0x180015950  movsd   qword ptr [rbp+var_18], xmm0
0x180015955  movzx   eax, word ptr cs:aPdf17+8; "\n"
0x18001595c  mov     word ptr [rbp+var_18+8], ax
0x180015960  mov     rcx, [rbx+10h]
0x180015964  mov     rax, [rcx]
0x180015967  mov     r8d, 9
0x18001596d  lea     rdx, [rbp+var_18]
0x180015971  mov     rax, [rax+18h]
0x180015975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001597a  mov     r10, [rbx+10h]
0x18001597e  mov     rcx, rdi
0x180015981  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180015986  mov     rdx, [r10]
0x180015989  mov     r9, [rdx+18h]
0x18001598d  mov     r8d, [rdi+10h]
0x180015991  mov     rdx, rax
0x180015994  mov     rcx, r10
0x180015997  mov     rax, r9
0x18001599a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001599f  nop
0x1800159a0  lea     rdx, [rbp+var_28]
0x1800159a4  lea     rcx, [rbp+var_28]
0x1800159a8  call    ??$_Erase_head@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V?$shared_ptr@$$CBVIObject@PCLmWriter@@@2@@std@@PEAX@std@@@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>>>::_Erase_head<std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>>>(std::allocator<std::_Tree_node<std::pair<std::string const,std::shared_ptr<PCLmWriter::IObject const>>,void *>> &)
0x1800159ad  mov     rcx, [rbp+var_8]
0x1800159b1  xor     rcx, rsp; StackCookie
0x1800159b4  call    __security_check_cookie
0x1800159b9  mov     rbx, [rsp+50h+arg_10]
0x1800159be  mov     rdi, [rsp+50h+arg_18]
0x1800159c3  add     rsp, 50h
0x1800159c7  pop     rbp
0x1800159c8  retn
```
