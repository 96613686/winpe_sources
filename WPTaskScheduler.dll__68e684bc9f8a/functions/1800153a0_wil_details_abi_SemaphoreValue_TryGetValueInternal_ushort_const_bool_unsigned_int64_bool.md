# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x1800153a0`
- end: `0x18001553c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `412`
- prototype: `__int64 __fastcall(const unsigned __int16 *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18001532c`

## callees

- `0x18000be70`
- `0x180011898`
- `0x180012d64`
- `0x18001478c`
- `0x1800147ac`
- `0x180014e74`
- `0x1800153a0`
- `0x180020c30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180015404`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180015494`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180015404`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180015494`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015414`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015414`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  HANDLE v6; // rax
  unsigned int v7; // r8d
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  int v12; // r8d
  HANDLE v13; // rax
  unsigned int v14; // r8d
  const char *v15; // r9
  int v16; // eax
  int v17; // r8d
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v21; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v22[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v22[0] = v6;
  if ( v6 )
  {
    v20 = 0;
    v19 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v20);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v12, (const char *)(unsigned int)ValueFromSemaphore);
      goto LABEL_13;
    }
    StringCchCatW(Name, v11, L"h");
    v13 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v21 = v13;
    if ( v13 )
    {
      v16 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v19);
      LastError = v16;
      if ( v16 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
        *a3 = v20 | (unsigned __int64)((__int64)v19 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v17, (const char *)(unsigned int)v16);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v14, v15);
    }
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v21);
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
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v22);
  return LastError;
}

```

## disassembly

```asm
0x1800153a0  mov     [rsp-8+arg_8], rbx
0x1800153a5  mov     [rsp-8+arg_18], rdi
0x1800153aa  push    rbp
0x1800153ab  lea     rbp, [rsp-160h]
0x1800153b3  sub     rsp, 260h
0x1800153ba  mov     rax, cs:__security_cookie
0x1800153c1  xor     rax, rsp
0x1800153c4  mov     [rbp+160h+var_10], rax
0x1800153cb  mov     rdi, r8
0x1800153ce  mov     qword ptr [r8], 0
0x1800153d5  mov     r8, rcx; unsigned __int16 *
0x1800153d8  mov     edx, 104h; unsigned __int64
0x1800153dd  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800153e2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800153e7  lea     r8, aP0; "_p0"
0x1800153ee  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800153f3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800153f8  lea     r8, [rsp+260h+Name]; lpName
0x1800153fd  xor     edx, edx; bInheritHandle
0x1800153ff  mov     ecx, 1F0003h; dwDesiredAccess
0x180015404  call    cs:__imp_OpenSemaphoreW
0x18001540a  mov     [rsp+260h+var_230], rax
0x18001540f  test    rax, rax
0x180015412  jnz     short loc_18001543B
0x180015414  call    cs:__imp_GetLastError
0x18001541a  cmp     eax, 2
0x18001541d  jz      loc_18001550A
0x180015423  mov     rcx, [rbp+168h]; this
0x18001542a  mov     edx, 0D0h; void *
0x18001542f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180015434  mov     ebx, eax
0x180015436  jmp     loc_18001550C
0x18001543b  lea     rdx, [rsp+260h+var_23C]; int *
0x180015440  mov     [rsp+260h+var_23C], 0
0x180015448  mov     rcx, rax; hHandle
0x18001544b  mov     [rsp+260h+var_240], 0; int
0x180015453  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180015458  mov     ebx, eax
0x18001545a  test    eax, eax
0x18001545c  jns     short loc_180015477
0x18001545e  mov     rcx, [rbp+168h]; this
0x180015465  mov     r9d, eax; char *
0x180015468  mov     edx, 0D6h; void *
0x18001546d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015472  jmp     loc_18001550C
0x180015477  lea     r8, asc_1800289C0; "h"
0x18001547e  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180015483  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180015488  lea     r8, [rsp+260h+Name]; lpName
0x18001548d  xor     edx, edx; bInheritHandle
0x18001548f  mov     ecx, 1F0003h; dwDesiredAccess
0x180015494  call    cs:__imp_OpenSemaphoreW
0x18001549a  mov     [rsp+260h+var_238], rax
0x18001549f  test    rax, rax
0x1800154a2  jnz     short loc_1800154C3
0x1800154a4  mov     rcx, [rbp+168h]; this
0x1800154ab  mov     edx, 0DCh; void *
0x1800154b0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800154b5  mov     ebx, eax
0x1800154b7  lea     rcx, [rsp+260h+var_238]
0x1800154bc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800154c1  jmp     short loc_18001550C
0x1800154c3  lea     rdx, [rsp+260h+var_240]; int *
0x1800154c8  mov     rcx, rax; hHandle
0x1800154cb  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800154d0  mov     ebx, eax
0x1800154d2  test    eax, eax
0x1800154d4  jns     short loc_1800154EC
0x1800154d6  mov     rcx, [rbp+168h]; this
0x1800154dd  mov     r9d, eax; char *
0x1800154e0  mov     edx, 0DEh; void *
0x1800154e5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800154ea  jmp     short loc_1800154B7
0x1800154ec  lea     rcx, [rsp+260h+var_238]
0x1800154f1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800154f6  movsxd  rcx, [rsp+260h+var_240]
0x1800154fb  movsxd  rax, [rsp+260h+var_23C]
0x180015500  shl     rcx, 1Fh
0x180015504  or      rcx, rax
0x180015507  mov     [rdi], rcx
0x18001550a  xor     ebx, ebx
0x18001550c  lea     rcx, [rsp+260h+var_230]
0x180015511  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180015516  mov     eax, ebx
0x180015518  mov     rcx, [rbp+160h+var_10]
0x18001551f  xor     rcx, rsp; StackCookie
0x180015522  call    __security_check_cookie
0x180015527  lea     r11, [rsp+260h+var_s0]
0x18001552f  mov     rbx, [r11+18h]
0x180015533  mov     rdi, [r11+28h]
0x180015537  mov     rsp, r11
0x18001553a  pop     rbp
0x18001553b  retn
```
