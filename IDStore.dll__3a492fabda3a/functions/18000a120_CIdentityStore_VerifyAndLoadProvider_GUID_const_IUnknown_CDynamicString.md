# CIdentityStore::VerifyAndLoadProvider(_GUID const *,IUnknown * *,CDynamicString *)

- ea: `0x18000a120`
- end: `0x18000a5dc`
- name: `?VerifyAndLoadProvider@CIdentityStore@@AEAAJPEBU_GUID@@PEAPEAUIUnknown@@PEAVCDynamicString@@@Z`
- size: `1212`
- prototype: `__int64 __fastcall(CIdentityStore *this, const struct _GUID *, LPVOID *, struct CDynamicString *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180008260`
- `0x180009cd0`

## callees

- `0x18000a120`
- `0x18000a5f0`
- `0x1800144b4`
- `0x1800145a0`
- `0x1800191ac`
- `0x180019210`
- `0x180019722`
- `0x180019750`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a2fd`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a2fd`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000a51d`
- `api-ms-win-core-heap-l1-1-0!HeapReAlloc` at `0x18000a51d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2e6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a3aa`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000a3aa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a420`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a420`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a2ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a362`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a2ae`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000a362`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a26c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000a26c`

## pseudocode

```c
__int64 __fastcall CIdentityStore::VerifyAndLoadProvider(
        CIdentityStore *this,
        const struct _GUID *a2,
        LPVOID *a3,
        struct CDynamicString *a4)
{
  int v7; // eax
  int v8; // edx
  __int64 v9; // r8
  signed int v10; // ebx
  HKEY v11; // rbp
  LSTATUS v12; // eax
  DWORD v13; // ecx
  DWORD v14; // ebx
  DWORD v15; // ecx
  void *v16; // rdi
  HANDLE ProcessHeap; // rax
  LPVOID v18; // rax
  unsigned __int64 v19; // rax
  void *v20; // rcx
  HRESULT Instance; // eax
  CIdentityProfileHandler *v22; // rcx
  __int64 v24; // rdx
  DWORD cbData; // [rsp+70h] [rbp-2B8h] BYREF
  DWORD Type; // [rsp+74h] [rbp-2B4h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-2B0h] BYREF
  unsigned __int16 v28[40]; // [rsp+80h] [rbp-2A8h] BYREF
  WCHAR SubKey[264]; // [rsp+D0h] [rbp-258h] BYREF

  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, a3, "CIdentityStore::VerifyAndLoadProvider");
  }
  v7 = StringCchPrintfW(
         v28,
         0x27u,
         L"{%08lX-%04X-%04X-%02X%02X-%02X%02X%02X%02X%02X%02X}",
         a2->Data1,
         a2->Data2,
         a2->Data3,
         a2->Data4[0],
         a2->Data4[1],
         a2->Data4[2],
         a2->Data4[3],
         a2->Data4[4],
         a2->Data4[5],
         a2->Data4[6],
         a2->Data4[7]);
  v10 = v7;
  if ( v7 < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
      goto LABEL_27;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_36;
    v24 = 29;
LABEL_33:
    WPP_SF_d(*((_QWORD *)v22 + 2), v24, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids, (unsigned int)v7);
LABEL_54:
    v22 = WPP_GLOBAL_Control;
    goto LABEL_36;
  }
  v7 = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", L"Software\\Microsoft\\IdentityStore\\Providers", v28);
  v10 = v7;
  if ( v7 < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
      goto LABEL_27;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_36;
    v24 = 30;
    goto LABEL_33;
  }
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
  {
    v22 = WPP_GLOBAL_Control;
    v10 = -2147019873;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
      goto LABEL_27;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_36;
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      (unsigned int)WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids,
      (unsigned int)v28,
      159);
    goto LABEL_54;
  }
  v11 = hKey;
  cbData = 0;
  Type = 1;
  v12 = RegQueryValueExW(hKey, L"Name", 0, &Type, 0, &cbData);
  v10 = v12;
  if ( v12 )
  {
    if ( v12 <= 0 )
      goto LABEL_20;
    goto LABEL_35;
  }
  v13 = cbData + 2;
  if ( cbData + 2 < cbData )
    goto LABEL_15;
  v14 = *((_DWORD *)a4 + 3);
  cbData += 2;
  v15 = v13 >> 1;
  if ( v15 > v14 )
  {
    v16 = *(void **)a4;
    v14 = v15 + (v15 >> 1) + 32;
    ProcessHeap = GetProcessHeap();
    if ( v16 )
      v18 = HeapReAlloc(ProcessHeap, 0, v16, 2 * v14);
    else
      v18 = HeapAlloc(ProcessHeap, 0, 2 * v14);
    if ( !v18 )
    {
      v10 = -2147024882;
      goto LABEL_48;
    }
    *(_QWORD *)a4 = v18;
    *((_DWORD *)a4 + 3) = v14;
  }
  v19 = 2LL * v14;
  if ( v19 > 0xFFFFFFFF )
  {
LABEL_15:
    v10 = -2147024362;
LABEL_48:
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        32,
        (unsigned int)WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids,
        (unsigned int)v28,
        v10);
      v22 = WPP_GLOBAL_Control;
    }
    goto LABEL_36;
  }
  v20 = *(void **)a4;
  cbData = 2 * v14;
  memset_0(v20, 0, (unsigned int)v19);
  v12 = RegQueryValueExW(v11, L"Name", 0, &Type, *(LPBYTE *)a4, &cbData);
  v10 = v12;
  if ( !v12 )
  {
    if ( Type != 1 )
    {
      v10 = -2147023267;
      goto LABEL_48;
    }
    *((_DWORD *)a4 + 2) = cbData >> 1;
    goto LABEL_21;
  }
  if ( v12 > 0 )
