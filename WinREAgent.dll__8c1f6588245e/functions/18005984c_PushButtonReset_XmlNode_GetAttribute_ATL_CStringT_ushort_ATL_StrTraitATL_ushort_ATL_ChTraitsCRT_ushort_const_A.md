# PushButtonReset::XmlNode::GetAttribute(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)

- ea: `0x18005984c`
- end: `0x180059a39`
- name: `?GetAttribute@XmlNode@PushButtonReset@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z`
- size: `493`
- prototype: ``
- caller_count: `4`
- callee_count: `7`
- tags: `registry_config, service_task`

## callers

- `0x1800520a4`
- `0x180052194`
- `0x1800521f8`
- `0x1800522e8`

## callees

- `0x180005cc0`
- `0x180011ef4`
- `0x180012968`
- `0x180037344`
- `0x18005984c`
- `0x18005a498`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x1800598bc`
- `OLEAUT32!__imp_SysAllocString` at `0x1800598bc`

## string_xrefs

- `0x180059892`: `base\reset\util\src\xml.cpp`
- `0x1800598f4`: `base\reset\util\src\xml.cpp`
- `0x180059998`: `base\reset\util\src\xml.cpp`
- `0x180059899`: `PushButtonReset::XmlNode::GetAttribute`
- `0x1800598fb`: `PushButtonReset::XmlNode::GetAttribute`
- `0x18005999f`: `PushButtonReset::XmlNode::GetAttribute`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PushButtonReset::XmlNode::GetAttribute(__int64 a1, const OLECHAR **a2, __int64 a3)
{
  __int64 v5; // rbx
  BSTR v7; // rax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, _QWORD, __int128 *); // rbx
  _QWORD *v10; // rax
  int v11; // ebx
  _QWORD *v12; // rax
  unsigned int v13; // eax
  __int64 v14; // rcx
  void **v15; // [rsp+40h] [rbp-19h] BYREF
  BSTR v16; // [rsp+48h] [rbp-11h] BYREF
  void **v17; // [rsp+50h] [rbp-9h] BYREF
  __int64 v18; // [rsp+58h] [rbp-1h] BYREF
  __int128 v19; // [rsp+60h] [rbp+7h] BYREF
  __int64 v20; // [rsp+70h] [rbp+17h]

  v5 = a1 + 24;
  if ( (*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 24) + 72LL))(a1 + 24) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147946717LL,
      "PushButtonReset::XmlNode::GetAttribute",
      "base\\reset\\util\\src\\xml.cpp",
      759,
      L"This node is not an element");
    return 2147946717LL;
  }
  v7 = SysAllocString(*a2);
  v15 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
  v16 = v7;
  if ( !*(_QWORD *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v15) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942414LL,
      "PushButtonReset::XmlNode::GetAttribute",
      "base\\reset\\util\\src\\xml.cpp",
      763,
      L"Failed to allocate bstrName");
    v15 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
    RAII::CleanupInfo<unsigned short *>::Release(&v16);
    return 2147942414LL;
  }
  v19 = 0;
  v20 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 24LL))(v5);
  v9 = *(__int64 (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v8 + 352LL);
  v10 = (_QWORD *)((__int64 (__fastcall *)(void ***))v15[4])(&v15);
  v11 = v9(v8, *v10, &v19);
  if ( v11 >= 0 )
  {
    if ( (_WORD)v19 == 1 )
    {
      v15 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
      RAII::CleanupInfo<unsigned short *>::Release(&v16);
      return 2147943568LL;
    }
    v17 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
    v18 = *((_QWORD *)&v19 + 1);
    v12 = (_QWORD *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v17);
    v13 = ATL::CSimpleStringT<unsigned short,0>::StringLength(*v12);
    ATL::CSimpleStringT<unsigned short,0>::SetString(a3, v14, v13);
    v17 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
    RAII::CleanupInfo<unsigned short *>::Release(&v18);
    v15 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
    RAII::CleanupInfo<unsigned short *>::Release(&v16);
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v11,
      "PushButtonReset::XmlNode::GetAttribute",
      "base\\reset\\util\\src\\xml.cpp",
      767,
      L"Failed to query attribute [%s]",
      *a2);
    v15 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
    RAII::CleanupInfo<unsigned short *>::Release(&v16);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18005984c  push    rbp
0x18005984e  push    rbx
0x18005984f  push    rsi
0x180059850  push    rdi
0x180059851  push    r14
0x180059853  push    r15
0x180059855  lea     rbp, [rsp-2Fh]
0x18005985a  sub     rsp, 88h
0x180059861  mov     r14, r8
0x180059864  mov     rsi, rdx
0x180059867  lea     rbx, [rcx+18h]
0x18005986b  mov     rax, [rbx]
0x18005986e  mov     rcx, rbx
0x180059871  mov     rax, [rax+48h]
0x180059875  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005987a  test    al, al
0x18005987c  jz      short loc_1800598B9
0x18005987e  lea     rax, aThisNodeIsNotA; "This node is not an element"
0x180059885  mov     [rsp+0B0h+var_88], rax
0x18005988a  mov     [rsp+0B0h+var_90], 2F7h
0x180059892  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x180059899  lea     r8, aPushbuttonrese_30; "PushButtonReset::XmlNode::GetAttribute"
0x1800598a0  mov     edx, 800710DDh
0x1800598a5  mov     ecx, 2
0x1800598aa  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800598af  mov     eax, 800710DDh
0x1800598b4  jmp     loc_180059A29
0x1800598b9  mov     rcx, [rsi]; psz
0x1800598bc  call    cs:__imp_SysAllocString
0x1800598c2  lea     r15, ??_7?$CAutoCleanup@PEAG@RAII@@6B@; const RAII::CAutoCleanup<ushort *>::`vftable'
0x1800598c9  mov     [rbp+57h+var_70], r15
0x1800598cd  mov     [rbp+57h+var_68], rax
0x1800598d1  lea     rcx, [rbp+57h+var_70]
0x1800598d5  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x1800598da  cmp     qword ptr [rax], 0
0x1800598de  jnz     short loc_18005992A
0x1800598e0  lea     rax, aFailedToAlloca_39; "Failed to allocate bstrName"
0x1800598e7  mov     [rsp+0B0h+var_88], rax
0x1800598ec  mov     [rsp+0B0h+var_90], 2FBh
0x1800598f4  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x1800598fb  lea     r8, aPushbuttonrese_30; "PushButtonReset::XmlNode::GetAttribute"
0x180059902  mov     edx, 8007000Eh
0x180059907  mov     ecx, 2
0x18005990c  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180059911  nop
0x180059912  mov     [rbp+57h+var_70], r15
0x180059916  lea     rcx, [rbp+57h+var_68]
0x18005991a  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005991f  nop
0x180059920  mov     eax, 8007000Eh
0x180059925  jmp     loc_180059A29
0x18005992a  xorps   xmm0, xmm0
0x18005992d  xor     eax, eax
0x18005992f  movups  [rbp+57h+var_50], xmm0
0x180059933  mov     [rbp+57h+var_40], rax
0x180059937  mov     rax, [rbx]
0x18005993a  mov     rcx, rbx
0x18005993d  mov     rax, [rax+18h]
0x180059941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059946  mov     rdi, rax
0x180059949  mov     rcx, [rax]
0x18005994c  mov     rbx, [rcx+160h]
0x180059953  mov     rcx, [rbp+57h+var_70]
0x180059957  mov     rax, [rcx+20h]
0x18005995b  lea     rcx, [rbp+57h+var_70]
0x18005995f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059964  lea     r8, [rbp+57h+var_50]
0x180059968  mov     rdx, [rax]
0x18005996b  mov     rcx, rdi
0x18005996e  mov     rax, rbx
0x180059971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059976  mov     ebx, eax
0x180059978  test    eax, eax
0x18005997a  jns     short loc_1800599C3
0x18005997c  mov     rcx, [rsi]
0x18005997f  mov     [rsp+0B0h+var_80], rcx
0x180059984  lea     rax, aFailedToQueryA; "Failed to query attribute [%s]"
0x18005998b  mov     [rsp+0B0h+var_88], rax
0x180059990  mov     [rsp+0B0h+var_90], 2FFh
0x180059998  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005999f  lea     r8, aPushbuttonrese_30; "PushButtonReset::XmlNode::GetAttribute"
0x1800599a6  mov     edx, ebx
0x1800599a8  mov     ecx, 2
0x1800599ad  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800599b2  nop
0x1800599b3  mov     [rbp+57h+var_70], r15
0x1800599b7  lea     rcx, [rbp+57h+var_68]
0x1800599bb  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x1800599c0  nop
0x1800599c1  jmp     short loc_180059A27
0x1800599c3  cmp     word ptr [rbp+57h+var_50], 1
0x1800599c8  jnz     short loc_1800599DF
0x1800599ca  mov     [rbp+57h+var_70], r15
0x1800599ce  lea     rcx, [rbp+57h+var_68]
0x1800599d2  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x1800599d7  nop
0x1800599d8  mov     eax, 80070490h
0x1800599dd  jmp     short loc_180059A29
0x1800599df  mov     [rbp+57h+var_60], r15
0x1800599e3  mov     rax, qword ptr [rbp+57h+var_50+8]
0x1800599e7  mov     [rbp+57h+var_58], rax
0x1800599eb  lea     rcx, [rbp+57h+var_60]
0x1800599ef  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x1800599f4  mov     rcx, [rax]
0x1800599f7  call    ?StringLength@?$CSimpleStringT@G$0A@@ATL@@SAHPEBG@Z; ATL::CSimpleStringT<ushort,0>::StringLength(ushort const *)
0x1800599fc  mov     r8d, eax
0x1800599ff  mov     rdx, rcx
0x180059a02  mov     rcx, r14
0x180059a05  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180059a0a  nop
0x180059a0b  mov     [rbp+57h+var_60], r15
0x180059a0f  lea     rcx, [rbp+57h+var_58]
0x180059a13  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x180059a18  nop
0x180059a19  mov     [rbp+57h+var_70], r15
0x180059a1d  lea     rcx, [rbp+57h+var_68]
0x180059a21  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x180059a26  nop
0x180059a27  mov     eax, ebx
0x180059a29  add     rsp, 88h
0x180059a30  pop     r15
0x180059a32  pop     r14
0x180059a34  pop     rdi
0x180059a35  pop     rsi
0x180059a36  pop     rbx
0x180059a37  pop     rbp
0x180059a38  retn
```
