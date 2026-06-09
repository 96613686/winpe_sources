# BIsRawBinaryDataInDate

- ea: `0x1800085b0`
- end: `0x180008760`
- name: `BIsRawBinaryDataInDate`
- size: `432`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180008d2c`

## callees

- `0x180007220`
- `0x1800085b0`
- `0x180049134`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800085f4`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180008667`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800085f4`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180008667`
- `KERNEL32!GetFileTime` at `0x1800086d5`
- `KERNEL32!GetFileTime` at `0x1800086d5`
- `KERNEL32!CloseHandle` at `0x1800086fa`
- `KERNEL32!CloseHandle` at `0x1800086fa`
- `KERNEL32!CreateFileW` at `0x1800086b6`
- `KERNEL32!CreateFileW` at `0x1800086b6`
- `KERNEL32!CompareFileTime` at `0x18000871f`
- `KERNEL32!CompareFileTime` at `0x18000871f`

## string_xrefs

- `0x18000862a`: `Raw binary data file has mismatched driver file path.`
- `0x180008741`: `CreateFile '%S' failed.`

## pseudocode

```c
__int64 __fastcall BIsRawBinaryDataInDate(unsigned int *a1, const wchar_t *a2)
{
  unsigned int v2; // r14d
  __int64 v4; // rdi
  __int64 v6; // rsi
  wchar_t *v7; // rax
  char *v8; // r13
  __int64 v9; // rbp
  char *v10; // r15
  unsigned int i; // edi
  __int64 v12; // rsi
  __int64 v13; // rax
  const wchar_t *v15; // rbx
  wchar_t *v16; // rax
  HANDLE FileW; // rax
  void *v18; // r14
  BOOL v19; // esi
  unsigned int v20; // [rsp+80h] [rbp+8h]
  _FILETIME LastWriteTime; // [rsp+90h] [rbp+18h] BYREF

  v2 = a1[49];
  v4 = a1[18];
  v6 = a1[48];
  LastWriteTime = 0;
  v20 = v2;
  v7 = wcsrchr(a2, 0x5Cu);
  if ( !v7 )
    return 0;
  v8 = (char *)a1 + v4;
  v9 = v7 - a2;
  v10 = (char *)a1 + v6;
  for ( i = 0; i < v2; ++i )
  {
    v12 = 16LL * i;
    v13 = *(unsigned int *)&v10[v12 + 4];
    if ( !(_DWORD)v13
      || (v15 = (const wchar_t *)&v8[v13]) == 0
      || (v16 = wcsrchr((const wchar_t *)&v8[v13], 0x5Cu)) == 0
      || (unsigned int)(v16 - v15) != (_DWORD)v9
      || wcsnicmp(a2, v15, (int)v9) )
    {
      WriteDbgTraceErrorGpd("BIsRawBinaryDataInDate", "Raw binary data file has mismatched driver file path.");
      return 0;
    }
    FileW = CreateFileW(v15, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
    v18 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      WriteDbgTraceErrorGpd("BIsRawBinaryDataInDate", "CreateFile '%S' failed.", v15);
LABEL_15:
      WriteDbgTraceErrorGpd("BIsRawBinaryDataInDate", "Raw binary data file is out-of-date.");
      return 0;
    }
    if ( GetFileTime(FileW, 0, 0, &LastWriteTime) )
    {
      v19 = CompareFileTime(&LastWriteTime, (const FILETIME *)&v10[v12 + 8]) == 0;
    }
    else
    {
      v19 = 0;
      WriteDbgTraceErrorGpd("BIsRawBinaryDataInDate", "GetFileTime '%S' failed.", v15);
    }
    CloseHandle(v18);
    if ( !v19 )
      goto LABEL_15;
    v2 = v20;
  }
  return 1;
}

