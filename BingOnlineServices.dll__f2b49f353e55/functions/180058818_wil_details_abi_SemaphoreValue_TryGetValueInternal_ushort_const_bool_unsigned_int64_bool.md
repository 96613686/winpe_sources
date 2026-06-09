# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180058818`
- end: `0x1800589b4`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180056708`

## callees

- `0x180004fa0`
- `0x18005660c`
- `0x180057400`
- `0x180058134`
- `0x180058154`
- `0x18005862c`
- `0x18005870c`
- `0x180058818`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005888c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005888c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18005887c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18005890c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18005887c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18005890c`

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
0x180058818  mov     [rsp-8+arg_8], rbx
0x18005881d  mov     [rsp-8+arg_18], rdi
0x180058822  push    rbp
0x180058823  lea     rbp, [rsp-170h]
0x18005882b  sub     rsp, 270h
0x180058832  mov     rax, cs:__security_cookie
0x180058839  xor     rax, rsp
0x18005883c  mov     [rbp+170h+var_10], rax
0x180058843  mov     r9, rcx; pszSrc
0x180058846  mov     qword ptr [r8], 0
0x18005884d  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180058852  mov     edx, 104h; cchDest
0x180058857  mov     rdi, r8
0x18005885a  call    StringCopyWorkerW
0x18005885f  lea     r8, aP0; "_p0"
0x180058866  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18005886b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180058870  lea     r8, [rsp+270h+pszDest]; lpName
0x180058875  xor     edx, edx; bInheritHandle
0x180058877  mov     ecx, 1F0003h; dwDesiredAccess
0x18005887c  call    cs:__imp_OpenSemaphoreW
0x180058882  mov     [rsp+270h+var_230], rax
0x180058887  test    rax, rax
0x18005888a  jnz     short loc_1800588B3
0x18005888c  call    cs:__imp_GetLastError
0x180058892  cmp     eax, 2
0x180058895  jz      loc_180058982
0x18005889b  mov     rcx, [rbp+178h]; this
0x1800588a2  mov     edx, 0D0h; void *
0x1800588a7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800588ac  mov     ebx, eax
0x1800588ae  jmp     loc_180058984
0x1800588b3  lea     rdx, [rsp+270h+var_23C]; int *
0x1800588b8  mov     [rsp+270h+var_23C], 0
0x1800588c0  mov     rcx, rax; hHandle
0x1800588c3  mov     [rsp+270h+var_240], 0
0x1800588cb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800588d0  mov     ebx, eax
0x1800588d2  test    eax, eax
0x1800588d4  jns     short loc_1800588EF
0x1800588d6  mov     rcx, [rbp+178h]; this
0x1800588dd  mov     r9d, eax; char *
0x1800588e0  mov     edx, 0D6h; void *
0x1800588e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800588ea  jmp     loc_180058984
0x1800588ef  lea     r8, asc_18006AAA8; "h"
0x1800588f6  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800588fb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180058900  lea     r8, [rsp+270h+pszDest]; lpName
0x180058905  xor     edx, edx; bInheritHandle
0x180058907  mov     ecx, 1F0003h; dwDesiredAccess
0x18005890c  call    cs:__imp_OpenSemaphoreW
0x180058912  mov     [rsp+270h+var_238], rax
0x180058917  test    rax, rax
0x18005891a  jnz     short loc_18005893B
0x18005891c  mov     rcx, [rbp+178h]; this
0x180058923  mov     edx, 0DCh; void *
0x180058928  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005892d  mov     ebx, eax
0x18005892f  lea     rcx, [rsp+270h+var_238]
0x180058934  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180058939  jmp     short loc_180058984
0x18005893b  lea     rdx, [rsp+270h+var_240]; int *
0x180058940  mov     rcx, rax; hHandle
0x180058943  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180058948  mov     ebx, eax
0x18005894a  test    eax, eax
0x18005894c  jns     short loc_180058964
0x18005894e  mov     rcx, [rbp+178h]; this
0x180058955  mov     r9d, eax; char *
0x180058958  mov     edx, 0DEh; void *
0x18005895d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180058962  jmp     short loc_18005892F
0x180058964  lea     rcx, [rsp+270h+var_238]
0x180058969  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005896e  movsxd  rcx, [rsp+270h+var_240]
0x180058973  movsxd  rax, [rsp+270h+var_23C]
0x180058978  shl     rcx, 1Fh
0x18005897c  or      rcx, rax
0x18005897f  mov     [rdi], rcx
0x180058982  xor     ebx, ebx
0x180058984  lea     rcx, [rsp+270h+var_230]
0x180058989  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18005898e  mov     eax, ebx
0x180058990  mov     rcx, [rbp+170h+var_10]
0x180058997  xor     rcx, rsp; StackCookie
0x18005899a  call    __security_check_cookie
0x18005899f  lea     r11, [rsp+270h+var_s0]
0x1800589a7  mov     rbx, [r11+18h]
0x1800589ab  mov     rdi, [r11+28h]
0x1800589af  mov     rsp, r11
0x1800589b2  pop     rbp
0x1800589b3  retn
```
