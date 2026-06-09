# PbrDeleteReparsePoint

- ea: `0x18004f39c`
- end: `0x18004f73c`
- name: `PbrDeleteReparsePoint`
- size: `928`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, service_task, installer_update`

## callers

- `0x18004c418`

## callees

- `0x180004af8`
- `0x180005cc0`
- `0x18000d6f0`
- `0x18000d92c`
- `0x180023654`
- `0x180037344`
- `0x18004d404`
- `0x18004f39c`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004f461`
- `KERNEL32!GetLastError` at `0x18004f4a8`
- `KERNEL32!GetLastError` at `0x18004f5e5`
- `KERNEL32!GetLastError` at `0x18004f62c`
- `KERNEL32!GetLastError` at `0x18004f6c9`
- `KERNEL32!GetLastError` at `0x18004f461`
- `KERNEL32!GetLastError` at `0x18004f4a8`
- `KERNEL32!GetLastError` at `0x18004f5e5`
- `KERNEL32!GetLastError` at `0x18004f62c`
- `KERNEL32!GetLastError` at `0x18004f6c9`
- `KERNEL32!HeapAlloc` at `0x18004f500`
- `KERNEL32!HeapAlloc` at `0x18004f500`
- `KERNEL32!GetProcessHeap` at `0x18004f4f2`
- `KERNEL32!GetProcessHeap` at `0x18004f4f2`
- `KERNEL32!CreateFileW` at `0x18004f43d`
- `KERNEL32!CreateFileW` at `0x18004f43d`
- `KERNEL32!DeviceIoControl` at `0x18004f5db`
- `KERNEL32!DeviceIoControl` at `0x18004f6bf`
- `KERNEL32!DeviceIoControl` at `0x18004f5db`
- `KERNEL32!DeviceIoControl` at `0x18004f6bf`

## string_xrefs

