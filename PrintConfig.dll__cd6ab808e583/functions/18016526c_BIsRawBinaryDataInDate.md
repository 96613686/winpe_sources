# BIsRawBinaryDataInDate

- ea: `0x18016526c`
- end: `0x18016542f`
- name: `BIsRawBinaryDataInDate`
- size: `451`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180166c88`

## callees

- `0x1800042d4`
- `0x180162b18`
- `0x18016526c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1801652a8`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180165301`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1801652a8`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180165301`
- `KERNEL32!CreateFileW` at `0x18016535c`
- `KERNEL32!CreateFileW` at `0x18016535c`
- `KERNEL32!CloseHandle` at `0x1801653bf`
- `KERNEL32!CloseHandle` at `0x1801653bf`
- `KERNEL32!CompareFileTime` at `0x180165394`
- `KERNEL32!CompareFileTime` at `0x180165394`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18016537b`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18016537b`

## string_xrefs

- `0x180165426`: `Raw binary data file has mismatched driver file path.`
- `0x1801653e6`: `CreateFile '%S' failed.`

## pseudocode

```c
__int64 __fastcall BIsRawBinaryDataInDate(unsigned int *a1, const wchar_t *a2)
{
  __int64 v2; // rdi
  unsigned int v4; // r13d
  __int64 v6; // rsi
  wchar_t *v7; // rax
  char *v8; // rcx
  __int64 v9; // rbp
  char *v10; // r15
  unsigned int v11; // edi
  __int64 v12; // rsi
  int v13; // eax
  const wchar_t *v14; // rbx
  wchar_t *v15; // rax
  HANDLE FileW; // rax
  void *v17; // r14
  BOOL v18; // esi
  struct _FILETIME LastWriteTime; // [rsp+80h] [rbp+8h] BYREF
  char *v21; // [rsp+90h] [rbp+18h]

  v2 = a1[18];
  v4 = a1[49];
  v6 = a1[48];
  LastWriteTime = 0;
  v7 = wcsrchr(a2, 0x5Cu);
  if ( v7 )
  {
    v8 = (char *)a1 + v2;
    v9 = v7 - a2;
    v10 = (char *)a1 + v6;
    v11 = 0;
    v21 = v8;
    if ( !v4 )
      return 1;
    while ( 1 )
    {
      v12 = 16LL * v11;
      v13 = *(_DWORD *)&v10[v12 + 4];
      if ( !v13 )
        break;
      v14 = (const wchar_t *)&v8[v13];
      if ( !v14 )
        break;
      v15 = wcsrchr((const wchar_t *)&v8[v13], 0x5Cu);
      if ( !v15 || (unsigned int)(v15 - v14) != (_DWORD)v9 || wcsnicmp(a2, v14, (int)v9) )
        break;
      FileW = CreateFileW(v14, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
      v17 = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        WriteDbgTraceErrorGpd("BIsRawBinaryDataInDate", "CreateFile '%S' failed.", v14);
LABEL_16:
        WriteDbgTraceErrorGpd("BIsRawBinaryDataInDate", "Raw binary data file is out-of-date.");
        return 0;
      }
      if ( GetFileTime(FileW, 0, 0, &LastWriteTime) )
      {
        v18 = CompareFileTime(&LastWriteTime, (const FILETIME *)&v10[v12 + 8]) == 0;
      }
      else
      {
        v18 = 0;
        WriteDbgTraceErrorGpd("BIsRawBinaryDataInDate", "GetFileTime '%S' failed.", v14);
      }
      CloseHandle(v17);
      if ( !v18 )
        goto LABEL_16;
      v8 = v21;
      if ( ++v11 >= v4 )
        return 1;
    }
    WriteDbgTraceErrorGpd("BIsRawBinaryDataInDate", "Raw binary data file has mismatched driver file path.");
  }
  return 0;
}

```

## disassembly

