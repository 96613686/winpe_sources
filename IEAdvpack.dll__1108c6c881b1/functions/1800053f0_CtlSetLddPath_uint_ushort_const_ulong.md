# CtlSetLddPath(uint,ushort const *,ulong)

- ea: `0x1800053f0`
- end: `0x18000557e`
- name: `?CtlSetLddPath@@YAJIPEBGK@Z`
- size: `398`
- prototype: `__int64 __fastcall(DWORD Id, const unsigned __int16 *, char)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000a61c`

## callees

- `0x1800022bc`
- `0x1800053f0`
- `0x180008a6c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180005442`
- `KERNEL32!GetLastError` at `0x1800054b2`
- `KERNEL32!GetLastError` at `0x180005522`
- `KERNEL32!GetLastError` at `0x180005442`
- `KERNEL32!GetLastError` at `0x1800054b2`
- `KERNEL32!GetLastError` at `0x180005522`
- `KERNEL32!LocalFree` at `0x180005567`
- `KERNEL32!LocalFree` at `0x180005567`
- `KERNEL32!LocalAlloc` at `0x180005434`
- `KERNEL32!LocalAlloc` at `0x180005434`
- `KERNEL32!GetShortPathNameW` at `0x1800054a8`
- `KERNEL32!GetShortPathNameW` at `0x1800054a8`
- `SETUPAPI!SetupSetDirectoryIdW` at `0x180005518`
- `SETUPAPI!SetupSetDirectoryIdW` at `0x180005518`

## pseudocode

