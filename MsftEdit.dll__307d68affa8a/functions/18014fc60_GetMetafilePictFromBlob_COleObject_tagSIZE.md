# GetMetafilePictFromBlob(COleObject *,tagSIZE *)

- ea: `0x18014fc60`
- end: `0x18014fe0a`
- name: `?GetMetafilePictFromBlob@@YAPEAXPEAVCOleObject@@PEAUtagSIZE@@@Z`
- size: `426`
- prototype: `void *__fastcall(struct COleObject *, struct tagSIZE *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x180158afc`

## callees

- `0x18006733c`
- `0x18013bad0`
- `0x18013c916`
- `0x18014f50c`
- `0x18014fc60`
- `0x1801a6970`
- `0x1801a9368`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18014fd96`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18014fd96`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18014fdc6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x18014fdc6`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18014fda7`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18014fda7`
- `ext-ms-win-gdi-draw-l1-1-1!SetWindowOrgEx` at `0x18014fd07`
- `ext-ms-win-gdi-draw-l1-1-1!SetWindowOrgEx` at `0x18014fd07`
- `ext-ms-win-gdi-draw-l1-1-1!SetWindowExtEx` at `0x18014fd19`
- `ext-ms-win-gdi-draw-l1-1-1!SetWindowExtEx` at `0x18014fd19`
- `ext-ms-win-gdi-metafile-l1-1-1!CloseMetaFile` at `0x18014fd7a`
- `ext-ms-win-gdi-metafile-l1-1-1!CloseMetaFile` at `0x18014fd7a`
- `ext-ms-win-gdi-metafile-l1-1-1!CreateMetaFileA` at `0x18014fcb7`
- `ext-ms-win-gdi-metafile-l1-1-1!CreateMetaFileA` at `0x18014fcb7`
- `ext-ms-win-gdi-metafile-l1-1-0!DeleteMetaFile` at `0x18014fdda`
- `ext-ms-win-gdi-metafile-l1-1-0!DeleteMetaFile` at `0x18014fdda`

## pseudocode

```c
void *__fastcall GetMetafilePictFromBlob(CTxtEdit **a1, struct tagSIZE *a2)
{
  __int64 v4; // rbx
  HDC MetaFileA; // rax
  HDC v6; // rdi
  LONG y; // r15d
  CTextMarkContainer *v8; // rcx
  CTextMarkContainer *v9; // rcx
  int v10; // r14d
  HMETAFILE v11; // rdi
  HGLOBAL v12; // rax
  void *v13; // rsi
  _QWORD *v14; // rax
  struct tagPOINT pt; // [rsp+30h] [rbp-59h] BYREF
  struct tagRECT v17; // [rsp+38h] [rbp-51h] BYREF
  tagSIZE sz; // [rsp+48h] [rbp-41h] BYREF
  struct tagRECT v19; // [rsp+50h] [rbp-39h] BYREF
  _QWORD v20[10]; // [rsp+60h] [rbp-29h] BYREF

  if ( CTxtEdit::GetTextMarkContainer(a1[6]) )
  {
    v19 = 0;
    if ( a2 )
    {
      v4 = (__int64)*a2;
      pt = (struct tagPOINT)v4;
      MetaFileA = CreateMetaFileA(0);
      v6 = MetaFileA;
      if ( MetaFileA )
      {
        y = pt.y;
        v19.bottom = pt.y;
        v17.bottom = pt.y;
        pt = 0;
        *(_QWORD *)&v19.left = 0;
        v19.right = v4;
        *(_QWORD *)&v17.left = 0;
        v17.right = v4;
        sz = 0;
        SetWindowOrgEx(MetaFileA, 0, 0, &pt);
        SetWindowExtEx(v6, v4, y, &sz);
        memset_0(v20, 0, sizeof(v20));
        v20[0] = 80;
        CTextMarkContainer::SetBlobDrawInfo(
          v8,
          (const struct COleObject *)a1,
          (const struct ITextBlob::BLOB_DRAW_INFO *)v20);
        v10 = CTextMarkContainer::DrawBlob(v9, (const struct COleObject *)a1, v6, &v19, 0);
        if ( v10 == -2147467263 )
          v10 = DrawBlobD2D((struct COleObject *)a1, v6, &v17);
        v11 = CloseMetaFile(v6);
        if ( v11 && !v10 )
        {
          v12 = GlobalAlloc(0x2042u, 0x18u);
          v13 = v12;
          if ( v12 )
          {
            v14 = GlobalLock(v12);
            if ( v14 )
            {
              v14[2] = v11;
              *((_DWORD *)v14 + 1) = v4;
              *((_DWORD *)v14 + 2) = y;
              *(_DWORD *)v14 = 8;
              GlobalUnlock(v13);
            }
            return v13;
          }
          goto LABEL_13;
        }
      }
      else
      {
        v11 = 0;
      }
      v13 = 0;
      if ( !v11 )
        return v13;
LABEL_13:
      DeleteMetaFile(v11);
      return v13;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18014fc60  mov     [rsp-8+arg_10], rbx
0x18014fc65  push    rbp
0x18014fc66  push    rsi
0x18014fc67  push    rdi
0x18014fc68  push    r14
0x18014fc6a  push    r15
0x18014fc6c  lea     rbp, [rsp-37h]
0x18014fc71  sub     rsp, 0C0h
0x18014fc78  mov     rax, cs:__security_cookie
0x18014fc7f  xor     rax, rsp
0x18014fc82  mov     [rbp+57h+var_30], rax
0x18014fc86  mov     rsi, rcx
0x18014fc89  mov     rbx, rdx
0x18014fc8c  mov     rcx, [rcx+30h]; this
0x18014fc90  call    ?GetTextMarkContainer@CTxtEdit@@QEAAPEAVCTextMarkContainer@@XZ; CTxtEdit::GetTextMarkContainer(void)
0x18014fc95  test    rax, rax
0x18014fc98  jz      loc_18014FDE5
0x18014fc9e  xorps   xmm0, xmm0
0x18014fca1  movups  xmmword ptr [rbp+57h+var_90.left], xmm0
0x18014fca5  test    rbx, rbx
0x18014fca8  jz      loc_18014FDE5
0x18014fcae  mov     rbx, [rbx]
0x18014fcb1  xor     ecx, ecx; pszFile
0x18014fcb3  mov     qword ptr [rbp+57h+pt.x], rbx
0x18014fcb7  call    cs:__imp_CreateMetaFileA
0x18014fcbd  mov     rdi, rax
0x18014fcc0  test    rax, rax
0x18014fcc3  jz      loc_18014FDCE
0x18014fcc9  mov     r15d, [rbp+57h+pt.y]
0x18014fccd  lea     r9, [rbp+57h+pt]; lppt
0x18014fcd1  xor     r8d, r8d; y
0x18014fcd4  mov     [rbp+57h+var_90.bottom], r15d
0x18014fcd8  xor     edx, edx; x
0x18014fcda  mov     [rbp+57h+var_A8.bottom], r15d
0x18014fcde  mov     rcx, rax; hdc
0x18014fce1  mov     qword ptr [rbp+57h+pt.x], 0
0x18014fce9  mov     qword ptr [rbp+57h+var_90.left], 0
0x18014fcf1  mov     [rbp+57h+var_90.right], ebx
0x18014fcf4  mov     qword ptr [rbp+57h+var_A8.left], 0
0x18014fcfc  mov     [rbp+57h+var_A8.right], ebx
0x18014fcff  mov     qword ptr [rbp+57h+sz.cx], 0
0x18014fd07  call    cs:__imp_SetWindowOrgEx
0x18014fd0d  lea     r9, [rbp+57h+sz]; lpsz
0x18014fd11  mov     r8d, r15d; y
0x18014fd14  mov     edx, ebx; x
0x18014fd16  mov     rcx, rdi; hdc
0x18014fd19  call    cs:__imp_SetWindowExtEx
0x18014fd1f  mov     r14d, 50h ; 'P'
0x18014fd25  lea     rcx, [rbp+57h+var_80]; void *
0x18014fd29  mov     r8d, r14d; Size
0x18014fd2c  xor     edx, edx; Val
0x18014fd2e  call    memset_0
0x18014fd33  lea     r8, [rbp+57h+var_80]; struct ITextBlob::BLOB_DRAW_INFO *
0x18014fd37  mov     [rbp+57h+var_80], r14
0x18014fd3b  mov     rdx, rsi; struct COleObject *
0x18014fd3e  call    ?SetBlobDrawInfo@CTextMarkContainer@@QEAAXAEBVCOleObject@@AEBUBLOB_DRAW_INFO@ITextBlob@@@Z; CTextMarkContainer::SetBlobDrawInfo(COleObject const &,ITextBlob::BLOB_DRAW_INFO const &)
0x18014fd43  lea     r9, [rbp+57h+var_90]; struct tagRECT *
0x18014fd47  mov     [rsp+0E0h+var_C0], 0; struct ITextRenderTarget *
0x18014fd50  mov     r8, rdi; HDC
0x18014fd53  mov     rdx, rsi; struct COleObject *
0x18014fd56  call    ?DrawBlob@CTextMarkContainer@@QEAAJAEBVCOleObject@@PEAUHDC__@@PEBUtagRECT@@PEAUITextRenderTarget@@@Z; CTextMarkContainer::DrawBlob(COleObject const &,HDC__ *,tagRECT const *,ITextRenderTarget *)
0x18014fd5b  mov     r14d, eax
0x18014fd5e  cmp     eax, 80004001h
0x18014fd63  jnz     short loc_18014FD77
0x18014fd65  lea     r8, [rbp+57h+var_A8]; struct tagRECT *
0x18014fd69  mov     rdx, rdi; hdcDest
0x18014fd6c  mov     rcx, rsi; struct COleObject *
0x18014fd6f  call    ?DrawBlobD2D@@YAJPEAVCOleObject@@PEAUHDC__@@PEAUtagRECT@@@Z; DrawBlobD2D(COleObject *,HDC__ *,tagRECT *)
0x18014fd74  mov     r14d, eax
0x18014fd77  mov     rcx, rdi; hdc
0x18014fd7a  call    cs:__imp_CloseMetaFile
0x18014fd80  mov     rdi, rax
0x18014fd83  test    rax, rax
0x18014fd86  jz      short loc_18014FDD0
0x18014fd88  test    r14d, r14d
0x18014fd8b  jnz     short loc_18014FDD0
0x18014fd8d  lea     edx, [r14+18h]; dwBytes
0x18014fd91  mov     ecx, 2042h; uFlags
0x18014fd96  call    cs:__imp_GlobalAlloc
0x18014fd9c  mov     rsi, rax
0x18014fd9f  test    rax, rax
0x18014fda2  jz      short loc_18014FDD7
0x18014fda4  mov     rcx, rax; hMem
0x18014fda7  call    cs:__imp_GlobalLock
0x18014fdad  test    rax, rax
0x18014fdb0  jz      short loc_18014FDE0
0x18014fdb2  mov     rcx, rsi; hMem
0x18014fdb5  mov     [rax+10h], rdi
0x18014fdb9  mov     [rax+4], ebx
0x18014fdbc  mov     [rax+8], r15d
0x18014fdc0  mov     dword ptr [rax], 8
0x18014fdc6  call    cs:__imp_GlobalUnlock
0x18014fdcc  jmp     short loc_18014FDE0
0x18014fdce  xor     edi, edi
0x18014fdd0  xor     esi, esi
0x18014fdd2  test    rdi, rdi
0x18014fdd5  jz      short loc_18014FDE0
0x18014fdd7  mov     rcx, rdi; hmf
0x18014fdda  call    cs:__imp_DeleteMetaFile
0x18014fde0  mov     rax, rsi
0x18014fde3  jmp     short loc_18014FDE7
0x18014fde5  xor     eax, eax
0x18014fde7  mov     rcx, [rbp+57h+var_30]
0x18014fdeb  xor     rcx, rsp; StackCookie
0x18014fdee  call    __security_check_cookie
0x18014fdf3  mov     rbx, [rsp+0E0h+arg_10]
0x18014fdfb  add     rsp, 0C0h
0x18014fe02  pop     r15
0x18014fe04  pop     r14
0x18014fe06  pop     rdi
0x18014fe07  pop     rsi
0x18014fe08  pop     rbp
0x18014fe09  retn
```
