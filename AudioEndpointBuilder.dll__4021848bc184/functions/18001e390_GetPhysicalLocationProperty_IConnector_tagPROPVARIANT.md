# GetPhysicalLocationProperty(IConnector *,tagPROPVARIANT *)

- ea: `0x18001e390`
- end: `0x18001e8e4`
- name: `?GetPhysicalLocationProperty@@YAJPEAUIConnector@@PEAUtagPROPVARIANT@@@Z`
- size: `1364`
- prototype: `__int64 __fastcall(struct IConnector *, PROPVARIANT *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18004a344`

## callees

- `0x180006b0c`
- `0x180010da8`
- `0x18001e390`
- `0x18003e920`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e49e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e49e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001e59c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001e65c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001e6b3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001e71c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001e75d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001e7a1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001e7fa`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001e59c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001e65c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001e6b3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001e71c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001e75d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001e7a1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001e7fa`

## string_xrefs

- `0x18001e646`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18001e69d`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18001e706`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18001e747`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18001e78b`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18001e7e4`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall GetPhysicalLocationProperty(struct IConnector *a1, PROPVARIANT *a2)
{
  __int64 v3; // rcx
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rbx
  __int64 (__fastcall *v7)(__int64, __int64, GUID *, __int64 *); // rdi
  __int64 v8; // rcx
  int v9; // ebx
  int v10; // eax
  unsigned int v11; // ebx
  _DWORD *v12; // rbx
  unsigned int v13; // edi
  int v14; // esi
  int v15; // r15d
  int v16; // r14d
  unsigned int v17; // eax
  int v19; // eax
  unsigned int v20; // r12d
  int v21; // [rsp+20h] [rbp-59h]
  __int64 v22; // [rsp+30h] [rbp-49h] BYREF
  __int64 v23; // [rsp+38h] [rbp-41h] BYREF
  PROPVARIANT *pvar; // [rsp+40h] [rbp-39h] BYREF
  _DWORD v25[10]; // [rsp+48h] [rbp-31h] BYREF
  PROPVARIANT **p_pvar; // [rsp+70h] [rbp-9h]
  char v27; // [rsp+78h] [rbp-1h]
  _DWORD v28[8]; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  pvar = a2;
  v25[0] = 0;
  v23 = 0;
  v22 = 0;
  memset(&v25[2], 0, 28);
  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  p_pvar = &pvar;
  v27 = 1;
  v3 = v23;
  v23 = 0;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = ((__int64 (__fastcall *)(struct IConnector *, GUID *, __int64 *))a1->lpVtbl->QueryInterface)(
         a1,
         &GUID_ae2de0e4_5bca_4f2d_aa46_5d13f8fdb3a9,
         &v23);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD5A,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v4,
      v21);
    PropVariantClear(pvar);
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    return v5;
  }
  else
  {
    v6 = v23;
    v7 = *(__int64 (__fastcall **)(__int64, __int64, GUID *, __int64 *))(*(_QWORD *)v23 + 104LL);
    v8 = v22;
    v22 = 0;
    if ( v8 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v9 = v7(v6, 1, &GUID_4509f757_2d46_4637_8e62_ce7db944f57b, &v22);
    if ( v9 < 0 )
    {
      PropVariantClear(pvar);
      if ( v22 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      if ( v23 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
      return (unsigned int)v9;
    }
    else
    {
      v10 = (*(__int64 (__fastcall **)(__int64, _DWORD *))(*(_QWORD *)v22 + 24LL))(v22, v25);
      v11 = v10;
      if ( v10 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD60,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
          (const char *)(unsigned int)v10,
          v21);
        PropVariantClear(pvar);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
        return v11;
      }
      else if ( v25[0] )
      {
        v12 = CoTaskMemAlloc(0x14u);
        if ( v12 )
        {
          *(_WORD *)pvar = 4113;
          *((_DWORD *)pvar + 2) = 20;
          pvar[2] = v12;
          *(_QWORD *)(v12 + 1) = 0;
          *(_QWORD *)(v12 + 3) = 0;
          *v12 = 129;
          v12[2] &= 0xFFFFFD37;
          v12[2] |= 0x130u;
          v12[4] = -1;
          v13 = 0;
          v14 = v25[7];
          v15 = v25[6];
          v16 = v25[5];
          while ( 1 )
          {
            if ( v13 >= v25[0] )
            {
              if ( v16 == 4 )
              {
                v12[2] &= ~0x20u;
                v12[2] |= 0x18u;
LABEL_14:
                v17 = v12[2];
              }
              else
              {
                switch ( v16 )
                {
                  case 1:
                  case 7:
                    v12[2] &= ~0x10u;
                    v12[2] |= 0x28u;
                    goto LABEL_14;
                  case 2:
                    v12[2] &= 0xFFFFFFE7;
                    v12[2] |= 0x20u;
                    goto LABEL_14;
                  case 3:
                    v12[2] &= 0xFFFFFFD7;
                    v12[2] |= 0x10u;
                    goto LABEL_14;
                  case 5:
                    v12[2] &= 0xFFFFFFC7;
                    goto LABEL_14;
                  case 6:
                    v12[2] &= 0xFFFFFFCF;
                    v12[2] |= 8u;
                    goto LABEL_14;
                  case 9:
                    v17 = v12[2] & 0xFFFFFFC3 | 0x24;
                    v12[2] = v17;
                    break;
                  case 12:
                    v17 = v12[2] & 0xFFFFFFC3 | 0x2C;
                    v12[2] = v17;
                    break;
                  default:
                    v12[2] &= ~8u;
                    v12[2] |= 0x30u;
                    goto LABEL_14;
                }
              }
              if ( v15 == 2 )
              {
                v17 |= 2u;
                v12[2] = v17;
              }
              if ( !v14 || v14 == 2 )
                v12[2] = v17 | 1;
              if ( v22 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
              if ( v23 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
              return 0;
            }
            memset(v28, 0, 28);
            v19 = (*(__int64 (__fastcall **)(__int64, _QWORD, _DWORD *))(*(_QWORD *)v22 + 32LL))(v22, v13, v28);
            v20 = v19;
            if ( v19 < 0 )
              break;
            if ( v13 )
            {
              if ( __PAIR64__(v15, v16) != *(_QWORD *)&v28[3] || v14 != v28[5] )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0xD87,
                  (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
                  (const char *)0x8007000ALL,
                  v21);
                PropVariantClear(pvar);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
                return 2147942410LL;
              }
            }
            else
            {
              v14 = _mm_cvtsi128_si32(_mm_srli_si128(*(__m128i *)&v28[3], 8));
              v15 = _mm_cvtsi128_si32(_mm_srli_si128(*(__m128i *)&v28[3], 4));
              v16 = _mm_cvtsi128_si32(*(__m128i *)&v28[3]);
            }
            ++v13;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD7F,
            (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
            (const char *)(unsigned int)v19,
            v21);
          PropVariantClear(pvar);
          if ( v22 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          if ( v23 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
          return v20;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD67,
            (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
            (const char *)0x8007000ELL,
            v21);
          PropVariantClear(pvar);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
          return 2147942414LL;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD62,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
          (const char *)0x80070490LL,
          v21);
        PropVariantClear(pvar);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
        return 2147943568LL;
      }
    }
  }
}

```