```c
__int64 __fastcall CtlSetLddPath(DWORD Id, const unsigned __int16 *a2, char a3)
{
  __int64 v3; // rax
  unsigned __int64 v7; // rax
  DWORD v8; // ebx
  WCHAR *v9; // rax
  WCHAR *v10; // rdi
  signed int v11; // eax
  signed int v12; // ebx
  signed int LastError; // eax
  UINT v14; // edx
  const unsigned __int16 *v15; // r8
  bool v16; // sf

  v3 = -1;
  do
    ++v3;
  while ( a2[v3] );
  v7 = v3 + 1;
  v8 = 260;
  if ( v7 >= 0x104 )
    v8 = v7;
  v9 = (WCHAR *)LocalAlloc(0x40u, 2LL * v8);
  v10 = v9;
  if ( v9 )
  {
    if ( dword_1800257F8 == 1 && (a3 & 1) != 0 || (a3 & 4) != 0 && !ctx )
    {
      if ( !GetShortPathNameW(a2, v9, v8) )
      {
        LastError = GetLastError();
        v12 = LastError;
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
        v14 = 1122;
        v15 = 0;
LABEL_17:
        MsgBox2Param(hWnd, v14, v15, 0, 0x10u, 0);
LABEL_30:
        LocalFree(v10);
        return (unsigned int)v12;
      }
    }
    else
    {
      StringCchCopyW(v9, v8, a2);
    }
    if ( dword_1800257F8 == 1 )
    {
      v12 = -2147467259;
      goto LABEL_30;
    }
    if ( SetupSetDirectoryIdW(InfHandle, Id, v10) )
    {
      v12 = 0;
      goto LABEL_30;
    }
    v12 = GetLastError();
    if ( (v12 & 0xE0000000) == 0xE0000000 )
    {
      v12 = (unsigned __int16)v12 | 0x800F0000;
    }
    else
    {
      v16 = v12 < 0;
      if ( v12 <= 0 )
      {
LABEL_27:
        if ( !v16 )
          goto LABEL_30;
        v15 = v10;
        v14 = 1113;
        goto LABEL_17;
      }
      v12 = (unsigned __int16)v12 | 0x80070000;
    }
    v16 = v12 < 0;
    goto LABEL_27;
  }
  v11 = GetLastError();
  v12 = v11;
  if ( v11 > 0 )
    v12 = (unsigned __int16)v11 | 0x80070000;
  MsgBox2Param(hWnd, 0x44Eu, 0, 0, 0x10u, 0);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800053f0  push    rbx
0x1800053f2  push    rbp
0x1800053f3  push    rsi
0x1800053f4  push    rdi
0x1800053f5  push    r12
0x1800053f7  push    r14
0x1800053f9  push    r15
0x1800053fb  sub     rsp, 30h
0x1800053ff  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005403  mov     ebp, r8d
0x180005406  xor     r12d, r12d
0x180005409  mov     rsi, rdx
0x18000540c  mov     r15d, ecx
0x18000540f  inc     rax
0x180005412  cmp     [rdx+rax*2], r12w
0x180005417  jnz     short loc_18000540F
0x180005419  inc     rax
0x18000541c  mov     ebx, 104h
0x180005421  cmp     rax, rbx
0x180005424  jb      short loc_180005428
0x180005426  mov     ebx, eax
0x180005428  mov     r14d, ebx
0x18000542b  mov     ecx, 40h ; '@'; uFlags
0x180005430  lea     rdx, [r14+r14]; uBytes
0x180005434  call    cs:__imp_LocalAlloc
0x18000543a  mov     rdi, rax
0x18000543d  test    rax, rax
0x180005440  jnz     short loc_180005480
0x180005442  call    cs:__imp_GetLastError
0x180005448  mov     ebx, eax
0x18000544a  test    eax, eax
0x18000544c  jle     short loc_180005457
0x18000544e  movzx   ebx, ax
0x180005451  or      ebx, 80070000h
0x180005457  mov     rcx, cs:hWnd; hWnd
0x18000545e  xor     r9d, r9d; unsigned __int16 *
0x180005461  mov     [rsp+68h+var_40], r12d; unsigned int
0x180005466  xor     r8d, r8d; unsigned __int16 *
0x180005469  mov     edx, 44Eh; uID
0x18000546e  mov     [rsp+68h+var_48], 10h; unsigned int
0x180005476  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z
0x18000547b  jmp     loc_18000556D
0x180005480  cmp     cs:dword_1800257F8, 1
0x180005487  jnz     short loc_18000548F
0x180005489  test    bpl, 1
0x18000548d  jnz     short loc_18000549F
0x18000548f  test    bpl, 4
0x180005493  jz      short loc_1800054ED
0x180005495  cmp     cs:?ctx@@3UADVCONTEXTW@@A, r12w
0x18000549d  jnz     short loc_1800054ED
0x18000549f  mov     r8d, ebx; cchBuffer
0x1800054a2  mov     rdx, rdi; lpszShortPath
0x1800054a5  mov     rcx, rsi; lpszLongPath
0x1800054a8  call    cs:__imp_GetShortPathNameW
0x1800054ae  test    eax, eax
0x1800054b0  jnz     short loc_1800054FB
0x1800054b2  call    cs:__imp_GetLastError
0x1800054b8  mov     ebx, eax
0x1800054ba  test    eax, eax
0x1800054bc  jle     short loc_1800054C7
0x1800054be  movzx   ebx, ax
0x1800054c1  or      ebx, 80070000h
0x1800054c7  xor     r9d, r9d; unsigned __int16 *
0x1800054ca  mov     edx, 462h; uID
0x1800054cf  xor     r8d, r8d; unsigned __int16 *
0x1800054d2  mov     rcx, cs:hWnd; hWnd
0x1800054d9  mov     [rsp+68h+var_40], r12d; unsigned int
0x1800054de  mov     [rsp+68h+var_48], 10h; unsigned int
0x1800054e6  call    ?MsgBox2Param@@YAHPEAUHWND__@@IPEBG1II@Z
0x1800054eb  jmp     short loc_180005564
0x1800054ed  mov     r8, rsi; unsigned __int16 *
0x1800054f0  mov     rdx, r14; unsigned __int64
0x1800054f3  mov     rcx, rdi; unsigned __int16 *
0x1800054f6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z
0x1800054fb  cmp     cs:dword_1800257F8, 1
0x180005502  jnz     short loc_18000550B
0x180005504  mov     ebx, 80004005h
0x180005509  jmp     short loc_180005564
0x18000550b  mov     rcx, cs:InfHandle; InfHandle
0x180005512  mov     r8, rdi; Directory
0x180005515  mov     edx, r15d; Id
0x180005518  call    cs:__imp_SetupSetDirectoryIdW
0x18000551e  test    eax, eax
0x180005520  jnz     short loc_180005561
0x180005522  call    cs:__imp_GetLastError
0x180005528  mov     ecx, 0E0000000h
0x18000552d  mov     ebx, eax
0x18000552f  and     eax, ecx
0x180005531  cmp     eax, ecx
0x180005533  jnz     short loc_180005540
0x180005535  movzx   ebx, bx
0x180005538  or      ebx, 800F0000h
0x18000553e  jmp     short loc_18000554D
0x180005540  test    ebx, ebx
0x180005542  jle     short loc_18000554F
0x180005544  movzx   ebx, bx
0x180005547  or      ebx, 80070000h
0x18000554d  test    ebx, ebx
0x18000554f  jns     short loc_180005564
0x180005551  xor     r9d, r9d
0x180005554  mov     r8, rdi
0x180005557  mov     edx, 459h
0x18000555c  jmp     loc_1800054D2
0x180005561  mov     ebx, r12d
0x180005564  mov     rcx, rdi; hMem
0x180005567  call    cs:__imp_LocalFree
0x18000556d  mov     eax, ebx
0x18000556f  add     rsp, 30h
0x180005573  pop     r15
0x180005575  pop     r14
0x180005577  pop     r12
0x180005579  pop     rdi
0x18000557a  pop     rsi
0x18000557b  pop     rbp
0x18000557c  pop     rbx
0x18000557d  retn
```
