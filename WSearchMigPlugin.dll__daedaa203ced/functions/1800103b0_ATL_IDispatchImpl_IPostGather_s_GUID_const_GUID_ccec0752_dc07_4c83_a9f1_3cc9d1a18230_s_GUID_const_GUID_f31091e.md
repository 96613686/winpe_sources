# ATL::IDispatchImpl<IPostGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a18230,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x1800103b0`
- end: `0x18001044b`
- name: `?Invoke@?$IDispatchImpl@UIPostGather@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a18230@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `155`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, LCID, unsigned __int16, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000fc68`
- `0x1800103b0`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IPostGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a18230,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::Invoke(
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

  v11 = qword_180025118;
  if ( !qword_180025118 || (result = 0, !qword_180025128) )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IPostGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a18230,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::_tih,
               a4);
    v11 = qword_180025118;
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
0x1800103b0  mov     [rsp+arg_0], rbx
0x1800103b5  push    rdi
0x1800103b6  sub     rsp, 50h
0x1800103ba  mov     rdi, rcx
0x1800103bd  mov     ebx, edx
0x1800103bf  mov     rcx, cs:qword_180025118
0x1800103c6  test    rcx, rcx
0x1800103c9  jz      short loc_1800103D6
0x1800103cb  xor     eax, eax
0x1800103cd  cmp     cs:qword_180025128, rax
0x1800103d4  jnz     short loc_1800103EC
0x1800103d6  mov     edx, r9d; lcid
0x1800103d9  lea     rcx, ?_tih@?$IDispatchImpl@UIPostGather@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a18230@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x1800103e0  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x1800103e5  mov     rcx, cs:qword_180025118
0x1800103ec  test    rcx, rcx
0x1800103ef  jz      short loc_180010440
0x1800103f1  mov     rdx, [rsp+58h+arg_40]
0x1800103f9  mov     r8d, ebx
0x1800103fc  mov     rax, [rcx]
0x1800103ff  movzx   r9d, [rsp+58h+arg_20]
0x180010408  mov     [rsp+58h+var_20], rdx
0x18001040d  mov     rdx, [rsp+58h+arg_38]
0x180010415  mov     rax, [rax+58h]
0x180010419  mov     [rsp+58h+var_28], rdx
0x18001041e  mov     rdx, [rsp+58h+arg_30]
0x180010426  mov     [rsp+58h+var_30], rdx
0x18001042b  mov     rdx, [rsp+58h+arg_28]
0x180010433  mov     [rsp+58h+var_38], rdx
0x180010438  mov     rdx, rdi
0x18001043b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010440  mov     rbx, [rsp+58h+arg_0]
0x180010445  add     rsp, 50h
0x180010449  pop     rdi
0x18001044a  retn
```
