# ATL::IDispatchImpl<IMsMpClientUtils,&__s_GUID const _GUID_e2d74550_8e41_460e_bb51_52e1f9522134,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x1800040a0`
- end: `0x180004107`
- name: `?GetTypeInfo@?$IDispatchImpl@UIMsMpClientUtils@@$1?_GUID_e2d74550_8e41_460e_bb51_52e1f9522134@@3U__s_GUID@@B$1?LIBID_MpComExportsLib@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003e28`
- `0x1800040a0`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IMsMpClientUtils,&__s_GUID const _GUID_e2d74550_8e41_460e_bb51_52e1f9522134,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
  v6 = qword_1800120D8;
  result = 0;
  if ( !qword_1800120D8 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IMsMpClientUtils,&__s_GUID const _GUID_e2d74550_8e41_460e_bb51_52e1f9522134,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>::_tih,
               a3);
    v6 = qword_1800120D8;
  }
  *a4 = v6;
  if ( qword_1800120D8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_1800120D8 + 8LL))(qword_1800120D8);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800040a0  push    rbx
0x1800040a2  sub     rsp, 20h
0x1800040a6  mov     rbx, r9
0x1800040a9  test    edx, edx
0x1800040ab  jz      short loc_1800040B4
0x1800040ad  mov     eax, 8002000Bh
0x1800040b2  jmp     short loc_180004101
0x1800040b4  test    rbx, rbx
0x1800040b7  jnz     short loc_1800040C0
0x1800040b9  mov     eax, 80004003h
0x1800040be  jmp     short loc_180004101
0x1800040c0  mov     rcx, cs:qword_1800120D8
0x1800040c7  xor     eax, eax
0x1800040c9  test    rcx, rcx
0x1800040cc  jnz     short loc_1800040E4
0x1800040ce  mov     edx, r8d; lcid
0x1800040d1  lea     rcx, ?_tih@?$IDispatchImpl@UIMsMpClientUtils@@$1?_GUID_e2d74550_8e41_460e_bb51_52e1f9522134@@3U__s_GUID@@B$1?LIBID_MpComExportsLib@@3U_GUID@@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x1800040d8  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x1800040dd  mov     rcx, cs:qword_1800120D8
0x1800040e4  mov     [rbx], rcx
0x1800040e7  mov     rcx, cs:qword_1800120D8
0x1800040ee  test    rcx, rcx
0x1800040f1  jz      short loc_180004101
0x1800040f3  mov     rax, [rcx]
0x1800040f6  mov     rax, [rax+8]
0x1800040fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040ff  xor     eax, eax
0x180004101  add     rsp, 20h
0x180004105  pop     rbx
0x180004106  retn
```
