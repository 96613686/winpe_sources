# ATL::IDispatchImpl<IDiscovery,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822c,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x18000fef0`
- end: `0x18000ff57`
- name: `?GetTypeInfo@?$IDispatchImpl@UIDiscovery@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822c@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `103`
- prototype: `__int64 __fastcall(__int64, int, LCID, __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000fc68`
- `0x18000fef0`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IDiscovery,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822c,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
        __int64 a1,
        int a2,
        LCID a3,
        __int64 *a4)
{
  __int64 result; // rax
  __int64 v6; // rcx

  if ( a2 )
    return 2147614731LL;
  if ( !a4 )
    return 2147500035LL;
  v6 = qword_180025098;
  result = 0;
  if ( !qword_180025098 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IDiscovery,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822c,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::_tih,
               a3);
    v6 = qword_180025098;
  }
  *a4 = v6;
  if ( qword_180025098 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_180025098 + 8LL))(qword_180025098);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000fef0  push    rbx
0x18000fef2  sub     rsp, 20h
0x18000fef6  mov     rbx, r9
0x18000fef9  test    edx, edx
0x18000fefb  jz      short loc_18000FF04
0x18000fefd  mov     eax, 8002000Bh
0x18000ff02  jmp     short loc_18000FF51
0x18000ff04  test    rbx, rbx
0x18000ff07  jnz     short loc_18000FF10
0x18000ff09  mov     eax, 80004003h
0x18000ff0e  jmp     short loc_18000FF51
0x18000ff10  mov     rcx, cs:qword_180025098
0x18000ff17  xor     eax, eax
0x18000ff19  test    rcx, rcx
0x18000ff1c  jnz     short loc_18000FF34
0x18000ff1e  mov     edx, r8d; lcid
0x18000ff21  lea     rcx, ?_tih@?$IDispatchImpl@UIDiscovery@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822c@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x18000ff28  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18000ff2d  mov     rcx, cs:qword_180025098
0x18000ff34  mov     [rbx], rcx
0x18000ff37  mov     rcx, cs:qword_180025098
0x18000ff3e  test    rcx, rcx
0x18000ff41  jz      short loc_18000FF51
0x18000ff43  mov     rax, [rcx]
0x18000ff46  mov     rax, [rax+8]
0x18000ff4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ff4f  xor     eax, eax
0x18000ff51  add     rsp, 20h
0x18000ff55  pop     rbx
0x18000ff56  retn
```
