# PatchImage

- ea: `0x1800229fc`
- end: `0x180022d86`
- name: `PatchImage`
- size: `906`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180021590`

## callees

- `0x1800036c8`
- `0x180005c00`
- `0x180005c70`
- `0x180005cc0`
- `0x180006828`
- `0x18000d540`
- `0x1800229fc`
- `0x180023500`
- `0x180028b60`
- `0x180037344`
- `0x180050588`
- `0x18006c690`
- `0x18006f010`

## import_xrefs

- `DismApi!_DismAddPackageEx` at `0x180022c85`
- `DismApi!_DismAddPackageEx` at `0x180022c85`
- `DismApi!_DismCleanImage` at `0x180022cef`
- `DismApi!_DismCleanImage` at `0x180022cef`

## string_xrefs

- `0x180022a5c`: `Failed to open DISM session`
- `0x180022a70`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180022ae1`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180022b57`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180022d0f`: `base\diagnosis\srt\winreagent\lib\operations\src\preparewinre.cpp`
- `0x180022b43`: `Failed to allocate dismSourcePaths`
- `0x180022cfb`: `DISM failed to cleanup superseded component`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PatchImage(__int64 a1, _QWORD *a2, __int64 a3, WinREAgent::OperationProgress *a4)
{
  __int64 v8; // rax
  int v9; // ebx
  unsigned __int64 v10; // rax
  unsigned __int64 v11; // rax
  __int64 v12; // r8
  unsigned __int64 v13; // rcx
  __int64 v14; // rdi
  __int64 v15; // rbx
  unsigned int i; // r14d
  __int64 v17; // rdi
  __int64 v18; // r14
  int v19; // r15d
  __int64 v20; // rdi
  unsigned int v21; // esi
  __int64 v22; // rbx
  __int64 v23; // rax
  __int64 v24; // rbx
  __int64 v25; // rax
  __int64 v27[2]; // [rsp+60h] [rbp-29h] BYREF
  __int64 v28[2]; // [rsp+70h] [rbp-19h] BYREF
  _QWORD v29[2]; // [rsp+80h] [rbp-9h] BYREF

  v29[1] = 0;
  v29[0] = &RAII::CAutoPbrDelete<PushButtonReset::DISMSession *>::`vftable';
  v8 = RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v29);
  v9 = PushButtonReset::DISMSession::Open(a1, v8);
  if ( v9 < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v9,
      "PatchImage",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
      304,
      L"Failed to open DISM session");
    goto LABEL_26;
  }
  v10 = 8LL * a2[1];
  if ( !is_mul_ok(a2[1], 8u) )
    v10 = -1;
  v27[1] = (__int64)operator new[](v10, (const struct std::nothrow_t *)&std::nothrow);
  v27[0] = (__int64)&RAII::CAutoDeleteArray<unsigned short const *>::`vftable';
  if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(v27) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942414LL,
      "PatchImage",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
      307,
      L"Failed to allocate dismPackages");
