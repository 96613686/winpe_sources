# CCodecFactory::HrReadComponentCategory(_GUID const &,WICComponentType)

- ea: `0x180071c14`
- end: `0x180071f06`
- name: `?HrReadComponentCategory@CCodecFactory@@SAJAEBU_GUID@@W4WICComponentType@@@Z`
- size: `754`
- prototype: `__int64 __fastcall(const struct _GUID *, enum WICComponentType)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003da8c`
- `0x180070958`

## callees

- `0x18002f260`
- `0x180071c14`
- `0x180071f0c`
- `0x180072080`
- `0x1800722f0`
- `0x1800bb784`
- `0x1800e2f90`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180071ddf`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x180071ddf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180071d83`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180071d83`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180071d0d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180071d0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180071e05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180071e35`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180071e05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180071e35`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180071cb4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180071d43`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180071cb4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180071d43`

## string_xrefs

- `0x180071d79`: `CLSID`

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
0x180071c14  mov     [rsp-8+arg_10], rbx
0x180071c19  mov     [rsp-8+arg_18], rsi
0x180071c1e  push    rbp
0x180071c1f  push    rdi
0x180071c20  push    r12
0x180071c22  push    r13
0x180071c24  push    r14
0x180071c26  lea     rbp, [rsp-380h]
0x180071c2e  sub     rsp, 480h
0x180071c35  mov     rax, cs:__security_cookie
0x180071c3c  xor     rax, rsp
0x180071c3f  mov     [rbp+3A0h+var_30], rax
0x180071c46  mov     rbx, rcx
0x180071c49  xor     r13d, r13d
0x180071c4c  lea     rcx, [rsp+4A0h+var_460]; void *
0x180071c51  mov     [rsp+4A0h+var_460], r13b
0x180071c56  mov     r12d, edx
0x180071c59  call    WicIsProcessAppContainer
0x180071c5e  mov     esi, eax
0x180071c60  test    eax, eax
0x180071c62  js      loc_180071E80
0x180071c68  cmp     [rsp+4A0h+var_460], 1
0x180071c6d  jz      loc_180071E13
0x180071c73  mov     r8d, 200h; unsigned int
0x180071c79  lea     rdx, [rsp+4A0h+SubKey]; unsigned __int16 *
0x180071c7e  mov     rcx, rbx; struct _GUID *
0x180071c81  call    ?BuildImagingCategoryKey@RegKey@@SAJAEBU_GUID@@PEAGI@Z; RegKey::BuildImagingCategoryKey(_GUID const &,ushort *,uint)
0x180071c86  mov     esi, eax
0x180071c88  test    eax, eax
0x180071c8a  js      loc_180071E80
0x180071c90  lea     rax, [rsp+4A0h+hKey]
0x180071c95  mov     [rsp+4A0h+hKey], r13
0x180071c9a  mov     r9d, 20019h; samDesired
0x180071ca0  mov     [rsp+4A0h+phkResult], rax; phkResult
0x180071ca5  xor     r8d, r8d; ulOptions
0x180071ca8  lea     rdx, [rsp+4A0h+SubKey]; lpSubKey
0x180071cad  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180071cb4  call    cs:__imp_RegOpenKeyExW
0x180071cba  mov     esi, eax
0x180071cbc  test    eax, eax
0x180071cbe  jnz     loc_180071E9A
0x180071cc4  mov     rbx, [rsp+4A0h+hKey]
0x180071cc9  mov     esi, r13d
0x180071ccc  test    esi, esi
0x180071cce  js      loc_180071E7B
0x180071cd4  mov     r14d, r13d
0x180071cd7  lea     rax, [rsp+4A0h+ftLastWriteTime]
0x180071cdc  mov     dword ptr [rsp+4A0h+hKey], 200h
0x180071ce4  mov     [rsp+4A0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180071ce9  lea     r9, [rsp+4A0h+hKey]; lpcchName
0x180071cee  mov     [rsp+4A0h+lpcchClass], r13; lpcchClass
0x180071cf3  lea     r8, [rsp+4A0h+SubKey]; lpName
0x180071cf8  mov     [rsp+4A0h+lpClass], r13; lpClass
0x180071cfd  mov     edx, r14d; dwIndex
0x180071d00  mov     rcx, rbx; hKey
0x180071d03  mov     [rsp+4A0h+phkResult], r13; lpReserved
0x180071d08  mov     qword ptr [rsp+4A0h+ftLastWriteTime.dwLowDateTime], r13
0x180071d0d  call    cs:__imp_RegEnumKeyExW
0x180071d13  test    eax, eax
0x180071d15  jnz     loc_180071E22
0x180071d1b  lea     rax, [rsp+4A0h+ftLastWriteTime]
0x180071d20  mov     [rsp+4A0h+cbData], 400h
0x180071d28  mov     r9d, 20019h; samDesired
0x180071d2e  mov     [rsp+4A0h+phkResult], rax; phkResult
0x180071d33  xor     r8d, r8d; ulOptions
0x180071d36  mov     qword ptr [rsp+4A0h+ftLastWriteTime.dwLowDateTime], r13
0x180071d3b  lea     rdx, [rsp+4A0h+SubKey]; lpSubKey
0x180071d40  mov     rcx, rbx; hKey
0x180071d43  call    cs:__imp_RegOpenKeyExW
0x180071d49  mov     ecx, eax
0x180071d4b  test    eax, eax
0x180071d4d  jnz     loc_180071E92
0x180071d53  mov     rdi, qword ptr [rsp+4A0h+ftLastWriteTime.dwLowDateTime]
0x180071d58  lea     rax, [rsp+4A0h+cbData]
0x180071d5d  mov     [rsp+4A0h+lpClass], rax; lpcbData
0x180071d62  lea     r9, [rsp+4A0h+Type]; lpType
0x180071d67  lea     rax, [rsp+4A0h+SubKey]
0x180071d6c  mov     [rsp+4A0h+Type], r13d
0x180071d71  xor     r8d, r8d; lpReserved
0x180071d74  mov     [rsp+4A0h+phkResult], rax; lpData
0x180071d79  lea     rdx, ValueName; "CLSID"
0x180071d80  mov     rcx, rdi; hKey
0x180071d83  call    cs:__imp_RegQueryValueExW
0x180071d89  mov     ecx, eax
0x180071d8b  mov     eax, [rsp+4A0h+Type]
0x180071d8f  sub     eax, 1
0x180071d92  jz      short loc_180071D99
0x180071d94  sub     eax, 1
0x180071d97  jnz     short loc_180071DBB
0x180071d99  mov     edx, [rsp+4A0h+cbData]
0x180071d9d  test    dl, 1
0x180071da0  jnz     short loc_180071DC4
0x180071da2  mov     eax, edx
0x180071da4  and     eax, 0FFFFFFFEh
0x180071da7  cmp     eax, 2
0x180071daa  jb      short loc_180071DC4
0x180071dac  mov     eax, edx
0x180071dae  shr     rax, 1
0x180071db1  cmp     word ptr [rsp+rax*2+4A0h+iid.Data4+6], r13w
0x180071db7  jz      short loc_180071DC9
0x180071db9  jmp     short loc_180071DC4
0x180071dbb  cmp     eax, 5
0x180071dbe  jz      loc_180071ECF
0x180071dc4  mov     ecx, 0Dh
0x180071dc9  xorps   xmm0, xmm0
0x180071dcc  movups  xmmword ptr [rsp+4A0h+iid.Data1], xmm0
0x180071dd1  test    ecx, ecx
0x180071dd3  jnz     short loc_180071DFD
0x180071dd5  lea     rdx, [rsp+4A0h+iid]; lpiid
0x180071dda  lea     rcx, [rsp+4A0h+SubKey]; lpsz
0x180071ddf  call    cs:__imp_IIDFromString
0x180071de5  test    eax, eax
0x180071de7  js      short loc_180071DFD
0x180071de9  cmp     [rsp+4A0h+var_460], r13b
0x180071dee  jnz     short loc_180071E68
0x180071df0  lea     rdx, [rsp+4A0h+iid]; struct _GUID *
0x180071df5  mov     ecx, r12d; enum WICComponentType
0x180071df8  call    ?HrCreateComponentInfo@CCodecFactory@@SAJW4WICComponentType@@AEBU_GUID@@@Z; CCodecFactory::HrCreateComponentInfo(WICComponentType,_GUID const &)
0x180071dfd  test    rdi, rdi
0x180071e00  jz      short loc_180071E0B
0x180071e02  mov     rcx, rdi; hKey
0x180071e05  call    cs:__imp_RegCloseKey
0x180071e0b  inc     r14d
0x180071e0e  jmp     loc_180071CD7
0x180071e13  cmp     r12d, 1
0x180071e17  jz      loc_180071C73
0x180071e1d  mov     esi, r13d
0x180071e20  jmp     short loc_180071E3B
0x180071e22  cmp     eax, 103h
0x180071e27  jnz     loc_180071EB1
0x180071e2d  test    rbx, rbx
0x180071e30  jz      short loc_180071E3B
0x180071e32  mov     rcx, rbx; hKey
0x180071e35  call    cs:__imp_RegCloseKey
0x180071e3b  mov     eax, esi
0x180071e3d  mov     rcx, [rbp+3A0h+var_30]
0x180071e44  xor     rcx, rsp; StackCookie
0x180071e47  call    __security_check_cookie
0x180071e4c  lea     r11, [rsp+4A0h+var_20]
0x180071e54  mov     rbx, [r11+40h]
0x180071e58  mov     rsi, [r11+48h]
0x180071e5c  mov     rsp, r11
0x180071e5f  pop     r14
0x180071e61  pop     r13
0x180071e63  pop     r12
0x180071e65  pop     rdi
0x180071e66  pop     rbp
0x180071e67  retn
0x180071e68  lea     rcx, [rsp+4A0h+iid]; struct _GUID *
0x180071e6d  call    ?IsNonBuiltInMSComponent@CCodecFactory@@SA_NAEBU_GUID@@@Z; CCodecFactory::IsNonBuiltInMSComponent(_GUID const &)
0x180071e72  test    al, al
0x180071e74  jz      short loc_180071DFD
0x180071e76  jmp     loc_180071DF0
0x180071e7b  mov     esi, r13d
0x180071e7e  jmp     short loc_180071E2D
0x180071e80  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180071e87  jz      short loc_180071E3B
0x180071e89  mov     ecx, eax; int
0x180071e8b  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180071e90  jmp     short loc_180071E3B
0x180071e92  mov     rdi, r13
0x180071e95  jmp     loc_180071DC9
0x180071e9a  mov     rbx, r13
0x180071e9d  jle     loc_180071CCC
0x180071ea3  movzx   esi, ax
0x180071ea6  or      esi, 80070000h
0x180071eac  jmp     loc_180071CCC
0x180071eb1  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x180071eb8  mov     esi, 88982F8Ah
0x180071ebd  jz      loc_180071E2D
0x180071ec3  mov     ecx, esi; int
0x180071ec5  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180071eca  jmp     loc_180071E2D
0x180071ecf  mov     edx, [rsp+4A0h+cbData]
0x180071ed3  test    dl, 1
0x180071ed6  jnz     loc_180071DC4
0x180071edc  mov     eax, edx
0x180071ede  and     eax, 0FFFFFFFEh
0x180071ee1  cmp     eax, 4
0x180071ee4  jb      loc_180071DC4
0x180071eea  mov     eax, edx
0x180071eec  shr     rax, 1
0x180071eef  cmp     word ptr [rsp+rax*2+4A0h+iid.Data4+6], r13w
0x180071ef5  jnz     loc_180071DC4
0x180071efb  cmp     word ptr [rsp+rax*2+4A0h+iid.Data4+4], r13w
0x180071f01  jmp     loc_180071DB7
```
