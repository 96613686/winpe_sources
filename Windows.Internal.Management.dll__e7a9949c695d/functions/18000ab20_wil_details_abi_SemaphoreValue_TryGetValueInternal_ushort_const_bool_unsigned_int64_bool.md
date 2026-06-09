# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000ab20`
- end: `0x18000acd8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000aa9c`

## callees

- `0x180004d50`
- `0x180008880`
- `0x180009610`
- `0x18000a284`
- `0x18000a2a4`
- `0x18000a7c0`
- `0x18000a8a4`
- `0x18000ab20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ab84`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ac22`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ab84`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ac22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ab94`

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
0x18000ab20  mov     [rsp-8+arg_8], rbx
0x18000ab25  mov     [rsp-8+arg_18], rdi
0x18000ab2a  push    rbp
0x18000ab2b  lea     rbp, [rsp-160h]
0x18000ab33  sub     rsp, 260h
0x18000ab3a  mov     rax, cs:__security_cookie
0x18000ab41  xor     rax, rsp
0x18000ab44  mov     [rbp+160h+var_10], rax
0x18000ab4b  mov     rdi, r8
0x18000ab4e  mov     qword ptr [r8], 0
0x18000ab55  mov     r8, rcx; unsigned __int16 *
0x18000ab58  mov     edx, 104h; unsigned __int64
0x18000ab5d  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000ab62  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ab67  lea     r8, aP0; "_p0"
0x18000ab6e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000ab73  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ab78  lea     r8, [rsp+260h+Name]; lpName
0x18000ab7d  xor     edx, edx; bInheritHandle
0x18000ab7f  mov     ecx, 1F0003h; dwDesiredAccess
0x18000ab84  call    cs:__imp_OpenSemaphoreW
0x18000ab8a  mov     [rsp+260h+var_230], rax
0x18000ab8f  test    rax, rax
0x18000ab92  jnz     short loc_18000ABC2
0x18000ab94  call    cs:__imp_GetLastError
0x18000ab9a  cmp     eax, 2
0x18000ab9d  jz      loc_18000ACA6
0x18000aba3  mov     rcx, [rbp+168h]; this
0x18000abaa  lea     r8, aWil; "wil"
0x18000abb1  mov     edx, 0D0h; void *
0x18000abb6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000abbb  mov     ebx, eax
0x18000abbd  jmp     loc_18000ACA8
0x18000abc2  lea     rdx, [rsp+260h+var_23C]; int *
0x18000abc7  mov     [rsp+260h+var_23C], 0
0x18000abcf  mov     rcx, rax; hHandle
0x18000abd2  mov     [rsp+260h+var_240], 0; int
0x18000abda  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000abdf  mov     ebx, eax
0x18000abe1  test    eax, eax
0x18000abe3  jns     short loc_18000AC05
0x18000abe5  mov     rcx, [rbp+168h]; this
0x18000abec  lea     r8, aWil; "wil"
0x18000abf3  mov     r9d, eax; char *
0x18000abf6  mov     edx, 0D6h; void *
0x18000abfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ac00  jmp     loc_18000ACA8
0x18000ac05  lea     r8, asc_1800D1188; "h"
0x18000ac0c  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000ac11  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ac16  lea     r8, [rsp+260h+Name]; lpName
0x18000ac1b  xor     edx, edx; bInheritHandle
0x18000ac1d  mov     ecx, 1F0003h; dwDesiredAccess
0x18000ac22  call    cs:__imp_OpenSemaphoreW
0x18000ac28  mov     [rsp+260h+var_238], rax
0x18000ac2d  test    rax, rax
0x18000ac30  jnz     short loc_18000AC58
0x18000ac32  mov     rcx, [rbp+168h]; this
0x18000ac39  lea     r8, aWil; "wil"
0x18000ac40  mov     edx, 0DCh; void *
0x18000ac45  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ac4a  mov     ebx, eax
0x18000ac4c  lea     rcx, [rsp+260h+var_238]
0x18000ac51  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ac56  jmp     short loc_18000ACA8
0x18000ac58  lea     rdx, [rsp+260h+var_240]; int *
0x18000ac5d  mov     rcx, rax; hHandle
0x18000ac60  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000ac65  mov     ebx, eax
0x18000ac67  test    eax, eax
0x18000ac69  jns     short loc_18000AC88
0x18000ac6b  mov     rcx, [rbp+168h]; this
0x18000ac72  lea     r8, aWil; "wil"
0x18000ac79  mov     r9d, eax; char *
0x18000ac7c  mov     edx, 0DEh; void *
0x18000ac81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ac86  jmp     short loc_18000AC4C
0x18000ac88  lea     rcx, [rsp+260h+var_238]
0x18000ac8d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ac92  movsxd  rcx, [rsp+260h+var_240]
0x18000ac97  movsxd  rax, [rsp+260h+var_23C]
0x18000ac9c  shl     rcx, 1Fh
0x18000aca0  or      rcx, rax
0x18000aca3  mov     [rdi], rcx
0x18000aca6  xor     ebx, ebx
0x18000aca8  lea     rcx, [rsp+260h+var_230]
0x18000acad  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000acb2  mov     eax, ebx
0x18000acb4  mov     rcx, [rbp+160h+var_10]
0x18000acbb  xor     rcx, rsp; StackCookie
0x18000acbe  call    __security_check_cookie
0x18000acc3  lea     r11, [rsp+260h+var_s0]
0x18000accb  mov     rbx, [r11+18h]
0x18000accf  mov     rdi, [r11+28h]
0x18000acd3  mov     rsp, r11
0x18000acd6  pop     rbp
0x18000acd7  retn
```
