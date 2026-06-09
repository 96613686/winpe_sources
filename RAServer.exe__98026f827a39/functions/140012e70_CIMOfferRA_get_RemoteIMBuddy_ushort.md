# CIMOfferRA::get_RemoteIMBuddy(ushort * *)

- ea: `0x140012e70`
- end: `0x140012ebf`
- name: `?get_RemoteIMBuddy@CIMOfferRA@@UEAAJPEAPEAG@Z`
- size: `79`
- prototype: `__int64 __fastcall(LPCSTR *this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14000e778`
- `0x140012e70`
- `0x140015240`

## string_xrefs

- `0x140012e98`: `base\diagnosis\ra\dcom\src\raimoffer.cpp`

## pseudocode

```c
__int64 __fastcall CIMOfferRA::get_RemoteIMBuddy(LPCSTR *this, unsigned __int16 **a2)
{
  if ( a2 )
  {
    *a2 = ATL::CComBSTR::Copy(this + 6);
    return 0;
  }
  else
  {
    CEventLogger::LogError(
      (CEventLogger *)this,
      0,
      L"base\\diagnosis\\ra\\dcom\\src\\raimoffer.cpp",
      0xA4u,
      L"CIMOfferRA::get_RemoteIMBuddy",
      0x80004003);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x140012e70  push    rbx
0x140012e72  sub     rsp, 30h
0x140012e76  mov     rbx, rdx
0x140012e79  test    rdx, rdx
0x140012e7c  jnz     short loc_140012EAB
0x140012e7e  lea     rax, aCimofferraGetR_0; "CIMOfferRA::get_RemoteIMBuddy"
0x140012e85  mov     [rsp+38h+var_10], 80004003h; unsigned int
0x140012e8d  mov     r9d, 0A4h; unsigned int
0x140012e93  mov     [rsp+38h+var_18], rax; unsigned __int16 *
0x140012e98  lea     r8, aBaseDiagnosisR_4; "base\\diagnosis\\ra\\dcom\\src\\raimoff"...
0x140012e9f  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140012ea4  mov     eax, 80004003h
0x140012ea9  jmp     short loc_140012EB9
0x140012eab  add     rcx, 30h ; '0'; this
0x140012eaf  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x140012eb4  mov     [rbx], rax
0x140012eb7  xor     eax, eax
0x140012eb9  add     rsp, 30h
0x140012ebd  pop     rbx
0x140012ebe  retn
```
