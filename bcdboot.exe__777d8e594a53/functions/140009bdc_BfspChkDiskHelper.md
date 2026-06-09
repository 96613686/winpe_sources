# BfspChkDiskHelper

- ea: `0x140009bdc`
- end: `0x140009fcd`
- name: `BfspChkDiskHelper`
- size: `1009`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, installer_update`

## callers

- `0x140009658`

## callees

- `0x140002c14`
- `0x1400032d0`
- `0x140003bf8`
- `0x140003cbc`
- `0x140009bdc`
- `0x14000e628`
- `0x14001acec`
- `0x14001bb00`
- `0x1400265fa`
- `0x140026650`
- `0x140027010`

## import_xrefs

- `KERNEL32!SetLastError` at `0x140009d64`
- `KERNEL32!SetLastError` at `0x140009d64`
- `KERNEL32!GetLastError` at `0x140009ca4`
- `KERNEL32!GetLastError` at `0x140009db8`
- `KERNEL32!GetLastError` at `0x140009e09`
- `KERNEL32!GetLastError` at `0x140009e3f`
- `KERNEL32!GetLastError` at `0x140009e66`
- `KERNEL32!GetLastError` at `0x140009f36`
- `KERNEL32!GetLastError` at `0x140009f8c`
- `KERNEL32!GetLastError` at `0x140009ca4`
- `KERNEL32!GetLastError` at `0x140009db8`
- `KERNEL32!GetLastError` at `0x140009e09`
- `KERNEL32!GetLastError` at `0x140009e3f`
- `KERNEL32!GetLastError` at `0x140009e66`
- `KERNEL32!GetLastError` at `0x140009f36`
- `KERNEL32!GetLastError` at `0x140009f8c`
- `KERNEL32!HeapFree` at `0x140009d9a`
- `KERNEL32!HeapFree` at `0x140009f6b`
- `KERNEL32!HeapFree` at `0x140009f84`
- `KERNEL32!HeapFree` at `0x140009d9a`
- `KERNEL32!HeapFree` at `0x140009f6b`
- `KERNEL32!HeapFree` at `0x140009f84`
- `KERNEL32!LoadLibraryW` at `0x140009e31`
- `KERNEL32!LoadLibraryW` at `0x140009e31`
- `KERNEL32!HeapAlloc` at `0x140009d54`
- `KERNEL32!HeapAlloc` at `0x140009d54`
- `KERNEL32!GetProcAddress` at `0x140009e58`
- `KERNEL32!GetProcAddress` at `0x140009e58`
- `KERNEL32!GetProcessHeap` at `0x140009d41`
- `KERNEL32!GetProcessHeap` at `0x140009d8c`
- `KERNEL32!GetProcessHeap` at `0x140009f5d`
- `KERNEL32!GetProcessHeap` at `0x140009f76`
- `KERNEL32!GetProcessHeap` at `0x140009d41`
- `KERNEL32!GetProcessHeap` at `0x140009d8c`
- `KERNEL32!GetProcessHeap` at `0x140009f5d`
- `KERNEL32!GetProcessHeap` at `0x140009f76`
- `KERNEL32!FreeLibrary` at `0x140009f57`
- `KERNEL32!FreeLibrary` at `0x140009f57`
- `KERNEL32!DeviceIoControl` at `0x140009c9a`
- `KERNEL32!DeviceIoControl` at `0x140009c9a`
- `KERNEL32!CloseHandle` at `0x140009cc2`
- `KERNEL32!CloseHandle` at `0x140009cc2`
- `KERNEL32!GetVolumeInformationW` at `0x140009dff`
- `KERNEL32!GetVolumeInformationW` at `0x140009dff`

## string_xrefs

- `0x140009ccf`: `BfsRepair: Failed to get system partition size %08x`
- `0x140009d02`: `BfsRepair: System volume too large for chkdsk. Size: %llu MB Max: %llu MB`
- `0x140009f94`: `BfsRepair: Failed to get system volume %08x`
- `0x140009e0f`: `BfsRepair: Failed to get volume information %08x`
- `0x140009e2a`: `FMIFS.DLL`
- `0x140009e45`: `BfsRepair: Failed to load FMIFS.DLL %08x`
- `0x140009e6f`: `BfsRepair: Failed to get ChkdskEx proc address %08x`
- `0x140009edf`: `BfsRepair: Failed to unload system store. Status: %08x`
- `0x140009ee8`: `BfsRepair: Failed to open system store. Status: %08x`

## pseudocode

```c
__int64 __fastcall BfspChkDiskHelper(__int64 a1, _DWORD *a2)
{
  unsigned __int64 v3; // rbx
  int v4; // eax
  char *v5; // rsi
  __int64 LastError; // rdi
  wchar_t *SystemPartition; // rsi
  __int64 v8; // rax
  size_t v9; // r12
  SIZE_T v10; // rbx
  HANDLE ProcessHeap; // rax
  wchar_t *v12; // rax
  wchar_t *v13; // r15
  HANDLE v14; // rax
  wchar_t *v15; // rax
  wchar_t *v16; // rbx
  DWORD v17; // eax
  const wchar_t *v18; // rdx
  HMODULE LibraryW; // rax
  HMODULE v20; // rsi
  __int64 v21; // r8
  FARPROC ProcAddress; // r12
  int v23; // eax
  int v24; // eax
  __int64 v25; // r8
  HANDLE v26; // rax
  HANDLE v27; // rax
  DWORD BytesReturned; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hDevice; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE Handle; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v32; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v33; // [rsp+68h] [rbp-98h]
  __int128 v34; // [rsp+78h] [rbp-88h]
  __int64 v35; // [rsp+88h] [rbp-78h]
  _BYTE OutBuffer[16]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v37; // [rsp+A0h] [rbp-60h]
  WCHAR FileSystemNameBuffer[264]; // [rsp+120h] [rbp+20h] BYREF

  Handle = 0;
  v35 = 0;
  v3 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  if ( a2 )
    *a2 = 0;
  BytesReturned = 0;
  memset_0(OutBuffer, 0, 0x90u);
  hDevice = 0;
  v4 = BfspOpenSystemPartition(&hDevice, 0x80000000LL);
  v5 = (char *)hDevice;
  LODWORD(LastError) = v4;
  if ( !v4 )
  {
    if ( DeviceIoControl(hDevice, 0x70048u, 0, 0, OutBuffer, 0x90u, &BytesReturned, 0) )
    {
      v3 = v37;
      LODWORD(LastError) = 0;
    }
    else
    {
      LODWORD(LastError) = GetLastError();
    }
  }
  if ( (unsigned __int64)(v5 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v5);
  if ( (_DWORD)LastError )
  {
    BfspLogMessage(4, L"BfsRepair: Failed to get system partition size %08x", (unsigned int)LastError);
    return (unsigned int)LastError;
  }
  if ( v3 > 0x40000000 )
  {
    BfspLogMessage(
      4,
      L"BfsRepair: System volume too large for chkdsk. Size: %llu MB Max: %llu MB",
      (__int64)v3 / 0x100000,
      1024);
    LODWORD(LastError) = 50;
    return (unsigned int)LastError;
  }
  SystemPartition = BfspGetSystemPartition(1);
  if ( !SystemPartition )
    goto LABEL_41;
  v8 = -1;
  do
    ++v8;
  while ( SystemPartition[v8] );
  v9 = v8 + 2;
  v10 = 2 * (v8 + 2);
  ProcessHeap = GetProcessHeap();
  v12 = (wchar_t *)HeapAlloc(ProcessHeap, 8u, v10);
  v13 = v12;
  if ( v12 )
  {
    StringCchCopyW(v12, v9, SystemPartition);
    StringCchCatW(v13, v9, L"\\");
  }
  else
  {
    SetLastError(8u);
  }
  v14 = GetProcessHeap();
  HeapFree(v14, 0, SystemPartition);
  if ( !v13 )
  {
LABEL_41:
    LastError = GetLastError();
    BfspLogMessage(4, L"BfsRepair: Failed to get system volume %08x", LastError);
    return (unsigned int)LastError;
  }
  v15 = BfspGetSystemPartition(0);
  v16 = v15;
  if ( v15 )
  {
    BfspLogMessage(2, L"BfsChkDsk: %ws", v15);
    if ( GetVolumeInformationW(v13, 0, 0, 0, 0, 0, FileSystemNameBuffer, 0x104u) )
    {
      LibraryW = LoadLibraryW(L"FMIFS.DLL");
      v20 = LibraryW;
      if ( LibraryW )
      {
        ProcAddress = GetProcAddress(LibraryW, "ChkdskEx");
        if ( ProcAddress )
        {
          v32 = 0;
          LOWORD(v32) = 513;
          v35 = 0;
          BYTE10(v32) = 0;
          *((_QWORD *)&v33 + 1) = 0;
          *(_QWORD *)&v33 = L"BFSVC";
          v34 = 0;
          DWORD1(v32) = -2144861952;
          v23 = BiOpenStoreWithHash(0, 0, v21, &Handle);
          if ( v23 < 0 )
          {
            BfspLogMessage(4, L"BfsRepair: Failed to open system store. Status: %08x", (unsigned int)v23);
          }
          else
          {
            v24 = BcdForciblyUnloadStore(Handle);
            if ( v24 < 0 )
              BfspLogMessage(4, L"BfsRepair: Failed to unload system store. Status: %08x", (unsigned int)v24);
          }
          dword_14003F864 = 0;
          dword_14003F860 = 0;
          LOBYTE(v25) = 1;
          ((void (__fastcall *)(wchar_t *, WCHAR *, __int64, __int128 *, __int64 (__fastcall *)()))ProcAddress)(
            v16,
            FileSystemNameBuffer,
            v25,
            &v32,
            BfspChkDiskCallback);
          if ( !dword_14003F864 )
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
        FreeLibrary(v20);
        goto LABEL_39;
      }
      v17 = GetLastError();
      v18 = L"BfsRepair: Failed to load FMIFS.DLL %08x";
    }
    else
    {
      v17 = GetLastError();
      v18 = L"BfsRepair: Failed to get volume information %08x";
    }
    LODWORD(LastError) = v17;
    BfspLogMessage(4, v18, v17);
  }
  else
  {
    LODWORD(LastError) = GetLastError();
  }
LABEL_39:
  v26 = GetProcessHeap();
  HeapFree(v26, 0, v13);
  if ( v16 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v16);
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140009bdc  push    rbp
0x140009bde  push    rbx
0x140009bdf  push    rsi
0x140009be0  push    rdi
0x140009be1  push    r12
0x140009be3  push    r13
0x140009be5  push    r14
0x140009be7  push    r15
0x140009be9  lea     rbp, [rsp-248h]
0x140009bf1  sub     rsp, 348h
0x140009bf8  mov     rax, cs:__security_cookie
0x140009bff  xor     rax, rsp
0x140009c02  mov     [rbp+280h+var_50], rax
0x140009c09  xor     r13d, r13d
0x140009c0c  xorps   xmm0, xmm0
0x140009c0f  xor     eax, eax
0x140009c11  mov     [rsp+380h+Handle], r13
0x140009c16  mov     [rbp+280h+var_2F8], rax
0x140009c1a  mov     r14, rdx
0x140009c1d  mov     ebx, r13d
0x140009c20  movups  [rsp+380h+var_328], xmm0
0x140009c25  movups  [rsp+380h+var_318], xmm0
0x140009c2a  movups  [rsp+380h+var_308], xmm0
0x140009c2f  test    rdx, rdx
0x140009c32  jz      short loc_140009C37
0x140009c34  mov     [rdx], r13d
0x140009c37  mov     r15d, 90h
0x140009c3d  mov     [rsp+380h+BytesReturned], r13d
0x140009c42  mov     r8d, r15d; Size
0x140009c45  lea     rcx, [rbp+280h+OutBuffer]; void *
0x140009c49  xor     edx, edx; Val
0x140009c4b  call    memset_0
0x140009c50  mov     edx, 80000000h
0x140009c55  mov     [rsp+380h+hDevice], r13
0x140009c5a  lea     rcx, [rsp+380h+hDevice]
0x140009c5f  call    BfspOpenSystemPartition
0x140009c64  mov     rsi, [rsp+380h+hDevice]
0x140009c69  mov     edi, eax
0x140009c6b  test    eax, eax
0x140009c6d  jnz     short loc_140009CB5
0x140009c6f  mov     [rsp+380h+lpOverlapped], r13; lpOverlapped
0x140009c74  lea     rax, [rsp+380h+BytesReturned]
0x140009c79  mov     [rsp+380h+lpBytesReturned], rax; lpBytesReturned
0x140009c7e  xor     r9d, r9d; nInBufferSize
0x140009c81  lea     rax, [rbp+280h+OutBuffer]
0x140009c85  mov     [rsp+380h+nOutBufferSize], r15d; nOutBufferSize
0x140009c8a  xor     r8d, r8d; lpInBuffer
0x140009c8d  mov     [rsp+380h+lpOutBuffer], rax; lpOutBuffer
0x140009c92  mov     edx, 70048h; dwIoControlCode
0x140009c97  mov     rcx, rsi; hDevice
0x140009c9a  call    cs:__imp_DeviceIoControl
0x140009ca0  test    eax, eax
0x140009ca2  jnz     short loc_140009CAE
0x140009ca4  call    cs:__imp_GetLastError
0x140009caa  mov     edi, eax
0x140009cac  jmp     short loc_140009CB5
0x140009cae  mov     rbx, [rbp+280h+var_2E0]
0x140009cb2  mov     edi, r13d
0x140009cb5  lea     rax, [rsi-1]
0x140009cb9  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140009cbd  ja      short loc_140009CC8
0x140009cbf  mov     rcx, rsi; hObject
0x140009cc2  call    cs:__imp_CloseHandle
0x140009cc8  test    edi, edi
0x140009cca  jz      short loc_140009CDB
0x140009ccc  mov     r8d, edi
0x140009ccf  lea     rdx, aBfsrepairFaile_7; "BfsRepair: Failed to get system partiti"...
0x140009cd6  jmp     loc_140009F9E
0x140009cdb  cmp     rbx, 40000000h
0x140009ce2  jbe     short loc_140009D18
0x140009ce4  mov     rax, rbx
0x140009ce7  mov     r9d, 400h
0x140009ced  cqo
0x140009cef  mov     ecx, 4
0x140009cf4  and     edx, 0FFFFFh
0x140009cfa  lea     r8, [rdx+rax]
0x140009cfe  sar     r8, 14h
0x140009d02  lea     rdx, aBfsrepairSyste; "BfsRepair: System volume too large for "...
0x140009d09  call    BfspLogMessage
0x140009d0e  mov     edi, 32h ; '2'
0x140009d13  jmp     loc_140009FA8
0x140009d18  mov     cl, 1
0x140009d1a  call    BfspGetSystemPartition
0x140009d1f  mov     rsi, rax
0x140009d22  test    rax, rax
0x140009d25  jz      loc_140009F8C
0x140009d2b  or      rax, 0FFFFFFFFFFFFFFFFh
0x140009d2f  inc     rax
0x140009d32  cmp     [rsi+rax*2], r13w
0x140009d37  jnz     short loc_140009D2F
0x140009d39  lea     r12, [rax+2]
0x140009d3d  lea     rbx, [r12+r12]
0x140009d41  call    cs:__imp_GetProcessHeap
0x140009d47  mov     r8, rbx; dwBytes
0x140009d4a  mov     ebx, 8
0x140009d4f  mov     edx, ebx; dwFlags
0x140009d51  mov     rcx, rax; hHeap
0x140009d54  call    cs:__imp_HeapAlloc
0x140009d5a  mov     r15, rax
0x140009d5d  test    rax, rax
0x140009d60  jnz     short loc_140009D6C
0x140009d62  mov     ecx, ebx; dwErrCode
0x140009d64  call    cs:__imp_SetLastError
0x140009d6a  jmp     short loc_140009D8C
0x140009d6c  mov     r8, rsi; pszSrc
0x140009d6f  mov     rdx, r12; cchDest
0x140009d72  mov     rcx, r15; pszDest
0x140009d75  call    StringCchCopyW
0x140009d7a  lea     r8, pszSrc; "\\"
0x140009d81  mov     rdx, r12; cchDest
0x140009d84  mov     rcx, r15; pszDest
0x140009d87  call    StringCchCatW
0x140009d8c  call    cs:__imp_GetProcessHeap
0x140009d92  mov     r8, rsi; lpMem
0x140009d95  xor     edx, edx; dwFlags
0x140009d97  mov     rcx, rax; hHeap
0x140009d9a  call    cs:__imp_HeapFree
0x140009da0  test    r15, r15
0x140009da3  jz      loc_140009F8C
0x140009da9  xor     ecx, ecx
0x140009dab  call    BfspGetSystemPartition
0x140009db0  mov     rbx, rax
0x140009db3  test    rax, rax
0x140009db6  jnz     short loc_140009DC5
0x140009db8  call    cs:__imp_GetLastError
0x140009dbe  mov     edi, eax
0x140009dc0  jmp     loc_140009F5D
0x140009dc5  mov     r8, rbx
0x140009dc8  lea     rdx, aBfschkdskWs; "BfsChkDsk: %ws"
0x140009dcf  mov     ecx, 2
0x140009dd4  call    BfspLogMessage
0x140009dd9  mov     dword ptr [rsp+380h+lpOverlapped], 104h; nFileSystemNameSize
0x140009de1  lea     rax, [rbp+280h+FileSystemNameBuffer]
0x140009de5  mov     [rsp+380h+lpBytesReturned], rax; lpFileSystemNameBuffer
0x140009dea  xor     r9d, r9d; lpVolumeSerialNumber
0x140009ded  mov     qword ptr [rsp+380h+nOutBufferSize], r13; lpFileSystemFlags
0x140009df2  xor     r8d, r8d; nVolumeNameSize
0x140009df5  xor     edx, edx; lpVolumeNameBuffer
0x140009df7  mov     [rsp+380h+lpOutBuffer], r13; lpMaximumComponentLength
0x140009dfc  mov     rcx, r15; lpRootPathName
0x140009dff  call    cs:__imp_GetVolumeInformationW
0x140009e05  test    eax, eax
0x140009e07  jnz     short loc_140009E2A
0x140009e09  call    cs:__imp_GetLastError
0x140009e0f  lea     rdx, aBfsrepairFaile_2; "BfsRepair: Failed to get volume informa"...
0x140009e16  mov     r8d, eax
0x140009e19  mov     ecx, 4
0x140009e1e  mov     edi, eax
0x140009e20  call    BfspLogMessage
0x140009e25  jmp     loc_140009F5D
0x140009e2a  lea     rcx, aFmifsDll; "FMIFS.DLL"
0x140009e31  call    cs:__imp_LoadLibraryW
0x140009e37  mov     rsi, rax
0x140009e3a  test    rax, rax
0x140009e3d  jnz     short loc_140009E4E
0x140009e3f  call    cs:__imp_GetLastError
0x140009e45  lea     rdx, aBfsrepairFaile; "BfsRepair: Failed to load FMIFS.DLL %08"...
0x140009e4c  jmp     short loc_140009E16
0x140009e4e  lea     rdx, aChkdskex; "ChkdskEx"
0x140009e55  mov     rcx, rsi; hModule
0x140009e58  call    cs:__imp_GetProcAddress
0x140009e5e  mov     r12, rax
0x140009e61  test    rax, rax
0x140009e64  jnz     short loc_140009E87
0x140009e66  call    cs:__imp_GetLastError
0x140009e6c  mov     r8d, eax
0x140009e6f  lea     rdx, aBfsrepairFaile_1; "BfsRepair: Failed to get ChkdskEx proc "...
0x140009e76  lea     ecx, [r12+4]
0x140009e7b  mov     edi, eax
0x140009e7d  call    BfspLogMessage
0x140009e82  jmp     loc_140009F54
0x140009e87  xorps   xmm0, xmm0
0x140009e8a  lea     r9, [rsp+380h+Handle]
0x140009e8f  movups  [rsp+380h+var_328], xmm0
0x140009e94  xor     eax, eax
0x140009e96  mov     word ptr [rsp+380h+var_328], 201h
0x140009e9d  mov     [rbp+280h+var_2F8], rax
0x140009ea1  xor     edx, edx
0x140009ea3  lea     rax, aBfsvc; "BFSVC"
0x140009eaa  mov     byte ptr [rsp+380h+var_328+0Ah], r13b
0x140009eaf  movups  [rsp+380h+var_318], xmm0
0x140009eb4  xor     ecx, ecx
0x140009eb6  mov     qword ptr [rsp+380h+var_318], rax
0x140009ebb  movups  [rsp+380h+var_308], xmm0
0x140009ec0  mov     dword ptr [rsp+380h+var_328+4], 80280100h
0x140009ec8  call    BiOpenStoreWithHash
0x140009ecd  test    eax, eax
0x140009ecf  js      short loc_140009EE8
0x140009ed1  mov     rcx, [rsp+380h+Handle]; Handle
0x140009ed6  call    BcdForciblyUnloadStore
0x140009edb  test    eax, eax
0x140009edd  jns     short loc_140009EFC
0x140009edf  lea     rdx, aBfsrepairFaile_5; "BfsRepair: Failed to unload system stor"...
0x140009ee6  jmp     short loc_140009EEF
0x140009ee8  lea     rdx, aBfsrepairFaile_3; "BfsRepair: Failed to open system store."...
0x140009eef  mov     r8d, eax
0x140009ef2  mov     ecx, 4
0x140009ef7  call    BfspLogMessage
0x140009efc  lea     rax, BfspChkDiskCallback
0x140009f03  mov     cs:dword_14003F864, r13d
0x140009f0a  mov     [rsp+380h+lpOutBuffer], rax
0x140009f0f  lea     r9, [rsp+380h+var_328]
0x140009f14  mov     rax, r12
0x140009f17  mov     cs:dword_14003F860, r13d
0x140009f1e  mov     r8b, 1
0x140009f21  lea     rdx, [rbp+280h+FileSystemNameBuffer]
0x140009f25  mov     rcx, rbx
0x140009f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009f2d  cmp     cs:dword_14003F864, r13d
0x140009f34  jnz     short loc_140009F48
0x140009f36  call    cs:__imp_GetLastError
0x140009f3c  mov     edi, eax
0x140009f3e  mov     eax, 65Bh
0x140009f43  test    edi, edi
0x140009f45  cmovz   edi, eax
0x140009f48  test    r14, r14
0x140009f4b  jz      short loc_140009F54
0x140009f4d  mov     dword ptr [r14], 1
0x140009f54  mov     rcx, rsi; hLibModule
0x140009f57  call    cs:__imp_FreeLibrary
0x140009f5d  call    cs:__imp_GetProcessHeap
0x140009f63  mov     r8, r15; lpMem
0x140009f66  xor     edx, edx; dwFlags
0x140009f68  mov     rcx, rax; hHeap
0x140009f6b  call    cs:__imp_HeapFree
0x140009f71  test    rbx, rbx
0x140009f74  jz      short loc_140009FA8
0x140009f76  call    cs:__imp_GetProcessHeap
0x140009f7c  mov     r8, rbx; lpMem
0x140009f7f  xor     edx, edx; dwFlags
0x140009f81  mov     rcx, rax; hHeap
0x140009f84  call    cs:__imp_HeapFree
0x140009f8a  jmp     short loc_140009FA8
0x140009f8c  call    cs:__imp_GetLastError
0x140009f92  mov     edi, eax
0x140009f94  lea     rdx, aBfsrepairFaile_0; "BfsRepair: Failed to get system volume "...
0x140009f9b  mov     r8d, eax
0x140009f9e  mov     ecx, 4
0x140009fa3  call    BfspLogMessage
0x140009fa8  mov     eax, edi
0x140009faa  mov     rcx, [rbp+280h+var_50]
0x140009fb1  xor     rcx, rsp; StackCookie
0x140009fb4  call    __security_check_cookie
0x140009fb9  add     rsp, 348h
0x140009fc0  pop     r15
0x140009fc2  pop     r14
0x140009fc4  pop     r13
0x140009fc6  pop     r12
0x140009fc8  pop     rdi
0x140009fc9  pop     rsi
0x140009fca  pop     rbx
0x140009fcb  pop     rbp
0x140009fcc  retn
```
