# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000cba4`
- end: `0x14000cd40`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000cb30`

## callees

- `0x1400078d8`
- `0x14000a120`
- `0x14000bebc`
- `0x14000bedc`
- `0x14000c644`
- `0x14000c724`
- `0x14000cba4`
- `0x140038d10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cc18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000cc18`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000cc08`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000cc98`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000cc08`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x14000cc98`

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
0x14000cba4  mov     [rsp-8+arg_8], rbx
0x14000cba9  mov     [rsp-8+arg_18], rdi
0x14000cbae  push    rbp
0x14000cbaf  lea     rbp, [rsp-170h]
0x14000cbb7  sub     rsp, 270h
0x14000cbbe  mov     rax, cs:__security_cookie
0x14000cbc5  xor     rax, rsp
0x14000cbc8  mov     [rbp+170h+var_10], rax
0x14000cbcf  mov     r9, rcx; pszSrc
0x14000cbd2  mov     qword ptr [r8], 0
0x14000cbd9  lea     rcx, [rsp+270h+pszDest]; pszDest
0x14000cbde  mov     edx, 104h; cchDest
0x14000cbe3  mov     rdi, r8
0x14000cbe6  call    StringCopyWorkerW
0x14000cbeb  lea     r8, aP0; "_p0"
0x14000cbf2  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x14000cbf7  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000cbfc  lea     r8, [rsp+270h+pszDest]; lpName
0x14000cc01  xor     edx, edx; bInheritHandle
0x14000cc03  mov     ecx, 1F0003h; dwDesiredAccess
0x14000cc08  call    cs:__imp_OpenSemaphoreW
0x14000cc0e  mov     [rsp+270h+var_230], rax
0x14000cc13  test    rax, rax
0x14000cc16  jnz     short loc_14000CC3F
0x14000cc18  call    cs:__imp_GetLastError
0x14000cc1e  cmp     eax, 2
0x14000cc21  jz      loc_14000CD0E
0x14000cc27  mov     rcx, [rbp+178h]; this
0x14000cc2e  mov     edx, 0D0h; void *
0x14000cc33  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000cc38  mov     ebx, eax
0x14000cc3a  jmp     loc_14000CD10
0x14000cc3f  lea     rdx, [rsp+270h+var_23C]; int *
0x14000cc44  mov     [rsp+270h+var_23C], 0
0x14000cc4c  mov     rcx, rax; hHandle
0x14000cc4f  mov     [rsp+270h+var_240], 0
0x14000cc57  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000cc5c  mov     ebx, eax
0x14000cc5e  test    eax, eax
0x14000cc60  jns     short loc_14000CC7B
0x14000cc62  mov     rcx, [rbp+178h]; this
0x14000cc69  mov     r9d, eax; char *
0x14000cc6c  mov     edx, 0D6h; void *
0x14000cc71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000cc76  jmp     loc_14000CD10
0x14000cc7b  lea     r8, asc_140046E88; "h"
0x14000cc82  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x14000cc87  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000cc8c  lea     r8, [rsp+270h+pszDest]; lpName
0x14000cc91  xor     edx, edx; bInheritHandle
0x14000cc93  mov     ecx, 1F0003h; dwDesiredAccess
0x14000cc98  call    cs:__imp_OpenSemaphoreW
0x14000cc9e  mov     [rsp+270h+var_238], rax
0x14000cca3  test    rax, rax
0x14000cca6  jnz     short loc_14000CCC7
0x14000cca8  mov     rcx, [rbp+178h]; this
0x14000ccaf  mov     edx, 0DCh; void *
0x14000ccb4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000ccb9  mov     ebx, eax
0x14000ccbb  lea     rcx, [rsp+270h+var_238]
0x14000ccc0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000ccc5  jmp     short loc_14000CD10
0x14000ccc7  lea     rdx, [rsp+270h+var_240]; int *
0x14000cccc  mov     rcx, rax; hHandle
0x14000cccf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000ccd4  mov     ebx, eax
0x14000ccd6  test    eax, eax
0x14000ccd8  jns     short loc_14000CCF0
0x14000ccda  mov     rcx, [rbp+178h]; this
0x14000cce1  mov     r9d, eax; char *
0x14000cce4  mov     edx, 0DEh; void *
0x14000cce9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000ccee  jmp     short loc_14000CCBB
0x14000ccf0  lea     rcx, [rsp+270h+var_238]
0x14000ccf5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000ccfa  movsxd  rcx, [rsp+270h+var_240]
0x14000ccff  movsxd  rax, [rsp+270h+var_23C]
0x14000cd04  shl     rcx, 1Fh
0x14000cd08  or      rcx, rax
0x14000cd0b  mov     [rdi], rcx
0x14000cd0e  xor     ebx, ebx
0x14000cd10  lea     rcx, [rsp+270h+var_230]
0x14000cd15  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000cd1a  mov     eax, ebx
0x14000cd1c  mov     rcx, [rbp+170h+var_10]
0x14000cd23  xor     rcx, rsp; StackCookie
0x14000cd26  call    __security_check_cookie
0x14000cd2b  lea     r11, [rsp+270h+var_s0]
0x14000cd33  mov     rbx, [r11+18h]
0x14000cd37  mov     rdi, [r11+28h]
0x14000cd3b  mov     rsp, r11
0x14000cd3e  pop     rbp
0x14000cd3f  retn
```
