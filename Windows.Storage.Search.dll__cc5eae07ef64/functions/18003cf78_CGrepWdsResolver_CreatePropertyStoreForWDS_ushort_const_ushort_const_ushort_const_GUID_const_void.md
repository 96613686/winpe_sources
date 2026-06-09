# CGrepWdsResolver::_CreatePropertyStoreForWDS(ushort const *,ushort const *,ushort const *,_GUID const &,void * *)

- ea: `0x18003cf78`
- end: `0x18003d276`
- name: `?_CreatePropertyStoreForWDS@CGrepWdsResolver@@AEAAJPEBG00AEBU_GUID@@PEAPEAX@Z`
- size: `766`
- prototype: `__int64 __fastcall(CGrepWdsResolver *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003cdc8`

## callees

- `0x18003cf78`
- `0x180068598`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003cffa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d07a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d0f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d14d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003cffa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d07a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d0f2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18003d14d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d19d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d1a8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d1b3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d1be`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d19d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d1a8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d1b3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d1be`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18003cfb8`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18003cfb8`

## pseudocode

```c
__int64 __fastcall CGrepWdsResolver::_CreatePropertyStoreForWDS(
        CGrepWdsResolver *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const struct _GUID *a5,
        void **a6)
{
  void **v9; // r12
  HRESULT v10; // ebx
  __int64 v11; // rdi
  __int64 v12; // rax
  __int64 v13; // rbx
  void *v14; // rax
  __int64 v15; // rax
  __int64 v16; // rbx
  void *v17; // rax
  __int64 v18; // rdi
  void *v19; // rax
  void *v20; // rax
  PROPVARIANT pvar[2]; // [rsp+20h] [rbp-59h] BYREF
  __int64 v23; // [rsp+30h] [rbp-49h]
  PROPVARIANT v24[2]; // [rsp+38h] [rbp-41h] BYREF
  __int64 v25; // [rsp+48h] [rbp-31h]
  PROPVARIANT v26[2]; // [rsp+50h] [rbp-29h] BYREF
  __int64 v27; // [rsp+60h] [rbp-19h]
  PROPVARIANT v28[2]; // [rsp+68h] [rbp-11h] BYREF
  __int64 v29; // [rsp+78h] [rbp-1h]
  void *ppv; // [rsp+D0h] [rbp+57h] BYREF

  v9 = a6;
  *a6 = 0;
  ppv = 0;
  v10 = PSCreateMemoryPropertyStore(&GUID_71604b0f_97b0_4764_8577_2f13e98a1422, &ppv);
  if ( v10 >= 0 )
  {
    *(_OWORD *)v28 = 0;
    v29 = 0;
    if ( a2 )
    {
      v11 = -1;
      v12 = -1;
      do
        ++v12;
      while ( a2[v12] );
      v13 = 2 * v12 + 2;
      v14 = CoTaskMemAlloc(v13);
      v28[1] = v14;
      if ( v14 )
      {
        memcpy_s(v14, v13, a2, v13);
        LOWORD(v28[0]) = 31;
        v10 = (*(__int64 (__fastcall **)(void *, const wchar_t *, PROPVARIANT *))(*(_QWORD *)ppv + 32LL))(
                ppv,
                L"MachineName",
                v28);
        if ( v10 < 0 )
        {
LABEL_23:
          PropVariantClear(v28);
          goto LABEL_24;
        }
        *(_OWORD *)v26 = 0;
        v27 = 0;
        if ( a3 )
        {
          v15 = -1;
          do
            ++v15;
          while ( a3[v15] );
          v16 = 2 * v15 + 2;
          v17 = CoTaskMemAlloc(v16);
          v26[1] = v17;
          if ( v17 )
          {
            memcpy_s(v17, v16, a3, v16);
            LOWORD(v26[0]) = 31;
            v10 = (*(__int64 (__fastcall **)(void *, const wchar_t *, PROPVARIANT *))(*(_QWORD *)ppv + 32LL))(
                    ppv,
                    L"Catalog",
                    v26);
            if ( v10 >= 0 && a4 )
            {
              *(_OWORD *)v24 = 0;
              v25 = 0;
              do
                ++v11;
              while ( a4[v11] );
              v18 = 2 * v11 + 2;
              v19 = CoTaskMemAlloc(v18);
              v24[1] = v19;
              if ( v19 )
              {
                memcpy_s(v19, v18, a4, v18);
                LOWORD(v24[0]) = 31;
                v10 = (*(__int64 (__fastcall **)(void *, const wchar_t *, PROPVARIANT *))(*(_QWORD *)ppv + 32LL))(
                        ppv,
                        L"Scope",
                        v24);
                if ( v10 >= 0 )
                {
                  pvar[0] = 0;
                  v23 = 0;
                  v20 = CoTaskMemAlloc(0x10u);
                  pvar[1] = v20;
                  if ( v20 )
                  {
                    memcpy_s(v20, 0x10u, L"Windows", 0x10u);
                    LOWORD(pvar[0]) = 31;
                    v10 = (*(__int64 (__fastcall **)(void *, const wchar_t *, PROPVARIANT *))(*(_QWORD *)ppv + 32LL))(
                            ppv,
                            L"Application",
                            pvar);
                    if ( v10 >= 0 )
                      v10 = (**(__int64 (__fastcall ***)(void *, GUID *, void **))ppv)(
                              ppv,
                              &GUID_71604b0f_97b0_4764_8577_2f13e98a1422,
                              v9);
                  }
                  else
                  {
                    *(_OWORD *)pvar = 0;
                    v23 = 0;
                    v10 = -2147024882;
                  }
                  PropVariantClear(pvar);
                }
              }
              else
              {
                *(_OWORD *)v24 = 0;
                v25 = 0;
                v10 = -2147024882;
              }
              PropVariantClear(v24);
            }
            goto LABEL_22;
          }
          v10 = -2147024882;
        }
        else
        {
          v10 = -2147024809;
        }
        *(_OWORD *)v26 = 0;
        v27 = 0;
LABEL_22:
        PropVariantClear(v26);
        goto LABEL_23;
      }
      v10 = -2147024882;
    }
    else
    {
      v10 = -2147024809;
    }
    *(_OWORD *)v28 = 0;
    v29 = 0;
    goto LABEL_23;
  }
LABEL_24:
  if ( ppv )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18003cf78  mov     [rsp-8+ppv], rcx
0x18003cf7d  push    rbp
0x18003cf7e  push    rbx
0x18003cf7f  push    rsi
0x18003cf80  push    rdi
0x18003cf81  push    r12
0x18003cf83  push    r13
0x18003cf85  push    r14
0x18003cf87  push    r15
0x18003cf89  lea     rbp, [rsp-0Fh]
0x18003cf8e  sub     rsp, 88h
0x18003cf95  mov     r15, r9
0x18003cf98  mov     r14, r8
0x18003cf9b  mov     rsi, rdx
0x18003cf9e  xor     r13d, r13d
0x18003cfa1  mov     r12, [rbp+47h+arg_28]
0x18003cfa5  mov     [r12], r13
0x18003cfa9  mov     [rbp+47h+ppv], r13
0x18003cfad  lea     rdx, [rbp+47h+ppv]; ppv
0x18003cfb1  lea     rcx, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422; riid
0x18003cfb8  call    cs:__imp_PSCreateMemoryPropertyStore
0x18003cfbe  mov     ebx, eax
0x18003cfc0  test    eax, eax
0x18003cfc2  js      loc_18003D1C5
0x18003cfc8  xorps   xmm0, xmm0
0x18003cfcb  xor     eax, eax
0x18003cfcd  movups  xmmword ptr [rbp+47h+var_58], xmm0
0x18003cfd1  mov     [rbp+47h+var_48], rax
0x18003cfd5  test    rsi, rsi
0x18003cfd8  jz      loc_18003D20E
0x18003cfde  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18003cfe2  mov     rax, rdi
0x18003cfe5  inc     rax
0x18003cfe8  cmp     [rsi+rax*2], r13w
0x18003cfed  jnz     short loc_18003CFE5
0x18003cfef  lea     rbx, ds:2[rax*2]
0x18003cff7  mov     rcx, rbx; cb
0x18003cffa  call    cs:__imp_CoTaskMemAlloc
0x18003d000  mov     [rbp+47h+var_58+8], rax
0x18003d004  test    rax, rax
0x18003d007  jz      loc_18003D215
0x18003d00d  mov     r9, rbx; SourceSize
0x18003d010  mov     r8, rsi; Source
0x18003d013  mov     rdx, rbx; DestinationSize
0x18003d016  mov     rcx, rax; Destination
0x18003d019  call    memcpy_s
0x18003d01e  mov     esi, 1Fh
0x18003d023  mov     word ptr [rbp+47h+var_58], si
0x18003d027  mov     rcx, [rbp+47h+ppv]
0x18003d02b  mov     rax, [rcx]
0x18003d02e  lea     r8, [rbp+47h+var_58]
0x18003d032  lea     rdx, aMachinename; "MachineName"
0x18003d039  mov     rax, [rax+20h]
0x18003d03d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d042  mov     ebx, eax
0x18003d044  test    eax, eax
0x18003d046  js      loc_18003D1BA
0x18003d04c  xorps   xmm0, xmm0
0x18003d04f  xor     eax, eax
0x18003d051  movups  xmmword ptr [rbp+47h+var_70], xmm0
0x18003d055  mov     [rbp+47h+var_60], rax
0x18003d059  test    r14, r14
0x18003d05c  jz      loc_18003D229
0x18003d062  mov     rax, rdi
0x18003d065  inc     rax
0x18003d068  cmp     [r14+rax*2], r13w
0x18003d06d  jnz     short loc_18003D065
0x18003d06f  lea     rbx, ds:2[rax*2]
0x18003d077  mov     rcx, rbx; cb
0x18003d07a  call    cs:__imp_CoTaskMemAlloc
0x18003d080  mov     [rbp+47h+var_70+8], rax
0x18003d084  test    rax, rax
0x18003d087  jz      loc_18003D230
0x18003d08d  mov     r9, rbx; SourceSize
0x18003d090  mov     r8, r14; Source
0x18003d093  mov     rdx, rbx; DestinationSize
0x18003d096  mov     rcx, rax; Destination
0x18003d099  call    memcpy_s
0x18003d09e  mov     word ptr [rbp+47h+var_70], si
0x18003d0a2  mov     rcx, [rbp+47h+ppv]
0x18003d0a6  mov     rax, [rcx]
0x18003d0a9  lea     r8, [rbp+47h+var_70]
0x18003d0ad  lea     rdx, aCatalog; "Catalog"
0x18003d0b4  mov     rax, [rax+20h]
0x18003d0b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d0bd  mov     ebx, eax
0x18003d0bf  test    eax, eax
0x18003d0c1  js      loc_18003D1AF
0x18003d0c7  test    r15, r15
0x18003d0ca  jz      loc_18003D1AF
0x18003d0d0  xorps   xmm0, xmm0
0x18003d0d3  xor     eax, eax
0x18003d0d5  movups  xmmword ptr [rbp+47h+var_88], xmm0
0x18003d0d9  mov     [rbp+47h+var_78], rax
0x18003d0dd  inc     rdi
0x18003d0e0  cmp     [r15+rdi*2], r13w
0x18003d0e5  jnz     short loc_18003D0DD
0x18003d0e7  lea     rdi, ds:2[rdi*2]
0x18003d0ef  mov     rcx, rdi; cb
0x18003d0f2  call    cs:__imp_CoTaskMemAlloc
0x18003d0f8  mov     [rbp+47h+var_88+8], rax
0x18003d0fc  test    rax, rax
0x18003d0ff  jz      loc_18003D25E
0x18003d105  mov     r9, rdi; SourceSize
0x18003d108  mov     r8, r15; Source
0x18003d10b  mov     rdx, rdi; DestinationSize
0x18003d10e  mov     rcx, rax; Destination
0x18003d111  call    memcpy_s
0x18003d116  mov     word ptr [rbp+47h+var_88], si
0x18003d11a  mov     rcx, [rbp+47h+ppv]
0x18003d11e  mov     rax, [rcx]
0x18003d121  lea     r8, [rbp+47h+var_88]
0x18003d125  lea     rdx, aScope_0; "Scope"
0x18003d12c  mov     rax, [rax+20h]
0x18003d130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d135  mov     ebx, eax
0x18003d137  test    eax, eax
0x18003d139  js      short loc_18003D1A4
0x18003d13b  xorps   xmm0, xmm0
0x18003d13e  xor     eax, eax
0x18003d140  movups  xmmword ptr [rbp+47h+pvar], xmm0
0x18003d144  mov     [rbp+47h+var_90], rax
0x18003d148  lea     ebx, [rax+10h]
0x18003d14b  mov     ecx, ebx; cb
0x18003d14d  call    cs:__imp_CoTaskMemAlloc
0x18003d153  mov     [rbp+47h+pvar+8], rax
0x18003d157  test    rax, rax
0x18003d15a  jz      loc_18003D247
0x18003d160  mov     r9d, ebx; SourceSize
0x18003d163  lea     r8, aWindows; "Windows"
0x18003d16a  mov     edx, ebx; DestinationSize
0x18003d16c  mov     rcx, rax; Destination
0x18003d16f  call    memcpy_s
0x18003d174  mov     word ptr [rbp+47h+pvar], si
0x18003d178  mov     rcx, [rbp+47h+ppv]
0x18003d17c  mov     rax, [rcx]
0x18003d17f  lea     r8, [rbp+47h+pvar]
0x18003d183  lea     rdx, aApplication; "Application"
0x18003d18a  mov     rax, [rax+20h]
0x18003d18e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d193  mov     ebx, eax
0x18003d195  test    eax, eax
0x18003d197  jns     short loc_18003D1F1
0x18003d199  lea     rcx, [rbp+47h+pvar]; pvar
0x18003d19d  call    cs:__imp_PropVariantClear
0x18003d1a3  nop
0x18003d1a4  lea     rcx, [rbp+47h+var_88]; pvar
0x18003d1a8  call    cs:__imp_PropVariantClear
0x18003d1ae  nop
0x18003d1af  lea     rcx, [rbp+47h+var_70]; pvar
0x18003d1b3  call    cs:__imp_PropVariantClear
0x18003d1b9  nop
0x18003d1ba  lea     rcx, [rbp+47h+var_58]; pvar
0x18003d1be  call    cs:__imp_PropVariantClear
0x18003d1c4  nop
0x18003d1c5  mov     rcx, [rbp+47h+ppv]
0x18003d1c9  test    rcx, rcx
0x18003d1cc  jz      short loc_18003D1DB
0x18003d1ce  mov     rax, [rcx]
0x18003d1d1  mov     rax, [rax+10h]
0x18003d1d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1da  nop
0x18003d1db  mov     eax, ebx
0x18003d1dd  add     rsp, 88h
0x18003d1e4  pop     r15
0x18003d1e6  pop     r14
0x18003d1e8  pop     r13
0x18003d1ea  pop     r12
0x18003d1ec  pop     rdi
0x18003d1ed  pop     rsi
0x18003d1ee  pop     rbx
0x18003d1ef  pop     rbp
0x18003d1f0  retn
0x18003d1f1  mov     rcx, [rbp+47h+ppv]
0x18003d1f5  mov     rax, [rcx]
0x18003d1f8  mov     r8, r12
0x18003d1fb  lea     rdx, _GUID_71604b0f_97b0_4764_8577_2f13e98a1422
0x18003d202  mov     rax, [rax]
0x18003d205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d20a  mov     ebx, eax
0x18003d20c  jmp     short loc_18003D199
0x18003d20e  mov     ebx, 80070057h
0x18003d213  jmp     short loc_18003D21A
0x18003d215  mov     ebx, 8007000Eh
0x18003d21a  xorps   xmm0, xmm0
0x18003d21d  xor     eax, eax
0x18003d21f  movups  xmmword ptr [rbp+47h+var_58], xmm0
0x18003d223  mov     [rbp+47h+var_48], rax
0x18003d227  jmp     short loc_18003D1BA
0x18003d229  mov     ebx, 80070057h
0x18003d22e  jmp     short loc_18003D235
0x18003d230  mov     ebx, 8007000Eh
0x18003d235  xorps   xmm0, xmm0
0x18003d238  xor     eax, eax
0x18003d23a  movups  xmmword ptr [rbp+47h+var_70], xmm0
0x18003d23e  mov     [rbp+47h+var_60], rax
0x18003d242  jmp     loc_18003D1AF
0x18003d247  xorps   xmm0, xmm0
0x18003d24a  xor     eax, eax
0x18003d24c  movups  xmmword ptr [rbp+47h+pvar], xmm0
0x18003d250  mov     [rbp+47h+var_90], rax
0x18003d254  mov     ebx, 8007000Eh
0x18003d259  jmp     loc_18003D199
0x18003d25e  xorps   xmm0, xmm0
0x18003d261  xor     eax, eax
0x18003d263  movups  xmmword ptr [rbp+47h+var_88], xmm0
0x18003d267  mov     [rbp+47h+var_78], rax
0x18003d26b  mov     ebx, 8007000Eh
0x18003d270  jmp     loc_18003D1A4
```