LABEL_35:
    v10 = (unsigned __int16)v12 | 0x80070000;
LABEL_20:
  if ( v10 < 0 )
    goto LABEL_48;
LABEL_21:
  Instance = CoCreateInstance(a2, 0, 1u, &GUID_0d1b9e0c_e8ba_4f55_a81b_bce934b948f5, a3);
  v10 = Instance;
  if ( Instance >= 0 )
    goto LABEL_22;
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
    goto LABEL_27;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      33,
      (unsigned int)WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids,
      (unsigned int)v28,
      Instance);
    goto LABEL_54;
  }
LABEL_36:
  if ( v22 == (CIdentityProfileHandler *)&WPP_GLOBAL_Control )
    goto LABEL_27;
  if ( (*((_BYTE *)v22 + 28) & 4) == 0 )
    goto LABEL_24;
  WPP_SF_sL(*((_QWORD *)v22 + 2), v8, v9, (unsigned int)"CIdentityStore::VerifyAndLoadProvider", v10);
LABEL_22:
  v22 = WPP_GLOBAL_Control;
LABEL_24:
  if ( v22 != (CIdentityProfileHandler *)&WPP_GLOBAL_Control && (*((_DWORD *)v22 + 7) & 0x400) != 0 )
    WPP_SF_s(*((_QWORD *)v22 + 2), 12, v9, "CIdentityStore::VerifyAndLoadProvider");
