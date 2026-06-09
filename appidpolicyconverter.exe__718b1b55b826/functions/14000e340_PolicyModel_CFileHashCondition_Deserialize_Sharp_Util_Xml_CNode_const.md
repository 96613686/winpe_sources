# PolicyModel::CFileHashCondition::Deserialize(Sharp::Util::Xml::CNode const &)

- ea: `0x14000e340`
- end: `0x14000e46c`
- name: `?Deserialize@CFileHashCondition@PolicyModel@@MEAAXAEBVCNode@Xml@Util@Sharp@@@Z`
- size: `300`
- prototype: `void __fastcall(PolicyModel::CFileHashCondition *__hidden this, const struct Sharp::Util::Xml::CNode *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config`

## callees

- `0x140001530`
- `0x1400070e4`
- `0x1400080b0`
- `0x140008368`
- `0x1400099b4`
- `0x14000dec4`
- `0x14000e238`
- `0x14000e340`
- `0x1400109fc`
- `0x140012c90`
- `0x14001377c`
- `0x140013b10`
- `0x140016010`

## pseudocode

```c
void __fastcall PolicyModel::CFileHashCondition::Deserialize(
        PolicyModel::CFileHashCondition *this,
        const struct Sharp::Util::Xml::CNode *a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rdi
  PolicyModel::CFileHash *v6; // rax
  volatile signed __int32 *v7; // rbx
  volatile signed __int32 *v8; // [rsp+20h] [rbp-60h] BYREF
  Sharp::Util::CRefCount *v9; // [rsp+28h] [rbp-58h] BYREF
  char v10[8]; // [rsp+30h] [rbp-50h] BYREF
  _QWORD *v11; // [rsp+38h] [rbp-48h]
  PolicyModel::CFileHash *v12; // [rsp+48h] [rbp-38h]
  volatile signed __int32 **v13; // [rsp+50h] [rbp-30h]
  _QWORD v14[4]; // [rsp+58h] [rbp-28h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_bf7ccfda65e038325518e9aae80970ab_Traceguids);
  std::wstring::wstring((__int64)v14);
  Sharp::Util::Xml::CNode::GetSpecificChilds(a2, v10, v14);
  std::wstring::_Tidy(v14, 1, 0);
  v4 = v11;
  v5 = (_QWORD *)*v11;
  while ( v5 != v4 )
  {
    v6 = (PolicyModel::CFileHash *)operator new(0x58u);
    v12 = v6;
    if ( v6 )
      v6 = (PolicyModel::CFileHash *)PolicyModel::CFileHash::CFileHash(v6);
    Sharp::Util::CSharedPtr<PolicyModel::CFileHash>::CSharedPtr<PolicyModel::CFileHash>(&v9, v6);
    v7 = (volatile signed __int32 *)v9;
    (*(void (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)(*((_QWORD *)v9 + 2) + 8LL) + 16LL))(
      *((_QWORD *)v9 + 2) + 8LL,
      v5 + 2);
    v13 = &v8;
    v8 = v7;
    _InterlockedIncrement(v7 + 2);
    PolicyModel::CFileHashCondition::AddHash((char *)this - 8, &v8);
    Sharp::Util::CRefCount::ReleaseReference((Sharp::Util::CRefCount *)v7);
    v5 = (_QWORD *)*v5;
    v4 = v11;
  }
  Sharp::Util::Xml::CNodeCollection::~CNodeCollection((Sharp::Util::Xml::CNodeCollection *)v10);
}

```

## disassembly

