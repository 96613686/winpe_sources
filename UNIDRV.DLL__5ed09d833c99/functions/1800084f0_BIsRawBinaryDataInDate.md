# BIsRawBinaryDataInDate

- ea: `0x1800084f0`
- end: `0x1800086c9`
- name: `BIsRawBinaryDataInDate`
- size: `473`
- prototype: `__int64 __fastcall(unsigned int *, const wchar_t *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180008c9c`

## callees

- `0x180007150`
- `0x1800084f0`
- `0x18004a674`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180008534`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800085ae`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180008534`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800085ae`
- `KERNEL32!GetFileTime` at `0x18000862c`
- `KERNEL32!GetFileTime` at `0x18000862c`
- `KERNEL32!CloseHandle` at `0x180008657`
- `KERNEL32!CloseHandle` at `0x180008657`
- `KERNEL32!CreateFileW` at `0x180008603`
- `KERNEL32!CreateFileW` at `0x180008603`
- `KERNEL32!CompareFileTime` at `0x180008682`
- `KERNEL32!CompareFileTime` at `0x180008682`

## string_xrefs

- `0x180008570`: `Raw binary data file has mismatched driver file path.`
- `0x1800086aa`: `CreateFile '%S' failed.`

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
      WriteDbgTraceErrorGpd((__int64)"BIsRawBinaryDataInDate", "Raw binary data file has mismatched driver file path.");
      return 0;
    }
    FileW = CreateFileW(v15, 0x80000000, 1u, 0, 3u, 0x100080u, 0);
    v18 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      WriteDbgTraceErrorGpd((__int64)"BIsRawBinaryDataInDate", "CreateFile '%S' failed.", v15);
