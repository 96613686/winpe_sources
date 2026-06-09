# CFBFileFormatCheck::ParseFileHeader(void)

- ea: `0x1800080dc`
- end: `0x180008221`
- name: `?ParseFileHeader@CFBFileFormatCheck@@AEAAKXZ`
- size: `325`
- prototype: `unsigned int __fastcall(CFBFileFormatCheck *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180007ed8`

## callees

- `0x1800080dc`
- `0x1800082b8`
- `0x18000d2ce`
- `0x18000d300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008121`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008121`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1800081a6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalAlloc` at `0x1800081a6`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180008117`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180008117`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180008150`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180008150`

## pseudocode

```c
unsigned int __fastcall CFBFileFormatCheck::ParseFileHeader(HANDLE *this)
{
  HANDLE v3; // rcx
  unsigned int v4; // ecx
  unsigned int v5; // eax
  HLOCAL v6; // rax
  int v7; // ecx
  __int16 v8; // dx
  int v9; // ecx
  bool v10; // zf
  DWORD NumberOfBytesRead; // [rsp+30h] [rbp-228h] BYREF
  _BYTE Buffer[26]; // [rsp+40h] [rbp-218h] BYREF
  unsigned __int16 v13; // [rsp+5Ah] [rbp-1FEh]
  __int16 v14; // [rsp+5Eh] [rbp-1FAh]
  unsigned int v15; // [rsp+6Ch] [rbp-1ECh]
  int v16; // [rsp+84h] [rbp-1D4h]
  unsigned int v17; // [rsp+88h] [rbp-1D0h]
  unsigned int v18[109]; // [rsp+8Ch] [rbp-1CCh] BYREF

  memset_0(Buffer, 0, 0x200u);
  if ( !SetFilePointerEx(*this, 0, 0, 0) )
    return GetLastError();
  v3 = *this;
  NumberOfBytesRead = 0;
  if ( !ReadFile(v3, Buffer, 0x200u, &NumberOfBytesRead, 0) )
    return GetLastError();
  if ( NumberOfBytesRead != 512 )
    return 13;
  v4 = v15;
  *((_DWORD *)this + 6) = v15;
  if ( !v4 )
    return 13;
  if ( v4 > 0xFFFFFFFA )
    return 13;
  *((_DWORD *)this + 7) = v16;
  v5 = v17;
  *((_DWORD *)this + 8) = v17;
  if ( v5 > 0xFFFFFFFA )
    return 13;
  v6 = LocalAlloc(0x40u, 4LL * (v4 + 1));
  this[5] = v6;
  if ( !v6 )
    return -2147024882;
  v7 = v13;
  v8 = v14;
  *((_WORD *)this + 18) = v13;
  v9 = v7 - 3;
  if ( v9 )
  {
    if ( v9 != 1 )
      return 13;
    v10 = v8 == 12;
  }
  else
  {
    v10 = v8 == 9;
  }
  if ( !v10 )
    return 13;
  *((_DWORD *)this + 14) = 1 << v8;
  *((_DWORD *)this + 16) = (unsigned int)(1 << v8) >> 2;
  return CFBFileFormatCheck::ParseDIFATSectorData((CFBFileFormatCheck *)this, v18, 0x6Du);
}

```

## disassembly

