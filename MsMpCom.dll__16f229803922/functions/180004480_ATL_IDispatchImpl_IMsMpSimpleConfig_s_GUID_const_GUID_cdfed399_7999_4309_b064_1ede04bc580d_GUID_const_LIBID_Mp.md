# ATL::IDispatchImpl<IMsMpSimpleConfig,&__s_GUID const _GUID_cdfed399_7999_4309_b064_1ede04bc580d,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180004480`
- end: `0x18000451b`
- name: `?Invoke@?$IDispatchImpl@UIMsMpSimpleConfig@@$1?_GUID_cdfed399_7999_4309_b064_1ede04bc580d@@3U__s_GUID@@B$1?LIBID_MpComExportsLib@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180003e28`
- `0x180004480`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IMsMpSimpleConfig,&__s_GUID const _GUID_cdfed399_7999_4309_b064_1ede04bc580d,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>::Invoke(
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

  v11 = qword_180012118;
  if ( !qword_180012118 || (result = 0, !qword_180012128) )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IMsMpSimpleConfig,&__s_GUID const _GUID_cdfed399_7999_4309_b064_1ede04bc580d,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>::_tih,
               a4);
    v11 = qword_180012118;
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
0x180004480  mov     [rsp+arg_0], rbx
0x180004485  push    rdi
0x180004486  sub     rsp, 50h
0x18000448a  mov     rdi, rcx
0x18000448d  mov     ebx, edx
0x18000448f  mov     rcx, cs:qword_180012118
0x180004496  test    rcx, rcx
0x180004499  jz      short loc_1800044A6
0x18000449b  xor     eax, eax
0x18000449d  cmp     cs:qword_180012128, rax
0x1800044a4  jnz     short loc_1800044BC
0x1800044a6  mov     edx, r9d; lcid
0x1800044a9  lea     rcx, ?_tih@?$IDispatchImpl@UIMsMpSimpleConfig@@$1?_GUID_cdfed399_7999_4309_b064_1ede04bc580d@@3U__s_GUID@@B$1?LIBID_MpComExportsLib@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x1800044b0  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x1800044b5  mov     rcx, cs:qword_180012118
0x1800044bc  test    rcx, rcx
0x1800044bf  jz      short loc_180004510
0x1800044c1  mov     rdx, [rsp+58h+arg_40]
0x1800044c9  mov     r8d, ebx
0x1800044cc  mov     rax, [rcx]
0x1800044cf  movzx   r9d, [rsp+58h+arg_20]
0x1800044d8  mov     [rsp+58h+var_20], rdx
0x1800044dd  mov     rdx, [rsp+58h+arg_38]
0x1800044e5  mov     rax, [rax+58h]
0x1800044e9  mov     [rsp+58h+var_28], rdx
0x1800044ee  mov     rdx, [rsp+58h+arg_30]
0x1800044f6  mov     [rsp+58h+var_30], rdx
0x1800044fb  mov     rdx, [rsp+58h+arg_28]
0x180004503  mov     [rsp+58h+var_38], rdx
0x180004508  mov     rdx, rdi
0x18000450b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004510  mov     rbx, [rsp+58h+arg_0]
0x180004515  add     rsp, 50h
0x180004519  pop     rdi
0x18000451a  retn
```
