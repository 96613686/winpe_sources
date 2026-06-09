# GetRegKeyPath(RegUtil::WURegKey)

- ea: `0x140018394`
- end: `0x1400185e3`
- name: `?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z`
- size: `591`
- prototype: `__int64 __fastcall(int, __int64, __int64, wchar_t **)`
- caller_count: `27`
- callee_count: `7`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x140003ee0`
- `0x140004174`
- `0x140004a7c`
- `0x1400052ec`
- `0x14000add0`
- `0x140015f20`
- `0x140016108`
- `0x1400167cc`
- `0x140016c54`
- `0x140017020`
- `0x140018394`
- `0x14002012c`
- `0x1400203ac`
- `0x140020814`
- `0x140023414`
- `0x14002350c`
- `0x14002387c`
- `0x140023974`
- `0x140023a3c`
- `0x140023ce0`
- `0x140023db4`
- `0x140024764`
- `0x140027b28`
- `0x140032cc0`
- `0x1400356ac`
- `0x14003585c`
- `0x14003f448`

## callees

- `0x140007780`
- `0x14000ce30`
- `0x14000db18`
- `0x1400116a4`
- `0x140018394`
- `0x1400191b8`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400185b2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400185b2`

## string_xrefs

- `0x1400184be`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsUpdate`
- `0x14001845e`: `SOFTWARE\Microsoft\WindowsUpdate`
- `0x140018465`: `WindowsUpdate`
- `0x14001843f`: `AdapterCacheKeyID`
- `0x140018533`: `SQMClientLink`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
              v13 = (wchar_t *)L"SIH";
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
0x140018394  mov     rax, rsp
0x140018397  mov     [rax+10h], rbx
0x14001839b  mov     [rax+18h], rdi
0x14001839f  mov     [rax+20h], r14
0x1400183a3  push    rbp
0x1400183a4  lea     rbp, [rax-168h]
0x1400183ab  sub     rsp, 260h
0x1400183b2  mov     rax, cs:__security_cookie
0x1400183b9  xor     rax, rsp
0x1400183bc  mov     [rbp+160h+var_10], rax
0x1400183c3  movsxd  rax, ecx
0x1400183c6  xor     ecx, ecx
0x1400183c8  mov     [rsp+260h+pv], rcx
0x1400183cd  mov     [rsp+260h+var_230], rcx
0x1400183d2  lea     rdi, [rax+rax*2]
0x1400183d6  lea     r14, ?paths@RegUtil@@3PAUkeyMap@1@A; RegUtil::keyMap near * RegUtil::paths
0x1400183dd  cmp     [r14+rdi*8+10h], rcx
0x1400183e2  jnz     loc_1400185A8
0x1400183e8  mov     edx, [r14+rdi*8+4]
0x1400183ed  cmp     edx, 6
0x1400183f0  jg      loc_1400184D5
0x1400183f6  jz      loc_1400184CE
0x1400183fc  test    edx, edx
0x1400183fe  jz      loc_1400184BE
0x140018404  sub     edx, 1
0x140018407  jz      loc_1400184A8
0x14001840d  sub     edx, 1
0x140018410  jz      short loc_14001845E
0x140018412  sub     edx, 1
0x140018415  jz      short loc_14001844B
0x140018417  sub     edx, 1
0x14001841a  jz      short loc_140018438
0x14001841c  cmp     edx, 1
0x14001841f  jnz     loc_1400185A8
0x140018425  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\SIH"
0x14001842c  lea     rcx, aSih; "SIH"
0x140018433  jmp     loc_14001853A
0x140018438  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\DirectX"
0x14001843f  lea     rcx, aAdaptercacheke; "AdapterCacheKeyID"
0x140018446  jmp     loc_14001853A
0x14001844b  lea     rdx, aSoftwareMicros_4; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140018452  lea     rcx, aAppxroot; "AppxRoot"
0x140018459  jmp     loc_14001853A
0x14001845e  lea     rdx, aSoftwareMicros; "SOFTWARE\\Microsoft\\WindowsUpdate"
0x140018465  lea     rcx, aWindowsupdate; "WindowsUpdate"
0x14001846c  lea     r8, [rsp+260h+pv]; wchar_t *
0x140018471  call    ?GetPersistedRegistryLocation@WUSystemInterfaceHelper@@YAJPEB_W0PEAPEA_W@Z; WUSystemInterfaceHelper::GetPersistedRegistryLocation(wchar_t const *,wchar_t const *,wchar_t * *)
0x140018476  test    eax, eax
0x140018478  js      loc_1400185A3
0x14001847e  mov     rax, [r14+rdi*8+8]
0x140018483  mov     [rsp+260h+var_240], rax
0x140018488  mov     r9, [rsp+260h+pv]
0x14001848d  lea     r8, aSS; "%s\\%s"
0x140018494  mov     edx, 104h; unsigned __int64
0x140018499  lea     rcx, [rsp+260h+Buffer]; Buffer
0x14001849e  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1400184a3  jmp     loc_140018570
0x1400184a8  xor     ecx, ecx
0x1400184aa  mov     rbx, [r14+rdi*8+8]
0x1400184af  call    ?GetRegKeyPath@@YAPEB_WW4WURegKey@RegUtil@@@Z; GetRegKeyPath(RegUtil::WURegKey)
0x1400184b4  mov     [rsp+260h+var_240], rbx
0x1400184b9  mov     r9, rax
0x1400184bc  jmp     short loc_14001848D
0x1400184be  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1400184c5  lea     rcx, aWucurrentversi; "WUCurrentVersion"
0x1400184cc  jmp     short loc_14001853A
0x1400184ce  mov     ecx, 1Dh
0x1400184d3  jmp     short loc_1400184AA
0x1400184d5  sub     edx, 7
0x1400184d8  jz      short loc_14001852C
0x1400184da  sub     edx, 1
0x1400184dd  jz      short loc_14001851C
0x1400184df  sub     edx, 1
0x1400184e2  jz      short loc_14001850C
0x1400184e4  sub     edx, 1
0x1400184e7  jz      short loc_140018505
0x1400184e9  cmp     edx, 1
0x1400184ec  jnz     loc_1400185A8
0x1400184f2  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Control\\Fea"...
0x1400184f9  lea     rcx, aFeaturemanagem; "FeatureManagement"
0x140018500  jmp     loc_14001846C
0x140018505  mov     ecx, 23h ; '#'
0x14001850a  jmp     short loc_1400184AA
0x14001850c  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\WindowsSelfHost"
0x140018513  lea     rcx, aWindowsselfhos; "WindowsSelfhost"
0x14001851a  jmp     short loc_14001853A
0x14001851c  lea     rdx, aSoftwarePolici_0; "Software\\Policies\\Microsoft\\WindowsS"...
0x140018523  lea     rcx, aEnterprisemode; "EnterpriseModernAppReleaseManagement"
0x14001852a  jmp     short loc_14001853A
0x14001852c  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\SQMClient"
0x140018533  lea     rcx, aSqmclientlink; "SQMClientLink"
0x14001853a  lea     r8, [rsp+260h+pv]; wchar_t *
0x14001853f  call    ?GetPersistedRegistryLocation@WUSystemInterfaceHelper@@YAJPEB_W0PEAPEA_W@Z; WUSystemInterfaceHelper::GetPersistedRegistryLocation(wchar_t const *,wchar_t const *,wchar_t * *)
0x140018544  test    eax, eax
0x140018546  js      short loc_1400185A3
0x140018548  mov     [rsp+260h+var_238], 100h; unsigned int
0x140018550  mov     [rsp+260h+var_240], 0; unsigned __int64 *
0x140018559  xor     r9d, r9d; wchar_t **
0x14001855c  mov     r8, [rsp+260h+pv]; wchar_t *
0x140018561  mov     edx, 104h; unsigned __int64
0x140018566  lea     rcx, [rsp+260h+Buffer]; pszDest
0x14001856b  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x140018570  test    eax, eax
0x140018572  js      short loc_1400185A3
0x140018574  lea     rdx, [rsp+260h+var_230]
0x140018579  lea     rcx, [rsp+260h+Buffer]
0x14001857e  call    ??$DuplicateString@PEA_WPEA_W@@YAJPEA_WPEAPEA_W@Z; DuplicateString<wchar_t *,wchar_t *>(wchar_t *,wchar_t * *)
0x140018583  test    eax, eax
0x140018585  js      short loc_1400185A3
0x140018587  mov     rdx, [rsp+260h+var_230]
0x14001858c  xor     eax, eax
0x14001858e  lock cmpxchg [r14+rdi*8+10h], rdx
0x140018595  neg     rax
0x140018598  sbb     rcx, rcx
0x14001859b  and     rcx, rdx; lpMem
0x14001859e  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x1400185a3  mov     rcx, [rsp+260h+pv]; pv
0x1400185a8  mov     rbx, [r14+rdi*8+10h]
0x1400185ad  test    rcx, rcx
0x1400185b0  jz      short loc_1400185B8
0x1400185b2  call    cs:__imp_CoTaskMemFree
0x1400185b8  mov     rax, rbx
0x1400185bb  mov     rcx, [rbp+160h+var_10]
0x1400185c2  xor     rcx, rsp; StackCookie
0x1400185c5  call    __security_check_cookie
0x1400185ca  lea     r11, [rsp+260h+var_s0]
0x1400185d2  mov     rbx, [r11+18h]
0x1400185d6  mov     rdi, [r11+20h]
0x1400185da  mov     r14, [r11+28h]
0x1400185de  mov     rsp, r11
0x1400185e1  pop     rbp
0x1400185e2  retn
```
