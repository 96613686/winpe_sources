# OleDuplicateData

- ea: `0x18002c3c0`
- end: `0x18002c4dd`
- name: `OleDuplicateData`
- size: `285`
- prototype: `HANDLE __stdcall(HANDLE hSrc, CLIPFORMAT cfFormat, UINT uiFlags)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000d470`
- `0x1800381e0`
- `0x18007834c`

## callees

- `0x18002c3c0`
- `0x18002c4e4`
- `0x1800848f4`
- `0x1800a5b68`
- `0x1800a644c`

## import_xrefs

- `KERNELBASE!GlobalFree` at `0x18002c48e`
- `KERNELBASE!GlobalFree` at `0x18002c48e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002c469`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002c485`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002c4bc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002c4c5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002c469`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002c485`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002c4bc`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18002c4c5`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18002c446`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18002c474`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18002c446`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18002c474`
- `GDI32!CopyMetaFileW` at `0x18002c4af`
- `GDI32!CopyMetaFileW` at `0x18002c4af`
- `GDI32!CopyEnhMetaFileW` at `0x18002c41a`
- `GDI32!CopyEnhMetaFileW` at `0x18002c41a`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
HANDLE __stdcall OleDuplicateData(HANDLE hSrc, CLIPFORMAT cfFormat, UINT uiFlags)
{
  UINT v4; // ebx
  void *v6; // rbx
  LPVOID v8; // rsi
  void *v9; // rax
  _QWORD *v10; // rax

  if ( !hSrc )
    return 0;
  v4 = 2;
  if ( cfFormat != 2 )
  {
    if ( cfFormat != 3 )
    {
      if ( cfFormat == 9 )
        return UtDupPalette((HPALETTE__ *)hSrc);
      if ( cfFormat == 14 )
        return CopyEnhMetaFileW((HENHMETAFILE)hSrc, 0);
      if ( uiFlags )
        v4 = uiFlags;
      return UtDupGlobal(hSrc, v4);
    }
    if ( uiFlags )
      v4 = uiFlags;
    if ( VerifyStructFromHGlobal(cfFormat, hSrc) >= 0 )
    {
      v8 = GlobalLock(hSrc);
      if ( v8 )
      {
        v9 = UtDupGlobal(hSrc, v4);
        v6 = v9;
        if ( v9 )
        {
          v10 = GlobalLock(v9);
          if ( v10 )
          {
            *(_OWORD *)v10 = *(_OWORD *)v8;
            v10[2] = *((_QWORD *)v8 + 2);
            v10[2] = CopyMetaFileW(*((HMETAFILE *)v8 + 2), 0);
            GlobalUnlock(hSrc);
            GlobalUnlock(v6);
            return v6;
          }
          GlobalUnlock(hSrc);
          GlobalFree(v6);
        }
        else
        {
          GlobalUnlock(hSrc);
        }
      }
    }
    return 0;
  }
  return BmDuplicate((HBITMAP__ *)hSrc, (unsigned int *)cfFormat, *(tagBITMAP **)&uiFlags);
}

```

## disassembly

