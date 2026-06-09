# OpenFontFile

- ea: `0x18016069c`
- end: `0x180160999`
- name: `OpenFontFile`
- size: `765`
- prototype: `__int64 __fastcall(HANDLE hPrinter, HANDLE hHeap, wchar_t *String1)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1801201d4`
- `0x180120c5c`
- `0x180120f44`
- `0x1801210d0`

## callees

- `0x1800032e0`
- `0x18000be0c`
- `0x180120e58`
- `0x18015fb54`
- `0x18016069c`
- `0x1801adb1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18016077e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1801607ea`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18016077e`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1801607ea`
- `KERNEL32!CreateFileMappingW` at `0x180160873`
- `KERNEL32!CreateFileMappingW` at `0x180160873`
- `KERNEL32!MapViewOfFile` at `0x180160893`
- `KERNEL32!MapViewOfFile` at `0x180160893`
- `KERNEL32!GetFileSize` at `0x18016084e`
- `KERNEL32!GetFileSize` at `0x18016084e`
- `KERNEL32!HeapAlloc` at `0x1801606eb`
- `KERNEL32!HeapAlloc` at `0x1801606eb`
- `KERNEL32!CreateFileW` at `0x180160834`
- `KERNEL32!CreateFileW` at `0x180160834`
- `KERNEL32!CloseHandle` at `0x1801608a3`
- `KERNEL32!CloseHandle` at `0x1801608b5`
- `KERNEL32!CloseHandle` at `0x1801608e0`
- `KERNEL32!CloseHandle` at `0x1801608a3`
- `KERNEL32!CloseHandle` at `0x1801608b5`
- `KERNEL32!CloseHandle` at `0x1801608e0`
- `WINSPOOL!GetPrinterDataW` at `0x1801607cb`
- `WINSPOOL!GetPrinterDataW` at `0x1801607cb`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x180160768`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x180160768`

## pseudocode

