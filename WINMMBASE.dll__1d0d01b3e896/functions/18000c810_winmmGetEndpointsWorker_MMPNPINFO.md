# winmmGetEndpointsWorker(_MMPNPINFO *)

- ea: `0x18000c810`
- end: `0x18000cff1`
- name: `?winmmGetEndpointsWorker@@YAJPEAU_MMPNPINFO@@@Z`
- size: `2017`
- prototype: `__int64 __fastcall(struct _MMPNPINFO *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000c784`

## callees

- `0x18000c810`
- `0x18000eb68`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000cad1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000cdc5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000ce02`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000ce33`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000cad1`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000cdc5`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000ce02`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000ce33`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000cb3a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000cb3a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cb5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cfb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cfc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cfd7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cb5b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf6f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf82`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cf99`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cfb1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cfc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000cfd7`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000cda5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000cda5`
- `MMDevAPI!__imp_MMDeviceGetDeviceEnumerator` at `0x18000c881`
- `MMDevAPI!__imp_MMDeviceGetDeviceEnumerator` at `0x18000c881`

## pseudocode

```c
// Hidden C++ exception states: #wind=20
__int64 __fastcall winmmGetEndpointsWorker(struct _MMPNPINFO *a1)
{
  unsigned __int64 v2; // rdi
  unsigned __int64 v3; // rcx
  int i; // eax
  int DeviceEnumerator; // r15d
  int v6; // eax
  int v7; // eax
  int v8; // eax
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // rbx
  int v13; // r12d
  const WCHAR *v14; // rbx
  unsigned __int64 v15; // r14
  int v16; // esi
  unsigned __int64 v17; // rdi
  __int64 v18; // rax
  __int64 v19; // rax
  unsigned __int64 v20; // r9
  WCHAR *v21; // r8
  unsigned __int64 v22; // rdx
  __int64 v23; // rcx
  WCHAR v24; // ax
  WCHAR *v25; // rcx
  unsigned __int64 v27; // rdx
  __int64 v28; // rcx
  WCHAR *v29; // rcx
  LPCWCH lpString1; // [rsp+30h] [rbp-89h] BYREF
  __int64 v31; // [rsp+38h] [rbp-81h] BYREF
  __int64 v32; // [rsp+40h] [rbp-79h] BYREF
  __int64 v33; // [rsp+48h] [rbp-71h] BYREF
  LPCWCH v34; // [rsp+50h] [rbp-69h] BYREF
  LPCWCH lpString2; // [rsp+58h] [rbp-61h] BYREF
  LPCWCH v36; // [rsp+60h] [rbp-59h] BYREF
  LPCWCH v37; // [rsp+68h] [rbp-51h] BYREF
  __int64 v38; // [rsp+70h] [rbp-49h] BYREF
  __int64 v39; // [rsp+78h] [rbp-41h] BYREF
  __int64 v40; // [rsp+80h] [rbp-39h] BYREF
  __int64 v41; // [rsp+88h] [rbp-31h] BYREF
  __int64 v42; // [rsp+90h] [rbp-29h] BYREF
  PROPVARIANT v43; // [rsp+98h] [rbp-21h]
  unsigned __int64 v44; // [rsp+A0h] [rbp-19h]
  PROPVARIANT pvar[2]; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v46; // [rsp+B8h] [rbp-1h]
  __int64 v47; // [rsp+C0h] [rbp+7h]
  unsigned int v48; // [rsp+120h] [rbp+67h] BYREF
  BOOL bIgnoreCase; // [rsp+128h] [rbp+6Fh] BYREF
  int v50; // [rsp+130h] [rbp+77h]
  __int64 v51; // [rsp+138h] [rbp+7Fh] BYREF

  v48 = 0;
  v33 = 0;
  v38 = 0;
  v47 = 0;
  v42 = 0;
  v41 = 0;
  v40 = 0;
  v39 = 0;
  lpString1 = 0;
  v34 = 0;
  lpString2 = 0;
  v36 = 0;
  v37 = 0;
  v2 = ((unsigned __int64)a1 + 19) & 0xFFFFFFFFFFFFFFF8uLL;
  v44 = v2;
  v3 = v2;
  for ( i = *((_DWORD *)a1 + 2); i; --i )
  {
    v27 = v3 + 12;
    *(_DWORD *)(v3 + 8) |= 1u;
    v28 = -1;
    do
      ++v28;
    while ( *(_WORD *)(v27 + 2 * v28) );
    v3 = (v27 + 2 * v28 + 9) & 0xFFFFFFFFFFFFFFF8uLL;
  }
  DeviceEnumerator = MMDeviceGetDeviceEnumerator(&v33);
  if ( DeviceEnumerator < 0 )
    goto LABEL_66;
  DeviceEnumerator = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v33 + 24LL))(
                       v33,
                       2,
                       1,
                       &v38);
  if ( DeviceEnumerator < 0 )
    goto LABEL_66;
  DeviceEnumerator = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v38 + 24LL))(v38, &v48);
  if ( DeviceEnumerator < 0 )
  {
LABEL_107:
    if ( lpString1 )
    {
      CoTaskMemFree((LPVOID)lpString1);
      lpString1 = 0;
    }
    if ( v34 )
    {
      CoTaskMemFree((LPVOID)v34);
      v34 = 0;
    }
    if ( lpString2 )
    {
      CoTaskMemFree((LPVOID)lpString2);
      lpString2 = 0;
    }
    if ( v36 )
    {
      CoTaskMemFree((LPVOID)v36);
      v36 = 0;
    }
    v29 = (WCHAR *)v37;
    if ( v37 )
      goto LABEL_116;
    goto LABEL_66;
  }
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, __int64 *))(*(_QWORD *)v33 + 32LL))(v33, 0, 0, &v42);
  DeviceEnumerator = v6;
  if ( v6 < 0 )
  {
    if ( v6 != -2147023728 )
      goto LABEL_66;
  }
  else
  {
    (*(void (__fastcall **)(__int64, LPCWCH *))(*(_QWORD *)v42 + 40LL))(v42, &v34);
  }
  v7 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int64 *))(*(_QWORD *)v33 + 32LL))(v33, 1, 0, &v41);
  DeviceEnumerator = v7;
  if ( v7 < 0 )
  {
    if ( v7 != -2147023728 )
      goto LABEL_66;
  }
  else
  {
    (*(void (__fastcall **)(__int64, LPCWCH *))(*(_QWORD *)v41 + 40LL))(v41, &lpString2);
  }
  v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64 *))(*(_QWORD *)v33 + 32LL))(v33, 0, 2, &v40);
  DeviceEnumerator = v8;
  if ( v8 < 0 )
  {
    if ( v8 != -2147023728 )
      goto LABEL_66;
  }
  else
  {
    (*(void (__fastcall **)(__int64, LPCWCH *))(*(_QWORD *)v40 + 40LL))(v40, &v36);
  }
  v9 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *))(*(_QWORD *)v33 + 32LL))(v33, 1, 2, &v39);
  DeviceEnumerator = v9;
  if ( v9 < 0 )
  {
    if ( v9 != -2147023728 )
      goto LABEL_66;
  }
  else
  {
    (*(void (__fastcall **)(__int64, LPCWCH *))(*(_QWORD *)v39 + 40LL))(v39, &v37);
  }
  DeviceEnumerator = 0;
  v10 = 0;
  while ( 1 )
  {
    v50 = v10;
    if ( (unsigned int)v10 >= v48 )
      break;
    v32 = 0;
    v31 = 0;
    v51 = 0;
    bIgnoreCase = 0;
    DeviceEnumerator = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v38 + 32LL))(v38, v10, &v31);
    if ( DeviceEnumerator < 0 )
    {
      if ( v51 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
      if ( v31 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
      if ( v32 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      goto LABEL_66;
    }
    v11 = v51;
    if ( v51 != v31 )
    {
      v12 = v51;
      v11 = 0;
      v51 = 0;
      if ( v31 )
      {
        (**(void (__fastcall ***)(__int64, GUID *, __int64 *))v31)(
          v31,
          &GUID_1be09788_6894_4089_8586_9a2a6c265ac5,
          &v51);
        v11 = v51;
      }
      if ( v12 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
        v11 = v51;
      }
    }
    if ( !v11 )
    {
      DeviceEnumerator = -2147467262;
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v51);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
      goto LABEL_107;
    }
    DeviceEnumerator = (*(__int64 (__fastcall **)(__int64, BOOL *))(*(_QWORD *)v11 + 24LL))(v11, &bIgnoreCase);
    if ( DeviceEnumerator < 0
      || (DeviceEnumerator = (*(__int64 (__fastcall **)(__int64, LPCWCH *))(*(_QWORD *)v31 + 40LL))(v31, &lpString1),
          DeviceEnumerator < 0) )
    {
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v51);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
      goto LABEL_66;
    }
    v43 = 0;
    if ( bIgnoreCase )
    {
      v13 = 0;
      if ( bIgnoreCase )
      {
        v13 = 2;
        if ( lpString2 && CompareStringOrdinal(lpString1, -1, lpString2, -1, bIgnoreCase) == 2 )
          v13 = -2147483646;
        if ( v37 && CompareStringOrdinal(lpString1, -1, v37, -1, 1) == 2 )
          goto LABEL_85;
      }
    }
    else
    {
      v13 = 4;
      if ( v34 && CompareStringOrdinal(lpString1, -1, v34, -1, 1) == 2 )
        v13 = -2147483644;
      if ( v36 && CompareStringOrdinal(lpString1, -1, v36, -1, 1) == 2 )
LABEL_85:
        v13 |= 0x40000000u;
    }
    DeviceEnumerator = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v31 + 32LL))(v31, 0, &v32);
    if ( DeviceEnumerator >= 0 )
    {
      *(_OWORD *)pvar = 0;
      v46 = 0;
      DeviceEnumerator = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v32 + 40LL))(
                           v32,
                           PKEY_MMDEVAPI_ActiveTime,
                           pvar);
      if ( DeviceEnumerator >= 0 && LOWORD(pvar[0]) == 21 )
        v43 = pvar[1];
      PropVariantClear(pvar);
    }
    v14 = lpString1;
    v15 = v2;
    v16 = *((_DWORD *)a1 + 2);
    if ( v16 )
    {
      while ( 1 )
      {
        v17 = v15 + 12;
        if ( !lstrcmpiW((LPCWSTR)(v15 + 12), v14) )
          break;
        v18 = -1;
        do
          ++v18;
        while ( *(_WORD *)(v17 + 2 * v18) );
        v15 = (v17 + 2 * v18 + 9) & 0xFFFFFFFFFFFFFFF8uLL;
        if ( !--v16 )
          goto LABEL_47;
      }
    }
    else
    {
LABEL_47:
      v19 = -1;
      do
        ++v19;
      while ( v14[v19] );
      v20 = ((v15 + 2 * v19 + 21) & 0xFFFFFFFFFFFFFFF8uLL) - (_QWORD)a1;
      if ( v20 >= 0x40000 )
        goto LABEL_35;
      *(_QWORD *)v15 = 0;
      *(_DWORD *)(v15 + 8) = 0;
      v21 = (WCHAR *)(v15 + 12);
      v22 = (((v15 + 2 * v19 + 21) & 0xFFFFFFFFFFFFFFF8uLL) - (v15 + 12)) >> 1;
      if ( v22 )
      {
        if ( v22 > 0x7FFFFFFF )
        {
          *v21 = 0;
        }
        else
        {
          v23 = 2147483646;
          do
          {
            if ( !v23 )
              break;
            v24 = *v14;
            if ( !*v14 )
              break;
            ++v14;
            *v21++ = v24;
            --v23;
            --v22;
          }
          while ( v22 );
          v25 = v21 - 1;
          if ( v22 )
            v25 = v21;
          *v25 = 0;
        }
      }
      ++*((_DWORD *)a1 + 2);
      *(_DWORD *)a1 = v20;
    }
    if ( v15 )
    {
      *(_DWORD *)(v15 + 8) &= ~1u;
      *(_DWORD *)(v15 + 8) |= v13;
      *(_QWORD *)v15 = v43;
    }
LABEL_35:
    if ( lpString1 )
    {
      CoTaskMemFree((LPVOID)lpString1);
      lpString1 = 0;
    }
    if ( v51 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
    if ( v31 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
    if ( v32 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v10 = (unsigned int)(v50 + 1);
    v2 = v44;
  }
  if ( v34 )
  {
    CoTaskMemFree((LPVOID)v34);
    v34 = 0;
  }
  if ( lpString2 )
  {
    CoTaskMemFree((LPVOID)lpString2);
    lpString2 = 0;
  }
  if ( v36 )
  {
    CoTaskMemFree((LPVOID)v36);
    v36 = 0;
  }
  v29 = (WCHAR *)v37;
  if ( v37 )
  {
LABEL_116:
    CoTaskMemFree(v29);
    v37 = 0;
  }
LABEL_66:
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  if ( v41 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  if ( v42 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  if ( v33 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
  return (unsigned int)DeviceEnumerator;
}

```

