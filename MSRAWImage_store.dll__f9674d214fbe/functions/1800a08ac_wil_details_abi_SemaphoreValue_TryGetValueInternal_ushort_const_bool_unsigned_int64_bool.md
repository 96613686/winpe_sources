# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800a08ac`
- end: `0x1800a0a66`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `442`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18009f0ec`

## callees

- `0x180002a00`
- `0x18009ef88`
- `0x18009faac`
- `0x1800a0174`
- `0x1800a01a0`
- `0x1800a06fc`
- `0x1800a0818`
- `0x1800a08ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800a0912`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800a09a8`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800a0912`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800a09a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0928`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a0928`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        STRSAFE_PCNZWCH pszSrc,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned int LastError; // ebx
  unsigned __int64 v6; // rdx
  HANDLE v7; // rax
  unsigned int v8; // r8d
  const char *v9; // r9
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  unsigned int v12; // r8d
  int v13; // edi
  HANDLE v14; // rax
  unsigned int v15; // r8d
  const char *v16; // r9
  int v17; // eax
  unsigned int v18; // r8d
  size_t v20; // [rsp+28h] [rbp-E0h]
  int v21; // [rsp+28h] [rbp-E0h]
  int v22[2]; // [rsp+38h] [rbp-D0h] BYREF
  HANDLE v23; // [rsp+40h] [rbp-C8h] BYREF
  HANDLE v24[2]; // [rsp+48h] [rbp-C0h] BYREF
  wchar_t pszDest[264]; // [rsp+58h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+280h] [rbp+178h]

  LastError = 0;
  *a3 = 0;
  StringCopyWorkerW(pszDest, 0x104u, a3, pszSrc, v20);
  StringCchCatW(pszDest, v6, L"_p0");
  v7 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v24[0] = v7;
  if ( v7 )
  {
    v22[1] = 0;
    v22[0] = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v7, &v22[1]);
    v13 = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      StringCchCatW(pszDest, v11, L"h");
      v14 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
      v23 = v14;
      if ( !v14 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDB, v15, v16);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
        goto LABEL_12;
      }
      v17 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, v22);
      v13 = v17;
      if ( v17 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
        *a3 = v22[1] | (unsigned __int64)((__int64)v22[0] << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDD, v18, (const char *)(unsigned int)v17, v21);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v23);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD5, v12, (const char *)(unsigned int)ValueFromSemaphore, v21);
    }
    LastError = v13;
  }
  else if ( GetLastError() != 2 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCF, v8, v9);
  }
LABEL_12:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v24);
  return LastError;
}

```

## disassembly

