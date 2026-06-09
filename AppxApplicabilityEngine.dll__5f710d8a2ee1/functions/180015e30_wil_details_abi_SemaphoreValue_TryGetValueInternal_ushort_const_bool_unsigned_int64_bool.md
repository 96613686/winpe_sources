# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180015e30`
- end: `0x180015fda`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180015dac`

## callees

- `0x18000a378`
- `0x18001433c`
- `0x180014f7c`
- `0x180015754`
- `0x18001577c`
- `0x180015cbc`
- `0x180015e30`
- `0x1800227c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180015e94`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180015f2b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180015e94`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180015f2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ea4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015ea4`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
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
  HANDLE v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  int v15; // eax
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20[0] = v6;
  if ( v6 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v17);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v12 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v17);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v15,
        v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v13, v14);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x180015e30  mov     [rsp-8+arg_8], rbx
0x180015e35  mov     [rsp-8+arg_18], rdi
0x180015e3a  push    rbp
0x180015e3b  lea     rbp, [rsp-160h]
0x180015e43  sub     rsp, 260h
0x180015e4a  mov     rax, cs:__security_cookie
0x180015e51  xor     rax, rsp
0x180015e54  mov     [rbp+160h+var_10], rax
0x180015e5b  mov     rdi, r8
0x180015e5e  mov     qword ptr [r8], 0
0x180015e65  mov     r8, rcx; unsigned __int16 *
0x180015e68  mov     edx, 104h; unsigned __int64
0x180015e6d  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180015e72  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180015e77  lea     r8, aP0; "_p0"
0x180015e7e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180015e83  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180015e88  lea     r8, [rsp+260h+Name]; lpName
0x180015e8d  xor     edx, edx; bInheritHandle
0x180015e8f  mov     ecx, 1F0003h; dwDesiredAccess
0x180015e94  call    cs:__imp_OpenSemaphoreW
0x180015e9a  mov     [rsp+260h+var_230], rax
0x180015e9f  test    rax, rax
0x180015ea2  jnz     short loc_180015ECB
0x180015ea4  call    cs:__imp_GetLastError
0x180015eaa  cmp     eax, 2
0x180015ead  jz      loc_180015FA8
0x180015eb3  mov     rcx, [rbp+168h]; this
0x180015eba  mov     edx, 0D0h; void *
0x180015ebf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180015ec4  mov     ebx, eax
0x180015ec6  jmp     loc_180015FAA
0x180015ecb  lea     rdx, [rsp+260h+var_23C]; int *
0x180015ed0  mov     [rsp+260h+var_23C], 0
0x180015ed8  mov     rcx, rax; hHandle
0x180015edb  mov     [rsp+260h+var_240], 0; int
0x180015ee3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180015ee8  mov     ebx, eax
0x180015eea  test    eax, eax
0x180015eec  jns     short loc_180015F0E
0x180015eee  mov     rcx, [rbp+168h]; this
0x180015ef5  lea     r8, aWil; "wil"
0x180015efc  mov     r9d, eax; char *
0x180015eff  mov     edx, 0D6h; void *
0x180015f04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015f09  jmp     loc_180015FAA
0x180015f0e  lea     r8, asc_18002EC00; "h"
0x180015f15  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180015f1a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180015f1f  lea     r8, [rsp+260h+Name]; lpName
0x180015f24  xor     edx, edx; bInheritHandle
0x180015f26  mov     ecx, 1F0003h; dwDesiredAccess
0x180015f2b  call    cs:__imp_OpenSemaphoreW
0x180015f31  mov     [rsp+260h+var_238], rax
0x180015f36  test    rax, rax
0x180015f39  jnz     short loc_180015F5A
0x180015f3b  mov     rcx, [rbp+168h]; this
0x180015f42  mov     edx, 0DCh; void *
0x180015f47  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180015f4c  mov     ebx, eax
0x180015f4e  lea     rcx, [rsp+260h+var_238]
0x180015f53  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180015f58  jmp     short loc_180015FAA
0x180015f5a  lea     rdx, [rsp+260h+var_240]; int *
0x180015f5f  mov     rcx, rax; hHandle
0x180015f62  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180015f67  mov     ebx, eax
0x180015f69  test    eax, eax
0x180015f6b  jns     short loc_180015F8A
0x180015f6d  mov     rcx, [rbp+168h]; this
0x180015f74  lea     r8, aWil; "wil"
0x180015f7b  mov     r9d, eax; char *
0x180015f7e  mov     edx, 0DEh; void *
0x180015f83  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015f88  jmp     short loc_180015F4E
0x180015f8a  lea     rcx, [rsp+260h+var_238]
0x180015f8f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180015f94  movsxd  rcx, [rsp+260h+var_240]
0x180015f99  movsxd  rax, [rsp+260h+var_23C]
0x180015f9e  shl     rcx, 1Fh
0x180015fa2  or      rcx, rax
0x180015fa5  mov     [rdi], rcx
0x180015fa8  xor     ebx, ebx
0x180015faa  lea     rcx, [rsp+260h+var_230]
0x180015faf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180015fb4  mov     eax, ebx
0x180015fb6  mov     rcx, [rbp+160h+var_10]
0x180015fbd  xor     rcx, rsp; StackCookie
0x180015fc0  call    __security_check_cookie
0x180015fc5  lea     r11, [rsp+260h+var_s0]
0x180015fcd  mov     rbx, [r11+18h]
0x180015fd1  mov     rdi, [r11+28h]
0x180015fd5  mov     rsp, r11
0x180015fd8  pop     rbp
0x180015fd9  retn
```
