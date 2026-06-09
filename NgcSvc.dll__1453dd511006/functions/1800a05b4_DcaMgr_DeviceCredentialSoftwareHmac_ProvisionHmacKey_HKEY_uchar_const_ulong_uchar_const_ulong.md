# DcaMgr::DeviceCredentialSoftwareHmac::ProvisionHmacKey(HKEY__ *,uchar const *,ulong,uchar const *,ulong)

- ea: `0x1800a05b4`
- end: `0x1800a0882`
- name: `?ProvisionHmacKey@DeviceCredentialSoftwareHmac@DcaMgr@@SAJPEAUHKEY__@@PEBEK1K@Z`
- size: `718`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, const unsigned __int8 *@<rdx>, unsigned int@<r8d>, const unsigned __int8 *@<r9>, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18004fe40`

## callees

- `0x18000782c`
- `0x18004826c`
- `0x180048304`
- `0x180050b30`
- `0x1800527ac`
- `0x180069b58`
- `0x180069c28`
- `0x1800a05b4`
- `0x1800a5a08`
- `0x1800a6408`
- `0x1800a66a8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a07f0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a0839`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a07f0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a0839`
- `bcrypt!BCryptGenRandom` at `0x1800a061c`
- `bcrypt!BCryptGenRandom` at `0x1800a061c`

## string_xrefs

- `0x1800a05f6`: `onecore\ds\security\devicecredential\service\lib\devicecredentialhmac.cpp`
- `0x1800a062d`: `onecore\ds\security\devicecredential\service\lib\devicecredentialhmac.cpp`
- `0x1800a06a7`: `onecore\ds\security\devicecredential\service\lib\devicecredentialhmac.cpp`
- `0x1800a0729`: `onecore\ds\security\devicecredential\service\lib\devicecredentialhmac.cpp`
- `0x1800a07ae`: `onecore\ds\security\devicecredential\service\lib\devicecredentialhmac.cpp`
- `0x1800a07ff`: `onecore\ds\security\devicecredential\service\lib\devicecredentialhmac.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DcaMgr::DeviceCredentialSoftwareHmac::ProvisionHmacKey(
        HKEY hKey,
        const unsigned __int8 *a2,
        unsigned int a3,
        const unsigned __int8 *a4)
{
  int Hmac; // edi
  NTSTATUS v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  int v13; // ecx
  __int64 v14; // rcx
  __int64 v15; // r8
  unsigned int v16; // eax
  __int64 v17; // rdx
  int lpData; // [rsp+20h] [rbp-41h]
  int lpDataa; // [rsp+20h] [rbp-41h]
  unsigned int lpDatab; // [rsp+20h] [rbp-41h]
  DWORD cbData; // [rsp+50h] [rbp-11h] BYREF
  DWORD v23; // [rsp+54h] [rbp-Dh]
  __int64 v24; // [rsp+58h] [rbp-9h] BYREF
  BYTE *v25; // [rsp+60h] [rbp-1h] BYREF
  BYTE *v26; // [rsp+68h] [rbp+7h] BYREF
  PUCHAR pbBuffer; // [rsp+70h] [rbp+Fh] BYREF
  BYTE **v28; // [rsp+78h] [rbp+17h] BYREF
  __int64 v29; // [rsp+80h] [rbp+1Fh] BYREF
  char v30; // [rsp+88h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+57h]

  wil::make_unique_hlocal_secure_nothrow<unsigned char [0]>(&pbBuffer, 0x20u);
  if ( pbBuffer )
  {
    v8 = BCryptGenRandom(0, pbBuffer, 0x20u, 2u);
    if ( v8 >= 0 )
    {
      v24 = 0;
      cbData = 0;
      v28 = (BYTE **)&v24;
      v29 = 0;
      v30 = 1;
      Hmac = GenerateHmac(v9, a2, a3, pbBuffer);
      wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&v28);
      if ( Hmac >= 0 )
      {
        MicrosoftTelemetryAssertTriggeredNoArgs(v11, v10, v12);
        v25 = 0;
        cbData = 0;
        v28 = &v25;
        v29 = 0;
        v30 = 1;
        LOBYTE(v13) = 1;
        Hmac = DpapiProtectUnprotect(v13, (_DWORD)pbBuffer, 32, (unsigned int)&v29, (__int64)&cbData);
        wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&v28);
        if ( Hmac >= 0 )
        {
          v26 = 0;
          v23 = 0;
          v28 = &v26;
          v29 = 0;
          v30 = 1;
          LOBYTE(v14) = 1;
          Hmac = AesEncryptDecrypt(v14, v24, v15, v24 + 16);
          wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&v28);
          if ( Hmac >= 0 )
          {
            v16 = RegSetValueExW(hKey, L"NonceForDeviceKey", 0, 3u, v25, cbData);
            if ( v16 )
            {
              v17 = 594;
            }
            else
            {
              v16 = RegSetValueExW(hKey, L"EncryptedPrivateKey", 0, 3u, v26, v23);
              if ( !v16 )
              {
                wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v26);
                wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v25);
                wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v24);
                Hmac = 0;
                goto LABEL_20;
              }
              v17 = 602;
            }
            Hmac = wil::details::in1diag3::Return_Win32(
                     retaddr,
                     (void *)v17,
                     (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialhmac.cpp",
                     (const char *)v16,
                     lpDatab);
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x24A,
              (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialhmac.cpp",
              (const char *)(unsigned int)Hmac,
              lpDataa);
          }
          wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v26);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x23C,
            (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialhmac.cpp",
            (const char *)(unsigned int)Hmac,
            lpDataa);
        }
        wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v25);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x231,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialhmac.cpp",
          (const char *)(unsigned int)Hmac,
          32);
      }
      wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&v24);
    }
    else
    {
      Hmac = wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x225,
               (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialhmac.cpp",
               (const char *)(unsigned int)v8,
               lpData);
    }
  }
  else
  {
    Hmac = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x220,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialhmac.cpp",
      (const char *)0x8007000ELL,
      lpData);
  }
LABEL_20:
  wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&pbBuffer);
  return (unsigned int)Hmac;
}

```

