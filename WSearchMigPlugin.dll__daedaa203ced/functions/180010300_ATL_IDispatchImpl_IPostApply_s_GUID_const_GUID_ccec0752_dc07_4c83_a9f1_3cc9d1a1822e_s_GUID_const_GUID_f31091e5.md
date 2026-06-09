# ATL::IDispatchImpl<IPostApply,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822e,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180010300`
- end: `0x18001039b`
- name: `?Invoke@?$IDispatchImpl@UIPostApply@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822e@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `155`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, LCID, unsigned __int16, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000fc68`
- `0x180010300`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IPostApply,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822e,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::Invoke(
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

  v11 = qword_180025198;
  if ( !qword_180025198 || (result = 0, !qword_1800251A8) )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IPostApply,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822e,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::_tih,
               a4);
    v11 = qword_180025198;
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
0x180010300  mov     [rsp+arg_0], rbx
0x180010305  push    rdi
0x180010306  sub     rsp, 50h
0x18001030a  mov     rdi, rcx
0x18001030d  mov     ebx, edx
0x18001030f  mov     rcx, cs:qword_180025198
0x180010316  test    rcx, rcx
0x180010319  jz      short loc_180010326
0x18001031b  xor     eax, eax
0x18001031d  cmp     cs:qword_1800251A8, rax
0x180010324  jnz     short loc_18001033C
0x180010326  mov     edx, r9d; lcid
0x180010329  lea     rcx, ?_tih@?$IDispatchImpl@UIPostApply@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822e@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180010330  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x180010335  mov     rcx, cs:qword_180025198
0x18001033c  test    rcx, rcx
0x18001033f  jz      short loc_180010390
0x180010341  mov     rdx, [rsp+58h+arg_40]
0x180010349  mov     r8d, ebx
0x18001034c  mov     rax, [rcx]
0x18001034f  movzx   r9d, [rsp+58h+arg_20]
0x180010358  mov     [rsp+58h+var_20], rdx
0x18001035d  mov     rdx, [rsp+58h+arg_38]
0x180010365  mov     rax, [rax+58h]
0x180010369  mov     [rsp+58h+var_28], rdx
0x18001036e  mov     rdx, [rsp+58h+arg_30]
0x180010376  mov     [rsp+58h+var_30], rdx
0x18001037b  mov     rdx, [rsp+58h+arg_28]
0x180010383  mov     [rsp+58h+var_38], rdx
0x180010388  mov     rdx, rdi
0x18001038b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010390  mov     rbx, [rsp+58h+arg_0]
0x180010395  add     rsp, 50h
0x180010399  pop     rdi
0x18001039a  retn
```