```asm
0x18002c3c0  push    rbx
0x18002c3c2  push    rbp
0x18002c3c3  push    rsi
0x18002c3c4  push    rdi
0x18002c3c5  sub     rsp, 28h
0x18002c3c9  movzx   r9d, cfFormat
0x18002c3cd  mov     rdi, hSrc
0x18002c3d0  test    hSrc, hSrc
0x18002c3d3  jz      short loc_18002C414
0x18002c3d5  mov     ecx, r9d
0x18002c3d8  mov     ebx, 2
0x18002c3dd  sub     ecx, ebx
0x18002c3df  jz      loc_18002C4D0
0x18002c3e5  sub     ecx, 1
0x18002c3e8  jz      short loc_18002C42C
0x18002c3ea  sub     ecx, 6
0x18002c3ed  jz      short loc_18002C422
0x18002c3ef  cmp     ecx, 5
0x18002c3f2  mov     hSrc, rdi; hEnh
0x18002c3f5  jz      short loc_18002C418
0x18002c3f7  test    uiFlags, uiFlags
0x18002c3fa  cmovnz  ebx, uiFlags
0x18002c3fe  mov     edx, ebx; uiFlags
0x18002c400  call    ?UtDupGlobal@@YAPEAXPEAXI@Z; UtDupGlobal(void *,uint)
0x18002c405  mov     rbx, rax
0x18002c408  mov     rax, rbx
0x18002c40b  add     rsp, 28h
0x18002c40f  pop     rdi
0x18002c410  pop     rsi
0x18002c411  pop     rbp
0x18002c412  pop     rbx
0x18002c413  retn
0x18002c414  xor     ebx, ebx
0x18002c416  jmp     short $errRtn_14
0x18002c418  xor     edx, edx; lpFileName
0x18002c41a  call    cs:__imp_CopyEnhMetaFileW
0x18002c420  jmp     short loc_18002C405
0x18002c422  mov     hSrc, rdi; hpalette
0x18002c425  call    ?UtDupPalette@@YAPEAUHPALETTE__@@PEAU1@@Z; UtDupPalette(HPALETTE__ *)
0x18002c42a  jmp     short loc_18002C405
0x18002c42c  test    uiFlags, uiFlags
0x18002c42f  mov     rdx, rdi; hGlobal
0x18002c432  movzx   ecx, r9w; cfFormat
0x18002c436  cmovnz  ebx, uiFlags
0x18002c43a  call    ?VerifyStructFromHGlobal@@YAJGPEAX@Z; VerifyStructFromHGlobal(ushort,void *)
0x18002c43f  test    eax, eax
0x18002c441  js      short loc_18002C414
0x18002c443  mov     hSrc, rdi; hMem
0x18002c446  call    cs:__imp_GlobalLock
0x18002c44c  mov     rsi, rax
0x18002c44f  test    rax, rax
0x18002c452  jz      short loc_18002C414
0x18002c454  mov     edx, ebx; uiFlags
0x18002c456  mov     hSrc, rdi; hsrc
0x18002c459  call    ?UtDupGlobal@@YAPEAXPEAXI@Z; UtDupGlobal(void *,uint)
0x18002c45e  mov     rbx, rax
0x18002c461  test    rax, rax
0x18002c464  jnz     short loc_18002C471
0x18002c466  mov     hSrc, rdi; hMem
0x18002c469  call    cs:__imp_GlobalUnlock
0x18002c46f  jmp     short loc_18002C414
0x18002c471  mov     hSrc, rbx; hMem
0x18002c474  call    cs:__imp_GlobalLock
0x18002c47a  mov     rbp, rax
0x18002c47d  test    rax, rax
0x18002c480  jnz     short loc_18002C499
0x18002c482  mov     hSrc, rdi; hMem
0x18002c485  call    cs:__imp_GlobalUnlock
0x18002c48b  mov     hSrc, rbx; hMem
0x18002c48e  call    cs:__imp_GlobalFree
0x18002c494  jmp     loc_18002C414
0x18002c499  movups  xmm0, xmmword ptr [rsi]
0x18002c49c  xor     edx, edx; LPCWSTR
0x18002c49e  movups  xmmword ptr [rax], xmm0
0x18002c4a1  movsd   xmm1, qword ptr [rsi+10h]
0x18002c4a6  movsd   qword ptr [rax+10h], xmm1
0x18002c4ab  mov     hSrc, [rsi+10h]; HMETAFILE
0x18002c4af  call    cs:__imp_CopyMetaFileW
0x18002c4b5  mov     hSrc, rdi; hMem
0x18002c4b8  mov     [rbp+10h], rax
0x18002c4bc  call    cs:__imp_GlobalUnlock
0x18002c4c2  mov     hSrc, rbx; hMem
0x18002c4c5  call    cs:__imp_GlobalUnlock
0x18002c4cb  jmp     $errRtn_14
0x18002c4d0  mov     hSrc, rdi; hold
0x18002c4d3  call    ?BmDuplicate@@YAPEAUHBITMAP__@@PEAU1@PEAKPEAUtagBITMAP@@@Z; BmDuplicate(HBITMAP__ *,ulong *,tagBITMAP *)
0x18002c4d8  jmp     loc_18002C405
```
