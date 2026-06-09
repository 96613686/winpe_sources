# CDirMonitor::Monitor(CDirMonitorEntry *,ushort const *,int,ulong,ulong)

- ea: `0x180018b30`
- end: `0x180018c6a`
- name: `?Monitor@CDirMonitor@@QEAAHPEAVCDirMonitorEntry@@PEBGHKK@Z`
- size: `314`
- prototype: `int(CDirMonitor *__hidden this, struct CDirMonitorEntry *, const unsigned __int16 *, int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180018974`

## callees

- `0x180018b30`
- `0x180018cb8`
- `0x180018d1c`
- `0x180023d6e`
- `0x180063eb8`
- `0x180064010`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180018bfa`
- `KERNEL32!CreateFileW` at `0x180018bfa`
- `KERNEL32!SetLastError` at `0x18002ee24`
- `KERNEL32!SetLastError` at `0x18002ee24`
- `KERNEL32!LocalFree` at `0x18002edca`
- `KERNEL32!LocalFree` at `0x18002ee05`
- `KERNEL32!LocalFree` at `0x18002edca`
- `KERNEL32!LocalFree` at `0x18002ee05`
- `KERNEL32!LocalAlloc` at `0x180018b9b`
- `KERNEL32!LocalAlloc` at `0x180018b9b`
- `KERNEL32!CloseHandle` at `0x18002edbc`
- `KERNEL32!CloseHandle` at `0x18002edec`
- `KERNEL32!CloseHandle` at `0x18002edf7`
- `KERNEL32!CloseHandle` at `0x18002edbc`
- `KERNEL32!CloseHandle` at `0x18002edec`
- `KERNEL32!CloseHandle` at `0x18002edf7`
- `iisutil!PuDbgPrint` at `0x18002edad`
- `iisutil!PuDbgPrint` at `0x18002edad`
- `W3TP!ThreadPoolBindIoCompletionCallback` at `0x180018c27`
- `W3TP!ThreadPoolBindIoCompletionCallback` at `0x180018c27`

## string_xrefs

- `0x18002eda6`: `servercommon\inetsrv\iis\iisrearc\iisplus\w3dirmon\dirmon.cxx`

## pseudocode

```c
__int64 __fastcall CDirMonitor::Monitor(
        CDirMonitor *this,
        struct CDirMonitorEntry *a2,
        const unsigned __int16 *a3,
        int a4)
{
  CDirMonitor *v5; // rbp
  __int64 v8; // rax
  HLOCAL v9; // rax
  HANDLE FileW; // rax
  void *v11; // rdi
  int inserted; // esi
  void *v14; // rcx
  DWORD v15; // ecx

  v5 = g_pDirMonitor;
  if ( (g_dwDebugFlags & 3) != 0 && (g_dwDebugFlags & 0x10000) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iisplus\\w3dirmon\\dirmon.cxx",
      569,
      "CDirMonitor::Monitor",
      "[CDirMonitor] Monitoring new CDirMonitorEntry\n");
  if ( !a2 || !a3 )
  {
    v15 = 87;
    goto LABEL_20;
  }
  v8 = -1;
  do
    ++v8;
  while ( a3[v8] );
  *((_DWORD *)a2 + 2) = v8;
  v9 = LocalAlloc(0x40u, 2LL * (unsigned int)(v8 + 1));
  *((_QWORD *)a2 + 2) = v9;
  if ( !v9 )
    goto LABEL_15;
  memcpy_0(v9, a3, 2LL * (unsigned int)(*((_DWORD *)a2 + 2) + 1));
  (*(void (__fastcall **)(struct CDirMonitorEntry *, __int64))(*(_QWORD *)a2 + 24LL))(a2, 512);
  FileW = CreateFileW(a3, 1u, 7u, 0, 3u, 0x42000000u, 0);
  v11 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    *((_QWORD *)a2 + 5) = FileW;
    *((_DWORD *)a2 + 13) = 287;
    *((_DWORD *)a2 + 12) = a4;
    if ( ThreadPoolBindIoCompletionCallback(FileW, DirMonOverlappedCompletionRoutine, 0) )
    {
      inserted = CDirMonitor::InsertEntry(v5, a2);
      if ( !inserted )
      {
        if ( (unsigned int)CDirMonitorEntry::RequestNotification(a2) )
          return (unsigned int)(inserted + 1);
        CDirMonitor::RemoveEntry(v5, a2);
        *((_QWORD *)a2 + 5) = -1;
        CloseHandle(v11);
        goto LABEL_14;
      }
      CloseHandle(v11);
      v14 = (void *)*((_QWORD *)a2 + 2);
      *((_QWORD *)a2 + 5) = -1;
      LocalFree(v14);
      *((_QWORD *)a2 + 2) = 0;
      *((_DWORD *)a2 + 2) = 0;
      if ( inserted != 1 )
        return 0;
      v15 = 183;
LABEL_20:
      SetLastError(v15);
      return 0;
    }
    CloseHandle(v11);
    *((_QWORD *)a2 + 5) = -1;
  }
