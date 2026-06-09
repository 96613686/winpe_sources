# CARPFolderViewCB::_OnAction(IUnknown *,IShellItemArray *,ulong)

- ea: `0x18001a934`
- end: `0x18001aae6`
- name: `?_OnAction@CARPFolderViewCB@@CAJPEAUIUnknown@@PEAUIShellItemArray@@K@Z`
- size: `434`
- prototype: `__int64 __fastcall(struct IUnknown *, struct IShellItemArray *, int)`
- caller_count: `4`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x18001aaf0`
- `0x18001ab10`
- `0x18001abe0`
- `0x18001ac00`

## callees

- `0x180011da0`
- `0x180013490`
- `0x1800172c4`
- `0x180017300`
- `0x18001a028`
- `0x18001a808`
- `0x18001a934`
- `0x18001acb0`

## import_xrefs

- `SHCORE!SHCreateThread` at `0x18001aaa5`
- `SHCORE!SHCreateThread` at `0x18001aaa5`
- `SHCORE!__imp_ualstrcpynW` at `0x18001aa7c`
- `SHCORE!__imp_ualstrcpynW` at `0x18001aa7c`
- `SHELL32!__imp_ILFree` at `0x18001aac7`
- `SHELL32!__imp_ILFree` at `0x18001aad1`
- `SHELL32!__imp_ILFree` at `0x18001aac7`
- `SHELL32!__imp_ILFree` at `0x18001aad1`

## pseudocode

```c
__int64 __fastcall CARPFolderViewCB::_OnAction(struct IUnknown *a1, struct IShellItemArray *a2, int a3)
{
  int FirstParentAndItemFromShellItemArray; // ebx
  void *v7; // rcx
  char *v8; // rdi
  __int64 IsValid; // rax
  __int64 v10; // rsi
  _OWORD *v11; // rdx
  _OWORD *v12; // rcx
  __int64 v13; // rax
  __int128 v14; // xmm1
  LPITEMIDLIST pidl; // [rsp+20h] [rbp-18h] BYREF
  void *pData; // [rsp+88h] [rbp+50h] BYREF

  FirstParentAndItemFromShellItemArray = 0;
  pData = 0;
  if ( (unsigned int)CARPFolderViewCB::_SingleItemSelected(a2) )
  {
    FirstParentAndItemFromShellItemArray = CTLocalAllocPolicy::Alloc(v7, 0x40u, 0x43Cu, &pData);
    if ( FirstParentAndItemFromShellItemArray >= 0 )
    {
      v8 = (char *)pData;
      *((_DWORD *)pData + 4) = a3;
      pData = 0;
      pidl = 0;
      FirstParentAndItemFromShellItemArray = CARPFolderViewCB::_GetFirstParentAndItemFromShellItemArray(
                                               a2,
                                               (struct _ITEMID_CHILD **)&pData,
                                               (struct _ITEMIDLIST_ABSOLUTE **)&pidl);
      if ( FirstParentAndItemFromShellItemArray >= 0 )
      {
        FirstParentAndItemFromShellItemArray = SHILCloneFirst(
                                                 (const struct _ITEMIDLIST_RELATIVE *)pData,
                                                 (struct _ITEMID_CHILD **)v8 + 1);
        if ( FirstParentAndItemFromShellItemArray >= 0 )
        {
          FirstParentAndItemFromShellItemArray = SHILClone(
                                                   (const struct _ITEMIDLIST_RELATIVE *)pidl,
                                                   (struct _ITEMIDLIST_RELATIVE **)v8);
          if ( FirstParentAndItemFromShellItemArray >= 0 )
          {
            *((struct IUnknown *)v8 + 3) = a1[12];
            IsValid = CItemIDFactory<tagARPITEM,1230000705>::_IsValid(pData);
            v10 = (IsValid + 14) & -(__int64)(IsValid != 0);
            if ( v10 )
            {
              FirstParentAndItemFromShellItemArray = 0;
              v11 = (_OWORD *)(v10 + 12);
              v12 = v8 + 36;
              if ( *(_DWORD *)(((IsValid + 14) & -(__int64)(IsValid != 0)) + 4) )
              {
                ualstrcpynW(v12, v11, 260);
              }
              else
              {
                v13 = 8;
                do
                {
                  *v12 = *v11;
                  v12[1] = v11[1];
                  v12[2] = v11[2];
                  v12[3] = v11[3];
                  v12[4] = v11[4];
                  v12[5] = v11[5];
                  v12[6] = v11[6];
                  v14 = v11[7];
                  v11 += 8;
                  v12[7] = v14;
                  v12 += 8;
                  --v13;
                }
                while ( v13 );
                *v12 = *v11;
                *((_QWORD *)v12 + 2) = *((_QWORD *)v11 + 2);
              }
              *((_DWORD *)v8 + 5) = *(_DWORD *)(v10 + 4);
              *((_DWORD *)v8 + 8) = a1[11].lpVtbl[5].AddRef;
              if ( !SHCreateThread(InvokeActionOnInstalledApp, v8, 8u, 0) )
              {
                FreePublishedAppDataParam(v8);
                FirstParentAndItemFromShellItemArray = -2147467259;
              }
            }
            else
            {
              FirstParentAndItemFromShellItemArray = -2147024809;
            }
          }
        }
        ILFree((LPITEMIDLIST)pData);
        ILFree(pidl);
      }
    }
  }
  return (unsigned int)FirstParentAndItemFromShellItemArray;
}

