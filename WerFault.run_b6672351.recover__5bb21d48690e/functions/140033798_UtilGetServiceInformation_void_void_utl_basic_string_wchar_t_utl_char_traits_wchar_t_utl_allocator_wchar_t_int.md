# UtilGetServiceInformation(void *,void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,int *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x140033798`
- end: `0x140033df6`
- name: `?UtilGetServiceInformation@@YAJPEAX0PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAH1111@Z`
- size: `1630`
- prototype: `__int64 __usercall@<rax>(HANDLE Process@<rcx>, HANDLE ThreadHandle@<rdx>, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14001bac4`

## callees

- `0x140002748`
- `0x14000551c`
- `0x14000ca20`
- `0x140012a9c`
- `0x140014a88`
- `0x140014b9c`
- `0x140014ee4`
- `0x140014f14`
- `0x140033510`
- `0x140033798`
- `0x140033dfc`
- `0x1400342ec`
- `0x140034400`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140033d6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140033d6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140033bb7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140033bb7`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140033966`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140033966`
- `ntdll!ZwQueryInformationThread` at `0x1400338fd`
- `ntdll!ZwQueryInformationThread` at `0x1400338fd`

## string_xrefs

- `0x140033b12`: `SYSTEM\CurrentControlSet\Services\`
- `0x140033be9`: `ServiceDll`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall UtilGetServiceInformation(
        HANDLE Process,
        HANDLE ThreadHandle,
        __int64 a3,
        __int64 a4,
        _QWORD *a5,
        _QWORD *a6,
        __int64 a7,
        __int64 a8)
{
  _QWORD *v10; // rbx
  _QWORD *v11; // r15
  int ServiceInformationFromCommandLine; // eax
  unsigned int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  unsigned int v16; // ebx
  unsigned int v17; // r14d
  CUserModeHangReport *v18; // rcx
  int ServiceDisplayName; // ebx
  __int64 v20; // rdx
  __int64 v21; // r9
  DWORD ProcessId; // eax
  int v23; // eax
  __int64 v24; // r14
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
  DWORD v37; // [rsp+30h] [rbp-99h]
  void *v38; // [rsp+40h] [rbp-89h] BYREF
  char *v39; // [rsp+48h] [rbp-81h]
  _WORD v40[8]; // [rsp+50h] [rbp-79h] BYREF
  __int64 v41; // [rsp+60h] [rbp-69h] BYREF
  void *v42; // [rsp+68h] [rbp-61h] BYREF
  _WORD *v43; // [rsp+70h] [rbp-59h]
  _WORD v44[8]; // [rsp+78h] [rbp-51h] BYREF
  LPCWSTR lpSubKey[2]; // [rsp+88h] [rbp-41h] BYREF
  _WORD v46[8]; // [rsp+98h] [rbp-31h] BYREF
  void *v47[2]; // [rsp+A8h] [rbp-21h] BYREF
  _WORD v48[8]; // [rsp+B8h] [rbp-11h] BYREF
  __int64 *ThreadInformation; // [rsp+C8h] [rbp-1h] BYREF
  int v50; // [rsp+D0h] [rbp+7h]
  int v51; // [rsp+D4h] [rbp+Bh]
  HKEY hKey; // [rsp+110h] [rbp+47h] BYREF

  v38 = v40;
  v39 = (char *)v40;
  v40[0] = 0;
  lpSubKey[0] = v46;
  lpSubKey[1] = v46;
  v46[0] = 0;
  v42 = v44;
  v43 = v44;
  v44[0] = 0;
  v47[0] = v48;
  v47[1] = v48;
  v48[0] = 0;
  hKey = 0;
  if ( !Process || !ThreadHandle || !a3 || !a4 || (v10 = a5) == 0 || (v11 = a6) == 0 || !a7 || !a8 )
  {
    ServiceDisplayName = -2147024809;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 77, WPP_5958ded8188d3319535ef35cd392335c_Traceguids);
    }
    goto LABEL_96;
  }
  ServiceInformationFromCommandLine = UtilGetServiceInformationFromCommandLine(Process, a3, a4, a5);
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
  if ( *v10 == v10[1] )
  {
    v41 = 0;
    ThreadInformation = &v41;
    v50 = 5920;
    v51 = 8;
    v13 = ZwQueryInformationThread(ThreadHandle, ThreadTebInformation, &ThreadInformation, 0x10u, 0);
    v16 = v13;
    v17 = 0;
    if ( v13 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, v15, v13);
        v18 = WPP_GLOBAL_Control;
      }
      ServiceDisplayName = v16 | 0x10000000;
      if ( ServiceDisplayName < 0 )
      {
        if ( v18 != (CUserModeHangReport *)&WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 )
        {
          v20 = 80;
LABEL_22:
          v21 = (unsigned int)ServiceDisplayName;
LABEL_33:
          WPP_SF_d(*((_QWORD *)v18 + 2), v20, WPP_5958ded8188d3319535ef35cd392335c_Traceguids, v21);
          goto LABEL_96;
        }
        goto LABEL_96;
      }
    }
    else
    {
      v17 = v41;
    }
    ProcessId = GetProcessId(Process);
    v23 = UtilQueryServiceTagNameFromServiceTag(ProcessId, v17, &v38);
    ServiceDisplayName = v23;
    if ( v23 < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v20 = 81;
        v21 = (unsigned int)v23;
        goto LABEL_33;
      }
      goto LABEL_96;
    }
  }
  else if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                                &v38,
                                *v10) )
  {
    ServiceDisplayName = -2147024882;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_96;
    }
    v20 = 79;
    goto LABEL_32;
  }
  v24 = -1;
  if ( v38 != v39 )
  {
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                             v11,
                             95) )
      goto LABEL_53;
    v25 = (v39 - (_BYTE *)v38) >> 1;
    if ( !v25 )
    {
LABEL_45:
      if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                              v11,
                              v38,
                              v25) )
      {
        if ( (unsigned __int64)((__int64)(v11[1] - *v11) >> 1) > 0x40 )
        {
          v29 = (_WORD *)(*v11 + 128LL);
          v11[1] = v29;
          *v29 = 0;
        }
        goto LABEL_48;
      }
LABEL_53:
      ServiceDisplayName = -2147024882;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_96;
      }
      v20 = 82;
      goto LABEL_32;
    }
    v26 = (v39 - (_BYTE *)v38) >> 1;
    v27 = (char *)v38;
    if ( *(_WORD *)v38 == 95 )
    {
LABEL_40:
      if ( v27 )
      {
        v28 = (v27 - (_BYTE *)v38) >> 1;
        goto LABEL_43;
      }
    }
    else
    {
      while ( v26 != 1 )
      {
        --v26;
        v27 += 2;
        if ( *(_WORD *)v27 == 95 )
          goto LABEL_40;
      }
    }
    v28 = -1;
LABEL_43:
    if ( v25 >= v28 )
      v25 = v28;
    goto LABEL_45;
  }
LABEL_48:
  ServiceDisplayName = UtilGetServiceDisplayName(v38, &v42);
  if ( (int)(ServiceDisplayName + 0x80000000) < 0 || ServiceDisplayName == -2147024846 )
  {
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                             lpSubKey,
                             L"SYSTEM\\CurrentControlSet\\Services\\") )
    {
      ServiceDisplayName = -2147024882;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_96;
      }
      v20 = 84;
      goto LABEL_32;
    }
    if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(
                             lpSubKey,
                             v38,
                             (v39 - (_BYTE *)v38) >> 1) )
    {
      ServiceDisplayName = -2147024882;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_96;
      }
      v20 = 85;
      goto LABEL_32;
    }
    v30 = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey[0], 0, 1u, v30)
      && hKey
      && (int)UtilRegGetString(hKey, L"Parameters", L"ServiceDll", (__int64)v47, 1, v37) >= 0 )
    {
      if ( v47[0] )
      {
        v32 = -1;
        do
          ++v32;
        while ( *((_WORD *)v47[0] + v32) );
        v33 = (unsigned __int16 *)((char *)v47[0] + 2 * v32);
        while ( 1 )
        {
          v31 = v33;
          if ( v33 <= v47[0] )
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
            ++v24;
          while ( v31[v24] );
        }
      }
      else
      {
        v31 = 0;
      }
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               a7,
                               v31) )
      {
        ServiceDisplayName = -2147024882;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_96;
        }
        v20 = 86;
        goto LABEL_32;
      }
    }
    if ( v42 == v43 )
    {
      if ( v38 != v39
        && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               a8,
                               v38) )
      {
        ServiceDisplayName = -2147024882;
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_96;
        }
        v20 = 88;
        goto LABEL_32;
      }
LABEL_92:
      ServiceDisplayName = 0;
      goto LABEL_96;
    }
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(a8, v42) )
      goto LABEL_92;
    ServiceDisplayName = -2147024882;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_96;
    }
    v20 = 87;
LABEL_32:
    v21 = 2147942414LL;
    goto LABEL_33;
  }
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v20 = 83;
    goto LABEL_22;
  }
LABEL_96:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v47[0] != v48 )
    operator delete(v47[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v42 != v44 )
    operator delete(v42, (const struct std::nothrow_t *)&std::nothrow);
  if ( lpSubKey[0] != v46 )
    operator delete((void *)lpSubKey[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v38 != v40 )
    operator delete(v38, (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)ServiceDisplayName;
}

```

