# CWispInk::GetDataAsMetafile(tagFORMATETC *,tagSTGMEDIUM *,int)

- ea: `0x180097d58`
- end: `0x180097f17`
- name: `?GetDataAsMetafile@CWispInk@@IEAAJPEAUtagFORMATETC@@PEAUtagSTGMEDIUM@@H@Z`
- size: `447`
- prototype: `__int64 __fastcall(CWispInk *__hidden this, struct tagFORMATETC *, struct tagSTGMEDIUM *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180097f20`

## callees

- `0x180003ba0`
- `0x180021814`
- `0x180096eb4`
- `0x180097d58`
- `0x18009804c`
- `0x18009828c`
- `0x180104f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097e29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097edf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097e29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180097edf`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180097e63`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180097e63`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180097e74`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180097e74`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180097eb4`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180097eb4`
- `GDI32!SetMetaFileBitsEx` at `0x180097e1b`
- `GDI32!SetMetaFileBitsEx` at `0x180097e1b`
- `GDI32!DeleteMetaFile` at `0x180097ed2`
- `GDI32!DeleteMetaFile` at `0x180097ed2`
- `GDI32!DeleteEnhMetaFile` at `0x180097e4b`
- `GDI32!DeleteEnhMetaFile` at `0x180097e4b`
- `gdiplus!GdipEmfToWmfBits` at `0x180097dc0`
- `gdiplus!GdipEmfToWmfBits` at `0x180097e0e`
- `gdiplus!GdipEmfToWmfBits` at `0x180097dc0`
- `gdiplus!GdipEmfToWmfBits` at `0x180097e0e`

## pseudocode

```c
__int64 __fastcall CWispInk::GetDataAsMetafile(
        CInkStroke **this,
        struct tagFORMATETC *a2,
        struct tagSTGMEDIUM *a3,
        int a4)
{
  int EMF; // edi
  HENHMETAFILE v8; // rsi
  HMETAFILE v9; // rbp
  UINT v10; // eax
  UINT v11; // ebx
  signed int LastError; // eax
  HBITMAP v13; // rax
  HBITMAP v14; // rsi
  _QWORD *v15; // rbx
  struct tagRECT *InkRect; // rax
  signed int v17; // eax
  struct tagRECT lpData; // [rsp+30h] [rbp-48h] BYREF
  __int64 v19; // [rsp+40h] [rbp-38h]

  if ( a4 )
    return 2147500033LL;
  *(_QWORD *)&lpData.left = 0;
  EMF = CWispInk::GetEMF(this, (HENHMETAFILE *)&lpData);
  if ( EMF < 0 )
    goto LABEL_16;
  v8 = *(HENHMETAFILE *)&lpData.left;
  v9 = 0;
  v10 = GdipEmfToWmfBits(*(_QWORD *)&lpData.left, 0, 0, 8, 0);
  v11 = v10;
  if ( v10 )
  {
    *(_QWORD *)&lpData.left = 0;
    *(_QWORD *)&lpData.right = 0;
    v19 = 0;
    if ( (unsigned __int8)Vector<unsigned char,BasicAllocator<unsigned char>>::resize(&lpData, v10) )
    {
      GdipEmfToWmfBits(v8, v11, *(_QWORD *)&lpData.left, 8, 0);
      v9 = SetMetaFileBitsEx(v11, *(const BYTE **)&lpData.left);
      if ( !v9 )
      {
        LastError = GetLastError();
        EMF = LastError;
        if ( LastError > 0 )
          EMF = (unsigned __int16)LastError | 0x80070000;
      }
    }
    else
    {
      EMF = -2147024882;
    }
    Vector<unsigned char,BasicAllocator<unsigned char>>::~Vector<unsigned char,BasicAllocator<unsigned char>>(&lpData);
  }
  else
  {
    EMF = -2147467259;
  }
  DeleteEnhMetaFile(v8);
  if ( EMF < 0 )
  {
LABEL_16:
    v17 = GetLastError();
    EMF = v17;
    if ( v17 > 0 )
      return (unsigned __int16)v17 | 0x80070000;
  }
  else
  {
    v13 = (HBITMAP)GlobalAlloc(0x2002u, 0x18u);
    v14 = v13;
    if ( v13 )
    {
      v15 = GlobalLock(v13);
      v15[2] = v9;
      *(_DWORD *)v15 = 8;
      InkRect = CWispInk::GetInkRect((CWispInk *)this, &lpData, 0, 0, 1);
      *(_QWORD *)((char *)v15 + 4) = AdjBBoxForGDI(InkRect);
      GlobalUnlock(v14);
      *(_QWORD *)&a3->tymed = 32;
      a3->pUnkForRelease = 0;
      a3->hBitmap = v14;
    }
    else
    {
      DeleteMetaFile(v9);
      return (unsigned int)-2147024882;
    }
  }
  return (unsigned int)EMF;
}

```

