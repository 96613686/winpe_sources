# SHCreateIDListWithFilters(_ITEMID_CHILD const *,IFilterCondition * *,int,_ITEMID_CHILD * *)

- ea: `0x180023ae0`
- end: `0x180023c71`
- name: `?SHCreateIDListWithFilters@@YAJPEFBU_ITEMID_CHILD@@PEAPEAUIFilterCondition@@HPEAPEAU1@@Z`
- size: `401`
- prototype: `__int64 __fastcall(const struct _ITEMID_CHILD *, struct IFilterCondition **, int, struct _ITEMID_CHILD **)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180023a1c`
- `0x180023fb0`

## callees

- `0x1800106b0`
- `0x180010728`
- `0x180022f10`
- `0x180023300`
- `0x180023ae0`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180023b7e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180023b9c`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180023b7e`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x180023b9c`
- `SHELL32!__imp_ILCloneFirst` at `0x180023b0a`
- `SHELL32!__imp_ILCloneFirst` at `0x180023b0a`
- `SHELL32!__imp_ILFree` at `0x180023c58`
- `SHELL32!__imp_ILFree` at `0x180023c58`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x180023bdb`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x180023bdb`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180023b56`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180023b56`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x180023bf0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x180023bf0`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180023c0a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180023c0a`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180023c36`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180023c36`

## pseudocode

```c
__int64 __fastcall SHCreateIDListWithFilters(
        const ITEMIDLIST *a1,
        struct IFilterCondition **a2,
        int a3,
        struct _ITEMID_CHILD **a4)
{
  HRESULT HGlobalFromStream; // ebx
  LPITEMIDLIST v7; // rax
  ITEMIDLIST *v8; // rdi
  int v9; // esi
  int v10; // eax
  SIZE_T v11; // rsi
  const struct _HIDDENITEMID *v12; // rax
  struct _ITEMID_CHILD *v13; // rax
  HGLOBAL phglobal; // [rsp+20h] [rbp-10h] BYREF
  _DWORD pv[2]; // [rsp+28h] [rbp-8h] BYREF
  int v17; // [rsp+70h] [rbp+40h] BYREF
  LPSTREAM ppstm; // [rsp+78h] [rbp+48h] BYREF

  v17 = a3;
  *a4 = 0;
  HGlobalFromStream = -2147024882;
  v7 = ILCloneFirst(a1);
  v8 = v7;
  if ( v7 )
  {
    if ( (unsigned int)ILRemoveHiddenID(v7) )
      ILExpungeRemovedHiddenIDs(v8);
    if ( a2 && v17 )
    {
      ppstm = 0;
      HGlobalFromStream = CreateStreamOnHGlobal(0, 1, &ppstm);
      if ( HGlobalFromStream >= 0 )
      {
        pv[1] = -1091633136;
        pv[0] = 0;
        HGlobalFromStream = IStream_Write(ppstm, pv, 8u);
        if ( HGlobalFromStream >= 0 )
        {
          HGlobalFromStream = IStream_Write(ppstm, &v17, 4u);
          if ( HGlobalFromStream >= 0 )
          {
            v9 = 0;
            while ( v9 < v17 )
            {
              v10 = IUnknown_SaveToStream(ppstm, 0, (struct IUnknown *)a2[v9++]);
              HGlobalFromStream = v10;
              if ( v10 < 0 )
                goto LABEL_19;
            }
            phglobal = 0;
            HGlobalFromStream = GetHGlobalFromStream(ppstm, &phglobal);
            if ( HGlobalFromStream >= 0 )
            {
              HGlobalFromStream = -2147467259;
              v11 = GlobalSize(phglobal);
              if ( v11 - 1 <= 0xFFFD )
              {
                v12 = (const struct _HIDDENITEMID *)GlobalLock(phglobal);
                if ( v12 )
                {
                  *(_WORD *)v12 = v11;
                  v13 = ILAppendHiddenID(v8, v12);
                  v8 = (ITEMIDLIST *)v13;
                  if ( v13 )
                  {
                    HGlobalFromStream = 0;
                    *a4 = v13;
                    v8 = 0;
                  }
                  GlobalUnlock(phglobal);
                }
              }
            }
          }
        }
LABEL_19:
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
      }
    }
    else
    {
      HGlobalFromStream = 0;
      *a4 = (struct _ITEMID_CHILD *)v8;
      v8 = 0;
    }
    ILFree(v8);
  }
  return (unsigned int)HGlobalFromStream;
}

