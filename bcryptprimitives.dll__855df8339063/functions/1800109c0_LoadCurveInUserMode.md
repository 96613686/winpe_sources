# LoadCurveInUserMode

- ea: `0x1800109c0`
- end: `0x180010ba8`
- name: `LoadCurveInUserMode`
- size: `488`
- prototype: `__int64 __fastcall(_QWORD *, unsigned int, WCHAR *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180022340`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x180010270`
- `0x1800102a0`
- `0x1800109c0`
- `0x1800228b0`
- `0x180023ce0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010a20`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010a51`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010a20`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180010a51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010a95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010b7d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010a95`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010b7d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010b53`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180080705`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180010b53`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180080705`

## string_xrefs

- `0x180010b06`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180080696`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800806bf`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x180080758`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall LoadCurveInUserMode(_QWORD *a1, unsigned int a2, WCHAR *a3, unsigned int a4)
{
  void *v8; // rdi
  BYTE *v9; // rsi
  LSTATUS v10; // eax
  int v11; // edx
  unsigned int v12; // ebx
  LSTATUS v13; // eax
  int v14; // edx
  LSTATUS v16; // eax
  __int64 v17; // r9
  __int64 v18; // rcx
  LSTATUS v19; // eax
  int v20; // eax
  DWORD cbData; // [rsp+40h] [rbp-68h] BYREF
  DWORD Type; // [rsp+44h] [rbp-64h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-60h] BYREF
  void *v24; // [rsp+50h] [rbp-58h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-50h] BYREF

  v24 = 0;
  cbData = 0;
  hKey = 0;
  phkResult = 0;
  Type = 0;
  v8 = 0;
  v9 = 0;
  v10 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SYSTEM\\CurrentControlSet\\Control\\Cryptography\\ECCParameters",
          0,
          0x20019u,
          &hKey);
  v12 = v10;
  if ( !v10 )
  {
    v13 = RegOpenKeyExW(hKey, a3, 0, 0x20019u, &phkResult);
    v12 = v13;
    if ( v13 )
    {
      if ( v13 > 0 )
        v12 = (unsigned __int16)v13 | 0xC0070000;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v14,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          (unsigned int)"Status",
          v12,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          70);
      goto LABEL_8;
    }
    v16 = RegQueryValueExW(phkResult, L"Parameters", 0, 0, 0, &cbData);
    v12 = v16;
    if ( v16 )
    {
      if ( v16 > 0 )
        v12 = (unsigned __int16)v16 | 0xC0070000;
      v17 = 1102;
    }
    else
    {
      v9 = (BYTE *)SafeAllocaAllocateFromHeap(cbData);
      if ( !v9 )
      {
        v12 = -1073741801;
        DebugTraceError(3221225495LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 1110);
        goto LABEL_8;
      }
      v19 = RegQueryValueExW(phkResult, L"Parameters", 0, &Type, v9, &cbData);
      v12 = v19;
      if ( !v19 )
      {
        if ( Type == 3 )
        {
          v20 = AssignGenericDomainParameters(&v24, a2, v9, cbData, a3, a4);
          v12 = v20;
          if ( v20 >= 0 )
          {
            v12 = 0;
            *a1 = v24;
          }
          else
          {
            DebugTraceError(
              (unsigned int)v20,
              "Status",
              "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
              1132);
            v8 = v24;
          }
          goto LABEL_8;
        }
        v12 = -1073741811;
        v17 = 1125;
        v18 = 3221225485LL;
LABEL_29:
        DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v17);
        goto LABEL_8;
      }
      if ( v19 > 0 )
        v12 = (unsigned __int16)v19 | 0xC0070000;
      v17 = 1118;
    }
    v18 = v12;
    goto LABEL_29;
  }
  if ( v10 > 0 )
    v12 = (unsigned __int16)v10 | 0xC0070000;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v11,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
      (unsigned int)"Status",
      v12,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
      60);
LABEL_8:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v9 )
    MSCryptFree(v9);
  if ( v8 )
    FreeGenericEccKeyParameters(v8);
  return v12;
}

```

## disassembly

