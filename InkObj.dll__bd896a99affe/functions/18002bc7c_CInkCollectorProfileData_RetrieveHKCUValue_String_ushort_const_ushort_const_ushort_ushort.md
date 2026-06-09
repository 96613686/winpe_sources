# CInkCollectorProfileData::RetrieveHKCUValue_String(ushort const *,ushort const *,ushort * *,ushort *)

- ea: `0x18002bc7c`
- end: `0x18002be77`
- name: `?RetrieveHKCUValue_String@CInkCollectorProfileData@@AEAAJPEBG0PEAPEAGPEAG@Z`
- size: `507`
- prototype: `__int64 __fastcall(CInkCollectorProfileData *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002bb08`

## callees

- `0x18002bc7c`
- `0x18007f40c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bcca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bd82`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bcca`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18002bd82`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bd5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002be17`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002be23`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bd5f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002be17`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002be23`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bcfb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bd3d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bdb3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bdf8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bcfb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bd3d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bdb3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002bdf8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002bd0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002bdc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002be2e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002bd0c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002bdc4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002be2e`

## pseudocode

```c
__int64 __fastcall CInkCollectorProfileData::RetrieveHKCUValue_String(
        CInkCollectorProfileData *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4)
{
  unsigned int v5; // ebx
  unsigned __int16 *lpData; // rax
  unsigned __int16 *v7; // rax
  unsigned __int16 *v8; // rax
  HKEY hKey; // [rsp+48h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  int v12; // [rsp+54h] [rbp+24h]

  v12 = HIDWORD(a3);
  cbData = 0;
  hKey = 0;
  v5 = 1;
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\\\Microsoft\\\\TPG\\\\Recognizers", 0, 1u, &hKey) )
  {
    if ( !RegQueryValueExW(hKey, L"GestureRecognizer", 0, 0, 0, &cbData) )
    {
      lpData = (unsigned __int16 *)CoTaskMemAlloc(cbData + 2LL);
      *a4 = lpData;
      if ( !lpData )
      {
LABEL_10:
        v5 = -2147024882;
        goto LABEL_13;
      }
      if ( !RegQueryValueExW(hKey, L"GestureRecognizer", 0, 0, (LPBYTE)lpData, &cbData) )
      {
        v5 = 0;
        (*a4)[(unsigned __int64)cbData >> 1] = 0;
LABEL_13:
        RegCloseKey(hKey);
        return v5;
      }
    }
    RegCloseKey(hKey);
  }
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\\\Microsoft\\\\TPG\\\\Recognizers", 0, 1u, &hKey) )
  {
    if ( !RegQueryValueExW(hKey, L"GestureRecognizer", 0, 0, 0, &cbData) )
    {
      v7 = (unsigned __int16 *)CoTaskMemAlloc(cbData + 2LL);
      *a4 = v7;
      if ( !v7 )
        goto LABEL_10;
      if ( !RegQueryValueExW(hKey, L"GestureRecognizer", 0, 0, (LPBYTE)v7, &cbData) )
      {
        (*a4)[(unsigned __int64)cbData >> 1] = 0;
        goto LABEL_13;
      }
    }
    RegCloseKey(hKey);
  }
  v8 = (unsigned __int16 *)CoTaskMemAlloc(0x4Eu);
  *a4 = v8;
  if ( !v8 )
    return 2147942414LL;
  StringCchCopyNW(v8, 0x27u, L"{BED9A940-7D48-48e3-9A68-F4887A5A1B2E}", 0x26u);
  (*a4)[38] = 0;
  return v5;
}

