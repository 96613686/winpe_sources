# SSPI_APP_CONTEXT::Initialize(IHttpContext *)

- ea: `0x1800068c0`
- end: `0x180007119`
- name: `?Initialize@SSPI_APP_CONTEXT@@QEAAJPEAVIHttpContext@@@Z`
- size: `2137`
- prototype: `__int64 __fastcall(SSPI_APP_CONTEXT *this, __int64 (__fastcall ***)(struct IHttpContext *))`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180005eac`

## callees

- `0x1800068c0`
- `0x180008b76`
- `0x180008ba0`
- `0x180009010`

## import_xrefs

- `msvcrt!wcschr` at `0x180006c3c`
- `msvcrt!wcschr` at `0x180006e10`
- `msvcrt!wcschr` at `0x180006e2b`
- `msvcrt!wcschr` at `0x180006e55`
- `msvcrt!wcschr` at `0x180006c3c`
- `msvcrt!wcschr` at `0x180006e10`
- `msvcrt!wcschr` at `0x180006e2b`
- `msvcrt!wcschr` at `0x180006e55`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006ee9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006f08`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006ee9`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006f08`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800070cd`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800070cd`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006923`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180006923`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180006e8a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180006e8a`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180006c54`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180006c54`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180006e71`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180006e71`
- `iisutil!?Append@MULTISZ@@QEAAHAEAVSTRU@@@Z` at `0x180006ea2`
- `iisutil!?Append@MULTISZ@@QEAAHAEAVSTRU@@@Z` at `0x180006ea2`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180006f1f`
- `iisutil!?First@MULTISZ@@QEBAPEBGXZ` at `0x180006f1f`

## string_xrefs

- `0x1800069b0`: `system.webServer/security/authentication/windowsAuthentication`
- `0x180006b01`: `tokenChecking`
- `0x180006d91`: `protocol`

## pseudocode

