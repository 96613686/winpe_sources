# CreateBitmapFromIcon(HICON__ *,int,int,tagSIZE const *,HBITMAP__ * *)

- ea: `0x18000dc60`
- end: `0x18000de70`
- name: `?CreateBitmapFromIcon@@YAJPEAUHICON__@@HHPEBUtagSIZE@@PEAPEAUHBITMAP__@@@Z`
- size: `528`
- prototype: `int(HICON, int, int, const struct tagSIZE *, HBITMAP *)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000e428`

## callees

- `0x18000db98`
- `0x18000dc60`
- `0x18000e6cc`
- `0x18000e790`
- `0x18000e87c`
- `0x18000e948`
- `0x18000f076`
- `0x18000f0a0`
- `0x180010010`

## import_xrefs

- `SHLWAPI!__imp_SHFillRectClr` at `0x18000dcf7`
- `SHLWAPI!__imp_SHFillRectClr` at `0x18000dcf7`
- `SHELL32!__imp_SHGetImageList` at `0x18000dd5c`
- `SHELL32!__imp_SHGetImageList` at `0x18000dd5c`
- `GDI32!DeleteObject` at `0x18000de41`
- `GDI32!DeleteObject` at `0x18000de41`
- `GDI32!DeleteDC` at `0x18000de32`
- `GDI32!DeleteDC` at `0x18000de32`
- `GDI32!CreateCompatibleDC` at `0x18000dcbb`
- `GDI32!CreateCompatibleDC` at `0x18000dcbb`
- `GDI32!SelectObject` at `0x18000dcd4`
- `GDI32!SelectObject` at `0x18000de23`
- `GDI32!SelectObject` at `0x18000dcd4`
- `GDI32!SelectObject` at `0x18000de23`

## pseudocode

