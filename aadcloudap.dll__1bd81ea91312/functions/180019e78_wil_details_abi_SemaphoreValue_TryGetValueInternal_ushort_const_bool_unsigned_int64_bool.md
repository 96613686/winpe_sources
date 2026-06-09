# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180019e78`
- end: `0x18001a01a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180019e04`

## callees

- `0x180003c20`
- `0x18000a200`
- `0x180015fdc`
- `0x180018ffc`
- `0x18001901c`
- `0x180019798`
- `0x180019824`
- `0x180019e78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180019ee1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180019f73`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180019ee1`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180019f73`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ef1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ef1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned int v10; // r8d
  HANDLE v11; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  int v14; // eax
  unsigned int v15; // r8d
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20[0] = v5;
  if ( v5 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v10, (const char *)(unsigned int)ValueFromSemaphore, v17);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v11;
    if ( v11 )
    {
      v14 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v17);
      LastError = v14;
      if ( v14 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v15, (const char *)(unsigned int)v14, v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v12, v13);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v6, v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x180019e78  mov     [rsp-8+arg_8], rbx
0x180019e7d  push    rbp
0x180019e7e  push    rdi
0x180019e7f  push    r14
0x180019e81  lea     rbp, [rsp-160h]
0x180019e89  sub     rsp, 260h
0x180019e90  mov     rax, cs:__security_cookie
0x180019e97  xor     rax, rsp
0x180019e9a  mov     [rbp+170h+var_20], rax
0x180019ea1  mov     rdi, r8
0x180019ea4  mov     qword ptr [r8], 0
0x180019eab  mov     r8, rcx; unsigned __int16 *
0x180019eae  mov     r14d, 104h
0x180019eb4  mov     edx, r14d; unsigned __int64
0x180019eb7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180019ebc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180019ec1  lea     r8, aP0; "_p0"
0x180019ec8  mov     edx, r14d; unsigned __int64
0x180019ecb  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180019ed0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180019ed5  lea     r8, [rsp+270h+Name]; lpName
0x180019eda  xor     edx, edx; bInheritHandle
0x180019edc  mov     ecx, 1F0003h; dwDesiredAccess
0x180019ee1  call    cs:__imp_OpenSemaphoreW
0x180019ee7  mov     [rsp+270h+var_240], rax
0x180019eec  test    rax, rax
0x180019eef  jnz     short loc_180019F17
0x180019ef1  call    cs:__imp_GetLastError
0x180019ef7  cmp     eax, 2
0x180019efa  jz      loc_180019FE9
0x180019f00  mov     rcx, [rbp+178h]; this
0x180019f07  lea     edx, [r14-34h]; void *
0x180019f0b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019f10  mov     ebx, eax
0x180019f12  jmp     loc_180019FEB
0x180019f17  mov     [rsp+270h+var_24C], 0
0x180019f1f  mov     [rsp+270h+var_250], 0; int
0x180019f27  lea     rdx, [rsp+270h+var_24C]; int *
0x180019f2c  mov     rcx, rax; hHandle
0x180019f2f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180019f34  mov     ebx, eax
0x180019f36  test    eax, eax
0x180019f38  jns     short loc_180019F53
0x180019f3a  mov     rcx, [rbp+178h]; this
0x180019f41  mov     r9d, eax; char *
0x180019f44  mov     edx, 0D6h; void *
0x180019f49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019f4e  jmp     loc_180019FEB
0x180019f53  lea     r8, asc_1800AF908; "h"
0x180019f5a  mov     rdx, r14; unsigned __int64
0x180019f5d  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180019f62  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180019f67  lea     r8, [rsp+270h+Name]; lpName
0x180019f6c  xor     edx, edx; bInheritHandle
0x180019f6e  mov     ecx, 1F0003h; dwDesiredAccess
0x180019f73  call    cs:__imp_OpenSemaphoreW
0x180019f79  mov     [rsp+270h+var_248], rax
0x180019f7e  test    rax, rax
0x180019f81  jnz     short loc_180019FA2
0x180019f83  mov     rcx, [rbp+178h]; this
0x180019f8a  mov     edx, 0DCh; void *
0x180019f8f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019f94  mov     ebx, eax
0x180019f96  lea     rcx, [rsp+270h+var_248]
0x180019f9b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180019fa0  jmp     short loc_180019FEB
0x180019fa2  lea     rdx, [rsp+270h+var_250]; int *
0x180019fa7  mov     rcx, rax; hHandle
0x180019faa  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180019faf  mov     ebx, eax
0x180019fb1  test    eax, eax
0x180019fb3  jns     short loc_180019FCB
0x180019fb5  mov     rcx, [rbp+178h]; this
0x180019fbc  mov     r9d, eax; char *
0x180019fbf  mov     edx, 0DEh; void *
0x180019fc4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019fc9  jmp     short loc_180019F96
0x180019fcb  lea     rcx, [rsp+270h+var_248]
0x180019fd0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180019fd5  movsxd  rcx, [rsp+270h+var_250]
0x180019fda  shl     rcx, 1Fh
0x180019fde  movsxd  rax, [rsp+270h+var_24C]
0x180019fe3  or      rcx, rax
0x180019fe6  mov     [rdi], rcx
0x180019fe9  xor     ebx, ebx
0x180019feb  lea     rcx, [rsp+270h+var_240]
0x180019ff0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180019ff5  mov     eax, ebx
0x180019ff7  mov     rcx, [rbp+170h+var_20]
0x180019ffe  xor     rcx, rsp; StackCookie
0x18001a001  call    __security_check_cookie
0x18001a006  mov     rbx, [rsp+270h+arg_8]
0x18001a00e  add     rsp, 260h
0x18001a015  pop     r14
0x18001a017  pop     rdi
0x18001a018  pop     rbp
0x18001a019  retn
```
