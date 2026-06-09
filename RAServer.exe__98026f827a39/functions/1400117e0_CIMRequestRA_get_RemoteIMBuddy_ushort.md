# CIMRequestRA::get_RemoteIMBuddy(ushort * *)

- ea: `0x1400117e0`
- end: `0x140011839`
- name: `?get_RemoteIMBuddy@CIMRequestRA@@UEAAJPEAPEAG@Z`
- size: `89`
- prototype: `__int64 __fastcall(LPCSTR *this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14000e778`
- `0x1400117e0`
- `0x140015240`

## string_xrefs

- `0x140011808`: `base\diagnosis\ra\dcom\src\raimrequest.cpp`

## pseudocode

```c
__int64 __fastcall CIMRequestRA::get_RemoteIMBuddy(LPCSTR *this, unsigned __int16 **a2)
{
  unsigned __int16 *v4; // rax

  if ( a2 )
  {
    v4 = ATL::CComBSTR::Copy(this + 7);
    *a2 = v4;
    return v4 == 0 ? 0x8007000E : 0;
  }
  else
  {
    CEventLogger::LogError(
      (CEventLogger *)this,
      0,
      L"base\\diagnosis\\ra\\dcom\\src\\raimrequest.cpp",
      0xCEu,
      L"CIMRequestRA::get_RemoteIMBuddy",
      0x80004003);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1400117e0  push    rbx
0x1400117e2  sub     rsp, 30h
0x1400117e6  mov     rbx, rdx
0x1400117e9  test    rdx, rdx
0x1400117ec  jnz     short loc_14001181B
0x1400117ee  lea     rax, aCimrequestraGe_0; "CIMRequestRA::get_RemoteIMBuddy"
0x1400117f5  mov     [rsp+38h+var_10], 80004003h; unsigned int
0x1400117fd  mov     r9d, 0CEh; unsigned int
0x140011803  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x140011808  lea     r8, aBaseDiagnosisR_1; "base\\diagnosis\\ra\\dcom\\src\\raimreq"...
0x14001180f  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140011814  mov     eax, 80004003h
0x140011819  jmp     short loc_140011833
0x14001181b  add     rcx, 38h ; '8'; this
0x14001181f  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x140011824  mov     [rbx], rax
0x140011827  neg     rax
0x14001182a  sbb     eax, eax
0x14001182c  not     eax
0x14001182e  and     eax, 8007000Eh
0x140011833  add     rsp, 30h
0x140011837  pop     rbx
0x140011838  retn
```
