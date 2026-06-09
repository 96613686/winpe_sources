# PolicyModel::CRule::DeserializeConditions<PolicyModel::CFileHashCondition>(Sharp::Util::Xml::CNode const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x140009410`
- end: `0x140009519`
- name: `??$DeserializeConditions@VCFileHashCondition@PolicyModel@@@CRule@PolicyModel@@AEAAXAEBVCNode@Xml@Util@Sharp@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z`
- size: `265`
- prototype: `void __fastcall(__int64, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x14000a560`

## callees

- `0x140001530`
- `0x1400070e4`
- `0x1400080b0`
- `0x140009410`
- `0x1400098c0`
- `0x14000a388`
- `0x14000a470`
- `0x14000dfb8`
- `0x140012c90`
- `0x14001377c`
- `0x140016010`

## pseudocode

```c
void __fastcall PolicyModel::CRule::DeserializeConditions<PolicyModel::CFileHashCondition>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char a4)
{
  _QWORD *v8; // rax
  _QWORD *v9; // rdi
  Sharp::Util::CRefCount *v10; // rax
  volatile signed __int32 *v11; // rbx
  volatile signed __int32 *v12; // [rsp+20h] [rbp-40h] BYREF
  Sharp::Util::CRefCount *v13[4]; // [rsp+28h] [rbp-38h] BYREF
  _BYTE v14[8]; // [rsp+48h] [rbp-18h] BYREF
  _QWORD *v15; // [rsp+50h] [rbp-10h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_d304a645fd6338ffd40dd01c834cc669_Traceguids);
  Sharp::Util::Xml::CNode::GetSpecificChilds(a2, v14, a3);
  v8 = v15;
  v9 = (_QWORD *)*v15;
  while ( v9 != v8 )
  {
    v10 = (Sharp::Util::CRefCount *)operator new(0x20u);
    v13[1] = v10;
    if ( v10 )
      v10 = (Sharp::Util::CRefCount *)PolicyModel::CFileHashCondition::CFileHashCondition(v10);
    Sharp::Util::CSharedPtr<PolicyModel::CRuleCondition>::CSharedPtr<PolicyModel::CRuleCondition>(v13, v10);
    v11 = (volatile signed __int32 *)v13[0];
    (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)(*((_QWORD *)v13[0] + 2) + 8LL) + 16LL))(
      *((_QWORD *)v13[0] + 2) + 8LL,
      v9 + 2);
    v12 = v11;
    _InterlockedIncrement(v11 + 2);
    if ( a4 )
    {
      v13[2] = (Sharp::Util::CRefCount *)&v12;
      PolicyModel::CRule::AddCondition(a1, &v12);
    }
    else
    {
      v13[3] = (Sharp::Util::CRefCount *)&v12;
      PolicyModel::CRule::AddException(a1, &v12);
    }
    Sharp::Util::CRefCount::ReleaseReference((Sharp::Util::CRefCount *)v11);
    v9 = (_QWORD *)*v9;
    v8 = v15;
  }
  Sharp::Util::Xml::CNodeCollection::~CNodeCollection((Sharp::Util::Xml::CNodeCollection *)v14);
}

```

## disassembly