```asm
0x18016526c  mov     rax, rsp
0x18016526f  mov     [rax+10h], rbx
0x180165273  push    rbp
0x180165274  push    rsi
0x180165275  push    rdi
0x180165276  push    r12
0x180165278  push    r13
0x18016527a  push    r14
0x18016527c  push    r15
0x18016527e  sub     rsp, 40h
0x180165282  mov     edi, [rcx+48h]
0x180165285  mov     r12, rdx
0x180165288  mov     r13d, [rcx+0C4h]
0x18016528f  mov     rbx, rcx
0x180165292  mov     esi, [rcx+0C0h]
0x180165298  mov     edx, 5Ch ; '\'; Ch
0x18016529d  mov     rcx, r12; Str
0x1801652a0  mov     qword ptr [rax+8], 0
0x1801652a8  call    cs:__imp_wcsrchr
0x1801652ae  mov     rbp, rax
0x1801652b1  test    rax, rax
0x1801652b4  jz      loc_18016540C
0x1801652ba  sub     rbp, r12
0x1801652bd  lea     rcx, [rbx+rdi]
0x1801652c1  sar     rbp, 1
0x1801652c4  lea     r15, [rbx+rsi]
0x1801652c8  xor     edi, edi
0x1801652ca  mov     [rsp+78h+arg_10], rcx
0x1801652d2  test    r13d, r13d
0x1801652d5  jz      loc_1801653DC
0x1801652db  mov     esi, edi
0x1801652dd  shl     rsi, 4
0x1801652e1  mov     eax, [rsi+r15+4]
0x1801652e6  test    eax, eax
0x1801652e8  jz      loc_180165426
0x1801652ee  mov     ebx, eax
0x1801652f0  add     rbx, rcx
0x1801652f3  jz      loc_180165426
0x1801652f9  mov     edx, 5Ch ; '\'; Ch
0x1801652fe  mov     rcx, rbx; Str
0x180165301  call    cs:__imp_wcsrchr
0x180165307  test    rax, rax
0x18016530a  jz      loc_180165426
0x180165310  sub     rax, rbx
0x180165313  sar     rax, 1
0x180165316  cmp     eax, ebp
0x180165318  jnz     loc_180165426
0x18016531e  movsxd  r8, ebp; MaxCount
0x180165321  mov     rdx, rbx; String2
0x180165324  mov     rcx, r12; String1
0x180165327  call    _wcsnicmp
0x18016532c  test    eax, eax
0x18016532e  jnz     loc_180165426
0x180165334  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18016533d  lea     r8d, [rax+1]; dwShareMode
0x180165341  mov     [rsp+78h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x180165349  xor     r9d, r9d; lpSecurityAttributes
0x18016534c  mov     edx, 80000000h; dwDesiredAccess
0x180165351  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180165359  mov     rcx, rbx; lpFileName
0x18016535c  call    cs:__imp_CreateFileW
0x180165362  mov     r14, rax
0x180165365  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180165369  jz      short loc_1801653E3
0x18016536b  lea     r9, [rsp+78h+LastWriteTime]; lpLastWriteTime
0x180165373  xor     r8d, r8d; lpLastAccessTime
0x180165376  xor     edx, edx; lpCreationTime
0x180165378  mov     rcx, rax; hFile
0x18016537b  call    cs:__imp_GetFileTime
0x180165381  test    eax, eax
0x180165383  jz      short loc_1801653A4
0x180165385  lea     rdx, [r15+8]
0x180165389  add     rdx, rsi; lpFileTime2
0x18016538c  lea     rcx, [rsp+78h+LastWriteTime]; lpFileTime1
0x180165394  call    cs:__imp_CompareFileTime
0x18016539a  xor     esi, esi
0x18016539c  test    eax, eax
0x18016539e  setz    sil
0x1801653a2  jmp     short loc_1801653BC
0x1801653a4  xor     esi, esi
0x1801653a6  lea     rdx, aGetfiletimeSFa; "GetFileTime '%S' failed."
0x1801653ad  mov     r8, rbx
0x1801653b0  lea     rcx, aBisrawbinaryda; "BIsRawBinaryDataInDate"
0x1801653b7  call    WriteDbgTraceErrorGpd
0x1801653bc  mov     rcx, r14; hObject
0x1801653bf  call    cs:__imp_CloseHandle
0x1801653c5  test    esi, esi
0x1801653c7  jz      short loc_1801653F9
0x1801653c9  mov     rcx, [rsp+78h+arg_10]
0x1801653d1  inc     edi
0x1801653d3  cmp     edi, r13d
0x1801653d6  jb      loc_1801652DB
0x1801653dc  mov     eax, 1
0x1801653e1  jmp     short loc_18016540E
0x1801653e3  mov     r8, rbx
0x1801653e6  lea     rdx, aCreatefileSFai; "CreateFile '%S' failed."
0x1801653ed  lea     rcx, aBisrawbinaryda; "BIsRawBinaryDataInDate"
0x1801653f4  call    WriteDbgTraceErrorGpd
0x1801653f9  lea     rdx, aRawBinaryDataF_0; "Raw binary data file is out-of-date."
0x180165400  lea     rcx, aBisrawbinaryda; "BIsRawBinaryDataInDate"
0x180165407  call    WriteDbgTraceErrorGpd
0x18016540c  xor     eax, eax
0x18016540e  mov     rbx, [rsp+78h+arg_8]
0x180165416  add     rsp, 40h
0x18016541a  pop     r15
0x18016541c  pop     r14
0x18016541e  pop     r13
0x180165420  pop     r12
0x180165422  pop     rdi
0x180165423  pop     rsi
0x180165424  pop     rbp
0x180165425  retn
0x180165426  lea     rdx, aRawBinaryDataF; "Raw binary data file has mismatched dri"...
0x18016542d  jmp     short loc_180165400
```
