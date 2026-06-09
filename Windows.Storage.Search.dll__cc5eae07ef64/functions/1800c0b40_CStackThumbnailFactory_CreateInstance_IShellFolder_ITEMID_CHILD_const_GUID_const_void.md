# CStackThumbnailFactory::CreateInstance(IShellFolder *,_ITEMID_CHILD const *,_GUID const &,void * *)

- ea: `0x1800c0b40`
- end: `0x1800c0d7b`
- name: `?CreateInstance@CStackThumbnailFactory@@QEAAJPEAUIShellFolder@@PEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z`
- size: `571`
- prototype: `__int64 __fastcall(CStackThumbnailFactory *__hidden this, struct IShellFolder *, const struct _ITEMID_CHILD *, IID *riid, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800171dc`

## callees

- `0x180015588`
- `0x1800306e0`
- `0x1800573fc`
- `0x180071df0`
- `0x1800c0b40`
- `0x1800c0ed0`
- `0x1800c0f80`
- `0x1800c1aa4`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!SHCreateItemWithParent` at `0x1800c0ba3`
- `Windows.Storage!SHCreateItemWithParent` at `0x1800c0ba3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x1800c0d43`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!QISearch` at `0x1800c0d43`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x1800c0bd7`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x1800c0bd7`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHGetCurColorRes` at `0x1800c0b5c`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_SHGetCurColorRes` at `0x1800c0b5c`

## pseudocode

