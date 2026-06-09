# CDownloadService::AddJob(ushort const *,ushort const *,BG_JOB_PRIORITY,ulong,ulong,ulong,int,_GUID *,CBITSDownloadMonitor *)

- ea: `0x18001b05c`
- end: `0x18001b6b4`
- name: `?AddJob@CDownloadService@@QEAAJPEBG0W4BG_JOB_PRIORITY@@KKKHPEAU_GUID@@PEAVCBITSDownloadMonitor@@@Z`
- size: `1624`
- prototype: `__int64 __fastcall(CDownloadService *__hidden this, const unsigned __int16 *, const unsigned __int16 *, enum BG_JOB_PRIORITY, unsigned int, unsigned int, unsigned int, int, GUID *rguid, struct CBITSDownloadMonitor *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180014680`

## callees

- `0x180002a50`
- `0x1800059ec`
- `0x1800062ac`
- `0x180007b5c`
- `0x180007c00`
- `0x18000a290`
- `0x18001afb4`
- `0x18001b05c`
- `0x18001bc30`
- `0x18001c328`
- `0x18001c3fc`
- `0x18001c4f8`
- `0x18001e07c`
- `0x18001e9f0`
- `0x18001eac4`
- `0x18001eba8`
- `0x18001f3da`
- `0x18001f420`
- `0x18001f4e0`
- `0x180021010`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18001b612`
- `ADVAPI32!RegCloseKey` at `0x18001b612`
- `ADVAPI32!RegGetValueW` at `0x18001b367`
- `ADVAPI32!RegGetValueW` at `0x18001b367`
- `ADVAPI32!RegOpenKeyExW` at `0x18001b30f`
- `ADVAPI32!RegOpenKeyExW` at `0x18001b30f`
- `KERNEL32!GetLastError` at `0x18001b4d2`
- `KERNEL32!GetLastError` at `0x18001b4d2`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001b4c2`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x18001b4c2`
- `ole32!StringFromGUID2` at `0x18001b52b`
- `ole32!StringFromGUID2` at `0x18001b52b`

## string_xrefs

- `0x18001b4bb`: `%windir%\System32\deviceenroller.exe`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CDownloadService::AddJob(
        CDownloadService *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        enum BG_JOB_PRIORITY a4,
        unsigned int a5,
        unsigned int a6,
        unsigned int a7,
        int a8,
        GUID *rguid,
        struct CBITSDownloadMonitor *a10)
{
  signed int BITSJob; // ebx
  char v13; // r14
  const unsigned __int16 *v14; // rcx
  __int64 v15; // rdx
  const unsigned __int16 *v16; // rdi
  const unsigned __int16 *v17; // rcx
  enum BG_CERT_STORE_LOCATION v18; // edi
  LSTATUS v19; // eax
  LSTATUS ValueW; // eax
  wchar_t *v21; // r8
  __int64 v22; // rdx
  signed int LastError; // eax
  const unsigned __int16 *v24; // rcx
  const unsigned __int16 *v25; // rcx
  int v26; // eax
  bool v28; // [rsp+40h] [rbp-C0h] BYREF
  struct IBackgroundCopyJob *v29; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcbData; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v31; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v32; // [rsp+60h] [rbp-A0h] BYREF
  enum BG_JOB_PRIORITY v33; // [rsp+68h] [rbp-98h]
  HKEY hkey; // [rsp+70h] [rbp-90h] BYREF
  const unsigned __int16 *v35; // [rsp+78h] [rbp-88h]
  __int64 v36; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v37[24]; // [rsp+88h] [rbp-78h] BYREF
  wchar_t String1[12]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v39; // [rsp+B8h] [rbp-48h]
  WCHAR SubKey[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Dst[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  unsigned __int16 pvData[264]; // [rsp+4E0h] [rbp+3E0h] BYREF
  OLECHAR sz[264]; // [rsp+6F0h] [rbp+5F0h] BYREF
  unsigned __int16 v44[4008]; // [rsp+900h] [rbp+800h] BYREF

  v33 = a4;
  v35 = a3;
  v29 = 0;
  v36 = 0;
  v32 = 0;
  v31 = 0;
  hkey = 0;
  memset_0(pvData, 0, 0x20Au);
  pcbData = 522;
  v28 = 0;
  memset(v37, 0, sizeof(v37));
  if ( !rguid || !a10 )
  {
    BITSJob = -2147024809;
    goto LABEL_70;
  }
  v13 = 0;
  if ( *((_BYTE *)this + 8) )
  {
    v14 = (const unsigned __int16 *)((char *)this + 16);
    if ( *((_QWORD *)this + 5) >= 8u )
      v14 = *(const unsigned __int16 **)v14;
    _RevertToSelf(v14);
    v13 = 1;
  }
  std::wstring::wstring(String1, a2);
  BITSJob = CreateBITSJob(String1);
  LOBYTE(v15) = 1;
  std::wstring::_Tidy(String1, v15, 0);
  if ( BITSJob >= 0 )
  {
    BITSJob = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, GUID *))v29->lpVtbl->GetId)(v29, rguid);
    if ( BITSJob >= 0 )
    {
      BITSJob = SetNullCredentials(v29);
      if ( BITSJob >= 0 )
      {
        BITSJob = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, GUID *, __int64 *))v29->lpVtbl->QueryInterface)(
                    v29,
                    &GUID_9a2584c3_f7d2_457a_9a5e_22b67bffc7d2,
                    &v31);
        if ( BITSJob >= 0 )
        {
          BITSJob = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, GUID *, __int64 *))v29->lpVtbl->QueryInterface)(
                      v29,
                      &GUID_54b50739_686f_45eb_9dff_d6a9a0faa9af,
                      &v32);
          if ( BITSJob >= 0 )
          {
            *(_OWORD *)&v37[8] = 0;
            *(_QWORD *)v37 = 0x400000002LL;
            BITSJob = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)v32 + 328LL))(v32, v37);
            if ( BITSJob >= 0 )
            {
              BITSJob = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, _QWORD, _QWORD, _QWORD))v29->lpVtbl->SetProxySettings)(
                          v29,
                          0,
                          0,
                          0);
              if ( BITSJob >= 0 )
              {
                if ( v13 )
                {
                  v16 = (const unsigned __int16 *)((char *)this + 16);
                  if ( *((_QWORD *)this + 5) < 8u )
                    v17 = (const unsigned __int16 *)((char *)this + 16);
                  else
                    v17 = *(const unsigned __int16 **)v16;
                  BITSJob = _ImpersonateUser(v17, *((_DWORD *)this + 12), &v28);
                  if ( BITSJob < 0 )
                    goto LABEL_59;
                  v13 = 0;
                  BITSJob = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v31 + 40LL))(v31);
                  if ( BITSJob < 0 )
                    goto LABEL_59;
                  if ( *((_QWORD *)this + 5) >= 8u )
                    v16 = *(const unsigned __int16 **)v16;
                  _RevertToSelf(v16);
                  v13 = 1;
                }
                BITSJob = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v31 + 24LL))(v31, 2);
                if ( BITSJob < 0 )
                  goto LABEL_59;
                v18 = GetClientCertMode() == 1;
                BITSJob = GetEnrollmentID(SubKey);
                if ( BITSJob < 0 )
                  goto LABEL_59;
                v19 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Enrollments", 0, 0x20019u, &hkey);
                BITSJob = v19;
                if ( v19 > 0 )
                  BITSJob = (unsigned __int16)v19 | 0x80070000;
                if ( BITSJob < 0 )
                  goto LABEL_59;
                ValueW = RegGetValueW(hkey, SubKey, L"DMPCertThumbPrint", 2u, 0, pvData, &pcbData);
                BITSJob = ValueW;
                if ( ValueW > 0 )
                  BITSJob = (unsigned __int16)ValueW | 0x80070000;
                if ( BITSJob < 0 )
                  goto LABEL_59;
                if ( pcbData )
                {
                  std::wstring::wstring(String1, L"MY");
                  GetCertStore(String1);
                  v21 = String1;
                  if ( v39 >= 8 )
                    v21 = *(wchar_t **)String1;
                  BITSJob = SetSecurityOptions(v29, v18, v21, pvData, a8);
                  LOBYTE(v22) = 1;
                  if ( BITSJob < 0 )
                  {
                    std::wstring::_Tidy(String1, v22, 0);
                    goto LABEL_59;
                  }
                  std::wstring::_Tidy(String1, v22, 0);
                }
                else if ( WPP_GLOBAL_Control != (LPCWSTR)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
                {
                  WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids);
                }
                if ( !a7 || (BITSJob = SetCostFlags(v29, a7), BITSJob >= 0) )
                {
                  BITSJob = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, _QWORD))v29->lpVtbl->SetPriority)(
                              v29,
                              (unsigned int)v33);
                  if ( BITSJob >= 0 )
                  {
                    BITSJob = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, _QWORD))v29->lpVtbl->SetNoProgressTimeout)(
                                v29,
                                a6);
                    if ( BITSJob >= 0 )
                    {
                      BITSJob = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, _QWORD))v29->lpVtbl->SetMinimumRetryDelay)(
                                  v29,
                                  a5);
                      if ( BITSJob >= 0 )
                      {
                        if ( ExpandEnvironmentStringsW(L"%windir%\\System32\\deviceenroller.exe", Dst, 0x104u) )
                        {
                          StringCchPrintfW(v44, 0xFA1u, L"%s /o \"%s\" /c /x", Dst, SubKey);
                          StringFromGUID2(rguid, sz, 260);
                          BITSJob = (*(__int64 (__fastcall **)(__int64, WCHAR *, unsigned __int16 *))(*(_QWORD *)v32 + 280LL))(
                                      v32,
                                      Dst,
                                      v44);
                          if ( BITSJob >= 0 )
                          {
                            BITSJob = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, __int64))v29->lpVtbl->SetNotifyFlags)(
                                        v29,
                                        3);
                            if ( BITSJob >= 0 )
                            {
                              BITSJob = (*(__int64 (__fastcall **)(char *, GUID *))(*((_QWORD *)a10 + 1) + 24LL))(
                                          (char *)a10 + 8,
                                          rguid);
                              if ( BITSJob >= 0 )
                              {
                                BITSJob = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *, const unsigned __int16 *, const unsigned __int16 *))v29->lpVtbl->AddFile)(
                                            v29,
                                            a2,
                                            v35);
                                if ( BITSJob >= 0 )
                                {
                                  BITSJob = ((__int64 (__fastcall *)(struct IBackgroundCopyJob *))v29->lpVtbl->Resume)(v29);
                                  if ( BITSJob >= 0 )
                                  {
                                    ATL::CComPtr<IBackgroundCopyJob>::Release(&v29);
                                    if ( v13 )
                                    {
                                      v24 = (const unsigned __int16 *)((char *)this + 16);
                                      if ( *((_QWORD *)this + 5) >= 8u )
                                        v24 = *(const unsigned __int16 **)v24;
                                      BITSJob = _ImpersonateUser(v24, *((_DWORD *)this + 12), &v28);
                                      if ( BITSJob >= 0 )
                                        v13 = 0;
                                    }
                                  }
                                }
                              }
                            }
                          }
                        }
                        else
                        {
                          LastError = GetLastError();
                          BITSJob = LastError;
                          if ( LastError > 0 )
                            BITSJob = (unsigned __int16)LastError | 0x80070000;
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
LABEL_59:
  if ( hkey )
    RegCloseKey(hkey);
  if ( BITSJob < 0 && v29 )
    ((void (__fastcall *)(struct IBackgroundCopyJob *))v29->lpVtbl->Cancel)(v29);
  if ( v13 && !v28 )
  {
    v25 = (const unsigned __int16 *)((char *)this + 16);
    if ( *((_QWORD *)this + 5) >= 8u )
      v25 = *(const unsigned __int16 **)v25;
    v26 = _ImpersonateUser(v25, *((_DWORD *)this + 12), &v28);
    if ( BITSJob >= 0 )
      BITSJob = v26;
  }
LABEL_70:
  ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(&v31);
  ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(&v32);
  ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(&v36);
  ATL::CComPtr<IBackgroundCopyCallback>::~CComPtr<IBackgroundCopyCallback>(&v29);
  return (unsigned int)BITSJob;
}

```

