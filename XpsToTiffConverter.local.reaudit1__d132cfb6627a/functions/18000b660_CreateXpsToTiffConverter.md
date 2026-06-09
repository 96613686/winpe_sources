# CreateXpsToTiffConverter

- ea: `0x18000b660`
- end: `0x18000b716`
- name: `CreateXpsToTiffConverter`
- size: `182`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180001aac`
- `0x1800020e4`
- `0x18000b660`

## pseudocode

```c
__int64 __fastcall CreateXpsToTiffConverter(_QWORD *a1)
{
  _QWORD *v2; // rbx
  const char *v3; // r9
  __int64 result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *a1 = 0;
  try
  {
    v2 = operator new(0xB8u);
    memset_0(v2 + 1, 0, 0xB0u);
    *v2 = &winrt::impl::producers_base<XpsToTiffConverter::XpsToTiffConverter,std::tuple<IPDLConverter>>::`vftable';
    _InterlockedIncrement(&`winrt::get_module_lock'::`2'::s_lock);
    v2[2] = 1;
    *((_DWORD *)v2 + 6) = 0;
    v2[4] = 0;
    v2[5] = 0;
    v2[6] = 0;
    v2[7] = 0;
    v2[8] = 0;
    v2[9] = 0;
    v2[10] = 0;
    *v2 = &winrt::impl::heap_implements<XpsToTiffConverter::XpsToTiffConverter>::`vftable'{for `winrt::impl::producers_base<XpsToTiffConverter::XpsToTiffConverter,std::tuple<IPDLConverter>>'};
    v2[1] = &winrt::impl::heap_implements<XpsToTiffConverter::XpsToTiffConverter>::`vftable'{for `winrt::impl::root_implements<XpsToTiffConverter::XpsToTiffConverter,IPDLConverter>'};
    *a1 = v2;
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x8C,
                           (unsigned int)"onecoreuap\\printscan\\print\\drivers\\renderfilters\\xpstotiffconverter\\xpsto"
                                         "tiffconverter.cpp",
                           v3);
  }
  return result;
}

```

## disassembly

```asm
0x18000b660  mov     [rsp+arg_8], rbx
0x18000b665  push    rdi
0x18000b666  sub     rsp, 20h
0x18000b66a  mov     rdi, rcx
0x18000b66d  mov     qword ptr [rcx], 0
0x18000b674  mov     ecx, 0B8h; Size
0x18000b679  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b67e  mov     rbx, rax
0x18000b681  lea     rcx, [rax+8]; void *
0x18000b685  xor     edx, edx; Val
0x18000b687  mov     r8d, 0B0h; Size
0x18000b68d  call    memset_0
0x18000b692  lea     rax, ??_7?$producers_base@UXpsToTiffConverter@1@V?$tuple@UIPDLConverter@@@std@@@impl@winrt@@6B@; const winrt::impl::producers_base<XpsToTiffConverter::XpsToTiffConverter,std::tuple<IPDLConverter>>::`vftable'
0x18000b699  mov     [rbx], rax
0x18000b69c  lock inc cs:?s_lock@?1??get_module_lock@winrt@@YAAEAUatomic_ref_count@impl@2@XZ@4U342@A; winrt::impl::atomic_ref_count `winrt::get_module_lock(void)'::`2'::s_lock
0x18000b6a3  mov     qword ptr [rbx+10h], 1
0x18000b6ab  mov     dword ptr [rbx+18h], 0
0x18000b6b2  mov     qword ptr [rbx+20h], 0
0x18000b6ba  mov     qword ptr [rbx+28h], 0
0x18000b6c2  mov     qword ptr [rbx+30h], 0
0x18000b6ca  mov     qword ptr [rbx+38h], 0
0x18000b6d2  mov     qword ptr [rbx+40h], 0
0x18000b6da  mov     qword ptr [rbx+48h], 0
0x18000b6e2  mov     qword ptr [rbx+50h], 0
0x18000b6ea  lea     rax, ??_7?$heap_implements@UXpsToTiffConverter@1@@impl@winrt@@6B?$producers_base@UXpsToTiffConverter@1@V?$tuple@UIPDLConverter@@@std@@@12@@; const winrt::impl::heap_implements<XpsToTiffConverter::XpsToTiffConverter>::`vftable'{for `winrt::impl::producers_base<XpsToTiffConverter::XpsToTiffConverter,std::tuple<IPDLConverter>>'}
0x18000b6f1  mov     [rbx], rax
0x18000b6f4  lea     rax, ??_7?$heap_implements@UXpsToTiffConverter@1@@impl@winrt@@6B?$root_implements@UXpsToTiffConverter@1@UIPDLConverter@@@12@@; const winrt::impl::heap_implements<XpsToTiffConverter::XpsToTiffConverter>::`vftable'{for `winrt::impl::root_implements<XpsToTiffConverter::XpsToTiffConverter,IPDLConverter>'}
0x18000b6fb  mov     [rbx+8], rax
0x18000b6ff  mov     [rdi], rbx
0x18000b702  xor     eax, eax
0x18000b704  jmp     short loc_18000B70A
0x18000b706  mov     eax, [rsp+28h+arg_0]
0x18000b70a  mov     rbx, [rsp+28h+arg_8]
0x18000b70f  add     rsp, 20h
0x18000b713  pop     rdi
0x18000b714  retn
```
