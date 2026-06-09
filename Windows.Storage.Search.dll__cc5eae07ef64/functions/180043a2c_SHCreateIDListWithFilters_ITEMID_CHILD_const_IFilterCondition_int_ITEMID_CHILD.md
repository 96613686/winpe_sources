# SHCreateIDListWithFilters(_ITEMID_CHILD const *,IFilterCondition * *,int,_ITEMID_CHILD * *)

- ea: `0x180043a2c`
- end: `0x180043bc5`
- name: `?SHCreateIDListWithFilters@@YAJPEFBU_ITEMID_CHILD@@PEAPEAUIFilterCondition@@HPEAPEAU1@@Z`
- size: `409`
- prototype: `__int64 __fastcall(const struct _ITEMID_CHILD *, struct IFilterCondition **, int, struct _ITEMID_CHILD **)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18005c878`
- `0x1800be9c4`

## callees

- `0x18000c420`
- `0x180043a2c`
- `0x180043bcc`
- `0x1800448b4`
- `0x180077c98`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IStream_Write` at `0x180043ac5`
- `SHCORE!IStream_Write` at `0x180043adf`
- `SHCORE!IStream_Write` at `0x180043ac5`
- `SHCORE!IStream_Write` at `0x180043adf`
- `Windows.Storage!ILFree` at `0x180043b1f`
- `Windows.Storage!ILFree` at `0x180043b1f`
- `Windows.Storage!ILCloneFirst` at `0x180043a56`
- `Windows.Storage!ILCloneFirst` at `0x180043a56`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180043aa5`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180043aa5`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x180043b44`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x180043b44`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180043b98`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180043b98`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180043b73`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180043b73`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x180043b59`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x180043b59`

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
  struct _ITEMIDLIST_RELATIVE *v8; // rdi
  int v9; // esi
  int v10; // eax
  SIZE_T v12; // rsi
  const struct _HIDDENITEMID *v13; // rax
  struct _ITEMID_CHILD *v14; // rax
  HGLOBAL phglobal; // [rsp+20h] [rbp-10h] BYREF
  _DWORD pv[2]; // [rsp+28h] [rbp-8h] BYREF
  int v17; // [rsp+70h] [rbp+40h] BYREF
  LPSTREAM ppstm; // [rsp+78h] [rbp+48h] BYREF

  v17 = a3;
  *a4 = 0;
  HGlobalFromStream = -2147024882;
  v7 = ILCloneFirst(a1);
  v8 = (struct _ITEMIDLIST_RELATIVE *)v7;
  if ( v7 )
  {
    if ( (unsigned int)ILRemoveHiddenID(v7, 3203334160LL) )
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
                goto LABEL_12;
            }
            phglobal = 0;
            HGlobalFromStream = GetHGlobalFromStream(ppstm, &phglobal);
            if ( HGlobalFromStream >= 0 )
            {
              HGlobalFromStream = -2147467259;
              v12 = GlobalSize(phglobal);
              if ( v12 - 1 <= 0xFFFD )
              {
                v13 = (const struct _HIDDENITEMID *)GlobalLock(phglobal);
                if ( v13 )
                {
                  *(_WORD *)v13 = v12;
                  v14 = ILAppendHiddenID(v8, v13);
                  v8 = v14;
                  if ( v14 )
                  {
                    HGlobalFromStream = 0;
                    *a4 = v14;
                    v8 = 0;
                  }
                  GlobalUnlock(phglobal);
                }
              }
            }
          }
        }
LABEL_12:
        (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
      }
    }
    else
    {
      HGlobalFromStream = 0;
      *a4 = v8;
      v8 = 0;
    }
    ILFree((LPITEMIDLIST)v8);
  }
  return (unsigned int)HGlobalFromStream;
}

```

## disassembly

