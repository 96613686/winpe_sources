# SSPI_META_STORED_CONTEXT::Initialize(IHttpContext *,INativeSectionException * *)

- ea: `0x180006204`
- end: `0x1800066c4`
- name: `?Initialize@SSPI_META_STORED_CONTEXT@@QEAAJPEAVIHttpContext@@PEAPEAVINativeSectionException@@@Z`
- size: `1216`
- prototype: `__int64 __fastcall(SSPI_META_STORED_CONTEXT *__hidden this, struct IHttpContext *, struct INativeSectionException **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180005ff0`

## callees

- `0x180006204`
- `0x180009010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000653a`
- `msvcrt!_wcsnicmp` at `0x18000653a`
- `msvcrt!_wcsicmp` at `0x18000645c`
- `msvcrt!_wcsicmp` at `0x18000647a`
- `msvcrt!_wcsicmp` at `0x1800064a5`
- `msvcrt!_wcsicmp` at `0x1800064c1`
- `msvcrt!_wcsicmp` at `0x18000656d`
- `msvcrt!_wcsicmp` at `0x180006582`
- `msvcrt!_wcsicmp` at `0x18000645c`
- `msvcrt!_wcsicmp` at `0x18000647a`
- `msvcrt!_wcsicmp` at `0x1800064a5`
- `msvcrt!_wcsicmp` at `0x1800064c1`
- `msvcrt!_wcsicmp` at `0x18000656d`
- `msvcrt!_wcsicmp` at `0x180006582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006620`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006620`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800064d6`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800064ef`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180006554`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800064d6`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x1800064ef`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180006554`
- `iisutil!?AppendW@MULTISZA@@QEAAHPEBG@Z` at `0x1800065a5`
- `iisutil!?AppendW@MULTISZA@@QEAAHPEBG@Z` at `0x1800065c1`
- `iisutil!?AppendW@MULTISZA@@QEAAHPEBG@Z` at `0x1800065a5`
- `iisutil!?AppendW@MULTISZA@@QEAAHPEBG@Z` at `0x1800065c1`

## string_xrefs

- `0x1800062a8`: `system.webServer/security/authentication/windowsAuthentication`

## pseudocode

```c
__int64 __fastcall SSPI_META_STORED_CONTEXT::Initialize(
        SSPI_META_STORED_CONTEXT *this,
        struct IHttpContext *a2,
        struct INativeSectionException **a3)
{
  __int64 v3; // rax
  __int64 (__fastcall *v6)(struct IHttpContext *); // rax
  __int64 (__fastcall ***v7)(_QWORD); // rax
  __int64 v8; // r14
  __int64 (__fastcall ***v9)(_QWORD, GUID *, __int64 *); // rax
  signed int v10; // ebx
  __int64 v11; // rax
  __int64 *v13; // rcx
  int v14; // esi
  unsigned int v15; // r14d
  wchar_t *v16; // rdx
  wchar_t *v17; // rax
  unsigned __int64 v18; // rcx
  signed int LastError; // eax
  __int64 *v20; // [rsp+40h] [rbp-30h] BYREF
  __int64 v21; // [rsp+48h] [rbp-28h] BYREF
  __int64 v22; // [rsp+50h] [rbp-20h] BYREF
  __int64 v23; // [rsp+58h] [rbp-18h] BYREF
  __int64 v24; // [rsp+60h] [rbp-10h] BYREF
  unsigned int v25; // [rsp+A8h] [rbp+38h] BYREF
  wchar_t *String1; // [rsp+B8h] [rbp+48h] BYREF

