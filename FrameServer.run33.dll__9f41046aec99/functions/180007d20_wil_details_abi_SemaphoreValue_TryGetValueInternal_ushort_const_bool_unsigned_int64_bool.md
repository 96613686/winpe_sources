# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180007d20`
- end: `0x180007ed8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180005f14`

## callees

- `0x180003e20`
- `0x180005d98`
- `0x180006bf8`
- `0x180007804`
- `0x180007824`
- `0x180007ae8`
- `0x180007bcc`
- `0x180007d20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007d84`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007e22`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007d84`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180007e22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d94`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007d94`

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
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v10; // rdx
  HANDLE v11; // rax
  const char *v12; // r9
  int v13; // eax
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v17; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18[0] = v6;
  if ( v6 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v16);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v15);
      goto LABEL_13;
    }
    StringCchCatW(Name, v10, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v17 = v11;
    if ( v11 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v15);
      LastError = v13;
      if ( v13 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v17);
        *a3 = v16 | (unsigned __int64)((__int64)v15 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v13,
        v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v12);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x180007d20  mov     [rsp-8+arg_8], rbx
0x180007d25  mov     [rsp-8+arg_18], rdi
0x180007d2a  push    rbp
0x180007d2b  lea     rbp, [rsp-160h]
0x180007d33  sub     rsp, 260h
0x180007d3a  mov     rax, cs:__security_cookie
0x180007d41  xor     rax, rsp
0x180007d44  mov     [rbp+160h+var_10], rax
0x180007d4b  mov     rdi, r8
0x180007d4e  mov     qword ptr [r8], 0
0x180007d55  mov     r8, rcx; unsigned __int16 *
0x180007d58  mov     edx, 104h; unsigned __int64
0x180007d5d  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180007d62  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180007d67  lea     r8, aP0; "_p0"
0x180007d6e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180007d73  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007d78  lea     r8, [rsp+260h+Name]; lpName
0x180007d7d  xor     edx, edx; bInheritHandle
0x180007d7f  mov     ecx, 1F0003h; dwDesiredAccess
0x180007d84  call    cs:__imp_OpenSemaphoreW
0x180007d8a  mov     [rsp+260h+var_230], rax
0x180007d8f  test    rax, rax
0x180007d92  jnz     short loc_180007DC2
0x180007d94  call    cs:__imp_GetLastError
0x180007d9a  cmp     eax, 2
0x180007d9d  jz      loc_180007EA6
0x180007da3  mov     rcx, [rbp+168h]; this
0x180007daa  lea     r8, aWil; "wil"
0x180007db1  mov     edx, 0D0h; void *
0x180007db6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007dbb  mov     ebx, eax
0x180007dbd  jmp     loc_180007EA8
0x180007dc2  lea     rdx, [rsp+260h+var_23C]; int *
0x180007dc7  mov     [rsp+260h+var_23C], 0
0x180007dcf  mov     rcx, rax; hHandle
0x180007dd2  mov     [rsp+260h+var_240], 0; int
0x180007dda  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007ddf  mov     ebx, eax
0x180007de1  test    eax, eax
0x180007de3  jns     short loc_180007E05
0x180007de5  mov     rcx, [rbp+168h]; this
0x180007dec  lea     r8, aWil; "wil"
0x180007df3  mov     r9d, eax; char *
0x180007df6  mov     edx, 0D6h; void *
0x180007dfb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007e00  jmp     loc_180007EA8
0x180007e05  lea     r8, asc_1800F3488; "h"
0x180007e0c  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180007e11  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007e16  lea     r8, [rsp+260h+Name]; lpName
0x180007e1b  xor     edx, edx; bInheritHandle
0x180007e1d  mov     ecx, 1F0003h; dwDesiredAccess
0x180007e22  call    cs:__imp_OpenSemaphoreW
0x180007e28  mov     [rsp+260h+var_238], rax
0x180007e2d  test    rax, rax
0x180007e30  jnz     short loc_180007E58
0x180007e32  mov     rcx, [rbp+168h]; this
0x180007e39  lea     r8, aWil; "wil"
0x180007e40  mov     edx, 0DCh; void *
0x180007e45  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007e4a  mov     ebx, eax
0x180007e4c  lea     rcx, [rsp+260h+var_238]
0x180007e51  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007e56  jmp     short loc_180007EA8
0x180007e58  lea     rdx, [rsp+260h+var_240]; int *
0x180007e5d  mov     rcx, rax; hHandle
0x180007e60  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007e65  mov     ebx, eax
0x180007e67  test    eax, eax
0x180007e69  jns     short loc_180007E88
0x180007e6b  mov     rcx, [rbp+168h]; this
0x180007e72  lea     r8, aWil; "wil"
0x180007e79  mov     r9d, eax; char *
0x180007e7c  mov     edx, 0DEh; void *
0x180007e81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180007e86  jmp     short loc_180007E4C
0x180007e88  lea     rcx, [rsp+260h+var_238]
0x180007e8d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007e92  movsxd  rcx, [rsp+260h+var_240]
0x180007e97  movsxd  rax, [rsp+260h+var_23C]
0x180007e9c  shl     rcx, 1Fh
0x180007ea0  or      rcx, rax
0x180007ea3  mov     [rdi], rcx
0x180007ea6  xor     ebx, ebx
0x180007ea8  lea     rcx, [rsp+260h+var_230]
0x180007ead  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007eb2  mov     eax, ebx
0x180007eb4  mov     rcx, [rbp+160h+var_10]
0x180007ebb  xor     rcx, rsp; StackCookie
0x180007ebe  call    __security_check_cookie
0x180007ec3  lea     r11, [rsp+260h+var_s0]
0x180007ecb  mov     rbx, [r11+18h]
0x180007ecf  mov     rdi, [r11+28h]
0x180007ed3  mov     rsp, r11
0x180007ed6  pop     rbp
0x180007ed7  retn
```
