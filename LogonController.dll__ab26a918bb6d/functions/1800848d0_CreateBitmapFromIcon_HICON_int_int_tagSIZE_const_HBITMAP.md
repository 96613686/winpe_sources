# CreateBitmapFromIcon(HICON__ *,int,int,tagSIZE const *,HBITMAP__ * *)

- ea: `0x1800848d0`
- end: `0x180084b10`
- name: `?CreateBitmapFromIcon@@YAJPEAUHICON__@@HHPEBUtagSIZE@@PEAPEAUHBITMAP__@@@Z`
- size: `576`
- prototype: `__int64 __usercall@<rax>(HICON hicon@<rcx>, int@<edx>, int@<r8d>, const struct tagSIZE *@<r9>, HBITMAP *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18001684c`

## callees

- `0x18006c000`
- `0x18006cad0`
- `0x18008480c`
- `0x1800848d0`
- `0x18009d010`

## import_xrefs

- `COMCTL32!ImageList_Destroy` at `0x1800849cf`
- `COMCTL32!ImageList_Destroy` at `0x1800849cf`
- `COMCTL32!ImageList_ReplaceIcon` at `0x1800849a8`
- `COMCTL32!ImageList_ReplaceIcon` at `0x1800849a8`
- `COMCTL32!HIMAGELIST_QueryInterface` at `0x1800849c4`
- `COMCTL32!HIMAGELIST_QueryInterface` at `0x1800849c4`
- `COMCTL32!ImageList_Create` at `0x18008498d`
- `COMCTL32!ImageList_Create` at `0x18008498d`
- `SHLWAPI!__imp_SHFillRectClr` at `0x180084967`
- `SHLWAPI!__imp_SHFillRectClr` at `0x180084967`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x18008492b`
- `ext-ms-win-gdi-dc-create-l1-1-0!CreateCompatibleDC` at `0x18008492b`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x180084ad0`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x180084ad0`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180084944`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180084ab5`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180084944`
- `ext-ms-win-gdi-dc-l1-2-0!SelectObject` at `0x180084ab5`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180084ade`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180084ade`
- `SHELL32!__imp_SHGetImageList` at `0x1800849e8`
- `SHELL32!__imp_SHGetImageList` at `0x1800849e8`

## pseudocode