  v3 = *(_QWORD *)a2;
  v24 = 0;
  v20 = 0;
  v21 = 0;
  v6 = *(__int64 (__fastcall **)(struct IHttpContext *))(v3 + 160);
  v23 = 0;
  v22 = 0;
  String1 = 0;
  v25 = 0;
  v7 = (__int64 (__fastcall ***)(_QWORD))v6(a2);
  v8 = (**v7)(v7);
  v9 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)s_pGlobalInfo + 56LL))(s_pGlobalInfo);
  v10 = (**v9)(v9, &IID_INativeConfigurationSystem, &v24);
  if ( v10 >= 0 )
  {
    v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64, __int64 **, struct INativeSectionException **, _QWORD))(*(_QWORD *)v24 + 24LL))(
            v24,
            L"system.webServer/security/authentication/windowsAuthentication",
            v8,
            &v20,
            a3,
            0);
    if ( v10 >= 0 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, char *, _QWORD, _QWORD))(*v20 + 72))(
              v20,
              L"enabled",
              (char *)this + 8,
              0,
              0);
      if ( v10 >= 0 )
      {
        v11 = *v20;
        if ( !*((_DWORD *)this + 2) )
        {
LABEL_5:
          (*(void (**)(void))(v11 + 16))();
          v20 = 0;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
          return 0;
        }
        v10 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, char *, _QWORD, _QWORD))(v11 + 72))(
                v20,
                L"authPersistSingleRequest",
                (char *)this + 132,
                0,
                0);
        if ( v10 >= 0 )
        {
          v13 = v20;
          *((_DWORD *)this + 33) = *((_DWORD *)this + 33) == 0;
          v10 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, char *, _QWORD, _QWORD))(*v13 + 72))(
                  v13,
                  L"authPersistNonNTLM",
                  (char *)this + 136,
                  0,
                  0);
          if ( v10 >= 0 )
          {
            v10 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64 *))(*v20 + 32))(
                    v20,
                    L"providers",
                    &v23);
            if ( v10 >= 0 )
            {
              v10 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 40LL))(v23, &v21);
              if ( v10 >= 0 )
              {
                v10 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v21 + 24LL))(v21, &v25);
                if ( v10 >= 0 )
                {
                  v14 = 0;
                  v15 = 0;
                  if ( !v25 )
                  {
LABEL_41:
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
                    v21 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
                    v23 = 0;
                    v11 = *v20;
                    goto LABEL_5;
                  }
                  while ( 1 )
                  {
                    v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v21 + 32LL))(
                            v21,
                            v15,
                            &v22);
                    if ( v10 < 0 )
                      break;
                    v10 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v22 + 64LL))(
                            v22,
                            L"value",
                            &String1,
                            0,
                            0);
                    if ( v10 < 0 )
                      break;
                    if ( _wcsicmp(String1, L"NTLM") )
                    {
                      if ( _wcsicmp(String1, L"Negotiate") )
                      {
                        if ( *((_DWORD *)s_pSSPIAuthProvider + 5) && !_wcsicmp(String1, L"Kerberos") )
                          *((_DWORD *)this + 32) |= 0x10u;
                      }
                      else
                      {
                        *((_DWORD *)this + 32) |= 8u;
                      }
                    }
                    else
                    {
                      *((_DWORD *)this + 32) |= 4u;
                    }
                    if ( _wcsicmp(String1, L"Negotiate") )
                    {
                      v17 = String1;
                      v18 = -1;
                      do
                        ++v18;
                      while ( String1[v18] );
                      if ( v18 >= 0xB )
                      {
                        if ( !_wcsnicmp(String1, L"Negotiate:", 0xAu) )
                        {
                          String1 += 10;
                          if ( !MULTISZ::Append((SSPI_META_STORED_CONTEXT *)((char *)this + 72), String1) )
                            goto LABEL_42;
                          if ( _wcsicmp(String1, L"NTLM") && _wcsicmp(String1, L"Kerberos") )
                            *((_DWORD *)this + 35) = 1;
                          if ( v14 )
                            goto LABEL_40;
                          v16 = (wchar_t *)L"Negotiate";
                          goto LABEL_36;
                        }
                        v17 = String1;
                      }
                      if ( !MULTISZA::AppendW((SSPI_META_STORED_CONTEXT *)((char *)this + 16), v17) )
                        goto LABEL_42;
                    }
                    else
                    {
                      if ( !MULTISZ::Append((SSPI_META_STORED_CONTEXT *)((char *)this + 72), L"NTLM")
                        || !MULTISZ::Append((SSPI_META_STORED_CONTEXT *)((char *)this + 72), L"Kerberos") )
                      {
LABEL_42:
                        LastError = GetLastError();
                        v10 = LastError;
                        if ( LastError > 0 )
                          v10 = (unsigned __int16)LastError | 0x80070000;
                        break;
                      }
                      if ( !v14 )
                      {
                        v16 = String1;
LABEL_36:
                        if ( !MULTISZA::AppendW((SSPI_META_STORED_CONTEXT *)((char *)this + 16), v16) )
                          goto LABEL_42;
                        v14 = 1;
                      }
                    }
