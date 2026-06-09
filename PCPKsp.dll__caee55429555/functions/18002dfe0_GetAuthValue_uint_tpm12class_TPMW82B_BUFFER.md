# GetAuthValue(uint,tpm12class::TPMW82B_BUFFER *)

- ea: `0x18002dfe0`
- end: `0x18002e377`
- name: `?GetAuthValue@@YAJIPEAVTPMW82B_BUFFER@tpm12class@@@Z`
- size: `919`
- prototype: `int(unsigned int, struct tpm12class::TPMW82B_BUFFER *)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, service_task`

## callers

- `0x1800293e0`
- `0x18002d934`
- `0x1800914ec`

## callees

- `0x1800133c4`
- `0x180014a60`
- `0x1800157c0`
- `0x180029a20`
- `0x18002a790`
- `0x18002dfe0`
- `0x18003d610`
- `0x180061b6c`
- `0x180061bac`
- `0x1800764d0`
- `0x1800768a0`
- `0x18007704c`
- `0x18009a56c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002e1b3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002e24f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002e1b3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18002e24f`
- `ntdll!RtlGetPersistedStateLocation` at `0x18002e0b3`
- `ntdll!RtlGetPersistedStateLocation` at `0x18002e101`
- `ntdll!RtlGetPersistedStateLocation` at `0x18002e167`
- `ntdll!RtlGetPersistedStateLocation` at `0x18002e0b3`
- `ntdll!RtlGetPersistedStateLocation` at `0x18002e101`
- `ntdll!RtlGetPersistedStateLocation` at `0x18002e167`

## string_xrefs

