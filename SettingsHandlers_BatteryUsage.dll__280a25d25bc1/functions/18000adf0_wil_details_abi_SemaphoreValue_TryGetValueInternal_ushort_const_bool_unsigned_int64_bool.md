# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000adf0`
- end: `0x18000afa8`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000ad6c`

## callees

- `0x1800028d0`
- `0x1800060f4`
- `0x180007de0`
- `0x18000a11c`
- `0x18000a13c`
- `0x18000a83c`
- `0x18000a8b8`
- `0x18000adf0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ae64`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ae54`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000aef2`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ae54`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000aef2`

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
0x18000adf0  mov     [rsp-8+arg_8], rbx
0x18000adf5  mov     [rsp-8+arg_18], rdi
0x18000adfa  push    rbp
0x18000adfb  lea     rbp, [rsp-160h]
0x18000ae03  sub     rsp, 260h
0x18000ae0a  mov     rax, cs:__security_cookie
0x18000ae11  xor     rax, rsp
0x18000ae14  mov     [rbp+160h+var_10], rax
0x18000ae1b  mov     rdi, r8
0x18000ae1e  mov     qword ptr [r8], 0
0x18000ae25  mov     r8, rcx; unsigned __int16 *
0x18000ae28  mov     edx, 104h; unsigned __int64
0x18000ae2d  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000ae32  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ae37  lea     r8, aP0; "_p0"
0x18000ae3e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000ae43  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ae48  lea     r8, [rsp+260h+Name]; lpName
0x18000ae4d  xor     edx, edx; bInheritHandle
0x18000ae4f  mov     ecx, 1F0003h; dwDesiredAccess
0x18000ae54  call    cs:__imp_OpenSemaphoreW
0x18000ae5a  mov     [rsp+260h+var_230], rax
0x18000ae5f  test    rax, rax
0x18000ae62  jnz     short loc_18000AE92
0x18000ae64  call    cs:__imp_GetLastError
0x18000ae6a  cmp     eax, 2
0x18000ae6d  jz      loc_18000AF76
0x18000ae73  mov     rcx, [rbp+168h]; this
0x18000ae7a  lea     r8, aWil; "wil"
0x18000ae81  mov     edx, 0D0h; void *
0x18000ae86  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ae8b  mov     ebx, eax
0x18000ae8d  jmp     loc_18000AF78
0x18000ae92  lea     rdx, [rsp+260h+var_23C]; int *
0x18000ae97  mov     [rsp+260h+var_23C], 0
0x18000ae9f  mov     rcx, rax; hHandle
0x18000aea2  mov     [rsp+260h+var_240], 0; int
0x18000aeaa  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000aeaf  mov     ebx, eax
0x18000aeb1  test    eax, eax
0x18000aeb3  jns     short loc_18000AED5
0x18000aeb5  mov     rcx, [rbp+168h]; this
0x18000aebc  lea     r8, aWil; "wil"
0x18000aec3  mov     r9d, eax; char *
0x18000aec6  mov     edx, 0D6h; void *
0x18000aecb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aed0  jmp     loc_18000AF78
0x18000aed5  lea     r8, asc_180063B00; "h"
0x18000aedc  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000aee1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000aee6  lea     r8, [rsp+260h+Name]; lpName
0x18000aeeb  xor     edx, edx; bInheritHandle
0x18000aeed  mov     ecx, 1F0003h; dwDesiredAccess
0x18000aef2  call    cs:__imp_OpenSemaphoreW
0x18000aef8  mov     [rsp+260h+var_238], rax
0x18000aefd  test    rax, rax
0x18000af00  jnz     short loc_18000AF28
0x18000af02  mov     rcx, [rbp+168h]; this
0x18000af09  lea     r8, aWil; "wil"
0x18000af10  mov     edx, 0DCh; void *
0x18000af15  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000af1a  mov     ebx, eax
0x18000af1c  lea     rcx, [rsp+260h+var_238]
0x18000af21  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000af26  jmp     short loc_18000AF78
0x18000af28  lea     rdx, [rsp+260h+var_240]; int *
0x18000af2d  mov     rcx, rax; hHandle
0x18000af30  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000af35  mov     ebx, eax
0x18000af37  test    eax, eax
0x18000af39  jns     short loc_18000AF58
0x18000af3b  mov     rcx, [rbp+168h]; this
0x18000af42  lea     r8, aWil; "wil"
0x18000af49  mov     r9d, eax; char *
0x18000af4c  mov     edx, 0DEh; void *
0x18000af51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000af56  jmp     short loc_18000AF1C
0x18000af58  lea     rcx, [rsp+260h+var_238]
0x18000af5d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000af62  movsxd  rcx, [rsp+260h+var_240]
0x18000af67  movsxd  rax, [rsp+260h+var_23C]
0x18000af6c  shl     rcx, 1Fh
0x18000af70  or      rcx, rax
0x18000af73  mov     [rdi], rcx
0x18000af76  xor     ebx, ebx
0x18000af78  lea     rcx, [rsp+260h+var_230]
0x18000af7d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000af82  mov     eax, ebx
0x18000af84  mov     rcx, [rbp+160h+var_10]
0x18000af8b  xor     rcx, rsp; StackCookie
0x18000af8e  call    __security_check_cookie
0x18000af93  lea     r11, [rsp+260h+var_s0]
0x18000af9b  mov     rbx, [r11+18h]
0x18000af9f  mov     rdi, [r11+28h]
0x18000afa3  mov     rsp, r11
0x18000afa6  pop     rbp
0x18000afa7  retn
```
