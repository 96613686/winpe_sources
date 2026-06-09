# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006ce0`
- end: `0x180006e82`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180004d48`

## callees

- `0x180004be4`
- `0x180005a4c`
- `0x1800067cc`
- `0x1800067ec`
- `0x180006a9c`
- `0x180006af0`
- `0x180006ce0`
- `0x18000b710`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006d59`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006d49`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006ddb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006d49`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006ddb`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  size_t v5; // r9
  wil::details *v6; // rax
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  int v12; // r8d
  size_t v13; // r9
  wil::details *v14; // rax
  unsigned int v15; // r8d
  const char *v16; // r9
  void *v17; // rdx
  int v18; // eax
  void *v19; // rdx
  int v20; // r8d
  int v22; // [rsp+20h] [rbp-E0h] BYREF
  int v23; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v24; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v25; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0", v5);
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v25 = v6;
  if ( v6 )
  {
    v23 = 0;
    v22 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v23);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h", v13);
    v14 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v24 = v14;
    if ( v14 )
    {
      v18 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, &v22);
      LastError = v18;
      if ( v18 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v24,
          v19);
        *a3 = v23 | (unsigned __int64)((__int64)v22 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v20, (const char *)(unsigned int)v18);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v15, v16);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v24,
      v17);
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
    &v25,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x180006ce0  mov     [rsp-8+arg_8], rbx
0x180006ce5  push    rbp
0x180006ce6  push    rdi
0x180006ce7  push    r14
0x180006ce9  lea     rbp, [rsp-160h]
0x180006cf1  sub     rsp, 260h
0x180006cf8  mov     rax, cs:__security_cookie
0x180006cff  xor     rax, rsp
0x180006d02  mov     [rbp+170h+var_20], rax
0x180006d09  mov     rdi, r8
0x180006d0c  mov     qword ptr [r8], 0
0x180006d13  mov     r8, rcx; unsigned __int16 *
0x180006d16  mov     r14d, 104h
0x180006d1c  mov     edx, r14d; unsigned __int64
0x180006d1f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006d24  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180006d29  lea     r8, aP0; "_p0"
0x180006d30  mov     edx, r14d; unsigned __int64
0x180006d33  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006d38  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006d3d  lea     r8, [rsp+270h+Name]; lpName
0x180006d42  xor     edx, edx; bInheritHandle
0x180006d44  mov     ecx, 1F0003h; dwDesiredAccess
0x180006d49  call    cs:__imp_OpenSemaphoreW
0x180006d4f  mov     [rsp+270h+var_240], rax
0x180006d54  test    rax, rax
0x180006d57  jnz     short loc_180006D7F
0x180006d59  call    cs:__imp_GetLastError
0x180006d5f  cmp     eax, 2
0x180006d62  jz      loc_180006E51
0x180006d68  mov     rcx, [rbp+178h]; this
0x180006d6f  lea     edx, [r14-34h]; void *
0x180006d73  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006d78  mov     ebx, eax
0x180006d7a  jmp     loc_180006E53
0x180006d7f  lea     rdx, [rsp+270h+var_24C]; int *
0x180006d84  mov     [rsp+270h+var_24C], 0
0x180006d8c  mov     rcx, rax; hHandle
0x180006d8f  mov     [rsp+270h+var_250], 0; int
0x180006d97  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006d9c  mov     ebx, eax
0x180006d9e  test    eax, eax
0x180006da0  jns     short loc_180006DBB
0x180006da2  mov     rcx, [rbp+178h]; this
0x180006da9  mov     r9d, eax; char *
0x180006dac  mov     edx, 0D6h; void *
0x180006db1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006db6  jmp     loc_180006E53
0x180006dbb  lea     r8, asc_18000EC58; "h"
0x180006dc2  mov     rdx, r14; unsigned __int64
0x180006dc5  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180006dca  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180006dcf  lea     r8, [rsp+270h+Name]; lpName
0x180006dd4  xor     edx, edx; bInheritHandle
0x180006dd6  mov     ecx, 1F0003h; dwDesiredAccess
0x180006ddb  call    cs:__imp_OpenSemaphoreW
0x180006de1  mov     [rsp+270h+var_248], rax
0x180006de6  test    rax, rax
0x180006de9  jnz     short loc_180006E0A
0x180006deb  mov     rcx, [rbp+178h]; this
0x180006df2  mov     edx, 0DCh; void *
0x180006df7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180006dfc  mov     ebx, eax
0x180006dfe  lea     rcx, [rsp+270h+var_248]
0x180006e03  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006e08  jmp     short loc_180006E53
0x180006e0a  lea     rdx, [rsp+270h+var_250]; int *
0x180006e0f  mov     rcx, rax; hHandle
0x180006e12  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180006e17  mov     ebx, eax
0x180006e19  test    eax, eax
0x180006e1b  jns     short loc_180006E33
0x180006e1d  mov     rcx, [rbp+178h]; this
0x180006e24  mov     r9d, eax; char *
0x180006e27  mov     edx, 0DEh; void *
0x180006e2c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006e31  jmp     short loc_180006DFE
0x180006e33  lea     rcx, [rsp+270h+var_248]
0x180006e38  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006e3d  movsxd  rcx, [rsp+270h+var_250]
0x180006e42  movsxd  rax, [rsp+270h+var_24C]
0x180006e47  shl     rcx, 1Fh
0x180006e4b  or      rcx, rax
0x180006e4e  mov     [rdi], rcx
0x180006e51  xor     ebx, ebx
0x180006e53  lea     rcx, [rsp+270h+var_240]
0x180006e58  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180006e5d  mov     eax, ebx
0x180006e5f  mov     rcx, [rbp+170h+var_20]
0x180006e66  xor     rcx, rsp; StackCookie
0x180006e69  call    __security_check_cookie
0x180006e6e  mov     rbx, [rsp+270h+arg_8]
0x180006e76  add     rsp, 260h
0x180006e7d  pop     r14
0x180006e7f  pop     rdi
0x180006e80  pop     rbp
0x180006e81  retn
```
