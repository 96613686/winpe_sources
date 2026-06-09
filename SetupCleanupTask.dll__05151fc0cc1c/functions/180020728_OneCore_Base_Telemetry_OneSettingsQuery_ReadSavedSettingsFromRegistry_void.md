# OneCore::Base::Telemetry::OneSettingsQuery::ReadSavedSettingsFromRegistry(void)

- ea: `0x180020728`
- end: `0x1800209f1`
- name: `?ReadSavedSettingsFromRegistry@OneSettingsQuery@Telemetry@Base@OneCore@@AEAAJXZ`
- size: `713`
- prototype: `__int64 __fastcall(OneCore::Base::Telemetry::OneSettingsQuery *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001f3f4`

## callees

- `0x180003850`
- `0x18001a124`
- `0x18001a5b4`
- `0x180020728`
- `0x180032310`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180020981`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180020981`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800208e2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800208e2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002080f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002080f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800209ad`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800209ad`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020905`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180020905`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020881`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800208f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800209b8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180020881`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800208f6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800209b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002084c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002086d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800209c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002084c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002086d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800209c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall OneCore::Base::Telemetry::OneSettingsQuery::ReadSavedSettingsFromRegistry(
        OneCore::Base::Telemetry::OneSettingsQuery *this)
{
  char *v1; // r14
  char *v2; // r12
  char *v3; // r15
  BYTE *v5; // rsi
  signed int v6; // ebx
  LSTATUS v7; // eax
  bool v8; // cc
  int v9; // ebx
  RtlNameValueArray *v10; // rdi
  void *v11; // r8
  void *v12; // r8
  HANDLE ProcessHeap; // rax
  HKEY v14; // rcx
  DWORD v15; // ebx
  HANDLE v16; // rax
  int v17; // r14d
  DWORD i; // edx
  LSTATUS v19; // eax
  HANDLE v20; // rax
  DWORD cbMaxValueLen; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbData; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cchValueName; // [rsp+68h] [rbp-98h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp-94h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  WCHAR SubKey[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR ValueName[264]; // [rsp+290h] [rbp+190h] BYREF

  v1 = (char *)this + 560;
  v2 = (char *)this + 1080;
  v3 = (char *)this + 40;
  cchValueName = 0;
  cbData = 0;
  cbMaxValueLen = 0;
  Type = 0;
  hKey = 0;
  v5 = 0;
  v6 = StringCchPrintfW(SubKey, 0x104u, L"%ls\\%ls\\%ls", (char *)this + 1080, (char *)this + 40, (char *)this + 560);
  if ( v6 >= 0 )
  {
    v6 = StringCchPrintfW(SubKey, 0x104u, L"%ls\\%ls\\%ls\\%ls", v2, v3, v1, L"Settings");
    if ( v6 >= 0 )
    {
      v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey);
      v6 = v7;
      v8 = v7 <= 0;
      if ( v7 )
        goto LABEL_4;
      v10 = (OneCore::Base::Telemetry::OneSettingsQuery *)((char *)this + 1608);
      RtlNameValueArray::Clear(v10);
      v11 = (void *)*((_QWORD *)v10 + 5);
      if ( v11 )
        HeapFree(*(HANDLE *)v10, 0, v11);
      *(_OWORD *)v10 = 0;
      *((_OWORD *)v10 + 1) = 0;
      *((_OWORD *)v10 + 2) = 0;
      v12 = (void *)*((_QWORD *)v10 + 5);
      if ( v12 )
        HeapFree(0, 0, v12);
      *(_OWORD *)v10 = 0;
      *((_OWORD *)v10 + 1) = 0;
      *((_OWORD *)v10 + 2) = 0;
      ProcessHeap = GetProcessHeap();
      v14 = hKey;
      *(_QWORD *)v10 = ProcessHeap;
      *((_QWORD *)v10 + 4) = 16;
      *((_QWORD *)v10 + 2) = 0;
      *((_QWORD *)v10 + 3) = 0;
      *((_QWORD *)v10 + 5) = 0;
      *((_QWORD *)v10 + 1) = 8;
      v7 = RegQueryInfoKeyW(v14, 0, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueLen, 0, 0);
      v6 = v7;
      v8 = v7 <= 0;
      if ( v7 )
      {
LABEL_4:
        if ( v8 )
          goto LABEL_22;
        v9 = (unsigned __int16)v7;
        goto LABEL_6;
      }
      v15 = cbMaxValueLen;
      v16 = GetProcessHeap();
      v5 = (BYTE *)HeapAlloc(v16, 8u, v15);
      if ( !v5 )
      {
        v6 = -2147024882;
        goto LABEL_22;
      }
      v17 = 1;
      for ( i = 0; ; i = v17++ )
      {
        cbData = cbMaxValueLen;
        cchValueName = 260;
        v19 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, &Type, v5, &cbData);
        v6 = v19;
        if ( v19 )
          break;
        v6 = RtlNameValueArray::Append(v10, ValueName, (const unsigned __int16 *)v5);
        if ( v6 < 0 )
          goto LABEL_22;
      }
      if ( v19 == 259 )
      {
        v6 = 0;
      }
      else if ( v19 > 0 )
      {
        v9 = (unsigned __int16)v19;
LABEL_6:
        v6 = v9 | 0x80070000;
      }
    }
  }
