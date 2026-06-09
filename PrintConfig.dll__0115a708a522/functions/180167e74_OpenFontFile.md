# OpenFontFile

- ea: `0x180167e74`
- end: `0x1801681be`
- name: `OpenFontFile`
- size: `842`
- prototype: `BYTE *__fastcall(HANDLE hPrinter, HANDLE hHeap, wchar_t *String1)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180125868`
- `0x18012643c`
- `0x1801267b4`
- `0x180126940`

## callees

- `0x180003400`
- `0x18000be68`
- `0x1801266a8`
- `0x180167274`
- `0x180167e74`
- `0x1801b568c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180167f62`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180167fda`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180167f62`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180167fda`
- `KERNEL32!CreateFileMappingW` at `0x180168079`
- `KERNEL32!CreateFileMappingW` at `0x180168079`
- `KERNEL32!MapViewOfFile` at `0x18016809f`
- `KERNEL32!MapViewOfFile` at `0x18016809f`
- `KERNEL32!GetFileSize` at `0x18016804e`
- `KERNEL32!GetFileSize` at `0x18016804e`
- `KERNEL32!HeapAlloc` at `0x180167ec3`
- `KERNEL32!HeapAlloc` at `0x180167ec3`
- `KERNEL32!CreateFileW` at `0x18016802a`
- `KERNEL32!CreateFileW` at `0x18016802a`
- `KERNEL32!CloseHandle` at `0x1801680b5`
- `KERNEL32!CloseHandle` at `0x1801680cd`
- `KERNEL32!CloseHandle` at `0x1801680fe`
- `KERNEL32!CloseHandle` at `0x1801680b5`
- `KERNEL32!CloseHandle` at `0x1801680cd`
- `KERNEL32!CloseHandle` at `0x1801680fe`
- `WINSPOOL!GetPrinterDataW` at `0x180167fb5`
- `WINSPOOL!GetPrinterDataW` at `0x180167fb5`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x180167f46`
- `WINSPOOL!GetPrinterDriverDirectoryW` at `0x180167f46`

## pseudocode

```c
BYTE *__fastcall OpenFontFile(HANDLE hPrinter, HANDLE hHeap, wchar_t *String1)
{
  BYTE *result; // rax
  BYTE *v7; // rbx
  wchar_t *v8; // rax
  DWORD PrinterDataW; // eax
  wchar_t *v10; // rax
  unsigned __int16 *v11; // rax
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
  result = (BYTE *)HeapAlloc(hHeap, 8u, 0x258u);
  v7 = result;
  if ( result )
  {
    *(_DWORD *)result = 1718514793;
    *((_QWORD *)result + 1) = hPrinter;
    *((_QWORD *)result + 2) = hHeap;
    *((_QWORD *)result + 72) = 0;
    *((_DWORD *)result + 143) = 0;
    if ( !wcscmp_0(String1, L"ExtFontCartFile") && !BGetFontCartridgeFile(hPrinter, hHeap) )
      goto LABEL_29;
    pcbNeeded = 520;
    if ( !GetPrinterDriverDirectoryW(0, 0, 1u, v7 + 24, 0x208u, &pcbNeeded) )
      goto LABEL_29;
    v8 = wcsrchr((const wchar_t *)v7 + 12, 0x5Cu);
    if ( v8 )
      *v8 = 0;
    StringCchCatW((unsigned __int16 *)v7 + 12, 260, L"\\unifont\\");
    pcbNeeded = 520;
    PrinterDataW = GetPrinterDataW(hPrinter, String1, pType, (LPBYTE)pData, 0x208u, &pcbNeeded);
    if ( PrinterDataW != 234 )
    {
      if ( PrinterDataW )
        goto LABEL_29;
    }
    v10 = wcsrchr(pData, 0x5Cu);
    if ( v10 )
      v11 = v10 + 1;
    else
      v11 = pData;
    StringCchCatW((unsigned __int16 *)v7 + 12, 260, v11);
    FileW = CreateFileW((LPCWSTR)v7 + 12, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
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
          *((_QWORD *)v7 + 72) = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
          CloseHandle(v15);
          if ( *((_QWORD *)v7 + 72) )
          {
LABEL_18:
            v16 = *((_QWORD *)v7 + 72);
            *((_QWORD *)v7 + 68) = v16;
            if ( v16 )
            {
              CloseHandle((HANDLE)v13);
              v17 = (_DWORD *)*((_QWORD *)v7 + 72);
              *((_QWORD *)v7 + 69) = v17;
              if ( pcbNeeded >= 0x30 && *v17 == 826689109 && v17[1] == 65537 && v17[2] == 48 )
              {
                v18 = (unsigned int)v17[6];
                if ( !(_DWORD)v18 )
                {
LABEL_28:
                  *((_DWORD *)v7 + 142) = 0;
                  *((_DWORD *)v7 + 143) = 1;
                  *((_QWORD *)v7 + 73) = 0;
                  *((_DWORD *)v7 + 148) = 0;
                  return v7;
                }
                v19 = 36LL * (unsigned int)v17[3];
                if ( v19 <= 0xFFFFFFFF && (int)v19 + (int)v18 >= (unsigned int)v19 && pcbNeeded >= (int)v19 + (int)v18 )
                {
                  *((_QWORD *)v7 + 70) = (char *)v17 + v18;
                  goto LABEL_28;
                }
              }
            }
LABEL_29:
            FICloseFontFile(v7);
            return 0;
          }
        }
      }
      CloseHandle((HANDLE)v13);
      v13 = -1;
    }
    *((_QWORD *)v7 + 72) = 0;
    goto LABEL_18;
  }
  return result;
}

```

