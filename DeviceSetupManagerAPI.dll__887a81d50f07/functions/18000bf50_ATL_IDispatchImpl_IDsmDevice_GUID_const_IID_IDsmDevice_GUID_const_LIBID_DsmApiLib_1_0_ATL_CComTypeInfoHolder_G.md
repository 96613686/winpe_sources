# ATL::IDispatchImpl<IDsmDevice,&_GUID const IID_IDsmDevice,&_GUID const LIBID_DsmApiLib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x18000bf50`
- end: `0x18000bfb7`
- name: `?GetTypeInfo@?$IDispatchImpl@UIDsmDevice@@$1?IID_IDsmDevice@@3U_GUID@@B$1?LIBID_DsmApiLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `103`
- prototype: `__int64 __fastcall(__int64, int, LCID, __int64 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000a584`
- `0x18000bf50`
- `0x18000f010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IDsmDevice,&_GUID const IID_IDsmDevice,&_GUID const LIBID_DsmApiLib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
  v6 = qword_180017208;
  result = 0;
  if ( !qword_180017208 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IDsmDevice,&_GUID const IID_IDsmDevice,&_GUID const LIBID_DsmApiLib,1,0,ATL::CComTypeInfoHolder>::_tih,
               a3);
    v6 = qword_180017208;
  }
  *a4 = v6;
  if ( qword_180017208 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_180017208 + 8LL))(qword_180017208);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000bf50  push    rbx
0x18000bf52  sub     rsp, 20h
0x18000bf56  mov     rbx, r9
0x18000bf59  test    edx, edx
0x18000bf5b  jz      short loc_18000BF64
0x18000bf5d  mov     eax, 8002000Bh
0x18000bf62  jmp     short loc_18000BFB1
0x18000bf64  test    rbx, rbx
0x18000bf67  jnz     short loc_18000BF70
0x18000bf69  mov     eax, 80004003h
0x18000bf6e  jmp     short loc_18000BFB1
0x18000bf70  mov     rcx, cs:qword_180017208
0x18000bf77  xor     eax, eax
0x18000bf79  test    rcx, rcx
0x18000bf7c  jnz     short loc_18000BF94
0x18000bf7e  mov     edx, r8d; lcid
0x18000bf81  lea     rcx, ?_tih@?$IDispatchImpl@UIDsmDevice@@$1?IID_IDsmDevice@@3U_GUID@@B$1?LIBID_DsmApiLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x18000bf88  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18000bf8d  mov     rcx, cs:qword_180017208
0x18000bf94  mov     [rbx], rcx
0x18000bf97  mov     rcx, cs:qword_180017208
0x18000bf9e  test    rcx, rcx
0x18000bfa1  jz      short loc_18000BFB1
0x18000bfa3  mov     rax, [rcx]
0x18000bfa6  mov     rax, [rax+8]
0x18000bfaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bfaf  xor     eax, eax
0x18000bfb1  add     rsp, 20h
0x18000bfb5  pop     rbx
0x18000bfb6  retn
```
