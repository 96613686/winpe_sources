# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18004dfc4`
- end: `0x18004e160`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18004df50`

## callees

- `0x1800449f0`
- `0x180048db0`
- `0x18004af08`
- `0x18004ce30`
- `0x18004ce50`
- `0x18004db70`
- `0x18004dbec`
- `0x18004dfc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18004e028`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18004e0b8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18004e028`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18004e0b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e038`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e038`

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
0x18004dfc4  mov     [rsp-8+arg_8], rbx
0x18004dfc9  mov     [rsp-8+arg_18], rdi
0x18004dfce  push    rbp
0x18004dfcf  lea     rbp, [rsp-170h]
0x18004dfd7  sub     rsp, 270h
0x18004dfde  mov     rax, cs:__security_cookie
0x18004dfe5  xor     rax, rsp
0x18004dfe8  mov     [rbp+170h+var_10], rax
0x18004dfef  mov     r9, rcx; pszSrc
0x18004dff2  mov     qword ptr [r8], 0
0x18004dff9  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18004dffe  mov     edx, 104h; cchDest
0x18004e003  mov     rdi, r8
0x18004e006  call    StringCopyWorkerW
0x18004e00b  lea     r8, aP0; "_p0"
0x18004e012  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18004e017  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004e01c  lea     r8, [rsp+270h+pszDest]; lpName
0x18004e021  xor     edx, edx; bInheritHandle
0x18004e023  mov     ecx, 1F0003h; dwDesiredAccess
0x18004e028  call    cs:__imp_OpenSemaphoreW
0x18004e02e  mov     [rsp+270h+var_230], rax
0x18004e033  test    rax, rax
0x18004e036  jnz     short loc_18004E05F
0x18004e038  call    cs:__imp_GetLastError
0x18004e03e  cmp     eax, 2
0x18004e041  jz      loc_18004E12E
0x18004e047  mov     rcx, [rbp+178h]; this
0x18004e04e  mov     edx, 0D0h; void *
0x18004e053  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004e058  mov     ebx, eax
0x18004e05a  jmp     loc_18004E130
0x18004e05f  lea     rdx, [rsp+270h+var_23C]; int *
0x18004e064  mov     [rsp+270h+var_23C], 0
0x18004e06c  mov     rcx, rax; hHandle
0x18004e06f  mov     [rsp+270h+var_240], 0
0x18004e077  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18004e07c  mov     ebx, eax
0x18004e07e  test    eax, eax
0x18004e080  jns     short loc_18004E09B
0x18004e082  mov     rcx, [rbp+178h]; this
0x18004e089  mov     r9d, eax; char *
0x18004e08c  mov     edx, 0D6h; void *
0x18004e091  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e096  jmp     loc_18004E130
0x18004e09b  lea     r8, asc_1800AE850; "h"
0x18004e0a2  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18004e0a7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004e0ac  lea     r8, [rsp+270h+pszDest]; lpName
0x18004e0b1  xor     edx, edx; bInheritHandle
0x18004e0b3  mov     ecx, 1F0003h; dwDesiredAccess
0x18004e0b8  call    cs:__imp_OpenSemaphoreW
0x18004e0be  mov     [rsp+270h+var_238], rax
0x18004e0c3  test    rax, rax
0x18004e0c6  jnz     short loc_18004E0E7
0x18004e0c8  mov     rcx, [rbp+178h]; this
0x18004e0cf  mov     edx, 0DCh; void *
0x18004e0d4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004e0d9  mov     ebx, eax
0x18004e0db  lea     rcx, [rsp+270h+var_238]
0x18004e0e0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004e0e5  jmp     short loc_18004E130
0x18004e0e7  lea     rdx, [rsp+270h+var_240]; int *
0x18004e0ec  mov     rcx, rax; hHandle
0x18004e0ef  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18004e0f4  mov     ebx, eax
0x18004e0f6  test    eax, eax
0x18004e0f8  jns     short loc_18004E110
0x18004e0fa  mov     rcx, [rbp+178h]; this
0x18004e101  mov     r9d, eax; char *
0x18004e104  mov     edx, 0DEh; void *
0x18004e109  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e10e  jmp     short loc_18004E0DB
0x18004e110  lea     rcx, [rsp+270h+var_238]
0x18004e115  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004e11a  movsxd  rcx, [rsp+270h+var_240]
0x18004e11f  movsxd  rax, [rsp+270h+var_23C]
0x18004e124  shl     rcx, 1Fh
0x18004e128  or      rcx, rax
0x18004e12b  mov     [rdi], rcx
0x18004e12e  xor     ebx, ebx
0x18004e130  lea     rcx, [rsp+270h+var_230]
0x18004e135  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004e13a  mov     eax, ebx
0x18004e13c  mov     rcx, [rbp+170h+var_10]
0x18004e143  xor     rcx, rsp; StackCookie
0x18004e146  call    __security_check_cookie
0x18004e14b  lea     r11, [rsp+270h+var_s0]
0x18004e153  mov     rbx, [r11+18h]
0x18004e157  mov     rdi, [r11+28h]
0x18004e15b  mov     rsp, r11
0x18004e15e  pop     rbp
0x18004e15f  retn
```
