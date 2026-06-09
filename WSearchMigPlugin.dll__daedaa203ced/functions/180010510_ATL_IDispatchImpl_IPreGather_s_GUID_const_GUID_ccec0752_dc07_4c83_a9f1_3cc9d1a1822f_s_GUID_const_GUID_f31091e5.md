# ATL::IDispatchImpl<IPreGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180010510`
- end: `0x1800105ab`
- name: `?Invoke@?$IDispatchImpl@UIPreGather@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `155`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, LCID, unsigned __int16, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000fc68`
- `0x180010510`
- `0x180018010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IPreGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::Invoke(
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

  v11 = qword_1800250D8;
  if ( !qword_1800250D8 || (result = 0, !qword_1800250E8) )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IPreGather,&__s_GUID const _GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f,&__s_GUID const _GUID_f31091e5_b0a8_11d6_b6fc_005056c00008,2,0,ATL::CComTypeInfoHolder>::_tih,
               a4);
    v11 = qword_1800250D8;
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
0x180010510  mov     [rsp+arg_0], rbx
0x180010515  push    rdi
0x180010516  sub     rsp, 50h
0x18001051a  mov     rdi, rcx
0x18001051d  mov     ebx, edx
0x18001051f  mov     rcx, cs:qword_1800250D8
0x180010526  test    rcx, rcx
0x180010529  jz      short loc_180010536
0x18001052b  xor     eax, eax
0x18001052d  cmp     cs:qword_1800250E8, rax
0x180010534  jnz     short loc_18001054C
0x180010536  mov     edx, r9d; lcid
0x180010539  lea     rcx, ?_tih@?$IDispatchImpl@UIPreGather@@$1?_GUID_ccec0752_dc07_4c83_a9f1_3cc9d1a1822f@@3U__s_GUID@@B$1?_GUID_f31091e5_b0a8_11d6_b6fc_005056c00008@@3U3@B$01$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180010540  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x180010545  mov     rcx, cs:qword_1800250D8
0x18001054c  test    rcx, rcx
0x18001054f  jz      short loc_1800105A0
0x180010551  mov     rdx, [rsp+58h+arg_40]
0x180010559  mov     r8d, ebx
0x18001055c  mov     rax, [rcx]
0x18001055f  movzx   r9d, [rsp+58h+arg_20]
0x180010568  mov     [rsp+58h+var_20], rdx
0x18001056d  mov     rdx, [rsp+58h+arg_38]
0x180010575  mov     rax, [rax+58h]
0x180010579  mov     [rsp+58h+var_28], rdx
0x18001057e  mov     rdx, [rsp+58h+arg_30]
0x180010586  mov     [rsp+58h+var_30], rdx
0x18001058b  mov     rdx, [rsp+58h+arg_28]
0x180010593  mov     [rsp+58h+var_38], rdx
0x180010598  mov     rdx, rdi
0x18001059b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105a0  mov     rbx, [rsp+58h+arg_0]
0x1800105a5  add     rsp, 50h
0x1800105a9  pop     rdi
0x1800105aa  retn
```
