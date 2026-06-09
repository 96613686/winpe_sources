# ATL::IDispatchImpl<IPreApply,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822d,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x180010040`
- end: `0x1800100a7`
- name: `?GetTypeInfo@?$IDispatchImpl@UIPreApply@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822d@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `103`
- prototype: `__int64 __fastcall(__int64, int, LCID, __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000fc68`
- `0x180010040`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IPreApply,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822d,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
  v6 = qword_180025158;
  result = 0;
  if ( !qword_180025158 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IPreApply,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822d,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::_tih,
               a3);
    v6 = qword_180025158;
  }
  *a4 = v6;
  if ( qword_180025158 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_180025158 + 8LL))(qword_180025158);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180010040  push    rbx
0x180010042  sub     rsp, 20h
0x180010046  mov     rbx, r9
0x180010049  test    edx, edx
0x18001004b  jz      short loc_180010054
0x18001004d  mov     eax, 8002000Bh
0x180010052  jmp     short loc_1800100A1
0x180010054  test    rbx, rbx
0x180010057  jnz     short loc_180010060
0x180010059  mov     eax, 80004003h
0x18001005e  jmp     short loc_1800100A1
0x180010060  mov     rcx, cs:qword_180025158
0x180010067  xor     eax, eax
0x180010069  test    rcx, rcx
0x18001006c  jnz     short loc_180010084
0x18001006e  mov     edx, r8d; lcid
0x180010071  lea     rcx, ?_tih@?$IDispatchImpl@UIPreApply@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822d@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180010078  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18001007d  mov     rcx, cs:qword_180025158
0x180010084  mov     [rbx], rcx
0x180010087  mov     rcx, cs:qword_180025158
0x18001008e  test    rcx, rcx
0x180010091  jz      short loc_1800100A1
0x180010093  mov     rax, [rcx]
0x180010096  mov     rax, [rax+8]
0x18001009a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001009f  xor     eax, eax
0x1800100a1  add     rsp, 20h
0x1800100a5  pop     rbx
0x1800100a6  retn
```
