# DeviceCastle::Library::Internal::DatabasePersistence::ReadProtectedFileData(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ushort const *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,_FILETIME *)

- ea: `0x1800503e0`
- end: `0x180050693`
- name: `?ReadProtectedFileData@DatabasePersistence@Internal@Library@DeviceCastle@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGAEAV56@PEAU_FILETIME@@@Z`
- size: `691`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18004ee7c`

## callees

- `0x180005840`
- `0x1800436c0`
- `0x180048060`
- `0x1800503e0`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050488`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800505df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180050488`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800505df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005055f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005055f`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1800504dd`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x1800504dd`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180050469`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180050469`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800504ad`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x1800504ad`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180050527`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180050527`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050664`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180050664`
- `CRYPT32!CryptUnprotectData` at `0x1800505d5`
- `CRYPT32!CryptUnprotectData` at `0x1800505d5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DeviceCastle::Library::Internal::DatabasePersistence::ReadProtectedFileData(
        __int64 *a1,
        const WCHAR *a2,
        _QWORD *a3,
        struct _FILETIME *a4)
{
  BYTE *pbData; // rbx
  char *FileW; // rax
  char *v9; // r15
  unsigned int v10; // esi
  signed int LastError; // eax
  signed int v12; // edi
  DWORD LowPart; // eax
  void *v14; // rax
  signed int v15; // eax
  __int64 cbData; // rcx
  BYTE *v17; // rax
  DWORD nNumberOfBytesToRead; // [rsp+40h] [rbp-49h] BYREF
  DATA_BLOB pDataOut; // [rsp+48h] [rbp-41h] BYREF
  void **v21; // [rsp+58h] [rbp-31h] BYREF
  BYTE *v22; // [rsp+60h] [rbp-29h]
  unsigned __int64 v23; // [rsp+68h] [rbp-21h]
  __int64 v24; // [rsp+70h] [rbp-19h]
  union _LARGE_INTEGER FileSize; // [rsp+78h] [rbp-11h] BYREF
  DATA_BLOB pOptionalEntropy; // [rsp+80h] [rbp-9h] BYREF
  DATA_BLOB pDataIn; // [rsp+90h] [rbp+7h] BYREF
  BYTE *v28; // [rsp+A0h] [rbp+17h]
  char *v29; // [rsp+A8h] [rbp+1Fh]

  v21 = &DeviceCastle::Library::Blob::`vftable';
  v22 = 0;
  v23 = 0;
  v24 = 0;
  pDataOut = 0;
  pOptionalEntropy = 0;
  pDataIn = 0;
  pbData = 0;
  v28 = 0;
  FileSize.QuadPart = 0;
  nNumberOfBytesToRead = 0;
  FileW = (char *)CreateFileW(a2, 0x80000000, 1u, 0, 3u, 0x80u, 0);
  v9 = FileW;
  v29 = FileW;
  v10 = -2147024362;
  if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 && GetFileSizeEx(FileW, &FileSize) )
  {
    LowPart = FileSize.LowPart;
    if ( FileSize.QuadPart > 0xFFFFFFFFuLL )
    {
      nNumberOfBytesToRead = -1;
      v12 = -2147024362;
      goto LABEL_12;
    }
    nNumberOfBytesToRead = FileSize.LowPart;
    if ( !a4 )
      goto LABEL_9;
    if ( GetFileTime(v9, a4, 0, 0) )
    {
      LowPart = nNumberOfBytesToRead;
LABEL_9:
      ((void (__fastcall *)(void ***, _QWORD))v21[9])(&v21, LowPart);
      v14 = (void *)((__int64 (__fastcall *)(void ***))v21[1])(&v21);
      if ( ReadFile(v9, v14, nNumberOfBytesToRead, &nNumberOfBytesToRead, 0) )
      {
        ((void (__fastcall *)(void ***, _QWORD))v21[11])(&v21, nNumberOfBytesToRead);
        v12 = 0;
        goto LABEL_12;
      }
    }
  }
  LastError = GetLastError();
  v12 = LastError;
  if ( LastError > 0 )
    v12 = (unsigned __int16)LastError | 0x80070000;
