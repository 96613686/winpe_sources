# CPubFolderEnum::_CreateItemIDFromPublishedApp(IPublishedApp *,uint,_ITEMID_CHILD * *)

- ea: `0x18004430c`
- end: `0x1800444d0`
- name: `?_CreateItemIDFromPublishedApp@CPubFolderEnum@@AEAAJPEAUIPublishedApp@@IPEAPEAU_ITEMID_CHILD@@@Z`
- size: `452`
- prototype: `__int64 __fastcall(CPubFolderEnum *__hidden this, struct IPublishedApp *, unsigned int, struct _ITEMID_CHILD **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800438b0`

## callees

- `0x180011e78`
- `0x1800440dc`
- `0x18004430c`
- `0x180044cfc`
- `0x1800582a2`
- `0x1800582e0`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044489`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800444ab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180044489`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800444ab`

## pseudocode

```c
__int64 __fastcall CPubFolderEnum::_CreateItemIDFromPublishedApp(
        CPubFolderEnum *this,
        struct IPublishedApp *a2,
        unsigned int a3,
        struct _ITEMID_CHILD **a4)
{
  struct IPublishedAppVtbl *lpVtbl; // rax
  struct IPublishedAppVtbl *v9; // rax
  struct IPublishedAppVtbl *v10; // rax
  struct IPublishedAppVtbl *v11; // rax
  __int64 v12; // rdx
  unsigned int v13; // ebx
  __int64 v15; // [rsp+40h] [rbp-C0h] BYREF
  _tagSlowAppInfo v16; // [rsp+48h] [rbp-B8h] BYREF
  struct _AppInfoData v17; // [rsp+70h] [rbp-90h] BYREF
  _PubAppInfo v18; // [rsp+110h] [rbp+10h] BYREF
  struct _MANAGEDAPPLICATION v19; // [rsp+160h] [rbp+60h] BYREF

  memset_0(&v17.pszDisplayName, 0, 0x90u);
  lpVtbl = a2->lpVtbl;
  v17.cbSize = 152;
  v17.dwMask = 131215;
  ((void (__fastcall *)(struct IPublishedApp *, struct _AppInfoData *))lpVtbl->GetAppInfo)(a2, &v17);
  v9 = a2->lpVtbl;
  memset(&v16, 0, sizeof(v16));
  if ( ((unsigned int (__fastcall *)(struct IPublishedApp *, _tagSlowAppInfo *))v9->GetCachedSlowAppInfo)(a2, &v16) )
    ((void (__fastcall *)(struct IPublishedApp *, _tagSlowAppInfo *))a2->lpVtbl->GetSlowAppInfo)(a2, &v16);
  memset_0(&v19, 0, sizeof(v19));
  v10 = a2->lpVtbl;
  v15 = 0;
  if ( ((__int64 (__fastcall *)(struct IPublishedApp *, GUID *, __int64 *))v10->QueryInterface)(
         a2,
         &GUID_9054fbc1_1b03_4a3d_bec7_c3f0f0de50a8,
         &v15) >= 0 )
  {
    (*(void (__fastcall **)(__int64, struct _MANAGEDAPPLICATION *))(*(_QWORD *)v15 + 96LL))(v15, &v19);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  }
  v18.cbSize = 80;
  memset_0(&v18.dwMask, 0, 0x4Cu);
  v11 = a2->lpVtbl;
  v18.dwMask = 1;
  ((void (__fastcall *)(struct IPublishedApp *, _PubAppInfo *))v11->GetPublishedAppInfo)(a2, &v18);
  ((void (__fastcall *)(struct IPublishedApp *))a2->lpVtbl->IsInstalled)(a2);
  v13 = CPubFolderEnum::_CreateItemIDFromAppInfo(this, v12, &v17, &v16, &v19, &v18, a3, a4);
  ClearAppInfoData(&v17);
  CoTaskMemFree(v16.pszImage);
  v16.pszImage = 0;
  ClearManagedApplication(&v19);
  if ( (v18.dwMask & 1) != 0 )
    CoTaskMemFree(v18.pszSource);
  return v13;
}

