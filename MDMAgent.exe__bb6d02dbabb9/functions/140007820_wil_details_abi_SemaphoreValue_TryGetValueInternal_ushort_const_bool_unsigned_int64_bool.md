# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x140007820`
- end: `0x1400079f1`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `465`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000779c`

## callees

- `0x1400029c0`
- `0x140004bb8`
- `0x140005d48`
- `0x140006bd4`
- `0x140006bf4`
- `0x1400074ec`
- `0x1400075e4`
- `0x140007820`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140007889`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140007935`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140007889`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x140007935`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000789f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000789f`

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
0x140007820  mov     [rsp-8+arg_8], rbx
0x140007825  push    rbp
0x140007826  push    rdi
0x140007827  push    r14
0x140007829  lea     rbp, [rsp-160h]
0x140007831  sub     rsp, 260h
0x140007838  mov     rax, cs:__security_cookie
0x14000783f  xor     rax, rsp
0x140007842  mov     [rbp+170h+var_20], rax
0x140007849  mov     rdi, r8
0x14000784c  mov     qword ptr [r8], 0
0x140007853  mov     r8, rcx; unsigned __int16 *
0x140007856  mov     r14d, 104h
0x14000785c  mov     edx, r14d; unsigned __int64
0x14000785f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140007864  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140007869  lea     r8, aP0; "_p0"
0x140007870  mov     edx, r14d; unsigned __int64
0x140007873  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140007878  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000787d  lea     r8, [rsp+270h+Name]; lpName
0x140007882  xor     edx, edx; bInheritHandle
0x140007884  mov     ecx, 1F0003h; dwDesiredAccess
0x140007889  call    cs:__imp_OpenSemaphoreW
0x140007890  nop     dword ptr [rax+rax+00h]
0x140007895  mov     [rsp+270h+var_240], rax
0x14000789a  test    rax, rax
0x14000789d  jnz     short loc_1400078D2
0x14000789f  call    cs:__imp_GetLastError
0x1400078a6  nop     dword ptr [rax+rax+00h]
0x1400078ab  cmp     eax, 2
0x1400078ae  jz      loc_1400079BF
0x1400078b4  mov     rcx, [rbp+178h]; this
0x1400078bb  lea     r8, aWil; "wil"
0x1400078c2  lea     edx, [r14-34h]; void *
0x1400078c6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400078cb  mov     ebx, eax
0x1400078cd  jmp     loc_1400079C1
0x1400078d2  lea     rdx, [rsp+270h+var_24C]; int *
0x1400078d7  mov     [rsp+270h+var_24C], 0
0x1400078df  mov     rcx, rax; hHandle
0x1400078e2  mov     [rsp+270h+var_250], 0; int
0x1400078ea  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1400078ef  mov     ebx, eax
0x1400078f1  test    eax, eax
0x1400078f3  jns     short loc_140007915
0x1400078f5  mov     rcx, [rbp+178h]; this
0x1400078fc  lea     r8, aWil; "wil"
0x140007903  mov     r9d, eax; char *
0x140007906  mov     edx, 0D6h; void *
0x14000790b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140007910  jmp     loc_1400079C1
0x140007915  lea     r8, asc_14001C068; "h"
0x14000791c  mov     rdx, r14; unsigned __int64
0x14000791f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x140007924  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x140007929  lea     r8, [rsp+270h+Name]; lpName
0x14000792e  xor     edx, edx; bInheritHandle
0x140007930  mov     ecx, 1F0003h; dwDesiredAccess
0x140007935  call    cs:__imp_OpenSemaphoreW
0x14000793c  nop     dword ptr [rax+rax+00h]
0x140007941  mov     [rsp+270h+var_248], rax
0x140007946  test    rax, rax
0x140007949  jnz     short loc_140007971
0x14000794b  mov     rcx, [rbp+178h]; this
0x140007952  lea     r8, aWil; "wil"
0x140007959  mov     edx, 0DCh; void *
0x14000795e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140007963  mov     ebx, eax
0x140007965  lea     rcx, [rsp+270h+var_248]
0x14000796a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000796f  jmp     short loc_1400079C1
0x140007971  lea     rdx, [rsp+270h+var_250]; int *
0x140007976  mov     rcx, rax; hHandle
0x140007979  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000797e  mov     ebx, eax
0x140007980  test    eax, eax
0x140007982  jns     short loc_1400079A1
0x140007984  mov     rcx, [rbp+178h]; this
0x14000798b  lea     r8, aWil; "wil"
0x140007992  mov     r9d, eax; char *
0x140007995  mov     edx, 0DEh; void *
0x14000799a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000799f  jmp     short loc_140007965
0x1400079a1  lea     rcx, [rsp+270h+var_248]
0x1400079a6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400079ab  movsxd  rcx, [rsp+270h+var_250]
0x1400079b0  movsxd  rax, [rsp+270h+var_24C]
0x1400079b5  shl     rcx, 1Fh
0x1400079b9  or      rcx, rax
0x1400079bc  mov     [rdi], rcx
0x1400079bf  xor     ebx, ebx
0x1400079c1  lea     rcx, [rsp+270h+var_240]
0x1400079c6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1400079cb  mov     eax, ebx
0x1400079cd  mov     rcx, [rbp+170h+var_20]
0x1400079d4  xor     rcx, rsp; StackCookie
0x1400079d7  call    __security_check_cookie
0x1400079dc  mov     rbx, [rsp+270h+arg_8]
0x1400079e4  add     rsp, 260h
0x1400079eb  pop     r14
0x1400079ed  pop     rdi
0x1400079ee  pop     rbp
0x1400079ef  retn
```
