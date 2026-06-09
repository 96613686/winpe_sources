# ATL::IDispatchImpl<IDsmControl,&_GUID const IID_IDsmControl,&_GUID const LIBID_DsmApiLib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x18000a800`
- end: `0x18000a867`
- name: `?GetTypeInfo@?$IDispatchImpl@UIDsmControl@@$1?IID_IDsmControl@@3U_GUID@@B$1?LIBID_DsmApiLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `103`
- prototype: `__int64 __fastcall(__int64, int, LCID, __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000a584`
- `0x18000a800`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IDsmControl,&_GUID const IID_IDsmControl,&_GUID const LIBID_DsmApiLib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
  v6 = qword_1800171C8;
  result = 0;
  if ( !qword_1800171C8 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IDsmControl,&_GUID const IID_IDsmControl,&_GUID const LIBID_DsmApiLib,1,0,ATL::CComTypeInfoHolder>::_tih,
               a3);
    v6 = qword_1800171C8;
  }
  *a4 = v6;
  if ( qword_1800171C8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_1800171C8 + 8LL))(qword_1800171C8);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000a800  push    rbx
0x18000a802  sub     rsp, 20h
0x18000a806  mov     rbx, r9
0x18000a809  test    edx, edx
0x18000a80b  jz      short loc_18000A814
0x18000a80d  mov     eax, 8002000Bh
0x18000a812  jmp     short loc_18000A861
0x18000a814  test    rbx, rbx
0x18000a817  jnz     short loc_18000A820
0x18000a819  mov     eax, 80004003h
0x18000a81e  jmp     short loc_18000A861
0x18000a820  mov     rcx, cs:qword_1800171C8
0x18000a827  xor     eax, eax
0x18000a829  test    rcx, rcx
0x18000a82c  jnz     short loc_18000A844
0x18000a82e  mov     edx, r8d; lcid
0x18000a831  lea     rcx, ?_tih@?$IDispatchImpl@UIDsmControl@@$1?IID_IDsmControl@@3U_GUID@@B$1?LIBID_DsmApiLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x18000a838  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18000a83d  mov     rcx, cs:qword_1800171C8
0x18000a844  mov     [rbx], rcx
0x18000a847  mov     rcx, cs:qword_1800171C8
0x18000a84e  test    rcx, rcx
0x18000a851  jz      short loc_18000A861
0x18000a853  mov     rax, [rcx]
0x18000a856  mov     rax, [rax+8]
0x18000a85a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a85f  xor     eax, eax
0x18000a861  add     rsp, 20h
0x18000a865  pop     rbx
0x18000a866  retn
```
