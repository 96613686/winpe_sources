# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009e3c`
- end: `0x180009fe6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180009db8`

## callees

- `0x180004170`
- `0x180007008`
- `0x1800080e8`
- `0x1800090f4`
- `0x180009114`
- `0x1800099f8`
- `0x180009a74`
- `0x180009e3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009ea0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009f37`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009ea0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009f37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009eb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009eb0`

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
0x180009e3c  mov     [rsp-8+arg_8], rbx
0x180009e41  mov     [rsp-8+arg_18], rdi
0x180009e46  push    rbp
0x180009e47  lea     rbp, [rsp-160h]
0x180009e4f  sub     rsp, 260h
0x180009e56  mov     rax, cs:__security_cookie
0x180009e5d  xor     rax, rsp
0x180009e60  mov     [rbp+160h+var_10], rax
0x180009e67  mov     rdi, r8
0x180009e6a  mov     qword ptr [r8], 0
0x180009e71  mov     r8, rcx; unsigned __int16 *
0x180009e74  mov     edx, 104h; unsigned __int64
0x180009e79  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180009e7e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009e83  lea     r8, aP0; "_p0"
0x180009e8a  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180009e8f  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009e94  lea     r8, [rsp+260h+Name]; lpName
0x180009e99  xor     edx, edx; bInheritHandle
0x180009e9b  mov     ecx, 1F0003h; dwDesiredAccess
0x180009ea0  call    cs:__imp_OpenSemaphoreW
0x180009ea6  mov     [rsp+260h+var_230], rax
0x180009eab  test    rax, rax
0x180009eae  jnz     short loc_180009ED7
0x180009eb0  call    cs:__imp_GetLastError
0x180009eb6  cmp     eax, 2
0x180009eb9  jz      loc_180009FB4
0x180009ebf  mov     rcx, [rbp+168h]; this
0x180009ec6  mov     edx, 0D0h; void *
0x180009ecb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009ed0  mov     ebx, eax
0x180009ed2  jmp     loc_180009FB6
0x180009ed7  lea     rdx, [rsp+260h+var_23C]; int *
0x180009edc  mov     [rsp+260h+var_23C], 0
0x180009ee4  mov     rcx, rax; hHandle
0x180009ee7  mov     [rsp+260h+var_240], 0; int
0x180009eef  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009ef4  mov     ebx, eax
0x180009ef6  test    eax, eax
0x180009ef8  jns     short loc_180009F1A
0x180009efa  mov     rcx, [rbp+168h]; this
0x180009f01  lea     r8, aWil; "wil"
0x180009f08  mov     r9d, eax; char *
0x180009f0b  mov     edx, 0D6h; void *
0x180009f10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009f15  jmp     loc_180009FB6
0x180009f1a  lea     r8, asc_18004AD10; "h"
0x180009f21  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180009f26  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009f2b  lea     r8, [rsp+260h+Name]; lpName
0x180009f30  xor     edx, edx; bInheritHandle
0x180009f32  mov     ecx, 1F0003h; dwDesiredAccess
0x180009f37  call    cs:__imp_OpenSemaphoreW
0x180009f3d  mov     [rsp+260h+var_238], rax
0x180009f42  test    rax, rax
0x180009f45  jnz     short loc_180009F66
0x180009f47  mov     rcx, [rbp+168h]; this
0x180009f4e  mov     edx, 0DCh; void *
0x180009f53  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009f58  mov     ebx, eax
0x180009f5a  lea     rcx, [rsp+260h+var_238]
0x180009f5f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009f64  jmp     short loc_180009FB6
0x180009f66  lea     rdx, [rsp+260h+var_240]; int *
0x180009f6b  mov     rcx, rax; hHandle
0x180009f6e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009f73  mov     ebx, eax
0x180009f75  test    eax, eax
0x180009f77  jns     short loc_180009F96
0x180009f79  mov     rcx, [rbp+168h]; this
0x180009f80  lea     r8, aWil; "wil"
0x180009f87  mov     r9d, eax; char *
0x180009f8a  mov     edx, 0DEh; void *
0x180009f8f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009f94  jmp     short loc_180009F5A
0x180009f96  lea     rcx, [rsp+260h+var_238]
0x180009f9b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009fa0  movsxd  rcx, [rsp+260h+var_240]
0x180009fa5  movsxd  rax, [rsp+260h+var_23C]
0x180009faa  shl     rcx, 1Fh
0x180009fae  or      rcx, rax
0x180009fb1  mov     [rdi], rcx
0x180009fb4  xor     ebx, ebx
0x180009fb6  lea     rcx, [rsp+260h+var_230]
0x180009fbb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009fc0  mov     eax, ebx
0x180009fc2  mov     rcx, [rbp+160h+var_10]
0x180009fc9  xor     rcx, rsp; StackCookie
0x180009fcc  call    __security_check_cookie
0x180009fd1  lea     r11, [rsp+260h+var_s0]
0x180009fd9  mov     rbx, [r11+18h]
0x180009fdd  mov     rdi, [r11+28h]
0x180009fe1  mov     rsp, r11
0x180009fe4  pop     rbp
0x180009fe5  retn
```
