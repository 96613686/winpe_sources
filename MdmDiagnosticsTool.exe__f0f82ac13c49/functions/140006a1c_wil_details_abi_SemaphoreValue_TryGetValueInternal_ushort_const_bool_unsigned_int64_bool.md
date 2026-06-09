# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140006a1c`
- end: `0x140006bd4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1400037d0`

## callees

- `0x140003438`
- `0x140004f98`
- `0x140006224`
- `0x140006244`
- `0x14000673c`
- `0x14000681c`
- `0x140006a1c`
- `0x1400096d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006a80`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006b1e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006a80`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006b1e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006a90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006a90`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  wil::details *v6; // rax
  void *v7; // rdx
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  wil::details *v12; // rax
  const char *v13; // r9
  void *v14; // rdx
  int v15; // eax
  void *v16; // rdx
  size_t v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+34h] [rbp-CCh] BYREF
  wil::details *v21; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v22; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v18);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v22 = v6;
  if ( v6 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v20);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v12 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v21 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v19);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v21,
          v16);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (int)"wil", v13);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v21,
      v14);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (int)"wil", v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v22,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x140006a1c  mov     [rsp-8+arg_8], rbx
0x140006a21  mov     [rsp-8+arg_18], rdi
0x140006a26  push    rbp
0x140006a27  lea     rbp, [rsp-170h]
0x140006a2f  sub     rsp, 270h
0x140006a36  mov     rax, cs:__security_cookie
0x140006a3d  xor     rax, rsp
0x140006a40  mov     [rbp+170h+var_10], rax
0x140006a47  mov     r9, rcx; pszSrc
0x140006a4a  mov     qword ptr [r8], 0
0x140006a51  lea     rcx, [rsp+270h+pszDest]; pszDest
0x140006a56  mov     edx, 104h; cchDest
0x140006a5b  mov     rdi, r8
0x140006a5e  call    StringCopyWorkerW
0x140006a63  lea     r8, aP0; "_p0"
0x140006a6a  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x140006a6f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140006a74  lea     r8, [rsp+270h+pszDest]; lpName
0x140006a79  xor     edx, edx; bInheritHandle
0x140006a7b  mov     ecx, 1F0003h; dwDesiredAccess
0x140006a80  call    cs:__imp_OpenSemaphoreW
0x140006a86  mov     [rsp+270h+var_230], rax
0x140006a8b  test    rax, rax
0x140006a8e  jnz     short loc_140006ABE
0x140006a90  call    cs:__imp_GetLastError
0x140006a96  cmp     eax, 2
0x140006a99  jz      loc_140006BA2
0x140006a9f  mov     rcx, [rbp+178h]; this
0x140006aa6  lea     r8, aWil; "wil"
0x140006aad  mov     edx, 0D0h; void *
0x140006ab2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140006ab7  mov     ebx, eax
0x140006ab9  jmp     loc_140006BA4
0x140006abe  lea     rdx, [rsp+270h+var_23C]; int *
0x140006ac3  mov     [rsp+270h+var_23C], 0
0x140006acb  mov     rcx, rax; hHandle
0x140006ace  mov     [rsp+270h+var_240], 0
0x140006ad6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140006adb  mov     ebx, eax
0x140006add  test    eax, eax
0x140006adf  jns     short loc_140006B01
0x140006ae1  mov     rcx, [rbp+178h]; this
0x140006ae8  lea     r8, aWil; "wil"
0x140006aef  mov     r9d, eax; char *
0x140006af2  mov     edx, 0D6h; void *
0x140006af7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006afc  jmp     loc_140006BA4
0x140006b01  lea     r8, asc_14000CEF0; "h"
0x140006b08  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x140006b0d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140006b12  lea     r8, [rsp+270h+pszDest]; lpName
0x140006b17  xor     edx, edx; bInheritHandle
0x140006b19  mov     ecx, 1F0003h; dwDesiredAccess
0x140006b1e  call    cs:__imp_OpenSemaphoreW
0x140006b24  mov     [rsp+270h+var_238], rax
0x140006b29  test    rax, rax
0x140006b2c  jnz     short loc_140006B54
0x140006b2e  mov     rcx, [rbp+178h]; this
0x140006b35  lea     r8, aWil; "wil"
0x140006b3c  mov     edx, 0DCh; void *
0x140006b41  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140006b46  mov     ebx, eax
0x140006b48  lea     rcx, [rsp+270h+var_238]
0x140006b4d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140006b52  jmp     short loc_140006BA4
0x140006b54  lea     rdx, [rsp+270h+var_240]; int *
0x140006b59  mov     rcx, rax; hHandle
0x140006b5c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140006b61  mov     ebx, eax
0x140006b63  test    eax, eax
0x140006b65  jns     short loc_140006B84
0x140006b67  mov     rcx, [rbp+178h]; this
0x140006b6e  lea     r8, aWil; "wil"
0x140006b75  mov     r9d, eax; char *
0x140006b78  mov     edx, 0DEh; void *
0x140006b7d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006b82  jmp     short loc_140006B48
0x140006b84  lea     rcx, [rsp+270h+var_238]
0x140006b89  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140006b8e  movsxd  rcx, [rsp+270h+var_240]
0x140006b93  movsxd  rax, [rsp+270h+var_23C]
0x140006b98  shl     rcx, 1Fh
0x140006b9c  or      rcx, rax
0x140006b9f  mov     [rdi], rcx
0x140006ba2  xor     ebx, ebx
0x140006ba4  lea     rcx, [rsp+270h+var_230]
0x140006ba9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140006bae  mov     eax, ebx
0x140006bb0  mov     rcx, [rbp+170h+var_10]
0x140006bb7  xor     rcx, rsp; StackCookie
0x140006bba  call    __security_check_cookie
0x140006bbf  lea     r11, [rsp+270h+var_s0]
0x140006bc7  mov     rbx, [r11+18h]
0x140006bcb  mov     rdi, [r11+28h]
0x140006bcf  mov     rsp, r11
0x140006bd2  pop     rbp
0x140006bd3  retn
```
