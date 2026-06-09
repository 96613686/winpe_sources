# BfspChkDiskHelper

- ea: `0x180048f2c`
- end: `0x18004922b`
- name: `BfspChkDiskHelper`
- size: `767`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, installer_update`

## callers

- `0x180048c3c`

## callees

- `0x1800078b0`
- `0x1800467b0`
- `0x18004695c`
- `0x180046a3c`
- `0x180048f2c`
- `0x18004cdd4`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800490c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800490c6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800491cb`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800491cb`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18004906d`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18004906d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800491df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800491f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800491df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800491f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800491d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800491ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800491d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800491ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048ffe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004901e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049077`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800490ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800490d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800491ab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180048ffe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004901e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049077`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800490ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800490d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800491ab`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18004909f`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18004909f`
- `bcd!BcdOpenStore` at `0x180049135`
- `bcd!BcdOpenStore` at `0x180049135`
- `bcd!BcdForciblyUnloadStore` at `0x180049144`
- `bcd!BcdForciblyUnloadStore` at `0x180049144`

## string_xrefs

- `0x180048fdb`: `BfsRepair: System volume too large for chkdsk. Size: %llu MB Max: %llu MB`
- `0x180049006`: `BfsRepair: Failed to get system volume %08x`
- `0x180048f9a`: `BfsRepair: Failed to get system partition size %08x`
- `0x180049098`: `FMIFS.DLL`
- `0x1800490b3`: `BfsRepair: Failed to load FMIFS.DLL %08x`
- `0x18004907d`: `BfsRepair: Failed to get volume information %08x`
- `0x18004914e`: `BfsRepair: Failed to unload system store. Status: %08x`
- `0x1800490dd`: `BfsRepair: Failed to get ChkdskEx proc address %08x`
- `0x180049157`: `BfsRepair: Failed to open system store. Status: %08x`

## pseudocode

```c
__int64 __fastcall BfspChkDiskHelper(__int64 a1, _DWORD *a2)
{
  unsigned int SystemPartitionSize; // eax
  __int64 LastError; // rbx
  WCHAR *SystemVolumePath; // r15
  __int64 SystemPartition; // rax
  void *v7; // rsi
  DWORD v8; // eax
  const wchar_t *v9; // rdx
  HMODULE LibraryW; // rax
  HMODULE v11; // r14
  FARPROC ProcAddress; // r12
  int v13; // eax
  int v14; // eax
  __int64 v15; // r8
  HANDLE ProcessHeap; // rax
  HANDLE v17; // rax
  unsigned __int64 v19; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v20; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v21; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v22; // [rsp+60h] [rbp-A0h]
  __int128 v23; // [rsp+70h] [rbp-90h]
  __int64 v24; // [rsp+80h] [rbp-80h]
  WCHAR FileSystemNameBuffer[264]; // [rsp+90h] [rbp-70h] BYREF

  v24 = 0;
  v19 = 0;
  v20 = 0;
  v21 = 0;
  v22 = 0;
  v23 = 0;
  if ( a2 )
    *a2 = 0;
  SystemPartitionSize = BfspGetSystemPartitionSize(&v19);
  LODWORD(LastError) = SystemPartitionSize;
  if ( SystemPartitionSize )
  {
    BfspLogMessage(4, L"BfsRepair: Failed to get system partition size %08x", SystemPartitionSize);
    return (unsigned int)LastError;
  }
  if ( v19 > 0x40000000 )
  {
    BfspLogMessage(
      4,
      L"BfsRepair: System volume too large for chkdsk. Size: %llu MB Max: %llu MB",
      (__int64)v19 / 0x100000,
      1024);
    LODWORD(LastError) = 50;
    return (unsigned int)LastError;
  }
  SystemVolumePath = (WCHAR *)BfspGetSystemVolumePath();
  if ( !SystemVolumePath )
  {
    LastError = GetLastError();
    BfspLogMessage(4, L"BfsRepair: Failed to get system volume %08x", LastError);
    return (unsigned int)LastError;
  }
  SystemPartition = BfspGetSystemPartition(0);
  v7 = (void *)SystemPartition;
  if ( SystemPartition )
  {
    BfspLogMessage(2, L"BfsChkDsk: %ws", SystemPartition);
    if ( GetVolumeInformationW(SystemVolumePath, 0, 0, 0, 0, 0, FileSystemNameBuffer, 0x104u) )
    {
      LibraryW = LoadLibraryW(L"FMIFS.DLL");
      v11 = LibraryW;
      if ( LibraryW )
      {
        ProcAddress = GetProcAddress(LibraryW, "ChkdskEx");
        if ( ProcAddress )
        {
          v21 = 0;
          BYTE10(v21) = 0;
          v24 = 0;
          *((_QWORD *)&v22 + 1) = 0;
          *(_QWORD *)&v22 = L"BFSVC";
          v23 = 0;
          LOWORD(v21) = 513;
          DWORD1(v21) = -2144861952;
          v13 = BcdOpenStore(0, 0, &v20);
          if ( v13 < 0 )
          {
            BfspLogMessage(4, L"BfsRepair: Failed to open system store. Status: %08x", (unsigned int)v13);
          }
          else
          {
            v14 = BcdForciblyUnloadStore(v20);
            if ( v14 < 0 )
              BfspLogMessage(4, L"BfsRepair: Failed to unload system store. Status: %08x", (unsigned int)v14);
          }
          dword_1800A4394 = 0;
          dword_1800A4390 = 0;
          LOBYTE(v15) = 1;
          ((void (__fastcall *)(void *, WCHAR *, __int64, __int128 *, __int64 (__fastcall *)()))ProcAddress)(
            v7,
            FileSystemNameBuffer,
            v15,
            &v21,
            BfspChkDiskCallback);
          if ( !dword_1800A4394 )
          {
            LODWORD(LastError) = GetLastError();
            if ( !(_DWORD)LastError )
              LODWORD(LastError) = 1627;
          }
          if ( a2 )
            *a2 = 1;
        }
        else
        {
          LastError = GetLastError();
          BfspLogMessage(4, L"BfsRepair: Failed to get ChkdskEx proc address %08x", LastError);
        }
        FreeLibrary(v11);
        goto LABEL_29;
      }
      v8 = GetLastError();
      v9 = L"BfsRepair: Failed to load FMIFS.DLL %08x";
    }
    else
    {
      v8 = GetLastError();
      v9 = L"BfsRepair: Failed to get volume information %08x";
    }
    LODWORD(LastError) = v8;
    BfspLogMessage(4, v9, v8);
  }
  else
  {
    LODWORD(LastError) = GetLastError();
  }
LABEL_29:
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, SystemVolumePath);
  if ( v7 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v7);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180048f2c  mov     [rsp-8+arg_0], rbx