- `0x18004f3fc`: `PbrDeleteReparsePoint`
- `0x18004f495`: `PbrDeleteReparsePoint`
- `0x18004f54d`: `PbrDeleteReparsePoint`
- `0x18004f619`: `PbrDeleteReparsePoint`
- `0x18004f47a`: `Failed to open [%s] for delete`
- `0x18004f5fe`: `Failed to get underlying reparse point for [%s]`
- `0x18004f6e2`: `Failed to delete underlying reparse point for [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall PbrDeleteReparsePoint(_QWORD *a1)
{
  int Canonical; // r14d
  LPCWSTR v3; // rbx
  signed int LastError; // eax
  signed int v5; // eax
  unsigned int v6; // esi
  HANDLE ProcessHeap; // rax
  LPVOID v9; // rax
  DWORD v10; // esi
  void *v11; // rdi
  HANDLE *v12; // rax
  signed int v13; // eax
  signed int v14; // eax
  void *v15; // rdi
  HANDLE *v16; // rax
  signed int v17; // eax
  _QWORD v18[2]; // [rsp+40h] [rbp-20h] BYREF
  void **v19; // [rsp+50h] [rbp-10h] BYREF
  HANDLE FileW; // [rsp+58h] [rbp-8h] BYREF
  DWORD nOutBufferSize; // [rsp+98h] [rbp+38h] BYREF
  LPCWSTR lpFileName; // [rsp+A0h] [rbp+40h] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpFileName);
  Canonical = PushButtonReset::Path::GetCanonical(a1, &lpFileName);
  v3 = lpFileName;
  if ( Canonical >= 0 )
  {
    v19 = &RAII::CAutoCleanup<void *>::`vftable';
    FileW = CreateFileW(lpFileName, 0x100u, 7u, 0, 3u, 0x2200000u, 0);
    if ( *(_QWORD *)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&((__int64)&v19) == -1 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LastError,
        "PbrDeleteReparsePoint",
        "base\\reset\\util\\src\\filesystem.cpp",
        84,
        L"Failed to open [%s] for delete",
        v3);
      v5 = GetLastError();
      v6 = v5;
      if ( v5 > 0 )
        v6 = (unsigned __int16)v5 | 0x80070000;
    }
    else
    {
      nOutBufferSize = 16408;
      v18[1] = 0;
      v18[0] = &RAII::CAutoPbrHeapFree<_REPARSE_GUID_DATA_BUFFER *>::`vftable';
      ProcessHeap = GetProcessHeap();
      v9 = HeapAlloc(ProcessHeap, 0, 0x4018u);
      ((void (__fastcall *)(_QWORD *, LPVOID))RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::operator=)(v18, v9);
      if ( (*(unsigned __int8 (__fastcall **)(_QWORD *))(v18[0] + 72LL))(v18) )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          2147942414LL,
          "PbrDeleteReparsePoint",
          "base\\reset\\util\\src\\filesystem.cpp",
          91,
          L"Failed to allocate buffer");
        v18[0] = &RAII::CAutoPbrHeapFree<_REPARSE_GUID_DATA_BUFFER *>::`vftable';
        RAII::CAutoPbrHeapFree<unsigned short *>::Release(v18);
        v19 = &RAII::CAutoCleanup<void *>::`vftable';
        RAII::CleanupInfo<void *>::Release(&FileW);
        Canonical = -2147024882;
        goto LABEL_23;
      }
      v10 = nOutBufferSize;
      v11 = (void *)(*(__int64 (__fastcall **)(_QWORD *))(v18[0] + 32LL))(v18);
      v12 = (HANDLE *)((__int64 (__fastcall *)(void ***))v19[4])(&v19);
      if ( DeviceIoControl(*v12, 0x900A8u, 0, 0, v11, v10, &nOutBufferSize, 0) )
      {
        *(_WORD *)((*(__int64 (__fastcall **)(_QWORD *))(v18[0] + 24LL))(v18) + 4) = 0;
        v15 = (void *)(*(__int64 (__fastcall **)(_QWORD *))(v18[0] + 32LL))(v18);
        v16 = (HANDLE *)((__int64 (__fastcall *)(void ***))v19[4])(&v19);
        if ( DeviceIoControl(*v16, 0x900ACu, v15, 0x18u, 0, 0, &nOutBufferSize, 0) )
        {
          v18[0] = &RAII::CAutoPbrHeapFree<_REPARSE_GUID_DATA_BUFFER *>::`vftable';
          RAII::CAutoPbrHeapFree<unsigned short *>::Release(v18);
          v19 = &RAII::CAutoCleanup<void *>::`vftable';
          RAII::CleanupInfo<void *>::Release(&FileW);
          goto LABEL_23;
        }
        v17 = GetLastError();
        if ( v17 > 0 )
          v17 = (unsigned __int16)v17 | 0x80070000;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v17,
          "PbrDeleteReparsePoint",
          "base\\reset\\util\\src\\filesystem.cpp",
          120,
          L"Failed to delete underlying reparse point for [%s]",
          v3);
      }
      else
      {
        v13 = GetLastError();
        if ( v13 > 0 )
          v13 = (unsigned __int16)v13 | 0x80070000;
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v13,
          "PbrDeleteReparsePoint",
          "base\\reset\\util\\src\\filesystem.cpp",
          104,
          L"Failed to get underlying reparse point for [%s]",
          v3);
      }
      v14 = GetLastError();
      v6 = v14;
      if ( v14 > 0 )
        v6 = (unsigned __int16)v14 | 0x80070000;
      v18[0] = &RAII::CAutoPbrHeapFree<_REPARSE_GUID_DATA_BUFFER *>::`vftable';
      RAII::CAutoPbrHeapFree<unsigned short *>::Release(v18);
    }
    v19 = &RAII::CAutoCleanup<void *>::`vftable';
    RAII::CleanupInfo<void *>::Release(&FileW);
    ATL::CStringData::Release((ATL::CStringData *)(v3 - 12));
    return v6;
  }
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)Canonical,
    "PbrDeleteReparsePoint",
    "base\\reset\\util\\src\\filesystem.cpp",
    70,
    L"Failed to get canonical form for [%s]",
    *a1);
LABEL_23:
  ATL::CStringData::Release((ATL::CStringData *)(v3 - 12));
  return (unsigned int)Canonical;
}

```

## disassembly