```

## disassembly

```asm
0x180023ae0  mov     [rsp-28h+arg_0], rbx
0x180023ae5  mov     [rsp-28h+arg_10], r8d
0x180023aea  push    rbp
0x180023aeb  push    rsi
0x180023aec  push    rdi
0x180023aed  push    r14
0x180023aef  push    r15
0x180023af1  mov     rbp, rsp
0x180023af4  sub     rsp, 30h
0x180023af8  mov     r14, r9
0x180023afb  mov     qword ptr [r9], 0
0x180023b02  mov     r15, rdx
0x180023b05  mov     ebx, 8007000Eh
0x180023b0a  call    cs:__imp_ILCloneFirst
0x180023b10  mov     rdi, rax
0x180023b13  test    rax, rax
0x180023b16  jz      loc_180023C5E
0x180023b1c  mov     rcx, rax
0x180023b1f  call    ILRemoveHiddenID
0x180023b24  test    eax, eax
0x180023b26  jz      short loc_180023B30
0x180023b28  mov     rcx, rdi
0x180023b2b  call    ILExpungeRemovedHiddenIDs
0x180023b30  test    r15, r15
0x180023b33  jz      loc_180023C4E
0x180023b39  cmp     [rbp+arg_10], 0
0x180023b3d  jz      loc_180023C4E
0x180023b43  lea     r8, [rbp+ppstm]; ppstm
0x180023b47  mov     [rbp+ppstm], 0
0x180023b4f  mov     edx, 1; fDeleteOnRelease
0x180023b54  xor     ecx, ecx; hGlobal
0x180023b56  call    cs:__imp_CreateStreamOnHGlobal
0x180023b5c  mov     ebx, eax
0x180023b5e  test    eax, eax
0x180023b60  js      loc_180023C55
0x180023b66  mov     rcx, [rbp+ppstm]; pstm
0x180023b6a  lea     rdx, [rbp+pv]; pv
0x180023b6e  xor     eax, eax
0x180023b70  mov     [rbp+var_4], 0BEEF0010h
0x180023b77  mov     [rbp+pv], eax
0x180023b7a  lea     r8d, [rax+8]; cb
0x180023b7e  call    cs:__imp_IStream_Write
0x180023b84  mov     ebx, eax
0x180023b86  test    eax, eax
0x180023b88  js      loc_180023C3C
0x180023b8e  mov     rcx, [rbp+ppstm]; pstm
0x180023b92  lea     rdx, [rbp+arg_10]; pv
0x180023b96  mov     r8d, 4; cb
0x180023b9c  call    cs:__imp_IStream_Write
0x180023ba2  mov     ebx, eax
0x180023ba4  test    eax, eax
0x180023ba6  js      loc_180023C3C
0x180023bac  xor     esi, esi
0x180023bae  mov     rcx, [rbp+ppstm]; struct IStream *
0x180023bb2  cmp     esi, [rbp+arg_10]
0x180023bb5  jge     short loc_180023BCF
0x180023bb7  movsxd  r8, esi
0x180023bba  xor     edx, edx; int
0x180023bbc  mov     r8, [r15+r8*8]; struct IUnknown *
0x180023bc0  call    ?IUnknown_SaveToStream@@YAJPEAUIStream@@HPEAUIUnknown@@@Z; IUnknown_SaveToStream(IStream *,int,IUnknown *)
0x180023bc5  inc     esi
0x180023bc7  mov     ebx, eax
0x180023bc9  test    eax, eax
0x180023bcb  jns     short loc_180023BAE
0x180023bcd  jmp     short loc_180023C3C
0x180023bcf  lea     rdx, [rbp+phglobal]; phglobal
0x180023bd3  mov     [rbp+phglobal], 0
0x180023bdb  call    cs:__imp_GetHGlobalFromStream
0x180023be1  mov     ebx, eax
0x180023be3  test    eax, eax
0x180023be5  js      short loc_180023C3C
0x180023be7  mov     rcx, [rbp+phglobal]; hMem
0x180023beb  mov     ebx, 80004005h
0x180023bf0  call    cs:__imp_GlobalSize
0x180023bf6  mov     rsi, rax
0x180023bf9  lea     rcx, [rax-1]
0x180023bfd  cmp     rcx, 0FFFDh
0x180023c04  ja      short loc_180023C3C
0x180023c06  mov     rcx, [rbp+phglobal]; hMem
0x180023c0a  call    cs:__imp_GlobalLock
0x180023c10  test    rax, rax
0x180023c13  jz      short loc_180023C3C
0x180023c15  mov     rdx, rax; struct _HIDDENITEMID *
0x180023c18  mov     [rax], si
0x180023c1b  mov     rcx, rdi; pidl
0x180023c1e  call    ?ILAppendHiddenID@@YAPEAU_ITEMIDLIST_RELATIVE@@PEAU1@PEFBU_HIDDENITEMID@@@Z; ILAppendHiddenID(_ITEMIDLIST_RELATIVE *,_HIDDENITEMID const *)
0x180023c23  mov     rdi, rax
0x180023c26  test    rax, rax
0x180023c29  jz      short loc_180023C32
0x180023c2b  xor     ebx, ebx
0x180023c2d  mov     [r14], rax
0x180023c30  xor     edi, edi
0x180023c32  mov     rcx, [rbp+phglobal]; hMem
0x180023c36  call    cs:__imp_GlobalUnlock
0x180023c3c  mov     rcx, [rbp+ppstm]
0x180023c40  mov     rax, [rcx]
0x180023c43  mov     rax, [rax+10h]
0x180023c47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c4c  jmp     short loc_180023C55
0x180023c4e  xor     ebx, ebx
0x180023c50  mov     [r14], rdi
0x180023c53  xor     edi, edi
0x180023c55  mov     rcx, rdi; pidl
0x180023c58  call    cs:__imp_ILFree
0x180023c5e  mov     eax, ebx
0x180023c60  mov     rbx, [rsp+30h+arg_0]
0x180023c65  add     rsp, 30h
0x180023c69  pop     r15
0x180023c6b  pop     r14
0x180023c6d  pop     rdi
0x180023c6e  pop     rsi
0x180023c6f  pop     rbp
0x180023c70  retn
```
