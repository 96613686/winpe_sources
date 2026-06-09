# WalletEncrypter::SaveKey(tlx::unique_any<tlx::handle_traits<void *,ulong (*)(void * const &),&wp::detail::_WpCloseVaultHandle(void * const &),0>> &)

- ea: `0x18001c230`
- end: `0x18001c484`
- name: `?SaveKey@WalletEncrypter@@AEAAJAEAV?$unique_any@U?$handle_traits@PEAXP6AKAEBQEAX@Z$1?_WpCloseVaultHandle@detail@wp@@YAK0@Z$0A@@tlx@@@tlx@@@Z`
- size: `596`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001b4d8`
- `0x18001be00`

## callees

- `0x18001b378`
- `0x18001c230`
- `0x18001c48c`
- `0x180043052`
- `0x180043090`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c408`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c408`
- `bcrypt!BCryptExportKey` at `0x18001c329`
- `bcrypt!BCryptExportKey` at `0x18001c3cf`
- `bcrypt!BCryptExportKey` at `0x18001c329`
- `bcrypt!BCryptExportKey` at `0x18001c3cf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c341`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c341`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18001c369`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18001c369`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultAddItem` at `0x18001c3fe`
- `ext-ms-win-security-vaultcli-l1-1-0!VaultAddItem` at `0x18001c3fe`

## pseudocode

```c
__int64 __fastcall WalletEncrypter::SaveKey(__int64 a1, __int64 *a2)
{
  void *v4; // rcx
  NTSTATUS v5; // eax
  unsigned int v6; // edi
  void *v7; // rbx
  size_t v8; // rdi
  NTSTATUS v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rcx
  signed int LastError; // eax
  int v13; // eax
  __int64 v14; // rcx
  __int128 *v15; // rax
  ULONG pcbResult; // [rsp+40h] [rbp-C0h] BYREF
  LPMALLOC ppMalloc; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID v19; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v20; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v21; // [rsp+68h] [rbp-98h]
  _QWORD v22[4]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v23[5]; // [rsp+98h] [rbp-68h] BYREF
  __int128 v24; // [rsp+C0h] [rbp-40h] BYREF
  const unsigned __int16 *v25; // [rsp+D0h] [rbp-30h]
  _QWORD *v26; // [rsp+D8h] [rbp-28h]
  _QWORD *v27; // [rsp+E0h] [rbp-20h]
  __int128 *v28; // [rsp+E8h] [rbp-18h]

  pcbResult = 0;
  memset_0((char *)&v24 + 4, 0, 0x4Cu);
  v4 = *(void **)(a1 + 24);
  v25 = L"Wallet Encryption Schema";
  v20 = 0;
  v22[0] = 1;
  v22[2] = L"WalletEncryptionKey";
  v22[1] = 7;
  v26 = v22;
  v22[3] = 0;
  v23[2] = L"WalletUser";
  v27 = v23;
  v28 = &v20;
  v23[0] = 2;
  v23[1] = 7;
  v23[3] = 0;
  v21 = 0;
  LODWORD(v20) = 3;
  v24 = xmmword_180050F80;
  DWORD2(v20) = 8;
  v19 = 0;
  v5 = BCryptExportKey(v4, 0, L"OpaqueKeyBlob", 0, 0, &pcbResult, 0);
  v6 = v5 | 0x10000000;
  if ( v5 >= 0 )
  {
    v19 = CoTaskMemAlloc(pcbResult);
    v7 = v19;
    if ( v19 )
    {
      ppMalloc = 0;
      v8 = 0;
      if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
      {
        v8 = ((__int64 (__fastcall *)(LPMALLOC, void *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v7);
        ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
      }
      memset_0(v7, 0, v8);
      v9 = BCryptExportKey(*(BCRYPT_KEY_HANDLE *)(a1 + 24), 0, L"OpaqueKeyBlob", (PUCHAR)v7, pcbResult, &pcbResult, 0);
      v6 = v9 | 0x10000000;
      if ( v9 >= 0 )
      {
        v10 = *a2;
        LODWORD(v21) = pcbResult;
        *((_QWORD *)&v21 + 1) = v7;
        if ( (unsigned int)VaultAddItem(v10, &v24, 0, 0, 0) )
        {
          LastError = GetLastError();
          v6 = LastError;
          if ( LastError )
          {
            if ( LastError > 0 )
              v6 = (unsigned __int16)LastError | 0x80070000;
          }
          else
          {
            v6 = -2143748092;
          }
        }
        else
        {
          v13 = WalletEncrypter::SaveKeyExpiration(v11, a2);
          v6 = 0;
          if ( v13 < 0 )
            v6 = v13;
        }
      }
    }
    else
    {
      v6 = -2147024882;
    }
  }
  v14 = 32;
  v15 = &v20;
  do
  {
    *(_BYTE *)v15 = 0;
    v15 = (__int128 *)((char *)v15 + 1);
    --v14;
  }
  while ( v14 );
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v19);
  return v6;
}

```

## disassembly

```asm
0x18001c230  mov     [rsp-8+arg_10], rbx
0x18001c235  push    rbp
0x18001c236  push    rsi
0x18001c237  push    rdi
0x18001c238  push    r14
0x18001c23a  push    r15
0x18001c23c  lea     rbp, [rsp-20h]
0x18001c241  sub     rsp, 120h
0x18001c248  mov     rax, cs:__security_cookie
0x18001c24f  xor     rax, rsp
0x18001c252  mov     [rbp+40h+var_30], rax
0x18001c256  xor     r15d, r15d
0x18001c259  mov     rsi, rdx
0x18001c25c  mov     r14, rcx
0x18001c25f  mov     [rsp+140h+var_100], r15d
0x18001c264  xor     edx, edx; Val
0x18001c266  lea     rcx, [rbp+40h+var_7C]; void *
0x18001c26a  lea     r8d, [r15+4Ch]; Size
0x18001c26e  call    memset_0
0x18001c273  movups  xmm1, cs:xmmword_180050F80
0x18001c27a  mov     rcx, [r14+18h]; hKey
0x18001c27e  lea     rax, ?sc_szWalletEncryptionSchemaName@WalletEncrypter@@1QBGB; "Wallet Encryption Schema"
0x18001c285  mov     [rbp+40h+var_70], rax
0x18001c289  lea     r8, pszBlobType; "OpaqueKeyBlob"
0x18001c290  xorps   xmm0, xmm0
0x18001c293  mov     [rsp+140h+dwFlags], r15d; dwFlags
0x18001c298  movups  [rsp+140h+var_E8], xmm0
0x18001c29d  lea     rax, ?sc_szWalletEncryptionKey@WalletEncrypter@@1QBGB; "WalletEncryptionKey"
0x18001c2a4  mov     [rsp+140h+var_C8], 1
0x18001c2ad  mov     [rbp+40h+var_B8], rax
0x18001c2b1  xor     r9d, r9d; pbOutput
0x18001c2b4  lea     rax, [rsp+140h+var_C8]
0x18001c2b9  mov     [rbp+40h+var_C0], 7
0x18001c2c1  mov     [rbp+40h+var_68], rax
0x18001c2c5  xor     edx, edx; hExportKey
0x18001c2c7  lea     rax, ?sc_szWalletUser@WalletEncrypter@@1QBGB; "WalletUser"
0x18001c2ce  mov     [rbp+40h+var_B0], r15
0x18001c2d2  mov     [rbp+40h+var_98], rax
0x18001c2d6  lea     rax, [rbp+40h+var_A8]
0x18001c2da  mov     [rbp+40h+var_60], rax
0x18001c2de  lea     rax, [rsp+140h+var_E8]
0x18001c2e3  mov     [rbp+40h+var_58], rax
0x18001c2e7  lea     rax, [rsp+140h+var_100]
0x18001c2ec  mov     [rsp+140h+pcbResult], rax; pcbResult
0x18001c2f1  mov     [rsp+140h+cbOutput], r15d; cbOutput
0x18001c2f6  mov     [rbp+40h+var_A8], 2
0x18001c2fe  mov     [rbp+40h+var_A0], 7
0x18001c306  mov     [rbp+40h+var_90], r15
0x18001c30a  movups  [rsp+140h+var_D8], xmm0
0x18001c30f  mov     dword ptr [rsp+140h+var_E8], 3
0x18001c317  movdqu  xmmword ptr [rbp-40h], xmm1
0x18001c31c  mov     dword ptr [rsp+140h+var_E8+8], 8
0x18001c324  mov     [rsp+140h+var_F0], r15
0x18001c329  call    cs:__imp_BCryptExportKey
0x18001c32f  mov     edi, eax
0x18001c331  or      edi, 10000000h
0x18001c337  jl      loc_18001C43F
0x18001c33d  mov     ecx, [rsp+140h+var_100]; cb
0x18001c341  call    cs:__imp_CoTaskMemAlloc
0x18001c347  mov     [rsp+140h+var_F0], rax
0x18001c34c  mov     rbx, rax
0x18001c34f  test    rax, rax
0x18001c352  jz      loc_18001C43A
0x18001c358  lea     rdx, [rsp+140h+ppMalloc]; ppMalloc
0x18001c35d  mov     [rsp+140h+ppMalloc], r15
0x18001c362  lea     ecx, [r15+1]; dwMemContext
0x18001c366  mov     edi, r15d
0x18001c369  call    cs:__imp_CoGetMalloc
0x18001c36f  test    eax, eax
0x18001c371  js      short loc_18001C39B
0x18001c373  mov     rcx, [rsp+140h+ppMalloc]
0x18001c378  mov     rdx, rbx
0x18001c37b  mov     rax, [rcx]
0x18001c37e  mov     rax, [rax+30h]
0x18001c382  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c387  mov     rcx, [rsp+140h+ppMalloc]
0x18001c38c  mov     rdi, rax
0x18001c38f  mov     rdx, [rcx]
0x18001c392  mov     rax, [rdx+10h]
0x18001c396  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c39b  mov     r8, rdi; Size
0x18001c39e  xor     edx, edx; Val
0x18001c3a0  mov     rcx, rbx; void *
0x18001c3a3  call    memset_0
0x18001c3a8  mov     eax, [rsp+140h+var_100]
0x18001c3ac  lea     rcx, [rsp+140h+var_100]
0x18001c3b1  mov     [rsp+140h+dwFlags], r15d; dwFlags
0x18001c3b6  lea     r8, pszBlobType; "OpaqueKeyBlob"
0x18001c3bd  mov     [rsp+140h+pcbResult], rcx; pcbResult
0x18001c3c2  mov     r9, rbx; pbOutput
0x18001c3c5  mov     rcx, [r14+18h]; hKey
0x18001c3c9  xor     edx, edx; hExportKey
0x18001c3cb  mov     [rsp+140h+cbOutput], eax; cbOutput
0x18001c3cf  call    cs:__imp_BCryptExportKey
0x18001c3d5  mov     edi, eax
0x18001c3d7  or      edi, 10000000h
0x18001c3dd  jl      short loc_18001C43F
0x18001c3df  mov     eax, [rsp+140h+var_100]
0x18001c3e3  lea     rdx, [rbp+40h+var_80]
0x18001c3e7  mov     rcx, [rsi]
0x18001c3ea  xor     r9d, r9d
0x18001c3ed  xor     r8d, r8d
0x18001c3f0  mov     dword ptr [rsp+140h+var_D8], eax
0x18001c3f4  mov     qword ptr [rsp+140h+var_D8+8], rbx
0x18001c3f9  mov     [rsp+140h+cbOutput], r15d
0x18001c3fe  call    cs:__imp_VaultAddItem
0x18001c404  test    eax, eax
0x18001c406  jz      short loc_18001C428
0x18001c408  call    cs:__imp_GetLastError
0x18001c40e  mov     edi, eax
0x18001c410  test    eax, eax
0x18001c412  jz      short loc_18001C421
0x18001c414  jle     short loc_18001C43F
0x18001c416  movzx   edi, ax
0x18001c419  or      edi, 80070000h
0x18001c41f  jmp     short loc_18001C43F
0x18001c421  mov     edi, 80390004h
0x18001c426  jmp     short loc_18001C43F
0x18001c428  mov     rdx, rsi
0x18001c42b  call    ?SaveKeyExpiration@WalletEncrypter@@AEBAJAEAV?$unique_any@U?$handle_traits@PEAXP6AKAEBQEAX@Z$1?_WpCloseVaultHandle@detail@wp@@YAK0@Z$0A@@tlx@@@tlx@@@Z; WalletEncrypter::SaveKeyExpiration(tlx::unique_any<tlx::handle_traits<void *,ulong (*)(void * const &),&wp::detail::_WpCloseVaultHandle(void * const &),0>> &)
0x18001c430  test    eax, eax
0x18001c432  mov     edi, r15d
0x18001c435  cmovs   edi, eax
0x18001c438  jmp     short loc_18001C43F
0x18001c43a  mov     edi, 8007000Eh
0x18001c43f  mov     ecx, 20h ; ' '
0x18001c444  lea     rax, [rsp+140h+var_E8]
0x18001c449  mov     [rax], r15b
0x18001c44c  inc     rax
0x18001c44f  sub     rcx, 1
0x18001c453  jnz     short loc_18001C449
0x18001c455  lea     rcx, [rsp+140h+var_F0]
0x18001c45a  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18001c45f  mov     eax, edi
0x18001c461  mov     rcx, [rbp+40h+var_30]
0x18001c465  xor     rcx, rsp; StackCookie
0x18001c468  call    __security_check_cookie
0x18001c46d  mov     rbx, [rsp+140h+arg_10]
0x18001c475  add     rsp, 120h
0x18001c47c  pop     r15
0x18001c47e  pop     r14
0x18001c480  pop     rdi
0x18001c481  pop     rsi
0x18001c482  pop     rbp
0x18001c483  retn
```