```asm
0x18004f39c  mov     [rsp-28h+arg_0], rbx
0x18004f3a1  mov     [rsp-28h+arg_18], rsi
0x18004f3a6  push    rbp
0x18004f3a7  push    rdi
0x18004f3a8  push    r12
0x18004f3aa  push    r13
0x18004f3ac  push    r14
0x18004f3ae  mov     rbp, rsp
0x18004f3b1  sub     rsp, 60h
0x18004f3b5  mov     rdi, rcx
0x18004f3b8  lea     rcx, [rbp+lpFileName]
0x18004f3bc  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18004f3c1  nop
0x18004f3c2  lea     rdx, [rbp+lpFileName]
0x18004f3c6  mov     rcx, rdi
0x18004f3c9  call    ?GetCanonical@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetCanonical(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18004f3ce  mov     r14d, eax
0x18004f3d1  mov     rbx, [rbp+lpFileName]
0x18004f3d5  test    eax, eax
0x18004f3d7  jns     short loc_18004F415
0x18004f3d9  mov     rcx, [rdi]
0x18004f3dc  mov     [rsp+60h+hTemplateFile], rcx
0x18004f3e1  lea     rax, aFailedToGetCan_2; "Failed to get canonical form for [%s]"
0x18004f3e8  mov     qword ptr [rsp+60h+dwFlagsAndAttributes], rax
0x18004f3ed  mov     [rsp+60h+dwCreationDisposition], 46h ; 'F'
0x18004f3f5  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004f3fc  lea     r8, aPbrdeleterepar; "PbrDeleteReparsePoint"
0x18004f403  mov     edx, r14d
0x18004f406  mov     ecx, 2
0x18004f40b  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004f410  jmp     loc_18004F717
0x18004f415  mov     [rsp+60h+hTemplateFile], 0; hTemplateFile
0x18004f41e  mov     [rsp+60h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18004f426  mov     [rsp+60h+dwCreationDisposition], 3; dwCreationDisposition
0x18004f42e  xor     r9d, r9d; lpSecurityAttributes
0x18004f431  mov     edx, 100h; dwDesiredAccess
0x18004f436  lea     r8d, [r9+7]; dwShareMode
0x18004f43a  mov     rcx, rbx; lpFileName
0x18004f43d  call    cs:__imp_CreateFileW
0x18004f443  lea     r12, ??_7?$CAutoCleanup@PEAX@RAII@@6B@; const RAII::CAutoCleanup<void *>::`vftable'
0x18004f44a  mov     [rbp+var_10], r12
0x18004f44e  mov     [rbp+var_8], rax
0x18004f452  lea     rcx, [rbp+var_10]
0x18004f456  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18004f45b  cmp     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x18004f45f  jnz     short loc_18004F4D7
0x18004f461  call    cs:__imp_GetLastError
0x18004f467  mov     edi, 80070000h
0x18004f46c  test    eax, eax
0x18004f46e  jle     short loc_18004F475
0x18004f470  movzx   eax, ax
0x18004f473  or      eax, edi
0x18004f475  mov     [rsp+60h+hTemplateFile], rbx
0x18004f47a  lea     rcx, aFailedToOpenSF; "Failed to open [%s] for delete"
0x18004f481  mov     qword ptr [rsp+60h+dwFlagsAndAttributes], rcx
0x18004f486  mov     [rsp+60h+dwCreationDisposition], 54h ; 'T'
0x18004f48e  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004f495  lea     r8, aPbrdeleterepar; "PbrDeleteReparsePoint"
0x18004f49c  mov     edx, eax
0x18004f49e  mov     ecx, 2
0x18004f4a3  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004f4a8  call    cs:__imp_GetLastError
0x18004f4ae  mov     esi, eax
0x18004f4b0  test    eax, eax
0x18004f4b2  jle     short loc_18004F4B9
0x18004f4b4  movzx   esi, ax
0x18004f4b7  or      esi, edi
0x18004f4b9  mov     [rbp+var_10], r12
0x18004f4bd  lea     rcx, [rbp+var_8]
0x18004f4c1  call    ?Release@?$CleanupInfo@PEAX@RAII@@SAXAEAPEAX@Z; RAII::CleanupInfo<void *>::Release(void * &)
0x18004f4c6  nop
0x18004f4c7  lea     rcx, [rbx-18h]; this
0x18004f4cb  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004f4d0  mov     eax, esi
0x18004f4d2  jmp     loc_18004F723
0x18004f4d7  mov     edi, 4018h
0x18004f4dc  mov     [rbp+nOutBufferSize], edi
0x18004f4df  mov     [rbp+var_18], 0
0x18004f4e7  lea     r13, ??_7?$CAutoPbrHeapFree@PEAU_REPARSE_GUID_DATA_BUFFER@@@RAII@@6B@; const RAII::CAutoPbrHeapFree<_REPARSE_GUID_DATA_BUFFER *>::`vftable'
0x18004f4ee  mov     [rbp+var_20], r13
0x18004f4f2  call    cs:__imp_GetProcessHeap
0x18004f4f8  mov     rcx, rax; hHeap
0x18004f4fb  mov     r8d, edi; dwBytes
0x18004f4fe  xor     edx, edx; dwFlags
0x18004f500  call    cs:__imp_HeapAlloc
0x18004f506  mov     rcx, [rbp+var_20]
0x18004f50a  mov     r8, [rcx+30h]
0x18004f50e  mov     rdx, rax
0x18004f511  lea     rcx, [rbp+var_20]
0x18004f515  mov     rax, r8
0x18004f518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f51d  mov     rax, [rbp+var_20]
0x18004f521  lea     rcx, [rbp+var_20]
0x18004f525  mov     rax, [rax+48h]
0x18004f529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f52e  test    al, al
0x18004f530  jz      short loc_18004F58A
0x18004f532  lea     rax, aFailedToAlloca_26; "Failed to allocate buffer"
0x18004f539  mov     qword ptr [rsp+60h+dwFlagsAndAttributes], rax
0x18004f53e  mov     [rsp+60h+dwCreationDisposition], 5Bh ; '['
0x18004f546  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004f54d  lea     r8, aPbrdeleterepar; "PbrDeleteReparsePoint"
0x18004f554  mov     edx, 8007000Eh
0x18004f559  mov     ecx, 2
0x18004f55e  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004f563  nop
0x18004f564  mov     [rbp+var_20], r13
0x18004f568  lea     rcx, [rbp+var_20]
0x18004f56c  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x18004f571  nop
0x18004f572  mov     [rbp+var_10], r12
0x18004f576  lea     rcx, [rbp+var_8]
0x18004f57a  call    ?Release@?$CleanupInfo@PEAX@RAII@@SAXAEAPEAX@Z; RAII::CleanupInfo<void *>::Release(void * &)
0x18004f57f  mov     r14d, 8007000Eh
0x18004f585  jmp     loc_18004F717
0x18004f58a  mov     esi, [rbp+nOutBufferSize]
0x18004f58d  mov     rax, [rbp+var_20]
0x18004f591  lea     rcx, [rbp+var_20]
0x18004f595  mov     rax, [rax+20h]
0x18004f599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f59e  mov     rdi, rax
0x18004f5a1  mov     rcx, [rbp+var_10]
0x18004f5a5  mov     rax, [rcx+20h]
0x18004f5a9  lea     rcx, [rbp+var_10]
0x18004f5ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f5b2  mov     [rsp+60h+lpOverlapped], 0; lpOverlapped
0x18004f5bb  lea     rcx, [rbp+nOutBufferSize]
0x18004f5bf  mov     [rsp+60h+hTemplateFile], rcx; lpBytesReturned
0x18004f5c4  mov     [rsp+60h+dwFlagsAndAttributes], esi; nOutBufferSize
0x18004f5c8  mov     qword ptr [rsp+60h+dwCreationDisposition], rdi; lpOutBuffer
0x18004f5cd  xor     r9d, r9d; nInBufferSize
0x18004f5d0  xor     r8d, r8d; lpInBuffer
0x18004f5d3  mov     edx, 900A8h; dwIoControlCode
0x18004f5d8  mov     rcx, [rax]; hDevice
0x18004f5db  call    cs:__imp_DeviceIoControl
0x18004f5e1  test    eax, eax
0x18004f5e3  jnz     short loc_18004F64F
0x18004f5e5  call    cs:__imp_GetLastError
0x18004f5eb  mov     edi, 80070000h
0x18004f5f0  test    eax, eax
0x18004f5f2  jle     short loc_18004F5F9
0x18004f5f4  movzx   eax, ax
0x18004f5f7  or      eax, edi
0x18004f5f9  mov     [rsp+60h+hTemplateFile], rbx
0x18004f5fe  lea     rcx, aFailedToGetUnd_0; "Failed to get underlying reparse point "...
0x18004f605  mov     qword ptr [rsp+60h+dwFlagsAndAttributes], rcx
0x18004f60a  mov     [rsp+60h+dwCreationDisposition], 68h ; 'h'
0x18004f612  lea     r9, aBaseResetUtilS_5; "base\\reset\\util\\src\\filesystem.cpp"
0x18004f619  lea     r8, aPbrdeleterepar; "PbrDeleteReparsePoint"
0x18004f620  mov     edx, eax
0x18004f622  mov     ecx, 2
0x18004f627  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18004f62c  call    cs:__imp_GetLastError
0x18004f632  test    eax, eax
0x18004f634  mov     esi, eax
0x18004f636  jle     short loc_18004F63D
0x18004f638  movzx   esi, ax
0x18004f63b  or      esi, edi
0x18004f63d  mov     [rbp+var_20], r13
0x18004f641  lea     rcx, [rbp+var_20]
0x18004f645  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x18004f64a  jmp     loc_18004F4B9
0x18004f64f  mov     rax, [rbp+var_20]
0x18004f653  lea     rcx, [rbp+var_20]
0x18004f657  mov     rax, [rax+18h]
0x18004f65b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f660  xor     ecx, ecx
0x18004f662  mov     [rax+4], cx
0x18004f666  mov     rax, [rbp+var_20]
0x18004f66a  lea     rcx, [rbp+var_20]
0x18004f66e  mov     rax, [rax+20h]
0x18004f672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f677  mov     rdi, rax
0x18004f67a  mov     rcx, [rbp+var_10]
0x18004f67e  mov     rax, [rcx+20h]
0x18004f682  lea     rcx, [rbp+var_10]
0x18004f686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f68b  mov     [rsp+60h+lpOverlapped], 0; lpOverlapped
0x18004f694  lea     rcx, [rbp+nOutBufferSize]
0x18004f698  mov     [rsp+60h+hTemplateFile], rcx; lpBytesReturned
0x18004f69d  mov     [rsp+60h+dwFlagsAndAttributes], 0; nOutBufferSize
0x18004f6a5  mov     qword ptr [rsp+60h+dwCreationDisposition], 0; lpOutBuffer
0x18004f6ae  mov     r9d, 18h; nInBufferSize
0x18004f6b4  mov     r8, rdi; lpInBuffer
0x18004f6b7  mov     edx, 900ACh; dwIoControlCode
0x18004f6bc  mov     rcx, [rax]; hDevice
0x18004f6bf  call    cs:__imp_DeviceIoControl
0x18004f6c5  test    eax, eax
0x18004f6c7  jnz     short loc_18004F6FB
0x18004f6c9  call    cs:__imp_GetLastError
0x18004f6cf  mov     edi, 80070000h
0x18004f6d4  test    eax, eax
0x18004f6d6  jle     short loc_18004F6DD
0x18004f6d8  movzx   eax, ax
0x18004f6db  or      eax, edi
0x18004f6dd  mov     [rsp+60h+hTemplateFile], rbx
0x18004f6e2  lea     rcx, aFailedToDelete_14; "Failed to delete underlying reparse poi"...
0x18004f6e9  mov     qword ptr [rsp+60h+dwFlagsAndAttributes], rcx
0x18004f6ee  mov     [rsp+60h+dwCreationDisposition], 78h ; 'x'
0x18004f6f6  jmp     loc_18004F612
0x18004f6fb  mov     [rbp+var_20], r13
0x18004f6ff  lea     rcx, [rbp+var_20]
0x18004f703  call    ?Release@?$CAutoPbrHeapFree@PEAG@RAII@@UEAAXXZ; RAII::CAutoPbrHeapFree<ushort *>::Release(void)
0x18004f708  nop
0x18004f709  mov     [rbp+var_10], r12
0x18004f70d  lea     rcx, [rbp+var_8]
0x18004f711  call    ?Release@?$CleanupInfo@PEAX@RAII@@SAXAEAPEAX@Z; RAII::CleanupInfo<void *>::Release(void * &)
0x18004f716  nop
0x18004f717  lea     rcx, [rbx-18h]; this
0x18004f71b  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18004f720  mov     eax, r14d
0x18004f723  lea     r11, [rsp+60h+var_s0]
0x18004f728  mov     rbx, [r11+30h]
0x18004f72c  mov     rsi, [r11+48h]
0x18004f730  mov     rsp, r11
0x18004f733  pop     r14
0x18004f735  pop     r13
0x18004f737  pop     r12
0x18004f739  pop     rdi
0x18004f73a  pop     rbp
0x18004f73b  retn
```
