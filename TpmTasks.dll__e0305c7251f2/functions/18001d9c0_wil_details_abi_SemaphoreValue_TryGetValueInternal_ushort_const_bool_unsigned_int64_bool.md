# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001d9c0`
- end: `0x18001db7e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001d93c`

## callees

- `0x1800078b0`
- `0x18000e570`
- `0x180014be0`
- `0x18001a40c`
- `0x18001a42c`
- `0x18001bd50`
- `0x18001bddc`
- `0x18001d9c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001da29`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001dac9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001da29`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001dac9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da39`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da39`

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
0x18001d9c0  mov     [rsp-8+arg_8], rbx
0x18001d9c5  push    rbp
0x18001d9c6  push    rdi
0x18001d9c7  push    r14
0x18001d9c9  lea     rbp, [rsp-160h]
0x18001d9d1  sub     rsp, 260h
0x18001d9d8  mov     rax, cs:__security_cookie
0x18001d9df  xor     rax, rsp
0x18001d9e2  mov     [rbp+170h+var_20], rax
0x18001d9e9  mov     rdi, r8
0x18001d9ec  mov     qword ptr [r8], 0
0x18001d9f3  mov     r8, rcx; unsigned __int16 *
0x18001d9f6  mov     r14d, 104h
0x18001d9fc  mov     edx, r14d; unsigned __int64
0x18001d9ff  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001da04  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001da09  lea     r8, aP0; "_p0"
0x18001da10  mov     edx, r14d; unsigned __int64
0x18001da13  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001da18  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001da1d  lea     r8, [rsp+270h+Name]; lpName
0x18001da22  xor     edx, edx; bInheritHandle
0x18001da24  mov     ecx, 1F0003h; dwDesiredAccess
0x18001da29  call    cs:__imp_OpenSemaphoreW
0x18001da2f  mov     [rsp+270h+var_240], rax
0x18001da34  test    rax, rax
0x18001da37  jnz     short loc_18001DA66
0x18001da39  call    cs:__imp_GetLastError
0x18001da3f  cmp     eax, 2
0x18001da42  jz      loc_18001DB4D
0x18001da48  mov     rcx, [rbp+178h]; this
0x18001da4f  lea     r8, aWil; "wil"
0x18001da56  lea     edx, [r14-34h]; void *
0x18001da5a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001da5f  mov     ebx, eax
0x18001da61  jmp     loc_18001DB4F
0x18001da66  lea     rdx, [rsp+270h+var_24C]; int *
0x18001da6b  mov     [rsp+270h+var_24C], 0
0x18001da73  mov     rcx, rax; hHandle
0x18001da76  mov     [rsp+270h+var_250], 0; int
0x18001da7e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001da83  mov     ebx, eax
0x18001da85  test    eax, eax
0x18001da87  jns     short loc_18001DAA9
0x18001da89  mov     rcx, [rbp+178h]; this
0x18001da90  lea     r8, aWil; "wil"
0x18001da97  mov     r9d, eax; char *
0x18001da9a  mov     edx, 0D6h; void *
0x18001da9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001daa4  jmp     loc_18001DB4F
0x18001daa9  lea     r8, asc_180067330; "h"
0x18001dab0  mov     rdx, r14; unsigned __int64
0x18001dab3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001dab8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001dabd  lea     r8, [rsp+270h+Name]; lpName
0x18001dac2  xor     edx, edx; bInheritHandle
0x18001dac4  mov     ecx, 1F0003h; dwDesiredAccess
0x18001dac9  call    cs:__imp_OpenSemaphoreW
0x18001dacf  mov     [rsp+270h+var_248], rax
0x18001dad4  test    rax, rax
0x18001dad7  jnz     short loc_18001DAFF
0x18001dad9  mov     rcx, [rbp+178h]; this
0x18001dae0  lea     r8, aWil; "wil"
0x18001dae7  mov     edx, 0DCh; void *
0x18001daec  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001daf1  mov     ebx, eax
0x18001daf3  lea     rcx, [rsp+270h+var_248]
0x18001daf8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001dafd  jmp     short loc_18001DB4F
0x18001daff  lea     rdx, [rsp+270h+var_250]; int *
0x18001db04  mov     rcx, rax; hHandle
0x18001db07  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001db0c  mov     ebx, eax
0x18001db0e  test    eax, eax
0x18001db10  jns     short loc_18001DB2F
0x18001db12  mov     rcx, [rbp+178h]; this
0x18001db19  lea     r8, aWil; "wil"
0x18001db20  mov     r9d, eax; char *
0x18001db23  mov     edx, 0DEh; void *
0x18001db28  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001db2d  jmp     short loc_18001DAF3
0x18001db2f  lea     rcx, [rsp+270h+var_248]
0x18001db34  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001db39  movsxd  rcx, [rsp+270h+var_250]
0x18001db3e  movsxd  rax, [rsp+270h+var_24C]
0x18001db43  shl     rcx, 1Fh
0x18001db47  or      rcx, rax
0x18001db4a  mov     [rdi], rcx
0x18001db4d  xor     ebx, ebx
0x18001db4f  lea     rcx, [rsp+270h+var_240]
0x18001db54  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001db59  mov     eax, ebx
0x18001db5b  mov     rcx, [rbp+170h+var_20]
0x18001db62  xor     rcx, rsp; StackCookie
0x18001db65  call    __security_check_cookie
0x18001db6a  mov     rbx, [rsp+270h+arg_8]
0x18001db72  add     rsp, 260h
0x18001db79  pop     r14
0x18001db7b  pop     rdi
0x18001db7c  pop     rbp
0x18001db7d  retn
```
