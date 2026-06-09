# _anonymous_namespace_::TransactionFilterAdapter::Read

- ea: `0x140052c60`
- end: `0x14005312f`
- name: `_anonymous_namespace_::TransactionFilterAdapter::Read`
- size: `1231`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callees

- `0x140005240`
- `0x140005570`
- `0x140006210`
- `0x14000cd28`
- `0x14003376c`
- `0x140037edc`
- `0x140052570`
- `0x140052c60`
- `0x140069b10`
- `0x140070010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x140052e4a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140052ec8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140053071`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140052ec8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140053071`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
  void *retaddr; // [rsp+2118h] [rbp+0h]

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
                      std::wstring::wstring(v37);
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
                      std::wstring::_Tidy_deallocate(v37);
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
                      std::wstring::wstring(v37);
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
                      std::wstring::_Tidy_deallocate(v37);
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
      indexer::result::details::result_from_caught_exception<1>(
        retaddr,
        245,
        "onecoreuap\\base\\appmodel\\search\\common\\filterpipeline\\transactionfilteradapter.cpp");
    }
LABEL_80:
    ;
  }
  return result;
}

```

## disassembly

```asm
0x140052c60  push    rsi
0x140052c62  push    rdi
0x140052c63  push    r12
0x140052c65  push    r14
0x140052c67  push    r15
0x140052c69  mov     eax, 20F0h
0x140052c6e  call    _alloca_probe
0x140052c73  sub     rsp, rax
0x140052c76  mov     [rsp+2118h+var_20B8], 0FFFFFFFFFFFFFFFEh
0x140052c7f  mov     [rsp+2118h+arg_10], rbx
0x140052c87  mov     rax, cs:__security_cookie
0x140052c8e  xor     rax, rsp
0x140052c91  mov     [rsp+2118h+var_38], rax
0x140052c99  mov     r14, rdx
0x140052c9c  mov     rdi, rcx
0x140052c9f  xor     r15d, r15d
0x140052ca2  test    rdx, rdx
0x140052ca5  jnz     short loc_140052CB1
0x140052ca7  mov     eax, 80004003h
0x140052cac  jmp     loc_140053106
0x140052cb1  cmp     [rcx+50h], r15b
0x140052cb5  jz      short loc_140052CC1
0x140052cb7  mov     [rdx], r15b
0x140052cba  xor     eax, eax
0x140052cbc  jmp     loc_140053106
0x140052cc1  mov     [rcx+51h], r15b
0x140052cc5  mov     eax, [rsp+2118h+var_20E0]
0x140052cc9  mov     [rcx+58h], eax
0x140052ccc  mov     [rcx+5Ch], r15b
0x140052cd0  movzx   eax, [rsp+2118h+var_20DB]
0x140052cd5  mov     [rcx+5Dh], ax
0x140052cd9  mov     al, [rsp+2118h+var_20D9]
0x140052cdd  mov     [rcx+5Fh], al
0x140052ce0  mov     rcx, [rcx+30h]
0x140052ce4  mov     rax, [rcx]
0x140052ce7  mov     rax, [rax+20h]
0x140052ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052cf0  test    eax, eax
0x140052cf2  jnz     loc_140053106
0x140052cf8  cmp     [r14], r15b
0x140052cfb  jnz     short loc_140052D08
0x140052cfd  mov     byte ptr [rdi+50h], 1
0x140052d01  xor     eax, eax
0x140052d03  jmp     loc_140053106
0x140052d08  mov     [rsp+2118h+var_20E4], r15d
0x140052d0d  mov     rcx, [rdi+30h]
0x140052d11  mov     rax, [rcx]
0x140052d14  lea     rdx, [rsp+2118h+var_20E4]
0x140052d19  mov     rax, [rax+28h]
0x140052d1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052d22  test    eax, eax
0x140052d24  jz      short loc_140052D2E
0x140052d26  mov     [r14], r15b
0x140052d29  jmp     loc_140053106
0x140052d2e  mov     ecx, [rsp+2118h+var_20E4]
0x140052d32  mov     ebx, 1
0x140052d37  cmp     ecx, ebx
0x140052d39  jz      short loc_140052D41
0x140052d3b  mov     al, bl
0x140052d3d  test    ecx, ecx
0x140052d3f  jnz     short loc_140052D49
0x140052d41  mov     eax, [rdi+54h]
0x140052d44  shr     eax, 14h
0x140052d47  and     al, bl
0x140052d49  mov     r12d, 80004005h
0x140052d4f  test    al, al
0x140052d51  jnz     loc_1400530E5
0x140052d57  cmp     ecx, ebx
0x140052d59  jnz     loc_140052EE0
0x140052d5f  xor     edx, edx; Val
0x140052d61  lea     r8d, [rdx+40h]; Size
0x140052d65  lea     rcx, [rsp+2118h+var_20A8]; void *
0x140052d6a  call    memset_0
0x140052d6f  mov     [rsp+2118h+var_2088], ebx
0x140052d76  mov     [rsp+2118h+pv], r15
0x140052d7e  mov     [rsp+2118h+var_20A0], 2
0x140052d86  mov     rcx, [rdi+40h]
0x140052d8a  mov     rax, [rcx]
0x140052d8d  lea     rdx, [rsp+2118h+var_20A4]
0x140052d92  mov     rax, [rax+18h]
0x140052d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052d9b  mov     esi, eax
0x140052d9d  cmp     eax, ebx
0x140052d9f  jl      short loc_140052DA9
0x140052da1  mov     esi, r12d
0x140052da4  jmp     loc_140052EB1
0x140052da9  test    eax, eax
0x140052dab  jnz     loc_140052EB1
0x140052db1  mov     rcx, [rdi+40h]
0x140052db5  mov     rax, [rcx]
0x140052db8  lea     rdx, [rsp+2118h+var_2098]
0x140052dc0  mov     rax, [rax+20h]
0x140052dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052dc9  mov     esi, eax
0x140052dcb  cmp     eax, ebx
0x140052dcd  cmovge  esi, r12d
0x140052dd1  test    esi, esi
0x140052dd3  jnz     loc_140052EB1
0x140052dd9  lea     rcx, [rsp+2118h+var_2068]
0x140052de1  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140052de6  nop
0x140052de7  lea     edx, [rsi+55h]
0x140052dea  lea     rcx, [rsp+2118h+var_2068]
0x140052df2  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x140052df7  mov     eax, [rsp+2118h+var_2058]
0x140052dfe  mov     [rsp+2118h+var_20D0], eax
0x140052e02  mov     rcx, [rdi+40h]
0x140052e06  mov     rax, [rcx]
0x140052e09  lea     r8, [rsp+2118h+var_2068]
0x140052e11  cmp     [rsp+2118h+var_2050], 7
0x140052e1a  cmova   r8, [rsp+2118h+var_2068]
0x140052e23  lea     rdx, [rsp+2118h+var_20D0]
0x140052e28  mov     rax, [rax+28h]
0x140052e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052e31  mov     esi, eax
0x140052e33  cmp     eax, ebx
0x140052e35  cmovge  esi, r12d
0x140052e39  lea     rcx, [rsp+2118h+var_2068]
0x140052e41  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140052e46  test    esi, esi
0x140052e48  jnz     short loc_140052EB1
0x140052e4a  mov     rax, cs:__imp_PropVariantClear
0x140052e51  mov     [rsp+2118h+var_20C8], rax
0x140052e56  mov     [rsp+2118h+var_20C0], r15
0x140052e5b  lea     ecx, [rsi+18h]; Size
0x140052e5e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140052e63  mov     [rsp+2118h+var_20D8], rax
0x140052e68  xorps   xmm0, xmm0
0x140052e6b  xor     ecx, ecx
0x140052e6d  movups  xmmword ptr [rax], xmm0
0x140052e70  mov     [rax+10h], rcx
0x140052e74  mov     rcx, [rdi+40h]
0x140052e78  mov     rax, [rcx]
0x140052e7b  lea     rdx, [rsp+2118h+var_20D8]
0x140052e80  mov     rax, [rax+30h]
0x140052e84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052e89  mov     esi, eax
0x140052e8b  cmp     eax, ebx
0x140052e8d  jl      short loc_140052E94
0x140052e8f  mov     esi, r12d
0x140052e92  jmp     short loc_140052EA7
0x140052e94  test    eax, eax
0x140052e96  js      short loc_140052EA7
0x140052e98  mov     rax, [rsp+2118h+var_20D8]
0x140052e9d  test    rax, rax
0x140052ea0  jz      short loc_140052EA7
0x140052ea2  mov     [rsp+2118h+var_20C0], rax
0x140052ea7  lea     rcx, [rsp+2118h+var_20C8]
0x140052eac  call    ??1?$unique_ptr@UtagPROPVARIANT@@P6AJPEAU1@@Z@std@@QEAA@XZ; std::unique_ptr<tagPROPVARIANT,long (*)(tagPROPVARIANT *)>::~unique_ptr<tagPROPVARIANT,long (*)(tagPROPVARIANT *)>(void)
0x140052eb1  cmp     [rsp+2118h+var_2088], r15d
0x140052eb9  jnz     short loc_140052ECE
0x140052ebb  mov     rcx, [rsp+2118h+pv]; pv
0x140052ec3  test    rcx, rcx
0x140052ec6  jz      short loc_140052ECE
0x140052ec8  call    cs:__imp_CoTaskMemFree
0x140052ece  test    esi, esi
0x140052ed0  jz      short loc_140052EDC
0x140052ed2  mov     [r14], r15b
0x140052ed5  mov     eax, esi
0x140052ed7  jmp     loc_140053106
0x140052edc  mov     ecx, [rsp+2118h+var_20E4]
0x140052ee0  test    ecx, ecx
0x140052ee2  jnz     loc_140053085
0x140052ee8  xor     edx, edx; Val
0x140052eea  lea     r8d, [rcx+40h]; Size
0x140052eee  lea     rcx, [rsp+2118h+var_20A8]; void *
0x140052ef3  call    memset_0
0x140052ef8  mov     [rsp+2118h+var_2088], ebx
0x140052eff  mov     [rsp+2118h+pv], r15
0x140052f07  mov     [rsp+2118h+var_20A0], ebx
0x140052f0b  mov     rcx, [rdi+38h]
0x140052f0f  mov     rax, [rcx]
0x140052f12  lea     rdx, [rsp+2118h+var_20A4]
0x140052f17  mov     rax, [rax+18h]
0x140052f1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052f20  mov     esi, eax
0x140052f22  cmp     eax, ebx
0x140052f24  jl      short loc_140052F2E
0x140052f26  mov     esi, r12d
0x140052f29  jmp     loc_14005305A
0x140052f2e  test    eax, eax
0x140052f30  jnz     loc_14005305A
0x140052f36  mov     rcx, [rdi+38h]
0x140052f3a  mov     rax, [rcx]
0x140052f3d  lea     rdx, [rsp+2118h+var_2098]
0x140052f45  mov     rax, [rax+20h]
0x140052f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052f4e  mov     esi, eax
0x140052f50  cmp     eax, ebx
0x140052f52  cmovge  esi, r12d
0x140052f56  test    esi, esi
0x140052f58  jnz     loc_14005305A
0x140052f5e  lea     rcx, [rsp+2118h+var_2068]
0x140052f66  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x140052f6b  nop
0x140052f6c  lea     edx, [rsi+55h]
0x140052f6f  lea     rcx, [rsp+2118h+var_2068]
0x140052f77  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x140052f7c  mov     eax, [rsp+2118h+var_2058]
0x140052f83  mov     [rsp+2118h+var_20CC], eax
0x140052f87  mov     rcx, [rdi+38h]
0x140052f8b  mov     rax, [rcx]
0x140052f8e  lea     r8, [rsp+2118h+var_2068]
0x140052f96  cmp     [rsp+2118h+var_2050], 7
0x140052f9f  cmova   r8, [rsp+2118h+var_2068]
0x140052fa8  lea     rdx, [rsp+2118h+var_20CC]
0x140052fad  mov     rax, [rax+28h]
0x140052fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140052fb6  mov     esi, eax
0x140052fb8  cmp     eax, ebx
0x140052fba  cmovge  esi, r12d
0x140052fbe  lea     rcx, [rsp+2118h+var_2068]
0x140052fc6  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140052fcb  test    esi, esi
0x140052fcd  jnz     loc_14005305A
0x140052fd3  mov     eax, r15d
0x140052fd6  test    eax, eax
0x140052fd8  jnz     short loc_140053041
0x140052fda  mov     [rsp+2118h+var_20E0], 1000h
0x140052fe2  mov     [rsp+2118h+var_20E8], r15b
0x140052fe7  mov     [rsp+2118h+var_20E7], r15b
0x140052fec  mov     rcx, [rdi+38h]
0x140052ff0  mov     rax, [rcx]
0x140052ff3  lea     rdx, [rsp+2118h+var_2048]
0x140052ffb  mov     [rsp+2118h+var_20F8], rdx
0x140053000  lea     r9, [rsp+2118h+var_20E0]
0x140053005  lea     r8, [rsp+2118h+var_20E7]
0x14005300a  lea     rdx, [rsp+2118h+var_20E8]
0x14005300f  mov     rax, [rax+30h]
0x140053013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053018  cmp     eax, ebx
0x14005301a  jl      short loc_140053021
0x14005301c  mov     eax, r12d
0x14005301f  jmp     short loc_140052FD6
0x140053021  test    eax, eax
0x140053023  jnz     short loc_140053041
0x140053025  cmp     [rsp+2118h+var_20E8], r15b
0x14005302a  jnz     short loc_140053033
0x14005302c  mov     eax, 80041705h
0x140053031  jmp     short loc_140052FD6
0x140053033  cmp     [rsp+2118h+var_20E7], r15b
0x140053038  jz      short loc_140052FD6
0x14005303a  mov     eax, 41709h
0x14005303f  jmp     short loc_140052FD6
0x140053041  jns     short loc_14005305A
0x140053043  lea     ecx, [rax+7FFBE8FFh]
0x140053049  cmp     ecx, 7
0x14005304c  ja      short loc_140053058
0x14005304e  mov     edx, 0D1h
0x140053053  bt      edx, ecx
0x140053056  jb      short loc_14005305A
0x140053058  mov     esi, eax
0x14005305a  cmp     [rsp+2118h+var_2088], r15d
0x140053062  jnz     short loc_140053077
0x140053064  mov     rcx, [rsp+2118h+pv]; pv
0x14005306c  test    rcx, rcx
0x14005306f  jz      short loc_140053077
0x140053071  call    cs:__imp_CoTaskMemFree
0x140053077  test    esi, esi
0x140053079  jz      short loc_140053085
0x14005307b  mov     [r14], r15b
0x14005307e  mov     eax, esi
0x140053080  jmp     loc_140053106
0x140053085  mov     rcx, [rdi+30h]
0x140053089  mov     rax, [rcx]
0x14005308c  mov     rdx, r14
0x14005308f  mov     rax, [rax+20h]
0x140053093  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053098  test    eax, eax
0x14005309a  jnz     short loc_140053106
0x14005309c  cmp     [r14], r15b
0x14005309f  jnz     short loc_1400530A8
0x1400530a1  mov     [rdi+50h], bl
0x1400530a4  xor     eax, eax
0x1400530a6  jmp     short loc_140053106
0x1400530a8  mov     rcx, [rdi+30h]
0x1400530ac  mov     rax, [rcx]
0x1400530af  lea     rdx, [rsp+2118h+var_20E4]
0x1400530b4  mov     rax, [rax+28h]
0x1400530b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400530bd  test    eax, eax
0x1400530bf  jz      short loc_1400530C6
0x1400530c1  mov     [r14], r15b
0x1400530c4  jmp     short loc_140053106
0x1400530c6  mov     ecx, [rsp+2118h+var_20E4]
0x1400530ca  cmp     ecx, ebx
0x1400530cc  jz      short loc_1400530D8
0x1400530ce  mov     al, bl
0x1400530d0  test    ecx, ecx
0x1400530d2  jnz     loc_140052D4F
0x1400530d8  mov     eax, [rdi+54h]
0x1400530db  shr     eax, 14h
0x1400530de  and     al, bl
0x1400530e0  jmp     loc_140052D4F
0x1400530e5  mov     [rdi+51h], bl
0x1400530e8  mov     [rdi+58h], ecx
0x1400530eb  mov     [rdi+5Ch], bl
0x1400530ee  movzx   eax, word ptr [rsp+2118h+var_20D8+5]
0x1400530f3  mov     [rdi+5Dh], ax
0x1400530f7  mov     al, byte ptr [rsp+2118h+var_20D8+7]
  ... truncated ...
```
