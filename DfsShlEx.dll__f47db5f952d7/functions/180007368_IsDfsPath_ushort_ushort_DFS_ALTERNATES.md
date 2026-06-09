# IsDfsPath(ushort *,ushort * *,DFS_ALTERNATES * * *)

- ea: `0x180007368`
- end: `0x180007811`
- name: `?IsDfsPath@@YA_NPEAGPEAPEAGPEAPEAPEAVDFS_ALTERNATES@@@Z`
- size: `1193`
- prototype: `bool __fastcall(unsigned __int16 *, unsigned __int16 **, struct DFS_ALTERNATES ***)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180007f20`

## callees

- `0x180002468`
- `0x180002490`
- `0x180004328`
- `0x180007090`
- `0x1800071d0`
- `0x180007368`
- `0x180007818`
- `0x180007b10`
- `0x18000a9d0`

## import_xrefs

- `msvcrt!_wcsdup` at `0x1800073c3`
- `msvcrt!_wcsdup` at `0x1800073c3`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007689`
- `msvcrt!??3@YAXPEAX@Z` at `0x180007689`
- `msvcrt!wcsnlen` at `0x180007401`
- `msvcrt!wcsnlen` at `0x180007401`
- `msvcrt!free` at `0x1800074bd`
- `msvcrt!free` at `0x1800074f9`
- `msvcrt!free` at `0x1800077f8`
- `msvcrt!free` at `0x1800074bd`
- `msvcrt!free` at `0x1800074f9`
- `msvcrt!free` at `0x1800077f8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800075e4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000769f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800076ab`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800075e4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000769f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800076ab`
- `msvcrt!calloc` at `0x1800074ac`
- `msvcrt!calloc` at `0x1800074ac`
- `KERNEL32!GetDriveTypeW` at `0x180007457`
- `KERNEL32!GetDriveTypeW` at `0x180007457`
- `OLEAUT32!__imp_SysAllocString` at `0x1800076f9`
- `OLEAUT32!__imp_SysAllocString` at `0x180007739`
- `OLEAUT32!__imp_SysAllocString` at `0x18000777d`
- `OLEAUT32!__imp_SysAllocString` at `0x1800076f9`
- `OLEAUT32!__imp_SysAllocString` at `0x180007739`
- `OLEAUT32!__imp_SysAllocString` at `0x18000777d`
- `OLEAUT32!__imp_SysFreeString` at `0x18000766d`
- `OLEAUT32!__imp_SysFreeString` at `0x180007677`
- `OLEAUT32!__imp_SysFreeString` at `0x180007680`
- `OLEAUT32!__imp_SysFreeString` at `0x1800076e9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000772b`
- `OLEAUT32!__imp_SysFreeString` at `0x180007770`
- `OLEAUT32!__imp_SysFreeString` at `0x18000766d`
- `OLEAUT32!__imp_SysFreeString` at `0x180007677`
- `OLEAUT32!__imp_SysFreeString` at `0x180007680`
- `OLEAUT32!__imp_SysFreeString` at `0x1800076e9`
- `OLEAUT32!__imp_SysFreeString` at `0x18000772b`
- `OLEAUT32!__imp_SysFreeString` at `0x180007770`
- `netutils!NetApiBufferFree` at `0x1800077ef`
- `netutils!NetApiBufferFree` at `0x1800077ef`

## pseudocode

