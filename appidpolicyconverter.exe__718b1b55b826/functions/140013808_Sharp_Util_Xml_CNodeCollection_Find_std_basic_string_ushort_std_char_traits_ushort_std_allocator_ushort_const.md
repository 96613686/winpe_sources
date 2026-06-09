# Sharp::Util::Xml::CNodeCollection::Find(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x140013808`
- end: `0x140013911`
- name: `?Find@CNodeCollection@Xml@Util@Sharp@@QEBA?AV1234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `265`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x140012c90`

## callees

- `0x1400070e4`
- `0x140008368`
- `0x14000918c`
- `0x140011974`
- `0x140012a74`
- `0x140013524`
- `0x1400137d8`
- `0x140013808`
- `0x140013b10`

## pseudocode

```c
_QWORD *__fastcall Sharp::Util::Xml::CNodeCollection::Find(__int64 a1, _QWORD *a2, __int64 a3)
{
  _QWORD *v6; // rbx
  __int64 Name; // rax
  char v8; // di
  Sharp::Util::Xml::CNode *v9; // rax
  _BYTE v11[16]; // [rsp+38h] [rbp-60h] BYREF
  _QWORD v12[4]; // [rsp+48h] [rbp-50h] BYREF

  *a2 = &Sharp::Util::Xml::CNodeCollection::`vftable';
  std::list<Sharp::Util::Xml::CNode>::list<Sharp::Util::Xml::CNode>(a2 + 1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_aa5cb3998772301bcbc4f4136f5a9bc8_Traceguids);
  v6 = *(_QWORD **)(a1 + 8);
  while ( 1 )
  {
    v6 = (_QWORD *)*v6;
    if ( v6 == *(_QWORD **)(a1 + 8) )
      break;
    Name = Sharp::Util::Xml::CNode::GetName(v6 + 2, v12);
    v8 = std::operator==<unsigned short>(Name, a3);
    std::wstring::_Tidy(v12, 1, 0);
    if ( v8 )
    {
      v9 = Sharp::Util::Xml::CNode::CNode(
             (Sharp::Util::Xml::CNode *)v11,
             (const struct Sharp::Util::Xml::CNode *)(v6 + 2));
      Sharp::Util::Xml::CNodeCollection::Add((__int64)a2, v9);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x140013808  mov     [rsp+arg_0], rbx
0x14001380d  push    rbp
0x14001380e  push    rsi
0x14001380f  push    rdi
0x140013810  push    r14
0x140013812  push    r15
0x140013814  sub     rsp, 70h
0x140013818  mov     rax, cs:__security_cookie
0x14001381f  xor     rax, rsp
0x140013822  mov     [rsp+98h+var_30], rax
0x140013827  mov     r15, r8
0x14001382a  mov     rsi, rdx
0x14001382d  mov     rbp, rcx
0x140013830  mov     [rsp+98h+var_70], rdx
0x140013835  mov     [rsp+98h+var_78], 0
0x14001383d  lea     rax, ??_7CNodeCollection@Xml@Util@Sharp@@6B@; const Sharp::Util::Xml::CNodeCollection::`vftable'
0x140013844  mov     [rdx], rax
0x140013847  lea     rcx, [rdx+8]
0x14001384b  call    ??0?$list@VCNode@Xml@Util@Sharp@@V?$allocator@VCNode@Xml@Util@Sharp@@@std@@@std@@QEAA@XZ; std::list<Sharp::Util::Xml::CNode>::list<Sharp::Util::Xml::CNode>(void)
0x140013850  nop
0x140013851  lea     rax, WPP_GLOBAL_Control
0x140013858  mov     rcx, cs:WPP_GLOBAL_Control
0x14001385f  cmp     rcx, rax
0x140013862  jz      short loc_140013880
0x140013864  test    byte ptr [rcx+1Ch], 8
0x140013868  jz      short loc_140013880
0x14001386a  mov     edx, 0Ah
0x14001386f  lea     r8, WPP_aa5cb3998772301bcbc4f4136f5a9bc8_Traceguids
0x140013876  mov     rcx, [rcx+10h]
0x14001387a  call    WPP_SF_
0x14001387f  nop
0x140013880  mov     [rsp+98h+var_78], 1
0x140013888  mov     rbx, [rbp+8]
0x14001388c  mov     rbx, [rbx]
0x14001388f  cmp     rbx, [rbp+8]
0x140013893  jz      short loc_1400138EC
0x140013895  lea     rdx, [rsp+98h+var_50]
0x14001389a  lea     rcx, [rbx+10h]
0x14001389e  call    ?GetName@CNode@Xml@Util@Sharp@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Sharp::Util::Xml::CNode::GetName(void)
0x1400138a3  nop
0x1400138a4  mov     rdx, r15
0x1400138a7  mov     rcx, rax
0x1400138aa  call    ??$?8GU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@0@Z; std::operator==<ushort>(std::wstring const &,std::wstring const &)
0x1400138af  mov     dil, al
0x1400138b2  xor     r8d, r8d
0x1400138b5  mov     dl, 1
0x1400138b7  lea     rcx, [rsp+98h+var_50]
0x1400138bc  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1400138c1  test    dil, dil
0x1400138c4  jz      short loc_14001388C
0x1400138c6  lea     rax, [rsp+98h+var_60]
0x1400138cb  mov     [rsp+98h+var_68], rax
0x1400138d0  lea     rdx, [rbx+10h]; struct Sharp::Util::Xml::CNode *
0x1400138d4  lea     rcx, [rsp+98h+var_60]; this
0x1400138d9  call    ??0CNode@Xml@Util@Sharp@@QEAA@AEBV0123@@Z; Sharp::Util::Xml::CNode::CNode(Sharp::Util::Xml::CNode const &)
0x1400138de  nop
0x1400138df  mov     rdx, rax
0x1400138e2  mov     rcx, rsi
0x1400138e5  call    ?Add@CNodeCollection@Xml@Util@Sharp@@QEAAXVCNode@234@@Z; Sharp::Util::Xml::CNodeCollection::Add(Sharp::Util::Xml::CNode)
0x1400138ea  jmp     short loc_14001388C
0x1400138ec  mov     rax, rsi
0x1400138ef  mov     rcx, [rsp+98h+var_30]
0x1400138f4  xor     rcx, rsp; StackCookie
0x1400138f7  call    __security_check_cookie
0x1400138fc  mov     rbx, [rsp+98h+arg_0]
0x140013904  add     rsp, 70h
0x140013908  pop     r15
0x14001390a  pop     r14
0x14001390c  pop     rdi
0x14001390d  pop     rsi
0x14001390e  pop     rbp
0x14001390f  retn
```
