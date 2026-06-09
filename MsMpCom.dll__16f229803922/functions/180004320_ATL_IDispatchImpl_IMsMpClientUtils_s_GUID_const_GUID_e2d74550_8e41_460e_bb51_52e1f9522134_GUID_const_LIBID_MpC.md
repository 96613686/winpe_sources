# ATL::IDispatchImpl<IMsMpClientUtils,&__s_GUID const _GUID_e2d74550_8e41_460e_bb51_52e1f9522134,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x180004320`
- end: `0x1800043bb`
- name: `?Invoke@?$IDispatchImpl@UIMsMpClientUtils@@$1?_GUID_e2d74550_8e41_460e_bb51_52e1f9522134@@3U__s_GUID@@B$1?LIBID_MpComExportsLib@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003e28`
- `0x180004320`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IMsMpClientUtils,&__s_GUID const _GUID_e2d74550_8e41_460e_bb51_52e1f9522134,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>::Invoke(
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

  v11 = qword_1800120D8;
  if ( !qword_1800120D8 || (result = 0, !qword_1800120E8) )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IMsMpClientUtils,&__s_GUID const _GUID_e2d74550_8e41_460e_bb51_52e1f9522134,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>::_tih,
               a4);
    v11 = qword_1800120D8;
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
0x180004320  mov     [rsp+arg_0], rbx
0x180004325  push    rdi
0x180004326  sub     rsp, 50h
0x18000432a  mov     rdi, rcx
0x18000432d  mov     ebx, edx
0x18000432f  mov     rcx, cs:qword_1800120D8
0x180004336  test    rcx, rcx
0x180004339  jz      short loc_180004346
0x18000433b  xor     eax, eax
0x18000433d  cmp     cs:qword_1800120E8, rax
0x180004344  jnz     short loc_18000435C
0x180004346  mov     edx, r9d; lcid
0x180004349  lea     rcx, ?_tih@?$IDispatchImpl@UIMsMpClientUtils@@$1?_GUID_e2d74550_8e41_460e_bb51_52e1f9522134@@3U__s_GUID@@B$1?LIBID_MpComExportsLib@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180004350  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x180004355  mov     rcx, cs:qword_1800120D8
0x18000435c  test    rcx, rcx
0x18000435f  jz      short loc_1800043B0
0x180004361  mov     rdx, [rsp+58h+arg_40]
0x180004369  mov     r8d, ebx
0x18000436c  mov     rax, [rcx]
0x18000436f  movzx   r9d, [rsp+58h+arg_20]
0x180004378  mov     [rsp+58h+var_20], rdx
0x18000437d  mov     rdx, [rsp+58h+arg_38]
0x180004385  mov     rax, [rax+58h]
0x180004389  mov     [rsp+58h+var_28], rdx
0x18000438e  mov     rdx, [rsp+58h+arg_30]
0x180004396  mov     [rsp+58h+var_30], rdx
0x18000439b  mov     rdx, [rsp+58h+arg_28]
0x1800043a3  mov     [rsp+58h+var_38], rdx
0x1800043a8  mov     rdx, rdi
0x1800043ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800043b0  mov     rbx, [rsp+58h+arg_0]
0x1800043b5  add     rsp, 50h
0x1800043b9  pop     rdi
0x1800043ba  retn
```
