# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180007e1c`
- end: `0x180007fc6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180007d98`

## callees

- `0x180002a90`
- `0x18000538c`
- `0x1800065f4`
- `0x180007634`
- `0x180007654`
- `0x180007bb0`
- `0x180007c90`
- `0x180007e1c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007e80`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007f17`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007e80`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007f17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007e90`

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
  HANDLE v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  int v15; // eax
  size_t v17; // [rsp+20h] [rbp-E0h]
  int v18; // [rsp+20h] [rbp-E0h]
  int v19; // [rsp+30h] [rbp-D0h] BYREF
  int v20; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v21; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v22[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v17);
  StringCchCatW(pszDest, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v22[0] = v6;
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
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v18);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, v11, L"h");
    v12 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v21 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v19);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v15,
        v18);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v13, v14);
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
0x180007e1c  mov     [rsp-8+arg_8], rbx
0x180007e21  mov     [rsp-8+arg_18], rdi
0x180007e26  push    rbp
0x180007e27  lea     rbp, [rsp-170h]
0x180007e2f  sub     rsp, 270h
0x180007e36  mov     rax, cs:__security_cookie
0x180007e3d  xor     rax, rsp
0x180007e40  mov     [rbp+170h+var_10], rax
0x180007e47  mov     r9, rcx; pszSrc
0x180007e4a  mov     qword ptr [r8], 0
0x180007e51  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180007e56  mov     edx, 104h; cchDest
0x180007e5b  mov     rdi, r8
0x180007e5e  call    StringCopyWorkerW
0x180007e63  lea     r8, aP0; "_p0"
0x180007e6a  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180007e6f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007e74  lea     r8, [rsp+270h+pszDest]; lpName
0x180007e79  xor     edx, edx; bInheritHandle
0x180007e7b  mov     ecx, 1F0003h; dwDesiredAccess
0x180007e80  call    cs:__imp_OpenSemaphoreW
0x180007e86  mov     [rsp+270h+var_230], rax
0x180007e8b  test    rax, rax
0x180007e8e  jnz     short loc_180007EB7
0x180007e90  call    cs:__imp_GetLastError
0x180007e96  cmp     eax, 2
0x180007e99  jz      loc_180007F94
0x180007e9f  mov     rcx, [rbp+178h]; this
0x180007ea6  mov     edx, 0D0h; void *
0x180007eab  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007eb0  mov     ebx, eax
0x180007eb2  jmp     loc_180007F96
0x180007eb7  lea     rdx, [rsp+270h+var_23C]; int *
0x180007ebc  mov     [rsp+270h+var_23C], 0
0x180007ec4  mov     rcx, rax; hHandle
0x180007ec7  mov     [rsp+270h+var_240], 0
0x180007ecf  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007ed4  mov     ebx, eax
0x180007ed6  test    eax, eax
0x180007ed8  jns     short loc_180007EFA
0x180007eda  mov     rcx, [rbp+178h]; this
0x180007ee1  lea     r8, aWil; "wil"
0x180007ee8  mov     r9d, eax; char *
0x180007eeb  mov     edx, 0D6h; void *
0x180007ef0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007ef5  jmp     loc_180007F96
0x180007efa  lea     r8, asc_18002F180; "h"
0x180007f01  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180007f06  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007f0b  lea     r8, [rsp+270h+pszDest]; lpName
0x180007f10  xor     edx, edx; bInheritHandle
0x180007f12  mov     ecx, 1F0003h; dwDesiredAccess
0x180007f17  call    cs:__imp_OpenSemaphoreW
0x180007f1d  mov     [rsp+270h+var_238], rax
0x180007f22  test    rax, rax
0x180007f25  jnz     short loc_180007F46
0x180007f27  mov     rcx, [rbp+178h]; this
0x180007f2e  mov     edx, 0DCh; void *
0x180007f33  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007f38  mov     ebx, eax
0x180007f3a  lea     rcx, [rsp+270h+var_238]
0x180007f3f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007f44  jmp     short loc_180007F96
0x180007f46  lea     rdx, [rsp+270h+var_240]; int *
0x180007f4b  mov     rcx, rax; hHandle
0x180007f4e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007f53  mov     ebx, eax
0x180007f55  test    eax, eax
0x180007f57  jns     short loc_180007F76
0x180007f59  mov     rcx, [rbp+178h]; this
0x180007f60  lea     r8, aWil; "wil"
0x180007f67  mov     r9d, eax; char *
0x180007f6a  mov     edx, 0DEh; void *
0x180007f6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007f74  jmp     short loc_180007F3A
0x180007f76  lea     rcx, [rsp+270h+var_238]
0x180007f7b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007f80  movsxd  rcx, [rsp+270h+var_240]
0x180007f85  movsxd  rax, [rsp+270h+var_23C]
0x180007f8a  shl     rcx, 1Fh
0x180007f8e  or      rcx, rax
0x180007f91  mov     [rdi], rcx
0x180007f94  xor     ebx, ebx
0x180007f96  lea     rcx, [rsp+270h+var_230]
0x180007f9b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007fa0  mov     eax, ebx
0x180007fa2  mov     rcx, [rbp+170h+var_10]
0x180007fa9  xor     rcx, rsp; StackCookie
0x180007fac  call    __security_check_cookie
0x180007fb1  lea     r11, [rsp+270h+var_s0]
0x180007fb9  mov     rbx, [r11+18h]
0x180007fbd  mov     rdi, [r11+28h]
0x180007fc1  mov     rsp, r11
0x180007fc4  pop     rbp
0x180007fc5  retn
```
