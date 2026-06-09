# BIsRawBinaryDataInDate

- ea: `0x18016cb30`
- end: `0x18016cd1c`
- name: `BIsRawBinaryDataInDate`
- size: `492`
- prototype: `__int64 __fastcall(unsigned int *, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18016e680`

## callees

- `0x180004414`
- `0x18016a374`
- `0x18016cb30`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18016cb6c`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18016cbcb`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18016cb6c`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x18016cbcb`
- `KERNEL32!CreateFileW` at `0x18016cc2c`
- `KERNEL32!CreateFileW` at `0x18016cc2c`
- `KERNEL32!CloseHandle` at `0x18016cca5`
- `KERNEL32!CloseHandle` at `0x18016cca5`
- `KERNEL32!CompareFileTime` at `0x18016cc74`
- `KERNEL32!CompareFileTime` at `0x18016cc74`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18016cc55`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x18016cc55`

## string_xrefs

- `0x18016cd13`: `Raw binary data file has mismatched driver file path.`
- `0x18016ccd2`: `CreateFile '%S' failed.`

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
0x18016cb30  mov     rax, rsp
0x18016cb33  mov     [rax+10h], rbx
0x18016cb37  push    rbp
0x18016cb38  push    rsi
0x18016cb39  push    rdi
0x18016cb3a  push    r12
0x18016cb3c  push    r13
0x18016cb3e  push    r14
0x18016cb40  push    r15
0x18016cb42  sub     rsp, 40h
0x18016cb46  mov     edi, [rcx+48h]
0x18016cb49  mov     r12, rdx
0x18016cb4c  mov     r13d, [rcx+0C4h]
0x18016cb53  mov     rbx, rcx
0x18016cb56  mov     esi, [rcx+0C0h]
0x18016cb5c  mov     edx, 5Ch ; '\'; Ch
0x18016cb61  mov     rcx, r12; Str
0x18016cb64  mov     qword ptr [rax+8], 0
0x18016cb6c  call    cs:__imp_wcsrchr
0x18016cb73  nop     dword ptr [rax+rax+00h]
0x18016cb78  mov     rbp, rax
0x18016cb7b  test    rax, rax
0x18016cb7e  jz      loc_18016CCF8
0x18016cb84  sub     rbp, r12
0x18016cb87  lea     rcx, [rbx+rdi]
0x18016cb8b  sar     rbp, 1
0x18016cb8e  lea     r15, [rbx+rsi]
0x18016cb92  xor     edi, edi
0x18016cb94  mov     [rsp+78h+arg_10], rcx
0x18016cb9c  test    r13d, r13d
0x18016cb9f  jz      loc_18016CCC8
0x18016cba5  mov     esi, edi
0x18016cba7  shl     rsi, 4
0x18016cbab  mov     eax, [rsi+r15+4]
0x18016cbb0  test    eax, eax
0x18016cbb2  jz      loc_18016CD13
0x18016cbb8  mov     ebx, eax
0x18016cbba  add     rbx, rcx
0x18016cbbd  jz      loc_18016CD13
0x18016cbc3  mov     edx, 5Ch ; '\'; Ch
0x18016cbc8  mov     rcx, rbx; Str
0x18016cbcb  call    cs:__imp_wcsrchr
0x18016cbd2  nop     dword ptr [rax+rax+00h]
0x18016cbd7  test    rax, rax
0x18016cbda  jz      loc_18016CD13
0x18016cbe0  sub     rax, rbx
0x18016cbe3  sar     rax, 1
0x18016cbe6  cmp     eax, ebp
0x18016cbe8  jnz     loc_18016CD13
0x18016cbee  movsxd  r8, ebp; MaxCount
0x18016cbf1  mov     rdx, rbx; String2
0x18016cbf4  mov     rcx, r12; String1
0x18016cbf7  call    _wcsnicmp
0x18016cbfc  test    eax, eax
0x18016cbfe  jnz     loc_18016CD13
0x18016cc04  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x18016cc0d  lea     r8d, [rax+1]; dwShareMode
0x18016cc11  mov     [rsp+78h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x18016cc19  xor     r9d, r9d; lpSecurityAttributes
0x18016cc1c  mov     edx, 80000000h; dwDesiredAccess
0x18016cc21  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x18016cc29  mov     rcx, rbx; lpFileName
0x18016cc2c  call    cs:__imp_CreateFileW
0x18016cc33  nop     dword ptr [rax+rax+00h]
0x18016cc38  mov     r14, rax
0x18016cc3b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18016cc3f  jz      loc_18016CCCF
0x18016cc45  lea     r9, [rsp+78h+LastWriteTime]; lpLastWriteTime
0x18016cc4d  xor     r8d, r8d; lpLastAccessTime
0x18016cc50  xor     edx, edx; lpCreationTime
0x18016cc52  mov     rcx, rax; hFile
0x18016cc55  call    cs:__imp_GetFileTime
0x18016cc5c  nop     dword ptr [rax+rax+00h]
0x18016cc61  test    eax, eax
0x18016cc63  jz      short loc_18016CC8A
0x18016cc65  lea     rdx, [r15+8]
0x18016cc69  add     rdx, rsi; lpFileTime2
0x18016cc6c  lea     rcx, [rsp+78h+LastWriteTime]; lpFileTime1
0x18016cc74  call    cs:__imp_CompareFileTime
0x18016cc7b  nop     dword ptr [rax+rax+00h]
0x18016cc80  xor     esi, esi
0x18016cc82  test    eax, eax
0x18016cc84  setz    sil
0x18016cc88  jmp     short loc_18016CCA2
0x18016cc8a  xor     esi, esi
0x18016cc8c  lea     rdx, aGetfiletimeSFa; "GetFileTime '%S' failed."
0x18016cc93  mov     r8, rbx
0x18016cc96  lea     rcx, aBisrawbinaryda; "BIsRawBinaryDataInDate"
0x18016cc9d  call    WriteDbgTraceErrorGpd
0x18016cca2  mov     rcx, r14; hObject
0x18016cca5  call    cs:__imp_CloseHandle
0x18016ccac  nop     dword ptr [rax+rax+00h]
0x18016ccb1  test    esi, esi
0x18016ccb3  jz      short loc_18016CCE5
0x18016ccb5  mov     rcx, [rsp+78h+arg_10]
0x18016ccbd  inc     edi
0x18016ccbf  cmp     edi, r13d
0x18016ccc2  jb      loc_18016CBA5
0x18016ccc8  mov     eax, 1
0x18016cccd  jmp     short loc_18016CCFA
0x18016cccf  mov     r8, rbx
0x18016ccd2  lea     rdx, aCreatefileSFai; "CreateFile '%S' failed."
0x18016ccd9  lea     rcx, aBisrawbinaryda; "BIsRawBinaryDataInDate"
0x18016cce0  call    WriteDbgTraceErrorGpd
0x18016cce5  lea     rdx, aRawBinaryDataF_0; "Raw binary data file is out-of-date."
0x18016ccec  lea     rcx, aBisrawbinaryda; "BIsRawBinaryDataInDate"
0x18016ccf3  call    WriteDbgTraceErrorGpd
0x18016ccf8  xor     eax, eax
0x18016ccfa  mov     rbx, [rsp+78h+arg_8]
0x18016cd02  add     rsp, 40h
0x18016cd06  pop     r15
0x18016cd08  pop     r14
0x18016cd0a  pop     r13
0x18016cd0c  pop     r12
0x18016cd0e  pop     rdi
0x18016cd0f  pop     rsi
0x18016cd10  pop     rbp
0x18016cd11  retn
0x18016cd13  lea     rdx, aRawBinaryDataF; "Raw binary data file has mismatched dri"...
0x18016cd1a  jmp     short loc_18016CCEC
```
