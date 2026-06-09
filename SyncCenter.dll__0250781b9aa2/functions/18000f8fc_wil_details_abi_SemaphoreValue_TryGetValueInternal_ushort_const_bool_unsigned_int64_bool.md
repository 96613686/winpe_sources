# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000f8fc`
- end: `0x18000faac`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `432`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000f878`

## callees

- `0x180005660`
- `0x18000b8d8`
- `0x18000df0c`
- `0x18000eb88`
- `0x18000f490`
- `0x18000f784`
- `0x18000f8fc`
- `0x180052950`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f965`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f9fe`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f965`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000f9fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f975`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f975`

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
  HANDLE v10; // rax
  unsigned int v11; // r8d
  const char *v12; // r9
  int v13; // eax
  int v15; // [rsp+20h] [rbp-E0h] BYREF
  int v16; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v17; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v18[0] = v5;
  if ( v5 )
  {
    v16 = 0;
    v15 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v16);
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
    StringCchCatW(Name, 0x104u, L"h");
    v10 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v17 = v10;
    if ( v10 )
    {
      v13 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v10, &v15);
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
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v11, v12);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v6, v7);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v18);
  return LastError;
}

```

## disassembly

```asm
0x18000f8fc  mov     [rsp-8+arg_8], rbx
0x18000f901  push    rbp
0x18000f902  push    rdi
0x18000f903  push    r14
0x18000f905  lea     rbp, [rsp-160h]
0x18000f90d  sub     rsp, 260h
0x18000f914  mov     rax, cs:__security_cookie
0x18000f91b  xor     rax, rsp
0x18000f91e  mov     [rbp+170h+var_20], rax
0x18000f925  mov     rdi, r8
0x18000f928  mov     qword ptr [r8], 0
0x18000f92f  mov     r8, rcx; unsigned __int16 *
0x18000f932  mov     r14d, 104h
0x18000f938  mov     edx, r14d; unsigned __int64
0x18000f93b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000f940  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f945  lea     r8, aP0; "_p0"
0x18000f94c  mov     edx, r14d; unsigned __int64
0x18000f94f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000f954  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f959  lea     r8, [rsp+270h+Name]; lpName
0x18000f95e  xor     edx, edx; bInheritHandle
0x18000f960  mov     ecx, 1F0003h; dwDesiredAccess
0x18000f965  call    cs:__imp_OpenSemaphoreW
0x18000f96b  mov     [rsp+270h+var_240], rax
0x18000f970  test    rax, rax
0x18000f973  jnz     short loc_18000F99B
0x18000f975  call    cs:__imp_GetLastError
0x18000f97b  cmp     eax, 2
0x18000f97e  jz      loc_18000FA7B
0x18000f984  mov     rcx, [rbp+178h]; this
0x18000f98b  lea     edx, [r14-34h]; void *
0x18000f98f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000f994  mov     ebx, eax
0x18000f996  jmp     loc_18000FA7D
0x18000f99b  lea     rdx, [rsp+270h+var_24C]; int *
0x18000f9a0  mov     [rsp+270h+var_24C], 0
0x18000f9a8  mov     rcx, rax; hHandle
0x18000f9ab  mov     [rsp+270h+var_250], 0; int
0x18000f9b3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000f9b8  mov     ebx, eax
0x18000f9ba  test    eax, eax
0x18000f9bc  jns     short loc_18000F9DE
0x18000f9be  mov     rcx, [rbp+178h]; this
0x18000f9c5  lea     r8, aWil; "wil"
0x18000f9cc  mov     r9d, eax; char *
0x18000f9cf  mov     edx, 0D6h; void *
0x18000f9d4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f9d9  jmp     loc_18000FA7D
0x18000f9de  lea     r8, asc_18005D290; "h"
0x18000f9e5  mov     rdx, r14; unsigned __int64
0x18000f9e8  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000f9ed  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000f9f2  lea     r8, [rsp+270h+Name]; lpName
0x18000f9f7  xor     edx, edx; bInheritHandle
0x18000f9f9  mov     ecx, 1F0003h; dwDesiredAccess
0x18000f9fe  call    cs:__imp_OpenSemaphoreW
0x18000fa04  mov     [rsp+270h+var_248], rax
0x18000fa09  test    rax, rax
0x18000fa0c  jnz     short loc_18000FA2D
0x18000fa0e  mov     rcx, [rbp+178h]; this
0x18000fa15  mov     edx, 0DCh; void *
0x18000fa1a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000fa1f  mov     ebx, eax
0x18000fa21  lea     rcx, [rsp+270h+var_248]
0x18000fa26  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000fa2b  jmp     short loc_18000FA7D
0x18000fa2d  lea     rdx, [rsp+270h+var_250]; int *
0x18000fa32  mov     rcx, rax; hHandle
0x18000fa35  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000fa3a  mov     ebx, eax
0x18000fa3c  test    eax, eax
0x18000fa3e  jns     short loc_18000FA5D
0x18000fa40  mov     rcx, [rbp+178h]; this
0x18000fa47  lea     r8, aWil; "wil"
0x18000fa4e  mov     r9d, eax; char *
0x18000fa51  mov     edx, 0DEh; void *
0x18000fa56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fa5b  jmp     short loc_18000FA21
0x18000fa5d  lea     rcx, [rsp+270h+var_248]
0x18000fa62  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000fa67  movsxd  rcx, [rsp+270h+var_250]
0x18000fa6c  movsxd  rax, [rsp+270h+var_24C]
0x18000fa71  shl     rcx, 1Fh
0x18000fa75  or      rcx, rax
0x18000fa78  mov     [rdi], rcx
0x18000fa7b  xor     ebx, ebx
0x18000fa7d  lea     rcx, [rsp+270h+var_240]
0x18000fa82  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000fa87  mov     eax, ebx
0x18000fa89  mov     rcx, [rbp+170h+var_20]
0x18000fa90  xor     rcx, rsp; StackCookie
0x18000fa93  call    __security_check_cookie
0x18000fa98  mov     rbx, [rsp+270h+arg_8]
0x18000faa0  add     rsp, 260h
0x18000faa7  pop     r14
0x18000faa9  pop     rdi
0x18000faaa  pop     rbp
0x18000faab  retn
```
