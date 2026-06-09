# _anonymous_namespace_::TransactionFilterAdapter::Read

- ea: `0x140030720`
- end: `0x140030bef`
- name: `_anonymous_namespace_::TransactionFilterAdapter::Read`
- size: `1231`
- prototype: `__int64 __fastcall(__int64, _BYTE *)`
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x1400030a0`
- `0x1400030c4`
- `0x140003c74`
- `0x14000b5c4`
- `0x14000d80c`
- `0x14001734c`
- `0x140030030`
- `0x140030720`
- `0x140049bf0`
- `0x14004f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140030988`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140030b31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140030988`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140030b31`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x14003090a`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::TransactionFilterAdapter::Read(__int64 a1, _BYTE *a2)
{
  __int64 result; // rax
  __int64 v5; // rcx
  int v6; // ecx
  bool v7; // al
  int v8; // eax
  int v9; // esi
  _QWORD *v10; // r8
  _QWORD *v11; // rax
  int v12; // eax
  int v13; // eax
  int v14; // esi
  _QWORD *v15; // r8
  int v16; // eax
  bool v17; // sf
  int v18; // edx
  char v19; // [rsp+30h] [rbp-20E8h] BYREF
  char v20[3]; // [rsp+31h] [rbp-20E7h] BYREF
  int v21; // [rsp+34h] [rbp-20E4h] BYREF
  int v22; // [rsp+38h] [rbp-20E0h] BYREF
  __int16 v23; // [rsp+3Dh] [rbp-20DBh]
  char v24; // [rsp+3Fh] [rbp-20D9h]
  _QWORD *v25; // [rsp+40h] [rbp-20D8h] BYREF
  int v26; // [rsp+48h] [rbp-20D0h] BYREF
  int v27; // [rsp+4Ch] [rbp-20CCh] BYREF
  HRESULT (__stdcall *v28)(PROPVARIANT *); // [rsp+50h] [rbp-20C8h] BYREF
  _QWORD *v29; // [rsp+58h] [rbp-20C0h]
  __int64 v30; // [rsp+60h] [rbp-20B8h]
  _BYTE v31[4]; // [rsp+70h] [rbp-20A8h] BYREF
  _BYTE v32[4]; // [rsp+74h] [rbp-20A4h] BYREF
  int v33; // [rsp+78h] [rbp-20A0h]
  _BYTE v34[16]; // [rsp+80h] [rbp-2098h] BYREF
  int v35; // [rsp+90h] [rbp-2088h]
  LPVOID pv; // [rsp+98h] [rbp-2080h]
  _QWORD v37[2]; // [rsp+B0h] [rbp-2068h] BYREF
  int v38; // [rsp+C0h] [rbp-2058h]
  unsigned __int64 v39; // [rsp+C8h] [rbp-2050h]
  char v40[8208]; // [rsp+D0h] [rbp-2048h] BYREF

  v30 = -2;
  if ( !a2 )
    return 2147500035LL;
  if ( *(_BYTE *)(a1 + 80) )
  {
    *a2 = 0;
    return 0;
  }
  else
  {
    *(_BYTE *)(a1 + 81) = 0;
    *(_DWORD *)(a1 + 88) = v22;
    *(_BYTE *)(a1 + 92) = 0;
    *(_WORD *)(a1 + 93) = v23;
    *(_BYTE *)(a1 + 95) = v24;
    v5 = *(_QWORD *)(a1 + 48);
    try
    {
      result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v5 + 32LL))(v5);
      if ( !(_DWORD)result )
      {
        if ( *a2 )
        {
          v21 = 0;
          result = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)(a1 + 48) + 40LL))(
                     *(_QWORD *)(a1 + 48),
                     &v21);
          if ( (_DWORD)result )
          {
            *a2 = 0;
          }
          else
          {
            v6 = v21;
            if ( v21 == 1 || (v7 = 1, !v21) )
              v7 = (*(_DWORD *)(a1 + 84) & 0x100000) != 0;
            while ( !v7 )
            {
              if ( v6 == 1 )
              {
                memset_0(v31, 0, 0x40u);
                v35 = 1;
                pv = 0;
                v33 = 2;
                v8 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 64) + 24LL))(
                       *(_QWORD *)(a1 + 64),
                       v32);
                v9 = v8;
                if ( v8 < 1 )
                {
                  if ( !v8 )
                  {
                    v9 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 64) + 32LL))(
                           *(_QWORD *)(a1 + 64),
                           v34);
                    if ( v9 >= 1 )
                      v9 = -2147467259;
                    if ( !v9 )
                    {
                      std::wstring::wstring((__int64)v37);
                      std::wstring::resize(v37, 85);
                      v26 = v38;
                      v10 = v37;
                      if ( v39 > 7 )
                        v10 = (_QWORD *)v37[0];
                      v9 = (*(__int64 (__fastcall **)(_QWORD, int *, _QWORD *))(**(_QWORD **)(a1 + 64) + 40LL))(
                             *(_QWORD *)(a1 + 64),
                             &v26,
                             v10);
                      if ( v9 >= 1 )
                        v9 = -2147467259;
                      std::wstring::_Tidy_deallocate((__int64)v37);
                      if ( !v9 )
                      {
                        v28 = PropVariantClear;
                        v29 = 0;
                        v11 = operator new(0x18u);
                        v25 = v11;
                        *(_OWORD *)v11 = 0;
                        v11[2] = 0;
                        v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD **))(**(_QWORD **)(a1 + 64) + 48LL))(
                                *(_QWORD *)(a1 + 64),
                                &v25);
                        v9 = v12;
                        if ( v12 < 1 )
                        {
                          if ( v12 >= 0 && v25 )
                            v29 = v25;
                        }
                        else
                        {
                          v9 = -2147467259;
                        }
                        std::unique_ptr<tagPROPVARIANT,long (*)(tagPROPVARIANT *)>::~unique_ptr<tagPROPVARIANT,long (*)(tagPROPVARIANT *)>(&v28);
                      }
                    }
                  }
                }
                else
                {
                  v9 = -2147467259;
                }
                if ( !v35 && pv )
                  CoTaskMemFree(pv);
                if ( v9 )
                {
                  *a2 = 0;
                  result = (unsigned int)v9;
                  goto LABEL_80;
                }
                v6 = v21;
              }
              if ( !v6 )
              {
                memset_0(v31, 0, 0x40u);
                v35 = 1;
                pv = 0;
                v33 = 1;
                v13 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 56) + 24LL))(
                        *(_QWORD *)(a1 + 56),
                        v32);
                v14 = v13;
                if ( v13 < 1 )
                {
                  if ( !v13 )
                  {
                    v14 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 56) + 32LL))(
                            *(_QWORD *)(a1 + 56),
                            v34);
                    if ( v14 >= 1 )
                      v14 = -2147467259;
                    if ( !v14 )
                    {
                      std::wstring::wstring((__int64)v37);
                      std::wstring::resize(v37, 85);
                      v27 = v38;
                      v15 = v37;
                      if ( v39 > 7 )
                        v15 = (_QWORD *)v37[0];
                      v14 = (*(__int64 (__fastcall **)(_QWORD, int *, _QWORD *))(**(_QWORD **)(a1 + 56) + 40LL))(
                              *(_QWORD *)(a1 + 56),
                              &v27,
                              v15);
                      if ( v14 >= 1 )
                        v14 = -2147467259;
                      std::wstring::_Tidy_deallocate((__int64)v37);
                      if ( !v14 )
                      {
                        v16 = 0;
                        while ( 1 )
                        {
                          v17 = v16 < 0;
                          if ( v16 )
                            break;
                          v22 = 4096;
                          v19 = 0;
                          v20[0] = 0;
                          v16 = (*(__int64 (__fastcall **)(_QWORD, char *, char *, int *, char *))(**(_QWORD **)(a1 + 56)
                                                                                                 + 48LL))(
                                  *(_QWORD *)(a1 + 56),
                                  &v19,
                                  v20,
                                  &v22,
                                  v40);
                          if ( v16 < 1 )
                          {
                            v17 = v16 < 0;
                            if ( v16 )
                              break;
                            if ( v19 )
                            {
                              if ( v20[0] )
                                v16 = 268041;
                            }
                            else
                            {
                              v16 = -2147215611;
                            }
                          }
                          else
                          {
                            v16 = -2147467259;
                          }
                        }
                        if ( v17 )
                        {
                          if ( (unsigned int)(v16 + 2147215615) > 7 || (v18 = 209, !_bittest(&v18, v16 + 2147215615)) )
                            v14 = v16;
                        }
                      }
                    }
                  }
                }
                else
                {
                  v14 = -2147467259;
                }
                if ( !v35 && pv )
                  CoTaskMemFree(pv);
                if ( v14 )
                {
                  *a2 = 0;
                  result = (unsigned int)v14;
                  goto LABEL_80;
                }
              }
              result = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 48) + 32LL))(
                         *(_QWORD *)(a1 + 48),
                         a2);
              if ( (_DWORD)result )
                goto LABEL_80;
              if ( !*a2 )
              {
                *(_BYTE *)(a1 + 80) = 1;
                result = 0;
                goto LABEL_80;
              }
              result = (*(__int64 (__fastcall **)(_QWORD, int *))(**(_QWORD **)(a1 + 48) + 40LL))(
                         *(_QWORD *)(a1 + 48),
                         &v21);
              if ( (_DWORD)result )
              {
                *a2 = 0;
                goto LABEL_80;
              }
              v6 = v21;
              if ( v21 != 1 )
              {
                v7 = 1;
                if ( v21 )
                  continue;
              }
              v7 = (*(_DWORD *)(a1 + 84) & 0x100000) != 0;
            }
            *(_BYTE *)(a1 + 81) = 1;
            *(_DWORD *)(a1 + 88) = v6;
            *(_BYTE *)(a1 + 92) = 1;
            *(_WORD *)(a1 + 93) = *(_WORD *)((char *)&v25 + 5);
            *(_BYTE *)(a1 + 95) = HIBYTE(v25);
            result = 0;
          }
        }
        else
        {
          *(_BYTE *)(a1 + 80) = 1;
          result = 0;
        }
      }
    }
    catch ( ... )
    {
      indexer::result::details::result_from_caught_exception<1>();
    }
