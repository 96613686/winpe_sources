# GetFilenameInAppDataStorageForCurrentApp(ushort *,uint,ushort const *,...)

- ea: `0x180003350`
- end: `0x180003704`
- name: `?GetFilenameInAppDataStorageForCurrentApp@@YAJPEAGIPEBGZZ`
- size: `948`
- prototype: `__int64(unsigned __int16 *, unsigned int, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003d734`
- `0x18005151c`

## callees

- `0x180003350`
- `0x180003710`
- `0x180010d80`
- `0x1800449f0`
- `0x180045380`
- `0x18004591c`
- `0x18004f2d4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180003597`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180003597`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000356e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000356e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000366f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003691`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000366f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003691`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036cd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800034c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800034c0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000351f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000351f`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800033f9`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800034eb`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800033f9`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800034eb`
- `ntdll!NtSetInformationFile` at `0x18000355d`
- `ntdll!NtSetInformationFile` at `0x18000355d`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800033a4`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x1800033a4`

## string_xrefs

- `0x1800034a7`: `%s\D3DSCache`

## pseudocode

```c
__int64 GetFilenameInAppDataStorageForCurrentApp(
        unsigned __int16 *a1,
        unsigned int a2,
        const unsigned __int16 *a3,
        ...)
{
  unsigned __int64 v3; // rbp
  HRESULT v5; // ebx
  __int64 result; // rax
  __int64 v7; // rax
  WCHAR *v8; // r8
  unsigned __int64 i; // r9
  unsigned __int64 v10; // r10
  unsigned int v11; // ebx
  __int64 v12; // rdi
  unsigned __int16 *v13; // rsi
  unsigned int v14; // ebp
  wchar_t *v15; // rcx
  size_t v16; // rdi
  int v17; // eax
  HANDLE FileW; // rax
  void *v19; // rbx
  __int64 v20; // rbx
  DWORD ModuleFileNameW; // esi
  unsigned __int16 *v22; // r15
  unsigned int v23; // ebp
  unsigned __int8 *v24; // rdx
  unsigned __int64 v25; // r9
  unsigned __int64 v26; // rcx
  __int64 v27; // rax
  unsigned __int64 v28; // r9
  unsigned __int64 v29; // r9
  DWORD LastError; // eax
  int v31; // edx
  int v32; // ecx
  PWSTR ppszPath; // [rsp+40h] [rbp-278h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+48h] [rbp-270h] BYREF
  WCHAR Filename[264]; // [rsp+60h] [rbp-258h] BYREF
  va_list Args; // [rsp+2D8h] [rbp+20h] BYREF

  va_start(Args, a3);
  v3 = a2;
  if ( !(unsigned __int8)IsSHGetKnownFolderPathPresent() )
    return (unsigned int)-2147467263;
  ppszPath = 0;
  v5 = SHGetKnownFolderPath(&FOLDERID_LocalAppData, 0, 0, &ppszPath);
  if ( v5 < 0 )
    return (unsigned int)v5;
  v5 = StringCchPrintfW(a1, v3, L"%s\\D3DSCache", ppszPath);
  CoTaskMemFree(ppszPath);
  if ( v5 < 0 )
    return (unsigned int)v5;
  if ( !CreateDirectoryW(a1, 0) && GetLastError() != 183 )
    return 2147500037LL;
  FileW = CreateFileW(a1, 0x10000000u, 1u, 0, 3u, 0x2000000u, 0);
  v19 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = GetLastError();
    if ( (Microsoft_Windows_Direct3DShaderCacheEnableBits & 0x40) != 0 )
      McTemplateU0qqq_EventWriteTransfer(v32, v31, LastError, 3, 0);
  }
  else
  {
    LODWORD(ppszPath) = 2;
    IoStatusBlock = 0;
    if ( NtSetInformationFile(FileW, &IoStatusBlock, &ppszPath, 4u, FileRenameInformation|0x40) < 0 )
      LogFileError(0, 3, 9);
    CloseHandle(v19);
  }
  v12 = -1;
  v20 = -1;
  do
    ++v20;
  while ( a1[v20] );
  ModuleFileNameW = GetModuleFileNameW(0, Filename, 0x104u);
  if ( ModuleFileNameW == 260 && GetLastError() == 122 )
    return 2147500037LL;
  v22 = &a1[v20];
  v23 = v3 - v20;
  v8 = Filename;
  v10 = 2 * ModuleFileNameW;
  _mm_lfence();
  for ( i = 0x12345678ABCDEF0LL; v10 > 4; i = qword_1800AD0A0[*v24 ^ (unsigned __int64)(unsigned __int8)v29]
                                            ^ (v29 >> 8) )
  {
    v24 = (unsigned __int8 *)v8 + 3;
    v10 -= 4LL;
    v25 = qword_1800AD0A0[*(unsigned __int8 *)v8 ^ (unsigned __int64)(unsigned __int8)i] ^ (i >> 8);
    v26 = *((unsigned __int8 *)v8 + 1) ^ (unsigned __int64)(unsigned __int8)v25;
    v27 = *((unsigned __int8 *)v8 + 2);
    v8 += 2;
    v28 = qword_1800AD0A0[v26] ^ (v25 >> 8);
    v29 = qword_1800AD0A0[v27 ^ (unsigned __int8)v28] ^ (v28 >> 8);
  }
  for ( ; v10; --v10 )
  {
    v7 = *(unsigned __int8 *)v8;
    v8 = (WCHAR *)((char *)v8 + 1);
    i = qword_1800AD0A0[v7 ^ (unsigned __int8)i] ^ (i >> 8);
  }
  result = StringCchPrintfW(&a1[v20], v23, L"\\%I64x\\", i);
  v11 = result;
  if ( (int)result >= 0 )
  {
    if ( !CreateDirectoryW(a1, 0) && GetLastError() != 183 )
      return 2147500037LL;
    if ( a3 )
    {
      do
        ++v12;
      while ( v22[v12] );
      v13 = &v22[v12];
      v14 = v23 - v12;
      if ( v14 )
      {
        if ( v14 > 0x7FFFFFFF )
        {
          v11 = -2147024809;
          *v13 = 0;
        }
        else
        {
          v15 = &v22[v12];
          v16 = v14 - 1LL;
          v17 = vsnwprintf(v15, v16, a3, Args);
          if ( v17 < 0 || v17 > v16 )
          {
            v13[v16] = 0;
            return (unsigned int)-2147024774;
          }
          else
          {
            v11 = 0;
            if ( v17 == v16 )
              v13[v16] = 0;
          }
        }
      }
      else
      {
        return (unsigned int)-2147024809;
      }
    }
    return v11;
  }
  return result;
}

```

