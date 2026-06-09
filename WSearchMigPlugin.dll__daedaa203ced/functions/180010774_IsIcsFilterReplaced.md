# IsIcsFilterReplaced

- ea: `0x180010774`
- end: `0x1800109a0`
- name: `IsIcsFilterReplaced`
- size: `556`
- prototype: `char()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800149a0`

## callees

- `0x1800026f0`
- `0x180010774`
- `0x180011a18`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180010894`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180010928`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180010894`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180010928`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800108ea`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800108ea`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800108da`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001096e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800108da`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001096e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800107d9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800107d9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001097d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001097d`

## pseudocode

```c
char IsIcsFilterReplaced()
{
  char v0; // bl
  HKEY v1; // rdi
  __int64 v2; // rax
  __int64 v3; // rax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v6[5]; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[16]; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v8; // [rsp+70h] [rbp-90h]
  __int128 v9; // [rsp+80h] [rbp-80h]
  _OWORD v10[2]; // [rsp+90h] [rbp-70h]
  _OWORD v11[3]; // [rsp+B0h] [rbp-50h] BYREF
  _OWORD v12[2]; // [rsp+E0h] [rbp-20h]
  wchar_t v13[264]; // [rsp+100h] [rbp+0h] BYREF

  v6[3] = -2;
  v0 = 0;
  v1 = 0;
  v6[1] = 0;
  v6[2] = 0;
  hKey = 0;
  if ( !RegOpenKeyExW(HKEY_CLASSES_ROOT, L".ics\\PersistentHandler", 0, 0x2001Fu, &hKey) )
  {
    v1 = hKey;
    v6[0] = hKey;
    *(_OWORD *)Data = *(_OWORD *)L"{5e941d80-bf96-11cd-b579-08002b30bfeb}";
    v8 = *(_OWORD *)L"0-bf96-11cd-b579-08002b30bfeb}";
    v9 = *(_OWORD *)L"1cd-b579-08002b30bfeb}";
    v10[0] = *(_OWORD *)L"-08002b30bfeb}";
    *(_OWORD *)((char *)v10 + 14) = *(_OWORD *)L"30bfeb}";
    v11[0] = *(_OWORD *)L"{e4c2c4de-bc6a-495e-ae1e-83f1ce9c2d31}";
    v11[1] = *(_OWORD *)L"e-bc6a-495e-ae1e-83f1ce9c2d31}";
    v11[2] = *(_OWORD *)L"95e-ae1e-83f1ce9c2d31}";
    v12[0] = *(_OWORD *)L"-83f1ce9c2d31}";
    *(_OWORD *)((char *)v12 + 14) = *(_OWORD *)L"9c2d31}";
    LODWORD(hKey) = 260;
    if ( (unsigned int)ATL::CRegKey::QueryStringValue((ATL::CRegKey *)v6, &word_18001B074, v13, (unsigned int *)&hKey)
      || (unsigned int)_o__wcsnicmp(v13, v11, (unsigned int)hKey) )
    {
      LODWORD(hKey) = 260;
      if ( !(unsigned int)ATL::CRegKey::QueryStringValue(
                            (ATL::CRegKey *)v6,
                            L"OriginalPersistentHandler",
                            v13,
                            (unsigned int *)&hKey)
        && !(unsigned int)_o__wcsnicmp(v13, v11, (unsigned int)hKey) )
      {
        v3 = -1;
        do
          ++v3;
        while ( *(_WORD *)&Data[2 * v3] );
        v0 = 1;
        RegSetValueExW(v1, L"OriginalPersistentHandler", 0, 1u, Data, 2 * v3 + 2);
      }
    }
    else
    {
      v2 = -1;
      do
        ++v2;
      while ( *(_WORD *)&Data[2 * v2] );
      v0 = 1;
      RegSetValueExW(v1, &word_18001B074, 0, 1u, Data, 2 * v2 + 2);
      RegDeleteValueW(v1, L"OriginalPersistentHandler");
    }
  }
  if ( v1 )
    RegCloseKey(v1);
  return v0;
}

