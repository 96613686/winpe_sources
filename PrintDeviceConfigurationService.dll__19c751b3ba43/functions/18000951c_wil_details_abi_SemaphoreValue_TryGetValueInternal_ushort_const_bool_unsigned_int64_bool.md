# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000951c`
- end: `0x1800096cc`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `432`
- prototype: `__int64 __fastcall(size_t *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180009498`

## callees

- `0x1800020c0`
- `0x180004f08`
- `0x180006650`
- `0x18000879c`
- `0x1800087bc`
- `0x180008e7c`
- `0x180008f08`
- `0x18000951c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009585`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000961e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180009585`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000961e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009595`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009595`

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
        (int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore);
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
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v15);
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
0x18000951c  mov     [rsp-8+arg_8], rbx
0x180009521  push    rbp
0x180009522  push    rdi
0x180009523  push    r14
0x180009525  lea     rbp, [rsp-160h]
0x18000952d  sub     rsp, 260h
0x180009534  mov     rax, cs:__security_cookie
0x18000953b  xor     rax, rsp
0x18000953e  mov     [rbp+170h+var_20], rax
0x180009545  mov     rdi, r8
0x180009548  mov     qword ptr [r8], 0
0x18000954f  mov     r8, rcx; unsigned __int16 *
0x180009552  mov     r14d, 104h
0x180009558  mov     edx, r14d; unsigned __int64
0x18000955b  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009560  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009565  lea     r8, aP0; "_p0"
0x18000956c  mov     edx, r14d; unsigned __int64
0x18000956f  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x180009574  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009579  lea     r8, [rsp+270h+Name]; lpName
0x18000957e  xor     edx, edx; bInheritHandle
0x180009580  mov     ecx, 1F0003h; dwDesiredAccess
0x180009585  call    cs:__imp_OpenSemaphoreW
0x18000958b  mov     [rsp+270h+var_240], rax
0x180009590  test    rax, rax
0x180009593  jnz     short loc_1800095BB
0x180009595  call    cs:__imp_GetLastError
0x18000959b  cmp     eax, 2
0x18000959e  jz      loc_18000969B
0x1800095a4  mov     rcx, [rbp+178h]; this
0x1800095ab  lea     edx, [r14-34h]; void *
0x1800095af  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800095b4  mov     ebx, eax
0x1800095b6  jmp     loc_18000969D
0x1800095bb  lea     rdx, [rsp+270h+var_24C]; int *
0x1800095c0  mov     [rsp+270h+var_24C], 0
0x1800095c8  mov     rcx, rax; hHandle
0x1800095cb  mov     [rsp+270h+var_250], 0; int
0x1800095d3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800095d8  mov     ebx, eax
0x1800095da  test    eax, eax
0x1800095dc  jns     short loc_1800095FE
0x1800095de  mov     rcx, [rbp+178h]; this
0x1800095e5  lea     r8, aWil; "wil"
0x1800095ec  mov     r9d, eax; char *
0x1800095ef  mov     edx, 0D6h; void *
0x1800095f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800095f9  jmp     loc_18000969D
0x1800095fe  lea     r8, asc_18001A158; "h"
0x180009605  mov     rdx, r14; unsigned __int64
0x180009608  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000960d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180009612  lea     r8, [rsp+270h+Name]; lpName
0x180009617  xor     edx, edx; bInheritHandle
0x180009619  mov     ecx, 1F0003h; dwDesiredAccess
0x18000961e  call    cs:__imp_OpenSemaphoreW
0x180009624  mov     [rsp+270h+var_248], rax
0x180009629  test    rax, rax
0x18000962c  jnz     short loc_18000964D
0x18000962e  mov     rcx, [rbp+178h]; this
0x180009635  mov     edx, 0DCh; void *
0x18000963a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000963f  mov     ebx, eax
0x180009641  lea     rcx, [rsp+270h+var_248]
0x180009646  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000964b  jmp     short loc_18000969D
0x18000964d  lea     rdx, [rsp+270h+var_250]; int *
0x180009652  mov     rcx, rax; hHandle
0x180009655  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000965a  mov     ebx, eax
0x18000965c  test    eax, eax
0x18000965e  jns     short loc_18000967D
0x180009660  mov     rcx, [rbp+178h]; this
0x180009667  lea     r8, aWil; "wil"
0x18000966e  mov     r9d, eax; char *
0x180009671  mov     edx, 0DEh; void *
0x180009676  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000967b  jmp     short loc_180009641
0x18000967d  lea     rcx, [rsp+270h+var_248]
0x180009682  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180009687  movsxd  rcx, [rsp+270h+var_250]
0x18000968c  movsxd  rax, [rsp+270h+var_24C]
0x180009691  shl     rcx, 1Fh
0x180009695  or      rcx, rax
0x180009698  mov     [rdi], rcx
0x18000969b  xor     ebx, ebx
0x18000969d  lea     rcx, [rsp+270h+var_240]
0x1800096a2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800096a7  mov     eax, ebx
0x1800096a9  mov     rcx, [rbp+170h+var_20]
0x1800096b0  xor     rcx, rsp; StackCookie
0x1800096b3  call    __security_check_cookie
0x1800096b8  mov     rbx, [rsp+270h+arg_8]
0x1800096c0  add     rsp, 260h
0x1800096c7  pop     r14
0x1800096c9  pop     rdi
0x1800096ca  pop     rbp
0x1800096cb  retn
```
