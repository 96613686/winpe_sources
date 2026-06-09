# GetAllConnectedNetworkIdsEx

- ea: `0x180008be8`
- end: `0x18000937f`
- name: `GetAllConnectedNetworkIdsEx`
- size: `1943`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180008920`

## callees

- `0x180008be8`
- `0x18000e840`
- `0x18001c500`
- `0x18001d09c`
- `0x18001d8e0`
- `0x180020350`
- `0x180020444`
- `0x18002c87c`
- `0x1800320fc`
- `0x180032114`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180009321`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180009321`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008d2b`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180008d2b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180008ca2`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180008ca2`
- `OLEAUT32!__imp_VariantInit` at `0x180008fe4`
- `OLEAUT32!__imp_VariantInit` at `0x180008fe4`

## pseudocode

```c
__int64 __fastcall GetAllConnectedNetworkIdsEx(
        _QWORD *a1,
        unsigned int *a2,
        __int64 a3,
        _DWORD *a4,
        _DWORD *a5,
        _DWORD *a6)
{
  _DWORD *v6; // rsi
  _DWORD *v8; // rax
  unsigned int v10; // r14d
  HRESULT v11; // ebx
  PVOID *v12; // rcx
  unsigned int v13; // eax
  unsigned int v14; // r12d
  int v15; // eax
  PVOID *v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // r9
  int v19; // eax
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  unsigned int v23; // ebx
  __int64 v24; // rsi
  int v25; // eax
  int ppv; // [rsp+20h] [rbp-79h]
  int v28; // [rsp+28h] [rbp-71h]
  bool v29; // [rsp+30h] [rbp-69h]
  __int64 v30; // [rsp+38h] [rbp-61h] BYREF
  int v31; // [rsp+40h] [rbp-59h] BYREF
  __int64 v32; // [rsp+48h] [rbp-51h] BYREF
  LPVOID v33; // [rsp+50h] [rbp-49h] BYREF
  __int64 v34; // [rsp+58h] [rbp-41h] BYREF
  __int64 v35; // [rsp+60h] [rbp-39h]
  _QWORD *v36; // [rsp+68h] [rbp-31h]
  _DWORD *v37; // [rsp+70h] [rbp-29h]
  VARIANTARG pvarg; // [rsp+78h] [rbp-21h] BYREF
  __int128 Buf1; // [rsp+90h] [rbp-9h] BYREF

  v6 = a5;
  v8 = a6;
  v37 = a5;
  v35 = (__int64)a6;
  v36 = a1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_dc(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_a1a562b7ea50350859a26b1c78d36c50_Traceguids, *a2, 1);
    v8 = (_DWORD *)v35;
  }
  v10 = 0;
  v33 = 0;
  v32 = 0;
  v30 = 0;
  v31 = 0;
  Buf1 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( v8 )
    *v8 = 0;
  v11 = CoInitializeEx(0, 4u);
  if ( (int)(v11 + 0x80000000) >= 0 && v11 != -2147417850 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          11,
          &WPP_a1a562b7ea50350859a26b1c78d36c50_Traceguids,
          (unsigned int)v11);
        v12 = (PVOID *)WPP_GLOBAL_Control;
      }
      goto LABEL_125;
    }
    return (unsigned int)v11;
  }
  v29 = v11 >= 0;
  v13 = CoCreateInstance(&CLSID_NetworkListManager, 0, 0x17u, &IID_INetworkListManager, &v33);
  v11 = v13;
  if ( v13 || !v33 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_116;
    }
    v17 = 12;
    goto LABEL_113;
  }
  v13 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64 *))(*(_QWORD *)v33 + 56LL))(v33, 1, &v32);
  v11 = v13;
  if ( v13 || !v32 )
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_116;
    }
    v17 = 13;
LABEL_113:
    v18 = v13;
LABEL_114:
    WPP_SF_d(v12[2], v17, &WPP_a1a562b7ea50350859a26b1c78d36c50_Traceguids, v18);
    goto LABEL_115;
  }
  v14 = 0;
  v15 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v32 + 64LL))(v32, 1, &v30, &v31);
  if ( v15 >= 0 )
  {
    if ( !v15 )
    {
      do
      {
        if ( !v30 )
          break;
        ++v14;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
        v30 = 0;
      }
      while ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v32 + 64LL))(
                 v32,
                 1,
                 &v30,
                 &v31) );
    }
  }
  else
  {
    v16 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_30;
    }
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)(v11 + 14),
      &WPP_a1a562b7ea50350859a26b1c78d36c50_Traceguids,
      (unsigned int)v15);
  }
  v16 = (PVOID *)WPP_GLOBAL_Control;
LABEL_30:
  if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 4) != 0 && *((_BYTE *)v16 + 25) >= 5u )
    WPP_SF_d(v16[2], 15, &WPP_a1a562b7ea50350859a26b1c78d36c50_Traceguids, v14);
  if ( !v14 )
  {
    *a2 = 0;
    v11 = 0;
LABEL_115:
    v12 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_116;
  }
  if ( v14 > *a2 )
  {
    *a2 = v14;
    v11 = 234;
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
    {
      goto LABEL_116;
    }
    v17 = 16;
LABEL_41:
    v18 = (unsigned int)v11;
    goto LABEL_114;
  }
  v19 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v32 + 80LL))(v32);
  v11 = v19;
  if ( v19 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        17,
        &WPP_a1a562b7ea50350859a26b1c78d36c50_Traceguids,
        (unsigned int)v19);
    }
    goto LABEL_48;
  }
  if ( v19 )
  {
LABEL_48:
    *a2 = 0;
    goto LABEL_115;
  }
  while ( 1 )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, int *))(*(_QWORD *)v32 + 64LL))(v32, 1, &v30, &v31);
    if ( v11 )
    {
      if ( v11 == 1 )
      {
        *a2 = v10;
        v11 = 0;
      }
      goto LABEL_115;
    }
    if ( !v30 )
      goto LABEL_118;
    if ( v10 >= v14 )
      break;
    v11 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v30 + 88LL))(v30, &Buf1);
    if ( v11 >= 0 )
      goto LABEL_57;
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        &WPP_a1a562b7ea50350859a26b1c78d36c50_Traceguids,
        (unsigned int)v11);
LABEL_57:
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( a4 || v6 )
    {
      v34 = 0;
      memset(&pvarg, 0, sizeof(pvarg));
      v20 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v30)(v30, &IID_IPropertyBag, &v34);
      v11 = v20;
      if ( v20 < 0 )
      {
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v17 = 20;
          goto LABEL_41;
        }
        goto LABEL_116;
      }
      if ( v20 )
        goto LABEL_115;
      VariantInit(&pvarg);
      v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, VARIANTARG *, _QWORD))(*(_QWORD *)v34 + 24LL))(
              v34,
              L"NA_NetworkClass",
              &pvarg,
              0);
      if ( v11 < 0
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          21,
          &WPP_a1a562b7ea50350859a26b1c78d36c50_Traceguids,
          (unsigned int)v11);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v34 + 16LL))(v34);
      if ( v11 )
        goto LABEL_115;
      if ( pvarg.lVal == 1 )
        *v6 = 1;
      if ( pvarg.lVal == 3 )
        *a4 = 1;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        LOBYTE(v21) = *v6 != 0;
        LOBYTE(v28) = v21;
        LOBYTE(ppv) = *a4 != 0;
        WPP_SF__guid_cc(*((_QWORD *)WPP_GLOBAL_Control + 2), v21, v22, &Buf1, ppv, v28);
      }
    }
    else if ( v11 )
    {
      goto LABEL_116;
    }
    if ( v35 )
    {
      v11 = IsNetworkReachableOverMbb(v30, v35);
      if ( v11 < 0 )
      {
        v12 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v17 = 23;
          goto LABEL_41;
        }
        goto LABEL_116;
      }
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
      {
        WPP_SF_c(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, &WPP_a1a562b7ea50350859a26b1c78d36c50_Traceguids);
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v23 = 0;
    v30 = 0;
    if ( v10 )
    {
      while ( 1 )
      {
        v24 = v23;
        v25 = memcmp_0(&Buf1, (const void *)(*v36 + 16LL * v23++), 0x10u);
        if ( v25 > 0 )
          break;
        if ( v23 >= v10 )
          goto LABEL_89;
      }
      memmove_0((void *)(*v36 + 16LL * v23), (const void *)(*v36 + 16 * v24), v10 - (unsigned int)v24);
      v23 = v24;
LABEL_89:
      v6 = v37;
    }
    ++v10;
    *(_OWORD *)(*v36 + 16LL * v23) = Buf1;
  }
  v12 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_a1a562b7ea50350859a26b1c78d36c50_Traceguids);
    goto LABEL_115;
  }
LABEL_116:
  if ( v30 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    v30 = 0;
LABEL_118:
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v32 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    v32 = 0;
  }
  if ( v33 )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v33 + 16LL))(v33);
    v12 = (PVOID *)WPP_GLOBAL_Control;
    v33 = 0;
  }
  if ( v29 )
  {
    CoUninitialize();
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_125:
  if ( v12 != &WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 4) != 0 && *((_BYTE *)v12 + 25) >= 6u )
    WPP_SF_d(v12[2], 25, &WPP_a1a562b7ea50350859a26b1c78d36c50_Traceguids, (unsigned int)v11);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180008be8  push    rbp
0x180008bea  push    rbx
0x180008beb  push    rsi
0x180008bec  push    r12
0x180008bee  push    r13
0x180008bf0  push    r14
0x180008bf2  push    r15
0x180008bf4  lea     rbp, [rsp-17h]
0x180008bf9  sub     rsp, 0B0h
0x180008c00  mov     rax, cs:__security_cookie
0x180008c07  xor     rax, rsp
0x180008c0a  mov     [rbp+47h+var_40], rax
0x180008c0e  mov     rsi, [rbp+47h+arg_20]
0x180008c12  mov     r13, r9
0x180008c15  mov     rax, [rbp+47h+arg_28]
0x180008c19  mov     r15, rdx
0x180008c1c  mov     [rbp+47h+var_70], rsi
0x180008c20  mov     [rbp+47h+var_80], rax
0x180008c24  mov     [rbp+47h+var_78], rcx
0x180008c28  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c2f  lea     r12, WPP_GLOBAL_Control
0x180008c36  cmp     rcx, r12
0x180008c39  jz      short loc_180008C68
0x180008c3b  test    byte ptr [rcx+1Ch], 4
0x180008c3f  jz      short loc_180008C68
0x180008c41  cmp     byte ptr [rcx+19h], 6
0x180008c45  jb      short loc_180008C68
0x180008c47  mov     r9d, [r15]
0x180008c4a  lea     r8, WPP_a1a562b7ea50350859a26b1c78d36c50_Traceguids
0x180008c51  mov     rcx, [rcx+10h]
0x180008c55  mov     edx, 0Ah
0x180008c5a  mov     byte ptr [rsp+0E0h+ppv], 1
0x180008c5f  call    WPP_SF_dc
0x180008c64  mov     rax, [rbp+47h+var_80]
0x180008c68  xor     r14d, r14d
0x180008c6b  xorps   xmm0, xmm0
0x180008c6e  mov     [rbp+47h+var_90], r14
0x180008c72  mov     [rbp+47h+var_98], r14
0x180008c76  mov     [rbp+47h+var_A8], r14
0x180008c7a  mov     [rbp+47h+var_A0], r14d
0x180008c7e  movups  [rbp+47h+Buf1], xmm0
0x180008c82  test    r13, r13
0x180008c85  jz      short loc_180008C8B
0x180008c87  mov     [r13+0], r14d
0x180008c8b  test    rsi, rsi
0x180008c8e  jz      short loc_180008C93
0x180008c90  mov     [rsi], r14d
0x180008c93  test    rax, rax
0x180008c96  jz      short loc_180008C9B
0x180008c98  mov     [rax], r14d
0x180008c9b  mov     edx, 4; dwCoInit
0x180008ca0  xor     ecx, ecx; pvReserved
0x180008ca2  call    cs:__imp_CoInitializeEx
0x180008ca8  mov     ecx, 80000000h
0x180008cad  mov     ebx, eax
0x180008caf  add     eax, ecx
0x180008cb1  test    ecx, eax
0x180008cb3  jnz     short loc_180008D05
0x180008cb5  cmp     ebx, 80010106h
0x180008cbb  jz      short loc_180008D05
0x180008cbd  mov     rcx, cs:WPP_GLOBAL_Control
0x180008cc4  cmp     rcx, r12
0x180008cc7  jz      loc_18000935E
0x180008ccd  test    byte ptr [rcx+1Ch], 4
0x180008cd1  jz      loc_180009335
0x180008cd7  cmp     byte ptr [rcx+19h], 2
0x180008cdb  jb      loc_180009335
0x180008ce1  mov     rcx, [rcx+10h]
0x180008ce5  lea     r8, WPP_a1a562b7ea50350859a26b1c78d36c50_Traceguids
0x180008cec  mov     edx, 0Bh
0x180008cf1  mov     r9d, ebx
0x180008cf4  call    WPP_SF_d
0x180008cf9  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d00  jmp     loc_180009335
0x180008d05  xor     edx, edx; pUnkOuter
0x180008d07  shr     ebx, 1Fh
0x180008d0a  lea     rax, [rbp+47h+var_90]
0x180008d0e  xor     bl, 1
0x180008d11  lea     r9, IID_INetworkListManager; riid
0x180008d18  mov     [rbp+47h+var_B0], bl
0x180008d1b  lea     rcx, CLSID_NetworkListManager; rclsid
0x180008d22  mov     [rsp+0E0h+ppv], rax; ppv
0x180008d27  lea     r8d, [rdx+17h]; dwClsContext
0x180008d2b  call    cs:__imp_CoCreateInstance
0x180008d31  mov     ebx, eax
0x180008d33  test    eax, eax
0x180008d35  jnz     loc_18000926F
0x180008d3b  mov     r9, [rbp+47h+var_90]
0x180008d3f  test    r9, r9
0x180008d42  jz      loc_18000926F
0x180008d48  mov     rax, [r9]
0x180008d4b  lea     r8, [rbp+47h+var_98]
0x180008d4f  lea     edx, [rbx+1]
0x180008d52  mov     rcx, r9
0x180008d55  mov     rax, [rax+38h]
0x180008d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d5e  mov     ebx, eax
0x180008d60  test    eax, eax
0x180008d62  jnz     loc_180009250
0x180008d68  mov     r10, [rbp+47h+var_98]
0x180008d6c  test    r10, r10
0x180008d6f  jz      loc_180009250
0x180008d75  mov     rax, [r10]
0x180008d78  lea     r9, [rbp+47h+var_A0]
0x180008d7c  lea     r8, [rbp+47h+var_A8]
0x180008d80  mov     rcx, r10
0x180008d83  lea     edx, [rbx+1]
0x180008d86  mov     r12d, r14d
0x180008d89  mov     rax, [rax+40h]
0x180008d8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d92  test    eax, eax
0x180008d94  jns     short loc_180008DCD
0x180008d96  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d9d  lea     rdx, WPP_GLOBAL_Control
0x180008da4  cmp     rcx, rdx
0x180008da7  jz      short loc_180008E16
0x180008da9  test    byte ptr [rcx+1Ch], 4
0x180008dad  jz      short loc_180008E16
0x180008daf  cmp     byte ptr [rcx+19h], 2
0x180008db3  jb      short loc_180008E16
0x180008db5  mov     rcx, [rcx+10h]
0x180008db9  lea     edx, [rbx+0Eh]
0x180008dbc  mov     r9d, eax
0x180008dbf  lea     r8, WPP_a1a562b7ea50350859a26b1c78d36c50_Traceguids
0x180008dc6  call    WPP_SF_d
0x180008dcb  jmp     short loc_180008E0F
0x180008dcd  jnz     short loc_180008E0F
0x180008dcf  mov     r8, [rbp+47h+var_A8]
0x180008dd3  test    r8, r8
0x180008dd6  jz      short loc_180008E0F
0x180008dd8  mov     rax, [r8]
0x180008ddb  mov     rcx, r8
0x180008dde  inc     r12d
0x180008de1  mov     rax, [rax+10h]
0x180008de5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dea  mov     rcx, [rbp+47h+var_98]
0x180008dee  lea     r9, [rbp+47h+var_A0]
0x180008df2  mov     [rbp+47h+var_A8], r14
0x180008df6  lea     r8, [rbp+47h+var_A8]
0x180008dfa  mov     edx, 1
0x180008dff  mov     rax, [rcx]
0x180008e02  mov     rax, [rax+40h]
0x180008e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e0b  test    eax, eax
0x180008e0d  jz      short loc_180008DCF
0x180008e0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e16  lea     rax, WPP_GLOBAL_Control
0x180008e1d  cmp     rcx, rax
0x180008e20  jz      short loc_180008E4D
0x180008e22  test    byte ptr [rcx+1Ch], 4
0x180008e26  jz      short loc_180008E4D
0x180008e28  cmp     byte ptr [rcx+19h], 5
0x180008e2c  jb      short loc_180008E4D
0x180008e2e  mov     rcx, [rcx+10h]
0x180008e32  lea     r8, WPP_a1a562b7ea50350859a26b1c78d36c50_Traceguids
0x180008e39  mov     edx, 0Fh
0x180008e3e  mov     r9d, r12d
0x180008e41  call    WPP_SF_d
0x180008e46  lea     rax, WPP_GLOBAL_Control
0x180008e4d  test    r12d, r12d
0x180008e50  jnz     short loc_180008E5D
0x180008e52  mov     [r15], r14d
0x180008e55  mov     ebx, r14d
0x180008e58  jmp     loc_18000929F
0x180008e5d  cmp     r12d, [r15]
0x180008e60  jbe     short loc_180008E9B
0x180008e62  mov     [r15], r12d
0x180008e65  mov     ebx, 0EAh
0x180008e6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008e71  cmp     rcx, rax
0x180008e74  jz      loc_1800092A6
0x180008e7a  test    byte ptr [rcx+1Ch], 4
0x180008e7e  jz      loc_1800092A6
0x180008e84  cmp     byte ptr [rcx+19h], 5
0x180008e88  jb      loc_1800092A6
0x180008e8e  mov     edx, 10h
0x180008e93  mov     r9d, ebx
0x180008e96  jmp     loc_18000928F
0x180008e9b  mov     rcx, [rbp+47h+var_98]
0x180008e9f  mov     rax, [rcx]
0x180008ea2  mov     rax, [rax+50h]
0x180008ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008eab  mov     ebx, eax
0x180008ead  test    eax, eax
0x180008eaf  jns     short loc_180008EEA
0x180008eb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180008eb8  lea     rdx, WPP_GLOBAL_Control
0x180008ebf  cmp     rcx, rdx
0x180008ec2  jz      short loc_180008EEC
0x180008ec4  test    byte ptr [rcx+1Ch], 4
0x180008ec8  jz      short loc_180008EEC
0x180008eca  cmp     byte ptr [rcx+19h], 2
0x180008ece  jb      short loc_180008EEC
0x180008ed0  mov     rcx, [rcx+10h]
0x180008ed4  lea     r8, WPP_a1a562b7ea50350859a26b1c78d36c50_Traceguids
0x180008edb  mov     edx, 11h
0x180008ee0  mov     r9d, eax
0x180008ee3  call    WPP_SF_d
0x180008ee8  jmp     short loc_180008EEC
0x180008eea  jz      short loc_180008EF4
0x180008eec  mov     [r15], r14d
0x180008eef  jmp     loc_18000929F
0x180008ef4  mov     rcx, [rbp+47h+var_98]
0x180008ef8  lea     r9, [rbp+47h+var_A0]
0x180008efc  lea     r8, [rbp+47h+var_A8]
0x180008f00  mov     edx, 1
0x180008f05  mov     rax, [rcx]
0x180008f08  mov     rax, [rax+40h]
0x180008f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f11  mov     ebx, eax
0x180008f13  test    eax, eax
0x180008f15  jnz     loc_180009244
0x180008f1b  mov     r8, [rbp+47h+var_A8]
0x180008f1f  test    r8, r8
0x180008f22  jz      loc_1800092C6
0x180008f28  cmp     r14d, r12d
0x180008f2b  jnb     loc_18000920A
0x180008f31  mov     rax, [r8]
0x180008f34  lea     rdx, [rbp+47h+Buf1]
0x180008f38  mov     rcx, r8
0x180008f3b  mov     rax, [rax+58h]
0x180008f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f44  mov     ebx, eax
0x180008f46  test    eax, eax
0x180008f48  jns     short loc_180008F81
0x180008f4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f51  lea     rax, WPP_GLOBAL_Control
0x180008f58  cmp     rcx, rax
0x180008f5b  jz      short loc_180008F88
0x180008f5d  test    byte ptr [rcx+1Ch], 4
0x180008f61  jz      short loc_180008F88
0x180008f63  cmp     byte ptr [rcx+19h], 2
0x180008f67  jb      short loc_180008F88
0x180008f69  mov     rcx, [rcx+10h]
0x180008f6d  lea     r8, WPP_a1a562b7ea50350859a26b1c78d36c50_Traceguids
0x180008f74  mov     edx, 13h
0x180008f79  mov     r9d, ebx
0x180008f7c  call    WPP_SF_d
0x180008f81  mov     rcx, cs:WPP_GLOBAL_Control
0x180008f88  test    r13, r13
0x180008f8b  jnz     short loc_180008F9F
0x180008f8d  test    rsi, rsi
0x180008f90  jnz     short loc_180008F9F
0x180008f92  test    ebx, ebx
0x180008f94  jz      loc_1800090B3
0x180008f9a  jmp     loc_1800092A6
0x180008f9f  mov     rcx, [rbp+47h+var_A8]
0x180008fa3  lea     r8, [rbp+47h+var_88]
0x180008fa7  xor     eax, eax
0x180008fa9  mov     [rbp+47h+var_88], 0
0x180008fb1  mov     qword ptr [rbp+47h+pvarg+10h], rax
0x180008fb5  lea     rdx, IID_IPropertyBag
0x180008fbc  xorps   xmm0, xmm0
0x180008fbf  movups  xmmword ptr [rbp+47h+pvarg], xmm0
0x180008fc3  mov     rax, [rcx]
0x180008fc6  mov     rax, [rax]
0x180008fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fce  mov     ebx, eax
0x180008fd0  test    eax, eax
0x180008fd2  js      loc_1800091D5
0x180008fd8  test    eax, eax
0x180008fda  jnz     loc_18000929F
0x180008fe0  lea     rcx, [rbp+47h+pvarg]; pvarg
0x180008fe4  call    cs:__imp_VariantInit
0x180008fea  mov     rcx, [rbp+47h+var_88]
0x180008fee  lea     r8, [rbp+47h+pvarg]
0x180008ff2  xor     r9d, r9d
0x180008ff5  lea     rdx, aNaNetworkclass; "NA_NetworkClass"
0x180008ffc  mov     rax, [rcx]
0x180008fff  mov     rax, [rax+18h]
0x180009003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009008  mov     ebx, eax
0x18000900a  test    eax, eax
0x18000900c  jns     short loc_180009045
0x18000900e  mov     rcx, cs:WPP_GLOBAL_Control
0x180009015  lea     rax, WPP_GLOBAL_Control
0x18000901c  cmp     rcx, rax
0x18000901f  jz      short loc_180009045
0x180009021  test    byte ptr [rcx+1Ch], 4
0x180009025  jz      short loc_180009045
0x180009027  cmp     byte ptr [rcx+19h], 2
0x18000902b  jb      short loc_180009045
0x18000902d  mov     rcx, [rcx+10h]
0x180009031  lea     r8, WPP_a1a562b7ea50350859a26b1c78d36c50_Traceguids
0x180009038  mov     edx, 15h
0x18000903d  mov     r9d, ebx
0x180009040  call    WPP_SF_d
0x180009045  mov     rcx, [rbp+47h+var_88]
0x180009049  mov     rax, [rcx]
0x18000904c  mov     rax, [rax+10h]
0x180009050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009055  test    ebx, ebx
0x180009057  jnz     loc_18000929F
0x18000905d  lea     eax, [rbx+1]
0x180009060  cmp     dword ptr [rbp+47h+pvarg+8], eax
0x180009063  jnz     short loc_180009067
0x180009065  mov     [rsi], eax
0x180009067  cmp     dword ptr [rbp+47h+pvarg+8], 3
0x18000906b  jnz     short loc_180009071
0x18000906d  mov     [r13+0], eax
  ... truncated ...
```
