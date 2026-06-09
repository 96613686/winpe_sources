# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000b194`
- end: `0x18000b336`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000b120`

## callees

- `0x180005808`
- `0x180007f94`
- `0x18000a798`
- `0x18000a7b8`
- `0x18000ac20`
- `0x18000ac74`
- `0x18000b194`
- `0x180043090`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b1fd`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b28f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b1fd`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000b28f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b20d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b20d`

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
0x18000b194  mov     [rsp-8+arg_8], rbx
0x18000b199  push    rbp
0x18000b19a  push    rdi
0x18000b19b  push    r14
0x18000b19d  lea     rbp, [rsp-160h]
0x18000b1a5  sub     rsp, 260h
0x18000b1ac  mov     rax, cs:__security_cookie
0x18000b1b3  xor     rax, rsp
0x18000b1b6  mov     [rbp+170h+var_20], rax
0x18000b1bd  mov     rdi, r8
0x18000b1c0  mov     qword ptr [r8], 0
0x18000b1c7  mov     r8, rcx; unsigned __int16 *
0x18000b1ca  mov     r14d, 104h
0x18000b1d0  mov     edx, r14d; unsigned __int64
0x18000b1d3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000b1d8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000b1dd  lea     r8, aP0; "_p0"
0x18000b1e4  mov     edx, r14d; unsigned __int64
0x18000b1e7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000b1ec  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b1f1  lea     r8, [rsp+270h+Name]; lpName
0x18000b1f6  xor     edx, edx; bInheritHandle
0x18000b1f8  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b1fd  call    cs:__imp_OpenSemaphoreW
0x18000b203  mov     [rsp+270h+var_240], rax
0x18000b208  test    rax, rax
0x18000b20b  jnz     short loc_18000B233
0x18000b20d  call    cs:__imp_GetLastError
0x18000b213  cmp     eax, 2
0x18000b216  jz      loc_18000B305
0x18000b21c  mov     rcx, [rbp+178h]; this
0x18000b223  lea     edx, [r14-34h]; void *
0x18000b227  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b22c  mov     ebx, eax
0x18000b22e  jmp     loc_18000B307
0x18000b233  lea     rdx, [rsp+270h+var_24C]; int *
0x18000b238  mov     [rsp+270h+var_24C], 0
0x18000b240  mov     rcx, rax; hHandle
0x18000b243  mov     [rsp+270h+var_250], 0; int
0x18000b24b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b250  mov     ebx, eax
0x18000b252  test    eax, eax
0x18000b254  jns     short loc_18000B26F
0x18000b256  mov     rcx, [rbp+178h]; this
0x18000b25d  mov     r9d, eax; char *
0x18000b260  mov     edx, 0D6h; void *
0x18000b265  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b26a  jmp     loc_18000B307
0x18000b26f  lea     r8, asc_18004A088; "h"
0x18000b276  mov     rdx, r14; unsigned __int64
0x18000b279  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000b27e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000b283  lea     r8, [rsp+270h+Name]; lpName
0x18000b288  xor     edx, edx; bInheritHandle
0x18000b28a  mov     ecx, 1F0003h; dwDesiredAccess
0x18000b28f  call    cs:__imp_OpenSemaphoreW
0x18000b295  mov     [rsp+270h+var_248], rax
0x18000b29a  test    rax, rax
0x18000b29d  jnz     short loc_18000B2BE
0x18000b29f  mov     rcx, [rbp+178h]; this
0x18000b2a6  mov     edx, 0DCh; void *
0x18000b2ab  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000b2b0  mov     ebx, eax
0x18000b2b2  lea     rcx, [rsp+270h+var_248]
0x18000b2b7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b2bc  jmp     short loc_18000B307
0x18000b2be  lea     rdx, [rsp+270h+var_250]; int *
0x18000b2c3  mov     rcx, rax; hHandle
0x18000b2c6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000b2cb  mov     ebx, eax
0x18000b2cd  test    eax, eax
0x18000b2cf  jns     short loc_18000B2E7
0x18000b2d1  mov     rcx, [rbp+178h]; this
0x18000b2d8  mov     r9d, eax; char *
0x18000b2db  mov     edx, 0DEh; void *
0x18000b2e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000b2e5  jmp     short loc_18000B2B2
0x18000b2e7  lea     rcx, [rsp+270h+var_248]
0x18000b2ec  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b2f1  movsxd  rcx, [rsp+270h+var_250]
0x18000b2f6  movsxd  rax, [rsp+270h+var_24C]
0x18000b2fb  shl     rcx, 1Fh
0x18000b2ff  or      rcx, rax
0x18000b302  mov     [rdi], rcx
0x18000b305  xor     ebx, ebx
0x18000b307  lea     rcx, [rsp+270h+var_240]
0x18000b30c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000b311  mov     eax, ebx
0x18000b313  mov     rcx, [rbp+170h+var_20]
0x18000b31a  xor     rcx, rsp; StackCookie
0x18000b31d  call    __security_check_cookie
0x18000b322  mov     rbx, [rsp+270h+arg_8]
0x18000b32a  add     rsp, 260h
0x18000b331  pop     r14
0x18000b333  pop     rdi
0x18000b334  pop     rbp
0x18000b335  retn
```
