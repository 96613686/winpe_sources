# PushButtonReset::XmlNode::SetAttribute(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x18005b518`
- end: `0x18005b7cc`
- name: `?SetAttribute@XmlNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z`
- size: `692`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x18005338c`

## callees

- `0x180005cc0`
- `0x180037344`
- `0x18005a498`
- `0x18005b518`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18005b581`
- `OLEAUT32!__imp_SysAllocString` at `0x18005b5f2`
- `OLEAUT32!__imp_SysAllocString` at `0x18005b581`
- `OLEAUT32!__imp_SysAllocString` at `0x18005b5f2`

## string_xrefs

- `0x18005b557`: `base\reset\util\src\xml.cpp`
- `0x18005b5b9`: `base\reset\util\src\xml.cpp`
- `0x18005b623`: `base\reset\util\src\xml.cpp`
- `0x18005b6c6`: `base\reset\util\src\xml.cpp`
- `0x18005b759`: `base\reset\util\src\xml.cpp`
- `0x18005b55e`: `PushButtonReset::XmlNode::SetAttribute`
- `0x18005b5c0`: `PushButtonReset::XmlNode::SetAttribute`
- `0x18005b62a`: `PushButtonReset::XmlNode::SetAttribute`
- `0x18005b6cd`: `PushButtonReset::XmlNode::SetAttribute`
- `0x18005b760`: `PushButtonReset::XmlNode::SetAttribute`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PushButtonReset::XmlNode::SetAttribute(__int64 a1, const OLECHAR **a2, const OLECHAR **a3)
{
  BSTR v7; // rax
  BSTR v8; // rax
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, _QWORD, __int128 *); // rbx
  _QWORD *v11; // rax
  int v12; // ebx
  void **v13; // [rsp+40h] [rbp-40h] BYREF
  BSTR v14; // [rsp+48h] [rbp-38h] BYREF
  void **v15; // [rsp+50h] [rbp-30h] BYREF
  BSTR v16; // [rsp+58h] [rbp-28h] BYREF
  __int128 v17; // [rsp+60h] [rbp-20h] BYREF
  __int64 v18; // [rsp+70h] [rbp-10h]
  __int64 v19; // [rsp+B0h] [rbp+30h] BYREF

  if ( *(_DWORD *)(a1 + 56) != 1 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147946717LL,
      "PushButtonReset::XmlNode::SetAttribute",
      "base\\reset\\util\\src\\xml.cpp",
      788,
      L"This node is not an element");
    return 2147946717LL;
  }
  v7 = SysAllocString(*a2);
  v13 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
  v14 = v7;
  if ( !*(_QWORD *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v13) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942414LL,
      "PushButtonReset::XmlNode::SetAttribute",
      "base\\reset\\util\\src\\xml.cpp",
      792,
      L"Failed to allocate bstrName");
    v13 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
    RAII::CleanupInfo<unsigned short *>::Release(&v14);
    return 2147942414LL;
  }
  v8 = SysAllocString(*a3);
  v15 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
  v16 = v8;
  if ( !*(_QWORD *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v15) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942414LL,
      "PushButtonReset::XmlNode::SetAttribute",
      "base\\reset\\util\\src\\xml.cpp",
      795,
      L"Failed to allocate bstrValue");
    v15 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
    RAII::CleanupInfo<unsigned short *>::Release(&v16);
    v13 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
    RAII::CleanupInfo<unsigned short *>::Release(&v14);
    return 2147942414LL;
  }
  v17 = 0;
  LOWORD(v17) = 8;
  *((_QWORD *)&v17 + 1) = *(_QWORD *)((__int64 (__fastcall *)(void ***))v15[4])(&v15);
  v19 = 0;
  if ( !(*(unsigned __int8 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(a1 + 24) + 64LL))(a1 + 24, &v19) )
    PushButtonReset::Logging::TraceErr(
      2,
      2147549183LL,
      "PushButtonReset::XmlNode::SetAttribute",
      "base\\reset\\util\\src\\xml.cpp",
      801,
      L"PbrAssert(%s) failed",
      L"m_domElement != nullptr");
  v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 24) + 24LL))(a1 + 24);
  v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v9 + 360LL);
  v11 = (_QWORD *)((__int64 (__fastcall *)(void ***))v13[4])(&v13);
  v18 = 0;
  v12 = v10(v9, *v11, &v17);
  if ( v12 < 0 )
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v12,
      "PushButtonReset::XmlNode::SetAttribute",
      "base\\reset\\util\\src\\xml.cpp",
      803,
      L"Failed to set [%s] to [%s]",
      *a2,
      *a3);
  v15 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
  RAII::CleanupInfo<unsigned short *>::Release(&v16);
  v13 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
  RAII::CleanupInfo<unsigned short *>::Release(&v14);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x18005b518  mov     [rsp-28h+arg_8], rbx
