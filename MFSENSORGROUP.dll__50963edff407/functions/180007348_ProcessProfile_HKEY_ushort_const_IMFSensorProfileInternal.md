# ProcessProfile(HKEY__ *,ushort const *,IMFSensorProfileInternal * *)

- ea: `0x180007348`
- end: `0x1800078ff`
- name: `?ProcessProfile@@YAJPEAUHKEY__@@PEBGPEAPEAUIMFSensorProfileInternal@@@Z`
- size: `1463`
- prototype: `int(HKEY, const unsigned __int16 *, struct IMFSensorProfileInternal **)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config`

## callers

- `0x18000b248`

## callees

- `0x180005fa0`
- `0x180007348`
- `0x1800093d4`
- `0x18000a24c`
- `0x18000c388`
- `0x1800357dc`
- `0x180044b1c`
- `0x180044b28`
- `0x180044f30`
- `0x180045900`
- `0x180077010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000759d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18000759d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007489`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800074c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800075e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800076bd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800077fd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180007489`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800074c1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800075e5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800076bd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800077fd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800073cb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800073cb`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000755c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18000755c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800078ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800078ef`

## pseudocode

```c
__int64 __fastcall ProcessProfile(HKEY a1, const unsigned __int16 *a2, struct IMFSensorProfileInternal **a3)
{
  _QWORD *v5; // r15
  unsigned int v6; // r14d
  LSTATUS v7; // eax
  signed int v8; // ebx
  BYTE *v9; // rdi
  int v11; // eax
  DWORD i; // esi
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  __int64 v15; // rdx
  LSTATUS v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rdx
  LSTATUS v19; // eax
  unsigned int j; // esi
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  struct IMFSensorProfileInternal *v24; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cchValueName; // [rsp+58h] [rbp-A8h] BYREF
  void *Block; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v27; // [rsp+68h] [rbp-98h]
  __int64 v28; // [rsp+6Ch] [rbp-94h]
  GUID iid; // [rsp+78h] [rbp-88h] BYREF
  __int64 v30; // [rsp+88h] [rbp-78h]
  WCHAR ValueName[264]; // [rsp+90h] [rbp-70h] BYREF

  v30 = 0;
  hKey = 0;
  Type = 0;
  v24 = 0;
  cbData = 0;
  iid = 0;
  v5 = 0;
  Block = 0;
  v28 = 0;
  v6 = 0;
  v27 = 0;
  v7 = RegOpenKeyExW(a1, a2, 0, 0x20019u, &hKey);
  v8 = v7;
  if ( v7 )
  {
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( v8 < 0 )
    {
      v9 = 0;
      if ( !g_wppLevels )
        goto LABEL_6;
      v17 = 180;
LABEL_53:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids, 0, v8);
      goto LABEL_6;
    }
  }
  if ( !RegQueryValueExW(hKey, L"BlockedControls", 0, &Type, 0, &cbData) )
  {
    cbData += 2;
    v9 = (BYTE *)operator new[](saturated_mul(cbData, 2u));
    if ( !v9 )
    {
      v8 = -2147024882;
      if ( g_wppLevels )
      {
        v15 = 181;
        goto LABEL_56;
      }
      goto LABEL_6;
    }
    v19 = RegQueryValueExW(hKey, L"BlockedControls", 0, &Type, v9, &cbData);
    v8 = v19;
    if ( v19 )
    {
      if ( v19 > 0 )
        v8 = (unsigned __int16)v19 | 0x80070000;
      if ( v8 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_6;
        v17 = 182;
        goto LABEL_53;
      }
    }
    v11 = ParseBlockedControlString(v9, &Block);
    v8 = v11;
    if ( v11 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_6;
      v18 = 183;
      goto LABEL_55;
    }
    operator delete(v9);
    v6 = v27;
    v5 = Block;
  }
  v9 = 0;
  if ( RegQueryValueExW(hKey, L"Constraint", 0, &Type, 0, &cbData) )
  {
LABEL_13:
    v11 = ParseProfileName(a2, &iid);
    v8 = v11;
    if ( v11 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_6;
      v18 = 186;
    }
    else
    {
      v11 = SensorProfile::CreateSensorProfile(
              (const unsigned __int16 *)v9,
              (struct __MIDL___MIDL_itf_mfidl_0000_0114_0001 *)&iid,
              &v24);
      v8 = v11;
      if ( v11 >= 0 )
      {
        for ( i = 0; ; ++i )
        {
          memset_0(ValueName, 0, 0x208u);
          cchValueName = 260;
          operator delete(v9);
          v9 = 0;
          cbData = 0;
          v13 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, &Type, 0, &cbData);
          if ( v13 == 259 )
          {
            for ( j = 0; ; ++j )
            {
              if ( j >= v6 )
              {
                *a3 = v24;
                v24 = 0;
                goto LABEL_6;
              }
              v11 = (*(__int64 (__fastcall **)(struct IMFSensorProfileInternal *, _QWORD))(*(_QWORD *)v24 + 128LL))(
                      v24,
                      v5[j]);
              v8 = v11;
              if ( v11 < 0 )
                break;
            }
            if ( g_wppLevels )
            {
              v18 = 192;
              goto LABEL_55;
            }
            goto LABEL_6;
          }
          if ( v13 )
          {
            if ( v13 <= 0 )
              v8 = v13;
            else
              v8 = (unsigned __int16)v13 | 0x80070000;
            if ( g_wppLevels )
            {
              v17 = 188;
              goto LABEL_53;
            }
            goto LABEL_6;
          }
          v8 = 0;
          if ( !(unsigned int)_o__wcsnicmp(ValueName, L"MTF", 3) )
          {
            cbData += 2;
            v9 = (BYTE *)operator new[](cbData);
            if ( !v9 )
            {
              v8 = -2147024882;
              if ( !g_wppLevels )
                goto LABEL_6;
              v15 = 189;
LABEL_56:
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v15,
                &WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids,
                0,
                -2147024882);
              goto LABEL_6;
            }
            v14 = RegQueryValueExW(hKey, ValueName, 0, &Type, v9, &cbData);
            v8 = v14;
            if ( v14 )
            {
              if ( v14 > 0 )
                v8 = (unsigned __int16)v14 | 0x80070000;
              if ( v8 < 0 )
              {
                if ( !g_wppLevels )
                  goto LABEL_6;
                v17 = 190;
                goto LABEL_53;
              }
            }
            v11 = (*(__int64 (__fastcall **)(struct IMFSensorProfileInternal *, BYTE *))(*(_QWORD *)v24 + 112LL))(
                    v24,
                    v9);
            v8 = v11;
            if ( v11 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_6;
              v18 = 191;
              goto LABEL_55;
            }
          }
        }
      }
      if ( !g_wppLevels )
        goto LABEL_6;
      v18 = 187;
    }
