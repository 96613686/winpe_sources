# OrderItem_LoadFromStream(_DPASTREAMINFO *,IStream *,void *)

- ea: `0x180015be0`
- end: `0x180015de6`
- name: `?OrderItem_LoadFromStream@@YAJPEAU_DPASTREAMINFO@@PEAUIStream@@PEAX@Z`
- size: `518`
- prototype: `HRESULT __stdcall(DPASTREAMINFO *pinfo, struct IStream *pstream, void *pvInstData)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800037ac`
- `0x1800157e8`
- `0x180015b0c`
- `0x180015b50`
- `0x180015be0`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x180015d27`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x180015d27`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x180015d34`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrDupW` at `0x180015d34`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x180015c12`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x180015c60`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x180015c12`
- `api-ms-win-downlevel-shlwapi-l2-1-0!IStream_Read` at `0x180015c60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015c38`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015c38`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180015cf6`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180015d8e`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180015dbb`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180015cf6`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180015d8e`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180015dbb`
- `api-ms-win-shell-namespace-l1-1-0!ILGetSize` at `0x180015d58`
- `api-ms-win-shell-namespace-l1-1-0!ILGetSize` at `0x180015d58`
- `api-ms-win-shell-namespace-l1-1-0!ILCloneFirst` at `0x180015d7d`
- `api-ms-win-shell-namespace-l1-1-0!ILCloneFirst` at `0x180015d7d`
- `api-ms-win-shell-namespace-l1-1-0!ILClone` at `0x180015d70`
- `api-ms-win-shell-namespace-l1-1-0!ILClone` at `0x180015d70`

## pseudocode