```c
char __fastcall IsDfsPath(unsigned __int16 *a1, unsigned __int16 **a2, struct DFS_ALTERNATES ***a3)
{
  __int64 v6; // rbp
  unsigned __int16 *v7; // r12
  WCHAR v9; // cx
  void *v10; // rsi
  __int64 v11; // rax
  size_t v12; // r15
  __int64 v13; // rax
  char v14; // r13
  _DWORD *v15; // rbx
  __int64 v16; // rax
  int v17; // esi
  __int64 v18; // rcx
  unsigned __int64 v19; // rbp
  unsigned __int64 v20; // rax
  unsigned __int16 *v21; // rax
  const unsigned __int16 *v22; // r8
  unsigned __int64 v23; // rax
  struct DFS_ALTERNATES **v24; // rax
  unsigned int v25; // esi
  struct DFS_ALTERNATES *v26; // rax
  struct DFS_ALTERNATES *v27; // rdx
  __int64 v28; // rbp
  BSTR *v29; // r15
  unsigned int i; // ebp
  const OLECHAR *v31; // r15
  struct DFS_ALTERNATES *v32; // r14
  OLECHAR *v33; // rcx
  BSTR v34; // rax
  const OLECHAR *v35; // r15
  struct DFS_ALTERNATES *v36; // r14
  OLECHAR *v37; // rcx
  BSTR v38; // rax
  BSTR *v39; // r14
  BSTR v40; // rax
  void *Block; // [rsp+30h] [rbp-58h] BYREF
  WCHAR SourceString[8]; // [rsp+38h] [rbp-50h] BYREF

  if ( !a1 || !*a1 || !a3 || !a2 )
    return 0;
  *a3 = 0;
  v6 = -1;
  *a2 = 0;
  if ( *a1 == 92 )
  {
    v7 = _wcsdup(a1);
    if ( !v7 )
      return 0;
  }
  else
  {
    if ( wcsnlen(a1, 3u) < 3 )
      return 0;
    if ( a1[1] != 58 )
      return 0;
    if ( a1[2] != 92 )
      return 0;
    v9 = *a1;
    if ( (unsigned __int16)(*a1 - 97) > 0x19u && (unsigned __int16)(v9 - 65) > 0x19u )
      return 0;
    wcscpy(SourceString, L"\\??\\C:\\");
    SourceString[4] = v9;
    if ( GetDriveTypeW(&SourceString[4]) != 4 )
      return 0;
    Block = 0;
    if ( GetRemotePath(SourceString, (unsigned __int16 **)&Block) < 0 )
      return 0;
    v10 = Block;
    do
      ++v6;
    while ( *((_WORD *)Block + v6) );
    v11 = -1;
    do
      ++v11;
    while ( a1[v11] );
    v12 = (int)v6 + (int)v11;
    v7 = (unsigned __int16 *)calloc(v12, 2u);
    if ( !v7 )
    {
      free(v10);
      return 0;
    }
    v13 = 3;
    if ( *((_WORD *)v10 + v6 - 1) != 92 )
      v13 = 2;
    StringCchPrintfW(v7, v12, L"%s%s", v10, &a1[v13]);
    free(v10);
  }
  Block = 0;
  v14 = 0;
  if ( (int)ResolveDfsPath(v7, (struct _DFS_INFO_3 **)&Block) >= 0 )
  {
    v15 = Block;
    if ( Block )
    {
      v16 = *(_QWORD *)Block;
      if ( **(_WORD **)Block != 92 || (v17 = 1, *(_WORD *)(v16 + 2) == 92) )
        v17 = 0;
      v18 = -1;
      do
        ++v18;
      while ( *(_WORD *)(v16 + 2 * v18) );
      v19 = v17 + (int)v18 + 1;
      v20 = 2 * v19;
      if ( !is_mul_ok(v19, 2u) )
        v20 = -1;
      v21 = (unsigned __int16 *)operator new[](v20, (const struct std::nothrow_t *)&std::nothrow);
      *a2 = v21;
      if ( v21 )
      {
        v22 = L"\\%s";
        if ( !v17 )
          v22 = L"%s";
        StringCchPrintfW(v21, v19, v22, *(_QWORD *)v15);
        v23 = 8LL * (unsigned int)(v15[5] + 1);
        if ( !is_mul_ok((unsigned int)(v15[5] + 1), 8u) )
          v23 = -1;
        v24 = (struct DFS_ALTERNATES **)operator new[](v23, (const struct std::nothrow_t *)&std::nothrow);
        *a3 = v24;
        if ( v24 )
        {
          v25 = 0;
          v24[v15[5]] = 0;
          if ( v15[5] )
          {
            while ( 1 )
            {
              v26 = (struct DFS_ALTERNATES *)operator new(0x20u, (const struct std::nothrow_t *)&std::nothrow);
              *(_QWORD *)SourceString = v26;
              v27 = v26;
              if ( v26 )
              {
                *(_QWORD *)v26 = 0;
                *((_QWORD *)v26 + 1) = 0;
                *((_QWORD *)v26 + 2) = 0;
                *((_DWORD *)v26 + 6) = 3;
              }
              else
              {
                v27 = 0;
              }
              (*a3)[v25] = v27;
              if ( !(*a3)[v25] )
                break;
              if ( ++v25 >= v15[5] )
                goto LABEL_53;
            }
            v28 = v25 - 1;
            if ( (int)v28 >= 0 )
            {
              do
              {
                v29 = (BSTR *)(*a3)[v28];
                if ( v29 )
                {
                  SysFreeString(v29[2]);
                  SysFreeString(v29[1]);
                  SysFreeString(*v29);
                  operator delete(v29);
                }
                v28 = (unsigned int)(v28 - 1);
              }
              while ( (int)v28 >= 0 );
              v15 = Block;
            }
            operator delete[](*a3);
            *a3 = 0;
            operator delete[](*a2);
            *a2 = 0;
          }
LABEL_53:
          if ( v25 >= v15[5] )
          {
            for ( i = 0; i < v15[5]; ++i )
            {
              v31 = *(const OLECHAR **)(*((_QWORD *)v15 + 3) + 24LL * i + 8);
              v32 = (*a3)[i];
              v33 = (OLECHAR *)*((_QWORD *)v32 + 1);
              if ( v31 != v33 )
              {
                SysFreeString(v33);
                if ( v31 )
                {
                  v34 = SysAllocString(v31);
                  *((_QWORD *)v32 + 1) = v34;
                  if ( !v34 )
                    goto LABEL_74;
                }
                else
                {
                  *((_QWORD *)v32 + 1) = 0;
                }
              }
              v35 = *(const OLECHAR **)(*((_QWORD *)v15 + 3) + 24LL * i + 16);
              v36 = (*a3)[i];
              v37 = (OLECHAR *)*((_QWORD *)v36 + 2);
              if ( v35 == v37 )
              {
                LODWORD(v35) = 0;
              }
              else
              {
                SysFreeString(v37);
                if ( v35 )
                {
                  v38 = SysAllocString(v35);
                  LODWORD(v35) = 0;
                  *((_QWORD *)v36 + 2) = v38;
                  if ( !v38 )
                    goto LABEL_74;
                }
                else
                {
                  *((_QWORD *)v36 + 2) = 0;
                }
              }
              v39 = (BSTR *)(*a3)[i];
              if ( L"\\\\" != *v39 )
              {
                SysFreeString(*v39);
                v40 = SysAllocString(L"\\\\");
                *v39 = v40;
                if ( !v40 )
LABEL_74:
                  ATL::AtlThrowImpl(-2147024882);
              }
              ATL::CComBSTR::operator+=((*a3)[i], *(_QWORD *)(*((_QWORD *)v15 + 3) + 24LL * i + 8));
              ATL::CComBSTR::operator+=((*a3)[i], L"\\");
              ATL::CComBSTR::operator+=((*a3)[i], *(_QWORD *)(*((_QWORD *)v15 + 3) + 24LL * i + 16));
              if ( (*(_BYTE *)(*((_QWORD *)v15 + 3) + 24LL * i) & 4) != 0 )
                *((_DWORD *)(*a3)[i] + 6) = (_DWORD)v35;
            }
            v14 = 1;
          }
        }
        else
        {
          operator delete[](*a2);
          *a2 = 0;
        }
      }
      NetApiBufferFree(v15);
    }
  }
  free(v7);
  return v14;
}

```

