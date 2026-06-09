# ATL::IDispatchImpl<IMsMpSimpleConfig,&__s_GUID const _GUID_cdfed399_7999_4309_b064_1ede04bc580d,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x180004180`
- end: `0x1800041e7`
- name: `?GetTypeInfo@?$IDispatchImpl@UIMsMpSimpleConfig@@$1?_GUID_cdfed399_7999_4309_b064_1ede04bc580d@@3U__s_GUID@@B$1?LIBID_MpComExportsLib@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180003e28`
- `0x180004180`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IMsMpSimpleConfig,&__s_GUID const _GUID_cdfed399_7999_4309_b064_1ede04bc580d,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
  v6 = qword_180012118;
  result = 0;
  if ( !qword_180012118 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IMsMpSimpleConfig,&__s_GUID const _GUID_cdfed399_7999_4309_b064_1ede04bc580d,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>::_tih,
               a3);
    v6 = qword_180012118;
  }
  *a4 = v6;
  if ( qword_180012118 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_180012118 + 8LL))(qword_180012118);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004180  push    rbx
0x180004182  sub     rsp, 20h
0x180004186  mov     rbx, r9
0x180004189  test    edx, edx
0x18000418b  jz      short loc_180004194
0x18000418d  mov     eax, 8002000Bh
0x180004192  jmp     short loc_1800041E1
0x180004194  test    rbx, rbx
0x180004197  jnz     short loc_1800041A0
0x180004199  mov     eax, 80004003h
0x18000419e  jmp     short loc_1800041E1
0x1800041a0  mov     rcx, cs:qword_180012118
0x1800041a7  xor     eax, eax
0x1800041a9  test    rcx, rcx
0x1800041ac  jnz     short loc_1800041C4
0x1800041ae  mov     edx, r8d; lcid
0x1800041b1  lea     rcx, ?_tih@?$IDispatchImpl@UIMsMpSimpleConfig@@$1?_GUID_cdfed399_7999_4309_b064_1ede04bc580d@@3U__s_GUID@@B$1?LIBID_MpComExportsLib@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x1800041b8  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x1800041bd  mov     rcx, cs:qword_180012118
0x1800041c4  mov     [rbx], rcx
0x1800041c7  mov     rcx, cs:qword_180012118
0x1800041ce  test    rcx, rcx
0x1800041d1  jz      short loc_1800041E1
0x1800041d3  mov     rax, [rcx]
0x1800041d6  mov     rax, [rax+8]
0x1800041da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041df  xor     eax, eax
0x1800041e1  add     rsp, 20h
0x1800041e5  pop     rbx
0x1800041e6  retn
```