```c
__int64 __fastcall CreateBitmapFromIcon(HDC a1, __int64 a2, void **a3, const struct tagSIZE *a4, HBITMAP *a5)
{
  int v7; // edi
  HDC CompatibleDC; // rax
  HDC v9; // rsi
  HGDIOBJ v10; // rax
  void *v11; // r13
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rdi
  int v15; // r14d
  __int64 v16; // rdx
  int v17; // r12d
  void *v18; // rcx
  void *ppvObj; // [rsp+30h] [rbp-71h] BYREF
  HGDIOBJ h; // [rsp+38h] [rbp-69h] BYREF
  __int64 v22; // [rsp+40h] [rbp-61h] BYREF
  _BYTE v23[8]; // [rsp+48h] [rbp-59h] BYREF
  int v24; // [rsp+50h] [rbp-51h]
  HDC v25; // [rsp+58h] [rbp-49h]
  LONG v26; // [rsp+68h] [rbp-39h]
  LONG v27; // [rsp+6Ch] [rbp-35h]
  int v28; // [rsp+78h] [rbp-29h]
  int v29; // [rsp+7Ch] [rbp-25h]
  int v30; // [rsp+80h] [rbp-21h]
  __int64 v31; // [rsp+A0h] [rbp-1h] BYREF
  LONG cx; // [rsp+A8h] [rbp+7h]
  LONG cy; // [rsp+ACh] [rbp+Bh]

  h = 0;
  *a5 = 0;
  v7 = Create32BitHBITMAP(a1, a4, a3, (HBITMAP *)&h);
  if ( v7 < 0 )
    return (unsigned int)v7;
  v7 = -2147467259;
  CompatibleDC = CreateCompatibleDC(0);
  v9 = CompatibleDC;
  if ( CompatibleDC )
  {
    v10 = SelectObject(CompatibleDC, h);
    cx = a4->cx;
    v11 = v10;
    cy = a4->cy;
    v31 = 0;
    SHFillRectClr(v9, &v31, 0xFFFFFFFFLL);
    ppvObj = 0;
    if ( a1 )
    {
      v12 = IsolationAwareImageList_Create((unsigned int)a4->cx, (unsigned int)a4->cy);
      v14 = v12;
      if ( v12 )
      {
        v15 = -2147024882;
        v17 = IsolationAwareImageList_ReplaceIcon(v12, v13, a1);
        if ( v17 != -1 )
          v15 = IsolationAwareHIMAGELIST_QueryInterface(v14, v16, &ppvObj);
        IsolationAwareImageList_Destroy(v14);
        goto LABEL_11;
      }
    }
    else if ( SHGetImageList(-1, &GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1, &ppvObj) >= 0
           && (*(int (__fastcall **)(void *, _QWORD, _QWORD))(*(_QWORD *)ppvObj + 256LL))(
                ppvObj,
                (unsigned int)a4->cx,
                (unsigned int)a4->cy) >= 0 )
    {
      v17 = 0;
      v15 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD))(*(_QWORD *)ppvObj + 296LL))(ppvObj, 0, 0);
LABEL_11:
      if ( v15 >= 0 )
      {
        v22 = 88;
        memset_0(v23, 0, 0x50u);
        v26 = a4->cx;
        v27 = a4->cy;
        v28 = -16777216;
        v29 = -16777216;
        v24 = v17 & 0xFFFFFF;
        v25 = v9;
        v30 = 327681;
        (*(void (__fastcall **)(void *, __int64 *))(*(_QWORD *)ppvObj + 64LL))(ppvObj, &v22);
      }
    }
    v18 = ppvObj;
    if ( ppvObj )
    {
      ppvObj = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v18 + 16LL))(v18);
    }
    *a5 = (HBITMAP)SelectObject(v9, v11);
    v7 = 0;
    DeleteDC(v9);
  }
  if ( !*a5 )
    DeleteObject(h);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000dc60  mov     [rsp-8+arg_8], rbx
0x18000dc65  push    rbp
0x18000dc66  push    rsi
0x18000dc67  push    rdi
0x18000dc68  push    r12
0x18000dc6a  push    r13
0x18000dc6c  push    r14
0x18000dc6e  push    r15
0x18000dc70  lea     rbp, [rsp-1Fh]
0x18000dc75  sub     rsp, 0C0h
0x18000dc7c  mov     rax, cs:__security_cookie
0x18000dc83  xor     rax, rsp
0x18000dc86  mov     [rbp+4Fh+var_40], rax
0x18000dc8a  mov     r15, [rbp+4Fh+arg_20]
0x18000dc8e  mov     rbx, r9
0x18000dc91  xor     r14d, r14d
0x18000dc94  lea     r9, [rbp+4Fh+h]; HBITMAP *
0x18000dc98  mov     rdx, rbx; struct tagSIZE *
0x18000dc9b  mov     [rbp+4Fh+h], r14
0x18000dc9f  mov     r12, rcx
0x18000dca2  mov     [r15], r14
0x18000dca5  call    ?Create32BitHBITMAP@@YAJPEAUHDC__@@PEBUtagSIZE@@PEAPEAXPEAPEAUHBITMAP__@@@Z; Create32BitHBITMAP(HDC__ *,tagSIZE const *,void * *,HBITMAP__ * *)
0x18000dcaa  mov     edi, eax
0x18000dcac  test    eax, eax
0x18000dcae  js      loc_18000DE47
0x18000dcb4  xor     ecx, ecx; hdc
0x18000dcb6  mov     edi, 80004005h
0x18000dcbb  call    cs:__imp_CreateCompatibleDC
0x18000dcc1  mov     rsi, rax
0x18000dcc4  test    rax, rax
0x18000dcc7  jz      loc_18000DE38
0x18000dccd  mov     rdx, [rbp+4Fh+h]; h
0x18000dcd1  mov     rcx, rax; hdc
0x18000dcd4  call    cs:__imp_SelectObject
0x18000dcda  mov     ecx, [rbx]
0x18000dcdc  lea     rdx, [rbp+4Fh+var_50]
0x18000dce0  mov     [rbp+4Fh+var_48], ecx
0x18000dce3  or      r8d, 0FFFFFFFFh
0x18000dce7  mov     ecx, [rbx+4]
0x18000dcea  mov     r13, rax
0x18000dced  mov     [rbp+4Fh+var_44], ecx
0x18000dcf0  mov     rcx, rsi
0x18000dcf3  mov     [rbp+4Fh+var_50], r14
0x18000dcf7  call    cs:__imp_SHFillRectClr
0x18000dcfd  mov     [rbp+4Fh+ppvObj], r14
0x18000dd01  test    r12, r12
0x18000dd04  jz      short loc_18000DD4E
0x18000dd06  mov     edx, [rbx+4]
0x18000dd09  mov     ecx, [rbx]
0x18000dd0b  call    IsolationAwareImageList_Create
0x18000dd10  mov     rdi, rax
0x18000dd13  test    rax, rax
0x18000dd16  jz      loc_18000DE04
0x18000dd1c  mov     r8, r12
0x18000dd1f  mov     rcx, rax
0x18000dd22  mov     r14d, 8007000Eh
0x18000dd28  call    IsolationAwareImageList_ReplaceIcon
0x18000dd2d  mov     r12d, eax
0x18000dd30  cmp     eax, 0FFFFFFFFh
0x18000dd33  jz      short loc_18000DD44
0x18000dd35  lea     r8, [rbp+4Fh+ppvObj]
0x18000dd39  mov     rcx, rdi
0x18000dd3c  call    IsolationAwareHIMAGELIST_QueryInterface
0x18000dd41  mov     r14d, eax
0x18000dd44  mov     rcx, rdi
0x18000dd47  call    IsolationAwareImageList_Destroy
0x18000dd4c  jmp     short loc_18000DDA5
0x18000dd4e  lea     r8, [rbp+4Fh+ppvObj]; ppvObj
0x18000dd52  or      ecx, 0FFFFFFFFh; iImageList
0x18000dd55  lea     rdx, _GUID_192b9d83_50fc_457b_90a0_2b82a8b5dae1; riid
0x18000dd5c  call    cs:__imp_SHGetImageList
0x18000dd62  test    eax, eax
0x18000dd64  js      loc_18000DE04
0x18000dd6a  mov     rcx, [rbp+4Fh+ppvObj]
0x18000dd6e  mov     r8d, [rbx+4]
0x18000dd72  mov     edx, [rbx]
0x18000dd74  mov     rax, [rcx]
0x18000dd77  mov     rax, [rax+100h]
0x18000dd7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd83  test    eax, eax
0x18000dd85  js      short loc_18000DE04
0x18000dd87  mov     rcx, [rbp+4Fh+ppvObj]
0x18000dd8b  xor     r8d, r8d
0x18000dd8e  xor     edx, edx
0x18000dd90  mov     r12d, r14d
0x18000dd93  mov     rax, [rcx]
0x18000dd96  mov     rax, [rax+128h]
0x18000dd9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dda2  mov     r14d, eax
0x18000dda5  test    r14d, r14d
0x18000dda8  js      short loc_18000DE01
0x18000ddaa  xor     edx, edx; Val
0x18000ddac  mov     [rbp+4Fh+var_B0], 58h ; 'X'
0x18000ddb4  lea     rcx, [rbp+4Fh+var_A8]; void *
0x18000ddb8  lea     r8d, [rdx+50h]; Size
0x18000ddbc  call    memset_0
0x18000ddc1  mov     eax, [rbx]
0x18000ddc3  lea     rdx, [rbp+4Fh+var_B0]
0x18000ddc7  mov     rcx, [rbp+4Fh+ppvObj]
0x18000ddcb  and     r12d, 0FFFFFFh
0x18000ddd2  mov     [rbp+4Fh+var_88], eax
0x18000ddd5  mov     eax, [rbx+4]
0x18000ddd8  mov     [rbp+4Fh+var_84], eax
0x18000dddb  mov     eax, 0FF000000h
0x18000dde0  mov     [rbp+4Fh+var_78], eax
0x18000dde3  mov     [rbp+4Fh+var_74], eax
0x18000dde6  mov     [rbp+4Fh+var_A0], r12d
0x18000ddea  mov     [rbp+4Fh+var_98], rsi
0x18000ddee  mov     [rbp+4Fh+var_70], 50001h
0x18000ddf5  mov     rax, [rcx]
0x18000ddf8  mov     rax, [rax+40h]
0x18000ddfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de01  xor     r14d, r14d
0x18000de04  mov     rcx, [rbp+4Fh+ppvObj]
0x18000de08  test    rcx, rcx
0x18000de0b  jz      short loc_18000DE1D
0x18000de0d  mov     [rbp+4Fh+ppvObj], r14
0x18000de11  mov     rax, [rcx]
0x18000de14  mov     rax, [rax+10h]
0x18000de18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000de1d  mov     rdx, r13; h
0x18000de20  mov     rcx, rsi; hdc
0x18000de23  call    cs:__imp_SelectObject
0x18000de29  mov     rcx, rsi; hdc
0x18000de2c  mov     [r15], rax
0x18000de2f  mov     edi, r14d
0x18000de32  call    cs:__imp_DeleteDC
0x18000de38  cmp     [r15], r14
0x18000de3b  jnz     short loc_18000DE47
0x18000de3d  mov     rcx, [rbp+4Fh+h]; ho
0x18000de41  call    cs:__imp_DeleteObject
0x18000de47  mov     eax, edi
0x18000de49  mov     rcx, [rbp+4Fh+var_40]
0x18000de4d  xor     rcx, rsp; StackCookie
0x18000de50  call    __security_check_cookie
0x18000de55  mov     rbx, [rsp+0F0h+arg_8]
0x18000de5d  add     rsp, 0C0h
0x18000de64  pop     r15
0x18000de66  pop     r14
0x18000de68  pop     r13
0x18000de6a  pop     r12
0x18000de6c  pop     rdi
0x18000de6d  pop     rsi
0x18000de6e  pop     rbp
0x18000de6f  retn
```
