# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009e0c`
- end: `0x180009fca`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180009d88`

## callees

- `0x180003ab0`
- `0x180005d04`
- `0x180007370`
- `0x18000919c`
- `0x1800091bc`
- `0x18000987c`
- `0x1800099b4`
- `0x180009e0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009e75`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009f15`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009e75`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009f15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e85`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  const char *v6; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v9; // rax
  const char *v10; // r9
  int v11; // eax
  size_t v13; // [rsp+20h] [rbp-E0h]
  int v14; // [rsp+20h] [rbp-E0h]
  int v15; // [rsp+30h] [rbp-D0h] BYREF
  int v16; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v17; // [rsp+38h] [rbp-C8h] BYREF
  HANDLE v18[2]; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v13);
  StringCchCatW(pszDest, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v18[0] = v5;
  if ( v5 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v16);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v14);
      goto LABEL_13;
    }
    StringCchCatW(pszDest, 0x104u, L"h");
    v9 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v17 = v9;
    if ( v9 )
    {
      v11 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, &v15);
      LastError = v11;
      if ( v11 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
        *a3 = v16 | (unsigned __int64)((__int64)v15 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v11,
        v14);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v10);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v6);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x180009e0c  mov     [rsp-8+arg_8], rbx
0x180009e11  push    rbp
0x180009e12  push    rdi
0x180009e13  push    r14
0x180009e15  lea     rbp, [rsp-170h]
0x180009e1d  sub     rsp, 270h
0x180009e24  mov     rax, cs:__security_cookie
0x180009e2b  xor     rax, rsp
0x180009e2e  mov     [rbp+180h+var_20], rax
0x180009e35  mov     r9, rcx; pszSrc
0x180009e38  mov     qword ptr [r8], 0
0x180009e3f  mov     r14d, 104h
0x180009e45  lea     rcx, [rsp+280h+pszDest]; pszDest
0x180009e4a  mov     edx, r14d; cchDest
0x180009e4d  mov     rdi, r8
0x180009e50  call    StringCopyWorkerW
0x180009e55  lea     r8, aP0; "_p0"
0x180009e5c  mov     edx, r14d; unsigned __int64
0x180009e5f  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x180009e64  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009e69  lea     r8, [rsp+280h+pszDest]; lpName
0x180009e6e  xor     edx, edx; bInheritHandle
0x180009e70  mov     ecx, 1F0003h; dwDesiredAccess
0x180009e75  call    cs:__imp_OpenSemaphoreW
0x180009e7b  mov     [rsp+280h+var_240], rax
0x180009e80  test    rax, rax
0x180009e83  jnz     short loc_180009EB2
0x180009e85  call    cs:__imp_GetLastError
0x180009e8b  cmp     eax, 2
0x180009e8e  jz      loc_180009F99
0x180009e94  mov     rcx, [rbp+188h]; this
0x180009e9b  lea     r8, aWil; "wil"
0x180009ea2  lea     edx, [r14-34h]; void *
0x180009ea6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009eab  mov     ebx, eax
0x180009ead  jmp     loc_180009F9B
0x180009eb2  lea     rdx, [rsp+280h+var_24C]; int *
0x180009eb7  mov     [rsp+280h+var_24C], 0
0x180009ebf  mov     rcx, rax; hHandle
0x180009ec2  mov     [rsp+280h+var_250], 0
0x180009eca  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009ecf  mov     ebx, eax
0x180009ed1  test    eax, eax
0x180009ed3  jns     short loc_180009EF5
0x180009ed5  mov     rcx, [rbp+188h]; this
0x180009edc  lea     r8, aWil; "wil"
0x180009ee3  mov     r9d, eax; char *
0x180009ee6  mov     edx, 0D6h; void *
0x180009eeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009ef0  jmp     loc_180009F9B
0x180009ef5  lea     r8, asc_180033E60; "h"
0x180009efc  mov     rdx, r14; unsigned __int64
0x180009eff  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x180009f04  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009f09  lea     r8, [rsp+280h+pszDest]; lpName
0x180009f0e  xor     edx, edx; bInheritHandle
0x180009f10  mov     ecx, 1F0003h; dwDesiredAccess
0x180009f15  call    cs:__imp_OpenSemaphoreW
0x180009f1b  mov     [rsp+280h+var_248], rax
0x180009f20  test    rax, rax
0x180009f23  jnz     short loc_180009F4B
0x180009f25  mov     rcx, [rbp+188h]; this
0x180009f2c  lea     r8, aWil; "wil"
0x180009f33  mov     edx, 0DCh; void *
0x180009f38  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009f3d  mov     ebx, eax
0x180009f3f  lea     rcx, [rsp+280h+var_248]
0x180009f44  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009f49  jmp     short loc_180009F9B
0x180009f4b  lea     rdx, [rsp+280h+var_250]; int *
0x180009f50  mov     rcx, rax; hHandle
0x180009f53  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009f58  mov     ebx, eax
0x180009f5a  test    eax, eax
0x180009f5c  jns     short loc_180009F7B
0x180009f5e  mov     rcx, [rbp+188h]; this
0x180009f65  lea     r8, aWil; "wil"
0x180009f6c  mov     r9d, eax; char *
0x180009f6f  mov     edx, 0DEh; void *
0x180009f74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009f79  jmp     short loc_180009F3F
0x180009f7b  lea     rcx, [rsp+280h+var_248]
0x180009f80  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009f85  movsxd  rcx, [rsp+280h+var_250]
0x180009f8a  movsxd  rax, [rsp+280h+var_24C]
0x180009f8f  shl     rcx, 1Fh
0x180009f93  or      rcx, rax
0x180009f96  mov     [rdi], rcx
0x180009f99  xor     ebx, ebx
0x180009f9b  lea     rcx, [rsp+280h+var_240]
0x180009fa0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009fa5  mov     eax, ebx
0x180009fa7  mov     rcx, [rbp+180h+var_20]
0x180009fae  xor     rcx, rsp; StackCookie
0x180009fb1  call    __security_check_cookie
0x180009fb6  mov     rbx, [rsp+280h+arg_8]
0x180009fbe  add     rsp, 270h
0x180009fc5  pop     r14
0x180009fc7  pop     rdi
0x180009fc8  pop     rbp
0x180009fc9  retn
```
