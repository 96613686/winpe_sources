# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180007910`
- end: `0x180007aac`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000ca58`

## callees

- `0x180006024`
- `0x180007224`
- `0x180007254`
- `0x180007910`
- `0x180007ab4`
- `0x180007e2c`
- `0x18000b6e4`
- `0x18000d300`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007974`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007a04`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007974`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007a04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007984`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007984`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
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
  size_t v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+20h] [rbp-E0h]
  int v21; // [rsp+30h] [rbp-D0h] BYREF
  int v22; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v23; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v24[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v19);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v24[0] = v6;
  if ( v6 )
  {
    v22 = 0;
    v21 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v22);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v20);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v23 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v21);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
        *a3 = v22 | (unsigned __int64)((__int64)v21 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v20);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v24);
  return LastError;
}

```

## disassembly

```asm
0x180007910  mov     [rsp-8+arg_8], rbx
0x180007915  mov     [rsp-8+arg_18], rdi
0x18000791a  push    rbp
0x18000791b  lea     rbp, [rsp-170h]
0x180007923  sub     rsp, 270h
0x18000792a  mov     rax, cs:__security_cookie
0x180007931  xor     rax, rsp
0x180007934  mov     [rbp+170h+var_10], rax
0x18000793b  mov     r9, rcx; pszSrc
0x18000793e  mov     qword ptr [r8], 0
0x180007945  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18000794a  mov     edx, 104h; cchDest
0x18000794f  mov     rdi, r8
0x180007952  call    StringCopyWorkerW
0x180007957  lea     r8, aP0; "_p0"
0x18000795e  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180007963  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007968  lea     r8, [rsp+270h+pszDest]; lpName
0x18000796d  xor     edx, edx; bInheritHandle
0x18000796f  mov     ecx, 1F0003h; dwDesiredAccess
0x180007974  call    cs:__imp_OpenSemaphoreW
0x18000797a  mov     [rsp+270h+var_230], rax
0x18000797f  test    rax, rax
0x180007982  jnz     short loc_1800079AB
0x180007984  call    cs:__imp_GetLastError
0x18000798a  cmp     eax, 2
0x18000798d  jz      loc_180007A7A
0x180007993  mov     rcx, [rbp+178h]; this
0x18000799a  mov     edx, 0D0h; void *
0x18000799f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800079a4  mov     ebx, eax
0x1800079a6  jmp     loc_180007A7C
0x1800079ab  lea     rdx, [rsp+270h+var_23C]; int *
0x1800079b0  mov     [rsp+270h+var_23C], 0
0x1800079b8  mov     rcx, rax; hHandle
0x1800079bb  mov     [rsp+270h+var_240], 0
0x1800079c3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800079c8  mov     ebx, eax
0x1800079ca  test    eax, eax
0x1800079cc  jns     short loc_1800079E7
0x1800079ce  mov     rcx, [rbp+178h]; this
0x1800079d5  mov     r9d, eax; char *
0x1800079d8  mov     edx, 0D6h; void *
0x1800079dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800079e2  jmp     loc_180007A7C
0x1800079e7  lea     r8, asc_18000FA98; "h"
0x1800079ee  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800079f3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800079f8  lea     r8, [rsp+270h+pszDest]; lpName
0x1800079fd  xor     edx, edx; bInheritHandle
0x1800079ff  mov     ecx, 1F0003h; dwDesiredAccess
0x180007a04  call    cs:__imp_OpenSemaphoreW
0x180007a0a  mov     [rsp+270h+var_238], rax
0x180007a0f  test    rax, rax
0x180007a12  jnz     short loc_180007A33
0x180007a14  mov     rcx, [rbp+178h]; this
0x180007a1b  mov     edx, 0DCh; void *
0x180007a20  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007a25  mov     ebx, eax
0x180007a27  lea     rcx, [rsp+270h+var_238]
0x180007a2c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007a31  jmp     short loc_180007A7C
0x180007a33  lea     rdx, [rsp+270h+var_240]; int *
0x180007a38  mov     rcx, rax; hHandle
0x180007a3b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007a40  mov     ebx, eax
0x180007a42  test    eax, eax
0x180007a44  jns     short loc_180007A5C
0x180007a46  mov     rcx, [rbp+178h]; this
0x180007a4d  mov     r9d, eax; char *
0x180007a50  mov     edx, 0DEh; void *
0x180007a55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007a5a  jmp     short loc_180007A27
0x180007a5c  lea     rcx, [rsp+270h+var_238]
0x180007a61  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007a66  movsxd  rcx, [rsp+270h+var_240]
0x180007a6b  movsxd  rax, [rsp+270h+var_23C]
0x180007a70  shl     rcx, 1Fh
0x180007a74  or      rcx, rax
0x180007a77  mov     [rdi], rcx
0x180007a7a  xor     ebx, ebx
0x180007a7c  lea     rcx, [rsp+270h+var_230]
0x180007a81  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007a86  mov     eax, ebx
0x180007a88  mov     rcx, [rbp+170h+var_10]
0x180007a8f  xor     rcx, rsp; StackCookie
0x180007a92  call    __security_check_cookie
0x180007a97  lea     r11, [rsp+270h+var_s0]
0x180007a9f  mov     rbx, [r11+18h]
0x180007aa3  mov     rdi, [r11+28h]
0x180007aa7  mov     rsp, r11
0x180007aaa  pop     rbp
0x180007aab  retn
```
