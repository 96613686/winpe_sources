# ATL::CComObject<Windows::CComEnumOnOwnedSTL<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,ushort *,Windows::CopyFromPairWstringToLpolestr,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>,ATL::CComMultiThreadModel>>::Release(void)

- ea: `0x14000cf10`
- end: `0x14000cf91`
- name: `?Release@?$CComObject@V?$CComEnumOnOwnedSTL@UIEnumString@@$1?_GUID_00000101_0000_0000_c000_000000000046@@3U__s_GUID@@BPEAGVCopyFromPairWstringToLpolestr@Windows@@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@VCComMultiThreadModel@ATL@@@Windows@@@ATL@@UEAAKXZ`
- size: `129`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000cf10`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<Windows::CComEnumOnOwnedSTL<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,unsigned short *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>,ATL::CComMultiThreadModel>>::Release(
        volatile signed __int32 *a1)
{
  signed __int32 i; // r8d
  unsigned __int32 v3; // edi

  for ( i = *((_DWORD *)a1 + 8);
        i != 0x7FFFFFFF && i != _InterlockedCompareExchange(a1 + 8, i - 1, i);
        i = *((_DWORD *)a1 + 8) )
  {
    ;
  }
  v3 = i - 1;
  if ( i == 1 )
  {
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, _QWORD))(*(_QWORD *)a1 + 56LL))(a1, v3 + 1);
    (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
  }
  return v3;
}

```

## disassembly

```asm
0x14000cf10  mov     [rsp+arg_0], rbx
0x14000cf15  push    rdi
0x14000cf16  sub     rsp, 20h
0x14000cf1a  mov     r8d, [rcx+20h]
0x14000cf1e  mov     rbx, rcx
0x14000cf21  mov     ecx, 7FFFFFFFh
0x14000cf26  jmp     short loc_14000CF3A
0x14000cf28  lea     edx, [r8-1]
0x14000cf2c  mov     eax, r8d
0x14000cf2f  lock cmpxchg [rbx+20h], edx
0x14000cf34  jz      short loc_14000CF3F
0x14000cf36  mov     r8d, [rbx+20h]
0x14000cf3a  cmp     r8d, ecx
0x14000cf3d  jnz     short loc_14000CF28
0x14000cf3f  lea     edi, [r8-1]
0x14000cf43  test    edi, edi
0x14000cf45  jnz     short loc_14000CF84
0x14000cf47  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x14000cf4e  mov     rax, [rcx]
0x14000cf51  mov     rax, [rax+8]
0x14000cf55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cf5a  test    rbx, rbx
0x14000cf5d  jz      short loc_14000CF71
0x14000cf5f  mov     rax, [rbx]
0x14000cf62  lea     edx, [rdi+1]
0x14000cf65  mov     rcx, rbx
0x14000cf68  mov     rax, [rax+38h]
0x14000cf6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cf71  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x14000cf78  mov     rdx, [rcx]
0x14000cf7b  mov     rax, [rdx+10h]
0x14000cf7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cf84  mov     rbx, [rsp+28h+arg_0]
0x14000cf89  mov     eax, edi
0x14000cf8b  add     rsp, 20h
0x14000cf8f  pop     rdi
0x14000cf90  retn
```
