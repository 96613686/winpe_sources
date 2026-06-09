# AppendHiddenSearchContext

- ea: `0x180026640`
- end: `0x1800267a6`
- name: `AppendHiddenSearchContext`
- size: `358`
- prototype: `__int64 __fastcall(struct _ITEMIDLIST_RELATIVE *Src, struct IUnknown *, struct IUnknown *, struct IUnknown *, LPSTREAM ppstm)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x1800113b4`
- `0x180022f50`
- `0x1800263f0`
- `0x180026640`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800266cd`
- `api-ms-win-shcore-stream-l1-1-0!IStream_Write` at `0x1800266cd`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x180026727`
- `api-ms-win-core-com-l1-1-0!GetHGlobalFromStream` at `0x180026727`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800266a1`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x1800266a1`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x180026737`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalSize` at `0x180026737`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18002674e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x18002674e`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180026770`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180026770`

## pseudocode

```c
__int64 __fastcall AppendHiddenSearchContext(
        struct _ITEMIDLIST_RELATIVE *Src,
        struct IUnknown *a2,
        struct IUnknown *a3,
        struct IUnknown *a4,
        LPSTREAM ppstm)
{
  struct _ITEMIDLIST_RELATIVE **v5; // rsi
  HRESULT HGlobalFromStream; // ebx
  SIZE_T v11; // rdi
  const struct _HIDDENITEMID *v12; // rax
  _DWORD pv[4]; // [rsp+20h] [rbp-10h] BYREF
  HGLOBAL phglobal; // [rsp+68h] [rbp+38h] BYREF

  v5 = (struct _ITEMIDLIST_RELATIVE **)ppstm;
  *(_QWORD *)ppstm = 0;
  if ( a2 || a3 || a4 )
  {
    ppstm = 0;
    HGlobalFromStream = CreateStreamOnHGlobal(0, 1, &ppstm);
    if ( HGlobalFromStream >= 0 )
    {
      pv[0] = 0x10000;
      pv[1] = -1091633129;
      HGlobalFromStream = IStream_Write(ppstm, pv, 8u);
      if ( HGlobalFromStream >= 0 )
      {
        HGlobalFromStream = SaveToStreamNull(ppstm, a2);
        if ( HGlobalFromStream >= 0 )
        {
          HGlobalFromStream = SaveToStreamNull(ppstm, a3);
          if ( HGlobalFromStream >= 0 )
          {
            HGlobalFromStream = SaveToStreamNull(ppstm, a4);
            if ( HGlobalFromStream >= 0 )
            {
              phglobal = 0;
              HGlobalFromStream = GetHGlobalFromStream(ppstm, &phglobal);
              if ( HGlobalFromStream >= 0 )
              {
                v11 = GlobalSize(phglobal);
                if ( v11 > 0xFFFF )
                {
                  HGlobalFromStream = -2147024362;
                }
                else
                {
                  HGlobalFromStream = 0;
                  v12 = (const struct _HIDDENITEMID *)GlobalLock(phglobal);
                  if ( v12 )
                  {
                    *(_WORD *)v12 = v11;
                    HGlobalFromStream = ILCloneWithHiddenID(Src, v12, v5);
                    GlobalUnlock(phglobal);
                  }
                }
              }
            }
          }
        }
      }
      (*(void (__fastcall **)(LPSTREAM))(*(_QWORD *)ppstm + 16LL))(ppstm);
    }
  }
  else
  {
    return (unsigned int)SHILClone(Src, v5);
  }
  return (unsigned int)HGlobalFromStream;
}