## disassembly

```asm
0x1800a05b4  push    rbp
0x1800a05b6  push    rsi
0x1800a05b7  push    rdi
0x1800a05b8  push    r14
0x1800a05ba  push    r15
0x1800a05bc  lea     rbp, [rsp-2Fh]
0x1800a05c1  sub     rsp, 90h
0x1800a05c8  mov     r15, r9
0x1800a05cb  mov     edi, r8d
0x1800a05ce  mov     r14, rdx
0x1800a05d1  mov     rsi, rcx
0x1800a05d4  mov     edx, 20h ; ' '
0x1800a05d9  lea     rcx, [rbp+4Fh+pbBuffer]
0x1800a05dd  call    ??$make_unique_hlocal_secure_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_secure_nothrow<uchar [0]>(unsigned __int64)
0x1800a05e2  nop
0x1800a05e3  cmp     [rbp+4Fh+pbBuffer], 0
0x1800a05e8  jnz     short loc_1800A060C
0x1800a05ea  mov     rcx, [rbp+57h]; this
0x1800a05ee  mov     edi, 8007000Eh
0x1800a05f3  mov     r9d, edi; char *
0x1800a05f6  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\devicecredential"...
0x1800a05fd  mov     edx, 220h; void *
0x1800a0602  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0607  jmp     loc_1800A0868
0x1800a060c  mov     r9d, 2; dwFlags
0x1800a0612  lea     r8d, [r9+1Eh]; cbBuffer
0x1800a0616  mov     rdx, [rbp+4Fh+pbBuffer]; pbBuffer
0x1800a061a  xor     ecx, ecx; hAlgorithm
0x1800a061c  call    cs:__imp_BCryptGenRandom
0x1800a0622  test    eax, eax
0x1800a0624  jns     short loc_1800A0645
0x1800a0626  mov     rcx, [rbp+57h]; this
0x1800a062a  mov     r9d, eax; char *
0x1800a062d  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\devicecredential"...
0x1800a0634  mov     edx, 225h; void *
0x1800a0639  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800a063e  mov     edi, eax
0x1800a0640  jmp     loc_1800A0868
0x1800a0645  mov     [rbp+4Fh+var_58], 0
0x1800a064d  mov     [rbp+4Fh+var_60], 0
0x1800a0654  lea     rax, [rbp+4Fh+var_58]
0x1800a0658  mov     [rbp+4Fh+var_38], rax
0x1800a065c  mov     [rbp+4Fh+var_30], 0
0x1800a0664  mov     [rbp+4Fh+var_28], 1
0x1800a0668  lea     rax, [rbp+4Fh+var_60]
0x1800a066c  mov     [rsp+0B0h+var_80], rax
0x1800a0671  lea     rax, [rbp+4Fh+var_30]
0x1800a0675  mov     qword ptr [rsp+0B0h+cbData], rax
0x1800a067a  mov     dword ptr [rsp+0B0h+lpData], 20h ; ' '; int
0x1800a0682  mov     r9, [rbp+4Fh+pbBuffer]
0x1800a0686  mov     r8d, edi
0x1800a0689  mov     rdx, r14
0x1800a068c  call    GenerateHmac
0x1800a0691  mov     edi, eax
0x1800a0693  lea     rcx, [rbp+4Fh+var_38]
0x1800a0697  call    ??1?$out_param_t@V?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>(void)
0x1800a069c  test    edi, edi
0x1800a069e  jns     short loc_1800A06C7
0x1800a06a0  mov     rcx, [rbp+57h]; this
0x1800a06a4  mov     r9d, edi; char *
0x1800a06a7  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\devicecredential"...
0x1800a06ae  mov     edx, 231h; void *
0x1800a06b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a06b8  nop
0x1800a06b9  lea     rcx, [rbp+4Fh+var_58]
0x1800a06bd  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a06c2  jmp     loc_1800A0868
0x1800a06c7  cmp     [rbp+4Fh+var_60], 20h ; ' '
0x1800a06cb  jz      short loc_1800A06D2
0x1800a06cd  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800a06d2  mov     [rbp+4Fh+var_50], 0
0x1800a06da  mov     [rbp+4Fh+var_60], 0
0x1800a06e1  lea     rax, [rbp+4Fh+var_50]
0x1800a06e5  mov     [rbp+4Fh+var_38], rax
0x1800a06e9  mov     [rbp+4Fh+var_30], 0
0x1800a06f1  mov     [rbp+4Fh+var_28], 1
0x1800a06f5  lea     rax, [rbp+4Fh+var_60]
0x1800a06f9  mov     [rsp+0B0h+lpData], rax; int
0x1800a06fe  lea     r9, [rbp+4Fh+var_30]
0x1800a0702  mov     r8d, 20h ; ' '
0x1800a0708  mov     rdx, [rbp+4Fh+pbBuffer]
0x1800a070c  mov     cl, 1
0x1800a070e  call    DpapiProtectUnprotect
0x1800a0713  mov     edi, eax
0x1800a0715  lea     rcx, [rbp+4Fh+var_38]
0x1800a0719  call    ??1?$out_param_t@V?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>(void)
0x1800a071e  test    edi, edi
0x1800a0720  jns     short loc_1800A0748
0x1800a0722  mov     rcx, [rbp+57h]; this
0x1800a0726  mov     r9d, edi; char *
0x1800a0729  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\devicecredential"...
0x1800a0730  mov     edx, 23Ch; void *
0x1800a0735  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a073a  lea     rcx, [rbp+4Fh+var_50]
0x1800a073e  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a0743  jmp     loc_1800A06B9
0x1800a0748  mov     [rbp+4Fh+var_48], 0
0x1800a0750  mov     [rbp+4Fh+var_5C], 0
0x1800a0757  lea     rax, [rbp+4Fh+var_48]
0x1800a075b  mov     [rbp+4Fh+var_38], rax
0x1800a075f  mov     [rbp+4Fh+var_30], 0
0x1800a0767  mov     [rbp+4Fh+var_28], 1
0x1800a076b  mov     rdx, [rbp+4Fh+var_58]
0x1800a076f  lea     r9, [rdx+10h]
0x1800a0773  lea     rax, [rbp+4Fh+var_5C]
0x1800a0777  mov     [rsp+0B0h+var_70], rax
0x1800a077c  lea     rax, [rbp+4Fh+var_30]
0x1800a0780  mov     [rsp+0B0h+var_78], rax
0x1800a0785  mov     eax, [rbp+4Fh+arg_20]
0x1800a0788  mov     dword ptr [rsp+0B0h+var_80], eax
0x1800a078c  mov     qword ptr [rsp+0B0h+cbData], r15
0x1800a0791  mov     cl, 1
0x1800a0793  call    AesEncryptDecrypt
0x1800a0798  mov     edi, eax
0x1800a079a  lea     rcx, [rbp+4Fh+var_38]
0x1800a079e  call    ??1?$out_param_t@V?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>(void)
0x1800a07a3  test    edi, edi
0x1800a07a5  jns     short loc_1800A07CD
0x1800a07a7  mov     rcx, [rbp+57h]; this
0x1800a07ab  mov     r9d, edi; char *
0x1800a07ae  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\devicecredential"...
0x1800a07b5  mov     edx, 24Ah; void *
0x1800a07ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a07bf  lea     rcx, [rbp+4Fh+var_48]
0x1800a07c3  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a07c8  jmp     loc_1800A073A
0x1800a07cd  mov     rcx, [rbp+4Fh+var_50]
0x1800a07d1  mov     eax, [rbp+4Fh+var_60]
0x1800a07d4  mov     [rsp+0B0h+cbData], eax; cbData
0x1800a07d8  mov     [rsp+0B0h+lpData], rcx; unsigned int
0x1800a07dd  mov     r9d, 3; dwType
0x1800a07e3  xor     r8d, r8d; Reserved
0x1800a07e6  lea     rdx, aNoncefordevice; "NonceForDeviceKey"
0x1800a07ed  mov     rcx, rsi; hKey
0x1800a07f0  call    cs:__imp_RegSetValueExW
0x1800a07f6  test    eax, eax
0x1800a07f8  jz      short loc_1800A0816
0x1800a07fa  mov     edx, 252h; void *
0x1800a07ff  lea     r8, aOnecoreDsSecur_38; "onecore\\ds\\security\\devicecredential"...
0x1800a0806  mov     r9d, eax; char *
0x1800a0809  mov     rcx, [rbp+57h]; this
0x1800a080d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a0812  mov     edi, eax
0x1800a0814  jmp     short loc_1800A07BF
0x1800a0816  mov     rcx, [rbp+4Fh+var_48]
0x1800a081a  mov     eax, [rbp+4Fh+var_5C]
0x1800a081d  mov     [rsp+0B0h+cbData], eax; cbData
0x1800a0821  mov     [rsp+0B0h+lpData], rcx; lpData
0x1800a0826  mov     r9d, 3; dwType
0x1800a082c  xor     r8d, r8d; Reserved
0x1800a082f  lea     rdx, aEncryptedpriva; "EncryptedPrivateKey"
0x1800a0836  mov     rcx, rsi; hKey
0x1800a0839  call    cs:__imp_RegSetValueExW
0x1800a083f  test    eax, eax
0x1800a0841  jz      short loc_1800A084A
0x1800a0843  mov     edx, 25Ah
0x1800a0848  jmp     short loc_1800A07FF
0x1800a084a  lea     rcx, [rbp+4Fh+var_48]
0x1800a084e  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a0853  lea     rcx, [rbp+4Fh+var_50]
0x1800a0857  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a085c  nop
0x1800a085d  lea     rcx, [rbp+4Fh+var_58]
0x1800a0861  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a0866  xor     edi, edi
0x1800a0868  lea     rcx, [rbp+4Fh+pbBuffer]
0x1800a086c  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a0871  mov     eax, edi
0x1800a0873  add     rsp, 90h
0x1800a087a  pop     r15
0x1800a087c  pop     r14
0x1800a087e  pop     rdi
0x1800a087f  pop     rsi
0x1800a0880  pop     rbp
0x1800a0881  retn
```