LABEL_40:
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
                    ++v15;
                    v22 = 0;
                    if ( v15 >= v25 )
                      goto LABEL_41;
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  if ( v22 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    v22 = 0;
  }
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
  }
  if ( v21 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v21 = 0;
  }
  if ( v20 )
  {
    (*(void (__fastcall **)(__int64 *))(*v20 + 16))(v20);
    v20 = 0;
  }
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180006204  mov     [rsp-28h+arg_0], rbx
0x180006209  push    rbp
0x18000620a  push    rsi
0x18000620b  push    rdi
0x18000620c  push    r14
0x18000620e  push    r15
0x180006210  mov     rbp, rsp
0x180006213  sub     rsp, 70h
0x180006217  mov     rax, [rdx]
0x18000621a  xor     r15d, r15d
0x18000621d  mov     rdi, rcx
0x180006220  mov     [rbp+var_10], r15
0x180006224  mov     rcx, rdx
0x180006227  mov     [rbp+var_30], r15
0x18000622b  mov     rsi, r8
0x18000622e  mov     [rbp+var_28], r15
0x180006232  mov     rax, [rax+0A0h]
0x180006239  mov     [rbp+var_18], r15
0x18000623d  mov     [rbp+var_20], r15
0x180006241  mov     [rbp+String1], r15
0x180006245  mov     [rbp+arg_8], r15d
0x180006249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000624e  mov     rdx, rax
0x180006251  mov     rcx, [rax]
0x180006254  mov     rax, [rcx]
0x180006257  mov     rcx, rdx
0x18000625a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000625f  mov     rcx, cs:?s_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * s_pGlobalInfo
0x180006266  mov     r14, rax
0x180006269  mov     rdx, [rcx]
0x18000626c  mov     rax, [rdx+38h]
0x180006270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006275  mov     r9, rax
0x180006278  lea     r8, [rbp+var_10]
0x18000627c  lea     rdx, IID_INativeConfigurationSystem
0x180006283  mov     rcx, [rax]
0x180006286  mov     rax, [rcx]
0x180006289  mov     rcx, r9
0x18000628c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006291  mov     ebx, eax
0x180006293  test    eax, eax
0x180006295  js      loc_180006635
0x18000629b  mov     rcx, [rbp+var_10]
0x18000629f  lea     r9, [rbp+var_30]
0x1800062a3  mov     [rsp+70h+var_48], r15
0x1800062a8  lea     rdx, aSystemWebserve; "system.webServer/security/authenticatio"...
0x1800062af  mov     r8, r14
0x1800062b2  mov     [rsp+70h+var_50], rsi
0x1800062b7  mov     rax, [rcx]
0x1800062ba  mov     rax, [rax+18h]
0x1800062be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062c3  mov     ebx, eax
0x1800062c5  test    eax, eax
0x1800062c7  js      loc_180006635
0x1800062cd  mov     rcx, [rbp+var_30]
0x1800062d1  lea     r8, [rdi+8]
0x1800062d5  xor     r9d, r9d
0x1800062d8  mov     [rsp+70h+var_50], r15
0x1800062dd  lea     rdx, aEnabled; "enabled"
0x1800062e4  mov     rax, [rcx]
0x1800062e7  mov     rax, [rax+48h]
0x1800062eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062f0  mov     ebx, eax
0x1800062f2  test    eax, eax
0x1800062f4  js      loc_180006635
0x1800062fa  mov     rcx, [rbp+var_30]
0x1800062fe  mov     rax, [rcx]
0x180006301  cmp     [rdi+8], r15d
0x180006305  jnz     short loc_18000632B
0x180006307  mov     rax, [rax+10h]
0x18000630b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006310  mov     rcx, [rbp+var_10]
0x180006314  mov     [rbp+var_30], r15
0x180006318  mov     rax, [rcx]
0x18000631b  mov     rax, [rax+10h]
0x18000631f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006324  xor     eax, eax
0x180006326  jmp     loc_1800066B0
0x18000632b  mov     rax, [rax+48h]
0x18000632f  lea     rsi, [rdi+84h]
0x180006336  mov     r8, rsi
0x180006339  mov     [rsp+70h+var_50], r15
0x18000633e  xor     r9d, r9d
0x180006341  lea     rdx, aAuthpersistsin; "authPersistSingleRequest"
0x180006348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000634d  mov     ebx, eax
0x18000634f  test    eax, eax
0x180006351  js      loc_180006635
0x180006357  cmp     [rsi], r15d
0x18000635a  lea     r8, [rdi+88h]
0x180006361  mov     rcx, [rbp+var_30]
0x180006365  lea     rdx, aAuthpersistnon; "authPersistNonNTLM"
0x18000636c  mov     eax, r15d
0x18000636f  mov     [rsp+70h+var_50], r15
0x180006374  setz    al
0x180006377  xor     r9d, r9d
0x18000637a  mov     [rsi], eax
0x18000637c  mov     rax, [rcx]
0x18000637f  mov     rax, [rax+48h]
0x180006383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006388  mov     ebx, eax
0x18000638a  test    eax, eax
0x18000638c  js      loc_180006635
0x180006392  mov     rcx, [rbp+var_30]
0x180006396  lea     r8, [rbp+var_18]
0x18000639a  lea     rdx, aProviders; "providers"
0x1800063a1  mov     rax, [rcx]
0x1800063a4  mov     rax, [rax+20h]
0x1800063a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063ad  mov     ebx, eax
0x1800063af  test    eax, eax
0x1800063b1  js      loc_180006635
0x1800063b7  mov     rcx, [rbp+var_18]
0x1800063bb  lea     rdx, [rbp+var_28]
0x1800063bf  mov     rax, [rcx]
0x1800063c2  mov     rax, [rax+28h]
0x1800063c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063cb  mov     ebx, eax
0x1800063cd  test    eax, eax
0x1800063cf  js      loc_180006635
0x1800063d5  mov     rcx, [rbp+var_28]
0x1800063d9  lea     rdx, [rbp+arg_8]
0x1800063dd  mov     rax, [rcx]
0x1800063e0  mov     rax, [rax+18h]
0x1800063e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063e9  mov     ebx, eax
0x1800063eb  test    eax, eax
0x1800063ed  js      loc_180006635
0x1800063f3  mov     esi, r15d
0x1800063f6  mov     r14d, r15d
0x1800063f9  cmp     [rbp+arg_8], r15d
0x1800063fd  jbe     loc_1800065EC
0x180006403  mov     rcx, [rbp+var_28]
0x180006407  lea     r8, [rbp+var_20]
0x18000640b  mov     edx, r14d
0x18000640e  mov     rax, [rcx]
0x180006411  mov     rax, [rax+20h]
0x180006415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000641a  mov     ebx, eax
0x18000641c  test    eax, eax
0x18000641e  js      loc_180006635
0x180006424  mov     rcx, [rbp+var_20]
0x180006428  lea     r8, [rbp+String1]
0x18000642c  xor     r9d, r9d
0x18000642f  mov     [rsp+70h+var_50], r15
0x180006434  lea     rdx, aValue; "value"
0x18000643b  mov     rax, [rcx]
0x18000643e  mov     rax, [rax+40h]
0x180006442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006447  mov     ebx, eax
0x180006449  test    eax, eax
0x18000644b  js      loc_180006635
0x180006451  mov     rcx, [rbp+String1]; String1
0x180006455  lea     rdx, aNtlm_0; "NTLM"
0x18000645c  call    cs:__imp__wcsicmp
0x180006462  test    eax, eax
0x180006464  jnz     short loc_18000646F
0x180006466  or      dword ptr [rdi+80h], 4
0x18000646d  jmp     short loc_1800064B6
0x18000646f  mov     rcx, [rbp+String1]; String1
0x180006473  lea     rdx, aNegotiate; "Negotiate"
0x18000647a  call    cs:__imp__wcsicmp
0x180006480  test    eax, eax
0x180006482  jnz     short loc_18000648D
0x180006484  or      dword ptr [rdi+80h], 8
0x18000648b  jmp     short loc_1800064B6
0x18000648d  mov     rax, cs:?s_pSSPIAuthProvider@@3PEAVSSPI_AUTH_PROVIDER@@EA; SSPI_AUTH_PROVIDER * s_pSSPIAuthProvider
0x180006494  cmp     [rax+14h], r15d
0x180006498  jz      short loc_1800064B6
0x18000649a  mov     rcx, [rbp+String1]; String1
0x18000649e  lea     rdx, aKerberos; "Kerberos"
0x1800064a5  call    cs:__imp__wcsicmp
0x1800064ab  test    eax, eax
0x1800064ad  jnz     short loc_1800064B6
0x1800064af  or      dword ptr [rdi+80h], 10h
0x1800064b6  mov     rcx, [rbp+String1]; String1
0x1800064ba  lea     rdx, aNegotiate; "Negotiate"
0x1800064c1  call    cs:__imp__wcsicmp
0x1800064c7  test    eax, eax
0x1800064c9  jnz     short loc_18000650E
0x1800064cb  lea     rdx, aNtlm_0; "NTLM"
0x1800064d2  lea     rcx, [rdi+48h]
0x1800064d6  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x1800064dc  test    eax, eax
0x1800064de  jz      loc_180006620
0x1800064e4  lea     rdx, aKerberos; "Kerberos"
0x1800064eb  lea     rcx, [rdi+48h]
0x1800064ef  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x1800064f5  test    eax, eax
0x1800064f7  jz      loc_180006620
0x1800064fd  test    esi, esi
0x1800064ff  jnz     loc_1800065CB
0x180006505  mov     rdx, [rbp+String1]
0x180006509  jmp     loc_1800065A1
0x18000650e  mov     rax, [rbp+String1]
0x180006512  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180006516  inc     rcx
0x180006519  cmp     [rax+rcx*2], r15w
0x18000651e  jnz     short loc_180006516
0x180006520  cmp     rcx, 0Bh
0x180006524  jb      loc_1800065BA
0x18000652a  mov     r8d, 0Ah; MaxCount
0x180006530  lea     rdx, aNegotiate_1; "Negotiate:"
0x180006537  mov     rcx, rax; String1
0x18000653a  call    cs:__imp__wcsnicmp
0x180006540  test    eax, eax
0x180006542  jnz     short loc_1800065B6
0x180006544  mov     rdx, [rbp+String1]
0x180006548  lea     rcx, [rdi+48h]
0x18000654c  add     rdx, 14h
0x180006550  mov     [rbp+String1], rdx
0x180006554  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x18000655a  test    eax, eax
0x18000655c  jz      loc_180006620
0x180006562  mov     rcx, [rbp+String1]; String1
0x180006566  lea     rdx, aNtlm_0; "NTLM"
0x18000656d  call    cs:__imp__wcsicmp
0x180006573  test    eax, eax
0x180006575  jz      short loc_180006596
0x180006577  mov     rcx, [rbp+String1]; String1
0x18000657b  lea     rdx, aKerberos; "Kerberos"
0x180006582  call    cs:__imp__wcsicmp
0x180006588  test    eax, eax
0x18000658a  jz      short loc_180006596
0x18000658c  mov     dword ptr [rdi+8Ch], 1
0x180006596  test    esi, esi
0x180006598  jnz     short loc_1800065CB
0x18000659a  lea     rdx, aNegotiate; "Negotiate"
0x1800065a1  lea     rcx, [rdi+10h]
0x1800065a5  call    cs:__imp_?AppendW@MULTISZA@@QEAAHPEBG@Z; MULTISZA::AppendW(ushort const *)
0x1800065ab  test    eax, eax
0x1800065ad  jz      short loc_180006620
0x1800065af  mov     esi, 1
0x1800065b4  jmp     short loc_1800065CB
0x1800065b6  mov     rax, [rbp+String1]
0x1800065ba  lea     rcx, [rdi+10h]
0x1800065be  mov     rdx, rax
0x1800065c1  call    cs:__imp_?AppendW@MULTISZA@@QEAAHPEBG@Z; MULTISZA::AppendW(ushort const *)
0x1800065c7  test    eax, eax
0x1800065c9  jz      short loc_180006620
0x1800065cb  mov     rcx, [rbp+var_20]
0x1800065cf  mov     rax, [rcx]
0x1800065d2  mov     rax, [rax+10h]
0x1800065d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065db  inc     r14d
0x1800065de  mov     [rbp+var_20], r15
0x1800065e2  cmp     r14d, [rbp+arg_8]
0x1800065e6  jb      loc_180006403
0x1800065ec  mov     rcx, [rbp+var_28]
0x1800065f0  mov     rax, [rcx]
0x1800065f3  mov     rax, [rax+10h]
0x1800065f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065fc  mov     rcx, [rbp+var_18]
0x180006600  mov     [rbp+var_28], r15
0x180006604  mov     rax, [rcx]
0x180006607  mov     rax, [rax+10h]
0x18000660b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006610  mov     rcx, [rbp+var_30]
0x180006614  mov     [rbp+var_18], r15
0x180006618  mov     rax, [rcx]
0x18000661b  jmp     loc_180006307
0x180006620  call    cs:__imp_GetLastError
0x180006626  mov     ebx, eax
0x180006628  test    eax, eax
0x18000662a  jle     short loc_180006635
0x18000662c  movzx   ebx, ax
0x18000662f  or      ebx, 80070000h
0x180006635  mov     rcx, [rbp+var_20]
0x180006639  test    rcx, rcx
0x18000663c  jz      short loc_18000664E
0x18000663e  mov     rax, [rcx]
0x180006641  mov     rax, [rax+10h]
0x180006645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000664a  mov     [rbp+var_20], r15
0x18000664e  mov     rcx, [rbp+var_18]
0x180006652  test    rcx, rcx
0x180006655  jz      short loc_180006667
0x180006657  mov     rax, [rcx]
0x18000665a  mov     rax, [rax+10h]
0x18000665e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006663  mov     [rbp+var_18], r15
0x180006667  mov     rcx, [rbp+var_28]
0x18000666b  test    rcx, rcx
0x18000666e  jz      short loc_180006680
0x180006670  mov     rax, [rcx]
0x180006673  mov     rax, [rax+10h]
0x180006677  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000667c  mov     [rbp+var_28], r15
0x180006680  mov     rcx, [rbp+var_30]
0x180006684  test    rcx, rcx
0x180006687  jz      short loc_180006699
0x180006689  mov     rax, [rcx]
0x18000668c  mov     rax, [rax+10h]
0x180006690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006695  mov     [rbp+var_30], r15
0x180006699  mov     rcx, [rbp+var_10]
0x18000669d  test    rcx, rcx
0x1800066a0  jz      short loc_1800066AE
0x1800066a2  mov     rax, [rcx]
0x1800066a5  mov     rax, [rax+10h]
  ... truncated ...
```