LABEL_55:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids, 0, v11);
    goto LABEL_6;
  }
  cbData += 2;
  v9 = (BYTE *)operator new[](saturated_mul(cbData, 2u));
  if ( v9 )
  {
    v16 = RegQueryValueExW(hKey, L"Constraint", 0, &Type, v9, &cbData);
    v8 = v16;
    if ( v16 )
    {
      if ( v16 > 0 )
        v8 = (unsigned __int16)v16 | 0x80070000;
      if ( v8 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_6;
        v17 = 185;
        goto LABEL_53;
      }
    }
    goto LABEL_13;
  }
  v8 = -2147024882;
  if ( g_wppLevels )
  {
    v15 = 184;
    goto LABEL_56;
  }
LABEL_6:
  operator delete(v9);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  CTUnkArray<IMFSensorProfileFilterSet>::RemoveAll(&Block);
  operator delete(Block);
  if ( v24 )
    (*(void (__fastcall **)(struct IMFSensorProfileInternal *))(*(_QWORD *)v24 + 16LL))(v24);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180007348  mov     [rsp-8+arg_18], rbx
0x18000734d  push    rbp
0x18000734e  push    rsi
0x18000734f  push    rdi
0x180007350  push    r12
0x180007352  push    r13
0x180007354  push    r14
0x180007356  push    r15
0x180007358  lea     rbp, [rsp-1B0h]
0x180007360  sub     rsp, 2B0h
0x180007367  mov     rax, cs:__security_cookie
0x18000736e  xor     rax, rsp
0x180007371  mov     [rbp+1E0h+var_40], rax
0x180007378  xor     r13d, r13d
0x18000737b  xor     eax, eax
0x18000737d  mov     [rbp+1E0h+var_258], rax
0x180007381  mov     r12, r8
0x180007384  lea     rax, [rsp+2E0h+hKey]
0x180007389  mov     [rsp+2E0h+hKey], r13
0x18000738e  xorps   xmm0, xmm0
0x180007391  mov     [rsp+2E0h+phkResult], rax; phkResult
0x180007396  mov     r9d, 20019h; samDesired
0x18000739c  mov     [rsp+2E0h+Type], r13d
0x1800073a1  xor     r8d, r8d; ulOptions
0x1800073a4  mov     [rsp+2E0h+var_290], r13
0x1800073a9  mov     rsi, rdx
0x1800073ac  mov     [rsp+2E0h+cbData], r13d
0x1800073b1  movups  xmmword ptr [rsp+2E0h+iid.Data1], xmm0
0x1800073b6  mov     r15d, r13d
0x1800073b9  mov     [rsp+2E0h+Block], r13
0x1800073be  mov     [rsp+2E0h+var_274], r13
0x1800073c3  mov     r14d, r13d
0x1800073c6  mov     [rsp+2E0h+var_278], r13d
0x1800073cb  call    cs:__imp_RegOpenKeyExW
0x1800073d1  mov     ebx, eax
0x1800073d3  test    eax, eax
0x1800073d5  jz      loc_180007466
0x1800073db  jle     short loc_1800073E6
0x1800073dd  movzx   ebx, ax
0x1800073e0  or      ebx, 80070000h
0x1800073e6  test    ebx, ebx
0x1800073e8  jns     short loc_180007466
0x1800073ea  mov     rdi, r13
0x1800073ed  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800073f4  jnb     loc_1800077A0
0x1800073fa  mov     rcx, rdi; Block
0x1800073fd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007402  mov     rcx, [rsp+2E0h+hKey]; hKey
0x180007407  test    rcx, rcx
0x18000740a  jnz     loc_1800078EF
0x180007410  lea     rcx, [rsp+2E0h+Block]
0x180007415  call    ?RemoveAll@?$CTUnkArray@UIMFSensorProfileFilterSet@@@@QEAAXXZ; CTUnkArray<IMFSensorProfileFilterSet>::RemoveAll(void)
0x18000741a  mov     rcx, [rsp+2E0h+Block]; Block
0x18000741f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007424  mov     rcx, [rsp+2E0h+var_290]
0x180007429  test    rcx, rcx
0x18000742c  jz      short loc_18000743A
0x18000742e  mov     rax, [rcx]
0x180007431  mov     rax, [rax+10h]
0x180007435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000743a  mov     eax, ebx
0x18000743c  mov     rcx, [rbp+1E0h+var_40]
0x180007443  xor     rcx, rsp; StackCookie
0x180007446  call    __security_check_cookie
0x18000744b  mov     rbx, [rsp+2E0h+arg_18]
0x180007453  add     rsp, 2B0h
0x18000745a  pop     r15
0x18000745c  pop     r14
0x18000745e  pop     r13
0x180007460  pop     r12
0x180007462  pop     rdi
0x180007463  pop     rsi
0x180007464  pop     rbp
0x180007465  retn
0x180007466  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18000746b  lea     rax, [rsp+2E0h+cbData]
0x180007470  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x180007475  lea     r9, [rsp+2E0h+Type]; lpType
0x18000747a  xor     r8d, r8d; lpReserved
0x18000747d  mov     [rsp+2E0h+phkResult], r13; lpData
0x180007482  lea     rdx, aBlockedcontrol; "BlockedControls"
0x180007489  call    cs:__imp_RegQueryValueExW
0x18000748f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180007493  test    eax, eax
0x180007495  jz      loc_180007622
0x18000749b  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800074a0  lea     rax, [rsp+2E0h+cbData]
0x1800074a5  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x1800074aa  lea     r9, [rsp+2E0h+Type]; lpType
0x1800074af  xor     r8d, r8d; lpReserved
0x1800074b2  mov     [rsp+2E0h+phkResult], r13; lpData
0x1800074b7  lea     rdx, aConstraint; "Constraint"
0x1800074be  mov     rdi, r13
0x1800074c1  call    cs:__imp_RegQueryValueExW
0x1800074c7  test    eax, eax
0x1800074c9  jz      loc_18000766D
0x1800074cf  lea     rdx, [rsp+2E0h+iid]; lpiid
0x1800074d4  mov     rcx, rsi; unsigned __int16 *
0x1800074d7  call    ?ParseProfileName@@YAJPEBGPEAU__MIDL___MIDL_itf_mfidl_0000_0114_0001@@@Z; ParseProfileName(ushort const *,__MIDL___MIDL_itf_mfidl_0000_0114_0001 *)
0x1800074dc  mov     ebx, eax
0x1800074de  test    eax, eax
0x1800074e0  js      loc_18000786B
0x1800074e6  lea     r8, [rsp+2E0h+var_290]; struct IMFSensorProfileInternal **
0x1800074eb  mov     rcx, rdi; unsigned __int16 *
0x1800074ee  lea     rdx, [rsp+2E0h+iid]; struct __MIDL___MIDL_itf_mfidl_0000_0114_0001 *
0x1800074f3  call    ?CreateSensorProfile@SensorProfile@@SAJPEBGPEAU__MIDL___MIDL_itf_mfidl_0000_0114_0001@@PEAPEAUIMFSensorProfileInternal@@@Z; SensorProfile::CreateSensorProfile(ushort const *,__MIDL___MIDL_itf_mfidl_0000_0114_0001 *,IMFSensorProfileInternal * *)
0x1800074f8  mov     ebx, eax
0x1800074fa  test    eax, eax
0x1800074fc  js      loc_180007882
0x180007502  mov     esi, r13d
0x180007505  xor     edx, edx; Val
0x180007507  lea     rcx, [rbp+1E0h+ValueName]; void *
0x18000750b  mov     r8d, 208h; Size
0x180007511  call    memset_0
0x180007516  mov     rcx, rdi; Block
0x180007519  mov     [rsp+2E0h+cchValueName], 104h
0x180007521  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007526  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18000752b  lea     rax, [rsp+2E0h+cbData]
0x180007530  mov     [rsp+2E0h+var_2A8], rax; lpcbData
0x180007535  lea     r9, [rsp+2E0h+cchValueName]; lpcchValueName
0x18000753a  lea     rax, [rsp+2E0h+Type]
0x18000753f  mov     [rsp+2E0h+lpData], r13; lpData
0x180007544  mov     [rsp+2E0h+lpcbData], rax; lpType
0x180007549  lea     r8, [rbp+1E0h+ValueName]; lpValueName
0x18000754d  mov     edx, esi; dwIndex
0x18000754f  mov     [rsp+2E0h+phkResult], r13; lpReserved
0x180007554  mov     rdi, r13
0x180007557  mov     [rsp+2E0h+cbData], r13d
0x18000755c  call    cs:__imp_RegEnumValueW
0x180007562  cmp     eax, 103h
0x180007567  jz      loc_1800078E0
0x18000756d  test    eax, eax
0x18000756f  jz      loc_18000761A
0x180007575  jle     loc_1800076F7
0x18000757b  movzx   ebx, ax
0x18000757e  or      ebx, 80070000h
0x180007584  test    ebx, ebx
0x180007586  js      loc_180007899
0x18000758c  mov     r8d, 3
0x180007592  lea     rdx, aMtf; "MTF"
0x180007599  lea     rcx, [rbp+1E0h+ValueName]
0x18000759d  call    cs:__imp__o__wcsnicmp
0x1800075a3  test    eax, eax
0x1800075a5  jnz     short loc_180007613
0x1800075a7  mov     eax, [rsp+2E0h+cbData]
0x1800075ab  add     eax, 2
0x1800075ae  mov     ecx, eax; unsigned __int64
0x1800075b0  mov     [rsp+2E0h+cbData], eax
0x1800075b4  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800075b9  mov     rdi, rax
0x1800075bc  test    rax, rax
0x1800075bf  jz      loc_1800078C7
0x1800075c5  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800075ca  lea     rax, [rsp+2E0h+cbData]
0x1800075cf  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x1800075d4  lea     r9, [rsp+2E0h+Type]; lpType
0x1800075d9  xor     r8d, r8d; lpReserved
0x1800075dc  mov     [rsp+2E0h+phkResult], rdi; lpData
0x1800075e1  lea     rdx, [rbp+1E0h+ValueName]; lpValueName
0x1800075e5  call    cs:__imp_RegQueryValueExW
0x1800075eb  mov     ebx, eax
0x1800075ed  test    eax, eax
0x1800075ef  jnz     loc_180007775
0x1800075f5  mov     rcx, [rsp+2E0h+var_290]
0x1800075fa  mov     rdx, rdi
0x1800075fd  mov     rax, [rcx]
0x180007600  mov     rax, [rax+70h]
0x180007604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007609  mov     ebx, eax
0x18000760b  test    eax, eax
0x18000760d  js      loc_1800078B0
0x180007613  inc     esi
0x180007615  jmp     loc_180007505
0x18000761a  mov     ebx, r13d
0x18000761d  jmp     loc_18000758C
0x180007622  mov     eax, [rsp+2E0h+cbData]
0x180007626  add     eax, 2
0x180007629  mov     ecx, eax
0x18000762b  mov     [rsp+2E0h+cbData], eax
0x18000762f  mov     eax, 2
0x180007634  mul     rcx
0x180007637  cmovb   rax, rbx
0x18000763b  mov     rcx, rax; unsigned __int64
0x18000763e  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180007643  mov     rdi, rax
0x180007646  test    rax, rax
0x180007649  jnz     loc_1800077DA
0x18000764f  mov     ecx, 8007000Eh
0x180007654  mov     ebx, ecx
0x180007656  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000765d  jb      loc_1800073FA
0x180007663  mov     edx, 0B5h
0x180007668  jmp     loc_1800077D4
0x18000766d  mov     eax, [rsp+2E0h+cbData]
0x180007671  add     eax, 2
0x180007674  mov     ecx, eax
0x180007676  mov     [rsp+2E0h+cbData], eax
0x18000767a  mov     eax, 2
0x18000767f  mul     rcx
0x180007682  cmovb   rax, rbx
0x180007686  mov     rcx, rax; unsigned __int64
0x180007689  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000768e  mov     rdi, rax
0x180007691  test    rax, rax
0x180007694  jz      loc_18000784D
0x18000769a  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18000769f  lea     rax, [rsp+2E0h+cbData]
0x1800076a4  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x1800076a9  lea     r9, [rsp+2E0h+Type]; lpType
0x1800076ae  xor     r8d, r8d; lpReserved
0x1800076b1  mov     [rsp+2E0h+phkResult], rdi; lpData
0x1800076b6  lea     rdx, aConstraint; "Constraint"
0x1800076bd  call    cs:__imp_RegQueryValueExW
0x1800076c3  mov     ebx, eax
0x1800076c5  test    eax, eax
0x1800076c7  jz      loc_1800074CF
0x1800076cd  jle     short loc_1800076D8
0x1800076cf  movzx   ebx, ax
0x1800076d2  or      ebx, 80070000h
0x1800076d8  test    ebx, ebx
0x1800076da  jns     loc_1800074CF
0x1800076e0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800076e7  jb      loc_1800073FA
0x1800076ed  mov     edx, 0B9h
0x1800076f2  jmp     loc_18000779A
0x1800076f7  mov     ebx, eax
0x1800076f9  jmp     loc_180007584
0x1800076fe  cmp     esi, r14d
0x180007701  jb      short loc_180007716
0x180007703  mov     rax, [rsp+2E0h+var_290]
0x180007708  mov     [r12], rax
0x18000770c  mov     [rsp+2E0h+var_290], r13
0x180007711  jmp     loc_1800073FA
0x180007716  mov     rcx, [rsp+2E0h+var_290]
0x18000771b  mov     edx, esi
0x18000771d  mov     rax, [rcx]
0x180007720  mov     rdx, [r15+rdx*8]
0x180007724  mov     rax, [rax+80h]
0x18000772b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007730  mov     ebx, eax
0x180007732  test    eax, eax
0x180007734  jns     loc_1800078E8
0x18000773a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007741  jb      loc_1800073FA
0x180007747  mov     edx, 0C0h
0x18000774c  jmp     short loc_1800077AC
0x18000774e  jle     short loc_180007759
0x180007750  movzx   ebx, ax
0x180007753  or      ebx, 80070000h
0x180007759  test    ebx, ebx
0x18000775b  jns     loc_18000780D
0x180007761  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007768  jb      loc_1800073FA
0x18000776e  mov     edx, 0B6h
0x180007773  jmp     short loc_18000779A
0x180007775  jle     short loc_180007780
0x180007777  movzx   ebx, ax
0x18000777a  or      ebx, 80070000h
0x180007780  test    ebx, ebx
0x180007782  jns     loc_1800075F5
0x180007788  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18000778f  jb      loc_1800073FA
0x180007795  mov     edx, 0BEh
0x18000779a  mov     dword ptr [rsp+2E0h+phkResult], ebx
0x18000779e  jmp     short loc_1800077B0
0x1800077a0  mov     edx, 0B4h
0x1800077a5  jmp     short loc_18000779A
0x1800077a7  mov     edx, 0B7h
0x1800077ac  mov     dword ptr [rsp+2E0h+phkResult], eax
0x1800077b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800077b7  lea     r8, WPP_6a5edec10265312d7fc810d270c6af2a_Traceguids
0x1800077be  xor     r9d, r9d
0x1800077c1  mov     rcx, [rcx+10h]
0x1800077c5  call    WPP_SF_qD
0x1800077ca  jmp     loc_1800073FA
0x1800077cf  mov     edx, 0BDh
0x1800077d4  mov     dword ptr [rsp+2E0h+phkResult], ecx
0x1800077d8  jmp     short loc_1800077B0
0x1800077da  mov     rcx, [rsp+2E0h+hKey]; hKey
0x1800077df  lea     rax, [rsp+2E0h+cbData]
0x1800077e4  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x1800077e9  lea     r9, [rsp+2E0h+Type]; lpType
0x1800077ee  xor     r8d, r8d; lpReserved
0x1800077f1  mov     [rsp+2E0h+phkResult], rdi; lpData
0x1800077f6  lea     rdx, aBlockedcontrol; "BlockedControls"
0x1800077fd  call    cs:__imp_RegQueryValueExW
0x180007803  mov     ebx, eax
0x180007805  test    eax, eax
0x180007807  jnz     loc_18000774E
0x18000780d  lea     rdx, [rsp+2E0h+Block]
0x180007812  mov     rcx, rdi
0x180007815  call    ?ParseBlockedControlString@@YAJPEBGAEAV?$CTUnkArray@UIMFSensorProfileBlockedControl@@@@@Z; ParseBlockedControlString(ushort const *,CTUnkArray<IMFSensorProfileBlockedControl> &)
0x18000781a  mov     ebx, eax
0x18000781c  test    eax, eax
0x18000781e  jns     short loc_180007832
0x180007820  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180007827  jb      loc_1800073FA
0x18000782d  jmp     loc_1800077A7
0x180007832  mov     rcx, rdi; Block
  ... truncated ...
```
