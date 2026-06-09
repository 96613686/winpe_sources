# IkeCheckCertKeyUsage

- ea: `0x18008a794`
- end: `0x18008a9e2`
- name: `IkeCheckCertKeyUsage`
- size: `590`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x1800915e4`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800037c4`
- `0x180003cf0`
- `0x1800061ec`
- `0x180008388`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x18005bce4`
- `0x18008a794`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a831`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a8b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a924`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a831`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a8b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008a924`
- `CRYPT32!CertFindExtension` at `0x18008a7f9`
- `CRYPT32!CertFindExtension` at `0x18008a7f9`
- `CRYPT32!CryptDecodeObject` at `0x18008a91a`
- `CRYPT32!CryptDecodeObject` at `0x18008a970`
- `CRYPT32!CryptDecodeObject` at `0x18008a91a`
- `CRYPT32!CryptDecodeObject` at `0x18008a970`

## string_xrefs

- `0x18008a89e`: `CertFindExtension failed with the following error.             This is OK as it means all Key usages are valid`

## pseudocode

```c
__int64 __fastcall IkeCheckCertKeyUsage(__int64 a1)
{
  PCERT_EXTENSION Extension; // rax
  __int64 v3; // rdx
  __int64 v4; // rcx
  __int64 v5; // r8
  __int64 v6; // r9
  PCERT_EXTENSION v7; // rbx
  __int64 v8; // r14
  __int64 v9; // rsi
  DWORD v10; // edi
  __int64 v11; // rcx
  __int64 TlsPeerAddr; // rbx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  int TlsMmLuid; // eax
  __int64 v18; // rcx
  __int64 v19; // rax
  DWORD v20; // eax
  int v21; // r8d
  int v22; // r9d
  __int64 v23; // rcx
  __int64 LastError; // r8
  const char *v25; // rdx
  void *pvStructInfo; // [rsp+40h] [rbp-49h] BYREF
  DWORD pcbStructInfo; // [rsp+48h] [rbp-41h] BYREF
  DWORD v29; // [rsp+4Ch] [rbp-3Dh] BYREF
  __int64 v30; // [rsp+50h] [rbp-39h] BYREF
  char v31[32]; // [rsp+60h] [rbp-29h] BYREF
  __int64 *v32; // [rsp+80h] [rbp-9h]
  __int64 v33; // [rsp+88h] [rbp-1h]
  char v34[16]; // [rsp+90h] [rbp+7h] BYREF
  const char *v35; // [rsp+A0h] [rbp+17h]
  __int64 v36; // [rsp+A8h] [rbp+1Fh]
  DWORD *v37; // [rsp+B0h] [rbp+27h]
  __int64 v38; // [rsp+B8h] [rbp+2Fh]

  pvStructInfo = 0;
  pcbStructInfo = 0;
  TraceLogHelper("IkeCheckCertKeyUsage", 1);
  Extension = CertFindExtension(
                "2.5.29.15",
                *(_DWORD *)(*(_QWORD *)(a1 + 24) + 192LL),
                *(CERT_EXTENSION **)(*(_QWORD *)(a1 + 24) + 200LL));
  v7 = Extension;
  if ( Extension )
  {
    if ( !CryptDecodeObject(
            1u,
            Extension->pszObjId,
            Extension->Value.pbData,
            Extension->Value.cbData,
            0,
            0,
            &pcbStructInfo) )
      goto LABEL_9;
    v8 = WfpMemAlloc(pcbStructInfo, 0);
    if ( v8 )
      goto LABEL_15;
    if ( CryptDecodeObject(1u, v7->pszObjId, v7->Value.pbData, v7->Value.cbData, 0, pvStructInfo, &pcbStructInfo) )
    {
      if ( *((char *)pvStructInfo + 24) < 0 )
        goto LABEL_15;
      LastError = 13818;
      v25 = "IkeCheckCertKeyUsage";
    }
    else
    {
LABEL_9:
      LastError = GetLastError();
      v25 = "CryptDecodeObject";
    }
    v8 = WfpReportSysErrorAsWinError(v23, v25, LastError, 1);
    goto LABEL_15;
  }
  v8 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v9 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v10 = GetLastError();
    TlsPeerAddr = IkeGetTlsPeerAddr(v11);
    TlsMmLuid = IkeGetTlsMmLuid(v14, v13, v15, v16);
    WPP_SF_iSL(v9, 23, (unsigned int)WPP_867431ae952033dfea5b8d66753a6411_Traceguids, TlsMmLuid, TlsPeerAddr, v10);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v30 = IkeGetTlsMmLuid(v4, v3, v5, v6);
    v32 = &v30;
    v33 = 8;
    v19 = IkeGetTlsPeerAddr(v18);
    tlgCreate1Sz_wchar_t(v34, v19);
    v36 = 111;
    v35 = "CertFindExtension failed with the following error.             This is OK as it means all Key usages are valid";
    v20 = GetLastError();
    v38 = 4;
    v29 = v20;
    v37 = &v29;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (unsigned int)&dword_180173278,
      (unsigned int)&byte_180158417,
      v21,
      v22,
      6,
      (__int64)v31);
  }
