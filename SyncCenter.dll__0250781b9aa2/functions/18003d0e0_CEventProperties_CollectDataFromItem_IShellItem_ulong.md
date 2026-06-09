# CEventProperties::CollectDataFromItem(IShellItem *,ulong)

- ea: `0x18003d0e0`
- end: `0x18003d4b4`
- name: `?CollectDataFromItem@CEventProperties@@EEAAJPEAUIShellItem@@K@Z`
- size: `980`
- prototype: `__int64 __fastcall(CEventProperties *__hidden this, struct IShellItem *, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180005660`
- `0x18003d0e0`
- `0x18005292a`
- `0x180052950`
- `0x180053010`

## import_xrefs

- `SHLWAPI!__imp_SHFormatDateTimeW` at `0x18003d263`
- `SHLWAPI!__imp_SHFormatDateTimeW` at `0x18003d263`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d1ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d1e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d29e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d2db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d316`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d34f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d388`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d1ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d1e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d29e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d2db`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d316`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d34f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d388`

## pseudocode

```c
__int64 __fastcall CEventProperties::CollectDataFromItem(
        CEventProperties *this,
        struct IShellItem *a2,
        unsigned int a3)
{
  __int64 v3; // r14
  __int64 v4; // rsi
  __int64 v6; // rbx
  struct IShellItemVtbl *lpVtbl; // rax
  struct IShellItemVtbl *v8; // rax
  int v9; // edi
  LPVOID pv; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
  int v13; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v14; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v15[276]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int16 v16[542]; // [rsp+164h] [rbp+64h] BYREF

  v3 = *((_QWORD *)this + 3);
  v4 = 3016LL * a3;
  *(_QWORD *)(v4 + v3) = a2;
  v6 = v4 + v3;
  lpVtbl = a2->lpVtbl;
  v12 = 0;
  if ( ((int (__fastcall *)(struct IShellItem *, _QWORD, const GUID *, GUID *, __int64 *))lpVtbl->BindToHandler)(
         a2,
         0,
         &BHID_SFObject,
         &GUID_fee0ef8b_46bd_4db4_b7e6_ff2c687313bc,
         &v12) >= 0 )
  {
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 24LL))(v12, v6 + 264);
    pv = 0;
    if ( (*(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v12 + 32LL))(v12, &pv) >= 0 )
    {
      StringCchCopyW((unsigned __int16 *)(v6 + 8), 0x40u, (const unsigned __int16 *)pv);
      CoTaskMemFree(pv);
    }
    if ( (*(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v12 + 40LL))(v12, &pv) >= 0 )
    {
      StringCchCopyW((unsigned __int16 *)(v6 + 136), 0x40u, (const unsigned __int16 *)pv);
      CoTaskMemFree(pv);
    }
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 48LL))(v12, v4 + v3 + 2884);
    v13 = 0;
    if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v12 + 56LL))(v12, &v13) >= 0 )
      *(_DWORD *)(v6 + 284) = v13;
    if ( (*(int (__fastcall **)(__int64, __int64))(*(_QWORD *)v12 + 64LL))(v12, v6 + 2876) >= 0 )
      SHFormatDateTimeW((const FILETIME *)(v6 + 2876), 0, (LPWSTR)(v4 + v3 + 2888), 0x40u);
    if ( (*(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v12 + 72LL))(v12, &pv) >= 0 )
    {
      StringCchCopyW((unsigned __int16 *)(v6 + 292), 0x80u, (const unsigned __int16 *)pv);
      CoTaskMemFree(pv);
    }
    if ( (*(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v12 + 80LL))(v12, &pv) >= 0 )
    {
      StringCchCopyW((unsigned __int16 *)(v6 + 548), 0x104u, (const unsigned __int16 *)pv);
      CoTaskMemFree(pv);
    }
    if ( (*(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v12 + 88LL))(v12, &pv) >= 0 )
    {
      StringCchCopyW((unsigned __int16 *)(v6 + 1068), 0x80u, (const unsigned __int16 *)pv);
      CoTaskMemFree(pv);
    }
    if ( (*(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v12 + 96LL))(v12, &pv) >= 0 )
    {
      StringCchCopyW((unsigned __int16 *)(v6 + 1324), 0x104u, (const unsigned __int16 *)pv);
      CoTaskMemFree(pv);
    }
    if ( (*(int (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v12 + 104LL))(v12, &pv) >= 0 )
    {
      StringCchCopyW((unsigned __int16 *)(v6 + 1844), 0x104u, (const unsigned __int16 *)pv);
      CoTaskMemFree(pv);
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  v8 = a2->lpVtbl;
  v14 = 0;
  v9 = ((__int64 (__fastcall *)(struct IShellItem *, _QWORD, const GUID *, GUID *, __int64 *))v8->BindToHandler)(
         a2,
         0,
         &BHID_SFObject,
         &GUID_4432069a_8093_4646_817f_3adea8ac480f,
         &v14);
  if ( v9 >= 0 )
  {
    memset_0(v15, 0, 0x550u);
    (*(void (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v14 + 24LL))(v14, v15);
    if ( (int)StringCchCopyW((unsigned __int16 *)(v6 + 2364), 0x80u, v16) >= 0 )
    {
      if ( *(_WORD *)(v6 + 136) )
      {
        pv = 0;
        if ( (*(int (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v14 + 56LL))(v14, v6 + 136, &pv) >= 0 )
        {
          (*(void (__fastcall **)(LPVOID, _BYTE *))(*(_QWORD *)pv + 32LL))(pv, v15);
          StringCchCopyW((unsigned __int16 *)(v6 + 2620), 0x80u, v16);
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)pv + 16LL))(pv);
        }
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18003d0e0  push    rbp
0x18003d0e2  push    rbx
0x18003d0e3  push    rsi
0x18003d0e4  push    rdi
0x18003d0e5  push    r12
0x18003d0e7  push    r14
0x18003d0e9  push    r15
0x18003d0eb  lea     rbp, [rsp-4B0h]
0x18003d0f3  sub     rsp, 5B0h
0x18003d0fa  mov     rax, cs:__security_cookie
0x18003d101  xor     rax, rsp
0x18003d104  mov     [rbp+4E0h+var_40], rax
0x18003d10b  mov     r14, [rcx+18h]
0x18003d10f  lea     r9, _GUID_fee0ef8b_46bd_4db4_b7e6_ff2c687313bc
0x18003d116  mov     eax, r8d
0x18003d119  lea     rcx, [rsp+5E0h+var_5A8]
0x18003d11e  imul    rsi, rax, 0BC8h
0x18003d125  mov     r15, rdx
0x18003d128  mov     [rsp+5E0h+var_5C0], rcx
0x18003d12d  xor     r12d, r12d
0x18003d130  lea     r8, BHID_SFObject
0x18003d137  mov     rcx, r15
0x18003d13a  mov     [rsi+r14], rdx
0x18003d13e  lea     rbx, [rsi+r14]
0x18003d142  mov     rax, [rdx]
0x18003d145  xor     edx, edx
0x18003d147  mov     [rsp+5E0h+var_5A8], r12
0x18003d14c  mov     rax, [rax+18h]
0x18003d150  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d155  test    eax, eax
0x18003d157  js      loc_18003D39F
0x18003d15d  mov     rcx, [rsp+5E0h+var_5A8]
0x18003d162  lea     rdx, [rbx+108h]
0x18003d169  mov     rax, [rcx]
0x18003d16c  mov     rax, [rax+18h]
0x18003d170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d175  mov     rcx, [rsp+5E0h+var_5A8]
0x18003d17a  lea     rdx, [rsp+5E0h+pv]
0x18003d17f  mov     [rsp+5E0h+pv], r12
0x18003d184  mov     rax, [rcx]
0x18003d187  mov     rax, [rax+20h]
0x18003d18b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d190  test    eax, eax
0x18003d192  js      short loc_18003D1B2
0x18003d194  mov     r8, [rsp+5E0h+pv]; unsigned __int16 *
0x18003d199  lea     edx, [r12+40h]; unsigned __int64
0x18003d19e  lea     rcx, [rbx+8]; unsigned __int16 *
0x18003d1a2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003d1a7  mov     rcx, [rsp+5E0h+pv]; pv
0x18003d1ac  call    cs:__imp_CoTaskMemFree
0x18003d1b2  mov     rcx, [rsp+5E0h+var_5A8]
0x18003d1b7  lea     rdx, [rsp+5E0h+pv]
0x18003d1bc  mov     rax, [rcx]
0x18003d1bf  mov     rax, [rax+28h]
0x18003d1c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1c8  test    eax, eax
0x18003d1ca  js      short loc_18003D1ED
0x18003d1cc  mov     r8, [rsp+5E0h+pv]; unsigned __int16 *
0x18003d1d1  lea     rcx, [rbx+88h]; unsigned __int16 *
0x18003d1d8  mov     edx, 40h ; '@'; unsigned __int64
0x18003d1dd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003d1e2  mov     rcx, [rsp+5E0h+pv]; pv
0x18003d1e7  call    cs:__imp_CoTaskMemFree
0x18003d1ed  mov     rcx, [rsp+5E0h+var_5A8]
0x18003d1f2  lea     rdx, [r14+0B44h]
0x18003d1f9  add     rdx, rsi
0x18003d1fc  mov     rax, [rcx]
0x18003d1ff  mov     rax, [rax+30h]
0x18003d203  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d208  mov     rcx, [rsp+5E0h+var_5A8]
0x18003d20d  lea     rdx, [rsp+5E0h+var_5A0]
0x18003d212  mov     [rsp+5E0h+var_5A0], r12d
0x18003d217  mov     rax, [rcx]
0x18003d21a  mov     rax, [rax+38h]
0x18003d21e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d223  test    eax, eax
0x18003d225  js      short loc_18003D231
0x18003d227  mov     eax, [rsp+5E0h+var_5A0]
0x18003d22b  mov     [rbx+11Ch], eax
0x18003d231  mov     rcx, [rsp+5E0h+var_5A8]
0x18003d236  lea     rdi, [rbx+0B3Ch]
0x18003d23d  mov     rdx, rdi
0x18003d240  mov     rax, [rcx]
0x18003d243  mov     rax, [rax+40h]
0x18003d247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d24c  test    eax, eax
0x18003d24e  js      short loc_18003D269
0x18003d250  xor     edx, edx; pdwFlags
0x18003d252  lea     r8, [r14+0B48h]
0x18003d259  add     r8, rsi; pszBuf
0x18003d25c  mov     rcx, rdi; pft
0x18003d25f  lea     r9d, [rdx+40h]; cchBuf
0x18003d263  call    cs:__imp_SHFormatDateTimeW
0x18003d269  mov     rcx, [rsp+5E0h+var_5A8]
0x18003d26e  lea     rdx, [rsp+5E0h+pv]
0x18003d273  mov     rax, [rcx]
0x18003d276  mov     rax, [rax+48h]
0x18003d27a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d27f  test    eax, eax
0x18003d281  js      short loc_18003D2A4
0x18003d283  mov     r8, [rsp+5E0h+pv]; unsigned __int16 *
0x18003d288  lea     rcx, [rbx+124h]; unsigned __int16 *
0x18003d28f  mov     edx, 80h; unsigned __int64
0x18003d294  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003d299  mov     rcx, [rsp+5E0h+pv]; pv
0x18003d29e  call    cs:__imp_CoTaskMemFree
0x18003d2a4  mov     rcx, [rsp+5E0h+var_5A8]
0x18003d2a9  lea     rdx, [rsp+5E0h+pv]
0x18003d2ae  mov     rax, [rcx]
0x18003d2b1  mov     rax, [rax+50h]
0x18003d2b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2ba  mov     edi, 104h
0x18003d2bf  test    eax, eax
0x18003d2c1  js      short loc_18003D2E1
0x18003d2c3  mov     r8, [rsp+5E0h+pv]; unsigned __int16 *
0x18003d2c8  lea     rcx, [rbx+224h]; unsigned __int16 *
0x18003d2cf  mov     edx, edi; unsigned __int64
0x18003d2d1  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003d2d6  mov     rcx, [rsp+5E0h+pv]; pv
0x18003d2db  call    cs:__imp_CoTaskMemFree
0x18003d2e1  mov     rcx, [rsp+5E0h+var_5A8]
0x18003d2e6  lea     rdx, [rsp+5E0h+pv]
0x18003d2eb  mov     rax, [rcx]
0x18003d2ee  mov     rax, [rax+58h]
0x18003d2f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2f7  test    eax, eax
0x18003d2f9  js      short loc_18003D31C
0x18003d2fb  mov     r8, [rsp+5E0h+pv]; unsigned __int16 *
0x18003d300  lea     rcx, [rbx+42Ch]; unsigned __int16 *
0x18003d307  mov     edx, 80h; unsigned __int64
0x18003d30c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003d311  mov     rcx, [rsp+5E0h+pv]; pv
0x18003d316  call    cs:__imp_CoTaskMemFree
0x18003d31c  mov     rcx, [rsp+5E0h+var_5A8]
0x18003d321  lea     rdx, [rsp+5E0h+pv]
0x18003d326  mov     rax, [rcx]
0x18003d329  mov     rax, [rax+60h]
0x18003d32d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d332  test    eax, eax
0x18003d334  js      short loc_18003D355
0x18003d336  mov     r8, [rsp+5E0h+pv]; unsigned __int16 *
0x18003d33b  lea     rcx, [rbx+52Ch]; unsigned __int16 *
0x18003d342  mov     rdx, rdi; unsigned __int64
0x18003d345  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003d34a  mov     rcx, [rsp+5E0h+pv]; pv
0x18003d34f  call    cs:__imp_CoTaskMemFree
0x18003d355  mov     rcx, [rsp+5E0h+var_5A8]
0x18003d35a  lea     rdx, [rsp+5E0h+pv]
0x18003d35f  mov     rax, [rcx]
0x18003d362  mov     rax, [rax+68h]
0x18003d366  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d36b  test    eax, eax
0x18003d36d  js      short loc_18003D38E
0x18003d36f  mov     r8, [rsp+5E0h+pv]; unsigned __int16 *
0x18003d374  lea     rcx, [rbx+734h]; unsigned __int16 *
0x18003d37b  mov     rdx, rdi; unsigned __int64
0x18003d37e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003d383  mov     rcx, [rsp+5E0h+pv]; pv
0x18003d388  call    cs:__imp_CoTaskMemFree
0x18003d38e  mov     rcx, [rsp+5E0h+var_5A8]
0x18003d393  mov     rax, [rcx]
0x18003d396  mov     rax, [rax+10h]
0x18003d39a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d39f  mov     rax, [r15]
0x18003d3a2  lea     rcx, [rsp+5E0h+var_598]
0x18003d3a7  mov     [rsp+5E0h+var_5C0], rcx
0x18003d3ac  lea     r9, _GUID_4432069a_8093_4646_817f_3adea8ac480f
0x18003d3b3  lea     r8, BHID_SFObject
0x18003d3ba  mov     [rsp+5E0h+var_598], r12
0x18003d3bf  xor     edx, edx
0x18003d3c1  mov     rcx, r15
0x18003d3c4  mov     rax, [rax+18h]
0x18003d3c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d3cd  mov     edi, eax
0x18003d3cf  test    eax, eax
0x18003d3d1  js      loc_18003D491
0x18003d3d7  xor     edx, edx; Val
0x18003d3d9  lea     rcx, [rsp+5E0h+var_590]; void *
0x18003d3de  mov     r8d, 550h; Size
0x18003d3e4  call    memset_0
0x18003d3e9  mov     rcx, [rsp+5E0h+var_598]
0x18003d3ee  mov     rdx, [rcx]
0x18003d3f1  mov     rax, [rdx+18h]
0x18003d3f5  lea     rdx, [rsp+5E0h+var_590]
0x18003d3fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d3ff  lea     rcx, [rbx+93Ch]; unsigned __int16 *
0x18003d406  mov     edx, 80h; unsigned __int64
0x18003d40b  lea     r8, [rbp+4E0h+var_47C]; unsigned __int16 *
0x18003d40f  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003d414  test    eax, eax
0x18003d416  js      short loc_18003D480
0x18003d418  lea     rdx, [rbx+88h]
0x18003d41f  cmp     [rdx], r12w
0x18003d423  jz      short loc_18003D480
0x18003d425  mov     rcx, [rsp+5E0h+var_598]
0x18003d42a  lea     r8, [rsp+5E0h+pv]
0x18003d42f  mov     [rsp+5E0h+pv], r12
0x18003d434  mov     rax, [rcx]
0x18003d437  mov     rax, [rax+38h]
0x18003d43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d440  test    eax, eax
0x18003d442  js      short loc_18003D480
0x18003d444  mov     rcx, [rsp+5E0h+pv]
0x18003d449  lea     rdx, [rsp+5E0h+var_590]
0x18003d44e  mov     rax, [rcx]
0x18003d451  mov     rax, [rax+20h]
0x18003d455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d45a  lea     rcx, [rbx+0A3Ch]; unsigned __int16 *
0x18003d461  mov     edx, 80h; unsigned __int64
0x18003d466  lea     r8, [rbp+4E0h+var_47C]; unsigned __int16 *
0x18003d46a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003d46f  mov     rcx, [rsp+5E0h+pv]
0x18003d474  mov     rax, [rcx]
0x18003d477  mov     rax, [rax+10h]
0x18003d47b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d480  mov     rcx, [rsp+5E0h+var_598]
0x18003d485  mov     rax, [rcx]
0x18003d488  mov     rax, [rax+10h]
0x18003d48c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d491  mov     eax, edi
0x18003d493  mov     rcx, [rbp+4E0h+var_40]
0x18003d49a  xor     rcx, rsp; StackCookie
0x18003d49d  call    __security_check_cookie
0x18003d4a2  add     rsp, 5B0h
0x18003d4a9  pop     r15
0x18003d4ab  pop     r14
0x18003d4ad  pop     r12
0x18003d4af  pop     rdi
0x18003d4b0  pop     rsi
0x18003d4b1  pop     rbx
0x18003d4b2  pop     rbp
0x18003d4b3  retn
```
