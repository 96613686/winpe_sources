# WalletEncrypter::GetKeyFromRegistry(void)

- ea: `0x18001bc58`
- end: `0x18001bdf8`
- name: `?GetKeyFromRegistry@WalletEncrypter@@AEAAJXZ`
- size: `416`
- prototype: `__int64 __fastcall(WalletEncrypter *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001be00`

## callees

- `0x18000de7c`
- `0x18001108c`
- `0x18001b310`
- `0x18001b378`
- `0x18001bc58`
- `0x18001c1e0`
- `0x180043052`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bcb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bcb6`
- `bcrypt!BCryptImportKey` at `0x18001bdb6`
- `bcrypt!BCryptImportKey` at `0x18001bdb6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bd01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001bd01`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18001bd24`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x18001bd24`

## pseudocode

```c
__int64 __fastcall WalletEncrypter::GetKeyFromRegistry(WalletEncrypter *this)
{
  const unsigned __int16 *v2; // rdx
  signed int LastError; // eax
  unsigned int v4; // ebx
  void *pbInput; // rbx
  size_t v6; // rdi
  const unsigned __int16 *v7; // rdx
  ULONG cbInput; // edi
  ULONG cbKeyObject; // esi
  UCHAR *pbKeyObject; // r14
  void **v11; // rax
  int v12; // eax
  HKEY v14[4]; // [rsp+50h] [rbp-20h] BYREF
  SIZE_T cb; // [rsp+A8h] [rbp+38h] BYREF
  LPMALLOC ppMalloc; // [rsp+B0h] [rbp+40h] BYREF
  LPVOID v17; // [rsp+B8h] [rbp+48h] BYREF

  memset(v14, 0, 24);
  LODWORD(cb) = 0;
  v17 = 0;
  if ( (unsigned int)ATL::CRegKey::Open(v14, HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Wallet", 0x20019u) )
    goto LABEL_2;
  if ( (unsigned int)ATL::CRegKey::QueryBinaryValue((ATL::CRegKey *)v14, v2, 0, (unsigned int *)&cb) )
  {
    v4 = -2143682560;
    goto LABEL_16;
  }
  v17 = CoTaskMemAlloc((unsigned int)cb);
  pbInput = v17;
  if ( !v17 )
  {
    v4 = -2147024882;
    goto LABEL_16;
  }
  v6 = 0;
  ppMalloc = 0;
  if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
  {
    v6 = ((__int64 (__fastcall *)(LPMALLOC, void *))ppMalloc->lpVtbl->GetSize)(ppMalloc, pbInput);
    ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
  }
  memset_0(pbInput, 0, v6);
  if ( (unsigned int)ATL::CRegKey::QueryBinaryValue((ATL::CRegKey *)v14, v7, pbInput, (unsigned int *)&cb) )
  {
LABEL_2:
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v4 = -2143748092;
    }
  }
  else
  {
    cbInput = cb;
    cbKeyObject = *((_DWORD *)this + 2);
    pbKeyObject = (UCHAR *)*((_QWORD *)this + 2);
    v11 = tlx::replace<tlx::handle_traits<void *,long (*)(void *),&long BCryptDestroyKey(void *),0>>((void **)this + 3);
    v12 = BCryptImportKey(
            *(BCRYPT_ALG_HANDLE *)this,
            0,
            L"KeyDataBlob",
            v11,
            pbKeyObject,
            cbKeyObject,
            (PUCHAR)pbInput,
            cbInput,
            0)
        | 0x10000000;
    v4 = 0;
    if ( v12 < 0 )
      v4 = v12;
  }
LABEL_16:
  CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v17);
  ATL::CRegKey::Close(v14);
  return v4;
}