## disassembly

```asm
0x180167e74  mov     [rsp-8+arg_18], rbx
0x180167e79  push    rbp
0x180167e7a  push    rsi
0x180167e7b  push    rdi
0x180167e7c  push    r14
0x180167e7e  push    r15
0x180167e80  lea     rbp, [rsp-170h]
0x180167e88  sub     rsp, 270h
0x180167e8f  mov     rax, cs:__security_cookie
0x180167e96  xor     rax, rsp
0x180167e99  mov     [rbp+190h+var_30], rax
0x180167ea0  xor     r15d, r15d
0x180167ea3  mov     rdi, rdx
0x180167ea6  mov     r14, r8
0x180167ea9  mov     [rsp+290h+var_250], r15d
0x180167eae  mov     rsi, rcx
0x180167eb1  mov     [rsp+290h+pType], r15d
0x180167eb6  mov     r8d, 258h; dwBytes
0x180167ebc  mov     rcx, rdi; hHeap
0x180167ebf  lea     edx, [r15+8]; dwFlags
0x180167ec3  call    cs:__imp_HeapAlloc
0x180167eca  nop     dword ptr [rax+rax+00h]
0x180167ecf  mov     rbx, rax
0x180167ed2  test    rax, rax
0x180167ed5  jz      loc_180168197
0x180167edb  lea     rdx, aExtfontcartfil; "ExtFontCartFile"
0x180167ee2  mov     dword ptr [rax], 666E7469h
0x180167ee8  mov     rcx, r14; String1
0x180167eeb  mov     [rax+8], rsi
0x180167eef  mov     [rax+10h], rdi
0x180167ef3  mov     [rax+240h], r15
0x180167efa  mov     [rax+23Ch], r15d
0x180167f01  call    wcscmp_0
0x180167f06  test    eax, eax
0x180167f08  jnz     short loc_180167F1D
0x180167f0a  mov     rdx, rdi; hHeap
0x180167f0d  mov     rcx, rsi; hPrinter
0x180167f10  call    BGetFontCartridgeFile
0x180167f15  test    eax, eax
0x180167f17  jz      loc_180168189
0x180167f1d  xor     edx, edx; pEnvironment
0x180167f1f  mov     [rsp+290h+var_250], 208h
0x180167f27  lea     rax, [rsp+290h+var_250]
0x180167f2c  xor     ecx, ecx; pName
0x180167f2e  mov     [rsp+290h+pcbNeeded], rax; pcbNeeded
0x180167f33  lea     rdi, [rbx+18h]
0x180167f37  mov     r9, rdi; pDriverDirectory
0x180167f3a  mov     [rsp+290h+cbBuf], 208h; cbBuf
0x180167f42  lea     r8d, [rdx+1]; Level
0x180167f46  call    cs:__imp_GetPrinterDriverDirectoryW
0x180167f4d  nop     dword ptr [rax+rax+00h]
0x180167f52  test    eax, eax
0x180167f54  jz      loc_180168189
0x180167f5a  mov     edx, 5Ch ; '\'; Ch
0x180167f5f  mov     rcx, rdi; Str
0x180167f62  call    cs:__imp_wcsrchr
0x180167f69  nop     dword ptr [rax+rax+00h]
0x180167f6e  test    rax, rax
0x180167f71  jz      short loc_180167F77
0x180167f73  mov     [rax], r15w
0x180167f77  lea     r8, aUnifont; "\\unifont\\"
0x180167f7e  mov     edx, 104h; unsigned __int64
0x180167f83  mov     rcx, rdi; unsigned __int16 *
0x180167f86  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180167f8b  lea     rax, [rsp+290h+var_250]
0x180167f90  mov     [rsp+290h+var_250], 208h
0x180167f98  mov     [rsp+290h+pcbNeeded], rax; pcbNeeded
0x180167f9d  lea     r9, [rsp+290h+pData]; pData
0x180167fa2  lea     r8, [rsp+290h+pType]; pType
0x180167fa7  mov     [rsp+290h+cbBuf], 208h; nSize
0x180167faf  mov     rdx, r14; pValueName
0x180167fb2  mov     rcx, rsi; hPrinter
0x180167fb5  call    cs:__imp_GetPrinterDataW
0x180167fbc  nop     dword ptr [rax+rax+00h]
0x180167fc1  cmp     eax, 0EAh
0x180167fc6  jz      short loc_180167FD0
0x180167fc8  test    eax, eax
0x180167fca  jnz     loc_180168189
0x180167fd0  mov     edx, 5Ch ; '\'; Ch
0x180167fd5  lea     rcx, [rsp+290h+pData]; Str
0x180167fda  call    cs:__imp_wcsrchr
0x180167fe1  nop     dword ptr [rax+rax+00h]
0x180167fe6  test    rax, rax
0x180167fe9  jz      short loc_180167FF1
0x180167feb  add     rax, 2
0x180167fef  jmp     short loc_180167FF6
0x180167ff1  lea     rax, [rsp+290h+pData]
0x180167ff6  mov     r8, rax; unsigned __int16 *
0x180167ff9  mov     edx, 104h; unsigned __int64
0x180167ffe  mov     rcx, rdi; unsigned __int16 *
0x180168001  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180168006  xor     r9d, r9d; lpSecurityAttributes
0x180168009  mov     [rsp+290h+hTemplateFile], r15; hTemplateFile
0x18016800e  mov     dword ptr [rsp+290h+pcbNeeded], 100080h; dwFlagsAndAttributes
0x180168016  mov     edx, 80000000h; dwDesiredAccess
0x18016801b  mov     rcx, rdi; lpFileName
0x18016801e  mov     [rsp+290h+cbBuf], 3; dwCreationDisposition
0x180168026  lea     r8d, [r9+1]; dwShareMode
0x18016802a  call    cs:__imp_CreateFileW
0x180168031  nop     dword ptr [rax+rax+00h]
0x180168036  mov     rdi, rax
0x180168039  mov     r14d, 0FFFFFFFFh
0x18016803f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180168043  jz      loc_1801680DD
0x180168049  xor     edx, edx; lpFileSizeHigh
0x18016804b  mov     rcx, rax; hFile
0x18016804e  call    cs:__imp_GetFileSize
0x180168055  nop     dword ptr [rax+rax+00h]
0x18016805a  mov     [rsp+290h+var_250], eax
0x18016805e  cmp     eax, r14d
0x180168061  jz      short loc_1801680CA
0x180168063  xor     r9d, r9d; dwMaximumSizeHigh
0x180168066  mov     [rsp+290h+pcbNeeded], r15; lpName
0x18016806b  xor     edx, edx; lpFileMappingAttributes
0x18016806d  mov     [rsp+290h+cbBuf], r15d; dwMaximumSizeLow
0x180168072  mov     rcx, rdi; hFile
0x180168075  lea     r8d, [r9+2]; flProtect
0x180168079  call    cs:__imp_CreateFileMappingW
0x180168080  nop     dword ptr [rax+rax+00h]
0x180168085  mov     rsi, rax
0x180168088  test    rax, rax
0x18016808b  jz      short loc_1801680CA
0x18016808d  xor     r9d, r9d; dwFileOffsetLow
0x180168090  mov     qword ptr [rsp+290h+cbBuf], r15; dwNumberOfBytesToMap
0x180168095  xor     r8d, r8d; dwFileOffsetHigh
0x180168098  mov     rcx, rax; hFileMappingObject
0x18016809b  lea     edx, [r9+4]; dwDesiredAccess
0x18016809f  call    cs:__imp_MapViewOfFile
0x1801680a6  nop     dword ptr [rax+rax+00h]
0x1801680ab  mov     rcx, rsi; hObject
0x1801680ae  mov     [rbx+240h], rax
0x1801680b5  call    cs:__imp_CloseHandle
0x1801680bc  nop     dword ptr [rax+rax+00h]
0x1801680c1  cmp     [rbx+240h], r15
0x1801680c8  jnz     short loc_1801680E4
0x1801680ca  mov     rcx, rdi; hObject
0x1801680cd  call    cs:__imp_CloseHandle
0x1801680d4  nop     dword ptr [rax+rax+00h]
0x1801680d9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1801680dd  mov     [rbx+240h], r15
0x1801680e4  mov     rax, [rbx+240h]
0x1801680eb  mov     [rbx+220h], rax
0x1801680f2  test    rax, rax
0x1801680f5  jz      loc_180168189
0x1801680fb  mov     rcx, rdi; hObject
0x1801680fe  call    cs:__imp_CloseHandle
0x180168105  nop     dword ptr [rax+rax+00h]
0x18016810a  mov     rcx, [rbx+240h]
0x180168111  mov     [rbx+228h], rcx
0x180168118  cmp     [rsp+290h+var_250], 30h ; '0'
0x18016811d  jb      short loc_180168189
0x18016811f  cmp     dword ptr [rcx], 31464655h
0x180168125  jnz     short loc_180168189
0x180168127  cmp     dword ptr [rcx+4], 10001h
0x18016812e  jnz     short loc_180168189
0x180168130  cmp     dword ptr [rcx+8], 30h ; '0'
0x180168134  jnz     short loc_180168189
0x180168136  mov     r8d, [rcx+18h]
0x18016813a  test    r8d, r8d
0x18016813d  jz      short loc_180168168
0x18016813f  mov     eax, [rcx+0Ch]
0x180168142  lea     rdx, [rax+rax*8]
0x180168146  shl     rdx, 2
0x18016814a  cmp     rdx, r14
0x18016814d  ja      short loc_180168189
0x18016814f  lea     eax, [rdx+r8]
0x180168153  cmp     eax, edx
0x180168155  jb      short loc_180168189
0x180168157  cmp     [rsp+290h+var_250], eax
0x18016815b  jb      short loc_180168189
0x18016815d  lea     rax, [rcx+r8]
0x180168161  mov     [rbx+230h], rax
0x180168168  mov     [rbx+238h], r15d
0x18016816f  mov     dword ptr [rbx+23Ch], 1
0x180168179  mov     [rbx+248h], r15
0x180168180  mov     [rbx+250h], r15d
0x180168187  jmp     short loc_180168194
0x180168189  mov     rcx, rbx; lpMem
0x18016818c  call    FICloseFontFile
0x180168191  mov     rbx, r15
0x180168194  mov     rax, rbx
0x180168197  mov     rcx, [rbp+190h+var_30]
0x18016819e  xor     rcx, rsp; StackCookie
0x1801681a1  call    __security_check_cookie
0x1801681a6  mov     rbx, [rsp+290h+arg_18]
0x1801681ae  add     rsp, 270h
0x1801681b5  pop     r15
0x1801681b7  pop     r14
0x1801681b9  pop     rdi
0x1801681ba  pop     rsi
0x1801681bb  pop     rbp
0x1801681bc  retn
```