LABEL_22:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v5 )
  {
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v5);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180020728  push    rbp
0x18002072a  push    rbx
0x18002072b  push    rsi
0x18002072c  push    rdi
0x18002072d  push    r12
0x18002072f  push    r13
0x180020731  push    r14
0x180020733  push    r15
0x180020735  lea     rbp, [rsp-3B8h]
0x18002073d  sub     rsp, 4B8h
0x180020744  mov     rax, cs:__security_cookie
0x18002074b  xor     rax, rsp
0x18002074e  mov     [rbp+3F0h+var_50], rax
0x180020755  xor     r13d, r13d
0x180020758  lea     r14, [rcx+230h]
0x18002075f  lea     r12, [rcx+438h]
0x180020766  mov     [rsp+4F0h+lpcbMaxSubKeyLen], r14
0x18002076b  lea     r15, [rcx+28h]
0x18002076f  mov     [rsp+4F0h+cchValueName], r13d
0x180020774  mov     rdi, rcx
0x180020777  mov     [rsp+4F0h+phkResult], r15
0x18002077c  mov     r9, r12
0x18002077f  mov     [rsp+4F0h+cbData], r13d
0x180020784  lea     r8, aLsLsLs; "%ls\\%ls\\%ls"
0x18002078b  mov     [rsp+4F0h+cbMaxValueLen], r13d
0x180020790  mov     edx, 104h; unsigned __int64
0x180020795  mov     [rsp+4F0h+Type], r13d
0x18002079a  lea     rcx, [rbp+3F0h+SubKey]; unsigned __int16 *
0x18002079e  mov     [rsp+4F0h+hKey], r13
0x1800207a3  mov     esi, r13d
0x1800207a6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800207ab  mov     ebx, eax
0x1800207ad  test    eax, eax
0x1800207af  js      loc_1800209A3
0x1800207b5  lea     rax, aSettings_0; "Settings"
0x1800207bc  mov     r9, r12
0x1800207bf  mov     [rsp+4F0h+lpcbMaxClassLen], rax
0x1800207c4  lea     r8, aLsLsLsLs; "%ls\\%ls\\%ls\\%ls"
0x1800207cb  mov     [rsp+4F0h+lpcbMaxSubKeyLen], r14
0x1800207d0  lea     rcx, [rbp+3F0h+SubKey]; unsigned __int16 *
0x1800207d4  mov     [rsp+4F0h+phkResult], r15
0x1800207d9  mov     r15d, 104h
0x1800207df  mov     edx, r15d; unsigned __int64
0x1800207e2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800207e7  mov     ebx, eax
0x1800207e9  test    eax, eax
0x1800207eb  js      loc_1800209A3
0x1800207f1  lea     rax, [rsp+4F0h+hKey]
0x1800207f6  mov     r9d, 20019h; samDesired
0x1800207fc  xor     r8d, r8d; ulOptions
0x1800207ff  mov     [rsp+4F0h+phkResult], rax; phkResult
0x180020804  lea     rdx, [rbp+3F0h+SubKey]; lpSubKey
0x180020808  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002080f  call    cs:__imp_RegOpenKeyExW
0x180020815  mov     ebx, eax
0x180020817  test    eax, eax
0x180020819  jz      short loc_18002082F
0x18002081b  jle     loc_1800209A3
0x180020821  movzx   ebx, ax
0x180020824  or      ebx, 80070000h
0x18002082a  jmp     loc_1800209A3
0x18002082f  add     rdi, 648h
0x180020836  mov     rcx, rdi; this
0x180020839  call    ?Clear@RtlNameValueArray@@QEAAXXZ; RtlNameValueArray::Clear(void)
0x18002083e  mov     r8, [rdi+28h]; lpMem
0x180020842  test    r8, r8
0x180020845  jz      short loc_180020852
0x180020847  mov     rcx, [rdi]; hHeap
0x18002084a  xor     edx, edx; dwFlags
0x18002084c  call    cs:__imp_HeapFree
0x180020852  xorps   xmm0, xmm0
0x180020855  movups  xmmword ptr [rdi], xmm0
0x180020858  movups  xmmword ptr [rdi+10h], xmm0
0x18002085c  movups  xmmword ptr [rdi+20h], xmm0
0x180020860  mov     r8, [rdi+28h]; lpMem
0x180020864  test    r8, r8
0x180020867  jz      short loc_180020873
0x180020869  xor     edx, edx; dwFlags
0x18002086b  xor     ecx, ecx; hHeap
0x18002086d  call    cs:__imp_HeapFree
0x180020873  xorps   xmm0, xmm0
0x180020876  movups  xmmword ptr [rdi], xmm0
0x180020879  movups  xmmword ptr [rdi+10h], xmm0
0x18002087d  movups  xmmword ptr [rdi+20h], xmm0
0x180020881  call    cs:__imp_GetProcessHeap
0x180020887  mov     rcx, [rsp+4F0h+hKey]; hKey
0x18002088c  mov     r14d, 8
0x180020892  mov     [rsp+4F0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x180020897  xor     r9d, r9d; lpReserved
0x18002089a  mov     [rsp+4F0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x18002089f  xor     r8d, r8d; lpcchClass
0x1800208a2  mov     [rdi], rax
0x1800208a5  xor     edx, edx; lpClass
0x1800208a7  lea     rax, [rsp+4F0h+cbMaxValueLen]
0x1800208ac  mov     qword ptr [rdi+20h], 10h
0x1800208b4  mov     [rsp+4F0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800208b9  mov     [rsp+4F0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x1800208be  mov     [rsp+4F0h+lpcValues], r13; lpcValues
0x1800208c3  mov     [rsp+4F0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x1800208c8  mov     [rsp+4F0h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x1800208cd  mov     [rsp+4F0h+phkResult], r13; lpcSubKeys
0x1800208d2  mov     [rdi+10h], r13
0x1800208d6  mov     [rdi+18h], r13
0x1800208da  mov     [rdi+28h], r13
0x1800208de  mov     [rdi+8], r14
0x1800208e2  call    cs:__imp_RegQueryInfoKeyW
0x1800208e8  mov     ebx, eax
0x1800208ea  test    eax, eax
0x1800208ec  jnz     loc_18002081B
0x1800208f2  mov     ebx, [rsp+4F0h+cbMaxValueLen]
0x1800208f6  call    cs:__imp_GetProcessHeap
0x1800208fc  mov     r8d, ebx; dwBytes
0x1800208ff  mov     edx, r14d; dwFlags
0x180020902  mov     rcx, rax; hHeap
0x180020905  call    cs:__imp_HeapAlloc
0x18002090b  mov     rsi, rax
0x18002090e  test    rax, rax
0x180020911  jnz     short loc_18002091D
0x180020913  mov     ebx, 8007000Eh
0x180020918  jmp     loc_1800209A3
0x18002091d  mov     r14d, 1
0x180020923  xor     edx, edx
0x180020925  jmp     short loc_180020945
0x180020927  mov     r8, rsi; unsigned __int16 *
0x18002092a  lea     rdx, [rbp+3F0h+ValueName]; unsigned __int16 *
0x180020931  mov     rcx, rdi; this
0x180020934  call    ?Append@RtlNameValueArray@@QEAAJPEBG0@Z; RtlNameValueArray::Append(ushort const *,ushort const *)
0x180020939  mov     ebx, eax
0x18002093b  test    eax, eax
0x18002093d  js      short loc_1800209A3
0x18002093f  mov     edx, r14d; dwIndex
0x180020942  inc     r14d
0x180020945  mov     eax, [rsp+4F0h+cbMaxValueLen]
0x180020949  lea     r9, [rsp+4F0h+cchValueName]; lpcchValueName
0x18002094e  mov     rcx, [rsp+4F0h+hKey]; hKey
0x180020953  lea     r8, [rbp+3F0h+ValueName]; lpValueName
0x18002095a  mov     [rsp+4F0h+cbData], eax
0x18002095e  lea     rax, [rsp+4F0h+cbData]
0x180020963  mov     [rsp+4F0h+lpcValues], rax; lpcbData
0x180020968  lea     rax, [rsp+4F0h+Type]
0x18002096d  mov     [rsp+4F0h+lpcbMaxClassLen], rsi; lpData
0x180020972  mov     [rsp+4F0h+lpcbMaxSubKeyLen], rax; lpType
0x180020977  mov     [rsp+4F0h+phkResult], r13; lpReserved
0x18002097c  mov     [rsp+4F0h+cchValueName], r15d
0x180020981  call    cs:__imp_RegEnumValueW
0x180020987  mov     ebx, eax
0x180020989  test    eax, eax
0x18002098b  jz      short loc_180020927
0x18002098d  cmp     eax, 103h
0x180020992  jz      short loc_1800209A0
0x180020994  test    eax, eax
0x180020996  jle     short loc_1800209A3
0x180020998  movzx   ebx, bx
0x18002099b  jmp     loc_180020824
0x1800209a0  mov     ebx, r13d
0x1800209a3  mov     rcx, [rsp+4F0h+hKey]; hKey
0x1800209a8  test    rcx, rcx
0x1800209ab  jz      short loc_1800209B3
0x1800209ad  call    cs:__imp_RegCloseKey
0x1800209b3  test    rsi, rsi
0x1800209b6  jz      short loc_1800209CC
0x1800209b8  call    cs:__imp_GetProcessHeap
0x1800209be  mov     r8, rsi; lpMem
0x1800209c1  xor     edx, edx; dwFlags
0x1800209c3  mov     rcx, rax; hHeap
0x1800209c6  call    cs:__imp_HeapFree
0x1800209cc  mov     eax, ebx
0x1800209ce  mov     rcx, [rbp+3F0h+var_50]
0x1800209d5  xor     rcx, rsp; StackCookie
0x1800209d8  call    __security_check_cookie
0x1800209dd  add     rsp, 4B8h
0x1800209e4  pop     r15
0x1800209e6  pop     r14
0x1800209e8  pop     r13
0x1800209ea  pop     r12
0x1800209ec  pop     rdi
0x1800209ed  pop     rsi
0x1800209ee  pop     rbx
0x1800209ef  pop     rbp
0x1800209f0  retn
```
