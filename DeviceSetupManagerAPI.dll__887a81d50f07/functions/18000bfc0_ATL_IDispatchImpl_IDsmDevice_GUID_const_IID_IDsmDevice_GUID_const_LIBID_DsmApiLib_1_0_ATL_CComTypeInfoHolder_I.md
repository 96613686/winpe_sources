# ATL::IDispatchImpl<IDsmDevice,&_GUID const IID_IDsmDevice,&_GUID const LIBID_DsmApiLib,1,0,ATL::CComTypeInfoHolder>::Invoke(long,_GUID const &,ulong,ushort,tagDISPPARAMS *,tagVARIANT *,tagEXCEPINFO *,uint *)

- ea: `0x18000bfc0`
- end: `0x18000c05b`
- name: `?Invoke@?$IDispatchImpl@UIDsmDevice@@$1?IID_IDsmDevice@@3U_GUID@@B$1?LIBID_DsmApiLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJJAEBU_GUID@@KGPEAUtagDISPPARAMS@@PEAUtagVARIANT@@PEAUtagEXCEPINFO@@PEAI@Z`
- size: `155`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, LCID, unsigned __int16, __int64, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000a584`
- `0x18000bfc0`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IDsmDevice,&_GUID const IID_IDsmDevice,&_GUID const LIBID_DsmApiLib,1,0,ATL::CComTypeInfoHolder>::Invoke(
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

  v11 = qword_180017208;
  if ( !qword_180017208 || (result = 0, !qword_180017218) )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IDsmDevice,&_GUID const IID_IDsmDevice,&_GUID const LIBID_DsmApiLib,1,0,ATL::CComTypeInfoHolder>::_tih,
               a4);
    v11 = qword_180017208;
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
0x18000bfc0  mov     [rsp+arg_0], rbx
0x18000bfc5  push    rdi
0x18000bfc6  sub     rsp, 50h
0x18000bfca  mov     rdi, rcx
0x18000bfcd  mov     ebx, edx
0x18000bfcf  mov     rcx, cs:qword_180017208
0x18000bfd6  test    rcx, rcx
0x18000bfd9  jz      short loc_18000BFE6
0x18000bfdb  xor     eax, eax
0x18000bfdd  cmp     cs:qword_180017218, rax
0x18000bfe4  jnz     short loc_18000BFFC
0x18000bfe6  mov     edx, r9d; lcid
0x18000bfe9  lea     rcx, ?_tih@?$IDispatchImpl@UIDsmDevice@@$1?IID_IDsmDevice@@3U_GUID@@B$1?LIBID_DsmApiLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x18000bff0  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18000bff5  mov     rcx, cs:qword_180017208
0x18000bffc  test    rcx, rcx
0x18000bfff  jz      short loc_18000C050
0x18000c001  mov     rdx, [rsp+58h+arg_40]
0x18000c009  mov     r8d, ebx
0x18000c00c  mov     rax, [rcx]
0x18000c00f  movzx   r9d, [rsp+58h+arg_20]
0x18000c018  mov     [rsp+58h+var_20], rdx
0x18000c01d  mov     rdx, [rsp+58h+arg_38]
0x18000c025  mov     rax, [rax+58h]
0x18000c029  mov     [rsp+58h+var_28], rdx
0x18000c02e  mov     rdx, [rsp+58h+arg_30]
0x18000c036  mov     [rsp+58h+var_30], rdx
0x18000c03b  mov     rdx, [rsp+58h+arg_28]
0x18000c043  mov     [rsp+58h+var_38], rdx
0x18000c048  mov     rdx, rdi
0x18000c04b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c050  mov     rbx, [rsp+58h+arg_0]
0x18000c055  add     rsp, 50h
0x18000c059  pop     rdi
0x18000c05a  retn
```
