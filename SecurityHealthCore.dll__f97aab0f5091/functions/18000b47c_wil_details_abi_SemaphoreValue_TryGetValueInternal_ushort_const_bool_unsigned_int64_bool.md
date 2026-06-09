# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000b47c`
- end: `0x18000b634`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000b3f8`

## callees

- `0x180004710`
- `0x1800075c8`
- `0x180008bd8`
- `0x18000a7cc`
- `0x18000a7ec`
- `0x18000aeac`
- `0x18000af28`
- `0x18000b47c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000b4f0`
- `KERNEL32!GetLastError` at `0x18000b4f0`
- `KERNEL32!OpenSemaphoreW` at `0x18000b4e0`
- `KERNEL32!OpenSemaphoreW` at `0x18000b57e`
- `KERNEL32!OpenSemaphoreW` at `0x18000b4e0`
- `KERNEL32!OpenSemaphoreW` at `0x18000b57e`

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
0x18000b47c  mov     [rsp-8+arg_8], rbx
0x18000b481  mov     [rsp-8+arg_18], rdi
0x18000b486  push    rbp
0x18000b487  lea     rbp, [rsp-160h]
0x18000b48f  sub     rsp, 260h
0x18000b496  mov     rax, cs:__security_cookie
0x18000b49d  xor     rax, rsp
0x18000b4a0  mov     [rbp+160h+var_10], rax
0x18000b4a7  mov     rdi, r8
0x18000b4aa  mov     qword ptr [r8], 0
0x18000b4b1  mov     r8, rcx; unsigned __int16 *
0x18000b4b4  mov     edx, 104h; unsigned __int64
0x18000b4b9  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000b4be  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b4c3  lea     r8, aP0; "_p0"
0x18000b4ca  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000b4cf  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b4d4  lea     r8, [rsp+260h+Name]; lpName
0x18000b4d9  xor     edx, edx; bInheritHandle
0x18000b4db  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b4e0  call    cs:__imp_OpenSemaphoreW
0x18000b4e6  mov     [rsp+260h+var_230], rax
0x18000b4eb  test    rax, rax
0x18000b4ee  jnz     short loc_18000B51E
0x18000b4f0  call    cs:__imp_GetLastError
0x18000b4f6  cmp     eax, 2
0x18000b4f9  jz      loc_18000B602
0x18000b4ff  mov     rcx, [rbp+168h]; this
0x18000b506  lea     r8, aWil; "wil"
0x18000b50d  mov     edx, 0D0h; void *
0x18000b512  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b517  mov     ebx, eax
0x18000b519  jmp     loc_18000B604
0x18000b51e  lea     rdx, [rsp+260h+var_23C]; int *
0x18000b523  mov     [rsp+260h+var_23C], 0
0x18000b52b  mov     rcx, rax; hHandle
0x18000b52e  mov     [rsp+260h+var_240], 0; int
0x18000b536  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b53b  mov     ebx, eax
0x18000b53d  test    eax, eax
0x18000b53f  jns     short loc_18000B561
0x18000b541  mov     rcx, [rbp+168h]; this
0x18000b548  lea     r8, aWil; "wil"
0x18000b54f  mov     r9d, eax; char *
0x18000b552  mov     edx, 0D6h; void *
0x18000b557  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b55c  jmp     loc_18000B604
0x18000b561  lea     r8, asc_1800F3C50; "h"
0x18000b568  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000b56d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b572  lea     r8, [rsp+260h+Name]; lpName
0x18000b577  xor     edx, edx; bInheritHandle
0x18000b579  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b57e  call    cs:__imp_OpenSemaphoreW
0x18000b584  mov     [rsp+260h+var_238], rax
0x18000b589  test    rax, rax
0x18000b58c  jnz     short loc_18000B5B4
0x18000b58e  mov     rcx, [rbp+168h]; this
0x18000b595  lea     r8, aWil; "wil"
0x18000b59c  mov     edx, 0DCh; void *
0x18000b5a1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b5a6  mov     ebx, eax
0x18000b5a8  lea     rcx, [rsp+260h+var_238]
0x18000b5ad  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b5b2  jmp     short loc_18000B604
0x18000b5b4  lea     rdx, [rsp+260h+var_240]; int *
0x18000b5b9  mov     rcx, rax; hHandle
0x18000b5bc  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b5c1  mov     ebx, eax
0x18000b5c3  test    eax, eax
0x18000b5c5  jns     short loc_18000B5E4
0x18000b5c7  mov     rcx, [rbp+168h]; this
0x18000b5ce  lea     r8, aWil; "wil"
0x18000b5d5  mov     r9d, eax; char *
0x18000b5d8  mov     edx, 0DEh; void *
0x18000b5dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b5e2  jmp     short loc_18000B5A8
0x18000b5e4  lea     rcx, [rsp+260h+var_238]
0x18000b5e9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b5ee  movsxd  rcx, [rsp+260h+var_240]
0x18000b5f3  movsxd  rax, [rsp+260h+var_23C]
0x18000b5f8  shl     rcx, 1Fh
0x18000b5fc  or      rcx, rax
0x18000b5ff  mov     [rdi], rcx
0x18000b602  xor     ebx, ebx
0x18000b604  lea     rcx, [rsp+260h+var_230]
0x18000b609  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b60e  mov     eax, ebx
0x18000b610  mov     rcx, [rbp+160h+var_10]
0x18000b617  xor     rcx, rsp; StackCookie
0x18000b61a  call    __security_check_cookie
0x18000b61f  lea     r11, [rsp+260h+var_s0]
0x18000b627  mov     rbx, [r11+18h]
0x18000b62b  mov     rdi, [r11+28h]
0x18000b62f  mov     rsp, r11
0x18000b632  pop     rbp
0x18000b633  retn
```
