# UtGetHEMFFromEMFStm(IStream *,ulong *,HENHMETAFILE__ * *)

- ea: `0x18009e360`
- end: `0x18009e450`
- name: `?UtGetHEMFFromEMFStm@@YAJPEAUIStream@@PEAKPEAPEAUHENHMETAFILE__@@@Z`
- size: `240`
- prototype: `HRESULT __fastcall(IStream *lpstream, unsigned int *pdwSize, HENHMETAFILE__ **lphPres)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18009db60`

## callees

- `0x18000b2d4`
- `0x18004188c`
- `0x18009e360`

## import_xrefs

- `KERNELBASE!GlobalAlloc` at `0x18009e38f`
- `KERNELBASE!GlobalAlloc` at `0x18009e38f`
- `KERNELBASE!GlobalFree` at `0x18009e3cd`
- `KERNELBASE!GlobalFree` at `0x18009e3f7`
- `KERNELBASE!GlobalFree` at `0x18009e3cd`
- `KERNELBASE!GlobalFree` at `0x18009e3f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e408`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e42d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e408`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e42d`
- `GDI32!DeleteDC` at `0x18009e3ee`
- `GDI32!DeleteDC` at `0x18009e3ee`
- `GDI32!CreateCompatibleDC` at `0x18009e3b7`
- `GDI32!CreateCompatibleDC` at `0x18009e3b7`
- `GDI32!GetEnhMetaFileBits` at `0x18009e421`
- `GDI32!GetEnhMetaFileBits` at `0x18009e421`
- `GDI32!SetWinMetaFileBits` at `0x18009e3e2`
- `GDI32!SetWinMetaFileBits` at `0x18009e3e2`

## pseudocode

```c
__int64 __fastcall UtGetHEMFFromEMFStm(IStream *lpstream, unsigned int *pdwSize, HENHMETAFILE__ **lphPres)
{
  unsigned __int64 v4; // rbx
  BYTE *v7; // rax
  BYTE *v8; // rdi
  unsigned int v9; // ebx
  HDC CompatibleDC; // rax
  HDC v11; // rbp
  signed int LastError; // eax
  UINT EnhMetaFileBits; // eax
  signed int v15; // eax

  *lphPres = 0;
  v4 = *pdwSize;
  if ( v4 < GetSafeAllocSize() )
  {
    v7 = (BYTE *)GlobalAlloc(0, (unsigned int)v4);
    v8 = v7;
    if ( v7 )
    {
      v9 = StRead(lpstream, v7, *pdwSize);
      if ( (v9 & 0x80000000) == 0 )
      {
        CompatibleDC = CreateCompatibleDC(0);
        v11 = CompatibleDC;
        if ( CompatibleDC )
        {
          *lphPres = SetWinMetaFileBits(*pdwSize, v8, CompatibleDC, 0);
          DeleteDC(v11);
          GlobalFree(v8);
          if ( !*lphPres )
          {
            LastError = GetLastError();
            v9 = LastError;
            if ( LastError > 0 )
              v9 = (unsigned __int16)LastError | 0x80070000;
          }
          EnhMetaFileBits = GetEnhMetaFileBits(*lphPres, 0, 0);
          *pdwSize = EnhMetaFileBits;
          if ( !EnhMetaFileBits )
          {
            v15 = GetLastError();
            v9 = v15;
            if ( v15 > 0 )
              return (unsigned __int16)v15 | 0x80070000;
          }
          return v9;
        }
        v9 = -2147467259;
      }
      GlobalFree(v8);
      return v9;
    }
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18009e360  push    rbx
0x18009e362  push    rbp
0x18009e363  push    rsi
0x18009e364  push    rdi
0x18009e365  push    r14
0x18009e367  sub     rsp, 20h
0x18009e36b  mov     qword ptr [lphPres], 0
0x18009e372  mov     r14, lphPres
0x18009e375  mov     ebx, [pdwSize]
0x18009e377  mov     rsi, pdwSize
0x18009e37a  mov     rbp, lpstream
0x18009e37d  call    GetSafeAllocSize
0x18009e382  cmp     rbx, rax
0x18009e385  jnb     loc_18009E440
0x18009e38b  mov     edx, ebx; dwBytes
0x18009e38d  xor     ecx, ecx; uFlags
0x18009e38f  call    cs:__imp_GlobalAlloc
0x18009e395  mov     rdi, rax
0x18009e398  test    rax, rax
0x18009e39b  jz      loc_18009E440
0x18009e3a1  mov     r8d, [rsi]; requestedByteCount
0x18009e3a4  mov     pdwSize, rax; buffer
0x18009e3a7  mov     lpstream, rbp; stream
0x18009e3aa  call    ?StRead@@YAJPEAUIStream@@PEAXK@Z; StRead(IStream *,void *,ulong)
0x18009e3af  mov     ebx, eax
0x18009e3b1  test    eax, eax
0x18009e3b3  js      short loc_18009E3CA
0x18009e3b5  xor     ecx, ecx; hdc
0x18009e3b7  call    cs:__imp_CreateCompatibleDC
0x18009e3bd  mov     rbp, rax
0x18009e3c0  test    rax, rax
0x18009e3c3  jnz     short loc_18009E3D7
0x18009e3c5  mov     ebx, 80004005h
0x18009e3ca  mov     lpstream, rdi; hMem
0x18009e3cd  call    cs:__imp_GlobalFree
0x18009e3d3  mov     eax, ebx
0x18009e3d5  jmp     short loc_18009E445
0x18009e3d7  mov     ecx, [rsi]; nSize
0x18009e3d9  xor     r9d, r9d; lpMFP
0x18009e3dc  mov     lphPres, rbp; hdcRef
0x18009e3df  mov     pdwSize, rdi; lpMeta16Data
0x18009e3e2  call    cs:__imp_SetWinMetaFileBits
0x18009e3e8  mov     lpstream, rbp; hdc
0x18009e3eb  mov     [r14], rax
0x18009e3ee  call    cs:__imp_DeleteDC
0x18009e3f4  mov     lpstream, rdi; hMem
0x18009e3f7  call    cs:__imp_GlobalFree
0x18009e3fd  cmp     qword ptr [r14], 0
0x18009e401  mov     edi, 80070000h
0x18009e406  jnz     short loc_18009E419
0x18009e408  call    cs:__imp_GetLastError
0x18009e40e  mov     ebx, eax
0x18009e410  test    eax, eax
0x18009e412  jle     short loc_18009E419
0x18009e414  movzx   ebx, ax
0x18009e417  or      ebx, edi
0x18009e419  mov     lpstream, [r14]; hEMF
0x18009e41c  xor     r8d, r8d; lpData
0x18009e41f  xor     edx, edx; nSize
0x18009e421  call    cs:__imp_GetEnhMetaFileBits
0x18009e427  mov     [rsi], eax
0x18009e429  test    eax, eax
0x18009e42b  jnz     short loc_18009E3D3
0x18009e42d  call    cs:__imp_GetLastError
0x18009e433  mov     ebx, eax
0x18009e435  test    eax, eax
0x18009e437  jle     short loc_18009E3D3
0x18009e439  movzx   ebx, ax
0x18009e43c  or      ebx, edi
0x18009e43e  jmp     short loc_18009E3D3
0x18009e440  mov     eax, 8007000Eh
0x18009e445  add     rsp, 20h
0x18009e449  pop     r14
0x18009e44b  pop     rdi
0x18009e44c  pop     rsi
0x18009e44d  pop     rbp
0x18009e44e  pop     rbx
0x18009e44f  retn
```
