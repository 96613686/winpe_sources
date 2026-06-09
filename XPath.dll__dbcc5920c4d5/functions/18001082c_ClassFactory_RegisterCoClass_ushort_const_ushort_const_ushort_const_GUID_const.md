# ClassFactory::RegisterCoClass(ushort const *,ushort const *,ushort const *,_GUID const *)

- ea: `0x18001082c`
- end: `0x180010b83`
- name: `?RegisterCoClass@ClassFactory@@CAJPEBG00PEBU_GUID@@@Z`
- size: `855`
- prototype: `__int64 __fastcall(const WCHAR *lpData, BYTE *, BYTE *, UUID *Uuid)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800031d0`

## callees

- `0x18000a640`
- `0x18000a690`
- `0x1800104b0`
- `0x18001082c`
- `0x180011840`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x180010b49`
- `RPCRT4!RpcStringFreeW` at `0x180010b49`
- `RPCRT4!UuidToStringW` at `0x1800108c3`
- `RPCRT4!UuidToStringW` at `0x1800108c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010a12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010b08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010b1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010b32`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010a12`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010b08`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010b1d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010b32`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800109ff`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800109ff`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010985`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800109d0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010a62`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010ab6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010aea`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010985`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800109d0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010a62`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010ab6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010aea`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180010930`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800109a0`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180010a2a`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180010a81`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180010930`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x1800109a0`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180010a2a`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyW` at `0x180010a81`

## string_xrefs

- `0x180010ad8`: `ThreadingModel`
- `0x180010999`: `CLSID`
- `0x1800109f1`: `CLSID`

## pseudocode

