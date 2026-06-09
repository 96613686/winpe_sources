# WinRECreateRecoveryPartition(unsigned __int64,unsigned __int64,PushButtonReset::Partition * *)

- ea: `0x180027fdc`
- end: `0x18002821a`
- name: `?WinRECreateRecoveryPartition@@YAJ_K0PEAPEAVPartition@PushButtonReset@@@Z`
- size: `574`
- prototype: `__int64 __fastcall(unsigned __int64, unsigned __int64, struct PushButtonReset::Partition **)`
- caller_count: `3`
- callee_count: `13`
- tags: `service_task`

## callers

- `0x180025180`
- `0x180026320`
- `0x180028220`

## callees

- `0x1800049a4`
- `0x180005cc0`
- `0x18000d6f0`
- `0x18000d92c`
- `0x180026260`
- `0x180027fdc`
- `0x180032ee0`
- `0x18003717c`
- `0x180037344`
- `0x18003b348`
- `0x1800444b4`
- `0x18006c690`
- `0x18006f010`

## string_xrefs

- `0x180028027`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x18002809b`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x180028126`: `base\diagnosis\srt\winreagent\lib\operations\src\repartition.cpp`
- `0x18002800a`: `WinRECreateRecoveryPartition`
- `0x1800280a2`: `WinRECreateRecoveryPartition`
- `0x18002811f`: `WinRECreateRecoveryPartition`
- `0x180028193`: `WinRECreateRecoveryPartition`
- `0x18002804f`: `%hs: Create recovery partition at offset [%llu], size [%llu]`
- `0x18002810b`: `Failed to create recoery partition`
- `0x1800281c6`: `%hs: WinRE partition created`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WinRECreateRecoveryPartition(__int64 a1, __int64 a2, struct PushButtonReset::Partition **a3)
{
  WinREAgent *v7; // rax
  struct PushButtonReset::Disk **v8; // rdx
  signed int Partition; // ebx
  __int64 v10; // rbx
  __int64 v11; // rdx
  PushButtonReset::Partition *v12; // rbx
  struct PushButtonReset::Partition *v13; // rax
  __int64 v14; // [rsp+30h] [rbp-30h] BYREF
  void **v15; // [rsp+38h] [rbp-28h] BYREF
  struct PushButtonReset::Partition *v16; // [rsp+40h] [rbp-20h]
  _QWORD v17[2]; // [rsp+48h] [rbp-18h] BYREF

  if ( a3 )
  {
    PushButtonReset::Logging::Trace(
      0,
      L"%hs: Create recovery partition at offset [%llu], size [%llu]",
      "WinRECreateRecoveryPartition",
      a1,
      a2);
    v17[1] = 0;
    v17[0] = &RAII::CAutoPbrDelete<PushButtonReset::Disk *>::`vftable';
    v7 = (WinREAgent *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)v17);
    Partition = WinREAgent::WinREGetOSDisk(v7, v8);
    if ( Partition >= 0 )
    {
      v16 = 0;
      v15 = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
      v10 = (*(__int64 (__fastcall **)(_QWORD *))(v17[0] + 24LL))(v17);
      RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v15);
      Partition = PushButtonReset::Disk::CreatePartition(v10, v11, a1, a2);
      if ( Partition >= 0 )
      {
        v12 = (PushButtonReset::Partition *)((__int64 (__fastcall *)(void ***))v15[3])(&v15);
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          (__int64)&v14,
          (__int64)&pszFormat);
        Partition = PushButtonReset::Partition::Format(v12);
        ATL::CStringData::Release((ATL::CStringData *)(v14 - 24));
        if ( Partition >= 0 )
        {
          v13 = v16;
          v16 = 0;
          *a3 = v13;
          PushButtonReset::Logging::Trace(0, L"%hs: WinRE partition created", "WinRECreateRecoveryPartition");
        }
        else
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)Partition,
            "WinRECreateRecoveryPartition",
            "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
            445,
            L"Failed to format the recovery partition");
        }
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)Partition,
          "WinRECreateRecoveryPartition",
          "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
          442,
          L"Failed to create recoery partition");
      }
      v15 = &RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable';
      RAII::CAutoPbrHeapFree<unsigned short *>::Release(&v15);
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Partition,
        "WinRECreateRecoveryPartition",
        "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
        433,
        L"Failed to get disk of OS");
    }
    v17[0] = &RAII::CAutoPbrDelete<PushButtonReset::Disk *>::`vftable';
    RAII::CAutoPbrDelete<PushButtonReset::Disk *>::Release(v17);
    return (unsigned int)Partition;
  }
  else
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942487LL,
      "WinRECreateRecoveryPartition",
      "base\\diagnosis\\srt\\winreagent\\lib\\operations\\src\\repartition.cpp",
      423,
      L"res cannot be null");
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180027fdc  mov     [rsp-28h+arg_18], rbx
0x180027fe1  push    rbp
0x180027fe2  push    rsi
0x180027fe3  push    r13
0x180027fe5  push    r14
0x180027fe7  push    r15
0x180027fe9  mov     rbp, rsp
0x180027fec  sub     rsp, 60h
0x180027ff0  mov     rax, cs:__security_cookie
0x180027ff7  xor     rax, rsp
0x180027ffa  mov     [rbp+var_8], rax
0x180027ffe  mov     rsi, r8
0x180028001  mov     r15, rdx
0x180028004  mov     r14, rcx
0x180028007  test    r8, r8
0x18002800a  lea     r8, aWinrecreaterec; "WinRECreateRecoveryPartition"
0x180028011  jnz     short loc_180028047
0x180028013  lea     rax, aResCannotBeNul; "res cannot be null"
0x18002801a  mov     [rsp+60h+var_38], rax
0x18002801f  mov     dword ptr [rsp+60h+var_40], 1A7h
0x180028027  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002802e  mov     edx, 80070057h
0x180028033  mov     ecx, 2
0x180028038  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002803d  mov     eax, 80070057h
0x180028042  jmp     loc_1800281F9
0x180028047  mov     [rsp+60h+var_40], r15
0x18002804c  mov     r9, r14
0x18002804f  lea     rdx, aHsCreateRecove; "%hs: Create recovery partition at offse"...
0x180028056  xor     ecx, ecx
0x180028058  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002805d  mov     [rbp+var_10], 0
0x180028065  lea     r13, ??_7?$CAutoPbrDelete@PEAVDisk@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Disk *>::`vftable'
0x18002806c  mov     [rbp+var_18], r13
0x180028070  lea     rcx, [rbp+var_18]
0x180028074  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x180028079  mov     rcx, rax; this
0x18002807c  call    ?WinREGetOSDisk@WinREAgent@@YAJPEAPEAVDisk@PushButtonReset@@@Z; WinREAgent::WinREGetOSDisk(PushButtonReset::Disk * *)
0x180028081  mov     ebx, eax
0x180028083  test    eax, eax
0x180028085  jns     short loc_1800280BA
0x180028087  lea     rax, aFailedToGetDis_2; "Failed to get disk of OS"
0x18002808e  mov     [rsp+60h+var_38], rax
0x180028093  mov     dword ptr [rsp+60h+var_40], 1B1h
0x18002809b  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x1800280a2  lea     r8, aWinrecreaterec; "WinRECreateRecoveryPartition"
0x1800280a9  mov     edx, ebx
0x1800280ab  mov     ecx, 2
0x1800280b0  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800280b5  jmp     loc_1800281EA
0x1800280ba  mov     [rbp+var_20], 0
0x1800280c2  lea     rax, ??_7?$CAutoPbrDelete@PEAVPartition@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable'
0x1800280c9  mov     [rbp+var_28], rax
0x1800280cd  mov     rax, [rbp+var_18]
0x1800280d1  lea     rcx, [rbp+var_18]
0x1800280d5  mov     rax, [rax+18h]
0x1800280d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280de  mov     rbx, rax
0x1800280e1  mov     rcx, [rbp+var_28]
0x1800280e5  mov     rax, [rcx+8]
0x1800280e9  lea     rcx, [rbp+var_28]
0x1800280ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280f2  mov     [rsp+60h+var_38], rax
0x1800280f7  mov     r9, r15
0x1800280fa  mov     r8, r14
0x1800280fd  mov     rcx, rbx
0x180028100  call    ?CreatePartition@Disk@PushButtonReset@@QEAAJW4PartitionType@2@_K1_NPEAPEAVPartition@2@@Z; PushButtonReset::Disk::CreatePartition(PushButtonReset::PartitionType,unsigned __int64,unsigned __int64,bool,PushButtonReset::Partition * *)
0x180028105  mov     ebx, eax
0x180028107  test    eax, eax
0x180028109  jns     short loc_18002813E
0x18002810b  lea     rax, aFailedToCreate_20; "Failed to create recoery partition"
0x180028112  mov     [rsp+60h+var_38], rax
0x180028117  mov     dword ptr [rsp+60h+var_40], 1BAh
0x18002811f  lea     r8, aWinrecreaterec; "WinRECreateRecoveryPartition"
0x180028126  lea     r9, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002812d  mov     edx, ebx
0x18002812f  mov     ecx, 2
0x180028134  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180028139  jmp     loc_1800281D5
0x18002813e  mov     rax, [rbp+var_28]
0x180028142  lea     rcx, [rbp+var_28]
0x180028146  mov     rax, [rax+18h]
0x18002814a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002814f  mov     rbx, rax
0x180028152  lea     rdx, pszFormat
0x180028159  lea     rcx, [rbp+var_30]
0x18002815d  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180028162  nop
0x180028163  mov     byte ptr [rsp+60h+var_38], 0
0x180028168  mov     dword ptr [rsp+60h+var_40], 0
0x180028170  mov     r9b, 1
0x180028173  lea     r8, [rbp+var_30]
0x180028177  mov     edx, 1
0x18002817c  mov     rcx, rbx; this
0x18002817f  call    ?Format@Partition@PushButtonReset@@QEAAJW4FilesystemType@2@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_NK2@Z; PushButtonReset::Partition::Format(PushButtonReset::FilesystemType,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,bool,ulong,bool)
0x180028184  mov     ebx, eax
0x180028186  mov     rcx, [rbp+var_30]
0x18002818a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002818e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180028193  lea     r8, aWinrecreaterec; "WinRECreateRecoveryPartition"
0x18002819a  test    ebx, ebx
0x18002819c  jns     short loc_1800281B7
0x18002819e  lea     rax, aFailedToFormat; "Failed to format the recovery partition"
0x1800281a5  mov     [rsp+60h+var_38], rax
0x1800281aa  mov     dword ptr [rsp+60h+var_40], 1BDh
0x1800281b2  jmp     loc_180028126
0x1800281b7  mov     rax, [rbp+var_20]
0x1800281bb  mov     [rbp+var_20], 0
0x1800281c3  mov     [rsi], rax
0x1800281c6  lea     rdx, aHsWinrePartiti; "%hs: WinRE partition created"
0x1800281cd  xor     ecx, ecx
0x1800281cf  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800281d4  nop
0x1800281d5  lea     rax, ??_7?$CAutoPbrDelete@PEAVPartition@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::Partition *>::`vftable'
0x1800281dc  mov     [rbp+var_28], rax
0x1800281e0  lea     rcx, [rbp+var_28]
0x1800281e4  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x1800281e9  nop
0x1800281ea  mov     [rbp+var_18], r13
0x1800281ee  lea     rcx, [rbp+var_18]
0x1800281f2  call    ?Release@?$CAutoPbrDelete@PEAVDisk@PushButtonReset@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<PushButtonReset::Disk *>::Release(void)
0x1800281f7  mov     eax, ebx
0x1800281f9  mov     rcx, [rbp+var_8]
0x1800281fd  xor     rcx, rsp; StackCookie
0x180028200  call    __security_check_cookie
0x180028205  mov     rbx, [rsp+60h+arg_18]
0x18002820d  add     rsp, 60h
0x180028211  pop     r15
0x180028213  pop     r14
0x180028215  pop     r13
0x180028217  pop     rsi
0x180028218  pop     rbp
0x180028219  retn
```
