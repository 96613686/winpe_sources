# SHGetNameAndFlagsW(_ITEMIDLIST_ABSOLUTE const *,ulong,ushort *,uint,ulong *)

- ea: `0x180017128`
- end: `0x1800172bd`
- name: `?SHGetNameAndFlagsW@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@KPEAGIPEAK@Z`
- size: `405`
- prototype: `__int64 __usercall@<rax>(LPCITEMIDLIST pidl@<rcx>, unsigned int@<edx>, unsigned __int16 *@<r8>, unsigned int@<r9d>, unsigned int *)`
- caller_count: `4`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180019f54`
- `0x18001c118`
- `0x18001c3dc`
- `0x18002f920`

## callees

- `0x180016f70`
- `0x180017128`
- `0x180019dac`
- `0x1800582a2`
- `0x180059010`

## import_xrefs

- `SHCORE!__imp_StrRetToBufW` at `0x1800171f9`
- `SHCORE!__imp_StrRetToBufW` at `0x1800171f9`
- `SHCORE!__imp_SHGetObjectCompatFlags` at `0x18001726b`
- `SHCORE!__imp_SHGetObjectCompatFlags` at `0x18001726b`
- `SHELL32!SHBindToParent` at `0x180017190`
- `SHELL32!SHBindToParent` at `0x180017190`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180017299`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180017299`

## pseudocode

```c
__int64 __fastcall SHGetNameAndFlagsW(
        LPCITEMIDLIST pidl,
        unsigned int a2,
        unsigned __int16 *a3,
        unsigned int a4,
        unsigned int *a5)
{
  int v8; // eax
  int v9; // r12d
  HRESULT v10; // esi
  struct IBindCtx *v11; // r8
  const ITEMIDLIST *v12; // r14
  void *v13; // rbx
  unsigned int *v14; // rdi
  void *v15; // r15
  unsigned int v16; // r14d
  unsigned int v17; // r9d
  int AttributesFromFolderAndIDList; // eax
  unsigned int v19; // ebx
  LPCITEMIDLIST ppidlLast; // [rsp+38h] [rbp-D0h] BYREF
  STRRET pstr; // [rsp+48h] [rbp-C0h] BYREF
  void *ppv; // [rsp+198h] [rbp+90h] BYREF
  unsigned int v24; // [rsp+1A0h] [rbp+98h] BYREF

  v24 = a4;
  if ( a3 )
    *a3 = 0;
  v8 = SHCoInitialize();
  ppv = 0;
  ppidlLast = 0;
  v9 = v8;
  v10 = SHBindToParent(pidl, &GUID_000214e6_0000_0000_c000_000000000046, &ppv, &ppidlLast);
  if ( v10 >= 0 )
  {
    if ( !a3 )
      goto LABEL_8;
    v12 = ppidlLast;
    v13 = ppv;
    *a3 = 0;
    memset_0(&pstr, 0, sizeof(pstr));
    v10 = (*(__int64 (__fastcall **)(void *, const ITEMIDLIST *, _QWORD, STRRET *))(*(_QWORD *)v13 + 88LL))(
            v13,
            v12,
            a2,
            &pstr);
    if ( v10 >= 0 )
      v10 = StrRetToBufW(&pstr, v12, a3, 0x104u);
    if ( v10 >= 0 )
    {
LABEL_8:
      v14 = a5;
      if ( a5 )
      {
        v15 = ppv;
        v16 = *a5;
        v17 = *a5;
        v24 = 0;
        AttributesFromFolderAndIDList = _GetAttributesFromFolderAndIDList(
                                          (struct IShellFolder *)ppv,
                                          (const struct _ITEMIDLIST_RELATIVE *)ppidlLast,
                                          v11,
                                          v17,
                                          &v24);
        v19 = v24;
        if ( AttributesFromFolderAndIDList >= 0
          && (v24 & 0x20C00000) == 541065216
          && (v16 & 0x800000) != 0
          && (SHGetObjectCompatFlags(v15, 0) & 0x200) != 0 )
        {
          v19 = v19 & 0xFF3FFFFF | 0x800000;
        }
        *v14 = v19;
      }
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  if ( !v9 )
    CoUninitialize();
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180017128  mov     rax, rsp
0x18001712b  mov     [rax+8], rbx
0x18001712f  mov     [rax+10h], rsi
0x180017133  mov     [rax+20h], r9d
0x180017137  push    rbp
0x180017138  push    rdi
0x180017139  push    r12
0x18001713b  push    r14
0x18001713d  push    r15
0x18001713f  lea     rbp, [rax-78h]
0x180017143  sub     rsp, 150h
0x18001714a  mov     rdi, r8
0x18001714d  mov     r15d, edx
0x180017150  mov     rbx, rcx
0x180017153  test    r8, r8
0x180017156  jz      short loc_18001715E
0x180017158  xor     eax, eax
0x18001715a  mov     [r8], ax
0x18001715e  call    ?SHCoInitialize@@YAJXZ; SHCoInitialize(void)
0x180017163  lea     r9, [rsp+170h+ppidlLast]; ppidlLast
0x180017168  mov     [rbp+70h+ppv], 0
0x180017173  lea     r8, [rbp+70h+ppv]; ppv
0x18001717a  mov     [rsp+170h+ppidlLast], 0
0x180017183  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18001718a  mov     rcx, rbx; pidl
0x18001718d  mov     r12d, eax
0x180017190  call    cs:__imp_SHBindToParent
0x180017196  mov     esi, eax
0x180017198  test    eax, eax
0x18001719a  js      loc_180017294
0x1800171a0  test    rdi, rdi
0x1800171a3  jz      short loc_180017205
0x1800171a5  mov     r14, [rsp+170h+ppidlLast]
0x1800171aa  lea     rcx, [rsp+170h+pstr]; void *
0x1800171af  mov     rbx, [rbp+70h+ppv]
0x1800171b6  xor     eax, eax
0x1800171b8  xor     edx, edx; Val
0x1800171ba  mov     [rdi], ax
0x1800171bd  mov     r8d, 110h; Size
0x1800171c3  call    memset_0
0x1800171c8  mov     rax, [rbx]
0x1800171cb  lea     r9, [rsp+170h+pstr]
0x1800171d0  mov     r8d, r15d
0x1800171d3  mov     rdx, r14
0x1800171d6  mov     rcx, rbx
0x1800171d9  mov     rax, [rax+58h]
0x1800171dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800171e2  mov     esi, eax
0x1800171e4  test    eax, eax
0x1800171e6  js      short loc_180017201
0x1800171e8  mov     r9d, 104h; cchBuf
0x1800171ee  lea     rcx, [rsp+170h+pstr]; pstr
0x1800171f3  mov     r8, rdi; pszBuf
0x1800171f6  mov     rdx, r14; pidl
0x1800171f9  call    cs:__imp_StrRetToBufW
0x1800171ff  mov     esi, eax
0x180017201  test    esi, esi
0x180017203  js      short loc_180017281
0x180017205  mov     rdi, [rbp+70h+arg_20]
0x18001720c  test    rdi, rdi
0x18001720f  jz      short loc_180017281
0x180017211  mov     r15, [rbp+70h+ppv]
0x180017218  lea     rax, [rbp+70h+arg_18]
0x18001721f  mov     r14d, [rdi]
0x180017222  mov     rcx, r15; struct IShellFolder *
0x180017225  mov     rdx, [rsp+170h+ppidlLast]; struct _ITEMIDLIST_RELATIVE *
0x18001722a  mov     r9d, r14d; unsigned int
0x18001722d  mov     [rbp+70h+arg_18], 0
0x180017237  mov     [rsp+170h+var_150], rax; unsigned int *
0x18001723c  call    ?_GetAttributesFromFolderAndIDList@@YAJPEAUIShellFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEAUIBindCtx@@KPEAK@Z; _GetAttributesFromFolderAndIDList(IShellFolder *,_ITEMIDLIST_RELATIVE const *,IBindCtx *,ulong,ulong *)
0x180017241  mov     ebx, [rbp+70h+arg_18]
0x180017247  test    eax, eax
0x180017249  js      short loc_18001727F
0x18001724b  mov     eax, ebx
0x18001724d  and     eax, 20C00000h
0x180017252  cmp     eax, 20400000h
0x180017257  setz    dl
0x18001725a  bt      r14d, 17h
0x18001725f  setb    al
0x180017262  test    al, dl
0x180017264  jz      short loc_18001727F
0x180017266  xor     edx, edx
0x180017268  mov     rcx, r15
0x18001726b  call    cs:__imp_SHGetObjectCompatFlags
0x180017271  bt      eax, 9
0x180017275  jnb     short loc_18001727F
0x180017277  btr     ebx, 16h
0x18001727b  bts     ebx, 17h
0x18001727f  mov     [rdi], ebx
0x180017281  mov     rcx, [rbp+70h+ppv]
0x180017288  mov     rax, [rcx]
0x18001728b  mov     rax, [rax+10h]
0x18001728f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017294  test    r12d, r12d
0x180017297  jnz     short loc_18001729F
0x180017299  call    cs:__imp_CoUninitialize
0x18001729f  lea     r11, [rsp+170h+var_20]
0x1800172a7  mov     eax, esi
0x1800172a9  mov     rbx, [r11+30h]
0x1800172ad  mov     rsi, [r11+38h]
0x1800172b1  mov     rsp, r11
0x1800172b4  pop     r15
0x1800172b6  pop     r14
0x1800172b8  pop     r12
0x1800172ba  pop     rdi
0x1800172bb  pop     rbp
0x1800172bc  retn
```