## disassembly

```asm
0x180097d58  mov     [rsp+arg_8], rbx
0x180097d5d  push    rbp
0x180097d5e  push    rsi
0x180097d5f  push    rdi
0x180097d60  push    r14
0x180097d62  push    r15
0x180097d64  sub     rsp, 50h
0x180097d68  mov     rax, cs:__security_cookie
0x180097d6f  xor     rax, rsp
0x180097d72  mov     [rsp+78h+var_30], rax
0x180097d77  mov     r15, r8
0x180097d7a  mov     r14, rcx
0x180097d7d  test    r9d, r9d
0x180097d80  jz      short loc_180097D8C
0x180097d82  mov     eax, 80004001h
0x180097d87  jmp     loc_180097EF6
0x180097d8c  lea     rdx, [rsp+78h+lpData]; HENHMETAFILE *
0x180097d91  mov     [rsp+78h+lpData], 0
0x180097d9a  call    ?GetEMF@CWispInk@@IEAAJAEAPEAUHENHMETAFILE__@@@Z; CWispInk::GetEMF(HENHMETAFILE__ * &)
0x180097d9f  mov     edi, eax
0x180097da1  test    eax, eax
0x180097da3  js      loc_180097EDF
0x180097da9  mov     rsi, [rsp+78h+lpData]
0x180097dae  xor     ebp, ebp
0x180097db0  xor     r8d, r8d
0x180097db3  mov     dword ptr [rsp+78h+var_58], ebp
0x180097db7  xor     edx, edx
0x180097db9  mov     rcx, rsi
0x180097dbc  lea     r9d, [rbp+8]
0x180097dc0  call    cs:__imp_GdipEmfToWmfBits
0x180097dc6  mov     ebx, eax
0x180097dc8  test    eax, eax
0x180097dca  jnz     short loc_180097DD3
0x180097dcc  mov     edi, 80004005h
0x180097dd1  jmp     short loc_180097E48
0x180097dd3  mov     rdx, rbx
0x180097dd6  mov     [rsp+78h+lpData], rbp
0x180097ddb  lea     rcx, [rsp+78h+lpData]
0x180097de0  mov     [rsp+78h+var_40], rbp
0x180097de5  mov     [rsp+78h+var_38], rbp
0x180097dea  call    ?resize@?$Vector@EV?$BasicAllocator@E@@@@QEAA_N_K@Z; Vector<uchar,BasicAllocator<uchar>>::resize(unsigned __int64)
0x180097def  test    al, al
0x180097df1  jnz     short loc_180097DFA
0x180097df3  mov     edi, 8007000Eh
0x180097df8  jmp     short loc_180097E3E
0x180097dfa  mov     r8, [rsp+78h+lpData]
0x180097dff  mov     r9d, 8
0x180097e05  mov     edx, ebx
0x180097e07  mov     dword ptr [rsp+78h+var_58], ebp
0x180097e0b  mov     rcx, rsi
0x180097e0e  call    cs:__imp_GdipEmfToWmfBits
0x180097e14  mov     rdx, [rsp+78h+lpData]; lpData
0x180097e19  mov     ecx, ebx; cbBuffer
0x180097e1b  call    cs:__imp_SetMetaFileBitsEx
0x180097e21  mov     rbp, rax
0x180097e24  test    rax, rax
0x180097e27  jnz     short loc_180097E3E
0x180097e29  call    cs:__imp_GetLastError
0x180097e2f  mov     edi, eax
0x180097e31  test    eax, eax
0x180097e33  jle     short loc_180097E3E
0x180097e35  movzx   edi, ax
0x180097e38  or      edi, 80070000h
0x180097e3e  lea     rcx, [rsp+78h+lpData]
0x180097e43  call    ??1?$Vector@EV?$BasicAllocator@E@@@@QEAA@XZ; Vector<uchar,BasicAllocator<uchar>>::~Vector<uchar,BasicAllocator<uchar>>(void)
0x180097e48  mov     rcx, rsi; hmf
0x180097e4b  call    cs:__imp_DeleteEnhMetaFile
0x180097e51  test    edi, edi
0x180097e53  js      loc_180097EDF
0x180097e59  mov     edx, 18h; dwBytes
0x180097e5e  mov     ecx, 2002h; uFlags
0x180097e63  call    cs:__imp_GlobalAlloc
0x180097e69  mov     rsi, rax
0x180097e6c  test    rax, rax
0x180097e6f  jz      short loc_180097ECF
0x180097e71  mov     rcx, rax; hMem
0x180097e74  call    cs:__imp_GlobalLock
0x180097e7a  xor     r9d, r9d; bool
0x180097e7d  mov     [rsp+78h+var_58], 1; bool
0x180097e82  xor     r8d, r8d; bool
0x180097e85  lea     rdx, [rsp+78h+lpData]; lprc
0x180097e8a  mov     rcx, r14; this
0x180097e8d  mov     rbx, rax
0x180097e90  mov     [rax+10h], rbp
0x180097e94  mov     dword ptr [rax], 8
0x180097e9a  call    ?GetInkRect@CWispInk@@IEBA?AUtagRECT@@_N00@Z; CWispInk::GetInkRect(bool,bool,bool)
0x180097e9f  mov     rcx, rax
0x180097ea2  call    AdjBBoxForGDI
0x180097ea7  mov     [rbx+4], eax
0x180097eaa  mov     rcx, rsi; hMem
0x180097ead  shr     rax, 20h
0x180097eb1  mov     [rbx+8], eax
0x180097eb4  call    cs:__imp_GlobalUnlock
0x180097eba  mov     qword ptr [r15], 20h ; ' '
0x180097ec1  mov     qword ptr [r15+10h], 0
0x180097ec9  mov     [r15+8], rsi
0x180097ecd  jmp     short loc_180097EF4
0x180097ecf  mov     rcx, rbp; hmf
0x180097ed2  call    cs:__imp_DeleteMetaFile
0x180097ed8  mov     edi, 8007000Eh
0x180097edd  jmp     short loc_180097EF4
0x180097edf  call    cs:__imp_GetLastError
0x180097ee5  mov     edi, eax
0x180097ee7  test    eax, eax
0x180097ee9  jle     short loc_180097EF4
0x180097eeb  movzx   edi, ax
0x180097eee  or      edi, 80070000h
0x180097ef4  mov     eax, edi
0x180097ef6  mov     rcx, [rsp+78h+var_30]
0x180097efb  xor     rcx, rsp; StackCookie
0x180097efe  call    __security_check_cookie
0x180097f03  mov     rbx, [rsp+78h+arg_8]
0x180097f0b  add     rsp, 50h
0x180097f0f  pop     r15
0x180097f11  pop     r14
0x180097f13  pop     rdi
0x180097f14  pop     rsi
0x180097f15  pop     rbp
0x180097f16  retn
```
