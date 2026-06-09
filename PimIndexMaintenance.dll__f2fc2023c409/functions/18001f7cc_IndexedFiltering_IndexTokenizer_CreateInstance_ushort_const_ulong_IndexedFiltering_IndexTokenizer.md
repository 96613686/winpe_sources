# IndexedFiltering::IndexTokenizer::CreateInstance(ushort const *,ulong,IndexedFiltering::IndexTokenizer * *)

- ea: `0x18001f7cc`
- end: `0x18001f8ce`
- name: `?CreateInstance@IndexTokenizer@IndexedFiltering@@SAJPEBGKPEAPEAV12@@Z`
- size: `258`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned int, struct IndexedFiltering::IndexTokenizer **)`
- caller_count: `2`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001c460`
- `0x18001cb80`

## callees

- `0x1800012fc`
- `0x180002da8`
- `0x180003f90`
- `0x18001f3c8`
- `0x18001f7cc`
- `0x18001fee4`
- `0x180020024`
- `0x180022010`

## string_xrefs

- `0x18001f7ed`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indextokenizer.cpp`
- `0x18001f8af`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\indextokenizer.cpp`

## pseudocode

```c
__int64 __fastcall IndexedFiltering::IndexTokenizer::CreateInstance(
        const unsigned __int16 *a1,
        unsigned int a2,
        struct IndexedFiltering::IndexTokenizer **a3)
{
  int v6; // edi
  _QWORD *v7; // rax
  __int64 v8; // rdx
  _QWORD *v9; // rbx
  __int64 v10; // rdx
  __int64 v11; // rcx

  if ( a3 )
  {
    v7 = operator new(0x68u);
    v9 = v7;
    if ( v7 )
    {
      v7[3] = 0;
      *v7 = &_CUnknownBase::`vftable';
      *((_DWORD *)v7 + 2) = 1;
      *v7 = &IndexedFiltering::IndexTokenizer::`vftable';
      v7[4] = 0;
      v7[5] = 0;
      utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>(v7 + 6);
      v9[9] = 0;
      *((_WORD *)v9 + 40) = 0;
      *((_DWORD *)v9 + 24) = 0;
      if ( *((_DWORD *)v9 + 2) != 1 )
        Log_AssertionEvent_6(v11, v10, 45);
      v6 = IndexedFiltering::IndexTokenizer::Init((IndexedFiltering::IndexTokenizer *)v9, a1, a2);
      if ( v6 < 0 )
        (*(void (__fastcall **)(_QWORD *, __int64))(*v9 + 24LL))(v9, 1);
      else
        *a3 = (struct IndexedFiltering::IndexTokenizer *)v9;
    }
    else
    {
      v6 = -2147024882;
      Log_HREvent_9(
        2147942414LL,
        v8,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indextokenizer.cpp",
        44);
    }
  }
  else
  {
    v6 = -2147024809;
    Log_HREvent(
      2147942487LL,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\indextokenizer.cpp",
      41);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001f7cc  push    rbx
0x18001f7ce  push    rbp
0x18001f7cf  push    rsi
0x18001f7d0  push    rdi
0x18001f7d1  sub     rsp, 38h
0x18001f7d5  mov     rsi, r8
0x18001f7d8  mov     edi, edx
0x18001f7da  mov     rbp, rcx
0x18001f7dd  test    r8, r8
0x18001f7e0  jnz     short loc_18001F801
0x18001f7e2  lea     r9d, [r8+29h]
0x18001f7e6  mov     edi, 80070057h
0x18001f7eb  mov     ecx, edi
0x18001f7ed  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001f7f4  lea     edx, [rsi+1]
0x18001f7f7  call    Log_HREvent
0x18001f7fc  jmp     loc_18001F8C3
0x18001f801  mov     ecx, 68h ; 'h'; Size
0x18001f806  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f80b  mov     rbx, rax
0x18001f80e  test    rax, rax
0x18001f811  jz      loc_18001F8AA
0x18001f817  lea     rax, ??_7_CUnknownBase@@6B@; const _CUnknownBase::`vftable'
0x18001f81e  mov     qword ptr [rbx+18h], 0
0x18001f826  mov     [rbx], rax
0x18001f829  lea     rcx, [rbx+30h]
0x18001f82d  lea     rax, ??_7IndexTokenizer@IndexedFiltering@@6B@; const IndexedFiltering::IndexTokenizer::`vftable'
0x18001f834  mov     dword ptr [rbx+8], 1
0x18001f83b  mov     [rbx], rax
0x18001f83e  mov     qword ptr [rbx+20h], 0
0x18001f846  mov     qword ptr [rbx+28h], 0
0x18001f84e  call    ??0?$vector@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@V?$allocator@U?$pair@UMetadataInfo@@V?$CComPtr@UIPOItemMetadata@@@ATL@@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>::vector<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>,utl::allocator<utl::pair<MetadataInfo,ATL::CComPtr<IPOItemMetadata>>>>(void)
0x18001f853  xor     eax, eax
0x18001f855  mov     qword ptr [rbx+48h], 0
0x18001f85d  mov     [rbx+50h], ax
0x18001f861  mov     dword ptr [rbx+60h], 0
0x18001f868  mov     eax, [rbx+8]
0x18001f86b  cmp     eax, 1
0x18001f86e  jz      short loc_18001F87B
0x18001f870  mov     r8d, 2Dh ; '-'
0x18001f876  call    Log_AssertionEvent_6
0x18001f87b  mov     r8d, edi; unsigned int
0x18001f87e  mov     rdx, rbp; unsigned __int16 *
0x18001f881  mov     rcx, rbx; this
0x18001f884  call    ?Init@IndexTokenizer@IndexedFiltering@@IEAAJPEBGK@Z; IndexedFiltering::IndexTokenizer::Init(ushort const *,ulong)
0x18001f889  mov     edi, eax
0x18001f88b  test    eax, eax
0x18001f88d  js      short loc_18001F894
0x18001f88f  mov     [rsi], rbx
0x18001f892  jmp     short loc_18001F8C3
0x18001f894  mov     rax, [rbx]
0x18001f897  mov     edx, 1
0x18001f89c  mov     rcx, rbx
0x18001f89f  mov     rax, [rax+18h]
0x18001f8a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8a8  jmp     short loc_18001F8C3
0x18001f8aa  mov     edi, 8007000Eh
0x18001f8af  lea     r8, aOnecoreuapBase_5; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001f8b6  mov     ecx, edi
0x18001f8b8  mov     r9d, 2Ch ; ','
0x18001f8be  call    Log_HREvent_9
0x18001f8c3  mov     eax, edi
0x18001f8c5  add     rsp, 38h
0x18001f8c9  pop     rdi
0x18001f8ca  pop     rsi
0x18001f8cb  pop     rbp
0x18001f8cc  pop     rbx
0x18001f8cd  retn
```