- `0x18002e0a3`: `System\CurrentControlSet\Services\TPM\WMI\Endorsement`
- `0x18002e0f1`: `System\CurrentControlSet\Services\TPM\WMI\Admin`
- `0x18002e157`: `System\CurrentControlSet\Services\TPM\WMI\Admin`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetAuthValue(int a1, void **a2)
{
  __int64 v4; // rdx
  int v5; // ebx
  int v6; // ebx
  unsigned int v7; // ebx
  int PersistedStateLocation; // eax
  __int64 v9; // rdx
  const WCHAR *v10; // rbx
  PVOID v11; // rdi
  __int64 v12; // rdx
  int v13; // eax
  const struct std::nothrow_t *v14; // rdx
  __int64 v15; // r9
  const struct std::nothrow_t *v16; // rdx
  __int64 v17; // rax
  int pdwType; // [rsp+20h] [rbp-E0h]
  int pdwTypea; // [rsp+20h] [rbp-E0h]
  LPDWORD pcbData; // [rsp+30h] [rbp-D0h]
  DWORD v22[2]; // [rsp+40h] [rbp-C0h] BYREF
  size_t Size; // [rsp+48h] [rbp-B8h] BYREF
  PVOID pvData; // [rsp+50h] [rbp-B0h] BYREF
  int *v25[3]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR SubKey[264]; // [rsp+70h] [rbp-90h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2A8h] [rbp+1A8h]

  KspFunctionLogger::KspFunctionLogger((KspFunctionLogger *)v25, L"GetAuthValue", 1);
  memset_0(SubKey, 0, 0x208u);
  v22[1] = 520;
  if ( !a2 )
  {
    v4 = 99;
LABEL_7:
    v7 = -2144795645;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers20.cpp",
      (const char *)0x80290403LL,
      pdwType);
    goto LABEL_42;
  }
  v5 = a1 - 1073741825;
  if ( v5 )
  {
    v6 = v5 - 9;
    if ( v6 )
    {
      if ( v6 != 1 )
      {
        v4 = 140;
        goto LABEL_7;
      }
      PersistedStateLocation = RtlGetPersistedStateLocation(
                                 L"TpmRegDriverPersistedDataEndorsement",
                                 0,
                                 L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Endorsement",
                                 0);
      if ( PersistedStateLocation < 0 )
      {
        v9 = 136;
LABEL_13:
        v7 = wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)v9,
               (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers20.cpp",
               (const char *)(unsigned int)PersistedStateLocation,
               (int)SubKey);
        goto LABEL_42;
      }
      v10 = L"EndorsementAuth";
    }
    else
    {
      PersistedStateLocation = RtlGetPersistedStateLocation(
                                 L"TpmRegDriverPersistedDataAdmin",
                                 0,
                                 L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Admin",
                                 0);
      if ( PersistedStateLocation < 0 )
      {
        v9 = 112;
        goto LABEL_13;
      }
      v10 = L"OwnerAuthFull";
    }
  }
  else
  {
    PersistedStateLocation = RtlGetPersistedStateLocation(
                               L"TpmRegDriverPersistedDataAdmin",
                               0,
                               L"System\\CurrentControlSet\\Services\\TPM\\WMI\\Admin",
                               0);
    if ( PersistedStateLocation < 0 )
    {
      v9 = 124;
      goto LABEL_13;
    }
    v10 = L"StorageOwnerAuth";
  }
  v22[0] = 0;
  if ( RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, v10, 2u, 0, 0, v22) < 0 )
  {
    pcbData = (LPDWORD)v10;
    v7 = -2144795647;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers20.cpp",
      (const char *)0x80290401LL,
      (int)"Failed to get regvalue: %ls\\%ls.",
      (const char *)SubKey,
      pcbData);
    goto LABEL_42;
  }
  wil::make_unique_nothrow<unsigned char [0]>(&pvData, v22[0]);
  v11 = pvData;
  if ( !pvData )
  {
    v7 = -2147024888;
    goto LABEL_42;
  }
  if ( RegGetValueW(HKEY_LOCAL_MACHINE, SubKey, v10, 2u, 0, pvData, v22) < 0 )
  {
    v12 = 163;
LABEL_36:
    v7 = -2144795647;
    v15 = 2150171649LL;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"onecore\\base\\ngscb\\platformcrypto\\pcpksp\\tpmhelpers20.cpp",
      (const char *)v15,
      pdwTypea);
    if ( v11 )
      operator delete(v11, v16);
    goto LABEL_42;
  }
  if ( v22[0] > 2 )
  {
    v17 = -1;
    do
      ++v17;
    while ( *((_WORD *)v11 + v17) );
    LODWORD(Size) = 3 * ((unsigned int)(v17 + 3) >> 2);
    v13 = tpm12class::TPMW82B_BUFFER::Allocate((tpm12class::TPMW82B_BUFFER *)a2, (unsigned int)Size);
    v7 = v13;
    if ( v13 < 0 )
    {
      v12 = 177;
      goto LABEL_27;
    }
    if ( (int)base64decodeW((const unsigned __int16 *)v11, a2[8], *((unsigned __int16 *)a2 + 28), (unsigned int *)&Size) < 0 )
    {
      v12 = 184;
      goto LABEL_36;
    }
    v13 = tpm12class::TPMW82B_BUFFER::Resize((tpm12class::TPMW82B_BUFFER *)a2, (unsigned int)Size);
    v7 = v13;
    if ( v13 < 0 )
    {
      v12 = 185;
      goto LABEL_27;
    }
  }
  else
  {
    v13 = tpm12class::TPMW82B_BUFFER::Allocate((tpm12class::TPMW82B_BUFFER *)a2, 0x20u);
    v7 = v13;
    if ( v13 < 0 )
    {
      v12 = 169;
LABEL_27:
      v15 = (unsigned int)v13;
      goto LABEL_28;
    }
  }
  if ( v11 )
    operator delete(v11, v14);
  v7 = 0;
LABEL_42:
  KspFunctionLogger::~KspFunctionLogger(v25);
  return v7;
}

