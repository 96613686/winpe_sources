# CNscTree::SetDirectItemCustomState(IShellItem *,int)

- ea: `0x18002b370`
- end: `0x18002b62e`
- name: `?SetDirectItemCustomState@CNscTree@@UEAAJPEAUIShellItem@@H@Z`
- size: `702`
- prototype: `__int64 __fastcall(CNscTree *__hidden this, struct IShellItem *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002a3c4`
- `0x18002b370`
- `0x1800340a0`
- `0x18014066e`
- `0x1801406d4`
- `0x180210010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002b5e1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002b60d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002b5e1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002b60d`
- `SHELL32!SHGetIDListFromObject` at `0x18002b471`
- `SHELL32!SHGetIDListFromObject` at `0x18002b471`
- `SHELL32!SHGetTemporaryPropertyForItem` at `0x18002b3e1`
- `SHELL32!SHGetTemporaryPropertyForItem` at `0x18002b3e1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b4c5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b56e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b5b6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b4c5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b56e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002b5b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b4af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b563`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b5ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b4af`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b563`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002b5ab`
- `USER32!SendMessageW` at `0x18002b45b`
- `USER32!SendMessageW` at `0x18002b523`
- `USER32!SendMessageW` at `0x18002b45b`
- `USER32!SendMessageW` at `0x18002b523`
- `PROPSYS!PropVariantToBuffer` at `0x18002b410`
- `PROPSYS!PropVariantToBuffer` at `0x18002b410`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CNscTree::SetDirectItemCustomState(HWND *this, struct IShellItem *a2, int a3)
{
  IShellItem *v6; // rcx
  HRESULT v7; // eax
  unsigned int v8; // ebx
  struct _TREEITEM *v9; // rbx
  LPITEMIDLIST v10; // rcx
  LPITEMIDLIST v12; // rcx
  int v13; // [rsp+20h] [rbp-60h]
  int v14; // [rsp+20h] [rbp-60h]
  PROPVARIANT ppropvar; // [rsp+30h] [rbp-50h] BYREF
  size_t Size; // [rsp+38h] [rbp-48h]
  void *Src; // [rsp+40h] [rbp-40h]
  LPARAM lParam[2]; // [rsp+48h] [rbp-38h] BYREF
  __int128 v19; // [rsp+58h] [rbp-28h]
  __int128 v20; // [rsp+68h] [rbp-18h]
  __int64 v21; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  IShellItem *psi; // [rsp+B0h] [rbp+30h]
  const struct _ITEMIDLIST_ABSOLUTE *pv; // [rsp+C8h] [rbp+48h] BYREF

  v6 = 0;
  psi = 0;
  if ( a2 )
  {
    ((void (__fastcall *)(struct IShellItem *))a2->lpVtbl->AddRef)(a2);
    v6 = a2;
    psi = a2;
  }
  LOWORD(ppropvar) = 0;
  if ( SHGetTemporaryPropertyForItem(v6, &PKEY_DescriptionID, &ppropvar) < 0 || !(_WORD)ppropvar )
    goto LABEL_10;
  pv = 0;
  if ( (_WORD)ppropvar != 65 )
  {
    if ( PropVariantToBuffer(&ppropvar, &pv, 8u) < 0 )
      goto LABEL_10;
    goto LABEL_7;
  }
  if ( (_DWORD)Size )
  {
    if ( Src )
    {
      if ( (unsigned int)Size <= 8 )
      {
        memcpy_0(&pv, Src, (unsigned int)Size);
        goto LABEL_7;
      }
      *(_DWORD *)_o__errno() = 34;
    }
    else
    {
      *(_DWORD *)_o__errno() = 22;
    }
    invalid_parameter_noinfo();
  }
LABEL_7:
  if ( pv )
  {
    if ( pv != (const struct _ITEMIDLIST_ABSOLUTE *)-65536LL )
    {
      v19 = 0;
      v20 = 0;
      v21 = 0;
      lParam[0] = 20;
      lParam[1] = (LPARAM)pv;
      if ( (unsigned int)SendMessageW(this[12], 0x113Eu, 0, (LPARAM)lParam) )
      {
        if ( v21 )
        {
          v9 = pv;
          goto LABEL_15;
        }
      }
    }
  }
LABEL_10:
  pv = 0;
  v7 = SHGetIDListFromObject((IUnknown *)psi, (LPITEMIDLIST *)&pv);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xCB4,
      (unsigned int)"shell\\explorerframe\\nsc.cpp",
      (const char *)(unsigned int)v7,
      v13);
    v12 = (LPITEMIDLIST)pv;
    pv = 0;
    CoTaskMemFree(v12);
    PropVariantClear(&ppropvar);
    if ( psi )
      ((void (__fastcall *)(IShellItem *))psi->lpVtbl->Release)(psi);
    goto LABEL_20;
  }
  v9 = CNscTree::_FindFromRoot((CNscTree *)(this - 38), 0, 0, pv, 0);
  v10 = (LPITEMIDLIST)pv;
  pv = 0;
  if ( !v9 )
  {
    CoTaskMemFree(v10);
    PropVariantClear(&ppropvar);
    if ( psi )
      ((void (__fastcall *)(IShellItem *))psi->lpVtbl->Release)(psi);
    v8 = -2147024809;
LABEL_20:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x54F,
      (unsigned int)"shell\\explorerframe\\nsc.cpp",
      (const char *)v8,
      v14);
    return v8;
  }
  CoTaskMemFree(v10);
LABEL_15:
  PropVariantClear(&ppropvar);
  if ( psi )
    ((void (__fastcall *)(IShellItem *))psi->lpVtbl->Release)(psi);
  *((_QWORD *)&v19 + 1) = 0;
  v20 = 0;
  v21 = 0;
  lParam[0] = 8;
  lParam[1] = (LPARAM)v9;
  DWORD1(v19) = 61440;
  LODWORD(v19) = a3 << 12;
  SendMessageW(this[12], 0x113Fu, 0, (LPARAM)lParam);
  return 0;
}

```

