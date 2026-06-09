# MiscMungePropSheetSizes(_PROPSHEETPAGEA const *,int,_PROPSHEETPAGEA * *)

- ea: `0x180028fa8`
- end: `0x180029207`
- name: `?MiscMungePropSheetSizes@@YAJPEBU_PROPSHEETPAGEA@@HPEAPEAU1@@Z`
- size: `607`
- prototype: `__int64 __fastcall(const struct _PROPSHEETPAGEA *, int, struct _PROPSHEETPAGEA **)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18007dcd8`
- `0x1800808b0`
- `0x1800b1c7c`

## callees

- `0x180028fa8`
- `0x1800585e8`
- `0x1800587cc`
- `0x180379380`
- `0x1803796a6`

## import_xrefs

- `MSVCR100!free` at `0x1800291d6`
- `MSVCR100!free` at `0x1800291d6`
- `MSVCR100!malloc` at `0x180028fe4`
- `MSVCR100!malloc` at `0x180029163`
- `MSVCR100!malloc` at `0x180028fe4`
- `MSVCR100!malloc` at `0x180029163`
- `KERNEL32!LockResource` at `0x180029059`
- `KERNEL32!LockResource` at `0x1800290c4`
- `KERNEL32!LockResource` at `0x180029059`
- `KERNEL32!LockResource` at `0x1800290c4`
- `KERNEL32!FreeResource` at `0x180029094`
- `KERNEL32!FreeResource` at `0x180029182`
- `KERNEL32!FreeResource` at `0x1800291cd`
- `KERNEL32!FreeResource` at `0x1800291e8`
- `KERNEL32!FreeResource` at `0x180029094`
- `KERNEL32!FreeResource` at `0x180029182`
- `KERNEL32!FreeResource` at `0x1800291cd`
- `KERNEL32!FreeResource` at `0x1800291e8`
- `KERNEL32!LoadResource` at `0x180029050`
- `KERNEL32!LoadResource` at `0x1800290bb`
- `KERNEL32!LoadResource` at `0x180029050`
- `KERNEL32!LoadResource` at `0x1800290bb`
- `KERNEL32!SizeofResource` at `0x180029158`
- `KERNEL32!SizeofResource` at `0x180029158`
- `KERNEL32!MulDiv` at `0x1800291a2`
- `KERNEL32!MulDiv` at `0x1800291bb`
- `KERNEL32!MulDiv` at `0x1800291a2`
- `KERNEL32!MulDiv` at `0x1800291bb`
- `KERNEL32!FindResourceA` at `0x180029040`
- `KERNEL32!FindResourceA` at `0x1800290aa`
- `KERNEL32!FindResourceA` at `0x180029040`
- `KERNEL32!FindResourceA` at `0x1800290aa`
- `GDI32!DeleteObject` at `0x180029086`
- `GDI32!DeleteObject` at `0x180029107`
- `GDI32!DeleteObject` at `0x180029086`
- `GDI32!DeleteObject` at `0x180029107`

## pseudocode

