# ATL::IDispatchImpl<IMsMpComFactory,&_GUID const IID_IMsMpComFactory,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x180004110`
- end: `0x180004177`
- name: `?GetTypeInfo@?$IDispatchImpl@UIMsMpComFactory@@$1?IID_IMsMpComFactory@@3U_GUID@@B$1?LIBID_MpComExportsLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003e28`
- `0x180004110`
- `0x18000a010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IMsMpComFactory,&_GUID const IID_IMsMpComFactory,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
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
  v6 = qword_180012098;
  result = 0;
  if ( !qword_180012098 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(
               (ATL::CComTypeInfoHolder *)ATL::IDispatchImpl<IMsMpComFactory,&_GUID const IID_IMsMpComFactory,&_GUID const LIBID_MpComExportsLib,1,0,ATL::CComTypeInfoHolder>::_tih,
               a3);
    v6 = qword_180012098;
  }
  *a4 = v6;
  if ( qword_180012098 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)qword_180012098 + 8LL))(qword_180012098);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004110  push    rbx
0x180004112  sub     rsp, 20h
0x180004116  mov     rbx, r9
0x180004119  test    edx, edx
0x18000411b  jz      short loc_180004124
0x18000411d  mov     eax, 8002000Bh
0x180004122  jmp     short loc_180004171
0x180004124  test    rbx, rbx
0x180004127  jnz     short loc_180004130
0x180004129  mov     eax, 80004003h
0x18000412e  jmp     short loc_180004171
0x180004130  mov     rcx, cs:qword_180012098
0x180004137  xor     eax, eax
0x180004139  test    rcx, rcx
0x18000413c  jnz     short loc_180004154
0x18000413e  mov     edx, r8d; lcid
0x180004141  lea     rcx, ?_tih@?$IDispatchImpl@UIMsMpComFactory@@$1?IID_IMsMpComFactory@@3U_GUID@@B$1?LIBID_MpComExportsLib@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@1VCComTypeInfoHolder@2@A; this
0x180004148  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x18000414d  mov     rcx, cs:qword_180012098
0x180004154  mov     [rbx], rcx
0x180004157  mov     rcx, cs:qword_180012098
0x18000415e  test    rcx, rcx
0x180004161  jz      short loc_180004171
0x180004163  mov     rax, [rcx]
0x180004166  mov     rax, [rax+8]
0x18000416a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000416f  xor     eax, eax
0x180004171  add     rsp, 20h
0x180004175  pop     rbx
0x180004176  retn
```
