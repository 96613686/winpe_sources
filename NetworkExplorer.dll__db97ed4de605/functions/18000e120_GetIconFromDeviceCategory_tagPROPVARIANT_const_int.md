# GetIconFromDeviceCategory(tagPROPVARIANT const &,int *)

- ea: `0x18000e120`
- end: `0x18000e41f`
- name: `?GetIconFromDeviceCategory@@YAJAEBUtagPROPVARIANT@@PEAH@Z`
- size: `767`
- prototype: `__int64 __fastcall(const struct tagPROPVARIANT *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180003950`

## callees

- `0x18000e120`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e186`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e1b7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e1e8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e219`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e24a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e27b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e2ac`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e2dd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e30e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e33f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e370`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e3a1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e3cf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e3fa`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e186`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e1b7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e1e8`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e219`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e24a`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e27b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e2ac`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e2dd`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e30e`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e33f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e370`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e3a1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e3cf`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000e3fa`

## string_xrefs

- `0x18000e3df`: `HomeSecurity`

## pseudocode

```c
__int64 __fastcall GetIconFromDeviceCategory(const struct tagPROPVARIANT *a1, int *a2)
{
  const WCHAR **p_bstrVal; // rdi
  unsigned int v4; // esi
  const WCHAR *v5; // rdi

  if ( a1->vt == 31 )
  {
    p_bstrVal = (const WCHAR **)&a1->bstrVal;
    goto LABEL_6;
  }
  v4 = -2147024809;
  if ( a1->vt == 4127 && a1->lVal )
  {
    p_bstrVal = (const WCHAR **)a1->bstrblobVal.pData;
LABEL_6:
    v5 = *p_bstrVal;
    v4 = 0;
    if ( CompareStringW(0x7Fu, 0, v5, -1, L"Printers", -1) == 2 )
    {
      *a2 = 112;
    }
    else if ( CompareStringW(0x7Fu, 0, v5, -1, L"Scanners", -1) == 2 )
    {
      *a2 = 113;
    }
    else if ( CompareStringW(0x7Fu, 0, v5, -1, L"FAX", -1) == 2 )
    {
      *a2 = 114;
    }
    else if ( CompareStringW(0x7Fu, 0, v5, -1, L"MFP", -1) == 2 )
    {
      *a2 = 115;
    }
    else if ( CompareStringW(0x7Fu, 0, v5, -1, L"Cameras", -1) == 2 )
    {
      *a2 = 116;
    }
    else if ( CompareStringW(0x7Fu, 0, v5, -1, L"Storage", -1) == 2 )
    {
      *a2 = 117;
    }
    else if ( CompareStringW(0x7Fu, 0, v5, -1, L"NetworkInfrastructure", -1) == 2 )
    {
      *a2 = 118;
    }
    else if ( CompareStringW(0x7Fu, 0, v5, -1, L"Displays", -1) == 2 )
    {
      *a2 = 119;
    }
    else if ( CompareStringW(0x7Fu, 0, v5, -1, L"MediaDevices", -1) == 2 )
    {
      *a2 = 120;
    }
    else if ( CompareStringW(0x7Fu, 0, v5, -1, L"Phones", -1) == 2 )
    {
      *a2 = 121;
    }
    else if ( CompareStringW(0x7Fu, 0, v5, -1, L"Input", -1) == 2 )
    {
      *a2 = 124;
    }
    else if ( CompareStringW(0x7Fu, 0, v5, -1, L"Gaming", -1) == 2 )
    {
      *a2 = 125;
    }
    else if ( CompareStringW(0x7Fu, 0, v5, -1, L"HomeAutomation", -1) == 2 )
    {
      *a2 = 127;
    }
    else if ( CompareStringW(0x7Fu, 0, v5, -1, L"HomeSecurity", -1) == 2 )
    {
      *a2 = 128;
    }
    else
    {
      return (unsigned int)-2147024809;
    }
  }
  return v4;
}

