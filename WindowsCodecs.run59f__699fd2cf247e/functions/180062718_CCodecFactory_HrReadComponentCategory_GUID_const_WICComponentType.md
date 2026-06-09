# CCodecFactory::HrReadComponentCategory(_GUID const &,WICComponentType)

- ea: `0x180062718`
- end: `0x180062a3d`
- name: `?HrReadComponentCategory@CCodecFactory@@SAJAEBU_GUID@@W4WICComponentType@@@Z`
- size: `805`
- prototype: `__int64 __fastcall(const struct _GUID *, enum WICComponentType)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800279c8`
- `0x180062620`

## callees

- `0x180061a2c`
- `0x1800624c0`
- `0x180062718`
- `0x180062a44`
- `0x1800b39f0`
- `0x1800bd9d4`
- `0x1800e5e60`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800628fb`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x1800628fb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180062899`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180062899`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180062817`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180062817`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006292b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062961`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006292b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062961`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800627b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180062853`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800627b8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180062853`

## string_xrefs

- `0x18006288f`: `CLSID`

## pseudocode

```c
__int64 __fastcall CCodecFactory::HrReadComponentCategory(const struct _GUID *a1, enum WICComponentType a2)
{
  int IsProcessAppContainer; // eax
  unsigned int v5; // esi
  LSTATUS v6; // eax
  HKEY v7; // rbx
  DWORD i; // r14d
  LSTATUS v9; // eax
  LSTATUS v10; // ecx
  HKEY v11; // rdi
  bool v12; // zf
  unsigned __int64 v14; // rax
  _BYTE v15[4]; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+58h] [rbp-A8h] BYREF
  GUID iid; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[512]; // [rsp+70h] [rbp-90h] BYREF

  v15[0] = 0;
  IsProcessAppContainer = WicIsProcessAppContainer(v15);
  v5 = IsProcessAppContainer;
  if ( IsProcessAppContainer < 0 )
    goto LABEL_35;
  if ( v15[0] == 1 && a2 != WICDecoder )
    return 0;
  IsProcessAppContainer = RegKey::BuildImagingCategoryKey(a1, SubKey, 0x200u);
  v5 = IsProcessAppContainer;
  if ( IsProcessAppContainer < 0 )
  {
LABEL_35:
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(IsProcessAppContainer);
    return v5;
  }
  hKey = 0;
  v6 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x20019u, &hKey);
  v5 = v6;
  if ( v6 )
  {
    v7 = 0;
    if ( v6 > 0 )
      v5 = (unsigned __int16)v6 | 0x80070000;
  }
  else
  {
    v7 = hKey;
    v5 = 0;
  }
  if ( (v5 & 0x80000000) != 0 )
  {
    v5 = 0;
    goto LABEL_29;
  }
  for ( i = 0; ; ++i )
  {
    LODWORD(hKey) = 512;
    ftLastWriteTime = 0;
    v9 = RegEnumKeyExW(v7, i, SubKey, (LPDWORD)&hKey, 0, 0, 0, &ftLastWriteTime);
    if ( v9 )
      break;
    cbData = 1024;
    ftLastWriteTime = 0;
    v10 = RegOpenKeyExW(v7, SubKey, 0, 0x20019u, (PHKEY)&ftLastWriteTime);
    if ( v10 )
    {
      v11 = 0;
      goto LABEL_19;
    }
    v11 = (HKEY)ftLastWriteTime;
    Type = 0;
    v10 = RegQueryValueExW(*(HKEY *)&ftLastWriteTime, L"CLSID", 0, &Type, (LPBYTE)SubKey, &cbData);
    if ( Type == 1 || Type == 2 )
    {
      if ( (cbData & 1) != 0 || (cbData & 0xFFFFFFFE) < 2 )
        goto LABEL_18;
      v12 = *(_WORD *)&iid.Data4[2 * ((unsigned __int64)cbData >> 1) + 6] == 0;
    }
    else
    {
      if ( Type != 7
        || (cbData & 1) != 0
        || (cbData & 0xFFFFFFFE) < 4
        || (v14 = (unsigned __int64)cbData >> 1, *(_WORD *)&iid.Data4[2 * v14 + 6]) )
      {
LABEL_18:
        v10 = 13;
        goto LABEL_19;
      }
      v12 = *(_WORD *)&iid.Data4[2 * v14 + 4] == 0;
    }
    if ( !v12 )
      goto LABEL_18;
LABEL_19:
    iid = 0;
    if ( !v10 && IIDFromString(SubKey, &iid) >= 0 && (!v15[0] || CCodecFactory::IsNonBuiltInMSComponent(&iid)) )
      CCodecFactory::HrCreateComponentInfo(a2, &iid);
    if ( v11 )
      RegCloseKey(v11);
  }
  if ( v9 != 259 )
  {
    v5 = -2003292278;
    if ( (_DWORD)g_doStackCaptures )
      DoStackCapture(-2003292278);
  }