```

## disassembly

```asm
0x18002dfe0  mov     [rsp-8+arg_0], rbx
0x18002dfe5  mov     [rsp-8+arg_10], rsi
0x18002dfea  push    rbp
0x18002dfeb  push    rdi
0x18002dfec  push    r14
0x18002dfee  lea     rbp, [rsp-190h]
0x18002dff6  sub     rsp, 290h
0x18002dffd  mov     rax, cs:__security_cookie
0x18002e004  xor     rax, rsp
0x18002e007  mov     [rbp+1A0h+var_20], rax
0x18002e00e  mov     rsi, rdx
0x18002e011  mov     ebx, ecx
0x18002e013  mov     r8b, 1; bool
0x18002e016  lea     rdx, aGetauthvalue; "GetAuthValue"
0x18002e01d  lea     rcx, [rsp+2A0h+var_248]; this
0x18002e022  call    ??0KspFunctionLogger@@QEAA@QEBG_N@Z; KspFunctionLogger::KspFunctionLogger(ushort const * const,bool)
0x18002e027  nop
0x18002e028  mov     edi, 208h
0x18002e02d  mov     r8d, edi; Size
0x18002e030  xor     edx, edx; Val
0x18002e032  lea     rcx, [rsp+2A0h+SubKey]; void *
0x18002e037  call    memset_0
0x18002e03c  mov     [rsp+2A0h+var_25C], edi
0x18002e040  xor     r14d, r14d
0x18002e043  test    rsi, rsi
0x18002e046  jnz     short loc_18002E04D
0x18002e048  lea     edx, [rsi+63h]
0x18002e04b  jmp     short loc_18002E068
0x18002e04d  sub     ebx, 40000001h
0x18002e053  jz      loc_18002E13C
0x18002e059  sub     ebx, 9
0x18002e05c  jz      short loc_18002E0D6
0x18002e05e  cmp     ebx, 1
0x18002e061  jz      short loc_18002E088
0x18002e063  mov     edx, 8Ch; void *
0x18002e068  mov     ebx, 80290403h
0x18002e06d  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18002e074  mov     r9d, ebx; char *
0x18002e077  mov     rcx, [rbp+1A8h]; this
0x18002e07e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e083  jmp     loc_18002E343
0x18002e088  lea     rax, [rsp+2A0h+var_25C]
0x18002e08d  mov     [rsp+2A0h+pcbData], rax
0x18002e092  mov     dword ptr [rsp+2A0h+pvData], edi
0x18002e096  lea     rax, [rsp+2A0h+SubKey]
0x18002e09b  mov     [rsp+2A0h+pdwType], rax
0x18002e0a0  xor     r9d, r9d
0x18002e0a3  lea     r8, aSystemCurrentc_16; "System\\CurrentControlSet\\Services\\TP"...
0x18002e0aa  xor     edx, edx
0x18002e0ac  lea     rcx, aTpmregdriverpe_2; "TpmRegDriverPersistedDataEndorsement"
0x18002e0b3  call    cs:__imp_RtlGetPersistedStateLocation
0x18002e0ba  nop     dword ptr [rax+rax+00h]
0x18002e0bf  test    eax, eax
0x18002e0c1  jns     short loc_18002E0CA
0x18002e0c3  mov     edx, 88h
0x18002e0c8  jmp     short loc_18002E116
0x18002e0ca  lea     rbx, aEndorsementaut; "EndorsementAuth"
0x18002e0d1  jmp     loc_18002E185
0x18002e0d6  lea     rax, [rsp+2A0h+var_25C]
0x18002e0db  mov     [rsp+2A0h+pcbData], rax
0x18002e0e0  mov     dword ptr [rsp+2A0h+pvData], edi
0x18002e0e4  lea     rax, [rsp+2A0h+SubKey]
0x18002e0e9  mov     [rsp+2A0h+pdwType], rax; int
0x18002e0ee  xor     r9d, r9d
0x18002e0f1  lea     r8, aSystemCurrentc_17; "System\\CurrentControlSet\\Services\\TP"...
0x18002e0f8  xor     edx, edx
0x18002e0fa  lea     rcx, aTpmregdriverpe_0; "TpmRegDriverPersistedDataAdmin"
0x18002e101  call    cs:__imp_RtlGetPersistedStateLocation
0x18002e108  nop     dword ptr [rax+rax+00h]
0x18002e10d  test    eax, eax
0x18002e10f  jns     short loc_18002E133
0x18002e111  mov     edx, 70h ; 'p'; void *
0x18002e116  mov     rcx, [rbp+1A8h]; this
0x18002e11d  mov     r9d, eax; char *
0x18002e120  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18002e127  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18002e12c  mov     ebx, eax
0x18002e12e  jmp     loc_18002E343
0x18002e133  lea     rbx, aOwnerauthfull; "OwnerAuthFull"
0x18002e13a  jmp     short loc_18002E185
0x18002e13c  lea     rax, [rsp+2A0h+var_25C]
0x18002e141  mov     [rsp+2A0h+pcbData], rax
0x18002e146  mov     dword ptr [rsp+2A0h+pvData], edi
0x18002e14a  lea     rax, [rsp+2A0h+SubKey]
0x18002e14f  mov     [rsp+2A0h+pdwType], rax
0x18002e154  xor     r9d, r9d
0x18002e157  lea     r8, aSystemCurrentc_17; "System\\CurrentControlSet\\Services\\TP"...
0x18002e15e  xor     edx, edx
0x18002e160  lea     rcx, aTpmregdriverpe_0; "TpmRegDriverPersistedDataAdmin"
0x18002e167  call    cs:__imp_RtlGetPersistedStateLocation
0x18002e16e  nop     dword ptr [rax+rax+00h]
0x18002e173  test    eax, eax
0x18002e175  jns     short loc_18002E17E
0x18002e177  mov     edx, 7Ch ; '|'
0x18002e17c  jmp     short loc_18002E116
0x18002e17e  lea     rbx, aStorageownerau; "StorageOwnerAuth"
0x18002e185  mov     [rsp+2A0h+var_260], r14d
0x18002e18a  lea     rax, [rsp+2A0h+var_260]
0x18002e18f  mov     [rsp+2A0h+pcbData], rax; pcbData
0x18002e194  mov     [rsp+2A0h+pvData], r14; pvData
0x18002e199  mov     [rsp+2A0h+pdwType], r14; pdwType
0x18002e19e  mov     r9d, 2; dwFlags
0x18002e1a4  mov     r8, rbx; lpValue
0x18002e1a7  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x18002e1ac  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002e1b3  call    cs:__imp_RegGetValueW
0x18002e1ba  nop     dword ptr [rax+rax+00h]
0x18002e1bf  test    eax, eax
0x18002e1c1  jns     short loc_18002E203
0x18002e1c3  mov     rcx, [rbp+1A8h]; this
0x18002e1ca  mov     [rsp+2A0h+pcbData], rbx
0x18002e1cf  lea     rax, [rsp+2A0h+SubKey]
0x18002e1d4  mov     [rsp+2A0h+pvData], rax; char *
0x18002e1d9  lea     rax, aFailedToGetReg; "Failed to get regvalue: %ls\\%ls."
0x18002e1e0  mov     [rsp+2A0h+pdwType], rax; int
0x18002e1e5  mov     ebx, 80290401h
0x18002e1ea  mov     r9d, ebx; char *
0x18002e1ed  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18002e1f4  mov     edx, 98h; void *
0x18002e1f9  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18002e1fe  jmp     loc_18002E343
0x18002e203  mov     edx, [rsp+2A0h+var_260]
0x18002e207  lea     rcx, [rsp+2A0h+var_250]
0x18002e20c  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18002e211  nop
0x18002e212  mov     rdi, [rsp+2A0h+var_250]
0x18002e217  test    rdi, rdi
0x18002e21a  jnz     short loc_18002E226
0x18002e21c  mov     ebx, 80070008h
0x18002e221  jmp     loc_18002E343
0x18002e226  lea     rax, [rsp+2A0h+var_260]
0x18002e22b  mov     [rsp+2A0h+pcbData], rax; pcbData
0x18002e230  mov     [rsp+2A0h+pvData], rdi; pvData
0x18002e235  mov     [rsp+2A0h+pdwType], r14; int
0x18002e23a  mov     r9d, 2; dwFlags
0x18002e240  mov     r8, rbx; lpValue
0x18002e243  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x18002e248  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18002e24f  call    cs:__imp_RegGetValueW
0x18002e256  nop     dword ptr [rax+rax+00h]
0x18002e25b  test    eax, eax
0x18002e25d  jns     short loc_18002E269
0x18002e25f  mov     edx, 0A3h
0x18002e264  jmp     loc_18002E30A
0x18002e269  cmp     [rsp+2A0h+var_260], 2
0x18002e26e  ja      short loc_18002E2B9
0x18002e270  mov     edx, 20h ; ' '; unsigned __int64
0x18002e275  mov     rcx, rsi; this
0x18002e278  call    ?Allocate@TPMW82B_BUFFER@tpm12class@@QEAAJ_K@Z; tpm12class::TPMW82B_BUFFER::Allocate(unsigned __int64)
0x18002e27d  mov     ebx, eax
0x18002e27f  test    eax, eax
0x18002e281  jns     loc_18002E333
0x18002e287  mov     edx, 0A9h; void *
0x18002e28c  mov     r9d, eax; char *
0x18002e28f  lea     r8, aOnecoreBaseNgs_14; "onecore\\base\\ngscb\\platformcrypto\\p"...
0x18002e296  mov     rcx, [rbp+1A8h]; this
0x18002e29d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002e2a2  nop
0x18002e2a3  test    rdi, rdi
0x18002e2a6  jz      loc_18002E343
0x18002e2ac  mov     rcx, rdi; void *
0x18002e2af  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002e2b4  jmp     loc_18002E343
0x18002e2b9  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002e2bd  inc     rax
0x18002e2c0  cmp     [rdi+rax*2], r14w
0x18002e2c5  jnz     short loc_18002E2BD
0x18002e2c7  add     eax, 3
0x18002e2ca  shr     eax, 2
0x18002e2cd  lea     eax, [rax+rax*2]
0x18002e2d0  mov     dword ptr [rsp+2A0h+Size], eax
0x18002e2d4  mov     edx, eax; unsigned __int64
0x18002e2d6  mov     rcx, rsi; this
0x18002e2d9  call    ?Allocate@TPMW82B_BUFFER@tpm12class@@QEAAJ_K@Z; tpm12class::TPMW82B_BUFFER::Allocate(unsigned __int64)
0x18002e2de  mov     ebx, eax
0x18002e2e0  test    eax, eax
0x18002e2e2  jns     short loc_18002E2EB
0x18002e2e4  mov     edx, 0B1h
0x18002e2e9  jmp     short loc_18002E28C
0x18002e2eb  movzx   r8d, word ptr [rsi+38h]; unsigned int
0x18002e2f0  lea     r9, [rsp+2A0h+Size]; unsigned int *
0x18002e2f5  mov     rdx, [rsi+40h]; void *
0x18002e2f9  mov     rcx, rdi; unsigned __int16 *
0x18002e2fc  call    ?base64decodeW@@YAJPEBGPEAXKPEAK@Z; base64decodeW(ushort const *,void *,ulong,ulong *)
0x18002e301  test    eax, eax
0x18002e303  jns     short loc_18002E317
0x18002e305  mov     edx, 0B8h
0x18002e30a  mov     ebx, 80290401h
0x18002e30f  mov     r9d, ebx
0x18002e312  jmp     loc_18002E28F
0x18002e317  mov     edx, dword ptr [rsp+2A0h+Size]; Size
0x18002e31b  mov     rcx, rsi; this
0x18002e31e  call    ?Resize@TPMW82B_BUFFER@tpm12class@@QEAAJ_K@Z; tpm12class::TPMW82B_BUFFER::Resize(unsigned __int64)
0x18002e323  mov     ebx, eax
0x18002e325  test    eax, eax
0x18002e327  jns     short loc_18002E333
0x18002e329  mov     edx, 0B9h
0x18002e32e  jmp     loc_18002E28C
0x18002e333  test    rdi, rdi
0x18002e336  jz      short loc_18002E340
0x18002e338  mov     rcx, rdi; void *
0x18002e33b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002e340  mov     ebx, r14d
0x18002e343  lea     rcx, [rsp+2A0h+var_248]; this
0x18002e348  call    ??1KspFunctionLogger@@QEAA@XZ; KspFunctionLogger::~KspFunctionLogger(void)
0x18002e34d  mov     eax, ebx
0x18002e34f  mov     rcx, [rbp+1A0h+var_20]
0x18002e356  xor     rcx, rsp; StackCookie
0x18002e359  call    __security_check_cookie
0x18002e35e  lea     r11, [rsp+2A0h+var_10]
0x18002e366  mov     rbx, [r11+20h]
0x18002e36a  mov     rsi, [r11+30h]
0x18002e36e  mov     rsp, r11
0x18002e371  pop     r14
0x18002e373  pop     rdi
0x18002e374  pop     rbp
0x18002e375  retn
```