## disassembly

```asm
0x140033798  mov     [rsp-8+arg_8], rbx
0x14003379d  mov     [rsp-8+arg_10], rsi
0x1400337a2  push    rbp
0x1400337a3  push    rdi
0x1400337a4  push    r12
0x1400337a6  push    r14
0x1400337a8  push    r15
0x1400337aa  lea     rbp, [rsp-17h]
0x1400337af  sub     rsp, 0E0h
0x1400337b6  mov     r10, r9
0x1400337b9  mov     r11, r8
0x1400337bc  mov     r14, rdx
0x1400337bf  mov     r12, rcx
0x1400337c2  lea     rax, [rbp+37h+var_B0]
0x1400337c6  mov     [rsp+100h+var_C0], rax
0x1400337cb  lea     rax, [rbp+37h+var_B0]
0x1400337cf  mov     [rsp+100h+var_B8], rax
0x1400337d4  xor     ecx, ecx
0x1400337d6  mov     [rbp+37h+var_B0], cx
0x1400337da  lea     rax, [rbp+37h+var_68]
0x1400337de  mov     [rbp+37h+lpSubKey], rax
0x1400337e2  lea     rax, [rbp+37h+var_68]
0x1400337e6  mov     [rbp+37h+var_70], rax
0x1400337ea  mov     [rbp+37h+var_68], cx
0x1400337ee  lea     rax, [rbp+37h+var_88]
0x1400337f2  mov     [rbp+37h+var_98], rax
0x1400337f6  lea     rax, [rbp+37h+var_88]
0x1400337fa  mov     [rbp+37h+var_90], rax
0x1400337fe  mov     [rbp+37h+var_88], cx
0x140033802  lea     rax, [rbp+37h+var_48]
0x140033806  mov     [rbp+37h+var_58], rax
0x14003380a  lea     rax, [rbp+37h+var_48]
0x14003380e  mov     [rbp+37h+var_50], rax
0x140033812  mov     [rbp+37h+var_48], cx
0x140033816  mov     [rbp+37h+hKey], rcx
0x14003381a  test    r12, r12
0x14003381d  jz      loc_140033D2E
0x140033823  test    rdx, rdx
0x140033826  jz      loc_140033D2E
0x14003382c  test    r8, r8
0x14003382f  jz      loc_140033D2E
0x140033835  test    r9, r9
0x140033838  jz      loc_140033D2E
0x14003383e  mov     rbx, [rbp+37h+arg_20]
0x140033842  test    rbx, rbx
0x140033845  jz      loc_140033D2E
0x14003384b  mov     r15, [rbp+37h+arg_28]
0x14003384f  test    r15, r15
0x140033852  jz      loc_140033D2E
0x140033858  cmp     [rbp+37h+arg_30], rcx
0x14003385c  jz      loc_140033D2E
0x140033862  cmp     [rbp+37h+arg_38], rcx
0x140033866  jz      loc_140033D2E
0x14003386c  mov     r9, rbx
0x14003386f  mov     r8, r10
0x140033872  mov     rdx, r11
0x140033875  mov     rcx, r12
0x140033878  call    ?UtilGetServiceInformationFromCommandLine@@YAJPEAXPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAH1@Z; UtilGetServiceInformationFromCommandLine(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,int *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x14003387d  lea     rsi, WPP_5958ded8188d3319535ef35cd392335c_Traceguids
0x140033884  lea     rdi, WPP_GLOBAL_Control
0x14003388b  test    eax, eax
0x14003388d  jns     short loc_1400338B5
0x14003388f  mov     rcx, cs:WPP_GLOBAL_Control
0x140033896  cmp     rcx, rdi
0x140033899  jz      short loc_1400338B5
0x14003389b  test    byte ptr [rcx+1Ch], 2
0x14003389f  jz      short loc_1400338B5
0x1400338a1  mov     edx, 4Eh ; 'N'
0x1400338a6  mov     r9d, eax
0x1400338a9  mov     r8, rsi
0x1400338ac  mov     rcx, [rcx+10h]
0x1400338b0  call    WPP_SF_d
0x1400338b5  mov     r8, [rbx+8]
0x1400338b9  mov     rdx, [rbx]
0x1400338bc  cmp     rdx, r8
0x1400338bf  jnz     loc_1400339AE
0x1400338c5  mov     [rbp+37h+var_A0], 0
0x1400338cd  lea     rax, [rbp+37h+var_A0]
0x1400338d1  mov     [rbp+37h+ThreadInformation], rax
0x1400338d5  mov     [rbp+37h+var_30], 1720h
0x1400338dc  mov     [rbp+37h+var_2C], 8
0x1400338e3  mov     [rsp+100h+ReturnLength], 0; ReturnLength
0x1400338ec  mov     r9d, 10h; ThreadInformationLength
0x1400338f2  lea     r8, [rbp+37h+ThreadInformation]; ThreadInformation
0x1400338f6  lea     edx, [r9+0Ah]; ThreadInformationClass
0x1400338fa  mov     rcx, r14; ThreadHandle
0x1400338fd  call    cs:__imp_ZwQueryInformationThread
0x140033904  nop     dword ptr [rax+rax+00h]
0x140033909  mov     ebx, eax
0x14003390b  xor     r14d, r14d
0x14003390e  test    eax, eax
0x140033910  jz      short loc_14003395F
0x140033912  mov     rcx, cs:WPP_GLOBAL_Control
0x140033919  cmp     rcx, rdi
0x14003391c  jz      short loc_140033937
0x14003391e  test    byte ptr [rcx+1Ch], 1
0x140033922  jz      short loc_140033937
0x140033924  mov     r9d, eax
0x140033927  mov     rcx, [rcx+10h]
0x14003392b  call    WPP_SF_L
0x140033930  mov     rcx, cs:WPP_GLOBAL_Control
0x140033937  or      ebx, 10000000h
0x14003393d  jge     short loc_140033963
0x14003393f  cmp     rcx, rdi
0x140033942  jz      loc_140033D62
0x140033948  test    byte ptr [rcx+1Ch], 1
0x14003394c  jz      loc_140033D62
0x140033952  mov     edx, 50h ; 'P'
0x140033957  mov     r9d, ebx
0x14003395a  jmp     loc_1400339EF
0x14003395f  mov     r14d, dword ptr [rbp+37h+var_A0]
0x140033963  mov     rcx, r12; Process
0x140033966  call    cs:__imp_GetProcessId
0x14003396d  nop     dword ptr [rax+rax+00h]
0x140033972  lea     r8, [rsp+100h+var_C0]
0x140033977  mov     edx, r14d
0x14003397a  mov     ecx, eax
0x14003397c  call    ?UtilQueryServiceTagNameFromServiceTag@@YAJKKPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilQueryServiceTagNameFromServiceTag(ulong,ulong,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x140033981  mov     ebx, eax
0x140033983  xor     r12d, r12d
0x140033986  test    eax, eax
0x140033988  jns     short loc_140033A00
0x14003398a  mov     rcx, cs:WPP_GLOBAL_Control
0x140033991  cmp     rcx, rdi
0x140033994  jz      loc_140033D62
0x14003399a  test    byte ptr [rcx+1Ch], 1
0x14003399e  jz      loc_140033D62
0x1400339a4  lea     edx, [r12+51h]
0x1400339a9  mov     r9d, eax
0x1400339ac  jmp     short loc_1400339EF
0x1400339ae  sub     r8, rdx
0x1400339b1  sar     r8, 1
0x1400339b4  lea     rcx, [rsp+100h+var_C0]
0x1400339b9  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x1400339be  xor     r12d, r12d
0x1400339c1  test    al, al
0x1400339c3  jnz     short loc_140033A00
0x1400339c5  mov     ebx, 8007000Eh
0x1400339ca  mov     rcx, cs:WPP_GLOBAL_Control
0x1400339d1  cmp     rcx, rdi
0x1400339d4  jz      loc_140033D62
0x1400339da  test    byte ptr [rcx+1Ch], 1
0x1400339de  jz      loc_140033D62
0x1400339e4  lea     edx, [r12+4Fh]
0x1400339e9  mov     r9d, 8007000Eh
0x1400339ef  mov     r8, rsi
0x1400339f2  mov     rcx, [rcx+10h]
0x1400339f6  call    WPP_SF_d
0x1400339fb  jmp     loc_140033D62
0x140033a00  or      r14, 0FFFFFFFFFFFFFFFFh
0x140033a04  mov     rax, [rsp+100h+var_B8]
0x140033a09  cmp     [rsp+100h+var_C0], rax
0x140033a0e  jz      loc_140033A9C
0x140033a14  lea     ebx, [r14+60h]
0x140033a18  mov     edx, ebx
0x140033a1a  mov     rcx, r15
0x140033a1d  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x140033a22  test    al, al
0x140033a24  jz      loc_140033AE3
0x140033a2a  mov     r8, [rsp+100h+var_B8]
0x140033a2f  mov     rdx, [rsp+100h+var_C0]
0x140033a34  sub     r8, rdx
0x140033a37  sar     r8, 1
0x140033a3a  jz      short loc_140033A71
0x140033a3c  mov     rcx, r8
0x140033a3f  mov     rax, rdx
0x140033a42  cmp     [rdx], bx
0x140033a45  jz      short loc_140033A59
0x140033a47  cmp     rcx, 1
0x140033a4b  jz      short loc_140033A66
0x140033a4d  dec     rcx
0x140033a50  add     rax, 2
0x140033a54  cmp     [rax], bx
0x140033a57  jnz     short loc_140033A47
0x140033a59  test    rax, rax
0x140033a5c  jz      short loc_140033A66
0x140033a5e  sub     rax, rdx
0x140033a61  sar     rax, 1
0x140033a64  jmp     short loc_140033A69
0x140033a66  mov     rax, r14
0x140033a69  cmp     r8, rax
0x140033a6c  jb      short loc_140033A71
0x140033a6e  mov     r8, rax
0x140033a71  mov     rcx, r15
0x140033a74  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140033a79  test    al, al
0x140033a7b  jz      short loc_140033AE3
0x140033a7d  mov     rcx, [r15]
0x140033a80  mov     rax, [r15+8]
0x140033a84  sub     rax, rcx
0x140033a87  sar     rax, 1
0x140033a8a  cmp     rax, 40h ; '@'
0x140033a8e  jbe     short loc_140033A9C
0x140033a90  sub     rcx, 0FFFFFFFFFFFFFF80h
0x140033a94  mov     [r15+8], rcx
0x140033a98  mov     [rcx], r12w
0x140033a9c  lea     rdx, [rbp+37h+var_98]
0x140033aa0  mov     rcx, [rsp+100h+var_C0]
0x140033aa5  call    ?UtilGetServiceDisplayName@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilGetServiceDisplayName(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x140033aaa  mov     ebx, eax
0x140033aac  mov     ecx, 80000000h
0x140033ab1  add     eax, ecx
0x140033ab3  test    ecx, eax
0x140033ab5  jnz     short loc_140033B0C
0x140033ab7  cmp     ebx, 80070032h
0x140033abd  jz      short loc_140033B0C
0x140033abf  mov     rcx, cs:WPP_GLOBAL_Control
0x140033ac6  cmp     rcx, rdi
0x140033ac9  jz      loc_140033D62
0x140033acf  test    byte ptr [rcx+1Ch], 1
0x140033ad3  jz      loc_140033D62
0x140033ad9  mov     edx, 53h ; 'S'
0x140033ade  jmp     loc_140033957
0x140033ae3  mov     ebx, 8007000Eh
0x140033ae8  mov     rcx, cs:WPP_GLOBAL_Control
0x140033aef  cmp     rcx, rdi
0x140033af2  jz      loc_140033D62
0x140033af8  test    byte ptr [rcx+1Ch], 1
0x140033afc  jz      loc_140033D62
0x140033b02  mov     edx, 52h ; 'R'
0x140033b07  jmp     loc_1400339E9
0x140033b0c  mov     r8d, 22h ; '"'
0x140033b12  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\"
0x140033b19  lea     rcx, [rbp+37h+lpSubKey]
0x140033b1d  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140033b22  test    al, al
0x140033b24  jnz     short loc_140033B4F
0x140033b26  mov     ebx, 8007000Eh
0x140033b2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140033b32  cmp     rcx, rdi
0x140033b35  jz      loc_140033D62
0x140033b3b  test    byte ptr [rcx+1Ch], 1
0x140033b3f  jz      loc_140033D62
0x140033b45  mov     edx, 54h ; 'T'
0x140033b4a  jmp     loc_1400339E9
0x140033b4f  mov     r8, [rsp+100h+var_B8]
0x140033b54  mov     rdx, [rsp+100h+var_C0]
0x140033b59  sub     r8, rdx
0x140033b5c  sar     r8, 1
0x140033b5f  lea     rcx, [rbp+37h+lpSubKey]
0x140033b63  call    ?append@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::append(wchar_t const *,unsigned __int64)
0x140033b68  test    al, al
0x140033b6a  jnz     short loc_140033B95
0x140033b6c  mov     ebx, 8007000Eh
0x140033b71  mov     rcx, cs:WPP_GLOBAL_Control
0x140033b78  cmp     rcx, rdi
0x140033b7b  jz      loc_140033D62
0x140033b81  test    byte ptr [rcx+1Ch], 1
0x140033b85  jz      loc_140033D62
0x140033b8b  mov     edx, 55h ; 'U'
0x140033b90  jmp     loc_1400339E9
0x140033b95  lea     rcx, [rbp+37h+hKey]
0x140033b99  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140033b9e  mov     [rsp+100h+ReturnLength], rax; phkResult
0x140033ba3  mov     r9d, 1; samDesired
0x140033ba9  xor     r8d, r8d; ulOptions
0x140033bac  mov     rdx, [rbp+37h+lpSubKey]; lpSubKey
0x140033bb0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140033bb7  call    cs:__imp_RegOpenKeyExW
0x140033bbe  nop     dword ptr [rax+rax+00h]
0x140033bc3  test    eax, eax
0x140033bc5  jnz     loc_140033C9C
0x140033bcb  mov     rcx, [rbp+37h+hKey]; hKey
0x140033bcf  test    rcx, rcx
0x140033bd2  jz      loc_140033C9C
0x140033bd8  mov     [rsp+100h+var_D8], 1; char
0x140033bdd  lea     rax, [rbp+37h+var_58]
0x140033be1  mov     [rsp+100h+ReturnLength], rax; __int64
0x140033be6  xor     r9d, r9d
0x140033be9  lea     r8, aServicedll; "ServiceDll"
0x140033bf0  lea     rdx, aParameters; "Parameters"
0x140033bf7  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x140033bfc  test    eax, eax
0x140033bfe  js      loc_140033C9C
0x140033c04  mov     r8, [rbp+37h+var_58]
0x140033c08  test    r8, r8
0x140033c0b  jnz     short loc_140033C4C
0x140033c0d  mov     rdx, r12
0x140033c10  mov     r14, r12
0x140033c13  mov     r8, r14
0x140033c16  mov     rcx, [rbp+37h+arg_30]
0x140033c1a  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140033c1f  test    al, al
0x140033c21  jnz     short loc_140033C9C
0x140033c23  mov     ebx, 8007000Eh
0x140033c28  mov     rcx, cs:WPP_GLOBAL_Control
0x140033c2f  cmp     rcx, rdi
0x140033c32  jz      loc_140033D62
0x140033c38  test    byte ptr [rcx+1Ch], 1
0x140033c3c  jz      loc_140033D62
0x140033c42  mov     edx, 56h ; 'V'
0x140033c47  jmp     loc_1400339E9
0x140033c4c  mov     rax, r14
0x140033c4f  inc     rax
0x140033c52  cmp     [r8+rax*2], r12w
0x140033c57  jnz     short loc_140033C4F
0x140033c59  lea     rcx, [r8+rax*2]
0x140033c5d  jmp     short loc_140033C80
0x140033c5f  sub     rcx, 2
0x140033c63  movzx   eax, word ptr [rcx]
  ... truncated ...
```
