# UtilGetServiceInformation(void *,void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,int *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x140031544`
- end: `0x140031c02`
- name: `?UtilGetServiceInformation@@YAJPEAX0PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAH1111@Z`
- size: `1726`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14001aa8c`

## callees

- `0x140002728`
- `0x140005468`
- `0x14000c8a0`
- `0x140012210`
- `0x140013ff0`
- `0x140014104`
- `0x14001444c`
- `0x140014474`
- `0x1400312e8`
- `0x140031544`
- `0x140031c08`
- `0x140032114`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140031b7c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140031b7c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400319cf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400319cf`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14003170c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14003170c`
- `ntdll!ZwQueryInformationThread` at `0x1400316ac`
- `ntdll!ZwQueryInformationThread` at `0x1400316ac`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x140031739`
- `api-ms-win-service-private-l1-1-0!I_QueryTagInformation` at `0x140031739`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140031799`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140031799`

## string_xrefs

- `0x14003192a`: `SYSTEM\CurrentControlSet\Services\`
- `0x1400319fb`: `ServiceDll`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall UtilGetServiceInformation(
        void *a1,
        void *a2,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        _QWORD *a6,
        __int64 a7,
        __int64 a8)
{
  int ServiceInformationFromCommandLine; // eax
  __int64 v10; // r8
  __int64 v11; // r12
  unsigned int v12; // ebx
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int v16; // edi
  CUserModeHangReport *v17; // rcx
  int ServiceDisplayName; // edi
  __int64 v19; // rdx
  __int64 v20; // r9
  DWORD ProcessId; // eax
  int v22; // eax
  HLOCAL v23; // rbx
  __int64 v24; // r8
  unsigned __int64 v25; // r8
  __int64 v26; // rcx
  char *v27; // rax
  unsigned __int64 v28; // rax
  _WORD *v29; // rcx
  HKEY *v30; // rax
  unsigned __int16 *v31; // rdx
  __int64 v32; // rax
  unsigned __int16 *v33; // rcx
  unsigned __int64 v34; // rax
  __int64 v35; // r9
  DWORD v37; // [rsp+38h] [rbp-A9h]
  void *v38; // [rsp+48h] [rbp-99h] BYREF
  char *v39; // [rsp+50h] [rbp-91h]
  _WORD v40[8]; // [rsp+58h] [rbp-89h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-79h] BYREF
  __int128 ThreadInformation; // [rsp+70h] [rbp-71h] BYREF
  HLOCAL hMem; // [rsp+80h] [rbp-61h]
  __int64 v44; // [rsp+88h] [rbp-59h] BYREF
  void *v45; // [rsp+90h] [rbp-51h] BYREF
  char *v46; // [rsp+98h] [rbp-49h]
  _WORD v47[8]; // [rsp+A0h] [rbp-41h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+B0h] [rbp-31h] BYREF
  _WORD v49[8]; // [rsp+C0h] [rbp-21h] BYREF
  void *v50[2]; // [rsp+D0h] [rbp-11h] BYREF
  _WORD v51[12]; // [rsp+E0h] [rbp-1h] BYREF

  v38 = v40;
  v39 = (char *)v40;
  v40[0] = 0;
  lpSubKey[0] = v49;
  lpSubKey[1] = v49;
  v49[0] = 0;
  v45 = v47;
  v46 = (char *)v47;
  v47[0] = 0;
  v50[0] = v51;
  v50[1] = v51;
  v51[0] = 0;
  hKey = 0;
  if ( !a1 || !a2 || !a3 || !a4 || !a5 || !a6 || !a7 || !a8 )
  {
    ServiceDisplayName = -2147024809;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_5958ded8188d3319535ef35cd392335c_Traceguids);
    }
    goto LABEL_108;
  }
  ServiceInformationFromCommandLine = UtilGetServiceInformationFromCommandLine(a1, a3, a4, a5);
  if ( ServiceInformationFromCommandLine < 0
    && WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      78,
      WPP_5958ded8188d3319535ef35cd392335c_Traceguids,
      (unsigned int)ServiceInformationFromCommandLine);
  }
  v10 = a5[1];
  v11 = -1;
  if ( *a5 != v10 )
  {
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             &v38,
                             *a5,
                             (v10 - *a5) >> 1) )
    {
      ServiceDisplayName = -2147024882;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_108;
      }
      v19 = 79;
      goto LABEL_43;
    }
    goto LABEL_45;
  }
  v12 = 0;
  v44 = 0;
  *(_QWORD *)&ThreadInformation = &v44;
  *((_QWORD *)&ThreadInformation + 1) = 0x800001720LL;
  v13 = ZwQueryInformationThread(a2, ThreadTebInformation, &ThreadInformation, 0x10u, 0);
  v16 = v13;
  if ( v13 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v15, v13);
      v17 = WPP_GLOBAL_Control;
    }
    ServiceDisplayName = v16 | 0x10000000;
    if ( ServiceDisplayName < 0 )
    {
      if ( v17 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 1) != 0 )
      {
        v19 = 80;
LABEL_22:
        v20 = (unsigned int)ServiceDisplayName;
LABEL_44:
        WPP_SF_d(*((_QWORD *)v17 + 2), v19, WPP_5958ded8188d3319535ef35cd392335c_Traceguids, v20);
        goto LABEL_108;
      }
      goto LABEL_108;
    }
  }
  else
  {
    v12 = v44;
  }
  ProcessId = GetProcessId(a1);
  v39 = (char *)v38;
  *(_WORD *)v38 = 0;
  hMem = 0;
  ThreadInformation = __PAIR64__(v12, ProcessId);
  v22 = I_QueryTagInformation(0, 1, &ThreadInformation);
  ServiceDisplayName = v22;
  if ( v22 )
  {
    if ( v22 > 0 )
      ServiceDisplayName = (unsigned __int16)v22 | 0x80070000;
  }
  else
  {
    v23 = hMem;
    ServiceDisplayName = 0;
    if ( !hMem )
      goto LABEL_45;
    if ( !*(_WORD *)hMem )
      goto LABEL_33;
    v24 = -1;
    do
      ++v24;
    while ( *((_WORD *)hMem + v24) );
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                            &v38,
                            hMem,
                            v24) )
    {
LABEL_33:
      if ( !v23 )
        goto LABEL_45;
    }
    else
    {
      ServiceDisplayName = -2147024882;
    }
    LocalFree(v23);
  }
  if ( ServiceDisplayName >= 0 )
  {
LABEL_45:
    if ( v38 == v39 )
      goto LABEL_59;
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             a6,
                             95) )
    {
LABEL_64:
      ServiceDisplayName = -2147024882;
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_108;
      }
      v19 = 82;
      goto LABEL_43;
    }
    v25 = (v39 - (_BYTE *)v38) >> 1;
    if ( !v25 )
    {
LABEL_56:
      if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                              a6,
                              v38,
                              v25) )
      {
        if ( (unsigned __int64)((__int64)(a6[1] - *a6) >> 1) > 0x40 )
        {
          v29 = (_WORD *)(*a6 + 128LL);
          a6[1] = v29;
          *v29 = 0;
        }
LABEL_59:
        ServiceDisplayName = UtilGetServiceDisplayName(v38, &v45);
        if ( (int)(ServiceDisplayName + 0x80000000) >= 0 && ServiceDisplayName != -2147024846 )
        {
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v19 = 83;
            goto LABEL_22;
          }
          goto LABEL_108;
        }
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                 lpSubKey,
                                 L"SYSTEM\\CurrentControlSet\\Services\\",
                                 34) )
        {
          ServiceDisplayName = -2147024882;
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_108;
          }
          v19 = 84;
          goto LABEL_43;
        }
        if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                                 lpSubKey,
                                 v38,
                                 (v39 - (_BYTE *)v38) >> 1) )
        {
          ServiceDisplayName = -2147024882;
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_108;
          }
          v19 = 85;
          goto LABEL_43;
        }
        v30 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
        if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 1u, v30)
          || !hKey
          || (int)UtilRegGetString(hKey, L"Parameters", L"ServiceDll", (__int64)v50, 1, v37) < 0 )
        {
LABEL_94:
          if ( v45 == v46 )
          {
            if ( v38 != v39
              && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                     a8,
                                     v38,
                                     (v39 - (_BYTE *)v38) >> 1) )
            {
              ServiceDisplayName = -2147024882;
              v17 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_108;
              }
              v19 = 88;
              goto LABEL_43;
            }
LABEL_104:
            ServiceDisplayName = 0;
            goto LABEL_108;
          }
          if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                  a8,
                                  v45,
                                  (v46 - (_BYTE *)v45) >> 1) )
            goto LABEL_104;
          ServiceDisplayName = -2147024882;
          v17 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_108;
          }
          v19 = 87;
LABEL_43:
          v20 = 2147942414LL;
          goto LABEL_44;
        }
        if ( v50[0] )
        {
          v32 = -1;
          do
            ++v32;
          while ( *((_WORD *)v50[0] + v32) );
          v33 = (unsigned __int16 *)((char *)v50[0] + 2 * v32);
          while ( 1 )
          {
            v31 = v33;
            if ( v33 <= v50[0] )
              break;
            v34 = *--v33;
            LOWORD(v34) = v34 - 47;
            if ( (unsigned __int16)v34 <= 0x2Du )
            {
              v35 = 0x200000000801LL;
              if ( _bittest64(&v35, v34) )
                break;
            }
          }
          if ( v31 )
          {
            do
              ++v11;
            while ( v31[v11] );
LABEL_81:
            if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                     a7,
                                     v31,
                                     v11) )
            {
              ServiceDisplayName = -2147024882;
              v17 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
                || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              {
                goto LABEL_108;
              }
              v19 = 86;
              goto LABEL_43;
            }
            goto LABEL_94;
          }
        }
        else
        {
          v31 = 0;
        }
        v11 = 0;
        goto LABEL_81;
      }
      goto LABEL_64;
    }
    v26 = (v39 - (_BYTE *)v38) >> 1;
    v27 = (char *)v38;
    if ( *(_WORD *)v38 == 95 )
    {
LABEL_51:
      if ( v27 )
      {
        v28 = (v27 - (_BYTE *)v38) >> 1;
        goto LABEL_54;
      }
    }
    else
    {
      while ( v26 != 1 )
      {
        --v26;
        v27 += 2;
        if ( *(_WORD *)v27 == 95 )
          goto LABEL_51;
      }
    }
    v28 = -1;
LABEL_54:
    if ( v25 >= v28 )
      v25 = v28;
    goto LABEL_56;
  }
  v17 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v19 = 81;
    goto LABEL_22;
  }
LABEL_108:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v50[0] != v51 )
    operator delete(v50[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v45 != v47 )
    operator delete(v45, (const struct std::nothrow_t *)&std::nothrow);
  if ( lpSubKey[0] != v49 )
    operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v38 != v40 )
    operator delete(v38, (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)ServiceDisplayName;
}

```

