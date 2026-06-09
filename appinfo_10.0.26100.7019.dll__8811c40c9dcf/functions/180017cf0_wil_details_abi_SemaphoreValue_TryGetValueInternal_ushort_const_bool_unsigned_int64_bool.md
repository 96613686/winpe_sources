# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180017cf0`
- end: `0x180017f06`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `534`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1800101f0`
- `0x180017c70`

## callees

- `0x180007c78`
- `0x18001274c`
- `0x180017cf0`
- `0x180017f48`
- `0x180017f68`
- `0x180017fb8`
- `0x180018150`
- `0x180018170`
- `0x18001abcc`
- `0x180042950`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180017d96`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180017e3b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180017d96`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180017e3b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017dac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017dac`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned int LastError; // ebx
  size_t *v6; // r8
  const wchar_t *v7; // r9
  size_t *v8; // r8
  HANDLE v9; // rax
  const char *v10; // r9
  int ValueFromSemaphore; // eax
  int v13; // edi
  HANDLE v14; // rax
  const char *v15; // r9
  int v16; // eax
  size_t v17; // [rsp+20h] [rbp-E0h]
  size_t pcchDestLength; // [rsp+30h] [rbp-D0h] BYREF
  int v19; // [rsp+38h] [rbp-C8h] BYREF
  int v20; // [rsp+3Ch] [rbp-C4h] BYREF
  HANDLE v21[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszDest[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  LastError = 0;
  *a3 = 0;
  if ( StringValidateDestW(a1, 0x104u, (const size_t)a3) < 0 )
    pszDest[0] = 0;
  else
    StringCopyWorkerW(pszDest, 0x104u, v6, v7, v17);
  pcchDestLength = 0;
  if ( StringValidateDestAndLengthW(pszDest, 0x104u, &pcchDestLength, (const size_t)v7) >= 0 )
    StringCopyWorkerW(&pszDest[pcchDestLength], 260 - pcchDestLength, v8, L"_p0", v17);
  v9 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
  v21[0] = v9;
  if ( v9 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, &v20);
    v13 = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      StringCchCatW(pszDest, 0x104u, L"h");
      v14 = OpenSemaphoreW(0x1F0003u, 0, pszDest);
      pcchDestLength = (size_t)v14;
      if ( !v14 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, (unsigned int)"wil", v15);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&pcchDestLength);
        goto LABEL_17;
      }
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v14, &v19);
      v13 = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&pcchDestLength);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_17;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDB,
        (unsigned int)"wil",
        (const char *)(unsigned int)v16,
        v17);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&pcchDestLength);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD3,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v17);
    }
    LastError = v13;
  }
  else if ( GetLastError() != 2 )
  {
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, (unsigned int)"wil", v10);
  }
LABEL_17:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
  return LastError;
}

