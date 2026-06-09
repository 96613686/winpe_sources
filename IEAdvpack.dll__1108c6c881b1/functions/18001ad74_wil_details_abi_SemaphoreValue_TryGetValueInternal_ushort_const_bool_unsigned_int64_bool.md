# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001ad74`
- end: `0x18001af16`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(size_t *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180018a30`

## callees

- `0x1800022bc`
- `0x180003180`
- `0x1800189b0`
- `0x180019590`
- `0x18001a9b4`
- `0x18001a9d4`
- `0x18001ad74`
- `0x18001b980`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x18001addd`
- `KERNEL32!OpenSemaphoreW` at `0x18001ae6f`
- `KERNEL32!OpenSemaphoreW` at `0x18001addd`
- `KERNEL32!OpenSemaphoreW` at `0x18001ae6f`
- `KERNEL32!GetLastError` at `0x18001aded`
- `KERNEL32!GetLastError` at `0x18001aded`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        size_t *a1,
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
  int v11; // r8d
  wil::details *v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  void *v15; // rdx
  int v16; // eax
  void *v17; // rdx
  int v18; // r8d
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v22; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v23; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, 260, L"_p0");
  v5 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v23 = v5;
  if ( v5 )
  {
    v21 = 0;
    v20 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v5, &v21);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v11, (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(Name, 260, L"h");
    v12 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v22 = v12;
    if ( v12 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v20);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v22,
          v17);
        *a3 = v21 | (unsigned __int64)((__int64)v20 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v18, (const char *)(unsigned int)v16);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v13, v14);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
      &v22,
      v15);
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
    &v23,
    v6);
  return LastError;
}

```

## disassembly

```asm
0x18001ad74  mov     [rsp-8+arg_8], rbx
0x18001ad79  push    rbp
0x18001ad7a  push    rdi
0x18001ad7b  push    r14
0x18001ad7d  lea     rbp, [rsp-160h]
0x18001ad85  sub     rsp, 260h
0x18001ad8c  mov     rax, cs:__security_cookie
0x18001ad93  xor     rax, rsp
0x18001ad96  mov     [rbp+170h+var_20], rax
0x18001ad9d  mov     rdi, r8
0x18001ada0  mov     qword ptr [r8], 0
0x18001ada7  mov     r8, rcx; unsigned __int16 *
0x18001adaa  mov     r14d, 104h
0x18001adb0  mov     edx, r14d; unsigned __int64
0x18001adb3  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001adb8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001adbd  lea     r8, aP0; "_p0"
0x18001adc4  mov     edx, r14d; unsigned __int64
0x18001adc7  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001adcc  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001add1  lea     r8, [rsp+270h+Name]; lpName
0x18001add6  xor     edx, edx; bInheritHandle
0x18001add8  mov     ecx, 1F0003h; dwDesiredAccess
0x18001addd  call    cs:__imp_OpenSemaphoreW
0x18001ade3  mov     [rsp+270h+var_240], rax
0x18001ade8  test    rax, rax
0x18001adeb  jnz     short loc_18001AE13
0x18001aded  call    cs:__imp_GetLastError
0x18001adf3  cmp     eax, 2
0x18001adf6  jz      loc_18001AEE5
0x18001adfc  mov     rcx, [rbp+178h]; this
0x18001ae03  lea     edx, [r14-34h]; void *
0x18001ae07  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ae0c  mov     ebx, eax
0x18001ae0e  jmp     loc_18001AEE7
0x18001ae13  lea     rdx, [rsp+270h+var_24C]; int *
0x18001ae18  mov     [rsp+270h+var_24C], 0
0x18001ae20  mov     rcx, rax; hHandle
0x18001ae23  mov     [rsp+270h+var_250], 0; int
0x18001ae2b  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001ae30  mov     ebx, eax
0x18001ae32  test    eax, eax
0x18001ae34  jns     short loc_18001AE4F
0x18001ae36  mov     rcx, [rbp+178h]; this
0x18001ae3d  mov     r9d, eax; char *
0x18001ae40  mov     edx, 0D6h; void *
0x18001ae45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ae4a  jmp     loc_18001AEE7
0x18001ae4f  lea     r8, asc_1800210D0; "h"
0x18001ae56  mov     rdx, r14; unsigned __int64
0x18001ae59  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18001ae5e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001ae63  lea     r8, [rsp+270h+Name]; lpName
0x18001ae68  xor     edx, edx; bInheritHandle
0x18001ae6a  mov     ecx, 1F0003h; dwDesiredAccess
0x18001ae6f  call    cs:__imp_OpenSemaphoreW
0x18001ae75  mov     [rsp+270h+var_248], rax
0x18001ae7a  test    rax, rax
0x18001ae7d  jnz     short loc_18001AE9E
0x18001ae7f  mov     rcx, [rbp+178h]; this
0x18001ae86  mov     edx, 0DCh; void *
0x18001ae8b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001ae90  mov     ebx, eax
0x18001ae92  lea     rcx, [rsp+270h+var_248]
0x18001ae97  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001ae9c  jmp     short loc_18001AEE7
0x18001ae9e  lea     rdx, [rsp+270h+var_250]; int *
0x18001aea3  mov     rcx, rax; hHandle
0x18001aea6  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001aeab  mov     ebx, eax
0x18001aead  test    eax, eax
0x18001aeaf  jns     short loc_18001AEC7
0x18001aeb1  mov     rcx, [rbp+178h]; this
0x18001aeb8  mov     r9d, eax; char *
0x18001aebb  mov     edx, 0DEh; void *
0x18001aec0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001aec5  jmp     short loc_18001AE92
0x18001aec7  lea     rcx, [rsp+270h+var_248]
0x18001aecc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001aed1  movsxd  rcx, [rsp+270h+var_250]
0x18001aed6  movsxd  rax, [rsp+270h+var_24C]
0x18001aedb  shl     rcx, 1Fh
0x18001aedf  or      rcx, rax
0x18001aee2  mov     [rdi], rcx
0x18001aee5  xor     ebx, ebx
0x18001aee7  lea     rcx, [rsp+270h+var_240]
0x18001aeec  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001aef1  mov     eax, ebx
0x18001aef3  mov     rcx, [rbp+170h+var_20]
0x18001aefa  xor     rcx, rsp; StackCookie
0x18001aefd  call    __security_check_cookie
0x18001af02  mov     rbx, [rsp+270h+arg_8]
0x18001af0a  add     rsp, 260h
0x18001af11  pop     r14
0x18001af13  pop     rdi
0x18001af14  pop     rbp
0x18001af15  retn
```
