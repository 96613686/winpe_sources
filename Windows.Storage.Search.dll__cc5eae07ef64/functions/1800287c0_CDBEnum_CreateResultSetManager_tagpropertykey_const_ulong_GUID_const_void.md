# CDBEnum::_CreateResultSetManager(_tagpropertykey const &,ulong,_GUID const &,void * *)

- ea: `0x1800287c0`
- end: `0x180028a5f`
- name: `?_CreateResultSetManager@CDBEnum@@AEAAJAEBU_tagpropertykey@@KAEBU_GUID@@PEAPEAX@Z`
- size: `671`
- prototype: `__int64 __usercall@<rax>(CDBEnum *__hidden this@<rcx>, const struct _tagpropertykey *@<rdx>, unsigned int@<r8d>, const struct _GUID *@<r9>, void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180028590`

## callees

- `0x1800287c0`
- `0x180028b44`
- `0x180028be4`
- `0x180028d30`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!ILFree` at `0x18002895c`
- `Windows.Storage!ILFree` at `0x18002895c`
- `Windows.Storage!SHGetIDListFromObject` at `0x1800287fb`
- `Windows.Storage!SHGetIDListFromObject` at `0x1800287fb`
- `Windows.Storage!SHCreateItemFromIDList` at `0x180028823`
- `Windows.Storage!SHCreateItemFromIDList` at `0x180028823`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x1800289ca`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x1800289ca`

## pseudocode

```c
__int64 __fastcall CDBEnum::_CreateResultSetManager(
        IUnknown **this,
        const struct _tagpropertykey *a2,
        unsigned int a3,
        struct _GUID *a4,
        void **a5)
{
  HRESULT v8; // eax
  HRESULT v9; // eax
  int v10; // eax
  const struct _GUID *v11; // r8
  int ResultShape; // eax
  const struct _GUID *v13; // r8
  void *v14; // rdi
  bool v15; // zf
  int v16; // eax
  int v18; // eax
  HRESULT v19; // eax
  int v20; // eax
  int v21; // eax
  __int64 v22; // [rsp+60h] [rbp-20h] BYREF
  __int64 v23; // [rsp+68h] [rbp-18h] BYREF
  LPITEMIDLIST ppidl; // [rsp+70h] [rbp-10h] BYREF
  void *ppv; // [rsp+A0h] [rbp+20h] BYREF
  void *v26; // [rsp+B8h] [rbp+38h] BYREF

  v26 = a4;
  ppidl = 0;
  *a5 = 0;
  v8 = SHGetIDListFromObject(this[6], &ppidl);
  *((_DWORD *)this + 11) = v8;
  if ( v8 >= 0 )
  {
    ppv = 0;
    v9 = SHCreateItemFromIDList(ppidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
    *((_DWORD *)this + 11) = v9;
    if ( v9 < 0 )
    {
LABEL_12:
      ILFree(ppidl);
      return *((unsigned int *)this + 11);
    }
    v23 = 0;
    v10 = CreateResultSetFactory(ppv, &PKEY_ResultSourceId, &GUID_8e621d2b_5a4c_450c_8b78_c7f52c1f1d9b, &v23);
    *((_DWORD *)this + 11) = v10;
    if ( v10 < 0 )
    {
LABEL_11:
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      goto LABEL_12;
    }
    a5 = 0;
    ResultShape = CDBEnum::_CreateResultShape((CDBEnum *)this, a2, v11, (void **)&a5);
    *((_DWORD *)this + 11) = ResultShape;
    if ( ResultShape < 0 )
    {
LABEL_10:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      goto LABEL_11;
    }
    v14 = 0;
    v26 = 0;
    if ( (a3 & 0x800) == 0 && (a3 & 0x10080) != 0x10080 )
    {
      v18 = CDBEnum::_CreateFilterOutHiddenCondition((CDBEnum *)0x10080, a3, v13, &v26);
      *((_DWORD *)this + 11) = v18;
      if ( v18 < 0 )
      {
LABEL_9:
        (*((void (__fastcall **)(void **))*a5 + 2))(a5);
        goto LABEL_10;
      }
      v14 = v26;
    }
    v15 = *((_DWORD *)this + 23) == 2;
    v22 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, void **, void *, const PROPERTYKEY *, _QWORD, _QWORD, bool, GUID *, __int64 *))(*(_QWORD *)v23 + 32LL))(
            v23,
            (unsigned __int64)(this + 2) & ((unsigned __int128)-(__int128)(unsigned __int64)this >> 64),
            a5,
            v14,
            &PKEY_Null,
            0,
            0,
            v15,
            &GUID_5632b1a4_e38a_400a_928a_d4cd63230295,
            &v22);
    *((_DWORD *)this + 11) = v16;
    if ( v16 >= 0 )
    {
      v26 = 0;
      v19 = SHCoCreateInstance(0, &CLSID_ResultSetManager, 0, &GUID_d6effa92_c1ad_4416_b077_84d5e448bdb8, &v26);
      *((_DWORD *)this + 11) = v19;
      if ( v19 >= 0 )
      {
        v20 = (*(__int64 (__fastcall **)(void *, __int64, void **, void *))(*(_QWORD *)v26 + 24LL))(v26, v22, a5, ppv);
        *((_DWORD *)this + 11) = v20;
        if ( v20 >= 0 )
        {
          v21 = (**(__int64 (__fastcall ***)(void *, GUID *, char *))v26)(
                  v26,
                  &GUID_d3b521a9_64fb_463e_b2cd_6ebbd1c50330,
                  (char *)this + 136);
          *((_DWORD *)this + 11) = v21;
          if ( v21 >= 0 )
            *((_DWORD *)this + 11) = ((__int64 (__fastcall *)(IUnknown *, char *))this[17]->lpVtbl[1].QueryInterface)(
                                       this[17],
                                       (char *)this + 148);
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)v26 + 16LL))(v26);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    if ( v14 )
      (*(void (__fastcall **)(void *))(*(_QWORD *)v14 + 16LL))(v14);
    goto LABEL_9;
  }
  return *((unsigned int *)this + 11);
}