```c
__int64 __fastcall MiscMungePropSheetSizes(const struct _PROPSHEETPAGEA *a1, int a2, struct _PROPSHEETPAGEA **a3)
{
  __int64 v3; // rsi
  size_t v6; // rdi
  struct _PROPSHEETPAGEA *v7; // rax
  char *v9; // r14
  HRSRC ResourceA; // rax
  HGLOBAL Resource; // rax
  struct DLGTEMPLATE *v12; // rbp
  HFONT HfontOfDlg; // rbx
  HRSRC v14; // r12
  HGLOBAL v15; // rax
  struct DLGTEMPLATE *v16; // rax
  struct DLGTEMPLATE *v17; // rbp
  int v18; // ecx
  HFONT v19; // rbx
  DWORD v20; // r12d
  __int16 *v21; // rax
  __int16 *v22; // rbx
  __int16 v23; // ax
  int v24; // ecx
  int nNumerator; // [rsp+58h] [rbp+10h] BYREF
  unsigned int v26; // [rsp+60h] [rbp+18h] BYREF

  nNumerator = 0;
  v26 = 0;
  v3 = a2;
  v6 = 104LL * a2;
  v7 = (struct _PROPSHEETPAGEA *)malloc(v6);
  *a3 = v7;
  if ( !v7 )
    return 2147942414LL;
  memcpy_0(v7, a1, v6);
  while ( v3 )
  {
    v9 = (char *)*a3;
    v6 -= 104LL;
    --v3;
    if ( ((*a3)[v6 / 0x68].dwFlags & 1) == 0 )
    {
      if ( !nDenominator )
      {
        ResourceA = FindResourceA(Rby_hinstComCtl, (LPCSTR)0x3EE, (LPCSTR)5);
        Resource = LoadResource(Rby_hinstComCtl, ResourceA);
        v12 = (struct DLGTEMPLATE *)LockResource(Resource);
        HfontOfDlg = DlgGetHfontOfDlg(v12);
        DlgGetBaseUnitsOfHfont(HfontOfDlg, &nDenominator, &dword_1803F8B1C);
        DeleteObject(HfontOfDlg);
        if ( v12 )
          FreeResource(v12);
      }
      v14 = FindResourceA(*(HMODULE *)&v9[v6 + 8], *(LPCSTR *)&v9[v6 + 16], (LPCSTR)5);
      v15 = LoadResource(*(HMODULE *)&v9[v6 + 8], v14);
      v16 = (struct DLGTEMPLATE *)LockResource(v15);
      v17 = v16;
      if ( v16 )
      {
        if ( v14 )
        {
          v18 = nNumerator;
          if ( !nNumerator )
          {
            v19 = DlgGetHfontOfDlg(v16);
            DlgGetBaseUnitsOfHfont(v19, (unsigned int *)&nNumerator, &v26);
            DeleteObject(v19);
            v18 = nNumerator;
          }
          if ( v18 == nDenominator && v26 == dword_1803F8B1C || !nDenominator || !dword_1803F8B1C || !v18 || !v26 )
          {
            FreeResource(v17);
            return 0;
          }
          v20 = SizeofResource(*(HMODULE *)&v9[v6 + 8], v14);
          v21 = (__int16 *)malloc(v20);
          v22 = v21;
          if ( !v21 )
          {
            FreeResource(v17);
            free(*a3);
            *a3 = 0;
            return 2147942414LL;
          }
          memcpy_0(v21, v17, v20);
          FreeResource(v17);
          *(_DWORD *)&v9[v6 + 4] |= 1u;
          *(_QWORD *)&v9[v6 + 16] = v22;
          v23 = MulDiv(v22[7], nNumerator, nDenominator);
          v24 = v22[8];
          v22[7] = v23;
          v22[8] = MulDiv(v24, v26, dword_1803F8B1C);
        }
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180028fa8  mov     [rsp+arg_0], rbx
0x180028fad  mov     [rsp+arg_18], rbp
0x180028fb2  push    rsi
0x180028fb3  push    rdi
0x180028fb4  push    r12
0x180028fb6  push    r14
0x180028fb8  push    r15
0x180028fba  mov     eax, 20h
0x180028fbf  call    _alloca_probe
0x180028fc4  sub     rsp, rax
0x180028fc7  and     [rsp+48h+nNumerator], 0
0x180028fcc  and     [rsp+48h+arg_10], 0
0x180028fd1  movsxd  rsi, edx
0x180028fd4  mov     rbx, rcx
0x180028fd7  mov     rdi, rsi
0x180028fda  mov     r15, r8
0x180028fdd  imul    rdi, 68h ; 'h'
0x180028fe1  mov     rcx, rdi; Size
0x180028fe4  call    cs:__imp_malloc
0x180028fea  mov     [r15], rax
0x180028fed  test    rax, rax
0x180028ff0  jnz     short loc_180028FFC
0x180028ff2  mov     eax, 8007000Eh
0x180028ff7  jmp     loc_1800291F0
0x180028ffc  mov     r8, rdi; Size
0x180028fff  mov     rdx, rbx; Src
0x180029002  mov     rcx, rax; void *
0x180029005  call    memcpy_0
0x18002900a  test    rsi, rsi
0x18002900d  jz      loc_1800291EE
0x180029013  mov     r14, [r15]
0x180029016  sub     rdi, 68h ; 'h'
0x18002901a  dec     rsi
0x18002901d  test    byte ptr [rdi+r14+4], 1
0x180029023  jnz     short loc_18002900A
0x180029025  cmp     cs:nDenominator, 0
0x18002902c  jnz     short loc_18002909A
0x18002902e  mov     rcx, cs:?Rby_hinstComCtl@@3PEAUHINSTANCE__@@EA; hModule
0x180029035  mov     edx, 3EEh; lpName
0x18002903a  mov     r8d, 5; lpType
0x180029040  call    cs:__imp_FindResourceA
0x180029046  mov     rcx, cs:?Rby_hinstComCtl@@3PEAUHINSTANCE__@@EA; hModule
0x18002904d  mov     rdx, rax; hResInfo
0x180029050  call    cs:__imp_LoadResource
0x180029056  mov     rcx, rax; hResData
0x180029059  call    cs:__imp_LockResource
0x18002905f  mov     rcx, rax; struct DLGTEMPLATE *
0x180029062  mov     rbp, rax
0x180029065  call    ?DlgGetHfontOfDlg@@YAPEAUHFONT__@@PEAUDLGTEMPLATE@@@Z; DlgGetHfontOfDlg(DLGTEMPLATE *)
0x18002906a  lea     r8, dword_1803F8B1C; unsigned int *
0x180029071  lea     rdx, nDenominator; unsigned int *
0x180029078  mov     rcx, rax; HFONT
0x18002907b  mov     rbx, rax
0x18002907e  call    ?DlgGetBaseUnitsOfHfont@@YAXPEAUHFONT__@@PEAI1@Z; DlgGetBaseUnitsOfHfont(HFONT__ *,uint *,uint *)
0x180029083  mov     rcx, rbx; ho
0x180029086  call    cs:__imp_DeleteObject
0x18002908c  test    rbp, rbp
0x18002908f  jz      short loc_18002909A
0x180029091  mov     rcx, rbp; hResData
0x180029094  call    cs:__imp_FreeResource
0x18002909a  mov     rdx, [rdi+r14+10h]; lpName
0x18002909f  mov     rcx, [rdi+r14+8]; hModule
0x1800290a4  mov     r8d, 5; lpType
0x1800290aa  call    cs:__imp_FindResourceA
0x1800290b0  mov     rcx, [rdi+r14+8]; hModule
0x1800290b5  mov     rdx, rax; hResInfo
0x1800290b8  mov     r12, rax
0x1800290bb  call    cs:__imp_LoadResource
0x1800290c1  mov     rcx, rax; hResData
0x1800290c4  call    cs:__imp_LockResource
0x1800290ca  mov     rbp, rax
0x1800290cd  test    rax, rax
0x1800290d0  jz      loc_18002900A
0x1800290d6  test    r12, r12
0x1800290d9  jz      loc_18002900A
0x1800290df  mov     ecx, [rsp+48h+nNumerator]
0x1800290e3  test    ecx, ecx
0x1800290e5  jnz     short loc_180029111
0x1800290e7  mov     rcx, rax; struct DLGTEMPLATE *
0x1800290ea  call    ?DlgGetHfontOfDlg@@YAPEAUHFONT__@@PEAUDLGTEMPLATE@@@Z; DlgGetHfontOfDlg(DLGTEMPLATE *)
0x1800290ef  lea     r8, [rsp+48h+arg_10]; unsigned int *
0x1800290f4  lea     rdx, [rsp+48h+nNumerator]; unsigned int *
0x1800290f9  mov     rcx, rax; HFONT
0x1800290fc  mov     rbx, rax
0x1800290ff  call    ?DlgGetBaseUnitsOfHfont@@YAXPEAUHFONT__@@PEAI1@Z; DlgGetBaseUnitsOfHfont(HFONT__ *,uint *,uint *)
0x180029104  mov     rcx, rbx; ho
0x180029107  call    cs:__imp_DeleteObject
0x18002910d  mov     ecx, [rsp+48h+nNumerator]
0x180029111  mov     edx, cs:nDenominator
0x180029117  mov     r8d, [rsp+48h+arg_10]
0x18002911c  mov     eax, cs:dword_1803F8B1C
0x180029122  cmp     ecx, edx
0x180029124  jnz     short loc_18002912F
0x180029126  cmp     r8d, eax
0x180029129  jz      loc_1800291E5
0x18002912f  test    edx, edx
0x180029131  jz      loc_1800291E5
0x180029137  test    eax, eax
0x180029139  jz      loc_1800291E5
0x18002913f  test    ecx, ecx
0x180029141  jz      loc_1800291E5
0x180029147  test    r8d, r8d
0x18002914a  jz      loc_1800291E5
0x180029150  mov     rcx, [rdi+r14+8]; hModule
0x180029155  mov     rdx, r12; hResInfo
0x180029158  call    cs:__imp_SizeofResource
0x18002915e  mov     ecx, eax; Size
0x180029160  mov     r12d, eax
0x180029163  call    cs:__imp_malloc
0x180029169  mov     rbx, rax
0x18002916c  test    rax, rax
0x18002916f  jz      short loc_1800291CA
0x180029171  mov     r8d, r12d; Size
0x180029174  mov     rdx, rbp; Src
0x180029177  mov     rcx, rax; void *
0x18002917a  call    memcpy_0
0x18002917f  mov     rcx, rbp; hResData
0x180029182  call    cs:__imp_FreeResource
0x180029188  or      dword ptr [rdi+r14+4], 1
0x18002918e  mov     [rdi+r14+10h], rbx
0x180029193  movsx   ecx, word ptr [rbx+0Eh]; nNumber
0x180029197  mov     r8d, cs:nDenominator; nDenominator
0x18002919e  mov     edx, [rsp+48h+nNumerator]; nNumerator
0x1800291a2  call    cs:__imp_MulDiv
0x1800291a8  movsx   ecx, word ptr [rbx+10h]; nNumber
0x1800291ac  mov     [rbx+0Eh], ax
0x1800291b0  mov     r8d, cs:dword_1803F8B1C; nDenominator
0x1800291b7  mov     edx, [rsp+48h+arg_10]; nNumerator
0x1800291bb  call    cs:__imp_MulDiv
0x1800291c1  mov     [rbx+10h], ax
0x1800291c5  jmp     loc_18002900A
0x1800291ca  mov     rcx, rbp; hResData
0x1800291cd  call    cs:__imp_FreeResource
0x1800291d3  mov     rcx, [r15]; Block
0x1800291d6  call    cs:__imp_free
0x1800291dc  and     qword ptr [r15], 0
0x1800291e0  jmp     loc_180028FF2
0x1800291e5  mov     rcx, rbp; hResData
0x1800291e8  call    cs:__imp_FreeResource
0x1800291ee  xor     eax, eax
0x1800291f0  mov     rbx, [rsp+48h+arg_0]
0x1800291f5  mov     rbp, [rsp+48h+arg_18]
0x1800291fa  add     rsp, 20h
0x1800291fe  pop     r15
0x180029200  pop     r14
0x180029202  pop     r12
0x180029204  pop     rdi
0x180029205  pop     rsi
0x180029206  retn
```
