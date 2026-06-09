# SetDefaultRecognizer(_GUID *,ulong)

- ea: `0x18007f254`
- end: `0x18007f403`
- name: `?SetDefaultRecognizer@@YAJPEAU_GUID@@K@Z`
- size: `431`
- prototype: `__int64 __fastcall(IID *rclsid, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006a380`

## callees

- `0x18007ec4c`
- `0x18007f254`
- `0x18007f490`
- `0x180104ece`
- `0x180104f30`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18007f308`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18007f308`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007f2e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18007f2e8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007f383`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18007f383`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f315`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f3c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f3d1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f315`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f3c1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18007f3d1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007f3b2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18007f3b2`
- `USER32!GetKeyboardLayout` at `0x18007f289`
- `USER32!GetKeyboardLayout` at `0x18007f289`

## pseudocode

```c
__int64 __fastcall SetDefaultRecognizer(IID *rclsid, unsigned __int16 a2)
{
  unsigned __int16 KeyboardLayout; // bx
  LSTATUS v5; // eax
  LSTATUS v6; // ebx
  __int64 result; // rax
  LSTATUS v8; // eax
  HKEY v9; // rcx
  LSTATUS v10; // eax
  HKEY v11; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  struct tagRECO_ATTRS v14; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ValueName[8]; // [rsp+1C0h] [rbp+C0h] BYREF

  KeyboardLayout = (unsigned __int16)GetKeyboardLayout(0);
  memset_0(&v14, 0, sizeof(v14));
  if ( !a2 )
    a2 = KeyboardLayout;
  StringFromLangId(ValueName, a2);
  if ( rclsid )
  {
    result = GetCachedRecoAttributes(rclsid, &v14);
    if ( (int)result < 0 )
      return result;
    v11 = 0;
    dwDisposition = 0;
    v8 = RegCreateKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\TPG\\Default Recognizers",
           0,
           0,
           0,
           0xF003Fu,
           0,
           &v11,
           &dwDisposition);
    v9 = v11;
    if ( v8 )
    {
      if ( !v11 )
        return 2147746358LL;
    }
    else
    {
      if ( !v11 )
        return 2147746358LL;
      v10 = RegSetValueExW(v11, ValueName, 0, 3u, (const BYTE *)rclsid, 0x10u);
      v9 = v11;
      if ( !v10 )
      {
        RegCloseKey(v11);
        return 0;
      }
    }
    RegCloseKey(v9);
    return 2147746358LL;
  }
  hKey = 0;
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\TPG\\Default Recognizers", 0, 0xF003Fu, &hKey);
  if ( v5 )
  {
    if ( v5 != 2 )
      return 2147746358LL;
    return 0;
  }
  v6 = RegDeleteValueW(hKey, ValueName);
  RegCloseKey(hKey);
  if ( !v6 )
    return 0;
  return 2147746358LL;
}