LABEL_15:
  WfpMemFree(&pvStructInfo);
  TraceLogHelper("IkeCheckCertKeyUsage", 0);
  return IkeReturnError(v8, "IkeCheckCertKeyUsage");
}

```

## disassembly

```asm
0x18008a794  mov     [rsp-8+arg_8], rbx
0x18008a799  mov     [rsp-8+arg_10], rsi
0x18008a79e  push    rbp
0x18008a79f  push    rdi
0x18008a7a0  push    r14
0x18008a7a2  lea     rbp, [rsp-47h]
0x18008a7a7  sub     rsp, 0D0h
0x18008a7ae  mov     rax, cs:__security_cookie
0x18008a7b5  xor     rax, rsp
0x18008a7b8  mov     [rbp+57h+var_20], rax
0x18008a7bc  mov     rbx, rcx
0x18008a7bf  mov     [rbp+57h+var_A0], 0
0x18008a7c7  mov     esi, 1
0x18008a7cc  mov     [rbp+57h+var_98], 0
0x18008a7d3  mov     edx, esi
0x18008a7d5  lea     rcx, aIkecheckcertke; "IkeCheckCertKeyUsage"
0x18008a7dc  call    TraceLogHelper
0x18008a7e1  mov     rdx, [rbx+18h]
0x18008a7e5  lea     rcx, a252915; "2.5.29.15"
0x18008a7ec  mov     r8, [rdx+0C8h]; rgExtensions
0x18008a7f3  mov     edx, [rdx+0C0h]; cExtensions
0x18008a7f9  call    cs:__imp_CertFindExtension
0x18008a7ff  mov     rbx, rax
0x18008a802  test    rax, rax
0x18008a805  jnz     loc_18008A8F3
0x18008a80b  xor     r14d, r14d
0x18008a80e  mov     rsi, cs:WPP_GLOBAL_Control
0x18008a815  lea     rax, WPP_GLOBAL_Control
0x18008a81c  cmp     rsi, rax
0x18008a81f  jz      short loc_18008A865
0x18008a821  cmp     byte ptr [rsi+19h], 4
0x18008a825  jb      short loc_18008A865
0x18008a827  test    byte ptr [rsi+1Ch], 10h
0x18008a82b  jz      short loc_18008A865
0x18008a82d  mov     rsi, [rsi+10h]
0x18008a831  call    cs:__imp_GetLastError
0x18008a837  mov     edi, eax
0x18008a839  call    IkeGetTlsPeerAddr
0x18008a83e  mov     rbx, rax
0x18008a841  call    IkeGetTlsMmLuid
0x18008a846  mov     r9, rax
0x18008a849  mov     dword ptr [rsp+0E0h+pvStructInfo], edi
0x18008a84d  lea     edx, [r14+17h]
0x18008a851  mov     qword ptr [rsp+0E0h+dwFlags], rbx
0x18008a856  lea     r8, WPP_867431ae952033dfea5b8d66753a6411_Traceguids
0x18008a85d  mov     rcx, rsi
0x18008a860  call    WPP_SF_iSL
0x18008a865  mov     eax, cs:dword_180173278
0x18008a86b  cmp     eax, 4
0x18008a86e  jbe     loc_18008A998
0x18008a874  call    IkeGetTlsMmLuid
0x18008a879  mov     [rbp+57h+var_90], rax
0x18008a87d  lea     rax, [rbp+57h+var_90]
0x18008a881  mov     [rbp+57h+var_60], rax
0x18008a885  mov     [rbp+57h+var_58], 8
0x18008a88d  call    IkeGetTlsPeerAddr
0x18008a892  mov     rdx, rax
0x18008a895  lea     rcx, [rbp+57h+var_50]
0x18008a899  call    _tlgCreate1Sz_wchar_t
0x18008a89e  lea     rcx, aCertfindextens_0; "CertFindExtension failed with the follo"...
0x18008a8a5  mov     [rbp+57h+var_38], 6Fh ; 'o'
0x18008a8ad  mov     [rbp+57h+var_40], rcx
0x18008a8b1  call    cs:__imp_GetLastError
0x18008a8b7  lea     rdx, byte_180158417
0x18008a8be  mov     [rbp+57h+var_28], 4
0x18008a8c6  mov     [rbp+57h+var_94], eax
0x18008a8c9  lea     rcx, dword_180173278
0x18008a8d0  lea     rax, [rbp+57h+var_94]
0x18008a8d4  mov     [rbp+57h+var_30], rax
0x18008a8d8  lea     rax, [rbp+57h+var_80]
0x18008a8dc  mov     [rsp+0E0h+pvStructInfo], rax
0x18008a8e1  mov     [rsp+0E0h+dwFlags], 6
0x18008a8e9  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x18008a8ee  jmp     loc_18008A998
0x18008a8f3  mov     r9d, [rbx+10h]; cbEncoded
0x18008a8f7  lea     rax, [rbp+57h+var_98]
0x18008a8fb  mov     r8, [rbx+18h]; pbEncoded
0x18008a8ff  mov     ecx, esi; dwCertEncodingType
0x18008a901  mov     rdx, [rbx]; lpszStructType
0x18008a904  mov     [rsp+0E0h+pcbStructInfo], rax; pcbStructInfo
0x18008a909  mov     [rsp+0E0h+pvStructInfo], 0; pvStructInfo
0x18008a912  mov     [rsp+0E0h+dwFlags], 0; dwFlags
0x18008a91a  call    cs:__imp_CryptDecodeObject
0x18008a920  test    eax, eax
0x18008a922  jnz     short loc_18008A936
0x18008a924  call    cs:__imp_GetLastError
0x18008a92a  mov     r8d, eax
0x18008a92d  lea     rdx, aCryptdecodeobj_1; "CryptDecodeObject"
0x18008a934  jmp     short loc_18008A98D
0x18008a936  mov     ecx, [rbp+57h+var_98]; dwBytes
0x18008a939  lea     r8, [rbp+57h+var_A0]
0x18008a93d  xor     edx, edx; dwFlags
0x18008a93f  call    WfpMemAlloc
0x18008a944  mov     r14, rax
0x18008a947  test    rax, rax
0x18008a94a  jnz     short loc_18008A998
0x18008a94c  mov     rdi, [rbp+57h+var_A0]
0x18008a950  lea     rax, [rbp+57h+var_98]
0x18008a954  mov     r9d, [rbx+10h]; cbEncoded
0x18008a958  mov     ecx, esi; dwCertEncodingType
0x18008a95a  mov     r8, [rbx+18h]; pbEncoded
0x18008a95e  mov     rdx, [rbx]; lpszStructType
0x18008a961  mov     [rsp+0E0h+pcbStructInfo], rax; pcbStructInfo
0x18008a966  mov     [rsp+0E0h+pvStructInfo], rdi; pvStructInfo
0x18008a96b  mov     [rsp+0E0h+dwFlags], r14d; dwFlags
0x18008a970  call    cs:__imp_CryptDecodeObject
0x18008a976  test    eax, eax
0x18008a978  jz      short loc_18008A924
0x18008a97a  test    byte ptr [rdi+18h], 80h
0x18008a97e  jnz     short loc_18008A998
0x18008a980  mov     r8d, 35FAh
0x18008a986  lea     rdx, aIkecheckcertke; "IkeCheckCertKeyUsage"
0x18008a98d  mov     r9d, esi
0x18008a990  call    WfpReportSysErrorAsWinError
0x18008a995  mov     r14, rax
0x18008a998  lea     rcx, [rbp+57h+var_A0]
0x18008a99c  call    WfpMemFree
0x18008a9a1  xor     edx, edx
0x18008a9a3  lea     rcx, aIkecheckcertke; "IkeCheckCertKeyUsage"
0x18008a9aa  call    TraceLogHelper
0x18008a9af  lea     rdx, aIkecheckcertke; "IkeCheckCertKeyUsage"
0x18008a9b6  mov     rcx, r14
0x18008a9b9  call    IkeReturnError
0x18008a9be  mov     rcx, [rbp+57h+var_20]
0x18008a9c2  xor     rcx, rsp; StackCookie
0x18008a9c5  call    __security_check_cookie
0x18008a9ca  lea     r11, [rsp+0E0h+var_10]
0x18008a9d2  mov     rbx, [r11+28h]
0x18008a9d6  mov     rsi, [r11+30h]
0x18008a9da  mov     rsp, r11
0x18008a9dd  pop     r14
0x18008a9df  pop     rdi
0x18008a9e0  pop     rbp
0x18008a9e1  retn
```
