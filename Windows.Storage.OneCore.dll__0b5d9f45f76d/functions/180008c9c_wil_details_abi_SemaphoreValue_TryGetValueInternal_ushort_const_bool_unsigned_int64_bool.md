# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180008c9c`
- end: `0x180008e59`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `445`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180008c18`

## callees

- `0x180002be0`
- `0x180004b90`
- `0x1800061c0`
- `0x180007f8c`
- `0x180007fac`
- `0x180008678`
- `0x1800086cc`
- `0x180008c9c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008d00`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008da3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008d00`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008da3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008d10`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        unsigned __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  const char *v6; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v9; // rax
  const char *v10; // r9
  int v11; // eax
  int v13; // [rsp+20h] [rbp-E0h] BYREF
  int v14; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v15; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v16[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, a2, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v16[0] = v5;
  if ( v5 )
  {
    v14 = 0;
    v13 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v14);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v13);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v15 = v9;
    if ( v9 )
    {
      v11 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, &v13);
      LastError = v11;
      if ( v11 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
        *a3 = v14 | (unsigned __int64)((__int64)v13 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v11,
        v13);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v10);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v6);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v16);
  return LastError;
}

```

## disassembly

```asm
0x180008c9c  mov     [rsp-8+arg_8], rbx
0x180008ca1  mov     [rsp-8+arg_18], rdi
0x180008ca6  push    rbp
0x180008ca7  lea     rbp, [rsp-160h]
0x180008caf  sub     rsp, 260h
0x180008cb6  mov     rax, cs:__security_cookie
0x180008cbd  xor     rax, rsp
0x180008cc0  mov     [rbp+160h+var_10], rax
0x180008cc7  mov     rdi, r8
0x180008cca  mov     qword ptr [r8], 0
0x180008cd1  mov     r8, rcx; unsigned __int16 *
0x180008cd4  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180008cd9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180008cde  lea     r8, aP0; "_p0"
0x180008ce5  mov     edx, 104h; unsigned __int64
0x180008cea  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180008cef  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008cf4  lea     r8, [rsp+260h+Name]; lpName
0x180008cf9  xor     edx, edx; bInheritHandle
0x180008cfb  mov     ecx, 1F0003h; dwDesiredAccess
0x180008d00  call    cs:__imp_OpenSemaphoreW
0x180008d06  mov     [rsp+260h+var_230], rax
0x180008d0b  test    rax, rax
0x180008d0e  jnz     short loc_180008D3E
0x180008d10  call    cs:__imp_GetLastError
0x180008d16  cmp     eax, 2
0x180008d19  jz      loc_180008E27
0x180008d1f  mov     rcx, [rbp+168h]; this
0x180008d26  lea     r8, aWil; "wil"
0x180008d2d  mov     edx, 0D0h; void *
0x180008d32  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008d37  mov     ebx, eax
0x180008d39  jmp     loc_180008E29
0x180008d3e  lea     rdx, [rsp+260h+var_23C]; int *
0x180008d43  mov     [rsp+260h+var_23C], 0
0x180008d4b  mov     rcx, rax; hHandle
0x180008d4e  mov     [rsp+260h+var_240], 0; int
0x180008d56  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008d5b  mov     ebx, eax
0x180008d5d  test    eax, eax
0x180008d5f  jns     short loc_180008D81
0x180008d61  mov     rcx, [rbp+168h]; this
0x180008d68  lea     r8, aWil; "wil"
0x180008d6f  mov     r9d, eax; char *
0x180008d72  mov     edx, 0D6h; void *
0x180008d77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d7c  jmp     loc_180008E29
0x180008d81  lea     r8, asc_180027D60; "h"
0x180008d88  mov     edx, 104h; unsigned __int64
0x180008d8d  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180008d92  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180008d97  lea     r8, [rsp+260h+Name]; lpName
0x180008d9c  xor     edx, edx; bInheritHandle
0x180008d9e  mov     ecx, 1F0003h; dwDesiredAccess
0x180008da3  call    cs:__imp_OpenSemaphoreW
0x180008da9  mov     [rsp+260h+var_238], rax
0x180008dae  test    rax, rax
0x180008db1  jnz     short loc_180008DD9
0x180008db3  mov     rcx, [rbp+168h]; this
0x180008dba  lea     r8, aWil; "wil"
0x180008dc1  mov     edx, 0DCh; void *
0x180008dc6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008dcb  mov     ebx, eax
0x180008dcd  lea     rcx, [rsp+260h+var_238]
0x180008dd2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008dd7  jmp     short loc_180008E29
0x180008dd9  lea     rdx, [rsp+260h+var_240]; int *
0x180008dde  mov     rcx, rax; hHandle
0x180008de1  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008de6  mov     ebx, eax
0x180008de8  test    eax, eax
0x180008dea  jns     short loc_180008E09
0x180008dec  mov     rcx, [rbp+168h]; this
0x180008df3  lea     r8, aWil; "wil"
0x180008dfa  mov     r9d, eax; char *
0x180008dfd  mov     edx, 0DEh; void *
0x180008e02  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e07  jmp     short loc_180008DCD
0x180008e09  lea     rcx, [rsp+260h+var_238]
0x180008e0e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008e13  movsxd  rcx, [rsp+260h+var_240]
0x180008e18  movsxd  rax, [rsp+260h+var_23C]
0x180008e1d  shl     rcx, 1Fh
0x180008e21  or      rcx, rax
0x180008e24  mov     [rdi], rcx
0x180008e27  xor     ebx, ebx
0x180008e29  lea     rcx, [rsp+260h+var_230]
0x180008e2e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008e33  mov     eax, ebx
0x180008e35  mov     rcx, [rbp+160h+var_10]
0x180008e3c  xor     rcx, rsp; StackCookie
0x180008e3f  call    __security_check_cookie
0x180008e44  lea     r11, [rsp+260h+var_s0]
0x180008e4c  mov     rbx, [r11+18h]
0x180008e50  mov     rdi, [r11+28h]
0x180008e54  mov     rsp, r11
0x180008e57  pop     rbp
0x180008e58  retn
```
