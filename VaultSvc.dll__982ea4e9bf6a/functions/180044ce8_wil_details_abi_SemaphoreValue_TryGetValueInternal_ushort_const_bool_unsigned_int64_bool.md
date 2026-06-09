# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180044ce8`
- end: `0x180044e98`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `432`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800430fc`

## callees

- `0x1800031f0`
- `0x180033f94`
- `0x180038c6c`
- `0x18003a580`
- `0x180042dac`
- `0x180043c28`
- `0x180044734`
- `0x180044ce8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180044d51`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180044dea`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180044d51`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180044dea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044d61`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180044d61`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v10; // rax
  unsigned int v11; // r8d
  const char *v12; // r9
  int v13; // eax
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v17; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18[0] = v5;
  if ( v5 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v16);
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
    StringCchCatW(Name, 0x104u, L"h");
    v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v17 = v10;
    if ( v10 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v15);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
        *a3 = v16 | (unsigned __int64)((__int64)v15 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v13);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v11, v12);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v6, v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x180044ce8  mov     [rsp-8+arg_8], rbx
0x180044ced  push    rbp
0x180044cee  push    rdi
0x180044cef  push    r14
0x180044cf1  lea     rbp, [rsp-160h]
0x180044cf9  sub     rsp, 260h
0x180044d00  mov     rax, cs:__security_cookie
0x180044d07  xor     rax, rsp
0x180044d0a  mov     [rbp+170h+var_20], rax
0x180044d11  mov     rdi, r8
0x180044d14  mov     qword ptr [r8], 0
0x180044d1b  mov     r8, rcx; unsigned __int16 *
0x180044d1e  mov     r14d, 104h
0x180044d24  mov     edx, r14d; unsigned __int64
0x180044d27  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180044d2c  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180044d31  lea     r8, aP0; "_p0"
0x180044d38  mov     edx, r14d; unsigned __int64
0x180044d3b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180044d40  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180044d45  lea     r8, [rsp+270h+Name]; lpName
0x180044d4a  xor     edx, edx; bInheritHandle
0x180044d4c  mov     ecx, 1F0003h; dwDesiredAccess
0x180044d51  call    cs:__imp_OpenSemaphoreW
0x180044d57  mov     [rsp+270h+var_240], rax
0x180044d5c  test    rax, rax
0x180044d5f  jnz     short loc_180044D87
0x180044d61  call    cs:__imp_GetLastError
0x180044d67  cmp     eax, 2
0x180044d6a  jz      loc_180044E67
0x180044d70  mov     rcx, [rbp+178h]; this
0x180044d77  lea     edx, [r14-34h]; void *
0x180044d7b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180044d80  mov     ebx, eax
0x180044d82  jmp     loc_180044E69
0x180044d87  lea     rdx, [rsp+270h+var_24C]; int *
0x180044d8c  mov     [rsp+270h+var_24C], 0
0x180044d94  mov     rcx, rax; hHandle
0x180044d97  mov     [rsp+270h+var_250], 0; int
0x180044d9f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180044da4  mov     ebx, eax
0x180044da6  test    eax, eax
0x180044da8  jns     short loc_180044DCA
0x180044daa  mov     rcx, [rbp+178h]; this
0x180044db1  lea     r8, aWil; "wil"
0x180044db8  mov     r9d, eax; char *
0x180044dbb  mov     edx, 0D6h; void *
0x180044dc0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044dc5  jmp     loc_180044E69
0x180044dca  lea     r8, asc_180052FC0; "h"
0x180044dd1  mov     rdx, r14; unsigned __int64
0x180044dd4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180044dd9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180044dde  lea     r8, [rsp+270h+Name]; lpName
0x180044de3  xor     edx, edx; bInheritHandle
0x180044de5  mov     ecx, 1F0003h; dwDesiredAccess
0x180044dea  call    cs:__imp_OpenSemaphoreW
0x180044df0  mov     [rsp+270h+var_248], rax
0x180044df5  test    rax, rax
0x180044df8  jnz     short loc_180044E19
0x180044dfa  mov     rcx, [rbp+178h]; this
0x180044e01  mov     edx, 0DCh; void *
0x180044e06  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180044e0b  mov     ebx, eax
0x180044e0d  lea     rcx, [rsp+270h+var_248]
0x180044e12  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180044e17  jmp     short loc_180044E69
0x180044e19  lea     rdx, [rsp+270h+var_250]; int *
0x180044e1e  mov     rcx, rax; hHandle
0x180044e21  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180044e26  mov     ebx, eax
0x180044e28  test    eax, eax
0x180044e2a  jns     short loc_180044E49
0x180044e2c  mov     rcx, [rbp+178h]; this
0x180044e33  lea     r8, aWil; "wil"
0x180044e3a  mov     r9d, eax; char *
0x180044e3d  mov     edx, 0DEh; void *
0x180044e42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044e47  jmp     short loc_180044E0D
0x180044e49  lea     rcx, [rsp+270h+var_248]
0x180044e4e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180044e53  movsxd  rcx, [rsp+270h+var_250]
0x180044e58  movsxd  rax, [rsp+270h+var_24C]
0x180044e5d  shl     rcx, 1Fh
0x180044e61  or      rcx, rax
0x180044e64  mov     [rdi], rcx
0x180044e67  xor     ebx, ebx
0x180044e69  lea     rcx, [rsp+270h+var_240]
0x180044e6e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180044e73  mov     eax, ebx
0x180044e75  mov     rcx, [rbp+170h+var_20]
0x180044e7c  xor     rcx, rsp; StackCookie
0x180044e7f  call    __security_check_cookie
0x180044e84  mov     rbx, [rsp+270h+arg_8]
0x180044e8c  add     rsp, 260h
0x180044e93  pop     r14
0x180044e95  pop     rdi
0x180044e96  pop     rbp
0x180044e97  retn
```
