# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000ae90`
- end: `0x18000b05b`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `459`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000ae0c`

## callees

- `0x180004eb0`
- `0x1800089e8`
- `0x180009894`
- `0x18000a5a4`
- `0x18000a5c4`
- `0x18000ab00`
- `0x18000abec`
- `0x18000ae90`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000aef4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000af9e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000aef4`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000af9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000af0a`

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
0x18000ae90  mov     [rsp-8+arg_8], rbx
0x18000ae95  mov     [rsp-8+arg_18], rdi
0x18000ae9a  push    rbp
0x18000ae9b  lea     rbp, [rsp-160h]
0x18000aea3  sub     rsp, 260h
0x18000aeaa  mov     rax, cs:__security_cookie
0x18000aeb1  xor     rax, rsp
0x18000aeb4  mov     [rbp+160h+var_10], rax
0x18000aebb  mov     rdi, r8
0x18000aebe  mov     qword ptr [r8], 0
0x18000aec5  mov     r8, rcx; unsigned __int16 *
0x18000aec8  mov     edx, 104h; unsigned __int64
0x18000aecd  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000aed2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000aed7  lea     r8, aP0; "_p0"
0x18000aede  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000aee3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000aee8  lea     r8, [rsp+260h+Name]; lpName
0x18000aeed  xor     edx, edx; bInheritHandle
0x18000aeef  mov     ecx, 1F0003h; dwDesiredAccess
0x18000aef4  call    cs:__imp_OpenSemaphoreW
0x18000aefb  nop     dword ptr [rax+rax+00h]
0x18000af00  mov     [rsp+260h+var_230], rax
0x18000af05  test    rax, rax
0x18000af08  jnz     short loc_18000AF3E
0x18000af0a  call    cs:__imp_GetLastError
0x18000af11  nop     dword ptr [rax+rax+00h]
0x18000af16  cmp     eax, 2
0x18000af19  jz      loc_18000B028
0x18000af1f  mov     rcx, [rbp+168h]; this
0x18000af26  lea     r8, aWil; "wil"
0x18000af2d  mov     edx, 0D0h; void *
0x18000af32  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000af37  mov     ebx, eax
0x18000af39  jmp     loc_18000B02A
0x18000af3e  lea     rdx, [rsp+260h+var_23C]; int *
0x18000af43  mov     [rsp+260h+var_23C], 0
0x18000af4b  mov     rcx, rax; hHandle
0x18000af4e  mov     [rsp+260h+var_240], 0; int
0x18000af56  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000af5b  mov     ebx, eax
0x18000af5d  test    eax, eax
0x18000af5f  jns     short loc_18000AF81
0x18000af61  mov     rcx, [rbp+168h]; this
0x18000af68  lea     r8, aWil; "wil"
0x18000af6f  mov     r9d, eax; char *
0x18000af72  mov     edx, 0D6h; void *
0x18000af77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000af7c  jmp     loc_18000B02A
0x18000af81  lea     r8, asc_1800D5108; "h"
0x18000af88  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18000af8d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000af92  lea     r8, [rsp+260h+Name]; lpName
0x18000af97  xor     edx, edx; bInheritHandle
0x18000af99  mov     ecx, 1F0003h; dwDesiredAccess
0x18000af9e  call    cs:__imp_OpenSemaphoreW
0x18000afa5  nop     dword ptr [rax+rax+00h]
0x18000afaa  mov     [rsp+260h+var_238], rax
0x18000afaf  test    rax, rax
0x18000afb2  jnz     short loc_18000AFDA
0x18000afb4  mov     rcx, [rbp+168h]; this
0x18000afbb  lea     r8, aWil; "wil"
0x18000afc2  mov     edx, 0DCh; void *
0x18000afc7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000afcc  mov     ebx, eax
0x18000afce  lea     rcx, [rsp+260h+var_238]
0x18000afd3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000afd8  jmp     short loc_18000B02A
0x18000afda  lea     rdx, [rsp+260h+var_240]; int *
0x18000afdf  mov     rcx, rax; hHandle
0x18000afe2  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000afe7  mov     ebx, eax
0x18000afe9  test    eax, eax
0x18000afeb  jns     short loc_18000B00A
0x18000afed  mov     rcx, [rbp+168h]; this
0x18000aff4  lea     r8, aWil; "wil"
0x18000affb  mov     r9d, eax; char *
0x18000affe  mov     edx, 0DEh; void *
0x18000b003  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b008  jmp     short loc_18000AFCE
0x18000b00a  lea     rcx, [rsp+260h+var_238]
0x18000b00f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b014  movsxd  rcx, [rsp+260h+var_240]
0x18000b019  movsxd  rax, [rsp+260h+var_23C]
0x18000b01e  shl     rcx, 1Fh
0x18000b022  or      rcx, rax
0x18000b025  mov     [rdi], rcx
0x18000b028  xor     ebx, ebx
0x18000b02a  lea     rcx, [rsp+260h+var_230]
0x18000b02f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b034  mov     eax, ebx
0x18000b036  mov     rcx, [rbp+160h+var_10]
0x18000b03d  xor     rcx, rsp; StackCookie
0x18000b040  call    __security_check_cookie
0x18000b045  lea     r11, [rsp+260h+var_s0]
0x18000b04d  mov     rbx, [r11+18h]
0x18000b051  mov     rdi, [r11+28h]
0x18000b055  mov     rsp, r11
0x18000b058  pop     rbp
0x18000b059  retn
```
