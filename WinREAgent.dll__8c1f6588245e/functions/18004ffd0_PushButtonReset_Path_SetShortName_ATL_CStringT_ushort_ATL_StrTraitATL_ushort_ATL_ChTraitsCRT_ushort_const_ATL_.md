# PushButtonReset::Path::SetShortName(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x18004ffd0`
- end: `0x1800502f9`
- name: `?SetShortName@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z`
- size: `809`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting, service_task, installer_update`

## callers

- `0x18004ed94`

## callees

- `0x180004af8`
- `0x18000d6f0`
- `0x18000d92c`
- `0x180023654`
- `0x180037344`
- `0x18004d404`
- `0x18004ffd0`
- `0x18006f010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800500e6`
- `msvcrt!wcscpy_s` at `0x1800500e6`
- `KERNEL32!GetLastError` at `0x1800501b8`
- `KERNEL32!GetLastError` at `0x1800501ff`
- `KERNEL32!GetLastError` at `0x1800501b8`
- `KERNEL32!GetLastError` at `0x1800501ff`
- `KERNEL32!HeapAlloc` at `0x180050025`
- `KERNEL32!HeapAlloc` at `0x180050025`
- `KERNEL32!GetProcessHeap` at `0x180050017`
- `KERNEL32!GetProcessHeap` at `0x180050017`
- `KERNEL32!CreateFileW` at `0x180050182`
- `KERNEL32!CreateFileW` at `0x180050182`
- `ntdll!NtSetInformationFile` at `0x18005025a`
- `ntdll!NtSetInformationFile` at `0x18005025a`
- `ntdll!RtlNtStatusToDosError` at `0x180050262`
- `ntdll!RtlNtStatusToDosError` at `0x180050262`

## string_xrefs

- `0x1800501d1`: `Failed to open [%s]`
- `0x180050072`: `PushButtonReset::Path::SetShortName`
- `0x18005012b`: `PushButtonReset::Path::SetShortName`
- `0x1800501ec`: `PushButtonReset::Path::SetShortName`
- `0x18005029e`: `PushButtonReset::Path::SetShortName`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PushButtonReset::Path::SetShortName(_QWORD *a1, const wchar_t **a2)
{
  ULONG v4; // esi
  int v5; // edx
  HANDLE ProcessHeap; // rax
  LPVOID v7; // rax
  signed int Canonical; // edi
  __int64 v9; // rbx
  const wchar_t *v10; // rdi
  __int64 v11; // rbx
  __int64 v12; // rax
  ATL::CStringData *v13; // rcx
  LPCWSTR v14; // rbx
  signed int LastError; // eax
  signed int v16; // eax
  void *v17; // rdi
  HANDLE *v18; // rax
  NTSTATUS v19; // eax
  signed int v20; // eax
  void **v22; // [rsp+40h] [rbp-30h] BYREF
  __int64 v23; // [rsp+48h] [rbp-28h] BYREF
  _QWORD v24[2]; // [rsp+50h] [rbp-20h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-10h] BYREF
  LPCWSTR lpFileName; // [rsp+A8h] [rbp+38h] BYREF
  HANDLE FileW; // [rsp+B0h] [rbp+40h] BYREF

  v4 = 8;
  v5 = *((_DWORD *)*a2 - 4);
  if ( v5 > 0 )
    v4 = 2 * v5 + 6;
  v24[1] = 0;
  v24[0] = &RAII::CAutoPbrHeapFree<_FILE_NAME_INFORMATION *>::`vftable';
  ProcessHeap = GetProcessHeap();
  v7 = HeapAlloc(ProcessHeap, 0, v4);
  ((void (__fastcall *)(_QWORD *, LPVOID))RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::operator=)(v24, v7);
  if ( (*(unsigned __int8 (__fastcall **)(_QWORD *))(v24[0] + 72LL))(v24) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942414LL,
      "PushButtonReset::Path::SetShortName",
      "base\\reset\\util\\src\\filesystem.cpp",
      619,
      L"Failed to allocate info");
    Canonical = -2147024882;
  }
  else
  {
    v9 = -1;
    do
      ++v9;
    while ( (*a2)[v9] );
    *(_DWORD *)(*(__int64 (__fastcall **)(_QWORD *))(v24[0] + 24LL))(v24) = 2 * v9;
    v10 = *a2;
    v11 = -1;
    do
      ++v11;
    while ( v10[v11] );
    v12 = (*(__int64 (__fastcall **)(_QWORD *))(v24[0] + 24LL))(v24);
    wcscpy_s((wchar_t *)(v12 + 4), v11 + 1, v10);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpFileName);
    Canonical = PushButtonReset::Path::GetCanonical(a1, &lpFileName);
    if ( Canonical >= 0 )
    {
      v22 = &RAII::CAutoCleanup<void *>::`vftable';
      v23 = 0;
      v14 = lpFileName;
      FileW = CreateFileW(lpFileName, 0x10000000u, 0, 0, 3u, 0x2200000u, 0);
      ((void (__fastcall *)(void ***, HANDLE *))RAII::CAutoCleanup<unsigned short *>::operator=)(&v22, &FileW);
      if ( *(_QWORD *)((__int64 (__fastcall *)(void ***))v22[4])(&v22) == -1 )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)LastError,
          "PushButtonReset::Path::SetShortName",
          "base\\reset\\util\\src\\filesystem.cpp",
          638,
          L"Failed to open [%s]",
          v14);
        v16 = GetLastError();
        Canonical = v16;
        if ( v16 > 0 )
          Canonical = (unsigned __int16)v16 | 0x80070000;
      }
      else
      {
        IoStatusBlock = 0;
        v17 = (void *)(*(__int64 (__fastcall **)(_QWORD *))(v24[0] + 32LL))(v24);
        v18 = (HANDLE *)((__int64 (__fastcall *)(void ***))v22[4])(&v22);
        v19 = NtSetInformationFile(*v18, &IoStatusBlock, v17, v4, FileShortNameInformation);
        v20 = RtlNtStatusToDosError(v19);
        Canonical = v20;
        if ( v20 > 0 )
          Canonical = (unsigned __int16)v20 | 0x80070000;
        if ( Canonical < 0 )
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)Canonical,
            "PushButtonReset::Path::SetShortName",
            "base\\reset\\util\\src\\filesystem.cpp",
            648,
            L"Failed to set short name to [%s]",
            *a2);
      }
      v22 = &RAII::CAutoCleanup<void *>::`vftable';
      RAII::CleanupInfo<void *>::Release(&v23);
      v13 = (ATL::CStringData *)(v14 - 12);
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Canonical,
        "PushButtonReset::Path::SetShortName",
        "base\\reset\\util\\src\\filesystem.cpp",
        627,
        L"Failed to get canonical form for [%s]",
        *a1);
      v13 = (ATL::CStringData *)(lpFileName - 12);
    }
    ATL::CStringData::Release(v13);
  }
  v24[0] = &RAII::CAutoPbrHeapFree<_FILE_NAME_INFORMATION *>::`vftable';
  RAII::CAutoPbrHeapFree<unsigned short *>::Release(v24);
  return (unsigned int)Canonical;
}

```