```c
_QWORD *__fastcall OpenFontFile(HANDLE hPrinter, HANDLE hHeap, wchar_t *String1)
{
  _QWORD *result; // rax
  __int64 v7; // rbx
  wchar_t *v8; // rax
  DWORD PrinterDataW; // eax
  wchar_t *v10; // rax
  BYTE *v11; // rax
  HANDLE FileW; // rax
  __int64 v13; // rdi
  HANDLE FileMappingW; // rax
  void *v15; // rsi
  __int64 v16; // rax
  _DWORD *v17; // rcx
  __int64 v18; // r8
  unsigned __int64 v19; // rdx
  DWORD pcbNeeded; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pType[3]; // [rsp+44h] [rbp-BCh] BYREF
  wchar_t pData[264]; // [rsp+50h] [rbp-B0h] BYREF

  pcbNeeded = 0;
  pType[0] = 0;
  result = HeapAlloc(hHeap, 8u, 0x258u);
  v7 = (__int64)result;
  if ( result )
  {
    *(_DWORD *)result = 1718514793;
    result[1] = hPrinter;
    result[2] = hHeap;
    result[72] = 0;
    *((_DWORD *)result + 143) = 0;
    if ( !wcscmp_0(String1, L"ExtFontCartFile") && !(unsigned int)BGetFontCartridgeFile(hPrinter, hHeap) )
      goto LABEL_29;
    pcbNeeded = 520;
    if ( !GetPrinterDriverDirectoryW(0, 0, 1u, (LPBYTE)(v7 + 24), 0x208u, &pcbNeeded) )
      goto LABEL_29;
    v8 = wcsrchr((const wchar_t *)(v7 + 24), 0x5Cu);
    if ( v8 )
      *v8 = 0;
    StringCchCatW((unsigned __int16 *)(v7 + 24), 0x104u, L"\\unifont\\");
    pcbNeeded = 520;
    PrinterDataW = GetPrinterDataW(hPrinter, String1, pType, (LPBYTE)pData, 0x208u, &pcbNeeded);
    if ( PrinterDataW != 234 )
    {
      if ( PrinterDataW )
        goto LABEL_29;
    }
    v10 = wcsrchr(pData, 0x5Cu);
    if ( v10 )
      v11 = (BYTE *)(v10 + 1);
    else
      v11 = (BYTE *)pData;
    StringCchCatW((unsigned __int16 *)(v7 + 24), 0x104u, (const unsigned __int16 *)v11);
    FileW = CreateFileW((LPCWSTR)(v7 + 24), 0x80000000, 1u, 0, 3u, 0x100080u, 0);
    v13 = (__int64)FileW;
    if ( FileW != (HANDLE)-1LL )
    {
      pcbNeeded = GetFileSize(FileW, 0);
      if ( pcbNeeded != -1 )
      {
        FileMappingW = CreateFileMappingW((HANDLE)v13, 0, 2u, 0, 0, 0);
        v15 = FileMappingW;
        if ( FileMappingW )
        {
          *(_QWORD *)(v7 + 576) = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
          CloseHandle(v15);
          if ( *(_QWORD *)(v7 + 576) )
          {
LABEL_18:
            v16 = *(_QWORD *)(v7 + 576);
            *(_QWORD *)(v7 + 544) = v16;
            if ( v16 )
            {
              CloseHandle((HANDLE)v13);
              v17 = *(_DWORD **)(v7 + 576);
              *(_QWORD *)(v7 + 552) = v17;
              if ( pcbNeeded >= 0x30 && *v17 == 826689109 && v17[1] == 65537 && v17[2] == 48 )
              {
                v18 = (unsigned int)v17[6];
                if ( !(_DWORD)v18 )
                {
LABEL_28:
                  *(_DWORD *)(v7 + 568) = 0;
                  *(_DWORD *)(v7 + 572) = 1;
                  *(_QWORD *)(v7 + 584) = 0;
                  *(_DWORD *)(v7 + 592) = 0;
                  return (_QWORD *)v7;
                }
                v19 = 36LL * (unsigned int)v17[3];
                if ( v19 <= 0xFFFFFFFF && (int)v19 + (int)v18 >= (unsigned int)v19 && pcbNeeded >= (int)v19 + (int)v18 )
                {
                  *(_QWORD *)(v7 + 560) = (char *)v17 + v18;
                  goto LABEL_28;
                }
              }
            }
LABEL_29:
            FICloseFontFile((LPVOID)v7);
            return 0;
          }
        }
      }
      CloseHandle((HANDLE)v13);
      v13 = -1;
    }
    *(_QWORD *)(v7 + 576) = 0;
    goto LABEL_18;
  }
  return result;
}

```

## disassembly

