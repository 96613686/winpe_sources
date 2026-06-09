# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180031024`
- end: `0x1800311ce`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `426`
- prototype: `__int64 __fastcall(unsigned __int16 *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180030fa0`

## callees

- `0x180012be0`
- `0x18001d8e0`
- `0x1800290d4`
- `0x18002dec4`
- `0x18002f268`
- `0x1800307c4`
- `0x180030ba4`
- `0x180031024`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031098`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031098`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180031088`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003111f`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180031088`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18003111f`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        unsigned __int16 *a1,
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
  HANDLE v12; // rax
  unsigned int v13; // r8d
  const char *v14; // r9
  int v15; // eax
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v19; // [rsp+28h] [rbp-D8h] BYREF
  HANDLE v20[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v20[0] = v6;
  if ( v6 )
  {
    v18 = 0;
    v17 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v18);
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
    StringCchCatW(Name, v11, L"h");
    v12 = OpenSemaphoreW(0x1F0003u, 0, Name);
    v19 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v17);
      LastError = v15;
      if ( v15 >= 0 )
      {
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v19);
        *a3 = v18 | (unsigned __int64)((__int64)v17 << 31);
        goto LABEL_12;
      }
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, (int)"wil", (const char *)(unsigned int)v15);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v13, v14);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v7, v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v20);
  return LastError;
}

```

## disassembly

```asm
0x180031024  mov     [rsp-8+arg_8], rbx
0x180031029  mov     [rsp-8+arg_18], rdi
0x18003102e  push    rbp
0x18003102f  lea     rbp, [rsp-160h]
0x180031037  sub     rsp, 260h
0x18003103e  mov     rax, cs:__security_cookie
0x180031045  xor     rax, rsp
0x180031048  mov     [rbp+160h+var_10], rax
0x18003104f  mov     rdi, r8
0x180031052  mov     qword ptr [r8], 0
0x180031059  mov     r8, rcx; unsigned __int16 *
0x18003105c  mov     edx, 104h; unsigned __int64
0x180031061  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180031066  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003106b  lea     r8, aP0; "_p0"
0x180031072  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180031077  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18003107c  lea     r8, [rsp+260h+Name]; lpName
0x180031081  xor     edx, edx; bInheritHandle
0x180031083  mov     ecx, 1F0003h; dwDesiredAccess
0x180031088  call    cs:__imp_OpenSemaphoreW
0x18003108e  mov     [rsp+260h+var_230], rax
0x180031093  test    rax, rax
0x180031096  jnz     short loc_1800310BF
0x180031098  call    cs:__imp_GetLastError
0x18003109e  cmp     eax, 2
0x1800310a1  jz      loc_18003119C
0x1800310a7  mov     rcx, [rbp+168h]; this
0x1800310ae  mov     edx, 0D0h; void *
0x1800310b3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800310b8  mov     ebx, eax
0x1800310ba  jmp     loc_18003119E
0x1800310bf  lea     rdx, [rsp+260h+var_23C]; int *
0x1800310c4  mov     [rsp+260h+var_23C], 0
0x1800310cc  mov     rcx, rax; hHandle
0x1800310cf  mov     [rsp+260h+var_240], 0; int
0x1800310d7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800310dc  mov     ebx, eax
0x1800310de  test    eax, eax
0x1800310e0  jns     short loc_180031102
0x1800310e2  mov     rcx, [rbp+168h]; this
0x1800310e9  lea     r8, aWil; "wil"
0x1800310f0  mov     r9d, eax; char *
0x1800310f3  mov     edx, 0D6h; void *
0x1800310f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800310fd  jmp     loc_18003119E
0x180031102  lea     r8, asc_180044B10; "h"
0x180031109  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x18003110e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180031113  lea     r8, [rsp+260h+Name]; lpName
0x180031118  xor     edx, edx; bInheritHandle
0x18003111a  mov     ecx, 1F0003h; dwDesiredAccess
0x18003111f  call    cs:__imp_OpenSemaphoreW
0x180031125  mov     [rsp+260h+var_238], rax
0x18003112a  test    rax, rax
0x18003112d  jnz     short loc_18003114E
0x18003112f  mov     rcx, [rbp+168h]; this
0x180031136  mov     edx, 0DCh; void *
0x18003113b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180031140  mov     ebx, eax
0x180031142  lea     rcx, [rsp+260h+var_238]
0x180031147  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003114c  jmp     short loc_18003119E
0x18003114e  lea     rdx, [rsp+260h+var_240]; int *
0x180031153  mov     rcx, rax; hHandle
0x180031156  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18003115b  mov     ebx, eax
0x18003115d  test    eax, eax
0x18003115f  jns     short loc_18003117E
0x180031161  mov     rcx, [rbp+168h]; this
0x180031168  lea     r8, aWil; "wil"
0x18003116f  mov     r9d, eax; char *
0x180031172  mov     edx, 0DEh; void *
0x180031177  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003117c  jmp     short loc_180031142
0x18003117e  lea     rcx, [rsp+260h+var_238]
0x180031183  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180031188  movsxd  rcx, [rsp+260h+var_240]
0x18003118d  movsxd  rax, [rsp+260h+var_23C]
0x180031192  shl     rcx, 1Fh
0x180031196  or      rcx, rax
0x180031199  mov     [rdi], rcx
0x18003119c  xor     ebx, ebx
0x18003119e  lea     rcx, [rsp+260h+var_230]
0x1800311a3  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800311a8  mov     eax, ebx
0x1800311aa  mov     rcx, [rbp+160h+var_10]
0x1800311b1  xor     rcx, rsp; StackCookie
0x1800311b4  call    __security_check_cookie
0x1800311b9  lea     r11, [rsp+260h+var_s0]
0x1800311c1  mov     rbx, [r11+18h]
0x1800311c5  mov     rdi, [r11+28h]
0x1800311c9  mov     rsp, r11
0x1800311cc  pop     rbp
0x1800311cd  retn
```
