# CNscTree::_FindItem(IShellItem *,int,_TREEITEM * *,bool)

- ea: `0x18002981c`
- end: `0x180029aec`
- name: `?_FindItem@CNscTree@@AEAAJPEAUIShellItem@@HPEAPEAU_TREEITEM@@_N@Z`
- size: `720`
- prototype: `__int64 __usercall@<rax>(CNscTree *__hidden this@<rcx>, IUnknown *punk@<rdx>, int@<r8d>, struct _TREEITEM **@<r9>, bool)`
- caller_count: `7`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800953b0`
- `0x1800d2a80`
- `0x1800e5b70`
- `0x180101880`
- `0x1801b4100`
- `0x1801b56b0`
- `0x1801b6c80`

## callees

- `0x18002981c`
- `0x180029af4`
- `0x18002a3c4`
- `0x1800340a0`
- `0x18014066e`
- `0x1801406d4`
- `0x180210010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180029ab1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180029add`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180029ab1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180029add`
- `SHELL32!SHGetIDListFromObject` at `0x180029931`
- `SHELL32!SHGetIDListFromObject` at `0x180029931`
- `SHELL32!SHGetTemporaryPropertyForItem` at `0x180029896`
- `SHELL32!SHGetTemporaryPropertyForItem` at `0x180029896`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800299db`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029a42`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029a72`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800299db`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029a42`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029a72`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002996b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029a37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029a67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002996b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029a37`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029a67`
- `USER32!SendMessageW` at `0x180029917`
- `USER32!SendMessageW` at `0x180029917`
- `PROPSYS!PropVariantToBuffer` at `0x1800298c9`
- `PROPSYS!PropVariantToBuffer` at `0x1800298c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CNscTree::_FindItem(
        HWND *this,
        IUnknown *punk,
        const struct _GUID *a3,
        struct _TREEITEM **a4,
        bool a5)
{
  IShellItem *v8; // rcx
  HRESULT v9; // eax
  unsigned int v10; // ebx
  struct _TREEITEM *v11; // rax
  LPITEMIDLIST v12; // rcx
  int v13; // eax
  IShellItem *v14; // rcx
  IShellItem *v15; // rcx
  LPITEMIDLIST v17; // rcx
  IShellItem *v18; // rcx
  IShellItem *v19; // rcx
  int v20; // [rsp+20h] [rbp-31h]
  struct _TREEITEM *pv; // [rsp+30h] [rbp-21h] BYREF
  PROPVARIANT ppropvar; // [rsp+38h] [rbp-19h] BYREF
  size_t Size; // [rsp+40h] [rbp-11h]
  void *Src; // [rsp+48h] [rbp-9h]
  LPARAM lParam[2]; // [rsp+50h] [rbp-1h] BYREF
  __int128 v26; // [rsp+60h] [rbp+Fh]
  __int128 v27; // [rsp+70h] [rbp+1Fh]
  __int64 v28; // [rsp+80h] [rbp+2Fh]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+57h]
  IShellItem *psi; // [rsp+C8h] [rbp+77h] BYREF

  *a4 = 0;
  psi = 0;
  if ( a5 )
  {
    v13 = _ConvertToNavigationItem(punk, 1, a3, (void **)&psi);
    v10 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xC9E,
        (unsigned int)"shell\\explorerframe\\nsc.cpp",
        (const char *)(unsigned int)v13,
        v20);
      v14 = psi;
      if ( psi )
      {
        psi = 0;
        ((void (__fastcall *)(IShellItem *))v14->lpVtbl->Release)(v14);
      }
      return v10;
    }
  }
  else if ( punk )
  {
    ((void (__fastcall *)(IUnknown *))punk->lpVtbl->AddRef)(punk);
    v8 = psi;
    psi = (IShellItem *)punk;
    if ( v8 )
      ((void (__fastcall *)(IShellItem *))v8->lpVtbl->Release)(v8);
  }
  LOWORD(ppropvar) = 0;
  if ( SHGetTemporaryPropertyForItem(psi, &PKEY_DescriptionID, &ppropvar) >= 0 && (_WORD)ppropvar )
  {
    pv = 0;
    if ( (_WORD)ppropvar != 65 )
    {
      if ( PropVariantToBuffer(&ppropvar, &pv, 8u) < 0 )
        goto LABEL_12;
      goto LABEL_9;
    }
    if ( (_DWORD)Size )
    {
      if ( Src )
      {
        if ( (unsigned int)Size <= 8 )
        {
          memcpy_0(&pv, Src, (unsigned int)Size);
          goto LABEL_9;
        }
        *(_DWORD *)_o__errno() = 34;
      }
      else
      {
        *(_DWORD *)_o__errno() = 22;
      }
      invalid_parameter_noinfo();
    }
LABEL_9:
    if ( pv )
    {
      if ( pv != (struct _TREEITEM *)-65536LL )
      {
        v26 = 0;
        v27 = 0;
        v28 = 0;
        lParam[0] = 20;
        lParam[1] = (LPARAM)pv;
        if ( (unsigned int)SendMessageW(this[50], 0x113Eu, 0, (LPARAM)lParam) )
        {
          if ( v28 )
          {
            *a4 = pv;
            goto LABEL_21;
          }
        }
      }
    }
  }
LABEL_12:
  pv = 0;
  v9 = SHGetIDListFromObject((IUnknown *)psi, (LPITEMIDLIST *)&pv);
  v10 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCB4,
      (unsigned int)"shell\\explorerframe\\nsc.cpp",
      (const char *)(unsigned int)v9,
      v20);
    v17 = (LPITEMIDLIST)pv;
    pv = 0;
    CoTaskMemFree(v17);
    PropVariantClear(&ppropvar);
    v18 = psi;
    if ( psi )
    {
      psi = 0;
      ((void (__fastcall *)(IShellItem *))v18->lpVtbl->Release)(v18);
    }
    return v10;
  }
  v11 = CNscTree::_FindFromRoot((CNscTree *)this, 0, 0, pv, 0);
  *a4 = v11;
  v12 = (LPITEMIDLIST)pv;
  pv = 0;
  if ( v11 )
  {
    CoTaskMemFree(v12);
LABEL_21:
    PropVariantClear(&ppropvar);
    v15 = psi;
    if ( psi )
    {
      psi = 0;
      ((void (__fastcall *)(IShellItem *))v15->lpVtbl->Release)(v15);
    }
    return 0;
  }
  CoTaskMemFree(v12);
  PropVariantClear(&ppropvar);
  v19 = psi;
  if ( psi )
  {
    psi = 0;
    ((void (__fastcall *)(IShellItem *))v19->lpVtbl->Release)(v19);
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x18002981c  mov     [rsp-8+arg_0], rbx
0x180029821  mov     [rsp-8+arg_8], rsi
0x180029826  push    rbp
0x180029827  push    rdi
0x180029828  push    r14
0x18002982a  lea     rbp, [rsp-3Fh]
0x18002982f  sub     rsp, 90h
0x180029836  mov     rdi, r9
0x180029839  mov     rbx, rdx
0x18002983c  mov     rsi, rcx
0x18002983f  xor     r14d, r14d
0x180029842  mov     [r9], r14
0x180029845  mov     [rbp+4Fh+psi], r14
0x180029849  cmp     [rbp+4Fh+arg_20], r14b
0x18002984d  jnz     loc_180029973
0x180029853  test    rdx, rdx
0x180029856  jz      short loc_180029882
0x180029858  mov     rax, [rdx]
0x18002985b  mov     rcx, rdx
0x18002985e  mov     rax, [rax+8]
0x180029862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029867  nop
0x180029868  mov     rcx, [rbp+4Fh+psi]
0x18002986c  mov     [rbp+4Fh+psi], rbx
0x180029870  test    rcx, rcx
0x180029873  jz      short loc_180029882
0x180029875  mov     rax, [rcx]
0x180029878  mov     rax, [rax+10h]
0x18002987c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029881  nop
0x180029882  mov     word ptr [rbp+4Fh+ppropvar], r14w
0x180029887  lea     r8, [rbp+4Fh+ppropvar]; ppropvar
0x18002988b  lea     rdx, PKEY_DescriptionID; propkey
0x180029892  mov     rcx, [rbp+4Fh+psi]; psi
0x180029896  call    cs:__imp_SHGetTemporaryPropertyForItem
0x18002989c  test    eax, eax
0x18002989e  js      loc_180029925
0x1800298a4  movzx   eax, word ptr [rbp+4Fh+ppropvar]
0x1800298a8  test    ax, ax
0x1800298ab  jz      short loc_180029925
0x1800298ad  mov     [rbp+4Fh+pv], r14
0x1800298b1  cmp     ax, 41h ; 'A'
0x1800298b5  jz      loc_180029A9D
0x1800298bb  mov     r8d, 8; cb
0x1800298c1  lea     rdx, [rbp+4Fh+pv]; pv
0x1800298c5  lea     rcx, [rbp+4Fh+ppropvar]; propvar
0x1800298c9  call    cs:__imp_PropVariantToBuffer
0x1800298cf  test    eax, eax
0x1800298d1  js      short loc_180029925
0x1800298d3  mov     rax, [rbp+4Fh+pv]
0x1800298d7  test    rax, rax
0x1800298da  jz      short loc_180029925
0x1800298dc  cmp     rax, 0FFFFFFFFFFFF0000h
0x1800298e2  jz      short loc_180029925
0x1800298e4  xorps   xmm0, xmm0
0x1800298e7  xor     ecx, ecx
0x1800298e9  movups  xmmword ptr [rbp+4Fh+lParam], xmm0
0x1800298ed  movups  [rbp+4Fh+var_40], xmm0
0x1800298f1  movups  [rbp+4Fh+var_30], xmm0
0x1800298f5  mov     [rbp+4Fh+var_20], rcx
0x1800298f9  mov     dword ptr [rbp+4Fh+lParam], 14h
0x180029900  mov     [rbp+4Fh+lParam+8], rax
0x180029904  lea     r9, [rbp+4Fh+lParam]; lParam
0x180029908  xor     r8d, r8d; wParam
0x18002990b  mov     edx, 113Eh; Msg
0x180029910  mov     rcx, [rsi+190h]; hWnd
0x180029917  call    cs:__imp_SendMessageW
0x18002991d  test    eax, eax
0x18002991f  jnz     loc_1800299C6
0x180029925  mov     [rbp+4Fh+pv], r14
0x180029929  lea     rdx, [rbp+4Fh+pv]; ppidl
0x18002992d  mov     rcx, [rbp+4Fh+psi]; punk
0x180029931  call    cs:__imp_SHGetIDListFromObject
0x180029937  mov     ebx, eax
0x180029939  test    eax, eax
0x18002993b  js      loc_180029A16
0x180029941  mov     [rsp+0A0h+var_80], r14d; int
0x180029946  mov     r9, [rbp+4Fh+pv]; struct _ITEMIDLIST_ABSOLUTE *
0x18002994a  xor     r8d, r8d; struct _ITEMIDLIST_ABSOLUTE *
0x18002994d  xor     edx, edx; struct _TREEITEM *
0x18002994f  mov     rcx, rsi; this
0x180029952  call    ?_FindFromRoot@CNscTree@@AEAAPEAU_TREEITEM@@PEAU2@PEBU_ITEMIDLIST_ABSOLUTE@@1H@Z; CNscTree::_FindFromRoot(_TREEITEM *,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *,int)
0x180029957  mov     [rdi], rax
0x18002995a  mov     rcx, [rbp+4Fh+pv]; pv
0x18002995e  mov     [rbp+4Fh+pv], r14
0x180029962  test    rax, rax
0x180029965  jz      loc_180029A67
0x18002996b  call    cs:__imp_CoTaskMemFree
0x180029971  jmp     short loc_1800299D7
0x180029973  lea     r9, [rbp+4Fh+psi]; void **
0x180029977  mov     edx, 1; int
0x18002997c  mov     rcx, rbx; punk
0x18002997f  call    ?_ConvertToNavigationItem@@YAJPEAUIShellItem@@HAEBU_GUID@@PEAPEAX@Z; _ConvertToNavigationItem(IShellItem *,int,_GUID const &,void * *)
0x180029984  mov     ebx, eax
0x180029986  test    eax, eax
0x180029988  jns     loc_180029882
0x18002998e  mov     rcx, [rbp+57h]; this
0x180029992  mov     r9d, eax; char *
0x180029995  lea     r8, aShellExplorerf_35; "shell\\explorerframe\\nsc.cpp"
0x18002999c  mov     edx, 0C9Eh; void *
0x1800299a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800299a6  nop
0x1800299a7  mov     rcx, [rbp+4Fh+psi]
0x1800299ab  test    rcx, rcx
0x1800299ae  jz      short loc_1800299C1
0x1800299b0  mov     [rbp+4Fh+psi], r14
0x1800299b4  mov     rax, [rcx]
0x1800299b7  mov     rax, [rax+10h]
0x1800299bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299c0  nop
0x1800299c1  jmp     loc_180029A63
0x1800299c6  cmp     [rbp+4Fh+var_20], r14
0x1800299ca  jz      loc_180029925
0x1800299d0  mov     rax, [rbp+4Fh+pv]
0x1800299d4  mov     [rdi], rax
0x1800299d7  lea     rcx, [rbp+4Fh+ppropvar]; pvar
0x1800299db  call    cs:__imp_PropVariantClear
0x1800299e1  nop
0x1800299e2  mov     rcx, [rbp+4Fh+psi]
0x1800299e6  test    rcx, rcx
0x1800299e9  jz      short loc_1800299FC
0x1800299eb  mov     [rbp+4Fh+psi], r14
0x1800299ef  mov     rax, [rcx]
0x1800299f2  mov     rax, [rax+10h]
0x1800299f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299fb  nop
0x1800299fc  xor     eax, eax
0x1800299fe  lea     r11, [rsp+0A0h+var_10]
0x180029a06  mov     rbx, [r11+20h]
0x180029a0a  mov     rsi, [r11+28h]
0x180029a0e  mov     rsp, r11
0x180029a11  pop     r14
0x180029a13  pop     rdi
0x180029a14  pop     rbp
0x180029a15  retn
0x180029a16  mov     rcx, [rbp+57h]; this
0x180029a1a  mov     r9d, ebx; char *
0x180029a1d  lea     r8, aShellExplorerf_35; "shell\\explorerframe\\nsc.cpp"
0x180029a24  mov     edx, 0CB4h; void *
0x180029a29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029a2e  nop
0x180029a2f  mov     rcx, [rbp+4Fh+pv]; pv
0x180029a33  mov     [rbp+4Fh+pv], r14
0x180029a37  call    cs:__imp_CoTaskMemFree
0x180029a3d  nop
0x180029a3e  lea     rcx, [rbp+4Fh+ppropvar]; pvar
0x180029a42  call    cs:__imp_PropVariantClear
0x180029a48  nop
0x180029a49  mov     rcx, [rbp+4Fh+psi]
0x180029a4d  test    rcx, rcx
0x180029a50  jz      short loc_180029A63
0x180029a52  mov     [rbp+4Fh+psi], r14
0x180029a56  mov     rax, [rcx]
0x180029a59  mov     rax, [rax+10h]
0x180029a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a62  nop
0x180029a63  mov     eax, ebx
0x180029a65  jmp     short loc_1800299FE
0x180029a67  call    cs:__imp_CoTaskMemFree
0x180029a6d  nop
0x180029a6e  lea     rcx, [rbp+4Fh+ppropvar]; pvar
0x180029a72  call    cs:__imp_PropVariantClear
0x180029a78  nop
0x180029a79  mov     rcx, [rbp+4Fh+psi]
0x180029a7d  test    rcx, rcx
0x180029a80  jz      short loc_180029A93
0x180029a82  mov     [rbp+4Fh+psi], r14
0x180029a86  mov     rax, [rcx]
0x180029a89  mov     rax, [rax+10h]
0x180029a8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029a92  nop
0x180029a93  mov     eax, 80070057h
0x180029a98  jmp     loc_1800299FE
0x180029a9d  mov     eax, dword ptr [rbp+4Fh+Size]
0x180029aa0  test    eax, eax
0x180029aa2  jz      loc_1800298D3
0x180029aa8  mov     rdx, [rbp+4Fh+Src]; Src
0x180029aac  test    rdx, rdx
0x180029aaf  jnz     short loc_180029AC7
0x180029ab1  call    cs:__imp__o__errno
0x180029ab7  mov     dword ptr [rax], 16h
0x180029abd  call    _invalid_parameter_noinfo
0x180029ac2  jmp     loc_1800298D3
0x180029ac7  cmp     eax, 8
0x180029aca  ja      short loc_180029ADD
0x180029acc  mov     r8, rax; Size
0x180029acf  lea     rcx, [rbp+4Fh+pv]; void *
0x180029ad3  call    memcpy_0
0x180029ad8  jmp     loc_1800298D3
0x180029add  call    cs:__imp__o__errno
0x180029ae3  mov     dword ptr [rax], 22h ; '"'
0x180029ae9  jmp     short loc_180029ABD
```
