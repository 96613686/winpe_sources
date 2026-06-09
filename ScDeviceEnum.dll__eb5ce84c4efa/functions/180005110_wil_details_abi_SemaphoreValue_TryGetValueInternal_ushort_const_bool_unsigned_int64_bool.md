# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180005110`
- end: `0x1800052ac`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180003160`

## callees

- `0x18000302c`
- `0x180003d3c`
- `0x180004a24`
- `0x180004a44`
- `0x180004f1c`
- `0x180004ffc`
- `0x180005110`
- `0x18001e020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005174`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005204`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005174`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180005204`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005184`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005184`

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
  int v12; // r8d
  HANDLE v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  int v17; // r8d
  size_t v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+30h] [rbp-D0h] BYREF
  int v21; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v22; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v23[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v19);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v23[0] = v6;
  if ( v6 )
  {
    v21 = 0;
    v20 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v21);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v22 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v20);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v22);
        *a3 = v21 | (unsigned __int64)((__int64)v20 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v22);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v23);
  return LastError;
}

```

## disassembly

```asm
0x180005110  mov     [rsp-8+arg_8], rbx
0x180005115  mov     [rsp-8+arg_18], rdi
0x18000511a  push    rbp
0x18000511b  lea     rbp, [rsp-170h]
0x180005123  sub     rsp, 270h
0x18000512a  mov     rax, cs:__security_cookie
0x180005131  xor     rax, rsp
0x180005134  mov     [rbp+170h+var_10], rax
0x18000513b  mov     r9, rcx; pszSrc
0x18000513e  mov     qword ptr [r8], 0
0x180005145  lea     rcx, [rsp+270h+pszDest]; pszDest
0x18000514a  mov     edx, 104h; cchDest
0x18000514f  mov     rdi, r8
0x180005152  call    StringCopyWorkerW
0x180005157  lea     r8, aP0; "_p0"
0x18000515e  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180005163  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005168  lea     r8, [rsp+270h+pszDest]; lpName
0x18000516d  xor     edx, edx; bInheritHandle
0x18000516f  mov     ecx, 1F0003h; dwDesiredAccess
0x180005174  call    cs:__imp_OpenSemaphoreW
0x18000517a  mov     [rsp+270h+var_230], rax
0x18000517f  test    rax, rax
0x180005182  jnz     short loc_1800051AB
0x180005184  call    cs:__imp_GetLastError
0x18000518a  cmp     eax, 2
0x18000518d  jz      loc_18000527A
0x180005193  mov     rcx, [rbp+178h]; this
0x18000519a  mov     edx, 0D0h; void *
0x18000519f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800051a4  mov     ebx, eax
0x1800051a6  jmp     loc_18000527C
0x1800051ab  lea     rdx, [rsp+270h+var_23C]; int *
0x1800051b0  mov     [rsp+270h+var_23C], 0
0x1800051b8  mov     rcx, rax; hHandle
0x1800051bb  mov     [rsp+270h+var_240], 0
0x1800051c3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800051c8  mov     ebx, eax
0x1800051ca  test    eax, eax
0x1800051cc  jns     short loc_1800051E7
0x1800051ce  mov     rcx, [rbp+178h]; this
0x1800051d5  mov     r9d, eax; char *
0x1800051d8  mov     edx, 0D6h; void *
0x1800051dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800051e2  jmp     loc_18000527C
0x1800051e7  lea     r8, asc_180023840; "h"
0x1800051ee  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800051f3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800051f8  lea     r8, [rsp+270h+pszDest]; lpName
0x1800051fd  xor     edx, edx; bInheritHandle
0x1800051ff  mov     ecx, 1F0003h; dwDesiredAccess
0x180005204  call    cs:__imp_OpenSemaphoreW
0x18000520a  mov     [rsp+270h+var_238], rax
0x18000520f  test    rax, rax
0x180005212  jnz     short loc_180005233
0x180005214  mov     rcx, [rbp+178h]; this
0x18000521b  mov     edx, 0DCh; void *
0x180005220  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005225  mov     ebx, eax
0x180005227  lea     rcx, [rsp+270h+var_238]
0x18000522c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005231  jmp     short loc_18000527C
0x180005233  lea     rdx, [rsp+270h+var_240]; int *
0x180005238  mov     rcx, rax; hHandle
0x18000523b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005240  mov     ebx, eax
0x180005242  test    eax, eax
0x180005244  jns     short loc_18000525C
0x180005246  mov     rcx, [rbp+178h]; this
0x18000524d  mov     r9d, eax; char *
0x180005250  mov     edx, 0DEh; void *
0x180005255  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000525a  jmp     short loc_180005227
0x18000525c  lea     rcx, [rsp+270h+var_238]
0x180005261  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005266  movsxd  rcx, [rsp+270h+var_240]
0x18000526b  movsxd  rax, [rsp+270h+var_23C]
0x180005270  shl     rcx, 1Fh
0x180005274  or      rcx, rax
0x180005277  mov     [rdi], rcx
0x18000527a  xor     ebx, ebx
0x18000527c  lea     rcx, [rsp+270h+var_230]
0x180005281  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005286  mov     eax, ebx
0x180005288  mov     rcx, [rbp+170h+var_10]
0x18000528f  xor     rcx, rsp; StackCookie
0x180005292  call    __security_check_cookie
0x180005297  lea     r11, [rsp+270h+var_s0]
0x18000529f  mov     rbx, [r11+18h]
0x1800052a3  mov     rdi, [r11+28h]
0x1800052a7  mov     rsp, r11
0x1800052aa  pop     rbp
0x1800052ab  retn
```