```asm
0x180043a2c  mov     [rsp-28h+arg_0], rbx
0x180043a31  mov     [rsp-28h+arg_10], r8d
0x180043a36  push    rbp
0x180043a37  push    rsi
0x180043a38  push    rdi
0x180043a39  push    r14
0x180043a3b  push    r15
0x180043a3d  mov     rbp, rsp
0x180043a40  sub     rsp, 30h
0x180043a44  mov     r14, r9
0x180043a47  mov     qword ptr [r9], 0
0x180043a4e  mov     r15, rdx
0x180043a51  mov     ebx, 8007000Eh
0x180043a56  call    cs:__imp_ILCloneFirst
0x180043a5c  mov     rdi, rax
0x180043a5f  test    rax, rax
0x180043a62  jz      loc_180043B25
0x180043a68  mov     esi, 0BEEF0010h
0x180043a6d  mov     rcx, rax
0x180043a70  mov     edx, esi
0x180043a72  call    ILRemoveHiddenID
0x180043a77  test    eax, eax
0x180043a79  jnz     loc_180043BA3
0x180043a7f  test    r15, r15
0x180043a82  jz      loc_180043BB9
0x180043a88  cmp     [rbp+arg_10], 0
0x180043a8c  jz      loc_180043BB9
0x180043a92  lea     r8, [rbp+ppstm]; ppstm
0x180043a96  mov     [rbp+ppstm], 0
0x180043a9e  mov     edx, 1; fDeleteOnRelease
0x180043aa3  xor     ecx, ecx; hGlobal
0x180043aa5  call    cs:__imp_CreateStreamOnHGlobal
0x180043aab  mov     ebx, eax
0x180043aad  test    eax, eax
0x180043aaf  js      short loc_180043B1C
0x180043ab1  mov     rcx, [rbp+ppstm]; pstm
0x180043ab5  lea     rdx, [rbp+pv]; pv
0x180043ab9  xor     eax, eax
0x180043abb  mov     [rbp+var_4], esi
0x180043abe  mov     [rbp+pv], eax
0x180043ac1  lea     r8d, [rax+8]; cb
0x180043ac5  call    cs:__imp_IStream_Write
0x180043acb  mov     ebx, eax
0x180043acd  test    eax, eax
0x180043acf  js      short loc_180043B0C
0x180043ad1  mov     rcx, [rbp+ppstm]; pstm
0x180043ad5  lea     rdx, [rbp+arg_10]; pv
0x180043ad9  mov     r8d, 4; cb
0x180043adf  call    cs:__imp_IStream_Write
0x180043ae5  mov     ebx, eax
0x180043ae7  test    eax, eax
0x180043ae9  js      short loc_180043B0C
0x180043aeb  xor     esi, esi
0x180043aed  mov     rcx, [rbp+ppstm]; struct IStream *
0x180043af1  cmp     esi, [rbp+arg_10]
0x180043af4  jge     short loc_180043B38
0x180043af6  movsxd  r8, esi
0x180043af9  xor     edx, edx; int
0x180043afb  mov     r8, [r15+r8*8]; struct IUnknown *
0x180043aff  call    ?IUnknown_SaveToStream@@YAJPEAUIStream@@HPEAUIUnknown@@@Z; IUnknown_SaveToStream(IStream *,int,IUnknown *)
0x180043b04  inc     esi
0x180043b06  mov     ebx, eax
0x180043b08  test    eax, eax
0x180043b0a  jns     short loc_180043AED
0x180043b0c  mov     rcx, [rbp+ppstm]
0x180043b10  mov     rax, [rcx]
0x180043b13  mov     rax, [rax+10h]
0x180043b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043b1c  mov     rcx, rdi; pidl
0x180043b1f  call    cs:__imp_ILFree
0x180043b25  mov     eax, ebx
0x180043b27  mov     rbx, [rsp+30h+arg_0]
0x180043b2c  add     rsp, 30h
0x180043b30  pop     r15
0x180043b32  pop     r14
0x180043b34  pop     rdi
0x180043b35  pop     rsi
0x180043b36  pop     rbp
0x180043b37  retn
0x180043b38  lea     rdx, [rbp+phglobal]; phglobal
0x180043b3c  mov     [rbp+phglobal], 0
0x180043b44  call    cs:__imp_GetHGlobalFromStream
0x180043b4a  mov     ebx, eax
0x180043b4c  test    eax, eax
0x180043b4e  js      short loc_180043B0C
0x180043b50  mov     rcx, [rbp+phglobal]; hMem
0x180043b54  mov     ebx, 80004005h
0x180043b59  call    cs:__imp_GlobalSize
0x180043b5f  mov     rsi, rax
0x180043b62  lea     rcx, [rax-1]
0x180043b66  cmp     rcx, 0FFFDh
0x180043b6d  ja      short loc_180043B0C
0x180043b6f  mov     rcx, [rbp+phglobal]; hMem
0x180043b73  call    cs:__imp_GlobalLock
0x180043b79  test    rax, rax
0x180043b7c  jz      short loc_180043B0C
0x180043b7e  mov     rdx, rax; struct _HIDDENITEMID *
0x180043b81  mov     [rax], si
0x180043b84  mov     rcx, rdi; Src
0x180043b87  call    ?ILAppendHiddenID@@YAPEAU_ITEMIDLIST_RELATIVE@@PEAU1@PEFBU_HIDDENITEMID@@@Z; ILAppendHiddenID(_ITEMIDLIST_RELATIVE *,_HIDDENITEMID const *)
0x180043b8c  mov     rdi, rax
0x180043b8f  test    rax, rax
0x180043b92  jnz     short loc_180043BB0
0x180043b94  mov     rcx, [rbp+phglobal]; hMem
0x180043b98  call    cs:__imp_GlobalUnlock
0x180043b9e  jmp     loc_180043B0C
0x180043ba3  mov     rcx, rdi
0x180043ba6  call    ILExpungeRemovedHiddenIDs
0x180043bab  jmp     loc_180043A7F
0x180043bb0  xor     ebx, ebx
0x180043bb2  mov     [r14], rax
0x180043bb5  xor     edi, edi
0x180043bb7  jmp     short loc_180043B94
0x180043bb9  xor     ebx, ebx
0x180043bbb  mov     [r14], rdi
0x180043bbe  xor     edi, edi
0x180043bc0  jmp     loc_180043B1C
```
