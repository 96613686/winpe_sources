# CArray<_com_ptr_t<_com_IIID<NaturalLanguage6::ISentence,&__s_GUID const _GUID_f0c13a7a_199b_44be_8492_f91eaa50f943>>,CArrayAllocator_malloc>::~CArray<_com_ptr_t<_com_IIID<NaturalLanguage6::ISentence,&__s_GUID const _GUID_f0c13a7a_199b_44be_8492_f91eaa50f943>>,CArrayAllocator_malloc>(void)

- ea: `0x180003a34`
- end: `0x180003a67`
- name: `??1?$CArray@V?$_com_ptr_t@V?$_com_IIID@UISentence@NaturalLanguage6@@$1?_GUID_f0c13a7a_199b_44be_8492_f91eaa50f943@@3U__s_GUID@@B@@@@VCArrayAllocator_malloc@@@@QEAA@XZ`
- size: `51`
- prototype: `void __fastcall(void **)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003a0c`
- `0x180015ed8`
- `0x180019e90`
- `0x18009e884`
- `0x18009fa47`
- `0x18009fbc3`
- `0x18009fd92`

## callees

- `0x180003a34`
- `0x180003e28`

## import_xrefs

- `msvcrt!free` at `0x180003a5a`
- `msvcrt!free` at `0x180003a5a`

## pseudocode

```c
void __fastcall CArray<_com_ptr_t<_com_IIID<NaturalLanguage6::ISentence,&__s_GUID const _GUID_f0c13a7a_199b_44be_8492_f91eaa50f943>>,CArrayAllocator_malloc>::~CArray<_com_ptr_t<_com_IIID<NaturalLanguage6::ISentence,&__s_GUID const _GUID_f0c13a7a_199b_44be_8492_f91eaa50f943>>,CArrayAllocator_malloc>(
        void **a1)
{
  CArray<_com_ptr_t<_com_IIID<NaturalLanguage6::ILexicon,&__s_GUID const _GUID_004cd7e2_8b63_4ef9_8d46_080cdbbe47af>>,CArrayAllocator_malloc>::DestructElements(
    a1,
    *a1,
    a1[1]);
  if ( *a1 )
    free(*a1);
}

```

## disassembly

```asm
0x180003a34  push    rbx
0x180003a36  sub     rsp, 30h
0x180003a3a  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x180003a43  mov     rbx, rcx
0x180003a46  mov     r8, [rcx+8]
0x180003a4a  mov     rdx, [rcx]
0x180003a4d  call    ?DestructElements@?$CArray@V?$_com_ptr_t@V?$_com_IIID@UILexicon@NaturalLanguage6@@$1?_GUID_004cd7e2_8b63_4ef9_8d46_080cdbbe47af@@3U__s_GUID@@B@@@@VCArrayAllocator_malloc@@@@AEAAXPEAX_K@Z; CArray<_com_ptr_t<_com_IIID<NaturalLanguage6::ILexicon,&__s_GUID const _GUID_004cd7e2_8b63_4ef9_8d46_080cdbbe47af>>,CArrayAllocator_malloc>::DestructElements(void *,unsigned __int64)
0x180003a52  mov     rcx, [rbx]; Block
0x180003a55  test    rcx, rcx
0x180003a58  jz      short loc_180003A61
0x180003a5a  call    cs:__imp_free
0x180003a60  nop
0x180003a61  add     rsp, 30h
0x180003a65  pop     rbx
0x180003a66  retn
```
