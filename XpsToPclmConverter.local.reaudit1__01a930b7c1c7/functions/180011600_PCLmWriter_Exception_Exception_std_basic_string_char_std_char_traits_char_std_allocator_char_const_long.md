# PCLmWriter::Exception::Exception(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,long)

- ea: `0x180011600`
- end: `0x180011670`
- name: `??0Exception@PCLmWriter@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@J@Z`
- size: `112`
- prototype: `__int64 __fastcall(std::exception *this)`
- caller_count: `8`
- callee_count: `4`
- tags: ``

## callers

- `0x180012cc0`
- `0x18001583c`
- `0x180018334`
- `0x180018950`
- `0x180018e10`
- `0x180018fb0`
- `0x180019db0`
- `0x18001ab14`

## callees

- `0x180010618`
- `0x1800113c4`
- `0x1800116d8`
- `0x180012f34`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
std::exception *__fastcall PCLmWriter::Exception::Exception(std::exception *this, __int64 a2, unsigned int a3)
{
  const char *v6; // rax

  v6 = (const char *)std::_String_val<std::_Simple_types<char>>::_Myptr(a2);
  std::exception::exception(this, v6);
  *(_QWORD *)this = &PCLmWriter::Exception::`vftable';
  *((_DWORD *)this + 6) = a3;
  *((_WORD *)this + 14) = 256;
  std::string::string((char *)this + 32);
  PCLmWriter::Exception::_SetReasonWithErrorCode(this, a2, a3);
  return this;
}

```

## disassembly

```asm
0x180011600  mov     [rsp+arg_8], rbx
0x180011605  mov     [rsp+arg_10], rsi
0x18001160a  mov     [rsp+arg_0], rcx
0x18001160f  push    rdi
0x180011610  sub     rsp, 20h
0x180011614  mov     ebx, r8d
0x180011617  mov     rdi, rdx
0x18001161a  mov     rsi, rcx
0x18001161d  mov     rcx, rdx
0x180011620  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180011625  mov     rdx, rax; char *
0x180011628  mov     rcx, rsi; this
0x18001162b  call    ??0exception@std@@QEAA@QEBD@Z; std::exception::exception(char const * const)
0x180011630  nop
0x180011631  lea     rax, ??_7Exception@PCLmWriter@@6B@; const PCLmWriter::Exception::`vftable'
0x180011638  mov     [rsi], rax
0x18001163b  mov     [rsi+18h], ebx
0x18001163e  mov     word ptr [rsi+1Ch], 100h
0x180011644  lea     rcx, [rsi+20h]
0x180011648  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::string(void)
0x18001164d  nop
0x18001164e  mov     r8d, ebx
0x180011651  mov     rdx, rdi
0x180011654  mov     rcx, rsi
0x180011657  call    ?_SetReasonWithErrorCode@Exception@PCLmWriter@@AEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@J@Z; PCLmWriter::Exception::_SetReasonWithErrorCode(std::string const &,long)
0x18001165c  nop
0x18001165d  mov     rax, rsi
0x180011660  mov     rbx, [rsp+28h+arg_8]
0x180011665  mov     rsi, [rsp+28h+arg_10]
0x18001166a  add     rsp, 20h
0x18001166e  pop     rdi
0x18001166f  retn
```
