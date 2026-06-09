# DiagExtractCabinet(ushort const *,ushort const *,void (*)(ushort const *,void *),void *)

- ea: `0x180025d7c`
- end: `0x180025fcf`
- name: `?DiagExtractCabinet@@YAJPEBG0P6AX0PEAX@Z1@Z`
- size: `595`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const unsigned __int16 *, void (*)(const unsigned __int16 *, void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18001f2c0`

## callees

- `0x180003fc0`
- `0x180025c70`
- `0x180025d7c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025e90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180025e90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025e4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025f5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025f78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025f91`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025e4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025f5f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025f78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025f91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025f6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025f86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025f9f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025f6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025f86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025f9f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025e5f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025e5f`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180025e86`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180025e86`
- `Cabinet!__imp_FDICreate` at `0x180025e36`
- `Cabinet!__imp_FDICreate` at `0x180025e36`
- `Cabinet!__imp_FDICopy` at `0x180025f33`
- `Cabinet!__imp_FDICopy` at `0x180025f33`
- `Cabinet!__imp_FDIDestroy` at `0x180025f4b`
- `Cabinet!__imp_FDIDestroy` at `0x180025f4b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DiagExtractCabinet(
        LPCWSTR lpFileName,
        const unsigned __int16 *a2,
        void (*a3)(const unsigned __int16 *, void *),
        void *a4)
{
  LPSTR v4; // rsi
  LPSTR v5; // r14
  HFDI v8; // r12
  signed int v9; // ebx
  HANDLE ProcessHeap; // rax
  WCHAR *v11; // rax
  WCHAR *v12; // rdi
  DWORD FullPathNameW; // eax
  signed int LastError; // eax
  int v15; // eax
  HANDLE v16; // rax
  HANDLE v17; // rax
  HANDLE v18; // rax
  LPSTR pszCabinet; // [rsp+50h] [rbp-19h] BYREF
  LPWSTR FilePart; // [rsp+58h] [rbp-11h] BYREF
  LPSTR pszCabPath; // [rsp+60h] [rbp-9h] BYREF
  __int128 pvUser; // [rsp+68h] [rbp-1h] BYREF
  const unsigned __int16 *v24; // [rsp+78h] [rbp+Fh]
  ERF perf; // [rsp+80h] [rbp+17h] BYREF

  v4 = 0;
  v5 = 0;
  pszCabinet = 0;
  pszCabPath = 0;
  FilePart = 0;
  *(_QWORD *)&perf.erfOper = 0;
  perf.fError = 0;
  v24 = 0;
  pvUser = 0;
  if ( lpFileName && a2 )
  {
    v8 = FDICreate(
           DiagCabAlloc,
           DiagCabFree,
           DiagCabFDIOpenFile,
           DiagCabFDIReadFile,
           DiagCabFDIWriteFile,
           DiagCabFDICloseFile,
           DiagCabFDISeekFile,
           -1,
           &perf);
    if ( !v8 )
      return (unsigned int)-2144337645;
    ProcessHeap = GetProcessHeap();
    v11 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x800u);
    v12 = v11;
    if ( v11 )
    {
      FullPathNameW = GetFullPathNameW(lpFileName, 0x400u, v11, &FilePart);
      if ( FullPathNameW )
      {
        if ( FullPathNameW < 0x400 )
        {
          if ( FilePart )
          {
            v9 = DiagDuplicateString(FilePart, &pszCabinet);
            if ( v9 < 0
              || (*FilePart = 0, v15 = DiagDuplicateString(v12, &pszCabPath), v5 = pszCabPath, v9 = v15, v15 < 0) )
            {
              v4 = pszCabinet;
            }
            else
            {
              pvUser = 0u;
              v4 = pszCabinet;
              v24 = a2;
              if ( !FDICopy(v8, pszCabinet, pszCabPath, 0, DiagCabFdiNotify, 0, &pvUser) )
                v9 = -2144337645;
            }
          }
          else
          {
            v9 = -2147024735;
          }
        }
        else
        {
          v9 = -2147024774;
        }
      }
      else
      {
        LastError = GetLastError();
        v9 = LastError;
        if ( LastError > 0 )
          v9 = (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      v9 = -2147024882;
    }
    FDIDestroy(v8);
  }
  else
  {
    v12 = 0;
    v9 = -2147024809;
  }
  if ( v5 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v5);
  }
  if ( v4 )
  {
    v17 = GetProcessHeap();
    HeapFree(v17, 0, v4);
  }
  if ( v12 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, v12);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180025d7c  mov     [rsp-8+arg_10], rbx
0x180025d81  mov     [rsp-8+arg_18], rsi
0x180025d86  push    rbp
0x180025d87  push    rdi
0x180025d88  push    r12
0x180025d8a  push    r14
0x180025d8c  push    r15
0x180025d8e  lea     rbp, [rsp-37h]
0x180025d93  sub     rsp, 0A0h
0x180025d9a  mov     rax, cs:__security_cookie
0x180025da1  xor     rax, rsp
0x180025da4  mov     [rbp+57h+var_30], rax
0x180025da8  xor     eax, eax
0x180025daa  xor     esi, esi
0x180025dac  xor     r14d, r14d
0x180025daf  mov     [rbp+57h+pszCabinet], rsi
0x180025db3  mov     [rbp+57h+pszCabPath], r14
0x180025db7  xorps   xmm0, xmm0
0x180025dba  mov     [rbp+57h+FilePart], rsi
0x180025dbe  mov     r15, rdx
0x180025dc1  mov     qword ptr [rbp+57h+var_40.erfOper], rax
0x180025dc5  mov     rbx, rcx
0x180025dc8  mov     [rbp+57h+var_40.fError], eax
0x180025dcb  mov     [rbp+57h+var_48], rax
0x180025dcf  movups  [rbp+57h+pvUser], xmm0
0x180025dd3  test    rcx, rcx
0x180025dd6  jz      loc_180025F53
0x180025ddc  test    rdx, rdx
0x180025ddf  jz      loc_180025F53
0x180025de5  lea     rax, [rbp+57h+var_40]
0x180025de9  mov     [rsp+0C0h+perf], rax; perf
0x180025dee  lea     r9, ?DiagCabFDIReadFile@@YAI_JPEAXI@Z; pfnread
0x180025df5  mov     [rsp+0C0h+cpuType], 0FFFFFFFFh; cpuType
0x180025dfd  lea     rax, ?DiagCabFDISeekFile@@YAJ_JJH@Z; DiagCabFDISeekFile(__int64,long,int)
0x180025e04  mov     [rsp+0C0h+pfnseek], rax; pfnseek
0x180025e09  lea     r8, ?DiagCabFDIOpenFile@@YA_JPEADHH@Z; pfnopen
0x180025e10  lea     rax, ?DiagCabFDICloseFile@@YAH_J@Z; DiagCabFDICloseFile(__int64)
0x180025e17  mov     [rsp+0C0h+pfnclose], rax; pfnclose
0x180025e1c  lea     rdx, ?DiagCabFree@@YAXPEAX@Z; pfnfree
0x180025e23  lea     rax, ?DiagCabFDIWriteFile@@YAI_JPEAXI@Z; DiagCabFDIWriteFile(__int64,void *,uint)
0x180025e2a  lea     rcx, ?DiagCabAlloc@@YAPEAXK@Z; pfnalloc
0x180025e31  mov     [rsp+0C0h+pfnwrite], rax; pfnwrite
0x180025e36  call    cs:__imp_FDICreate
0x180025e3c  mov     r12, rax
0x180025e3f  test    rax, rax
0x180025e42  jnz     short loc_180025E4E
0x180025e44  mov     ebx, 80300113h
0x180025e49  jmp     loc_180025FA5
0x180025e4e  call    cs:__imp_GetProcessHeap
0x180025e54  xor     edx, edx; dwFlags
0x180025e56  mov     r8d, 800h; dwBytes
0x180025e5c  mov     rcx, rax; hHeap
0x180025e5f  call    cs:__imp_HeapAlloc
0x180025e65  mov     rdi, rax
0x180025e68  test    rax, rax
0x180025e6b  jnz     short loc_180025E77
0x180025e6d  mov     ebx, 8007000Eh
0x180025e72  jmp     loc_180025F48
0x180025e77  lea     r9, [rbp+57h+FilePart]; lpFilePart
0x180025e7b  mov     r8, rdi; lpBuffer
0x180025e7e  mov     edx, 400h; nBufferLength
0x180025e83  mov     rcx, rbx; lpFileName
0x180025e86  call    cs:__imp_GetFullPathNameW
0x180025e8c  test    eax, eax
0x180025e8e  jnz     short loc_180025EAE
0x180025e90  call    cs:__imp_GetLastError
0x180025e96  mov     ebx, eax
0x180025e98  test    eax, eax
0x180025e9a  jle     loc_180025F48
0x180025ea0  movzx   ebx, ax
0x180025ea3  or      ebx, 80070000h
0x180025ea9  jmp     loc_180025F48
0x180025eae  cmp     eax, 400h
0x180025eb3  jb      short loc_180025EBF
0x180025eb5  mov     ebx, 8007007Ah
0x180025eba  jmp     loc_180025F48
0x180025ebf  mov     rcx, [rbp+57h+FilePart]; lpWideCharStr
0x180025ec3  test    rcx, rcx
0x180025ec6  jnz     short loc_180025ECF
0x180025ec8  mov     ebx, 800700A1h
0x180025ecd  jmp     short loc_180025F48
0x180025ecf  lea     rdx, [rbp+57h+pszCabinet]; char **
0x180025ed3  call    ?DiagDuplicateString@@YAJPEBGPEAPEAD@Z; DiagDuplicateString(ushort const *,char * *)
0x180025ed8  mov     ebx, eax
0x180025eda  test    eax, eax
0x180025edc  js      short loc_180025F44
0x180025ede  mov     rax, [rbp+57h+FilePart]
0x180025ee2  lea     rdx, [rbp+57h+pszCabPath]; char **
0x180025ee6  xor     ecx, ecx
0x180025ee8  mov     [rax], cx
0x180025eeb  mov     rcx, rdi; lpWideCharStr
0x180025eee  call    ?DiagDuplicateString@@YAJPEBGPEAPEAD@Z; DiagDuplicateString(ushort const *,char * *)
0x180025ef3  mov     r14, [rbp+57h+pszCabPath]
0x180025ef7  mov     ebx, eax
0x180025ef9  test    eax, eax
0x180025efb  js      short loc_180025F44
0x180025efd  lea     rax, [rbp+57h+pvUser]
0x180025f01  mov     qword ptr [rbp+57h+pvUser], rsi
0x180025f05  mov     [rsp+0C0h+pfnseek], rax; pvUser
0x180025f0a  xor     r9d, r9d; flags
0x180025f0d  mov     [rsp+0C0h+pfnclose], rsi; pfnfdid
0x180025f12  lea     rax, ?DiagCabFdiNotify@@YA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z; DiagCabFdiNotify(FDINOTIFICATIONTYPE,FDINOTIFICATION *)
0x180025f19  mov     qword ptr [rbp+57h+pvUser+8], rsi
0x180025f1d  mov     r8, r14; pszCabPath
0x180025f20  mov     rsi, [rbp+57h+pszCabinet]
0x180025f24  mov     rcx, r12; hfdi
0x180025f27  mov     rdx, rsi; pszCabinet
0x180025f2a  mov     [rbp+57h+var_48], r15
0x180025f2e  mov     [rsp+0C0h+pfnwrite], rax; pfnfdin
0x180025f33  call    cs:__imp_FDICopy
0x180025f39  test    eax, eax
0x180025f3b  jnz     short loc_180025F48
0x180025f3d  mov     ebx, 80300113h
0x180025f42  jmp     short loc_180025F48
0x180025f44  mov     rsi, [rbp+57h+pszCabinet]
0x180025f48  mov     rcx, r12; hfdi
0x180025f4b  call    cs:__imp_FDIDestroy
0x180025f51  jmp     short loc_180025F5A
0x180025f53  xor     edi, edi
0x180025f55  mov     ebx, 80070057h
0x180025f5a  test    r14, r14
0x180025f5d  jz      short loc_180025F73
0x180025f5f  call    cs:__imp_GetProcessHeap
0x180025f65  mov     r8, r14; lpMem
0x180025f68  xor     edx, edx; dwFlags
0x180025f6a  mov     rcx, rax; hHeap
0x180025f6d  call    cs:__imp_HeapFree
0x180025f73  test    rsi, rsi
0x180025f76  jz      short loc_180025F8C
0x180025f78  call    cs:__imp_GetProcessHeap
0x180025f7e  mov     r8, rsi; lpMem
0x180025f81  xor     edx, edx; dwFlags
0x180025f83  mov     rcx, rax; hHeap
0x180025f86  call    cs:__imp_HeapFree
0x180025f8c  test    rdi, rdi
0x180025f8f  jz      short loc_180025FA5
0x180025f91  call    cs:__imp_GetProcessHeap
0x180025f97  mov     r8, rdi; lpMem
0x180025f9a  xor     edx, edx; dwFlags
0x180025f9c  mov     rcx, rax; hHeap
0x180025f9f  call    cs:__imp_HeapFree
0x180025fa5  mov     eax, ebx
0x180025fa7  mov     rcx, [rbp+57h+var_30]
0x180025fab  xor     rcx, rsp; StackCookie
0x180025fae  call    __security_check_cookie
0x180025fb3  lea     r11, [rsp+0C0h+var_20]
0x180025fbb  mov     rbx, [r11+40h]
0x180025fbf  mov     rsi, [r11+48h]
0x180025fc3  mov     rsp, r11
0x180025fc6  pop     r15
0x180025fc8  pop     r14
0x180025fca  pop     r12
0x180025fcc  pop     rdi
0x180025fcd  pop     rbp
0x180025fce  retn
```
