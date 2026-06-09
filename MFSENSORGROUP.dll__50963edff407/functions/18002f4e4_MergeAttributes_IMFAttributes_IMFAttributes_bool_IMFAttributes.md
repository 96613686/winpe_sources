# MergeAttributes(IMFAttributes *,IMFAttributes *,bool,IMFAttributes * *)

- ea: `0x18002f4e4`
- end: `0x18002f7aa`
- name: `?MergeAttributes@@YAJPEAUIMFAttributes@@0_NPEAPEAU1@@Z`
- size: `710`
- prototype: `__int64 __fastcall(struct IMFAttributes *, struct IMFAttributes *, bool, struct IMFAttributes **)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180006dd4`
- `0x1800185e4`
- `0x180043a80`

## callees

- `0x180005fa0`
- `0x18002f3cc`
- `0x18002f4e4`
- `0x180044f30`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002f71f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002f76a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002f71f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002f76a`
- `MFPlat!MFCreateAttributes` at `0x18002f60a`
- `MFPlat!MFCreateAttributes` at `0x18002f60a`

## pseudocode

```c
__int64 __fastcall MergeAttributes(
        struct IMFAttributes *a1,
        struct IMFAttributes *a2,
        char a3,
        struct IMFAttributes **a4)
{
  HRESULT v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  UINT32 v11; // edx
  unsigned int i; // edi
  struct IMFAttributesVtbl *lpVtbl; // rax
  HRESULT (__stdcall *GetItemByIndex)(IMFAttributes *, UINT32, GUID *, PROPVARIANT *); // rax
  struct IMFAttributesVtbl *v15; // rax
  IMFAttributes *ppMFAttributes; // [rsp+30h] [rbp-50h] BYREF
  unsigned int v18; // [rsp+38h] [rbp-48h] BYREF
  int v19; // [rsp+3Ch] [rbp-44h] BYREF
  int v20; // [rsp+40h] [rbp-40h] BYREF
  PROPVARIANT pvar[2]; // [rsp+48h] [rbp-38h] BYREF
  __int64 v22; // [rsp+58h] [rbp-28h]
  GUID v23; // [rsp+60h] [rbp-20h] BYREF

  v18 = 0;
  v19 = 0;
  ppMFAttributes = 0;
  v22 = 0;
  *(_OWORD *)pvar = 0;
  if ( !a1 )
  {
    v8 = -2147024809;
    v9 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_38;
    v10 = 79;
    goto LABEL_4;
  }
  if ( a2 )
  {
    v8 = ((__int64 (__fastcall *)(struct IMFAttributes *, unsigned int *))a1->lpVtbl->GetCount)(a1, &v18);
    v9 = v8;
    if ( v8 >= 0 )
    {
      v8 = ((__int64 (__fastcall *)(struct IMFAttributes *, int *))a2->lpVtbl->GetCount)(a2, &v19);
      v9 = v8;
      if ( v8 >= 0 )
      {
        if ( a4 )
        {
          v11 = v18 + v19;
          *a4 = 0;
          v8 = MFCreateAttributes(&ppMFAttributes, v11);
          v9 = v8;
          if ( v8 < 0 )
          {
            if ( g_wppLevels )
            {
              v10 = 83;
              goto LABEL_4;
            }
            goto LABEL_38;
          }
          v8 = ((__int64 (__fastcall *)(struct IMFAttributes *, IMFAttributes *))a2->lpVtbl->CopyAllItems)(
                 a2,
                 ppMFAttributes);
          v9 = v8;
          if ( v8 < 0 )
          {
            if ( g_wppLevels )
            {
              v10 = 84;
              goto LABEL_4;
            }
            goto LABEL_38;
          }
        }
        else
        {
          ComSmartPtr<IMFCameraProfileValidation>::operator=(&ppMFAttributes, (__int64)a2);
        }
        for ( i = 0; ; ++i )
        {
          if ( i >= v18 )
          {
            if ( a4 )
            {
              *a4 = ppMFAttributes;
              ppMFAttributes = 0;
            }
            goto LABEL_38;
          }
          lpVtbl = a1->lpVtbl;
          v20 = 0;
          GetItemByIndex = lpVtbl->GetItemByIndex;
          v23 = GUID_00000000_0000_0000_0000_000000000000;
          v8 = ((__int64 (__fastcall *)(struct IMFAttributes *, _QWORD, GUID *, PROPVARIANT *))GetItemByIndex)(
                 a1,
                 i,
                 &v23,
                 pvar);
          v9 = v8;
          if ( v8 < 0 )
            break;
          v15 = ppMFAttributes->lpVtbl;
          if ( a3 )
          {
            v8 = ((__int64 (__fastcall *)(IMFAttributes *, GUID *, PROPVARIANT *))v15->SetItem)(
                   ppMFAttributes,
                   &v23,
                   pvar);
            v9 = v8;
            if ( v8 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_38;
              v10 = 86;
              goto LABEL_4;
            }
          }
          else if ( ((int (__fastcall *)(IMFAttributes *, GUID *, int *))v15->GetItemType)(ppMFAttributes, &v23, &v20) < 0 )
          {
            v8 = ((__int64 (__fastcall *)(IMFAttributes *, GUID *, PROPVARIANT *))ppMFAttributes->lpVtbl->SetItem)(
                   ppMFAttributes,
                   &v23,
                   pvar);
            v9 = v8;
            if ( v8 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_38;
              v10 = 87;
              goto LABEL_4;
            }
          }
          PropVariantClear(pvar);
        }
        if ( !g_wppLevels )
          goto LABEL_38;
        v10 = 85;
        goto LABEL_4;
      }
      if ( g_wppLevels )
      {
        v10 = 82;
        goto LABEL_4;
      }
    }
    else if ( g_wppLevels )
    {
      v10 = 81;
      goto LABEL_4;
    }
  }
  else
  {
    v8 = -2147024809;
    v9 = -2147024809;
    if ( g_wppLevels )
    {
      v10 = 80;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v10, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, v8);
    }
  }
