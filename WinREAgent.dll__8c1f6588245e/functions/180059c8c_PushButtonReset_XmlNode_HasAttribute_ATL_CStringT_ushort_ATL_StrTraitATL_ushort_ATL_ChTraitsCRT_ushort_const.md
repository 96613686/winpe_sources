# PushButtonReset::XmlNode::HasAttribute(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x180059c8c`
- end: `0x180059e4b`
- name: `?HasAttribute@XmlNode@PushButtonReset@@QEAA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `447`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18005125c`
- `0x180051960`
- `0x180051ab0`

## callees

- `0x180005cc0`
- `0x18003717c`
- `0x180037344`
- `0x180059c8c`
- `0x18005a498`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180059ccf`
- `OLEAUT32!__imp_SysAllocString` at `0x180059ccf`
- `OLEAUT32!__imp_SysFreeString` at `0x180059e24`
- `OLEAUT32!__imp_SysFreeString` at `0x180059e24`

## string_xrefs

- `0x180059d07`: `base\reset\util\src\xml.cpp`
- `0x180059da3`: `base\reset\util\src\xml.cpp`
- `0x180059e05`: `base\reset\util\src\xml.cpp`
- `0x180059d0e`: `PushButtonReset::XmlNode::HasAttribute`
- `0x180059daa`: `PushButtonReset::XmlNode::HasAttribute`
- `0x180059e0c`: `PushButtonReset::XmlNode::HasAttribute`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
bool __fastcall PushButtonReset::XmlNode::HasAttribute(__int64 a1, const OLECHAR **a2)
{
  __int64 v3; // rbx
  BSTR v5; // rax
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, _QWORD, BSTR *); // rbx
  _QWORD *v8; // rax
  int v9; // ebx
  void **v10; // [rsp+40h] [rbp-30h] BYREF
  BSTR v11; // [rsp+48h] [rbp-28h] BYREF
  BSTR bstrString[2]; // [rsp+50h] [rbp-20h] BYREF
  __int64 v13; // [rsp+60h] [rbp-10h]

  v3 = a1 + 24;
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 24) + 72LL))(a1 + 24) )
  {
    PushButtonReset::Logging::Trace(1, L"This node isn't an element, returning false");
    return 0;
  }
  v5 = SysAllocString(*a2);
  v10 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
  v11 = v5;
  if ( !*(_QWORD *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v10) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942414LL,
      "PushButtonReset::XmlNode::HasAttribute",
      "base\\reset\\util\\src\\xml.cpp",
      733,
      L"Cannot allocate bstrName");
    v10 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
    RAII::CleanupInfo<unsigned short *>::Release(&v11);
    return 0;
  }
  *(_OWORD *)bstrString = 0;
  v13 = 0;
  v6 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 24LL))(v3);
  v7 = *(__int64 (__fastcall **)(__int64, _QWORD, BSTR *))(*(_QWORD *)v6 + 352LL);
  v8 = (_QWORD *)((__int64 (__fastcall *)(void ***))v10[4])(&v10);
  v9 = v7(v6, *v8, bstrString);
  if ( v9 < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v9,
      "PushButtonReset::XmlNode::HasAttribute",
      "base\\reset\\util\\src\\xml.cpp",
      741,
      L"Failed to query for attribute %s",
      *a2);
    v10 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
    RAII::CleanupInfo<unsigned short *>::Release(&v11);
    return 0;
  }
  if ( !v9 && LOWORD(bstrString[0]) != 1 )
  {
    if ( LOWORD(bstrString[0]) != 8 )
      PushButtonReset::Logging::TraceErr(
        2,
        2147549183LL,
        "PushButtonReset::XmlNode::HasAttribute",
        "base\\reset\\util\\src\\xml.cpp",
        746,
        L"PbrAssert(%s) failed",
        L"varValue.vt == VT_BSTR");
    SysFreeString(bstrString[1]);
  }
  v10 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
  RAII::CleanupInfo<unsigned short *>::Release(&v11);
  return v9 == 0;
}

```

## disassembly