## disassembly

```asm
0x140031544  mov     rax, rsp
0x140031547  mov     [rax+10h], rbx
0x14003154b  mov     [rax+18h], rdi
0x14003154f  mov     [rax+8], rcx
0x140031553  push    rbp
0x140031554  push    r12
0x140031556  push    r13
0x140031558  push    r14
0x14003155a  push    r15
0x14003155c  lea     rbp, [rax-3Fh]
0x140031560  sub     rsp, 0F0h
0x140031567  mov     r10, r9
0x14003156a  mov     r11, r8
0x14003156d  mov     rdi, rdx
0x140031570  lea     rax, [rsp+110h+var_C0]
0x140031575  mov     [rsp+110h+var_D0], rax
0x14003157a  lea     rax, [rsp+110h+var_C0]
0x14003157f  mov     [rsp+110h+var_C8], rax
0x140031584  xor     r14d, r14d
0x140031587  mov     [rsp+110h+var_C0], r14w
0x14003158d  lea     rax, [rbp+37h+var_58]
0x140031591  mov     [rbp+37h+lpSubKey], rax
0x140031595  lea     rax, [rbp+37h+var_58]
0x140031599  mov     [rbp+37h+var_60], rax
0x14003159d  mov     [rbp+37h+var_58], r14w
0x1400315a2  lea     rax, [rbp+37h+var_78]
0x1400315a6  mov     [rbp+37h+var_88], rax
0x1400315aa  lea     rax, [rbp+37h+var_78]
0x1400315ae  mov     [rbp+37h+var_80], rax
0x1400315b2  mov     [rbp+37h+var_78], r14w
0x1400315b7  lea     rax, [rbp+37h+var_38]
0x1400315bb  mov     [rbp+37h+var_48], rax
0x1400315bf  lea     rax, [rbp+37h+var_38]
0x1400315c3  mov     [rbp+37h+var_40], rax
0x1400315c7  mov     [rbp+37h+var_38], r14w
0x1400315cc  mov     [rbp+37h+hKey], r14
0x1400315d0  test    rcx, rcx
0x1400315d3  jz      loc_140031B3F
0x1400315d9  test    rdx, rdx
0x1400315dc  jz      loc_140031B3F
0x1400315e2  test    r8, r8
0x1400315e5  jz      loc_140031B3F
0x1400315eb  test    r9, r9
0x1400315ee  jz      loc_140031B3F
0x1400315f4  mov     rbx, [rbp+37h+arg_20]
0x1400315f8  test    rbx, rbx
0x1400315fb  jz      loc_140031B3F
0x140031601  mov     r13, [rbp+37h+arg_28]
0x140031605  test    r13, r13
0x140031608  jz      loc_140031B3F
0x14003160e  cmp     [rbp+37h+arg_30], r14
0x140031612  jz      loc_140031B3F
0x140031618  cmp     [rbp+37h+arg_38], r14
0x14003161c  jz      loc_140031B3F
0x140031622  mov     r9, rbx
0x140031625  mov     r8, r10
0x140031628  mov     rdx, r11
0x14003162b  call    ?UtilGetServiceInformationFromCommandLine@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAH1@Z; UtilGetServiceInformationFromCommandLine(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,int *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x140031630  lea     r15, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x140031637  lea     r14, WPP_GLOBAL_Control
0x14003163e  test    eax, eax
0x140031640  jns     short loc_140031668
0x140031642  mov     rcx, cs:WPP_GLOBAL_Control
0x140031649  cmp     rcx, r14
0x14003164c  jz      short loc_140031668
0x14003164e  test    byte ptr [rcx+1Ch], 2
0x140031652  jz      short loc_140031668
0x140031654  mov     edx, 4Eh ; 'N'
0x140031659  mov     r9d, eax
0x14003165c  mov     r8, r15
0x14003165f  mov     rcx, [rcx+10h]
0x140031663  call    WPP_SF_d
0x140031668  mov     r8, [rbx+8]
0x14003166c  mov     rdx, [rbx]
0x14003166f  or      r12, 0FFFFFFFFFFFFFFFFh
0x140031673  cmp     rdx, r8
0x140031676  jnz     loc_1400317C9
0x14003167c  xor     ebx, ebx
0x14003167e  mov     [rbp+37h+var_90], rbx
0x140031682  lea     rax, [rbp+37h+var_90]
0x140031686  mov     qword ptr [rbp+37h+ThreadInformation], rax
0x14003168a  mov     dword ptr [rbp+37h+ThreadInformation+8], 1720h
0x140031691  mov     dword ptr [rbp+37h+ThreadInformation+0Ch], 8
0x140031698  mov     [rsp+110h+ReturnLength], rbx; ReturnLength
0x14003169d  lea     r9d, [r12+11h]; ThreadInformationLength
0x1400316a2  lea     r8, [rbp+37h+ThreadInformation]; ThreadInformation
0x1400316a6  lea     edx, [rbx+1Ah]; ThreadInformationClass
0x1400316a9  mov     rcx, rdi; ThreadHandle
0x1400316ac  call    cs:__imp_ZwQueryInformationThread
0x1400316b2  mov     edi, eax
0x1400316b4  test    eax, eax
0x1400316b6  jz      short loc_140031705
0x1400316b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400316bf  cmp     rcx, r14
0x1400316c2  jz      short loc_1400316DD
0x1400316c4  test    byte ptr [rcx+1Ch], 1
0x1400316c8  jz      short loc_1400316DD
0x1400316ca  mov     r9d, eax
0x1400316cd  mov     rcx, [rcx+10h]
0x1400316d1  call    WPP_SF_L
0x1400316d6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400316dd  or      edi, 10000000h
0x1400316e3  jge     short loc_140031708
0x1400316e5  cmp     rcx, r14
0x1400316e8  jz      loc_140031B73
0x1400316ee  test    byte ptr [rcx+1Ch], 1
0x1400316f2  jz      loc_140031B73
0x1400316f8  mov     edx, 50h ; 'P'
0x1400316fd  mov     r9d, edi
0x140031700  jmp     loc_140031807
0x140031705  mov     ebx, dword ptr [rbp+37h+var_90]
0x140031708  mov     rcx, [rbp+37h+Process]; Process
0x14003170c  call    cs:__imp_GetProcessId
0x140031712  mov     rdx, [rsp+110h+var_D0]
0x140031717  mov     [rsp+110h+var_C8], rdx
0x14003171c  xor     ecx, ecx
0x14003171e  mov     [rdx], cx
0x140031721  xorps   xmm0, xmm0
0x140031724  movups  [rbp+37h+ThreadInformation], xmm0
0x140031728  mov     [rbp+37h+hMem], rcx
0x14003172c  mov     dword ptr [rbp+37h+ThreadInformation], eax
0x14003172f  mov     dword ptr [rbp+37h+ThreadInformation+4], ebx
0x140031732  lea     r8, [rbp+37h+ThreadInformation]
0x140031736  lea     edx, [rcx+1]
0x140031739  call    cs:__imp_I_QueryTagInformation
0x14003173f  mov     edi, eax
0x140031741  xor     ebx, ebx
0x140031743  test    eax, eax
0x140031745  jz      short loc_140031754
0x140031747  jle     short loc_1400317A1
0x140031749  movzx   edi, ax
0x14003174c  or      edi, 80070000h
0x140031752  jmp     short loc_1400317A1
0x140031754  mov     rbx, [rbp+37h+hMem]
0x140031758  xor     edi, edi
0x14003175a  test    rbx, rbx
0x14003175d  jz      loc_140031818
0x140031763  cmp     [rbx], di
0x140031766  jz      short loc_14003178D
0x140031768  mov     r8, r12
0x14003176b  inc     r8
0x14003176e  cmp     [rbx+r8*2], di
0x140031773  jnz     short loc_14003176B
0x140031775  mov     rdx, rbx
0x140031778  lea     rcx, [rsp+110h+var_D0]
0x14003177d  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140031782  test    al, al
0x140031784  jnz     short loc_14003178D
0x140031786  mov     edi, 8007000Eh
0x14003178b  jmp     short loc_140031796
0x14003178d  test    rbx, rbx
0x140031790  jz      loc_140031818
0x140031796  mov     rcx, rbx; hMem
0x140031799  call    cs:__imp_LocalFree
0x14003179f  xor     ebx, ebx
0x1400317a1  test    edi, edi
0x1400317a3  jns     short loc_14003181A
0x1400317a5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400317ac  cmp     rcx, r14
0x1400317af  jz      loc_140031B73
0x1400317b5  test    byte ptr [rcx+1Ch], 1
0x1400317b9  jz      loc_140031B73
0x1400317bf  mov     edx, 51h ; 'Q'
0x1400317c4  jmp     loc_1400316FD
0x1400317c9  sub     r8, rdx
0x1400317cc  sar     r8, 1
0x1400317cf  lea     rcx, [rsp+110h+var_D0]
0x1400317d4  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1400317d9  xor     ebx, ebx
0x1400317db  test    al, al
0x1400317dd  jnz     short loc_14003181A
0x1400317df  mov     edi, 8007000Eh
0x1400317e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400317eb  cmp     rcx, r14
0x1400317ee  jz      loc_140031B73
0x1400317f4  test    byte ptr [rcx+1Ch], 1
0x1400317f8  jz      loc_140031B73
0x1400317fe  lea     edx, [rbx+4Fh]
0x140031801  mov     r9d, 8007000Eh
0x140031807  mov     r8, r15
0x14003180a  mov     rcx, [rcx+10h]
0x14003180e  call    WPP_SF_d
0x140031813  jmp     loc_140031B73
0x140031818  xor     ebx, ebx
0x14003181a  mov     rax, [rsp+110h+var_C8]
0x14003181f  cmp     [rsp+110h+var_D0], rax
0x140031824  jz      loc_1400318B3
0x14003182a  mov     edi, 5Fh ; '_'
0x14003182f  mov     edx, edi
0x140031831  mov     rcx, r13
0x140031834  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x140031839  test    al, al
0x14003183b  jz      loc_1400318FB
0x140031841  mov     r8, [rsp+110h+var_C8]
0x140031846  mov     rdx, [rsp+110h+var_D0]
0x14003184b  sub     r8, rdx
0x14003184e  sar     r8, 1
0x140031851  jz      short loc_140031888
0x140031853  mov     rcx, r8
0x140031856  mov     rax, rdx
0x140031859  cmp     [rdx], di
0x14003185c  jz      short loc_140031870
0x14003185e  cmp     rcx, 1
0x140031862  jz      short loc_14003187D
0x140031864  dec     rcx
0x140031867  add     rax, 2
0x14003186b  cmp     [rax], di
0x14003186e  jnz     short loc_14003185E
0x140031870  test    rax, rax
0x140031873  jz      short loc_14003187D
0x140031875  sub     rax, rdx
0x140031878  sar     rax, 1
0x14003187b  jmp     short loc_140031880
0x14003187d  mov     rax, r12
0x140031880  cmp     r8, rax
0x140031883  jb      short loc_140031888
0x140031885  mov     r8, rax
0x140031888  mov     rcx, r13
0x14003188b  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140031890  test    al, al
0x140031892  jz      short loc_1400318FB
0x140031894  mov     rcx, [r13+0]
0x140031898  mov     rax, [r13+8]
0x14003189c  sub     rax, rcx
0x14003189f  sar     rax, 1
0x1400318a2  cmp     rax, 40h ; '@'
0x1400318a6  jbe     short loc_1400318B3
0x1400318a8  sub     rcx, 0FFFFFFFFFFFFFF80h
0x1400318ac  mov     [r13+8], rcx
0x1400318b0  mov     [rcx], bx
0x1400318b3  lea     rdx, [rbp+37h+var_88]
0x1400318b7  mov     rcx, [rsp+110h+var_D0]
0x1400318bc  call    ?UtilGetServiceDisplayName@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetServiceDisplayName(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1400318c1  mov     edi, eax
0x1400318c3  mov     eax, 80000000h
0x1400318c8  lea     ecx, [rdi+rax]
0x1400318cb  test    eax, ecx
0x1400318cd  jnz     short loc_140031924
0x1400318cf  cmp     edi, 80070032h
0x1400318d5  jz      short loc_140031924
0x1400318d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400318de  cmp     rcx, r14
0x1400318e1  jz      loc_140031B73
0x1400318e7  test    byte ptr [rcx+1Ch], 1
0x1400318eb  jz      loc_140031B73
0x1400318f1  mov     edx, 53h ; 'S'
0x1400318f6  jmp     loc_1400316FD
0x1400318fb  mov     edi, 8007000Eh
0x140031900  mov     rcx, cs:WPP_GLOBAL_Control
0x140031907  cmp     rcx, r14
0x14003190a  jz      loc_140031B73
0x140031910  test    byte ptr [rcx+1Ch], 1
0x140031914  jz      loc_140031B73
0x14003191a  mov     edx, 52h ; 'R'
0x14003191f  jmp     loc_140031801
0x140031924  mov     r8d, 22h ; '"'
0x14003192a  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\"
0x140031931  lea     rcx, [rbp+37h+lpSubKey]
0x140031935  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14003193a  test    al, al
0x14003193c  jnz     short loc_140031967
0x14003193e  mov     edi, 8007000Eh
0x140031943  mov     rcx, cs:WPP_GLOBAL_Control
0x14003194a  cmp     rcx, r14
0x14003194d  jz      loc_140031B73
0x140031953  test    byte ptr [rcx+1Ch], 1
0x140031957  jz      loc_140031B73
0x14003195d  mov     edx, 54h ; 'T'
0x140031962  jmp     loc_140031801
0x140031967  mov     r8, [rsp+110h+var_C8]
0x14003196c  mov     rdx, [rsp+110h+var_D0]
0x140031971  sub     r8, rdx
0x140031974  sar     r8, 1
0x140031977  lea     rcx, [rbp+37h+lpSubKey]
0x14003197b  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140031980  test    al, al
0x140031982  jnz     short loc_1400319AD
0x140031984  mov     edi, 8007000Eh
0x140031989  mov     rcx, cs:WPP_GLOBAL_Control
0x140031990  cmp     rcx, r14
0x140031993  jz      loc_140031B73
0x140031999  test    byte ptr [rcx+1Ch], 1
0x14003199d  jz      loc_140031B73
0x1400319a3  mov     edx, 55h ; 'U'
0x1400319a8  jmp     loc_140031801
0x1400319ad  lea     rcx, [rbp+37h+hKey]
0x1400319b1  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x1400319b6  mov     [rsp+110h+ReturnLength], rax; phkResult
0x1400319bb  mov     r9d, 1; samDesired
0x1400319c1  xor     r8d, r8d; ulOptions
0x1400319c4  mov     rdx, [rbp+37h+lpSubKey]; lpSubKey
0x1400319c8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1400319cf  call    cs:__imp_RegOpenKeyExW
0x1400319d5  test    eax, eax
0x1400319d7  jnz     loc_140031AAE
0x1400319dd  mov     rcx, [rbp+37h+hKey]; hKey
0x1400319e1  test    rcx, rcx
0x1400319e4  jz      loc_140031AAE
0x1400319ea  mov     [rsp+110h+var_E8], 1; char
0x1400319ef  lea     rax, [rbp+37h+var_48]
  ... truncated ...
```