```

## disassembly

```asm
0x1800085b0  mov     rax, rsp
0x1800085b3  mov     [rax+10h], rbx
0x1800085b7  push    rbp
0x1800085b8  push    rsi
0x1800085b9  push    rdi
0x1800085ba  push    r12
0x1800085bc  push    r13
0x1800085be  push    r14
0x1800085c0  push    r15
0x1800085c2  sub     rsp, 40h
0x1800085c6  mov     r14d, [rcx+0C4h]
0x1800085cd  mov     r12, rdx
0x1800085d0  mov     edi, [rcx+48h]
0x1800085d3  mov     rbx, rcx
0x1800085d6  mov     esi, [rcx+0C0h]
0x1800085dc  mov     edx, 5Ch ; '\'; Ch
0x1800085e1  mov     rcx, r12; Str
0x1800085e4  mov     qword ptr [rax+18h], 0
0x1800085ec  mov     [rsp+78h+arg_0], r14d
0x1800085f4  call    cs:__imp_wcsrchr
0x1800085fa  mov     rbp, rax
0x1800085fd  test    rax, rax
0x180008600  jz      short loc_18000863D
0x180008602  sub     rbp, r12
0x180008605  lea     r13, [rbx+rdi]
0x180008609  sar     rbp, 1
0x18000860c  lea     r15, [rbx+rsi]
0x180008610  xor     edi, edi
0x180008612  cmp     edi, r14d
0x180008615  jnb     loc_180008756
0x18000861b  mov     esi, edi
0x18000861d  shl     rsi, 4
0x180008621  mov     eax, [rsi+r15+4]
0x180008626  test    eax, eax
0x180008628  jnz     short loc_180008657
0x18000862a  lea     rdx, aRawBinaryDataF; "Raw binary data file has mismatched dri"...
0x180008631  lea     rcx, aBisrawbinaryda; "BIsRawBinaryDataInDate"
0x180008638  call    WriteDbgTraceErrorGpd
0x18000863d  xor     eax, eax
0x18000863f  mov     rbx, [rsp+78h+arg_8]
0x180008647  add     rsp, 40h
0x18000864b  pop     r15
0x18000864d  pop     r14
0x18000864f  pop     r13
0x180008651  pop     r12
0x180008653  pop     rdi
0x180008654  pop     rsi
0x180008655  pop     rbp
0x180008656  retn
0x180008657  mov     rbx, rax
0x18000865a  add     rbx, r13
0x18000865d  jz      short loc_18000862A
0x18000865f  mov     edx, 5Ch ; '\'; Ch
0x180008664  mov     rcx, rbx; Str
0x180008667  call    cs:__imp_wcsrchr
0x18000866d  test    rax, rax
0x180008670  jz      short loc_18000862A
0x180008672  sub     rax, rbx
0x180008675  sar     rax, 1
0x180008678  cmp     eax, ebp
0x18000867a  jnz     short loc_18000862A
0x18000867c  movsxd  r8, ebp; MaxCount
0x18000867f  mov     rdx, rbx; String2
0x180008682  mov     rcx, r12; String1
0x180008685  call    _wcsnicmp
0x18000868a  test    eax, eax
0x18000868c  jnz     short loc_18000862A
0x18000868e  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x180008697  lea     r8d, [rax+1]; dwShareMode
0x18000869b  mov     [rsp+78h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x1800086a3  xor     r9d, r9d; lpSecurityAttributes
0x1800086a6  mov     edx, 80000000h; dwDesiredAccess
0x1800086ab  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x1800086b3  mov     rcx, rbx; lpFileName
0x1800086b6  call    cs:__imp_CreateFileW
0x1800086bc  mov     r14, rax
0x1800086bf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800086c3  jz      short loc_18000873E
0x1800086c5  lea     r9, [rsp+78h+LastWriteTime]; lpLastWriteTime
0x1800086cd  xor     r8d, r8d; lpLastAccessTime
0x1800086d0  xor     edx, edx; lpCreationTime
0x1800086d2  mov     rcx, rax; hFile
0x1800086d5  call    cs:__imp_GetFileTime
0x1800086db  test    eax, eax
0x1800086dd  jnz     short loc_180008710
0x1800086df  xor     esi, esi
0x1800086e1  lea     rdx, aGetfiletimeSFa; "GetFileTime '%S' failed."
0x1800086e8  mov     r8, rbx
0x1800086eb  lea     rcx, aBisrawbinaryda; "BIsRawBinaryDataInDate"
0x1800086f2  call    WriteDbgTraceErrorGpd
0x1800086f7  mov     rcx, r14; hObject
0x1800086fa  call    cs:__imp_CloseHandle
0x180008700  test    esi, esi
0x180008702  jnz     short loc_18000872F
0x180008704  lea     rdx, aRawBinaryDataF_0; "Raw binary data file is out-of-date."
0x18000870b  jmp     loc_180008631
0x180008710  lea     rdx, [r15+8]
0x180008714  add     rdx, rsi; lpFileTime2
0x180008717  lea     rcx, [rsp+78h+LastWriteTime]; lpFileTime1
0x18000871f  call    cs:__imp_CompareFileTime
0x180008725  xor     esi, esi
0x180008727  test    eax, eax
0x180008729  setz    sil
0x18000872d  jmp     short loc_1800086F7
0x18000872f  mov     r14d, [rsp+78h+arg_0]
0x180008737  inc     edi
0x180008739  jmp     loc_180008612
0x18000873e  mov     r8, rbx
0x180008741  lea     rdx, aCreatefileSFai; "CreateFile '%S' failed."
0x180008748  lea     rcx, aBisrawbinaryda; "BIsRawBinaryDataInDate"
0x18000874f  call    WriteDbgTraceErrorGpd
0x180008754  jmp     short loc_180008704
0x180008756  mov     eax, 1
0x18000875b  jmp     loc_18000863F
```
