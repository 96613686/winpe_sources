# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000f570`
- end: `0x18000f72e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `446`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000f4ec`

## callees

- `0x180006e50`
- `0x18000adf8`
- `0x18000c648`
- `0x18000e6ac`
- `0x18000e6cc`
- `0x18000efac`
- `0x18000f038`
- `0x18000f570`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f5d9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f679`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f5d9`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f5e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f5e9`

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
0x18000f570  mov     [rsp-8+arg_8], rbx
0x18000f575  push    rbp
0x18000f576  push    rdi
0x18000f577  push    r14
0x18000f579  lea     rbp, [rsp-160h]
0x18000f581  sub     rsp, 260h
0x18000f588  mov     rax, cs:__security_cookie
0x18000f58f  xor     rax, rsp
0x18000f592  mov     [rbp+170h+var_20], rax
0x18000f599  mov     rdi, r8
0x18000f59c  mov     qword ptr [r8], 0
0x18000f5a3  mov     r8, rcx; unsigned __int16 *
0x18000f5a6  mov     r14d, 104h
0x18000f5ac  mov     edx, r14d; unsigned __int64
0x18000f5af  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000f5b4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f5b9  lea     r8, aP0; "_p0"
0x18000f5c0  mov     edx, r14d; unsigned __int64
0x18000f5c3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000f5c8  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f5cd  lea     r8, [rsp+270h+Name]; lpName
0x18000f5d2  xor     edx, edx; bInheritHandle
0x18000f5d4  mov     ecx, 1F0003h; dwDesiredAccess
0x18000f5d9  call    cs:__imp_OpenSemaphoreW
0x18000f5df  mov     [rsp+270h+var_240], rax
0x18000f5e4  test    rax, rax
0x18000f5e7  jnz     short loc_18000F616
0x18000f5e9  call    cs:__imp_GetLastError
0x18000f5ef  cmp     eax, 2
0x18000f5f2  jz      loc_18000F6FD
0x18000f5f8  mov     rcx, [rbp+178h]; this
0x18000f5ff  lea     r8, aWil; "wil"
0x18000f606  lea     edx, [r14-34h]; void *
0x18000f60a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f60f  mov     ebx, eax
0x18000f611  jmp     loc_18000F6FF
0x18000f616  lea     rdx, [rsp+270h+var_24C]; int *
0x18000f61b  mov     [rsp+270h+var_24C], 0
0x18000f623  mov     rcx, rax; hHandle
0x18000f626  mov     [rsp+270h+var_250], 0; int
0x18000f62e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000f633  mov     ebx, eax
0x18000f635  test    eax, eax
0x18000f637  jns     short loc_18000F659
0x18000f639  mov     rcx, [rbp+178h]; this
0x18000f640  lea     r8, aWil; "wil"
0x18000f647  mov     r9d, eax; char *
0x18000f64a  mov     edx, 0D6h; void *
0x18000f64f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f654  jmp     loc_18000F6FF
0x18000f659  lea     r8, asc_1801045F8; "h"
0x18000f660  mov     rdx, r14; unsigned __int64
0x18000f663  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000f668  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f66d  lea     r8, [rsp+270h+Name]; lpName
0x18000f672  xor     edx, edx; bInheritHandle
0x18000f674  mov     ecx, 1F0003h; dwDesiredAccess
0x18000f679  call    cs:__imp_OpenSemaphoreW
0x18000f67f  mov     [rsp+270h+var_248], rax
0x18000f684  test    rax, rax
0x18000f687  jnz     short loc_18000F6AF
0x18000f689  mov     rcx, [rbp+178h]; this
0x18000f690  lea     r8, aWil; "wil"
0x18000f697  mov     edx, 0DCh; void *
0x18000f69c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f6a1  mov     ebx, eax
0x18000f6a3  lea     rcx, [rsp+270h+var_248]
0x18000f6a8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f6ad  jmp     short loc_18000F6FF
0x18000f6af  lea     rdx, [rsp+270h+var_250]; int *
0x18000f6b4  mov     rcx, rax; hHandle
0x18000f6b7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000f6bc  mov     ebx, eax
0x18000f6be  test    eax, eax
0x18000f6c0  jns     short loc_18000F6DF
0x18000f6c2  mov     rcx, [rbp+178h]; this
0x18000f6c9  lea     r8, aWil; "wil"
0x18000f6d0  mov     r9d, eax; char *
0x18000f6d3  mov     edx, 0DEh; void *
0x18000f6d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f6dd  jmp     short loc_18000F6A3
0x18000f6df  lea     rcx, [rsp+270h+var_248]
0x18000f6e4  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f6e9  movsxd  rcx, [rsp+270h+var_250]
0x18000f6ee  movsxd  rax, [rsp+270h+var_24C]
0x18000f6f3  shl     rcx, 1Fh
0x18000f6f7  or      rcx, rax
0x18000f6fa  mov     [rdi], rcx
0x18000f6fd  xor     ebx, ebx
0x18000f6ff  lea     rcx, [rsp+270h+var_240]
0x18000f704  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000f709  mov     eax, ebx
0x18000f70b  mov     rcx, [rbp+170h+var_20]
0x18000f712  xor     rcx, rsp; StackCookie
0x18000f715  call    __security_check_cookie
0x18000f71a  mov     rbx, [rsp+270h+arg_8]
0x18000f722  add     rsp, 260h
0x18000f729  pop     r14
0x18000f72b  pop     rdi
0x18000f72c  pop     rbp
0x18000f72d  retn
```
