# ATL::IDispatchImpl<IDiscovery,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822c,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180010250`
- end: `0x1800102eb`
- name: `?Invoke@?$IDispatchImpl@UIDiscovery@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822c@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `155`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, LCID, unsigned __int16, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000fc68`
- `0x180010250`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IDiscovery,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822c,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::Invoke(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        LCID a4,
        unsigned __int16 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9)
{
  __int64 v11; // rcx
  __int64 result; // rax

  v11 = qword_180025098;
  if ( !qword_180025098 || (result = 0, !qword_1800250A8) )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IDiscovery,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822c,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::_tih,
               a4);
    v11 = qword_180025098;
  }
  if ( v11 )
    return (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, __int64, __int64, __int64, __int64))(*(_QWORD *)v11 + 88LL))(
             v11,
             a1,
             a2,
             a5,
             a6,
             a7,
             a8,
             a9);
  return result;
}

```

## disassembly

```asm
0x180010250  mov     [rsp+arg_0], rbx
0x180010255  push    rdi
0x180010256  sub     rsp, 50h
0x18001025a  mov     rdi, rcx
0x18001025d  mov     ebx, edx
0x18001025f  mov     rcx, cs:qword_180025098
0x180010266  test    rcx, rcx
0x180010269  jz      short loc_180010276
0x18001026b  xor     eax, eax
0x18001026d  cmp     cs:qword_1800250A8, rax
0x180010274  jnz     short loc_18001028C
0x180010276  mov     edx, r9d; lcid
0x180010279  lea     rcx, ?_tih@?$IDispatchImpl@UIDiscovery@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822c@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180010280  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x180010285  mov     rcx, cs:qword_180025098
0x18001028c  test    rcx, rcx
0x18001028f  jz      short loc_1800102E0
0x180010291  mov     rdx, [rsp+58h+arg_40]
0x180010299  mov     r8d, ebx
0x18001029c  mov     rax, [rcx]
0x18001029f  movzx   r9d, [rsp+58h+arg_20]
0x1800102a8  mov     [rsp+58h+var_20], rdx
0x1800102ad  mov     rdx, [rsp+58h+arg_38]
0x1800102b5  mov     rax, [rax+58h]
0x1800102b9  mov     [rsp+58h+var_28], rdx
0x1800102be  mov     rdx, [rsp+58h+arg_30]
0x1800102c6  mov     [rsp+58h+var_30], rdx
0x1800102cb  mov     rdx, [rsp+58h+arg_28]
0x1800102d3  mov     [rsp+58h+var_38], rdx
0x1800102d8  mov     rdx, rdi
0x1800102db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102e0  mov     rbx, [rsp+58h+arg_0]
0x1800102e5  add     rsp, 50h
0x1800102e9  pop     rdi
0x1800102ea  retn
```
