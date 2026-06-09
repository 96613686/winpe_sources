# ATL::IDispatchImpl<IPostApply,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822e,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x18000ff60`
- end: `0x18000ffc7`
- name: `?GetTypeInfo@?$IDispatchImpl@UIPostApply@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822e@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `103`
- prototype: `__int64 __fastcall(__int64, int, LCID, __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000fc68`
- `0x18000ff60`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IPostApply,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822e,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
  v6 = qword_180025198;
  result = 0;
  if ( !qword_180025198 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IPostApply,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822e,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::_tih,
               a3);
    v6 = qword_180025198;
  }
  *a4 = v6;
  if ( qword_180025198 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_180025198 + 8LL))(qword_180025198);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000ff60  push    rbx
0x18000ff62  sub     rsp, 20h
0x18000ff66  mov     rbx, r9
0x18000ff69  test    edx, edx
0x18000ff6b  jz      short loc_18000FF74
0x18000ff6d  mov     eax, 8002000Bh
0x18000ff72  jmp     short loc_18000FFC1
0x18000ff74  test    rbx, rbx
0x18000ff77  jnz     short loc_18000FF80
0x18000ff79  mov     eax, 80004003h
0x18000ff7e  jmp     short loc_18000FFC1
0x18000ff80  mov     rcx, cs:qword_180025198
0x18000ff87  xor     eax, eax
0x18000ff89  test    rcx, rcx
0x18000ff8c  jnz     short loc_18000FFA4
0x18000ff8e  mov     edx, r8d; lcid
0x18000ff91  lea     rcx, ?_tih@?$IDispatchImpl@UIPostApply@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822e@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x18000ff98  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18000ff9d  mov     rcx, cs:qword_180025198
0x18000ffa4  mov     [rbx], rcx
0x18000ffa7  mov     rcx, cs:qword_180025198
0x18000ffae  test    rcx, rcx
0x18000ffb1  jz      short loc_18000FFC1
0x18000ffb3  mov     rax, [rcx]
0x18000ffb6  mov     rax, [rax+8]
0x18000ffba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffbf  xor     eax, eax
0x18000ffc1  add     rsp, 20h
0x18000ffc5  pop     rbx
0x18000ffc6  retn
```
