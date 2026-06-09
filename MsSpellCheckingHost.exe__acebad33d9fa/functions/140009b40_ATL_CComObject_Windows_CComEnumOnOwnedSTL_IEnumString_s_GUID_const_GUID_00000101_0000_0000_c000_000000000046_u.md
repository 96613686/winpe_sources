# ATL::CComObject<Windows::CComEnumOnOwnedSTL<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,ushort *,Windows::CopyFromPairWstringToLpolestr,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,ATL::CComMultiThreadModel>>::CreateInstance(ATL::CComObject<Windows::CComEnumOnOwnedSTL<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,ushort *,Windows::CopyFromPairWstringToLpolestr,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,ATL::CComMultiThreadModel>> * *)

- ea: `0x140009b40`
- end: `0x140009c50`
- name: `?CreateInstance@?$CComObject@V?$CComEnumOnOwnedSTL@UIEnumString@@$1?_GUID_00000101_0000_0000_c000_000000000046@@3U__s_GUID@@BPEAGVCopyFromPairWstringToLpolestr@Windows@@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@VCComMultiThreadModel@ATL@@@Windows@@@ATL@@SAJPEAPEAV12@@Z`
- size: `272`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140009850`
- `0x14000afe0`

## callees

- `0x1400014fc`
- `0x140003dfc`
- `0x140009b40`
- `0x14000e94c`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<Windows::CComEnumOnOwnedSTL<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,unsigned short *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>,ATL::CComMultiThreadModel>>::CreateInstance(
        _QWORD *a1)
{
  _QWORD *v1; // r14
  unsigned int v3; // esi
  _QWORD *v4; // rax
  _QWORD *v5; // rdi
  int v6; // ecx
  int v7; // eax
  _QWORD *v9; // [rsp+70h] [rbp+18h]

  v1 = a1;
  if ( !a1 )
    return 2147500035LL;
  try
  {
    *a1 = 0;
    v3 = -2147024882;
    v4 = operator new(0x58u);
    v5 = v4;
    if ( v4 )
    {
      v4[1] = 0;
      v4[2] = 0;
      v4[1] = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,std::wstring>>>::_Buyheadnode();
      v5[3] = 0;
      *((_DWORD *)v5 + 8) = 0;
      *(_OWORD *)(v5 + 5) = 0;
      *(_OWORD *)(v5 + 7) = 0;
      v5[9] = 0;
      *((_BYTE *)v5 + 80) = 0;
      *v5 = &ATL::CComObject<Windows::CComEnumOnOwnedSTL<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,unsigned short *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>,ATL::CComMultiThreadModel>>::`vftable';
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    }
    v9 = v5;
  }
  catch ( ... )
  {
    v1 = a1;
    v3 = -2147024882;
    v5 = v9;
  }
  if ( v5 )
  {
    v6 = ATL::CComCriticalSection::Init((ATL::CComCriticalSection *)(v5 + 5));
    if ( v6 >= 0 )
      *((_BYTE *)v5 + 80) = 1;
    v7 = 0;
    if ( v6 < 0 )
      v7 = v6;
    v3 = 0;
    if ( v7 < 0 )
      v3 = v7;
    if ( v3 )
    {
      (*(void (__fastcall **)(_QWORD *, __int64))(*v5 + 56LL))(v5, 1);
      v5 = 0;
    }
  }
  *v1 = v5;
  return v3;
}

```

## disassembly

```asm
0x140009b40  mov     [rsp+arg_0], rcx
0x140009b45  push    rsi
0x140009b46  push    rdi
0x140009b47  push    r14
0x140009b49  push    r15
0x140009b4b  sub     rsp, 38h
0x140009b4f  mov     r14, rcx
0x140009b52  test    rcx, rcx
0x140009b55  jnz     short loc_140009B61
0x140009b57  mov     eax, 80004003h
0x140009b5c  jmp     loc_140009C45
0x140009b61  mov     qword ptr [rcx], 0
0x140009b68  mov     esi, 8007000Eh
0x140009b6d  mov     [rsp+58h+arg_8], esi
0x140009b71  mov     [rsp+58h+arg_10], 0
0x140009b7a  mov     ecx, 58h ; 'X'; Size
0x140009b7f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140009b84  mov     rdi, rax
0x140009b87  mov     [rsp+58h+arg_18], rax
0x140009b8c  test    rdi, rdi
0x140009b8f  jz      short loc_140009BEB
0x140009b91  mov     qword ptr [rax+8], 0
0x140009b99  mov     qword ptr [rax+10h], 0
0x140009ba1  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,std::wstring>>>::_Buyheadnode(void)
0x140009ba6  mov     [rdi+8], rax
0x140009baa  mov     qword ptr [rdi+18h], 0
0x140009bb2  mov     dword ptr [rdi+20h], 0
0x140009bb9  xorps   xmm0, xmm0
0x140009bbc  xor     eax, eax
0x140009bbe  movups  xmmword ptr [rdi+28h], xmm0
0x140009bc2  movups  xmmword ptr [rdi+38h], xmm0
0x140009bc6  mov     [rdi+48h], rax
0x140009bca  mov     [rdi+50h], al
0x140009bcd  lea     rax, ??_7?$CComObject@V?$CComEnumOnOwnedSTL@UIEnumString@@$1?_GUID_00000101_0000_0000_c000_000000000046@@3U__s_GUID@@BPEAGVCopyFromPairWstringToLpolestr@Windows@@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@VCComMultiThreadModel@ATL@@@Windows@@@ATL@@6B@; const ATL::CComObject<Windows::CComEnumOnOwnedSTL<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,ushort *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>,ATL::CComMultiThreadModel>>::`vftable'
0x140009bd4  mov     [rdi], rax
0x140009bd7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x140009bde  mov     rax, [rcx]
0x140009be1  mov     rax, [rax+8]
0x140009be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009bea  nop
0x140009beb  mov     [rsp+58h+arg_10], rdi
0x140009bf0  jmp     short loc_140009C00
0x140009bf2  mov     r14, [rsp+58h+arg_0]
0x140009bf7  mov     esi, [rsp+58h+arg_8]
0x140009bfb  mov     rdi, [rsp+58h+arg_10]
0x140009c00  test    rdi, rdi
0x140009c03  jz      short loc_140009C40
0x140009c05  lea     rcx, [rdi+28h]; this
0x140009c09  call    ?Init@CComCriticalSection@ATL@@QEAAJXZ; ATL::CComCriticalSection::Init(void)
0x140009c0e  mov     ecx, eax
0x140009c10  test    eax, eax
0x140009c12  js      short loc_140009C18
0x140009c14  mov     byte ptr [rdi+50h], 1
0x140009c18  xor     eax, eax
0x140009c1a  test    ecx, ecx
0x140009c1c  cmovs   eax, ecx
0x140009c1f  xor     esi, esi
0x140009c21  test    eax, eax
0x140009c23  cmovs   esi, eax
0x140009c26  test    esi, esi
0x140009c28  jz      short loc_140009C40
0x140009c2a  mov     rax, [rdi]
0x140009c2d  mov     edx, 1
0x140009c32  mov     rcx, rdi
0x140009c35  mov     rax, [rax+38h]
0x140009c39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009c3e  xor     edi, edi
0x140009c40  mov     [r14], rdi
0x140009c43  mov     eax, esi
0x140009c45  add     rsp, 38h
0x140009c49  pop     r15
0x140009c4b  pop     r14
0x140009c4d  pop     rdi
0x140009c4e  pop     rsi
0x140009c4f  retn
```
