# Sharp::Util::Xml::CNodeCollection::FindFirst(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140013918`
- end: `0x1400139a1`
- name: `?FindFirst@CNodeCollection@Xml@Util@Sharp@@QEBAPEBVCNode@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `137`
- prototype: `_QWORD *__fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140012b94`
- `0x140012f20`

## callees

- `0x140008368`
- `0x14000918c`
- `0x140012a74`
- `0x140013918`
- `0x140013b10`

## pseudocode

```c
_QWORD *__fastcall Sharp::Util::Xml::CNodeCollection::FindFirst(__int64 a1, __int64 a2)
{
  _QWORD *v4; // rbp
  _QWORD *v5; // rbx
  _QWORD *v6; // rsi
  __int64 Name; // rax
  char v8; // di
  _QWORD v10[4]; // [rsp+20h] [rbp-68h] BYREF

  v4 = 0;
  v5 = *(_QWORD **)(a1 + 8);
  while ( 1 )
  {
    v5 = (_QWORD *)*v5;
    if ( v5 == *(_QWORD **)(a1 + 8) )
      break;
    v6 = v5 + 2;
    Name = Sharp::Util::Xml::CNode::GetName(v5 + 2, v10);
    v8 = std::operator==<unsigned short>(Name, a2);
    std::wstring::_Tidy(v10, 1, 0);
    if ( !v8 )
      v6 = v4;
    v4 = v6;
  }
  return v4;
}

```

## disassembly

```asm
0x140013918  push    rbx
0x14001391a  push    rbp
0x14001391b  push    rsi
0x14001391c  push    rdi
0x14001391d  push    r14
0x14001391f  push    r15
0x140013921  sub     rsp, 58h
0x140013925  mov     rax, cs:__security_cookie
0x14001392c  xor     rax, rsp
0x14001392f  mov     [rsp+88h+var_48], rax
0x140013934  mov     r15, rdx
0x140013937  mov     r14, rcx
0x14001393a  xor     ebp, ebp
0x14001393c  mov     rbx, [rcx+8]
0x140013940  mov     rbx, [rbx]
0x140013943  cmp     rbx, [r14+8]
0x140013947  jz      short loc_140013984
0x140013949  lea     rsi, [rbx+10h]
0x14001394d  lea     rdx, [rsp+88h+var_68]
0x140013952  mov     rcx, rsi
0x140013955  call    ?GetName@CNode@Xml@Util@Sharp@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Sharp::Util::Xml::CNode::GetName(void)
0x14001395a  nop
0x14001395b  mov     rdx, r15
0x14001395e  mov     rcx, rax
0x140013961  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator==<ushort>(std::wstring const &,std::wstring const &)
0x140013966  mov     dil, al
0x140013969  xor     r8d, r8d
0x14001396c  mov     dl, 1
0x14001396e  lea     rcx, [rsp+88h+var_68]
0x140013973  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x140013978  test    dil, dil
0x14001397b  cmovz   rsi, rbp
0x14001397f  mov     rbp, rsi
0x140013982  jmp     short loc_140013940
0x140013984  mov     rax, rbp
0x140013987  mov     rcx, [rsp+88h+var_48]
0x14001398c  xor     rcx, rsp; StackCookie
0x14001398f  call    __security_check_cookie
0x140013994  add     rsp, 58h
0x140013998  pop     r15
0x14001399a  pop     r14
0x14001399c  pop     rdi
0x14001399d  pop     rsi
0x14001399e  pop     rbp
0x14001399f  pop     rbx
0x1400139a0  retn
```
