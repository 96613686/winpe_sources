# ATL::IDispatchImpl<IDsmControl,&_GUID const IID_IDsmControl,&_GUID const LIBID_DsmApiLib,1,0,ATL::CComTypeInfoHolder>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x18000a890`
- end: `0x18000a92b`
- name: `?Invoke@?$IDispatchImpl@UIDsmControl@@$1?IID_IDsmControl@@3U_GUID@@B$1?LIBID_DsmApiLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `155`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, LCID, unsigned __int16, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000a584`
- `0x18000a890`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IDsmControl,&_GUID const IID_IDsmControl,&_GUID const LIBID_DsmApiLib,1,0,ATL::CComTypeInfoHolder>::Invoke(
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

  v11 = qword_1800171C8;
  if ( !qword_1800171C8 || (result = 0, !qword_1800171D8) )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IDsmControl,&_GUID const IID_IDsmControl,&_GUID const LIBID_DsmApiLib,1,0,ATL::CComTypeInfoHolder>::_tih,
               a4);
    v11 = qword_1800171C8;
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
0x18000a890  mov     [rsp+arg_0], rbx
0x18000a895  push    rdi
0x18000a896  sub     rsp, 50h
0x18000a89a  mov     rdi, rcx
0x18000a89d  mov     ebx, edx
0x18000a89f  mov     rcx, cs:qword_1800171C8
0x18000a8a6  test    rcx, rcx
0x18000a8a9  jz      short loc_18000A8B6
0x18000a8ab  xor     eax, eax
0x18000a8ad  cmp     cs:qword_1800171D8, rax
0x18000a8b4  jnz     short loc_18000A8CC
0x18000a8b6  mov     edx, r9d; lcid
0x18000a8b9  lea     rcx, ?_tih@?$IDispatchImpl@UIDsmControl@@$1?IID_IDsmControl@@3U_GUID@@B$1?LIBID_DsmApiLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x18000a8c0  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18000a8c5  mov     rcx, cs:qword_1800171C8
0x18000a8cc  test    rcx, rcx
0x18000a8cf  jz      short loc_18000A920
0x18000a8d1  mov     rdx, [rsp+58h+arg_40]
0x18000a8d9  mov     r8d, ebx
0x18000a8dc  mov     rax, [rcx]
0x18000a8df  movzx   r9d, [rsp+58h+arg_20]
0x18000a8e8  mov     [rsp+58h+var_20], rdx
0x18000a8ed  mov     rdx, [rsp+58h+arg_38]
0x18000a8f5  mov     rax, [rax+58h]
0x18000a8f9  mov     [rsp+58h+var_28], rdx
0x18000a8fe  mov     rdx, [rsp+58h+arg_30]
0x18000a906  mov     [rsp+58h+var_30], rdx
0x18000a90b  mov     rdx, [rsp+58h+arg_28]
0x18000a913  mov     [rsp+58h+var_38], rdx
0x18000a918  mov     rdx, rdi
0x18000a91b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a920  mov     rbx, [rsp+58h+arg_0]
0x18000a925  add     rsp, 50h
0x18000a929  pop     rdi
0x18000a92a  retn
```
