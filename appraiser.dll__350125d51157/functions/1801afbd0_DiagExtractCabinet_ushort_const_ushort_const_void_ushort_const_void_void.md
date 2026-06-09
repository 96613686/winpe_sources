# DiagExtractCabinet(ushort const *,ushort const *,void (*)(ushort const *,void *),void *)

- ea: `0x1801afbd0`
- end: `0x1801afe23`
- name: `?DiagExtractCabinet@@YAJPEBG0P6AX0PEAX@Z1@Z`
- size: `595`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, const unsigned __int16 *, void (*)(const unsigned __int16 *, void *), void *)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x180039538`
- `0x18004608c`
- `0x1800858c8`

## callees

- `0x180008570`
- `0x1801afac4`
- `0x1801afbd0`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x1801afcda`
- `KERNEL32!GetFullPathNameW` at `0x1801afcda`
- `KERNEL32!GetProcessHeap` at `0x1801afca2`
- `KERNEL32!GetProcessHeap` at `0x1801afdb3`
- `KERNEL32!GetProcessHeap` at `0x1801afdcc`
- `KERNEL32!GetProcessHeap` at `0x1801afde5`
- `KERNEL32!GetProcessHeap` at `0x1801afca2`
- `KERNEL32!GetProcessHeap` at `0x1801afdb3`
- `KERNEL32!GetProcessHeap` at `0x1801afdcc`
- `KERNEL32!GetProcessHeap` at `0x1801afde5`
- `KERNEL32!HeapAlloc` at `0x1801afcb3`
- `KERNEL32!HeapAlloc` at `0x1801afcb3`
- `KERNEL32!GetLastError` at `0x1801afce4`
- `KERNEL32!GetLastError` at `0x1801afce4`
- `KERNEL32!HeapFree` at `0x1801afdc1`
- `KERNEL32!HeapFree` at `0x1801afdda`
- `KERNEL32!HeapFree` at `0x1801afdf3`
- `KERNEL32!HeapFree` at `0x1801afdc1`
- `KERNEL32!HeapFree` at `0x1801afdda`
- `KERNEL32!HeapFree` at `0x1801afdf3`
- `Cabinet!__imp_FDICreate` at `0x1801afc8a`
- `Cabinet!__imp_FDICreate` at `0x1801afc8a`
- `Cabinet!__imp_FDICopy` at `0x1801afd87`
- `Cabinet!__imp_FDICopy` at `0x1801afd87`
- `Cabinet!__imp_FDIDestroy` at `0x1801afd9f`
- `Cabinet!__imp_FDIDestroy` at `0x1801afd9f`

## pseudocode

