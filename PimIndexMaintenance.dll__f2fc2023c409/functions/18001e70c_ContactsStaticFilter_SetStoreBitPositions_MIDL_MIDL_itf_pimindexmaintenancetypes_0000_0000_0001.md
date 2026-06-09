# ContactsStaticFilter::SetStoreBitPositions(__MIDL___MIDL_itf_pimindexmaintenancetypes_0000_0000_0001)

- ea: `0x18001e70c`
- end: `0x18001ea0f`
- name: `?SetStoreBitPositions@ContactsStaticFilter@@AEAAJW4__MIDL___MIDL_itf_pimindexmaintenancetypes_0000_0000_0001@@@Z`
- size: `771`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001e294`

## callees

- `0x180002da8`
- `0x180003f0c`
- `0x18000428c`
- `0x1800086a0`
- `0x18000b5f4`
- `0x18001e6d4`
- `0x18001e70c`
- `0x18001ea98`
- `0x18002120a`
- `0x180021240`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e8a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001e8a0`
- `PIMSTORE!GetDefaultStoreFilter` at `0x18001e80a`
- `PIMSTORE!GetDefaultStoreFilter` at `0x18001e80a`

## string_xrefs

- `0x18001e75c`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\contactsstaticfilter.cpp`
- `0x18001e81c`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\contactsstaticfilter.cpp`
- `0x18001e8f7`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\contactsstaticfilter.cpp`
- `0x18001e9f0`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\indexfilter\contactsstaticfilter.cpp`

## pseudocode

```c
__int64 __fastcall ContactsStaticFilter::SetStoreBitPositions(__int64 *a1, int a2)
{
  __int64 v2; // rax
  int v5; // eax
  unsigned int v6; // ebx
  unsigned __int16 v8; // r15
  __int64 v9; // rax
  StoreFilterBlob *v10; // r13
  int DefaultStoreFilter; // eax
  unsigned __int16 v12; // r12
  int v13; // ebx
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, _DWORD *, __int64, _QWORD, _QWORD *, int *, HANDLE); // rsi
  HANDLE ProcessHeap; // rdi
  _QWORD *v17; // rax
  int v18; // eax
  __int64 v19; // rcx
  _DWORD *v20; // rax
  unsigned int v21; // r10d
  unsigned int v22; // r11d
  __int64 v23; // r9
  __int64 v24; // rcx
  __int64 v25; // r9
  __int64 v26; // [rsp+40h] [rbp-29h] BYREF
  _DWORD *v27; // [rsp+48h] [rbp-21h] BYREF
  __int64 v28; // [rsp+50h] [rbp-19h] BYREF
  int v29; // [rsp+58h] [rbp-11h] BYREF
  _DWORD v30[4]; // [rsp+60h] [rbp-9h] BYREF

  v2 = *a1;
  v28 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v2 + 32))(a1, &v28);
  v6 = v5;
  if ( v5 < 0 )
  {
    Log_HREvent(
      (unsigned int)v5,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\contactsstaticfilter.cpp",
      143);
    goto LABEL_6;
  }
  v26 = 0;
  v30[0] = 327698;
  if ( a2 == -1 )
  {
    auto_struct<StoreFilterBlob,&public: static void StoreFilterBlob::FreeStoreFilterBlob(StoreFilterBlob *)>::reset(a1 + 3);
LABEL_5:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
    v6 = 0;
    goto LABEL_6;
  }
  if ( (a2 & 2) != 0 )
    v30[1] = 28180499;
  v8 = ((a2 & 2) != 0) + 1;
  if ( (a2 & 0x80u) != 0 )
  {
    v9 = v8;
    v8 = ((a2 & 2) != 0) + 2;
    v30[v9] = 279379987;
  }
  v10 = (StoreFilterBlob *)(a1 + 3);
  if ( *((_DWORD *)a1 + 6) )
  {
    memset_0((void *)a1[4], 0, *(unsigned int *)v10);
LABEL_16:
    v12 = 0;
    v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v28 + 80LL))(v28, 0, &v26);
    while ( v13 >= 0 )
    {
      v14 = v26;
      if ( !v26 || v12 >= v8 - 1 )
        break;
      v27 = 0;
      v29 = 0;
      v15 = *(__int64 (__fastcall **)(__int64, _DWORD *, __int64, _QWORD, _QWORD *, int *, HANDLE))(*(_QWORD *)v26 + 80LL);
      ProcessHeap = GetProcessHeap();
      v17 = tlx::replace<_SQLCEPROPVAL,&void _LocalFreer<_SQLCEPROPVAL>(_SQLCEPROPVAL *)>(&v27);
      v18 = v15(v14, v30, 1, v8, v17, &v29, ProcessHeap);
      v6 = v18;
      if ( v18 < 0 )
      {
        v25 = 207;
LABEL_43:
        Log_HREvent(
          (unsigned int)v18,
          1,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\contactsstaticfilter.cpp",
          v25);
        auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>((void **)&v27);
        goto LABEL_14;
      }
      v20 = v27;
      if ( *v27 != 327698 )
      {
        Log_AssertionEvent(
          v19,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\contactsstaticfilter.cpp",
          209);
        v20 = v27;
      }
      if ( (*((_WORD *)v20 + 3) & 0x300) == 0 )
      {
        v21 = 1;
        v22 = v8;
        while ( v21 < v22 )
        {
          v23 = 3LL * v21;
          if ( (v20[6 * v21 + 1] & 0x3000000) == 0 )
          {
            if ( v20[6 * v21] == 28180499 && v20[6 * v21 + 2] == 7 )
            {
              v18 = StoreFilterBlob::SetNthBlobBit(v10, *((unsigned __int16 *)v20 + 4));
              v6 = v18;
              if ( v18 < 0 )
              {
                v25 = 225;
                goto LABEL_43;
              }
              v20 = v27;
              ++v12;
            }
            if ( (v20[2 * v23 + 1] & 0x3000000) == 0 && v20[2 * v23] == 279379987 && v20[2 * v23 + 2] == 1 )
            {
              v18 = StoreFilterBlob::SetNthBlobBit(v10, *((unsigned __int16 *)v20 + 4));
              v6 = v18;
              if ( v18 < 0 )
              {
                v25 = 236;
                goto LABEL_43;
              }
              v20 = v27;
              ++v12;
            }
          }
          ++v21;
        }
      }
      v24 = v26;
      if ( v26 )
      {
        v26 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
      }
      v13 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v28 + 88LL))(v28, &v26);
      auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>((void **)&v27);
    }
    goto LABEL_5;
  }
  DefaultStoreFilter = GetDefaultStoreFilter(a1 + 3);
  v6 = DefaultStoreFilter;
  if ( DefaultStoreFilter >= 0 )
    goto LABEL_16;
  Log_HREvent(
    (unsigned int)DefaultStoreFilter,
    1,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\indexfilter\\contactsstaticfilter.cpp",
    180);
LABEL_14:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
LABEL_6:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
  return v6;
}

```

