# ATL::IProvideClassInfoImpl<&__s_GUID const _GUID_617c0a54_d12e_4340_87e7_01cc31bde762,&_GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>::GetClassInfoW(ITypeInfo * *)

- ea: `0x18000f0e0`
- end: `0x18000f13b`
- name: `?GetClassInfoW@?$IProvideClassInfoImpl@$1?_GUID_617c0a54_d12e_4340_87e7_01cc31bde762@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJPEAPEAUITypeInfo@@@Z`
- size: `91`
- prototype: `__int64 __fastcall(__int64, __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000f0e0`
- `0x18000fc68`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall ATL::IProvideClassInfoImpl<&__s_GUID const _GUID_617c0a54_d12e_4340_87e7_01cc31bde762,&public: static _GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>::GetClassInfoW(
        __int64 a1,
        __int64 *a2)
{
  __int64 result; // rax
  __int64 v4; // rcx

  if ( !a2 )
    return 2147500035LL;
  v4 = qword_1800251D8;
  result = 0;
  if ( !qword_1800251D8 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IProvideClassInfoImpl<&__s_GUID const _GUID_617c0a54_d12e_4340_87e7_01cc31bde762,&public: static _GUID ATL::CAtlModule::m_libid,1,0,ATL::CComTypeInfoHolder>::_tih,
               0);
    v4 = qword_1800251D8;
  }
  *a2 = v4;
  if ( qword_1800251D8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_1800251D8 + 8LL))(qword_1800251D8);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000f0e0  push    rbx
0x18000f0e2  sub     rsp, 20h
0x18000f0e6  mov     rbx, rdx
0x18000f0e9  test    rdx, rdx
0x18000f0ec  jnz     short loc_18000F0F5
0x18000f0ee  mov     eax, 80004003h
0x18000f0f3  jmp     short loc_18000F135
0x18000f0f5  mov     rcx, cs:qword_1800251D8
0x18000f0fc  xor     eax, eax
0x18000f0fe  test    rcx, rcx
0x18000f101  jnz     short loc_18000F118
0x18000f103  xor     edx, edx; lcid
0x18000f105  lea     rcx, ?_tih@?$IProvideClassInfoImpl@$1?_GUID_617c0a54_d12e_4340_87e7_01cc31bde762@@3U__s_GUID@@B$1?m_libid@CAtlModule@ATL@@2U_GUID@@A$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x18000f10c  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18000f111  mov     rcx, cs:qword_1800251D8
0x18000f118  mov     [rbx], rcx
0x18000f11b  mov     rcx, cs:qword_1800251D8
0x18000f122  test    rcx, rcx
0x18000f125  jz      short loc_18000F135
0x18000f127  mov     rax, [rcx]
0x18000f12a  mov     rax, [rax+8]
0x18000f12e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f133  xor     eax, eax
0x18000f135  add     rsp, 20h
0x18000f139  pop     rbx
0x18000f13a  retn
```
