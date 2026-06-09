# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001ac50`
- end: `0x18001adfa`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001abcc`

## callees

- `0x180004a48`
- `0x1800074f4`
- `0x180015c20`
- `0x180015c40`
- `0x18001a600`
- `0x18001a67c`
- `0x18001ac50`
- `0x18002d220`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001acb4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001ad4b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001acb4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001ad4b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001acc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001acc4`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
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
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20[0] = v6;
  if ( v6 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v17);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v12 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v17);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v15,
        v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v13, v14);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x18001ac50  mov     [rsp-8+arg_8], rbx
0x18001ac55  mov     [rsp-8+arg_18], rdi
0x18001ac5a  push    rbp
0x18001ac5b  lea     rbp, [rsp-160h]
0x18001ac63  sub     rsp, 260h
0x18001ac6a  mov     rax, cs:__security_cookie
0x18001ac71  xor     rax, rsp
0x18001ac74  mov     [rbp+160h+var_10], rax
0x18001ac7b  mov     rdi, r8
0x18001ac7e  mov     qword ptr [r8], 0
0x18001ac85  mov     r8, rcx; unsigned __int16 *
0x18001ac88  mov     edx, 104h; unsigned __int64
0x18001ac8d  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001ac92  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001ac97  lea     r8, aP0; "_p0"
0x18001ac9e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001aca3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001aca8  lea     r8, [rsp+260h+Name]; lpName
0x18001acad  xor     edx, edx; bInheritHandle
0x18001acaf  mov     ecx, 1F0003h; dwDesiredAccess
0x18001acb4  call    cs:__imp_OpenSemaphoreW
0x18001acba  mov     [rsp+260h+var_230], rax
0x18001acbf  test    rax, rax
0x18001acc2  jnz     short loc_18001ACEB
0x18001acc4  call    cs:__imp_GetLastError
0x18001acca  cmp     eax, 2
0x18001accd  jz      loc_18001ADC8
0x18001acd3  mov     rcx, [rbp+168h]; this
0x18001acda  mov     edx, 0D0h; void *
0x18001acdf  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ace4  mov     ebx, eax
0x18001ace6  jmp     loc_18001ADCA
0x18001aceb  lea     rdx, [rsp+260h+var_23C]; int *
0x18001acf0  mov     [rsp+260h+var_23C], 0
0x18001acf8  mov     rcx, rax; hHandle
0x18001acfb  mov     [rsp+260h+var_240], 0; int
0x18001ad03  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001ad08  mov     ebx, eax
0x18001ad0a  test    eax, eax
0x18001ad0c  jns     short loc_18001AD2E
0x18001ad0e  mov     rcx, [rbp+168h]; this
0x18001ad15  lea     r8, aWil; "wil"
0x18001ad1c  mov     r9d, eax; char *
0x18001ad1f  mov     edx, 0D6h; void *
0x18001ad24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ad29  jmp     loc_18001ADCA
0x18001ad2e  lea     r8, asc_180031F60; "h"
0x18001ad35  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18001ad3a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001ad3f  lea     r8, [rsp+260h+Name]; lpName
0x18001ad44  xor     edx, edx; bInheritHandle
0x18001ad46  mov     ecx, 1F0003h; dwDesiredAccess
0x18001ad4b  call    cs:__imp_OpenSemaphoreW
0x18001ad51  mov     [rsp+260h+var_238], rax
0x18001ad56  test    rax, rax
0x18001ad59  jnz     short loc_18001AD7A
0x18001ad5b  mov     rcx, [rbp+168h]; this
0x18001ad62  mov     edx, 0DCh; void *
0x18001ad67  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ad6c  mov     ebx, eax
0x18001ad6e  lea     rcx, [rsp+260h+var_238]
0x18001ad73  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001ad78  jmp     short loc_18001ADCA
0x18001ad7a  lea     rdx, [rsp+260h+var_240]; int *
0x18001ad7f  mov     rcx, rax; hHandle
0x18001ad82  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001ad87  mov     ebx, eax
0x18001ad89  test    eax, eax
0x18001ad8b  jns     short loc_18001ADAA
0x18001ad8d  mov     rcx, [rbp+168h]; this
0x18001ad94  lea     r8, aWil; "wil"
0x18001ad9b  mov     r9d, eax; char *
0x18001ad9e  mov     edx, 0DEh; void *
0x18001ada3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ada8  jmp     short loc_18001AD6E
0x18001adaa  lea     rcx, [rsp+260h+var_238]
0x18001adaf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001adb4  movsxd  rcx, [rsp+260h+var_240]
0x18001adb9  movsxd  rax, [rsp+260h+var_23C]
0x18001adbe  shl     rcx, 1Fh
0x18001adc2  or      rcx, rax
0x18001adc5  mov     [rdi], rcx
0x18001adc8  xor     ebx, ebx
0x18001adca  lea     rcx, [rsp+260h+var_230]
0x18001adcf  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001add4  mov     eax, ebx
0x18001add6  mov     rcx, [rbp+160h+var_10]
0x18001addd  xor     rcx, rsp; StackCookie
0x18001ade0  call    __security_check_cookie
0x18001ade5  lea     r11, [rsp+260h+var_s0]
0x18001aded  mov     rbx, [r11+18h]
0x18001adf1  mov     rdi, [r11+28h]
0x18001adf5  mov     rsp, r11
0x18001adf8  pop     rbp
0x18001adf9  retn
```
