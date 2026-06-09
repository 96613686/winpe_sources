# Ofc::TComplexTypeHelper<ODF::StyleRubyPropertiesContent>::FillWriters(ODF::StyleRubyPropertiesContent const &,Ofc::CNamespaceDeclarationTracker &,Ofc::CWriterEmit &,Ofc::IWriterParams &)

- ea: `0x1800c4460`
- end: `0x1800c4652`
- name: `?FillWriters@?$TComplexTypeHelper@VStyleRubyPropertiesContent@ODF@@@Ofc@@SAXAEBVStyleRubyPropertiesContent@ODF@@AEAVCNamespaceDeclarationTracker@2@AEAVCWriterEmit@2@AEAVIWriterParams@2@@Z`
- size: `498`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800937ec`

## callees

- `0x1800048d4`
- `0x1800078b4`
- `0x1800c4460`
- `0x1800cd6d0`
- `0x1800cd70c`
- `0x1801a80e0`

## import_xrefs

- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800c4493`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800c4544`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800c4493`
- `mso40uiWin32Client!__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z` at `0x1800c4544`
- `mso40uiWin32Client!__imp_?GetPropertyState@CPropertySetImpl@Tph@Ofc@@IEBA?AW4State@23@I@Z` at `0x1800c44b4`
- `mso40uiWin32Client!__imp_?GetPropertyState@CPropertySetImpl@Tph@Ofc@@IEBA?AW4State@23@I@Z` at `0x1800c4568`
- `mso40uiWin32Client!__imp_?GetPropertyState@CPropertySetImpl@Tph@Ofc@@IEBA?AW4State@23@I@Z` at `0x1800c44b4`
- `mso40uiWin32Client!__imp_?GetPropertyState@CPropertySetImpl@Tph@Ofc@@IEBA?AW4State@23@I@Z` at `0x1800c4568`
- `mso40uiWin32Client!__imp_?GetPropertyStgType@CPropertySetImpl@Tph@Ofc@@IEBAPEBV?$TAnyStorage@$07@3@I@Z` at `0x1800c44c5`
- `mso40uiWin32Client!__imp_?GetPropertyStgType@CPropertySetImpl@Tph@Ofc@@IEBAPEBV?$TAnyStorage@$07@3@I@Z` at `0x1800c457a`
- `mso40uiWin32Client!__imp_?GetPropertyStgType@CPropertySetImpl@Tph@Ofc@@IEBAPEBV?$TAnyStorage@$07@3@I@Z` at `0x1800c44c5`
- `mso40uiWin32Client!__imp_?GetPropertyStgType@CPropertySetImpl@Tph@Ofc@@IEBAPEBV?$TAnyStorage@$07@3@I@Z` at `0x1800c457a`
- `mso40uiWin32Client!__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ` at `0x1800c4623`
- `mso40uiWin32Client!__imp_?WriteAttrHelper@Ofc@@YAXPEB_WHAEAVIWriterParams@1@AEBV?$TFixedVarStr@$0ICF@@1@@Z` at `0x1800c4539`
- `mso40uiWin32Client!__imp_?WriteAttrHelper@Ofc@@YAXPEB_WHAEAVIWriterParams@1@AEBV?$TFixedVarStr@$0ICF@@1@@Z` at `0x1800c45e9`
- `mso40uiWin32Client!__imp_?WriteAttrHelper@Ofc@@YAXPEB_WHAEAVIWriterParams@1@AEBV?$TFixedVarStr@$0ICF@@1@@Z` at `0x1800c4539`
- `mso40uiWin32Client!__imp_?WriteAttrHelper@Ofc@@YAXPEB_WHAEAVIWriterParams@1@AEBV?$TFixedVarStr@$0ICF@@1@@Z` at `0x1800c45e9`
- `mso40uiWin32Client!__imp_?FIsEmptyLocal@CPropertySetImpl@Tph@Ofc@@IEBA_NI@Z` at `0x1800c449e`
- `mso40uiWin32Client!__imp_?FIsEmptyLocal@CPropertySetImpl@Tph@Ofc@@IEBA_NI@Z` at `0x1800c4552`
- `mso40uiWin32Client!__imp_?FIsEmptyLocal@CPropertySetImpl@Tph@Ofc@@IEBA_NI@Z` at `0x1800c449e`
- `mso40uiWin32Client!__imp_?FIsEmptyLocal@CPropertySetImpl@Tph@Ofc@@IEBA_NI@Z` at `0x1800c4552`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800c44fe`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800c45b3`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800c44fe`
- `Mso20Win32Client!__imp_?Free@Memory@Mso@@YAXPEAX@Z` at `0x1800c45b3`

## pseudocode

```c
void __fastcall Ofc::TComplexTypeHelper<ODF::StyleRubyPropertiesContent>::FillWriters(
        Ofc::Tph::CPropertySetImpl *a1,
        Ofc::CNamespaceDeclarationTracker *a2,
        Ofc::CWriterEmit *a3,
        __int64 a4)
{
  void *v8; // rdx
  __int64 PropertyStgType; // rbp
  Mso::Memory *v10; // rcx
  void *v11; // rdx
  __int64 v12; // rsi
  Mso::Memory *v13; // rcx
  unsigned int v14; // eax
  unsigned int v15; // eax

  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 319);
  if ( !Ofc::Tph::CPropertySetImpl::FIsEmptyLocal(a1, 0) && Ofc::Tph::CPropertySetImpl::GetPropertyState(a1, 0) == 3 )
  {
    PropertyStgType = Ofc::Tph::CPropertySetImpl::GetPropertyStgType(a1, 0);
    if ( !PropertyStgType )
    {
      v14 = MsoReserveTag::operator unsigned int("wl5f");
      Ofc::CInvalidParamException::ThrowTag(v14);
      __debugbreak();
    }
    v10 = (Mso::Memory *)(*(_QWORD *)(a4 + 32) - 12LL);
    if ( *((_DWORD *)v10 + 1)
      && (*(_DWORD *)v10 == 1 || _InterlockedExchangeAdd((volatile signed __int32 *)v10, 0xFFFFFFFF) == 1)
      && v10 )
    {
      Mso::Memory::Free(v10, v8);
    }
    *(_QWORD *)(a4 + 32) = &dword_1801DBD74;
    *(_DWORD *)(a4 + 56) = 0;
    *(_WORD *)(a4 + 60) = 0;
    Ofc::TSimpleTypeHelper<enum ODF::RubyPosition>::ToString(PropertyStgType, a4, a4 + 32);
    Ofc::WriteAttrHelper(L"ruby-position", 319, a4, a4 + 32);
  }
  Ofc::CNamespaceDeclarationTracker::AddUri(a2, 319);
  if ( !Ofc::Tph::CPropertySetImpl::FIsEmptyLocal(a1, 1u) && Ofc::Tph::CPropertySetImpl::GetPropertyState(a1, 1) == 3 )
  {
    v12 = Ofc::Tph::CPropertySetImpl::GetPropertyStgType(a1, 1);
    if ( !v12 )
    {
      v15 = MsoReserveTag::operator unsigned int("wl5f");
      Ofc::CInvalidParamException::ThrowTag(v15);
      __debugbreak();
    }
    v13 = (Mso::Memory *)(*(_QWORD *)(a4 + 32) - 12LL);
    if ( *((_DWORD *)v13 + 1)
      && (*(_DWORD *)v13 == 1 || _InterlockedExchangeAdd((volatile signed __int32 *)v13, 0xFFFFFFFF) == 1) )
    {
      if ( v13 )
        Mso::Memory::Free(v13, v11);
    }
    *(_QWORD *)(a4 + 32) = &dword_1801DBD74;
    *(_DWORD *)(a4 + 56) = 0;
    *(_WORD *)(a4 + 60) = 0;
    Ofc::TSimpleTypeHelper<enum ODF::RubyAlign>::ToString(v12, a4, a4 + 32);
    Ofc::WriteAttrHelper(L"ruby-align", 319, a4, a4 + 32);
  }
  (**(void (__fastcall ***)(Ofc::CWriterEmit *, _QWORD))a3)(a3, *(_QWORD *)(a4 + 16));
  Ofc::CWriterEmit::EmitEndElement(a3);
}

