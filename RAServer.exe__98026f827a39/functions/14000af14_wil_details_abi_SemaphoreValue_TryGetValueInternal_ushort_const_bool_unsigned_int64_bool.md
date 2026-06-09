# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x14000af14`
- end: `0x14000b0b6`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `418`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x14000aea0`

## callees

- `0x140003994`
- `0x140006f48`
- `0x14000a16c`
- `0x14000a18c`
- `0x14000a9c4`
- `0x14000aab8`
- `0x14000af14`
- `0x140015aa0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14000af8d`
- `KERNEL32!GetLastError` at `0x14000af8d`
- `KERNEL32!OpenSemaphoreW` at `0x14000af7d`
- `KERNEL32!OpenSemaphoreW` at `0x14000b00f`
- `KERNEL32!OpenSemaphoreW` at `0x14000af7d`
- `KERNEL32!OpenSemaphoreW` at `0x14000b00f`

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
  StringCchCatW(Name, 0x104u, L"_p0");
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
    StringCchCatW(Name, 0x104u, L"h");
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
0x14000af14  mov     [rsp-8+arg_8], rbx
0x14000af19  push    rbp
0x14000af1a  push    rdi
0x14000af1b  push    r14
0x14000af1d  lea     rbp, [rsp-160h]
0x14000af25  sub     rsp, 260h
0x14000af2c  mov     rax, cs:__security_cookie
0x14000af33  xor     rax, rsp
0x14000af36  mov     [rbp+170h+var_20], rax
0x14000af3d  mov     rdi, r8
0x14000af40  mov     qword ptr [r8], 0
0x14000af47  mov     r8, rcx; unsigned __int16 *
0x14000af4a  mov     r14d, 104h
0x14000af50  mov     edx, r14d; unsigned __int64
0x14000af53  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000af58  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000af5d  lea     r8, aP0; "_p0"
0x14000af64  mov     edx, r14d; unsigned __int64
0x14000af67  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000af6c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000af71  lea     r8, [rsp+270h+Name]; lpName
0x14000af76  xor     edx, edx; bInheritHandle
0x14000af78  mov     ecx, 1F0003h; dwDesiredAccess
0x14000af7d  call    cs:__imp_OpenSemaphoreW
0x14000af83  mov     [rsp+270h+var_240], rax
0x14000af88  test    rax, rax
0x14000af8b  jnz     short loc_14000AFB3
0x14000af8d  call    cs:__imp_GetLastError
0x14000af93  cmp     eax, 2
0x14000af96  jz      loc_14000B085
0x14000af9c  mov     rcx, [rbp+178h]; this
0x14000afa3  lea     edx, [r14-34h]; void *
0x14000afa7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000afac  mov     ebx, eax
0x14000afae  jmp     loc_14000B087
0x14000afb3  lea     rdx, [rsp+270h+var_24C]; int *
0x14000afb8  mov     [rsp+270h+var_24C], 0
0x14000afc0  mov     rcx, rax; hHandle
0x14000afc3  mov     [rsp+270h+var_250], 0; int
0x14000afcb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000afd0  mov     ebx, eax
0x14000afd2  test    eax, eax
0x14000afd4  jns     short loc_14000AFEF
0x14000afd6  mov     rcx, [rbp+178h]; this
0x14000afdd  mov     r9d, eax; char *
0x14000afe0  mov     edx, 0D6h; void *
0x14000afe5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000afea  jmp     loc_14000B087
0x14000afef  lea     r8, asc_14001AFC8; "h"
0x14000aff6  mov     rdx, r14; unsigned __int64
0x14000aff9  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x14000affe  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x14000b003  lea     r8, [rsp+270h+Name]; lpName
0x14000b008  xor     edx, edx; bInheritHandle
0x14000b00a  mov     ecx, 1F0003h; dwDesiredAccess
0x14000b00f  call    cs:__imp_OpenSemaphoreW
0x14000b015  mov     [rsp+270h+var_248], rax
0x14000b01a  test    rax, rax
0x14000b01d  jnz     short loc_14000B03E
0x14000b01f  mov     rcx, [rbp+178h]; this
0x14000b026  mov     edx, 0DCh; void *
0x14000b02b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14000b030  mov     ebx, eax
0x14000b032  lea     rcx, [rsp+270h+var_248]
0x14000b037  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000b03c  jmp     short loc_14000B087
0x14000b03e  lea     rdx, [rsp+270h+var_250]; int *
0x14000b043  mov     rcx, rax; hHandle
0x14000b046  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x14000b04b  mov     ebx, eax
0x14000b04d  test    eax, eax
0x14000b04f  jns     short loc_14000B067
0x14000b051  mov     rcx, [rbp+178h]; this
0x14000b058  mov     r9d, eax; char *
0x14000b05b  mov     edx, 0DEh; void *
0x14000b060  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14000b065  jmp     short loc_14000B032
0x14000b067  lea     rcx, [rsp+270h+var_248]
0x14000b06c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000b071  movsxd  rcx, [rsp+270h+var_250]
0x14000b076  movsxd  rax, [rsp+270h+var_24C]
0x14000b07b  shl     rcx, 1Fh
0x14000b07f  or      rcx, rax
0x14000b082  mov     [rdi], rcx
0x14000b085  xor     ebx, ebx
0x14000b087  lea     rcx, [rsp+270h+var_240]
0x14000b08c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x14000b091  mov     eax, ebx
0x14000b093  mov     rcx, [rbp+170h+var_20]
0x14000b09a  xor     rcx, rsp; StackCookie
0x14000b09d  call    __security_check_cookie
0x14000b0a2  mov     rbx, [rsp+270h+arg_8]
0x14000b0aa  add     rsp, 260h
0x14000b0b1  pop     r14
0x14000b0b3  pop     rdi
0x14000b0b4  pop     rbp
0x14000b0b5  retn
```
