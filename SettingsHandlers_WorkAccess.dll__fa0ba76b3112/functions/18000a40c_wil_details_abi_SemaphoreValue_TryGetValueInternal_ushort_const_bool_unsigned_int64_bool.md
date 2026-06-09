# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000a40c`
- end: `0x18000a5d7`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `459`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000a388`

## callees

- `0x180002a60`
- `0x1800055cc`
- `0x180007344`
- `0x1800096cc`
- `0x1800096ec`
- `0x180009de8`
- `0x180009e68`
- `0x18000a40c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a470`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a51a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a470`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a51a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a486`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a486`

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
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v10; // rdx
  HANDLE v11; // rax
  const char *v12; // r9
  int v13; // eax
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v17; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18[0] = v6;
  if ( v6 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v16);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v15);
      goto LABEL_13;
    }
    StringCchCatW(Name, v10, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v17 = v11;
    if ( v11 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v15);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
        *a3 = v16 | (unsigned __int64)((__int64)v15 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v12);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x18000a40c  mov     [rsp-8+arg_8], rbx
0x18000a411  mov     [rsp-8+arg_18], rdi
0x18000a416  push    rbp
0x18000a417  lea     rbp, [rsp-160h]
0x18000a41f  sub     rsp, 260h
0x18000a426  mov     rax, cs:__security_cookie
0x18000a42d  xor     rax, rsp
0x18000a430  mov     [rbp+160h+var_10], rax
0x18000a437  mov     rdi, r8
0x18000a43a  mov     qword ptr [r8], 0
0x18000a441  mov     r8, rcx; unsigned __int16 *
0x18000a444  mov     edx, 104h; unsigned __int64
0x18000a449  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000a44e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a453  lea     r8, aP0; "_p0"
0x18000a45a  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000a45f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a464  lea     r8, [rsp+260h+Name]; lpName
0x18000a469  xor     edx, edx; bInheritHandle
0x18000a46b  mov     ecx, 1F0003h; dwDesiredAccess
0x18000a470  call    cs:__imp_OpenSemaphoreW
0x18000a477  nop     dword ptr [rax+rax+00h]
0x18000a47c  mov     [rsp+260h+var_230], rax
0x18000a481  test    rax, rax
0x18000a484  jnz     short loc_18000A4BA
0x18000a486  call    cs:__imp_GetLastError
0x18000a48d  nop     dword ptr [rax+rax+00h]
0x18000a492  cmp     eax, 2
0x18000a495  jz      loc_18000A5A4
0x18000a49b  mov     rcx, [rbp+168h]; this
0x18000a4a2  lea     r8, aWil; "wil"
0x18000a4a9  mov     edx, 0D0h; void *
0x18000a4ae  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a4b3  mov     ebx, eax
0x18000a4b5  jmp     loc_18000A5A6
0x18000a4ba  lea     rdx, [rsp+260h+var_23C]; int *
0x18000a4bf  mov     [rsp+260h+var_23C], 0
0x18000a4c7  mov     rcx, rax; hHandle
0x18000a4ca  mov     [rsp+260h+var_240], 0; int
0x18000a4d2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a4d7  mov     ebx, eax
0x18000a4d9  test    eax, eax
0x18000a4db  jns     short loc_18000A4FD
0x18000a4dd  mov     rcx, [rbp+168h]; this
0x18000a4e4  lea     r8, aWil; "wil"
0x18000a4eb  mov     r9d, eax; char *
0x18000a4ee  mov     edx, 0D6h; void *
0x18000a4f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a4f8  jmp     loc_18000A5A6
0x18000a4fd  lea     r8, asc_18005A2E8; "h"
0x18000a504  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000a509  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a50e  lea     r8, [rsp+260h+Name]; lpName
0x18000a513  xor     edx, edx; bInheritHandle
0x18000a515  mov     ecx, 1F0003h; dwDesiredAccess
0x18000a51a  call    cs:__imp_OpenSemaphoreW
0x18000a521  nop     dword ptr [rax+rax+00h]
0x18000a526  mov     [rsp+260h+var_238], rax
0x18000a52b  test    rax, rax
0x18000a52e  jnz     short loc_18000A556
0x18000a530  mov     rcx, [rbp+168h]; this
0x18000a537  lea     r8, aWil; "wil"
0x18000a53e  mov     edx, 0DCh; void *
0x18000a543  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a548  mov     ebx, eax
0x18000a54a  lea     rcx, [rsp+260h+var_238]
0x18000a54f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a554  jmp     short loc_18000A5A6
0x18000a556  lea     rdx, [rsp+260h+var_240]; int *
0x18000a55b  mov     rcx, rax; hHandle
0x18000a55e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a563  mov     ebx, eax
0x18000a565  test    eax, eax
0x18000a567  jns     short loc_18000A586
0x18000a569  mov     rcx, [rbp+168h]; this
0x18000a570  lea     r8, aWil; "wil"
0x18000a577  mov     r9d, eax; char *
0x18000a57a  mov     edx, 0DEh; void *
0x18000a57f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a584  jmp     short loc_18000A54A
0x18000a586  lea     rcx, [rsp+260h+var_238]
0x18000a58b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a590  movsxd  rcx, [rsp+260h+var_240]
0x18000a595  movsxd  rax, [rsp+260h+var_23C]
0x18000a59a  shl     rcx, 1Fh
0x18000a59e  or      rcx, rax
0x18000a5a1  mov     [rdi], rcx
0x18000a5a4  xor     ebx, ebx
0x18000a5a6  lea     rcx, [rsp+260h+var_230]
0x18000a5ab  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a5b0  mov     eax, ebx
0x18000a5b2  mov     rcx, [rbp+160h+var_10]
0x18000a5b9  xor     rcx, rsp; StackCookie
0x18000a5bc  call    __security_check_cookie
0x18000a5c1  lea     r11, [rsp+260h+var_s0]
0x18000a5c9  mov     rbx, [r11+18h]
0x18000a5cd  mov     rdi, [r11+28h]
0x18000a5d1  mov     rsp, r11
0x18000a5d4  pop     rbp
0x18000a5d5  retn
```