LABEL_7:
    v27[0] = (__int64)&RAII::CAutoDeleteArray<unsigned short const *>::`vftable';
    RAII::CAutoDeleteArray<unsigned short const *>::Release(v27);
    v9 = -2147024882;
    goto LABEL_26;
  }
  v11 = 8LL * *(_QWORD *)(a3 + 8);
  if ( !is_mul_ok(*(_QWORD *)(a3 + 8), 8u) )
    v11 = -1;
  v28[1] = (__int64)operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
  v28[0] = (__int64)&RAII::CAutoDeleteArray<unsigned short const *>::`vftable';
  if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(v28) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942414LL,
      "PatchImage",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
      310,
      L"Failed to allocate dismSourcePaths");
    v28[0] = (__int64)&RAII::CAutoDeleteArray<unsigned short const *>::`vftable';
    RAII::CAutoDeleteArray<unsigned short const *>::Release(v28);
    goto LABEL_7;
  }
  v13 = a2[1];
  if ( v13 )
  {
    v14 = 0;
    do
    {
      if ( (unsigned int)v14 >= v13 )
        ATL::AtlThrowImpl(-2147024809);
      _mm_lfence();
      v15 = **(_QWORD **)(*a2 + 8 * v14);
      *(_QWORD *)(*(__int64 (__fastcall **)(__int64 *))(v27[0] + 120))(v27) = v15;
      v14 = (unsigned int)(v14 + 1);
      v13 = a2[1];
    }
    while ( (unsigned int)v14 < v13 );
  }
  for ( i = 0; (unsigned __int64)i < *(_QWORD *)(a3 + 8); ++i )
  {
    v17 = *(_QWORD *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                       a3,
                       i,
                       v12);
    *(_QWORD *)(*(__int64 (__fastcall **)(__int64 *, _QWORD))(v28[0] + 120))(v28, i) = v17;
  }
  v18 = *((_QWORD *)a4 + 9);
  v19 = *(_DWORD *)(a3 + 8);
  v20 = (*(__int64 (__fastcall **)(__int64 *))(v28[0] + 32))(v28);
  v21 = *((_DWORD *)a2 + 2);
  v22 = (*(__int64 (__fastcall **)(__int64 *))(v27[0] + 32))(v27);
  v23 = (*(__int64 (__fastcall **)(_QWORD *))(v29[0] + 24LL))(v29);
  v9 = _DismAddPackageEx(*(unsigned int *)(v23 + 4), v22, v21, 0, 0, 0, v20, v19, v18, PrepareWinREProgressCallback, a4);
  if ( v9 >= 0 )
  {
    WinREAgent::OperationProgress::CompletedOperation(a4);
    v24 = *((_QWORD *)a4 + 9);
    v25 = (*(__int64 (__fastcall **)(_QWORD *))(v29[0] + 24LL))(v29);
    v9 = _DismCleanImage(*(unsigned int *)(v25 + 4), 4, 1, v24, PrepareWinREProgressCallback, a4);
    if ( v9 >= 0 )
      WinREAgent::OperationProgress::CompletedOperation(a4);
    else
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v9,
        "PatchImage",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
        347,
        L"DISM failed to cleanup superseded component");
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v9,
      "PatchImage",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\preparewinre.cpp",
      335,
      L"DISM failed to add packages");
  }
  v28[0] = (__int64)&RAII::CAutoDeleteArray<unsigned short const *>::`vftable';
  RAII::CAutoDeleteArray<unsigned short const *>::Release(v28);
  v27[0] = (__int64)&RAII::CAutoDeleteArray<unsigned short const *>::`vftable';
  RAII::CAutoDeleteArray<unsigned short const *>::Release(v27);
LABEL_26:
  v29[0] = &RAII::CAutoPbrDelete<PushButtonReset::DISMSession *>::`vftable';
  RAII::CAutoPbrDelete<PushButtonReset::DISMSession *>::Release(v29);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800229fc  push    rbp
