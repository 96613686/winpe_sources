# CLockScreen::_s_CollectCallerDetails(void *,ushort * *)

- ea: `0x1800bae1c`
- end: `0x1800bb094`
- name: `?_s_CollectCallerDetails@CLockScreen@@KAJPEAXPEAPEAG@Z`
- size: `632`
- prototype: `__int64 __fastcall(void *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800b53b0`
- `0x1800b5460`
- `0x1800ba9f0`

## callees

- `0x18000af94`
- `0x18000d2b8`
- `0x18003aa84`
- `0x180050ba0`
- `0x1800bae1c`
- `0x1800d8130`
- `0x1800d81b4`
- `0x1800d8494`

## import_xrefs

- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800baf12`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800baf12`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800baf8a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800baf8a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1800baf61`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x1800baf61`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bb032`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800bb032`

## string_xrefs

- `0x1800baea0`: `%SystemRoot%\System32\dllhost.exe`
- `0x1800bae95`: `%SystemRoot%\System32\taskhost.exe`
- `0x1800bae89`: `%SystemRoot%\System32\rundll32.exe`
- `0x1800bae71`: `%SystemRoot%\System32\SettingSyncHost.exe`
- `0x1800baeab`: `%SystemRoot%\System32\svchost.exe`

## pseudocode

```c
__int64 __fastcall CLockScreen::_s_CollectCallerDetails(void *a1, unsigned __int16 **a2, unsigned int *a3)
{
  unsigned __int16 **v5; // rdx
  int CallerProcessImageName; // ebx
  unsigned __int16 **v7; // r8
  unsigned int v8; // edi
  __int64 v9; // rcx
  int ProcessAppId; // eax
  void *v11; // rdi
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rcx
  DWORD dwSize; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 v19[4]; // [rsp+40h] [rbp-C0h] BYREF
  const WCHAR *v20; // [rsp+48h] [rbp-B8h]
  _BYTE v21[8]; // [rsp+50h] [rbp-B0h]
  const wchar_t *v22; // [rsp+58h] [rbp-A8h]
  const WCHAR *v23; // [rsp+60h] [rbp-A0h]
  char v24; // [rsp+68h] [rbp-98h]
  const wchar_t *v25; // [rsp+70h] [rbp-90h]
  __int64 v26; // [rsp+78h] [rbp-88h]
  char v27; // [rsp+80h] [rbp-80h]
  const wchar_t *v28; // [rsp+88h] [rbp-78h]
  __int64 v29; // [rsp+90h] [rbp-70h]
  char v30; // [rsp+98h] [rbp-68h]
  const wchar_t *v31; // [rsp+A0h] [rbp-60h]
  __int64 v32; // [rsp+A8h] [rbp-58h]
  char v33; // [rsp+B0h] [rbp-50h]
  const wchar_t *v34; // [rsp+B8h] [rbp-48h]
  __int64 v35; // [rsp+C0h] [rbp-40h]
  char v36; // [rsp+C8h] [rbp-38h]
  WCHAR ExeName[264]; // [rsp+250h] [rbp+150h] BYREF
  WCHAR String2[264]; // [rsp+460h] [rbp+360h] BYREF

  v21[0] = 1;
  *a2 = 0;
  *(_QWORD *)v19 = L"%SystemRoot%\\ImmersiveControlPanel\\SystemSettings.exe";
  v20 = L"IMMERSIVE_CPL";
  v22 = L"%SystemRoot%\\System32\\SettingSyncHost.exe";
  v23 = L"ROAMING";
  v25 = L"%SystemRoot%\\System32\\rundll32.exe";
  v28 = L"%SystemRoot%\\System32\\taskhost.exe";
  v31 = L"%SystemRoot%\\System32\\dllhost.exe";
  v34 = L"%SystemRoot%\\System32\\svchost.exe";
  v24 = 1;
  v26 = 0;
  v27 = 0;
  v29 = 0;
  v30 = 0;
  v32 = 0;
  v33 = 0;
  v35 = 0;
  v36 = 0;
  dwSize = 260;
  if ( !a1 )
  {
    CallerProcessImageName = CallerIdentity::GetCallerProcessImageName(ExeName, &dwSize, a3);
LABEL_6:
    v8 = 0;
    if ( CallerProcessImageName >= 0 )
      goto LABEL_7;
    return (unsigned int)CallerProcessImageName;
  }
  if ( !QueryFullProcessImageNameW(a1, 0, ExeName, &dwSize) )
  {
    CallerProcessImageName = ResultFromKnownLastError();
    if ( CallerProcessImageName < 0 )
      return (unsigned int)CallerProcessImageName;
    goto LABEL_6;
  }
  CallerProcessImageName = 0;
  v8 = 0;
  do
  {
LABEL_7:
    if ( *a2 || v8 >= 6 )
      break;
    CallerProcessImageName = SHExpandEnvironmentStringsW(*(_QWORD *)&v19[12 * v8], String2, 260);
    if ( CallerProcessImageName >= 0 && CompareStringOrdinal(ExeName, -1, String2, -1, 1) == 2 )
    {
      if ( !v21[24 * v8] )
        return (unsigned int)-2147024891;
      CallerProcessImageName = _AllocString<CTCoAllocPolicy>(v9, (__int64)v5, *(const WCHAR **)&v21[24 * v8 - 8], a2);
    }
    ++v8;
  }
  while ( CallerProcessImageName >= 0 );
  if ( CallerProcessImageName >= 0 && !*a2 )
  {
    pv = 0;
    if ( a1 )
      ProcessAppId = CallerIdentity::GetProcessAppId(a1, &pv, v7);
    else
      ProcessAppId = CallerIdentity::GetCallingProcessAppId((CallerIdentity *)&pv, v5);
    if ( ProcessAppId < 0 )
    {
      CallerProcessImageName = StringCchPrintfW(v19, 0x104u, L"%s%s", L"IMAGENAME:", ExeName);
      if ( CallerProcessImageName >= 0 )
        return (unsigned int)_AllocString<CTCoAllocPolicy>(v15, v14, v19, a2);
    }
    else
    {
      v11 = pv;
      CallerProcessImageName = StringCchPrintfW(v19, 0x104u, L"%s%s", L"APPID:", pv);
      if ( CallerProcessImageName >= 0 )
        CallerProcessImageName = _AllocString<CTCoAllocPolicy>(v13, v12, v19, a2);
      CoTaskMemFree(v11);
    }
  }
  return (unsigned int)CallerProcessImageName;
}

```