```

## disassembly

```asm
0x1800c4460  mov     rax, rsp
0x1800c4463  mov     [rax+8], rbx
0x1800c4467  mov     [rax+10h], rbp
0x1800c446b  mov     [rax+18h], rsi
0x1800c446f  mov     [rax+20h], rdi
0x1800c4473  push    r12
0x1800c4475  push    r14
0x1800c4477  push    r15
0x1800c4479  sub     rsp, 20h
0x1800c447d  mov     r15, rdx
0x1800c4480  mov     rsi, rcx
0x1800c4483  mov     ebp, 13Fh
0x1800c4488  mov     rcx, r15
0x1800c448b  mov     edx, ebp
0x1800c448d  mov     rdi, r9
0x1800c4490  mov     r14, r8
0x1800c4493  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800c4499  xor     edx, edx
0x1800c449b  mov     rcx, rsi
0x1800c449e  call    cs:__imp_?FIsEmptyLocal@CPropertySetImpl@Tph@Ofc@@IEBA_NI@Z; Ofc::Tph::CPropertySetImpl::FIsEmptyLocal(uint)
0x1800c44a4  xor     r12d, r12d
0x1800c44a7  test    al, al
0x1800c44a9  jnz     loc_1800C453F
0x1800c44af  xor     edx, edx
0x1800c44b1  mov     rcx, rsi
0x1800c44b4  call    cs:__imp_?GetPropertyState@CPropertySetImpl@Tph@Ofc@@IEBA?AW4State@23@I@Z; Ofc::Tph::CPropertySetImpl::GetPropertyState(uint)
0x1800c44ba  cmp     rax, 3
0x1800c44be  jnz     short loc_1800C453F
0x1800c44c0  xor     edx, edx
0x1800c44c2  mov     rcx, rsi
0x1800c44c5  call    cs:__imp_?GetPropertyStgType@CPropertySetImpl@Tph@Ofc@@IEBAPEBV?$TAnyStorage@$07@3@I@Z; Ofc::Tph::CPropertySetImpl::GetPropertyStgType(uint)
0x1800c44cb  mov     rbp, rax
0x1800c44ce  test    rax, rax
0x1800c44d1  jz      loc_1800C462A
0x1800c44d7  lea     rbx, [rdi+20h]
0x1800c44db  mov     rcx, [rbx]
0x1800c44de  sub     rcx, 0Ch
0x1800c44e2  cmp     [rcx+4], r12d
0x1800c44e6  jz      short loc_1800C4504
0x1800c44e8  cmp     dword ptr [rcx], 1
0x1800c44eb  jz      short loc_1800C44F9
0x1800c44ed  or      eax, 0FFFFFFFFh
0x1800c44f0  lock xadd [rcx], eax
0x1800c44f4  cmp     eax, 1
0x1800c44f7  jnz     short loc_1800C4504
0x1800c44f9  test    rcx, rcx
0x1800c44fc  jz      short loc_1800C4504
0x1800c44fe  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800c4504  lea     rax, dword_1801DBD74
0x1800c450b  mov     r8, rbx
0x1800c450e  mov     [rbx], rax
0x1800c4511  mov     rdx, rdi
0x1800c4514  mov     rcx, rbp
0x1800c4517  mov     [rbx+18h], r12d
0x1800c451b  mov     [rbx+1Ch], r12w
0x1800c4520  call    ?ToString@?$TSimpleTypeHelper@W4RubyPosition@ODF@@@Ofc@@SAXAEBW4RubyPosition@ODF@@PEAVIWriterParams@2@AEAV?$TFixedVarStr@$0ICF@@2@@Z; Ofc::TSimpleTypeHelper<ODF::RubyPosition>::ToString(ODF::RubyPosition const &,Ofc::IWriterParams *,Ofc::TFixedVarStr<2085> &)
0x1800c4525  mov     ebp, 13Fh
0x1800c452a  lea     rcx, aRubyPosition; "ruby-position"
0x1800c4531  mov     edx, ebp
0x1800c4533  mov     r9, rbx
0x1800c4536  mov     r8, rdi
0x1800c4539  call    cs:__imp_?WriteAttrHelper@Ofc@@YAXPEB_WHAEAVIWriterParams@1@AEBV?$TFixedVarStr@$0ICF@@1@@Z; Ofc::WriteAttrHelper(wchar_t const *,int,Ofc::IWriterParams &,Ofc::TFixedVarStr<2085> const &)
0x1800c453f  mov     edx, ebp
0x1800c4541  mov     rcx, r15
0x1800c4544  call    cs:__imp_?AddUri@CNamespaceDeclarationTracker@Ofc@@QEAAXH@Z; Ofc::CNamespaceDeclarationTracker::AddUri(int)
0x1800c454a  mov     edx, 1
0x1800c454f  mov     rcx, rsi
0x1800c4552  call    cs:__imp_?FIsEmptyLocal@CPropertySetImpl@Tph@Ofc@@IEBA_NI@Z; Ofc::Tph::CPropertySetImpl::FIsEmptyLocal(uint)
0x1800c4558  test    al, al
0x1800c455a  jnz     loc_1800C45EF
0x1800c4560  mov     edx, 1
0x1800c4565  mov     rcx, rsi
0x1800c4568  call    cs:__imp_?GetPropertyState@CPropertySetImpl@Tph@Ofc@@IEBA?AW4State@23@I@Z; Ofc::Tph::CPropertySetImpl::GetPropertyState(uint)
0x1800c456e  cmp     rax, 3
0x1800c4572  jnz     short loc_1800C45EF
0x1800c4574  lea     edx, [rax-2]
0x1800c4577  mov     rcx, rsi
0x1800c457a  call    cs:__imp_?GetPropertyStgType@CPropertySetImpl@Tph@Ofc@@IEBAPEBV?$TAnyStorage@$07@3@I@Z; Ofc::Tph::CPropertySetImpl::GetPropertyStgType(uint)
0x1800c4580  mov     rsi, rax
0x1800c4583  test    rax, rax
0x1800c4586  jz      loc_1800C463E
0x1800c458c  lea     rbx, [rdi+20h]
0x1800c4590  mov     rcx, [rbx]
0x1800c4593  sub     rcx, 0Ch
0x1800c4597  cmp     [rcx+4], r12d
0x1800c459b  jz      short loc_1800C45B9
0x1800c459d  cmp     dword ptr [rcx], 1
0x1800c45a0  jz      short loc_1800C45AE
0x1800c45a2  or      eax, 0FFFFFFFFh
0x1800c45a5  lock xadd [rcx], eax
0x1800c45a9  cmp     eax, 1
0x1800c45ac  jnz     short loc_1800C45B9
0x1800c45ae  test    rcx, rcx
0x1800c45b1  jz      short loc_1800C45B9
0x1800c45b3  call    cs:__imp_?Free@Memory@Mso@@YAXPEAX@Z; Mso::Memory::Free(void *)
0x1800c45b9  lea     rax, dword_1801DBD74
0x1800c45c0  mov     r8, rbx
0x1800c45c3  mov     [rbx], rax
0x1800c45c6  mov     rdx, rdi
0x1800c45c9  mov     rcx, rsi
0x1800c45cc  mov     [rbx+18h], r12d
0x1800c45d0  mov     [rbx+1Ch], r12w
0x1800c45d5  call    ?ToString@?$TSimpleTypeHelper@W4RubyAlign@ODF@@@Ofc@@SAXAEBW4RubyAlign@ODF@@PEAVIWriterParams@2@AEAV?$TFixedVarStr@$0ICF@@2@@Z; Ofc::TSimpleTypeHelper<ODF::RubyAlign>::ToString(ODF::RubyAlign const &,Ofc::IWriterParams *,Ofc::TFixedVarStr<2085> &)
0x1800c45da  mov     r9, rbx
0x1800c45dd  lea     rcx, aRubyAlign; "ruby-align"
0x1800c45e4  mov     r8, rdi
0x1800c45e7  mov     edx, ebp
0x1800c45e9  call    cs:__imp_?WriteAttrHelper@Ofc@@YAXPEB_WHAEAVIWriterParams@1@AEBV?$TFixedVarStr@$0ICF@@1@@Z; Ofc::WriteAttrHelper(wchar_t const *,int,Ofc::IWriterParams &,Ofc::TFixedVarStr<2085> const &)
0x1800c45ef  mov     rax, [r14]
0x1800c45f2  mov     rcx, r14
0x1800c45f5  mov     rdx, [rdi+10h]
0x1800c45f9  mov     rax, [rax]
0x1800c45fc  call    cs:__guard_dispatch_icall_fptr
0x1800c4602  mov     rcx, r14
0x1800c4605  mov     rbx, [rsp+38h+arg_0]
0x1800c460a  mov     rbp, [rsp+38h+arg_8]
0x1800c460f  mov     rsi, [rsp+38h+arg_10]
0x1800c4614  mov     rdi, [rsp+38h+arg_18]
0x1800c4619  add     rsp, 20h
0x1800c461d  pop     r15
0x1800c461f  pop     r14
0x1800c4621  pop     r12
0x1800c4623  jmp     cs:__imp_?EmitEndElement@CWriterEmit@Ofc@@QEAAXXZ; Ofc::CWriterEmit::EmitEndElement(void)
0x1800c462a  lea     rcx, ?tag_f5lw@Ofc@@3VMsoReserveTag@@B; "wl5f"
0x1800c4631  call    ??BMsoReserveTag@@QEBAIXZ; MsoReserveTag::operator uint(void)
0x1800c4636  mov     ecx, eax; unsigned int
0x1800c4638  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x1800c463d  int     3; Trap to Debugger
0x1800c463e  lea     rcx, ?tag_f5lw@Ofc@@3VMsoReserveTag@@B; "wl5f"
0x1800c4645  call    ??BMsoReserveTag@@QEBAIXZ; MsoReserveTag::operator uint(void)
0x1800c464a  mov     ecx, eax; unsigned int
0x1800c464c  call    ?ThrowTag@CInvalidParamException@Ofc@@SAXK@Z; Ofc::CInvalidParamException::ThrowTag(ulong)
0x1800c4651  int     3; Trap to Debugger
```