```c
__int64 __fastcall ClassFactory::RegisterCoClass(const WCHAR *lpData, BYTE *a2, BYTE *a3, UUID *Uuid)
{
  const unsigned __int16 *v7; // rdx
  int v8; // ebx
  __int64 v9; // r8
  LSTATUS v10; // eax
  bool v11; // cc
  __int64 v12; // rdi
  __int64 v13; // rax
  const WCHAR *v14; // rsi
  __int64 v15; // rax
  HKEY hKey; // [rsp+30h] [rbp-D0h] BYREF
  HKEY v18; // [rsp+38h] [rbp-C8h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-C0h] BYREF
  RPC_WSTR StringUuid; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v21; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[4]; // [rsp+58h] [rbp-A8h] BYREF
  int v23; // [rsp+5Ch] [rbp-A4h]
  LPCWSTR lpSubKey; // [rsp+60h] [rbp-A0h]
  int v25; // [rsp+68h] [rbp-98h]
  __int16 v26; // [rsp+70h] [rbp-90h] BYREF

  v23 = 512;
  phkResult = 0;
  hKey = 0;
  v21 = 0;
  v18 = 0;
  StringUuid = 0;
  v22[2] = 0;
  lpSubKey = (LPCWSTR)&v26;
  v25 = 0;
  v26 = 0;
  if ( lpData && a2 && a3 )
  {
    v8 = UuidToStringW(Uuid, &StringUuid);
    if ( !v8 )
    {
      v8 = STRU::Copy((STRU *)v22, v7, v9);
      if ( v8 >= 0 )
      {
        v8 = STRU::Append((STRU *)v22, StringUuid, 0);
        if ( v8 >= 0 )
        {
          v8 = STRU::Append((STRU *)v22, L"}", 0);
          if ( v8 >= 0 )
          {
            v10 = RegCreateKeyW(HKEY_CLASSES_ROOT, lpData, &phkResult);
            v11 = v10 <= 0;
            if ( v10 )
              goto LABEL_9;
            v12 = -1;
            v13 = -1;
            do
              ++v13;
            while ( *(_WORD *)&a2[2 * v13] );
            v10 = RegSetValueExW(phkResult, 0, 0, 1u, a2, 2 * v13 + 2);
            v11 = v10 <= 0;
            if ( v10 )
              goto LABEL_9;
            v10 = RegCreateKeyW(phkResult, L"CLSID", &hKey);
            v11 = v10 <= 0;
            if ( v10 )
              goto LABEL_9;
            v14 = lpSubKey;
            v10 = RegSetValueExW(hKey, 0, 0, 1u, (const BYTE *)lpSubKey, 2 * v25 + 2);
            v11 = v10 <= 0;
            if ( v10 )
              goto LABEL_9;
            v10 = RegOpenKeyExW(HKEY_CLASSES_ROOT, L"CLSID", 0, 0xF003Fu, &v21);
            v11 = v10 <= 0;
            if ( v10 )
              goto LABEL_9;
            RegCloseKey(hKey);
            hKey = 0;
            v10 = RegCreateKeyW(v21, v14, &hKey);
            v11 = v10 <= 0;
            if ( v10 )
              goto LABEL_9;
            v15 = -1;
            do
              ++v15;
            while ( lpData[v15] );
            v10 = RegSetValueExW(hKey, 0, 0, 1u, (const BYTE *)lpData, 2 * v15 + 2);
            v11 = v10 <= 0;
            if ( v10 )
              goto LABEL_9;
            v10 = RegCreateKeyW(hKey, L"InProcServer32", &v18);
            v11 = v10 <= 0;
            if ( v10 )
              goto LABEL_9;
            do
              ++v12;
            while ( *(_WORD *)&a3[2 * v12] );
            v10 = RegSetValueExW(v18, 0, 0, 1u, a3, 2 * v12 + 2);
            v11 = v10 <= 0;
            if ( v10 || (v10 = RegSetValueExW(v18, L"ThreadingModel", 0, 1u, L"Both", 0xAu), v11 = v10 <= 0, v10) )
            {
LABEL_9:
              if ( v11 )
                v8 = v10;
              else
                v8 = (unsigned __int16)v10 | 0x80070000;
            }
          }
        }
      }
    }
  }
  else
  {
    v8 = -2147024809;
  }
  if ( v18 )
  {
    RegCloseKey(v18);
    v18 = 0;
  }
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( StringUuid )
  {
    RpcStringFreeW(&StringUuid);
    StringUuid = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v22);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001082c  push    rbp
0x18001082e  push    rbx
0x18001082f  push    rsi
0x180010830  push    rdi
0x180010831  push    r12
0x180010833  push    r13
0x180010835  push    r14
0x180010837  push    r15
0x180010839  lea     rbp, [rsp-188h]
0x180010841  sub     rsp, 288h
0x180010848  mov     rax, cs:__security_cookie
0x18001084f  xor     rax, rsp
0x180010852  mov     [rbp+1C0h+var_50], rax
0x180010859  xor     r12d, r12d
0x18001085c  mov     [rsp+2C0h+var_264], 200h
0x180010864  mov     [rsp+2C0h+phkResult], r12
0x180010869  lea     rax, [rsp+2C0h+var_250]
0x18001086e  mov     [rsp+2C0h+hKey], r12
0x180010873  mov     r15, r8
0x180010876  mov     [rsp+2C0h+var_270], r12
0x18001087b  mov     rsi, rdx
0x18001087e  mov     [rsp+2C0h+var_288], r12
0x180010883  mov     r14, rcx
0x180010886  mov     [rsp+2C0h+StringUuid], r12
0x18001088b  mov     [rsp+2C0h+var_266], r12b
0x180010890  mov     [rsp+2C0h+lpSubKey], rax
0x180010895  mov     [rsp+2C0h+var_258], r12d
0x18001089a  mov     [rsp+2C0h+var_250], r12w
0x1800108a0  test    rcx, rcx
0x1800108a3  jz      loc_180010AF9
0x1800108a9  test    rdx, rdx
0x1800108ac  jz      loc_180010AF9
0x1800108b2  test    r8, r8
0x1800108b5  jz      loc_180010AF9
0x1800108bb  lea     rdx, [rsp+2C0h+StringUuid]; StringUuid
0x1800108c0  mov     rcx, r9; Uuid
0x1800108c3  call    cs:__imp_UuidToStringW
0x1800108c9  mov     ebx, eax
0x1800108cb  test    eax, eax
0x1800108cd  jnz     loc_180010AFE
0x1800108d3  lea     rcx, [rsp+2C0h+var_268]; this
0x1800108d8  call    ?Copy@STRU@@QEAAJPEBGKK@Z; STRU::Copy(ushort const *,ulong,ulong)
0x1800108dd  mov     ebx, eax
0x1800108df  test    eax, eax
0x1800108e1  js      loc_180010AFE
0x1800108e7  mov     rdx, [rsp+2C0h+StringUuid]; unsigned __int16 *
0x1800108ec  lea     rcx, [rsp+2C0h+var_268]; this
0x1800108f1  xor     r8d, r8d; unsigned int
0x1800108f4  call    ?Append@STRU@@QEAAJPEBGKK@Z; STRU::Append(ushort const *,ulong,ulong)
0x1800108f9  mov     ebx, eax
0x1800108fb  test    eax, eax
0x1800108fd  js      loc_180010AFE
0x180010903  xor     r8d, r8d; unsigned int
0x180010906  lea     rdx, asc_18001726C; "}"
0x18001090d  lea     rcx, [rsp+2C0h+var_268]; this
0x180010912  call    ?Append@STRU@@QEAAJPEBGKK@Z; STRU::Append(ushort const *,ulong,ulong)
0x180010917  mov     ebx, eax
0x180010919  test    eax, eax
0x18001091b  js      loc_180010AFE
0x180010921  lea     r8, [rsp+2C0h+phkResult]; phkResult
0x180010926  mov     rdx, r14; lpSubKey
0x180010929  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180010930  call    cs:__imp_RegCreateKeyW
0x180010936  test    eax, eax
0x180010938  jz      short loc_180010951
0x18001093a  jg      short loc_180010943
0x18001093c  mov     ebx, eax
0x18001093e  jmp     loc_180010AFE
0x180010943  movzx   ebx, ax
0x180010946  or      ebx, 80070000h
0x18001094c  jmp     loc_180010AFE
0x180010951  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180010955  mov     rax, rdi
0x180010958  inc     rax
0x18001095b  cmp     [rsi+rax*2], r12w
0x180010960  jnz     short loc_180010958
0x180010962  mov     rcx, [rsp+2C0h+phkResult]; hKey
0x180010967  lea     eax, ds:2[rax*2]
0x18001096e  mov     [rsp+2C0h+cbData], eax; cbData
0x180010972  mov     r13d, 1
0x180010978  mov     r9d, r13d; dwType
0x18001097b  mov     [rsp+2C0h+lpData], rsi; lpData
0x180010980  xor     r8d, r8d; Reserved
0x180010983  xor     edx, edx; lpValueName
0x180010985  call    cs:__imp_RegSetValueExW
0x18001098b  test    eax, eax
0x18001098d  jnz     short loc_18001093A
0x18001098f  mov     rcx, [rsp+2C0h+phkResult]; hKey
0x180010994  lea     r8, [rsp+2C0h+hKey]; phkResult
0x180010999  lea     rdx, SubKey; "CLSID"
0x1800109a0  call    cs:__imp_RegCreateKeyW
0x1800109a6  test    eax, eax
0x1800109a8  jnz     short loc_18001093A
0x1800109aa  mov     eax, [rsp+2C0h+var_258]
0x1800109ae  mov     r9d, r13d; dwType
0x1800109b1  mov     rsi, [rsp+2C0h+lpSubKey]
0x1800109b6  xor     r8d, r8d; Reserved
0x1800109b9  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800109be  xor     edx, edx; lpValueName
0x1800109c0  lea     eax, ds:2[rax*2]
0x1800109c7  mov     [rsp+2C0h+cbData], eax; cbData
0x1800109cb  mov     [rsp+2C0h+lpData], rsi; lpData
0x1800109d0  call    cs:__imp_RegSetValueExW
0x1800109d6  test    eax, eax
0x1800109d8  jnz     loc_18001093A
0x1800109de  lea     rax, [rsp+2C0h+var_270]
0x1800109e3  mov     r9d, 0F003Fh; samDesired
0x1800109e9  xor     r8d, r8d; ulOptions
0x1800109ec  mov     [rsp+2C0h+lpData], rax; phkResult
0x1800109f1  lea     rdx, SubKey; "CLSID"
0x1800109f8  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800109ff  call    cs:__imp_RegOpenKeyExW
0x180010a05  test    eax, eax
0x180010a07  jnz     loc_18001093A
0x180010a0d  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180010a12  call    cs:__imp_RegCloseKey
0x180010a18  mov     rcx, [rsp+2C0h+var_270]; hKey
0x180010a1d  lea     r8, [rsp+2C0h+hKey]; phkResult
0x180010a22  mov     rdx, rsi; lpSubKey
0x180010a25  mov     [rsp+2C0h+hKey], r12
0x180010a2a  call    cs:__imp_RegCreateKeyW
0x180010a30  test    eax, eax
0x180010a32  jnz     loc_18001093A
0x180010a38  mov     rax, rdi
0x180010a3b  inc     rax
0x180010a3e  cmp     [r14+rax*2], r12w
0x180010a43  jnz     short loc_180010A3B
0x180010a45  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180010a4a  lea     eax, ds:2[rax*2]
0x180010a51  mov     [rsp+2C0h+cbData], eax; cbData
0x180010a55  mov     r9d, r13d; dwType
0x180010a58  xor     r8d, r8d; Reserved
0x180010a5b  mov     [rsp+2C0h+lpData], r14; lpData
0x180010a60  xor     edx, edx; lpValueName
0x180010a62  call    cs:__imp_RegSetValueExW
0x180010a68  test    eax, eax
0x180010a6a  jnz     loc_18001093A
0x180010a70  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180010a75  lea     r8, [rsp+2C0h+var_288]; phkResult
0x180010a7a  lea     rdx, aInprocserver32; "InProcServer32"
0x180010a81  call    cs:__imp_RegCreateKeyW
0x180010a87  test    eax, eax
0x180010a89  jnz     loc_18001093A
0x180010a8f  inc     rdi
0x180010a92  cmp     [r15+rdi*2], r12w
0x180010a97  jnz     short loc_180010A8F
0x180010a99  mov     rcx, [rsp+2C0h+var_288]; hKey
0x180010a9e  lea     eax, ds:2[rdi*2]
0x180010aa5  mov     [rsp+2C0h+cbData], eax; cbData
0x180010aa9  mov     r9d, r13d; dwType
0x180010aac  xor     r8d, r8d; Reserved
0x180010aaf  mov     [rsp+2C0h+lpData], r15; lpData
0x180010ab4  xor     edx, edx; lpValueName
0x180010ab6  call    cs:__imp_RegSetValueExW
0x180010abc  test    eax, eax
0x180010abe  jnz     loc_18001093A
0x180010ac4  mov     rcx, [rsp+2C0h+var_288]; hKey
0x180010ac9  lea     rax, Data; "Both"
0x180010ad0  mov     [rsp+2C0h+cbData], 0Ah; cbData
0x180010ad8  lea     rdx, ValueName; "ThreadingModel"
0x180010adf  mov     r9d, r13d; dwType
0x180010ae2  mov     [rsp+2C0h+lpData], rax; lpData
0x180010ae7  xor     r8d, r8d; Reserved
0x180010aea  call    cs:__imp_RegSetValueExW
0x180010af0  test    eax, eax
0x180010af2  jz      short loc_180010AFE
0x180010af4  jmp     loc_18001093A
0x180010af9  mov     ebx, 80070057h
0x180010afe  mov     rcx, [rsp+2C0h+var_288]; hKey
0x180010b03  test    rcx, rcx
0x180010b06  jz      short loc_180010B13
0x180010b08  call    cs:__imp_RegCloseKey
0x180010b0e  mov     [rsp+2C0h+var_288], r12
0x180010b13  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180010b18  test    rcx, rcx
0x180010b1b  jz      short loc_180010B28
0x180010b1d  call    cs:__imp_RegCloseKey
0x180010b23  mov     [rsp+2C0h+hKey], r12
0x180010b28  mov     rcx, [rsp+2C0h+phkResult]; hKey
0x180010b2d  test    rcx, rcx
0x180010b30  jz      short loc_180010B3D
0x180010b32  call    cs:__imp_RegCloseKey
0x180010b38  mov     [rsp+2C0h+phkResult], r12
0x180010b3d  cmp     [rsp+2C0h+StringUuid], r12
0x180010b42  jz      short loc_180010B54
0x180010b44  lea     rcx, [rsp+2C0h+StringUuid]; String
0x180010b49  call    cs:__imp_RpcStringFreeW
0x180010b4f  mov     [rsp+2C0h+StringUuid], r12
0x180010b54  lea     rcx, [rsp+2C0h+var_268]; this
0x180010b59  call    ??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180010b5e  mov     eax, ebx
0x180010b60  mov     rcx, [rbp+1C0h+var_50]
0x180010b67  xor     rcx, rsp; StackCookie
0x180010b6a  call    __security_check_cookie
0x180010b6f  add     rsp, 288h
0x180010b76  pop     r15
0x180010b78  pop     r14
0x180010b7a  pop     r13
0x180010b7c  pop     r12
0x180010b7e  pop     rdi
0x180010b7f  pop     rsi
0x180010b80  pop     rbx
0x180010b81  pop     rbp
0x180010b82  retn
```
