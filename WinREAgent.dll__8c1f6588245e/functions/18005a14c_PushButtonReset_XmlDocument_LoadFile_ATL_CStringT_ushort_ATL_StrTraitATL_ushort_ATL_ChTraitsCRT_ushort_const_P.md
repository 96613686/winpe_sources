# PushButtonReset::XmlDocument::LoadFile(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::XmlDocument * *)

- ea: `0x18005a14c`
- end: `0x18005a461`
- name: `?LoadFile@XmlDocument@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z`
- size: `789`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task`

## callers

- `0x180052528`

## callees

- `0x180005cc0`
- `0x180023620`
- `0x180037344`
- `0x1800527c0`
- `0x180059054`
- `0x18005a14c`
- `0x18005a498`
- `0x18005a68c`
- `0x18006f010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18005a1c9`
- `OLEAUT32!__imp_SysAllocString` at `0x18005a1c9`

## string_xrefs

- `0x18005a1a8`: `base\reset\util\src\xml.cpp`
- `0x18005a200`: `base\reset\util\src\xml.cpp`
- `0x18005a2d1`: `base\reset\util\src\xml.cpp`
- `0x18005a3ae`: `base\reset\util\src\xml.cpp`
- `0x18005a3e4`: `base\reset\util\src\xml.cpp`
- `0x18005a194`: `Failed to initialize XmlDocument`
- `0x18005a1ec`: `Failed to allocate path`
- `0x18005a1af`: `PushButtonReset::XmlDocument::LoadFile`
- `0x18005a207`: `PushButtonReset::XmlDocument::LoadFile`
- `0x18005a2d8`: `PushButtonReset::XmlDocument::LoadFile`
- `0x18005a3b5`: `PushButtonReset::XmlDocument::LoadFile`
- `0x18005a3eb`: `PushButtonReset::XmlDocument::LoadFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall PushButtonReset::XmlDocument::LoadFile(const OLECHAR **a1, _QWORD *a2)
{
  struct PushButtonReset::XmlDocument **v4; // rax
  int v5; // ebx
  BSTR v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rdi
  int (__fastcall *v11)(__int64, __int64); // rbx
  __int64 v12; // rax
  struct IXMLDOMParseError *v13; // rax
  int v14; // eax
  __int64 v15; // rax
  void **v17; // [rsp+40h] [rbp-29h] BYREF
  BSTR v18; // [rsp+48h] [rbp-21h] BYREF
  void **v19; // [rsp+50h] [rbp-19h] BYREF
  __int64 v20; // [rsp+58h] [rbp-11h]
  __int128 v21; // [rsp+60h] [rbp-9h] BYREF
  __int64 v22; // [rsp+70h] [rbp+7h]
  __int16 v23; // [rsp+E0h] [rbp+77h] BYREF

  v20 = 0;
  v19 = &RAII::CAutoPbrDelete<PushButtonReset::XmlDocument *>::`vftable';
  v4 = (struct PushButtonReset::XmlDocument **)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v19);
  v5 = PushButtonReset::XmlDocument::Create(v4);
  if ( v5 >= 0 )
  {
    v6 = SysAllocString(*a1);
    v17 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
    v18 = v6;
    if ( *(_QWORD *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v17) )
    {
      v21 = 0;
      LOWORD(v21) = 8;
      *((_QWORD *)&v21 + 1) = *(_QWORD *)((__int64 (__fastcall *)(void ***))v17[4])(&v17);
      v23 = 0;
      v7 = ((__int64 (__fastcall *)(void ***))v19[3])(&v19);
      v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 24LL))(v7);
      v22 = 0;
      v5 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int16 *))(*(_QWORD *)v8 + 464LL))(v8, &v21, &v23);
      if ( v5 >= 0 )
      {
        if ( v23 )
        {
          v15 = v20;
          v20 = 0;
          *a2 = v15;
          v17 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
          RAII::CleanupInfo<unsigned short *>::Release(&v18);
        }
        else
        {
          *((_QWORD *)&v21 + 1) = 0;
          *(_QWORD *)&v21 = &RAII::CAutoRelease<IXMLDOMParseError *>::`vftable';
          v9 = ((__int64 (__fastcall *)(void ***))v19[3])(&v19);
          v10 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 24LL))(v9);
          v11 = *(int (__fastcall **)(__int64, __int64))(*(_QWORD *)v10 + 480LL);
          v12 = (*(__int64 (__fastcall **)(__int128 *))(v21 + 8))(&v21);
          if ( v11(v10, v12) >= 0 )
          {
            ((void (__fastcall *)(void ***))v19[3])(&v19);
            v13 = (struct IXMLDOMParseError *)(*(__int64 (__fastcall **)(__int128 *))(v21 + 32))(&v21);
            v14 = PushButtonReset::XmlDocument::ReportErrors(v13);
            if ( v14 < 0 )
              PushButtonReset::Logging::TraceErr(
                2,
                (unsigned int)v14,
                "PushButtonReset::XmlDocument::LoadFile",
                "base\\reset\\util\\src\\xml.cpp",
                95,
                L"Failed to report parse error(s)");
          }
          PushButtonReset::Logging::TraceErr(
            2,
            2147942413LL,
            "PushButtonReset::XmlDocument::LoadFile",
            "base\\reset\\util\\src\\xml.cpp",
            100,
            L"The contents of %s cannot be parsed",
            *a1);
          *(_QWORD *)&v21 = &RAII::CAutoRelease<IXMLDOMParseError *>::`vftable';
          RAII::CAutoRelease<IXMLDOMParseError *>::Release(&v21);
          v17 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
          RAII::CleanupInfo<unsigned short *>::Release(&v18);
          v5 = -2147024883;
        }
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v5,
          "PushButtonReset::XmlDocument::LoadFile",
          "base\\reset\\util\\src\\xml.cpp",
          84,
          L"Failed to load document at %s",
          *a1);
        v17 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
        RAII::CleanupInfo<unsigned short *>::Release(&v18);
      }
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147942414LL,
        "PushButtonReset::XmlDocument::LoadFile",
        "base\\reset\\util\\src\\xml.cpp",
        76,
        L"Failed to allocate path");
      v17 = &RAII::CAutoCleanup<unsigned short *>::`vftable';
      RAII::CleanupInfo<unsigned short *>::Release(&v18);
      v5 = -2147024882;
    }
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v5,
      "PushButtonReset::XmlDocument::LoadFile",
      "base\\reset\\util\\src\\xml.cpp",
      73,
      L"Failed to initialize XmlDocument");
  }
  v19 = &RAII::CAutoPbrDelete<PushButtonReset::XmlDocument *>::`vftable';
  RAII::CAutoPbrDelete<PushButtonReset::XmlDocument *>::Release(&v19);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18005a14c  push    rbp
0x18005a14e  push    rbx
0x18005a14f  push    rsi
0x18005a150  push    rdi
0x18005a151  push    r12
0x18005a153  push    r13
0x18005a155  push    r14
0x18005a157  push    r15
0x18005a159  lea     rbp, [rsp-1Fh]
0x18005a15e  sub     rsp, 88h
0x18005a165  mov     rdi, rdx
0x18005a168  mov     rsi, rcx
0x18005a16b  xor     r14d, r14d
0x18005a16e  mov     [rbp+57h+var_68], r14
0x18005a172  lea     r12, ??_7?$CAutoPbrDelete@PEAVXmlDocument@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::XmlDocument *>::`vftable'
0x18005a179  mov     [rbp+57h+var_70], r12
0x18005a17d  lea     rcx, [rbp+57h+var_70]
0x18005a181  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18005a186  mov     rcx, rax; struct PushButtonReset::XmlDocument **
0x18005a189  call    ?Create@XmlDocument@PushButtonReset@@SAJPEAPEAV12@@Z; PushButtonReset::XmlDocument::Create(PushButtonReset::XmlDocument * *)
0x18005a18e  mov     ebx, eax
0x18005a190  test    eax, eax
0x18005a192  jns     short loc_18005A1C6
0x18005a194  lea     rax, aFailedToInitia_11; "Failed to initialize XmlDocument"
0x18005a19b  mov     [rsp+0C0h+var_98], rax
0x18005a1a0  mov     [rsp+0C0h+var_A0], 49h ; 'I'
0x18005a1a8  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005a1af  lea     r8, aPushbuttonrese; "PushButtonReset::XmlDocument::LoadFile"
0x18005a1b6  mov     edx, ebx
0x18005a1b8  lea     ecx, [r14+2]
0x18005a1bc  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005a1c1  jmp     loc_18005A43E
0x18005a1c6  mov     rcx, [rsi]; psz
0x18005a1c9  call    cs:__imp_SysAllocString
0x18005a1cf  lea     r15, ??_7?$CAutoCleanup@PEAG@RAII@@6B@; const RAII::CAutoCleanup<ushort *>::`vftable'
0x18005a1d6  mov     [rbp+57h+var_80], r15
0x18005a1da  mov     [rbp+57h+var_78], rax
0x18005a1de  lea     rcx, [rbp+57h+var_80]
0x18005a1e2  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18005a1e7  cmp     [rax], r14
0x18005a1ea  jnz     short loc_18005A236
0x18005a1ec  lea     rax, aFailedToAlloca_19; "Failed to allocate path"
0x18005a1f3  mov     [rsp+0C0h+var_98], rax
0x18005a1f8  mov     [rsp+0C0h+var_A0], 4Ch ; 'L'
0x18005a200  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005a207  lea     r8, aPushbuttonrese; "PushButtonReset::XmlDocument::LoadFile"
0x18005a20e  mov     edx, 8007000Eh
0x18005a213  mov     ecx, 2
0x18005a218  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005a21d  nop
0x18005a21e  mov     [rbp+57h+var_80], r15
0x18005a222  lea     rcx, [rbp+57h+var_78]
0x18005a226  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005a22b  nop
0x18005a22c  mov     ebx, 8007000Eh
0x18005a231  jmp     loc_18005A43E
0x18005a236  xorps   xmm0, xmm0
0x18005a239  xor     ebx, ebx
0x18005a23b  movups  [rbp+57h+var_60], xmm0
0x18005a23f  lea     eax, [rbx+8]
0x18005a242  mov     word ptr [rbp+57h+var_60], ax
0x18005a246  mov     rax, [rbp+57h+var_80]
0x18005a24a  lea     rcx, [rbp+57h+var_80]
0x18005a24e  mov     rax, [rax+20h]
0x18005a252  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a257  mov     rcx, [rax]
0x18005a25a  mov     qword ptr [rbp+57h+var_60+8], rcx
0x18005a25e  mov     [rbp+57h+arg_10], r14w
0x18005a263  mov     rax, [rbp+57h+var_70]
0x18005a267  lea     rcx, [rbp+57h+var_70]
0x18005a26b  mov     rax, [rax+18h]
0x18005a26f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a274  mov     rdx, rax
0x18005a277  mov     rcx, [rax]
0x18005a27a  mov     rax, [rcx+18h]
0x18005a27e  mov     rcx, rdx
0x18005a281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a286  mov     r9, rax
0x18005a289  movups  xmm0, [rbp+57h+var_60]
0x18005a28d  movaps  [rbp+57h+var_60], xmm0
0x18005a291  mov     [rbp+57h+var_50], rbx
0x18005a295  mov     rcx, [rax]
0x18005a298  mov     rax, [rcx+1D0h]
0x18005a29f  lea     r8, [rbp+57h+arg_10]
0x18005a2a3  lea     rdx, [rbp+57h+var_60]
0x18005a2a7  mov     rcx, r9
0x18005a2aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a2af  mov     ebx, eax
0x18005a2b1  test    eax, eax
0x18005a2b3  jns     short loc_18005A2FF
0x18005a2b5  mov     rcx, [rsi]
0x18005a2b8  mov     [rsp+0C0h+var_90], rcx
0x18005a2bd  lea     rax, aFailedToLoadDo; "Failed to load document at %s"
0x18005a2c4  mov     [rsp+0C0h+var_98], rax
0x18005a2c9  mov     [rsp+0C0h+var_A0], 54h ; 'T'
0x18005a2d1  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005a2d8  lea     r8, aPushbuttonrese; "PushButtonReset::XmlDocument::LoadFile"
0x18005a2df  mov     edx, ebx
0x18005a2e1  mov     ecx, 2
0x18005a2e6  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005a2eb  nop
0x18005a2ec  mov     [rbp+57h+var_80], r15
0x18005a2f0  lea     rcx, [rbp+57h+var_78]
0x18005a2f4  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005a2f9  nop
0x18005a2fa  jmp     loc_18005A43E
0x18005a2ff  cmp     [rbp+57h+arg_10], r14w
0x18005a304  jnz     loc_18005A425
0x18005a30a  mov     qword ptr [rbp+57h+var_60+8], r14
0x18005a30e  lea     r13, ??_7?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@6B@; const RAII::CAutoRelease<IXMLDOMParseError *>::`vftable'
0x18005a315  mov     qword ptr [rbp+57h+var_60], r13
0x18005a319  mov     rax, [rbp+57h+var_70]
0x18005a31d  lea     rcx, [rbp+57h+var_70]
0x18005a321  mov     rax, [rax+18h]
0x18005a325  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a32a  mov     rdx, rax
0x18005a32d  mov     rcx, [rax]
0x18005a330  mov     rax, [rcx+18h]
0x18005a334  mov     rcx, rdx
0x18005a337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a33c  mov     rdi, rax
0x18005a33f  mov     rcx, [rax]
0x18005a342  mov     rbx, [rcx+1E0h]
0x18005a349  mov     rcx, qword ptr [rbp+57h+var_60]
0x18005a34d  mov     rax, [rcx+8]
0x18005a351  lea     rcx, [rbp+57h+var_60]
0x18005a355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a35a  mov     rdx, rax
0x18005a35d  mov     rcx, rdi
0x18005a360  mov     rax, rbx
0x18005a363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a368  test    eax, eax
0x18005a36a  js      short loc_18005A3C8
0x18005a36c  mov     rax, [rbp+57h+var_70]
0x18005a370  lea     rcx, [rbp+57h+var_70]
0x18005a374  mov     rax, [rax+18h]
0x18005a378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a37d  mov     rax, qword ptr [rbp+57h+var_60]
0x18005a381  lea     rcx, [rbp+57h+var_60]
0x18005a385  mov     rax, [rax+20h]
0x18005a389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a38e  mov     rcx, rax; struct IXMLDOMParseError *
0x18005a391  call    ?ReportErrors@XmlDocument@PushButtonReset@@CAJPEAUIXMLDOMParseError@@@Z; PushButtonReset::XmlDocument::ReportErrors(IXMLDOMParseError *)
0x18005a396  test    eax, eax
0x18005a398  jns     short loc_18005A3C8
0x18005a39a  lea     rcx, aFailedToReport; "Failed to report parse error(s)"
0x18005a3a1  mov     [rsp+0C0h+var_98], rcx
0x18005a3a6  mov     [rsp+0C0h+var_A0], 5Fh ; '_'
0x18005a3ae  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005a3b5  lea     r8, aPushbuttonrese; "PushButtonReset::XmlDocument::LoadFile"
0x18005a3bc  mov     edx, eax
0x18005a3be  mov     ecx, 2
0x18005a3c3  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005a3c8  mov     rax, [rsi]
0x18005a3cb  mov     [rsp+0C0h+var_90], rax
0x18005a3d0  lea     rax, aTheContentsOfS; "The contents of %s cannot be parsed"
0x18005a3d7  mov     [rsp+0C0h+var_98], rax
0x18005a3dc  mov     [rsp+0C0h+var_A0], 64h ; 'd'
0x18005a3e4  lea     r9, aBaseResetUtilS_0; "base\\reset\\util\\src\\xml.cpp"
0x18005a3eb  lea     r8, aPushbuttonrese; "PushButtonReset::XmlDocument::LoadFile"
0x18005a3f2  mov     edx, 8007000Dh
0x18005a3f7  mov     ecx, 2
0x18005a3fc  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005a401  nop
0x18005a402  mov     qword ptr [rbp+57h+var_60], r13
0x18005a406  lea     rcx, [rbp+57h+var_60]
0x18005a40a  call    ?Release@?$CAutoRelease@PEAUIXMLDOMParseError@@@RAII@@UEAAXXZ; RAII::CAutoRelease<IXMLDOMParseError *>::Release(void)
0x18005a40f  nop
0x18005a410  mov     [rbp+57h+var_80], r15
0x18005a414  lea     rcx, [rbp+57h+var_78]
0x18005a418  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005a41d  nop
0x18005a41e  mov     ebx, 8007000Dh
0x18005a423  jmp     short loc_18005A43E
0x18005a425  mov     rax, [rbp+57h+var_68]
0x18005a429  mov     [rbp+57h+var_68], r14
0x18005a42d  mov     [rdi], rax
0x18005a430  mov     [rbp+57h+var_80], r15
0x18005a434  lea     rcx, [rbp+57h+var_78]
0x18005a438  call    ?Release@?$CleanupInfo@PEAG@RAII@@SAXAEAPEAG@Z; RAII::CleanupInfo<ushort *>::Release(ushort * &)
0x18005a43d  nop
0x18005a43e  mov     [rbp+57h+var_70], r12
0x18005a442  lea     rcx, [rbp+57h+var_70]
0x18005a446  call    ?Release@?$CAutoPbrDelete@PEAVXmlDocument@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::XmlDocument *>::Release(void)
0x18005a44b  mov     eax, ebx
0x18005a44d  add     rsp, 88h
0x18005a454  pop     r15
0x18005a456  pop     r14
0x18005a458  pop     r13
0x18005a45a  pop     r12
0x18005a45c  pop     rdi
0x18005a45d  pop     rsi
0x18005a45e  pop     rbx
0x18005a45f  pop     rbp
0x18005a460  retn
```
