# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18009fb64`
- end: `0x18009fd06`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18008bca0`

## callees

- `0x18003b118`
- `0x18007e9e0`
- `0x18008b294`
- `0x180092b08`
- `0x18009cc98`
- `0x18009ccb8`
- `0x18009f060`
- `0x18009fb64`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009fbdd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009fbdd`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18009fbcd`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18009fc5f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18009fbcd`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18009fc5f`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  HANDLE v5; // rax
  unsigned int v6; // r8d
  const char *v7; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned int v10; // r8d
  HANDLE v11; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  int v14; // eax
  unsigned int v15; // r8d
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20[0] = v5;
  if ( v5 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v18);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v10, (const char *)(unsigned int)ValueFromSemaphore, v17);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v11 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v11;
    if ( v11 )
    {
      v14 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v17);
      LastError = v14;
      if ( v14 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v15, (const char *)(unsigned int)v14, v17);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v12, v13);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v6, v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x18009fb64  mov     [rsp-8+arg_8], rbx
0x18009fb69  push    rbp
0x18009fb6a  push    rdi
0x18009fb6b  push    r14
0x18009fb6d  lea     rbp, [rsp-160h]
0x18009fb75  sub     rsp, 260h
0x18009fb7c  mov     rax, cs:__security_cookie
0x18009fb83  xor     rax, rsp
0x18009fb86  mov     [rbp+170h+var_20], rax
0x18009fb8d  mov     rdi, r8
0x18009fb90  mov     qword ptr [r8], 0
0x18009fb97  mov     r8, rcx; unsigned __int16 *
0x18009fb9a  mov     r14d, 104h
0x18009fba0  mov     edx, r14d; unsigned __int64
0x18009fba3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18009fba8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18009fbad  lea     r8, aP0; "_p0"
0x18009fbb4  mov     edx, r14d; unsigned __int64
0x18009fbb7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18009fbbc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18009fbc1  lea     r8, [rsp+270h+Name]; lpName
0x18009fbc6  xor     edx, edx; bInheritHandle
0x18009fbc8  mov     ecx, 1F0003h; dwDesiredAccess
0x18009fbcd  call    cs:__imp_OpenSemaphoreW
0x18009fbd3  mov     [rsp+270h+var_240], rax
0x18009fbd8  test    rax, rax
0x18009fbdb  jnz     short loc_18009FC03
0x18009fbdd  call    cs:__imp_GetLastError
0x18009fbe3  cmp     eax, 2
0x18009fbe6  jz      loc_18009FCD5
0x18009fbec  mov     rcx, [rbp+178h]; this
0x18009fbf3  lea     edx, [r14-34h]; void *
0x18009fbf7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009fbfc  mov     ebx, eax
0x18009fbfe  jmp     loc_18009FCD7
0x18009fc03  lea     rdx, [rsp+270h+var_24C]; int *
0x18009fc08  mov     [rsp+270h+var_24C], 0
0x18009fc10  mov     rcx, rax; hHandle
0x18009fc13  mov     [rsp+270h+var_250], 0; int
0x18009fc1b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18009fc20  mov     ebx, eax
0x18009fc22  test    eax, eax
0x18009fc24  jns     short loc_18009FC3F
0x18009fc26  mov     rcx, [rbp+178h]; this
0x18009fc2d  mov     r9d, eax; char *
0x18009fc30  mov     edx, 0D6h; void *
0x18009fc35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009fc3a  jmp     loc_18009FCD7
0x18009fc3f  lea     r8, asc_1801AD488; "h"
0x18009fc46  mov     rdx, r14; unsigned __int64
0x18009fc49  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18009fc4e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18009fc53  lea     r8, [rsp+270h+Name]; lpName
0x18009fc58  xor     edx, edx; bInheritHandle
0x18009fc5a  mov     ecx, 1F0003h; dwDesiredAccess
0x18009fc5f  call    cs:__imp_OpenSemaphoreW
0x18009fc65  mov     [rsp+270h+var_248], rax
0x18009fc6a  test    rax, rax
0x18009fc6d  jnz     short loc_18009FC8E
0x18009fc6f  mov     rcx, [rbp+178h]; this
0x18009fc76  mov     edx, 0DCh; void *
0x18009fc7b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009fc80  mov     ebx, eax
0x18009fc82  lea     rcx, [rsp+270h+var_248]
0x18009fc87  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009fc8c  jmp     short loc_18009FCD7
0x18009fc8e  lea     rdx, [rsp+270h+var_250]; int *
0x18009fc93  mov     rcx, rax; hHandle
0x18009fc96  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18009fc9b  mov     ebx, eax
0x18009fc9d  test    eax, eax
0x18009fc9f  jns     short loc_18009FCB7
0x18009fca1  mov     rcx, [rbp+178h]; this
0x18009fca8  mov     r9d, eax; char *
0x18009fcab  mov     edx, 0DEh; void *
0x18009fcb0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009fcb5  jmp     short loc_18009FC82
0x18009fcb7  lea     rcx, [rsp+270h+var_248]
0x18009fcbc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009fcc1  movsxd  rcx, [rsp+270h+var_250]
0x18009fcc6  movsxd  rax, [rsp+270h+var_24C]
0x18009fccb  shl     rcx, 1Fh
0x18009fccf  or      rcx, rax
0x18009fcd2  mov     [rdi], rcx
0x18009fcd5  xor     ebx, ebx
0x18009fcd7  lea     rcx, [rsp+270h+var_240]
0x18009fcdc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18009fce1  mov     eax, ebx
0x18009fce3  mov     rcx, [rbp+170h+var_20]
0x18009fcea  xor     rcx, rsp; StackCookie
0x18009fced  call    __security_check_cookie
0x18009fcf2  mov     rbx, [rsp+270h+arg_8]
0x18009fcfa  add     rsp, 260h
0x18009fd01  pop     r14
0x18009fd03  pop     rdi
0x18009fd04  pop     rbp
0x18009fd05  retn
```