## disassembly

```asm
0x18004ffd0  mov     [rsp-28h+arg_0], rbx
0x18004ffd5  mov     [rsp-28h+arg_18], rsi
0x18004ffda  push    rbp
0x18004ffdb  push    rdi
0x18004ffdc  push    r12
0x18004ffde  push    r14
0x18004ffe0  push    r15
0x18004ffe2  mov     rbp, rsp
0x18004ffe5  sub     rsp, 70h
0x18004ffe9  mov     r14, rdx
0x18004ffec  mov     r15, rcx
0x18004ffef  mov     esi, 8
0x18004fff4  mov     rax, [rdx]
0x18004fff7  mov     edx, [rax-10h]
0x18004fffa  xor     r12d, r12d
0x18004fffd  test    edx, edx
0x18004ffff  jle     short loc_180050008
0x180050001  lea     esi, ds:6[rdx*2]
0x180050008  mov     [rbp+var_18], r12
0x18005000c  lea     rax, ??_7?$CAutoPbrHeapFree@PEAU_FILE_NAME_INFORMATION@@@RAII@@6B@; const RAII::CAutoPbrHeapFree<_FILE_NAME_INFORMATION *>::`vftable'
0x180050013  mov     [rbp+var_20], rax
0x180050017  call    cs:__imp_GetProcessHeap
0x18005001d  mov     rcx, rax; hHeap
0x180050020  mov     r8d, esi; dwBytes
0x180050023  xor     edx, edx; dwFlags
0x180050025  call    cs:__imp_HeapAlloc
0x18005002b  mov     rcx, [rbp+var_20]
0x18005002f  mov     r8, [rcx+30h]
0x180050033  mov     rdx, rax
0x180050036  lea     rcx, [rbp+var_20]
0x18005003a  mov     rax, r8
0x18005003d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050042  mov     rax, [rbp+var_20]
0x180050046  lea     rcx, [rbp+var_20]
0x18005004a  mov     rax, [rax+48h]
0x18005004e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050053  test    al, al
0x180050055  jz      short loc_180050092
0x180050057  lea     rax, aFailedToAlloca_40; "Failed to allocate info"
0x18005005e  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], rax
0x180050063  mov     [rsp+70h+dwCreationDisposition], 26Bh
0x18005006b  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x180050072  lea     r8, aPushbuttonrese_15; "PushButtonReset::Path::SetShortName"
0x180050079  mov     edx, 8007000Eh
0x18005007e  mov     ecx, 2
0x180050083  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180050088  mov     edi, 8007000Eh
0x18005008d  jmp     loc_1800502CA
0x180050092  mov     rax, [r14]
0x180050095  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180050099  inc     rbx
0x18005009c  cmp     [rax+rbx*2], r12w
0x1800500a1  jnz     short loc_180050099
0x1800500a3  mov     rax, [rbp+var_20]
0x1800500a7  lea     rcx, [rbp+var_20]
0x1800500ab  mov     rax, [rax+18h]
0x1800500af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800500b4  lea     ecx, [rbx+rbx]
0x1800500b7  mov     [rax], ecx
0x1800500b9  mov     rdi, [r14]
0x1800500bc  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800500c0  inc     rbx
0x1800500c3  cmp     [rdi+rbx*2], r12w
0x1800500c8  jnz     short loc_1800500C0
0x1800500ca  mov     rax, [rbp+var_20]
0x1800500ce  lea     rcx, [rbp+var_20]
0x1800500d2  mov     rax, [rax+18h]
0x1800500d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800500db  lea     rcx, [rax+4]; Destination
0x1800500df  mov     r8, rdi; Source
0x1800500e2  lea     rdx, [rbx+1]; SizeInWords
0x1800500e6  call    cs:__imp_wcscpy_s
0x1800500ec  lea     rcx, [rbp+lpFileName]
0x1800500f0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800500f5  nop
0x1800500f6  lea     rdx, [rbp+lpFileName]
0x1800500fa  mov     rcx, r15
0x1800500fd  call    ?GetCanonical@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetCanonical(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x180050102  mov     edi, eax
0x180050104  test    eax, eax
0x180050106  jns     short loc_18005014C
0x180050108  mov     rcx, [r15]
0x18005010b  mov     [rsp+70h+hTemplateFile], rcx
0x180050110  lea     rax, aFailedToGetCan_2; "Failed to get canonical form for [%s]"
0x180050117  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], rax
0x18005011c  mov     [rsp+70h+dwCreationDisposition], 273h
0x180050124  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18005012b  lea     r8, aPushbuttonrese_15; "PushButtonReset::Path::SetShortName"
0x180050132  mov     edx, edi
0x180050134  mov     ecx, 2
0x180050139  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18005013e  nop
0x18005013f  mov     rcx, [rbp+lpFileName]
0x180050143  add     rcx, 0FFFFFFFFFFFFFFE8h
0x180050147  jmp     loc_1800502C4
0x18005014c  lea     r15, ??_7?$CAutoCleanup@PEAX@RAII@@6B@; const RAII::CAutoCleanup<void *>::`vftable'
0x180050153  mov     [rbp+var_30], r15
0x180050157  mov     [rbp+var_28], r12
0x18005015b  mov     [rsp+70h+hTemplateFile], r12; hTemplateFile
0x180050160  mov     [rsp+70h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180050168  mov     [rsp+70h+dwCreationDisposition], 3; dwCreationDisposition
0x180050170  xor     r9d, r9d; lpSecurityAttributes
0x180050173  xor     r8d, r8d; dwShareMode
0x180050176  mov     edx, 10000000h; dwDesiredAccess
0x18005017b  mov     rbx, [rbp+lpFileName]
0x18005017f  mov     rcx, rbx; lpFileName
0x180050182  call    cs:__imp_CreateFileW
0x180050188  mov     [rbp+arg_10], rax
0x18005018c  mov     rax, [rbp+var_30]
0x180050190  lea     rdx, [rbp+arg_10]
0x180050194  lea     rcx, [rbp+var_30]
0x180050198  mov     rax, [rax+30h]
0x18005019c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800501a1  mov     rax, [rbp+var_30]
0x1800501a5  lea     rcx, [rbp+var_30]
0x1800501a9  mov     rax, [rax+20h]
0x1800501ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800501b2  cmp     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x1800501b6  jnz     short loc_180050219
0x1800501b8  call    cs:__imp_GetLastError
0x1800501be  mov     esi, 80070000h
0x1800501c3  test    eax, eax
0x1800501c5  jle     short loc_1800501CC
0x1800501c7  movzx   eax, ax
0x1800501ca  or      eax, esi
0x1800501cc  mov     [rsp+70h+hTemplateFile], rbx
0x1800501d1  lea     rcx, aFailedToOpenS; "Failed to open [%s]"
0x1800501d8  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], rcx
0x1800501dd  mov     [rsp+70h+dwCreationDisposition], 27Eh
0x1800501e5  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x1800501ec  lea     r8, aPushbuttonrese_15; "PushButtonReset::Path::SetShortName"
0x1800501f3  mov     edx, eax
0x1800501f5  mov     ecx, 2
0x1800501fa  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800501ff  call    cs:__imp_GetLastError
0x180050205  mov     edi, eax
0x180050207  test    eax, eax
0x180050209  jle     loc_1800502B2
0x18005020f  movzx   edi, ax
0x180050212  or      edi, esi
0x180050214  jmp     loc_1800502B2
0x180050219  xorps   xmm0, xmm0
0x18005021c  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180050220  mov     rax, [rbp+var_20]
0x180050224  lea     rcx, [rbp+var_20]
0x180050228  mov     rax, [rax+20h]
0x18005022c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050231  mov     rdi, rax
0x180050234  mov     rcx, [rbp+var_30]
0x180050238  mov     rax, [rcx+20h]
0x18005023c  lea     rcx, [rbp+var_30]
0x180050240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050245  mov     [rsp+70h+dwCreationDisposition], 28h ; '('; FileInformationClass
0x18005024d  mov     r9d, esi; Length
0x180050250  mov     r8, rdi; FileInformation
0x180050253  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x180050257  mov     rcx, [rax]; FileHandle
0x18005025a  call    cs:__imp_NtSetInformationFile
0x180050260  mov     ecx, eax; Status
0x180050262  call    cs:__imp_RtlNtStatusToDosError
0x180050268  mov     edi, eax
0x18005026a  test    eax, eax
0x18005026c  jle     short loc_180050277
0x18005026e  movzx   edi, ax
0x180050271  or      edi, 80070000h
0x180050277  test    edi, edi
0x180050279  jns     short loc_1800502B2
0x18005027b  mov     rax, [r14]
0x18005027e  mov     [rsp+70h+hTemplateFile], rax
0x180050283  lea     rax, aFailedToSetSho; "Failed to set short name to [%s]"
0x18005028a  mov     qword ptr [rsp+70h+dwFlagsAndAttributes], rax
0x18005028f  mov     [rsp+70h+dwCreationDisposition], 288h
0x180050297  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18005029e  lea     r8, aPushbuttonrese_15; "PushButtonReset::Path::SetShortName"
0x1800502a5  mov     edx, edi
0x1800502a7  mov     ecx, 2
0x1800502ac  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800502b1  nop
0x1800502b2  mov     [rbp+var_30], r15
0x1800502b6  lea     rcx, [rbp+var_28]
0x1800502ba  call    ?Release@?$CleanupInfo@PEAX@RAII@@SAXAEAPEAX@Z; RAII::CleanupInfo<void *>::Release(void * &)
0x1800502bf  nop
0x1800502c0  lea     rcx, [rbx-18h]; this
0x1800502c4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800502c9  nop
0x1800502ca  lea     rax, ??_7?$CAutoPbrHeapFree@PEAU_FILE_NAME_INFORMATION@@@RAII@@6B@; const RAII::CAutoPbrHeapFree<_FILE_NAME_INFORMATION *>::`vftable'
0x1800502d1  mov     [rbp+var_20], rax
0x1800502d5  lea     rcx, [rbp+var_20]
0x1800502d9  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x1800502de  mov     eax, edi
0x1800502e0  lea     r11, [rsp+70h+var_s0]
0x1800502e5  mov     rbx, [r11+30h]
0x1800502e9  mov     rsi, [r11+48h]
0x1800502ed  mov     rsp, r11
0x1800502f0  pop     r15
0x1800502f2  pop     r14
0x1800502f4  pop     r12
0x1800502f6  pop     rdi
0x1800502f7  pop     rbp
0x1800502f8  retn
```
