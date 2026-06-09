# CDBFolderDataObject::_GetFileGroupDescriptor(tagFORMATETC const *,tagSTGMEDIUM *)

- ea: `0x180082448`
- end: `0x180082795`
- name: `?_GetFileGroupDescriptor@CDBFolderDataObject@@AEAAJPEBUtagFORMATETC@@PEAUtagSTGMEDIUM@@@Z`
- size: `845`
- prototype: `__int64 __fastcall(CDBFolderDataObject *__hidden this, const struct tagFORMATETC *, struct tagSTGMEDIUM *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180081310`

## callees

- `0x18008141c`
- `0x180082448`
- `0x1800ea010`

## import_xrefs

- `SHCORE!SHUnicodeToAnsi` at `0x180082636`
- `SHCORE!SHUnicodeToAnsi` at `0x180082636`
- `Windows.Storage!SHCreateItemWithParent` at `0x180082557`
- `Windows.Storage!SHCreateItemWithParent` at `0x180082557`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082736`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180082736`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180082761`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180082761`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800824e8`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x1800824e8`

## pseudocode

```c
__int64 __fastcall CDBFolderDataObject::_GetFileGroupDescriptor(
        CDBFolderDataObject *this,
        const struct tagFORMATETC *a2,
        struct tagSTGMEDIUM *a3)
{
  HRESULT DefaultDestinationNameFromDisplayName; // ebx
  __int64 v7; // r9
  unsigned int v8; // ecx
  unsigned int v9; // eax
  unsigned int v10; // edx
  HBITMAP v11; // r15
  unsigned int v12; // r12d
  __int64 v13; // r8
  IShellFolder *v14; // rdx
  PCWSTR v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rdx
  HBITMAP v18; // rdi
  _WORD *v19; // rax
  _WORD *v20; // rcx
  struct IShellItem *v21; // rcx
  int v22; // rax^4
  int v23; // eax
  PCWSTR pwszSrc; // [rsp+30h] [rbp-10h] BYREF
  __int64 v26; // [rsp+38h] [rbp-8h] BYREF
  int v27; // [rsp+88h] [rbp+48h] BYREF
  struct IShellItem *ppvItem; // [rsp+98h] [rbp+58h] BYREF

  DefaultDestinationNameFromDisplayName = -2147221404;
  if ( (a2->tymed & 1) == 0 )
    return (unsigned int)DefaultDestinationNameFromDisplayName;
  v7 = (unsigned int)(*((_DWORD *)this + 8) - 1);
  v8 = -1;
  if ( a2->cfFormat == g_cfFileGroupDescriptorW )
  {
    if ( (unsigned __int64)(592 * v7) > 0xFFFFFFFF )
    {
      v8 = 0;
      DefaultDestinationNameFromDisplayName = -2147024362;
      goto LABEL_11;
    }
    v9 = 592 * v7 + 596;
    v10 = 596;
  }
  else
  {
    if ( (unsigned __int64)(332 * v7) > 0xFFFFFFFF )
      return (unsigned int)-2147024362;
    v9 = 332 * v7 + 336;
    v10 = 336;
  }
  if ( v9 >= v10 )
    v8 = v9;
  DefaultDestinationNameFromDisplayName = v9 < v10 ? 0x80070216 : 0;
LABEL_11:
  if ( DefaultDestinationNameFromDisplayName >= 0 )
  {
    v11 = (HBITMAP)GlobalAlloc(0x40u, v8);
    a3->hBitmap = v11;
    DefaultDestinationNameFromDisplayName = v11 == 0 ? 0x8007000E : 0;
    if ( v11 )
    {
      a3->tymed = 1;
      DefaultDestinationNameFromDisplayName = 0;
      v12 = 0;
      *(_DWORD *)v11 = *(_DWORD *)(HBITMAP)((int)this + 32);
      if ( *((_DWORD *)this + 8) )
      {
        while ( DefaultDestinationNameFromDisplayName >= 0 )
        {
          v13 = *((_QWORD *)this + 5);
          v14 = (IShellFolder *)*((_QWORD *)this + 3);
          ppvItem = 0;
          DefaultDestinationNameFromDisplayName = SHCreateItemWithParent(
                                                    0,
                                                    v14,
                                                    *(LPCITEMIDLIST *)(v13 + 8LL * v12),
                                                    &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93,
                                                    (void **)&ppvItem);
          if ( DefaultDestinationNameFromDisplayName >= 0 )
          {
            pwszSrc = 0;
            if ( !*((_DWORD *)this + 13)
              || (DefaultDestinationNameFromDisplayName = ((__int64 (__fastcall *)(struct IShellItem *, __int64, PCWSTR *))ppvItem->lpVtbl->GetDisplayName)(
                                                            ppvItem,
                                                            2147844096LL,
                                                            &pwszSrc),
                  !pwszSrc) )
            {
              DefaultDestinationNameFromDisplayName = GetDefaultDestinationNameFromDisplayName(
                                                        ppvItem,
                                                        0,
                                                        (unsigned __int16 **)&pwszSrc);
            }
            if ( DefaultDestinationNameFromDisplayName >= 0 )
            {
              if ( a2->cfFormat == g_cfFileGroupDescriptorW )
              {
                v15 = pwszSrc;
                v16 = 2147483646;
                v17 = 260;
                v18 = v11 + 148 * v12;
                v19 = v18 + 19;
                do
                {
                  if ( !v16 )
                    break;
                  if ( !*v15 )
                    break;
                  *v19++ = *v15++;
                  --v16;
                  --v17;
                }
                while ( v17 );
                v20 = v19 - 1;
                if ( v17 )
                  v20 = v19;
                DefaultDestinationNameFromDisplayName = v17 == 0 ? 0x8007007A : 0;
                *v20 = 0;
              }
              else
              {
                v18 = v11 + 83 * v12;
                if ( SHUnicodeToAnsi(pwszSrc, (PSTR)v18 + 76, 260) == 260 )
                  DefaultDestinationNameFromDisplayName = -2147467259;
              }
              if ( DefaultDestinationNameFromDisplayName >= 0 )
              {
                v21 = ppvItem;
                *((_DWORD *)v18 + 1) = 0x4000;
                v26 = 0;
                if ( ((int (__fastcall *)(struct IShellItem *, const PROPERTYKEY *, __int64 *))v21->lpVtbl[2].BindToHandler)(
                       v21,
                       &PKEY_Size,
                       &v26) >= 0 )
                {
                  v22 = HIDWORD(v26);
                  *((_DWORD *)v18 + 18) = v26;
                  *((_DWORD *)v18 + 1) |= 0x40u;
                  *((_DWORD *)v18 + 17) = v22;
                }
                v27 = 0;
                if ( ((int (__fastcall *)(struct IShellItem *, const PROPERTYKEY *, int *))ppvItem->lpVtbl[2].Release)(
                       ppvItem,
                       &PKEY_FileAttributes,
                       &v27) >= 0 )
                {
                  v23 = v27;
                  *((_DWORD *)v18 + 1) |= 4u;
                  *((_DWORD *)v18 + 10) = v23;
                }
                if ( ((int (__fastcall *)(struct IShellItem *, const PROPERTYKEY *, HBITMAP))ppvItem->lpVtbl[1].Compare)(
                       ppvItem,
                       &PKEY_DateModified,
                       v18 + 15) >= 0 )
                  *((_DWORD *)v18 + 1) |= 0x20u;
                if ( ((int (__fastcall *)(struct IShellItem *, const PROPERTYKEY *, HBITMAP))ppvItem->lpVtbl[1].Compare)(
                       ppvItem,
                       &PKEY_DateCreated,
                       v18 + 11) >= 0 )
                  *((_DWORD *)v18 + 1) |= 8u;
                if ( ((int (__fastcall *)(struct IShellItem *, const PROPERTYKEY *, HBITMAP))ppvItem->lpVtbl[1].Compare)(
                       ppvItem,
                       &PKEY_DateAccessed,
                       v18 + 13) >= 0 )
                  *((_DWORD *)v18 + 1) |= 0x10u;
              }
              CoTaskMemFree((LPVOID)pwszSrc);
            }
            ((void (__fastcall *)(struct IShellItem *))ppvItem->lpVtbl->Release)(ppvItem);
          }
          if ( ++v12 >= *((_DWORD *)this + 8) )
          {
            if ( DefaultDestinationNameFromDisplayName >= 0 )
              return (unsigned int)DefaultDestinationNameFromDisplayName;
            break;
          }
        }
        GlobalFree(a3->hBitmap);
        *(_OWORD *)&a3->tymed = 0;
        a3->pUnkForRelease = 0;
      }
    }
  }
  return (unsigned int)DefaultDestinationNameFromDisplayName;
}

```