```c
__int64 __fastcall OrderItem_LoadFromStream(
        DPASTREAMINFO *pinfo,
        struct IStream *pstream,
        struct IShellFolder *pvInstData)
{
  HRESULT v6; // ebx
  ULONG v7; // ebp
  SIZE_T v8; // r14
  ITEMIDLIST *v9; // rax
  ITEMIDLIST *v10; // rsi
  __int64 cb; // rcx
  struct __MIDL___MIDL_itf_inetpriv_shared_0000_0014_0001 *v12; // rax
  struct __MIDL___MIDL_itf_inetpriv_shared_0000_0014_0001 *v13; // rdi
  _DWORD *v14; // rbx
  const struct _ITEMIDLIST *v15; // rdx
  __int64 v16; // rsi
  struct _ITEMIDLIST *v17; // rax
  const ITEMIDLIST *v18; // rbx
  __int64 v19; // rax
  LPITEMIDLIST v20; // rbx
  __int64 pv; // [rsp+70h] [rbp+18h] BYREF
  struct _ITEMIDLIST *v23; // [rsp+78h] [rbp+20h] BYREF

  pv = 0;
  v6 = IStream_Read(pstream, &pv, 8u);
  if ( v6 >= 0 )
  {
    if ( (unsigned int)pv <= 8 )
      return (unsigned int)-2147467259;
    v7 = pv - 8;
    v8 = (unsigned int)(pv - 8);
    v9 = (ITEMIDLIST *)CoTaskMemAlloc(v8);
    v10 = v9;
    if ( !v9 )
      return (unsigned int)-2147024882;
    memset_0(v9, 0, (unsigned int)v8);
    v6 = IStream_Read(pstream, v10, v7);
    if ( v6 < 0 )
      goto LABEL_28;
    if ( v7 >= 3 )
    {
      cb = v10->mkid.cb;
      if ( cb + 2 <= v8 && !*(USHORT *)((char *)&v10->mkid.cb + cb) )
      {
        v12 = OrderItem_Create(v10, SHIDWORD(pv));
        v13 = v12;
        if ( v12 )
        {
          pinfo->pvItem = v12;
          v14 = (_DWORD *)((char *)v12 + 16);
          v15 = *(const struct _ITEMIDLIST **)v12;
          v16 = (**(unsigned __int16 **)v12 + 3) & 0xFFFFFFFE;
          if ( v8 >= v16 + 4 )
            *v14 = *(_DWORD *)((char *)&v15->mkid.cb + v16);
          if ( (*v14 & 0x4000) != 0 )
          {
            if ( pvInstData )
            {
              v23 = 0;
              if ( IdlRealFromIdlSimple(pvInstData, v15, &v23) >= 0 )
              {
                ILFree(*(LPITEMIDLIST *)v13);
                v17 = v23;
                *v14 &= ~0x4000u;
                *(_QWORD *)v13 = v17;
              }
            }
          }
          if ( v8 >= v16 + 10 )
          {
            v18 = (const ITEMIDLIST *)(v16 + *(_QWORD *)v13 + 8LL);
            if ( v18 && *(_DWORD *)(*(_QWORD *)v13 + v16 + 4) )
            {
              if ( !PathIsRelativeW(&v18->mkid.cb) )
              {
                *((_QWORD *)v13 + 3) = StrDupW(&v18->mkid.cb);
                v19 = -1;
                do
                  ++v19;
                while ( *(&v18->mkid.cb + v19) );
                *((_DWORD *)v13 + 8) = *(_DWORD *)&v18->mkid.abID[2 * v19];
              }
            }
            else if ( ILGetSize(v18) <= (unsigned __int64)(v7 - (unsigned int)v16) - 8 )
            {
              *((_QWORD *)v13 + 5) = ILClone(v18);
            }
          }
          v20 = ILCloneFirst(*(LPCITEMIDLIST *)v13);
          if ( v20 )
          {
            ILFree(*(LPITEMIDLIST *)v13);
            *(_QWORD *)v13 = v20;
            return 0;
          }
          v10 = 0;
          v6 = -2147024882;
          OrderItem_Free(v13, 1);
        }
        else
        {
          v6 = -2147024882;
        }
LABEL_28:
        ILFree(v10);
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180015be0  mov     [rsp+arg_0], rbx
0x180015be5  push    rbp
0x180015be6  push    rsi
0x180015be7  push    rdi
0x180015be8  push    r12
0x180015bea  push    r13
0x180015bec  push    r14
0x180015bee  push    r15
0x180015bf0  sub     rsp, 20h
0x180015bf4  mov     rdi, rdx
0x180015bf7  xor     r12d, r12d
0x180015bfa  mov     r15, r8
0x180015bfd  mov     [rsp+58h+pv], r12
0x180015c02  mov     r13, rcx
0x180015c05  lea     rdx, [rsp+58h+pv]; pv
0x180015c0a  mov     rcx, rdi; pstm
0x180015c0d  lea     r8d, [r12+8]; cb
0x180015c12  call    cs:__imp_IStream_Read
0x180015c18  mov     ebx, eax
0x180015c1a  test    eax, eax
0x180015c1c  js      loc_180015DCF
0x180015c22  mov     rax, [rsp+58h+pv]
0x180015c27  cmp     eax, 8
0x180015c2a  jbe     loc_180015DCA
0x180015c30  lea     ebp, [rax-8]
0x180015c33  mov     ecx, ebp; cb
0x180015c35  mov     r14d, ebp
0x180015c38  call    cs:__imp_CoTaskMemAlloc
0x180015c3e  mov     rsi, rax
0x180015c41  test    rax, rax
0x180015c44  jz      loc_180015DC3
0x180015c4a  mov     r8d, r14d; Size
0x180015c4d  xor     edx, edx; Val
0x180015c4f  mov     rcx, rax; void *
0x180015c52  call    memset_0
0x180015c57  mov     r8d, ebp; cb
0x180015c5a  mov     rdx, rsi; pv
0x180015c5d  mov     rcx, rdi; pstm
0x180015c60  call    cs:__imp_IStream_Read
0x180015c66  mov     ebx, eax
0x180015c68  test    eax, eax
0x180015c6a  js      loc_180015DB8
0x180015c70  cmp     ebp, 3
0x180015c73  jb      loc_180015DCF
0x180015c79  movzx   ecx, word ptr [rsi]
0x180015c7c  lea     rax, [rcx+2]
0x180015c80  cmp     rax, r14
0x180015c83  ja      loc_180015DCF
0x180015c89  cmp     [rcx+rsi], r12w
0x180015c8e  jnz     loc_180015DCF
0x180015c94  mov     edx, dword ptr [rsp+58h+pv+4]; int
0x180015c98  mov     rcx, rsi; struct _ITEMIDLIST *
0x180015c9b  call    ?OrderItem_Create@@YAPEAU__MIDL___MIDL_itf_inetpriv_shared_0000_0014_0001@@PEFAU_ITEMIDLIST@@H@Z; OrderItem_Create(_ITEMIDLIST *,int)
0x180015ca0  mov     rdi, rax
0x180015ca3  test    rax, rax
0x180015ca6  jz      loc_180015DB3
0x180015cac  mov     [r13+8], rax
0x180015cb0  lea     rbx, [rax+10h]
0x180015cb4  mov     rdx, [rax]; struct _ITEMIDLIST *
0x180015cb7  movzx   ecx, word ptr [rdx]
0x180015cba  add     ecx, 3
0x180015cbd  and     ecx, 0FFFFFFFEh
0x180015cc0  mov     esi, ecx
0x180015cc2  add     rcx, 4
0x180015cc6  cmp     r14, rcx
0x180015cc9  jb      short loc_180015CD0
0x180015ccb  mov     eax, [rsi+rdx]
0x180015cce  mov     [rbx], eax
0x180015cd0  test    dword ptr [rbx], 4000h
0x180015cd6  jz      short loc_180015D08
0x180015cd8  test    r15, r15
0x180015cdb  jz      short loc_180015D08
0x180015cdd  lea     r8, [rsp+58h+arg_18]; struct _ITEMIDLIST **
0x180015ce2  mov     [rsp+58h+arg_18], r12
0x180015ce7  mov     rcx, r15; struct IShellFolder *
0x180015cea  call    ?IdlRealFromIdlSimple@@YAJPEAUIShellFolder@@PEFBU_ITEMIDLIST@@PEAPEFAU2@@Z; IdlRealFromIdlSimple(IShellFolder *,_ITEMIDLIST const *,_ITEMIDLIST * *)
0x180015cef  test    eax, eax
0x180015cf1  js      short loc_180015D08
0x180015cf3  mov     rcx, [rdi]; pidl
0x180015cf6  call    cs:__imp_ILFree
0x180015cfc  mov     rax, [rsp+58h+arg_18]
0x180015d01  btr     dword ptr [rbx], 0Eh
0x180015d05  mov     [rdi], rax
0x180015d08  lea     rax, [rsi+0Ah]
0x180015d0c  cmp     r14, rax
0x180015d0f  jb      short loc_180015D7A
0x180015d11  mov     rax, [rdi]
0x180015d14  lea     rbx, [rax+8]
0x180015d18  add     rbx, rsi
0x180015d1b  jz      short loc_180015D55
0x180015d1d  cmp     [rax+rsi+4], r12d
0x180015d22  jz      short loc_180015D55
0x180015d24  mov     rcx, rbx; pszPath
0x180015d27  call    cs:__imp_PathIsRelativeW
0x180015d2d  test    eax, eax
0x180015d2f  jnz     short loc_180015D7A
0x180015d31  mov     rcx, rbx; pszSrch
0x180015d34  call    cs:__imp_StrDupW
0x180015d3a  mov     [rdi+18h], rax
0x180015d3e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180015d42  inc     rax
0x180015d45  cmp     [rbx+rax*2], r12w
0x180015d4a  jnz     short loc_180015D42
0x180015d4c  mov     eax, [rbx+rax*2+2]
0x180015d50  mov     [rdi+20h], eax
0x180015d53  jmp     short loc_180015D7A
0x180015d55  mov     rcx, rbx; pidl
0x180015d58  call    cs:__imp_ILGetSize
0x180015d5e  mov     edx, eax
0x180015d60  sub     ebp, esi
0x180015d62  mov     eax, ebp
0x180015d64  sub     rax, 8
0x180015d68  cmp     rdx, rax
0x180015d6b  ja      short loc_180015D7A
0x180015d6d  mov     rcx, rbx; pidl
0x180015d70  call    cs:__imp_ILClone
0x180015d76  mov     [rdi+28h], rax
0x180015d7a  mov     rcx, [rdi]; pidl
0x180015d7d  call    cs:__imp_ILCloneFirst
0x180015d83  mov     rbx, rax
0x180015d86  test    rax, rax
0x180015d89  jz      short loc_180015D9C
0x180015d8b  mov     rcx, [rdi]; pidl
0x180015d8e  call    cs:__imp_ILFree
0x180015d94  mov     [rdi], rbx
0x180015d97  mov     ebx, r12d
0x180015d9a  jmp     short loc_180015DCF
0x180015d9c  mov     edx, 1; int
0x180015da1  mov     rcx, rdi; struct __MIDL___MIDL_itf_inetpriv_shared_0000_0014_0001 *
0x180015da4  mov     rsi, r12
0x180015da7  mov     ebx, 8007000Eh
0x180015dac  call    ?OrderItem_Free@@YAXPEAU__MIDL___MIDL_itf_inetpriv_shared_0000_0014_0001@@H@Z; OrderItem_Free(__MIDL___MIDL_itf_inetpriv_shared_0000_0014_0001 *,int)
0x180015db1  jmp     short loc_180015DB8
0x180015db3  mov     ebx, 8007000Eh
0x180015db8  mov     rcx, rsi; pidl
0x180015dbb  call    cs:__imp_ILFree
0x180015dc1  jmp     short loc_180015DCF
0x180015dc3  mov     ebx, 8007000Eh
0x180015dc8  jmp     short loc_180015DCF
0x180015dca  mov     ebx, 80004005h
0x180015dcf  mov     eax, ebx
0x180015dd1  mov     rbx, [rsp+58h+arg_0]
0x180015dd6  add     rsp, 20h
0x180015dda  pop     r15
0x180015ddc  pop     r14
0x180015dde  pop     r13
0x180015de0  pop     r12
0x180015de2  pop     rdi
0x180015de3  pop     rsi
0x180015de4  pop     rbp
0x180015de5  retn
```
