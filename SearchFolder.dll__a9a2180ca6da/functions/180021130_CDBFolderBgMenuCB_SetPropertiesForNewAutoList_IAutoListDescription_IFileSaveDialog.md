# CDBFolderBgMenuCB::_SetPropertiesForNewAutoList(IAutoListDescription *,IFileSaveDialog *)

- ea: `0x180021130`
- end: `0x180021366`
- name: `?_SetPropertiesForNewAutoList@CDBFolderBgMenuCB@@AEAAJPEAUIAutoListDescription@@PEAUIFileSaveDialog@@@Z`
- size: `566`
- prototype: `__int64 __fastcall(CDBFolderBgMenuCB *__hidden this, struct IAutoListDescription *, struct IFileSaveDialog *)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e834`

## callees

- `0x180006900`
- `0x180021130`
- `0x180041618`
- `0x180051010`

## import_xrefs

- `SHELL32!__imp_SHGetUserDisplayName` at `0x1800211ae`
- `SHELL32!__imp_SHGetUserDisplayName` at `0x1800211ae`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800212ae`
- `SHLWAPI!__imp_StrCmpICW` at `0x1800212ae`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800211fc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800211fc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021300`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021300`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x1800211c8`
- `PROPSYS!InitPropVariantFromStringAsVector` at `0x1800211c8`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18002117d`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18002117d`

## pseudocode

