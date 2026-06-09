# Windows::IEnumOnOwnedSTLImpl<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,ushort *,Windows::CopyFromPairWstringToLpolestr,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>>>::Clone(IEnumString * *)

- ea: `0x140009850`
- end: `0x1400098f0`
- name: `?Clone@?$IEnumOnOwnedSTLImpl@UIEnumString@@$1?_GUID_00000101_0000_0000_c000_000000000046@@3U__s_GUID@@BPEAGVCopyFromPairWstringToLpolestr@Windows@@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Windows@@UEAAJPEAPEAUIEnumString@@@Z`
- size: `160`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140009850`
- `0x140009b40`
- `0x14000ae40`
- `0x140013010`

## pseudocode

```c
__int64 __fastcall Windows::IEnumOnOwnedSTLImpl<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,unsigned short *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>>::Clone(
        __int64 a1,
        _QWORD *a2)
{
  int v4; // edi
  _QWORD *v5; // rbx
  _QWORD *v7; // [rsp+58h] [rbp+10h] BYREF

  v4 = -2147467261;
  if ( a2 )
  {
    *a2 = 0;
    v7 = 0;
    v4 = ATL::CComObject<Windows::CComEnumOnOwnedSTL<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,unsigned short *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>,ATL::CComMultiThreadModel>>::CreateInstance(&v7);
    if ( v4 >= 0 )
    {
      v5 = v7;
      (*(void (__fastcall **)(_QWORD *))(*v7 + 8LL))(v7);
      v4 = Windows::IEnumOnOwnedSTLImpl<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,unsigned short *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>>::Init(
             v5,
             a1 + 8);
      if ( v4 >= 0 )
      {
        v5[3] = *(_QWORD *)(a1 + 24);
        v4 = (*(__int64 (__fastcall **)(_QWORD *, GUID *, _QWORD *))*v5)(
               v5,
               &GUID_00000101_0000_0000_c000_000000000046,
               a2);
      }
      if ( v5 )
        (*(void (__fastcall **)(_QWORD *))(*v5 + 16LL))(v5);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140009850  push    rbx
0x140009852  push    rbp
0x140009853  push    rsi
0x140009854  push    rdi
0x140009855  sub     rsp, 28h
0x140009859  mov     rsi, rdx
0x14000985c  mov     rbp, rcx
0x14000985f  mov     edi, 80004003h
0x140009864  test    rdx, rdx
0x140009867  jz      short loc_1400098E5
0x140009869  lea     rcx, [rsp+48h+arg_8]
0x14000986e  mov     qword ptr [rdx], 0
0x140009875  mov     [rsp+48h+arg_8], 0
0x14000987e  call    ?CreateInstance@?$CComObject@V?$CComEnumOnOwnedSTL@UIEnumString@@$1?_GUID_00000101_0000_0000_c000_000000000046@@3U__s_GUID@@BPEAGVCopyFromPairWstringToLpolestr@Windows@@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@VCComMultiThreadModel@ATL@@@Windows@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<Windows::CComEnumOnOwnedSTL<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,ushort *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>,ATL::CComMultiThreadModel>>::CreateInstance(ATL::CComObject<Windows::CComEnumOnOwnedSTL<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,ushort *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>,ATL::CComMultiThreadModel>> * *)
0x140009883  mov     edi, eax
0x140009885  test    eax, eax
0x140009887  js      short loc_1400098E5
0x140009889  mov     rbx, [rsp+48h+arg_8]
0x14000988e  mov     rcx, rbx
0x140009891  mov     rax, [rbx]
0x140009894  mov     rax, [rax+8]
0x140009898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000989d  lea     rdx, [rbp+8]
0x1400098a1  mov     rcx, rbx
0x1400098a4  call    ?Init@?$IEnumOnOwnedSTLImpl@UIEnumString@@$1?_GUID_00000101_0000_0000_c000_000000000046@@3U__s_GUID@@BPEAGVCopyFromPairWstringToLpolestr@Windows@@V?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Windows@@QEAAJAEAV?$map@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z; Windows::IEnumOnOwnedSTLImpl<IEnumString,&__s_GUID const _GUID_00000101_0000_0000_c000_000000000046,ushort *,Windows::CopyFromPairWstringToLpolestr,std::map<std::wstring const,std::wstring>>::Init(std::map<std::wstring const,std::wstring> &)
0x1400098a9  mov     edi, eax
0x1400098ab  test    eax, eax
0x1400098ad  js      short loc_1400098D1
0x1400098af  mov     rax, [rbp+18h]
0x1400098b3  lea     rdx, _GUID_00000101_0000_0000_c000_000000000046
0x1400098ba  mov     [rbx+18h], rax
0x1400098be  mov     r8, rsi
0x1400098c1  mov     rax, [rbx]
0x1400098c4  mov     rcx, rbx
0x1400098c7  mov     rax, [rax]
0x1400098ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400098cf  mov     edi, eax
0x1400098d1  test    rbx, rbx
0x1400098d4  jz      short loc_1400098E5
0x1400098d6  mov     rax, [rbx]
0x1400098d9  mov     rcx, rbx
0x1400098dc  mov     rax, [rax+10h]
0x1400098e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400098e5  mov     eax, edi
0x1400098e7  add     rsp, 28h
0x1400098eb  pop     rdi
0x1400098ec  pop     rsi
0x1400098ed  pop     rbp
0x1400098ee  pop     rbx
0x1400098ef  retn
```