```

## disassembly

```asm
0x18001bc58  mov     [rsp-28h+arg_0], rbx
0x18001bc5d  push    rbp
0x18001bc5e  push    rsi
0x18001bc5f  push    rdi
0x18001bc60  push    r14
0x18001bc62  push    r15
0x18001bc64  mov     rbp, rsp
0x18001bc67  sub     rsp, 70h
0x18001bc6b  mov     r15, rcx
0x18001bc6e  mov     [rbp+var_20], 0
0x18001bc76  lea     rcx, [rbp+var_20]; this
0x18001bc7a  mov     [rbp+var_18], 0
0x18001bc82  mov     r9d, 20019h; unsigned int
0x18001bc88  mov     [rbp+var_10], 0
0x18001bc90  lea     r8, ?sc_szWalletRegKey@WalletEncrypter@@1QBGB; "Software\\Microsoft\\Wallet"
0x18001bc97  mov     dword ptr [rbp+cb], 0
0x18001bc9e  mov     rdx, 0FFFFFFFF80000002h; hKey
0x18001bca5  mov     [rbp+arg_18], 0
0x18001bcad  call    ?Open@CRegKey@ATL@@QEAAJPEAUHKEY__@@PEBGK@Z; ATL::CRegKey::Open(HKEY__ *,ushort const *,ulong)
0x18001bcb2  test    eax, eax
0x18001bcb4  jz      short loc_18001BCE0
0x18001bcb6  call    cs:__imp_GetLastError
0x18001bcbc  mov     ebx, eax
0x18001bcbe  test    eax, eax
0x18001bcc0  jz      short loc_18001BCD6
0x18001bcc2  jle     loc_18001BDD0
0x18001bcc8  movzx   ebx, ax
0x18001bccb  or      ebx, 80070000h
0x18001bcd1  jmp     loc_18001BDD0
0x18001bcd6  mov     ebx, 80390004h
0x18001bcdb  jmp     loc_18001BDD0
0x18001bce0  lea     r9, [rbp+cb]; unsigned int *
0x18001bce4  xor     r8d, r8d; void *
0x18001bce7  lea     rcx, [rbp+var_20]; this
0x18001bceb  call    ?QueryBinaryValue@CRegKey@ATL@@QEAAJPEBGPEAXPEAK@Z; ATL::CRegKey::QueryBinaryValue(ushort const *,void *,ulong *)
0x18001bcf0  test    eax, eax
0x18001bcf2  jz      short loc_18001BCFE
0x18001bcf4  mov     ebx, 803A0000h
0x18001bcf9  jmp     loc_18001BDD0
0x18001bcfe  mov     ecx, dword ptr [rbp+cb]; cb
0x18001bd01  call    cs:__imp_CoTaskMemAlloc
0x18001bd07  mov     [rbp+arg_18], rax
0x18001bd0b  mov     rbx, rax
0x18001bd0e  test    rax, rax
0x18001bd11  jz      loc_18001BDCB
0x18001bd17  xor     edi, edi
0x18001bd19  lea     rdx, [rbp+ppMalloc]; ppMalloc
0x18001bd1d  mov     [rbp+ppMalloc], rdi
0x18001bd21  lea     ecx, [rdi+1]; dwMemContext
0x18001bd24  call    cs:__imp_CoGetMalloc
0x18001bd2a  test    eax, eax
0x18001bd2c  js      short loc_18001BD54
0x18001bd2e  mov     rcx, [rbp+ppMalloc]
0x18001bd32  mov     rdx, rbx
0x18001bd35  mov     rax, [rcx]
0x18001bd38  mov     rax, [rax+30h]
0x18001bd3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd41  mov     rcx, [rbp+ppMalloc]
0x18001bd45  mov     rdi, rax
0x18001bd48  mov     rdx, [rcx]
0x18001bd4b  mov     rax, [rdx+10h]
0x18001bd4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bd54  mov     r8, rdi; Size
0x18001bd57  xor     edx, edx; Val
0x18001bd59  mov     rcx, rbx; void *
0x18001bd5c  call    memset_0
0x18001bd61  lea     r9, [rbp+cb]; unsigned int *
0x18001bd65  mov     r8, rbx; void *
0x18001bd68  lea     rcx, [rbp+var_20]; this
0x18001bd6c  call    ?QueryBinaryValue@CRegKey@ATL@@QEAAJPEBGPEAXPEAK@Z; ATL::CRegKey::QueryBinaryValue(ushort const *,void *,ulong *)
0x18001bd71  test    eax, eax
0x18001bd73  jnz     loc_18001BCB6
0x18001bd79  mov     edi, dword ptr [rbp+cb]
0x18001bd7c  lea     rcx, [r15+18h]
0x18001bd80  mov     esi, [r15+8]
0x18001bd84  mov     r14, [r15+10h]
0x18001bd88  call    ??$replace@U?$handle_traits@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,long (*)(void *),&BCryptDestroyKey(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&BCryptDestroyKey(void *),0>> &)
0x18001bd8d  mov     rcx, [r15]; hAlgorithm
0x18001bd90  lea     r8, aKeydatablob; "KeyDataBlob"
0x18001bd97  mov     [rsp+70h+dwFlags], 0; dwFlags
0x18001bd9f  mov     r9, rax; phKey
0x18001bda2  mov     [rsp+70h+cbInput], edi; cbInput
0x18001bda6  xor     edx, edx; hImportKey
0x18001bda8  mov     [rsp+70h+pbInput], rbx; pbInput
0x18001bdad  mov     [rsp+70h+cbKeyObject], esi; cbKeyObject
0x18001bdb1  mov     [rsp+70h+pbKeyObject], r14; pbKeyObject
0x18001bdb6  call    cs:__imp_BCryptImportKey
0x18001bdbc  or      eax, 10000000h
0x18001bdc1  mov     ebx, 0
0x18001bdc6  cmovl   ebx, eax
0x18001bdc9  jmp     short loc_18001BDD0
0x18001bdcb  mov     ebx, 8007000Eh
0x18001bdd0  lea     rcx, [rbp+arg_18]
0x18001bdd4  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x18001bdd9  lea     rcx, [rbp+var_20]; this
0x18001bddd  call    ?Close@CRegKey@ATL@@QEAAJXZ; ATL::CRegKey::Close(void)
0x18001bde2  mov     eax, ebx
0x18001bde4  mov     rbx, [rsp+70h+arg_0]
0x18001bdec  add     rsp, 70h
0x18001bdf0  pop     r15
0x18001bdf2  pop     r14
0x18001bdf4  pop     rdi
0x18001bdf5  pop     rsi
0x18001bdf6  pop     rbp
0x18001bdf7  retn
```