## disassembly

```asm
0x180082448  mov     [rsp-38h+arg_0], rbx
0x18008244d  push    rbp
0x18008244e  push    rsi
0x18008244f  push    rdi
0x180082450  push    r12
0x180082452  push    r13
0x180082454  push    r14
0x180082456  push    r15
0x180082458  mov     rbp, rsp
0x18008245b  sub     rsp, 40h
0x18008245f  test    byte ptr [rdx+18h], 1
0x180082463  mov     r14, r8
0x180082466  mov     r13, rdx
0x180082469  mov     rsi, rcx
0x18008246c  mov     ebx, 80040064h
0x180082471  jz      loc_18008277B
0x180082477  mov     r9d, [rcx+20h]
0x18008247b  xor     edi, edi
0x18008247d  movzx   eax, cs:?g_cfFileGroupDescriptorW@@3GA; ushort g_cfFileGroupDescriptorW
0x180082484  dec     r9d
0x180082487  mov     ecx, 0FFFFFFFFh
0x18008248c  cmp     [rdx], ax
0x18008248f  jnz     short loc_1800824B2
0x180082491  imul    rax, r9, 250h
0x180082498  cmp     rax, rcx
0x18008249b  ja      short loc_1800824A9
0x18008249d  add     eax, 254h
0x1800824a2  mov     edx, 254h
0x1800824a7  jmp     short loc_1800824CC
0x1800824a9  mov     ecx, edi
0x1800824ab  mov     ebx, 80070216h
0x1800824b0  jmp     short loc_1800824D9
0x1800824b2  imul    rax, r9, 14Ch
0x1800824b9  cmp     rax, rcx
0x1800824bc  ja      loc_180082776
0x1800824c2  add     eax, 150h
0x1800824c7  mov     edx, 150h
0x1800824cc  cmp     eax, edx
0x1800824ce  cmovnb  ecx, eax
0x1800824d1  sbb     ebx, ebx
0x1800824d3  and     ebx, 80070216h
0x1800824d9  test    ebx, ebx
0x1800824db  js      loc_18008277B
0x1800824e1  mov     edx, ecx; dwBytes
0x1800824e3  mov     ecx, 40h ; '@'; uFlags
0x1800824e8  call    cs:__imp_GlobalAlloc
0x1800824ee  mov     r15, rax
0x1800824f1  mov     [r14+8], rax
0x1800824f5  neg     rax
0x1800824f8  sbb     ebx, ebx
0x1800824fa  not     ebx
0x1800824fc  and     ebx, 8007000Eh
0x180082502  test    r15, r15
0x180082505  jz      loc_18008277B
0x18008250b  mov     dword ptr [r14], 1
0x180082512  mov     ebx, edi
0x180082514  mov     eax, [rsi+20h]
0x180082517  mov     r12d, edi
0x18008251a  mov     [r15], eax
0x18008251d  cmp     [rsi+20h], edi
0x180082520  jbe     loc_18008277B
0x180082526  jmp     short loc_18008252A
0x180082528  xor     edi, edi
0x18008252a  test    ebx, ebx
0x18008252c  js      loc_18008275D
0x180082532  mov     r8, [rsi+28h]
0x180082536  lea     rax, [rbp+arg_18]
0x18008253a  mov     rdx, [rsi+18h]; psfParent
0x18008253e  lea     r9, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x180082545  mov     [rbp+arg_18], rdi
0x180082549  xor     ecx, ecx; pidlParent
0x18008254b  mov     edi, r12d
0x18008254e  mov     [rsp+40h+ppvItem], rax; ppvItem
0x180082553  mov     r8, [r8+rdi*8]; pidl
0x180082557  call    cs:__imp_SHCreateItemWithParent
0x18008255d  mov     ebx, eax
0x18008255f  xor     eax, eax
0x180082561  test    ebx, ebx
0x180082563  js      loc_18008274C
0x180082569  mov     [rbp+pwszSrc], rax
0x18008256d  cmp     [rsi+34h], eax
0x180082570  jz      short loc_180082596
0x180082572  mov     rcx, [rbp+arg_18]
0x180082576  lea     r8, [rbp+pwszSrc]
0x18008257a  mov     edx, 80058000h
0x18008257f  mov     rax, [rcx]
0x180082582  mov     rax, [rax+28h]
0x180082586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008258b  xor     r10d, r10d
0x18008258e  mov     ebx, eax
0x180082590  cmp     [rbp+pwszSrc], r10
0x180082594  jnz     short loc_1800825AA
0x180082596  mov     rcx, [rbp+arg_18]; struct IShellItem *
0x18008259a  lea     r8, [rbp+pwszSrc]; unsigned __int16 **
0x18008259e  xor     edx, edx; struct IShellItem *
0x1800825a0  call    ?GetDefaultDestinationNameFromDisplayName@@YAJPEAUIShellItem@@0PEAPEAG@Z; GetDefaultDestinationNameFromDisplayName(IShellItem *,IShellItem *,ushort * *)
0x1800825a5  mov     ebx, eax
0x1800825a7  xor     r10d, r10d
0x1800825aa  test    ebx, ebx
0x1800825ac  js      loc_18008273C
0x1800825b2  movzx   eax, cs:?g_cfFileGroupDescriptorW@@3GA; ushort g_cfFileGroupDescriptorW
0x1800825b9  cmp     [r13+0], ax
0x1800825be  jnz     short loc_18008261E
0x1800825c0  mov     r8, [rbp+pwszSrc]
0x1800825c4  mov     ecx, 7FFFFFFEh
0x1800825c9  imul    rdi, 250h
0x1800825d0  mov     edx, 104h
0x1800825d5  add     rdi, r15
0x1800825d8  lea     rax, [rdi+4Ch]
0x1800825dc  test    rcx, rcx
0x1800825df  jz      short loc_180082600
0x1800825e1  movzx   r9d, word ptr [r8]
0x1800825e5  test    r9w, r9w
0x1800825e9  jz      short loc_180082600
0x1800825eb  mov     [rax], r9w
0x1800825ef  add     r8, 2
0x1800825f3  add     rax, 2
0x1800825f7  dec     rcx
0x1800825fa  sub     rdx, 1
0x1800825fe  jnz     short loc_1800825DC
0x180082600  test    rdx, rdx
0x180082603  lea     rcx, [rax-2]
0x180082607  cmovnz  rcx, rax
0x18008260b  neg     rdx
0x18008260e  sbb     ebx, ebx
0x180082610  not     ebx
0x180082612  and     ebx, 8007007Ah
0x180082618  mov     [rcx], r10w
0x18008261c  jmp     short loc_18008264C
0x18008261e  mov     rcx, [rbp+pwszSrc]; pwszSrc
0x180082622  mov     r8d, 104h; cchBuf
0x180082628  imul    rdi, 14Ch
0x18008262f  add     rdi, r15
0x180082632  lea     rdx, [rdi+4Ch]; pszDst
0x180082636  call    cs:__imp_SHUnicodeToAnsi
0x18008263c  cmp     eax, 104h
0x180082641  mov     ecx, 80004005h
0x180082646  cmovz   ebx, ecx
0x180082649  xor     r10d, r10d
0x18008264c  test    ebx, ebx
0x18008264e  js      loc_180082732
0x180082654  mov     rcx, [rbp+arg_18]
0x180082658  lea     r8, [rbp+var_8]
0x18008265c  mov     dword ptr [rdi+4], 4000h
0x180082663  lea     rdx, PKEY_Size
0x18008266a  mov     [rbp+var_8], r10
0x18008266e  mov     rax, [rcx]
0x180082671  mov     rax, [rax+98h]
0x180082678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008267d  test    eax, eax
0x18008267f  js      short loc_180082696
0x180082681  mov     rcx, [rbp+var_8]
0x180082685  mov     rax, rcx
0x180082688  mov     [rdi+48h], ecx
0x18008268b  shr     rax, 20h
0x18008268f  or      dword ptr [rdi+4], 40h
0x180082693  mov     [rdi+44h], eax
0x180082696  mov     rcx, [rbp+arg_18]
0x18008269a  lea     r8, [rbp+arg_8]
0x18008269e  mov     [rbp+arg_8], 0
0x1800826a5  lea     rdx, PKEY_FileAttributes
0x1800826ac  mov     rax, [rcx]
0x1800826af  mov     rax, [rax+90h]
0x1800826b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800826bb  test    eax, eax
0x1800826bd  js      short loc_1800826C9
0x1800826bf  mov     eax, [rbp+arg_8]
0x1800826c2  or      dword ptr [rdi+4], 4
0x1800826c6  mov     [rdi+28h], eax
0x1800826c9  mov     rcx, [rbp+arg_18]
0x1800826cd  lea     r8, [rdi+3Ch]
0x1800826d1  lea     rdx, PKEY_DateModified
0x1800826d8  mov     rax, [rcx]
0x1800826db  mov     rax, [rax+78h]
0x1800826df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800826e4  test    eax, eax
0x1800826e6  js      short loc_1800826EC
0x1800826e8  or      dword ptr [rdi+4], 20h
0x1800826ec  mov     rcx, [rbp+arg_18]
0x1800826f0  lea     r8, [rdi+2Ch]
0x1800826f4  lea     rdx, PKEY_DateCreated
0x1800826fb  mov     rax, [rcx]
0x1800826fe  mov     rax, [rax+78h]
0x180082702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082707  test    eax, eax
0x180082709  js      short loc_18008270F
0x18008270b  or      dword ptr [rdi+4], 8
0x18008270f  mov     rcx, [rbp+arg_18]
0x180082713  lea     r8, [rdi+34h]
0x180082717  lea     rdx, PKEY_DateAccessed
0x18008271e  mov     rax, [rcx]
0x180082721  mov     rax, [rax+78h]
0x180082725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008272a  test    eax, eax
0x18008272c  js      short loc_180082732
0x18008272e  or      dword ptr [rdi+4], 10h
0x180082732  mov     rcx, [rbp+pwszSrc]; pv
0x180082736  call    cs:__imp_CoTaskMemFree
0x18008273c  mov     rcx, [rbp+arg_18]
0x180082740  mov     rax, [rcx]
0x180082743  mov     rax, [rax+10h]
0x180082747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008274c  inc     r12d
0x18008274f  cmp     r12d, [rsi+20h]
0x180082753  jb      loc_180082528
0x180082759  test    ebx, ebx
0x18008275b  jns     short loc_18008277B
0x18008275d  mov     rcx, [r14+8]; hMem
0x180082761  call    cs:__imp_GlobalFree
0x180082767  xorps   xmm0, xmm0
0x18008276a  xor     eax, eax
0x18008276c  movups  xmmword ptr [r14], xmm0
0x180082770  mov     [r14+10h], rax
0x180082774  jmp     short loc_18008277B
0x180082776  mov     ebx, 80070216h
0x18008277b  mov     eax, ebx
0x18008277d  mov     rbx, [rsp+40h+arg_0]
0x180082785  add     rsp, 40h
0x180082789  pop     r15
0x18008278b  pop     r14
0x18008278d  pop     r13
0x18008278f  pop     r12
0x180082791  pop     rdi
0x180082792  pop     rsi
0x180082793  pop     rbp
0x180082794  retn
```