```

## disassembly

```asm
0x180017cf0  mov     [rsp-8+arg_0], rbx
0x180017cf5  mov     [rsp-8+arg_8], rsi
0x180017cfa  push    rbp
0x180017cfb  push    rdi
0x180017cfc  push    r14
0x180017cfe  lea     rbp, [rsp-170h]
0x180017d06  sub     rsp, 270h
0x180017d0d  mov     rax, cs:__security_cookie
0x180017d14  xor     rax, rsp
0x180017d17  mov     [rbp+180h+var_20], rax
0x180017d1e  mov     r14d, 104h
0x180017d24  xor     ebx, ebx
0x180017d26  mov     edx, r14d; cchDest
0x180017d29  mov     [r8], rbx
0x180017d2c  mov     rsi, r8
0x180017d2f  mov     r9, rcx
0x180017d32  call    StringValidateDestW
0x180017d37  test    eax, eax
0x180017d39  js      short loc_180017D4A
0x180017d3b  mov     edx, r14d; cchDest
0x180017d3e  lea     rcx, [rsp+280h+pszDest]; pszDest
0x180017d43  call    StringCopyWorkerW
0x180017d48  jmp     short loc_180017D4F
0x180017d4a  mov     [rsp+280h+pszDest], bx
0x180017d4f  lea     r8, [rsp+280h+pcchDestLength]; pcchDestLength
0x180017d54  mov     [rsp+280h+pcchDestLength], rbx
0x180017d59  mov     rdx, r14; cchDest
0x180017d5c  lea     rcx, [rsp+280h+pszDest]; pszDest
0x180017d61  call    StringValidateDestAndLengthW
0x180017d66  test    eax, eax
0x180017d68  js      short loc_180017D8A
0x180017d6a  mov     rax, [rsp+280h+pcchDestLength]
0x180017d6f  lea     rcx, [rsp+280h+pszDest]
0x180017d74  mov     rdx, r14
0x180017d77  lea     r9, aP0; "_p0"
0x180017d7e  sub     rdx, rax; cchDest
0x180017d81  lea     rcx, [rcx+rax*2]; pszDest
0x180017d85  call    StringCopyWorkerW
0x180017d8a  lea     r8, [rsp+280h+pszDest]; lpName
0x180017d8f  xor     edx, edx; bInheritHandle
0x180017d91  mov     ecx, 1F0003h; dwDesiredAccess
0x180017d96  call    cs:__imp_OpenSemaphoreW
0x180017d9d  nop     dword ptr [rax+rax+00h]
0x180017da2  mov     [rsp+280h+var_240], rax
0x180017da7  test    rax, rax
0x180017daa  jnz     short loc_180017DDE
0x180017dac  call    cs:__imp_GetLastError
0x180017db3  nop     dword ptr [rax+rax+00h]
0x180017db8  cmp     eax, 2
0x180017dbb  jz      loc_180017ED2
0x180017dc1  mov     rcx, [rbp+188h]; this
0x180017dc8  lea     r8, aWil; "wil"
0x180017dcf  mov     edx, 0CDh; void *
0x180017dd4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180017dd9  jmp     loc_180017EDE
0x180017dde  lea     rdx, [rsp+280h+var_244]; int *
0x180017de3  mov     [rsp+280h+var_244], ebx
0x180017de7  mov     rcx, rax; hHandle
0x180017dea  mov     [rsp+280h+var_248], ebx
0x180017dee  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180017df3  mov     edi, eax
0x180017df5  test    eax, eax
0x180017df7  jns     short loc_180017E1B
0x180017df9  mov     rcx, [rbp+188h]; this
0x180017e00  lea     r8, aWil; "wil"
0x180017e07  mov     r9d, eax; char *
0x180017e0a  mov     edx, 0D3h; void *
0x180017e0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017e14  mov     ebx, edi
0x180017e16  jmp     loc_180017ED2
0x180017e1b  lea     r8, asc_18004A4BC; "h"
0x180017e22  mov     rdx, r14; unsigned __int64
0x180017e25  lea     rcx, [rsp+280h+pszDest]; unsigned __int16 *
0x180017e2a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180017e2f  lea     r8, [rsp+280h+pszDest]; lpName
0x180017e34  xor     edx, edx; bInheritHandle
0x180017e36  mov     ecx, 1F0003h; dwDesiredAccess
0x180017e3b  call    cs:__imp_OpenSemaphoreW
0x180017e42  nop     dword ptr [rax+rax+00h]
0x180017e47  mov     [rsp+280h+pcchDestLength], rax
0x180017e4c  test    rax, rax
0x180017e4f  jnz     short loc_180017E77
0x180017e51  mov     rcx, [rbp+188h]; this
0x180017e58  lea     r8, aWil; "wil"
0x180017e5f  mov     edx, 0D9h; void *
0x180017e64  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180017e69  lea     rcx, [rsp+280h+pcchDestLength]
0x180017e6e  mov     ebx, eax
0x180017e70  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180017e75  jmp     short loc_180017ED2
0x180017e77  lea     rdx, [rsp+280h+var_248]; int *
0x180017e7c  mov     rcx, rax; hHandle
0x180017e7f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180017e84  mov     edi, eax
0x180017e86  test    eax, eax
0x180017e88  jns     short loc_180017EB4
0x180017e8a  mov     rcx, [rbp+188h]; this
0x180017e91  lea     r8, aWil; "wil"
0x180017e98  mov     r9d, eax; char *
0x180017e9b  mov     edx, 0DBh; void *
0x180017ea0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017ea5  lea     rcx, [rsp+280h+pcchDestLength]
0x180017eaa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180017eaf  jmp     loc_180017E14
0x180017eb4  lea     rcx, [rsp+280h+pcchDestLength]
0x180017eb9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180017ebe  movsxd  rdx, [rsp+280h+var_248]
0x180017ec3  movsxd  rcx, [rsp+280h+var_244]
0x180017ec8  shl     rdx, 1Fh
0x180017ecc  or      rdx, rcx
0x180017ecf  mov     [rsi], rdx
0x180017ed2  lea     rcx, [rsp+280h+var_240]
0x180017ed7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180017edc  mov     eax, ebx
0x180017ede  mov     rcx, [rbp+180h+var_20]
0x180017ee5  xor     rcx, rsp; StackCookie
0x180017ee8  call    __security_check_cookie
0x180017eed  lea     r11, [rsp+280h+var_10]
0x180017ef5  mov     rbx, [r11+20h]
0x180017ef9  mov     rsi, [r11+28h]
0x180017efd  mov     rsp, r11
0x180017f00  pop     r14
0x180017f02  pop     rdi
0x180017f03  pop     rbp
0x180017f04  retn
```