0x180048f31  mov     [rsp-8+arg_10], rsi
0x180048f36  push    rbp
0x180048f37  push    rdi
0x180048f38  push    r12
0x180048f3a  push    r14
0x180048f3c  push    r15
0x180048f3e  lea     rbp, [rsp-1B0h]
0x180048f46  sub     rsp, 2B0h
0x180048f4d  mov     rax, cs:__security_cookie
0x180048f54  xor     rax, rsp
0x180048f57  mov     [rbp+1D0h+var_30], rax
0x180048f5e  xor     eax, eax
0x180048f60  xorps   xmm0, xmm0
0x180048f63  mov     [rbp+1D0h+var_250], rax
0x180048f67  mov     rdi, rdx
0x180048f6a  mov     [rsp+2D0h+var_290], rax
0x180048f6f  mov     [rsp+2D0h+var_288], rax
0x180048f74  movups  [rsp+2D0h+var_280], xmm0
0x180048f79  movups  [rsp+2D0h+var_270], xmm0
0x180048f7e  movups  [rsp+2D0h+var_260], xmm0
0x180048f83  test    rdx, rdx
0x180048f86  jz      short loc_180048F8A
0x180048f88  mov     [rdx], eax
0x180048f8a  lea     rcx, [rsp+2D0h+var_290]
0x180048f8f  call    BfspGetSystemPartitionSize
0x180048f94  mov     ebx, eax
0x180048f96  test    eax, eax
0x180048f98  jz      short loc_180048FB3
0x180048f9a  lea     rdx, aBfsrepairFaile_6; "BfsRepair: Failed to get system partiti"...
0x180048fa1  mov     r8d, eax
0x180048fa4  mov     ecx, 4
0x180048fa9  call    BfspLogMessage
0x180048fae  jmp     loc_1800491FE
0x180048fb3  mov     rax, [rsp+2D0h+var_290]
0x180048fb8  cmp     rax, 40000000h
0x180048fbe  jbe     short loc_180048FF1
0x180048fc0  cqo
0x180048fc2  mov     r9d, 400h
0x180048fc8  and     edx, 0FFFFFh
0x180048fce  mov     ecx, 4
0x180048fd3  lea     r8, [rdx+rax]
0x180048fd7  sar     r8, 14h
0x180048fdb  lea     rdx, aBfsrepairSyste; "BfsRepair: System volume too large for "...
0x180048fe2  call    BfspLogMessage
0x180048fe7  mov     ebx, 32h ; '2'
0x180048fec  jmp     loc_1800491FE
0x180048ff1  call    BfspGetSystemVolumePath
0x180048ff6  mov     r15, rax
0x180048ff9  test    rax, rax
0x180048ffc  jnz     short loc_18004900F
0x180048ffe  call    cs:__imp_GetLastError
0x180049004  mov     ebx, eax
0x180049006  lea     rdx, aBfsrepairFaile_0; "BfsRepair: Failed to get system volume "...
0x18004900d  jmp     short loc_180048FA1
0x18004900f  xor     ecx, ecx
0x180049011  call    BfspGetSystemPartition
0x180049016  mov     rsi, rax
0x180049019  test    rax, rax
0x18004901c  jnz     short loc_18004902B
0x18004901e  call    cs:__imp_GetLastError
0x180049024  mov     ebx, eax
0x180049026  jmp     loc_1800491D1
0x18004902b  mov     r8, rsi
0x18004902e  lea     rdx, aBfschkdskWs; "BfsChkDsk: %ws"
0x180049035  mov     ecx, 2
0x18004903a  call    BfspLogMessage
0x18004903f  mov     [rsp+2D0h+nFileSystemNameSize], 104h; nFileSystemNameSize
0x180049047  lea     rax, [rbp+1D0h+FileSystemNameBuffer]
0x18004904b  mov     [rsp+2D0h+lpFileSystemNameBuffer], rax; lpFileSystemNameBuffer
0x180049050  xor     r9d, r9d; lpVolumeSerialNumber
0x180049053  mov     [rsp+2D0h+lpFileSystemFlags], 0; lpFileSystemFlags
0x18004905c  xor     r8d, r8d; nVolumeNameSize
0x18004905f  xor     edx, edx; lpVolumeNameBuffer
0x180049061  mov     [rsp+2D0h+lpMaximumComponentLength], 0; lpMaximumComponentLength
0x18004906a  mov     rcx, r15; lpRootPathName
0x18004906d  call    cs:__imp_GetVolumeInformationW
0x180049073  test    eax, eax
0x180049075  jnz     short loc_180049098
0x180049077  call    cs:__imp_GetLastError
0x18004907d  lea     rdx, aBfsrepairFaile_2; "BfsRepair: Failed to get volume informa"...
0x180049084  mov     r8d, eax
0x180049087  mov     ecx, 4
0x18004908c  mov     ebx, eax
0x18004908e  call    BfspLogMessage
0x180049093  jmp     loc_1800491D1
0x180049098  lea     rcx, aFmifsDll; "FMIFS.DLL"
0x18004909f  call    cs:__imp_LoadLibraryW
0x1800490a5  mov     r14, rax
0x1800490a8  test    rax, rax
0x1800490ab  jnz     short loc_1800490BC
0x1800490ad  call    cs:__imp_GetLastError
0x1800490b3  lea     rdx, aBfsrepairFaile; "BfsRepair: Failed to load FMIFS.DLL %08"...
0x1800490ba  jmp     short loc_180049084
0x1800490bc  lea     rdx, aChkdskex; "ChkdskEx"
0x1800490c3  mov     rcx, r14; hModule
0x1800490c6  call    cs:__imp_GetProcAddress
0x1800490cc  mov     r12, rax
0x1800490cf  test    rax, rax
0x1800490d2  jnz     short loc_1800490F5
0x1800490d4  call    cs:__imp_GetLastError
0x1800490da  mov     r8d, eax
0x1800490dd  lea     rdx, aBfsrepairFaile_1; "BfsRepair: Failed to get ChkdskEx proc "...
0x1800490e4  lea     ecx, [r12+4]
0x1800490e9  mov     ebx, eax
0x1800490eb  call    BfspLogMessage
0x1800490f0  jmp     loc_1800491C8
0x1800490f5  xorps   xmm0, xmm0
0x1800490f8  lea     r8, [rsp+2D0h+var_288]
0x1800490fd  xor     eax, eax
0x1800490ff  xor     edx, edx
0x180049101  movups  [rsp+2D0h+var_280], xmm0
0x180049106  mov     byte ptr [rsp+2D0h+var_280+0Ah], al
0x18004910a  xor     ecx, ecx
0x18004910c  mov     [rbp+1D0h+var_250], rax
0x180049110  lea     rax, aBfsvc; "BFSVC"
0x180049117  movups  [rsp+2D0h+var_270], xmm0
0x18004911c  mov     qword ptr [rsp+2D0h+var_270], rax
0x180049121  movups  [rsp+2D0h+var_260], xmm0
0x180049126  mov     word ptr [rsp+2D0h+var_280], 201h
0x18004912d  mov     dword ptr [rsp+2D0h+var_280+4], 80280100h
0x180049135  call    cs:__imp_BcdOpenStore
0x18004913b  test    eax, eax
0x18004913d  js      short loc_180049157
0x18004913f  mov     rcx, [rsp+2D0h+var_288]
0x180049144  call    cs:__imp_BcdForciblyUnloadStore
0x18004914a  test    eax, eax
0x18004914c  jns     short loc_18004916B
0x18004914e  lea     rdx, aBfsrepairFaile_4; "BfsRepair: Failed to unload system stor"...
0x180049155  jmp     short loc_18004915E
0x180049157  lea     rdx, aBfsrepairFaile_3; "BfsRepair: Failed to open system store."...
0x18004915e  mov     r8d, eax
0x180049161  mov     ecx, 4
0x180049166  call    BfspLogMessage
0x18004916b  lea     rax, BfspChkDiskCallback
0x180049172  mov     cs:dword_1800A4394, 0
0x18004917c  mov     [rsp+2D0h+lpMaximumComponentLength], rax
0x180049181  lea     r9, [rsp+2D0h+var_280]
0x180049186  mov     rax, r12
0x180049189  mov     cs:dword_1800A4390, 0
0x180049193  mov     r8b, 1
0x180049196  lea     rdx, [rbp+1D0h+FileSystemNameBuffer]
0x18004919a  mov     rcx, rsi
0x18004919d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800491a2  cmp     cs:dword_1800A4394, 0
0x1800491a9  jnz     short loc_1800491BD
0x1800491ab  call    cs:__imp_GetLastError
0x1800491b1  mov     ebx, eax
0x1800491b3  mov     eax, 65Bh
0x1800491b8  test    ebx, ebx
0x1800491ba  cmovz   ebx, eax
0x1800491bd  test    rdi, rdi
0x1800491c0  jz      short loc_1800491C8
0x1800491c2  mov     dword ptr [rdi], 1
0x1800491c8  mov     rcx, r14; hLibModule
0x1800491cb  call    cs:__imp_FreeLibrary
0x1800491d1  call    cs:__imp_GetProcessHeap
0x1800491d7  mov     r8, r15; lpMem
0x1800491da  xor     edx, edx; dwFlags
0x1800491dc  mov     rcx, rax; hHeap
0x1800491df  call    cs:__imp_HeapFree
0x1800491e5  test    rsi, rsi
0x1800491e8  jz      short loc_1800491FE
0x1800491ea  call    cs:__imp_GetProcessHeap
0x1800491f0  mov     r8, rsi; lpMem
0x1800491f3  xor     edx, edx; dwFlags
0x1800491f5  mov     rcx, rax; hHeap
0x1800491f8  call    cs:__imp_HeapFree
0x1800491fe  mov     eax, ebx
0x180049200  mov     rcx, [rbp+1D0h+var_30]
0x180049207  xor     rcx, rsp; StackCookie
0x18004920a  call    __security_check_cookie
0x18004920f  lea     r11, [rsp+2D0h+var_20]
0x180049217  mov     rbx, [r11+30h]
0x18004921b  mov     rsi, [r11+40h]
0x18004921f  mov     rsp, r11
0x180049222  pop     r15
0x180049224  pop     r14
0x180049226  pop     r12
0x180049228  pop     rdi
0x180049229  pop     rbp
0x18004922a  retn
```