```asm
0x180059c8c  push    rbp
0x180059c8e  push    rbx
0x180059c8f  push    rsi
0x180059c90  push    rdi
0x180059c91  push    r14
0x180059c93  mov     rbp, rsp
0x180059c96  sub     rsp, 70h
0x180059c9a  mov     rsi, rdx
0x180059c9d  lea     rbx, [rcx+18h]
0x180059ca1  mov     rax, [rbx]
0x180059ca4  mov     rcx, rbx
0x180059ca7  mov     rax, [rax+48h]
0x180059cab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059cb0  test    al, al
0x180059cb2  jz      short loc_180059CCC
0x180059cb4  lea     rdx, aThisNodeIsnTAn; "This node isn't an element, returning f"...
0x180059cbb  mov     ecx, 1
0x180059cc0  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180059cc5  xor     al, al
0x180059cc7  jmp     loc_180059E40
0x180059ccc  mov     rcx, [rsi]; psz
0x180059ccf  call    cs:__imp_SysAllocString
0x180059cd5  lea     r14, ??_7?$CAutoCleanup@PEAG@RAII@@6B@; const RAII::CAutoCleanup<ushort *>::`vftable'
0x180059cdc  mov     [rbp+var_30], r14
0x180059ce0  mov     [rbp+var_28], rax
0x180059ce4  lea     rcx, [rbp+var_30]
0x180059ce8  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180059ced  cmp     qword ptr [rax], 0
0x180059cf1  jnz     short loc_180059D35
0x180059cf3  lea     rax, aCannotAllocate; "Cannot allocate bstrName"
0x180059cfa  mov     [rsp+70h+var_48], rax
0x180059cff  mov     [rsp+70h+var_50], 2DDh
0x180059d07  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x180059d0e  lea     r8, aPushbuttonrese_99; "PushButtonReset::XmlNode::HasAttribute"
0x180059d15  mov     edx, 8007000Eh
0x180059d1a  mov     ecx, 2
0x180059d1f  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180059d24  nop
0x180059d25  mov     [rbp+var_30], r14
0x180059d29  lea     rcx, [rbp+var_28]
0x180059d2d  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x180059d32  nop
0x180059d33  jmp     short loc_180059CC5
0x180059d35  xorps   xmm0, xmm0
0x180059d38  xor     eax, eax
0x180059d3a  movups  xmmword ptr [rbp+bstrString], xmm0
0x180059d3e  mov     [rbp+var_10], rax
0x180059d42  mov     rax, [rbx]
0x180059d45  mov     rcx, rbx
0x180059d48  mov     rax, [rax+18h]
0x180059d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059d51  mov     rdi, rax
0x180059d54  mov     rcx, [rax]
0x180059d57  mov     rbx, [rcx+160h]
0x180059d5e  mov     rcx, [rbp+var_30]
0x180059d62  mov     rax, [rcx+20h]
0x180059d66  lea     rcx, [rbp+var_30]
0x180059d6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059d6f  lea     r8, [rbp+bstrString]
0x180059d73  mov     rdx, [rax]
0x180059d76  mov     rcx, rdi
0x180059d79  mov     rax, rbx
0x180059d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059d81  mov     ebx, eax
0x180059d83  test    eax, eax
0x180059d85  jns     short loc_180059DD1
0x180059d87  mov     rcx, [rsi]
0x180059d8a  mov     [rsp+70h+var_40], rcx
0x180059d8f  lea     rax, aFailedToQueryF; "Failed to query for attribute %s"
0x180059d96  mov     [rsp+70h+var_48], rax
0x180059d9b  mov     [rsp+70h+var_50], 2E5h
0x180059da3  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x180059daa  lea     r8, aPushbuttonrese_99; "PushButtonReset::XmlNode::HasAttribute"
0x180059db1  mov     edx, ebx
0x180059db3  mov     ecx, 2
0x180059db8  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180059dbd  nop
0x180059dbe  mov     [rbp+var_30], r14
0x180059dc2  lea     rcx, [rbp+var_28]
0x180059dc6  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x180059dcb  nop
0x180059dcc  jmp     loc_180059CC5
0x180059dd1  test    ebx, ebx
0x180059dd3  jnz     short loc_180059E2B
0x180059dd5  lea     eax, [rbx+1]
0x180059dd8  cmp     word ptr [rbp+bstrString], ax
0x180059ddc  jz      short loc_180059E2B
0x180059dde  cmp     word ptr [rbp+bstrString], 8
0x180059de3  jz      short loc_180059E20
0x180059de5  lea     rax, aVarvalueVtVtBs; "varValue.vt == VT_BSTR"
0x180059dec  mov     [rsp+70h+var_40], rax
0x180059df1  lea     rax, aPbrassertSFail; "PbrAssert(%s) failed"
0x180059df8  mov     [rsp+70h+var_48], rax
0x180059dfd  mov     [rsp+70h+var_50], 2EAh
0x180059e05  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x180059e0c  lea     r8, aPushbuttonrese_99; "PushButtonReset::XmlNode::HasAttribute"
0x180059e13  mov     edx, 8000FFFFh
0x180059e18  lea     ecx, [rbx+2]
0x180059e1b  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180059e20  mov     rcx, [rbp+bstrString+8]; bstrString
0x180059e24  call    cs:__imp_SysFreeString
0x180059e2a  nop
0x180059e2b  test    ebx, ebx
0x180059e2d  setz    bl
0x180059e30  mov     [rbp+var_30], r14
0x180059e34  lea     rcx, [rbp+var_28]
0x180059e38  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x180059e3d  nop
0x180059e3e  mov     al, bl
0x180059e40  add     rsp, 70h
0x180059e44  pop     r14
0x180059e46  pop     rdi
0x180059e47  pop     rsi
0x180059e48  pop     rbx
0x180059e49  pop     rbp
0x180059e4a  retn
```