```

## disassembly

```asm
0x18000e120  push    rbx
0x18000e122  push    rbp
0x18000e123  push    rsi
0x18000e124  push    rdi
0x18000e125  push    r14
0x18000e127  sub     rsp, 30h
0x18000e12b  mov     eax, 1Fh
0x18000e130  mov     rbx, rdx
0x18000e133  cmp     ax, [rcx]
0x18000e136  jnz     short loc_18000E13E
0x18000e138  lea     rdi, [rcx+8]
0x18000e13c  jmp     short loc_18000E15F
0x18000e13e  mov     eax, 101Fh
0x18000e143  mov     esi, 80070057h
0x18000e148  cmp     ax, [rcx]
0x18000e14b  jnz     loc_18000E412
0x18000e151  cmp     dword ptr [rcx+8], 0
0x18000e155  jz      loc_18000E412
0x18000e15b  mov     rdi, [rcx+10h]
0x18000e15f  mov     rdi, [rdi]
0x18000e162  lea     rax, aPrinters; "Printers"
0x18000e169  or      ebp, 0FFFFFFFFh
0x18000e16c  xor     esi, esi
0x18000e16e  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18000e172  mov     r9d, ebp; cchCount1
0x18000e175  mov     r8, rdi; lpString1
0x18000e178  mov     [rsp+58h+lpString2], rax; lpString2
0x18000e17d  xor     edx, edx; dwCmpFlags
0x18000e17f  lea     r14d, [rsi+7Fh]
0x18000e183  mov     ecx, r14d; Locale
0x18000e186  call    cs:__imp_CompareStringW
0x18000e18c  cmp     eax, 2
0x18000e18f  jnz     short loc_18000E19C
0x18000e191  mov     dword ptr [rbx], 70h ; 'p'
0x18000e197  jmp     loc_18000E412
0x18000e19c  lea     rax, aScanners; "Scanners"
0x18000e1a3  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18000e1a7  mov     r9d, ebp; cchCount1
0x18000e1aa  mov     [rsp+58h+lpString2], rax; lpString2
0x18000e1af  mov     r8, rdi; lpString1
0x18000e1b2  xor     edx, edx; dwCmpFlags
0x18000e1b4  mov     ecx, r14d; Locale
0x18000e1b7  call    cs:__imp_CompareStringW
0x18000e1bd  cmp     eax, 2
0x18000e1c0  jnz     short loc_18000E1CD
0x18000e1c2  mov     dword ptr [rbx], 71h ; 'q'
0x18000e1c8  jmp     loc_18000E412
0x18000e1cd  lea     rax, aFax; "FAX"
0x18000e1d4  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18000e1d8  mov     r9d, ebp; cchCount1
0x18000e1db  mov     [rsp+58h+lpString2], rax; lpString2
0x18000e1e0  mov     r8, rdi; lpString1
0x18000e1e3  xor     edx, edx; dwCmpFlags
0x18000e1e5  mov     ecx, r14d; Locale
0x18000e1e8  call    cs:__imp_CompareStringW
0x18000e1ee  cmp     eax, 2
0x18000e1f1  jnz     short loc_18000E1FE
0x18000e1f3  mov     dword ptr [rbx], 72h ; 'r'
0x18000e1f9  jmp     loc_18000E412
0x18000e1fe  lea     rax, aMfp; "MFP"
0x18000e205  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18000e209  mov     r9d, ebp; cchCount1
0x18000e20c  mov     [rsp+58h+lpString2], rax; lpString2
0x18000e211  mov     r8, rdi; lpString1
0x18000e214  xor     edx, edx; dwCmpFlags
0x18000e216  mov     ecx, r14d; Locale
0x18000e219  call    cs:__imp_CompareStringW
0x18000e21f  cmp     eax, 2
0x18000e222  jnz     short loc_18000E22F
0x18000e224  mov     dword ptr [rbx], 73h ; 's'
0x18000e22a  jmp     loc_18000E412
0x18000e22f  lea     rax, aCameras; "Cameras"
0x18000e236  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18000e23a  mov     r9d, ebp; cchCount1
0x18000e23d  mov     [rsp+58h+lpString2], rax; lpString2
0x18000e242  mov     r8, rdi; lpString1
0x18000e245  xor     edx, edx; dwCmpFlags
0x18000e247  mov     ecx, r14d; Locale
0x18000e24a  call    cs:__imp_CompareStringW
0x18000e250  cmp     eax, 2
0x18000e253  jnz     short loc_18000E260
0x18000e255  mov     dword ptr [rbx], 74h ; 't'
0x18000e25b  jmp     loc_18000E412
0x18000e260  lea     rax, aStorage; "Storage"
0x18000e267  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18000e26b  mov     r9d, ebp; cchCount1
0x18000e26e  mov     [rsp+58h+lpString2], rax; lpString2
0x18000e273  mov     r8, rdi; lpString1
0x18000e276  xor     edx, edx; dwCmpFlags
0x18000e278  mov     ecx, r14d; Locale
0x18000e27b  call    cs:__imp_CompareStringW
0x18000e281  cmp     eax, 2
0x18000e284  jnz     short loc_18000E291
0x18000e286  mov     dword ptr [rbx], 75h ; 'u'
0x18000e28c  jmp     loc_18000E412
0x18000e291  lea     rax, aNetworkinfrast; "NetworkInfrastructure"
0x18000e298  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18000e29c  mov     r9d, ebp; cchCount1
0x18000e29f  mov     [rsp+58h+lpString2], rax; lpString2
0x18000e2a4  mov     r8, rdi; lpString1
0x18000e2a7  xor     edx, edx; dwCmpFlags
0x18000e2a9  mov     ecx, r14d; Locale
0x18000e2ac  call    cs:__imp_CompareStringW
0x18000e2b2  cmp     eax, 2
0x18000e2b5  jnz     short loc_18000E2C2
0x18000e2b7  mov     dword ptr [rbx], 76h ; 'v'
0x18000e2bd  jmp     loc_18000E412
0x18000e2c2  lea     rax, aDisplays; "Displays"
0x18000e2c9  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18000e2cd  mov     r9d, ebp; cchCount1
0x18000e2d0  mov     [rsp+58h+lpString2], rax; lpString2
0x18000e2d5  mov     r8, rdi; lpString1
0x18000e2d8  xor     edx, edx; dwCmpFlags
0x18000e2da  mov     ecx, r14d; Locale
0x18000e2dd  call    cs:__imp_CompareStringW
0x18000e2e3  cmp     eax, 2
0x18000e2e6  jnz     short loc_18000E2F3
0x18000e2e8  mov     dword ptr [rbx], 77h ; 'w'
0x18000e2ee  jmp     loc_18000E412
0x18000e2f3  lea     rax, aMediadevices; "MediaDevices"
0x18000e2fa  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18000e2fe  mov     r9d, ebp; cchCount1
0x18000e301  mov     [rsp+58h+lpString2], rax; lpString2
0x18000e306  mov     r8, rdi; lpString1
0x18000e309  xor     edx, edx; dwCmpFlags
0x18000e30b  mov     ecx, r14d; Locale
0x18000e30e  call    cs:__imp_CompareStringW
0x18000e314  cmp     eax, 2
0x18000e317  jnz     short loc_18000E324
0x18000e319  mov     dword ptr [rbx], 78h ; 'x'
0x18000e31f  jmp     loc_18000E412
0x18000e324  lea     rax, aPhones; "Phones"
0x18000e32b  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18000e32f  mov     r9d, ebp; cchCount1
0x18000e332  mov     [rsp+58h+lpString2], rax; lpString2
0x18000e337  mov     r8, rdi; lpString1
0x18000e33a  xor     edx, edx; dwCmpFlags
0x18000e33c  mov     ecx, r14d; Locale
0x18000e33f  call    cs:__imp_CompareStringW
0x18000e345  cmp     eax, 2
0x18000e348  jnz     short loc_18000E355
0x18000e34a  mov     dword ptr [rbx], 79h ; 'y'
0x18000e350  jmp     loc_18000E412
0x18000e355  lea     rax, aInput; "Input"
0x18000e35c  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18000e360  mov     r9d, ebp; cchCount1
0x18000e363  mov     [rsp+58h+lpString2], rax; lpString2
0x18000e368  mov     r8, rdi; lpString1
0x18000e36b  xor     edx, edx; dwCmpFlags
0x18000e36d  mov     ecx, r14d; Locale
0x18000e370  call    cs:__imp_CompareStringW
0x18000e376  cmp     eax, 2
0x18000e379  jnz     short loc_18000E386
0x18000e37b  mov     dword ptr [rbx], 7Ch ; '|'
0x18000e381  jmp     loc_18000E412
0x18000e386  lea     rax, aGaming; "Gaming"
0x18000e38d  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18000e391  mov     r9d, ebp; cchCount1
0x18000e394  mov     [rsp+58h+lpString2], rax; lpString2
0x18000e399  mov     r8, rdi; lpString1
0x18000e39c  xor     edx, edx; dwCmpFlags
0x18000e39e  mov     ecx, r14d; Locale
0x18000e3a1  call    cs:__imp_CompareStringW
0x18000e3a7  cmp     eax, 2
0x18000e3aa  jnz     short loc_18000E3B4
0x18000e3ac  mov     dword ptr [rbx], 7Dh ; '}'
0x18000e3b2  jmp     short loc_18000E412
0x18000e3b4  lea     rax, aHomeautomation; "HomeAutomation"
0x18000e3bb  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18000e3bf  mov     r9d, ebp; cchCount1
0x18000e3c2  mov     [rsp+58h+lpString2], rax; lpString2
0x18000e3c7  mov     r8, rdi; lpString1
0x18000e3ca  xor     edx, edx; dwCmpFlags
0x18000e3cc  mov     ecx, r14d; Locale
0x18000e3cf  call    cs:__imp_CompareStringW
0x18000e3d5  cmp     eax, 2
0x18000e3d8  jnz     short loc_18000E3DF
0x18000e3da  mov     [rbx], r14d
0x18000e3dd  jmp     short loc_18000E412
0x18000e3df  lea     rax, aHomesecurity; "HomeSecurity"
0x18000e3e6  mov     [rsp+58h+cchCount2], ebp; cchCount2
0x18000e3ea  mov     r9d, ebp; cchCount1
0x18000e3ed  mov     [rsp+58h+lpString2], rax; lpString2
0x18000e3f2  mov     r8, rdi; lpString1
0x18000e3f5  xor     edx, edx; dwCmpFlags
0x18000e3f7  mov     ecx, r14d; Locale
0x18000e3fa  call    cs:__imp_CompareStringW
0x18000e400  cmp     eax, 2
0x18000e403  jnz     short loc_18000E40D
0x18000e405  mov     dword ptr [rbx], 80h
0x18000e40b  jmp     short loc_18000E412
0x18000e40d  mov     esi, 80070057h
0x18000e412  mov     eax, esi
0x18000e414  add     rsp, 30h
0x18000e418  pop     r14
0x18000e41a  pop     rdi
0x18000e41b  pop     rsi
0x18000e41c  pop     rbp
0x18000e41d  pop     rbx
0x18000e41e  retn
```