```asm
0x140009410  push    rbp
0x140009412  push    rbx
0x140009413  push    rsi
0x140009414  push    rdi
0x140009415  push    r14
0x140009417  mov     rbp, rsp
0x14000941a  sub     rsp, 60h
0x14000941e  mov     r14b, r9b
0x140009421  mov     rbx, r8
0x140009424  mov     rdi, rdx
0x140009427  mov     rsi, rcx
0x14000942a  lea     rax, WPP_GLOBAL_Control
0x140009431  mov     rcx, cs:WPP_GLOBAL_Control
0x140009438  cmp     rcx, rax
0x14000943b  jz      short loc_140009458
0x14000943d  test    byte ptr [rcx+1Ch], 8
0x140009441  jz      short loc_140009458
0x140009443  mov     edx, 14h
0x140009448  lea     r8, WPP_d304a645fd6338ffd40dd01c834cc669_Traceguids
0x14000944f  mov     rcx, [rcx+10h]
0x140009453  call    WPP_SF_
0x140009458  mov     r8, rbx
0x14000945b  lea     rdx, [rbp+var_18]
0x14000945f  mov     rcx, rdi
0x140009462  call    ?GetSpecificChilds@CNode@Xml@Util@Sharp@@QEBA?AVCNodeCollection@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CNode::GetSpecificChilds(std::wstring const &)
0x140009467  nop
0x140009468  mov     rax, [rbp+var_10]
0x14000946c  mov     rdi, [rax]
0x14000946f  cmp     rdi, rax
0x140009472  jz      loc_140009505
0x140009478  mov     ecx, 20h ; ' '; Size
0x14000947d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009482  mov     [rbp+var_30], rax
0x140009486  test    rax, rax
0x140009489  jz      short loc_140009494
0x14000948b  mov     rcx, rax; this
0x14000948e  call    ??0CFileHashCondition@PolicyModel@@QEAA@XZ; PolicyModel::CFileHashCondition::CFileHashCondition(void)
0x140009493  nop
0x140009494  mov     rdx, rax
0x140009497  lea     rcx, [rbp+var_38]
0x14000949b  call    ??0?$CSharedPtr@VCRuleCondition@PolicyModel@@@Util@Sharp@@QEAA@PEAVCRuleCondition@PolicyModel@@@Z; Sharp::Util::CSharedPtr<PolicyModel::CRuleCondition>::CSharedPtr<PolicyModel::CRuleCondition>(PolicyModel::CRuleCondition *)
0x1400094a0  nop
0x1400094a1  mov     rbx, [rbp+var_38]
0x1400094a5  mov     rcx, [rbx+10h]
0x1400094a9  add     rcx, 8
0x1400094ad  mov     rax, [rcx]
0x1400094b0  lea     rdx, [rdi+10h]
0x1400094b4  mov     rax, [rax+10h]
0x1400094b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400094bd  lea     rax, [rbp+var_40]
0x1400094c1  mov     [rbp+var_40], rbx
0x1400094c5  lock inc dword ptr [rbx+8]
0x1400094c9  test    r14b, r14b
0x1400094cc  jz      short loc_1400094E0
0x1400094ce  mov     [rbp+var_28], rax
0x1400094d2  lea     rdx, [rbp+var_40]
0x1400094d6  mov     rcx, rsi
0x1400094d9  call    ?AddCondition@CRule@PolicyModel@@QEAAXV?$CSharedPtr@VCRuleCondition@PolicyModel@@@Util@Sharp@@@Z; PolicyModel::CRule::AddCondition(Sharp::Util::CSharedPtr<PolicyModel::CRuleCondition>)
0x1400094de  jmp     short loc_1400094F1
0x1400094e0  mov     [rbp+var_20], rax
0x1400094e4  lea     rdx, [rbp+var_40]
0x1400094e8  mov     rcx, rsi
0x1400094eb  call    ?AddException@CRule@PolicyModel@@QEAAXV?$CSharedPtr@VCRuleCondition@PolicyModel@@@Util@Sharp@@@Z; PolicyModel::CRule::AddException(Sharp::Util::CSharedPtr<PolicyModel::CRuleCondition>)
0x1400094f0  nop
0x1400094f1  mov     rcx, rbx; this
0x1400094f4  call    ?ReleaseReference@CRefCount@Util@Sharp@@QEAAJXZ; Sharp::Util::CRefCount::ReleaseReference(void)
0x1400094f9  mov     rdi, [rdi]
0x1400094fc  mov     rax, [rbp+var_10]
0x140009500  jmp     loc_14000946F
0x140009505  lea     rcx, [rbp+var_18]; this
0x140009509  call    ??1CNodeCollection@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNodeCollection::~CNodeCollection(void)
0x14000950e  add     rsp, 60h
0x140009512  pop     r14
0x140009514  pop     rdi
0x140009515  pop     rsi
0x140009516  pop     rbx
0x140009517  pop     rbp
0x140009518  retn
```
