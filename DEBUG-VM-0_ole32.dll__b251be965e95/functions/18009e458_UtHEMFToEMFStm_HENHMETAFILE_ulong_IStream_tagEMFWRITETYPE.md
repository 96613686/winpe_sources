# UtHEMFToEMFStm(HENHMETAFILE__ *,ulong,IStream *,tagEMFWRITETYPE)

- ea: `0x18009e458`
- end: `0x18009e58b`
- name: `?UtHEMFToEMFStm@@YAJPEAUHENHMETAFILE__@@KPEAUIStream@@W4tagEMFWRITETYPE@@@Z`
- size: `307`
- prototype: `HRESULT __fastcall(HENHMETAFILE__ *hEMF, unsigned int dwSize, IStream *lpstream, tagEMFWRITETYPE emfwType)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18009d950`
- `0x18009dd10`

## callees

- `0x18000b2d4`
- `0x18009e458`
- `0x1800a4c44`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009e538`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18009e538`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009e499`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18009e499`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e4e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e562`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e4e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e562`
- `GDI32!DeleteDC` at `0x18009e501`
- `GDI32!DeleteDC` at `0x18009e50c`
- `GDI32!DeleteDC` at `0x18009e501`
- `GDI32!DeleteDC` at `0x18009e50c`
- `GDI32!CreateCompatibleDC` at `0x18009e4b7`
- `GDI32!CreateCompatibleDC` at `0x18009e4b7`
- `GDI32!GetEnhMetaFileBits` at `0x18009e558`
- `GDI32!GetEnhMetaFileBits` at `0x18009e558`
- `GDI32!GetWinMetaFileBits` at `0x18009e4df`
- `GDI32!GetWinMetaFileBits` at `0x18009e4df`

## pseudocode

