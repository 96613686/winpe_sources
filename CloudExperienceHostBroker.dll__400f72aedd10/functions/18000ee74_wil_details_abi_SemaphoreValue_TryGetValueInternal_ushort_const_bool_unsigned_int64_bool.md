# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000ee74`
- end: `0x18000f02c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000edf0`

## callees

- `0x180008344`
- `0x180009f30`
- `0x18000ca0c`
- `0x18000d854`
- `0x18000e6f4`
- `0x18000ebd0`
- `0x18000ec4c`
- `0x18000ee74`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000eed8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ef76`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000eed8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ef76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eee8`

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
0x18000ee74  mov     [rsp-8+arg_8], rbx
0x18000ee79  mov     [rsp-8+arg_18], rdi
0x18000ee7e  push    rbp
0x18000ee7f  lea     rbp, [rsp-160h]
0x18000ee87  sub     rsp, 260h
0x18000ee8e  mov     rax, cs:__security_cookie
0x18000ee95  xor     rax, rsp
0x18000ee98  mov     [rbp+160h+var_10], rax
0x18000ee9f  mov     rdi, r8
0x18000eea2  mov     qword ptr [r8], 0
0x18000eea9  mov     r8, rcx; unsigned __int16 *
0x18000eeac  mov     edx, 104h; unsigned __int64
0x18000eeb1  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000eeb6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000eebb  lea     r8, aP0; "_p0"
0x18000eec2  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000eec7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000eecc  lea     r8, [rsp+260h+Name]; lpName
0x18000eed1  xor     edx, edx; bInheritHandle
0x18000eed3  mov     ecx, 1F0003h; dwDesiredAccess
0x18000eed8  call    cs:__imp_OpenSemaphoreW
0x18000eede  mov     [rsp+260h+var_230], rax
0x18000eee3  test    rax, rax
0x18000eee6  jnz     short loc_18000EF16
0x18000eee8  call    cs:__imp_GetLastError
0x18000eeee  cmp     eax, 2
0x18000eef1  jz      loc_18000EFFA
0x18000eef7  mov     rcx, [rbp+168h]; this
0x18000eefe  lea     r8, aWil; "wil"
0x18000ef05  mov     edx, 0D0h; void *
0x18000ef0a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ef0f  mov     ebx, eax
0x18000ef11  jmp     loc_18000EFFC
0x18000ef16  lea     rdx, [rsp+260h+var_23C]; int *
0x18000ef1b  mov     [rsp+260h+var_23C], 0
0x18000ef23  mov     rcx, rax; hHandle
0x18000ef26  mov     [rsp+260h+var_240], 0; int
0x18000ef2e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000ef33  mov     ebx, eax
0x18000ef35  test    eax, eax
0x18000ef37  jns     short loc_18000EF59
0x18000ef39  mov     rcx, [rbp+168h]; this
0x18000ef40  lea     r8, aWil; "wil"
0x18000ef47  mov     r9d, eax; char *
0x18000ef4a  mov     edx, 0D6h; void *
0x18000ef4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ef54  jmp     loc_18000EFFC
0x18000ef59  lea     r8, asc_180041BA0; "h"
0x18000ef60  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000ef65  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ef6a  lea     r8, [rsp+260h+Name]; lpName
0x18000ef6f  xor     edx, edx; bInheritHandle
0x18000ef71  mov     ecx, 1F0003h; dwDesiredAccess
0x18000ef76  call    cs:__imp_OpenSemaphoreW
0x18000ef7c  mov     [rsp+260h+var_238], rax
0x18000ef81  test    rax, rax
0x18000ef84  jnz     short loc_18000EFAC
0x18000ef86  mov     rcx, [rbp+168h]; this
0x18000ef8d  lea     r8, aWil; "wil"
0x18000ef94  mov     edx, 0DCh; void *
0x18000ef99  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ef9e  mov     ebx, eax
0x18000efa0  lea     rcx, [rsp+260h+var_238]
0x18000efa5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000efaa  jmp     short loc_18000EFFC
0x18000efac  lea     rdx, [rsp+260h+var_240]; int *
0x18000efb1  mov     rcx, rax; hHandle
0x18000efb4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000efb9  mov     ebx, eax
0x18000efbb  test    eax, eax
0x18000efbd  jns     short loc_18000EFDC
0x18000efbf  mov     rcx, [rbp+168h]; this
0x18000efc6  lea     r8, aWil; "wil"
0x18000efcd  mov     r9d, eax; char *
0x18000efd0  mov     edx, 0DEh; void *
0x18000efd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000efda  jmp     short loc_18000EFA0
0x18000efdc  lea     rcx, [rsp+260h+var_238]
0x18000efe1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000efe6  movsxd  rcx, [rsp+260h+var_240]
0x18000efeb  movsxd  rax, [rsp+260h+var_23C]
0x18000eff0  shl     rcx, 1Fh
0x18000eff4  or      rcx, rax
0x18000eff7  mov     [rdi], rcx
0x18000effa  xor     ebx, ebx
0x18000effc  lea     rcx, [rsp+260h+var_230]
0x18000f001  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f006  mov     eax, ebx
0x18000f008  mov     rcx, [rbp+160h+var_10]
0x18000f00f  xor     rcx, rsp; StackCookie
0x18000f012  call    __security_check_cookie
0x18000f017  lea     r11, [rsp+260h+var_s0]
0x18000f01f  mov     rbx, [r11+18h]
0x18000f023  mov     rdi, [r11+28h]
0x18000f027  mov     rsp, r11
0x18000f02a  pop     rbp
0x18000f02b  retn
```