```

## disassembly

```asm
0x1800287c0  mov     [rsp-18h+arg_8], rbx
0x1800287c5  mov     [rsp-18h+arg_18], r9
0x1800287ca  push    rbp
0x1800287cb  push    rsi
0x1800287cc  push    rdi
0x1800287cd  mov     rbp, rsp
0x1800287d0  sub     rsp, 80h
0x1800287d7  mov     rax, [rbp+arg_20]
0x1800287db  mov     rdi, rdx
0x1800287de  mov     rbx, rcx
0x1800287e1  mov     [rbp+ppidl], 0
0x1800287e9  lea     rdx, [rbp+ppidl]; ppidl
0x1800287ed  mov     esi, r8d
0x1800287f0  mov     qword ptr [rax], 0
0x1800287f7  mov     rcx, [rcx+30h]; punk
0x1800287fb  call    cs:__imp_SHGetIDListFromObject
0x180028801  mov     [rbx+2Ch], eax
0x180028804  test    eax, eax
0x180028806  js      loc_180028962
0x18002880c  mov     rcx, [rbp+ppidl]; pidl
0x180028810  lea     r8, [rbp+ppv]; ppv
0x180028814  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18002881b  mov     [rbp+ppv], 0
0x180028823  call    cs:__imp_SHCreateItemFromIDList
0x180028829  mov     [rbx+2Ch], eax
0x18002882c  test    eax, eax
0x18002882e  js      loc_180028958
0x180028834  mov     rcx, [rbp+ppv]
0x180028838  lea     r9, [rbp+var_18]
0x18002883c  lea     r8, _GUID_8e621d2b_5a4c_450c_8b78_c7f52c1f1d9b
0x180028843  mov     [rbp+var_18], 0
0x18002884b  lea     rdx, PKEY_ResultSourceId
0x180028852  call    CreateResultSetFactory
0x180028857  mov     [rbx+2Ch], eax
0x18002885a  test    eax, eax
0x18002885c  js      loc_180028948
0x180028862  lea     r9, [rbp+arg_20]; void **
0x180028866  mov     [rbp+arg_20], 0
0x18002886e  mov     rdx, rdi; struct _tagpropertykey *
0x180028871  mov     rcx, rbx; this
0x180028874  call    ?_CreateResultShape@CDBEnum@@AEAAJAEBU_tagpropertykey@@AEBU_GUID@@PEAPEAX@Z; CDBEnum::_CreateResultShape(_tagpropertykey const &,_GUID const &,void * *)
0x180028879  mov     [rbx+2Ch], eax
0x18002887c  test    eax, eax
0x18002887e  js      loc_180028938
0x180028884  xor     edi, edi
0x180028886  mov     [rbp+arg_18], rdi
0x18002888a  bt      esi, 0Bh
0x18002888e  jnb     loc_180028993
0x180028894  mov     r11, [rbp+var_18]
0x180028898  lea     rcx, [rbx+10h]
0x18002889c  mov     r8, [rbp+arg_20]
0x1800288a0  xor     r10d, r10d
0x1800288a3  cmp     dword ptr [rbx+5Ch], 2
0x1800288a7  mov     rax, rbx
0x1800288aa  mov     [rbp+var_20], 0
0x1800288b2  mov     r9, [r11]
0x1800288b5  setz    r10b
0x1800288b9  neg     rax
0x1800288bc  sbb     rdx, rdx
0x1800288bf  mov     rax, [r9+20h]
0x1800288c3  and     rdx, rcx
0x1800288c6  lea     rcx, [rbp+var_20]
0x1800288ca  mov     r9, rdi
0x1800288cd  mov     [rsp+80h+var_38], rcx
0x1800288d2  lea     rcx, _GUID_5632b1a4_e38a_400a_928a_d4cd63230295
0x1800288d9  mov     [rsp+80h+var_40], rcx
0x1800288de  lea     rcx, PKEY_Null
0x1800288e5  mov     [rsp+80h+var_48], r10d
0x1800288ea  mov     [rsp+80h+var_50], 0
0x1800288f3  mov     [rsp+80h+var_58], 0
0x1800288fc  mov     [rsp+80h+var_60], rcx
0x180028901  mov     rcx, r11
0x180028904  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028909  mov     [rbx+2Ch], eax
0x18002890c  test    eax, eax
0x18002890e  jns     loc_1800289A6
0x180028914  test    rdi, rdi
0x180028917  jz      short loc_180028928
0x180028919  mov     rax, [rdi]
0x18002891c  mov     rcx, rdi
0x18002891f  mov     rax, [rax+10h]
0x180028923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028928  mov     rcx, [rbp+arg_20]
0x18002892c  mov     rax, [rcx]
0x18002892f  mov     rax, [rax+10h]
0x180028933  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028938  mov     rcx, [rbp+var_18]
0x18002893c  mov     rax, [rcx]
0x18002893f  mov     rax, [rax+10h]
0x180028943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028948  mov     rcx, [rbp+ppv]
0x18002894c  mov     rax, [rcx]
0x18002894f  mov     rax, [rax+10h]
0x180028953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028958  mov     rcx, [rbp+ppidl]; pidl
0x18002895c  call    cs:__imp_ILFree
0x180028962  mov     eax, [rbx+2Ch]
0x180028965  mov     rbx, [rsp+80h+arg_8]
0x18002896d  add     rsp, 80h
0x180028974  pop     rdi
0x180028975  pop     rsi
0x180028976  pop     rbp
0x180028977  retn
0x180028978  lea     r9, [rbp+arg_18]; void **
0x18002897c  mov     edx, esi; unsigned int
0x18002897e  call    ?_CreateFilterOutHiddenCondition@CDBEnum@@AEAAJKAEBU_GUID@@PEAPEAX@Z; CDBEnum::_CreateFilterOutHiddenCondition(ulong,_GUID const &,void * *)
0x180028983  mov     [rbx+2Ch], eax
0x180028986  test    eax, eax
0x180028988  js      short loc_180028928
0x18002898a  mov     rdi, [rbp+arg_18]
0x18002898e  jmp     loc_180028894
0x180028993  mov     ecx, 10080h; this
0x180028998  mov     eax, esi
0x18002899a  and     eax, ecx
0x18002899c  cmp     eax, ecx
0x18002899e  jz      loc_180028894
0x1800289a4  jmp     short loc_180028978
0x1800289a6  lea     rax, [rbp+arg_18]
0x1800289aa  mov     [rbp+arg_18], 0
0x1800289b2  lea     r9, _GUID_d6effa92_c1ad_4416_b077_84d5e448bdb8; riid
0x1800289b9  mov     [rsp+80h+var_60], rax; ppv
0x1800289be  xor     r8d, r8d; pUnkOuter
0x1800289c1  lea     rdx, CLSID_ResultSetManager; pclsid
0x1800289c8  xor     ecx, ecx; pszCLSID
0x1800289ca  call    cs:__imp_SHCoCreateInstance
0x1800289d0  mov     [rbx+2Ch], eax
0x1800289d3  test    eax, eax
0x1800289d5  js      short loc_180028A4A
0x1800289d7  mov     rcx, [rbp+arg_18]
0x1800289db  mov     r9, [rbp+ppv]
0x1800289df  mov     r8, [rbp+arg_20]
0x1800289e3  mov     rdx, [rbp+var_20]
0x1800289e7  mov     rax, [rcx]
0x1800289ea  mov     rax, [rax+18h]
0x1800289ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800289f3  mov     [rbx+2Ch], eax
0x1800289f6  test    eax, eax
0x1800289f8  js      short loc_180028A3A
0x1800289fa  mov     rcx, [rbp+arg_18]
0x1800289fe  lea     rsi, [rbx+88h]
0x180028a05  mov     r8, rsi
0x180028a08  lea     rdx, _GUID_d3b521a9_64fb_463e_b2cd_6ebbd1c50330
0x180028a0f  mov     rax, [rcx]
0x180028a12  mov     rax, [rax]
0x180028a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a1a  mov     [rbx+2Ch], eax
0x180028a1d  test    eax, eax
0x180028a1f  js      short loc_180028A3A
0x180028a21  mov     rcx, [rsi]
0x180028a24  lea     rdx, [rbx+94h]
0x180028a2b  mov     rax, [rcx]
0x180028a2e  mov     rax, [rax+18h]
0x180028a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a37  mov     [rbx+2Ch], eax
0x180028a3a  mov     rcx, [rbp+arg_18]
0x180028a3e  mov     rax, [rcx]
0x180028a41  mov     rax, [rax+10h]
0x180028a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a4a  mov     rcx, [rbp+var_20]
0x180028a4e  mov     rax, [rcx]
0x180028a51  mov     rax, [rax+10h]
0x180028a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028a5a  jmp     loc_180028914
```
