# _WriteImplementingClassesOfCategory(_GUID const &,_DSA *)

- ea: `0x18002a824`
- end: `0x18002a960`
- name: `?_WriteImplementingClassesOfCategory@@YAJAEBU_GUID@@PEAU_DSA@@@Z`
- size: `316`
- prototype: `__int64 __fastcall(const struct _GUID *, struct _DSA *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18002a31c`

## callees

- `0x180002ce0`
- `0x180002d04`
- `0x18002a41c`
- `0x18002a628`
- `0x18002a824`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002a8b6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002a8b6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a934`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a934`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a91f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a91f`

## pseudocode

```c
__int64 __fastcall _WriteImplementingClassesOfCategory(const struct _GUID *a1, struct _DSA *a2)
{
  int ComCatCacheKey; // edi
  LSTATUS v4; // eax
  BYTE *v5; // rbx
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  BYTE *lpData; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF

  ComCatCacheKey = _MakeComCatCacheKey(a1, SubKey);
  if ( ComCatCacheKey >= 0 )
  {
    hKey = 0;
    dwDisposition = 0;
    v4 = RegCreateKeyExW(HKEY_CURRENT_USER, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, &dwDisposition);
    ComCatCacheKey = v4;
    if ( v4 > 0 )
      ComCatCacheKey = (unsigned __int16)v4 | 0x80070000;
    if ( ComCatCacheKey >= 0 )
    {
      lpData = 0;
      cbData = 0;
      ComCatCacheKey = _ComCatCacheFromDSA((unsigned int *)a2, &lpData, &cbData);
      if ( ComCatCacheKey >= 0 )
      {
        v5 = lpData;
        ComCatCacheKey = RegSetValueExW(hKey, L"Implementing", 0, 3u, lpData, cbData);
        operator delete(v5);
      }
      RegCloseKey(hKey);
    }
  }
  return (unsigned int)ComCatCacheKey;
}

```

## disassembly

```asm
0x18002a824  mov     [rsp-8+arg_10], rbx
0x18002a829  mov     [rsp-8+arg_18], rdi
0x18002a82e  push    rbp
0x18002a82f  lea     rbp, [rsp-190h]
0x18002a837  sub     rsp, 290h
0x18002a83e  mov     rax, cs:__security_cookie
0x18002a845  xor     rax, rsp
0x18002a848  mov     [rbp+190h+var_10], rax
0x18002a84f  mov     rbx, rdx
0x18002a852  lea     rdx, [rsp+290h+SubKey]; unsigned __int16 *
0x18002a857  call    ?_MakeComCatCacheKey@@YAJAEBU_GUID@@PEAGK@Z; _MakeComCatCacheKey(_GUID const &,ushort *,ulong)
0x18002a85c  mov     edi, eax
0x18002a85e  test    eax, eax
0x18002a860  js      loc_18002A93A
0x18002a866  lea     rax, [rsp+290h+dwDisposition]
0x18002a86b  mov     [rsp+290h+hKey], 0
0x18002a874  mov     [rsp+290h+lpdwDisposition], rax; lpdwDisposition
0x18002a879  lea     rdx, [rsp+290h+SubKey]; lpSubKey
0x18002a87e  lea     rax, [rsp+290h+hKey]
0x18002a883  mov     [rsp+290h+dwDisposition], 0
0x18002a88b  mov     [rsp+290h+phkResult], rax; phkResult
0x18002a890  xor     r9d, r9d; lpClass
0x18002a893  mov     [rsp+290h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002a89c  xor     r8d, r8d; Reserved
0x18002a89f  mov     [rsp+290h+samDesired], 20006h; samDesired
0x18002a8a7  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002a8ae  mov     [rsp+290h+dwOptions], 0; dwOptions
0x18002a8b6  call    cs:__imp_RegCreateKeyExW
0x18002a8bc  mov     edi, eax
0x18002a8be  test    eax, eax
0x18002a8c0  jle     short loc_18002A8CB
0x18002a8c2  movzx   edi, ax
0x18002a8c5  or      edi, 80070000h
0x18002a8cb  test    edi, edi
0x18002a8cd  js      short loc_18002A93A
0x18002a8cf  lea     r8, [rsp+290h+cbData]; unsigned int *
0x18002a8d4  mov     [rsp+290h+lpData], 0
0x18002a8dd  lea     rdx, [rsp+290h+lpData]; unsigned __int8 **
0x18002a8e2  mov     [rsp+290h+cbData], 0
0x18002a8ea  mov     rcx, rbx; hdsa
0x18002a8ed  call    ?_ComCatCacheFromDSA@@YAJPEAU_DSA@@PEAPEAEPEAK@Z; _ComCatCacheFromDSA(_DSA *,uchar * *,ulong *)
0x18002a8f2  mov     edi, eax
0x18002a8f4  test    eax, eax
0x18002a8f6  js      short loc_18002A92F
0x18002a8f8  mov     eax, [rsp+290h+cbData]
0x18002a8fc  lea     rdx, aImplementing; "Implementing"
0x18002a903  mov     rbx, [rsp+290h+lpData]
0x18002a908  mov     r9d, 3; dwType
0x18002a90e  mov     rcx, [rsp+290h+hKey]; hKey
0x18002a913  xor     r8d, r8d; Reserved
0x18002a916  mov     [rsp+290h+samDesired], eax; cbData
0x18002a91a  mov     qword ptr [rsp+290h+dwOptions], rbx; lpData
0x18002a91f  call    cs:__imp_RegSetValueExW
0x18002a925  mov     rcx, rbx; Block
0x18002a928  mov     edi, eax
0x18002a92a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002a92f  mov     rcx, [rsp+290h+hKey]; hKey
0x18002a934  call    cs:__imp_RegCloseKey
0x18002a93a  mov     eax, edi
0x18002a93c  mov     rcx, [rbp+190h+var_10]
0x18002a943  xor     rcx, rsp; StackCookie
0x18002a946  call    __security_check_cookie
0x18002a94b  lea     r11, [rsp+290h+var_s0]
0x18002a953  mov     rbx, [r11+20h]
0x18002a957  mov     rdi, [r11+28h]
0x18002a95b  mov     rsp, r11
0x18002a95e  pop     rbp
0x18002a95f  retn
```
