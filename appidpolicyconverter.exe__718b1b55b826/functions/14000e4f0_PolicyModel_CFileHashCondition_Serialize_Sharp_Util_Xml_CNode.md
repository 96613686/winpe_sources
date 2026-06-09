# PolicyModel::CFileHashCondition::Serialize(Sharp::Util::Xml::CNode &)

- ea: `0x14000e4f0`
- end: `0x14000e5d6`
- name: `?Serialize@CFileHashCondition@PolicyModel@@MEBAXAEAVCNode@Xml@Util@Sharp@@@Z`
- size: `230`
- prototype: `void __fastcall(PolicyModel::CFileHashCondition *this, struct Sharp::Util::Xml::CNode *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config`

## callees

- `0x1400070e4`
- `0x140008368`
- `0x14000e4f0`
- `0x140012138`
- `0x140012764`
- `0x140013b10`
- `0x140016010`

## pseudocode

```c
void __fastcall PolicyModel::CFileHashCondition::Serialize(
        PolicyModel::CFileHashCondition *this,
        struct Sharp::Util::Xml::CNode *a2)
{
  _QWORD *v4; // rbx
  __int64 v5; // rcx
  unsigned __int16 *v6; // rax
  __int64 v7; // rcx
  OLECHAR v8[8]; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v9[4]; // [rsp+30h] [rbp-38h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_bf7ccfda65e038325518e9aae80970ab_Traceguids);
  v4 = (_QWORD *)*((_QWORD *)this + 1);
  while ( 1 )
  {
    v4 = (_QWORD *)*v4;
    if ( v4 == *((_QWORD **)this + 1) )
      break;
    v5 = *(_QWORD *)(v4[2] + 16LL) + 8LL;
    v6 = (unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v5 + 24LL))(v5, v9);
    Sharp::Util::Xml::CNode::CreateChild(a2, v8, v6);
    std::wstring::_Tidy(v9, 1, 0);
    v7 = *(_QWORD *)(v4[2] + 16LL) + 8LL;
    (*(void (__fastcall **)(__int64, OLECHAR *))(*(_QWORD *)v7 + 8LL))(v7, v8);
    Sharp::Util::Xml::CNode::~CNode((Sharp::Util::Xml::CNode *)v8);
  }
}

```

## disassembly

```asm
0x14000e4f0  mov     [rsp+arg_0], rbx
0x14000e4f5  mov     [rsp+arg_10], rsi
0x14000e4fa  push    rdi
0x14000e4fb  sub     rsp, 60h
0x14000e4ff  mov     rax, cs:__security_cookie
0x14000e506  xor     rax, rsp
0x14000e509  mov     [rsp+68h+var_18], rax
0x14000e50e  mov     rsi, rdx
0x14000e511  mov     rdi, rcx
0x14000e514  lea     rax, WPP_GLOBAL_Control
0x14000e51b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e522  cmp     rcx, rax
0x14000e525  jz      short loc_14000E542
0x14000e527  test    byte ptr [rcx+1Ch], 8
0x14000e52b  jz      short loc_14000E542
0x14000e52d  mov     edx, 0Dh
0x14000e532  lea     r8, WPP_bf7ccfda65e038325518e9aae80970ab_Traceguids
0x14000e539  mov     rcx, [rcx+10h]
0x14000e53d  call    WPP_SF_
0x14000e542  mov     rbx, [rdi+8]
0x14000e546  mov     rbx, [rbx]
0x14000e549  cmp     rbx, [rdi+8]
0x14000e54d  jz      short loc_14000E5B7
0x14000e54f  mov     rax, [rbx+10h]
0x14000e553  mov     rcx, [rax+10h]
0x14000e557  add     rcx, 8
0x14000e55b  mov     rax, [rcx]
0x14000e55e  lea     rdx, [rsp+68h+var_38]
0x14000e563  mov     rax, [rax+18h]
0x14000e567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e56c  nop
0x14000e56d  mov     r8, rax; unsigned __int16 *
0x14000e570  lea     rdx, [rsp+68h+var_48]; struct Sharp::Util::Xml::CNode *
0x14000e575  mov     rcx, rsi; this
0x14000e578  call    ?CreateChild@CNode@Xml@Util@Sharp@@QEAA?AV1234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CNode::CreateChild(std::wstring const &)
0x14000e57d  nop
0x14000e57e  xor     r8d, r8d
0x14000e581  mov     dl, 1
0x14000e583  lea     rcx, [rsp+68h+var_38]
0x14000e588  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000e58d  mov     rax, [rbx+10h]
0x14000e591  mov     rcx, [rax+10h]
0x14000e595  add     rcx, 8
0x14000e599  mov     rax, [rcx]
0x14000e59c  lea     rdx, [rsp+68h+var_48]
0x14000e5a1  mov     rax, [rax+8]
0x14000e5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e5aa  nop
0x14000e5ab  lea     rcx, [rsp+68h+var_48]; this
0x14000e5b0  call    ??1CNode@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNode::~CNode(void)
0x14000e5b5  jmp     short loc_14000E546
0x14000e5b7  mov     rcx, [rsp+68h+var_18]
0x14000e5bc  xor     rcx, rsp; StackCookie
0x14000e5bf  call    __security_check_cookie
0x14000e5c4  lea     r11, [rsp+68h+var_8]
0x14000e5c9  mov     rbx, [r11+10h]
0x14000e5cd  mov     rsi, [r11+20h]
0x14000e5d1  mov     rsp, r11
0x14000e5d4  pop     rdi
0x14000e5d5  retn
```
