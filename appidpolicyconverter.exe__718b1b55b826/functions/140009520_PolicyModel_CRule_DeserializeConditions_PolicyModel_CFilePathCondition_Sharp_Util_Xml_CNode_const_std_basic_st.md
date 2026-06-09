# PolicyModel::CRule::DeserializeConditions<PolicyModel::CFilePathCondition>(Sharp::Util::Xml::CNode const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x140009520`
- end: `0x1400096bd`
- name: `??$DeserializeConditions@VCFilePathCondition@PolicyModel@@@CRule@PolicyModel@@AEAAXAEBVCNode@Xml@Util@Sharp@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z`
- size: `413`
- prototype: `void __fastcall(__int64, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x14000a560`

## callees

- `0x140001530`
- `0x1400070e4`
- `0x1400080b0`
- `0x140008368`
- `0x140009520`
- `0x1400098c0`
- `0x1400099b4`
- `0x14000a388`
- `0x14000a470`
- `0x14000d6f4`
- `0x14000db08`
- `0x14000db9c`
- `0x140012c90`
- `0x14001377c`
- `0x140013b10`
- `0x140016010`

## pseudocode

```c
void __fastcall PolicyModel::CRule::DeserializeConditions<PolicyModel::CFilePathCondition>(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char a4)
{
  int v8; // esi
  _QWORD *v9; // rax
  _QWORD *v10; // rdi
  PolicyModel::CFilePathCondition *v11; // rax
  PolicyModel::CFilePathCondition *v12; // rbx
  const struct PolicyModel::CFilePath *v13; // rax
  __int64 v14; // rdx
  volatile signed __int32 *v15; // rbx
  volatile signed __int32 *v16; // [rsp+28h] [rbp-61h] BYREF
  Sharp::Util::CRefCount *v17; // [rsp+30h] [rbp-59h] BYREF
  char v18[8]; // [rsp+38h] [rbp-51h] BYREF
  _QWORD *v19; // [rsp+40h] [rbp-49h]
  PolicyModel::CFilePathCondition *v20; // [rsp+50h] [rbp-39h]
  volatile signed __int32 **v21; // [rsp+58h] [rbp-31h]
  volatile signed __int32 **v22; // [rsp+60h] [rbp-29h]
  _BYTE v23[32]; // [rsp+68h] [rbp-21h] BYREF
  _BYTE v24[48]; // [rsp+88h] [rbp-1h] BYREF

  v8 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_d304a645fd6338ffd40dd01c834cc669_Traceguids);
  Sharp::Util::Xml::CNode::GetSpecificChilds(a2, v18, a3);
  v9 = v19;
  v10 = (_QWORD *)*v19;
  while ( v10 != v9 )
  {
    v11 = (PolicyModel::CFilePathCondition *)operator new(0x40u);
    v12 = v11;
    v20 = v11;
    if ( v11 )
    {
      std::wstring::wstring(v23, L"*");
      v13 = (const struct PolicyModel::CFilePath *)PolicyModel::CFilePath::CFilePath(v24, v23);
      v8 |= 3u;
      v11 = (PolicyModel::CFilePathCondition *)PolicyModel::CFilePathCondition::CFilePathCondition(v12, v13);
    }
    Sharp::Util::CSharedPtr<PolicyModel::CRuleCondition>::CSharedPtr<PolicyModel::CRuleCondition>(&v17, v11);
    if ( (v8 & 2) != 0 )
    {
      v8 &= ~2u;
      PolicyModel::CFilePath::~CFilePath((PolicyModel::CFilePath *)v24);
    }
    if ( (v8 & 1) != 0 )
    {
      v8 &= ~1u;
      LOBYTE(v14) = 1;
      std::wstring::_Tidy(v23, v14, 0);
    }
    v15 = (volatile signed __int32 *)v17;
    (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)(*((_QWORD *)v17 + 2) + 8LL) + 16LL))(
      *((_QWORD *)v17 + 2) + 8LL,
      v10 + 2);
    v16 = v15;
    _InterlockedIncrement(v15 + 2);
    if ( a4 )
    {
      v21 = &v16;
      PolicyModel::CRule::AddCondition(a1, &v16);
    }
    else
    {
      v22 = &v16;
      PolicyModel::CRule::AddException(a1, &v16);
    }
    Sharp::Util::CRefCount::ReleaseReference((Sharp::Util::CRefCount *)v15);
    v10 = (_QWORD *)*v10;
    v9 = v19;
  }
  Sharp::Util::Xml::CNodeCollection::~CNodeCollection((Sharp::Util::Xml::CNodeCollection *)v18);
}

```

