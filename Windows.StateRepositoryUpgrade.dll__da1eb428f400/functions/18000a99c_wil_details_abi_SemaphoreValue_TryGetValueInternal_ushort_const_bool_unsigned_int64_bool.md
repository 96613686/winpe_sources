# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000a99c`
- end: `0x18000ab5a`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000a918`

## callees

- `0x180003980`
- `0x180008d0c`
- `0x180009970`
- `0x18000a3a0`
- `0x18000a3c0`
- `0x18000a688`
- `0x18000a77c`
- `0x18000a99c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000aa05`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000aaa5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000aa05`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000aaa5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aa15`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
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
0x18000a99c  mov     [rsp-8+arg_8], rbx
0x18000a9a1  push    rbp
0x18000a9a2  push    rdi
0x18000a9a3  push    r14
0x18000a9a5  lea     rbp, [rsp-160h]
0x18000a9ad  sub     rsp, 260h
0x18000a9b4  mov     rax, cs:__security_cookie
0x18000a9bb  xor     rax, rsp
0x18000a9be  mov     [rbp+170h+var_20], rax
0x18000a9c5  mov     rdi, r8
0x18000a9c8  mov     qword ptr [r8], 0
0x18000a9cf  mov     r8, rcx; unsigned __int16 *
0x18000a9d2  mov     r14d, 104h
0x18000a9d8  mov     edx, r14d; unsigned __int64
0x18000a9db  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a9e0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000a9e5  lea     r8, aP0; "_p0"
0x18000a9ec  mov     edx, r14d; unsigned __int64
0x18000a9ef  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a9f4  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a9f9  lea     r8, [rsp+270h+Name]; lpName
0x18000a9fe  xor     edx, edx; bInheritHandle
0x18000aa00  mov     ecx, 1F0003h; dwDesiredAccess
0x18000aa05  call    cs:__imp_OpenSemaphoreW
0x18000aa0b  mov     [rsp+270h+var_240], rax
0x18000aa10  test    rax, rax
0x18000aa13  jnz     short loc_18000AA42
0x18000aa15  call    cs:__imp_GetLastError
0x18000aa1b  cmp     eax, 2
0x18000aa1e  jz      loc_18000AB29
0x18000aa24  mov     rcx, [rbp+178h]; this
0x18000aa2b  lea     r8, aWil; "wil"
0x18000aa32  lea     edx, [r14-34h]; void *
0x18000aa36  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000aa3b  mov     ebx, eax
0x18000aa3d  jmp     loc_18000AB2B
0x18000aa42  lea     rdx, [rsp+270h+var_24C]; int *
0x18000aa47  mov     [rsp+270h+var_24C], 0
0x18000aa4f  mov     rcx, rax; hHandle
0x18000aa52  mov     [rsp+270h+var_250], 0; int
0x18000aa5a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000aa5f  mov     ebx, eax
0x18000aa61  test    eax, eax
0x18000aa63  jns     short loc_18000AA85
0x18000aa65  mov     rcx, [rbp+178h]; this
0x18000aa6c  lea     r8, aWil; "wil"
0x18000aa73  mov     r9d, eax; char *
0x18000aa76  mov     edx, 0D6h; void *
0x18000aa7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aa80  jmp     loc_18000AB2B
0x18000aa85  lea     r8, asc_180035110; "h"
0x18000aa8c  mov     rdx, r14; unsigned __int64
0x18000aa8f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000aa94  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000aa99  lea     r8, [rsp+270h+Name]; lpName
0x18000aa9e  xor     edx, edx; bInheritHandle
0x18000aaa0  mov     ecx, 1F0003h; dwDesiredAccess
0x18000aaa5  call    cs:__imp_OpenSemaphoreW
0x18000aaab  mov     [rsp+270h+var_248], rax
0x18000aab0  test    rax, rax
0x18000aab3  jnz     short loc_18000AADB
0x18000aab5  mov     rcx, [rbp+178h]; this
0x18000aabc  lea     r8, aWil; "wil"
0x18000aac3  mov     edx, 0DCh; void *
0x18000aac8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000aacd  mov     ebx, eax
0x18000aacf  lea     rcx, [rsp+270h+var_248]
0x18000aad4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000aad9  jmp     short loc_18000AB2B
0x18000aadb  lea     rdx, [rsp+270h+var_250]; int *
0x18000aae0  mov     rcx, rax; hHandle
0x18000aae3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000aae8  mov     ebx, eax
0x18000aaea  test    eax, eax
0x18000aaec  jns     short loc_18000AB0B
0x18000aaee  mov     rcx, [rbp+178h]; this
0x18000aaf5  lea     r8, aWil; "wil"
0x18000aafc  mov     r9d, eax; char *
0x18000aaff  mov     edx, 0DEh; void *
0x18000ab04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ab09  jmp     short loc_18000AACF
0x18000ab0b  lea     rcx, [rsp+270h+var_248]
0x18000ab10  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ab15  movsxd  rcx, [rsp+270h+var_250]
0x18000ab1a  movsxd  rax, [rsp+270h+var_24C]
0x18000ab1f  shl     rcx, 1Fh
0x18000ab23  or      rcx, rax
0x18000ab26  mov     [rdi], rcx
0x18000ab29  xor     ebx, ebx
0x18000ab2b  lea     rcx, [rsp+270h+var_240]
0x18000ab30  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000ab35  mov     eax, ebx
0x18000ab37  mov     rcx, [rbp+170h+var_20]
0x18000ab3e  xor     rcx, rsp; StackCookie
0x18000ab41  call    __security_check_cookie
0x18000ab46  mov     rbx, [rsp+270h+arg_8]
0x18000ab4e  add     rsp, 260h
0x18000ab55  pop     r14
0x18000ab57  pop     rdi
0x18000ab58  pop     rbp
0x18000ab59  retn
```