```c
__int64 __fastcall CStackThumbnailFactory::CreateInstance(
        CStackThumbnailFactory *this,
        struct IShellFolder *a2,
        const struct _ITEMID_CHILD *a3,
        IID *riid,
        void **a5)
{
  HRESULT v9; // ebx
  __int64 v10; // rdi
  char *v11; // rax
  _QWORD *v12; // rdi
  _QWORD *v13; // rcx
  int v14; // r9d
  int v15; // r10d
  void (__fastcall ***v16)(_QWORD, GUID *); // r11
  void *ppv; // [rsp+30h] [rbp-18h] BYREF
  struct IShellItem *ppvItem[2]; // [rsp+38h] [rbp-10h] BYREF

  if ( (unsigned int)SHGetCurColorRes() <= 0x10 )
  {
    return (unsigned int)-2144927486;
  }
  else
  {
    v9 = CStackThumbnailFactory::_Initialize(this, a2, a3);
    if ( v9 >= 0 )
    {
      ppvItem[0] = 0;
      v9 = SHCreateItemWithParent(
             0,
             a2,
             (LPCITEMIDLIST)a3,
             &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
             (void **)ppvItem);
      if ( v9 >= 0 )
      {
        ppv = 0;
        v9 = SHCoCreateInstance(0, &CLSID_LayerComposer, 0, &GUID_55262bff_41b7_45fd_8673_e5d67db871fa, &ppv);
        if ( v9 >= 0 )
        {
          (*(void (__fastcall **)(void *, __int64, CStackThumbnailFactory *, bool))(*(_QWORD *)ppv + 24LL))(
            ppv,
            3,
            this,
            (*((_DWORD *)this + 7) & 4) == 0);
          (*(void (__fastcall **)(void *, _QWORD, _QWORD))(*(_QWORD *)ppv + 32LL))(
            ppv,
            *((unsigned int *)this + 3),
            *((_DWORD *)this + 7) & 8);
          (*(void (__fastcall **)(void *, _QWORD, _QWORD))(*(_QWORD *)ppv + 56LL))(
            ppv,
            *((unsigned int *)this + 4),
            *((unsigned int *)this + 5));
          v10 = 0;
          do
          {
            (*(void (__fastcall **)(void *, _QWORD, char *, __int64))(*(_QWORD *)ppv + 48LL))(
              ppv,
              (unsigned int)v10,
              (char *)this + 64 * v10 + 8 * (unsigned int)v10 + 248,
              9);
            v10 = (unsigned int)(v10 + 1);
          }
          while ( (unsigned int)v10 < 3 );
          v11 = (char *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
          v12 = v11;
          if ( v11 )
          {
            CObjectWithSite::CObjectWithSite((CObjectWithSite *)(v11 + 24));
            v12[1] = &CStackThumbnailer::`vftable'{for `IThumbnailSettings'};
            *v12 = &CStackThumbnailer::`vftable'{for `IExtractImage'};
            v12[2] = &CStackThumbnailer::`vftable'{for `IInitializeWithItem'};
            *v13 = &CStackThumbnailer::`vftable'{for `CObjectWithSite'};
            v12[5] = 0;
            *((_BYTE *)v12 + 48) = 0;
            *((_DWORD *)v12 + 15) = 1;
            v12[8] = 0;
            v12[9] = 0;
            *((_DWORD *)v12 + 20) = v14;
            *((_DWORD *)v12 + 21) = 0;
            *((_DWORD *)v12 + 22) = v15;
            *(_QWORD *)((char *)v12 + 52) = 0;
            (**v16)(v16, &GUID_55262bff_41b7_45fd_8673_e5d67db871fa);
            v9 = CStackThumbnailer::Initialize((CStackThumbnailer *)(v12 + 2), ppvItem[0], 0);
            if ( v9 >= 0 )
              v9 = QISearch(v12, &stru_1800F3040, riid, a5);
            CStackThumbnailer::Release((CStackThumbnailer *)v12);
          }
        }
        ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(&ppv);
      }
      ATL::CComPtr<IResultShape>::~CComPtr<IResultShape>(ppvItem);
    }
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800c0b40  push    rbp
0x1800c0b42  push    rbx
0x1800c0b43  push    rsi
0x1800c0b44  push    rdi
0x1800c0b45  push    r14
0x1800c0b47  push    r15
0x1800c0b49  mov     rbp, rsp
0x1800c0b4c  sub     rsp, 48h
0x1800c0b50  mov     r15, r9
0x1800c0b53  mov     rdi, r8
0x1800c0b56  mov     r14, rdx
0x1800c0b59  mov     rsi, rcx
0x1800c0b5c  call    cs:__imp_SHGetCurColorRes
0x1800c0b62  cmp     eax, 10h
0x1800c0b65  jbe     loc_1800C0D67
0x1800c0b6b  mov     r8, rdi; struct _ITEMID_CHILD *
0x1800c0b6e  mov     rdx, r14; struct IShellFolder *
0x1800c0b71  mov     rcx, rsi; this
0x1800c0b74  call    ?_Initialize@CStackThumbnailFactory@@AEAAJPEAUIShellFolder@@PEFBU_ITEMID_CHILD@@@Z; CStackThumbnailFactory::_Initialize(IShellFolder *,_ITEMID_CHILD const *)
0x1800c0b79  mov     ebx, eax
0x1800c0b7b  test    eax, eax
0x1800c0b7d  js      loc_1800C0D6C
0x1800c0b83  lea     rax, [rbp+var_10]
0x1800c0b87  mov     [rbp+var_10], 0
0x1800c0b8f  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800c0b96  mov     [rsp+48h+ppvItem], rax; ppvItem
0x1800c0b9b  mov     r8, rdi; pidl
0x1800c0b9e  mov     rdx, r14; psfParent
0x1800c0ba1  xor     ecx, ecx; pidlParent
0x1800c0ba3  call    cs:__imp_SHCreateItemWithParent
0x1800c0ba9  mov     ebx, eax
0x1800c0bab  test    eax, eax
0x1800c0bad  js      loc_1800C0D5C
0x1800c0bb3  lea     rax, [rbp+ppv]
0x1800c0bb7  mov     [rbp+ppv], 0
0x1800c0bbf  lea     r9, _GUID_55262bff_41b7_45fd_8673_e5d67db871fa; riid
0x1800c0bc6  mov     [rsp+48h+ppvItem], rax; ppv
0x1800c0bcb  xor     r8d, r8d; pUnkOuter
0x1800c0bce  lea     rdx, CLSID_LayerComposer; pclsid
0x1800c0bd5  xor     ecx, ecx; pszCLSID
0x1800c0bd7  call    cs:__imp_SHCoCreateInstance
0x1800c0bdd  mov     ebx, eax
0x1800c0bdf  test    eax, eax
0x1800c0be1  js      loc_1800C0D53
0x1800c0be7  mov     rcx, [rbp+ppv]
0x1800c0beb  mov     r8, rsi
0x1800c0bee  mov     r9d, [rsi+1Ch]
0x1800c0bf2  mov     edx, 3
0x1800c0bf7  shr     r9d, 2
0x1800c0bfb  not     r9d
0x1800c0bfe  mov     rax, [rcx]
0x1800c0c01  and     r9d, 1
0x1800c0c05  mov     rax, [rax+18h]
0x1800c0c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0c0e  mov     rcx, [rbp+ppv]
0x1800c0c12  mov     r8d, [rsi+1Ch]
0x1800c0c16  mov     edx, [rsi+0Ch]
0x1800c0c19  and     r8d, 8
0x1800c0c1d  mov     rax, [rcx]
0x1800c0c20  mov     rax, [rax+20h]
0x1800c0c24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0c29  mov     rcx, [rbp+ppv]
0x1800c0c2d  mov     r8d, [rsi+14h]
0x1800c0c31  mov     edx, [rsi+10h]
0x1800c0c34  mov     rax, [rcx]
0x1800c0c37  mov     rax, [rax+38h]
0x1800c0c3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0c40  xor     edi, edi
0x1800c0c42  mov     rcx, [rbp+ppv]
0x1800c0c46  mov     edx, edi
0x1800c0c48  mov     r8d, edi
0x1800c0c4b  add     r8, 1Fh
0x1800c0c4f  mov     r9, [rcx]
0x1800c0c52  lea     r8, [r8+rdi*8]
0x1800c0c56  lea     r8, [rsi+r8*8]
0x1800c0c5a  mov     rax, [r9+30h]
0x1800c0c5e  mov     r9d, 9
0x1800c0c64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0c69  inc     edi
0x1800c0c6b  cmp     edi, 3
0x1800c0c6e  jb      short loc_1800C0C42
0x1800c0c70  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800c0c77  mov     ecx, 60h ; '`'; unsigned __int64
0x1800c0c7c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800c0c81  mov     rdi, rax
0x1800c0c84  test    rax, rax
0x1800c0c87  jz      loc_1800C0D53
0x1800c0c8d  mov     r10d, [rsi+1Ch]
0x1800c0c91  lea     rcx, [rax+18h]; this
0x1800c0c95  mov     r9d, [rsi+18h]
0x1800c0c99  mov     r11, [rbp+ppv]
0x1800c0c9d  call    ??0CObjectWithSite@@QEAA@XZ; CObjectWithSite::CObjectWithSite(void)
0x1800c0ca2  lea     rax, ??_7CStackThumbnailer@@6BIThumbnailSettings@@@; const CStackThumbnailer::`vftable'{for `IThumbnailSettings'}
0x1800c0ca9  mov     [rdi+8], rax
0x1800c0cad  lea     rdx, ??_7CStackThumbnailer@@6BIExtractImage@@@; const CStackThumbnailer::`vftable'{for `IExtractImage'}
0x1800c0cb4  mov     [rdi], rdx
0x1800c0cb7  lea     rax, ??_7CStackThumbnailer@@6BIInitializeWithItem@@@; const CStackThumbnailer::`vftable'{for `IInitializeWithItem'}
0x1800c0cbe  mov     [rdi+10h], rax
0x1800c0cc2  lea     r8, [rdi+48h]
0x1800c0cc6  lea     rax, ??_7CStackThumbnailer@@6BCObjectWithSite@@@; const CStackThumbnailer::`vftable'{for `CObjectWithSite'}
0x1800c0ccd  mov     [rcx], rax
0x1800c0cd0  lea     rdx, _GUID_55262bff_41b7_45fd_8673_e5d67db871fa
0x1800c0cd7  mov     qword ptr [rdi+28h], 0
0x1800c0cdf  xor     eax, eax
0x1800c0ce1  mov     byte ptr [rdi+30h], 0
0x1800c0ce5  mov     rcx, r11
0x1800c0ce8  mov     dword ptr [rdi+3Ch], 1
0x1800c0cef  mov     qword ptr [rdi+40h], 0
0x1800c0cf7  mov     qword ptr [r8], 0
0x1800c0cfe  mov     [rdi+50h], r9d
0x1800c0d02  mov     dword ptr [rdi+54h], 0
0x1800c0d09  mov     [rdi+58h], r10d
0x1800c0d0d  mov     [rdi+34h], rax
0x1800c0d11  mov     rax, [r11]
0x1800c0d14  mov     rax, [rax]
0x1800c0d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c0d1c  mov     rdx, [rbp+var_10]; struct IShellItem *
0x1800c0d20  lea     rcx, [rdi+10h]; this
0x1800c0d24  xor     r8d, r8d; unsigned int
0x1800c0d27  call    ?Initialize@CStackThumbnailer@@UEAAJPEAUIShellItem@@K@Z; CStackThumbnailer::Initialize(IShellItem *,ulong)
0x1800c0d2c  mov     ebx, eax
0x1800c0d2e  test    eax, eax
0x1800c0d30  js      short loc_1800C0D4B
0x1800c0d32  mov     r9, [rbp+arg_20]; ppv
0x1800c0d36  lea     rdx, stru_1800F3040; pqit
0x1800c0d3d  mov     r8, r15; riid
0x1800c0d40  mov     rcx, rdi; that
0x1800c0d43  call    cs:__imp_QISearch
0x1800c0d49  mov     ebx, eax
0x1800c0d4b  mov     rcx, rdi; this
0x1800c0d4e  call    ?Release@CStackThumbnailer@@UEAAKXZ; CStackThumbnailer::Release(void)
0x1800c0d53  lea     rcx, [rbp+ppv]
0x1800c0d57  call    ??1?$CComQIPtr@UIShellItemImageFactoryPriv@@$1?_GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc@@3U__s_GUID@@B@ATL@@QEAA@XZ; ATL::CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>::~CComQIPtr<IShellItemImageFactoryPriv,&__s_GUID const _GUID_8a322201_0a87_46c1_9c77_7620e0cc5bbc>(void)
0x1800c0d5c  lea     rcx, [rbp+var_10]
0x1800c0d60  call    ??1?$CComPtr@UIResultShape@@@ATL@@QEAA@XZ; ATL::CComPtr<IResultShape>::~CComPtr<IResultShape>(void)
0x1800c0d65  jmp     short loc_1800C0D6C
0x1800c0d67  mov     ebx, 80270102h
0x1800c0d6c  mov     eax, ebx
0x1800c0d6e  add     rsp, 48h
0x1800c0d72  pop     r15
0x1800c0d74  pop     r14
0x1800c0d76  pop     rdi
0x1800c0d77  pop     rsi
0x1800c0d78  pop     rbx
0x1800c0d79  pop     rbp
0x1800c0d7a  retn
```