## disassembly

```asm
0x18002b370  mov     [rsp-28h+arg_8], rbx
0x18002b375  push    rbp
0x18002b376  push    rsi
0x18002b377  push    rdi
0x18002b378  push    r14
0x18002b37a  push    r15
0x18002b37c  mov     rbp, rsp
0x18002b37f  sub     rsp, 80h
0x18002b386  mov     edi, r8d
0x18002b389  mov     rbx, rdx
0x18002b38c  mov     r14, rcx
0x18002b38f  xor     r15d, r15d
0x18002b392  mov     ecx, r15d
0x18002b395  mov     [rbp+psi], rcx
0x18002b399  test    rdx, rdx
0x18002b39c  jz      short loc_18002B3D1
0x18002b39e  mov     rax, [rdx]
0x18002b3a1  mov     rcx, rdx
0x18002b3a4  mov     rax, [rax+8]
0x18002b3a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3ad  nop
0x18002b3ae  mov     rdx, [rbp+psi]
0x18002b3b2  mov     rcx, rbx
0x18002b3b5  mov     [rbp+psi], rbx
0x18002b3b9  test    rdx, rdx
0x18002b3bc  jz      short loc_18002B3D1
0x18002b3be  mov     rax, [rdx]
0x18002b3c1  mov     rcx, rdx
0x18002b3c4  mov     rax, [rax+10h]
0x18002b3c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3cd  mov     rcx, [rbp+psi]; psi
0x18002b3d1  mov     word ptr [rbp+ppropvar], r15w
0x18002b3d6  lea     r8, [rbp+ppropvar]; ppropvar
0x18002b3da  lea     rdx, PKEY_DescriptionID; propkey
0x18002b3e1  call    cs:__imp_SHGetTemporaryPropertyForItem
0x18002b3e7  test    eax, eax
0x18002b3e9  js      short loc_18002B465
0x18002b3eb  movzx   eax, word ptr [rbp+ppropvar]
0x18002b3ef  test    ax, ax
0x18002b3f2  jz      short loc_18002B465
0x18002b3f4  mov     [rbp+pv], r15
0x18002b3f8  cmp     ax, 41h ; 'A'
0x18002b3fc  jz      loc_18002B5CD
0x18002b402  mov     r8d, 8; cb
0x18002b408  lea     rdx, [rbp+pv]; pv
0x18002b40c  lea     rcx, [rbp+ppropvar]; propvar
0x18002b410  call    cs:__imp_PropVariantToBuffer
0x18002b416  test    eax, eax
0x18002b418  js      short loc_18002B465
0x18002b41a  mov     rax, [rbp+pv]
0x18002b41e  test    rax, rax
0x18002b421  jz      short loc_18002B465
0x18002b423  cmp     rax, 0FFFFFFFFFFFF0000h
0x18002b429  jz      short loc_18002B465
0x18002b42b  xorps   xmm0, xmm0
0x18002b42e  xor     ecx, ecx
0x18002b430  movups  xmmword ptr [rbp+lParam], xmm0
0x18002b434  movups  [rbp+var_28], xmm0
0x18002b438  movups  [rbp+var_18], xmm0
0x18002b43c  mov     [rbp+var_8], rcx
0x18002b440  mov     dword ptr [rbp+lParam], 14h
0x18002b447  mov     [rbp+lParam+8], rax
0x18002b44b  lea     r9, [rbp+lParam]; lParam
0x18002b44f  xor     r8d, r8d; wParam
0x18002b452  mov     edx, 113Eh; Msg
0x18002b457  mov     rcx, [r14+60h]; hWnd
0x18002b45b  call    cs:__imp_SendMessageW
0x18002b461  test    eax, eax
0x18002b463  jnz     short loc_18002B4B7
0x18002b465  mov     [rbp+pv], r15
0x18002b469  lea     rdx, [rbp+pv]; ppidl
0x18002b46d  mov     rcx, [rbp+psi]; punk
0x18002b471  call    cs:__imp_SHGetIDListFromObject
0x18002b477  mov     ebx, eax
0x18002b479  test    eax, eax
0x18002b47b  js      loc_18002B542
0x18002b481  mov     [rsp+80h+var_60], r15d; int
0x18002b486  mov     r9, [rbp+pv]; struct _ITEMIDLIST_ABSOLUTE *
0x18002b48a  xor     r8d, r8d; struct _ITEMIDLIST_ABSOLUTE *
0x18002b48d  xor     edx, edx; struct _TREEITEM *
0x18002b48f  lea     rcx, [r14-130h]; this
0x18002b496  call    ?_FindFromRoot@CNscTree@@AEAAPEAU_TREEITEM@@PEAU2@PEBU_ITEMIDLIST_ABSOLUTE@@1H@Z; CNscTree::_FindFromRoot(_TREEITEM *,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *,int)
0x18002b49b  mov     rbx, rax
0x18002b49e  mov     rcx, [rbp+pv]; pv
0x18002b4a2  mov     [rbp+pv], r15
0x18002b4a6  test    rax, rax
0x18002b4a9  jz      loc_18002B5AB
0x18002b4af  call    cs:__imp_CoTaskMemFree
0x18002b4b5  jmp     short loc_18002B4C1
0x18002b4b7  cmp     [rbp+var_8], r15
0x18002b4bb  jz      short loc_18002B465
0x18002b4bd  mov     rbx, [rbp+pv]
0x18002b4c1  lea     rcx, [rbp+ppropvar]; pvar
0x18002b4c5  call    cs:__imp_PropVariantClear
0x18002b4cb  nop
0x18002b4cc  mov     rcx, [rbp+psi]
0x18002b4d0  test    rcx, rcx
0x18002b4d3  jz      short loc_18002B4E6
0x18002b4d5  mov     [rbp+psi], r15
0x18002b4d9  mov     rax, [rcx]
0x18002b4dc  mov     rax, [rax+10h]
0x18002b4e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b4e5  nop
0x18002b4e6  xorps   xmm0, xmm0
0x18002b4e9  xor     eax, eax
0x18002b4eb  movups  xmmword ptr [rbp+lParam], xmm0
0x18002b4ef  movups  [rbp+var_28], xmm0
0x18002b4f3  movups  [rbp+var_18], xmm0
0x18002b4f7  mov     [rbp+var_8], rax
0x18002b4fb  mov     dword ptr [rbp+lParam], 8
0x18002b502  mov     [rbp+lParam+8], rbx
0x18002b506  mov     dword ptr [rbp+var_28+4], 0F000h
0x18002b50d  shl     edi, 0Ch
0x18002b510  mov     dword ptr [rbp+var_28], edi
0x18002b513  lea     r9, [rbp+lParam]; lParam
0x18002b517  xor     r8d, r8d; wParam
0x18002b51a  mov     edx, 113Fh; Msg
0x18002b51f  mov     rcx, [r14+60h]; hWnd
0x18002b523  call    cs:__imp_SendMessageW
0x18002b529  xor     eax, eax
0x18002b52b  mov     rbx, [rsp+80h+arg_8]
0x18002b533  add     rsp, 80h
0x18002b53a  pop     r15
0x18002b53c  pop     r14
0x18002b53e  pop     rdi
0x18002b53f  pop     rsi
0x18002b540  pop     rbp
0x18002b541  retn
0x18002b542  mov     rcx, [rbp+28h]; this
0x18002b546  mov     r9d, eax; char *
0x18002b549  lea     r8, aShellExplorerf_35; "shell\\explorerframe\\nsc.cpp"
0x18002b550  mov     edx, 0CB4h; void *
0x18002b555  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b55a  nop
0x18002b55b  mov     rcx, [rbp+pv]; pv
0x18002b55f  mov     [rbp+pv], r15
0x18002b563  call    cs:__imp_CoTaskMemFree
0x18002b569  nop
0x18002b56a  lea     rcx, [rbp+ppropvar]; pvar
0x18002b56e  call    cs:__imp_PropVariantClear
0x18002b574  nop
0x18002b575  mov     rcx, [rbp+psi]
0x18002b579  test    rcx, rcx
0x18002b57c  jz      short loc_18002B58F
0x18002b57e  mov     [rbp+psi], r15
0x18002b582  mov     rax, [rcx]
0x18002b585  mov     rax, [rax+10h]
0x18002b589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b58e  nop
0x18002b58f  mov     rcx, [rbp+28h]; this
0x18002b593  mov     r9d, ebx; char *
0x18002b596  lea     r8, aShellExplorerf_35; "shell\\explorerframe\\nsc.cpp"
0x18002b59d  mov     edx, 54Fh; void *
0x18002b5a2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b5a7  mov     eax, ebx
0x18002b5a9  jmp     short loc_18002B52B
0x18002b5ab  call    cs:__imp_CoTaskMemFree
0x18002b5b1  nop
0x18002b5b2  lea     rcx, [rbp+ppropvar]; pvar
0x18002b5b6  call    cs:__imp_PropVariantClear
0x18002b5bc  nop
0x18002b5bd  mov     rcx, [rbp+psi]
0x18002b5c1  test    rcx, rcx
0x18002b5c4  jnz     short loc_18002B61B
0x18002b5c6  mov     ebx, 80070057h
0x18002b5cb  jmp     short loc_18002B58F
0x18002b5cd  mov     eax, dword ptr [rbp+Size]
0x18002b5d0  test    eax, eax
0x18002b5d2  jz      loc_18002B41A
0x18002b5d8  mov     rdx, [rbp+Src]; Src
0x18002b5dc  test    rdx, rdx
0x18002b5df  jnz     short loc_18002B5F7
0x18002b5e1  call    cs:__imp__o__errno
0x18002b5e7  mov     dword ptr [rax], 16h
0x18002b5ed  call    _invalid_parameter_noinfo
0x18002b5f2  jmp     loc_18002B41A
0x18002b5f7  cmp     eax, 8
0x18002b5fa  ja      short loc_18002B60D
0x18002b5fc  mov     r8, rax; Size
0x18002b5ff  lea     rcx, [rbp+pv]; void *
0x18002b603  call    memcpy_0
0x18002b608  jmp     loc_18002B41A
0x18002b60d  call    cs:__imp__o__errno
0x18002b613  mov     dword ptr [rax], 22h ; '"'
0x18002b619  jmp     short loc_18002B5ED
0x18002b61b  mov     [rbp+psi], r15
0x18002b61f  mov     rax, [rcx]
0x18002b622  mov     rax, [rax+10h]
0x18002b626  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b62b  jmp     short loc_18002B5C6
```