```

## disassembly

```asm
0x180010774  push    rbp
0x180010776  push    rbx
0x180010777  push    rsi
0x180010778  push    rdi
0x180010779  lea     rbp, [rsp-228h]
0x180010781  sub     rsp, 328h
0x180010788  mov     [rsp+340h+var_2F0], 0FFFFFFFFFFFFFFFEh
0x180010791  mov     rax, cs:__security_cookie
0x180010798  xor     rax, rsp
0x18001079b  mov     [rbp+240h+var_30], rax
0x1800107a2  xor     esi, esi
0x1800107a4  mov     bl, sil
0x1800107a7  mov     edi, esi
0x1800107a9  mov     [rsp+340h+var_300], rsi
0x1800107ae  mov     [rsp+340h+var_2F8], rsi
0x1800107b3  mov     [rsp+340h+hKey], rsi
0x1800107b8  lea     rax, [rsp+340h+hKey]
0x1800107bd  mov     [rsp+340h+phkResult], rax; phkResult
0x1800107c2  mov     r9d, 2001Fh; samDesired
0x1800107c8  xor     r8d, r8d; ulOptions
0x1800107cb  lea     rdx, SubKey; ".ics\\PersistentHandler"
0x1800107d2  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800107d9  call    cs:__imp_RegOpenKeyExW
0x1800107df  test    eax, eax
0x1800107e1  jnz     loc_180010975
0x1800107e7  mov     rdi, [rsp+340h+hKey]
0x1800107ec  mov     [rsp+340h+var_308], rdi
0x1800107f1  movaps  xmm0, xmmword ptr cs:a5e941d80Bf9611; "{5e941d80-bf96-11cd-b579-08002b30bfeb}"
0x1800107f8  movaps  xmmword ptr [rsp+340h+Data], xmm0
0x1800107fd  movaps  xmm1, xmmword ptr cs:a5e941d80Bf9611+10h; "0-bf96-11cd-b579-08002b30bfeb}"
0x180010804  movaps  [rsp+340h+var_2D0], xmm1
0x180010809  movaps  xmm0, xmmword ptr cs:a5e941d80Bf9611+20h; "1cd-b579-08002b30bfeb}"
0x180010810  movaps  [rbp+240h+var_2C0], xmm0
0x180010814  movaps  xmm1, xmmword ptr cs:a5e941d80Bf9611+30h; "-08002b30bfeb}"
0x18001081b  movaps  xmmword ptr [rbp+240h+var_2B0], xmm1
0x18001081f  movups  xmm0, xmmword ptr cs:a5e941d80Bf9611+3Eh; "30bfeb}"
0x180010826  movups  xmmword ptr [rbp+240h+var_2B0+0Eh], xmm0
0x18001082a  movaps  xmm1, xmmword ptr cs:aE4c2c4deBc6a49; "{e4c2c4de-bc6a-495e-ae1e-83f1ce9c2d31}"
0x180010831  movaps  [rbp+240h+var_290], xmm1
0x180010835  movaps  xmm0, xmmword ptr cs:aE4c2c4deBc6a49+10h; "e-bc6a-495e-ae1e-83f1ce9c2d31}"
0x18001083c  movaps  [rbp+240h+var_280], xmm0
0x180010840  movaps  xmm1, xmmword ptr cs:aE4c2c4deBc6a49+20h; "95e-ae1e-83f1ce9c2d31}"
0x180010847  movaps  [rbp+240h+var_270], xmm1
0x18001084b  movaps  xmm0, xmmword ptr cs:aE4c2c4deBc6a49+30h; "-83f1ce9c2d31}"
0x180010852  movaps  xmmword ptr [rbp+240h+var_260], xmm0
0x180010856  movups  xmm1, xmmword ptr cs:aE4c2c4deBc6a49+3Eh; "9c2d31}"
0x18001085d  movups  xmmword ptr [rbp+240h+var_260+0Eh], xmm1
0x180010861  mov     dword ptr [rsp+340h+hKey], 104h
0x180010869  lea     r9, [rsp+340h+hKey]; unsigned int *
0x18001086e  lea     r8, [rbp+240h+var_240]; wchar_t *
0x180010872  lea     rdx, word_18001B074; wchar_t *
0x180010879  lea     rcx, [rsp+340h+var_308]; this
0x18001087e  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEB_WPEA_WPEAK@Z; ATL::CRegKey::QueryStringValue(wchar_t const *,wchar_t *,ulong *)
0x180010883  test    eax, eax
0x180010885  jnz     short loc_1800108F5
0x180010887  mov     r8d, dword ptr [rsp+340h+hKey]
0x18001088c  lea     rdx, [rbp+240h+var_290]
0x180010890  lea     rcx, [rbp+240h+var_240]
0x180010894  call    cs:__imp__o__wcsnicmp
0x18001089a  test    eax, eax
0x18001089c  jnz     short loc_1800108F5
0x18001089e  lea     rcx, [rsp+340h+Data]
0x1800108a3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800108a7  inc     rax
0x1800108aa  cmp     [rcx+rax*2], si
0x1800108ae  jnz     short loc_1800108A7
0x1800108b0  lea     eax, ds:2[rax*2]
0x1800108b7  mov     [rsp+340h+cbData], eax; cbData
0x1800108bb  lea     rax, [rsp+340h+Data]
0x1800108c0  mov     [rsp+340h+phkResult], rax; lpData
0x1800108c5  mov     ebx, 1
0x1800108ca  mov     r9d, ebx; dwType
0x1800108cd  xor     r8d, r8d; Reserved
0x1800108d0  lea     rdx, word_18001B074; lpValueName
0x1800108d7  mov     rcx, rdi; hKey
0x1800108da  call    cs:__imp_RegSetValueExW
0x1800108e0  lea     rdx, aOriginalpersis; "OriginalPersistentHandler"
0x1800108e7  mov     rcx, rdi; hKey
0x1800108ea  call    cs:__imp_RegDeleteValueW
0x1800108f0  jmp     loc_180010975
0x1800108f5  mov     dword ptr [rsp+340h+hKey], 104h
0x1800108fd  lea     r9, [rsp+340h+hKey]; unsigned int *
0x180010902  lea     r8, [rbp+240h+var_240]; wchar_t *
0x180010906  lea     rdx, aOriginalpersis; "OriginalPersistentHandler"
0x18001090d  lea     rcx, [rsp+340h+var_308]; this
0x180010912  call    ?QueryStringValue@CRegKey@ATL@@QEAAJPEB_WPEA_WPEAK@Z; ATL::CRegKey::QueryStringValue(wchar_t const *,wchar_t *,ulong *)
0x180010917  test    eax, eax
0x180010919  jnz     short loc_180010975
0x18001091b  mov     r8d, dword ptr [rsp+340h+hKey]
0x180010920  lea     rdx, [rbp+240h+var_290]
0x180010924  lea     rcx, [rbp+240h+var_240]
0x180010928  call    cs:__imp__o__wcsnicmp
0x18001092e  test    eax, eax
0x180010930  jnz     short loc_180010975
0x180010932  lea     rcx, [rsp+340h+Data]
0x180010937  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001093b  inc     rax
0x18001093e  cmp     [rcx+rax*2], si
0x180010942  jnz     short loc_18001093B
0x180010944  lea     eax, ds:2[rax*2]
0x18001094b  mov     [rsp+340h+cbData], eax; cbData
0x18001094f  lea     rax, [rsp+340h+Data]
0x180010954  mov     [rsp+340h+phkResult], rax; lpData
0x180010959  mov     ebx, 1
0x18001095e  mov     r9d, ebx; dwType
0x180010961  xor     r8d, r8d; Reserved
0x180010964  lea     rdx, aOriginalpersis; "OriginalPersistentHandler"
0x18001096b  mov     rcx, rdi; hKey
0x18001096e  call    cs:__imp_RegSetValueExW
0x180010974  nop
0x180010975  test    rdi, rdi
0x180010978  jz      short loc_180010983
0x18001097a  mov     rcx, rdi; hKey
0x18001097d  call    cs:__imp_RegCloseKey
0x180010983  mov     al, bl
0x180010985  mov     rcx, [rbp+240h+var_30]
0x18001098c  xor     rcx, rsp; StackCookie
0x18001098f  call    __security_check_cookie
0x180010994  add     rsp, 328h
0x18001099b  pop     rdi
0x18001099c  pop     rsi
0x18001099d  pop     rbx
0x18001099e  pop     rbp
0x18001099f  retn
```