LABEL_12:
  if ( (unsigned __int64)(v9 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v9);
  if ( v12 < 0 )
  {
    v10 = v12;
  }
  else if ( v23 > 0xFFFFFFFF )
  {
    pDataIn.cbData = -1;
  }
  else
  {
    pDataIn.cbData = v23;
    pDataIn.pbData = v22;
    if ( (unsigned __int64)(2 * a1[2]) > 0xFFFFFFFF )
    {
      pOptionalEntropy.cbData = -1;
    }
    else
    {
      pOptionalEntropy.cbData = 2 * *((_DWORD *)a1 + 4);
      if ( (unsigned __int64)a1[3] > 7 )
        a1 = (__int64 *)*a1;
      pOptionalEntropy.pbData = (BYTE *)a1;
      if ( CryptUnprotectData(&pDataIn, 0, &pOptionalEntropy, 0, 0, 0, &pDataOut) )
      {
        pbData = pDataOut.pbData;
        v28 = pDataOut.pbData;
        if ( (pDataOut.cbData & 1) != 0 )
        {
          v10 = -2147467259;
        }
        else
        {
          std::wstring::resize(a3);
          if ( a3[3] > 7u )
            a3 = (_QWORD *)*a3;
          memcpy_0(a3, pDataOut.pbData, pDataOut.cbData);
          cbData = pDataOut.cbData;
          v17 = pDataOut.pbData;
          if ( pDataOut.cbData )
          {
            do
            {
              *v17++ = 0;
              --cbData;
            }
            while ( cbData );
          }
          v10 = 0;
        }
      }
      else
      {
        v15 = GetLastError();
        v10 = v15;
        if ( v15 > 0 )
          v10 = (unsigned __int16)v15 | 0x80070000;
      }
    }
  }
  if ( pbData )
    LocalFree(pbData);
  v21 = &DeviceCastle::Library::Blob::`vftable';
  DeviceCastle::Library::Blob::Clear((DeviceCastle::Library::Blob *)&v21);
  return v10;
}

```

## disassembly

```asm
0x1800503e0  push    rbp
0x1800503e2  push    rbx
0x1800503e3  push    rsi
0x1800503e4  push    rdi
0x1800503e5  push    r12
0x1800503e7  push    r14
0x1800503e9  push    r15
0x1800503eb  lea     rbp, [rsp-27h]
0x1800503f0  sub     rsp, 0B0h
0x1800503f7  mov     rdi, r9
0x1800503fa  mov     r14, r8
0x1800503fd  mov     rax, rdx
0x180050400  mov     r12, rcx
0x180050403  lea     rcx, ??_7Blob@Library@DeviceCastle@@6B@; const DeviceCastle::Library::Blob::`vftable'
0x18005040a  mov     [rbp+57h+var_88], rcx
0x18005040e  mov     [rbp+57h+var_80], 0
0x180050416  mov     [rbp+57h+var_78], 0
0x18005041e  mov     [rbp+57h+var_70], 0
0x180050426  xorps   xmm0, xmm0
0x180050429  movups  xmmword ptr [rbp+57h+pDataOut.cbData], xmm0
0x18005042d  xorps   xmm1, xmm1
0x180050430  movups  xmmword ptr [rbp+57h+pOptionalEntropy.cbData], xmm1
0x180050434  movups  xmmword ptr [rbp+57h+pDataIn.cbData], xmm0
0x180050438  xor     ebx, ebx
0x18005043a  mov     [rbp+57h+var_40], rbx
0x18005043e  mov     qword ptr [rbp+57h+FileSize], rbx
0x180050442  mov     [rbp+57h+nNumberOfBytesToRead], ebx
0x180050445  mov     [rsp+0E0h+hTemplateFile], rbx; hTemplateFile
0x18005044a  mov     [rsp+0E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180050452  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x18005045a  xor     r9d, r9d; lpSecurityAttributes
0x18005045d  mov     edx, 80000000h; dwDesiredAccess
0x180050462  lea     r8d, [rbx+1]; dwShareMode
0x180050466  mov     rcx, rax; lpFileName
0x180050469  call    cs:__imp_CreateFileW
0x18005046f  mov     r15, rax
0x180050472  mov     [rbp+57h+var_38], rax
0x180050476  lea     rcx, [rax+1]
0x18005047a  mov     esi, 80070216h
0x18005047f  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180050486  jnz     short loc_1800504A6
0x180050488  call    cs:__imp_GetLastError
0x18005048e  mov     edi, eax
0x180050490  test    eax, eax
0x180050492  jle     loc_180050552
0x180050498  movzx   edi, ax
0x18005049b  or      edi, 80070000h
0x1800504a1  jmp     loc_180050552
0x1800504a6  lea     rdx, [rbp+57h+FileSize]; lpFileSize
0x1800504aa  mov     rcx, r15; hFile
0x1800504ad  call    cs:__imp_GetFileSizeEx
0x1800504b3  test    eax, eax
0x1800504b5  jz      short loc_180050488
0x1800504b7  mov     rax, qword ptr [rbp+57h+FileSize]
0x1800504bb  mov     ecx, 0FFFFFFFFh
0x1800504c0  cmp     rax, rcx
0x1800504c3  ja      loc_18005054D
0x1800504c9  mov     [rbp+57h+nNumberOfBytesToRead], eax
0x1800504cc  test    rdi, rdi
0x1800504cf  jz      short loc_1800504EA
0x1800504d1  xor     r9d, r9d; lpLastWriteTime
0x1800504d4  xor     r8d, r8d; lpLastAccessTime
0x1800504d7  mov     rdx, rdi; lpCreationTime
0x1800504da  mov     rcx, r15; hFile
0x1800504dd  call    cs:__imp_GetFileTime
0x1800504e3  test    eax, eax
0x1800504e5  jz      short loc_180050488
0x1800504e7  mov     eax, [rbp+57h+nNumberOfBytesToRead]
0x1800504ea  mov     edx, eax
0x1800504ec  mov     rax, [rbp+57h+var_88]
0x1800504f0  lea     rcx, [rbp+57h+var_88]
0x1800504f4  mov     rax, [rax+48h]
0x1800504f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800504fd  mov     edi, [rbp+57h+nNumberOfBytesToRead]
0x180050500  mov     rax, [rbp+57h+var_88]
0x180050504  lea     rcx, [rbp+57h+var_88]
0x180050508  mov     rax, [rax+8]
0x18005050c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050511  mov     qword ptr [rsp+0E0h+dwCreationDisposition], 0; lpOverlapped
0x18005051a  lea     r9, [rbp+57h+nNumberOfBytesToRead]; lpNumberOfBytesRead
0x18005051e  mov     r8d, edi; nNumberOfBytesToRead
0x180050521  mov     rdx, rax; lpBuffer
0x180050524  mov     rcx, r15; hFile
0x180050527  call    cs:__imp_ReadFile
0x18005052d  test    eax, eax
0x18005052f  jz      loc_180050488
0x180050535  mov     edx, [rbp+57h+nNumberOfBytesToRead]
0x180050538  mov     rax, [rbp+57h+var_88]
0x18005053c  lea     rcx, [rbp+57h+var_88]
0x180050540  mov     rax, [rax+58h]
0x180050544  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050549  xor     edi, edi
0x18005054b  jmp     short loc_180050552
0x18005054d  mov     [rbp+57h+nNumberOfBytesToRead], ecx
0x180050550  mov     edi, esi
0x180050552  lea     rax, [r15-1]
0x180050556  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18005055a  ja      short loc_180050565
0x18005055c  mov     rcx, r15; hObject
0x18005055f  call    cs:__imp_CloseHandle
0x180050565  test    edi, edi
0x180050567  js      loc_18005065A
0x18005056d  mov     rax, [rbp+57h+var_78]
0x180050571  mov     ecx, 0FFFFFFFFh
0x180050576  cmp     rax, rcx
0x180050579  ja      loc_180050655
0x18005057f  mov     [rbp+57h+pDataIn.cbData], eax
0x180050582  mov     rax, [rbp+57h+var_80]
0x180050586  mov     [rbp+57h+pDataIn.pbData], rax
0x18005058a  mov     rax, [r12+10h]
0x18005058f  add     rax, rax
0x180050592  cmp     rax, rcx
0x180050595  ja      loc_180050650
0x18005059b  mov     [rbp+57h+pOptionalEntropy.cbData], eax
0x18005059e  cmp     qword ptr [r12+18h], 7
0x1800505a4  jbe     short loc_1800505AA
0x1800505a6  mov     r12, [r12]
0x1800505aa  mov     [rbp+57h+pOptionalEntropy.pbData], r12
0x1800505ae  lea     rax, [rbp+57h+pDataOut]
0x1800505b2  mov     [rsp+0E0h+hTemplateFile], rax; pDataOut
0x1800505b7  mov     [rsp+0E0h+dwFlagsAndAttributes], 0; dwFlags
0x1800505bf  mov     qword ptr [rsp+0E0h+dwCreationDisposition], 0; pPromptStruct
0x1800505c8  xor     r9d, r9d; pvReserved
0x1800505cb  lea     r8, [rbp+57h+pOptionalEntropy]; pOptionalEntropy
0x1800505cf  xor     edx, edx; ppszDataDescr
0x1800505d1  lea     rcx, [rbp+57h+pDataIn]; pDataIn
0x1800505d5  call    cs:__imp_CryptUnprotectData
0x1800505db  test    eax, eax
0x1800505dd  jnz     short loc_1800505F6
0x1800505df  call    cs:__imp_GetLastError
0x1800505e5  mov     esi, eax
0x1800505e7  test    eax, eax
0x1800505e9  jle     short loc_18005065C
0x1800505eb  movzx   esi, ax
0x1800505ee  or      esi, 80070000h
0x1800505f4  jmp     short loc_18005065C
0x1800505f6  mov     rbx, [rbp+57h+pDataOut.pbData]
0x1800505fa  mov     [rbp+57h+var_40], rbx
0x1800505fe  mov     eax, [rbp+57h+pDataOut.cbData]
0x180050601  test    al, 1
0x180050603  jz      short loc_18005060C
0x180050605  mov     esi, 80004005h
0x18005060a  jmp     short loc_18005065C
0x18005060c  mov     edx, [rbp+57h+pDataOut.cbData]
0x18005060f  shr     rdx, 1
0x180050612  mov     rcx, r14; Src
0x180050615  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x18005061a  cmp     qword ptr [r14+18h], 7
0x18005061f  jbe     short loc_180050624
0x180050621  mov     r14, [r14]
0x180050624  mov     r8d, [rbp+57h+pDataOut.cbData]; Size
0x180050628  mov     rdx, [rbp+57h+pDataOut.pbData]; Src
0x18005062c  mov     rcx, r14; void *
0x18005062f  call    memcpy_0
0x180050634  mov     ecx, [rbp+57h+pDataOut.cbData]
0x180050637  mov     rax, [rbp+57h+pDataOut.pbData]
0x18005063b  test    rcx, rcx
0x18005063e  jz      short loc_18005064C
0x180050640  mov     byte ptr [rax], 0
0x180050643  inc     rax
0x180050646  sub     rcx, 1
0x18005064a  jnz     short loc_180050640
0x18005064c  xor     esi, esi
0x18005064e  jmp     short loc_18005065C
0x180050650  mov     [rbp+57h+pOptionalEntropy.cbData], ecx
0x180050653  jmp     short loc_18005065C
0x180050655  mov     [rbp+57h+pDataIn.cbData], ecx
0x180050658  jmp     short loc_18005065C
0x18005065a  mov     esi, edi
0x18005065c  test    rbx, rbx
0x18005065f  jz      short loc_18005066B
0x180050661  mov     rcx, rbx; hMem
0x180050664  call    cs:__imp_LocalFree
0x18005066a  nop
0x18005066b  lea     rax, ??_7Blob@Library@DeviceCastle@@6B@; const DeviceCastle::Library::Blob::`vftable'
0x180050672  mov     [rbp+57h+var_88], rax
0x180050676  lea     rcx, [rbp+57h+var_88]; this
0x18005067a  call    ?Clear@Blob@Library@DeviceCastle@@UEAAXXZ; DeviceCastle::Library::Blob::Clear(void)
0x18005067f  mov     eax, esi
0x180050681  add     rsp, 0B0h
0x180050688  pop     r15
0x18005068a  pop     r14
0x18005068c  pop     r12
0x18005068e  pop     rdi
0x18005068f  pop     rsi
0x180050690  pop     rbx
0x180050691  pop     rbp
0x180050692  retn
```
