# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000ed40`
- end: `0x18000eedc`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000eccc`

## callees

- `0x180002020`
- `0x18000a740`
- `0x18000d044`
- `0x18000e764`
- `0x18000e784`
- `0x18000ebd0`
- `0x18000ec4c`
- `0x18000ed40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000eda4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ee34`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000eda4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ee34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000edb4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000edb4`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  wil::details *v6; // rax
  void *v7; // rdx
  unsigned int v8; // r8d
  const char *v9; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v12; // rdx
  int v13; // r8d
  wil::details *v14; // rax
  unsigned int v15; // r8d
  const char *v16; // r9
  void *v17; // rdx
  int v18; // eax
  void *v19; // rdx
  int v20; // r8d
  size_t v22; // [rsp+20h] [rbp-E0h]
  int v23; // [rsp+30h] [rbp-D0h] BYREF
  int v24; // [rsp+34h] [rbp-CCh] BYREF
  wil::details *v25; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v26; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v22);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v26 = v6;
  if ( v6 )
  {
    v24 = 0;
    v23 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v24);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v13, (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v12, L"h");
    v14 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v25 = v14;
    if ( v14 )
    {
      v18 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, &v23);
      LastError = v18;
      if ( v18 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v25,
          v19);
        *a3 = v24 | (unsigned __int64)((__int64)v23 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v20, (const char *)(unsigned int)v18);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v15, v16);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v25,
      v17);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v8, v9);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v26,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x18000ed40  mov     [rsp-8+arg_8], rbx
0x18000ed45  mov     [rsp-8+arg_18], rdi
0x18000ed4a  push    rbp
0x18000ed4b  lea     rbp, [rsp-170h]
0x18000ed53  sub     rsp, 270h
0x18000ed5a  mov     rax, cs:__security_cookie
0x18000ed61  xor     rax, rsp
0x18000ed64  mov     [rbp+170h+var_10], rax
0x18000ed6b  mov     r9, rcx; pszSrc
0x18000ed6e  mov     qword ptr [r8], 0
0x18000ed75  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18000ed7a  mov     edx, 104h; cchDest
0x18000ed7f  mov     rdi, r8
0x18000ed82  call    StringCopyWorkerW
0x18000ed87  lea     r8, aP0; "_p0"
0x18000ed8e  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000ed93  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ed98  lea     r8, [rsp+270h+pszDest]; lpName
0x18000ed9d  xor     edx, edx; bInheritHandle
0x18000ed9f  mov     ecx, 1F0003h; dwDesiredAccess
0x18000eda4  call    cs:__imp_OpenSemaphoreW
0x18000edaa  mov     [rsp+270h+var_230], rax
0x18000edaf  test    rax, rax
0x18000edb2  jnz     short loc_18000EDDB
0x18000edb4  call    cs:__imp_GetLastError
0x18000edba  cmp     eax, 2
0x18000edbd  jz      loc_18000EEAA
0x18000edc3  mov     rcx, [rbp+178h]; this
0x18000edca  mov     edx, 0D0h; void *
0x18000edcf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000edd4  mov     ebx, eax
0x18000edd6  jmp     loc_18000EEAC
0x18000eddb  lea     rdx, [rsp+270h+var_23C]; int *
0x18000ede0  mov     [rsp+270h+var_23C], 0
0x18000ede8  mov     rcx, rax; hHandle
0x18000edeb  mov     [rsp+270h+var_240], 0
0x18000edf3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000edf8  mov     ebx, eax
0x18000edfa  test    eax, eax
0x18000edfc  jns     short loc_18000EE17
0x18000edfe  mov     rcx, [rbp+178h]; this
0x18000ee05  mov     r9d, eax; char *
0x18000ee08  mov     edx, 0D6h; void *
0x18000ee0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ee12  jmp     loc_18000EEAC
0x18000ee17  lea     r8, asc_18001A900; "h"
0x18000ee1e  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000ee23  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ee28  lea     r8, [rsp+270h+pszDest]; lpName
0x18000ee2d  xor     edx, edx; bInheritHandle
0x18000ee2f  mov     ecx, 1F0003h; dwDesiredAccess
0x18000ee34  call    cs:__imp_OpenSemaphoreW
0x18000ee3a  mov     [rsp+270h+var_238], rax
0x18000ee3f  test    rax, rax
0x18000ee42  jnz     short loc_18000EE63
0x18000ee44  mov     rcx, [rbp+178h]; this
0x18000ee4b  mov     edx, 0DCh; void *
0x18000ee50  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ee55  mov     ebx, eax
0x18000ee57  lea     rcx, [rsp+270h+var_238]
0x18000ee5c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ee61  jmp     short loc_18000EEAC
0x18000ee63  lea     rdx, [rsp+270h+var_240]; int *
0x18000ee68  mov     rcx, rax; hHandle
0x18000ee6b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000ee70  mov     ebx, eax
0x18000ee72  test    eax, eax
0x18000ee74  jns     short loc_18000EE8C
0x18000ee76  mov     rcx, [rbp+178h]; this
0x18000ee7d  mov     r9d, eax; char *
0x18000ee80  mov     edx, 0DEh; void *
0x18000ee85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ee8a  jmp     short loc_18000EE57
0x18000ee8c  lea     rcx, [rsp+270h+var_238]
0x18000ee91  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ee96  movsxd  rcx, [rsp+270h+var_240]
0x18000ee9b  movsxd  rax, [rsp+270h+var_23C]
0x18000eea0  shl     rcx, 1Fh
0x18000eea4  or      rcx, rax
0x18000eea7  mov     [rdi], rcx
0x18000eeaa  xor     ebx, ebx
0x18000eeac  lea     rcx, [rsp+270h+var_230]
0x18000eeb1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000eeb6  mov     eax, ebx
0x18000eeb8  mov     rcx, [rbp+170h+var_10]
0x18000eebf  xor     rcx, rsp; StackCookie
0x18000eec2  call    __security_check_cookie
0x18000eec7  lea     r11, [rsp+270h+var_s0]
0x18000eecf  mov     rbx, [r11+18h]
0x18000eed3  mov     rdi, [r11+28h]
0x18000eed7  mov     rsp, r11
0x18000eeda  pop     rbp
0x18000eedb  retn
```
