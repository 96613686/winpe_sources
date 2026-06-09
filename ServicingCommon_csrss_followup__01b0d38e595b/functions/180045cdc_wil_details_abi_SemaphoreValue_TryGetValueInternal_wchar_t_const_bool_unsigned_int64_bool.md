# wil::details_abi::SemaphoreValue::TryGetValueInternal(wchar_t const *,bool,unsigned __int64 *,bool *)

- ea: `0x180045cdc`
- end: `0x180045ead`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEB_W_NPEA_KPEA_N@Z`
- size: `465`
- prototype: `__int64 __fastcall(const wchar_t *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180045c58`

## callees

- `0x18001d694`
- `0x180020440`
- `0x18002d2b0`
- `0x180040b30`
- `0x1800412e0`
- `0x1800441a4`
- `0x180045028`
- `0x180045cdc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180045d5b`
- `KERNEL32!GetLastError` at `0x180045d5b`
- `KERNEL32!OpenSemaphoreW` at `0x180045d45`
- `KERNEL32!OpenSemaphoreW` at `0x180045df1`
- `KERNEL32!OpenSemaphoreW` at `0x180045d45`
- `KERNEL32!OpenSemaphoreW` at `0x180045df1`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const wchar_t *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  const char *v6; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  HANDLE v9; // rax
  const char *v10; // r9
  int v11; // eax
  int v13; // [rsp+20h] [rbp-E0h] BYREF
  int v14; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v15; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v16[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v16[0] = v5;
  if ( v5 )
  {
    v14 = 0;
    v13 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v14);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v13);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v9 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v15 = v9;
    if ( v9 )
    {
      v11 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v9, &v13);
      LastError = v11;
      if ( v11 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
        *a3 = v14 | (unsigned __int64)((__int64)v13 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v11,
        v13);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v10);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v15);
    goto LABEL_13;
  }
  if ( GetLastError() == 2 )
  {
LABEL_12:
    LastError = 0;
    goto LABEL_13;
  }
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v6);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v16);
  return LastError;
}

```

## disassembly

```asm
0x180045cdc  mov     [rsp-8+arg_8], rbx
0x180045ce1  push    rbp
0x180045ce2  push    rdi
0x180045ce3  push    r14
0x180045ce5  lea     rbp, [rsp-160h]
0x180045ced  sub     rsp, 260h
0x180045cf4  mov     rax, cs:__security_cookie
0x180045cfb  xor     rax, rsp
0x180045cfe  mov     [rbp+170h+var_20], rax
0x180045d05  mov     rdi, r8
0x180045d08  mov     qword ptr [r8], 0
0x180045d0f  mov     r8, rcx; wchar_t *
0x180045d12  mov     r14d, 104h
0x180045d18  mov     edx, r14d; unsigned __int64
0x180045d1b  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180045d20  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180045d25  lea     r8, aP0; "_p0"
0x180045d2c  mov     edx, r14d; unsigned __int64
0x180045d2f  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180045d34  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180045d39  lea     r8, [rsp+270h+Name]; lpName
0x180045d3e  xor     edx, edx; bInheritHandle
0x180045d40  mov     ecx, 1F0003h; dwDesiredAccess
0x180045d45  call    cs:__imp_OpenSemaphoreW
0x180045d4c  nop     dword ptr [rax+rax+00h]
0x180045d51  mov     [rsp+270h+var_240], rax
0x180045d56  test    rax, rax
0x180045d59  jnz     short loc_180045D8E
0x180045d5b  call    cs:__imp_GetLastError
0x180045d62  nop     dword ptr [rax+rax+00h]
0x180045d67  cmp     eax, 2
0x180045d6a  jz      loc_180045E7B
0x180045d70  mov     rcx, [rbp+178h]; this
0x180045d77  lea     r8, aWil; "wil"
0x180045d7e  lea     edx, [r14-34h]; void *
0x180045d82  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180045d87  mov     ebx, eax
0x180045d89  jmp     loc_180045E7D
0x180045d8e  lea     rdx, [rsp+270h+var_24C]; int *
0x180045d93  mov     [rsp+270h+var_24C], 0
0x180045d9b  mov     rcx, rax; hHandle
0x180045d9e  mov     [rsp+270h+var_250], 0; int
0x180045da6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180045dab  mov     ebx, eax
0x180045dad  test    eax, eax
0x180045daf  jns     short loc_180045DD1
0x180045db1  mov     rcx, [rbp+178h]; this
0x180045db8  lea     r8, aWil; "wil"
0x180045dbf  mov     r9d, eax; char *
0x180045dc2  mov     edx, 0D6h; void *
0x180045dc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045dcc  jmp     loc_180045E7D
0x180045dd1  lea     r8, asc_1800AF4C0; "h"
0x180045dd8  mov     rdx, r14; unsigned __int64
0x180045ddb  lea     rcx, [rsp+270h+Name]; wchar_t *
0x180045de0  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180045de5  lea     r8, [rsp+270h+Name]; lpName
0x180045dea  xor     edx, edx; bInheritHandle
0x180045dec  mov     ecx, 1F0003h; dwDesiredAccess
0x180045df1  call    cs:__imp_OpenSemaphoreW
0x180045df8  nop     dword ptr [rax+rax+00h]
0x180045dfd  mov     [rsp+270h+var_248], rax
0x180045e02  test    rax, rax
0x180045e05  jnz     short loc_180045E2D
0x180045e07  mov     rcx, [rbp+178h]; this
0x180045e0e  lea     r8, aWil; "wil"
0x180045e15  mov     edx, 0DCh; void *
0x180045e1a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180045e1f  mov     ebx, eax
0x180045e21  lea     rcx, [rsp+270h+var_248]
0x180045e26  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180045e2b  jmp     short loc_180045E7D
0x180045e2d  lea     rdx, [rsp+270h+var_250]; int *
0x180045e32  mov     rcx, rax; hHandle
0x180045e35  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180045e3a  mov     ebx, eax
0x180045e3c  test    eax, eax
0x180045e3e  jns     short loc_180045E5D
0x180045e40  mov     rcx, [rbp+178h]; this
0x180045e47  lea     r8, aWil; "wil"
0x180045e4e  mov     r9d, eax; char *
0x180045e51  mov     edx, 0DEh; void *
0x180045e56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180045e5b  jmp     short loc_180045E21
0x180045e5d  lea     rcx, [rsp+270h+var_248]
0x180045e62  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180045e67  movsxd  rcx, [rsp+270h+var_250]
0x180045e6c  movsxd  rax, [rsp+270h+var_24C]
0x180045e71  shl     rcx, 1Fh
0x180045e75  or      rcx, rax
0x180045e78  mov     [rdi], rcx
0x180045e7b  xor     ebx, ebx
0x180045e7d  lea     rcx, [rsp+270h+var_240]
0x180045e82  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180045e87  mov     eax, ebx
0x180045e89  mov     rcx, [rbp+170h+var_20]
0x180045e90  xor     rcx, rsp; StackCookie
0x180045e93  call    __security_check_cookie
0x180045e98  mov     rbx, [rsp+270h+arg_8]
0x180045ea0  add     rsp, 260h
0x180045ea7  pop     r14
0x180045ea9  pop     rdi
0x180045eaa  pop     rbp
0x180045eab  retn
```