```c
__int64 __fastcall CDBFolderBgMenuCB::_SetPropertiesForNewAutoList(
        CDBFolderBgMenuCB *this,
        struct IAutoListDescription *a2,
        struct IFileSaveDialog *a3)
{
  HRESULT inited; // ebx
  __int64 v6; // rax
  int v7; // esi
  unsigned int i; // edi
  LPCWSTR pszStr2; // [rsp+30h] [rbp-D0h] BYREF
  void *ppv; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v12; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v13; // [rsp+48h] [rbp-B8h] BYREF
  PROPVARIANT ppropvar[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v15; // [rsp+60h] [rbp-A0h]
  WCHAR psz[264]; // [rsp+70h] [rbp-90h] BYREF

  ppv = 0;
  inited = PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv);
  if ( inited >= 0 )
  {
    LODWORD(pszStr2) = 260;
    v15 = 0;
    *(_OWORD *)ppropvar = 0;
    inited = SHGetUserDisplayName(psz, &pszStr2);
    if ( inited >= 0 )
    {
      inited = InitPropVariantFromStringAsVector(psz, ppropvar);
      if ( inited >= 0 )
      {
        inited = (*(__int64 (__fastcall **)(void *, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)ppv + 48LL))(
                   ppv,
                   &PKEY_Author,
                   ppropvar);
        PropVariantClear(ppropvar);
        if ( inited >= 0 )
        {
          v6 = *(_QWORD *)a2;
          v13 = 0;
          inited = (*(__int64 (__fastcall **)(struct IAutoListDescription *, GUID *, __int64 *))(v6 + 112))(
                     a2,
                     &GUID_d18f09e2_81c2_4217_a295_43b66fa4e495,
                     &v13);
          if ( inited >= 0 )
          {
            v12 = 0;
            inited = (*(__int64 (__fastcall **)(__int64, _QWORD, GUID *, __int64 *))(*(_QWORD *)v13 + 32LL))(
                       v13,
                       0,
                       &GUID_1d17905d_aeb6_4ac9_8cd5_2c103f186212,
                       &v12);
            if ( inited >= 0 )
            {
              pszStr2 = 0;
              inited = (*(__int64 (__fastcall **)(__int64, LPCWSTR *))(*(_QWORD *)v12 + 24LL))(v12, &pszStr2);
              if ( inited >= 0 )
              {
                v7 = 0;
                for ( i = 0; i < 4; ++i )
                {
                  if ( v7 )
                    break;
                  if ( StrCmpICW(off_180054860[2 * i], pszStr2) )
                  {
                    v7 = 0;
                  }
                  else
                  {
                    v7 = 1;
                    inited = IPropertyStore_SetString(ppv, &PKEY_Kind, off_180054860[2 * i + 1]);
                  }
                }
                if ( inited >= 0 )
                  inited = ((__int64 (__fastcall *)(struct IFileSaveDialog *, void *))a3->lpVtbl->SetProperties)(
                             a3,
                             ppv);
                CoTaskMemFree((LPVOID)pszStr2);
              }
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
          }
        }
      }
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x180021130  mov     [rsp-8+arg_0], rbx
0x180021135  mov     [rsp-8+arg_18], rsi
0x18002113a  push    rbp
0x18002113b  push    rdi
0x18002113c  push    r13
0x18002113e  push    r14
0x180021140  push    r15
0x180021142  lea     rbp, [rsp-190h]
0x18002114a  sub     rsp, 290h
0x180021151  mov     rax, cs:__security_cookie
0x180021158  xor     rax, rsp
0x18002115b  mov     [rbp+1B0h+var_30], rax
0x180021162  mov     rdi, rdx
0x180021165  mov     [rsp+2B0h+ppv], 0
0x18002116e  lea     rdx, [rsp+2B0h+ppv]; ppv
0x180021173  mov     r15, r8
0x180021176  lea     rcx, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99; riid
0x18002117d  call    cs:__imp_PSCreateMemoryPropertyStore
0x180021183  mov     ebx, eax
0x180021185  test    eax, eax
0x180021187  js      loc_180021339
0x18002118d  xorps   xmm0, xmm0
0x180021190  mov     dword ptr [rsp+2B0h+pszStr2], 104h
0x180021198  xor     eax, eax
0x18002119a  lea     rdx, [rsp+2B0h+pszStr2]
0x18002119f  lea     rcx, [rsp+2B0h+psz]
0x1800211a4  mov     [rsp+2B0h+var_250], rax
0x1800211a9  movups  xmmword ptr [rsp+2B0h+ppropvar], xmm0
0x1800211ae  call    cs:__imp_SHGetUserDisplayName
0x1800211b4  mov     ebx, eax
0x1800211b6  test    eax, eax
0x1800211b8  js      loc_180021328
0x1800211be  lea     rdx, [rsp+2B0h+ppropvar]; ppropvar
0x1800211c3  lea     rcx, [rsp+2B0h+psz]; psz
0x1800211c8  call    cs:__imp_InitPropVariantFromStringAsVector
0x1800211ce  mov     ebx, eax
0x1800211d0  test    eax, eax
0x1800211d2  js      loc_180021328
0x1800211d8  mov     rcx, [rsp+2B0h+ppv]
0x1800211dd  lea     r8, [rsp+2B0h+ppropvar]
0x1800211e2  lea     rdx, PKEY_Author
0x1800211e9  mov     rax, [rcx]
0x1800211ec  mov     rax, [rax+30h]
0x1800211f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800211f5  lea     rcx, [rsp+2B0h+ppropvar]; pvar
0x1800211fa  mov     ebx, eax
0x1800211fc  call    cs:__imp_PropVariantClear
0x180021202  test    ebx, ebx
0x180021204  js      loc_180021328
0x18002120a  mov     rax, [rdi]
0x18002120d  lea     r8, [rsp+2B0h+var_268]
0x180021212  lea     rdx, _GUID_d18f09e2_81c2_4217_a295_43b66fa4e495
0x180021219  mov     [rsp+2B0h+var_268], 0
0x180021222  mov     rcx, rdi
0x180021225  mov     rax, [rax+70h]
0x180021229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002122e  mov     ebx, eax
0x180021230  test    eax, eax
0x180021232  js      loc_180021328
0x180021238  mov     rcx, [rsp+2B0h+var_268]
0x18002123d  lea     r9, [rsp+2B0h+var_270]
0x180021242  mov     [rsp+2B0h+var_270], 0
0x18002124b  lea     r8, _GUID_1d17905d_aeb6_4ac9_8cd5_2c103f186212
0x180021252  xor     edx, edx
0x180021254  mov     rax, [rcx]
0x180021257  mov     rax, [rax+20h]
0x18002125b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021260  mov     ebx, eax
0x180021262  test    eax, eax
0x180021264  js      loc_180021317
0x18002126a  mov     rcx, [rsp+2B0h+var_270]
0x18002126f  lea     rdx, [rsp+2B0h+pszStr2]
0x180021274  mov     [rsp+2B0h+pszStr2], 0
0x18002127d  mov     rax, [rcx]
0x180021280  mov     rax, [rax+18h]
0x180021284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021289  mov     ebx, eax
0x18002128b  test    eax, eax
0x18002128d  js      short loc_180021306
0x18002128f  xor     esi, esi
0x180021291  lea     r13, off_180054860; "document"
0x180021298  xor     edi, edi
0x18002129a  test    esi, esi
0x18002129c  jnz     short loc_1800212DE
0x18002129e  mov     rdx, [rsp+2B0h+pszStr2]; pszStr2
0x1800212a3  mov     r14d, edi
0x1800212a6  add     r14, r14
0x1800212a9  mov     rcx, [r13+r14*8+0]; pszStr1
0x1800212ae  call    cs:__imp_StrCmpICW
0x1800212b4  test    eax, eax
0x1800212b6  jnz     short loc_1800212D5
0x1800212b8  mov     r8, [r13+r14*8+8]
0x1800212bd  lea     rdx, PKEY_Kind
0x1800212c4  mov     rcx, [rsp+2B0h+ppv]
0x1800212c9  lea     esi, [rax+1]
0x1800212cc  call    IPropertyStore_SetString
0x1800212d1  mov     ebx, eax
0x1800212d3  jmp     short loc_1800212D7
0x1800212d5  xor     esi, esi
0x1800212d7  inc     edi
0x1800212d9  cmp     edi, 4
0x1800212dc  jb      short loc_18002129A
0x1800212de  test    ebx, ebx
0x1800212e0  js      short loc_1800212FB
0x1800212e2  mov     rax, [r15]
0x1800212e5  mov     rcx, r15
0x1800212e8  mov     rdx, [rsp+2B0h+ppv]
0x1800212ed  mov     rax, [rax+0E0h]
0x1800212f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212f9  mov     ebx, eax
0x1800212fb  mov     rcx, [rsp+2B0h+pszStr2]; pv
0x180021300  call    cs:__imp_CoTaskMemFree
0x180021306  mov     rcx, [rsp+2B0h+var_270]
0x18002130b  mov     rax, [rcx]
0x18002130e  mov     rax, [rax+10h]
0x180021312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021317  mov     rcx, [rsp+2B0h+var_268]
0x18002131c  mov     rax, [rcx]
0x18002131f  mov     rax, [rax+10h]
0x180021323  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021328  mov     rcx, [rsp+2B0h+ppv]
0x18002132d  mov     rax, [rcx]
0x180021330  mov     rax, [rax+10h]
0x180021334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021339  mov     eax, ebx
0x18002133b  mov     rcx, [rbp+1B0h+var_30]
0x180021342  xor     rcx, rsp; StackCookie
0x180021345  call    __security_check_cookie
0x18002134a  lea     r11, [rsp+2B0h+var_20]
0x180021352  mov     rbx, [r11+30h]
0x180021356  mov     rsi, [r11+48h]
0x18002135a  mov     rsp, r11
0x18002135d  pop     r15
0x18002135f  pop     r14
0x180021361  pop     r13
0x180021363  pop     rdi
0x180021364  pop     rbp
0x180021365  retn
```