```asm
0x1800109c0  push    rbx
0x1800109c2  push    rbp
0x1800109c3  push    rsi
0x1800109c4  push    rdi
0x1800109c5  push    r12
0x1800109c7  push    r13
0x1800109c9  push    r14
0x1800109cb  push    r15
0x1800109cd  sub     rsp, 68h
0x1800109d1  xor     r13d, r13d
0x1800109d4  lea     rax, [rsp+0A8h+hKey]
0x1800109d9  mov     r15d, r9d
0x1800109dc  mov     [rsp+0A8h+var_58], r13
0x1800109e1  mov     rbp, r8
0x1800109e4  mov     [rsp+0A8h+cbData], r13d
0x1800109e9  mov     r12d, edx
0x1800109ec  mov     [rsp+0A8h+hKey], r13
0x1800109f1  mov     r14, rcx
0x1800109f4  mov     [rsp+0A8h+var_60], r13
0x1800109f9  mov     r9d, 20019h; samDesired
0x1800109ff  mov     [rsp+0A8h+Type], r13d
0x180010a04  xor     r8d, r8d; ulOptions
0x180010a07  mov     [rsp+0A8h+phkResult], rax; phkResult
0x180010a0c  lea     rdx, SubKey; "SYSTEM\\CurrentControlSet\\Control\\Cry"...
0x180010a13  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180010a1a  mov     edi, r13d
0x180010a1d  mov     esi, r13d
0x180010a20  call    cs:__imp_RegOpenKeyExW
0x180010a27  nop     dword ptr [rax+rax+00h]
0x180010a2c  mov     ebx, eax
0x180010a2e  test    eax, eax
0x180010a30  jnz     loc_180010AD5
0x180010a36  mov     rcx, [rsp+0A8h+hKey]; hKey
0x180010a3b  lea     rax, [rsp+0A8h+var_60]
0x180010a40  mov     r9d, 20019h; samDesired
0x180010a46  mov     [rsp+0A8h+phkResult], rax; phkResult
0x180010a4b  xor     r8d, r8d; ulOptions
0x180010a4e  mov     rdx, rbp; lpSubKey
0x180010a51  call    cs:__imp_RegOpenKeyExW
0x180010a58  nop     dword ptr [rax+rax+00h]
0x180010a5d  mov     ebx, eax
0x180010a5f  test    eax, eax
0x180010a61  jz      loc_180010B32
0x180010a67  jle     short loc_180010A72
0x180010a69  movzx   ebx, ax
0x180010a6c  or      ebx, 0C0070000h
0x180010a72  mov     rcx, cs:WPP_GLOBAL_Control
0x180010a79  lea     rax, WPP_GLOBAL_Control
0x180010a80  cmp     rcx, rax
0x180010a83  jz      short loc_180010A8B
0x180010a85  test    byte ptr [rcx+1Ch], 1
0x180010a89  jnz     short loc_180010AFA
0x180010a8b  mov     rcx, [rsp+0A8h+hKey]; hKey
0x180010a90  test    rcx, rcx
0x180010a93  jz      short loc_180010AA1
0x180010a95  call    cs:__imp_RegCloseKey
0x180010a9c  nop     dword ptr [rax+rax+00h]
0x180010aa1  mov     rcx, [rsp+0A8h+var_60]; hKey
0x180010aa6  test    rcx, rcx
0x180010aa9  jnz     loc_180010B7D
0x180010aaf  test    rsi, rsi
0x180010ab2  jnz     loc_180010B8E
0x180010ab8  test    rdi, rdi
0x180010abb  jnz     loc_180010B9B
0x180010ac1  mov     eax, ebx
0x180010ac3  add     rsp, 68h
0x180010ac7  pop     r15
0x180010ac9  pop     r14
0x180010acb  pop     r13
0x180010acd  pop     r12
0x180010acf  pop     rdi
0x180010ad0  pop     rsi
0x180010ad1  pop     rbp
0x180010ad2  pop     rbx
0x180010ad3  retn
0x180010ad5  jg      short loc_180010B27
0x180010ad7  mov     rcx, cs:WPP_GLOBAL_Control
0x180010ade  lea     rax, WPP_GLOBAL_Control
0x180010ae5  cmp     rcx, rax
0x180010ae8  jz      short loc_180010A8B
0x180010aea  test    byte ptr [rcx+1Ch], 1
0x180010aee  jz      short loc_180010A8B
0x180010af0  mov     [rsp+0A8h+var_78], 43Ch
0x180010af8  jmp     short loc_180010B02
0x180010afa  mov     [rsp+0A8h+var_78], 446h
0x180010b02  mov     rcx, [rcx+10h]
0x180010b06  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180010b0d  mov     [rsp+0A8h+lpcbData], r8
0x180010b12  lea     r9, aStatus; "Status"
0x180010b19  mov     dword ptr [rsp+0A8h+phkResult], ebx
0x180010b1d  call    WPP_SF_sDsd
0x180010b22  jmp     loc_180010A8B
0x180010b27  movzx   ebx, ax
0x180010b2a  or      ebx, 0C0070000h
0x180010b30  jmp     short loc_180010AD7
0x180010b32  mov     rcx, [rsp+0A8h+var_60]; hKey
0x180010b37  lea     rax, [rsp+0A8h+cbData]
0x180010b3c  mov     [rsp+0A8h+lpcbData], rax; lpcbData
0x180010b41  lea     rdx, ValueName; "Parameters"
0x180010b48  xor     r9d, r9d; lpType
0x180010b4b  mov     [rsp+0A8h+phkResult], r13; lpData
0x180010b50  xor     r8d, r8d; lpReserved
0x180010b53  call    cs:__imp_RegQueryValueExW
0x180010b5a  nop     dword ptr [rax+rax+00h]
0x180010b5f  mov     ebx, eax
0x180010b61  test    eax, eax
0x180010b63  jz      loc_1800806A8
0x180010b69  jle     loc_180080664
0x180010b6f  movzx   ebx, ax
0x180010b72  or      ebx, 0C0070000h
0x180010b78  jmp     loc_180080664
0x180010b7d  call    cs:__imp_RegCloseKey
0x180010b84  nop     dword ptr [rax+rax+00h]
0x180010b89  jmp     loc_180010AAF
0x180010b8e  mov     rcx, rsi
0x180010b91  call    MSCryptFree
0x180010b96  jmp     loc_180010AB8
0x180010b9b  mov     rcx, rdi; P
0x180010b9e  call    FreeGenericEccKeyParameters
0x180010ba3  jmp     loc_180010AC1
0x180080664  mov     r9d, 44Eh
0x18008066a  jmp     short loc_18008067B
0x18008066c  movzx   ebx, ax
0x18008066f  or      ebx, 0C0070000h
0x180080675  mov     r9d, 45Eh
0x18008067b  mov     ecx, ebx
0x18008067d  jmp     short loc_18008068F
0x18008067f  mov     ebx, 0C000000Dh
0x180080684  mov     r9d, 465h
0x18008068a  mov     ecx, 0C000000Dh
0x18008068f  lea     rdx, aStatus; "Status"
0x180080696  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18008069d  call    DebugTraceError
0x1800806a2  nop
0x1800806a3  jmp     loc_180010A8B
0x1800806a8  mov     ecx, [rsp+0A8h+cbData]
0x1800806ac  call    SafeAllocaAllocateFromHeap
0x1800806b1  mov     rsi, rax
0x1800806b4  test    rax, rax
0x1800806b7  jnz     short loc_1800806E2
0x1800806b9  mov     r9d, 456h
0x1800806bf  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800806c6  lea     rdx, aStatus; "Status"
0x1800806cd  mov     ecx, 0C0000017h
0x1800806d2  mov     ebx, 0C0000017h
0x1800806d7  call    DebugTraceError
0x1800806dc  nop
0x1800806dd  jmp     loc_180010A8B
0x1800806e2  mov     rcx, [rsp+0A8h+var_60]; hKey
0x1800806e7  lea     rax, [rsp+0A8h+cbData]
0x1800806ec  mov     [rsp+0A8h+lpcbData], rax; lpcbData
0x1800806f1  lea     r9, [rsp+0A8h+Type]; lpType
0x1800806f6  xor     r8d, r8d; lpReserved
0x1800806f9  mov     [rsp+0A8h+phkResult], rsi; lpData
0x1800806fe  lea     rdx, ValueName; "Parameters"
0x180080705  call    cs:__imp_RegQueryValueExW
0x18008070c  nop     dword ptr [rax+rax+00h]
0x180080711  mov     ebx, eax
0x180080713  test    eax, eax
0x180080715  jz      short loc_180080722
0x180080717  jle     loc_180080675
0x18008071d  jmp     loc_18008066C
0x180080722  cmp     [rsp+0A8h+Type], 3
0x180080727  jnz     loc_18008067F
0x18008072d  mov     r9d, [rsp+0A8h+cbData]
0x180080732  lea     rcx, [rsp+0A8h+var_58]
0x180080737  mov     dword ptr [rsp+0A8h+lpcbData], r15d
0x18008073c  mov     r8, rsi
0x18008073f  mov     edx, r12d
0x180080742  mov     [rsp+0A8h+phkResult], rbp
0x180080747  call    AssignGenericDomainParameters
0x18008074c  mov     ebx, eax
0x18008074e  test    eax, eax
0x180080750  jns     short loc_180080777
0x180080752  mov     r9d, 46Ch
0x180080758  lea     r8, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18008075f  lea     rdx, aStatus; "Status"
0x180080766  mov     ecx, eax
0x180080768  call    DebugTraceError
0x18008076d  mov     rdi, [rsp+0A8h+var_58]
0x180080772  jmp     loc_180010A8B
0x180080777  mov     rax, [rsp+0A8h+var_58]
0x18008077c  mov     ebx, r13d
0x18008077f  mov     [r14], rax
0x180080782  jmp     loc_180010A8B
```