```c
__int64 __fastcall CreateBitmapFromIcon(HICON hicon, __int64 a2, void **a3, const struct tagSIZE *a4, HBITMAP *a5)
{
  HRESULT v7; // ebx
  HDC CompatibleDC; // rax
  HDC v9; // rsi
  HGDIOBJ v10; // rax
  void *v11; // r13
  struct _IMAGELIST *v12; // rax
  struct _IMAGELIST *v13; // r14
  int v14; // r12d
  void *v15; // rcx
  HBITMAP v16; // rax
  void *ppv; // [rsp+30h] [rbp-71h] BYREF
  HGDIOBJ h; // [rsp+38h] [rbp-69h] BYREF
  __int64 v20; // [rsp+40h] [rbp-61h] BYREF
  _BYTE v21[8]; // [rsp+48h] [rbp-59h] BYREF
  int v22; // [rsp+50h] [rbp-51h]
  HDC v23; // [rsp+58h] [rbp-49h]
  LONG v24; // [rsp+68h] [rbp-39h]
  LONG v25; // [rsp+6Ch] [rbp-35h]
  int v26; // [rsp+78h] [rbp-29h]
  int v27; // [rsp+7Ch] [rbp-25h]
  int v28; // [rsp+80h] [rbp-21h]
  __int64 v29; // [rsp+A0h] [rbp-1h] BYREF
  LONG cx; // [rsp+A8h] [rbp+7h]
  LONG cy; // [rsp+ACh] [rbp+Bh]

  h = 0;
  *a5 = 0;
  v7 = Create32BitHBITMAP((HDC)hicon, a4, a3, (HBITMAP *)&h);
  if ( v7 < 0 )
    return (unsigned int)v7;
  v7 = -2147467259;
  CompatibleDC = CreateCompatibleDC(0);
  v9 = CompatibleDC;
  if ( !CompatibleDC )
  {
LABEL_19:
    DeleteObject(h);
    *a5 = 0;
    return (unsigned int)v7;
  }
  v10 = SelectObject(CompatibleDC, h);
  cx = a4->cx;
  v11 = v10;
  cy = a4->cy;
  v29 = 0;
  SHFillRectClr(v9, &v29, 0xFFFFFFFFLL);
  ppv = 0;
  if ( hicon )
  {
    v7 = -2147024882;
    v12 = ImageList_Create(a4->cx, a4->cy, 0x21u, 1, 1);
    v13 = v12;
    if ( !v12 )
      goto LABEL_13;
    v14 = ImageList_ReplaceIcon(v12, -1, hicon);
    if ( v14 != -1 )
      v7 = HIMAGELIST_QueryInterface(v13, &GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1, &ppv);
    ImageList_Destroy(v13);
  }
  else
  {
    v7 = SHGetImageList(-1, &GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1, &ppv);
    if ( v7 < 0 )
      goto LABEL_13;
    v7 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD))(*(_QWORD *)ppv + 256LL))(
           ppv,
           (unsigned int)a4->cx,
           (unsigned int)a4->cy);
    if ( v7 < 0 )
      goto LABEL_13;
    v14 = 0;
    v7 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD))(*(_QWORD *)ppv + 296LL))(ppv, 0, 0);
  }
  if ( v7 >= 0 )
  {
    v20 = 88;
    memset_0(v21, 0, 0x50u);
    v24 = a4->cx;
    v25 = a4->cy;
    v26 = -16777216;
    v27 = -16777216;
    v22 = v14 & 0xFFFFFF;
    v23 = v9;
    v28 = 327681;
    v7 = (*(__int64 (__fastcall **)(void *, __int64 *))(*(_QWORD *)ppv + 64LL))(ppv, &v20);
  }
LABEL_13:
  v15 = ppv;
  ppv = 0;
  if ( v15 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 16LL))(v15);
  v16 = (HBITMAP)SelectObject(v9, v11);
  *a5 = v16;
  if ( v7 >= 0 && !v16 )
    v7 = -2147467259;
  DeleteDC(v9);
  if ( v7 < 0 )
    goto LABEL_19;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800848d0  mov     [rsp-8+arg_8], rbx
0x1800848d5  push    rbp
0x1800848d6  push    rsi
0x1800848d7  push    rdi
0x1800848d8  push    r12
0x1800848da  push    r13
0x1800848dc  push    r14
0x1800848de  push    r15
0x1800848e0  lea     rbp, [rsp-1Fh]
0x1800848e5  sub     rsp, 0C0h
0x1800848ec  mov     rax, cs:__security_cookie
0x1800848f3  xor     rax, rsp
0x1800848f6  mov     [rbp+4Fh+var_40], rax
0x1800848fa  mov     r15, [rbp+4Fh+arg_20]
0x1800848fe  mov     rdi, r9
0x180084901  xor     r14d, r14d
0x180084904  lea     r9, [rbp+4Fh+h]; HBITMAP *
0x180084908  mov     rdx, rdi; struct tagSIZE *
0x18008490b  mov     [rbp+4Fh+h], r14
0x18008490f  mov     r12, rcx
0x180084912  mov     [r15], r14
0x180084915  call    ?Create32BitHBITMAP@@YAJPEAUHDC__@@PEBUtagSIZE@@PEAPEAXPEAPEAUHBITMAP__@@@Z; Create32BitHBITMAP(HDC__ *,tagSIZE const *,void * *,HBITMAP__ * *)
0x18008491a  mov     ebx, eax
0x18008491c  test    eax, eax
0x18008491e  js      loc_180084AE7
0x180084924  xor     ecx, ecx; hdc
0x180084926  mov     ebx, 80004005h
0x18008492b  call    cs:__imp_CreateCompatibleDC
0x180084931  mov     rsi, rax
0x180084934  test    rax, rax
0x180084937  jz      loc_180084ADA
0x18008493d  mov     rdx, [rbp+4Fh+h]; h
0x180084941  mov     rcx, rax; hdc
0x180084944  call    cs:__imp_SelectObject
0x18008494a  mov     ecx, [rdi]
0x18008494c  lea     rdx, [rbp+4Fh+var_50]
0x180084950  mov     [rbp+4Fh+var_48], ecx
0x180084953  or      r8d, 0FFFFFFFFh
0x180084957  mov     ecx, [rdi+4]
0x18008495a  mov     r13, rax
0x18008495d  mov     [rbp+4Fh+var_44], ecx
0x180084960  mov     rcx, rsi
0x180084963  mov     [rbp+4Fh+var_50], r14
0x180084967  call    cs:__imp_SHFillRectClr
0x18008496d  mov     [rbp+4Fh+ppv], r14
0x180084971  test    r12, r12
0x180084974  jz      short loc_1800849DA
0x180084976  mov     edx, [rdi+4]; cy
0x180084979  lea     r9d, [r14+1]; cInitial
0x18008497d  mov     ecx, [rdi]; cx
0x18008497f  lea     r8d, [r14+21h]; flags
0x180084983  mov     [rsp+0F0h+cGrow], r9d; cGrow
0x180084988  mov     ebx, 8007000Eh
0x18008498d  call    cs:__imp_ImageList_Create
0x180084993  mov     r14, rax
0x180084996  test    rax, rax
0x180084999  jz      loc_180084A93
0x18008499f  mov     r8, r12; hicon
0x1800849a2  or      edx, 0FFFFFFFFh; i
0x1800849a5  mov     rcx, rax; himl
0x1800849a8  call    cs:__imp_ImageList_ReplaceIcon
0x1800849ae  mov     r12d, eax
0x1800849b1  cmp     eax, 0FFFFFFFFh
0x1800849b4  jz      short loc_1800849CC
0x1800849b6  lea     r8, [rbp+4Fh+ppv]; ppv
0x1800849ba  mov     rcx, r14; himl
0x1800849bd  lea     rdx, _GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1; riid
0x1800849c4  call    cs:__imp_HIMAGELIST_QueryInterface
0x1800849ca  mov     ebx, eax
0x1800849cc  mov     rcx, r14; himl
0x1800849cf  call    cs:__imp_ImageList_Destroy
0x1800849d5  xor     r14d, r14d
0x1800849d8  jmp     short loc_180084A34
0x1800849da  lea     r8, [rbp+4Fh+ppv]; ppvObj
0x1800849de  or      ecx, 0FFFFFFFFh; iImageList
0x1800849e1  lea     rdx, _GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1; riid
0x1800849e8  call    cs:__imp_SHGetImageList
0x1800849ee  mov     ebx, eax
0x1800849f0  test    eax, eax
0x1800849f2  js      loc_180084A96
0x1800849f8  mov     rcx, [rbp+4Fh+ppv]
0x1800849fc  mov     r8d, [rdi+4]
0x180084a00  mov     edx, [rdi]
0x180084a02  mov     rax, [rcx]
0x180084a05  mov     rax, [rax+100h]
0x180084a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084a11  mov     ebx, eax
0x180084a13  test    eax, eax
0x180084a15  js      short loc_180084A96
0x180084a17  mov     rcx, [rbp+4Fh+ppv]
0x180084a1b  xor     r8d, r8d
0x180084a1e  xor     edx, edx
0x180084a20  mov     r12d, r14d
0x180084a23  mov     rax, [rcx]
0x180084a26  mov     rax, [rax+128h]
0x180084a2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084a32  mov     ebx, eax
0x180084a34  test    ebx, ebx
0x180084a36  js      short loc_180084A96
0x180084a38  xor     edx, edx; Val
0x180084a3a  mov     [rbp+4Fh+var_B0], 58h ; 'X'
0x180084a42  lea     rcx, [rbp+4Fh+var_A8]; void *
0x180084a46  lea     r8d, [rdx+50h]; Size
0x180084a4a  call    memset_0
0x180084a4f  mov     eax, [rdi]
0x180084a51  lea     rdx, [rbp+4Fh+var_B0]
0x180084a55  mov     rcx, [rbp+4Fh+ppv]
0x180084a59  and     r12d, 0FFFFFFh
0x180084a60  mov     [rbp+4Fh+var_88], eax
0x180084a63  mov     eax, [rdi+4]
0x180084a66  mov     [rbp+4Fh+var_84], eax
0x180084a69  mov     eax, 0FF000000h
0x180084a6e  mov     [rbp+4Fh+var_78], eax
0x180084a71  mov     [rbp+4Fh+var_74], eax
0x180084a74  mov     [rbp+4Fh+var_A0], r12d
0x180084a78  mov     [rbp+4Fh+var_98], rsi
0x180084a7c  mov     [rbp+4Fh+var_70], 50001h
0x180084a83  mov     rax, [rcx]
0x180084a86  mov     rax, [rax+40h]
0x180084a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084a8f  mov     ebx, eax
0x180084a91  jmp     short loc_180084A96
0x180084a93  xor     r14d, r14d
0x180084a96  mov     rcx, [rbp+4Fh+ppv]
0x180084a9a  mov     [rbp+4Fh+ppv], r14
0x180084a9e  test    rcx, rcx
0x180084aa1  jz      short loc_180084AAF
0x180084aa3  mov     rax, [rcx]
0x180084aa6  mov     rax, [rax+10h]
0x180084aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180084aaf  mov     rdx, r13; h
0x180084ab2  mov     rcx, rsi; hdc
0x180084ab5  call    cs:__imp_SelectObject
0x180084abb  mov     [r15], rax
0x180084abe  test    ebx, ebx
0x180084ac0  js      short loc_180084ACD
0x180084ac2  test    rax, rax
0x180084ac5  mov     eax, 80004005h
0x180084aca  cmovz   ebx, eax
0x180084acd  mov     rcx, rsi; hdc
0x180084ad0  call    cs:__imp_DeleteDC
0x180084ad6  test    ebx, ebx
0x180084ad8  jns     short loc_180084AE7
0x180084ada  mov     rcx, [rbp+4Fh+h]; ho
0x180084ade  call    cs:__imp_DeleteObject
0x180084ae4  mov     [r15], r14
0x180084ae7  mov     eax, ebx
0x180084ae9  mov     rcx, [rbp+4Fh+var_40]
0x180084aed  xor     rcx, rsp; StackCookie
0x180084af0  call    __security_check_cookie
0x180084af5  mov     rbx, [rsp+0F0h+arg_8]
0x180084afd  add     rsp, 0C0h
0x180084b04  pop     r15
0x180084b06  pop     r14
0x180084b08  pop     r13
0x180084b0a  pop     r12
0x180084b0c  pop     rdi
0x180084b0d  pop     rsi
0x180084b0e  pop     rbp
0x180084b0f  retn
```
