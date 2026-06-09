# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x140005988`
- end: `0x140005b38`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `432`
- prototype: `__int64 __fastcall(wchar_t *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140005904`

## callees

- `0x140002310`
- `0x140003cb4`
- `0x14000491c`
- `0x1400053a0`
- `0x1400053c0`
- `0x1400056c8`
- `0x140005754`
- `0x140005988`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400059f1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005a8a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1400059f1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140005a8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005a01`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140005a01`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        wchar_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  wil::details *v5; // rax
  void *v6; // rdx
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  wil::details *v11; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  void *v14; // rdx
  int v15; // eax
  void *v16; // rdx
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v20; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v21; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v5;
  if ( v5 )
  {
    v19 = 0;
    v18 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v19);
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
    v11 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v20 = v11;
    if ( v11 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v18);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v20,
          v16);
        *a3 = v19 | (unsigned __int64)((__int64)v18 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v12, v13);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v20,
      v14);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v21,
    v6);
  return LastError;
}

```

## disassembly

```asm
0x140005988  mov     [rsp-8+arg_8], rbx
0x14000598d  push    rbp
0x14000598e  push    rdi
0x14000598f  push    r14
0x140005991  lea     rbp, [rsp-160h]
0x140005999  sub     rsp, 260h
0x1400059a0  mov     rax, cs:__security_cookie
0x1400059a7  xor     rax, rsp
0x1400059aa  mov     [rbp+170h+var_20], rax
0x1400059b1  mov     rdi, r8
0x1400059b4  mov     qword ptr [r8], 0
0x1400059bb  mov     r8, rcx; wchar_t *
0x1400059be  mov     r14d, 104h
0x1400059c4  mov     edx, r14d; unsigned __int64
0x1400059c7  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1400059cc  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400059d1  lea     r8, aP0; "_p0"
0x1400059d8  mov     edx, r14d; unsigned __int64
0x1400059db  lea     rcx, [rsp+270h+Name]; wchar_t *
0x1400059e0  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x1400059e5  lea     r8, [rsp+270h+Name]; lpName
0x1400059ea  xor     edx, edx; bInheritHandle
0x1400059ec  mov     ecx, 1F0003h; dwDesiredAccess
0x1400059f1  call    cs:__imp_OpenSemaphoreW
0x1400059f7  mov     [rsp+270h+var_240], rax
0x1400059fc  test    rax, rax
0x1400059ff  jnz     short loc_140005A27
0x140005a01  call    cs:__imp_GetLastError
0x140005a07  cmp     eax, 2
0x140005a0a  jz      loc_140005B07
0x140005a10  mov     rcx, [rbp+178h]; this
0x140005a17  lea     edx, [r14-34h]; void *
0x140005a1b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005a20  mov     ebx, eax
0x140005a22  jmp     loc_140005B09
0x140005a27  lea     rdx, [rsp+270h+var_24C]; int *
0x140005a2c  mov     [rsp+270h+var_24C], 0
0x140005a34  mov     rcx, rax; hHandle
0x140005a37  mov     [rsp+270h+var_250], 0; int
0x140005a3f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005a44  mov     ebx, eax
0x140005a46  test    eax, eax
0x140005a48  jns     short loc_140005A6A
0x140005a4a  mov     rcx, [rbp+178h]; this
0x140005a51  lea     r8, aWil; "wil"
0x140005a58  mov     r9d, eax; char *
0x140005a5b  mov     edx, 0D6h; void *
0x140005a60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005a65  jmp     loc_140005B09
0x140005a6a  lea     r8, asc_14002EB90; "h"
0x140005a71  mov     rdx, r14; unsigned __int64
0x140005a74  lea     rcx, [rsp+270h+Name]; wchar_t *
0x140005a79  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140005a7e  lea     r8, [rsp+270h+Name]; lpName
0x140005a83  xor     edx, edx; bInheritHandle
0x140005a85  mov     ecx, 1F0003h; dwDesiredAccess
0x140005a8a  call    cs:__imp_OpenSemaphoreW
0x140005a90  mov     [rsp+270h+var_248], rax
0x140005a95  test    rax, rax
0x140005a98  jnz     short loc_140005AB9
0x140005a9a  mov     rcx, [rbp+178h]; this
0x140005aa1  mov     edx, 0DCh; void *
0x140005aa6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005aab  mov     ebx, eax
0x140005aad  lea     rcx, [rsp+270h+var_248]
0x140005ab2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140005ab7  jmp     short loc_140005B09
0x140005ab9  lea     rdx, [rsp+270h+var_250]; int *
0x140005abe  mov     rcx, rax; hHandle
0x140005ac1  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005ac6  mov     ebx, eax
0x140005ac8  test    eax, eax
0x140005aca  jns     short loc_140005AE9
0x140005acc  mov     rcx, [rbp+178h]; this
0x140005ad3  lea     r8, aWil; "wil"
0x140005ada  mov     r9d, eax; char *
0x140005add  mov     edx, 0DEh; void *
0x140005ae2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005ae7  jmp     short loc_140005AAD
0x140005ae9  lea     rcx, [rsp+270h+var_248]
0x140005aee  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140005af3  movsxd  rcx, [rsp+270h+var_250]
0x140005af8  movsxd  rax, [rsp+270h+var_24C]
0x140005afd  shl     rcx, 1Fh
0x140005b01  or      rcx, rax
0x140005b04  mov     [rdi], rcx
0x140005b07  xor     ebx, ebx
0x140005b09  lea     rcx, [rsp+270h+var_240]
0x140005b0e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140005b13  mov     eax, ebx
0x140005b15  mov     rcx, [rbp+170h+var_20]
0x140005b1c  xor     rcx, rsp; StackCookie
0x140005b1f  call    __security_check_cookie
0x140005b24  mov     rbx, [rsp+270h+arg_8]
0x140005b2c  add     rsp, 260h
0x140005b33  pop     r14
0x140005b35  pop     rdi
0x140005b36  pop     rbp
0x140005b37  retn
```
