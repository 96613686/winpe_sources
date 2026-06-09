# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000989c`
- end: `0x180009a38`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180007778`

## callees

- `0x180003c80`
- `0x180007468`
- `0x1800082f0`
- `0x1800091b4`
- `0x1800091d4`
- `0x1800096ac`
- `0x18000978c`
- `0x18000989c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009910`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009910`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009900`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009990`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009900`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009990`

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
0x18000989c  mov     [rsp-8+arg_8], rbx
0x1800098a1  mov     [rsp-8+arg_18], rdi
0x1800098a6  push    rbp
0x1800098a7  lea     rbp, [rsp-170h]
0x1800098af  sub     rsp, 270h
0x1800098b6  mov     rax, cs:__security_cookie
0x1800098bd  xor     rax, rsp
0x1800098c0  mov     [rbp+170h+var_10], rax
0x1800098c7  mov     r9, rcx; pszSrc
0x1800098ca  mov     qword ptr [r8], 0
0x1800098d1  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800098d6  mov     edx, 104h; cchDest
0x1800098db  mov     rdi, r8
0x1800098de  call    StringCopyWorkerW
0x1800098e3  lea     r8, aP0; "_p0"
0x1800098ea  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800098ef  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800098f4  lea     r8, [rsp+270h+pszDest]; lpName
0x1800098f9  xor     edx, edx; bInheritHandle
0x1800098fb  mov     ecx, 1F0003h; dwDesiredAccess
0x180009900  call    cs:__imp_OpenSemaphoreW
0x180009906  mov     [rsp+270h+var_230], rax
0x18000990b  test    rax, rax
0x18000990e  jnz     short loc_180009937
0x180009910  call    cs:__imp_GetLastError
0x180009916  cmp     eax, 2
0x180009919  jz      loc_180009A06
0x18000991f  mov     rcx, [rbp+178h]; this
0x180009926  mov     edx, 0D0h; void *
0x18000992b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009930  mov     ebx, eax
0x180009932  jmp     loc_180009A08
0x180009937  lea     rdx, [rsp+270h+var_23C]; int *
0x18000993c  mov     [rsp+270h+var_23C], 0
0x180009944  mov     rcx, rax; hHandle
0x180009947  mov     [rsp+270h+var_240], 0
0x18000994f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009954  mov     ebx, eax
0x180009956  test    eax, eax
0x180009958  jns     short loc_180009973
0x18000995a  mov     rcx, [rbp+178h]; this
0x180009961  mov     r9d, eax; char *
0x180009964  mov     edx, 0D6h; void *
0x180009969  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000996e  jmp     loc_180009A08
0x180009973  lea     r8, asc_1804F7AE4; "h"
0x18000997a  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x18000997f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009984  lea     r8, [rsp+270h+pszDest]; lpName
0x180009989  xor     edx, edx; bInheritHandle
0x18000998b  mov     ecx, 1F0003h; dwDesiredAccess
0x180009990  call    cs:__imp_OpenSemaphoreW
0x180009996  mov     [rsp+270h+var_238], rax
0x18000999b  test    rax, rax
0x18000999e  jnz     short loc_1800099BF
0x1800099a0  mov     rcx, [rbp+178h]; this
0x1800099a7  mov     edx, 0DCh; void *
0x1800099ac  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800099b1  mov     ebx, eax
0x1800099b3  lea     rcx, [rsp+270h+var_238]
0x1800099b8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800099bd  jmp     short loc_180009A08
0x1800099bf  lea     rdx, [rsp+270h+var_240]; int *
0x1800099c4  mov     rcx, rax; hHandle
0x1800099c7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800099cc  mov     ebx, eax
0x1800099ce  test    eax, eax
0x1800099d0  jns     short loc_1800099E8
0x1800099d2  mov     rcx, [rbp+178h]; this
0x1800099d9  mov     r9d, eax; char *
0x1800099dc  mov     edx, 0DEh; void *
0x1800099e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800099e6  jmp     short loc_1800099B3
0x1800099e8  lea     rcx, [rsp+270h+var_238]
0x1800099ed  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800099f2  movsxd  rcx, [rsp+270h+var_240]
0x1800099f7  movsxd  rax, [rsp+270h+var_23C]
0x1800099fc  shl     rcx, 1Fh
0x180009a00  or      rcx, rax
0x180009a03  mov     [rdi], rcx
0x180009a06  xor     ebx, ebx
0x180009a08  lea     rcx, [rsp+270h+var_230]
0x180009a0d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009a12  mov     eax, ebx
0x180009a14  mov     rcx, [rbp+170h+var_10]
0x180009a1b  xor     rcx, rsp; StackCookie
0x180009a1e  call    __security_check_cookie
0x180009a23  lea     r11, [rsp+270h+var_s0]
0x180009a2b  mov     rbx, [r11+18h]
0x180009a2f  mov     rdi, [r11+28h]
0x180009a33  mov     rsp, r11
0x180009a36  pop     rbp
0x180009a37  retn
```
