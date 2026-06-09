# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180010eec`
- end: `0x180011091`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `421`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000ef04`

## callees

- `0x18000ca90`
- `0x18000ed34`
- `0x18000fb2c`
- `0x180010714`
- `0x180010734`
- `0x180010c60`
- `0x180010cac`
- `0x180010eec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180010f4b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180010fe2`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180010f4b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180010fe2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f5b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010f5b`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
        unsigned __int64 a2,
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
  StringCchCopyW(Name, a2, a1);
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
0x180010eec  mov     [rsp-8+arg_8], rbx
0x180010ef1  mov     [rsp-8+arg_18], rdi
0x180010ef6  push    rbp
0x180010ef7  lea     rbp, [rsp-160h]
0x180010eff  sub     rsp, 260h
0x180010f06  mov     rax, cs:__security_cookie
0x180010f0d  xor     rax, rsp
0x180010f10  mov     [rbp+160h+var_10], rax
0x180010f17  mov     rdi, r8
0x180010f1a  mov     qword ptr [r8], 0
0x180010f21  mov     r8, rcx; wchar_t *
0x180010f24  lea     rcx, [rsp+260h+Name]; wchar_t *
0x180010f29  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180010f2e  lea     r8, aP0; "_p0"
0x180010f35  lea     rcx, [rsp+260h+Name]; wchar_t *
0x180010f3a  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180010f3f  lea     r8, [rsp+260h+Name]; lpName
0x180010f44  xor     edx, edx; bInheritHandle
0x180010f46  mov     ecx, 1F0003h; dwDesiredAccess
0x180010f4b  call    cs:__imp_OpenSemaphoreW
0x180010f51  mov     [rsp+260h+var_230], rax
0x180010f56  test    rax, rax
0x180010f59  jnz     short loc_180010F82
0x180010f5b  call    cs:__imp_GetLastError
0x180010f61  cmp     eax, 2
0x180010f64  jz      loc_18001105F
0x180010f6a  mov     rcx, [rbp+168h]; this
0x180010f71  mov     edx, 0D0h; void *
0x180010f76  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180010f7b  mov     ebx, eax
0x180010f7d  jmp     loc_180011061
0x180010f82  lea     rdx, [rsp+260h+var_23C]; int *
0x180010f87  mov     [rsp+260h+var_23C], 0
0x180010f8f  mov     rcx, rax; hHandle
0x180010f92  mov     [rsp+260h+var_240], 0; int
0x180010f9a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180010f9f  mov     ebx, eax
0x180010fa1  test    eax, eax
0x180010fa3  jns     short loc_180010FC5
0x180010fa5  mov     rcx, [rbp+168h]; this
0x180010fac  lea     r8, aWil; "wil"
0x180010fb3  mov     r9d, eax; char *
0x180010fb6  mov     edx, 0D6h; void *
0x180010fbb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010fc0  jmp     loc_180011061
0x180010fc5  lea     r8, asc_1801689F0; "h"
0x180010fcc  lea     rcx, [rsp+260h+Name]; wchar_t *
0x180010fd1  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180010fd6  lea     r8, [rsp+260h+Name]; lpName
0x180010fdb  xor     edx, edx; bInheritHandle
0x180010fdd  mov     ecx, 1F0003h; dwDesiredAccess
0x180010fe2  call    cs:__imp_OpenSemaphoreW
0x180010fe8  mov     [rsp+260h+var_238], rax
0x180010fed  test    rax, rax
0x180010ff0  jnz     short loc_180011011
0x180010ff2  mov     rcx, [rbp+168h]; this
0x180010ff9  mov     edx, 0DCh; void *
0x180010ffe  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180011003  mov     ebx, eax
0x180011005  lea     rcx, [rsp+260h+var_238]
0x18001100a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001100f  jmp     short loc_180011061
0x180011011  lea     rdx, [rsp+260h+var_240]; int *
0x180011016  mov     rcx, rax; hHandle
0x180011019  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001101e  mov     ebx, eax
0x180011020  test    eax, eax
0x180011022  jns     short loc_180011041
0x180011024  mov     rcx, [rbp+168h]; this
0x18001102b  lea     r8, aWil; "wil"
0x180011032  mov     r9d, eax; char *
0x180011035  mov     edx, 0DEh; void *
0x18001103a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001103f  jmp     short loc_180011005
0x180011041  lea     rcx, [rsp+260h+var_238]
0x180011046  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001104b  movsxd  rcx, [rsp+260h+var_240]
0x180011050  movsxd  rax, [rsp+260h+var_23C]
0x180011055  shl     rcx, 1Fh
0x180011059  or      rcx, rax
0x18001105c  mov     [rdi], rcx
0x18001105f  xor     ebx, ebx
0x180011061  lea     rcx, [rsp+260h+var_230]
0x180011066  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001106b  mov     eax, ebx
0x18001106d  mov     rcx, [rbp+160h+var_10]
0x180011074  xor     rcx, rsp; StackCookie
0x180011077  call    __security_check_cookie
0x18001107c  lea     r11, [rsp+260h+var_s0]
0x180011084  mov     rbx, [r11+18h]
0x180011088  mov     rdi, [r11+28h]
0x18001108c  mov     rsp, r11
0x18001108f  pop     rbp
0x180011090  retn
```