## disassembly

```asm
0x1800bae1c  mov     [rsp-8+arg_10], rbx
0x1800bae21  mov     [rsp-8+arg_18], rsi
0x1800bae26  push    rbp
0x1800bae27  push    rdi
0x1800bae28  push    r12
0x1800bae2a  push    r14
0x1800bae2c  push    r15
0x1800bae2e  lea     rbp, [rsp-580h]
0x1800bae36  sub     rsp, 680h
0x1800bae3d  mov     rax, cs:__security_cookie
0x1800bae44  xor     rax, rsp
0x1800bae47  mov     [rbp+5A0h+var_30], rax
0x1800bae4e  xor     r12d, r12d
0x1800bae51  mov     [rsp+6A0h+var_650], 1
0x1800bae56  mov     [rdx], r12
0x1800bae59  lea     rax, aSystemrootImme; "%SystemRoot%\\ImmersiveControlPanel\\Sy"...
0x1800bae60  mov     qword ptr [rsp+6A0h+var_660], rax
0x1800bae65  lea     rax, aImmersiveCpl; "IMMERSIVE_CPL"
0x1800bae6c  mov     [rsp+6A0h+var_658], rax
0x1800bae71  lea     rax, aSystemrootSyst_0; "%SystemRoot%\\System32\\SettingSyncHost"...
0x1800bae78  mov     [rsp+6A0h+var_648], rax
0x1800bae7d  lea     rax, aRoaming; "ROAMING"
0x1800bae84  mov     [rsp+6A0h+var_640], rax
0x1800bae89  lea     rax, aSystemrootSyst_4; "%SystemRoot%\\System32\\rundll32.exe"
0x1800bae90  mov     [rsp+6A0h+var_630], rax
0x1800bae95  lea     rax, aSystemrootSyst_3; "%SystemRoot%\\System32\\taskhost.exe"
0x1800bae9c  mov     [rbp+5A0h+var_618], rax
0x1800baea0  lea     rax, aSystemrootSyst_5; "%SystemRoot%\\System32\\dllhost.exe"
0x1800baea7  mov     [rbp+5A0h+var_600], rax
0x1800baeab  lea     rax, aSystemrootSyst; "%SystemRoot%\\System32\\svchost.exe"
0x1800baeb2  mov     [rbp+5A0h+var_5E8], rax
0x1800baeb6  mov     rsi, rdx
0x1800baeb9  mov     [rsp+6A0h+var_638], 1
0x1800baebe  mov     r15, rcx
0x1800baec1  mov     [rsp+6A0h+var_628], r12
0x1800baec6  mov     [rbp+5A0h+var_620], r12b
0x1800baeca  mov     [rbp+5A0h+var_610], r12
0x1800baece  mov     [rbp+5A0h+var_608], r12b
0x1800baed2  mov     [rbp+5A0h+var_5F8], r12
0x1800baed6  mov     [rbp+5A0h+var_5F0], r12b
0x1800baeda  mov     [rbp+5A0h+var_5E0], r12
0x1800baede  mov     [rbp+5A0h+var_5D8], r12b
0x1800baee2  mov     [rsp+6A0h+dwSize], 104h
0x1800baeea  test    rcx, rcx
0x1800baeed  jnz     short loc_1800BAF04
0x1800baeef  lea     rdx, [rsp+6A0h+dwSize]; lpdwSize
0x1800baef4  lea     rcx, [rbp+5A0h+ExeName]; lpExeName
0x1800baefb  call    ?GetCallerProcessImageName@CallerIdentity@@YAJPEAGPEAK@Z; CallerIdentity::GetCallerProcessImageName(ushort *,ulong *)
0x1800baf00  mov     ebx, eax
0x1800baf02  jmp     short loc_1800BAF33
0x1800baf04  lea     r9, [rsp+6A0h+dwSize]; lpdwSize
0x1800baf09  xor     edx, edx; dwFlags
0x1800baf0b  lea     r8, [rbp+5A0h+ExeName]; lpExeName
0x1800baf12  call    cs:__imp_QueryFullProcessImageNameW
0x1800baf18  test    eax, eax
0x1800baf1a  jz      short loc_1800BAF24
0x1800baf1c  mov     ebx, r12d
0x1800baf1f  mov     edi, r12d
0x1800baf22  jmp     short loc_1800BAF3E
0x1800baf24  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800baf29  mov     ebx, eax
0x1800baf2b  test    eax, eax
0x1800baf2d  js      loc_1800BB067
0x1800baf33  mov     edi, r12d
0x1800baf36  test    ebx, ebx
0x1800baf38  js      loc_1800BB067
0x1800baf3e  cmp     [rsi], r12
0x1800baf41  jnz     short loc_1800BAFB1
0x1800baf43  cmp     edi, 6
0x1800baf46  jnb     short loc_1800BAFB1
0x1800baf48  movsxd  rax, edi
0x1800baf4b  lea     rdx, [rbp+5A0h+String2]
0x1800baf52  mov     r8d, 104h
0x1800baf58  lea     r14, [rax+rax*2]
0x1800baf5c  mov     rcx, qword ptr [rsp+r14*8+6A0h+var_660]
0x1800baf61  call    cs:__imp_SHExpandEnvironmentStringsW
0x1800baf67  mov     ebx, eax
0x1800baf69  test    eax, eax
0x1800baf6b  js      short loc_1800BAFAB
0x1800baf6d  or      r9d, 0FFFFFFFFh; cchCount2
0x1800baf71  mov     [rsp+6A0h+bIgnoreCase], 1; bIgnoreCase
0x1800baf79  or      edx, r9d; cchCount1
0x1800baf7c  lea     r8, [rbp+5A0h+String2]; lpString2
0x1800baf83  lea     rcx, [rbp+5A0h+ExeName]; lpString1
0x1800baf8a  call    cs:__imp_CompareStringOrdinal
0x1800baf90  cmp     eax, 2
0x1800baf93  jnz     short loc_1800BAFAB
0x1800baf95  cmp     [rsp+r14*8+6A0h+var_650], r12b
0x1800baf9a  jz      short loc_1800BAFD8
0x1800baf9c  mov     r8, [rsp+r14*8+6A0h+var_658]
0x1800bafa1  mov     r9, rsi
0x1800bafa4  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800bafa9  mov     ebx, eax
0x1800bafab  inc     edi
0x1800bafad  test    ebx, ebx
0x1800bafaf  jns     short loc_1800BAF3E
0x1800bafb1  test    ebx, ebx
0x1800bafb3  js      loc_1800BB067
0x1800bafb9  cmp     [rsi], r12
0x1800bafbc  jnz     loc_1800BB067
0x1800bafc2  mov     [rsp+6A0h+pv], r12
0x1800bafc7  test    r15, r15
0x1800bafca  jnz     short loc_1800BAFE2
0x1800bafcc  lea     rcx, [rsp+6A0h+pv]; this
0x1800bafd1  call    ?GetCallingProcessAppId@CallerIdentity@@YAJPEAPEAG@Z; CallerIdentity::GetCallingProcessAppId(ushort * *)
0x1800bafd6  jmp     short loc_1800BAFEF
0x1800bafd8  mov     ebx, 80070005h
0x1800bafdd  jmp     loc_1800BB067
0x1800bafe2  lea     rdx, [rsp+6A0h+pv]; void *
0x1800bafe7  mov     rcx, r15; ProcessHandle
0x1800bafea  call    ?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppId(void *,ushort * *)
0x1800bafef  lea     r8, aSS_2; "%s%s"
0x1800baff6  mov     edx, 104h; unsigned __int64
0x1800baffb  lea     rcx, [rsp+6A0h+var_660]; unsigned __int16 *
0x1800bb000  test    eax, eax
0x1800bb002  js      short loc_1800BB03A
0x1800bb004  mov     rdi, [rsp+6A0h+pv]
0x1800bb009  lea     r9, aAppid; "APPID:"
0x1800bb010  mov     qword ptr [rsp+6A0h+bIgnoreCase], rdi
0x1800bb015  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800bb01a  mov     ebx, eax
0x1800bb01c  test    eax, eax
0x1800bb01e  js      short loc_1800BB02F
0x1800bb020  mov     r9, rsi
0x1800bb023  lea     r8, [rsp+6A0h+var_660]
0x1800bb028  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800bb02d  mov     ebx, eax
0x1800bb02f  mov     rcx, rdi; pv
0x1800bb032  call    cs:__imp_CoTaskMemFree
0x1800bb038  jmp     short loc_1800BB067
0x1800bb03a  lea     rax, [rbp+5A0h+ExeName]
0x1800bb041  lea     r9, aImagename; "IMAGENAME:"
0x1800bb048  mov     qword ptr [rsp+6A0h+bIgnoreCase], rax
0x1800bb04d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800bb052  mov     ebx, eax
0x1800bb054  test    eax, eax
0x1800bb056  js      short loc_1800BB067
0x1800bb058  mov     r9, rsi
0x1800bb05b  lea     r8, [rsp+6A0h+var_660]
0x1800bb060  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x1800bb065  mov     ebx, eax
0x1800bb067  mov     eax, ebx
0x1800bb069  mov     rcx, [rbp+5A0h+var_30]
0x1800bb070  xor     rcx, rsp; StackCookie
0x1800bb073  call    __security_check_cookie
0x1800bb078  lea     r11, [rsp+6A0h+var_20]
0x1800bb080  mov     rbx, [r11+40h]
0x1800bb084  mov     rsi, [r11+48h]
0x1800bb088  mov     rsp, r11
0x1800bb08b  pop     r15
0x1800bb08d  pop     r14
0x1800bb08f  pop     r12
0x1800bb091  pop     rdi
0x1800bb092  pop     rbp
0x1800bb093  retn
```
