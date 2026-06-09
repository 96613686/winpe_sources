# RdVhd::Util::CVhdHelper::WaitAllVhdVolumesReady(void *)

- ea: `0x18004b29c`
- end: `0x18004b5f7`
- name: `?WaitAllVhdVolumesReady@CVhdHelper@Util@RdVhd@@IEBAJPEAX@Z`
- size: `859`
- prototype: `int(RdVhd::Util::CVhdHelper *__hidden this, void *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18004a578`
- `0x18004a7a4`

## callees

- `0x180004db0`
- `0x180019b38`
- `0x180031204`
- `0x180031448`
- `0x18003146c`
- `0x1800327c8`
- `0x1800488e4`
- `0x180048b28`
- `0x18004b29c`
- `0x18004b600`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b495`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b521`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b495`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004b521`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b56f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004b56f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004b2ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004b575`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004b2ea`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18004b575`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004b486`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004b486`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004b510`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18004b510`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x18004b3b9`
- `VirtDisk!GetVirtualDiskPhysicalPath` at `0x18004b3b9`

## string_xrefs

- `0x18004b5d3`: `Waiting for VHD volumes to be ready`

## pseudocode

```c
__int64 __fastcall RdVhd::Util::CVhdHelper::WaitAllVhdVolumesReady(RdVhd::Util::CVhdHelper *this, void *a2)
{
  DWORD TickCount; // r14d
  signed int v4; // ebx
  int v5; // eax
  RdVhd::Uvhd::CUvhdDiskManager *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r9
  WCHAR *Buffer; // rax
  signed int VirtualDiskPhysicalPath; // eax
  const WCHAR *v11; // rax
  HANDLE FileW; // rsi
  signed int LastError; // eax
  signed int v14; // eax
  DWORD v15; // eax
  unsigned int v16; // r10d
  void **v18; // [rsp+40h] [rbp-38h] BYREF
  int v19; // [rsp+48h] [rbp-30h]
  __int64 v20; // [rsp+4Ch] [rbp-2Ch]
  int v21; // [rsp+54h] [rbp-24h]
  __int64 v22; // [rsp+58h] [rbp-20h]
  int v23; // [rsp+60h] [rbp-18h]
  ULONG DiskPathSizeInBytes; // [rsp+B0h] [rbp+38h] BYREF
  int v25; // [rsp+B4h] [rbp+3Ch]

  v25 = HIDWORD(this);
  DiskPathSizeInBytes = 0;
  v18 = &CPathString::`vftable';
  v20 = 128;
  v22 = 0;
  v21 = 0;
  v23 = 0x8000000;
  v19 = 0;
  TickCount = GetTickCount();
  if ( !a2 )
  {
    if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 146, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids, L"hVhd");
    }
    v4 = -2147024809;
    goto LABEL_46;
  }
  v5 = CBaseStringT<unsigned short>::EnsureSpace(&v18, 260);
  v4 = v5;
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_46;
    }
    v7 = 147;
LABEL_12:
    v8 = (unsigned int)v5;
LABEL_13:
    WPP_SF_d(*((_QWORD *)v6 + 2), v7, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids, v8);
    goto LABEL_46;
  }
  DiskPathSizeInBytes = 2 * CBaseStringT<unsigned short>::GetBufferLength(&v18);
  Buffer = (WCHAR *)CBaseStringT<unsigned short>::GetBuffer(&v18);
  VirtualDiskPhysicalPath = GetVirtualDiskPhysicalPath(a2, &DiskPathSizeInBytes, Buffer);
  v4 = VirtualDiskPhysicalPath;
  if ( VirtualDiskPhysicalPath )
  {
    if ( VirtualDiskPhysicalPath > 0 )
      v4 = (unsigned __int16)VirtualDiskPhysicalPath | 0x80070000;
    if ( v4 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_46;
      }
      v7 = 148;
LABEL_22:
      v8 = (unsigned int)v4;
      goto LABEL_13;
    }
  }
  v5 = CBaseStringT<unsigned short>::SetLength(&v18, DiskPathSizeInBytes >> 1);
  v4 = v5;
  if ( v5 < 0 )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_46;
    }
    v7 = 149;
    goto LABEL_12;
  }
  v11 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v18);
  FileW = CreateFileW(v11, 0x80000000, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_46;
      }
      v7 = 150;
      goto LABEL_22;
    }
  }
  if ( !DeviceIoControl(FileW, 0x7421Cu, 0, 0, 0, 0, 0, 0) )
  {
    v14 = GetLastError();
    v4 = v14;
    if ( v14 > 0 )
      v4 = (unsigned __int16)v14 | 0x80070000;
    if ( v4 < 0
      && WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        151,
        WPP_cd119b7af839377e03a1eca67cd76764_Traceguids,
        (unsigned int)v4);
    }
  }
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
LABEL_46:
  v15 = GetTickCount();
  v16 = v15 - TickCount;
  if ( v15 < TickCount )
    v16 = v15 - TickCount - 1;
  if ( WPP_GLOBAL_Control != (RdVhd::Uvhd::CUvhdDiskManager *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_Sdd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      152,
      (unsigned int)WPP_cd119b7af839377e03a1eca67cd76764_Traceguids,
      (unsigned int)L"Waiting for VHD volumes to be ready",
      v16 / 0x3E8,
      v16 % 0x3E8);
  }
  CPathString::~CPathString((CPathString *)&v18);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18004b29c  mov     qword ptr [rsp-30h+DiskPathSizeInBytes], rcx