## disassembly

```asm
0x180003350  mov     [rsp+Format], r8
0x180003355  mov     qword ptr [rsp+Args], r9
0x18000335a  push    rbx
0x18000335b  push    rbp
0x18000335c  push    r12
0x18000335e  push    r14
0x180003360  sub     rsp, 298h
0x180003367  mov     rax, cs:__security_cookie
0x18000336e  xor     rax, rsp
0x180003371  mov     [rsp+2B8h+var_48], rax
0x180003379  mov     ebp, edx
0x18000337b  mov     r14, rcx
0x18000337e  call    IsSHGetKnownFolderPathPresent
0x180003383  test    al, al
0x180003385  jz      loc_1800036AC
0x18000338b  xor     r12d, r12d
0x18000338e  lea     r9, [rsp+2B8h+ppszPath]; ppszPath
0x180003393  xor     r8d, r8d; hToken
0x180003396  mov     [rsp+2B8h+ppszPath], r12
0x18000339b  xor     edx, edx; dwFlags
0x18000339d  lea     rcx, FOLDERID_LocalAppData; rfid
0x1800033a4  call    cs:__imp_SHGetKnownFolderPath
0x1800033aa  mov     ebx, eax
0x1800033ac  test    eax, eax
0x1800033ae  jns     loc_1800034A2
0x1800033b4  mov     eax, ebx
0x1800033b6  jmp     loc_180003484
0x1800033bb  test    r10, r10
0x1800033be  jz      short loc_1800033DD
0x1800033c0  movzx   eax, byte ptr [r8]
0x1800033c4  lea     r8, [r8+1]
0x1800033c8  movzx   ecx, r9b
0x1800033cc  xor     rcx, rax
0x1800033cf  shr     r9, 8
0x1800033d3  xor     r9, [r11+rcx*8]
0x1800033d7  sub     r10, 1
0x1800033db  jnz     short loc_1800033C0
0x1800033dd  mov     edx, ebp; unsigned __int64
0x1800033df  lea     r8, aI64x; "\\%I64x\\"
0x1800033e6  mov     rcx, r15; unsigned __int16 *
0x1800033e9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800033ee  mov     ebx, eax
0x1800033f0  test    eax, eax
0x1800033f2  js      short loc_18000346C
0x1800033f4  xor     edx, edx; lpSecurityAttributes
0x1800033f6  mov     rcx, r14; lpPathName
0x1800033f9  call    cs:__imp_CreateDirectoryW
0x1800033ff  test    eax, eax
0x180003401  jz      loc_180003691
0x180003407  mov     r8, [rsp+2B8h+Format]; Format
0x18000340f  test    r8, r8
0x180003412  jz      short loc_18000346A
0x180003414  inc     rdi
0x180003417  cmp     [r15+rdi*2], r12w
0x18000341c  jnz     short loc_180003414
0x18000341e  lea     rsi, [r15+rdi*2]
0x180003422  lea     r9, [rsp+2B8h+Args]; Args
0x18000342a  sub     ebp, edi
0x18000342c  jz      loc_1800036EE
0x180003432  cmp     ebp, 7FFFFFFFh
0x180003438  ja      loc_1800036DD
0x18000343e  mov     edi, ebp
0x180003440  mov     rcx, rsi; Buffer
0x180003443  dec     rdi
0x180003446  mov     rdx, rdi; BufferCount
0x180003449  call    _vsnwprintf
0x18000344e  test    eax, eax
0x180003450  js      loc_180003682
0x180003456  cdqe
0x180003458  cmp     rax, rdi
0x18000345b  ja      loc_180003682
0x180003461  mov     ebx, r12d
0x180003464  jz      loc_1800036E4
0x18000346a  mov     eax, ebx
0x18000346c  mov     rdi, [rsp+2B8h+var_30]
0x180003474  mov     rsi, [rsp+2B8h+var_28]
0x18000347c  mov     r15, [rsp+2B8h+var_38]
0x180003484  mov     rcx, [rsp+2B8h+var_48]
0x18000348c  xor     rcx, rsp; StackCookie
0x18000348f  call    __security_check_cookie
0x180003494  add     rsp, 298h
0x18000349b  pop     r14
0x18000349d  pop     r12
0x18000349f  pop     rbp
0x1800034a0  pop     rbx
0x1800034a1  retn
0x1800034a2  mov     r9, [rsp+2B8h+ppszPath]
0x1800034a7  lea     r8, aSD3dscache; "%s\\D3DSCache"
0x1800034ae  mov     rdx, rbp; unsigned __int64
0x1800034b1  mov     rcx, r14; unsigned __int16 *
0x1800034b4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800034b9  mov     rcx, [rsp+2B8h+ppszPath]; pv
0x1800034be  mov     ebx, eax
0x1800034c0  call    cs:__imp_CoTaskMemFree
0x1800034c6  test    ebx, ebx
0x1800034c8  js      loc_1800033B4
0x1800034ce  mov     [rsp+2B8h+var_28], rsi
0x1800034d6  xor     edx, edx; lpSecurityAttributes
0x1800034d8  mov     [rsp+2B8h+var_30], rdi
0x1800034e0  mov     rcx, r14; lpPathName
0x1800034e3  mov     [rsp+2B8h+var_38], r15
0x1800034eb  call    cs:__imp_CreateDirectoryW
0x1800034f1  test    eax, eax
0x1800034f3  jz      loc_18000366F
0x1800034f9  mov     [rsp+2B8h+hTemplateFile], r12; hTemplateFile
0x1800034fe  xor     r9d, r9d; lpSecurityAttributes
0x180003501  mov     [rsp+2B8h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x180003509  mov     edx, 10000000h; dwDesiredAccess
0x18000350e  mov     r8d, 1; dwShareMode
0x180003514  mov     [rsp+2B8h+dwCreationDisposition], 3; dwCreationDisposition
0x18000351c  mov     rcx, r14; lpFileName
0x18000351f  call    cs:__imp_CreateFileW
0x180003525  mov     rbx, rax
0x180003528  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000352c  jz      loc_180003644
0x180003532  xorps   xmm0, xmm0
0x180003535  mov     dword ptr [rsp+2B8h+ppszPath], 2
0x18000353d  mov     r9d, 4; Length
0x180003543  mov     [rsp+2B8h+dwCreationDisposition], 4Ah ; 'J'; FileInformationClass
0x18000354b  lea     r8, [rsp+2B8h+ppszPath]; FileInformation
0x180003550  mov     rcx, rax; FileHandle
0x180003553  lea     rdx, [rsp+2B8h+IoStatusBlock]; IoStatusBlock
0x180003558  movups  xmmword ptr [rsp+2B8h+IoStatusBlock], xmm0
0x18000355d  call    cs:__imp_NtSetInformationFile
0x180003563  test    eax, eax
0x180003565  js      loc_1800036B6
0x18000356b  mov     rcx, rbx; hObject
0x18000356e  call    cs:__imp_CloseHandle
0x180003574  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000357b  mov     rbx, rdi
0x18000357e  xchg    ax, ax
0x180003580  inc     rbx
0x180003583  cmp     [r14+rbx*2], r12w
0x180003588  jnz     short loc_180003580
0x18000358a  mov     r8d, 104h; nSize
0x180003590  lea     rdx, [rsp+2B8h+Filename]; lpFilename
0x180003595  xor     ecx, ecx; hModule
0x180003597  call    cs:__imp_GetModuleFileNameW
0x18000359d  mov     esi, eax
0x18000359f  cmp     eax, 104h
0x1800035a4  jz      loc_1800036CD
0x1800035aa  lea     r15, [r14+rbx*2]
0x1800035ae  sub     ebp, ebx
0x1800035b0  lea     r8, [rsp+2B8h+Filename]
0x1800035b5  lea     r10d, [rsi+rsi]
0x1800035b9  lfence
0x1800035bc  lea     r11, qword_1800AD0A0
0x1800035c3  mov     r9, 12345678ABCDEF0h
0x1800035cd  cmp     r10, 4
0x1800035d1  jbe     loc_1800033BB
0x1800035d7  nop     word ptr [rax+rax+00000000h]
0x1800035e0  movzx   eax, byte ptr [r8]
0x1800035e4  lea     rdx, [r8+3]
0x1800035e8  movzx   ecx, r9b
0x1800035ec  sub     r10, 4
0x1800035f0  xor     rcx, rax
0x1800035f3  shr     r9, 8
0x1800035f7  movzx   eax, byte ptr [r8+1]
0x1800035fc  xor     r9, [r11+rcx*8]
0x180003600  movzx   ecx, r9b
0x180003604  xor     rcx, rax
0x180003607  shr     r9, 8
0x18000360b  movzx   eax, byte ptr [r8+2]
0x180003610  add     r8, 4
0x180003614  xor     r9, [r11+rcx*8]
0x180003618  movzx   ecx, r9b
0x18000361c  xor     rcx, rax
0x18000361f  shr     r9, 8
0x180003623  movzx   eax, byte ptr [rdx]
0x180003626  xor     r9, [r11+rcx*8]
0x18000362a  movzx   ecx, r9b
0x18000362e  xor     rcx, rax
0x180003631  shr     r9, 8
0x180003635  xor     r9, [r11+rcx*8]
0x180003639  cmp     r10, 4
0x18000363d  ja      short loc_1800035E0
0x18000363f  jmp     loc_1800033BB
0x180003644  call    cs:__imp_GetLastError
0x18000364a  test    byte ptr cs:Microsoft_Windows_Direct3DShaderCacheEnableBits, 40h
0x180003651  jz      loc_180003574
0x180003657  mov     r9d, 3
0x18000365d  mov     [rsp+2B8h+dwCreationDisposition], r12d
0x180003662  mov     r8d, eax
0x180003665  call    McTemplateU0qqq_EventWriteTransfer
0x18000366a  jmp     loc_180003574
0x18000366f  call    cs:__imp_GetLastError
0x180003675  cmp     eax, 0B7h
0x18000367a  jz      loc_1800034F9
0x180003680  jmp     short loc_1800036A2
0x180003682  mov     [rsi+rdi*2], r12w
0x180003687  mov     ebx, 8007007Ah
0x18000368c  jmp     loc_18000346A
0x180003691  call    cs:__imp_GetLastError
0x180003697  cmp     eax, 0B7h
0x18000369c  jz      loc_180003407
0x1800036a2  mov     eax, 80004005h
0x1800036a7  jmp     loc_18000346C
0x1800036ac  mov     ebx, 80004001h
0x1800036b1  jmp     loc_1800033B4
0x1800036b6  mov     edx, 3
0x1800036bb  xor     ecx, ecx
0x1800036bd  mov     r8d, 9
0x1800036c3  call    ?LogFileError@@YAJHW4SHADER_CACHE_FILE_TYPE@@W4SHADER_CACHE_FILE_OP@@@Z; LogFileError(int,SHADER_CACHE_FILE_TYPE,SHADER_CACHE_FILE_OP)
0x1800036c8  jmp     loc_18000356B
0x1800036cd  call    cs:__imp_GetLastError
0x1800036d3  cmp     eax, 7Ah ; 'z'
0x1800036d6  jz      short loc_1800036A2
0x1800036d8  jmp     loc_1800035AA
0x1800036dd  mov     ebx, 80070057h
0x1800036e2  jmp     short loc_1800036FB
0x1800036e4  mov     [rsi+rdi*2], r12w
0x1800036e9  jmp     loc_18000346A
0x1800036ee  mov     ebx, 80070057h
0x1800036f3  test    ebp, ebp
0x1800036f5  jz      loc_18000346A
0x1800036fb  mov     [rsi], r12w
0x1800036ff  jmp     loc_18000346A
```