LABEL_80:
    ;
  }
  return result;
}

```

## disassembly

```asm
0x140030720  push    rsi
0x140030722  push    rdi
0x140030723  push    r12
0x140030725  push    r14
0x140030727  push    r15
0x140030729  mov     eax, 20F0h
0x14003072e  call    _alloca_probe
0x140030733  sub     rsp, rax
0x140030736  mov     [rsp+2118h+var_20B8], 0FFFFFFFFFFFFFFFEh
0x14003073f  mov     [rsp+2118h+arg_10], rbx
0x140030747  mov     rax, cs:__security_cookie
0x14003074e  xor     rax, rsp
0x140030751  mov     [rsp+2118h+var_38], rax
0x140030759  mov     r14, rdx
0x14003075c  mov     rdi, rcx
0x14003075f  xor     r15d, r15d
0x140030762  test    rdx, rdx
0x140030765  jnz     short loc_140030771
0x140030767  mov     eax, 80004003h
0x14003076c  jmp     loc_140030BC6
0x140030771  cmp     [rcx+50h], r15b
0x140030775  jz      short loc_140030781
0x140030777  mov     [rdx], r15b
0x14003077a  xor     eax, eax
0x14003077c  jmp     loc_140030BC6
0x140030781  mov     [rcx+51h], r15b
0x140030785  mov     eax, [rsp+2118h+var_20E0]
0x140030789  mov     [rcx+58h], eax
0x14003078c  mov     [rcx+5Ch], r15b
0x140030790  movzx   eax, [rsp+2118h+var_20DB]
0x140030795  mov     [rcx+5Dh], ax
0x140030799  mov     al, [rsp+2118h+var_20D9]
0x14003079d  mov     [rcx+5Fh], al
0x1400307a0  mov     rcx, [rcx+30h]
0x1400307a4  mov     rax, [rcx]
0x1400307a7  mov     rax, [rax+20h]
0x1400307ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400307b0  test    eax, eax
0x1400307b2  jnz     loc_140030BC6
0x1400307b8  cmp     [r14], r15b
0x1400307bb  jnz     short loc_1400307C8
0x1400307bd  mov     byte ptr [rdi+50h], 1
0x1400307c1  xor     eax, eax
0x1400307c3  jmp     loc_140030BC6
0x1400307c8  mov     [rsp+2118h+var_20E4], r15d
0x1400307cd  mov     rcx, [rdi+30h]
0x1400307d1  mov     rax, [rcx]
0x1400307d4  lea     rdx, [rsp+2118h+var_20E4]
0x1400307d9  mov     rax, [rax+28h]
0x1400307dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400307e2  test    eax, eax
0x1400307e4  jz      short loc_1400307EE
0x1400307e6  mov     [r14], r15b
0x1400307e9  jmp     loc_140030BC6
0x1400307ee  mov     ecx, [rsp+2118h+var_20E4]
0x1400307f2  mov     ebx, 1
0x1400307f7  cmp     ecx, ebx
0x1400307f9  jz      short loc_140030801
0x1400307fb  mov     al, bl
0x1400307fd  test    ecx, ecx
0x1400307ff  jnz     short loc_140030809
0x140030801  mov     eax, [rdi+54h]
0x140030804  shr     eax, 14h
0x140030807  and     al, bl
0x140030809  mov     r12d, 80004005h
0x14003080f  test    al, al
0x140030811  jnz     loc_140030BA5
0x140030817  cmp     ecx, ebx
0x140030819  jnz     loc_1400309A0
0x14003081f  xor     edx, edx; Val
0x140030821  lea     r8d, [rdx+40h]; Size
0x140030825  lea     rcx, [rsp+2118h+var_20A8]; void *
0x14003082a  call    memset_0
0x14003082f  mov     [rsp+2118h+var_2088], ebx
0x140030836  mov     [rsp+2118h+pv], r15
0x14003083e  mov     [rsp+2118h+var_20A0], 2
0x140030846  mov     rcx, [rdi+40h]
0x14003084a  mov     rax, [rcx]
0x14003084d  lea     rdx, [rsp+2118h+var_20A4]
0x140030852  mov     rax, [rax+18h]
0x140030856  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003085b  mov     esi, eax
0x14003085d  cmp     eax, ebx
0x14003085f  jl      short loc_140030869
0x140030861  mov     esi, r12d
0x140030864  jmp     loc_140030971
0x140030869  test    eax, eax
0x14003086b  jnz     loc_140030971
0x140030871  mov     rcx, [rdi+40h]
0x140030875  mov     rax, [rcx]
0x140030878  lea     rdx, [rsp+2118h+var_2098]
0x140030880  mov     rax, [rax+20h]
0x140030884  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030889  mov     esi, eax
0x14003088b  cmp     eax, ebx
0x14003088d  cmovge  esi, r12d
0x140030891  test    esi, esi
0x140030893  jnz     loc_140030971
0x140030899  lea     rcx, [rsp+2118h+var_2068]
0x1400308a1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1400308a6  nop
0x1400308a7  lea     edx, [rsi+55h]
0x1400308aa  lea     rcx, [rsp+2118h+var_2068]
0x1400308b2  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1400308b7  mov     eax, [rsp+2118h+var_2058]
0x1400308be  mov     [rsp+2118h+var_20D0], eax
0x1400308c2  mov     rcx, [rdi+40h]
0x1400308c6  mov     rax, [rcx]
0x1400308c9  lea     r8, [rsp+2118h+var_2068]
0x1400308d1  cmp     [rsp+2118h+var_2050], 7
0x1400308da  cmova   r8, [rsp+2118h+var_2068]
0x1400308e3  lea     rdx, [rsp+2118h+var_20D0]
0x1400308e8  mov     rax, [rax+28h]
0x1400308ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400308f1  mov     esi, eax
0x1400308f3  cmp     eax, ebx
0x1400308f5  cmovge  esi, r12d
0x1400308f9  lea     rcx, [rsp+2118h+var_2068]
0x140030901  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140030906  test    esi, esi
0x140030908  jnz     short loc_140030971
0x14003090a  mov     rax, cs:__imp_PropVariantClear
0x140030911  mov     [rsp+2118h+var_20C8], rax
0x140030916  mov     [rsp+2118h+var_20C0], r15
0x14003091b  lea     ecx, [rsi+18h]; Size
0x14003091e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140030923  mov     [rsp+2118h+var_20D8], rax
0x140030928  xorps   xmm0, xmm0
0x14003092b  xor     ecx, ecx
0x14003092d  movups  xmmword ptr [rax], xmm0
0x140030930  mov     [rax+10h], rcx
0x140030934  mov     rcx, [rdi+40h]
0x140030938  mov     rax, [rcx]
0x14003093b  lea     rdx, [rsp+2118h+var_20D8]
0x140030940  mov     rax, [rax+30h]
0x140030944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030949  mov     esi, eax
0x14003094b  cmp     eax, ebx
0x14003094d  jl      short loc_140030954
0x14003094f  mov     esi, r12d
0x140030952  jmp     short loc_140030967
0x140030954  test    eax, eax
0x140030956  js      short loc_140030967
0x140030958  mov     rax, [rsp+2118h+var_20D8]
0x14003095d  test    rax, rax
0x140030960  jz      short loc_140030967
0x140030962  mov     [rsp+2118h+var_20C0], rax
0x140030967  lea     rcx, [rsp+2118h+var_20C8]
0x14003096c  call    ??1?$unique_ptr@UtagPROPVARIANT@@P6AJPEAU1@@Z@std@@QEAA@XZ; std::unique_ptr<tagPROPVARIANT,long (*)(tagPROPVARIANT *)>::~unique_ptr<tagPROPVARIANT,long (*)(tagPROPVARIANT *)>(void)
0x140030971  cmp     [rsp+2118h+var_2088], r15d
0x140030979  jnz     short loc_14003098E
0x14003097b  mov     rcx, [rsp+2118h+pv]; pv
0x140030983  test    rcx, rcx
0x140030986  jz      short loc_14003098E
0x140030988  call    cs:__imp_CoTaskMemFree
0x14003098e  test    esi, esi
0x140030990  jz      short loc_14003099C
0x140030992  mov     [r14], r15b
0x140030995  mov     eax, esi
0x140030997  jmp     loc_140030BC6
0x14003099c  mov     ecx, [rsp+2118h+var_20E4]
0x1400309a0  test    ecx, ecx
0x1400309a2  jnz     loc_140030B45
0x1400309a8  xor     edx, edx; Val
0x1400309aa  lea     r8d, [rcx+40h]; Size
0x1400309ae  lea     rcx, [rsp+2118h+var_20A8]; void *
0x1400309b3  call    memset_0
0x1400309b8  mov     [rsp+2118h+var_2088], ebx
0x1400309bf  mov     [rsp+2118h+pv], r15
0x1400309c7  mov     [rsp+2118h+var_20A0], ebx
0x1400309cb  mov     rcx, [rdi+38h]
0x1400309cf  mov     rax, [rcx]
0x1400309d2  lea     rdx, [rsp+2118h+var_20A4]
0x1400309d7  mov     rax, [rax+18h]
0x1400309db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400309e0  mov     esi, eax
0x1400309e2  cmp     eax, ebx
0x1400309e4  jl      short loc_1400309EE
0x1400309e6  mov     esi, r12d
0x1400309e9  jmp     loc_140030B1A
0x1400309ee  test    eax, eax
0x1400309f0  jnz     loc_140030B1A
0x1400309f6  mov     rcx, [rdi+38h]
0x1400309fa  mov     rax, [rcx]
0x1400309fd  lea     rdx, [rsp+2118h+var_2098]
0x140030a05  mov     rax, [rax+20h]
0x140030a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030a0e  mov     esi, eax
0x140030a10  cmp     eax, ebx
0x140030a12  cmovge  esi, r12d
0x140030a16  test    esi, esi
0x140030a18  jnz     loc_140030B1A
0x140030a1e  lea     rcx, [rsp+2118h+var_2068]
0x140030a26  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140030a2b  nop
0x140030a2c  lea     edx, [rsi+55h]
0x140030a2f  lea     rcx, [rsp+2118h+var_2068]
0x140030a37  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x140030a3c  mov     eax, [rsp+2118h+var_2058]
0x140030a43  mov     [rsp+2118h+var_20CC], eax
0x140030a47  mov     rcx, [rdi+38h]
0x140030a4b  mov     rax, [rcx]
0x140030a4e  lea     r8, [rsp+2118h+var_2068]
0x140030a56  cmp     [rsp+2118h+var_2050], 7
0x140030a5f  cmova   r8, [rsp+2118h+var_2068]
0x140030a68  lea     rdx, [rsp+2118h+var_20CC]
0x140030a6d  mov     rax, [rax+28h]
0x140030a71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030a76  mov     esi, eax
0x140030a78  cmp     eax, ebx
0x140030a7a  cmovge  esi, r12d
0x140030a7e  lea     rcx, [rsp+2118h+var_2068]
0x140030a86  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140030a8b  test    esi, esi
0x140030a8d  jnz     loc_140030B1A
0x140030a93  mov     eax, r15d
0x140030a96  test    eax, eax
0x140030a98  jnz     short loc_140030B01
0x140030a9a  mov     [rsp+2118h+var_20E0], 1000h
0x140030aa2  mov     [rsp+2118h+var_20E8], r15b
0x140030aa7  mov     [rsp+2118h+var_20E7], r15b
0x140030aac  mov     rcx, [rdi+38h]
0x140030ab0  mov     rax, [rcx]
0x140030ab3  lea     rdx, [rsp+2118h+var_2048]
0x140030abb  mov     [rsp+2118h+var_20F8], rdx
0x140030ac0  lea     r9, [rsp+2118h+var_20E0]
0x140030ac5  lea     r8, [rsp+2118h+var_20E7]
0x140030aca  lea     rdx, [rsp+2118h+var_20E8]
0x140030acf  mov     rax, [rax+30h]
0x140030ad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030ad8  cmp     eax, ebx
0x140030ada  jl      short loc_140030AE1
0x140030adc  mov     eax, r12d
0x140030adf  jmp     short loc_140030A96
0x140030ae1  test    eax, eax
0x140030ae3  jnz     short loc_140030B01
0x140030ae5  cmp     [rsp+2118h+var_20E8], r15b
0x140030aea  jnz     short loc_140030AF3
0x140030aec  mov     eax, 80041705h
0x140030af1  jmp     short loc_140030A96
0x140030af3  cmp     [rsp+2118h+var_20E7], r15b
0x140030af8  jz      short loc_140030A96
0x140030afa  mov     eax, 41709h
0x140030aff  jmp     short loc_140030A96
0x140030b01  jns     short loc_140030B1A
0x140030b03  lea     ecx, [rax+7FFBE8FFh]
0x140030b09  cmp     ecx, 7
0x140030b0c  ja      short loc_140030B18
0x140030b0e  mov     edx, 0D1h
0x140030b13  bt      edx, ecx
0x140030b16  jb      short loc_140030B1A
0x140030b18  mov     esi, eax
0x140030b1a  cmp     [rsp+2118h+var_2088], r15d
0x140030b22  jnz     short loc_140030B37
0x140030b24  mov     rcx, [rsp+2118h+pv]; pv
0x140030b2c  test    rcx, rcx
0x140030b2f  jz      short loc_140030B37
0x140030b31  call    cs:__imp_CoTaskMemFree
0x140030b37  test    esi, esi
0x140030b39  jz      short loc_140030B45
0x140030b3b  mov     [r14], r15b
0x140030b3e  mov     eax, esi
0x140030b40  jmp     loc_140030BC6
0x140030b45  mov     rcx, [rdi+30h]
0x140030b49  mov     rax, [rcx]
0x140030b4c  mov     rdx, r14
0x140030b4f  mov     rax, [rax+20h]
0x140030b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030b58  test    eax, eax
0x140030b5a  jnz     short loc_140030BC6
0x140030b5c  cmp     [r14], r15b
0x140030b5f  jnz     short loc_140030B68
0x140030b61  mov     [rdi+50h], bl
0x140030b64  xor     eax, eax
0x140030b66  jmp     short loc_140030BC6
0x140030b68  mov     rcx, [rdi+30h]
0x140030b6c  mov     rax, [rcx]
0x140030b6f  lea     rdx, [rsp+2118h+var_20E4]
0x140030b74  mov     rax, [rax+28h]
0x140030b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030b7d  test    eax, eax
0x140030b7f  jz      short loc_140030B86
0x140030b81  mov     [r14], r15b
0x140030b84  jmp     short loc_140030BC6
0x140030b86  mov     ecx, [rsp+2118h+var_20E4]
0x140030b8a  cmp     ecx, ebx
0x140030b8c  jz      short loc_140030B98
0x140030b8e  mov     al, bl
0x140030b90  test    ecx, ecx
0x140030b92  jnz     loc_14003080F
0x140030b98  mov     eax, [rdi+54h]
0x140030b9b  shr     eax, 14h
0x140030b9e  and     al, bl
0x140030ba0  jmp     loc_14003080F
0x140030ba5  mov     [rdi+51h], bl
0x140030ba8  mov     [rdi+58h], ecx
0x140030bab  mov     [rdi+5Ch], bl
0x140030bae  movzx   eax, word ptr [rsp+2118h+var_20D8+5]
0x140030bb3  mov     [rdi+5Dh], ax
0x140030bb7  mov     al, byte ptr [rsp+2118h+var_20D8+7]
  ... truncated ...
```
