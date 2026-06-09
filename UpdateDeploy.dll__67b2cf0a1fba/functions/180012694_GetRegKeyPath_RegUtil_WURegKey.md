# GetRegKeyPath(RegUtil::WURegKey)

- ea: `0x180012694`
- end: `0x1800128e3`
- name: `?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z`
- size: `591`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180003824`
- `0x180012694`
- `0x180013494`
- `0x1800330b8`
- `0x18004b048`
- `0x18004b240`

## callees

- `0x180003c94`
- `0x180008b30`
- `0x18000970c`
- `0x18000dce4`
- `0x180012694`
- `0x1800460a0`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800128b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800128b2`

## string_xrefs

- `0x1800127be`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsUpdate`
- `0x18001275e`: `SOFTWARE\Microsoft\WindowsUpdate`
- `0x180012765`: `WindowsUpdate`
- `0x18001273f`: `AdapterCacheKeyID`
- `0x180012833`: `SQMClientLink`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetRegKeyPath(int a1, __int64 a2, __int64 a3, wchar_t **a4)
{
  __int64 v4; // rax
  void *v5; // rcx
  __int64 v6; // rdi
  int v7; // edx
  int v8; // edx
  int v9; // edx
  int v10; // edx
  int v11; // edx
  const wchar_t *v12; // rdx
  wchar_t *v13; // rcx
  const wchar_t *v14; // rdx
  wchar_t *v15; // rcx
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rbx
  __int64 RegKeyPath; // r9
  int v20; // edx
  int v21; // edx
  int v22; // edx
  int v23; // edx
  __int64 v24; // rbx
  signed __int64 v26; // [rsp+38h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-C8h] BYREF
  wchar_t Buffer[264]; // [rsp+48h] [rbp-C0h] BYREF

  v4 = a1;
  v5 = 0;
  pv = 0;
  v26 = 0;
  v6 = 3 * v4;
  if ( !*(&RegUtil::paths + 3 * v4 + 2) )
  {
    v7 = *((_DWORD *)&RegUtil::paths + 6 * v4 + 1);
    if ( v7 > 6 )
    {
      v20 = v7 - 7;
      if ( !v20 )
      {
        v12 = L"SOFTWARE\\Microsoft\\SQMClient";
        v13 = L"SQMClientLink";
        goto LABEL_31;
      }
      v21 = v20 - 1;
      if ( !v21 )
      {
        v12 = L"Software\\Policies\\Microsoft\\WindowsStore\\Apps";
        v13 = L"EnterpriseModernAppReleaseManagement";
        goto LABEL_31;
      }
      v22 = v21 - 1;
      if ( !v22 )
      {
        v12 = L"Software\\Microsoft\\WindowsSelfHost";
        v13 = L"WindowsSelfhost";
        goto LABEL_31;
      }
      v23 = v22 - 1;
      if ( v23 )
      {
        if ( v23 != 1 )
          goto LABEL_37;
        v14 = L"SYSTEM\\CurrentControlSet\\Control\\FeatureManagement";
        v15 = L"FeatureManagement";
        goto LABEL_14;
      }
      v17 = 35;
    }
    else if ( v7 == 6 )
    {
      v17 = 29;
    }
    else
    {
      if ( !v7 )
      {
        v12 = L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate";
        v13 = L"WUCurrentVersion";
        goto LABEL_31;
      }
      v8 = v7 - 1;
      if ( v8 )
      {
        v9 = v8 - 1;
        if ( v9 )
        {
          v10 = v9 - 1;
          if ( v10 )
          {
            v11 = v10 - 1;
            if ( v11 )
            {
              if ( v11 != 1 )
                goto LABEL_37;
              v12 = L"SOFTWARE\\Microsoft\\SIH";
              v13 = L"SIH";
            }
            else
            {
              v12 = L"Software\\Microsoft\\DirectX";
              v13 = L"AdapterCacheKeyID";
            }
          }
          else
          {
            v12 = L"Software\\Microsoft\\Windows\\CurrentVersion\\Appx";
            v13 = L"AppxRoot";
          }
LABEL_31:
          if ( (int)WUSystemInterfaceHelper::GetPersistedRegistryLocation(
                      (WUSystemInterfaceHelper *)v13,
                      v12,
                      (const wchar_t *)&pv,
                      a4) >= 0 )
          {
            v16 = StringCchCopyExW(Buffer, 0x104u, (const wchar_t *)pv, 0, 0, 0x100u);
            goto LABEL_33;
          }
LABEL_36:
          v5 = pv;
          goto LABEL_37;
        }
        v14 = L"SOFTWARE\\Microsoft\\WindowsUpdate";
        v15 = L"WindowsUpdate";
LABEL_14:
        if ( (int)WUSystemInterfaceHelper::GetPersistedRegistryLocation(
                    (WUSystemInterfaceHelper *)v15,
                    v14,
                    (const wchar_t *)&pv,
                    a4) >= 0 )
        {
          v16 = StringCchPrintfW(Buffer, 0x104u, L"%s\\%s", pv, *(&RegUtil::paths + v6 + 1));
          goto LABEL_33;
        }
        goto LABEL_36;
      }
      v17 = 0;
    }
    v18 = (__int64)*(&RegUtil::paths + 3 * v4 + 1);
    RegKeyPath = GetRegKeyPath(v17);
    v16 = StringCchPrintfW(Buffer, 0x104u, L"%s\\%s", RegKeyPath, v18);
LABEL_33:
    if ( v16 >= 0 && (int)DuplicateString<wchar_t *,wchar_t *>(Buffer, &v26) >= 0 )
      SusFree((void *)(v26
                     & -(__int64)(_InterlockedCompareExchange64(
                                    (volatile signed __int64 *)&RegUtil::paths + v6 + 2,
                                    v26,
                                    0) != 0)));
    goto LABEL_36;
  }
LABEL_37:
  v24 = (__int64)*(&RegUtil::paths + v6 + 2);
  if ( v5 )
    CoTaskMemFree(v5);
  return v24;
}

```

