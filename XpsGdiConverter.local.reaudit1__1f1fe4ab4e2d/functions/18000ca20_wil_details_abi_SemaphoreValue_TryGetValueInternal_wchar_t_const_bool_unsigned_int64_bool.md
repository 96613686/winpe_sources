# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000ca20`
- end: `0x18000cbbc`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000c9ac`

## callees

- `0x180008830`
- `0x18000aacc`
- `0x18000b7fc`
- `0x18000c244`
- `0x18000c264`
- `0x18000c780`
- `0x18000c7fc`
- `0x18000ca20`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x18000ca84`
- `KERNEL32!OpenSemaphoreW` at `0x18000cb14`
- `KERNEL32!OpenSemaphoreW` at `0x18000ca84`
- `KERNEL32!OpenSemaphoreW` at `0x18000cb14`
- `KERNEL32!GetLastError` at `0x18000ca94`
- `KERNEL32!GetLastError` at `0x18000ca94`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
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
  unsigned int v12; // r8d
  HANDLE v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  unsigned int v17; // r8d
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v21; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v22[0] = v6;
  if ( v6 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v20);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v19);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v21 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v19);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v19);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
  return LastError;
}

```

## disassembly

```asm
0x18000ca20  mov     [rsp-8+arg_8], rbx
0x18000ca25  mov     [rsp-8+arg_18], rdi
0x18000ca2a  push    rbp
0x18000ca2b  lea     rbp, [rsp-160h]
0x18000ca33  sub     rsp, 260h
0x18000ca3a  mov     rax, cs:__security_cookie
0x18000ca41  xor     rax, rsp
0x18000ca44  mov     [rbp+160h+var_10], rax
0x18000ca4b  mov     rdi, r8
0x18000ca4e  mov     qword ptr [r8], 0
0x18000ca55  mov     r8, rcx; wchar_t *
0x18000ca58  mov     edx, 104h; unsigned __int64
0x18000ca5d  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18000ca62  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000ca67  lea     r8, aP0; "_p0"
0x18000ca6e  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18000ca73  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000ca78  lea     r8, [rsp+260h+Name]; lpName
0x18000ca7d  xor     edx, edx; bInheritHandle
0x18000ca7f  mov     ecx, 1F0003h; dwDesiredAccess
0x18000ca84  call    cs:__imp_OpenSemaphoreW
0x18000ca8a  mov     [rsp+260h+var_230], rax
0x18000ca8f  test    rax, rax
0x18000ca92  jnz     short loc_18000CABB
0x18000ca94  call    cs:__imp_GetLastError
0x18000ca9a  cmp     eax, 2
0x18000ca9d  jz      loc_18000CB8A
0x18000caa3  mov     rcx, [rbp+168h]; this
0x18000caaa  mov     edx, 0D0h; void *
0x18000caaf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000cab4  mov     ebx, eax
0x18000cab6  jmp     loc_18000CB8C
0x18000cabb  lea     rdx, [rsp+260h+var_23C]; int *
0x18000cac0  mov     [rsp+260h+var_23C], 0
0x18000cac8  mov     rcx, rax; hHandle
0x18000cacb  mov     [rsp+260h+var_240], 0; int
0x18000cad3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000cad8  mov     ebx, eax
0x18000cada  test    eax, eax
0x18000cadc  jns     short loc_18000CAF7
0x18000cade  mov     rcx, [rbp+168h]; this
0x18000cae5  mov     r9d, eax; char *
0x18000cae8  mov     edx, 0D6h; void *
0x18000caed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000caf2  jmp     loc_18000CB8C
0x18000caf7  lea     r8, asc_18004CEB0; "h"
0x18000cafe  lea     rcx, [rsp+260h+Name]; wchar_t *
0x18000cb03  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18000cb08  lea     r8, [rsp+260h+Name]; lpName
0x18000cb0d  xor     edx, edx; bInheritHandle
0x18000cb0f  mov     ecx, 1F0003h; dwDesiredAccess
0x18000cb14  call    cs:__imp_OpenSemaphoreW
0x18000cb1a  mov     [rsp+260h+var_238], rax
0x18000cb1f  test    rax, rax
0x18000cb22  jnz     short loc_18000CB43
0x18000cb24  mov     rcx, [rbp+168h]; this
0x18000cb2b  mov     edx, 0DCh; void *
0x18000cb30  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000cb35  mov     ebx, eax
0x18000cb37  lea     rcx, [rsp+260h+var_238]
0x18000cb3c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000cb41  jmp     short loc_18000CB8C
0x18000cb43  lea     rdx, [rsp+260h+var_240]; int *
0x18000cb48  mov     rcx, rax; hHandle
0x18000cb4b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000cb50  mov     ebx, eax
0x18000cb52  test    eax, eax
0x18000cb54  jns     short loc_18000CB6C
0x18000cb56  mov     rcx, [rbp+168h]; this
0x18000cb5d  mov     r9d, eax; char *
0x18000cb60  mov     edx, 0DEh; void *
0x18000cb65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cb6a  jmp     short loc_18000CB37
0x18000cb6c  lea     rcx, [rsp+260h+var_238]
0x18000cb71  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000cb76  movsxd  rcx, [rsp+260h+var_240]
0x18000cb7b  movsxd  rax, [rsp+260h+var_23C]
0x18000cb80  shl     rcx, 1Fh
0x18000cb84  or      rcx, rax
0x18000cb87  mov     [rdi], rcx
0x18000cb8a  xor     ebx, ebx
0x18000cb8c  lea     rcx, [rsp+260h+var_230]
0x18000cb91  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000cb96  mov     eax, ebx
0x18000cb98  mov     rcx, [rbp+160h+var_10]
0x18000cb9f  xor     rcx, rsp; StackCookie
0x18000cba2  call    __security_check_cookie
0x18000cba7  lea     r11, [rsp+260h+var_s0]
0x18000cbaf  mov     rbx, [r11+18h]
0x18000cbb3  mov     rdi, [r11+28h]
0x18000cbb7  mov     rsp, r11
0x18000cbba  pop     rbp
0x18000cbbb  retn
```
