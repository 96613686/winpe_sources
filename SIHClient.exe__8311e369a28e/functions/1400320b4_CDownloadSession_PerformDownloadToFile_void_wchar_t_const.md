# CDownloadSession::PerformDownloadToFile(void *,wchar_t const *)

- ea: `0x1400320b4`
- end: `0x140032260`
- name: `?PerformDownloadToFile@CDownloadSession@@AEAAJPEAXPEB_W@Z`
- size: `428`
- prototype: `__int64 __fastcall(CDownloadSession *this, void *, const wchar_t *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140030dd8`

## callees

- `0x14000cdb8`
- `0x14000ce30`
- `0x1400122f0`
- `0x1400154b4`
- `0x1400320b4`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400321c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400321c8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400321f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140032215`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400321f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140032215`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400321fa`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400321fa`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x140032258`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x140032258`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400321a2`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1400321a2`
- `WINHTTP!WinHttpReadData` at `0x1400321be`
- `WINHTTP!WinHttpReadData` at `0x1400321be`

## string_xrefs

- `0x140032132`: `WinHttp: SafeCreateFile`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CDownloadSession::PerformDownloadToFile(CDownloadSession *this, void *a2, const wchar_t *a3)
{
  void *v4; // rbx
  int v6; // eax
  HANDLE v7; // rdi
  signed int v8; // esi
  signed int LastError; // eax
  void *v10; // rcx
  LPOVERLAPPED lpOverlapped; // [rsp+20h] [rbp-68h]
  struct _SECURITY_ATTRIBUTES *v13; // [rsp+28h] [rbp-60h]
  void *v14; // [rsp+40h] [rbp-48h]
  HANDLE hFile; // [rsp+50h] [rbp-38h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+58h] [rbp-30h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+5Ch] [rbp-2Ch] BYREF

  v4 = 0;
  nNumberOfBytesToWrite = 0;
  NumberOfBytesWritten = 0;
  hFile = 0;
  v6 = SafeCreateFile(&hFile, 0, a3, 0x40000000u, 0, v13, 2u, 0x80u, v14);
  v7 = hFile;
  v8 = v6;
  if ( v6 >= 0 )
  {
    WUTrace(0, 0, 32, 5, 0, L"WinHttp: downloading to FILE %ls");
    v4 = SusAlloc(0x8000u);
    if ( v4 )
    {
      while ( 1 )
      {
        if ( !WinHttpReadData(*((HINTERNET *)this + 2), v4, 0x8000u, &nNumberOfBytesToWrite) )
        {
LABEL_8:
          LastError = GetLastError();
          v8 = (unsigned __int16)LastError | 0x80070000;
          if ( LastError <= 0 )
            v8 = LastError;
          if ( v8 >= 0 )
            v8 = -2147418113;
          goto LABEL_12;
        }
        if ( !nNumberOfBytesToWrite )
          break;
        if ( !WriteFile(v7, v4, nNumberOfBytesToWrite, &NumberOfBytesWritten, 0) )
          goto LABEL_8;
      }
      if ( *((int *)this + 51) >= 0 )
        SetFileTime(v7, (const FILETIME *)((char *)this + 196), 0, 0);
      goto LABEL_15;
    }
    v8 = -2147024882;
  }
  else
  {
    LODWORD(lpOverlapped) = v6;
    WUTrace(0, 0, 32, 5, lpOverlapped, L"WinHttp: SafeCreateFile");
  }
LABEL_12:
  v10 = v7;
  v7 = 0;
  if ( v10 != (void *)-1LL )
    CloseHandle(v10);
  DeleteFileW(a3);
  if ( v4 )
LABEL_15:
    SusFree(v4);
  if ( v7 )
    CloseHandle(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400320b4  mov     r11, rsp
0x1400320b7  mov     [r11+10h], rbx
0x1400320bb  mov     [r11+20h], rbp
0x1400320bf  push    rsi
0x1400320c0  push    rdi
0x1400320c1  push    r14
0x1400320c3  sub     rsp, 70h
0x1400320c7  mov     rax, cs:__security_cookie
0x1400320ce  xor     rax, rsp
0x1400320d1  mov     [rsp+88h+var_28], rax
0x1400320d6  mov     rbp, rcx
0x1400320d9  mov     [rsp+88h+var_50], 80h; unsigned int
0x1400320e1  xor     ebx, ebx
0x1400320e3  mov     [rsp+88h+var_58], 2; unsigned int
0x1400320eb  lea     rcx, [r11-38h]; void **
0x1400320ef  mov     dword ptr [rsp+88h+lpOverlapped], ebx; unsigned int
0x1400320f3  xor     edx, edx; unsigned int
0x1400320f5  mov     [rsp+88h+nNumberOfBytesToWrite], 0
0x1400320fd  mov     r9d, 40000000h; unsigned int
0x140032103  mov     [rsp+88h+NumberOfBytesWritten], 0
0x14003210b  mov     r14, r8
0x14003210e  mov     qword ptr [r11-38h], 0
0x140032116  call    ?SafeCreateFile@@YAJPEAPEAXKPEB_WKKPEAU_SECURITY_ATTRIBUTES@@KKPEAX@Z; SafeCreateFile(void * *,ulong,wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong,void *)
0x14003211b  mov     rdi, [rsp+88h+hFile]
0x140032120  lea     r9d, [rbx+5]
0x140032124  xor     edx, edx
0x140032126  lea     r8d, [rbx+20h]
0x14003212a  xor     ecx, ecx
0x14003212c  mov     esi, eax
0x14003212e  test    eax, eax
0x140032130  jns     short loc_14003214C
0x140032132  lea     rax, aWinhttpSafecre; "WinHttp: SafeCreateFile"
0x140032139  mov     [rsp+88h+var_60], rax
0x14003213e  mov     dword ptr [rsp+88h+lpOverlapped], esi
0x140032142  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140032147  jmp     loc_1400321E6
0x14003214c  lea     rax, aWinhttpDownloa; "WinHttp: downloading to FILE %ls"
0x140032153  mov     qword ptr [rsp+88h+var_58], r14
0x140032158  mov     [rsp+88h+var_60], rax
0x14003215d  mov     [rsp+88h+lpOverlapped], rbx
0x140032162  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140032167  mov     ecx, 8000h; unsigned __int64
0x14003216c  call    ?SusAlloc@@YAPEAX_K@Z; SusAlloc(unsigned __int64)
0x140032171  mov     rbx, rax
0x140032174  test    rax, rax
0x140032177  jnz     short loc_1400321AC
0x140032179  mov     esi, 8007000Eh
0x14003217e  jmp     short loc_1400321E6
0x140032180  mov     r8d, [rsp+88h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x140032185  test    r8d, r8d
0x140032188  jz      loc_14003223F
0x14003218e  lea     r9, [rsp+88h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140032193  mov     [rsp+88h+lpOverlapped], 0; lpOverlapped
0x14003219c  mov     rdx, rbx; lpBuffer
0x14003219f  mov     rcx, rdi; hFile
0x1400321a2  call    cs:__imp_WriteFile
0x1400321a8  test    eax, eax
0x1400321aa  jz      short loc_1400321C8
0x1400321ac  mov     rcx, [rbp+10h]; hRequest
0x1400321b0  lea     r9, [rsp+88h+nNumberOfBytesToWrite]; lpdwNumberOfBytesRead
0x1400321b5  mov     r8d, 8000h; dwNumberOfBytesToRead
0x1400321bb  mov     rdx, rbx; lpBuffer
0x1400321be  call    cs:__imp_WinHttpReadData
0x1400321c4  test    eax, eax
0x1400321c6  jnz     short loc_140032180
0x1400321c8  call    cs:__imp_GetLastError
0x1400321ce  movzx   esi, ax
0x1400321d1  or      esi, 80070000h
0x1400321d7  test    eax, eax
0x1400321d9  cmovle  esi, eax
0x1400321dc  mov     eax, 8000FFFFh
0x1400321e1  test    esi, esi
0x1400321e3  cmovns  esi, eax
0x1400321e6  mov     rcx, rdi; hObject
0x1400321e9  xor     edi, edi
0x1400321eb  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1400321ef  jz      short loc_1400321F7
0x1400321f1  call    cs:__imp_CloseHandle
0x1400321f7  mov     rcx, r14; lpFileName
0x1400321fa  call    cs:__imp_DeleteFileW
0x140032200  test    rbx, rbx
0x140032203  jz      short loc_14003220D
0x140032205  mov     rcx, rbx; lpMem
0x140032208  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14003220d  test    rdi, rdi
0x140032210  jz      short loc_14003221B
0x140032212  mov     rcx, rdi; hObject
0x140032215  call    cs:__imp_CloseHandle
0x14003221b  mov     eax, esi
0x14003221d  mov     rcx, [rsp+88h+var_28]
0x140032222  xor     rcx, rsp; StackCookie
0x140032225  call    __security_check_cookie
0x14003222a  lea     r11, [rsp+88h+var_18]
0x14003222f  mov     rbx, [r11+28h]
0x140032233  mov     rbp, [r11+38h]
0x140032237  mov     rsp, r11
0x14003223a  pop     r14
0x14003223c  pop     rdi
0x14003223d  pop     rsi
0x14003223e  retn
0x14003223f  cmp     dword ptr [rbp+0CCh], 0
0x140032246  jl      short loc_140032205
0x140032248  lea     rdx, [rbp+0C4h]; lpCreationTime
0x14003224f  xor     r9d, r9d; lpLastWriteTime
0x140032252  xor     r8d, r8d; lpLastAccessTime
0x140032255  mov     rcx, rdi; hFile
0x140032258  call    cs:__imp_SetFileTime
0x14003225e  jmp     short loc_140032205
```