```

## disassembly

```asm
0x180026640  mov     [rsp-28h+arg_0], rbx
0x180026645  mov     [rsp-28h+arg_10], rsi
0x18002664a  push    rbp
0x18002664b  push    rdi
0x18002664c  push    r12
0x18002664e  push    r14
0x180026650  push    r15
0x180026652  mov     rbp, rsp
0x180026655  sub     rsp, 30h
0x180026659  mov     rsi, [rbp+ppstm]
0x18002665d  mov     r14, r9
0x180026660  mov     rdi, r8
0x180026663  mov     r15, rdx
0x180026666  mov     r12, rcx
0x180026669  mov     qword ptr [rsi], 0
0x180026670  test    rdx, rdx
0x180026673  jnz     short loc_18002668E
0x180026675  test    r8, r8
0x180026678  jnz     short loc_18002668E
0x18002667a  test    r9, r9
0x18002667d  jnz     short loc_18002668E
0x18002667f  mov     rdx, rsi; struct _ITEMIDLIST_RELATIVE **
0x180026682  call    ?SHILClone@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILClone(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE * *)
0x180026687  mov     ebx, eax
0x180026689  jmp     loc_18002678D
0x18002668e  lea     r8, [rbp+ppstm]; ppstm
0x180026692  mov     [rbp+ppstm], 0
0x18002669a  mov     edx, 1; fDeleteOnRelease
0x18002669f  xor     ecx, ecx; hGlobal
0x1800266a1  call    cs:__imp_CreateStreamOnHGlobal
0x1800266a7  mov     ebx, eax
0x1800266a9  test    eax, eax
0x1800266ab  js      loc_18002678D
0x1800266b1  mov     rcx, [rbp+ppstm]; pstm
0x1800266b5  lea     rdx, [rbp+pv]; pv
0x1800266b9  mov     r8d, 8; cb
0x1800266bf  mov     [rbp+pv], 10000h
0x1800266c6  mov     [rbp+var_C], 0BEEF0017h
0x1800266cd  call    cs:__imp_IStream_Write
0x1800266d3  mov     ebx, eax
0x1800266d5  test    eax, eax
0x1800266d7  js      loc_18002677D
0x1800266dd  mov     rcx, [rbp+ppstm]; struct IStream *
0x1800266e1  mov     rdx, r15; struct IUnknown *
0x1800266e4  call    ?SaveToStreamNull@@YAJPEAUIStream@@PEAUIUnknown@@@Z; SaveToStreamNull(IStream *,IUnknown *)
0x1800266e9  mov     ebx, eax
0x1800266eb  test    eax, eax
0x1800266ed  js      loc_18002677D
0x1800266f3  mov     rcx, [rbp+ppstm]; struct IStream *
0x1800266f7  mov     rdx, rdi; struct IUnknown *
0x1800266fa  call    ?SaveToStreamNull@@YAJPEAUIStream@@PEAUIUnknown@@@Z; SaveToStreamNull(IStream *,IUnknown *)
0x1800266ff  mov     ebx, eax
0x180026701  test    eax, eax
0x180026703  js      short loc_18002677D
0x180026705  mov     rcx, [rbp+ppstm]; struct IStream *
0x180026709  mov     rdx, r14; struct IUnknown *
0x18002670c  call    ?SaveToStreamNull@@YAJPEAUIStream@@PEAUIUnknown@@@Z; SaveToStreamNull(IStream *,IUnknown *)
0x180026711  mov     ebx, eax
0x180026713  test    eax, eax
0x180026715  js      short loc_18002677D
0x180026717  mov     rcx, [rbp+ppstm]; pstm
0x18002671b  lea     rdx, [rbp+phglobal]; phglobal
0x18002671f  mov     [rbp+phglobal], 0
0x180026727  call    cs:__imp_GetHGlobalFromStream
0x18002672d  mov     ebx, eax
0x18002672f  test    eax, eax
0x180026731  js      short loc_18002677D
0x180026733  mov     rcx, [rbp+phglobal]; hMem
0x180026737  call    cs:__imp_GlobalSize
0x18002673d  mov     rdi, rax
0x180026740  cmp     rax, 0FFFFh
0x180026746  ja      short loc_180026778
0x180026748  mov     rcx, [rbp+phglobal]; hMem
0x18002674c  xor     ebx, ebx
0x18002674e  call    cs:__imp_GlobalLock
0x180026754  test    rax, rax
0x180026757  jz      short loc_18002677D
0x180026759  mov     r8, rsi; struct _ITEMIDLIST_RELATIVE **
0x18002675c  mov     [rax], di
0x18002675f  mov     rdx, rax; struct _HIDDENITEMID *
0x180026762  mov     rcx, r12; Src
0x180026765  call    ?ILCloneWithHiddenID@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEFBU_HIDDENITEMID@@PEAPEAU1@@Z; ILCloneWithHiddenID(_ITEMIDLIST_RELATIVE const *,_HIDDENITEMID const *,_ITEMIDLIST_RELATIVE * *)
0x18002676a  mov     rcx, [rbp+phglobal]; hMem
0x18002676e  mov     ebx, eax
0x180026770  call    cs:__imp_GlobalUnlock
0x180026776  jmp     short loc_18002677D
0x180026778  mov     ebx, 80070216h
0x18002677d  mov     rcx, [rbp+ppstm]
0x180026781  mov     rax, [rcx]
0x180026784  mov     rax, [rax+10h]
0x180026788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002678d  mov     rsi, [rsp+30h+arg_10]
0x180026792  mov     eax, ebx
0x180026794  mov     rbx, [rsp+30h+arg_0]
0x180026799  add     rsp, 30h
0x18002679d  pop     r15
0x18002679f  pop     r14
0x1800267a1  pop     r12
0x1800267a3  pop     rdi
0x1800267a4  pop     rbp
0x1800267a5  retn
```
