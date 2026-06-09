# ATL::IDispatchImpl<IBrowserCap,&_GUID const IID_IBrowserCap,&_GUID const LIBID_BrowserType,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(uint,ulong,ITypeInfo * *)

- ea: `0x180004330`
- end: `0x180004390`
- name: `?GetTypeInfo@?$IDispatchImpl@UIBrowserCap@@$1?IID_IBrowserCap@@3U_GUID@@B$1?LIBID_BrowserType@@3U3@B$00$0A@VCComTypeInfoHolder@ATL@@@ATL@@UEAAJIKPEAPEAUITypeInfo@@@Z`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003f7c`
- `0x180004330`
- `0x18000d010`

## pseudocode

```c
__int64 __fastcall ATL::IDispatchImpl<IBrowserCap,&_GUID const IID_IBrowserCap,&_GUID const LIBID_BrowserType,1,0,ATL::CComTypeInfoHolder>::GetTypeInfo(
        __int64 a1,
        int a2,
        LCID a3,
        struct ITypeInfo **a4)
{
  __int64 result; // rax
  struct ITypeInfo *v6; // rcx

  if ( a2 )
    return 2147614731LL;
  if ( !a4 )
    return 2147500035LL;
  v6 = qword_1800120A8;
  result = 0;
  if ( !qword_1800120A8 )
  {
    result = ATL::CComTypeInfoHolder::GetTI(0, a3);
    v6 = qword_1800120A8;
  }
  *a4 = v6;
  if ( qword_1800120A8 )
  {
    ((void (__fastcall *)(struct ITypeInfo *))qword_1800120A8->lpVtbl->AddRef)(qword_1800120A8);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180004330  push    rbx
0x180004332  sub     rsp, 20h
0x180004336  mov     rbx, r9
0x180004339  test    edx, edx
0x18000433b  jz      short loc_180004344
0x18000433d  mov     eax, 8002000Bh
0x180004342  jmp     short loc_18000438A
0x180004344  test    rbx, rbx
0x180004347  jnz     short loc_180004350
0x180004349  mov     eax, 80004003h
0x18000434e  jmp     short loc_18000438A
0x180004350  mov     rcx, cs:qword_1800120A8; this
0x180004357  xor     eax, eax
0x180004359  test    rcx, rcx
0x18000435c  jnz     short loc_18000436D
0x18000435e  mov     edx, r8d; unsigned int
0x180004361  call    ?GetTI@CComTypeInfoHolder@ATL@@QEAAJK@Z; ATL::CComTypeInfoHolder::GetTI(ulong)
0x180004366  mov     rcx, cs:qword_1800120A8
0x18000436d  mov     [rbx], rcx
0x180004370  mov     rcx, cs:qword_1800120A8
0x180004377  test    rcx, rcx
0x18000437a  jz      short loc_18000438A
0x18000437c  mov     rax, [rcx]
0x18000437f  mov     rax, [rax+8]
0x180004383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004388  xor     eax, eax
0x18000438a  add     rsp, 20h
0x18000438e  pop     rbx
0x18000438f  retn
```