```

## disassembly

```asm
0x18001a934  push    rbp
0x18001a936  push    rbx
0x18001a937  push    rsi
0x18001a938  push    rdi
0x18001a939  push    r14
0x18001a93b  push    r15
0x18001a93d  mov     rbp, rsp
0x18001a940  sub     rsp, 38h
0x18001a944  mov     r15, rcx
0x18001a947  xor     ebx, ebx
0x18001a949  mov     rcx, rdx; struct IShellItemArray *
0x18001a94c  mov     [rbp+pData], rbx
0x18001a950  mov     r14d, r8d
0x18001a953  mov     rsi, rdx
0x18001a956  call    ?_SingleItemSelected@CARPFolderViewCB@@CAHPEAUIShellItemArray@@@Z; CARPFolderViewCB::_SingleItemSelected(IShellItemArray *)
0x18001a95b  test    eax, eax
0x18001a95d  jz      loc_18001AAD7
0x18001a963  lea     r9, [rbp+pData]; void **
0x18001a967  mov     r8d, 43Ch; unsigned __int64
0x18001a96d  lea     edx, [rbx+40h]; unsigned int
0x18001a970  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18001a975  mov     ebx, eax
0x18001a977  test    eax, eax
0x18001a979  js      loc_18001AAD7
0x18001a97f  mov     rdi, [rbp+pData]
0x18001a983  lea     r8, [rbp+pidl]; struct _ITEMIDLIST_ABSOLUTE **
0x18001a987  lea     rdx, [rbp+pData]; struct _ITEMID_CHILD **
0x18001a98b  mov     rcx, rsi; struct IShellItemArray *
0x18001a98e  mov     [rdi+10h], r14d
0x18001a992  mov     [rbp+pData], 0
0x18001a99a  mov     [rbp+pidl], 0
0x18001a9a2  call    ?_GetFirstParentAndItemFromShellItemArray@CARPFolderViewCB@@CAJPEAUIShellItemArray@@PEAPEAU_ITEMID_CHILD@@PEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CARPFolderViewCB::_GetFirstParentAndItemFromShellItemArray(IShellItemArray *,_ITEMID_CHILD * *,_ITEMIDLIST_ABSOLUTE * *)
0x18001a9a7  mov     ebx, eax
0x18001a9a9  test    eax, eax
0x18001a9ab  js      loc_18001AAD7
0x18001a9b1  mov     rcx, [rbp+pData]; struct _ITEMIDLIST_RELATIVE *
0x18001a9b5  lea     rdx, [rdi+8]; struct _ITEMID_CHILD **
0x18001a9b9  call    ?SHILCloneFirst@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU_ITEMID_CHILD@@@Z; SHILCloneFirst(_ITEMIDLIST_RELATIVE const *,_ITEMID_CHILD * *)
0x18001a9be  mov     ebx, eax
0x18001a9c0  test    eax, eax
0x18001a9c2  js      loc_18001AAC3
0x18001a9c8  mov     rcx, [rbp+pidl]; struct _ITEMIDLIST_RELATIVE *
0x18001a9cc  mov     rdx, rdi; struct _ITEMIDLIST_RELATIVE **
0x18001a9cf  call    ?SHILClone@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILClone(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE * *)
0x18001a9d4  mov     ebx, eax
0x18001a9d6  test    eax, eax
0x18001a9d8  js      loc_18001AAC3
0x18001a9de  mov     rax, [r15+60h]
0x18001a9e2  mov     [rdi+18h], rax
0x18001a9e6  mov     rcx, [rbp+pData]
0x18001a9ea  call    ?_IsValid@?$CItemIDFactory@UtagARPITEM@@$0EJFAFCEB@@@CAPEFBUCHILDITEMID@1@PEFBU_ITEMIDLIST_RELATIVE@@@Z; CItemIDFactory<tagARPITEM,1230000705>::_IsValid(_ITEMIDLIST_RELATIVE const *)
0x18001a9ef  lea     rcx, [rax+0Eh]
0x18001a9f3  neg     rax
0x18001a9f6  sbb     rsi, rsi
0x18001a9f9  and     rsi, rcx
0x18001a9fc  jz      loc_18001AABE
0x18001aa02  xor     ebx, ebx
0x18001aa04  lea     rdx, [rsi+0Ch]
0x18001aa08  lea     rcx, [rdi+24h]
0x18001aa0c  lea     r14d, [rbx+8]
0x18001aa10  cmp     [rsi+4], ebx
0x18001aa13  jnz     short loc_18001AA76
0x18001aa15  mov     eax, r14d
0x18001aa18  lea     r8d, [r14+78h]
0x18001aa1c  movups  xmm0, xmmword ptr [rdx]
0x18001aa1f  movups  xmmword ptr [rcx], xmm0
0x18001aa22  movups  xmm1, xmmword ptr [rdx+10h]
0x18001aa26  movups  xmmword ptr [rcx+10h], xmm1
0x18001aa2a  movups  xmm0, xmmword ptr [rdx+20h]
0x18001aa2e  movups  xmmword ptr [rcx+20h], xmm0
0x18001aa32  movups  xmm1, xmmword ptr [rdx+30h]
0x18001aa36  movups  xmmword ptr [rcx+30h], xmm1
0x18001aa3a  movups  xmm0, xmmword ptr [rdx+40h]
0x18001aa3e  movups  xmmword ptr [rcx+40h], xmm0
0x18001aa42  movups  xmm1, xmmword ptr [rdx+50h]
0x18001aa46  movups  xmmword ptr [rcx+50h], xmm1
0x18001aa4a  movups  xmm0, xmmword ptr [rdx+60h]
0x18001aa4e  movups  xmmword ptr [rcx+60h], xmm0
0x18001aa52  movups  xmm1, xmmword ptr [rdx+70h]
0x18001aa56  add     rdx, r8
0x18001aa59  movups  xmmword ptr [rcx+70h], xmm1
0x18001aa5d  add     rcx, r8
0x18001aa60  sub     rax, 1
0x18001aa64  jnz     short loc_18001AA1C
0x18001aa66  movups  xmm0, xmmword ptr [rdx]
0x18001aa69  movups  xmmword ptr [rcx], xmm0
0x18001aa6c  mov     rax, [rdx+10h]
0x18001aa70  mov     [rcx+10h], rax
0x18001aa74  jmp     short loc_18001AA82
0x18001aa76  mov     r8d, 104h
0x18001aa7c  call    cs:__imp_ualstrcpynW
0x18001aa82  mov     eax, [rsi+4]
0x18001aa85  lea     rcx, ?InvokeActionOnInstalledApp@@YAKPEAX@Z; pfnThreadProc
0x18001aa8c  mov     [rdi+14h], eax
0x18001aa8f  xor     r9d, r9d; pfnCallback
0x18001aa92  mov     rax, [r15+58h]
0x18001aa96  mov     r8d, r14d; flags
0x18001aa99  mov     edx, [rax+80h]
0x18001aa9f  mov     [rdi+20h], edx
0x18001aaa2  mov     rdx, rdi; pData
0x18001aaa5  call    cs:__imp_SHCreateThread
0x18001aaab  test    eax, eax
0x18001aaad  jnz     short loc_18001AAC3
0x18001aaaf  mov     rcx, rdi; hMem
0x18001aab2  call    ?FreePublishedAppDataParam@@YAXPEAUtagPublishedAppData@@@Z; FreePublishedAppDataParam(tagPublishedAppData *)
0x18001aab7  mov     ebx, 80004005h
0x18001aabc  jmp     short loc_18001AAC3
0x18001aabe  mov     ebx, 80070057h
0x18001aac3  mov     rcx, [rbp+pData]; pidl
0x18001aac7  call    cs:__imp_ILFree
0x18001aacd  mov     rcx, [rbp+pidl]; pidl
0x18001aad1  call    cs:__imp_ILFree
0x18001aad7  mov     eax, ebx
0x18001aad9  add     rsp, 38h
0x18001aadd  pop     r15
0x18001aadf  pop     r14
0x18001aae1  pop     rdi
0x18001aae2  pop     rsi
0x18001aae3  pop     rbx
0x18001aae4  pop     rbp
0x18001aae5  retn
```