LABEL_27:
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(hKey);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000a120  mov     r11, rsp
0x18000a123  push    rbx
0x18000a124  sub     rsp, 320h
0x18000a12b  mov     rax, cs:__security_cookie
0x18000a132  xor     rax, rsp
0x18000a135  mov     [rsp+328h+var_48], rax
0x18000a13d  mov     [r11-10h], rsi
0x18000a141  mov     [r11-18h], rdi
0x18000a145  mov     [r11-20h], r12
0x18000a149  mov     r12, r8
0x18000a14c  mov     [r11-28h], r13
0x18000a150  mov     [r11-30h], r14
0x18000a154  mov     r14, rdx
0x18000a157  mov     [r11-38h], r15
0x18000a15b  mov     r15, r9
0x18000a15e  mov     [rsp+328h+hKey], 0FFFFFFFFFFFFFFFFh
0x18000a167  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a16e  lea     r13, WPP_GLOBAL_Control
0x18000a175  cmp     rcx, r13
0x18000a178  jz      short loc_18000A187
0x18000a17a  test    dword ptr [rcx+1Ch], 400h
0x18000a181  jnz     loc_18000A4B0
0x18000a187  movzx   ecx, byte ptr [r14+0Eh]
0x18000a18c  movzx   edx, byte ptr [r14+0Dh]
0x18000a191  movzx   r8d, byte ptr [r14+0Ch]
0x18000a196  movzx   r9d, byte ptr [r14+0Bh]
0x18000a19b  movzx   eax, byte ptr [r14+0Fh]
0x18000a1a0  movzx   r10d, byte ptr [r14+0Ah]
0x18000a1a5  movzx   r11d, byte ptr [r14+9]
0x18000a1aa  movzx   ebx, byte ptr [r14+8]
0x18000a1af  movzx   edi, word ptr [r14+6]
0x18000a1b4  movzx   esi, word ptr [r14+4]
0x18000a1b9  mov     [rsp+328h+var_2C0], eax
0x18000a1bd  mov     [rsp+328h+var_2C8], ecx
0x18000a1c1  lea     rcx, [rsp+328h+var_2A8]; unsigned __int16 *
0x18000a1c9  mov     [rsp+328h+var_2D0], edx
0x18000a1cd  mov     edx, 27h ; '''; unsigned __int64
0x18000a1d2  mov     [rsp+328h+var_2D8], r8d
0x18000a1d7  lea     r8, a08lx04x04x02x0; "{%08lX-%04X-%04X-%02X%02X-%02X%02X%02X%"...
0x18000a1de  mov     [rsp+328h+var_2E0], r9d
0x18000a1e3  mov     r9d, [r14]
0x18000a1e6  mov     [rsp+328h+var_2E8], r10d
0x18000a1eb  mov     [rsp+328h+var_2F0], r11d
0x18000a1f0  mov     [rsp+328h+var_2F8], ebx
0x18000a1f4  mov     dword ptr [rsp+328h+lpcbData], edi
0x18000a1f8  mov     dword ptr [rsp+328h+phkResult], esi
0x18000a1fc  mov     [rsp+328h+arg_0], rbp
0x18000a204  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a209  mov     ebx, eax
0x18000a20b  test    eax, eax
0x18000a20d  js      loc_18000A4CA
0x18000a213  lea     rax, [rsp+328h+var_2A8]
0x18000a21b  mov     edx, 104h; unsigned __int64
0x18000a220  lea     r9, SubKey; "Software\\Microsoft\\IdentityStore\\Pro"...
0x18000a227  mov     [rsp+328h+phkResult], rax
0x18000a22c  lea     r8, aSS; "%s\\%s"
0x18000a233  lea     rcx, [rsp+328h+SubKey]; unsigned __int16 *
0x18000a23b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000a240  mov     ebx, eax
0x18000a242  test    eax, eax
0x18000a244  js      loc_18000A441
0x18000a24a  lea     rax, [rsp+328h+hKey]
0x18000a24f  mov     r9d, 20019h; samDesired
0x18000a255  xor     r8d, r8d; ulOptions
0x18000a258  mov     [rsp+328h+phkResult], rax; phkResult
0x18000a25d  lea     rdx, [rsp+328h+SubKey]; lpSubKey
0x18000a265  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000a26c  call    cs:__imp_RegOpenKeyExW
0x18000a272  test    eax, eax
0x18000a274  jnz     loc_18000A4EA
0x18000a27a  mov     rbp, [rsp+328h+hKey]
0x18000a27f  lea     rax, [rsp+328h+cbData]
0x18000a284  xor     ecx, ecx
0x18000a286  mov     [rsp+328h+lpcbData], rax; lpcbData
0x18000a28b  mov     [rsp+328h+phkResult], rcx; lpData
0x18000a290  lea     r9, [rsp+328h+Type]; lpType
0x18000a295  mov     [rsp+328h+cbData], ecx
0x18000a299  lea     rdx, ValueName; "Name"
0x18000a2a0  mov     rcx, rbp; hKey
0x18000a2a3  mov     [rsp+328h+Type], 1
0x18000a2ab  xor     r8d, r8d; lpReserved
0x18000a2ae  call    cs:__imp_RegQueryValueExW
0x18000a2b4  mov     ebx, eax
0x18000a2b6  test    eax, eax
0x18000a2b8  jnz     loc_18000A470
0x18000a2be  mov     eax, [rsp+328h+cbData]
0x18000a2c2  lea     ecx, [rax+2]
0x18000a2c5  cmp     ecx, eax
0x18000a2c7  jb      short loc_18000A322
0x18000a2c9  mov     ebx, [r15+0Ch]
0x18000a2cd  mov     [rsp+328h+cbData], ecx
0x18000a2d1  shr     ecx, 1
0x18000a2d3  cmp     ecx, ebx
0x18000a2d5  jbe     short loc_18000A313
0x18000a2d7  mov     rdi, [r15]
0x18000a2da  mov     ebx, ecx
0x18000a2dc  shr     ebx, 1
0x18000a2de  add     ebx, 20h ; ' '
0x18000a2e1  add     ebx, ecx
0x18000a2e3  lea     esi, [rbx+rbx]
0x18000a2e6  call    cs:__imp_GetProcessHeap
0x18000a2ec  xor     edx, edx; dwFlags
0x18000a2ee  mov     rcx, rax; hHeap
0x18000a2f1  test    rdi, rdi
0x18000a2f4  jnz     loc_18000A517
0x18000a2fa  mov     r8d, esi; dwBytes
0x18000a2fd  call    cs:__imp_HeapAlloc
0x18000a303  test    rax, rax
0x18000a306  jz      loc_18000A52F
0x18000a30c  mov     [r15], rax
0x18000a30f  mov     [r15+0Ch], ebx
0x18000a313  mov     eax, ebx
0x18000a315  mov     ecx, 0FFFFFFFFh
0x18000a31a  add     rax, rax
0x18000a31d  cmp     rax, rcx
0x18000a320  jbe     short loc_18000A32C
0x18000a322  mov     ebx, 80070216h
0x18000a327  jmp     loc_18000A534
0x18000a32c  mov     rcx, [r15]; void *
0x18000a32f  xor     edx, edx; Val
0x18000a331  mov     r8d, eax; Size
0x18000a334  mov     [rsp+328h+cbData], r8d
0x18000a339  call    memset_0
0x18000a33e  lea     rax, [rsp+328h+cbData]
0x18000a343  xor     r8d, r8d; lpReserved
0x18000a346  mov     [rsp+328h+lpcbData], rax; lpcbData
0x18000a34b  lea     r9, [rsp+328h+Type]; lpType
0x18000a350  mov     rax, [r15]
0x18000a353  lea     rdx, ValueName; "Name"
0x18000a35a  mov     rcx, rbp; hKey
0x18000a35d  mov     [rsp+328h+phkResult], rax; lpData
0x18000a362  call    cs:__imp_RegQueryValueExW
0x18000a368  mov     ebx, eax
0x18000a36a  test    eax, eax
0x18000a36c  jnz     short loc_18000A385
0x18000a36e  cmp     [rsp+328h+Type], 1
0x18000a373  jnz     loc_18000A528
0x18000a379  mov     eax, [rsp+328h+cbData]
0x18000a37d  shr     eax, 1
0x18000a37f  mov     [r15+8], eax
0x18000a383  jmp     short loc_18000A393
0x18000a385  jg      loc_18000A476
0x18000a38b  test    ebx, ebx
0x18000a38d  js      loc_18000A534
0x18000a393  lea     r9, _GUID_0d1b9e0c_e8ba_4f55_a81b_bce934b948f5; riid
0x18000a39a  mov     [rsp+328h+phkResult], r12; ppv
0x18000a39f  xor     edx, edx; pUnkOuter
0x18000a3a1  mov     r8d, 1; dwClsContext
0x18000a3a7  mov     rcx, r14; rclsid
0x18000a3aa  call    cs:__imp_CoCreateInstance
0x18000a3b0  mov     ebx, eax
0x18000a3b2  test    eax, eax
0x18000a3b4  js      loc_18000A57B
0x18000a3ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a3c1  jmp     short loc_18000A3CB
0x18000a3c3  test    ebx, ebx
0x18000a3c5  js      loc_18000A484
0x18000a3cb  cmp     rcx, r13
0x18000a3ce  jz      short loc_18000A3DD
0x18000a3d0  test    dword ptr [rcx+1Ch], 400h
0x18000a3d7  jnz     loc_18000A5C2
0x18000a3dd  mov     rcx, [rsp+328h+hKey]; hKey
0x18000a3e2  mov     r15, [rsp+328h+var_38]
0x18000a3ea  mov     r14, [rsp+328h+var_30]
0x18000a3f2  mov     r13, [rsp+328h+var_28]
0x18000a3fa  mov     r12, [rsp+328h+var_20]
0x18000a402  mov     rdi, [rsp+328h+var_18]
0x18000a40a  mov     rsi, [rsp+328h+var_10]
0x18000a412  mov     rbp, [rsp+328h+arg_0]
0x18000a41a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000a41e  jz      short loc_18000A426
0x18000a420  call    cs:__imp_RegCloseKey
0x18000a426  mov     eax, ebx
0x18000a428  mov     rcx, [rsp+328h+var_48]
0x18000a430  xor     rcx, rsp; StackCookie
0x18000a433  call    __security_check_cookie
0x18000a438  add     rsp, 320h
0x18000a43f  pop     rbx
0x18000a440  retn
0x18000a441  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a448  cmp     rcx, r13
0x18000a44b  jz      short loc_18000A3DD
0x18000a44d  test    byte ptr [rcx+1Ch], 4
0x18000a451  jz      short loc_18000A484
0x18000a453  mov     edx, 1Eh
0x18000a458  mov     rcx, [rcx+10h]
0x18000a45c  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x18000a463  mov     r9d, eax
0x18000a466  call    WPP_SF_d
0x18000a46b  jmp     loc_18000A5B6
0x18000a470  jle     loc_18000A38B
0x18000a476  movzx   ebx, ax
0x18000a479  or      ebx, 80070000h
0x18000a47f  jmp     loc_18000A38B
0x18000a484  cmp     rcx, r13
0x18000a487  jz      loc_18000A3DD
0x18000a48d  test    byte ptr [rcx+1Ch], 4
0x18000a491  jz      loc_18000A3CB
0x18000a497  mov     rcx, [rcx+10h]
0x18000a49b  lea     r9, aCidentitystore; "CIdentityStore::VerifyAndLoadProvider"
0x18000a4a2  mov     dword ptr [rsp+328h+phkResult], ebx
0x18000a4a6  call    WPP_SF_sL
0x18000a4ab  jmp     loc_18000A3BA
0x18000a4b0  mov     rcx, [rcx+10h]
0x18000a4b4  lea     r9, aCidentitystore; "CIdentityStore::VerifyAndLoadProvider"
0x18000a4bb  mov     edx, 0Ah
0x18000a4c0  call    WPP_SF_s
0x18000a4c5  jmp     loc_18000A187
0x18000a4ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a4d1  cmp     rcx, r13
0x18000a4d4  jz      loc_18000A3DD
0x18000a4da  test    byte ptr [rcx+1Ch], 4
0x18000a4de  jz      short loc_18000A484
0x18000a4e0  mov     edx, 1Dh
0x18000a4e5  jmp     loc_18000A458
0x18000a4ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a4f1  mov     ebx, 8007139Fh
0x18000a4f6  cmp     rcx, r13
0x18000a4f9  jz      loc_18000A3DD
0x18000a4ff  test    byte ptr [rcx+1Ch], 4
0x18000a503  jz      loc_18000A484
0x18000a509  mov     edx, 1Fh
0x18000a50e  mov     dword ptr [rsp+328h+phkResult], ebx
0x18000a512  jmp     loc_18000A59E
0x18000a517  mov     r9, rsi; dwBytes
0x18000a51a  mov     r8, rdi; lpMem
0x18000a51d  call    cs:__imp_HeapReAlloc
0x18000a523  jmp     loc_18000A303
0x18000a528  mov     ebx, 8007065Dh
0x18000a52d  jmp     short loc_18000A534
0x18000a52f  mov     ebx, 8007000Eh
0x18000a534  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a53b  cmp     rcx, r13
0x18000a53e  jz      loc_18000A3C3
0x18000a544  test    byte ptr [rcx+1Ch], 4
0x18000a548  jz      loc_18000A3C3
0x18000a54e  mov     rcx, [rcx+10h]
0x18000a552  lea     r9, [rsp+328h+var_2A8]
0x18000a55a  mov     edx, 20h ; ' '
0x18000a55f  mov     dword ptr [rsp+328h+phkResult], ebx
0x18000a563  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x18000a56a  call    WPP_SF_Sd
0x18000a56f  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a576  jmp     loc_18000A3C3
0x18000a57b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a582  cmp     rcx, r13
0x18000a585  jz      loc_18000A3DD
0x18000a58b  test    byte ptr [rcx+1Ch], 4
0x18000a58f  jz      loc_18000A484
0x18000a595  mov     edx, 21h ; '!'
0x18000a59a  mov     dword ptr [rsp+328h+phkResult], eax
0x18000a59e  mov     rcx, [rcx+10h]
0x18000a5a2  lea     r9, [rsp+328h+var_2A8]
0x18000a5aa  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x18000a5b1  call    WPP_SF_Sd
0x18000a5b6  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a5bd  jmp     loc_18000A484
0x18000a5c2  mov     rcx, [rcx+10h]
0x18000a5c6  lea     r9, aCidentitystore; "CIdentityStore::VerifyAndLoadProvider"
0x18000a5cd  mov     edx, 0Ch
0x18000a5d2  call    WPP_SF_s
0x18000a5d7  jmp     loc_18000A3DD
```