```asm
0x18016069c  mov     [rsp-8+arg_18], rbx
0x1801606a1  push    rbp
0x1801606a2  push    rsi
0x1801606a3  push    rdi
0x1801606a4  push    r14
0x1801606a6  push    r15
0x1801606a8  lea     rbp, [rsp-170h]
0x1801606b0  sub     rsp, 270h
0x1801606b7  mov     rax, cs:__security_cookie
0x1801606be  xor     rax, rsp
0x1801606c1  mov     [rbp+190h+var_30], rax
0x1801606c8  xor     r15d, r15d
0x1801606cb  mov     rdi, rdx
0x1801606ce  mov     r14, r8
0x1801606d1  mov     [rsp+290h+var_250], r15d
0x1801606d6  mov     rsi, rcx
0x1801606d9  mov     [rsp+290h+pType], r15d
0x1801606de  mov     r8d, 258h; dwBytes
0x1801606e4  mov     rcx, rdi; hHeap
0x1801606e7  lea     edx, [r15+8]; dwFlags
0x1801606eb  call    cs:__imp_HeapAlloc
0x1801606f1  mov     rbx, rax
0x1801606f4  test    rax, rax
0x1801606f7  jz      loc_180160973
0x1801606fd  lea     rdx, aExtfontcartfil; "ExtFontCartFile"
0x180160704  mov     dword ptr [rax], 666E7469h
0x18016070a  mov     rcx, r14; String1
0x18016070d  mov     [rax+8], rsi
0x180160711  mov     [rax+10h], rdi
0x180160715  mov     [rax+240h], r15
0x18016071c  mov     [rax+23Ch], r15d
0x180160723  call    wcscmp_0
0x180160728  test    eax, eax
0x18016072a  jnz     short loc_18016073F
0x18016072c  mov     rdx, rdi; hHeap
0x18016072f  mov     rcx, rsi; hPrinter
0x180160732  call    BGetFontCartridgeFile
0x180160737  test    eax, eax
0x180160739  jz      loc_180160965
0x18016073f  xor     edx, edx; pEnvironment
0x180160741  mov     [rsp+290h+var_250], 208h
0x180160749  lea     rax, [rsp+290h+var_250]
0x18016074e  xor     ecx, ecx; pName
0x180160750  mov     [rsp+290h+pcbNeeded], rax; pcbNeeded
0x180160755  lea     rdi, [rbx+18h]
0x180160759  mov     r9, rdi; pDriverDirectory
0x18016075c  mov     [rsp+290h+cbBuf], 208h; cbBuf
0x180160764  lea     r8d, [rdx+1]; Level
0x180160768  call    cs:__imp_GetPrinterDriverDirectoryW
0x18016076e  test    eax, eax
0x180160770  jz      loc_180160965
0x180160776  mov     edx, 5Ch ; '\'; Ch
0x18016077b  mov     rcx, rdi; Str
0x18016077e  call    cs:__imp_wcsrchr
0x180160784  test    rax, rax
0x180160787  jz      short loc_18016078D
0x180160789  mov     [rax], r15w
0x18016078d  lea     r8, aUnifont; "\\unifont\\"
0x180160794  mov     edx, 104h; unsigned __int64
0x180160799  mov     rcx, rdi; unsigned __int16 *
0x18016079c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1801607a1  lea     rax, [rsp+290h+var_250]
0x1801607a6  mov     [rsp+290h+var_250], 208h
0x1801607ae  mov     [rsp+290h+pcbNeeded], rax; pcbNeeded
0x1801607b3  lea     r9, [rsp+290h+pData]; pData
0x1801607b8  lea     r8, [rsp+290h+pType]; pType
0x1801607bd  mov     [rsp+290h+cbBuf], 208h; nSize
0x1801607c5  mov     rdx, r14; pValueName
0x1801607c8  mov     rcx, rsi; hPrinter
0x1801607cb  call    cs:__imp_GetPrinterDataW
0x1801607d1  cmp     eax, 0EAh
0x1801607d6  jz      short loc_1801607E0
0x1801607d8  test    eax, eax
0x1801607da  jnz     loc_180160965
0x1801607e0  mov     edx, 5Ch ; '\'; Ch
0x1801607e5  lea     rcx, [rsp+290h+pData]; Str
0x1801607ea  call    cs:__imp_wcsrchr
0x1801607f0  test    rax, rax
0x1801607f3  jz      short loc_1801607FB
0x1801607f5  add     rax, 2
0x1801607f9  jmp     short loc_180160800
0x1801607fb  lea     rax, [rsp+290h+pData]
0x180160800  mov     r8, rax; unsigned __int16 *
0x180160803  mov     edx, 104h; unsigned __int64
0x180160808  mov     rcx, rdi; unsigned __int16 *
0x18016080b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180160810  xor     r9d, r9d; lpSecurityAttributes
0x180160813  mov     [rsp+290h+hTemplateFile], r15; hTemplateFile
0x180160818  mov     dword ptr [rsp+290h+pcbNeeded], 100080h; dwFlagsAndAttributes
0x180160820  mov     edx, 80000000h; dwDesiredAccess
0x180160825  mov     rcx, rdi; lpFileName
0x180160828  mov     [rsp+290h+cbBuf], 3; dwCreationDisposition
0x180160830  lea     r8d, [r9+1]; dwShareMode
0x180160834  call    cs:__imp_CreateFileW
0x18016083a  mov     rdi, rax
0x18016083d  mov     r14d, 0FFFFFFFFh
0x180160843  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180160847  jz      short loc_1801608BF
0x180160849  xor     edx, edx; lpFileSizeHigh
0x18016084b  mov     rcx, rax; hFile
0x18016084e  call    cs:__imp_GetFileSize
0x180160854  mov     [rsp+290h+var_250], eax
0x180160858  cmp     eax, r14d
0x18016085b  jz      short loc_1801608B2
0x18016085d  xor     r9d, r9d; dwMaximumSizeHigh
0x180160860  mov     [rsp+290h+pcbNeeded], r15; lpName
0x180160865  xor     edx, edx; lpFileMappingAttributes
0x180160867  mov     [rsp+290h+cbBuf], r15d; dwMaximumSizeLow
0x18016086c  mov     rcx, rdi; hFile
0x18016086f  lea     r8d, [r9+2]; flProtect
0x180160873  call    cs:__imp_CreateFileMappingW
0x180160879  mov     rsi, rax
0x18016087c  test    rax, rax
0x18016087f  jz      short loc_1801608B2
0x180160881  xor     r9d, r9d; dwFileOffsetLow
0x180160884  mov     qword ptr [rsp+290h+cbBuf], r15; dwNumberOfBytesToMap
0x180160889  xor     r8d, r8d; dwFileOffsetHigh
0x18016088c  mov     rcx, rax; hFileMappingObject
0x18016088f  lea     edx, [r9+4]; dwDesiredAccess
0x180160893  call    cs:__imp_MapViewOfFile
0x180160899  mov     rcx, rsi; hObject
0x18016089c  mov     [rbx+240h], rax
0x1801608a3  call    cs:__imp_CloseHandle
0x1801608a9  cmp     [rbx+240h], r15
0x1801608b0  jnz     short loc_1801608C6
0x1801608b2  mov     rcx, rdi; hObject
0x1801608b5  call    cs:__imp_CloseHandle
0x1801608bb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1801608bf  mov     [rbx+240h], r15
0x1801608c6  mov     rax, [rbx+240h]
0x1801608cd  mov     [rbx+220h], rax
0x1801608d4  test    rax, rax
0x1801608d7  jz      loc_180160965
0x1801608dd  mov     rcx, rdi; hObject
0x1801608e0  call    cs:__imp_CloseHandle
0x1801608e6  mov     rcx, [rbx+240h]
0x1801608ed  mov     [rbx+228h], rcx
0x1801608f4  cmp     [rsp+290h+var_250], 30h ; '0'
0x1801608f9  jb      short loc_180160965
0x1801608fb  cmp     dword ptr [rcx], 31464655h
0x180160901  jnz     short loc_180160965
0x180160903  cmp     dword ptr [rcx+4], 10001h
0x18016090a  jnz     short loc_180160965
0x18016090c  cmp     dword ptr [rcx+8], 30h ; '0'
0x180160910  jnz     short loc_180160965
0x180160912  mov     r8d, [rcx+18h]
0x180160916  test    r8d, r8d
0x180160919  jz      short loc_180160944
0x18016091b  mov     eax, [rcx+0Ch]
0x18016091e  lea     rdx, [rax+rax*8]
0x180160922  shl     rdx, 2
0x180160926  cmp     rdx, r14
0x180160929  ja      short loc_180160965
0x18016092b  lea     eax, [rdx+r8]
0x18016092f  cmp     eax, edx
0x180160931  jb      short loc_180160965
0x180160933  cmp     [rsp+290h+var_250], eax
0x180160937  jb      short loc_180160965
0x180160939  lea     rax, [rcx+r8]
0x18016093d  mov     [rbx+230h], rax
0x180160944  mov     [rbx+238h], r15d
0x18016094b  mov     dword ptr [rbx+23Ch], 1
0x180160955  mov     [rbx+248h], r15
0x18016095c  mov     [rbx+250h], r15d
0x180160963  jmp     short loc_180160970
0x180160965  mov     rcx, rbx; lpMem
0x180160968  call    FICloseFontFile
0x18016096d  mov     rbx, r15
0x180160970  mov     rax, rbx
0x180160973  mov     rcx, [rbp+190h+var_30]
0x18016097a  xor     rcx, rsp; StackCookie
0x18016097d  call    __security_check_cookie
0x180160982  mov     rbx, [rsp+290h+arg_18]
0x18016098a  add     rsp, 270h
0x180160991  pop     r15
0x180160993  pop     r14
0x180160995  pop     rdi
0x180160996  pop     rsi
0x180160997  pop     rbp
0x180160998  retn
```