```c
__int64 __fastcall SSPI_APP_CONTEXT::Initialize(
        SSPI_APP_CONTEXT *this,
        __int64 (__fastcall ***a2)(struct IHttpContext *))
{
  __int64 (__fastcall **v4)(struct IHttpContext *); // rax
  __int64 (__fastcall *v5)(struct IHttpContext *); // rax
  __int64 v6; // rax
  __int64 v7; // rsi
  __int64 (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rax
  wchar_t *v9; // rdx
  int v10; // ebx
  __int64 v11; // r8
  _DWORD *v12; // r14
  __int64 v13; // rcx
  __int64 v14; // rcx
  char v15; // al
  __int64 v16; // rcx
  int *v17; // rsi
  int v18; // ecx
  unsigned int v19; // eax
  unsigned int v20; // esi
  __int64 v21; // rcx
  __int64 (__fastcall *v22)(__int64, _QWORD, __int64 *, _QWORD); // rbx
  __int64 (__fastcall ***v23)(_QWORD); // rax
  unsigned int v24; // eax
  unsigned int v25; // esi
  wchar_t *v26; // rax
  wchar_t *v27; // rax
  HLOCAL v28; // rax
  HLOCAL v29; // rax
  wchar_t *v30; // rax
  __int64 v31; // r9
  __int64 v32; // rcx
  __int64 v33; // rax
  wchar_t *Str; // [rsp+40h] [rbp-89h] BYREF
  __int64 v36; // [rsp+48h] [rbp-81h] BYREF
  int v37; // [rsp+50h] [rbp-79h] BYREF
  unsigned int v38; // [rsp+54h] [rbp-75h] BYREF
  unsigned int v39; // [rsp+58h] [rbp-71h] BYREF
  __int64 v40; // [rsp+60h] [rbp-69h] BYREF
  __int64 v41; // [rsp+68h] [rbp-61h] BYREF
  __int64 v42; // [rsp+70h] [rbp-59h] BYREF
  int v43; // [rsp+78h] [rbp-51h] BYREF
  int v44; // [rsp+7Ch] [rbp-4Dh] BYREF
  __int64 v45; // [rsp+80h] [rbp-49h] BYREF
  __int64 v46; // [rsp+88h] [rbp-41h] BYREF
  __int64 v47; // [rsp+90h] [rbp-39h] BYREF
  __int64 v48; // [rsp+98h] [rbp-31h] BYREF
  __int64 v49; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v50; // [rsp+A8h] [rbp-21h] BYREF
  wchar_t *String1; // [rsp+B0h] [rbp-19h] BYREF
  _BYTE v52[56]; // [rsp+B8h] [rbp-11h] BYREF

  v48 = 0;
  v36 = 0;
  v37 = 0;
  v43 = 0;
  v44 = 0;
  v42 = 0;
  v47 = 0;
  v38 = 0;
  v41 = 0;
  Str = 0;
  STRU::STRU((STRU *)v52);
  v4 = *a2;
  v46 = 0;
  v50 = 0;
  v49 = 0;
  v5 = v4[1];
  v45 = 0;
  v39 = 0;
  v40 = 0;
  String1 = 0;
  v6 = v5((struct IHttpContext *)a2);
  v7 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v8 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 56LL))(s_pGlobalInfo);
  v10 = (**v8)(v8, &IID_INativeConfigurationSystem, &v48);
  if ( v10 < 0 )
    goto LABEL_64;
  v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 *, _QWORD, _QWORD))(*(_QWORD *)v48 + 24LL))(
          v48,
          L"system.webServer/security/authentication/windowsAuthentication",
          v7,
          &v36,
          0,
          0);
  if ( v10 < 0 )
    goto LABEL_64;
  v12 = (_DWORD *)((char *)this + 8);
  v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v36 + 72LL))(
          v36,
          L"useKernelMode",
          (char *)this + 8,
          0,
          0);
  if ( v10 < 0 )
    goto LABEL_64;
  if ( *v12 )
  {
    v13 = v36;
    *((_BYTE *)this + 25) = 1;
    v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v13 + 72LL))(
            v13,
            L"authPersistSingleRequest",
            &v37,
            0,
            0);
    if ( v10 < 0 )
      goto LABEL_64;
    v14 = v36;
    *((_BYTE *)this + 26) = v37 != 0;
    v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v14 + 72LL))(
            v14,
            L"authPersistNonNTLM",
            &v43,
            0,
            0);
    if ( v10 < 0 )
      goto LABEL_64;
    if ( v37 || (v15 = 1, !v43) )
      v15 = 0;
    v16 = v36;
    *((_BYTE *)this + 27) = v15;
    v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *, _QWORD, _QWORD))(*(_QWORD *)v16 + 72LL))(
            v16,
            L"useAppPoolCredentials",
            &v44,
            0,
            0);
    if ( v10 < 0 )
      goto LABEL_64;
    *((_BYTE *)this + 27) |= v44 != 0 ? 2 : 0;
  }
  v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v36 + 32LL))(
          v36,
          L"extendedProtection",
          &v42);
  if ( v10 >= 0 )
  {
    v17 = (int *)((char *)this + 80);
    v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v42 + 48LL))(
            v42,
            L"tokenChecking",
            (char *)this + 80,
            0,
            0);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v42 + 48LL))(
              v42,
              L"flags",
              (char *)this + 84,
              0,
              0);
      if ( v10 >= 0 )
      {
        if ( !*v12 && *v17 > 0 )
          *((_DWORD *)this + 21) |= 8u;
        v18 = *((_DWORD *)this + 21);
        v9 = (wchar_t *)(v18 & 0x20);
        if ( (v18 & 0x20) != 0 && (v18 & 1) == 0 )
          goto LABEL_20;
        if ( *v17 == 1 && (v18 & 1) != 0 && (v18 & 0x20) != 0 )
        {
          if ( (v18 & 2) != 0 )
          {
LABEL_20:
            v10 = -2147024809;
            goto LABEL_64;
          }
        }
        else if ( (v18 & 2) != 0 )
        {
          *((_DWORD *)this + 24) = 0;
          goto LABEL_64;
        }
        v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v42 + 40LL))(v42, &v47);
        if ( v10 >= 0 )
        {
          v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v47 + 24LL))(v47, &v38);
          if ( v10 >= 0 )
          {
            v19 = v38;
            v20 = 0;
            if ( v38 )
            {
              while ( 1 )
              {
                v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v47 + 32LL))(v47, v20, &v41);
                if ( v10 < 0 )
                  break;
                v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v41 + 64LL))(
                        v41,
                        L"name",
                        &Str,
                        0,
                        0);
                if ( v10 < 0 )
                  break;
                if ( (*((_BYTE *)this + 84) & 4) == 0 && !wcschr(Str, 0x2Eu) )
                  goto LABEL_20;
                if ( !MULTISZ::Append((SSPI_APP_CONTEXT *)((char *)this + 104), Str) )
                  goto LABEL_87;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
                v19 = v38;
                ++v20;
                v41 = 0;
                if ( v20 >= v38 )
                  goto LABEL_34;
              }
            }
            else
            {
LABEL_34:
              v21 = v48;
              *((_DWORD *)this + 24) = v19;
              v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v21 + 56LL))(v21, &v46);
              if ( v10 >= 0 )
              {
                v22 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *, _QWORD))(*(_QWORD *)v46 + 32LL);
                v23 = (__int64 (__fastcall ***)(_QWORD))(**a2)((struct IHttpContext *)a2);
                v24 = (**v23)(v23);
                v10 = v22(v46, v24, &v50, 0);
                if ( v10 >= 0 )
                {
                  v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v50 + 32LL))(
                          v50,
                          L"bindings",
                          &v49);
                  if ( v10 >= 0 )
                  {
                    v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v49 + 40LL))(v49, &v45);
                    if ( v10 >= 0 )
                    {
                      v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v45 + 24LL))(v45, &v39);
                      if ( v10 >= 0 )
                      {
                        v25 = 0;
                        if ( v39 )
                        {
                          while ( 1 )
                          {
                            v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v45 + 32LL))(
                                    v45,
                                    v25,
                                    &v40);
                            if ( v10 < 0 )
                              break;
                            v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v40 + 64LL))(
                                    v40,
                                    L"protocol",
                                    &String1,
                                    0,
                                    0);
                            if ( v10 < 0 )
                              break;
                            if ( !wcscmp_0(String1, L"http") || !wcscmp_0(String1, L"https") )
                            {
                              v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v40 + 64LL))(
                                      v40,
                                      L"bindingInformation",
                                      &Str,
                                      0,
                                      0);
                              if ( v10 < 0 )
                                break;
                              v26 = wcschr(Str, 0x3Au);
                              Str = v26;
                              if ( v26 )
                              {
                                v27 = wcschr(v26 + 1, 0x3Au);
                                Str = v27;
                                if ( v27 )
                                {
                                  Str = v27 + 1;
                                  if ( v27[1] )
                                  {
                                    if ( (*((_BYTE *)this + 84) & 4) != 0 || wcschr(v27 + 1, 0x2Eu) )
                                    {
                                      v10 = STRU::Copy((STRU *)v52, L"HTTP/", 5u);
                                      if ( v10 < 0 )
                                        break;
                                      v10 = STRU::Append((STRU *)v52, Str);
                                      if ( v10 < 0 )
                                        break;
                                      if ( !MULTISZ::Append(
                                              (SSPI_APP_CONTEXT *)((char *)this + 104),
                                              (struct STRU *)v52) )
                                        goto LABEL_87;
                                      ++*((_DWORD *)this + 24);
                                    }
                                  }
                                }
                              }
                            }
                            (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
                            ++v25;
                            v40 = 0;
                            if ( v25 >= v39 )
                              goto LABEL_55;
                          }
                        }
                        else
                        {
LABEL_55:
                          if ( *((_DWORD *)this + 24) )
                          {
                            v28 = LocalAlloc(0, 24LL * *((unsigned int *)this + 24));
                            *((_QWORD *)this + 20) = v28;
                            if ( v28
                              && (v29 = LocalAlloc(0, 8LL * *((unsigned int *)this + 24)),
                                  (*((_QWORD *)this + 11) = v29) != 0) )
                            {
                              v30 = (wchar_t *)MULTISZ::First((SSPI_APP_CONTEXT *)((char *)this + 104));
                              v11 = 0;
                              for ( Str = v30;
                                    (unsigned int)v11 < *((_DWORD *)this + 24);
                                    Str = (wchar_t *)((unsigned __int64)v9 & -(__int64)(*v9 != 0)) )
                              {
                                v31 = 3LL * (unsigned int)v11;
                                *(_QWORD *)(*((_QWORD *)this + 11) + 8LL * (unsigned int)v11) = *((_QWORD *)this + 20)
                                                                                              + 24LL * (unsigned int)v11;
                                *(_DWORD *)(*((_QWORD *)this + 20) + 8 * v31) = 1;
                                *(_QWORD *)(*((_QWORD *)this + 20) + 8 * v31 + 8) = Str;
                                v32 = -1;
                                do
                                  ++v32;
                                while ( Str[v32] );
                                *(_DWORD *)(*((_QWORD *)this + 20) + 24LL * (unsigned int)v11 + 16) = 2 * v32;
                                v33 = -1;
                                do
                                  ++v33;
                                while ( Str[v33] );
                                v9 = &Str[v33 + 1];
                                v11 = (unsigned int)(v11 + 1);
                              }
                            }
                            else
                            {
LABEL_87:
                              v10 = -2147024888;
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
LABEL_64:
  if ( v40 )
  {
    (*(void (__fastcall **)(__int64, wchar_t *, __int64))(*(_QWORD *)v40 + 16LL))(v40, v9, v11);
    v40 = 0;
  }
  if ( v45 )
  {
    (*(void (__fastcall **)(__int64, wchar_t *, __int64))(*(_QWORD *)v45 + 16LL))(v45, v9, v11);
    v45 = 0;
  }
  if ( v49 )
  {
    (*(void (__fastcall **)(__int64, wchar_t *, __int64))(*(_QWORD *)v49 + 16LL))(v49, v9, v11);
    v49 = 0;
  }
  if ( v50 )
  {
    (*(void (__fastcall **)(__int64, wchar_t *, __int64))(*(_QWORD *)v50 + 16LL))(v50, v9, v11);
    v50 = 0;
  }
  if ( v46 )
  {
    (*(void (__fastcall **)(__int64, wchar_t *, __int64))(*(_QWORD *)v46 + 16LL))(v46, v9, v11);
    v46 = 0;
  }
  if ( v41 )
  {
    (*(void (__fastcall **)(__int64, wchar_t *, __int64))(*(_QWORD *)v41 + 16LL))(v41, v9, v11);
    v41 = 0;
  }
  if ( v47 )
  {
    (*(void (__fastcall **)(__int64, wchar_t *, __int64))(*(_QWORD *)v47 + 16LL))(v47, v9, v11);
    v47 = 0;
  }
  if ( v42 )
  {
    (*(void (__fastcall **)(__int64, wchar_t *, __int64))(*(_QWORD *)v42 + 16LL))(v42, v9, v11);
    v42 = 0;
  }
  if ( v36 )
  {
    (*(void (__fastcall **)(__int64, wchar_t *, __int64))(*(_QWORD *)v36 + 16LL))(v36, v9, v11);
    v36 = 0;
  }
  if ( v48 )
  {
    (*(void (__fastcall **)(__int64, wchar_t *, __int64))(*(_QWORD *)v48 + 16LL))(v48, v9, v11);
    v48 = 0;
  }
  STRU::~STRU((STRU *)v52);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1800068c0  mov     [rsp-8+arg_10], rbx
0x1800068c5  mov     [rsp-8+arg_18], rsi
0x1800068ca  push    rbp
0x1800068cb  push    rdi
0x1800068cc  push    r12
0x1800068ce  push    r14
0x1800068d0  push    r15
0x1800068d2  lea     rbp, [rsp-37h]
0x1800068d7  sub     rsp, 100h
0x1800068de  mov     rax, cs:__security_cookie
0x1800068e5  xor     rax, rsp
0x1800068e8  mov     [rbp+57h+var_30], rax
0x1800068ec  xor     r12d, r12d
0x1800068ef  mov     rdi, rcx
0x1800068f2  lea     rcx, [rbp+57h+var_68]
0x1800068f6  mov     [rbp+57h+var_88], r12
0x1800068fa  mov     [rsp+120h+var_D8], r12
0x1800068ff  mov     r15, rdx
0x180006902  mov     [rbp+57h+var_D0], r12d
0x180006906  mov     [rbp+57h+var_A8], r12d
0x18000690a  mov     [rbp+57h+var_A4], r12d
0x18000690e  mov     [rbp+57h+var_B0], r12
0x180006912  mov     [rbp+57h+var_90], r12
0x180006916  mov     [rbp+57h+var_CC], r12d
0x18000691a  mov     [rbp+57h+var_B8], r12
0x18000691e  mov     [rsp+120h+Str], r12
0x180006923  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x180006929  mov     rax, [r15]
0x18000692c  mov     rcx, r15
0x18000692f  mov     [rbp+57h+var_98], r12
0x180006933  mov     [rbp+57h+var_78], r12
0x180006937  mov     [rbp+57h+var_80], r12
0x18000693b  mov     rax, [rax+8]
0x18000693f  mov     [rbp+57h+var_A0], r12
0x180006943  mov     [rbp+57h+var_C8], r12d
0x180006947  mov     [rbp+57h+var_C0], r12
0x18000694b  mov     [rbp+57h+String1], r12
0x18000694f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006954  mov     rdx, rax
0x180006957  mov     rcx, [rax]
0x18000695a  mov     rax, [rcx+10h]
0x18000695e  mov     rcx, rdx
0x180006961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006966  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x18000696d  mov     rsi, rax
0x180006970  mov     rdx, [rcx]
0x180006973  mov     rax, [rdx+38h]
0x180006977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000697c  mov     r9, rax
0x18000697f  lea     r8, [rbp+57h+var_88]
0x180006983  lea     rdx, IID_INativeConfigurationSystem
0x18000698a  mov     rcx, [rax]
0x18000698d  mov     rax, [rcx]
0x180006990  mov     rcx, r9
0x180006993  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006998  mov     ebx, eax
0x18000699a  test    eax, eax
0x18000699c  js      loc_180006FCD
0x1800069a2  mov     rcx, [rbp+57h+var_88]
0x1800069a6  lea     r9, [rsp+120h+var_D8]
0x1800069ab  mov     [rsp+120h+var_F8], r12
0x1800069b0  lea     rdx, aSystemWebserve; "system.webServer/security/authenticatio"...
0x1800069b7  mov     r8, rsi
0x1800069ba  mov     [rsp+120h+var_100], r12
0x1800069bf  mov     rax, [rcx]
0x1800069c2  mov     rax, [rax+18h]
0x1800069c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069cb  mov     ebx, eax
0x1800069cd  test    eax, eax
0x1800069cf  js      loc_180006FCD
0x1800069d5  mov     rcx, [rsp+120h+var_D8]
0x1800069da  lea     r14, [rdi+8]
0x1800069de  xor     r9d, r9d
0x1800069e1  mov     [rsp+120h+var_100], r12
0x1800069e6  mov     r8, r14
0x1800069e9  lea     rdx, aUsekernelmode; "useKernelMode"
0x1800069f0  mov     rax, [rcx]
0x1800069f3  mov     rax, [rax+48h]
0x1800069f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069fc  mov     ebx, eax
0x1800069fe  test    eax, eax
0x180006a00  js      loc_180006FCD
0x180006a06  cmp     [r14], r12d
0x180006a09  jz      loc_180006AC8
0x180006a0f  mov     rcx, [rsp+120h+var_D8]
0x180006a14  lea     r8, [rbp+57h+var_D0]
0x180006a18  mov     byte ptr [rdi+19h], 1
0x180006a1c  lea     rdx, aAuthpersistsin; "authPersistSingleRequest"
0x180006a23  xor     r9d, r9d
0x180006a26  mov     [rsp+120h+var_100], r12
0x180006a2b  mov     rax, [rcx]
0x180006a2e  mov     rax, [rax+48h]
0x180006a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a37  mov     ebx, eax
0x180006a39  test    eax, eax
0x180006a3b  js      loc_180006FCD
0x180006a41  cmp     [rbp+57h+var_D0], r12d
0x180006a45  lea     r8, [rbp+57h+var_A8]
0x180006a49  mov     rcx, [rsp+120h+var_D8]
0x180006a4e  lea     rdx, aAuthpersistnon; "authPersistNonNTLM"
0x180006a55  setnz   al
0x180006a58  mov     [rsp+120h+var_100], r12
0x180006a5d  mov     [rdi+1Ah], al
0x180006a60  xor     r9d, r9d
0x180006a63  mov     rax, [rcx]
0x180006a66  mov     rax, [rax+48h]
0x180006a6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a6f  mov     ebx, eax
0x180006a71  test    eax, eax
0x180006a73  js      loc_180006FCD
0x180006a79  cmp     [rbp+57h+var_D0], r12d
0x180006a7d  jnz     short loc_180006A87
0x180006a7f  mov     al, 1
0x180006a81  cmp     [rbp+57h+var_A8], r12d
0x180006a85  jnz     short loc_180006A8A
0x180006a87  mov     al, r12b
0x180006a8a  mov     rcx, [rsp+120h+var_D8]
0x180006a8f  lea     r8, [rbp+57h+var_A4]
0x180006a93  mov     [rdi+1Bh], al
0x180006a96  lea     rdx, aUseapppoolcred; "useAppPoolCredentials"
0x180006a9d  xor     r9d, r9d
0x180006aa0  mov     [rsp+120h+var_100], r12
0x180006aa5  mov     rax, [rcx]
0x180006aa8  mov     rax, [rax+48h]
0x180006aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ab1  mov     ebx, eax
0x180006ab3  test    eax, eax
0x180006ab5  js      loc_180006FCD
0x180006abb  mov     eax, [rbp+57h+var_A4]
0x180006abe  neg     eax
0x180006ac0  sbb     cl, cl
0x180006ac2  and     cl, 2
0x180006ac5  or      [rdi+1Bh], cl
0x180006ac8  mov     rcx, [rsp+120h+var_D8]
0x180006acd  lea     r8, [rbp+57h+var_B0]
0x180006ad1  lea     rdx, aExtendedprotec; "extendedProtection"
0x180006ad8  mov     rax, [rcx]
0x180006adb  mov     rax, [rax+20h]
0x180006adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ae4  mov     ebx, eax
0x180006ae6  test    eax, eax
0x180006ae8  js      loc_180006FCD
0x180006aee  mov     rcx, [rbp+57h+var_B0]
0x180006af2  lea     rsi, [rdi+50h]
0x180006af6  xor     r9d, r9d
0x180006af9  mov     [rsp+120h+var_100], r12
0x180006afe  mov     r8, rsi
0x180006b01  lea     rdx, aTokenchecking; "tokenChecking"
0x180006b08  mov     rax, [rcx]
0x180006b0b  mov     rax, [rax+30h]
0x180006b0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b14  mov     ebx, eax
0x180006b16  test    eax, eax
0x180006b18  js      loc_180006FCD
0x180006b1e  mov     rcx, [rbp+57h+var_B0]
0x180006b22  lea     r8, [rsi+4]
0x180006b26  xor     r9d, r9d
0x180006b29  mov     [rsp+120h+var_100], r12
0x180006b2e  lea     rdx, aFlags; "flags"
0x180006b35  mov     rax, [rcx]
0x180006b38  mov     rax, [rax+30h]
0x180006b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b41  mov     ebx, eax
0x180006b43  test    eax, eax
0x180006b45  js      loc_180006FCD
0x180006b4b  cmp     [r14], r12d
0x180006b4e  jnz     short loc_180006B59
0x180006b50  cmp     [rsi], r12d
0x180006b53  jle     short loc_180006B59
0x180006b55  or      dword ptr [rdi+54h], 8
0x180006b59  mov     ecx, [rdi+54h]
0x180006b5c  mov     eax, ecx
0x180006b5e  and     eax, 1
0x180006b61  mov     edx, ecx
0x180006b63  and     edx, 20h
0x180006b66  jz      short loc_180006B76
0x180006b68  test    eax, eax
0x180006b6a  jnz     short loc_180006B76
0x180006b6c  mov     ebx, 80070057h
0x180006b71  jmp     loc_180006FCD
0x180006b76  cmp     dword ptr [rsi], 1
0x180006b79  jnz     loc_1800070FD
0x180006b7f  test    eax, eax
0x180006b81  jz      loc_1800070FD
0x180006b87  test    edx, edx
0x180006b89  jz      loc_1800070FD
0x180006b8f  test    cl, 2
0x180006b92  jnz     short loc_180006B6C
0x180006b94  mov     rcx, [rbp+57h+var_B0]
0x180006b98  lea     rdx, [rbp+57h+var_90]
0x180006b9c  mov     rax, [rcx]
0x180006b9f  mov     rax, [rax+28h]
0x180006ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ba8  mov     ebx, eax
0x180006baa  test    eax, eax
0x180006bac  js      loc_180006FCD
0x180006bb2  mov     rcx, [rbp+57h+var_90]
0x180006bb6  lea     rdx, [rbp+57h+var_CC]
0x180006bba  mov     rax, [rcx]
0x180006bbd  mov     rax, [rax+18h]
0x180006bc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bc6  mov     ebx, eax
0x180006bc8  test    eax, eax
0x180006bca  js      loc_180006FCD
0x180006bd0  mov     eax, [rbp+57h+var_CC]
0x180006bd3  mov     esi, r12d
0x180006bd6  test    eax, eax
0x180006bd8  jz      loc_180006C83
0x180006bde  mov     rcx, [rbp+57h+var_90]
0x180006be2  lea     r8, [rbp+57h+var_B8]
0x180006be6  mov     edx, esi
0x180006be8  mov     rax, [rcx]
0x180006beb  mov     rax, [rax+20h]
0x180006bef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bf4  mov     ebx, eax
0x180006bf6  test    eax, eax
0x180006bf8  js      loc_180006FCD
0x180006bfe  mov     rcx, [rbp+57h+var_B8]
0x180006c02  lea     r8, [rsp+120h+Str]
0x180006c07  xor     r9d, r9d
0x180006c0a  mov     [rsp+120h+var_100], r12
0x180006c0f  lea     rdx, aName; "name"
0x180006c16  mov     rax, [rcx]
0x180006c19  mov     rax, [rax+40h]
0x180006c1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c22  mov     ebx, eax
0x180006c24  test    eax, eax
0x180006c26  js      loc_180006FCD
0x180006c2c  test    byte ptr [rdi+54h], 4
0x180006c30  jnz     short loc_180006C4B
0x180006c32  mov     rcx, [rsp+120h+Str]; Str
0x180006c37  mov     edx, 2Eh ; '.'; Ch
0x180006c3c  call    cs:__imp_wcschr
0x180006c42  test    rax, rax
0x180006c45  jz      loc_180006B6C
0x180006c4b  mov     rdx, [rsp+120h+Str]
0x180006c50  lea     rcx, [rdi+68h]
0x180006c54  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x180006c5a  test    eax, eax
0x180006c5c  jz      loc_18000710F
0x180006c62  mov     rcx, [rbp+57h+var_B8]
0x180006c66  mov     rax, [rcx]
0x180006c69  mov     rax, [rax+10h]
0x180006c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c72  mov     eax, [rbp+57h+var_CC]
0x180006c75  inc     esi
0x180006c77  mov     [rbp+57h+var_B8], r12
0x180006c7b  cmp     esi, eax
0x180006c7d  jb      loc_180006BDE
0x180006c83  mov     rcx, [rbp+57h+var_88]
0x180006c87  lea     rdx, [rbp+57h+var_98]
0x180006c8b  mov     [rdi+60h], eax
0x180006c8e  mov     rax, [rcx]
0x180006c91  mov     rax, [rax+38h]
0x180006c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c9a  mov     ebx, eax
0x180006c9c  test    eax, eax
0x180006c9e  js      loc_180006FCD
0x180006ca4  mov     rax, [rbp+57h+var_98]
0x180006ca8  mov     rcx, r15
0x180006cab  mov     rdx, [rax]
0x180006cae  mov     rax, [r15]
0x180006cb1  mov     rbx, [rdx+20h]
0x180006cb5  mov     rax, [rax]
0x180006cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cbd  mov     rdx, rax
0x180006cc0  mov     rcx, [rax]
0x180006cc3  mov     rax, [rcx]
0x180006cc6  mov     rcx, rdx
0x180006cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cce  mov     rcx, [rbp+57h+var_98]
0x180006cd2  lea     r8, [rbp+57h+var_78]
0x180006cd6  mov     edx, eax
0x180006cd8  xor     r9d, r9d
0x180006cdb  mov     rax, rbx
0x180006cde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ce3  mov     ebx, eax
0x180006ce5  test    eax, eax
0x180006ce7  js      loc_180006FCD
0x180006ced  mov     rcx, [rbp+57h+var_78]
0x180006cf1  lea     r8, [rbp+57h+var_80]
0x180006cf5  lea     rdx, aBindings; "bindings"
0x180006cfc  mov     rax, [rcx]
0x180006cff  mov     rax, [rax+20h]
0x180006d03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d08  mov     ebx, eax
0x180006d0a  test    eax, eax
0x180006d0c  js      loc_180006FCD
0x180006d12  mov     rcx, [rbp+57h+var_80]
0x180006d16  lea     rdx, [rbp+57h+var_A0]
0x180006d1a  mov     rax, [rcx]
0x180006d1d  mov     rax, [rax+28h]
0x180006d21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d26  mov     ebx, eax
0x180006d28  test    eax, eax
0x180006d2a  js      loc_180006FCD
0x180006d30  mov     rcx, [rbp+57h+var_A0]
0x180006d34  lea     rdx, [rbp+57h+var_C8]
0x180006d38  mov     rax, [rcx]
0x180006d3b  mov     rax, [rax+18h]
  ... truncated ...
```
