# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009dcc`
- end: `0x180009f7c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `432`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180009d48`

## callees

- `0x180003450`
- `0x180005c74`
- `0x1800072f8`
- `0x18000910c`
- `0x18000912c`
- `0x1800097f8`
- `0x180009884`
- `0x180009dcc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009e35`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009ece`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009e35`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009ece`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e45`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009e45`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  wil::details *v5; // rax
  void *v6; // rdx
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  wil::details *v11; // rax
  unsigned int v12; // r8d
  const char *v13; // r9
  void *v14; // rdx
  int v15; // eax
  void *v16; // rdx
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v20; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v21; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 0x104u, L"_p0");
  v5 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v5;
  if ( v5 )
  {
    v19 = 0;
    v18 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v19);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v18);
      goto LABEL_13;
    }
    StringCchCatW(Name, 0x104u, L"h");
    v11 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v20 = v11;
    if ( v11 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v11, &v18);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v20,
          v16);
        *a3 = v19 | (unsigned __int64)((__int64)v18 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v15,
        v18);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v12, v13);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v20,
      v14);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v21,
    v6);
  return LastError;
}

```

## disassembly

```asm
0x180009dcc  mov     [rsp-8+arg_8], rbx
0x180009dd1  push    rbp
0x180009dd2  push    rdi
0x180009dd3  push    r14
0x180009dd5  lea     rbp, [rsp-160h]
0x180009ddd  sub     rsp, 260h
0x180009de4  mov     rax, cs:__security_cookie
0x180009deb  xor     rax, rsp
0x180009dee  mov     [rbp+170h+var_20], rax
0x180009df5  mov     rdi, r8
0x180009df8  mov     qword ptr [r8], 0
0x180009dff  mov     r8, rcx; unsigned __int16 *
0x180009e02  mov     r14d, 104h
0x180009e08  mov     edx, r14d; unsigned __int64
0x180009e0b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009e10  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009e15  lea     r8, aP0; "_p0"
0x180009e1c  mov     edx, r14d; unsigned __int64
0x180009e1f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009e24  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009e29  lea     r8, [rsp+270h+Name]; lpName
0x180009e2e  xor     edx, edx; bInheritHandle
0x180009e30  mov     ecx, 1F0003h; dwDesiredAccess
0x180009e35  call    cs:__imp_OpenSemaphoreW
0x180009e3b  mov     [rsp+270h+var_240], rax
0x180009e40  test    rax, rax
0x180009e43  jnz     short loc_180009E6B
0x180009e45  call    cs:__imp_GetLastError
0x180009e4b  cmp     eax, 2
0x180009e4e  jz      loc_180009F4B
0x180009e54  mov     rcx, [rbp+178h]; this
0x180009e5b  lea     edx, [r14-34h]; void *
0x180009e5f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009e64  mov     ebx, eax
0x180009e66  jmp     loc_180009F4D
0x180009e6b  lea     rdx, [rsp+270h+var_24C]; int *
0x180009e70  mov     [rsp+270h+var_24C], 0
0x180009e78  mov     rcx, rax; hHandle
0x180009e7b  mov     [rsp+270h+var_250], 0; int
0x180009e83  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009e88  mov     ebx, eax
0x180009e8a  test    eax, eax
0x180009e8c  jns     short loc_180009EAE
0x180009e8e  mov     rcx, [rbp+178h]; this
0x180009e95  lea     r8, aWil; "wil"
0x180009e9c  mov     r9d, eax; char *
0x180009e9f  mov     edx, 0D6h; void *
0x180009ea4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009ea9  jmp     loc_180009F4D
0x180009eae  lea     r8, asc_18004A998; "h"
0x180009eb5  mov     rdx, r14; unsigned __int64
0x180009eb8  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009ebd  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009ec2  lea     r8, [rsp+270h+Name]; lpName
0x180009ec7  xor     edx, edx; bInheritHandle
0x180009ec9  mov     ecx, 1F0003h; dwDesiredAccess
0x180009ece  call    cs:__imp_OpenSemaphoreW
0x180009ed4  mov     [rsp+270h+var_248], rax
0x180009ed9  test    rax, rax
0x180009edc  jnz     short loc_180009EFD
0x180009ede  mov     rcx, [rbp+178h]; this
0x180009ee5  mov     edx, 0DCh; void *
0x180009eea  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009eef  mov     ebx, eax
0x180009ef1  lea     rcx, [rsp+270h+var_248]
0x180009ef6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009efb  jmp     short loc_180009F4D
0x180009efd  lea     rdx, [rsp+270h+var_250]; int *
0x180009f02  mov     rcx, rax; hHandle
0x180009f05  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180009f0a  mov     ebx, eax
0x180009f0c  test    eax, eax
0x180009f0e  jns     short loc_180009F2D
0x180009f10  mov     rcx, [rbp+178h]; this
0x180009f17  lea     r8, aWil; "wil"
0x180009f1e  mov     r9d, eax; char *
0x180009f21  mov     edx, 0DEh; void *
0x180009f26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009f2b  jmp     short loc_180009EF1
0x180009f2d  lea     rcx, [rsp+270h+var_248]
0x180009f32  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009f37  movsxd  rcx, [rsp+270h+var_250]
0x180009f3c  movsxd  rax, [rsp+270h+var_24C]
0x180009f41  shl     rcx, 1Fh
0x180009f45  or      rcx, rax
0x180009f48  mov     [rdi], rcx
0x180009f4b  xor     ebx, ebx
0x180009f4d  lea     rcx, [rsp+270h+var_240]
0x180009f52  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009f57  mov     eax, ebx
0x180009f59  mov     rcx, [rbp+170h+var_20]
0x180009f60  xor     rcx, rsp; StackCookie
0x180009f63  call    __security_check_cookie
0x180009f68  mov     rbx, [rsp+270h+arg_8]
0x180009f70  add     rsp, 260h
0x180009f77  pop     r14
0x180009f79  pop     rdi
0x180009f7a  pop     rbp
0x180009f7b  retn
```
