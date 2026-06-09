# ATL::IDispatchImpl<IMsMpComFactory,&_GUID const IID_IMsMpComFactory,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x1800043d0`
- end: `0x18000446b`
- name: `?Invoke@?$IDispatchImpl@UIMsMpComFactory@@$1?IID_IMsMpComFactory@@3U_GUID@@B$1?LIBID_MpComExportsLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `155`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003e28`
- `0x1800043d0`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IMsMpComFactory,&_GUID const IID_IMsMpComFactory,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>::Invoke(
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

  v11 = qword_180012098;
  if ( !qword_180012098 || (result = 0, !qword_1800120A8) )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IMsMpComFactory,&_GUID const IID_IMsMpComFactory,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>::_tih,
               a4);
    v11 = qword_180012098;
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
0x1800043d0  mov     [rsp+arg_0], rbx
0x1800043d5  push    rdi
0x1800043d6  sub     rsp, 50h
0x1800043da  mov     rdi, rcx
0x1800043dd  mov     ebx, edx
0x1800043df  mov     rcx, cs:qword_180012098
0x1800043e6  test    rcx, rcx
0x1800043e9  jz      short loc_1800043F6
0x1800043eb  xor     eax, eax
0x1800043ed  cmp     cs:qword_1800120A8, rax
0x1800043f4  jnz     short loc_18000440C
0x1800043f6  mov     edx, r9d; lcid
0x1800043f9  lea     rcx, ?_tih@?$IDispatchImpl@UIMsMpComFactory@@$1?IID_IMsMpComFactory@@3U_GUID@@B$1?LIBID_MpComExportsLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180004400  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x180004405  mov     rcx, cs:qword_180012098
0x18000440c  test    rcx, rcx
0x18000440f  jz      short loc_180004460
0x180004411  mov     rdx, [rsp+58h+arg_40]
0x180004419  mov     r8d, ebx
0x18000441c  mov     rax, [rcx]
0x18000441f  movzx   r9d, [rsp+58h+arg_20]
0x180004428  mov     [rsp+58h+var_20], rdx
0x18000442d  mov     rdx, [rsp+58h+arg_38]
0x180004435  mov     rax, [rax+58h]
0x180004439  mov     [rsp+58h+var_28], rdx
0x18000443e  mov     rdx, [rsp+58h+arg_30]
0x180004446  mov     [rsp+58h+var_30], rdx
0x18000444b  mov     rdx, [rsp+58h+arg_28]
0x180004453  mov     [rsp+58h+var_38], rdx
0x180004458  mov     rdx, rdi
0x18000445b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004460  mov     rbx, [rsp+58h+arg_0]
0x180004465  add     rsp, 50h
0x180004469  pop     rdi
0x18000446a  retn
```