```c
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
              if ( !FDICopy(v8, pszCabinet, pszCabPath, 0, (PFNFDINOTIFY)DiagCabFdiNotify, 0, &pvUser) )
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
0x1801afbd0  mov     [rsp-8+arg_10], rbx
0x1801afbd5  mov     [rsp-8+arg_18], rsi
0x1801afbda  push    rbp
0x1801afbdb  push    rdi
0x1801afbdc  push    r12
0x1801afbde  push    r14
0x1801afbe0  push    r15
0x1801afbe2  lea     rbp, [rsp-37h]
0x1801afbe7  sub     rsp, 0A0h
0x1801afbee  mov     rax, cs:__security_cookie
0x1801afbf5  xor     rax, rsp
0x1801afbf8  mov     [rbp+57h+var_30], rax
0x1801afbfc  xor     eax, eax
0x1801afbfe  xor     esi, esi
0x1801afc00  xor     r14d, r14d
0x1801afc03  mov     [rbp+57h+pszCabinet], rsi
0x1801afc07  mov     [rbp+57h+pszCabPath], r14
0x1801afc0b  xorps   xmm0, xmm0
0x1801afc0e  mov     [rbp+57h+FilePart], rsi
0x1801afc12  mov     r15, rdx
0x1801afc15  mov     qword ptr [rbp+57h+var_40.erfOper], rax
0x1801afc19  mov     rbx, rcx
0x1801afc1c  mov     [rbp+57h+var_40.fError], eax
0x1801afc1f  mov     [rbp+57h+var_48], rax
0x1801afc23  movups  [rbp+57h+pvUser], xmm0
0x1801afc27  test    rcx, rcx
0x1801afc2a  jz      loc_1801AFDA7
0x1801afc30  test    rdx, rdx
0x1801afc33  jz      loc_1801AFDA7
0x1801afc39  lea     rax, [rbp+57h+var_40]
0x1801afc3d  mov     [rsp+0C0h+perf], rax; perf
0x1801afc42  lea     r9, ?DiagCabFDIReadFile@@YAI_JPEAXI@Z; pfnread
0x1801afc49  mov     [rsp+0C0h+cpuType], 0FFFFFFFFh; cpuType
0x1801afc51  lea     rax, ?DiagCabFDISeekFile@@YAJ_JJH@Z; DiagCabFDISeekFile(__int64,long,int)
0x1801afc58  mov     [rsp+0C0h+pfnseek], rax; pfnseek
0x1801afc5d  lea     r8, ?DiagCabFDIOpenFile@@YA_JPEADHH@Z; pfnopen
0x1801afc64  lea     rax, ?DiagCabFDICloseFile@@YAH_J@Z; DiagCabFDICloseFile(__int64)
0x1801afc6b  mov     [rsp+0C0h+pfnclose], rax; pfnclose
0x1801afc70  lea     rdx, ?DiagCabFree@@YAXPEAX@Z; pfnfree
0x1801afc77  lea     rax, ?DiagCabFDIWriteFile@@YAI_JPEAXI@Z; DiagCabFDIWriteFile(__int64,void *,uint)
0x1801afc7e  lea     rcx, ?DiagCabAlloc@@YAPEAXK@Z; pfnalloc
0x1801afc85  mov     [rsp+0C0h+pfnwrite], rax; pfnwrite
0x1801afc8a  call    cs:__imp_FDICreate
0x1801afc90  mov     r12, rax
0x1801afc93  test    rax, rax
0x1801afc96  jnz     short loc_1801AFCA2
0x1801afc98  mov     ebx, 80300113h
0x1801afc9d  jmp     loc_1801AFDF9
0x1801afca2  call    cs:__imp_GetProcessHeap
0x1801afca8  xor     edx, edx; dwFlags
0x1801afcaa  mov     r8d, 800h; dwBytes
0x1801afcb0  mov     rcx, rax; hHeap
0x1801afcb3  call    cs:__imp_HeapAlloc
0x1801afcb9  mov     rdi, rax
0x1801afcbc  test    rax, rax
0x1801afcbf  jnz     short loc_1801AFCCB
0x1801afcc1  mov     ebx, 8007000Eh
0x1801afcc6  jmp     loc_1801AFD9C
0x1801afccb  lea     r9, [rbp+57h+FilePart]; lpFilePart
0x1801afccf  mov     r8, rdi; lpBuffer
0x1801afcd2  mov     edx, 400h; nBufferLength
0x1801afcd7  mov     rcx, rbx; lpFileName
0x1801afcda  call    cs:__imp_GetFullPathNameW
0x1801afce0  test    eax, eax
0x1801afce2  jnz     short loc_1801AFD02
0x1801afce4  call    cs:__imp_GetLastError
0x1801afcea  mov     ebx, eax
0x1801afcec  test    eax, eax
0x1801afcee  jle     loc_1801AFD9C
0x1801afcf4  movzx   ebx, ax
0x1801afcf7  or      ebx, 80070000h
0x1801afcfd  jmp     loc_1801AFD9C
0x1801afd02  cmp     eax, 400h
0x1801afd07  jb      short loc_1801AFD13
0x1801afd09  mov     ebx, 8007007Ah
0x1801afd0e  jmp     loc_1801AFD9C
0x1801afd13  mov     rcx, [rbp+57h+FilePart]; lpWideCharStr
0x1801afd17  test    rcx, rcx
0x1801afd1a  jnz     short loc_1801AFD23
0x1801afd1c  mov     ebx, 800700A1h
0x1801afd21  jmp     short loc_1801AFD9C
0x1801afd23  lea     rdx, [rbp+57h+pszCabinet]; char **
0x1801afd27  call    ?DiagDuplicateString@@YAJPEBGPEAPEAD@Z; DiagDuplicateString(ushort const *,char * *)
0x1801afd2c  mov     ebx, eax
0x1801afd2e  test    eax, eax
0x1801afd30  js      short loc_1801AFD98
0x1801afd32  mov     rax, [rbp+57h+FilePart]
0x1801afd36  lea     rdx, [rbp+57h+pszCabPath]; char **
0x1801afd3a  xor     ecx, ecx
0x1801afd3c  mov     [rax], cx
0x1801afd3f  mov     rcx, rdi; lpWideCharStr
0x1801afd42  call    ?DiagDuplicateString@@YAJPEBGPEAPEAD@Z; DiagDuplicateString(ushort const *,char * *)
0x1801afd47  mov     r14, [rbp+57h+pszCabPath]
0x1801afd4b  mov     ebx, eax
0x1801afd4d  test    eax, eax
0x1801afd4f  js      short loc_1801AFD98
0x1801afd51  lea     rax, [rbp+57h+pvUser]
0x1801afd55  mov     qword ptr [rbp+57h+pvUser], rsi
0x1801afd59  mov     [rsp+0C0h+pfnseek], rax; pvUser
0x1801afd5e  xor     r9d, r9d; flags
0x1801afd61  mov     [rsp+0C0h+pfnclose], rsi; pfnfdid
0x1801afd66  lea     rax, ?DiagCabFdiNotify@@YA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z; DiagCabFdiNotify(FDINOTIFICATIONTYPE,FDINOTIFICATION *)
0x1801afd6d  mov     qword ptr [rbp+57h+pvUser+8], rsi
0x1801afd71  mov     r8, r14; pszCabPath
0x1801afd74  mov     rsi, [rbp+57h+pszCabinet]
0x1801afd78  mov     rcx, r12; hfdi
0x1801afd7b  mov     rdx, rsi; pszCabinet
0x1801afd7e  mov     [rbp+57h+var_48], r15
0x1801afd82  mov     [rsp+0C0h+pfnwrite], rax; pfnfdin
0x1801afd87  call    cs:__imp_FDICopy
0x1801afd8d  test    eax, eax
0x1801afd8f  jnz     short loc_1801AFD9C
0x1801afd91  mov     ebx, 80300113h
0x1801afd96  jmp     short loc_1801AFD9C
0x1801afd98  mov     rsi, [rbp+57h+pszCabinet]
0x1801afd9c  mov     rcx, r12; hfdi
0x1801afd9f  call    cs:__imp_FDIDestroy
0x1801afda5  jmp     short loc_1801AFDAE
0x1801afda7  xor     edi, edi
0x1801afda9  mov     ebx, 80070057h
0x1801afdae  test    r14, r14
0x1801afdb1  jz      short loc_1801AFDC7
0x1801afdb3  call    cs:__imp_GetProcessHeap
0x1801afdb9  mov     r8, r14; lpMem
0x1801afdbc  xor     edx, edx; dwFlags
0x1801afdbe  mov     rcx, rax; hHeap
0x1801afdc1  call    cs:__imp_HeapFree
0x1801afdc7  test    rsi, rsi
0x1801afdca  jz      short loc_1801AFDE0
0x1801afdcc  call    cs:__imp_GetProcessHeap
0x1801afdd2  mov     r8, rsi; lpMem
0x1801afdd5  xor     edx, edx; dwFlags
0x1801afdd7  mov     rcx, rax; hHeap
0x1801afdda  call    cs:__imp_HeapFree
0x1801afde0  test    rdi, rdi
0x1801afde3  jz      short loc_1801AFDF9
0x1801afde5  call    cs:__imp_GetProcessHeap
0x1801afdeb  mov     r8, rdi; lpMem
0x1801afdee  xor     edx, edx; dwFlags
0x1801afdf0  mov     rcx, rax; hHeap
0x1801afdf3  call    cs:__imp_HeapFree
0x1801afdf9  mov     eax, ebx
0x1801afdfb  mov     rcx, [rbp+57h+var_30]
0x1801afdff  xor     rcx, rsp; StackCookie
0x1801afe02  call    __security_check_cookie
0x1801afe07  lea     r11, [rsp+0C0h+var_20]
0x1801afe0f  mov     rbx, [r11+40h]
0x1801afe13  mov     rsi, [r11+48h]
0x1801afe17  mov     rsp, r11
0x1801afe1a  pop     r15
0x1801afe1c  pop     r14
0x1801afe1e  pop     r12
0x1801afe20  pop     rdi
0x1801afe21  pop     rbp
0x1801afe22  retn
```
