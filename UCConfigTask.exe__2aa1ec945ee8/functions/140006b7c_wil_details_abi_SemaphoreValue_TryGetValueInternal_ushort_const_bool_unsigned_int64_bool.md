# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140006b7c`
- end: `0x140006d26`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140006af8`

## callees

- `0x1400014c0`
- `0x140003078`
- `0x1400045b8`
- `0x140005fac`
- `0x140005fcc`
- `0x140006690`
- `0x140006770`
- `0x140006b7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006be0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006c77`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006be0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140006c77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006bf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006bf0`

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
  unsigned int v8; // r8d
  const char *v9; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  wil::details *v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  void *v16; // rdx
  int v17; // eax
  void *v18; // rdx
  size_t v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+34h] [rbp-CCh] BYREF
  wil::details *v23; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v24; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v20);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v24 = v6;
  if ( v6 )
  {
    v22 = 0;
    v21 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v22);
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
    StringCchCatW(pszDest, v12, L"h");
    v13 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v23 = v13;
    if ( v13 )
    {
      v17 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v21);
      LastError = v17;
      if ( v17 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v23,
          v18);
        *a3 = v22 | (unsigned __int64)((__int64)v21 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v23,
      v16);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v8, v9);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v24,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x140006b7c  mov     [rsp-8+arg_8], rbx
0x140006b81  mov     [rsp-8+arg_18], rdi
0x140006b86  push    rbp
0x140006b87  lea     rbp, [rsp-170h]
0x140006b8f  sub     rsp, 270h
0x140006b96  mov     rax, cs:__security_cookie
0x140006b9d  xor     rax, rsp
0x140006ba0  mov     [rbp+170h+var_10], rax
0x140006ba7  mov     r9, rcx; pszSrc
0x140006baa  mov     qword ptr [r8], 0
0x140006bb1  lea     rcx, [rsp+270h+pszDest]; pszDest
0x140006bb6  mov     edx, 104h; cchDest
0x140006bbb  mov     rdi, r8
0x140006bbe  call    StringCopyWorkerW
0x140006bc3  lea     r8, aP0; "_p0"
0x140006bca  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x140006bcf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140006bd4  lea     r8, [rsp+270h+pszDest]; lpName
0x140006bd9  xor     edx, edx; bInheritHandle
0x140006bdb  mov     ecx, 1F0003h; dwDesiredAccess
0x140006be0  call    cs:__imp_OpenSemaphoreW
0x140006be6  mov     [rsp+270h+var_230], rax
0x140006beb  test    rax, rax
0x140006bee  jnz     short loc_140006C17
0x140006bf0  call    cs:__imp_GetLastError
0x140006bf6  cmp     eax, 2
0x140006bf9  jz      loc_140006CF4
0x140006bff  mov     rcx, [rbp+178h]; this
0x140006c06  mov     edx, 0D0h; void *
0x140006c0b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140006c10  mov     ebx, eax
0x140006c12  jmp     loc_140006CF6
0x140006c17  lea     rdx, [rsp+270h+var_23C]; int *
0x140006c1c  mov     [rsp+270h+var_23C], 0
0x140006c24  mov     rcx, rax; hHandle
0x140006c27  mov     [rsp+270h+var_240], 0
0x140006c2f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140006c34  mov     ebx, eax
0x140006c36  test    eax, eax
0x140006c38  jns     short loc_140006C5A
0x140006c3a  mov     rcx, [rbp+178h]; this
0x140006c41  lea     r8, aWil; "wil"
0x140006c48  mov     r9d, eax; char *
0x140006c4b  mov     edx, 0D6h; void *
0x140006c50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006c55  jmp     loc_140006CF6
0x140006c5a  lea     r8, asc_14000A9E0; "h"
0x140006c61  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x140006c66  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140006c6b  lea     r8, [rsp+270h+pszDest]; lpName
0x140006c70  xor     edx, edx; bInheritHandle
0x140006c72  mov     ecx, 1F0003h; dwDesiredAccess
0x140006c77  call    cs:__imp_OpenSemaphoreW
0x140006c7d  mov     [rsp+270h+var_238], rax
0x140006c82  test    rax, rax
0x140006c85  jnz     short loc_140006CA6
0x140006c87  mov     rcx, [rbp+178h]; this
0x140006c8e  mov     edx, 0DCh; void *
0x140006c93  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140006c98  mov     ebx, eax
0x140006c9a  lea     rcx, [rsp+270h+var_238]
0x140006c9f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140006ca4  jmp     short loc_140006CF6
0x140006ca6  lea     rdx, [rsp+270h+var_240]; int *
0x140006cab  mov     rcx, rax; hHandle
0x140006cae  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140006cb3  mov     ebx, eax
0x140006cb5  test    eax, eax
0x140006cb7  jns     short loc_140006CD6
0x140006cb9  mov     rcx, [rbp+178h]; this
0x140006cc0  lea     r8, aWil; "wil"
0x140006cc7  mov     r9d, eax; char *
0x140006cca  mov     edx, 0DEh; void *
0x140006ccf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140006cd4  jmp     short loc_140006C9A
0x140006cd6  lea     rcx, [rsp+270h+var_238]
0x140006cdb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140006ce0  movsxd  rcx, [rsp+270h+var_240]
0x140006ce5  movsxd  rax, [rsp+270h+var_23C]
0x140006cea  shl     rcx, 1Fh
0x140006cee  or      rcx, rax
0x140006cf1  mov     [rdi], rcx
0x140006cf4  xor     ebx, ebx
0x140006cf6  lea     rcx, [rsp+270h+var_230]
0x140006cfb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140006d00  mov     eax, ebx
0x140006d02  mov     rcx, [rbp+170h+var_10]
0x140006d09  xor     rcx, rsp; StackCookie
0x140006d0c  call    __security_check_cookie
0x140006d11  lea     r11, [rsp+270h+var_s0]
0x140006d19  mov     rbx, [r11+18h]
0x140006d1d  mov     rdi, [r11+28h]
0x140006d21  mov     rsp, r11
0x140006d24  pop     rbp
0x140006d25  retn
```
