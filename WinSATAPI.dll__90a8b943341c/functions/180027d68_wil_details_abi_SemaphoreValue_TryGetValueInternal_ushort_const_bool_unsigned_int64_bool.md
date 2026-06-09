# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180027d68`
- end: `0x180027f29`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `449`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180027cf8`

## callees

- `0x18000c900`
- `0x1800101e8`
- `0x180023414`
- `0x180025518`
- `0x1800271ec`
- `0x180027218`
- `0x180027d68`
- `0x18002fb50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027dea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027dea`
- `KERNEL32!OpenSemaphoreW` at `0x180027dd4`
- `KERNEL32!OpenSemaphoreW` at `0x180027e6c`
- `KERNEL32!OpenSemaphoreW` at `0x180027dd4`
- `KERNEL32!OpenSemaphoreW` at `0x180027e6c`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned int LastError; // ebx
  HANDLE v6; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  int ValueFromSemaphore; // eax
  unsigned int v10; // r8d
  int v11; // edi
  HANDLE v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  int v15; // eax
  unsigned int v16; // r8d
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v20; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v21[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  LastError = 0;
  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v21[0] = v6;
  if ( v6 )
  {
    v19 = 0;
    v18 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v19);
    v11 = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      StringCchCatW(Name, 0x104u, L"h");
      v12 = OpenSemaphoreW(0x1F0003u, 0, Name);
      v20 = v12;
      if ( !v12 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD9, v13, v14);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
        goto LABEL_12;
      }
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v18);
      v11 = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
        *a3 = v19 | (unsigned __int64)((__int64)v18 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDB, v16, (const char *)(unsigned int)v15, v18);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v20);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD3, v10, (const char *)(unsigned int)ValueFromSemaphore, v18);
    }
    LastError = v11;
  }
  else if ( GetLastError() != 2 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xCD, v7, v8);
  }
LABEL_12:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v21);
  return LastError;
}

```

## disassembly

```asm
0x180027d68  mov     [rsp-8+arg_0], rbx
0x180027d6d  mov     [rsp-8+arg_8], rsi
0x180027d72  push    rbp
0x180027d73  push    rdi
0x180027d74  push    r14
0x180027d76  lea     rbp, [rsp-160h]
0x180027d7e  sub     rsp, 260h
0x180027d85  mov     rax, cs:__security_cookie
0x180027d8c  xor     rax, rsp
0x180027d8f  mov     [rbp+170h+var_20], rax
0x180027d96  mov     rsi, r8
0x180027d99  xor     ebx, ebx
0x180027d9b  mov     [r8], rbx
0x180027d9e  mov     r14d, 104h
0x180027da4  mov     r8, rcx; unsigned __int16 *
0x180027da7  mov     edx, r14d; unsigned __int64
0x180027daa  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180027daf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180027db4  lea     r8, aP0; "_p0"
0x180027dbb  mov     edx, r14d; unsigned __int64
0x180027dbe  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180027dc3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180027dc8  lea     r8, [rsp+270h+Name]; lpName
0x180027dcd  xor     edx, edx; bInheritHandle
0x180027dcf  mov     ecx, 1F0003h; dwDesiredAccess
0x180027dd4  call    cs:__imp_OpenSemaphoreW
0x180027ddb  nop     dword ptr [rax+rax+00h]
0x180027de0  mov     [rsp+270h+var_240], rax
0x180027de5  test    rax, rax
0x180027de8  jnz     short loc_180027E16
0x180027dea  call    cs:__imp_GetLastError
0x180027df1  nop     dword ptr [rax+rax+00h]
0x180027df6  cmp     eax, 2
0x180027df9  jz      loc_180027EF5
0x180027dff  mov     rcx, [rbp+178h]; this
0x180027e06  lea     edx, [r14-37h]; void *
0x180027e0a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180027e0f  mov     ebx, eax
0x180027e11  jmp     loc_180027EF5
0x180027e16  lea     rdx, [rsp+270h+var_24C]; int *
0x180027e1b  mov     [rsp+270h+var_24C], ebx
0x180027e1f  mov     rcx, rax; hHandle
0x180027e22  mov     [rsp+270h+var_250], ebx; int
0x180027e26  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180027e2b  mov     edi, eax
0x180027e2d  test    eax, eax
0x180027e2f  jns     short loc_180027E4C
0x180027e31  mov     rcx, [rbp+178h]; this
0x180027e38  mov     r9d, eax; char *
0x180027e3b  mov     edx, 0D3h; void *
0x180027e40  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027e45  mov     ebx, edi
0x180027e47  jmp     loc_180027EF5
0x180027e4c  lea     r8, asc_18003AF50; "h"
0x180027e53  mov     rdx, r14; unsigned __int64
0x180027e56  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180027e5b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180027e60  lea     r8, [rsp+270h+Name]; lpName
0x180027e65  xor     edx, edx; bInheritHandle
0x180027e67  mov     ecx, 1F0003h; dwDesiredAccess
0x180027e6c  call    cs:__imp_OpenSemaphoreW
0x180027e73  nop     dword ptr [rax+rax+00h]
0x180027e78  mov     [rsp+270h+var_248], rax
0x180027e7d  test    rax, rax
0x180027e80  jnz     short loc_180027EA1
0x180027e82  mov     rcx, [rbp+178h]; this
0x180027e89  mov     edx, 0D9h; void *
0x180027e8e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180027e93  lea     rcx, [rsp+270h+var_248]
0x180027e98  mov     ebx, eax
0x180027e9a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027e9f  jmp     short loc_180027EF5
0x180027ea1  lea     rdx, [rsp+270h+var_250]; int *
0x180027ea6  mov     rcx, rax; hHandle
0x180027ea9  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180027eae  mov     edi, eax
0x180027eb0  test    eax, eax
0x180027eb2  jns     short loc_180027ED7
0x180027eb4  mov     rcx, [rbp+178h]; this
0x180027ebb  mov     r9d, eax; char *
0x180027ebe  mov     edx, 0DBh; void *
0x180027ec3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027ec8  lea     rcx, [rsp+270h+var_248]
0x180027ecd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027ed2  jmp     loc_180027E45
0x180027ed7  lea     rcx, [rsp+270h+var_248]
0x180027edc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027ee1  movsxd  rdx, [rsp+270h+var_250]
0x180027ee6  movsxd  rcx, [rsp+270h+var_24C]
0x180027eeb  shl     rdx, 1Fh
0x180027eef  or      rdx, rcx
0x180027ef2  mov     [rsi], rdx
0x180027ef5  lea     rcx, [rsp+270h+var_240]
0x180027efa  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180027eff  mov     eax, ebx
0x180027f01  mov     rcx, [rbp+170h+var_20]
0x180027f08  xor     rcx, rsp; StackCookie
0x180027f0b  call    __security_check_cookie
0x180027f10  lea     r11, [rsp+270h+var_10]
0x180027f18  mov     rbx, [r11+20h]
0x180027f1c  mov     rsi, [r11+28h]
0x180027f20  mov     rsp, r11
0x180027f23  pop     r14
0x180027f25  pop     rdi
0x180027f26  pop     rbp
0x180027f27  retn
```