## disassembly

```asm
0x140009520  mov     [rsp-8+arg_18], rbx
0x140009525  push    rbp
0x140009526  push    rsi
0x140009527  push    rdi
0x140009528  push    r14
0x14000952a  push    r15
0x14000952c  lea     rbp, [rsp-37h]
0x140009531  sub     rsp, 0C0h
0x140009538  mov     rax, cs:__security_cookie
0x14000953f  xor     rax, rsp
0x140009542  mov     [rbp+57h+var_28], rax
0x140009546  mov     r15b, r9b
0x140009549  mov     rdi, r8
0x14000954c  mov     rbx, rdx
0x14000954f  mov     r14, rcx
0x140009552  xor     esi, esi
0x140009554  mov     [rbp+57h+var_C0], esi
0x140009557  lea     rax, WPP_GLOBAL_Control
0x14000955e  mov     rcx, cs:WPP_GLOBAL_Control
0x140009565  cmp     rcx, rax
0x140009568  jz      short loc_140009583
0x14000956a  test    byte ptr [rcx+1Ch], 8
0x14000956e  jz      short loc_140009583
0x140009570  lea     edx, [rsi+14h]
0x140009573  lea     r8, WPP_d304a645fd6338ffd40dd01c834cc669_Traceguids
0x14000957a  mov     rcx, [rcx+10h]
0x14000957e  call    WPP_SF_
0x140009583  mov     r8, rdi
0x140009586  lea     rdx, [rbp+57h+var_A8]
0x14000958a  mov     rcx, rbx
0x14000958d  call    ?GetSpecificChilds@CNode@Xml@Util@Sharp@@QEBA?AVCNodeCollection@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CNode::GetSpecificChilds(std::wstring const &)
0x140009592  nop
0x140009593  mov     rax, [rbp+57h+var_A0]
0x140009597  mov     rdi, [rax]
0x14000959a  cmp     rdi, rax
0x14000959d  jz      loc_140009691
0x1400095a3  mov     ecx, 40h ; '@'; Size
0x1400095a8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400095ad  mov     rbx, rax
0x1400095b0  mov     [rbp+57h+var_90], rax
0x1400095b4  test    rax, rax
0x1400095b7  jz      short loc_1400095F0
0x1400095b9  lea     rdx, asc_140018D18; "*"
0x1400095c0  lea     rcx, [rbp+57h+var_78]
0x1400095c4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x1400095c9  nop
0x1400095ca  or      esi, 1
0x1400095cd  mov     [rbp+57h+var_C0], esi
0x1400095d0  lea     rdx, [rbp+57h+var_78]
0x1400095d4  lea     rcx, [rbp+57h+var_58]
0x1400095d8  call    ??0CFilePath@PolicyModel@@QEAA@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PolicyModel::CFilePath::CFilePath(std::wstring const &)
0x1400095dd  nop
0x1400095de  or      esi, 2
0x1400095e1  mov     [rbp+57h+var_C0], esi
0x1400095e4  mov     rdx, rax; struct PolicyModel::CFilePath *
0x1400095e7  mov     rcx, rbx; this
0x1400095ea  call    ??0CFilePathCondition@PolicyModel@@QEAA@AEBVCFilePath@1@@Z; PolicyModel::CFilePathCondition::CFilePathCondition(PolicyModel::CFilePath const &)
0x1400095ef  nop
0x1400095f0  mov     rdx, rax
0x1400095f3  lea     rcx, [rbp+57h+var_B0]
0x1400095f7  call    ??0?$CSharedPtr@VCRuleCondition@PolicyModel@@@Util@Sharp@@QEAA@PEAVCRuleCondition@PolicyModel@@@Z; Sharp::Util::CSharedPtr<PolicyModel::CRuleCondition>::CSharedPtr<PolicyModel::CRuleCondition>(PolicyModel::CRuleCondition *)
0x1400095fc  nop
0x1400095fd  test    sil, 2
0x140009601  jz      short loc_140009613
0x140009603  and     esi, 0FFFFFFFDh
0x140009606  mov     [rbp+57h+var_C0], esi
0x140009609  lea     rcx, [rbp+57h+var_58]; this
0x14000960d  call    ??1CFilePath@PolicyModel@@UEAA@XZ; PolicyModel::CFilePath::~CFilePath(void)
0x140009612  nop
0x140009613  test    sil, 1
0x140009617  jz      short loc_14000962D
0x140009619  and     esi, 0FFFFFFFEh
0x14000961c  mov     [rbp+57h+var_C0], esi
0x14000961f  xor     r8d, r8d
0x140009622  mov     dl, 1
0x140009624  lea     rcx, [rbp+57h+var_78]
0x140009628  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000962d  mov     rbx, [rbp+57h+var_B0]
0x140009631  mov     rcx, [rbx+10h]
0x140009635  add     rcx, 8
0x140009639  mov     rax, [rcx]
0x14000963c  lea     rdx, [rdi+10h]
0x140009640  mov     rax, [rax+10h]
0x140009644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009649  lea     rax, [rbp+57h+var_B8]
0x14000964d  mov     [rbp+57h+var_B8], rbx
0x140009651  lock inc dword ptr [rbx+8]
0x140009655  test    r15b, r15b
0x140009658  jz      short loc_14000966C
0x14000965a  mov     [rbp+57h+var_88], rax
0x14000965e  lea     rdx, [rbp+57h+var_B8]
0x140009662  mov     rcx, r14
0x140009665  call    ?AddCondition@CRule@PolicyModel@@QEAAXV?$CSharedPtr@VCRuleCondition@PolicyModel@@@Util@Sharp@@@Z; PolicyModel::CRule::AddCondition(Sharp::Util::CSharedPtr<PolicyModel::CRuleCondition>)
0x14000966a  jmp     short loc_14000967D
0x14000966c  mov     [rbp+57h+var_80], rax
0x140009670  lea     rdx, [rbp+57h+var_B8]
0x140009674  mov     rcx, r14
0x140009677  call    ?AddException@CRule@PolicyModel@@QEAAXV?$CSharedPtr@VCRuleCondition@PolicyModel@@@Util@Sharp@@@Z; PolicyModel::CRule::AddException(Sharp::Util::CSharedPtr<PolicyModel::CRuleCondition>)
0x14000967c  nop
0x14000967d  mov     rcx, rbx; this
0x140009680  call    ?ReleaseReference@CRefCount@Util@Sharp@@QEAAJXZ; Sharp::Util::CRefCount::ReleaseReference(void)
0x140009685  mov     rdi, [rdi]
0x140009688  mov     rax, [rbp+57h+var_A0]
0x14000968c  jmp     loc_14000959A
0x140009691  lea     rcx, [rbp+57h+var_A8]; this
0x140009695  call    ??1CNodeCollection@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNodeCollection::~CNodeCollection(void)
0x14000969a  mov     rcx, [rbp+57h+var_28]
0x14000969e  xor     rcx, rsp; StackCookie
0x1400096a1  call    __security_check_cookie
0x1400096a6  mov     rbx, [rsp+0E0h+arg_18]
0x1400096ae  add     rsp, 0C0h
0x1400096b5  pop     r15
0x1400096b7  pop     r14
0x1400096b9  pop     rdi
0x1400096ba  pop     rsi
0x1400096bb  pop     rbp
0x1400096bc  retn
```
