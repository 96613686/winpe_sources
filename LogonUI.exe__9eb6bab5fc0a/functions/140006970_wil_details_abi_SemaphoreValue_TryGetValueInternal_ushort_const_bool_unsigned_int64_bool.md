# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140006970`
- end: `0x140006b0c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1400068fc`

## callees

- `0x14000190c`
- `0x140002910`
- `0x140003d08`
- `0x140004e48`
- `0x14000618c`
- `0x1400061ac`
- `0x140006650`
- `0x140006970`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400069d4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006a64`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400069d4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006a64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400069e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400069e4`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  HANDLE v6; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  unsigned int v12; // r8d
  HANDLE v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  unsigned int v17; // r8d
  size_t v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v23; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v24[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v19);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v24[0] = v6;
  if ( v6 )
  {
    v22 = 0;
    v21 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v22);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v20);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v23 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v21);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
        *a3 = v22 | (unsigned __int64)((__int64)v21 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v20);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v7, v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v24);
  return LastError;
}

```

## disassembly

```asm
0x140006970  mov     [rsp-8+arg_8], rbx
0x140006975  mov     [rsp-8+arg_18], rdi
0x14000697a  push    rbp
0x14000697b  lea     rbp, [rsp-170h]
0x140006983  sub     rsp, 270h
0x14000698a  mov     rax, cs:__security_cookie
0x140006991  xor     rax, rsp
0x140006994  mov     [rbp+170h+var_10], rax
0x14000699b  mov     r9, rcx; pszSrc
0x14000699e  mov     qword ptr [r8], 0
0x1400069a5  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1400069aa  mov     edx, 104h; cchDest
0x1400069af  mov     rdi, r8
0x1400069b2  call    StringCopyWorkerW
0x1400069b7  lea     r8, aP0; "_p0"
0x1400069be  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1400069c3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1400069c8  lea     r8, [rsp+270h+pszDest]; lpName
0x1400069cd  xor     edx, edx; bInheritHandle
0x1400069cf  mov     ecx, 1F0003h; dwDesiredAccess
0x1400069d4  call    cs:__imp_OpenSemaphoreW
0x1400069da  mov     [rsp+270h+var_230], rax
0x1400069df  test    rax, rax
0x1400069e2  jnz     short loc_140006A0B
0x1400069e4  call    cs:__imp_GetLastError
0x1400069ea  cmp     eax, 2
0x1400069ed  jz      loc_140006ADA
0x1400069f3  mov     rcx, [rbp+178h]; this
0x1400069fa  mov     edx, 0D0h; void *
0x1400069ff  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140006a04  mov     ebx, eax
0x140006a06  jmp     loc_140006ADC
0x140006a0b  lea     rdx, [rsp+270h+var_23C]; int *
0x140006a10  mov     [rsp+270h+var_23C], 0
0x140006a18  mov     rcx, rax; hHandle
0x140006a1b  mov     [rsp+270h+var_240], 0
0x140006a23  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140006a28  mov     ebx, eax
0x140006a2a  test    eax, eax
0x140006a2c  jns     short loc_140006A47
0x140006a2e  mov     rcx, [rbp+178h]; this
0x140006a35  mov     r9d, eax; char *
0x140006a38  mov     edx, 0D6h; void *
0x140006a3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006a42  jmp     loc_140006ADC
0x140006a47  lea     r8, asc_1400099F0; "h"
0x140006a4e  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x140006a53  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140006a58  lea     r8, [rsp+270h+pszDest]; lpName
0x140006a5d  xor     edx, edx; bInheritHandle
0x140006a5f  mov     ecx, 1F0003h; dwDesiredAccess
0x140006a64  call    cs:__imp_OpenSemaphoreW
0x140006a6a  mov     [rsp+270h+var_238], rax
0x140006a6f  test    rax, rax
0x140006a72  jnz     short loc_140006A93
0x140006a74  mov     rcx, [rbp+178h]; this
0x140006a7b  mov     edx, 0DCh; void *
0x140006a80  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140006a85  mov     ebx, eax
0x140006a87  lea     rcx, [rsp+270h+var_238]
0x140006a8c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140006a91  jmp     short loc_140006ADC
0x140006a93  lea     rdx, [rsp+270h+var_240]; int *
0x140006a98  mov     rcx, rax; hHandle
0x140006a9b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140006aa0  mov     ebx, eax
0x140006aa2  test    eax, eax
0x140006aa4  jns     short loc_140006ABC
0x140006aa6  mov     rcx, [rbp+178h]; this
0x140006aad  mov     r9d, eax; char *
0x140006ab0  mov     edx, 0DEh; void *
0x140006ab5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006aba  jmp     short loc_140006A87
0x140006abc  lea     rcx, [rsp+270h+var_238]
0x140006ac1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140006ac6  movsxd  rcx, [rsp+270h+var_240]
0x140006acb  movsxd  rax, [rsp+270h+var_23C]
0x140006ad0  shl     rcx, 1Fh
0x140006ad4  or      rcx, rax
0x140006ad7  mov     [rdi], rcx
0x140006ada  xor     ebx, ebx
0x140006adc  lea     rcx, [rsp+270h+var_230]
0x140006ae1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140006ae6  mov     eax, ebx
0x140006ae8  mov     rcx, [rbp+170h+var_10]
0x140006aef  xor     rcx, rsp; StackCookie
0x140006af2  call    __security_check_cookie
0x140006af7  lea     r11, [rsp+270h+var_s0]
0x140006aff  mov     rbx, [r11+18h]
0x140006b03  mov     rdi, [r11+28h]
0x140006b07  mov     rsp, r11
0x140006b0a  pop     rbp
0x140006b0b  retn
```
