# ATL::IDispatchImpl<IPostGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a18230,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x18000ffd0`
- end: `0x180010037`
- name: `?GetTypeInfo@?$IDispatchImpl@UIPostGather@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a18230@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `103`
- prototype: `__int64 __fastcall(__int64, int, LCID, __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000fc68`
- `0x18000ffd0`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IPostGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a18230,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
  v6 = qword_180025118;
  result = 0;
  if ( !qword_180025118 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IPostGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a18230,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::_tih,
               a3);
    v6 = qword_180025118;
  }
  *a4 = v6;
  if ( qword_180025118 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_180025118 + 8LL))(qword_180025118);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000ffd0  push    rbx
0x18000ffd2  sub     rsp, 20h
0x18000ffd6  mov     rbx, r9
0x18000ffd9  test    edx, edx
0x18000ffdb  jz      short loc_18000FFE4
0x18000ffdd  mov     eax, 8002000Bh
0x18000ffe2  jmp     short loc_180010031
0x18000ffe4  test    rbx, rbx
0x18000ffe7  jnz     short loc_18000FFF0
0x18000ffe9  mov     eax, 80004003h
0x18000ffee  jmp     short loc_180010031
0x18000fff0  mov     rcx, cs:qword_180025118
0x18000fff7  xor     eax, eax
0x18000fff9  test    rcx, rcx
0x18000fffc  jnz     short loc_180010014
0x18000fffe  mov     edx, r8d; lcid
0x180010001  lea     rcx, ?_tih@?$IDispatchImpl@UIPostGather@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a18230@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180010008  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18001000d  mov     rcx, cs:qword_180025118
0x180010014  mov     [rbx], rcx
0x180010017  mov     rcx, cs:qword_180025118
0x18001001e  test    rcx, rcx
0x180010021  jz      short loc_180010031
0x180010023  mov     rax, [rcx]
0x180010026  mov     rax, [rax+8]
0x18001002a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001002f  xor     eax, eax
0x180010031  add     rsp, 20h
0x180010035  pop     rbx
0x180010036  retn
```