## disassembly

```asm
0x18001e390  mov     [rsp-8+arg_10], rbx
0x18001e395  mov     [rsp-8+arg_18], rsi
0x18001e39a  push    rbp
0x18001e39b  push    rdi
0x18001e39c  push    r12
0x18001e39e  push    r14
0x18001e3a0  push    r15
0x18001e3a2  lea     rbp, [rsp-37h]
0x18001e3a7  sub     rsp, 0B0h
0x18001e3ae  mov     rax, cs:__security_cookie
0x18001e3b5  xor     rax, rsp
0x18001e3b8  mov     [rbp+57h+var_30], rax
0x18001e3bc  mov     rbx, rcx
0x18001e3bf  mov     [rbp+57h+pvar], rdx
0x18001e3c3  xor     esi, esi
0x18001e3c5  mov     [rbp+57h+var_88], esi
0x18001e3c8  mov     [rbp+57h+var_98], rsi
0x18001e3cc  mov     [rbp+57h+var_A0], rsi
0x18001e3d0  xorps   xmm0, xmm0
0x18001e3d3  xor     eax, eax
0x18001e3d5  movups  [rbp+57h+var_80], xmm0
0x18001e3d9  movups  [rbp+57h+var_80+0Ch], xmm0
0x18001e3dd  xorps   xmm1, xmm1
0x18001e3e0  movups  xmmword ptr [rdx], xmm1
0x18001e3e3  mov     [rdx+10h], rax
0x18001e3e7  lea     rax, [rbp+57h+pvar]
0x18001e3eb  mov     [rbp+57h+var_60], rax
0x18001e3ef  mov     [rbp+57h+var_58], 1
0x18001e3f3  mov     rcx, [rbp+57h+var_98]
0x18001e3f7  mov     [rbp+57h+var_98], rsi
0x18001e3fb  test    rcx, rcx
0x18001e3fe  jz      short loc_18001E40D
0x18001e400  mov     rax, [rcx]
0x18001e403  mov     rax, [rax+10h]
0x18001e407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e40c  nop
0x18001e40d  mov     rax, [rbx]
0x18001e410  lea     r8, [rbp+57h+var_98]
0x18001e414  lea     rdx, _GUID_ae2de0e4_5bca_4f2d_aa46_5d13f8fdb3a9
0x18001e41b  mov     rcx, rbx
0x18001e41e  mov     rax, [rax]
0x18001e421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e426  mov     ebx, eax
0x18001e428  test    eax, eax
0x18001e42a  js      loc_18001E63F
0x18001e430  mov     rbx, [rbp+57h+var_98]
0x18001e434  mov     rax, [rbx]
0x18001e437  mov     rdi, [rax+68h]
0x18001e43b  mov     rcx, [rbp+57h+var_A0]
0x18001e43f  mov     [rbp+57h+var_A0], rsi
0x18001e443  test    rcx, rcx
0x18001e446  jnz     loc_18001E6EE
0x18001e44c  lea     r9, [rbp+57h+var_A0]
0x18001e450  lea     r8, _GUID_4509f757_2d46_4637_8e62_ce7db944f57b
0x18001e457  mov     edx, 1
0x18001e45c  mov     rcx, rbx
0x18001e45f  mov     rax, rdi
0x18001e462  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e467  mov     ebx, eax
0x18001e469  test    eax, eax
0x18001e46b  js      loc_18001E598
0x18001e471  mov     rcx, [rbp+57h+var_A0]
0x18001e475  mov     rax, [rcx]
0x18001e478  lea     rdx, [rbp+57h+var_88]
0x18001e47c  mov     rax, [rax+18h]
0x18001e480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e485  mov     ebx, eax
0x18001e487  test    eax, eax
0x18001e489  js      loc_18001E6FF
0x18001e48f  cmp     [rbp+57h+var_88], 0
0x18001e493  jz      loc_18001E73D
0x18001e499  mov     ecx, 14h; cb
0x18001e49e  call    cs:__imp_CoTaskMemAlloc
0x18001e4a4  mov     rbx, rax
0x18001e4a7  test    rax, rax
0x18001e4aa  jz      loc_18001E781
0x18001e4b0  mov     rax, [rbp+57h+pvar]
0x18001e4b4  mov     word ptr [rax], 1011h
0x18001e4b9  mov     rax, [rbp+57h+pvar]
0x18001e4bd  mov     dword ptr [rax+8], 14h
0x18001e4c4  mov     rax, [rbp+57h+pvar]
0x18001e4c8  mov     [rax+10h], rbx
0x18001e4cc  mov     [rbx+4], rsi
0x18001e4d0  mov     [rbx+0Ch], rsi
0x18001e4d4  mov     dword ptr [rbx], 81h
0x18001e4da  and     dword ptr [rbx+8], 0FFFFFD37h
0x18001e4e1  or      dword ptr [rbx+8], 130h
0x18001e4e8  mov     dword ptr [rbx+10h], 0FFFFFFFFh
0x18001e4ef  mov     edi, esi
0x18001e4f1  mov     esi, [rbp+57h+var_6C]
0x18001e4f4  mov     r15d, [rbp+57h+var_70]
0x18001e4f8  mov     r14d, dword ptr [rbp+57h+var_80+0Ch]
0x18001e4fc  cmp     edi, [rbp+57h+var_88]
0x18001e4ff  jb      loc_18001E5D3
0x18001e505  cmp     r14d, 4
0x18001e509  jz      loc_18001E632
0x18001e50f  dec     r14d; switch 14 cases
0x18001e512  cmp     r14d, 0Dh
0x18001e516  jbe     loc_18001E81E
0x18001e51c  and     dword ptr [rbx+8], 0FFFFFFF7h; jumptable 000000018001E832 default case, cases 4,8,10,11,13,14
0x18001e520  or      dword ptr [rbx+8], 30h
0x18001e524  mov     eax, [rbx+8]
0x18001e527  cmp     r15d, 2
0x18001e52b  jz      loc_18001E893
0x18001e531  test    esi, esi
0x18001e533  jz      loc_18001E89E
0x18001e539  cmp     esi, 2
0x18001e53c  jz      loc_18001E89E
0x18001e542  mov     rcx, [rbp+57h+var_A0]
0x18001e546  test    rcx, rcx
0x18001e549  jz      short loc_18001E558
0x18001e54b  mov     rax, [rcx]
0x18001e54e  mov     rax, [rax+10h]
0x18001e552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e557  nop
0x18001e558  mov     rcx, [rbp+57h+var_98]
0x18001e55c  test    rcx, rcx
0x18001e55f  jz      short loc_18001E56E
0x18001e561  mov     rax, [rcx]
0x18001e564  mov     rax, [rax+10h]
0x18001e568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e56d  nop
0x18001e56e  xor     eax, eax
0x18001e570  mov     rcx, [rbp+57h+var_30]
0x18001e574  xor     rcx, rsp; StackCookie
0x18001e577  call    __security_check_cookie
0x18001e57c  lea     r11, [rsp+0D0h+var_20]
0x18001e584  mov     rbx, [r11+40h]
0x18001e588  mov     rsi, [r11+48h]
0x18001e58c  mov     rsp, r11
0x18001e58f  pop     r15
0x18001e591  pop     r14
0x18001e593  pop     r12
0x18001e595  pop     rdi
0x18001e596  pop     rbp
0x18001e597  retn
0x18001e598  mov     rcx, [rbp+57h+pvar]; pvar
0x18001e59c  call    cs:__imp_PropVariantClear
0x18001e5a2  nop
0x18001e5a3  mov     rcx, [rbp+57h+var_A0]
0x18001e5a7  test    rcx, rcx
0x18001e5aa  jz      short loc_18001E5B9
0x18001e5ac  mov     rdx, [rcx]
0x18001e5af  mov     rax, [rdx+10h]
0x18001e5b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5b8  nop
0x18001e5b9  mov     rcx, [rbp+57h+var_98]
0x18001e5bd  test    rcx, rcx
0x18001e5c0  jz      short loc_18001E5CF
0x18001e5c2  mov     rax, [rcx]
0x18001e5c5  mov     rax, [rax+10h]
0x18001e5c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5ce  nop
0x18001e5cf  mov     eax, ebx
0x18001e5d1  jmp     short loc_18001E570
0x18001e5d3  xorps   xmm0, xmm0
0x18001e5d6  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18001e5da  movups  xmmword ptr [rbp+57h+var_50+0Ch], xmm0
0x18001e5de  mov     rcx, [rbp+57h+var_A0]
0x18001e5e2  mov     rax, [rcx]
0x18001e5e5  lea     r8, [rbp+57h+var_50]
0x18001e5e9  mov     edx, edi
0x18001e5eb  mov     rax, [rax+20h]
0x18001e5ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5f4  mov     r12d, eax
0x18001e5f7  test    eax, eax
0x18001e5f9  js      loc_18001E696
0x18001e5ff  test    edi, edi
0x18001e601  jnz     loc_18001E7C5
0x18001e607  movups  xmm2, xmmword ptr [rbp+57h+var_50+0Ch]
0x18001e60b  movdqa  xmm0, xmm2
0x18001e60f  psrldq  xmm0, 8
0x18001e614  movd    esi, xmm0
0x18001e618  movdqa  xmm1, xmm2
0x18001e61c  psrldq  xmm1, 4
0x18001e621  movd    r15d, xmm1
0x18001e626  movd    r14d, xmm2
0x18001e62b  inc     edi
0x18001e62d  jmp     loc_18001E4FC
0x18001e632  and     dword ptr [rbx+8], 0FFFFFFDFh
0x18001e636  or      dword ptr [rbx+8], 18h
0x18001e63a  jmp     loc_18001E524
0x18001e63f  mov     rcx, [rbp+5Fh]; this
0x18001e643  mov     r9d, ebx; char *
0x18001e646  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18001e64d  mov     edx, 0D5Ah; void *
0x18001e652  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e657  nop
0x18001e658  mov     rcx, [rbp+57h+pvar]; pvar
0x18001e65c  call    cs:__imp_PropVariantClear
0x18001e662  nop
0x18001e663  mov     rcx, [rbp+57h+var_A0]
0x18001e667  test    rcx, rcx
0x18001e66a  jz      short loc_18001E679
0x18001e66c  mov     rax, [rcx]
0x18001e66f  mov     rax, [rax+10h]
0x18001e673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e678  nop
0x18001e679  mov     rcx, [rbp+57h+var_98]
0x18001e67d  test    rcx, rcx
0x18001e680  jz      short loc_18001E68F
0x18001e682  mov     rax, [rcx]
0x18001e685  mov     rax, [rax+10h]
0x18001e689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e68e  nop
0x18001e68f  mov     eax, ebx
0x18001e691  jmp     loc_18001E570
0x18001e696  mov     rcx, [rbp+5Fh]; this
0x18001e69a  mov     r9d, r12d; char *
0x18001e69d  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18001e6a4  mov     edx, 0D7Fh; void *
0x18001e6a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e6ae  nop
0x18001e6af  mov     rcx, [rbp+57h+pvar]; pvar
0x18001e6b3  call    cs:__imp_PropVariantClear
0x18001e6b9  nop
0x18001e6ba  mov     rcx, [rbp+57h+var_A0]
0x18001e6be  test    rcx, rcx
0x18001e6c1  jz      short loc_18001E6D0
0x18001e6c3  mov     rax, [rcx]
0x18001e6c6  mov     rax, [rax+10h]
0x18001e6ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6cf  nop
0x18001e6d0  mov     rcx, [rbp+57h+var_98]
0x18001e6d4  test    rcx, rcx
0x18001e6d7  jz      short loc_18001E6E6
0x18001e6d9  mov     rax, [rcx]
0x18001e6dc  mov     rax, [rax+10h]
0x18001e6e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6e5  nop
0x18001e6e6  mov     eax, r12d
0x18001e6e9  jmp     loc_18001E570
0x18001e6ee  mov     rdx, [rcx]
0x18001e6f1  mov     rax, [rdx+10h]
0x18001e6f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6fa  jmp     loc_18001E44C
0x18001e6ff  mov     rcx, [rbp+5Fh]; this
0x18001e703  mov     r9d, ebx; char *
0x18001e706  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18001e70d  mov     edx, 0D60h; void *
0x18001e712  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e717  nop
0x18001e718  mov     rcx, [rbp+57h+pvar]; pvar
0x18001e71c  call    cs:__imp_PropVariantClear
0x18001e722  nop
0x18001e723  lea     rcx, [rbp+57h+var_A0]
0x18001e727  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001e72c  nop
0x18001e72d  lea     rcx, [rbp+57h+var_98]
0x18001e731  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001e736  mov     eax, ebx
0x18001e738  jmp     loc_18001E570
0x18001e73d  mov     rcx, [rbp+5Fh]; this
0x18001e741  mov     r9d, 80070490h; char *
0x18001e747  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18001e74e  mov     edx, 0D62h; void *
0x18001e753  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e758  nop
0x18001e759  mov     rcx, [rbp+57h+pvar]; pvar
0x18001e75d  call    cs:__imp_PropVariantClear
0x18001e763  nop
0x18001e764  lea     rcx, [rbp+57h+var_A0]
0x18001e768  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001e76d  nop
0x18001e76e  lea     rcx, [rbp+57h+var_98]
0x18001e772  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001e777  mov     eax, 80070490h
0x18001e77c  jmp     loc_18001E570
0x18001e781  mov     rcx, [rbp+5Fh]; this
0x18001e785  mov     r9d, 8007000Eh; char *
0x18001e78b  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18001e792  mov     edx, 0D67h; void *
0x18001e797  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e79c  nop
0x18001e79d  mov     rcx, [rbp+57h+pvar]; pvar
0x18001e7a1  call    cs:__imp_PropVariantClear
0x18001e7a7  nop
0x18001e7a8  lea     rcx, [rbp+57h+var_A0]
0x18001e7ac  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001e7b1  nop
0x18001e7b2  lea     rcx, [rbp+57h+var_98]
0x18001e7b6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18001e7bb  mov     eax, 8007000Eh
0x18001e7c0  jmp     loc_18001E570
0x18001e7c5  cmp     r14d, dword ptr [rbp+57h+var_50+0Ch]
0x18001e7c9  jnz     short loc_18001E7DA
0x18001e7cb  cmp     r15d, dword ptr [rbp+57h+var_50+10h]
0x18001e7cf  jnz     short loc_18001E7DA
0x18001e7d1  cmp     esi, [rbp+57h+var_3C]
0x18001e7d4  jz      loc_18001E62B
0x18001e7da  mov     rcx, [rbp+5Fh]; this
0x18001e7de  mov     r9d, 8007000Ah; char *
0x18001e7e4  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18001e7eb  mov     edx, 0D87h; void *
0x18001e7f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e7f5  nop
0x18001e7f6  mov     rcx, [rbp+57h+pvar]; pvar
0x18001e7fa  call    cs:__imp_PropVariantClear
0x18001e800  nop
0x18001e801  lea     rcx, [rbp+57h+var_A0]
  ... truncated ...
```