LABEL_15:
      WriteDbgTraceErrorGpd((__int64)"BIsRawBinaryDataInDate", "Raw binary data file is out-of-date.");
      return 0;
    }
    if ( GetFileTime(FileW, 0, 0, &LastWriteTime) )
    {
      v19 = CompareFileTime(&LastWriteTime, (const FILETIME *)&v10[v12 + 8]) == 0;
    }
    else
    {
      v19 = 0;
      WriteDbgTraceErrorGpd((__int64)"BIsRawBinaryDataInDate", "GetFileTime '%S' failed.", v15);
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
0x1800084f0  mov     rax, rsp
0x1800084f3  mov     [rax+10h], rbx
0x1800084f7  push    rbp
0x1800084f8  push    rsi
0x1800084f9  push    rdi
0x1800084fa  push    r12
0x1800084fc  push    r13
0x1800084fe  push    r14
0x180008500  push    r15
0x180008502  sub     rsp, 40h
0x180008506  mov     r14d, [rcx+0C4h]
0x18000850d  mov     r12, rdx
0x180008510  mov     edi, [rcx+48h]
0x180008513  mov     rbx, rcx
0x180008516  mov     esi, [rcx+0C0h]
0x18000851c  mov     edx, 5Ch ; '\'; Ch
0x180008521  mov     rcx, r12; Str
0x180008524  mov     qword ptr [rax+18h], 0
0x18000852c  mov     [rsp+78h+arg_0], r14d
0x180008534  call    cs:__imp_wcsrchr
0x18000853b  nop     dword ptr [rax+rax+00h]
0x180008540  mov     rbp, rax
0x180008543  test    rax, rax
0x180008546  jz      short loc_180008583
0x180008548  sub     rbp, r12
0x18000854b  lea     r13, [rbx+rdi]
0x18000854f  sar     rbp, 1
0x180008552  lea     r15, [rbx+rsi]
0x180008556  xor     edi, edi
0x180008558  cmp     edi, r14d
0x18000855b  jnb     loc_1800086BF
0x180008561  mov     esi, edi
0x180008563  shl     rsi, 4
0x180008567  mov     eax, [rsi+r15+4]
0x18000856c  test    eax, eax
0x18000856e  jnz     short loc_18000859E
0x180008570  lea     rdx, aRawBinaryDataF; "Raw binary data file has mismatched dri"...
0x180008577  lea     rcx, aBisrawbinaryda; "BIsRawBinaryDataInDate"
0x18000857e  call    WriteDbgTraceErrorGpd
0x180008583  xor     eax, eax
0x180008585  mov     rbx, [rsp+78h+arg_8]
0x18000858d  add     rsp, 40h
0x180008591  pop     r15
0x180008593  pop     r14
0x180008595  pop     r13
0x180008597  pop     r12
0x180008599  pop     rdi
0x18000859a  pop     rsi
0x18000859b  pop     rbp
0x18000859c  retn
0x18000859e  mov     rbx, rax
0x1800085a1  add     rbx, r13
0x1800085a4  jz      short loc_180008570
0x1800085a6  mov     edx, 5Ch ; '\'; Ch
0x1800085ab  mov     rcx, rbx; Str
0x1800085ae  call    cs:__imp_wcsrchr
0x1800085b5  nop     dword ptr [rax+rax+00h]
0x1800085ba  test    rax, rax
0x1800085bd  jz      short loc_180008570
0x1800085bf  sub     rax, rbx
0x1800085c2  sar     rax, 1
0x1800085c5  cmp     eax, ebp
0x1800085c7  jnz     short loc_180008570
0x1800085c9  movsxd  r8, ebp; MaxCount
0x1800085cc  mov     rdx, rbx; String2
0x1800085cf  mov     rcx, r12; String1
0x1800085d2  call    _wcsnicmp
0x1800085d7  test    eax, eax
0x1800085d9  jnz     short loc_180008570
0x1800085db  mov     [rsp+78h+hTemplateFile], 0; hTemplateFile
0x1800085e4  lea     r8d, [rax+1]; dwShareMode
0x1800085e8  mov     [rsp+78h+dwFlagsAndAttributes], 100080h; dwFlagsAndAttributes
0x1800085f0  xor     r9d, r9d; lpSecurityAttributes
0x1800085f3  mov     edx, 80000000h; dwDesiredAccess
0x1800085f8  mov     [rsp+78h+dwCreationDisposition], 3; dwCreationDisposition
0x180008600  mov     rcx, rbx; lpFileName
0x180008603  call    cs:__imp_CreateFileW
0x18000860a  nop     dword ptr [rax+rax+00h]
0x18000860f  mov     r14, rax
0x180008612  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180008616  jz      loc_1800086A7
0x18000861c  lea     r9, [rsp+78h+LastWriteTime]; lpLastWriteTime
0x180008624  xor     r8d, r8d; lpLastAccessTime
0x180008627  xor     edx, edx; lpCreationTime
0x180008629  mov     rcx, rax; hFile
0x18000862c  call    cs:__imp_GetFileTime
0x180008633  nop     dword ptr [rax+rax+00h]
0x180008638  test    eax, eax
0x18000863a  jnz     short loc_180008673
0x18000863c  xor     esi, esi
0x18000863e  lea     rdx, aGetfiletimeSFa; "GetFileTime '%S' failed."
0x180008645  mov     r8, rbx
0x180008648  lea     rcx, aBisrawbinaryda; "BIsRawBinaryDataInDate"
0x18000864f  call    WriteDbgTraceErrorGpd
0x180008654  mov     rcx, r14; hObject
0x180008657  call    cs:__imp_CloseHandle
0x18000865e  nop     dword ptr [rax+rax+00h]
0x180008663  test    esi, esi
0x180008665  jnz     short loc_180008698
0x180008667  lea     rdx, aRawBinaryDataF_0; "Raw binary data file is out-of-date."
0x18000866e  jmp     loc_180008577
0x180008673  lea     rdx, [r15+8]
0x180008677  add     rdx, rsi; lpFileTime2
0x18000867a  lea     rcx, [rsp+78h+LastWriteTime]; lpFileTime1
0x180008682  call    cs:__imp_CompareFileTime
0x180008689  nop     dword ptr [rax+rax+00h]
0x18000868e  xor     esi, esi
0x180008690  test    eax, eax
0x180008692  setz    sil
0x180008696  jmp     short loc_180008654
0x180008698  mov     r14d, [rsp+78h+arg_0]
0x1800086a0  inc     edi
0x1800086a2  jmp     loc_180008558
0x1800086a7  mov     r8, rbx
0x1800086aa  lea     rdx, aCreatefileSFai; "CreateFile '%S' failed."
0x1800086b1  lea     rcx, aBisrawbinaryda; "BIsRawBinaryDataInDate"
0x1800086b8  call    WriteDbgTraceErrorGpd
0x1800086bd  jmp     short loc_180008667
0x1800086bf  mov     eax, 1
0x1800086c4  jmp     loc_180008585
```