```

## disassembly

```asm
0x18002bc7c  mov     r11, rsp
0x18002bc7f  mov     [r11+8], rbx
0x18002bc83  mov     [r11+20h], rdi
0x18002bc87  mov     [r11+18h], r8
0x18002bc8b  mov     [r11+10h], rdx
0x18002bc8f  push    rbp
0x18002bc90  mov     rbp, rsp
0x18002bc93  sub     rsp, 30h
0x18002bc97  mov     rdi, r9
0x18002bc9a  mov     [rbp+cbData], 0
0x18002bca1  lea     rax, [rbp+hKey]
0x18002bca5  mov     [rbp+hKey], 0
0x18002bcad  mov     ebx, 1
0x18002bcb2  mov     [r11-18h], rax
0x18002bcb6  mov     r9d, ebx; samDesired
0x18002bcb9  lea     rdx, aSoftwareMicros_3; "Software\\\\Microsoft\\\\TPG\\\\Recogni"...
0x18002bcc0  xor     r8d, r8d; ulOptions
0x18002bcc3  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002bcca  call    cs:__imp_RegOpenKeyExW
0x18002bcd0  test    eax, eax
0x18002bcd2  jnz     loc_18002BD65
0x18002bcd8  mov     rcx, [rbp+hKey]; hKey
0x18002bcdc  lea     rax, [rbp+cbData]
0x18002bce0  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002bce5  lea     rdx, aGesturerecogni; "GestureRecognizer"
0x18002bcec  xor     r9d, r9d; lpType
0x18002bcef  mov     [rsp+30h+lpData], 0; lpData
0x18002bcf8  xor     r8d, r8d; lpReserved
0x18002bcfb  call    cs:__imp_RegQueryValueExW
0x18002bd01  test    eax, eax
0x18002bd03  jnz     short loc_18002BD5B
0x18002bd05  mov     ecx, [rbp+cbData]
0x18002bd08  add     rcx, 2; cb
0x18002bd0c  call    cs:__imp_CoTaskMemAlloc
0x18002bd12  mov     [rdi], rax
0x18002bd15  test    rax, rax
0x18002bd18  jz      loc_18002BDD2
0x18002bd1e  lea     rcx, [rbp+cbData]
0x18002bd22  xor     r9d, r9d; lpType
0x18002bd25  mov     [rsp+30h+lpcbData], rcx; lpcbData
0x18002bd2a  lea     rdx, aGesturerecogni; "GestureRecognizer"
0x18002bd31  mov     rcx, [rbp+hKey]; hKey
0x18002bd35  xor     r8d, r8d; lpReserved
0x18002bd38  mov     [rsp+30h+lpData], rax; lpData
0x18002bd3d  call    cs:__imp_RegQueryValueExW
0x18002bd43  test    eax, eax
0x18002bd45  jnz     short loc_18002BD5B
0x18002bd47  mov     edx, [rbp+cbData]
0x18002bd4a  mov     rcx, [rdi]
0x18002bd4d  shr     rdx, 1
0x18002bd50  xor     ebx, ebx
0x18002bd52  mov     [rcx+rdx*2], ax
0x18002bd56  jmp     loc_18002BE13
0x18002bd5b  mov     rcx, [rbp+hKey]; hKey
0x18002bd5f  call    cs:__imp_RegCloseKey
0x18002bd65  lea     rax, [rbp+hKey]
0x18002bd69  mov     r9d, ebx; samDesired
0x18002bd6c  xor     r8d, r8d; ulOptions
0x18002bd6f  mov     [rsp+30h+lpData], rax; phkResult
0x18002bd74  lea     rdx, aSoftwareMicros_3; "Software\\\\Microsoft\\\\TPG\\\\Recogni"...
0x18002bd7b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002bd82  call    cs:__imp_RegOpenKeyExW
0x18002bd88  test    eax, eax
0x18002bd8a  jnz     loc_18002BE29
0x18002bd90  mov     rcx, [rbp+hKey]; hKey
0x18002bd94  lea     rax, [rbp+cbData]
0x18002bd98  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002bd9d  lea     rdx, aGesturerecogni; "GestureRecognizer"
0x18002bda4  xor     r9d, r9d; lpType
0x18002bda7  mov     [rsp+30h+lpData], 0; lpData
0x18002bdb0  xor     r8d, r8d; lpReserved
0x18002bdb3  call    cs:__imp_RegQueryValueExW
0x18002bdb9  test    eax, eax
0x18002bdbb  jnz     short loc_18002BE1F
0x18002bdbd  mov     ecx, [rbp+cbData]
0x18002bdc0  add     rcx, 2; cb
0x18002bdc4  call    cs:__imp_CoTaskMemAlloc
0x18002bdca  mov     [rdi], rax
0x18002bdcd  test    rax, rax
0x18002bdd0  jnz     short loc_18002BDD9
0x18002bdd2  mov     ebx, 8007000Eh
0x18002bdd7  jmp     short loc_18002BE13
0x18002bdd9  lea     rcx, [rbp+cbData]
0x18002bddd  xor     r9d, r9d; lpType
0x18002bde0  mov     [rsp+30h+lpcbData], rcx; lpcbData
0x18002bde5  lea     rdx, aGesturerecogni; "GestureRecognizer"
0x18002bdec  mov     rcx, [rbp+hKey]; hKey
0x18002bdf0  xor     r8d, r8d; lpReserved
0x18002bdf3  mov     [rsp+30h+lpData], rax; lpData
0x18002bdf8  call    cs:__imp_RegQueryValueExW
0x18002bdfe  test    eax, eax
0x18002be00  jnz     short loc_18002BE1F
0x18002be02  mov     r8d, [rbp+cbData]
0x18002be06  mov     rdx, [rdi]
0x18002be09  shr     r8, 1
0x18002be0c  xor     ecx, ecx
0x18002be0e  mov     [rdx+r8*2], cx
0x18002be13  mov     rcx, [rbp+hKey]; hKey
0x18002be17  call    cs:__imp_RegCloseKey
0x18002be1d  jmp     short loc_18002BE65
0x18002be1f  mov     rcx, [rbp+hKey]; hKey
0x18002be23  call    cs:__imp_RegCloseKey
0x18002be29  mov     ecx, 4Eh ; 'N'; cb
0x18002be2e  call    cs:__imp_CoTaskMemAlloc
0x18002be34  mov     [rdi], rax
0x18002be37  test    rax, rax
0x18002be3a  jnz     short loc_18002BE43
0x18002be3c  mov     eax, 8007000Eh
0x18002be41  jmp     short loc_18002BE67
0x18002be43  mov     r9d, 26h ; '&'; unsigned __int64
0x18002be49  lea     r8, aBed9a9407d4848; "{BED9A940-7D48-48e3-9A68-F4887A5A1B2E}"
0x18002be50  mov     rcx, rax; unsigned __int16 *
0x18002be53  lea     edx, [r9+1]; unsigned __int64
0x18002be57  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x18002be5c  mov     rcx, [rdi]
0x18002be5f  xor     eax, eax
0x18002be61  mov     [rcx+4Ch], ax
0x18002be65  mov     eax, ebx
0x18002be67  mov     rbx, [rsp+30h+arg_0]
0x18002be6c  mov     rdi, [rsp+30h+arg_18]
0x18002be71  add     rsp, 30h
0x18002be75  pop     rbp
0x18002be76  retn
```
