# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180021ec0`
- end: `0x18002206b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `427`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180021e4c`

## callees

- `0x18001be10`
- `0x18001d848`
- `0x18001f030`
- `0x180020fec`
- `0x18002100c`
- `0x180021a3c`
- `0x180021b1c`
- `0x180021ec0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180021f24`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180021fb6`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180021f24`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180021fb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021f34`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021f34`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
      goto LABEL_12;
    }
    StringCchCatW(pszDest, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
    v23 = v13;
    if ( !v13 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
      goto LABEL_12;
    }
    v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v21);
    LastError = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v20);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
      goto LABEL_12;
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
    *a3 = v22 | (unsigned __int64)((__int64)v21 << 31);
LABEL_11:
    LastError = 0;
    goto LABEL_12;
  }
  if ( GetLastError() == 2 )
    goto LABEL_11;
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v7, v8);
LABEL_12:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v24);
  return LastError;
}

```

## disassembly

```asm
0x180021ec0  mov     [rsp-8+arg_8], rbx
0x180021ec5  mov     [rsp-8+arg_18], rdi
0x180021eca  push    rbp
0x180021ecb  lea     rbp, [rsp-170h]
0x180021ed3  sub     rsp, 270h
0x180021eda  mov     rax, cs:__security_cookie
0x180021ee1  xor     rax, rsp
0x180021ee4  mov     [rbp+170h+var_10], rax
0x180021eeb  mov     rdi, r8
0x180021eee  mov     qword ptr [r8], 0
0x180021ef5  mov     r9, rcx; pszSrc
0x180021ef8  mov     edx, 104h; cchDest
0x180021efd  lea     rcx, [rsp+270h+pszDest]; pszDest
0x180021f02  call    StringCopyWorkerW
0x180021f07  lea     r8, aP0; "_p0"
0x180021f0e  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180021f13  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180021f18  lea     r8, [rsp+270h+pszDest]; lpName
0x180021f1d  xor     edx, edx; bInheritHandle
0x180021f1f  mov     ecx, 1F0003h; dwDesiredAccess
0x180021f24  call    cs:__imp_OpenSemaphoreW
0x180021f2a  mov     [rsp+270h+var_230], rax
0x180021f2f  test    rax, rax
0x180021f32  jnz     short loc_180021F5C
0x180021f34  call    cs:__imp_GetLastError
0x180021f3a  cmp     eax, 2
0x180021f3d  jnz     short loc_180021F44
0x180021f3f  jmp     loc_180022039
0x180021f44  mov     rcx, [rbp+178h]; this
0x180021f4b  mov     edx, 0D0h; void *
0x180021f50  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180021f55  mov     ebx, eax
0x180021f57  jmp     loc_18002203B
0x180021f5c  mov     [rsp+270h+var_23C], 0
0x180021f64  mov     [rsp+270h+var_240], 0
0x180021f6c  lea     rdx, [rsp+270h+var_23C]; int *
0x180021f71  mov     rcx, rax; hHandle
0x180021f74  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180021f79  mov     ebx, eax
0x180021f7b  test    eax, eax
0x180021f7d  jns     short loc_180021F99
0x180021f7f  mov     rcx, [rbp+178h]; this
0x180021f86  mov     r9d, eax; char *
0x180021f89  mov     edx, 0D6h; void *
0x180021f8e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180021f93  nop
0x180021f94  jmp     loc_18002203B
0x180021f99  lea     r8, asc_180039608; "h"
0x180021fa0  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x180021fa5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180021faa  lea     r8, [rsp+270h+pszDest]; lpName
0x180021faf  xor     edx, edx; bInheritHandle
0x180021fb1  mov     ecx, 1F0003h; dwDesiredAccess
0x180021fb6  call    cs:__imp_OpenSemaphoreW
0x180021fbc  mov     [rsp+270h+var_238], rax
0x180021fc1  test    rax, rax
0x180021fc4  jnz     short loc_180021FE6
0x180021fc6  mov     rcx, [rbp+178h]; this
0x180021fcd  mov     edx, 0DCh; void *
0x180021fd2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180021fd7  mov     ebx, eax
0x180021fd9  lea     rcx, [rsp+270h+var_238]
0x180021fde  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180021fe3  nop
0x180021fe4  jmp     short loc_18002203B
0x180021fe6  lea     rdx, [rsp+270h+var_240]; int *
0x180021feb  mov     rcx, rax; hHandle
0x180021fee  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180021ff3  mov     ebx, eax
0x180021ff5  test    eax, eax
0x180021ff7  jns     short loc_18002201B
0x180021ff9  mov     rcx, [rbp+178h]; this
0x180022000  mov     r9d, eax; char *
0x180022003  mov     edx, 0DEh; void *
0x180022008  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002200d  nop
0x18002200e  lea     rcx, [rsp+270h+var_238]
0x180022013  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180022018  nop
0x180022019  jmp     short loc_18002203B
0x18002201b  lea     rcx, [rsp+270h+var_238]
0x180022020  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180022025  movsxd  rcx, [rsp+270h+var_240]
0x18002202a  shl     rcx, 1Fh
0x18002202e  movsxd  rax, [rsp+270h+var_23C]
0x180022033  or      rcx, rax
0x180022036  mov     [rdi], rcx
0x180022039  xor     ebx, ebx
0x18002203b  lea     rcx, [rsp+270h+var_230]
0x180022040  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180022045  mov     eax, ebx
0x180022047  mov     rcx, [rbp+170h+var_10]
0x18002204e  xor     rcx, rsp; StackCookie
0x180022051  call    __security_check_cookie
0x180022056  lea     r11, [rsp+270h+var_s0]
0x18002205e  mov     rbx, [r11+18h]
0x180022062  mov     rdi, [r11+28h]
0x180022066  mov     rsp, r11
0x180022069  pop     rbp
0x18002206a  retn
```
