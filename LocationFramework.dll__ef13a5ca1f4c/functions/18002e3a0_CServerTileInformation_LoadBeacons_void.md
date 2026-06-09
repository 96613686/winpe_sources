# CServerTileInformation::LoadBeacons(void)

- ea: `0x18002e3a0`
- end: `0x18002e649`
- name: `?LoadBeacons@CServerTileInformation@@AEAAJXZ`
- size: `681`
- prototype: `__int64 __fastcall(CServerTileInformation *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18007a990`
- `0x1801247b0`

## callees

- `0x18002e3a0`
- `0x18003503c`
- `0x18009e2e4`
- `0x1800a98c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e3ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e40d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e3ea`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002e40d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e3c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002e3c0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e625`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002e625`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18002e4b2`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18002e4b2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002e48f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002e48f`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002e540`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18002e540`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002e517`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18002e517`

## pseudocode

```c
__int64 __fastcall CServerTileInformation::LoadBeacons(CServerTileInformation *this)
{
  const WCHAR *v2; // rcx
  __int64 v3; // rax
  int LastErrorAsHResult; // esi
  HANDLE v6; // rax
  DWORD LowPart; // eax
  HANDLE FileMappingW; // rax
  LPVOID v9; // rax
  _QWORD *v10; // r14
  _DWORD *v11; // rax
  void *v12; // rcx
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+40h] [rbp-48h] BYREF
  _LARGE_INTEGER FileSize; // [rsp+58h] [rbp-30h] BYREF

  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  v2 = (const WCHAR *)((char *)this + 304);
  v3 = -1;
  do
    ++v3;
  while ( v2[v3] );
  if ( !v3 )
  {
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
    return 2147942487LL;
  }
  FileSize.QuadPart = 0;
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
  SecurityAttributes.lpSecurityDescriptor = 0;
  v6 = CreateFileW(v2, 0xC0000000, 0, &SecurityAttributes, 3u, 0x80u, 0);
  *((_QWORD *)this + 30) = v6;
  if ( v6 == (HANDLE)-1LL )
  {
    LastErrorAsHResult = LocationHelper::GetLastErrorAsHResult();
    if ( LastErrorAsHResult < 0 )
      goto LABEL_26;
  }
  if ( GetFileSizeEx(*((HANDLE *)this + 30), &FileSize) )
  {
    FileSize.QuadPart /= 1024LL;
    LowPart = FileSize.LowPart;
    if ( FileSize.HighPart > 0 )
    {
      LastErrorAsHResult = -2147418113;
      goto LABEL_26;
    }
    *((_DWORD *)this + 64) = FileSize.LowPart;
    if ( !LowPart )
      *((_DWORD *)this + 64) = 1;
    FileMappingW = CreateFileMappingW(*((HANDLE *)this + 30), 0, 4u, 0, 0, 0);
    *((_QWORD *)this + 31) = FileMappingW;
    if ( FileMappingW )
    {
      v9 = MapViewOfFile(FileMappingW, 0xF001Fu, 0, 0, 0);
      v10 = (_QWORD *)((char *)this + 232);
      *((_QWORD *)this + 29) = v9;
      if ( v9 )
      {
        LastErrorAsHResult = 0;
        goto LABEL_15;
      }
      LastErrorAsHResult = LocationHelper::GetLastErrorAsHResult();
      if ( LastErrorAsHResult >= 0 )
      {
LABEL_15:
        if ( LastErrorAsHResult >= 0 )
        {
          v11 = (_DWORD *)*v10;
          if ( *(_DWORD *)*v10 == 300 )
          {
            *((_OWORD *)this + 4) = *(_OWORD *)(v11 + 1);
            *((_OWORD *)this + 5) = *(_OWORD *)(v11 + 5);
            *((_OWORD *)this + 6) = *(_OWORD *)(v11 + 9);
            *((_OWORD *)this + 7) = *(_OWORD *)(v11 + 13);
            *((_OWORD *)this + 8) = *(_OWORD *)(v11 + 17);
            *((_OWORD *)this + 9) = *(_OWORD *)(v11 + 21);
            *((_OWORD *)this + 10) = *(_OWORD *)(v11 + 25);
            *((_OWORD *)this + 11) = *(_OWORD *)(v11 + 29);
            *((_OWORD *)this + 12) = *(_OWORD *)(v11 + 33);
            *((_QWORD *)this + 26) = *(_QWORD *)(v11 + 37);
            goto LABEL_6;
          }
          LastErrorAsHResult = -2147023504;
        }
LABEL_26:
        CServerTileInformation::UnloadMappedFile(this);
        goto LABEL_6;
      }
    }
    else
    {
      LastErrorAsHResult = -2147467259;
      v10 = (_QWORD *)((char *)this + 232);
    }
    v12 = (void *)*((_QWORD *)this + 31);
    if ( v12 )
    {
      CloseHandle(v12);
      *((_QWORD *)this + 31) = 0;
    }
    goto LABEL_15;
  }
  LastErrorAsHResult = LocationHelper::GetLastErrorAsHResult();
  if ( LastErrorAsHResult < 0 )
    goto LABEL_26;
LABEL_6:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 264));
  return (unsigned int)LastErrorAsHResult;
}

```