```

## disassembly

```asm
0x18007f254  mov     [rsp-8+arg_10], rbx
0x18007f259  mov     [rsp-8+arg_18], rsi
0x18007f25e  push    rbp
0x18007f25f  push    rdi
0x18007f260  push    r14
0x18007f262  lea     rbp, [rsp-0E0h]
0x18007f26a  sub     rsp, 1E0h
0x18007f271  mov     rax, cs:__security_cookie
0x18007f278  xor     rax, rsp
0x18007f27b  mov     [rbp+0F0h+var_20], rax
0x18007f282  mov     rsi, rcx
0x18007f285  mov     edi, edx
0x18007f287  xor     ecx, ecx; idThread
0x18007f289  call    cs:__imp_GetKeyboardLayout
0x18007f28f  xor     edx, edx; Val
0x18007f291  lea     rcx, [rsp+1F0h+var_180]; void *
0x18007f296  mov     r8d, 144h; Size
0x18007f29c  mov     rbx, rax
0x18007f29f  call    memset_0
0x18007f2a4  xor     r14d, r14d
0x18007f2a7  lea     rcx, [rbp+0F0h+ValueName]; unsigned __int16 *
0x18007f2ae  test    di, di
0x18007f2b1  cmovz   di, bx
0x18007f2b5  movzx   edx, di; unsigned __int16
0x18007f2b8  call    ?StringFromLangId@@YAXQEAGG@Z; StringFromLangId(ushort * const,ushort)
0x18007f2bd  test    rsi, rsi
0x18007f2c0  jnz     short loc_18007F32A
0x18007f2c2  lea     rax, [rsp+1F0h+hKey]
0x18007f2c7  mov     [rsp+1F0h+hKey], r14
0x18007f2cc  mov     r9d, 0F003Fh; samDesired
0x18007f2d2  mov     [rsp+1F0h+phkResult], rax; phkResult
0x18007f2d7  xor     r8d, r8d; ulOptions
0x18007f2da  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\TPG\\Default Recog"...
0x18007f2e1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007f2e8  call    cs:__imp_RegOpenKeyExW
0x18007f2ee  test    eax, eax
0x18007f2f0  jz      short loc_18007F2FC
0x18007f2f2  cmp     eax, 2
0x18007f2f5  jz      short loc_18007F323
0x18007f2f7  jmp     loc_18007F3D7
0x18007f2fc  mov     rcx, [rsp+1F0h+hKey]; hKey
0x18007f301  lea     rdx, [rbp+0F0h+ValueName]; lpValueName
0x18007f308  call    cs:__imp_RegDeleteValueW
0x18007f30e  mov     rcx, [rsp+1F0h+hKey]; hKey
0x18007f313  mov     ebx, eax
0x18007f315  call    cs:__imp_RegCloseKey
0x18007f31b  test    ebx, ebx
0x18007f31d  jnz     loc_18007F3D7
0x18007f323  xor     eax, eax
0x18007f325  jmp     loc_18007F3DC
0x18007f32a  lea     rdx, [rsp+1F0h+var_180]; struct tagRECO_ATTRS *
0x18007f32f  mov     rcx, rsi; rclsid
0x18007f332  call    ?GetCachedRecoAttributes@@YAJPEAU_GUID@@PEAUtagRECO_ATTRS@@@Z; GetCachedRecoAttributes(_GUID *,tagRECO_ATTRS *)
0x18007f337  test    eax, eax
0x18007f339  js      loc_18007F3DC
0x18007f33f  lea     rax, [rsp+1F0h+dwDisposition]
0x18007f344  mov     [rsp+1F0h+var_1A0], r14
0x18007f349  mov     [rsp+1F0h+lpdwDisposition], rax; lpdwDisposition
0x18007f34e  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\TPG\\Default Recog"...
0x18007f355  lea     rax, [rsp+1F0h+var_1A0]
0x18007f35a  mov     [rsp+1F0h+dwDisposition], r14d
0x18007f35f  mov     [rsp+1F0h+var_1B8], rax; phkResult
0x18007f364  xor     r9d, r9d; lpClass
0x18007f367  mov     [rsp+1F0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18007f36c  xor     r8d, r8d; Reserved
0x18007f36f  mov     [rsp+1F0h+samDesired], 0F003Fh; samDesired
0x18007f377  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007f37e  mov     dword ptr [rsp+1F0h+phkResult], r14d; dwOptions
0x18007f383  call    cs:__imp_RegCreateKeyExW
0x18007f389  mov     rcx, [rsp+1F0h+var_1A0]; hKey
0x18007f38e  test    eax, eax
0x18007f390  jnz     short loc_18007F3CC
0x18007f392  test    rcx, rcx
0x18007f395  jz      short loc_18007F3D7
0x18007f397  mov     [rsp+1F0h+samDesired], 10h; cbData
0x18007f39f  lea     r9d, [rax+3]; dwType
0x18007f3a3  xor     r8d, r8d; Reserved
0x18007f3a6  mov     [rsp+1F0h+phkResult], rsi; lpData
0x18007f3ab  lea     rdx, [rbp+0F0h+ValueName]; lpValueName
0x18007f3b2  call    cs:__imp_RegSetValueExW
0x18007f3b8  mov     rcx, [rsp+1F0h+var_1A0]; hKey
0x18007f3bd  test    eax, eax
0x18007f3bf  jnz     short loc_18007F3D1
0x18007f3c1  call    cs:__imp_RegCloseKey
0x18007f3c7  jmp     loc_18007F323
0x18007f3cc  test    rcx, rcx
0x18007f3cf  jz      short loc_18007F3D7
0x18007f3d1  call    cs:__imp_RegCloseKey
0x18007f3d7  mov     eax, 80040236h
0x18007f3dc  mov     rcx, [rbp+0F0h+var_20]
0x18007f3e3  xor     rcx, rsp; StackCookie
0x18007f3e6  call    __security_check_cookie
0x18007f3eb  lea     r11, [rsp+1F0h+var_10]
0x18007f3f3  mov     rbx, [r11+30h]
0x18007f3f7  mov     rsi, [r11+38h]
0x18007f3fb  mov     rsp, r11
0x18007f3fe  pop     r14
0x18007f400  pop     rdi
0x18007f401  pop     rbp
0x18007f402  retn
```
