# GetFilePatchSignatureW

- ea: `0x1800043e0`
- end: `0x180004518`
- name: `GetFilePatchSignatureW`
- size: `312`
- prototype: `BOOL __stdcall(LPCWSTR FileName, ULONG OptionFlags, PVOID OptionData, ULONG IgnoreRangeCount, PPATCH_IGNORE_RANGE IgnoreRangeArray, ULONG RetainRangeCount, PPATCH_RETAIN_RANGE RetainRangeArray, ULONG SignatureBufferSize, LPWSTR SignatureBuffer)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callees

- `0x180001400`
- `0x180004310`
- `0x1800043e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800044c0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800044c0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004444`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180004444`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044ef`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800044df`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800044df`

## pseudocode

```c
BOOL __stdcall GetFilePatchSignatureW(
        LPCWSTR FileName,
        ULONG OptionFlags,
        PVOID OptionData,
        ULONG IgnoreRangeCount,
        PPATCH_IGNORE_RANGE IgnoreRangeArray,
        ULONG RetainRangeCount,
        PPATCH_RETAIN_RANGE RetainRangeArray,
        ULONG SignatureBufferSize,
        LPWSTR SignatureBuffer)
{
  _BOOL8 v9; // rbx
  HANDLE FileW; // rdi
  unsigned __int64 v14; // rcx
  __int64 v15; // rax
  CHAR MultiByteStr[40]; // [rsp+50h] [rbp-78h] BYREF

  LODWORD(v9) = 0;
  FileW = CreateFileW(FileName, 0x80000000, 3u, 0, 3u, 0x8000000u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
    LODWORD(v9) = GetFilePatchSignatureByHandle(
                    FileW,
                    OptionFlags,
                    OptionData,
                    IgnoreRangeCount,
                    IgnoreRangeArray,
                    RetainRangeCount,
                    RetainRangeArray,
                    0x28u,
                    MultiByteStr);
    if ( v9 )
    {
      v14 = SignatureBufferSize >> 1;
      v15 = -1;
      do
        ++v15;
      while ( MultiByteStr[v15] );
      if ( v14 >= v15 + 1 )
      {
        v9 = MultiByteToWideChar(0, 1u, MultiByteStr, -1, SignatureBuffer, v14) != 0;
      }
      else
      {
        SetLastError(0x7Au);
        LODWORD(v9) = 0;
      }
    }
    CloseHandle(FileW);
  }
  return v9;
}

```

## disassembly

```asm
0x1800043e0  push    rbx
0x1800043e2  push    rbp
0x1800043e3  push    rsi
0x1800043e4  push    rdi
0x1800043e5  push    r12
0x1800043e7  push    r13
0x1800043e9  push    r14
0x1800043eb  push    r15
0x1800043ed  sub     rsp, 88h
0x1800043f4  mov     rax, cs:__security_cookie
0x1800043fb  xor     rax, rsp
0x1800043fe  mov     [rsp+0C8h+var_50], rax
0x180004403  mov     r15, [rsp+0C8h+IgnoreRangeArray]
0x18000440b  xor     ebx, ebx
0x18000440d  mov     r12, [rsp+0C8h+RetainRangeArray]
0x180004415  mov     rbp, r8
0x180004418  mov     r13, [rsp+0C8h+SignatureBuffer]
0x180004420  mov     esi, r9d
0x180004423  mov     r14d, edx
0x180004426  mov     [rsp+0C8h+hTemplateFile], rbx; hTemplateFile
0x18000442b  lea     r8d, [rbx+3]; dwShareMode
0x18000442f  mov     [rsp+0C8h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x180004437  xor     r9d, r9d; lpSecurityAttributes
0x18000443a  mov     [rsp+0C8h+dwCreationDisposition], r8d; dwCreationDisposition
0x18000443f  mov     edx, 80000000h; dwDesiredAccess
0x180004444  call    cs:__imp_CreateFileW
0x18000444a  mov     rdi, rax
0x18000444d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004451  jz      loc_1800044F5
0x180004457  lea     rax, [rsp+0C8h+MultiByteStr]
0x18000445c  mov     r9d, esi; IgnoreRangeCount
0x18000445f  mov     [rsp+0C8h+var_88], rax; SignatureBuffer
0x180004464  mov     r8, rbp; OptionData
0x180004467  mov     eax, [rsp+0C8h+RetainRangeCount]
0x18000446e  mov     edx, r14d; OptionFlags
0x180004471  mov     [rsp+0C8h+var_90], 28h ; '('; SignatureBufferSize
0x180004479  mov     rcx, rdi; FileHandle
0x18000447c  mov     [rsp+0C8h+hTemplateFile], r12; RetainRangeArray
0x180004481  mov     [rsp+0C8h+dwFlagsAndAttributes], eax; RetainRangeCount
0x180004485  mov     qword ptr [rsp+0C8h+dwCreationDisposition], r15; IgnoreRangeArray
0x18000448a  call    GetFilePatchSignatureByHandle
0x18000448f  mov     ebx, eax
0x180004491  test    eax, eax
0x180004493  jz      short loc_1800044EC
0x180004495  mov     ecx, [rsp+0C8h+SignatureBufferSize]
0x18000449c  lea     rdx, [rsp+0C8h+MultiByteStr]
0x1800044a1  shr     ecx, 1
0x1800044a3  or      r9, 0FFFFFFFFFFFFFFFFh; cbMultiByte
0x1800044a7  mov     rax, r9
0x1800044aa  inc     rax
0x1800044ad  cmp     byte ptr [rdx+rax], 0
0x1800044b1  jnz     short loc_1800044AA
0x1800044b3  inc     rax
0x1800044b6  cmp     rcx, rax
0x1800044b9  jnb     short loc_1800044CA
0x1800044bb  mov     ecx, 7Ah ; 'z'; dwErrCode
0x1800044c0  call    cs:__imp_SetLastError
0x1800044c6  xor     ebx, ebx
0x1800044c8  jmp     short loc_1800044EC
0x1800044ca  mov     [rsp+0C8h+dwFlagsAndAttributes], ecx; cchWideChar
0x1800044ce  lea     r8, [rsp+0C8h+MultiByteStr]; lpMultiByteStr
0x1800044d3  xor     ecx, ecx; CodePage
0x1800044d5  mov     qword ptr [rsp+0C8h+dwCreationDisposition], r13; lpWideCharStr
0x1800044da  mov     edx, 1; dwFlags
0x1800044df  call    cs:__imp_MultiByteToWideChar
0x1800044e5  xor     ebx, ebx
0x1800044e7  test    eax, eax
0x1800044e9  setnz   bl
0x1800044ec  mov     rcx, rdi; hObject
0x1800044ef  call    cs:__imp_CloseHandle
0x1800044f5  mov     eax, ebx
0x1800044f7  mov     rcx, [rsp+0C8h+var_50]
0x1800044fc  xor     rcx, rsp; StackCookie
0x1800044ff  call    __security_check_cookie
0x180004504  add     rsp, 88h
0x18000450b  pop     r15
0x18000450d  pop     r14
0x18000450f  pop     r13
0x180004511  pop     r12
0x180004513  pop     rdi
0x180004514  pop     rsi
0x180004515  pop     rbp
0x180004516  pop     rbx
0x180004517  retn
```