## disassembly

```asm
0x18002e3a0  push    rbx
0x18002e3a2  push    rdi
0x18002e3a3  sub     rsp, 78h
0x18002e3a7  mov     rax, cs:__security_cookie
0x18002e3ae  xor     rax, rsp
0x18002e3b1  mov     [rsp+88h+var_28], rax
0x18002e3b6  mov     rbx, rcx
0x18002e3b9  add     rcx, 108h; lpCriticalSection
0x18002e3c0  call    cs:__imp_EnterCriticalSection
0x18002e3c6  lea     rcx, [rbx+130h]; lpFileName
0x18002e3cd  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18002e3d4  inc     rax
0x18002e3d7  cmp     word ptr [rcx+rax*2], 0
0x18002e3dc  jnz     short loc_18002E3D4
0x18002e3de  test    rax, rax
0x18002e3e1  jnz     short loc_18002E43E
0x18002e3e3  lea     rcx, [rbx+108h]; lpCriticalSection
0x18002e3ea  call    cs:__imp_LeaveCriticalSection
0x18002e3f0  mov     eax, 80070057h
0x18002e3f5  jmp     short loc_18002E42A
0x18002e3f7  call    ?GetLastErrorAsHResult@LocationHelper@@SAJXZ; LocationHelper::GetLastErrorAsHResult(void)
0x18002e3fc  mov     esi, eax
0x18002e3fe  test    eax, eax
0x18002e400  js      loc_18002E63C
0x18002e406  lea     rcx, [rbx+108h]; lpCriticalSection
0x18002e40d  call    cs:__imp_LeaveCriticalSection
0x18002e413  mov     r14, [rsp+88h+var_18]
0x18002e418  mov     eax, esi
0x18002e41a  mov     rsi, [rsp+88h+arg_10]
0x18002e422  mov     rbp, [rsp+88h+arg_8]
0x18002e42a  mov     rcx, [rsp+88h+var_28]
0x18002e42f  xor     rcx, rsp; StackCookie
0x18002e432  call    __security_check_cookie
0x18002e437  add     rsp, 78h
0x18002e43b  pop     rdi
0x18002e43c  pop     rbx
0x18002e43d  retn
0x18002e43e  mov     [rsp+88h+arg_8], rbp
0x18002e446  lea     r9, [rsp+88h+SecurityAttributes]; lpSecurityAttributes
0x18002e44b  xor     ebp, ebp
0x18002e44d  mov     [rsp+88h+arg_10], rsi
0x18002e455  mov     [rsp+88h+hTemplateFile], rbp; hTemplateFile
0x18002e45a  xor     r8d, r8d; dwShareMode
0x18002e45d  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18002e465  mov     edx, 0C0000000h; dwDesiredAccess
0x18002e46a  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x18002e472  mov     [rsp+88h+var_18], r14
0x18002e477  mov     qword ptr [rsp+88h+FileSize], rbp
0x18002e47c  mov     qword ptr [rsp+88h+SecurityAttributes.nLength], 18h
0x18002e485  mov     qword ptr [rsp+88h+SecurityAttributes.bInheritHandle], rbp
0x18002e48a  mov     [rsp+88h+SecurityAttributes.lpSecurityDescriptor], rbp
0x18002e48f  call    cs:__imp_CreateFileW
0x18002e495  mov     [rbx+0F0h], rax
0x18002e49c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002e4a0  jz      loc_18002E5E1
0x18002e4a6  mov     rcx, [rbx+0F0h]; hFile
0x18002e4ad  lea     rdx, [rsp+88h+FileSize]; lpFileSize
0x18002e4b2  call    cs:__imp_GetFileSizeEx
0x18002e4b8  test    eax, eax
0x18002e4ba  jz      loc_18002E3F7
0x18002e4c0  mov     rax, qword ptr [rsp+88h+FileSize]
0x18002e4c5  cqo
0x18002e4c7  and     edx, 3FFh
0x18002e4cd  add     rax, rdx
0x18002e4d0  sar     rax, 0Ah
0x18002e4d4  mov     rcx, rax
0x18002e4d7  mov     qword ptr [rsp+88h+FileSize], rax
0x18002e4dc  shr     rcx, 20h
0x18002e4e0  test    ecx, ecx
0x18002e4e2  jg      loc_18002E5F1
0x18002e4e8  mov     [rbx+100h], eax
0x18002e4ee  test    eax, eax
0x18002e4f0  jnz     short loc_18002E4FC
0x18002e4f2  mov     dword ptr [rbx+100h], 1
0x18002e4fc  mov     rcx, [rbx+0F0h]; hFile
0x18002e503  xor     r9d, r9d; dwMaximumSizeHigh
0x18002e506  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rbp; lpName
0x18002e50b  xor     edx, edx; lpFileMappingAttributes
0x18002e50d  mov     r8d, 4; flProtect
0x18002e513  mov     [rsp+88h+dwCreationDisposition], ebp; dwMaximumSizeLow
0x18002e517  call    cs:__imp_CreateFileMappingW
0x18002e51d  mov     [rbx+0F8h], rax
0x18002e524  test    rax, rax
0x18002e527  jz      loc_18002E5F8
0x18002e52d  xor     r9d, r9d; dwFileOffsetLow
0x18002e530  mov     qword ptr [rsp+88h+dwCreationDisposition], rbp; dwNumberOfBytesToMap
0x18002e535  xor     r8d, r8d; dwFileOffsetHigh
0x18002e538  mov     edx, 0F001Fh; dwDesiredAccess
0x18002e53d  mov     rcx, rax; hFileMappingObject
0x18002e540  call    cs:__imp_MapViewOfFile
0x18002e546  lea     r14, [rbx+0E8h]
0x18002e54d  mov     [r14], rax
0x18002e550  test    rax, rax
0x18002e553  jz      loc_18002E606
0x18002e559  mov     esi, ebp
0x18002e55b  test    esi, esi
0x18002e55d  js      loc_18002E63C
0x18002e563  mov     rax, [r14]
0x18002e566  cmp     dword ptr [rax], 12Ch
0x18002e56c  jnz     loc_18002E637
0x18002e572  movups  xmm0, xmmword ptr [rax+4]
0x18002e576  movups  xmmword ptr [rbx+40h], xmm0
0x18002e57a  movups  xmm1, xmmword ptr [rax+14h]
0x18002e57e  movups  xmmword ptr [rbx+50h], xmm1
0x18002e582  movups  xmm0, xmmword ptr [rax+24h]
0x18002e586  movups  xmmword ptr [rbx+60h], xmm0
0x18002e58a  movups  xmm1, xmmword ptr [rax+34h]
0x18002e58e  movups  xmmword ptr [rbx+70h], xmm1
0x18002e592  movups  xmm0, xmmword ptr [rax+44h]
0x18002e596  movups  xmmword ptr [rbx+80h], xmm0
0x18002e59d  movups  xmm1, xmmword ptr [rax+54h]
0x18002e5a1  movups  xmmword ptr [rbx+90h], xmm1
0x18002e5a8  movups  xmm0, xmmword ptr [rax+64h]
0x18002e5ac  movups  xmmword ptr [rbx+0A0h], xmm0
0x18002e5b3  movups  xmm1, xmmword ptr [rax+74h]
0x18002e5b7  movups  xmmword ptr [rbx+0B0h], xmm1
0x18002e5be  movups  xmm0, xmmword ptr [rax+84h]
0x18002e5c5  movups  xmmword ptr [rbx+0C0h], xmm0
0x18002e5cc  movsd   xmm1, qword ptr [rax+94h]
0x18002e5d4  movsd   qword ptr [rbx+0D0h], xmm1
0x18002e5dc  jmp     loc_18002E406
0x18002e5e1  call    ?GetLastErrorAsHResult@LocationHelper@@SAJXZ; LocationHelper::GetLastErrorAsHResult(void)
0x18002e5e6  mov     esi, eax
0x18002e5e8  test    eax, eax
0x18002e5ea  js      short loc_18002E63C
0x18002e5ec  jmp     loc_18002E4A6
0x18002e5f1  mov     esi, 8000FFFFh
0x18002e5f6  jmp     short loc_18002E63C
0x18002e5f8  mov     esi, 80004005h
0x18002e5fd  lea     r14, [rbx+0E8h]
0x18002e604  jmp     short loc_18002E615
0x18002e606  call    ?GetLastErrorAsHResult@LocationHelper@@SAJXZ; LocationHelper::GetLastErrorAsHResult(void)
0x18002e60b  mov     esi, eax
0x18002e60d  test    eax, eax
0x18002e60f  jns     loc_18002E55B
0x18002e615  mov     rcx, [rbx+0F8h]; hObject
0x18002e61c  test    rcx, rcx
0x18002e61f  jz      loc_18002E55B
0x18002e625  call    cs:__imp_CloseHandle
0x18002e62b  mov     [rbx+0F8h], rbp
0x18002e632  jmp     loc_18002E55B
0x18002e637  mov     esi, 80070570h
0x18002e63c  mov     rcx, rbx; this
0x18002e63f  call    ?UnloadMappedFile@CServerTileInformation@@AEAAXXZ; CServerTileInformation::UnloadMappedFile(void)
0x18002e644  jmp     loc_18002E406
```