0x1800229fe  push    rbx
0x1800229ff  push    rsi
0x180022a00  push    rdi
0x180022a01  push    r12
0x180022a03  push    r13
0x180022a05  push    r14
0x180022a07  push    r15
0x180022a09  lea     rbp, [rsp-1Fh]
0x180022a0e  sub     rsp, 0A8h
0x180022a15  mov     rax, cs:__security_cookie
0x180022a1c  xor     rax, rsp
0x180022a1f  mov     [rbp+57h+var_50], rax
0x180022a23  mov     r13, r9
0x180022a26  mov     r15, r8
0x180022a29  mov     rsi, rdx
0x180022a2c  mov     rbx, rcx
0x180022a2f  mov     [rbp+57h+var_58], 0
0x180022a37  lea     rax, ??_7?$CAutoPbrDelete@PEAVDISMSession@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::DISMSession *>::`vftable'
0x180022a3e  mov     [rbp+57h+var_60], rax
0x180022a42  lea     rcx, [rbp+57h+var_60]
0x180022a46  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180022a4b  mov     rdx, rax
0x180022a4e  mov     rcx, rbx
0x180022a51  call    ?Open@DISMSession@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; PushButtonReset::DISMSession::Open(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::DISMSession * *)
0x180022a56  mov     ebx, eax
0x180022a58  test    eax, eax
0x180022a5a  jns     short loc_180022A8F
0x180022a5c  lea     rax, aFailedToOpenDi_1; "Failed to open DISM session"
0x180022a63  mov     [rsp+0E0h+var_B8], rax
0x180022a68  mov     dword ptr [rsp+0E0h+var_C0], 130h
0x180022a70  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180022a77  lea     r8, aPatchimage; "PatchImage"
0x180022a7e  mov     edx, ebx
0x180022a80  mov     ecx, 2
0x180022a85  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180022a8a  jmp     loc_180022D50
0x180022a8f  mov     ebx, 8
0x180022a94  mov     eax, ebx
0x180022a96  mul     qword ptr [rsi+8]
0x180022a9a  lea     rdi, [rbx-9]
0x180022a9e  cmovb   rax, rdi
0x180022aa2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180022aa9  mov     rcx, rax; unsigned __int64
0x180022aac  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180022ab1  mov     [rbp+57h+var_78], rax
0x180022ab5  lea     r12, ??_7?$CAutoDeleteArray@PEBG@RAII@@6B@; const RAII::CAutoDeleteArray<ushort const *>::`vftable'
0x180022abc  mov     [rbp+57h+var_80], r12
0x180022ac0  lea     rcx, [rbp+57h+var_80]
0x180022ac4  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x180022ac9  test    al, al
0x180022acb  jz      short loc_180022B14
0x180022acd  lea     rax, aFailedToAlloca_10; "Failed to allocate dismPackages"
0x180022ad4  mov     [rsp+0E0h+var_B8], rax
0x180022ad9  mov     dword ptr [rsp+0E0h+var_C0], 133h
0x180022ae1  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180022ae8  lea     r8, aPatchimage; "PatchImage"
0x180022aef  mov     edx, 8007000Eh
0x180022af4  lea     ecx, [rbx-6]
0x180022af7  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180022afc  nop
0x180022afd  mov     [rbp+57h+var_80], r12
0x180022b01  lea     rcx, [rbp+57h+var_80]
0x180022b05  call    ?Release@?$CAutoDeleteArray@PEBG@RAII@@UEAAXXZ; RAII::CAutoDeleteArray<ushort const *>::Release(void)
0x180022b0a  mov     ebx, 8007000Eh
0x180022b0f  jmp     loc_180022D50
0x180022b14  mov     rax, rbx
0x180022b17  mul     qword ptr [r15+8]
0x180022b1b  cmovb   rax, rdi
0x180022b1f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180022b26  mov     rcx, rax; unsigned __int64
0x180022b29  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180022b2e  mov     [rbp+57h+var_68], rax
0x180022b32  mov     [rbp+57h+var_70], r12
0x180022b36  lea     rcx, [rbp+57h+var_70]
0x180022b3a  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x180022b3f  test    al, al
0x180022b41  jz      short loc_180022B87
0x180022b43  lea     rax, aFailedToAlloca_32; "Failed to allocate dismSourcePaths"
0x180022b4a  mov     [rsp+0E0h+var_B8], rax
0x180022b4f  mov     dword ptr [rsp+0E0h+var_C0], 136h
0x180022b57  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180022b5e  lea     r8, aPatchimage; "PatchImage"
0x180022b65  mov     edx, 8007000Eh
0x180022b6a  mov     ecx, 2
0x180022b6f  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180022b74  nop
0x180022b75  mov     [rbp+57h+var_70], r12
0x180022b79  lea     rcx, [rbp+57h+var_70]
0x180022b7d  call    ?Release@?$CAutoDeleteArray@PEBG@RAII@@UEAAXXZ; RAII::CAutoDeleteArray<ushort const *>::Release(void)
0x180022b82  jmp     loc_180022AFD
0x180022b87  mov     rcx, [rsi+8]
0x180022b8b  test    rcx, rcx
0x180022b8e  jz      short loc_180022BCB
0x180022b90  xor     edi, edi
0x180022b92  mov     edx, edi
0x180022b94  cmp     rdx, rcx
0x180022b97  jnb     loc_180022CA7
0x180022b9d  lfence
0x180022ba0  mov     rax, [rsi]
0x180022ba3  mov     rcx, [rax+rdi*8]
0x180022ba7  mov     rbx, [rcx]
0x180022baa  mov     rax, [rbp+57h+var_80]
0x180022bae  lea     rcx, [rbp+57h+var_80]
0x180022bb2  mov     rax, [rax+78h]
0x180022bb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022bbb  mov     [rax], rbx
0x180022bbe  inc     edi
0x180022bc0  mov     rcx, [rsi+8]
0x180022bc4  mov     eax, edi
0x180022bc6  cmp     rax, rcx
0x180022bc9  jb      short loc_180022B92
0x180022bcb  xor     r14d, r14d
0x180022bce  cmp     [r15+8], r14
0x180022bd2  jbe     short loc_180022C05
0x180022bd4  mov     edx, r14d
0x180022bd7  mov     rcx, r15
0x180022bda  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x180022bdf  mov     rdi, [rax]
0x180022be2  mov     rax, [rbp+57h+var_70]
0x180022be6  mov     edx, r14d
0x180022be9  lea     rcx, [rbp+57h+var_70]
0x180022bed  mov     rax, [rax+78h]
0x180022bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022bf6  mov     [rax], rdi
0x180022bf9  inc     r14d
0x180022bfc  mov     eax, r14d
0x180022bff  cmp     rax, [r15+8]
0x180022c03  jb      short loc_180022BD4
0x180022c05  mov     r14, [r13+48h]
0x180022c09  mov     r15d, [r15+8]
0x180022c0d  mov     rax, [rbp+57h+var_70]
0x180022c11  lea     rcx, [rbp+57h+var_70]
0x180022c15  mov     rax, [rax+20h]
0x180022c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c1e  mov     rdi, rax
0x180022c21  mov     esi, [rsi+8]
0x180022c24  mov     rcx, [rbp+57h+var_80]
0x180022c28  mov     rax, [rcx+20h]
0x180022c2c  lea     rcx, [rbp+57h+var_80]
0x180022c30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c35  mov     rbx, rax
0x180022c38  mov     rcx, [rbp+57h+var_60]
0x180022c3c  mov     rax, [rcx+18h]
0x180022c40  lea     rcx, [rbp+57h+var_60]
0x180022c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c49  mov     [rsp+0E0h+var_90], r13
0x180022c4e  lea     rcx, PrepareWinREProgressCallback
0x180022c55  mov     [rsp+0E0h+var_98], rcx
0x180022c5a  mov     [rsp+0E0h+var_A0], r14
0x180022c5f  mov     [rsp+0E0h+var_A8], r15d
0x180022c64  mov     [rsp+0E0h+var_B0], rdi
0x180022c69  mov     dword ptr [rsp+0E0h+var_B8], 0
0x180022c71  mov     dword ptr [rsp+0E0h+var_C0], 0
0x180022c79  xor     r9d, r9d
0x180022c7c  mov     r8d, esi
0x180022c7f  mov     rdx, rbx
0x180022c82  mov     ecx, [rax+4]
0x180022c85  call    cs:__imp__DismAddPackageEx
0x180022c8b  mov     ebx, eax
0x180022c8d  test    eax, eax
0x180022c8f  jns     short loc_180022CB2
0x180022c91  lea     rax, aDismFailedToAd; "DISM failed to add packages"
0x180022c98  mov     [rsp+0E0h+var_B8], rax
0x180022c9d  mov     dword ptr [rsp+0E0h+var_C0], 14Fh
0x180022ca5  jmp     short loc_180022D0F
0x180022ca7  mov     ecx, 80070057h; int
0x180022cac  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180022cb2  mov     rcx, r13; this
0x180022cb5  call    ?CompletedOperation@OperationProgress@WinREAgent@@QEAAXXZ; WinREAgent::OperationProgress::CompletedOperation(void)
0x180022cba  mov     rbx, [r13+48h]
0x180022cbe  mov     rax, [rbp+57h+var_60]
0x180022cc2  lea     rcx, [rbp+57h+var_60]
0x180022cc6  mov     rax, [rax+18h]
0x180022cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ccf  mov     [rsp+0E0h+var_B8], r13
0x180022cd4  lea     rcx, PrepareWinREProgressCallback
0x180022cdb  mov     [rsp+0E0h+var_C0], rcx
0x180022ce0  mov     r9, rbx
0x180022ce3  mov     edx, 4
0x180022ce8  lea     r8d, [rdx-3]
0x180022cec  mov     ecx, [rax+4]
0x180022cef  call    cs:__imp__DismCleanImage
0x180022cf5  mov     ebx, eax
0x180022cf7  test    eax, eax
0x180022cf9  jns     short loc_180022D2B
0x180022cfb  lea     rax, aDismFailedToCl; "DISM failed to cleanup superseded compo"...
0x180022d02  mov     [rsp+0E0h+var_B8], rax
0x180022d07  mov     dword ptr [rsp+0E0h+var_C0], 15Bh
0x180022d0f  lea     r9, aBaseDiagnosisS_22; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x180022d16  lea     r8, aPatchimage; "PatchImage"
0x180022d1d  mov     edx, ebx
0x180022d1f  mov     ecx, 2
0x180022d24  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180022d29  jmp     short loc_180022D34
0x180022d2b  mov     rcx, r13; this
0x180022d2e  call    ?CompletedOperation@OperationProgress@WinREAgent@@QEAAXXZ; WinREAgent::OperationProgress::CompletedOperation(void)
0x180022d33  nop
0x180022d34  mov     [rbp+57h+var_70], r12
0x180022d38  lea     rcx, [rbp+57h+var_70]
0x180022d3c  call    ?Release@?$CAutoDeleteArray@PEBG@RAII@@UEAAXXZ; RAII::CAutoDeleteArray<ushort const *>::Release(void)
0x180022d41  nop
0x180022d42  mov     [rbp+57h+var_80], r12
0x180022d46  lea     rcx, [rbp+57h+var_80]
0x180022d4a  call    ?Release@?$CAutoDeleteArray@PEBG@RAII@@UEAAXXZ; RAII::CAutoDeleteArray<ushort const *>::Release(void)
0x180022d4f  nop
0x180022d50  lea     rax, ??_7?$CAutoPbrDelete@PEAVDISMSession@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::DISMSession *>::`vftable'
0x180022d57  mov     [rbp+57h+var_60], rax
0x180022d5b  lea     rcx, [rbp+57h+var_60]
0x180022d5f  call    ?Release@?$CAutoPbrDelete@PEAVDISMSession@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::DISMSession *>::Release(void)
0x180022d64  mov     eax, ebx
0x180022d66  mov     rcx, [rbp+57h+var_50]
0x180022d6a  xor     rcx, rsp; StackCookie
0x180022d6d  call    __security_check_cookie
0x180022d72  add     rsp, 0A8h
0x180022d79  pop     r15
0x180022d7b  pop     r14
0x180022d7d  pop     r13
0x180022d7f  pop     r12
0x180022d81  pop     rdi
0x180022d82  pop     rsi
0x180022d83  pop     rbx
0x180022d84  pop     rbp
0x180022d85  retn
```
