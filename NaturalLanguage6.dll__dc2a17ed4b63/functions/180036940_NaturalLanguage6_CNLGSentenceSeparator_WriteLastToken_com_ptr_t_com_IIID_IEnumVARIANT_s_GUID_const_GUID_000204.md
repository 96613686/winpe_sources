# NaturalLanguage6::CNLGSentenceSeparator::WriteLastToken(_com_ptr_t<_com_IIID<IEnumVARIANT,&__s_GUID const _GUID_00020404_0000_0000_c000_000000000046>>,_com_ptr_t<_com_IIID<NaturalLanguage6::ISentence,&__s_GUID const _GUID_f0c13a7a_199b_44be_8492_f91eaa50f943>> &,_variant_t &,ulong &,tagTEXT_SOURCE *,IWordSink *,bool &)

- ea: `0x180036940`
- end: `0x180036a62`
- name: `?WriteLastToken@CNLGSentenceSeparator@NaturalLanguage6@@AEAAJV?$_com_ptr_t@V?$_com_IIID@UIEnumVARIANT@@$1?_GUID_00020404_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAV?$_com_ptr_t@V?$_com_IIID@UISentence@NaturalLanguage6@@$1?_GUID_f0c13a7a_199b_44be_8492_f91eaa50f943@@3U__s_GUID@@B@@@@AEAV_variant_t@@AEAKPEAUtagTEXT_SOURCE@@PEAUIWordSink@@AEA_N@Z`
- size: `290`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, struct tagTEXT_SOURCE *, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180005380`

## callees

- `0x180003edc`
- `0x180005160`
- `0x180005ad0`
- `0x180005b50`
- `0x18002bf50`
- `0x18002c170`
- `0x18002c2a0`
- `0x18002cd48`
- `0x180036940`
- `0x1800b0010`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall NaturalLanguage6::CNLGSentenceSeparator::WriteLastToken(
        NaturalLanguage6::CNLGSentenceSeparator *a1,
        __int64 *a2,
        __int64 *a3,
        VARIANTARG *a4,
        _DWORD *a5,
        struct tagTEXT_SOURCE *a6,
        __int64 a7,
        _BYTE *a8)
{
  int updated; // edi
  __int64 v13; // rax
  __int64 v14; // rcx
  __int64 v15; // r8
  struct IUnknown *v16; // rax
  struct IUnknown *v17; // rax
  struct IUnknown **Item; // rax
  __int64 v20[2]; // [rsp+30h] [rbp-58h] BYREF
  __int64 *v21; // [rsp+40h] [rbp-48h]

  v20[1] = -2;
  updated = NaturalLanguage6::CNLGSentenceSeparator::UpdateTextChunkBuffer(a1, a6);
  if ( updated >= 0 )
  {
    v13 = _com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>::operator->(a2);
    updated = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 40LL))(v13);
    if ( updated >= 0 )
    {
      v21 = v20;
      v20[0] = *a2;
      _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(v20);
      updated = NaturalLanguage6::CNLGSentenceSeparator::AdvanceSentencePointer(v14, v20, v15, a4, (__int64)a5);
      if ( updated >= 0 )
      {
        if ( *a5 )
        {
          if ( *a3 )
          {
            v16 = (struct IUnknown *)_com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>::operator->(a3);
            if ( (int)NaturalLanguage6::ISentence::GetCount(v16) > 0 )
            {
              v21 = v20;
              v17 = (struct IUnknown *)_com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>::operator->(a3);
              Item = (struct IUnknown **)NaturalLanguage6::ISentence::GetItem(v17);
              updated = NaturalLanguage6::CNLGSentenceSeparator::PutSegment((__int64)a1, (__int64)a6, a7, Item, a8);
            }
          }
        }
      }
    }
  }
  _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(a2);
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180036940  mov     [rsp+arg_8], rdx
0x180036945  push    rbx
0x180036946  push    rbp
0x180036947  push    rsi
0x180036948  push    rdi
0x180036949  push    r14
0x18003694b  push    r15
0x18003694d  sub     rsp, 58h
0x180036951  mov     [rsp+88h+var_50], 0FFFFFFFFFFFFFFFEh
0x18003695a  mov     r14, r9
0x18003695d  mov     rsi, r8
0x180036960  mov     rbx, rdx
0x180036963  mov     r15, rcx
0x180036966  mov     rdx, [rsp+88h+arg_28]; struct tagTEXT_SOURCE *
0x18003696e  call    ?UpdateTextChunkBuffer@CNLGSentenceSeparator@NaturalLanguage6@@AEAAJPEAUtagTEXT_SOURCE@@@Z; NaturalLanguage6::CNLGSentenceSeparator::UpdateTextChunkBuffer(tagTEXT_SOURCE *)
0x180036973  mov     edi, eax
0x180036975  test    eax, eax
0x180036977  js      loc_180036A4B
0x18003697d  mov     rcx, rbx
0x180036980  call    ??C?$_com_ptr_t@V?$_com_IIID@UITextSegment@NaturalLanguage6@@$1?_GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56@@3U__s_GUID@@B@@@@QEBAPEAUITextSegment@NaturalLanguage6@@XZ; _com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>::operator->(void)
0x180036985  mov     rdx, rax
0x180036988  mov     rcx, [rax]
0x18003698b  mov     rax, [rcx+28h]
0x18003698f  mov     rcx, rdx
0x180036992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180036997  mov     edi, eax
0x180036999  test    eax, eax
0x18003699b  js      loc_180036A4B
0x1800369a1  lea     rax, [rsp+88h+var_58]
0x1800369a6  mov     [rsp+88h+var_48], rax
0x1800369ab  mov     rax, [rbx]
0x1800369ae  mov     [rsp+88h+var_58], rax
0x1800369b3  lea     rcx, [rsp+88h+var_58]
0x1800369b8  call    ?_AddRef@?$_com_ptr_t@V?$_com_IIID@UCUserData@@$1?_GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa@@3U__s_GUID@@B@@@@AEAAXXZ; _com_ptr_t<_com_IIID<CUserData,&__s_GUID const _GUID_b7495f50_7e10_4402_a951_3d604dd2cdfa>>::_AddRef(void)
0x1800369bd  nop
0x1800369be  mov     rbp, [rsp+88h+arg_20]
0x1800369c6  mov     [rsp+88h+var_68], rbp
0x1800369cb  mov     r9, r14
0x1800369ce  lea     rdx, [rsp+88h+var_58]
0x1800369d3  call    ?AdvanceSentencePointer@CNLGSentenceSeparator@NaturalLanguage6@@AEAAJV?$_com_ptr_t@V?$_com_IIID@UIEnumVARIANT@@$1?_GUID_00020404_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@AEAV?$_com_ptr_t@V?$_com_IIID@UISentence@NaturalLanguage6@@$1?_GUID_f0c13a7a_199b_44be_8492_f91eaa50f943@@3U__s_GUID@@B@@@@AEAV_variant_t@@AEAK@Z; NaturalLanguage6::CNLGSentenceSeparator::AdvanceSentencePointer(_com_ptr_t<_com_IIID<IEnumVARIANT,&__s_GUID const _GUID_00020404_0000_0000_c000_000000000046>>,_com_ptr_t<_com_IIID<NaturalLanguage6::ISentence,&__s_GUID const _GUID_f0c13a7a_199b_44be_8492_f91eaa50f943>> &,_variant_t &,ulong &)
0x1800369d8  mov     edi, eax
0x1800369da  test    eax, eax
0x1800369dc  js      short loc_180036A4B
0x1800369de  cmp     dword ptr [rbp+0], 0
0x1800369e2  jz      short loc_180036A4B
0x1800369e4  cmp     qword ptr [rsi], 0
0x1800369e8  jz      short loc_180036A4B
0x1800369ea  mov     rcx, rsi
0x1800369ed  call    ??C?$_com_ptr_t@V?$_com_IIID@UITextSegment@NaturalLanguage6@@$1?_GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56@@3U__s_GUID@@B@@@@QEBAPEAUITextSegment@NaturalLanguage6@@XZ; _com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>::operator->(void)
0x1800369f2  mov     rcx, rax; this
0x1800369f5  call    ?GetCount@ISentence@NaturalLanguage6@@QEAAJXZ; NaturalLanguage6::ISentence::GetCount(void)
0x1800369fa  test    eax, eax
0x1800369fc  jle     short loc_180036A4B
0x1800369fe  lea     rax, [rsp+88h+var_58]
0x180036a03  mov     [rsp+88h+var_48], rax
0x180036a08  mov     rcx, rsi
0x180036a0b  call    ??C?$_com_ptr_t@V?$_com_IIID@UITextSegment@NaturalLanguage6@@$1?_GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56@@3U__s_GUID@@B@@@@QEBAPEAUITextSegment@NaturalLanguage6@@XZ; _com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>::operator->(void)
0x180036a10  xor     r8d, r8d
0x180036a13  lea     rdx, [rsp+88h+var_58]
0x180036a18  mov     rcx, rax; struct IUnknown *
0x180036a1b  call    ?GetItem@ISentence@NaturalLanguage6@@QEAA?AV?$_com_ptr_t@V?$_com_IIID@UITextSegment@NaturalLanguage6@@$1?_GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56@@3U__s_GUID@@B@@@@J@Z; NaturalLanguage6::ISentence::GetItem(long)
0x180036a20  nop
0x180036a21  mov     rcx, [rsp+88h+arg_38]
0x180036a29  mov     [rsp+88h+var_68], rcx
0x180036a2e  mov     r9, rax
0x180036a31  mov     r8, [rsp+88h+arg_30]
0x180036a39  mov     rdx, [rsp+88h+arg_28]
0x180036a41  mov     rcx, r15
0x180036a44  call    ?PutSegment@CNLGSentenceSeparator@NaturalLanguage6@@AEAAJPEAUtagTEXT_SOURCE@@PEAUIWordSink@@V?$_com_ptr_t@V?$_com_IIID@UITextSegment@NaturalLanguage6@@$1?_GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56@@3U__s_GUID@@B@@@@AEA_N@Z; NaturalLanguage6::CNLGSentenceSeparator::PutSegment(tagTEXT_SOURCE *,IWordSink *,_com_ptr_t<_com_IIID<NaturalLanguage6::ITextSegment,&__s_GUID const _GUID_af4656b8_5e5e_4fb2_a2d8_1e977e549a56>>,bool &)
0x180036a49  mov     edi, eax
0x180036a4b  mov     rcx, rbx
0x180036a4e  call    ??1?$_com_ptr_t@V?$_com_IIID@UIClassFactory@@$1?_GUID_00000001_0000_0000_c000_000000000046@@3U__s_GUID@@B@@@@QEAA@XZ; _com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>::~_com_ptr_t<_com_IIID<IClassFactory,&__s_GUID const _GUID_00000001_0000_0000_c000_000000000046>>(void)
0x180036a53  mov     eax, edi
0x180036a55  add     rsp, 58h
0x180036a59  pop     r15
0x180036a5b  pop     r14
0x180036a5d  pop     rdi
0x180036a5e  pop     rsi
0x180036a5f  pop     rbp
0x180036a60  pop     rbx
0x180036a61  retn
```
