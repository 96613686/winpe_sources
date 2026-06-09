# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180005b78`
- end: `0x180005d27`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `431`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180002e64`

## callees

- `0x180002d24`
- `0x180003f38`
- `0x180005414`
- `0x180005434`
- `0x180005928`
- `0x1800059a8`
- `0x180005b78`
- `0x18001f420`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180005bf2`
- `KERNEL32!GetLastError` at `0x180005bf2`
- `KERNEL32!OpenSemaphoreW` at `0x180005bdc`
- `KERNEL32!OpenSemaphoreW` at `0x180005c78`
- `KERNEL32!OpenSemaphoreW` at `0x180005bdc`
- `KERNEL32!OpenSemaphoreW` at `0x180005c78`

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
  unsigned int v12; // r8d
  HANDLE v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  unsigned int v17; // r8d
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v21; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v22[0] = v6;
  if ( v6 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v20);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore, v19);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v21 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v19);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16, v19);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
  return LastError;
}

```

## disassembly

```asm
0x180005b78  mov     [rsp-8+arg_8], rbx
0x180005b7d  mov     [rsp-8+arg_18], rdi
0x180005b82  push    rbp
0x180005b83  lea     rbp, [rsp-160h]
0x180005b8b  sub     rsp, 260h
0x180005b92  mov     rax, cs:__security_cookie
0x180005b99  xor     rax, rsp
0x180005b9c  mov     [rbp+160h+var_10], rax
0x180005ba3  mov     rdi, r8
0x180005ba6  mov     qword ptr [r8], 0
0x180005bad  mov     r8, rcx; unsigned __int16 *
0x180005bb0  mov     edx, 104h; unsigned __int64
0x180005bb5  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180005bba  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180005bbf  lea     r8, aP0; "_p0"
0x180005bc6  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180005bcb  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005bd0  lea     r8, [rsp+260h+Name]; lpName
0x180005bd5  xor     edx, edx; bInheritHandle
0x180005bd7  mov     ecx, 1F0003h; dwDesiredAccess
0x180005bdc  call    cs:__imp_OpenSemaphoreW
0x180005be3  nop     dword ptr [rax+rax+00h]
0x180005be8  mov     [rsp+260h+var_230], rax
0x180005bed  test    rax, rax
0x180005bf0  jnz     short loc_180005C1F
0x180005bf2  call    cs:__imp_GetLastError
0x180005bf9  nop     dword ptr [rax+rax+00h]
0x180005bfe  cmp     eax, 2
0x180005c01  jz      loc_180005CF4
0x180005c07  mov     rcx, [rbp+168h]; this
0x180005c0e  mov     edx, 0D0h; void *
0x180005c13  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005c18  mov     ebx, eax
0x180005c1a  jmp     loc_180005CF6
0x180005c1f  lea     rdx, [rsp+260h+var_23C]; int *
0x180005c24  mov     [rsp+260h+var_23C], 0
0x180005c2c  mov     rcx, rax; hHandle
0x180005c2f  mov     [rsp+260h+var_240], 0; int
0x180005c37  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005c3c  mov     ebx, eax
0x180005c3e  test    eax, eax
0x180005c40  jns     short loc_180005C5B
0x180005c42  mov     rcx, [rbp+168h]; this
0x180005c49  mov     r9d, eax; char *
0x180005c4c  mov     edx, 0D6h; void *
0x180005c51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005c56  jmp     loc_180005CF6
0x180005c5b  lea     r8, asc_180023218; "h"
0x180005c62  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180005c67  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180005c6c  lea     r8, [rsp+260h+Name]; lpName
0x180005c71  xor     edx, edx; bInheritHandle
0x180005c73  mov     ecx, 1F0003h; dwDesiredAccess
0x180005c78  call    cs:__imp_OpenSemaphoreW
0x180005c7f  nop     dword ptr [rax+rax+00h]
0x180005c84  mov     [rsp+260h+var_238], rax
0x180005c89  test    rax, rax
0x180005c8c  jnz     short loc_180005CAD
0x180005c8e  mov     rcx, [rbp+168h]; this
0x180005c95  mov     edx, 0DCh; void *
0x180005c9a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005c9f  mov     ebx, eax
0x180005ca1  lea     rcx, [rsp+260h+var_238]
0x180005ca6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005cab  jmp     short loc_180005CF6
0x180005cad  lea     rdx, [rsp+260h+var_240]; int *
0x180005cb2  mov     rcx, rax; hHandle
0x180005cb5  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005cba  mov     ebx, eax
0x180005cbc  test    eax, eax
0x180005cbe  jns     short loc_180005CD6
0x180005cc0  mov     rcx, [rbp+168h]; this
0x180005cc7  mov     r9d, eax; char *
0x180005cca  mov     edx, 0DEh; void *
0x180005ccf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005cd4  jmp     short loc_180005CA1
0x180005cd6  lea     rcx, [rsp+260h+var_238]
0x180005cdb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005ce0  movsxd  rcx, [rsp+260h+var_240]
0x180005ce5  movsxd  rax, [rsp+260h+var_23C]
0x180005cea  shl     rcx, 1Fh
0x180005cee  or      rcx, rax
0x180005cf1  mov     [rdi], rcx
0x180005cf4  xor     ebx, ebx
0x180005cf6  lea     rcx, [rsp+260h+var_230]
0x180005cfb  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005d00  mov     eax, ebx
0x180005d02  mov     rcx, [rbp+160h+var_10]
0x180005d09  xor     rcx, rsp; StackCookie
0x180005d0c  call    __security_check_cookie
0x180005d11  lea     r11, [rsp+260h+var_s0]
0x180005d19  mov     rbx, [r11+18h]
0x180005d1d  mov     rdi, [r11+28h]
0x180005d21  mov     rsp, r11
0x180005d24  pop     rbp
0x180005d25  retn
```
