# ATL::IDispatchImpl<IPreGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x1800100b0`
- end: `0x180010117`
- name: `?GetTypeInfo@?$IDispatchImpl@UIPreGather@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `103`
- prototype: `__int64 __fastcall(__int64, int, LCID, __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000fc68`
- `0x1800100b0`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IPreGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
  v6 = qword_1800250D8;
  result = 0;
  if ( !qword_1800250D8 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IPreGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::_tih,
               a3);
    v6 = qword_1800250D8;
  }
  *a4 = v6;
  if ( qword_1800250D8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_1800250D8 + 8LL))(qword_1800250D8);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800100b0  push    rbx
0x1800100b2  sub     rsp, 20h
0x1800100b6  mov     rbx, r9
0x1800100b9  test    edx, edx
0x1800100bb  jz      short loc_1800100C4
0x1800100bd  mov     eax, 8002000Bh
0x1800100c2  jmp     short loc_180010111
0x1800100c4  test    rbx, rbx
0x1800100c7  jnz     short loc_1800100D0
0x1800100c9  mov     eax, 80004003h
0x1800100ce  jmp     short loc_180010111
0x1800100d0  mov     rcx, cs:qword_1800250D8
0x1800100d7  xor     eax, eax
0x1800100d9  test    rcx, rcx
0x1800100dc  jnz     short loc_1800100F4
0x1800100de  mov     edx, r8d; lcid
0x1800100e1  lea     rcx, ?_tih@?$IDispatchImpl@UIPreGather@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x1800100e8  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x1800100ed  mov     rcx, cs:qword_1800250D8
0x1800100f4  mov     [rbx], rcx
0x1800100f7  mov     rcx, cs:qword_1800250D8
0x1800100fe  test    rcx, rcx
0x180010101  jz      short loc_180010111
0x180010103  mov     rax, [rcx]
0x180010106  mov     rax, [rax+8]
0x18001010a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001010f  xor     eax, eax
0x180010111  add     rsp, 20h
0x180010115  pop     rbx
0x180010116  retn
```
