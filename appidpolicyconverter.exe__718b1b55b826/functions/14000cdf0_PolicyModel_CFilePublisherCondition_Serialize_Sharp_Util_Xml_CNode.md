# PolicyModel::CFilePublisherCondition::Serialize(Sharp::Util::Xml::CNode &)

- ea: `0x14000cdf0`
- end: `0x14000cf45`
- name: `?Serialize@CFilePublisherCondition@PolicyModel@@MEBAXAEAVCNode@Xml@Util@Sharp@@@Z`
- size: `341`
- prototype: `void __fastcall(const OLECHAR *this, struct Sharp::Util::Xml::CNode *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config`

## callees

- `0x1400070e4`
- `0x140008368`
- `0x1400099b4`
- `0x14000cdf0`
- `0x140012138`
- `0x140012604`
- `0x140012764`
- `0x140013b10`
- `0x140016010`

## pseudocode

```c
void __fastcall PolicyModel::CFilePublisherCondition::Serialize(
        const OLECHAR *this,
        struct Sharp::Util::Xml::CNode *a2)
{
  unsigned __int16 *v4; // rax
  OLECHAR v5[8]; // [rsp+20h] [rbp-40h] BYREF
  unsigned __int16 v6[16]; // [rsp+30h] [rbp-30h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_f3cd61ca77c6343f41027d72af25da0d_Traceguids);
  std::wstring::wstring((__int64)v6);
  Sharp::Util::Xml::CNode::CreateAttribute((__int64)a2, v6, this + 4);
  std::wstring::_Tidy(v6, 1, 0);
  std::wstring::wstring((__int64)v6);
  Sharp::Util::Xml::CNode::CreateAttribute((__int64)a2, v6, this + 20);
  std::wstring::_Tidy(v6, 1, 0);
  std::wstring::wstring((__int64)v6);
  Sharp::Util::Xml::CNode::CreateAttribute((__int64)a2, v6, this + 36);
  std::wstring::_Tidy(v6, 1, 0);
  v4 = (unsigned __int16 *)(*(__int64 (__fastcall **)(char *, unsigned __int16 *))(*((_QWORD *)this + 14) + 24LL))(
                             (char *)this + 112,
                             v6);
  Sharp::Util::Xml::CNode::CreateChild(a2, v5, v4);
  std::wstring::_Tidy(v6, 1, 0);
  (*(void (__fastcall **)(char *, OLECHAR *))(*((_QWORD *)this + 14) + 8LL))((char *)this + 112, v5);
  Sharp::Util::Xml::CNode::~CNode((Sharp::Util::Xml::CNode *)v5);
}

```

## disassembly