## disassembly

```asm
0x18000c810  push    rbp
0x18000c812  push    rbx
0x18000c813  push    rsi
0x18000c814  push    rdi
0x18000c815  push    r12
0x18000c817  push    r13
0x18000c819  push    r14
0x18000c81b  push    r15
0x18000c81d  lea     rbp, [rsp-1Fh]
0x18000c822  sub     rsp, 0D8h
0x18000c829  mov     r13, rcx
0x18000c82c  xor     esi, esi
0x18000c82e  mov     [rbp+57h+arg_0], esi
0x18000c831  mov     [rbp+57h+var_C8], rsi
0x18000c835  mov     [rbp+57h+var_A0], rsi
0x18000c839  mov     [rbp+57h+var_50], rsi
0x18000c83d  mov     [rbp+57h+var_80], rsi
0x18000c841  mov     [rbp+57h+var_88], rsi
0x18000c845  mov     [rbp+57h+var_90], rsi
0x18000c849  mov     [rbp+57h+var_98], rsi
0x18000c84d  mov     [rsp+110h+lpString1], rsi
0x18000c852  mov     [rbp+57h+var_C0], rsi
0x18000c856  mov     [rbp+57h+lpString2], rsi
0x18000c85a  mov     [rbp+57h+var_B0], rsi
0x18000c85e  mov     [rbp+57h+var_A8], rsi
0x18000c862  lea     rdi, [rcx+13h]
0x18000c866  and     rdi, 0FFFFFFFFFFFFFFF8h
0x18000c86a  mov     [rbp+57h+var_70], rdi
0x18000c86e  mov     rcx, rdi
0x18000c871  mov     eax, [r13+8]
0x18000c875  test    eax, eax
0x18000c877  jnz     loc_18000CE53
0x18000c87d  lea     rcx, [rbp+57h+var_C8]
0x18000c881  call    cs:__imp_MMDeviceGetDeviceEnumerator
0x18000c887  mov     r15d, eax
0x18000c88a  test    eax, eax
0x18000c88c  js      loc_18000CCC1
0x18000c892  mov     rcx, [rbp+57h+var_C8]
0x18000c896  mov     rax, [rcx]
0x18000c899  lea     r9, [rbp+57h+var_A0]
0x18000c89d  mov     edx, 2
0x18000c8a2  mov     r8d, 1
0x18000c8a8  mov     rax, [rax+18h]
0x18000c8ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8b1  mov     r15d, eax
0x18000c8b4  test    eax, eax
0x18000c8b6  js      loc_18000CCC1
0x18000c8bc  mov     rcx, [rbp+57h+var_A0]
0x18000c8c0  mov     rax, [rcx]
0x18000c8c3  lea     rdx, [rbp+57h+arg_0]
0x18000c8c7  mov     rax, [rax+18h]
0x18000c8cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8d0  mov     r15d, eax
0x18000c8d3  test    eax, eax
0x18000c8d5  js      loc_18000CF3E
0x18000c8db  mov     rcx, [rbp+57h+var_C8]
0x18000c8df  mov     rax, [rcx]
0x18000c8e2  lea     r9, [rbp+57h+var_80]
0x18000c8e6  xor     r8d, r8d
0x18000c8e9  xor     edx, edx
0x18000c8eb  mov     rax, [rax+20h]
0x18000c8ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c8f4  mov     r15d, eax
0x18000c8f7  test    eax, eax
0x18000c8f9  js      loc_18000CE43
0x18000c8ff  mov     rcx, [rbp+57h+var_80]
0x18000c903  mov     rax, [rcx]
0x18000c906  lea     rdx, [rbp+57h+var_C0]
0x18000c90a  mov     rax, [rax+28h]
0x18000c90e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c913  mov     rcx, [rbp+57h+var_C8]
0x18000c917  mov     rax, [rcx]
0x18000c91a  lea     r9, [rbp+57h+var_88]
0x18000c91e  xor     r8d, r8d
0x18000c921  mov     edx, 1
0x18000c926  mov     rax, [rax+20h]
0x18000c92a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c92f  mov     r15d, eax
0x18000c932  test    eax, eax
0x18000c934  js      loc_18000CE86
0x18000c93a  mov     rcx, [rbp+57h+var_88]
0x18000c93e  mov     rax, [rcx]
0x18000c941  lea     rdx, [rbp+57h+lpString2]
0x18000c945  mov     rax, [rax+28h]
0x18000c949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c94e  mov     rcx, [rbp+57h+var_C8]
0x18000c952  mov     rax, [rcx]
0x18000c955  lea     r9, [rbp+57h+var_90]
0x18000c959  xor     edx, edx
0x18000c95b  mov     r8d, 2
0x18000c961  mov     rax, [rax+20h]
0x18000c965  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c96a  mov     r15d, eax
0x18000c96d  test    eax, eax
0x18000c96f  js      loc_18000CE96
0x18000c975  mov     rcx, [rbp+57h+var_90]
0x18000c979  mov     rax, [rcx]
0x18000c97c  lea     rdx, [rbp+57h+var_B0]
0x18000c980  mov     rax, [rax+28h]
0x18000c984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c989  mov     rcx, [rbp+57h+var_C8]
0x18000c98d  mov     rax, [rcx]
0x18000c990  lea     r9, [rbp+57h+var_98]
0x18000c994  mov     edx, 1
0x18000c999  mov     r8d, 2
0x18000c99f  mov     rax, [rax+20h]
0x18000c9a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9a8  mov     r15d, eax
0x18000c9ab  test    eax, eax
0x18000c9ad  js      loc_18000CEA6
0x18000c9b3  mov     rcx, [rbp+57h+var_98]
0x18000c9b7  mov     rax, [rcx]
0x18000c9ba  lea     rdx, [rbp+57h+var_A8]
0x18000c9be  mov     rax, [rax+28h]
0x18000c9c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9c7  mov     r15d, esi
0x18000c9ca  mov     edx, esi
0x18000c9cc  mov     ebx, 80000002h
0x18000c9d1  mov     [rbp+57h+arg_10], edx
0x18000c9d4  cmp     edx, [rbp+57h+arg_0]
0x18000c9d7  jnb     loc_18000CFA8
0x18000c9dd  mov     [rbp+57h+var_D0], rsi
0x18000c9e1  mov     [rsp+110h+var_D8], rsi
0x18000c9e6  mov     [rbp+57h+arg_18], rsi
0x18000c9ea  mov     [rbp+57h+arg_8], esi
0x18000c9ed  mov     rcx, [rbp+57h+var_A0]
0x18000c9f1  mov     rax, [rcx]
0x18000c9f4  lea     r8, [rsp+110h+var_D8]
0x18000c9f9  mov     rax, [rax+20h]
0x18000c9fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca02  mov     r15d, eax
0x18000ca05  test    eax, eax
0x18000ca07  js      loc_18000CC7E
0x18000ca0d  mov     r9, [rsp+110h+var_D8]
0x18000ca12  mov     rcx, [rbp+57h+arg_18]
0x18000ca16  cmp     rcx, r9
0x18000ca19  jz      short loc_18000CA55
0x18000ca1b  mov     rbx, rcx
0x18000ca1e  mov     rcx, rsi
0x18000ca21  mov     [rbp+57h+arg_18], rcx
0x18000ca25  test    r9, r9
0x18000ca28  jz      short loc_18000CA47
0x18000ca2a  mov     rax, [r9]
0x18000ca2d  lea     r8, [rbp+57h+arg_18]
0x18000ca31  lea     rdx, _GUID_1be09788_6894_4089_8586_9a2a6c265ac5
0x18000ca38  mov     rcx, r9
0x18000ca3b  mov     rax, [rax]
0x18000ca3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca43  mov     rcx, [rbp+57h+arg_18]
0x18000ca47  test    rbx, rbx
0x18000ca4a  jnz     loc_18000CEB6
0x18000ca50  mov     ebx, 80000002h
0x18000ca55  test    rcx, rcx
0x18000ca58  jz      loc_18000CF1A
0x18000ca5e  mov     rax, [rcx]
0x18000ca61  lea     rdx, [rbp+57h+arg_8]
0x18000ca65  mov     rax, [rax+18h]
0x18000ca69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca6e  mov     r15d, eax
0x18000ca71  test    eax, eax
0x18000ca73  js      loc_18000CEF7
0x18000ca79  mov     rcx, [rsp+110h+var_D8]
0x18000ca7e  mov     rax, [rcx]
0x18000ca81  lea     rdx, [rsp+110h+lpString1]
0x18000ca86  mov     rax, [rax+28h]
0x18000ca8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ca8f  mov     r15d, eax
0x18000ca92  test    eax, eax
0x18000ca94  js      loc_18000CEF7
0x18000ca9a  mov     [rbp+57h+var_78], rsi
0x18000ca9e  mov     eax, [rbp+57h+arg_8]
0x18000caa1  test    eax, eax
0x18000caa3  jz      loc_18000CDDE
0x18000caa9  mov     r12d, esi
0x18000caac  cmp     eax, 1
0x18000caaf  jnz     short loc_18000CAEB
0x18000cab1  mov     r12d, 2
0x18000cab7  mov     r8, [rbp+57h+lpString2]; lpString2
0x18000cabb  test    r8, r8
0x18000cabe  jz      short loc_18000CADE
0x18000cac0  mov     [rsp+110h+bIgnoreCase], eax; bIgnoreCase
0x18000cac4  mov     edx, 0FFFFFFFFh; cchCount1
0x18000cac9  mov     r9d, edx; cchCount2
0x18000cacc  mov     rcx, [rsp+110h+lpString1]; lpString1
0x18000cad1  call    cs:__imp_CompareStringOrdinal
0x18000cad7  cmp     eax, r12d
0x18000cada  cmovz   r12d, ebx
0x18000cade  mov     r8, [rbp+57h+var_A8]; lpString2
0x18000cae2  test    r8, r8
0x18000cae5  jnz     loc_18000CDB0
0x18000caeb  mov     rcx, [rsp+110h+var_D8]
0x18000caf0  mov     rax, [rcx]
0x18000caf3  lea     r8, [rbp+57h+var_D0]
0x18000caf7  xor     edx, edx
0x18000caf9  mov     rax, [rax+20h]
0x18000cafd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb02  mov     r15d, eax
0x18000cb05  test    eax, eax
0x18000cb07  jns     loc_18000CD63
0x18000cb0d  mov     rbx, [rsp+110h+lpString1]
0x18000cb12  mov     r14, rdi
0x18000cb15  mov     esi, [r13+8]
0x18000cb19  test    esi, esi
0x18000cb1b  jz      loc_18000CBE3
0x18000cb21  nop     dword ptr [rax+00h]
0x18000cb25  nop     word ptr [rax+rax+00000000h]
0x18000cb30  lea     rdi, [r14+0Ch]
0x18000cb34  mov     rdx, rbx; lpString2
0x18000cb37  mov     rcx, rdi; lpString1
0x18000cb3a  call    cs:__imp_lstrcmpiW
0x18000cb40  test    eax, eax
0x18000cb42  jnz     short loc_18000CBB9
0x18000cb44  test    r14, r14
0x18000cb47  jnz     loc_18000CEE2
0x18000cb4d  mov     rcx, [rsp+110h+lpString1]; pv
0x18000cb52  test    rcx, rcx
0x18000cb55  jz      loc_18000CD5C
0x18000cb5b  call    cs:__imp_CoTaskMemFree
0x18000cb61  xor     esi, esi
0x18000cb63  mov     [rsp+110h+lpString1], rsi
0x18000cb68  mov     rcx, [rbp+57h+arg_18]
0x18000cb6c  test    rcx, rcx
0x18000cb6f  jz      short loc_18000CB7E
0x18000cb71  mov     rax, [rcx]
0x18000cb74  mov     rax, [rax+10h]
0x18000cb78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb7d  nop
0x18000cb7e  mov     rcx, [rsp+110h+var_D8]
0x18000cb83  test    rcx, rcx
0x18000cb86  jz      short loc_18000CB95
0x18000cb88  mov     rax, [rcx]
0x18000cb8b  mov     rax, [rax+10h]
0x18000cb8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb94  nop
0x18000cb95  mov     rcx, [rbp+57h+var_D0]
0x18000cb99  test    rcx, rcx
0x18000cb9c  jz      short loc_18000CBAB
0x18000cb9e  mov     rax, [rcx]
0x18000cba1  mov     rax, [rax+10h]
0x18000cba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbaa  nop
0x18000cbab  mov     edx, [rbp+57h+arg_10]
0x18000cbae  inc     edx
0x18000cbb0  mov     rdi, [rbp+57h+var_70]
0x18000cbb4  jmp     loc_18000C9CC
0x18000cbb9  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000cbc0  lea     rax, [rax+1]
0x18000cbc4  cmp     word ptr [rdi+rax*2], 0
0x18000cbc9  jnz     short loc_18000CBC0
0x18000cbcb  lea     r14, ds:9[rax*2]
0x18000cbd3  add     r14, rdi
0x18000cbd6  and     r14, 0FFFFFFFFFFFFFFF8h
0x18000cbda  add     esi, 0FFFFFFFFh
0x18000cbdd  jnz     loc_18000CB30
0x18000cbe3  mov     rax, 0FFFFFFFFFFFFFFFFh
0x18000cbea  lea     rax, [rax+1]
0x18000cbee  cmp     word ptr [rbx+rax*2], 0
0x18000cbf3  jnz     short loc_18000CBEA
0x18000cbf5  lea     rdx, ds:15h[rax*2]
0x18000cbfd  add     rdx, r14
0x18000cc00  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18000cc04  mov     r9, rdx
0x18000cc07  sub     r9, r13
0x18000cc0a  cmp     r9, 40000h
0x18000cc11  jnb     loc_18000CB4D
0x18000cc17  xor     r10d, r10d
0x18000cc1a  mov     [r14], r10
0x18000cc1d  mov     [r14+8], r10d
0x18000cc21  lea     r8, [r14+0Ch]
0x18000cc25  sub     rdx, r8
0x18000cc28  shr     rdx, 1
0x18000cc2b  jz      short loc_18000CC71
0x18000cc2d  cmp     rdx, 7FFFFFFFh
0x18000cc34  ja      loc_18000CED9
0x18000cc3a  mov     ecx, 7FFFFFFEh
0x18000cc3f  nop
0x18000cc40  test    rcx, rcx
0x18000cc43  jz      short loc_18000CC62
0x18000cc45  movzx   eax, word ptr [rbx]
0x18000cc48  test    ax, ax
0x18000cc4b  jz      short loc_18000CC62
0x18000cc4d  add     rbx, 2
0x18000cc51  mov     [r8], ax
0x18000cc55  add     r8, 2
0x18000cc59  dec     rcx
0x18000cc5c  sub     rdx, 1
0x18000cc60  jnz     short loc_18000CC40
0x18000cc62  lea     rcx, [r8-2]
0x18000cc66  test    rdx, rdx
0x18000cc69  cmovnz  rcx, r8
0x18000cc6d  mov     [rcx], r10w
0x18000cc71  inc     dword ptr [r13+8]
0x18000cc75  mov     [r13+0], r9d
0x18000cc79  jmp     loc_18000CB44
0x18000cc7e  mov     rcx, [rbp+57h+arg_18]
0x18000cc82  test    rcx, rcx
0x18000cc85  jz      short loc_18000CC94
0x18000cc87  mov     rax, [rcx]
0x18000cc8a  mov     rax, [rax+10h]
0x18000cc8e  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