```asm
0x1800a08ac  mov     rax, rsp
0x1800a08af  mov     [rax+8], rbx
0x1800a08b3  mov     [rax+10h], rsi
0x1800a08b7  mov     [rax+20h], rdi
0x1800a08bb  push    rbp
0x1800a08bc  lea     rbp, [rax-178h]
0x1800a08c3  sub     rsp, 270h
0x1800a08ca  mov     rax, cs:__security_cookie
0x1800a08d1  xor     rax, rsp
0x1800a08d4  mov     [rbp+170h+var_10], rax
0x1800a08db  mov     r9, rcx; pszSrc
0x1800a08de  xor     ebx, ebx
0x1800a08e0  lea     rcx, [rsp+270h+pszDest]; pszDest
0x1800a08e5  mov     [r8], rbx
0x1800a08e8  mov     edx, 104h; cchDest
0x1800a08ed  mov     rsi, r8
0x1800a08f0  call    StringCopyWorkerW
0x1800a08f5  lea     r8, aP0; "_p0"
0x1800a08fc  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800a0901  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a0906  lea     r8, [rsp+270h+pszDest]; lpName
0x1800a090b  xor     edx, edx; bInheritHandle
0x1800a090d  mov     ecx, 1F0003h; dwDesiredAccess
0x1800a0912  call    cs:__imp_OpenSemaphoreW
0x1800a0919  nop     dword ptr [rax+rax+00h]
0x1800a091e  mov     [rsp+270h+var_230], rax
0x1800a0923  test    rax, rax
0x1800a0926  jnz     short loc_1800A0955
0x1800a0928  call    cs:__imp_GetLastError
0x1800a092f  nop     dword ptr [rax+rax+00h]
0x1800a0934  cmp     eax, 2
0x1800a0937  jz      loc_1800A0A31
0x1800a093d  mov     rcx, [rbp+178h]; this
0x1800a0944  mov     edx, 0CFh; void *
0x1800a0949  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a094e  mov     ebx, eax
0x1800a0950  jmp     loc_1800A0A31
0x1800a0955  lea     rdx, [rsp+270h+var_240+4]; int *
0x1800a095a  mov     [rsp+270h+var_240+4], ebx
0x1800a095e  mov     rcx, rax; hHandle
0x1800a0961  mov     [rsp+270h+var_240], ebx
0x1800a0965  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800a096a  mov     edi, eax
0x1800a096c  test    eax, eax
0x1800a096e  jns     short loc_1800A098B
0x1800a0970  mov     rcx, [rbp+178h]; this
0x1800a0977  mov     r9d, eax; char *
0x1800a097a  mov     edx, 0D5h; void *
0x1800a097f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0984  mov     ebx, edi
0x1800a0986  jmp     loc_1800A0A31
0x1800a098b  lea     r8, asc_1800D4AB0; "h"
0x1800a0992  lea     rcx, [rsp+270h+pszDest]; unsigned __int16 *
0x1800a0997  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800a099c  lea     r8, [rsp+270h+pszDest]; lpName
0x1800a09a1  xor     edx, edx; bInheritHandle
0x1800a09a3  mov     ecx, 1F0003h; dwDesiredAccess
0x1800a09a8  call    cs:__imp_OpenSemaphoreW
0x1800a09af  nop     dword ptr [rax+rax+00h]
0x1800a09b4  mov     [rsp+270h+var_238], rax
0x1800a09b9  test    rax, rax
0x1800a09bc  jnz     short loc_1800A09DD
0x1800a09be  mov     rcx, [rbp+178h]; this
0x1800a09c5  mov     edx, 0DBh; void *
0x1800a09ca  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800a09cf  lea     rcx, [rsp+270h+var_238]
0x1800a09d4  mov     ebx, eax
0x1800a09d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a09db  jmp     short loc_1800A0A31
0x1800a09dd  lea     rdx, [rsp+270h+var_240]; int *
0x1800a09e2  mov     rcx, rax; hHandle
0x1800a09e5  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800a09ea  mov     edi, eax
0x1800a09ec  test    eax, eax
0x1800a09ee  jns     short loc_1800A0A13
0x1800a09f0  mov     rcx, [rbp+178h]; this
0x1800a09f7  mov     r9d, eax; char *
0x1800a09fa  mov     edx, 0DDh; void *
0x1800a09ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a0a04  lea     rcx, [rsp+270h+var_238]
0x1800a0a09  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a0a0e  jmp     loc_1800A0984
0x1800a0a13  lea     rcx, [rsp+270h+var_238]
0x1800a0a18  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a0a1d  movsxd  rdx, [rsp+270h+var_240]
0x1800a0a22  movsxd  rcx, [rsp+270h+var_240+4]
0x1800a0a27  shl     rdx, 1Fh
0x1800a0a2b  or      rdx, rcx
0x1800a0a2e  mov     [rsi], rdx
0x1800a0a31  lea     rcx, [rsp+270h+var_230]
0x1800a0a36  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800a0a3b  mov     eax, ebx
0x1800a0a3d  mov     rcx, [rbp+170h+var_10]
0x1800a0a44  xor     rcx, rsp; StackCookie
0x1800a0a47  call    __security_check_cookie
0x1800a0a4c  lea     r11, [rsp+270h+var_s0]
0x1800a0a54  mov     rbx, [r11+10h]
0x1800a0a58  mov     rsi, [r11+18h]
0x1800a0a5c  mov     rdi, [r11+28h]
0x1800a0a60  mov     rsp, r11
0x1800a0a63  pop     rbp
0x1800a0a64  retn
```