```c
__int64 __fastcall UtHEMFToEMFStm(HENHMETAFILE hEMF, unsigned int dwSize, IStream *lpstream, tagEMFWRITETYPE emfwType)
{
  SIZE_T v4; // rbx
  unsigned __int8 *v9; // rax
  unsigned __int8 *v10; // rsi
  HDC hdcRef; // rax
  HDC v12; // rdi
  signed int v13; // ebx
  signed int v14; // eax
  unsigned int v15; // edx
  int v16; // r8d
  signed int LastError; // eax

  v4 = dwSize;
  if ( !hEMF )
    return 2147745799LL;
  if ( dwSize >= GetSafeAllocSize() )
    return 2147942414LL;
  v9 = (unsigned __int8 *)HeapAlloc(g_hHeap, 0, v4);
  v10 = v9;
  if ( !v9 )
    return 2147942414LL;
  if ( emfwType != WRITE_AS_WMF )
  {
    if ( !GetEnhMetaFileBits(hEMF, v4, v9) )
    {
      LastError = GetLastError();
      v13 = LastError;
      if ( LastError > 0 )
        v13 = (unsigned __int16)LastError | 0x80070000;
      goto $errRtn_152;
    }
LABEL_13:
    v13 = ((__int64 (__fastcall *)(IStream *, unsigned __int8 *, _QWORD, _QWORD))lpstream->lpVtbl->Write)(
            lpstream,
            v10,
            (unsigned int)v4,
            0);
    goto $errRtn_152;
  }
  hdcRef = CreateCompatibleDC(0);
  v12 = hdcRef;
  if ( hdcRef )
  {
    if ( !GetWinMetaFileBits(hEMF, v4, v10, 8, hdcRef) )
    {
      v14 = GetLastError();
      v13 = v14;
      if ( v14 > 0 )
        v13 = (unsigned __int16)v14 | 0x80070000;
      DeleteDC(v12);
      goto $errRtn_152;
    }
    DeleteDC(v12);
    goto LABEL_13;
  }
  v13 = -2147467259;
$errRtn_152:
  HeapFree(g_hHeap, 0, v10);
  if ( v13 >= 0 )
    return (unsigned int)StSetSize(lpstream, v15, v16);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18009e458  push    rbx
0x18009e45a  push    rbp
0x18009e45b  push    rsi
0x18009e45c  push    rdi
0x18009e45d  push    r14
0x18009e45f  push    r15
0x18009e461  sub     rsp, 38h
0x18009e465  mov     ebx, dwSize
0x18009e467  mov     r14d, emfwType
0x18009e46a  mov     r15, lpstream
0x18009e46d  mov     rbp, hEMF
0x18009e470  test    hEMF, hEMF
0x18009e473  jnz     short loc_18009E47F
0x18009e475  mov     eax, 80040007h
0x18009e47a  jmp     loc_18009E57E
0x18009e47f  call    GetSafeAllocSize
0x18009e484  cmp     rbx, rax
0x18009e487  jnb     loc_18009E579
0x18009e48d  mov     hEMF, cs:?g_hHeap@@3QEAXEA; hHeap
0x18009e494  mov     lpstream, rbx; dwBytes
0x18009e497  xor     dwSize, dwSize; dwFlags
0x18009e499  call    cs:__imp_HeapAlloc
0x18009e49f  mov     rsi, rax
0x18009e4a2  test    rax, rax
0x18009e4a5  jz      loc_18009E579
0x18009e4ab  cmp     r14d, 0Dh
0x18009e4af  jnz     loc_18009E550
0x18009e4b5  xor     ecx, ecx; hdc
0x18009e4b7  call    cs:__imp_CreateCompatibleDC
0x18009e4bd  mov     rdi, rax
0x18009e4c0  test    rax, rax
0x18009e4c3  jnz     short loc_18009E4CC
0x18009e4c5  mov     ebx, 80004005h
0x18009e4ca  jmp     short $errRtn_152
0x18009e4cc  mov     emfwType, 8; iMapMode
0x18009e4d2  mov     [rsp+68h+hdcRef], rdi; hdcRef
0x18009e4d7  mov     lpstream, rsi; pData16
0x18009e4da  mov     dwSize, ebx; cbData16
0x18009e4dc  mov     hEMF, rbp; hemf
0x18009e4df  call    cs:__imp_GetWinMetaFileBits
0x18009e4e5  test    eax, eax
0x18009e4e7  jnz     short loc_18009E509
0x18009e4e9  call    cs:__imp_GetLastError
0x18009e4ef  mov     ebx, eax
0x18009e4f1  test    eax, eax
0x18009e4f3  jle     short loc_18009E4FE
0x18009e4f5  movzx   ebx, ax
0x18009e4f8  or      ebx, 80070000h
0x18009e4fe  mov     hEMF, rdi; hdc
0x18009e501  call    cs:__imp_DeleteDC
0x18009e507  jmp     short $errRtn_152
0x18009e509  mov     hEMF, rdi; hdc
0x18009e50c  call    cs:__imp_DeleteDC
0x18009e512  mov     rax, [r15]
0x18009e515  xor     emfwType, emfwType
0x18009e518  mov     r8d, ebx
0x18009e51b  mov     rdx, rsi
0x18009e51e  mov     hEMF, r15
0x18009e521  mov     rax, [rax+20h]
0x18009e525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009e52a  mov     ebx, eax
0x18009e52c  mov     hEMF, cs:?g_hHeap@@3QEAXEA; hHeap
0x18009e533  mov     lpstream, rsi; lpMem
0x18009e536  xor     dwSize, dwSize; dwFlags
0x18009e538  call    cs:__imp_HeapFree
0x18009e53e  test    ebx, ebx
0x18009e540  js      short loc_18009E54C
0x18009e542  mov     hEMF, r15; pstm
0x18009e545  call    ?StSetSize@@YAJPEAUIStream@@KH@Z; StSetSize(IStream *,ulong,int)
0x18009e54a  mov     ebx, eax
0x18009e54c  mov     eax, ebx
0x18009e54e  jmp     short loc_18009E57E
0x18009e550  mov     lpstream, rsi; lpData
0x18009e553  mov     dwSize, ebx; nSize
0x18009e555  mov     hEMF, rbp; hEMF
0x18009e558  call    cs:__imp_GetEnhMetaFileBits
0x18009e55e  test    eax, eax
0x18009e560  jnz     short loc_18009E512
0x18009e562  call    cs:__imp_GetLastError
0x18009e568  mov     ebx, eax
0x18009e56a  test    eax, eax
0x18009e56c  jle     short $errRtn_152
0x18009e56e  movzx   ebx, ax
0x18009e571  or      ebx, 80070000h
0x18009e577  jmp     short $errRtn_152
0x18009e579  mov     eax, 8007000Eh
0x18009e57e  add     rsp, 38h
0x18009e582  pop     r15
0x18009e584  pop     r14
0x18009e586  pop     rdi
0x18009e587  pop     rsi
0x18009e588  pop     rbp
0x18009e589  pop     rbx
0x18009e58a  retn
```