LABEL_29:
  if ( v7 )
    RegCloseKey(v7);
  return v5;
}

```

## disassembly

```asm
0x180062718  mov     [rsp-8+arg_10], rbx
0x18006271d  mov     [rsp-8+arg_18], rsi
0x180062722  push    rbp
0x180062723  push    rdi
0x180062724  push    r12
0x180062726  push    r13
0x180062728  push    r14
0x18006272a  lea     rbp, [rsp-380h]
0x180062732  sub     rsp, 480h
0x180062739  mov     rax, cs:__security_cookie
0x180062740  xor     rax, rsp
0x180062743  mov     [rbp+3A0h+var_30], rax
0x18006274a  mov     rbx, rcx
0x18006274d  xor     r13d, r13d
0x180062750  lea     rcx, [rsp+4A0h+var_460]; void *
0x180062755  mov     [rsp+4A0h+var_460], r13b
0x18006275a  mov     r12d, edx
0x18006275d  call    WicIsProcessAppContainer
0x180062762  mov     esi, eax
0x180062764  test    eax, eax
0x180062766  js      loc_1800629B7
0x18006276c  cmp     [rsp+4A0h+var_460], 1
0x180062771  jz      loc_18006293F
0x180062777  mov     r8d, 200h; unsigned int
0x18006277d  lea     rdx, [rsp+4A0h+SubKey]; unsigned __int16 *
0x180062782  mov     rcx, rbx; struct _GUID *
0x180062785  call    ?BuildImagingCategoryKey@RegKey@@SAJAEBU_GUID@@PEAGI@Z; RegKey::BuildImagingCategoryKey(_GUID const &,ushort *,uint)
0x18006278a  mov     esi, eax
0x18006278c  test    eax, eax
0x18006278e  js      loc_1800629B7
0x180062794  lea     rax, [rsp+4A0h+hKey]
0x180062799  mov     [rsp+4A0h+hKey], r13
0x18006279e  mov     r9d, 20019h; samDesired
0x1800627a4  mov     [rsp+4A0h+phkResult], rax; phkResult
0x1800627a9  xor     r8d, r8d; ulOptions
0x1800627ac  lea     rdx, [rsp+4A0h+SubKey]; lpSubKey
0x1800627b1  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800627b8  call    cs:__imp_RegOpenKeyExW
0x1800627bf  nop     dword ptr [rax+rax+00h]
0x1800627c4  mov     esi, eax
0x1800627c6  test    eax, eax
0x1800627c8  jnz     loc_1800629D1
0x1800627ce  mov     rbx, [rsp+4A0h+hKey]
0x1800627d3  mov     esi, r13d
0x1800627d6  test    esi, esi
0x1800627d8  js      loc_1800629B2
0x1800627de  mov     r14d, r13d
0x1800627e1  lea     rax, [rsp+4A0h+ftLastWriteTime]
0x1800627e6  mov     dword ptr [rsp+4A0h+hKey], 200h
0x1800627ee  mov     [rsp+4A0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800627f3  lea     r9, [rsp+4A0h+hKey]; lpcchName
0x1800627f8  mov     [rsp+4A0h+lpcchClass], r13; lpcchClass
0x1800627fd  lea     r8, [rsp+4A0h+SubKey]; lpName
0x180062802  mov     [rsp+4A0h+lpClass], r13; lpClass
0x180062807  mov     edx, r14d; dwIndex
0x18006280a  mov     rcx, rbx; hKey
0x18006280d  mov     [rsp+4A0h+phkResult], r13; lpReserved
0x180062812  mov     qword ptr [rsp+4A0h+ftLastWriteTime.dwLowDateTime], r13
0x180062817  call    cs:__imp_RegEnumKeyExW
0x18006281e  nop     dword ptr [rax+rax+00h]
0x180062823  test    eax, eax
0x180062825  jnz     loc_18006294E
0x18006282b  lea     rax, [rsp+4A0h+ftLastWriteTime]
0x180062830  mov     [rsp+4A0h+cbData], 400h
0x180062838  mov     r9d, 20019h; samDesired
0x18006283e  mov     [rsp+4A0h+phkResult], rax; phkResult
0x180062843  xor     r8d, r8d; ulOptions
0x180062846  mov     qword ptr [rsp+4A0h+ftLastWriteTime.dwLowDateTime], r13
0x18006284b  lea     rdx, [rsp+4A0h+SubKey]; lpSubKey
0x180062850  mov     rcx, rbx; hKey
0x180062853  call    cs:__imp_RegOpenKeyExW
0x18006285a  nop     dword ptr [rax+rax+00h]
0x18006285f  mov     ecx, eax
0x180062861  test    eax, eax
0x180062863  jnz     loc_1800629C9
0x180062869  mov     rdi, qword ptr [rsp+4A0h+ftLastWriteTime.dwLowDateTime]
0x18006286e  lea     rax, [rsp+4A0h+cbData]
0x180062873  mov     [rsp+4A0h+lpClass], rax; lpcbData
0x180062878  lea     r9, [rsp+4A0h+Type]; lpType
0x18006287d  lea     rax, [rsp+4A0h+SubKey]
0x180062882  mov     [rsp+4A0h+Type], r13d
0x180062887  xor     r8d, r8d; lpReserved
0x18006288a  mov     [rsp+4A0h+phkResult], rax; lpData
0x18006288f  lea     rdx, ValueName; "CLSID"
0x180062896  mov     rcx, rdi; hKey
0x180062899  call    cs:__imp_RegQueryValueExW
0x1800628a0  nop     dword ptr [rax+rax+00h]
0x1800628a5  mov     ecx, eax
0x1800628a7  mov     eax, [rsp+4A0h+Type]
0x1800628ab  sub     eax, 1
0x1800628ae  jz      short loc_1800628B5
0x1800628b0  sub     eax, 1
0x1800628b3  jnz     short loc_1800628D7
0x1800628b5  mov     edx, [rsp+4A0h+cbData]
0x1800628b9  test    dl, 1
0x1800628bc  jnz     short loc_1800628E0
0x1800628be  mov     eax, edx
0x1800628c0  and     eax, 0FFFFFFFEh
0x1800628c3  cmp     eax, 2
0x1800628c6  jb      short loc_1800628E0
0x1800628c8  mov     eax, edx
0x1800628ca  shr     rax, 1
0x1800628cd  cmp     word ptr [rsp+rax*2+4A0h+iid.Data4+6], r13w
0x1800628d3  jz      short loc_1800628E5
0x1800628d5  jmp     short loc_1800628E0
0x1800628d7  cmp     eax, 5
0x1800628da  jz      loc_180062A06
0x1800628e0  mov     ecx, 0Dh
0x1800628e5  xorps   xmm0, xmm0
0x1800628e8  movups  xmmword ptr [rsp+4A0h+iid.Data1], xmm0
0x1800628ed  test    ecx, ecx
0x1800628ef  jnz     short loc_180062923
0x1800628f1  lea     rdx, [rsp+4A0h+iid]; lpiid
0x1800628f6  lea     rcx, [rsp+4A0h+SubKey]; lpsz
0x1800628fb  call    cs:__imp_IIDFromString
0x180062902  nop     dword ptr [rax+rax+00h]
0x180062907  test    eax, eax
0x180062909  js      short loc_180062923
0x18006290b  cmp     [rsp+4A0h+var_460], r13b
0x180062910  jnz     loc_18006299B
0x180062916  lea     rdx, [rsp+4A0h+iid]; struct _GUID *
0x18006291b  mov     ecx, r12d; enum WICComponentType
0x18006291e  call    ?HrCreateComponentInfo@CCodecFactory@@SAJW4WICComponentType@@AEBU_GUID@@@Z; CCodecFactory::HrCreateComponentInfo(WICComponentType,_GUID const &)
0x180062923  test    rdi, rdi
0x180062926  jz      short loc_180062937
0x180062928  mov     rcx, rdi; hKey
0x18006292b  call    cs:__imp_RegCloseKey
0x180062932  nop     dword ptr [rax+rax+00h]
0x180062937  inc     r14d
0x18006293a  jmp     loc_1800627E1
0x18006293f  cmp     r12d, 1
0x180062943  jz      loc_180062777
0x180062949  mov     esi, r13d
0x18006294c  jmp     short loc_18006296D
0x18006294e  cmp     eax, 103h
0x180062953  jnz     loc_1800629E8
0x180062959  test    rbx, rbx
0x18006295c  jz      short loc_18006296D
0x18006295e  mov     rcx, rbx; hKey
0x180062961  call    cs:__imp_RegCloseKey
0x180062968  nop     dword ptr [rax+rax+00h]
0x18006296d  mov     eax, esi
0x18006296f  mov     rcx, [rbp+3A0h+var_30]
0x180062976  xor     rcx, rsp; StackCookie
0x180062979  call    __security_check_cookie
0x18006297e  lea     r11, [rsp+4A0h+var_20]
0x180062986  mov     rbx, [r11+40h]
0x18006298a  mov     rsi, [r11+48h]
0x18006298e  mov     rsp, r11
0x180062991  pop     r14
0x180062993  pop     r13
0x180062995  pop     r12
0x180062997  pop     rdi
0x180062998  pop     rbp
0x180062999  retn
0x18006299b  lea     rcx, [rsp+4A0h+iid]; struct _GUID *
0x1800629a0  call    ?IsNonBuiltInMSComponent@CCodecFactory@@SA_NAEBU_GUID@@@Z; CCodecFactory::IsNonBuiltInMSComponent(_GUID const &)
0x1800629a5  test    al, al
0x1800629a7  jz      loc_180062923
0x1800629ad  jmp     loc_180062916
0x1800629b2  mov     esi, r13d
0x1800629b5  jmp     short loc_180062959
0x1800629b7  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800629be  jz      short loc_18006296D
0x1800629c0  mov     ecx, eax; int
0x1800629c2  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800629c7  jmp     short loc_18006296D
0x1800629c9  mov     rdi, r13
0x1800629cc  jmp     loc_1800628E5
0x1800629d1  mov     rbx, r13
0x1800629d4  jle     loc_1800627D6
0x1800629da  movzx   esi, ax
0x1800629dd  or      esi, 80070000h
0x1800629e3  jmp     loc_1800627D6
0x1800629e8  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800629ef  mov     esi, 88982F8Ah
0x1800629f4  jz      loc_180062959
0x1800629fa  mov     ecx, esi; int
0x1800629fc  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180062a01  jmp     loc_180062959
0x180062a06  mov     edx, [rsp+4A0h+cbData]
0x180062a0a  test    dl, 1
0x180062a0d  jnz     loc_1800628E0
0x180062a13  mov     eax, edx
0x180062a15  and     eax, 0FFFFFFFEh
0x180062a18  cmp     eax, 4
0x180062a1b  jb      loc_1800628E0
0x180062a21  mov     eax, edx
0x180062a23  shr     rax, 1
0x180062a26  cmp     word ptr [rsp+rax*2+4A0h+iid.Data4+6], r13w
0x180062a2c  jnz     loc_1800628E0
0x180062a32  cmp     word ptr [rsp+rax*2+4A0h+iid.Data4+4], r13w
0x180062a38  jmp     loc_1800628D3
```