## disassembly

```asm
0x180007368  mov     [rsp+arg_18], rbx
0x18000736d  push    rbp
0x18000736e  push    rsi
0x18000736f  push    rdi
0x180007370  push    r12
0x180007372  push    r13
0x180007374  push    r14
0x180007376  push    r15
0x180007378  sub     rsp, 50h
0x18000737c  mov     rax, cs:__security_cookie
0x180007383  xor     rax, rsp
0x180007386  mov     [rsp+88h+var_40], rax
0x18000738b  xor     r15d, r15d
0x18000738e  mov     rdi, r8
0x180007391  mov     r14, rdx
0x180007394  mov     rbx, rcx
0x180007397  test    rcx, rcx
0x18000739a  jz      short loc_1800073D5
0x18000739c  cmp     [rcx], r15w
0x1800073a0  jz      short loc_1800073D5
0x1800073a2  test    r8, r8
0x1800073a5  jz      short loc_1800073D5
0x1800073a7  test    rdx, rdx
0x1800073aa  jz      short loc_1800073D5
0x1800073ac  mov     [r8], r15
0x1800073af  lea     esi, [r15+5Ch]
0x1800073b3  or      rbp, 0FFFFFFFFFFFFFFFFh
0x1800073b7  mov     [rdx], r15
0x1800073ba  lea     r13d, [r15+4]
0x1800073be  cmp     si, [rcx]
0x1800073c1  jnz     short loc_1800073FC
0x1800073c3  call    cs:__imp__wcsdup
0x1800073c9  mov     r12, rax
0x1800073cc  test    rax, rax
0x1800073cf  jnz     loc_18000750A
0x1800073d5  xor     al, al
0x1800073d7  mov     rcx, [rsp+88h+var_40]
0x1800073dc  xor     rcx, rsp; StackCookie
0x1800073df  call    __security_check_cookie
0x1800073e4  mov     rbx, [rsp+88h+arg_18]
0x1800073ec  add     rsp, 50h
0x1800073f0  pop     r15
0x1800073f2  pop     r14
0x1800073f4  pop     r13
0x1800073f6  pop     r12
0x1800073f8  pop     rdi
0x1800073f9  pop     rsi
0x1800073fa  pop     rbp
0x1800073fb  retn
0x1800073fc  mov     edx, 3; MaxCount
0x180007401  call    cs:__imp_wcsnlen
0x180007407  cmp     rax, 3
0x18000740b  jb      short loc_1800073D5
0x18000740d  cmp     word ptr [rbx+2], 3Ah ; ':'
0x180007412  jnz     short loc_1800073D5
0x180007414  cmp     [rbx+4], si
0x180007418  jnz     short loc_1800073D5
0x18000741a  movzx   ecx, word ptr [rbx]
0x18000741d  lea     eax, [rcx-61h]
0x180007420  cmp     ax, 19h
0x180007424  jbe     short loc_18000742F
0x180007426  lea     eax, [rcx-41h]
0x180007429  cmp     ax, 19h
0x18000742d  ja      short loc_1800073D5
0x18000742f  mov     rax, 5C003F003F005Ch
0x180007439  mov     qword ptr [rsp+88h+SourceString], rax
0x18000743e  mov     rax, 5C003A0043h
0x180007448  mov     qword ptr [rsp+88h+RootPathName], rax
0x18000744d  mov     [rsp+88h+RootPathName], cx
0x180007452  lea     rcx, [rsp+88h+RootPathName]; lpRootPathName
0x180007457  call    cs:__imp_GetDriveTypeW
0x18000745d  cmp     eax, r13d
0x180007460  jnz     loc_1800073D5
0x180007466  lea     rdx, [rsp+88h+Block]; unsigned __int16 **
0x18000746b  mov     [rsp+88h+Block], r15
0x180007470  lea     rcx, [rsp+88h+SourceString]; SourceString
0x180007475  call    ?GetRemotePath@@YAJPEBGPEAPEAG@Z; GetRemotePath(ushort const *,ushort * *)
0x18000747a  test    eax, eax
0x18000747c  js      loc_1800073D5
0x180007482  mov     rsi, [rsp+88h+Block]
0x180007487  inc     rbp
0x18000748a  cmp     [rsi+rbp*2], r15w
0x18000748f  jnz     short loc_180007487
0x180007491  or      rax, 0FFFFFFFFFFFFFFFFh
0x180007495  inc     rax
0x180007498  cmp     [rbx+rax*2], r15w
0x18000749d  jnz     short loc_180007495
0x18000749f  add     eax, ebp
0x1800074a1  mov     edx, 2; Size
0x1800074a6  movsxd  r15, eax
0x1800074a9  mov     rcx, r15; Count
0x1800074ac  call    cs:__imp_calloc
0x1800074b2  mov     r12, rax
0x1800074b5  test    rax, rax
0x1800074b8  jnz     short loc_1800074C8
0x1800074ba  mov     rcx, rsi; Block
0x1800074bd  call    cs:__imp_free
0x1800074c3  jmp     loc_1800073D5
0x1800074c8  mov     eax, 6
0x1800074cd  lea     r8, aSS; "%s%s"
0x1800074d4  mov     r9, rsi
0x1800074d7  mov     rdx, r15; unsigned __int64
0x1800074da  lea     ecx, [rax+56h]
0x1800074dd  cmp     [rsi+rbp*2-2], cx
0x1800074e2  mov     rcx, r12; unsigned __int16 *
0x1800074e5  cmovnz  rax, r13
0x1800074e9  add     rax, rbx
0x1800074ec  mov     [rsp+88h+var_68], rax
0x1800074f1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800074f6  mov     rcx, rsi; Block
0x1800074f9  call    cs:__imp_free
0x1800074ff  xor     r15d, r15d
0x180007502  or      rbp, 0FFFFFFFFFFFFFFFFh
0x180007506  lea     esi, [r15+5Ch]
0x18000750a  lea     rdx, [rsp+88h+Block]; struct _DFS_INFO_3 **
0x18000750f  mov     [rsp+88h+Block], r15
0x180007514  mov     rcx, r12; unsigned __int16 *
0x180007517  mov     r13b, r15b
0x18000751a  call    ?ResolveDfsPath@@YAJPEBGPEAPEAU_DFS_INFO_3@@@Z; ResolveDfsPath(ushort const *,_DFS_INFO_3 * *)
0x18000751f  test    eax, eax
0x180007521  js      loc_1800077F5
0x180007527  mov     rbx, [rsp+88h+Block]
0x18000752c  test    rbx, rbx
0x18000752f  jz      loc_1800077F5
0x180007535  mov     rax, [rbx]
0x180007538  cmp     si, [rax]
0x18000753b  jnz     short loc_180007548
0x18000753d  cmp     si, [rax+2]
0x180007541  mov     esi, 1
0x180007546  jnz     short loc_18000754B
0x180007548  mov     esi, r15d
0x18000754b  mov     rcx, rbp
0x18000754e  inc     rcx
0x180007551  cmp     [rax+rcx*2], r15w
0x180007556  jnz     short loc_18000754E
0x180007558  inc     ecx
0x18000755a  mov     eax, 2
0x18000755f  add     ecx, esi
0x180007561  movsxd  rbp, ecx
0x180007564  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000756b  mul     rbp
0x18000756e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180007575  cmovb   rax, rcx
0x180007579  mov     rcx, rax; unsigned __int64
0x18000757c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180007581  mov     [r14], rax
0x180007584  test    rax, rax
0x180007587  jz      loc_1800077EC
0x18000758d  mov     r9, [rbx]
0x180007590  lea     rcx, aS_0; "%s"
0x180007597  test    esi, esi
0x180007599  lea     r8, aS_1; "\\%s"
0x1800075a0  mov     rdx, rbp; unsigned __int64
0x1800075a3  cmovz   r8, rcx; unsigned __int16 *
0x1800075a7  mov     rcx, rax; unsigned __int16 *
0x1800075aa  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800075af  mov     ecx, [rbx+14h]
0x1800075b2  mov     eax, 8
0x1800075b7  inc     ecx
0x1800075b9  mul     rcx
0x1800075bc  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800075c3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800075ca  cmovb   rax, rcx
0x1800075ce  mov     rcx, rax; unsigned __int64
0x1800075d1  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800075d6  mov     [rdi], rax
0x1800075d9  mov     rcx, rax
0x1800075dc  test    rax, rax
0x1800075df  jnz     short loc_1800075F2
0x1800075e1  mov     rcx, [r14]
0x1800075e4  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800075ea  mov     [r14], r15
0x1800075ed  jmp     loc_1800077EC
0x1800075f2  mov     eax, [rbx+14h]
0x1800075f5  mov     esi, r15d
0x1800075f8  mov     [rcx+rax*8], r15
0x1800075fc  cmp     [rbx+14h], r15d
0x180007600  jbe     loc_1800076B4
0x180007606  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000760d  mov     ecx, 20h ; ' '; unsigned __int64
0x180007612  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180007617  mov     qword ptr [rsp+88h+SourceString], rax
0x18000761c  mov     rdx, rax
0x18000761f  test    rax, rax
0x180007622  jz      short loc_180007638
0x180007624  mov     [rax], r15
0x180007627  mov     [rax+8], r15
0x18000762b  mov     [rax+10h], r15
0x18000762f  mov     dword ptr [rax+18h], 3
0x180007636  jmp     short loc_18000763B
0x180007638  mov     rdx, r15
0x18000763b  mov     rax, [rdi]
0x18000763e  mov     ecx, esi
0x180007640  mov     [rax+rcx*8], rdx
0x180007644  mov     rax, [rdi]
0x180007647  cmp     [rax+rcx*8], r15
0x18000764b  jz      short loc_180007656
0x18000764d  inc     esi
0x18000764f  cmp     esi, [rbx+14h]
0x180007652  jb      short loc_180007606
0x180007654  jmp     short loc_1800076B4
0x180007656  lea     ebp, [rsi-1]
0x180007659  test    ebp, ebp
0x18000765b  js      short loc_18000769C
0x18000765d  mov     rax, [rdi]
0x180007660  mov     r15, [rax+rbp*8]
0x180007664  test    r15, r15
0x180007667  jz      short loc_18000768F
0x180007669  mov     rcx, [r15+10h]; bstrString
0x18000766d  call    cs:__imp_SysFreeString
0x180007673  mov     rcx, [r15+8]; bstrString
0x180007677  call    cs:__imp_SysFreeString
0x18000767d  mov     rcx, [r15]; bstrString
0x180007680  call    cs:__imp_SysFreeString
0x180007686  mov     rcx, r15
0x180007689  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000768f  sub     ebp, 1
0x180007692  jns     short loc_18000765D
0x180007694  mov     rbx, [rsp+88h+Block]
0x180007699  xor     r15d, r15d
0x18000769c  mov     rcx, [rdi]
0x18000769f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800076a5  mov     [rdi], r15
0x1800076a8  mov     rcx, [r14]
0x1800076ab  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800076b1  mov     [r14], r15
0x1800076b4  cmp     esi, [rbx+14h]
0x1800076b7  jb      loc_1800077EC
0x1800076bd  mov     ebp, r15d
0x1800076c0  cmp     [rbx+14h], r15d
0x1800076c4  jbe     loc_1800077E9
0x1800076ca  mov     rax, [rbx+18h]
0x1800076ce  mov     esi, ebp
0x1800076d0  lea     r13, [rsi+rsi*2]
0x1800076d4  mov     r15, [rax+r13*8+8]
0x1800076d9  mov     rax, [rdi]
0x1800076dc  mov     r14, [rax+rsi*8]
0x1800076e0  mov     rcx, [r14+8]; bstrString
0x1800076e4  cmp     r15, rcx
0x1800076e7  jz      short loc_180007712
0x1800076e9  call    cs:__imp_SysFreeString
0x1800076ef  xor     eax, eax
0x1800076f1  test    r15, r15
0x1800076f4  jz      short loc_18000770E
0x1800076f6  mov     rcx, r15; psz
0x1800076f9  call    cs:__imp_SysAllocString
0x1800076ff  mov     [r14+8], rax
0x180007703  test    rax, rax
0x180007706  jz      loc_180007806
0x18000770c  jmp     short loc_180007712
0x18000770e  mov     [r14+8], rax
0x180007712  mov     rax, [rbx+18h]
0x180007716  mov     r15, [rax+r13*8+10h]
0x18000771b  mov     rax, [rdi]
0x18000771e  mov     r14, [rax+rsi*8]
0x180007722  mov     rcx, [r14+10h]; bstrString
0x180007726  cmp     r15, rcx
0x180007729  jz      short loc_180007757
0x18000772b  call    cs:__imp_SysFreeString
0x180007731  test    r15, r15
0x180007734  jz      short loc_180007751
0x180007736  mov     rcx, r15; psz
0x180007739  call    cs:__imp_SysAllocString
0x18000773f  xor     r15d, r15d
0x180007742  mov     [r14+10h], rax
0x180007746  test    rax, rax
0x180007749  jz      loc_180007806
0x18000774f  jmp     short loc_18000775A
0x180007751  mov     [r14+10h], r15
0x180007755  jmp     short loc_18000775A
0x180007757  xor     r15d, r15d
0x18000775a  mov     rax, [rdi]
0x18000775d  mov     r14, [rax+rsi*8]
0x180007761  lea     rax, psz; "\\\\"
0x180007768  cmp     rax, [r14]
0x18000776b  jz      short loc_18000778B
0x18000776d  mov     rcx, [r14]; bstrString
0x180007770  call    cs:__imp_SysFreeString
0x180007776  lea     rcx, psz; "\\\\"
0x18000777d  call    cs:__imp_SysAllocString
0x180007783  mov     [r14], rax
0x180007786  test    rax, rax
0x180007789  jz      short loc_180007806
0x18000778b  mov     rdx, [rbx+18h]
0x18000778f  mov     rcx, [rdi]
0x180007792  mov     rdx, [rdx+r13*8+8]
0x180007797  mov     rcx, [rcx+rsi*8]
0x18000779b  call    ??YCComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator+=(ushort const *)
0x1800077a0  mov     rcx, [rdi]
0x1800077a3  lea     rdx, asc_18000F990; "\\"
0x1800077aa  mov     rcx, [rcx+rsi*8]
0x1800077ae  call    ??YCComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator+=(ushort const *)
0x1800077b3  mov     rdx, [rbx+18h]
0x1800077b7  mov     rcx, [rdi]
0x1800077ba  mov     rdx, [rdx+r13*8+10h]
0x1800077bf  mov     rcx, [rcx+rsi*8]
0x1800077c3  call    ??YCComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator+=(ushort const *)
0x1800077c8  mov     rax, [rbx+18h]
0x1800077cc  test    byte ptr [rax+r13*8], 4
0x1800077d1  jz      short loc_1800077DE
  ... truncated ...
```