0x18004b2a1  push    rbp
0x18004b2a2  push    rbx
0x18004b2a3  push    rsi
0x18004b2a4  push    rdi
0x18004b2a5  push    r12
0x18004b2a7  push    r14
0x18004b2a9  mov     rbp, rsp
0x18004b2ac  sub     rsp, 78h
0x18004b2b0  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x18004b2b7  mov     [rbp+DiskPathSizeInBytes], 0
0x18004b2be  mov     [rbp+var_38], rax
0x18004b2c2  mov     rdi, rdx
0x18004b2c5  mov     [rbp+var_2C], 80h
0x18004b2cd  mov     [rbp+var_20], 0
0x18004b2d5  mov     [rbp+var_24], 0
0x18004b2dc  mov     [rbp+var_18], 8000000h
0x18004b2e3  mov     [rbp+var_30], 0
0x18004b2ea  call    cs:__imp_GetTickCount
0x18004b2f0  lea     r12, WPP_cd119b7af839377e03a1eca67cd76764_Traceguids
0x18004b2f7  mov     r14d, eax
0x18004b2fa  test    rdi, rdi
0x18004b2fd  jnz     short loc_18004B340
0x18004b2ff  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b306  lea     rdi, WPP_GLOBAL_Control
0x18004b30d  cmp     rcx, rdi
0x18004b310  jz      short loc_18004B336
0x18004b312  test    byte ptr [rcx+1Ch], 1
0x18004b316  jz      short loc_18004B336
0x18004b318  cmp     byte ptr [rcx+19h], 2
0x18004b31c  jb      short loc_18004B336
0x18004b31e  mov     rcx, [rcx+10h]
0x18004b322  lea     r9, aHvhd; "hVhd"
0x18004b329  mov     edx, 92h
0x18004b32e  mov     r8, r12
0x18004b331  call    WPP_SF_S
0x18004b336  mov     ebx, 80070057h
0x18004b33b  jmp     loc_18004B575
0x18004b340  mov     edx, 104h
0x18004b345  lea     rcx, [rbp+var_38]
0x18004b349  call    ?EnsureSpace@?$CBaseStringT@G@@IEAAJK@Z; CBaseStringT<ushort>::EnsureSpace(ulong)
0x18004b34e  mov     ebx, eax
0x18004b350  test    eax, eax
0x18004b352  jns     short loc_18004B398
0x18004b354  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b35b  lea     rdi, WPP_GLOBAL_Control
0x18004b362  cmp     rcx, rdi
0x18004b365  jz      loc_18004B575
0x18004b36b  test    byte ptr [rcx+1Ch], 4
0x18004b36f  jz      loc_18004B575
0x18004b375  cmp     byte ptr [rcx+19h], 2
0x18004b379  jb      loc_18004B575
0x18004b37f  mov     edx, 93h
0x18004b384  mov     r9d, eax
0x18004b387  mov     rcx, [rcx+10h]
0x18004b38b  mov     r8, r12
0x18004b38e  call    WPP_SF_d
0x18004b393  jmp     loc_18004B575
0x18004b398  lea     rcx, [rbp+var_38]
0x18004b39c  call    ?GetBufferLength@?$CBaseStringT@G@@QEBAKXZ; CBaseStringT<ushort>::GetBufferLength(void)
0x18004b3a1  add     eax, eax
0x18004b3a3  lea     rcx, [rbp+var_38]
0x18004b3a7  mov     [rbp+DiskPathSizeInBytes], eax
0x18004b3aa  call    ?GetBuffer@?$CBaseStringT@G@@QEAAPEAGK@Z; CBaseStringT<ushort>::GetBuffer(ulong)
0x18004b3af  mov     r8, rax; DiskPath
0x18004b3b2  lea     rdx, [rbp+DiskPathSizeInBytes]; DiskPathSizeInBytes
0x18004b3b6  mov     rcx, rdi; VirtualDiskHandle
0x18004b3b9  call    cs:__imp_GetVirtualDiskPhysicalPath
0x18004b3bf  mov     ebx, eax
0x18004b3c1  mov     edi, 80070000h
0x18004b3c6  test    eax, eax
0x18004b3c8  jz      short loc_18004B40D
0x18004b3ca  jle     short loc_18004B3D1
0x18004b3cc  movzx   ebx, ax
0x18004b3cf  or      ebx, edi
0x18004b3d1  test    ebx, ebx
0x18004b3d3  jns     short loc_18004B40D
0x18004b3d5  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b3dc  lea     rdi, WPP_GLOBAL_Control
0x18004b3e3  cmp     rcx, rdi
0x18004b3e6  jz      loc_18004B575
0x18004b3ec  test    byte ptr [rcx+1Ch], 4
0x18004b3f0  jz      loc_18004B575
0x18004b3f6  cmp     byte ptr [rcx+19h], 2
0x18004b3fa  jb      loc_18004B575
0x18004b400  mov     edx, 94h
0x18004b405  mov     r9d, ebx
0x18004b408  jmp     loc_18004B387
0x18004b40d  mov     edx, [rbp+DiskPathSizeInBytes]
0x18004b410  lea     rcx, [rbp+var_38]
0x18004b414  shr     edx, 1
0x18004b416  call    ?SetLength@?$CBaseStringT@G@@QEAAJK@Z; CBaseStringT<ushort>::SetLength(ulong)
0x18004b41b  mov     ebx, eax
0x18004b41d  test    eax, eax
0x18004b41f  jns     short loc_18004B456
0x18004b421  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b428  lea     rdi, WPP_GLOBAL_Control
0x18004b42f  cmp     rcx, rdi
0x18004b432  jz      loc_18004B575
0x18004b438  test    byte ptr [rcx+1Ch], 4
0x18004b43c  jz      loc_18004B575
0x18004b442  cmp     byte ptr [rcx+19h], 2
0x18004b446  jb      loc_18004B575
0x18004b44c  mov     edx, 95h
0x18004b451  jmp     loc_18004B384
0x18004b456  lea     rcx, [rbp+var_38]
0x18004b45a  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18004b45f  mov     r8d, 3; dwShareMode
0x18004b465  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18004b46e  mov     rcx, rax; lpFileName
0x18004b471  mov     [rsp+78h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18004b479  xor     r9d, r9d; lpSecurityAttributes
0x18004b47c  mov     [rsp+78h+dwCreationDisposition], r8d; dwCreationDisposition
0x18004b481  mov     edx, 80000000h; dwDesiredAccess
0x18004b486  call    cs:__imp_CreateFileW
0x18004b48c  mov     rsi, rax
0x18004b48f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004b493  jnz     short loc_18004B4DF
0x18004b495  call    cs:__imp_GetLastError
0x18004b49b  mov     ebx, eax
0x18004b49d  test    eax, eax
0x18004b49f  jle     short loc_18004B4A6
0x18004b4a1  movzx   ebx, ax
0x18004b4a4  or      ebx, edi
0x18004b4a6  test    ebx, ebx
0x18004b4a8  jns     short loc_18004B4DF
0x18004b4aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b4b1  lea     rdi, WPP_GLOBAL_Control
0x18004b4b8  cmp     rcx, rdi
0x18004b4bb  jz      loc_18004B575
0x18004b4c1  test    byte ptr [rcx+1Ch], 4
0x18004b4c5  jz      loc_18004B575
0x18004b4cb  cmp     byte ptr [rcx+19h], 2
0x18004b4cf  jb      loc_18004B575
0x18004b4d5  mov     edx, 96h
0x18004b4da  jmp     loc_18004B405
0x18004b4df  mov     [rsp+78h+lpOverlapped], 0; lpOverlapped
0x18004b4e8  xor     r9d, r9d; nInBufferSize
0x18004b4eb  mov     [rsp+78h+hTemplateFile], 0; lpBytesReturned
0x18004b4f4  xor     r8d, r8d; lpInBuffer
0x18004b4f7  mov     [rsp+78h+dwFlagsAndAttributes], 0; nOutBufferSize
0x18004b4ff  mov     edx, 7421Ch; dwIoControlCode
0x18004b504  mov     rcx, rsi; hDevice
0x18004b507  mov     qword ptr [rsp+78h+dwCreationDisposition], 0; lpOutBuffer
0x18004b510  call    cs:__imp_DeviceIoControl
0x18004b516  lea     rdi, WPP_GLOBAL_Control
0x18004b51d  test    eax, eax
0x18004b51f  jnz     short loc_18004B566
0x18004b521  call    cs:__imp_GetLastError
0x18004b527  mov     ebx, eax
0x18004b529  test    eax, eax
0x18004b52b  jle     short loc_18004B536
0x18004b52d  movzx   ebx, ax
0x18004b530  or      ebx, 80070000h
0x18004b536  test    ebx, ebx
0x18004b538  jns     short loc_18004B566
0x18004b53a  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b541  cmp     rcx, rdi
0x18004b544  jz      short loc_18004B566
0x18004b546  test    byte ptr [rcx+1Ch], 1
0x18004b54a  jz      short loc_18004B566
0x18004b54c  cmp     byte ptr [rcx+19h], 2
0x18004b550  jb      short loc_18004B566
0x18004b552  mov     rcx, [rcx+10h]
0x18004b556  mov     edx, 97h
0x18004b55b  mov     r9d, ebx
0x18004b55e  mov     r8, r12
0x18004b561  call    WPP_SF_d
0x18004b566  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18004b56a  jz      short loc_18004B575
0x18004b56c  mov     rcx, rsi; hObject
0x18004b56f  call    cs:__imp_CloseHandle
0x18004b575  call    cs:__imp_GetTickCount
0x18004b57b  mov     r10d, eax
0x18004b57e  sub     r10d, r14d
0x18004b581  cmp     eax, r14d
0x18004b584  lea     ecx, [r10-1]
0x18004b588  cmovb   r10d, ecx
0x18004b58c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004b593  cmp     rcx, rdi
0x18004b596  jz      short loc_18004B5DF
0x18004b598  test    byte ptr [rcx+1Ch], 1
0x18004b59c  jz      short loc_18004B5DF
0x18004b59e  cmp     byte ptr [rcx+19h], 4
0x18004b5a2  jb      short loc_18004B5DF
0x18004b5a4  mov     rcx, [rcx+10h]
0x18004b5a8  mov     eax, 10624DD3h
0x18004b5ad  mul     r10d
0x18004b5b0  mov     r8, r12
0x18004b5b3  mov     r9d, edx
0x18004b5b6  mov     edx, 98h
0x18004b5bb  shr     r9d, 6
0x18004b5bf  imul    eax, r9d, 3E8h
0x18004b5c6  sub     r10d, eax
0x18004b5c9  mov     [rsp+78h+dwFlagsAndAttributes], r10d
0x18004b5ce  mov     [rsp+78h+dwCreationDisposition], r9d
0x18004b5d3  lea     r9, aWaitingForVhdV; "Waiting for VHD volumes to be ready"
0x18004b5da  call    WPP_SF_Sdd
0x18004b5df  lea     rcx, [rbp+var_38]; this
0x18004b5e3  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x18004b5e8  mov     eax, ebx
0x18004b5ea  add     rsp, 78h
0x18004b5ee  pop     r14
0x18004b5f0  pop     r12
0x18004b5f2  pop     rdi
0x18004b5f3  pop     rsi
0x18004b5f4  pop     rbx
0x18004b5f5  pop     rbp
0x18004b5f6  retn
```