## disassembly

```asm
0x18001b05c  push    rbp
0x18001b05e  push    rbx
0x18001b05f  push    rsi
0x18001b060  push    rdi
0x18001b061  push    r12
0x18001b063  push    r13
0x18001b065  push    r14
0x18001b067  push    r15
0x18001b069  lea     rbp, [rsp-2768h]
0x18001b071  mov     eax, 2868h
0x18001b076  call    _alloca_probe
0x18001b07b  sub     rsp, rax
0x18001b07e  mov     rax, cs:__security_cookie
0x18001b085  xor     rax, rsp
0x18001b088  mov     [rbp+27A0h+var_50], rax
0x18001b08f  mov     [rsp+28A0h+var_2838], r9d
0x18001b094  mov     [rsp+28A0h+var_2828], r8
0x18001b099  mov     r12, rdx
0x18001b09c  mov     rsi, rcx
0x18001b09f  mov     r15, [rbp+27A0h+rguid]
0x18001b0a6  mov     r13, [rbp+27A0h+arg_48]
0x18001b0ad  mov     [rsp+28A0h+var_2858], 0
0x18001b0b6  mov     [rbp+27A0h+var_2820], 0
0x18001b0be  mov     [rsp+28A0h+var_2840], 0
0x18001b0c7  mov     [rsp+28A0h+var_2848], 0
0x18001b0d0  mov     [rsp+28A0h+hkey], 0
0x18001b0d9  mov     ebx, 20Ah
0x18001b0de  mov     r8d, ebx; Size
0x18001b0e1  xor     edx, edx; Val
0x18001b0e3  lea     rcx, [rbp+27A0h+var_23C0]; void *
0x18001b0ea  call    memset_0
0x18001b0ef  mov     [rsp+28A0h+var_2850], ebx
0x18001b0f3  mov     [rsp+28A0h+var_2860], 0
0x18001b0f8  xorps   xmm0, xmm0
0x18001b0fb  xor     eax, eax
0x18001b0fd  movups  [rbp+27A0h+var_2818], xmm0
0x18001b101  mov     [rbp+27A0h+var_2808], rax
0x18001b105  test    r15, r15
0x18001b108  jz      short loc_18001B10F
0x18001b10a  test    r13, r13
0x18001b10d  jnz     short loc_18001B119
0x18001b10f  mov     ebx, 80070057h
0x18001b114  jmp     loc_18001B664
0x18001b119  xor     r14b, r14b
0x18001b11c  cmp     [rsi+8], al
0x18001b11f  jz      short loc_18001B137
0x18001b121  lea     rcx, [rsi+10h]
0x18001b125  cmp     qword ptr [rcx+18h], 8
0x18001b12a  jb      short loc_18001B12F
0x18001b12c  mov     rcx, [rcx]; unsigned __int16 *
0x18001b12f  call    ?_RevertToSelf@@YAXPEBG@Z; _RevertToSelf(ushort const *)
0x18001b134  mov     r14b, 1
0x18001b137  mov     rdx, r12
0x18001b13a  lea     rcx, [rbp+27A0h+String1]
0x18001b13e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001b143  nop
0x18001b144  lea     rdx, [rsp+28A0h+var_2858]
0x18001b149  lea     rcx, [rbp+27A0h+String1]; String1
0x18001b14d  call    ?CreateBITSJob@@YAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAUIBackgroundCopyJob@@@Z; CreateBITSJob(std::wstring const &,IBackgroundCopyJob * *)
0x18001b152  mov     ebx, eax
0x18001b154  xor     r8d, r8d
0x18001b157  mov     dl, 1
0x18001b159  lea     rcx, [rbp+27A0h+String1]
0x18001b15d  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001b162  mov     eax, ebx
0x18001b164  shr     eax, 1Fh
0x18001b167  test    al, al
0x18001b169  jnz     loc_18001B608
0x18001b16f  mov     rcx, [rsp+28A0h+var_2858]
0x18001b174  mov     rax, [rcx]
0x18001b177  mov     rdx, r15
0x18001b17a  mov     rax, [rax+50h]
0x18001b17e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b183  mov     ebx, eax
0x18001b185  test    eax, eax
0x18001b187  js      loc_18001B608
0x18001b18d  mov     rcx, [rsp+28A0h+var_2858]; struct IBackgroundCopyJob *
0x18001b192  call    ?SetNullCredentials@@YAJPEAUIBackgroundCopyJob@@@Z; SetNullCredentials(IBackgroundCopyJob *)
0x18001b197  mov     ebx, eax
0x18001b199  test    eax, eax
0x18001b19b  js      loc_18001B608
0x18001b1a1  mov     rcx, [rsp+28A0h+var_2858]
0x18001b1a6  mov     rax, [rcx]
0x18001b1a9  lea     r8, [rsp+28A0h+var_2848]
0x18001b1ae  lea     rdx, _GUID_9a2584c3_f7d2_457a_9a5e_22b67bffc7d2
0x18001b1b5  mov     rax, [rax]
0x18001b1b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1bd  mov     ebx, eax
0x18001b1bf  test    eax, eax
0x18001b1c1  js      loc_18001B608
0x18001b1c7  mov     rcx, [rsp+28A0h+var_2858]
0x18001b1cc  mov     rax, [rcx]
0x18001b1cf  lea     r8, [rsp+28A0h+var_2840]
0x18001b1d4  lea     rdx, _GUID_54b50739_686f_45eb_9dff_d6a9a0faa9af
0x18001b1db  mov     rax, [rax]
0x18001b1de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b1e3  mov     ebx, eax
0x18001b1e5  test    eax, eax
0x18001b1e7  js      loc_18001B608
0x18001b1ed  mov     dword ptr [rbp+27A0h+var_2818+4], 4
0x18001b1f4  xorps   xmm0, xmm0
0x18001b1f7  movdqu  [rbp+27A0h+var_2818+8], xmm0
0x18001b1fc  mov     dword ptr [rbp+27A0h+var_2818], 2
0x18001b203  mov     rcx, [rsp+28A0h+var_2840]
0x18001b208  mov     rax, [rcx]
0x18001b20b  lea     rdx, [rbp+27A0h+var_2818]
0x18001b20f  mov     rax, [rax+148h]
0x18001b216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b21b  mov     ebx, eax
0x18001b21d  test    eax, eax
0x18001b21f  js      loc_18001B608
0x18001b225  mov     rcx, [rsp+28A0h+var_2858]
0x18001b22a  mov     rax, [rcx]
0x18001b22d  xor     r9d, r9d
0x18001b230  xor     r8d, r8d
0x18001b233  xor     edx, edx
0x18001b235  mov     rax, [rax+100h]
0x18001b23c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b241  mov     ebx, eax
0x18001b243  test    eax, eax
0x18001b245  js      loc_18001B608
0x18001b24b  test    r14b, r14b
0x18001b24e  jz      short loc_18001B2AD
0x18001b250  lea     rdi, [rsi+10h]
0x18001b254  cmp     qword ptr [rdi+18h], 8
0x18001b259  jb      short loc_18001B260
0x18001b25b  mov     rcx, [rdi]
0x18001b25e  jmp     short loc_18001B263
0x18001b260  mov     rcx, rdi; unsigned __int16 *
0x18001b263  lea     r8, [rsp+28A0h+var_2860]; bool *
0x18001b268  mov     edx, [rsi+30h]; unsigned int
0x18001b26b  call    ?_ImpersonateUser@@YAJPEBGKAEA_N@Z; _ImpersonateUser(ushort const *,ulong,bool &)
0x18001b270  mov     ebx, eax
0x18001b272  test    eax, eax
0x18001b274  js      loc_18001B608
0x18001b27a  xor     r14b, r14b
0x18001b27d  mov     rcx, [rsp+28A0h+var_2848]
0x18001b282  mov     rax, [rcx]
0x18001b285  mov     rax, [rax+28h]
0x18001b289  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b28e  mov     ebx, eax
0x18001b290  test    eax, eax
0x18001b292  js      loc_18001B608
0x18001b298  cmp     qword ptr [rdi+18h], 8
0x18001b29d  jb      short loc_18001B2A2
0x18001b29f  mov     rdi, [rdi]
0x18001b2a2  mov     rcx, rdi; unsigned __int16 *
0x18001b2a5  call    ?_RevertToSelf@@YAXPEBG@Z; _RevertToSelf(ushort const *)
0x18001b2aa  mov     r14b, 1
0x18001b2ad  mov     rcx, [rsp+28A0h+var_2848]
0x18001b2b2  mov     rax, [rcx]
0x18001b2b5  mov     edx, 2
0x18001b2ba  mov     rax, [rax+18h]
0x18001b2be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2c3  mov     ebx, eax
0x18001b2c5  test    eax, eax
0x18001b2c7  js      loc_18001B608
0x18001b2cd  call    ?GetClientCertMode@@YA?AW4CLIENT_CERT_MODE@@XZ; GetClientCertMode(void)
0x18001b2d2  xor     edi, edi
0x18001b2d4  cmp     eax, 1
0x18001b2d7  setz    dil
0x18001b2db  lea     rcx, [rbp+27A0h+SubKey]; unsigned __int16 *
0x18001b2df  call    ?GetEnrollmentID@@YAJPEAG@Z; GetEnrollmentID(ushort *)
0x18001b2e4  mov     ebx, eax
0x18001b2e6  test    eax, eax
0x18001b2e8  js      loc_18001B608
0x18001b2ee  lea     rax, [rsp+28A0h+hkey]
0x18001b2f3  mov     [rsp+28A0h+phkResult], rax; phkResult
0x18001b2f8  mov     r9d, 20019h; samDesired
0x18001b2fe  xor     r8d, r8d; ulOptions
0x18001b301  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Enrollments"
0x18001b308  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001b30f  call    cs:__imp_RegOpenKeyExW
0x18001b316  nop     dword ptr [rax+rax+00h]
0x18001b31b  mov     ebx, eax
0x18001b31d  test    eax, eax
0x18001b31f  jle     short loc_18001B32A
0x18001b321  movzx   ebx, ax
0x18001b324  or      ebx, 80070000h
0x18001b32a  test    ebx, ebx
0x18001b32c  js      loc_18001B608
0x18001b332  lea     rax, [rsp+28A0h+var_2850]
0x18001b337  mov     [rsp+28A0h+pcbData], rax; pcbData
0x18001b33c  lea     rax, [rbp+27A0h+var_23C0]
0x18001b343  mov     [rsp+28A0h+pvData], rax; pvData
0x18001b348  mov     [rsp+28A0h+phkResult], 0; pdwType
0x18001b351  mov     r9d, 2; dwFlags
0x18001b357  lea     r8, Value; "DMPCertThumbPrint"
0x18001b35e  lea     rdx, [rbp+27A0h+SubKey]; lpSubKey
0x18001b362  mov     rcx, [rsp+28A0h+hkey]; hkey
0x18001b367  call    cs:__imp_RegGetValueW
0x18001b36e  nop     dword ptr [rax+rax+00h]
0x18001b373  mov     ebx, eax
0x18001b375  test    eax, eax
0x18001b377  jle     short loc_18001B382
0x18001b379  movzx   ebx, ax
0x18001b37c  or      ebx, 80070000h
0x18001b382  test    ebx, ebx
0x18001b384  js      loc_18001B608
0x18001b38a  cmp     [rsp+28A0h+var_2850], 0
0x18001b38f  jz      short loc_18001B3F6
0x18001b391  lea     rdx, aMy; "MY"
0x18001b398  lea     rcx, [rbp+27A0h+String1]
0x18001b39c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x18001b3a1  nop
0x18001b3a2  lea     rcx, [rbp+27A0h+String1]
0x18001b3a6  call    ?GetCertStore@@YAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; GetCertStore(std::wstring &)
0x18001b3ab  lea     r8, [rbp+27A0h+String1]
0x18001b3af  cmp     [rbp+27A0h+var_27E8], 8
0x18001b3b4  cmovnb  r8, qword ptr [rbp+27A0h+String1]; unsigned __int16 *
0x18001b3b9  mov     eax, [rbp+27A0h+arg_38]
0x18001b3bf  mov     dword ptr [rsp+28A0h+phkResult], eax; int
0x18001b3c3  lea     r9, [rbp+27A0h+var_23C0]; unsigned __int16 *
0x18001b3ca  mov     edx, edi; enum BG_CERT_STORE_LOCATION
0x18001b3cc  mov     rcx, [rsp+28A0h+var_2858]; struct IBackgroundCopyJob *
0x18001b3d1  call    ?SetSecurityOptions@@YAJPEAUIBackgroundCopyJob@@W4BG_CERT_STORE_LOCATION@@PEBG2H@Z; SetSecurityOptions(IBackgroundCopyJob *,BG_CERT_STORE_LOCATION,ushort const *,ushort const *,int)
0x18001b3d6  mov     ebx, eax
0x18001b3d8  xor     r8d, r8d
0x18001b3db  mov     dl, 1
0x18001b3dd  lea     rcx, [rbp+27A0h+String1]
0x18001b3e1  test    eax, eax
0x18001b3e3  jns     short loc_18001B3EF
0x18001b3e5  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001b3ea  jmp     loc_18001B608
0x18001b3ef  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001b3f4  jmp     short loc_18001B424
0x18001b3f6  lea     rax, WPP_GLOBAL_Control
0x18001b3fd  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b404  cmp     rcx, rax
0x18001b407  jz      short loc_18001B424
0x18001b409  test    byte ptr [rcx+1Ch], 4
0x18001b40d  jz      short loc_18001B424
0x18001b40f  mov     edx, 16h
0x18001b414  lea     r8, WPP_26f90604ebd834e0d5ed309148d8b5dc_Traceguids
0x18001b41b  mov     rcx, [rcx+10h]
0x18001b41f  call    WPP_SF_
0x18001b424  mov     edx, [rbp+27A0h+arg_30]; unsigned int
0x18001b42a  test    edx, edx
0x18001b42c  jz      short loc_18001B442
0x18001b42e  mov     rcx, [rsp+28A0h+var_2858]; struct IBackgroundCopyJob *
0x18001b433  call    ?SetCostFlags@@YAJPEAUIBackgroundCopyJob@@K@Z; SetCostFlags(IBackgroundCopyJob *,ulong)
0x18001b438  mov     ebx, eax
0x18001b43a  test    eax, eax
0x18001b43c  js      loc_18001B608
0x18001b442  mov     rcx, [rsp+28A0h+var_2858]
0x18001b447  mov     rax, [rcx]
0x18001b44a  mov     edx, [rsp+28A0h+var_2838]
0x18001b44e  mov     rax, [rax+0A8h]
0x18001b455  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b45a  mov     ebx, eax
0x18001b45c  test    eax, eax
0x18001b45e  js      loc_18001B608
0x18001b464  mov     rcx, [rsp+28A0h+var_2858]
0x18001b469  mov     rax, [rcx]
0x18001b46c  mov     edx, [rbp+27A0h+arg_28]
0x18001b472  mov     rax, [rax+0E8h]
0x18001b479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b47e  mov     ebx, eax
0x18001b480  test    eax, eax
0x18001b482  js      loc_18001B608
0x18001b488  mov     rcx, [rsp+28A0h+var_2858]
0x18001b48d  mov     rax, [rcx]
0x18001b490  mov     edx, [rbp+27A0h+arg_20]
0x18001b496  mov     rax, [rax+0D8h]
0x18001b49d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b4a2  mov     ebx, eax
0x18001b4a4  test    eax, eax
0x18001b4a6  js      loc_18001B608
0x18001b4ac  mov     ebx, 104h
0x18001b4b1  mov     r8d, ebx; nSize
0x18001b4b4  lea     rdx, [rbp+27A0h+Dst]; lpDst
0x18001b4bb  lea     rcx, Src; "%windir%\\System32\\deviceenroller.exe"
0x18001b4c2  call    cs:__imp_ExpandEnvironmentStringsW
0x18001b4c9  nop     dword ptr [rax+rax+00h]
0x18001b4ce  test    eax, eax
0x18001b4d0  jnz     short loc_18001B4F6
0x18001b4d2  call    cs:__imp_GetLastError
0x18001b4d9  nop     dword ptr [rax+rax+00h]
0x18001b4de  mov     ebx, eax
0x18001b4e0  test    eax, eax
0x18001b4e2  jle     loc_18001B608
0x18001b4e8  movzx   ebx, ax
0x18001b4eb  or      ebx, 80070000h
0x18001b4f1  jmp     loc_18001B608
0x18001b4f6  lea     rax, [rbp+27A0h+SubKey]
0x18001b4fa  mov     [rsp+28A0h+phkResult], rax
0x18001b4ff  lea     r9, [rbp+27A0h+Dst]
0x18001b506  lea     r8, aSOSCX; "%s /o \"%s\" /c /x"
0x18001b50d  mov     edx, 0FA1h; unsigned __int64
0x18001b512  lea     rcx, [rbp+27A0h+var_1FA0]; unsigned __int16 *
0x18001b519  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001b51e  mov     r8d, ebx; cchMax
0x18001b521  lea     rdx, [rbp+27A0h+sz]; lpsz
0x18001b528  mov     rcx, r15; rguid
0x18001b52b  call    cs:__imp_StringFromGUID2
0x18001b532  nop     dword ptr [rax+rax+00h]
0x18001b537  mov     rcx, [rsp+28A0h+var_2840]
0x18001b53c  mov     rax, [rcx]
0x18001b53f  lea     r8, [rbp+27A0h+var_1FA0]
0x18001b546  lea     rdx, [rbp+27A0h+Dst]
  ... truncated ...
```