## disassembly

```asm
0x180012694  mov     rax, rsp
0x180012697  mov     [rax+10h], rbx
0x18001269b  mov     [rax+18h], rdi
0x18001269f  mov     [rax+20h], r14
0x1800126a3  push    rbp
0x1800126a4  lea     rbp, [rax-168h]
0x1800126ab  sub     rsp, 260h
0x1800126b2  mov     rax, cs:__security_cookie
0x1800126b9  xor     rax, rsp
0x1800126bc  mov     [rbp+160h+var_10], rax
0x1800126c3  movsxd  rax, ecx
0x1800126c6  xor     ecx, ecx
0x1800126c8  mov     [rsp+260h+pv], rcx
0x1800126cd  mov     [rsp+260h+var_230], rcx
0x1800126d2  lea     rdi, [rax+rax*2]
0x1800126d6  lea     r14, ?paths@RegUtil@@3PAUkeyMap@1@A; RegUtil::keyMap near * RegUtil::paths
0x1800126dd  cmp     [r14+rdi*8+10h], rcx
0x1800126e2  jnz     loc_1800128A8
0x1800126e8  mov     edx, [r14+rdi*8+4]
0x1800126ed  cmp     edx, 6
0x1800126f0  jg      loc_1800127D5
0x1800126f6  jz      loc_1800127CE
0x1800126fc  test    edx, edx
0x1800126fe  jz      loc_1800127BE
0x180012704  sub     edx, 1
0x180012707  jz      loc_1800127A8
0x18001270d  sub     edx, 1
0x180012710  jz      short loc_18001275E
0x180012712  sub     edx, 1
0x180012715  jz      short loc_18001274B
0x180012717  sub     edx, 1
0x18001271a  jz      short loc_180012738
0x18001271c  cmp     edx, 1
0x18001271f  jnz     loc_1800128A8
0x180012725  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\SIH"
0x18001272c  lea     rcx, aSih; "SIH"
0x180012733  jmp     loc_18001283A
0x180012738  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\DirectX"
0x18001273f  lea     rcx, aAdaptercacheke; "AdapterCacheKeyID"
0x180012746  jmp     loc_18001283A
0x18001274b  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180012752  lea     rcx, aAppxroot; "AppxRoot"
0x180012759  jmp     loc_18001283A
0x18001275e  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\WindowsUpdate"
0x180012765  lea     rcx, aWindowsupdate; "WindowsUpdate"
0x18001276c  lea     r8, [rsp+260h+pv]; wchar_t *
0x180012771  call    ?GetPersistedRegistryLocation@WUSystemInterfaceHelper@@YAJPEB_W0PEAPEA_W@Z; WUSystemInterfaceHelper::GetPersistedRegistryLocation(wchar_t const *,wchar_t const *,wchar_t * *)
0x180012776  test    eax, eax
0x180012778  js      loc_1800128A3
0x18001277e  mov     rax, [r14+rdi*8+8]
0x180012783  mov     [rsp+260h+var_240], rax
0x180012788  mov     r9, [rsp+260h+pv]
0x18001278d  lea     r8, aSS; "%s\\%s"
0x180012794  mov     edx, 104h; unsigned __int64
0x180012799  lea     rcx, [rsp+260h+Buffer]; Buffer
0x18001279e  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800127a3  jmp     loc_180012870
0x1800127a8  xor     ecx, ecx
0x1800127aa  mov     rbx, [r14+rdi*8+8]
0x1800127af  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x1800127b4  mov     [rsp+260h+var_240], rbx
0x1800127b9  mov     r9, rax
0x1800127bc  jmp     short loc_18001278D
0x1800127be  lea     rdx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800127c5  lea     rcx, aWucurrentversi; "WUCurrentVersion"
0x1800127cc  jmp     short loc_18001283A
0x1800127ce  mov     ecx, 1Dh
0x1800127d3  jmp     short loc_1800127AA
0x1800127d5  sub     edx, 7
0x1800127d8  jz      short loc_18001282C
0x1800127da  sub     edx, 1
0x1800127dd  jz      short loc_18001281C
0x1800127df  sub     edx, 1
0x1800127e2  jz      short loc_18001280C
0x1800127e4  sub     edx, 1
0x1800127e7  jz      short loc_180012805
0x1800127e9  cmp     edx, 1
0x1800127ec  jnz     loc_1800128A8
0x1800127f2  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Fea"...
0x1800127f9  lea     rcx, aFeaturemanagem; "FeatureManagement"
0x180012800  jmp     loc_18001276C
0x180012805  mov     ecx, 23h ; '#'
0x18001280a  jmp     short loc_1800127AA
0x18001280c  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\WindowsSelfHost"
0x180012813  lea     rcx, aWindowsselfhos; "WindowsSelfhost"
0x18001281a  jmp     short loc_18001283A
0x18001281c  lea     rdx, aSoftwarePolici_1; "Software\\Policies\\Microsoft\\WindowsS"...
0x180012823  lea     rcx, aEnterprisemode; "EnterpriseModernAppReleaseManagement"
0x18001282a  jmp     short loc_18001283A
0x18001282c  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\SQMClient"
0x180012833  lea     rcx, aSqmclientlink; "SQMClientLink"
0x18001283a  lea     r8, [rsp+260h+pv]; wchar_t *
0x18001283f  call    ?GetPersistedRegistryLocation@WUSystemInterfaceHelper@@YAJPEB_W0PEAPEA_W@Z; WUSystemInterfaceHelper::GetPersistedRegistryLocation(wchar_t const *,wchar_t const *,wchar_t * *)
0x180012844  test    eax, eax
0x180012846  js      short loc_1800128A3
0x180012848  mov     [rsp+260h+var_238], 100h; unsigned int
0x180012850  mov     [rsp+260h+var_240], 0; unsigned __int64 *
0x180012859  xor     r9d, r9d; wchar_t **
0x18001285c  mov     r8, [rsp+260h+pv]; wchar_t *
0x180012861  mov     edx, 104h; unsigned __int64
0x180012866  lea     rcx, [rsp+260h+Buffer]; pszDest
0x18001286b  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x180012870  test    eax, eax
0x180012872  js      short loc_1800128A3
0x180012874  lea     rdx, [rsp+260h+var_230]
0x180012879  lea     rcx, [rsp+260h+Buffer]
0x18001287e  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x180012883  test    eax, eax
0x180012885  js      short loc_1800128A3
0x180012887  mov     rdx, [rsp+260h+var_230]
0x18001288c  xor     eax, eax
0x18001288e  lock cmpxchg [r14+rdi*8+10h], rdx
0x180012895  neg     rax
0x180012898  sbb     rcx, rcx
0x18001289b  and     rcx, rdx; lpMem
0x18001289e  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1800128a3  mov     rcx, [rsp+260h+pv]; pv
0x1800128a8  mov     rbx, [r14+rdi*8+10h]
0x1800128ad  test    rcx, rcx
0x1800128b0  jz      short loc_1800128B8
0x1800128b2  call    cs:__imp_CoTaskMemFree
0x1800128b8  mov     rax, rbx
0x1800128bb  mov     rcx, [rbp+160h+var_10]
0x1800128c2  xor     rcx, rsp; StackCookie
0x1800128c5  call    __security_check_cookie
0x1800128ca  lea     r11, [rsp+260h+var_s0]
0x1800128d2  mov     rbx, [r11+18h]
0x1800128d6  mov     rdi, [r11+20h]
0x1800128da  mov     r14, [r11+28h]
0x1800128de  mov     rsp, r11
0x1800128e1  pop     rbp
0x1800128e2  retn
```