```asm
0x1800080dc  push    rbx
0x1800080de  sub     rsp, 250h
0x1800080e5  mov     rax, cs:__security_cookie
0x1800080ec  xor     rax, rsp
0x1800080ef  mov     [rsp+258h+var_18], rax
0x1800080f7  mov     rbx, rcx
0x1800080fa  xor     edx, edx; Val
0x1800080fc  lea     rcx, [rsp+258h+Buffer]; void *
0x180008101  mov     r8d, 200h; Size
0x180008107  call    memset_0
0x18000810c  mov     rcx, [rbx]; hFile
0x18000810f  xor     edx, edx; liDistanceToMove
0x180008111  xor     r9d, r9d; dwMoveMethod
0x180008114  xor     r8d, r8d; lpNewFilePointer
0x180008117  call    cs:__imp_SetFilePointerEx
0x18000811d  test    eax, eax
0x18000811f  jnz     short loc_18000812C
0x180008121  call    cs:__imp_GetLastError
0x180008127  jmp     loc_180008208
0x18000812c  mov     rcx, [rbx]; hFile
0x18000812f  lea     r9, [rsp+258h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180008134  mov     r8d, 200h; nNumberOfBytesToRead
0x18000813a  mov     [rsp+258h+NumberOfBytesRead], 0
0x180008142  lea     rdx, [rsp+258h+Buffer]; lpBuffer
0x180008147  mov     [rsp+258h+lpOverlapped], 0; lpOverlapped
0x180008150  call    cs:__imp_ReadFile
0x180008156  test    eax, eax
0x180008158  jz      short loc_180008121
0x18000815a  cmp     [rsp+258h+NumberOfBytesRead], 200h
0x180008162  jz      short loc_18000816E
0x180008164  mov     eax, 0Dh
0x180008169  jmp     loc_180008208
0x18000816e  mov     ecx, [rsp+258h+var_1EC]
0x180008172  mov     [rbx+18h], ecx
0x180008175  test    ecx, ecx
0x180008177  jz      short loc_180008164
0x180008179  mov     edx, 0FFFFFFFAh
0x18000817e  cmp     ecx, edx
0x180008180  ja      short loc_180008164
0x180008182  mov     eax, [rsp+258h+var_1D4]
0x180008189  mov     [rbx+1Ch], eax
0x18000818c  mov     eax, [rsp+258h+var_1D0]
0x180008193  mov     [rbx+20h], eax
0x180008196  cmp     eax, edx
0x180008198  ja      short loc_180008164
0x18000819a  lea     edx, [rcx+1]
0x18000819d  mov     ecx, 40h ; '@'; uFlags
0x1800081a2  shl     rdx, 2; uBytes
0x1800081a6  call    cs:__imp_LocalAlloc
0x1800081ac  mov     [rbx+28h], rax
0x1800081b0  test    rax, rax
0x1800081b3  jnz     short loc_1800081BC
0x1800081b5  mov     eax, 8007000Eh
0x1800081ba  jmp     short loc_180008208
0x1800081bc  movzx   ecx, [rsp+258h+var_1FE]
0x1800081c1  movzx   edx, [rsp+258h+var_1FA]
0x1800081c6  mov     [rbx+24h], cx
0x1800081ca  sub     ecx, 3
0x1800081cd  jz      short loc_1800081DA
0x1800081cf  cmp     ecx, 1
0x1800081d2  jnz     short loc_180008164
0x1800081d4  cmp     dx, 0Ch
0x1800081d8  jmp     short loc_1800081DE
0x1800081da  cmp     dx, 9
0x1800081de  jnz     short loc_180008164
0x1800081e0  mov     cl, dl
0x1800081e2  mov     eax, 1
0x1800081e7  shl     eax, cl
0x1800081e9  lea     rdx, [rsp+258h+var_1CC]; unsigned int *
0x1800081f1  mov     [rbx+38h], eax
0x1800081f4  mov     r8d, 6Dh ; 'm'; unsigned int
0x1800081fa  shr     eax, 2
0x1800081fd  mov     rcx, rbx; this
0x180008200  mov     [rbx+40h], eax
0x180008203  call    ?ParseDIFATSectorData@CFBFileFormatCheck@@AEAAKPEAKK@Z; CFBFileFormatCheck::ParseDIFATSectorData(ulong *,ulong)
0x180008208  mov     rcx, [rsp+258h+var_18]
0x180008210  xor     rcx, rsp; StackCookie
0x180008213  call    __security_check_cookie
0x180008218  add     rsp, 250h
0x18000821f  pop     rbx
0x180008220  retn
```