## disassembly

```asm
0x18001e70c  push    rbp
0x18001e70e  push    rbx
0x18001e70f  push    rsi
0x18001e710  push    rdi
0x18001e711  push    r12
0x18001e713  push    r13
0x18001e715  push    r14
0x18001e717  push    r15
0x18001e719  lea     rbp, [rsp-1Fh]
0x18001e71e  sub     rsp, 88h
0x18001e725  mov     rax, cs:__security_cookie
0x18001e72c  xor     rax, rsp
0x18001e72f  mov     [rbp+57h+var_50], rax
0x18001e733  mov     rax, [rcx]
0x18001e736  mov     esi, edx
0x18001e738  lea     rdx, [rbp+57h+var_70]
0x18001e73c  mov     [rbp+57h+var_70], 0
0x18001e744  mov     rdi, rcx
0x18001e747  mov     rax, [rax+20h]
0x18001e74b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e750  mov     ebx, eax
0x18001e752  test    eax, eax
0x18001e754  jns     short loc_18001E771
0x18001e756  mov     r9d, 8Fh
0x18001e75c  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001e763  mov     edx, 1
0x18001e768  mov     ecx, eax
0x18001e76a  call    Log_HREvent
0x18001e76f  jmp     short loc_18001E799
0x18001e771  mov     [rbp+57h+var_80], 0
0x18001e779  mov     [rbp+57h+var_60], 50012h
0x18001e780  cmp     esi, 0FFFFFFFFh
0x18001e783  jnz     short loc_18001E7C4
0x18001e785  lea     rcx, [rdi+18h]
0x18001e789  call    ?reset@?$auto_struct@UStoreFilterBlob@@$1?FreeStoreFilterBlob@1@SAXPEAU1@@Z@@QEAAXXZ; auto_struct<StoreFilterBlob,&StoreFilterBlob::FreeStoreFilterBlob(StoreFilterBlob *)>::reset(void)
0x18001e78e  lea     rcx, [rbp+57h+var_80]
0x18001e792  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001e797  xor     ebx, ebx
0x18001e799  lea     rcx, [rbp+57h+var_70]
0x18001e79d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001e7a2  mov     eax, ebx
0x18001e7a4  mov     rcx, [rbp+57h+var_50]
0x18001e7a8  xor     rcx, rsp; StackCookie
0x18001e7ab  call    __security_check_cookie
0x18001e7b0  add     rsp, 88h
0x18001e7b7  pop     r15
0x18001e7b9  pop     r14
0x18001e7bb  pop     r13
0x18001e7bd  pop     r12
0x18001e7bf  pop     rdi
0x18001e7c0  pop     rsi
0x18001e7c1  pop     rbx
0x18001e7c2  pop     rbp
0x18001e7c3  retn
0x18001e7c4  mov     eax, esi
0x18001e7c6  and     eax, 2
0x18001e7c9  jz      short loc_18001E7D2
0x18001e7cb  mov     [rbp+57h+var_5C], 1AE0013h
0x18001e7d2  neg     eax
0x18001e7d4  mov     r14d, 1
0x18001e7da  sbb     r15w, r15w
0x18001e7de  neg     r15w
0x18001e7e2  add     r15w, r14w
0x18001e7e6  test    sil, sil
0x18001e7e9  jns     short loc_18001E7FB
0x18001e7eb  movzx   eax, r15w
0x18001e7ef  add     r15w, r14w
0x18001e7f3  mov     [rbp+rax*4+57h+var_60], 10A70013h
0x18001e7fb  lea     r13, [rdi+18h]
0x18001e7ff  xor     edx, edx; Val
0x18001e801  cmp     [r13+0], edx
0x18001e805  jnz     short loc_18001E83B
0x18001e807  mov     rcx, r13
0x18001e80a  call    cs:__imp_GetDefaultStoreFilter
0x18001e810  mov     ebx, eax
0x18001e812  test    eax, eax
0x18001e814  jns     short loc_18001E848
0x18001e816  mov     r9d, 0B4h
0x18001e81c  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001e823  mov     edx, r14d
0x18001e826  mov     ecx, eax
0x18001e828  call    Log_HREvent
0x18001e82d  lea     rcx, [rbp+57h+var_80]
0x18001e831  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001e836  jmp     loc_18001E799
0x18001e83b  mov     r8d, [r13+0]; Size
0x18001e83f  mov     rcx, [rdi+20h]; void *
0x18001e843  call    memset_0
0x18001e848  mov     rcx, [rbp+57h+var_70]
0x18001e84c  lea     r8, [rbp+57h+var_80]
0x18001e850  xor     r12d, r12d
0x18001e853  xor     edx, edx
0x18001e855  mov     rax, [rcx]
0x18001e858  mov     rax, [rax+50h]
0x18001e85c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e861  mov     ebx, eax
0x18001e863  test    ebx, ebx
0x18001e865  js      loc_18001E78E
0x18001e86b  mov     rbx, [rbp+57h+var_80]
0x18001e86f  test    rbx, rbx
0x18001e872  jz      loc_18001E78E
0x18001e878  movzx   ecx, r15w
0x18001e87c  dec     ecx
0x18001e87e  movzx   eax, r12w
0x18001e882  cmp     eax, ecx
0x18001e884  jge     loc_18001E78E
0x18001e88a  mov     [rbp+57h+var_78], 0
0x18001e892  mov     [rbp+57h+var_68], 0
0x18001e899  mov     rax, [rbx]
0x18001e89c  mov     rsi, [rax+50h]
0x18001e8a0  call    cs:__imp_GetProcessHeap
0x18001e8a6  lea     rcx, [rbp+57h+var_78]
0x18001e8aa  mov     rdi, rax
0x18001e8ad  call    ??$replace@U_SQLCEPROPVAL@@$1??$_LocalFreer@U_SQLCEPROPVAL@@@@YAXPEAU1@@Z@tlx@@YAPEAPEAU_SQLCEPROPVAL@@AEAV?$auto_array_ptr@U_SQLCEPROPVAL@@$1??$_LocalFreer@U_SQLCEPROPVAL@@@@YAXPEAU1@@Z@0@@Z; tlx::replace<_SQLCEPROPVAL,&_LocalFreer<_SQLCEPROPVAL>(_SQLCEPROPVAL *)>(tlx::auto_array_ptr<_SQLCEPROPVAL,&_LocalFreer<_SQLCEPROPVAL>(_SQLCEPROPVAL *)> &)
0x18001e8b2  lea     rcx, [rbp+57h+var_68]
0x18001e8b6  mov     [rsp+0C0h+var_90], rdi
0x18001e8bb  mov     [rsp+0C0h+var_98], rcx
0x18001e8c0  lea     rdx, [rbp+57h+var_60]
0x18001e8c4  mov     [rsp+0C0h+var_A0], rax
0x18001e8c9  movzx   r9d, r15w
0x18001e8cd  mov     rax, rsi
0x18001e8d0  mov     r8d, r14d
0x18001e8d3  mov     rcx, rbx
0x18001e8d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8db  mov     ebx, eax
0x18001e8dd  test    eax, eax
0x18001e8df  js      loc_18001E9EA
0x18001e8e5  mov     rax, [rbp+57h+var_78]
0x18001e8e9  cmp     dword ptr [rax], 50012h
0x18001e8ef  jz      short loc_18001E907
0x18001e8f1  mov     r8d, 0D1h
0x18001e8f7  lea     rdx, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001e8fe  call    Log_AssertionEvent
0x18001e903  mov     rax, [rbp+57h+var_78]
0x18001e907  mov     edi, 300h
0x18001e90c  test    [rax+6], di
0x18001e910  jnz     loc_18001E999
0x18001e916  mov     r10d, r14d
0x18001e919  movzx   r11d, r15w
0x18001e91d  cmp     r10d, r11d
0x18001e920  jnb     short loc_18001E999
0x18001e922  mov     ecx, r10d
0x18001e925  lea     r9, [rcx+rcx*2]
0x18001e929  test    [rax+r9*8+6], di
0x18001e92f  jnz     short loc_18001E994
0x18001e931  cmp     dword ptr [rax+r9*8], 1AE0013h
0x18001e939  jnz     short loc_18001E961
0x18001e93b  cmp     dword ptr [rax+r9*8+8], 7
0x18001e941  jnz     short loc_18001E961
0x18001e943  movzx   edx, word ptr [rax+8]; unsigned int
0x18001e947  mov     rcx, r13; this
0x18001e94a  call    ?SetNthBlobBit@StoreFilterBlob@@QEAAJI@Z; StoreFilterBlob::SetNthBlobBit(uint)
0x18001e94f  mov     ebx, eax
0x18001e951  test    eax, eax
0x18001e953  js      loc_18001E9DA
0x18001e959  mov     rax, [rbp+57h+var_78]
0x18001e95d  add     r12w, r14w
0x18001e961  test    [rax+r9*8+6], di
0x18001e967  jnz     short loc_18001E994
0x18001e969  cmp     dword ptr [rax+r9*8], 10A70013h
0x18001e971  jnz     short loc_18001E994
0x18001e973  cmp     [rax+r9*8+8], r14d
0x18001e978  jnz     short loc_18001E994
0x18001e97a  movzx   edx, word ptr [rax+8]; unsigned int
0x18001e97e  mov     rcx, r13; this
0x18001e981  call    ?SetNthBlobBit@StoreFilterBlob@@QEAAJI@Z; StoreFilterBlob::SetNthBlobBit(uint)
0x18001e986  mov     ebx, eax
0x18001e988  test    eax, eax
0x18001e98a  js      short loc_18001E9E2
0x18001e98c  mov     rax, [rbp+57h+var_78]
0x18001e990  add     r12w, r14w
0x18001e994  add     r10d, r14d
0x18001e997  jmp     short loc_18001E91D
0x18001e999  mov     rcx, [rbp+57h+var_80]
0x18001e99d  test    rcx, rcx
0x18001e9a0  jz      short loc_18001E9B6
0x18001e9a2  mov     [rbp+57h+var_80], 0
0x18001e9aa  mov     rax, [rcx]
0x18001e9ad  mov     rax, [rax+10h]
0x18001e9b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9b6  mov     rcx, [rbp+57h+var_70]
0x18001e9ba  lea     rdx, [rbp+57h+var_80]
0x18001e9be  mov     rax, [rcx]
0x18001e9c1  mov     rax, [rax+58h]
0x18001e9c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e9ca  lea     rcx, [rbp+57h+var_78]
0x18001e9ce  mov     ebx, eax
0x18001e9d0  call    ??1?$auto_local_array_ptr@UPIMINDEXENTRY@@@@QEAA@XZ; auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(void)
0x18001e9d5  jmp     loc_18001E863
0x18001e9da  mov     r9d, 0E1h
0x18001e9e0  jmp     short loc_18001E9F0
0x18001e9e2  mov     r9d, 0ECh
0x18001e9e8  jmp     short loc_18001E9F0
0x18001e9ea  mov     r9d, 0CFh
0x18001e9f0  lea     r8, aOnecoreuapBase_16; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18001e9f7  mov     edx, r14d
0x18001e9fa  mov     ecx, eax
0x18001e9fc  call    Log_HREvent
0x18001ea01  lea     rcx, [rbp+57h+var_78]
0x18001ea05  call    ??1?$auto_local_array_ptr@UPIMINDEXENTRY@@@@QEAA@XZ; auto_local_array_ptr<PIMINDEXENTRY>::~auto_local_array_ptr<PIMINDEXENTRY>(void)
0x18001ea0a  jmp     loc_18001E82D
```
