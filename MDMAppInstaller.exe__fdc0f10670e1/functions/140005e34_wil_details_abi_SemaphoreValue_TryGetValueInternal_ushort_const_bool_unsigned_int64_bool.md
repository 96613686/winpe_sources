# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140005e34`
- end: `0x140005fec`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x140005db0`

## callees

- `0x140003c68`
- `0x140004bec`
- `0x140005684`
- `0x1400056a4`
- `0x140005bc0`
- `0x140005ca0`
- `0x140005e34`
- `0x14001a8d0`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x140005e98`
- `KERNEL32!OpenSemaphoreW` at `0x140005f36`
- `KERNEL32!OpenSemaphoreW` at `0x140005e98`
- `KERNEL32!OpenSemaphoreW` at `0x140005f36`
- `KERNEL32!GetLastError` at `0x140005ea8`
- `KERNEL32!GetLastError` at `0x140005ea8`

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
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  wil::details *v12; // rax
  const char *v13; // r9
  void *v14; // rdx
  int v15; // eax
  void *v16; // rdx
  size_t v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+34h] [rbp-CCh] BYREF
  wil::details *v21; // [rsp+38h] [rbp-C8h] BYREF
  wil::details *v22; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v18);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v22 = v6;
  if ( v6 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v20);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v12 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v21 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v19);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v21,
          v16);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v13);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v21,
      v14);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v22,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x140005e34  mov     [rsp-8+arg_8], rbx
0x140005e39  mov     [rsp-8+arg_18], rdi
0x140005e3e  push    rbp
0x140005e3f  lea     rbp, [rsp-170h]
0x140005e47  sub     rsp, 270h
0x140005e4e  mov     rax, cs:__security_cookie
0x140005e55  xor     rax, rsp
0x140005e58  mov     [rbp+170h+var_10], rax
0x140005e5f  mov     r9, rcx; pszSrc
0x140005e62  mov     qword ptr [r8], 0
0x140005e69  lea     rcx, [rsp+270h+pszDest]; pszDest
0x140005e6e  mov     edx, 104h; cchDest
0x140005e73  mov     rdi, r8
0x140005e76  call    StringCopyWorkerW
0x140005e7b  lea     r8, aP0; "_p0"
0x140005e82  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x140005e87  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005e8c  lea     r8, [rsp+270h+pszDest]; lpName
0x140005e91  xor     edx, edx; bInheritHandle
0x140005e93  mov     ecx, 1F0003h; dwDesiredAccess
0x140005e98  call    cs:__imp_OpenSemaphoreW
0x140005e9e  mov     [rsp+270h+var_230], rax
0x140005ea3  test    rax, rax
0x140005ea6  jnz     short loc_140005ED6
0x140005ea8  call    cs:__imp_GetLastError
0x140005eae  cmp     eax, 2
0x140005eb1  jz      loc_140005FBA
0x140005eb7  mov     rcx, [rbp+178h]; this
0x140005ebe  lea     r8, aWil; "wil"
0x140005ec5  mov     edx, 0D0h; void *
0x140005eca  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005ecf  mov     ebx, eax
0x140005ed1  jmp     loc_140005FBC
0x140005ed6  lea     rdx, [rsp+270h+var_23C]; int *
0x140005edb  mov     [rsp+270h+var_23C], 0
0x140005ee3  mov     rcx, rax; hHandle
0x140005ee6  mov     [rsp+270h+var_240], 0
0x140005eee  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005ef3  mov     ebx, eax
0x140005ef5  test    eax, eax
0x140005ef7  jns     short loc_140005F19
0x140005ef9  mov     rcx, [rbp+178h]; this
0x140005f00  lea     r8, aWil; "wil"
0x140005f07  mov     r9d, eax; char *
0x140005f0a  mov     edx, 0D6h; void *
0x140005f0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005f14  jmp     loc_140005FBC
0x140005f19  lea     r8, asc_14001DE78; "h"
0x140005f20  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x140005f25  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140005f2a  lea     r8, [rsp+270h+pszDest]; lpName
0x140005f2f  xor     edx, edx; bInheritHandle
0x140005f31  mov     ecx, 1F0003h; dwDesiredAccess
0x140005f36  call    cs:__imp_OpenSemaphoreW
0x140005f3c  mov     [rsp+270h+var_238], rax
0x140005f41  test    rax, rax
0x140005f44  jnz     short loc_140005F6C
0x140005f46  mov     rcx, [rbp+178h]; this
0x140005f4d  lea     r8, aWil; "wil"
0x140005f54  mov     edx, 0DCh; void *
0x140005f59  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140005f5e  mov     ebx, eax
0x140005f60  lea     rcx, [rsp+270h+var_238]
0x140005f65  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140005f6a  jmp     short loc_140005FBC
0x140005f6c  lea     rdx, [rsp+270h+var_240]; int *
0x140005f71  mov     rcx, rax; hHandle
0x140005f74  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x140005f79  mov     ebx, eax
0x140005f7b  test    eax, eax
0x140005f7d  jns     short loc_140005F9C
0x140005f7f  mov     rcx, [rbp+178h]; this
0x140005f86  lea     r8, aWil; "wil"
0x140005f8d  mov     r9d, eax; char *
0x140005f90  mov     edx, 0DEh; void *
0x140005f95  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140005f9a  jmp     short loc_140005F60
0x140005f9c  lea     rcx, [rsp+270h+var_238]
0x140005fa1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140005fa6  movsxd  rcx, [rsp+270h+var_240]
0x140005fab  movsxd  rax, [rsp+270h+var_23C]
0x140005fb0  shl     rcx, 1Fh
0x140005fb4  or      rcx, rax
0x140005fb7  mov     [rdi], rcx
0x140005fba  xor     ebx, ebx
0x140005fbc  lea     rcx, [rsp+270h+var_230]
0x140005fc1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x140005fc6  mov     eax, ebx
0x140005fc8  mov     rcx, [rbp+170h+var_10]
0x140005fcf  xor     rcx, rsp; StackCookie
0x140005fd2  call    __security_check_cookie
0x140005fd7  lea     r11, [rsp+270h+var_s0]
0x140005fdf  mov     rbx, [r11+18h]
0x140005fe3  mov     rdi, [r11+28h]
0x140005fe7  mov     rsp, r11
0x140005fea  pop     rbp
0x140005feb  retn
```