```

## disassembly

```asm
0x18004430c  push    rbp
0x18004430e  push    rbx
0x18004430f  push    rsi
0x180044310  push    rdi
0x180044311  push    r14
0x180044313  lea     rbp, [rsp-0F0h]
0x18004431b  sub     rsp, 1F0h
0x180044322  mov     rax, cs:__security_cookie
0x180044329  xor     rax, rsp
0x18004432c  mov     [rbp+110h+var_30], rax
0x180044333  mov     edi, r8d
0x180044336  mov     rbx, rdx
0x180044339  mov     rsi, rcx
0x18004433c  xor     edx, edx; Val
0x18004433e  mov     r8d, 90h; Size
0x180044344  lea     rcx, [rsp+210h+var_1A0.pszDisplayName]; void *
0x180044349  mov     r14, r9
0x18004434c  call    memset_0
0x180044351  mov     rax, [rbx]
0x180044354  lea     rdx, [rsp+210h+var_1A0]
0x180044359  mov     rcx, rbx
0x18004435c  mov     [rsp+210h+var_1A0.cbSize], 98h
0x180044364  mov     [rsp+210h+var_1A0.dwMask], 2008Fh
0x18004436c  mov     rax, [rax+18h]
0x180044370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044375  mov     rax, [rbx]
0x180044378  lea     rdx, [rsp+210h+var_1C8]
0x18004437d  xorps   xmm0, xmm0
0x180044380  mov     rcx, rbx
0x180044383  movups  xmmword ptr [rsp+210h+var_1C8.ullSize], xmm0
0x180044388  mov     rax, [rax+30h]
0x18004438c  movups  xmmword ptr [rsp+210h+var_1C8.iTimesUsed], xmm0
0x180044391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044396  test    eax, eax
0x180044398  jz      short loc_1800443AE
0x18004439a  mov     rax, [rbx]
0x18004439d  lea     rdx, [rsp+210h+var_1C8]
0x1800443a2  mov     rcx, rbx
0x1800443a5  mov     rax, [rax+28h]
0x1800443a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800443ae  xor     edx, edx; Val
0x1800443b0  lea     rcx, [rbp+110h+var_B0]; void *
0x1800443b4  mov     r8d, 80h; Size
0x1800443ba  call    memset_0
0x1800443bf  mov     rax, [rbx]
0x1800443c2  lea     r8, [rsp+210h+var_1D0]
0x1800443c7  lea     rdx, _GUID_9054fbc1_1b03_4a3d_bec7_c3f0f0de50a8
0x1800443ce  mov     [rsp+210h+var_1D0], 0
0x1800443d7  mov     rcx, rbx
0x1800443da  mov     rax, [rax]
0x1800443dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800443e2  test    eax, eax
0x1800443e4  js      short loc_18004440C
0x1800443e6  mov     rcx, [rsp+210h+var_1D0]
0x1800443eb  lea     rdx, [rbp+110h+var_B0]
0x1800443ef  mov     rax, [rcx]
0x1800443f2  mov     rax, [rax+60h]
0x1800443f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800443fb  mov     rcx, [rsp+210h+var_1D0]
0x180044400  mov     rax, [rcx]
0x180044403  mov     rax, [rax+10h]
0x180044407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004440c  xor     edx, edx; Val
0x18004440e  mov     [rbp+110h+var_100.cbSize], 50h ; 'P'
0x180044415  lea     rcx, [rbp+110h+var_100.dwMask]; void *
0x180044419  lea     r8d, [rdx+4Ch]; Size
0x18004441d  call    memset_0
0x180044422  mov     rax, [rbx]
0x180044425  lea     rdx, [rbp+110h+var_100]
0x180044429  mov     rcx, rbx
0x18004442c  mov     [rbp+110h+var_100.dwMask], 1
0x180044433  mov     rax, [rax+48h]
0x180044437  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004443c  mov     rax, [rbx]
0x18004443f  mov     rcx, rbx
0x180044442  mov     rax, [rax+38h]
0x180044446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004444b  mov     [rsp+210h+var_1D8], r14; struct _ITEMID_CHILD **
0x180044450  lea     rax, [rbp+110h+var_100]
0x180044454  mov     [rsp+210h+var_1E0], edi; unsigned int
0x180044458  lea     r9, [rsp+210h+var_1C8]; struct _tagSlowAppInfo *
0x18004445d  mov     [rsp+210h+var_1E8], rax; struct _PubAppInfo *
0x180044462  lea     r8, [rsp+210h+var_1A0]; struct _AppInfoData *
0x180044467  lea     rax, [rbp+110h+var_B0]
0x18004446b  mov     rcx, rsi; this
0x18004446e  mov     [rsp+210h+var_1F0], rax; struct _MANAGEDAPPLICATION *
0x180044473  call    ?_CreateItemIDFromAppInfo@CPubFolderEnum@@AEAAJHPEAU_AppInfoData@@PEAU_tagSlowAppInfo@@PEAU_MANAGEDAPPLICATION@@PEAU_PubAppInfo@@IPEAPEAU_ITEMID_CHILD@@@Z; CPubFolderEnum::_CreateItemIDFromAppInfo(int,_AppInfoData *,_tagSlowAppInfo *,_MANAGEDAPPLICATION *,_PubAppInfo *,uint,_ITEMID_CHILD * *)
0x180044478  lea     rcx, [rsp+210h+var_1A0]; struct _AppInfoData *
0x18004447d  mov     ebx, eax
0x18004447f  call    ?ClearAppInfoData@@YAXPEAU_AppInfoData@@@Z; ClearAppInfoData(_AppInfoData *)
0x180044484  mov     rcx, [rsp+210h+var_1C8.pszImage]; pv
0x180044489  call    cs:__imp_CoTaskMemFree
0x18004448f  lea     rcx, [rbp+110h+var_B0]; struct _MANAGEDAPPLICATION *
0x180044493  mov     [rsp+210h+var_1C8.pszImage], 0
0x18004449c  call    ?ClearManagedApplication@@YAXPEAU_MANAGEDAPPLICATION@@@Z; ClearManagedApplication(_MANAGEDAPPLICATION *)
0x1800444a1  test    byte ptr [rbp+110h+var_100.dwMask], 1
0x1800444a5  jz      short loc_1800444B1
0x1800444a7  mov     rcx, [rbp+110h+var_100.pszSource]; pv
0x1800444ab  call    cs:__imp_CoTaskMemFree
0x1800444b1  mov     eax, ebx
0x1800444b3  mov     rcx, [rbp+110h+var_30]
0x1800444ba  xor     rcx, rsp; StackCookie
0x1800444bd  call    __security_check_cookie
0x1800444c2  add     rsp, 1F0h
0x1800444c9  pop     r14
0x1800444cb  pop     rdi
0x1800444cc  pop     rsi
0x1800444cd  pop     rbx
0x1800444ce  pop     rbp
0x1800444cf  retn
```
