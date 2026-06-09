# PolicyModel::CRule::DeserializeConditions<PolicyModel::CFilePublisherCondition>(Sharp::Util::Xml::CNode const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x1400096c4`
- end: `0x1400097cd`
- name: `??$DeserializeConditions@VCFilePublisherCondition@PolicyModel@@@CRule@PolicyModel@@AEAAXAEBVCNode@Xml@Util@Sharp@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z`
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
- `0x1400096c4`
- `0x1400098c0`
- `0x14000a388`
- `0x14000a470`
- `0x14000c758`
- `0x140012c90`
- `0x14001377c`
- `0x140016010`

## pseudocode

```c
void __fastcall PolicyModel::CRule::DeserializeConditions<PolicyModel::CFilePublisherCondition>(
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
    v10 = (Sharp::Util::CRefCount *)operator new(0x90u);
    v13[1] = v10;
    if ( v10 )
      v10 = (Sharp::Util::CRefCount *)PolicyModel::CFilePublisherCondition::CFilePublisherCondition(v10);
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
0x1400096c4  push    rbp
0x1400096c6  push    rbx
0x1400096c7  push    rsi
0x1400096c8  push    rdi
0x1400096c9  push    r14
0x1400096cb  mov     rbp, rsp
0x1400096ce  sub     rsp, 60h
0x1400096d2  mov     r14b, r9b
0x1400096d5  mov     rbx, r8
0x1400096d8  mov     rdi, rdx
0x1400096db  mov     rsi, rcx
0x1400096de  lea     rax, WPP_GLOBAL_Control
0x1400096e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400096ec  cmp     rcx, rax
0x1400096ef  jz      short loc_14000970C
0x1400096f1  test    byte ptr [rcx+1Ch], 8
0x1400096f5  jz      short loc_14000970C
0x1400096f7  mov     edx, 14h
0x1400096fc  lea     r8, WPP_d304a645fd6338ffd40dd01c834cc669_Traceguids
0x140009703  mov     rcx, [rcx+10h]
0x140009707  call    WPP_SF_
0x14000970c  mov     r8, rbx
0x14000970f  lea     rdx, [rbp+var_18]
0x140009713  mov     rcx, rdi
0x140009716  call    ?GetSpecificChilds@CNode@Xml@Util@Sharp@@QEBA?AVCNodeCollection@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CNode::GetSpecificChilds(std::wstring const &)
0x14000971b  nop
0x14000971c  mov     rax, [rbp+var_10]
0x140009720  mov     rdi, [rax]
0x140009723  cmp     rdi, rax
0x140009726  jz      loc_1400097B9
0x14000972c  mov     ecx, 90h; Size
0x140009731  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009736  mov     [rbp+var_30], rax
0x14000973a  test    rax, rax
0x14000973d  jz      short loc_140009748
0x14000973f  mov     rcx, rax; this
0x140009742  call    ??0CFilePublisherCondition@PolicyModel@@QEAA@XZ; PolicyModel::CFilePublisherCondition::CFilePublisherCondition(void)
0x140009747  nop
0x140009748  mov     rdx, rax
0x14000974b  lea     rcx, [rbp+var_38]
0x14000974f  call    ??0?$CSharedPtr@VCRuleCondition@PolicyModel@@@Util@Sharp@@QEAA@PEAVCRuleCondition@PolicyModel@@@Z; Sharp::Util::CSharedPtr<PolicyModel::CRuleCondition>::CSharedPtr<PolicyModel::CRuleCondition>(PolicyModel::CRuleCondition *)
0x140009754  nop
0x140009755  mov     rbx, [rbp+var_38]
0x140009759  mov     rcx, [rbx+10h]
0x14000975d  add     rcx, 8
0x140009761  mov     rax, [rcx]
0x140009764  lea     rdx, [rdi+10h]
0x140009768  mov     rax, [rax+10h]
0x14000976c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009771  lea     rax, [rbp+var_40]
0x140009775  mov     [rbp+var_40], rbx
0x140009779  lock inc dword ptr [rbx+8]
0x14000977d  test    r14b, r14b
0x140009780  jz      short loc_140009794
0x140009782  mov     [rbp+var_28], rax
0x140009786  lea     rdx, [rbp+var_40]
0x14000978a  mov     rcx, rsi
0x14000978d  call    ?AddCondition@CRule@PolicyModel@@QEAAXV?$CSharedPtr@VCRuleCondition@PolicyModel@@@Util@Sharp@@@Z; PolicyModel::CRule::AddCondition(Sharp::Util::CSharedPtr<PolicyModel::CRuleCondition>)
0x140009792  jmp     short loc_1400097A5
0x140009794  mov     [rbp+var_20], rax
0x140009798  lea     rdx, [rbp+var_40]
0x14000979c  mov     rcx, rsi
0x14000979f  call    ?AddException@CRule@PolicyModel@@QEAAXV?$CSharedPtr@VCRuleCondition@PolicyModel@@@Util@Sharp@@@Z; PolicyModel::CRule::AddException(Sharp::Util::CSharedPtr<PolicyModel::CRuleCondition>)
0x1400097a4  nop
0x1400097a5  mov     rcx, rbx; this
0x1400097a8  call    ?ReleaseReference@CRefCount@Util@Sharp@@QEAAJXZ; Sharp::Util::CRefCount::ReleaseReference(void)
0x1400097ad  mov     rdi, [rdi]
0x1400097b0  mov     rax, [rbp+var_10]
0x1400097b4  jmp     loc_140009723
0x1400097b9  lea     rcx, [rbp+var_18]; this
0x1400097bd  call    ??1CNodeCollection@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNodeCollection::~CNodeCollection(void)
0x1400097c2  add     rsp, 60h
0x1400097c6  pop     r14
0x1400097c8  pop     rdi
0x1400097c9  pop     rsi
0x1400097ca  pop     rbx
0x1400097cb  pop     rbp
0x1400097cc  retn
```