```asm
0x14000e340  mov     [rsp-18h+arg_10], rbx
0x14000e345  push    rbp
0x14000e346  push    rsi
0x14000e347  push    rdi
0x14000e348  mov     rbp, rsp
0x14000e34b  sub     rsp, 80h
0x14000e352  mov     rax, cs:__security_cookie
0x14000e359  xor     rax, rsp
0x14000e35c  mov     [rbp+var_8], rax
0x14000e360  mov     rbx, rdx
0x14000e363  mov     rsi, rcx
0x14000e366  lea     rax, WPP_GLOBAL_Control
0x14000e36d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e374  cmp     rcx, rax
0x14000e377  jz      short loc_14000E394
0x14000e379  test    byte ptr [rcx+1Ch], 8
0x14000e37d  jz      short loc_14000E394
0x14000e37f  mov     edx, 0Eh
0x14000e384  lea     r8, WPP_bf7ccfda65e038325518e9aae80970ab_Traceguids
0x14000e38b  mov     rcx, [rcx+10h]
0x14000e38f  call    WPP_SF_
0x14000e394  lea     rdx, aFilehash; "FileHash"
0x14000e39b  lea     rcx, [rbp+var_28]
0x14000e39f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000e3a4  nop
0x14000e3a5  lea     r8, [rbp+var_28]
0x14000e3a9  lea     rdx, [rbp+var_50]
0x14000e3ad  mov     rcx, rbx
0x14000e3b0  call    ?GetSpecificChilds@CNode@Xml@Util@Sharp@@QEBA?AVCNodeCollection@234@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Sharp::Util::Xml::CNode::GetSpecificChilds(std::wstring const &)
0x14000e3b5  nop
0x14000e3b6  xor     r8d, r8d
0x14000e3b9  mov     dl, 1
0x14000e3bb  lea     rcx, [rbp+var_28]
0x14000e3bf  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000e3c4  mov     rax, [rbp+var_48]
0x14000e3c8  mov     rdi, [rax]
0x14000e3cb  cmp     rdi, rax
0x14000e3ce  jz      short loc_14000E444
0x14000e3d0  mov     ecx, 58h ; 'X'; Size
0x14000e3d5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000e3da  mov     [rbp+var_38], rax
0x14000e3de  test    rax, rax
0x14000e3e1  jz      short loc_14000E3EC
0x14000e3e3  mov     rcx, rax; this
0x14000e3e6  call    ??0CFileHash@PolicyModel@@AEAA@XZ; PolicyModel::CFileHash::CFileHash(void)
0x14000e3eb  nop
0x14000e3ec  mov     rdx, rax
0x14000e3ef  lea     rcx, [rbp+var_58]
0x14000e3f3  call    ??0?$CSharedPtr@VCFileHash@PolicyModel@@@Util@Sharp@@QEAA@PEAVCFileHash@PolicyModel@@@Z; Sharp::Util::CSharedPtr<PolicyModel::CFileHash>::CSharedPtr<PolicyModel::CFileHash>(PolicyModel::CFileHash *)
0x14000e3f8  nop
0x14000e3f9  mov     rbx, [rbp+var_58]
0x14000e3fd  mov     rcx, [rbx+10h]
0x14000e401  add     rcx, 8
0x14000e405  mov     rax, [rcx]
0x14000e408  lea     rdx, [rdi+10h]
0x14000e40c  mov     rax, [rax+10h]
0x14000e410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e415  lea     rax, [rbp+var_60]
0x14000e419  mov     [rbp+var_30], rax
0x14000e41d  mov     [rbp+var_60], rbx
0x14000e421  lock inc dword ptr [rbx+8]
0x14000e425  lea     rcx, [rsi-8]
0x14000e429  lea     rdx, [rbp+var_60]
0x14000e42d  call    ?AddHash@CFileHashCondition@PolicyModel@@QEAAXV?$CSharedPtr@VCFileHash@PolicyModel@@@Util@Sharp@@@Z; PolicyModel::CFileHashCondition::AddHash(Sharp::Util::CSharedPtr<PolicyModel::CFileHash>)
0x14000e432  nop
0x14000e433  mov     rcx, rbx; this
0x14000e436  call    ?ReleaseReference@CRefCount@Util@Sharp@@QEAAJXZ; Sharp::Util::CRefCount::ReleaseReference(void)
0x14000e43b  mov     rdi, [rdi]
0x14000e43e  mov     rax, [rbp+var_48]
0x14000e442  jmp     short loc_14000E3CB
0x14000e444  lea     rcx, [rbp+var_50]; this
0x14000e448  call    ??1CNodeCollection@Xml@Util@Sharp@@UEAA@XZ; Sharp::Util::Xml::CNodeCollection::~CNodeCollection(void)
0x14000e44d  mov     rcx, [rbp+var_8]
0x14000e451  xor     rcx, rsp; StackCookie
0x14000e454  call    __security_check_cookie
0x14000e459  mov     rbx, [rsp+80h+arg_10]
0x14000e461  add     rsp, 80h
0x14000e468  pop     rdi
0x14000e469  pop     rsi
0x14000e46a  pop     rbp
0x14000e46b  retn
```