LABEL_38:
  PropVariantClear(pvar);
  if ( ppMFAttributes )
    ((void (__fastcall *)(IMFAttributes *))ppMFAttributes->lpVtbl->Release)(ppMFAttributes);
  return v9;
}

```

## disassembly

```asm
0x18002f4e4  mov     [rsp-28h+arg_10], rbx
0x18002f4e9  push    rbp
0x18002f4ea  push    rsi
0x18002f4eb  push    rdi
0x18002f4ec  push    r14
0x18002f4ee  push    r15
0x18002f4f0  mov     rbp, rsp
0x18002f4f3  sub     rsp, 80h
0x18002f4fa  mov     rax, cs:__security_cookie
0x18002f501  xor     rax, rsp
0x18002f504  mov     [rbp+var_10], rax
0x18002f508  xor     eax, eax
0x18002f50a  mov     [rbp+var_48], 0
0x18002f511  mov     [rbp+var_44], 0
0x18002f518  xorps   xmm0, xmm0
0x18002f51b  mov     [rbp+ppMFAttributes], 0
0x18002f523  mov     rsi, r9
0x18002f526  mov     [rbp+var_28], rax
0x18002f52a  mov     r15b, r8b
0x18002f52d  mov     rdi, rdx
0x18002f530  mov     r14, rcx
0x18002f533  movups  xmmword ptr [rbp+pvar], xmm0
0x18002f537  test    rcx, rcx
0x18002f53a  jnz     short loc_18002F576
0x18002f53c  mov     eax, 80070057h
0x18002f541  mov     ebx, eax
0x18002f543  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002f54a  jb      loc_18002F766
0x18002f550  lea     edx, [rcx+4Fh]
0x18002f553  mov     rcx, cs:WPP_GLOBAL_Control
0x18002f55a  lea     r8, WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids
0x18002f561  xor     r9d, r9d
0x18002f564  mov     [rsp+80h+var_60], eax
0x18002f568  mov     rcx, [rcx+10h]
0x18002f56c  call    WPP_SF_qD
0x18002f571  jmp     loc_18002F766
0x18002f576  test    rdi, rdi
0x18002f579  jnz     short loc_18002F594
0x18002f57b  mov     eax, 80070057h
0x18002f580  mov     ebx, eax
0x18002f582  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002f589  jb      loc_18002F766
0x18002f58f  lea     edx, [rdi+50h]
0x18002f592  jmp     short loc_18002F553
0x18002f594  mov     rax, [rcx]
0x18002f597  lea     rdx, [rbp+var_48]
0x18002f59b  mov     rax, [rax+0F0h]
0x18002f5a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5a7  mov     ebx, eax
0x18002f5a9  test    eax, eax
0x18002f5ab  jns     short loc_18002F5C1
0x18002f5ad  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002f5b4  jb      loc_18002F766
0x18002f5ba  mov     edx, 51h ; 'Q'
0x18002f5bf  jmp     short loc_18002F553
0x18002f5c1  mov     rax, [rdi]
0x18002f5c4  lea     rdx, [rbp+var_44]
0x18002f5c8  mov     rcx, rdi
0x18002f5cb  mov     rax, [rax+0F0h]
0x18002f5d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5d7  mov     ebx, eax
0x18002f5d9  test    eax, eax
0x18002f5db  jns     short loc_18002F5F4
0x18002f5dd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002f5e4  jb      loc_18002F766
0x18002f5ea  mov     edx, 52h ; 'R'
0x18002f5ef  jmp     loc_18002F553
0x18002f5f4  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x18002f5f8  test    rsi, rsi
0x18002f5fb  jz      short loc_18002F660
0x18002f5fd  mov     edx, [rbp+var_44]
0x18002f600  add     edx, [rbp+var_48]; cInitialSize
0x18002f603  mov     qword ptr [rsi], 0
0x18002f60a  call    cs:__imp_MFCreateAttributes
0x18002f610  mov     ebx, eax
0x18002f612  test    eax, eax
0x18002f614  jns     short loc_18002F62D
0x18002f616  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002f61d  jb      loc_18002F766
0x18002f623  mov     edx, 53h ; 'S'
0x18002f628  jmp     loc_18002F553
0x18002f62d  mov     rax, [rdi]
0x18002f630  mov     rcx, rdi
0x18002f633  mov     rdx, [rbp+ppMFAttributes]
0x18002f637  mov     rax, [rax+100h]
0x18002f63e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f643  mov     ebx, eax
0x18002f645  test    eax, eax
0x18002f647  jns     short loc_18002F668
0x18002f649  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002f650  jb      loc_18002F766
0x18002f656  mov     edx, 54h ; 'T'
0x18002f65b  jmp     loc_18002F553
0x18002f660  mov     rdx, rdi
0x18002f663  call    ??4?$ComSmartPtr@UIMFCameraProfileValidation@@@@QEAAPEAUIMFCameraProfileValidation@@PEAU1@@Z; ComSmartPtr<IMFCameraProfileValidation>::operator=(IMFCameraProfileValidation *)
0x18002f668  xor     edi, edi
0x18002f66a  cmp     edi, [rbp+var_48]
0x18002f66d  jnb     loc_18002F752
0x18002f673  mov     rax, [r14]
0x18002f676  lea     r9, [rbp+pvar]
0x18002f67a  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18002f681  lea     r8, [rbp+var_20]
0x18002f685  mov     [rbp+var_40], 0
0x18002f68c  mov     edx, edi
0x18002f68e  mov     rcx, r14
0x18002f691  mov     rax, [rax+0F8h]
0x18002f698  movdqu  [rbp+var_20], xmm0
0x18002f69d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6a2  mov     ebx, eax
0x18002f6a4  test    eax, eax
0x18002f6a6  js      loc_18002F73F
0x18002f6ac  mov     rcx, [rbp+ppMFAttributes]
0x18002f6b0  lea     rdx, [rbp+var_20]
0x18002f6b4  mov     rax, [rcx]
0x18002f6b7  test    r15b, r15b
0x18002f6ba  jz      short loc_18002F6E9
0x18002f6bc  mov     rax, [rax+90h]
0x18002f6c3  lea     r8, [rbp+pvar]
0x18002f6c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6cc  mov     ebx, eax
0x18002f6ce  test    eax, eax
0x18002f6d0  jns     short loc_18002F71B
0x18002f6d2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002f6d9  jb      loc_18002F766
0x18002f6df  mov     edx, 56h ; 'V'
0x18002f6e4  jmp     loc_18002F553
0x18002f6e9  mov     rax, [rax+20h]
0x18002f6ed  lea     r8, [rbp+var_40]
0x18002f6f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f6f6  test    eax, eax
0x18002f6f8  jns     short loc_18002F71B
0x18002f6fa  mov     rcx, [rbp+ppMFAttributes]
0x18002f6fe  lea     r8, [rbp+pvar]
0x18002f702  lea     rdx, [rbp+var_20]
0x18002f706  mov     rax, [rcx]
0x18002f709  mov     rax, [rax+90h]
0x18002f710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f715  mov     ebx, eax
0x18002f717  test    eax, eax
0x18002f719  js      short loc_18002F72C
0x18002f71b  lea     rcx, [rbp+pvar]; pvar
0x18002f71f  call    cs:__imp_PropVariantClear
0x18002f725  inc     edi
0x18002f727  jmp     loc_18002F66A
0x18002f72c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002f733  jb      short loc_18002F766
0x18002f735  mov     edx, 57h ; 'W'
0x18002f73a  jmp     loc_18002F553
0x18002f73f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002f746  jb      short loc_18002F766
0x18002f748  mov     edx, 55h ; 'U'
0x18002f74d  jmp     loc_18002F553
0x18002f752  test    rsi, rsi
0x18002f755  jz      short loc_18002F766
0x18002f757  mov     rax, [rbp+ppMFAttributes]
0x18002f75b  mov     [rsi], rax
0x18002f75e  mov     [rbp+ppMFAttributes], 0
0x18002f766  lea     rcx, [rbp+pvar]; pvar
0x18002f76a  call    cs:__imp_PropVariantClear
0x18002f770  mov     rcx, [rbp+ppMFAttributes]
0x18002f774  test    rcx, rcx
0x18002f777  jz      short loc_18002F785
0x18002f779  mov     rax, [rcx]
0x18002f77c  mov     rax, [rax+10h]
0x18002f780  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f785  mov     eax, ebx
0x18002f787  mov     rcx, [rbp+var_10]
0x18002f78b  xor     rcx, rsp; StackCookie
0x18002f78e  call    __security_check_cookie
0x18002f793  mov     rbx, [rsp+80h+arg_10]
0x18002f79b  add     rsp, 80h
0x18002f7a2  pop     r15
0x18002f7a4  pop     r14
0x18002f7a6  pop     rdi
0x18002f7a7  pop     rsi
0x18002f7a8  pop     rbp
0x18002f7a9  retn
```
