# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180027980`
- end: `0x180027b2a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800278fc`

## callees

- `0x180013cbc`
- `0x180018e9c`
- `0x18001bbe0`
- `0x18001f1e8`
- `0x180022c24`
- `0x180025a14`
- `0x180025a34`
- `0x180027980`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800279e4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180027a7b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800279e4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180027a7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800279f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800279f4`

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
0x180027980  mov     [rsp-8+arg_8], rbx
0x180027985  mov     [rsp-8+arg_18], rdi
0x18002798a  push    rbp
0x18002798b  lea     rbp, [rsp-160h]
0x180027993  sub     rsp, 260h
0x18002799a  mov     rax, cs:__security_cookie
0x1800279a1  xor     rax, rsp
0x1800279a4  mov     [rbp+160h+var_10], rax
0x1800279ab  mov     rdi, r8
0x1800279ae  mov     qword ptr [r8], 0
0x1800279b5  mov     r8, rcx; unsigned __int16 *
0x1800279b8  mov     edx, 104h; unsigned __int64
0x1800279bd  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800279c2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800279c7  lea     r8, aP0; "_p0"
0x1800279ce  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800279d3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800279d8  lea     r8, [rsp+260h+Name]; lpName
0x1800279dd  xor     edx, edx; bInheritHandle
0x1800279df  mov     ecx, 1F0003h; dwDesiredAccess
0x1800279e4  call    cs:__imp_OpenSemaphoreW
0x1800279ea  mov     [rsp+260h+var_230], rax
0x1800279ef  test    rax, rax
0x1800279f2  jnz     short loc_180027A1B
0x1800279f4  call    cs:__imp_GetLastError
0x1800279fa  cmp     eax, 2
0x1800279fd  jz      loc_180027AF8
0x180027a03  mov     rcx, [rbp+168h]; this
0x180027a0a  mov     edx, 0D0h; void *
0x180027a0f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180027a14  mov     ebx, eax
0x180027a16  jmp     loc_180027AFA
0x180027a1b  lea     rdx, [rsp+260h+var_23C]; int *
0x180027a20  mov     [rsp+260h+var_23C], 0
0x180027a28  mov     rcx, rax; hHandle
0x180027a2b  mov     [rsp+260h+var_240], 0; int
0x180027a33  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180027a38  mov     ebx, eax
0x180027a3a  test    eax, eax
0x180027a3c  jns     short loc_180027A5E
0x180027a3e  mov     rcx, [rbp+168h]; this
0x180027a45  lea     r8, aWil; "wil"
0x180027a4c  mov     r9d, eax; char *
0x180027a4f  mov     edx, 0D6h; void *
0x180027a54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027a59  jmp     loc_180027AFA
0x180027a5e  lea     r8, asc_1800361A8; "h"
0x180027a65  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180027a6a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180027a6f  lea     r8, [rsp+260h+Name]; lpName
0x180027a74  xor     edx, edx; bInheritHandle
0x180027a76  mov     ecx, 1F0003h; dwDesiredAccess
0x180027a7b  call    cs:__imp_OpenSemaphoreW
0x180027a81  mov     [rsp+260h+var_238], rax
0x180027a86  test    rax, rax
0x180027a89  jnz     short loc_180027AAA
0x180027a8b  mov     rcx, [rbp+168h]; this
0x180027a92  mov     edx, 0DCh; void *
0x180027a97  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180027a9c  mov     ebx, eax
0x180027a9e  lea     rcx, [rsp+260h+var_238]
0x180027aa3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027aa8  jmp     short loc_180027AFA
0x180027aaa  lea     rdx, [rsp+260h+var_240]; int *
0x180027aaf  mov     rcx, rax; hHandle
0x180027ab2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180027ab7  mov     ebx, eax
0x180027ab9  test    eax, eax
0x180027abb  jns     short loc_180027ADA
0x180027abd  mov     rcx, [rbp+168h]; this
0x180027ac4  lea     r8, aWil; "wil"
0x180027acb  mov     r9d, eax; char *
0x180027ace  mov     edx, 0DEh; void *
0x180027ad3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027ad8  jmp     short loc_180027A9E
0x180027ada  lea     rcx, [rsp+260h+var_238]
0x180027adf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027ae4  movsxd  rcx, [rsp+260h+var_240]
0x180027ae9  movsxd  rax, [rsp+260h+var_23C]
0x180027aee  shl     rcx, 1Fh
0x180027af2  or      rcx, rax
0x180027af5  mov     [rdi], rcx
0x180027af8  xor     ebx, ebx
0x180027afa  lea     rcx, [rsp+260h+var_230]
0x180027aff  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027b04  mov     eax, ebx
0x180027b06  mov     rcx, [rbp+160h+var_10]
0x180027b0d  xor     rcx, rsp; StackCookie
0x180027b10  call    __security_check_cookie
0x180027b15  lea     r11, [rsp+260h+var_s0]
0x180027b1d  mov     rbx, [r11+18h]
0x180027b21  mov     rdi, [r11+28h]
0x180027b25  mov     rsp, r11
0x180027b28  pop     rbp
0x180027b29  retn
```