LABEL_14:
  LocalFree(*((HLOCAL *)a2 + 2));
  *((_QWORD *)a2 + 2) = 0;
LABEL_15:
  *((_DWORD *)a2 + 2) = 0;
  return 0;
}

```

## disassembly

```asm
0x180018b30  push    rbx
0x180018b32  push    rbp
0x180018b33  push    rsi
0x180018b34  push    rdi
0x180018b35  push    r14
0x180018b37  push    r15
0x180018b39  sub     rsp, 48h
0x180018b3d  mov     eax, cs:g_dwDebugFlags
0x180018b43  mov     esi, r9d
0x180018b46  mov     rbp, cs:?g_pDirMonitor@@3PEAVCDirMonitor@@EA; CDirMonitor * g_pDirMonitor
0x180018b4d  test    al, 3
0x180018b4f  mov     rdi, r8
0x180018b52  mov     rbx, rdx
0x180018b55  setnz   cl
0x180018b58  bt      eax, 10h
0x180018b5c  setb    al
0x180018b5f  test    al, cl
0x180018b61  jnz     loc_18002ED86
0x180018b67  xor     r14d, r14d
0x180018b6a  test    rbx, rbx
0x180018b6d  jz      loc_18002EE1F
0x180018b73  test    rdi, rdi
0x180018b76  jz      loc_18002EE1F
0x180018b7c  or      r15, 0FFFFFFFFFFFFFFFFh
0x180018b80  mov     rax, r15
0x180018b83  inc     rax
0x180018b86  cmp     [rdi+rax*2], r14w
0x180018b8b  jnz     short loc_180018B83
0x180018b8d  lea     edx, [rax+1]
0x180018b90  mov     [rbx+8], eax
0x180018b93  add     rdx, rdx; uBytes
0x180018b96  mov     ecx, 40h ; '@'; uFlags
0x180018b9b  call    cs:__imp_LocalAlloc
0x180018ba1  mov     [rbx+10h], rax
0x180018ba5  mov     rcx, rax; void *
0x180018ba8  test    rax, rax
0x180018bab  jz      loc_18002EDD4
0x180018bb1  mov     r8d, [rbx+8]
0x180018bb5  mov     rdx, rdi; Src
0x180018bb8  inc     r8d
0x180018bbb  add     r8, r8; Size
0x180018bbe  call    memcpy_0
0x180018bc3  mov     rax, [rbx]
0x180018bc6  mov     edx, 200h
0x180018bcb  mov     rcx, rbx
0x180018bce  mov     rax, [rax+18h]
0x180018bd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018bd7  xor     r9d, r9d; lpSecurityAttributes
0x180018bda  mov     [rsp+78h+hTemplateFile], r14; hTemplateFile
0x180018bdf  mov     [rsp+78h+dwFlagsAndAttributes], 42000000h; dwFlagsAndAttributes
0x180018be7  mov     rcx, rdi; lpFileName
0x180018bea  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180018bf2  lea     edx, [r9+1]; dwDesiredAccess
0x180018bf6  lea     r8d, [r9+7]; dwShareMode
0x180018bfa  call    cs:__imp_CreateFileW
0x180018c00  mov     rdi, rax
0x180018c03  cmp     rax, r15
0x180018c06  jz      loc_18002EDC6
0x180018c0c  xor     r8d, r8d
0x180018c0f  mov     [rbx+28h], rax
0x180018c13  lea     rdx, ?DirMonOverlappedCompletionRoutine@@YAXKKPEAU_OVERLAPPED@@@Z; DirMonOverlappedCompletionRoutine(ulong,ulong,_OVERLAPPED *)
0x180018c1a  mov     dword ptr [rbx+34h], 11Fh
0x180018c21  mov     rcx, rax
0x180018c24  mov     [rbx+30h], esi
0x180018c27  call    cs:__imp_?ThreadPoolBindIoCompletionCallback@@YAHPEAXP6AXKKPEAU_OVERLAPPED@@@ZK@Z; ThreadPoolBindIoCompletionCallback(void *,void (*)(ulong,ulong,_OVERLAPPED *),ulong)
0x180018c2d  test    eax, eax
0x180018c2f  jz      loc_18002EDB9
0x180018c35  mov     rdx, rbx
0x180018c38  mov     rcx, rbp
0x180018c3b  call    ?InsertEntry@CDirMonitor@@QEAA?AW4LK_RETCODE@@PEAVCDirMonitorEntry@@@Z; CDirMonitor::InsertEntry(CDirMonitorEntry *)
0x180018c40  mov     esi, eax
0x180018c42  test    eax, eax
0x180018c44  jnz     loc_18002EDF4
0x180018c4a  mov     rcx, rbx; this
0x180018c4d  call    ?RequestNotification@CDirMonitorEntry@@AEAAHXZ; CDirMonitorEntry::RequestNotification(void)
0x180018c52  test    eax, eax
0x180018c54  jz      loc_18002EDDA
0x180018c5a  lea     eax, [rsi+1]
0x180018c5d  add     rsp, 48h
0x180018c61  pop     r15
0x180018c63  pop     r14
0x180018c65  pop     rdi
0x180018c66  pop     rsi
0x180018c67  pop     rbp
0x180018c68  pop     rbx
0x180018c69  retn
0x18002ed86  mov     rcx, cs:g_pDebug
0x18002ed8d  lea     rax, aCdirmonitorMon; "[CDirMonitor] Monitoring new CDirMonito"...
0x18002ed94  lea     r9, aCdirmonitorMon_0; "CDirMonitor::Monitor"
0x18002ed9b  mov     qword ptr [rsp+78h+dwCreationDisposition], rax
0x18002eda0  mov     r8d, 239h
0x18002eda6  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18002edad  call    cs:__imp_PuDbgPrint
0x18002edb3  nop
0x18002edb4  jmp     loc_180018B67
0x18002edb9  mov     rcx, rdi; hObject
0x18002edbc  call    cs:__imp_CloseHandle
0x18002edc2  mov     [rbx+28h], r15
0x18002edc6  mov     rcx, [rbx+10h]; hMem
0x18002edca  call    cs:__imp_LocalFree
0x18002edd0  mov     [rbx+10h], r14
0x18002edd4  mov     [rbx+8], r14d
0x18002edd8  jmp     short loc_18002EE2A
0x18002edda  mov     rdx, rbx
0x18002eddd  mov     rcx, rbp
0x18002ede0  call    ?RemoveEntry@CDirMonitor@@QEAA?AW4LK_RETCODE@@PEAVCDirMonitorEntry@@@Z; CDirMonitor::RemoveEntry(CDirMonitorEntry *)
0x18002ede5  mov     rcx, rdi; hObject
0x18002ede8  mov     [rbx+28h], r15
0x18002edec  call    cs:__imp_CloseHandle
0x18002edf2  jmp     short loc_18002EDC6
0x18002edf4  mov     rcx, rdi; hObject
0x18002edf7  call    cs:__imp_CloseHandle
0x18002edfd  mov     rcx, [rbx+10h]; hMem
0x18002ee01  mov     [rbx+28h], r15
0x18002ee05  call    cs:__imp_LocalFree
0x18002ee0b  mov     [rbx+10h], r14
0x18002ee0f  mov     [rbx+8], r14d
0x18002ee13  cmp     esi, 1
0x18002ee16  jnz     short loc_18002EE2A
0x18002ee18  mov     ecx, 0B7h
0x18002ee1d  jmp     short loc_18002EE24
0x18002ee1f  mov     ecx, 57h ; 'W'; dwErrCode
0x18002ee24  call    cs:__imp_SetLastError
0x18002ee2a  xor     eax, eax
0x18002ee2c  jmp     loc_180018C5D
```