0x18005b51d  mov     [rsp-28h+arg_10], rsi
0x18005b522  push    rbp
0x18005b523  push    rdi
0x18005b524  push    r13
0x18005b526  push    r14
0x18005b528  push    r15
0x18005b52a  mov     rbp, rsp
0x18005b52d  sub     rsp, 80h
0x18005b534  mov     rsi, r8
0x18005b537  mov     r14, rdx
0x18005b53a  mov     rbx, rcx
0x18005b53d  cmp     dword ptr [rcx+38h], 1
0x18005b541  jz      short loc_18005B57E
0x18005b543  lea     rax, aThisNodeIsNotA; "This node is not an element"
0x18005b54a  mov     [rsp+80h+var_58], rax
0x18005b54f  mov     [rsp+80h+var_60], 314h
0x18005b557  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005b55e  lea     r8, aPushbuttonrese_83; "PushButtonReset::XmlNode::SetAttribute"
0x18005b565  mov     edx, 800710DDh
0x18005b56a  mov     ecx, 2
0x18005b56f  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005b574  mov     eax, 800710DDh
0x18005b579  jmp     loc_18005B7B0
0x18005b57e  mov     rcx, [rdx]; psz
0x18005b581  call    cs:__imp_SysAllocString
0x18005b587  lea     r15, ??_7?$CAutoCleanup@PEAG@RAII@@6B@; const RAII::CAutoCleanup<ushort *>::`vftable'
0x18005b58e  mov     [rbp+var_40], r15
0x18005b592  mov     [rbp+var_38], rax
0x18005b596  lea     rcx, [rbp+var_40]
0x18005b59a  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18005b59f  cmp     qword ptr [rax], 0
0x18005b5a3  jnz     short loc_18005B5EF
0x18005b5a5  lea     rax, aFailedToAlloca_39; "Failed to allocate bstrName"
0x18005b5ac  mov     [rsp+80h+var_58], rax
0x18005b5b1  mov     [rsp+80h+var_60], 318h
0x18005b5b9  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005b5c0  lea     r8, aPushbuttonrese_83; "PushButtonReset::XmlNode::SetAttribute"
0x18005b5c7  mov     edx, 8007000Eh
0x18005b5cc  mov     ecx, 2
0x18005b5d1  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005b5d6  nop
0x18005b5d7  mov     [rbp+var_40], r15
0x18005b5db  lea     rcx, [rbp+var_38]
0x18005b5df  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005b5e4  nop
0x18005b5e5  mov     eax, 8007000Eh
0x18005b5ea  jmp     loc_18005B7B0
0x18005b5ef  mov     rcx, [rsi]; psz
0x18005b5f2  call    cs:__imp_SysAllocString
0x18005b5f8  mov     [rbp+var_30], r15
0x18005b5fc  mov     [rbp+var_28], rax
0x18005b600  lea     rcx, [rbp+var_30]
0x18005b604  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18005b609  cmp     qword ptr [rax], 0
0x18005b60d  jnz     short loc_18005B65F
0x18005b60f  lea     rax, aFailedToAlloca_27; "Failed to allocate bstrValue"
0x18005b616  mov     [rsp+80h+var_58], rax
0x18005b61b  mov     [rsp+80h+var_60], 31Bh
0x18005b623  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005b62a  lea     r8, aPushbuttonrese_83; "PushButtonReset::XmlNode::SetAttribute"
0x18005b631  mov     edx, 8007000Eh
0x18005b636  mov     ecx, 2
0x18005b63b  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005b640  nop
0x18005b641  mov     [rbp+var_30], r15
0x18005b645  lea     rcx, [rbp+var_28]
0x18005b649  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005b64e  nop
0x18005b64f  mov     [rbp+var_40], r15
0x18005b653  lea     rcx, [rbp+var_38]
0x18005b657  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005b65c  nop
0x18005b65d  jmp     short loc_18005B5E5
0x18005b65f  xorps   xmm0, xmm0
0x18005b662  xor     r13d, r13d
0x18005b665  movups  [rbp+var_20], xmm0
0x18005b669  lea     eax, [r13+8]
0x18005b66d  mov     word ptr [rbp+var_20], ax
0x18005b671  mov     rax, [rbp+var_30]
0x18005b675  lea     rcx, [rbp+var_30]
0x18005b679  mov     rax, [rax+20h]
0x18005b67d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b682  mov     rcx, [rax]
0x18005b685  mov     qword ptr [rbp+var_20+8], rcx
0x18005b689  mov     [rbp+arg_0], r13
0x18005b68d  mov     rax, [rbx+18h]
0x18005b691  lea     rdx, [rbp+arg_0]
0x18005b695  lea     rcx, [rbx+18h]
0x18005b699  mov     rax, [rax+40h]
0x18005b69d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b6a2  test    al, al
0x18005b6a4  jnz     short loc_18005B6E2
0x18005b6a6  lea     rax, aMDomelementNul; "m_domElement != nullptr"
0x18005b6ad  mov     [rsp+80h+var_50], rax
0x18005b6b2  lea     rax, aPbrassertSFail; "PbrAssert(%s) failed"
0x18005b6b9  mov     [rsp+80h+var_58], rax
0x18005b6be  mov     [rsp+80h+var_60], 321h
0x18005b6c6  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005b6cd  lea     r8, aPushbuttonrese_83; "PushButtonReset::XmlNode::SetAttribute"
0x18005b6d4  mov     edx, 8000FFFFh
0x18005b6d9  lea     ecx, [r13+2]
0x18005b6dd  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005b6e2  mov     rax, [rbx+18h]
0x18005b6e6  lea     rcx, [rbx+18h]
0x18005b6ea  mov     rax, [rax+18h]
0x18005b6ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b6f3  mov     rdi, rax
0x18005b6f6  mov     rcx, [rax]
0x18005b6f9  mov     rbx, [rcx+168h]
0x18005b700  mov     rcx, [rbp+var_40]
0x18005b704  mov     rax, [rcx+20h]
0x18005b708  lea     rcx, [rbp+var_40]
0x18005b70c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b711  movups  xmm0, [rbp+var_20]
0x18005b715  movaps  [rbp+var_20], xmm0
0x18005b719  mov     [rbp+var_10], r13
0x18005b71d  lea     r8, [rbp+var_20]
0x18005b721  mov     rdx, [rax]
0x18005b724  mov     rcx, rdi
0x18005b727  mov     rax, rbx
0x18005b72a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b72f  mov     ebx, eax
0x18005b731  test    eax, eax
0x18005b733  jns     short loc_18005B792
0x18005b735  mov     rcx, [rsi]
0x18005b738  mov     [rsp+80h+var_48], rcx
0x18005b73d  mov     rcx, [r14]
0x18005b740  mov     [rsp+80h+var_50], rcx
0x18005b745  lea     rax, aFailedToSetSTo; "Failed to set [%s] to [%s]"
0x18005b74c  mov     [rsp+80h+var_58], rax
0x18005b751  mov     [rsp+80h+var_60], 323h
0x18005b759  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005b760  lea     r8, aPushbuttonrese_83; "PushButtonReset::XmlNode::SetAttribute"
0x18005b767  mov     edx, ebx
0x18005b769  mov     ecx, 2
0x18005b76e  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005b773  nop
0x18005b774  mov     [rbp+var_30], r15
0x18005b778  lea     rcx, [rbp+var_28]
0x18005b77c  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005b781  nop
0x18005b782  mov     [rbp+var_40], r15
0x18005b786  lea     rcx, [rbp+var_38]
0x18005b78a  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005b78f  nop
0x18005b790  jmp     short loc_18005B7AE
0x18005b792  mov     [rbp+var_30], r15
0x18005b796  lea     rcx, [rbp+var_28]
0x18005b79a  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005b79f  nop
0x18005b7a0  mov     [rbp+var_40], r15
0x18005b7a4  lea     rcx, [rbp+var_38]
0x18005b7a8  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005b7ad  nop
0x18005b7ae  mov     eax, ebx
0x18005b7b0  lea     r11, [rsp+80h+var_s0]
0x18005b7b8  mov     rbx, [r11+38h]
0x18005b7bc  mov     rsi, [r11+40h]
0x18005b7c0  mov     rsp, r11
0x18005b7c3  pop     r15
0x18005b7c5  pop     r14
0x18005b7c7  pop     r13
0x18005b7c9  pop     rdi
0x18005b7ca  pop     rbp
0x18005b7cb  retn
```