```asm
0x14000cdf0  mov     [rsp-8+arg_10], rbx
0x14000cdf5  mov     [rsp-8+arg_18], rdi
0x14000cdfa  push    rbp
0x14000cdfb  mov     rbp, rsp
0x14000cdfe  sub     rsp, 60h
0x14000ce02  mov     rax, cs:__security_cookie
0x14000ce09  xor     rax, rsp
0x14000ce0c  mov     [rbp+var_10], rax
0x14000ce10  mov     rdi, rdx
0x14000ce13  mov     rbx, rcx
0x14000ce16  lea     rax, WPP_GLOBAL_Control
0x14000ce1d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ce24  cmp     rcx, rax
0x14000ce27  jz      short loc_14000CE44
0x14000ce29  test    byte ptr [rcx+1Ch], 8
0x14000ce2d  jz      short loc_14000CE44
0x14000ce2f  mov     edx, 0Ch
0x14000ce34  lea     r8, WPP_f3cd61ca77c6343f41027d72af25da0d_Traceguids
0x14000ce3b  mov     rcx, [rcx+10h]
0x14000ce3f  call    WPP_SF_
0x14000ce44  lea     rdx, aPublishername; "PublisherName"
0x14000ce4b  lea     rcx, [rbp+var_30]
0x14000ce4f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000ce54  nop
0x14000ce55  lea     r8, [rbx+8]
0x14000ce59  lea     rdx, [rbp+var_30]
0x14000ce5d  mov     rcx, rdi
0x14000ce60  call    ?CreateAttribute@CNode@Xml@Util@Sharp@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Sharp::Util::Xml::CNode::CreateAttribute(std::wstring const &,std::wstring const &)
0x14000ce65  nop
0x14000ce66  xor     r8d, r8d
0x14000ce69  mov     dl, 1
0x14000ce6b  lea     rcx, [rbp+var_30]
0x14000ce6f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000ce74  lea     rdx, aProductname; "ProductName"
0x14000ce7b  lea     rcx, [rbp+var_30]
0x14000ce7f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000ce84  nop
0x14000ce85  lea     r8, [rbx+28h]
0x14000ce89  lea     rdx, [rbp+var_30]
0x14000ce8d  mov     rcx, rdi
0x14000ce90  call    ?CreateAttribute@CNode@Xml@Util@Sharp@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Sharp::Util::Xml::CNode::CreateAttribute(std::wstring const &,std::wstring const &)
0x14000ce95  nop
0x14000ce96  xor     r8d, r8d
0x14000ce99  mov     dl, 1
0x14000ce9b  lea     rcx, [rbp+var_30]
0x14000ce9f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000cea4  lea     rdx, aBinaryname; "BinaryName"
0x14000ceab  lea     rcx, [rbp+var_30]
0x14000ceaf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000ceb4  nop
0x14000ceb5  lea     r8, [rbx+48h]
0x14000ceb9  lea     rdx, [rbp+var_30]
0x14000cebd  mov     rcx, rdi
0x14000cec0  call    ?CreateAttribute@CNode@Xml@Util@Sharp@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Sharp::Util::Xml::CNode::CreateAttribute(std::wstring const &,std::wstring const &)
0x14000cec5  nop
0x14000cec6  xor     r8d, r8d
0x14000cec9  mov     dl, 1
0x14000cecb  lea     rcx, [rbp+var_30]
0x14000cecf  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000ced4  mov     rax, [rbx+70h]
0x14000ced8  lea     rdx, [rbp+var_30]
0x14000cedc  lea     rcx, [rbx+70h]
0x14000cee0  mov     rax, [rax+18h]
0x14000cee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cee9  nop
0x14000ceea  mov     r8, rax; unsigned __int16 *
0x14000ceed  lea     rdx, [rbp+var_40]; struct Sharp::Util::Xml::CNode *
0x14000cef1  mov     rcx, rdi; this
0x14000cef4  call    ?CreateChild@CNode@Xml@Util@Sharp@@QEAA?AV1234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CNode::CreateChild(std::wstring const &)
0x14000cef9  nop
0x14000cefa  xor     r8d, r8d
0x14000cefd  mov     dl, 1
0x14000ceff  lea     rcx, [rbp+var_30]
0x14000cf03  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000cf08  mov     rax, [rbx+70h]
0x14000cf0c  lea     rdx, [rbp+var_40]
0x14000cf10  lea     rcx, [rbx+70h]
0x14000cf14  mov     rax, [rax+8]
0x14000cf18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cf1d  nop
0x14000cf1e  lea     rcx, [rbp+var_40]; this
0x14000cf22  call    ??1CNode@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNode::~CNode(void)
0x14000cf27  mov     rcx, [rbp+var_10]
0x14000cf2b  xor     rcx, rsp; StackCookie
0x14000cf2e  call    __security_check_cookie
0x14000cf33  lea     r11, [rsp+60h+var_s0]
0x14000cf38  mov     rbx, [r11+20h]
0x14000cf3c  mov     rdi, [r11+28h]
0x14000cf40  mov     rsp, r11
0x14000cf43  pop     rbp
0x14000cf44  retn
```
