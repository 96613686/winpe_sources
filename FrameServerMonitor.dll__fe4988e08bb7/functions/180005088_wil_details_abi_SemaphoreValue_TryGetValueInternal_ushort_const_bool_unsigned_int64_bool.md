# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180005088`
- end: `0x180005240`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `440`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180003314`

## callees

- `0x1800019f0`
- `0x180003194`
- `0x180003fb0`
- `0x180004bb0`
- `0x180004bd0`
- `0x180004e50`
- `0x180004f34`
- `0x180005088`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800050ec`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000518a`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800050ec`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000518a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050fc`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  unsigned __int64 v5; // rdx
  wil::details *v6; // rax
  void *v7; // rdx
  const char *v8; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  unsigned __int64 v11; // rdx
  wil::details *v12; // rax
  const char *v13; // r9
  void *v14; // rdx
  int v15; // eax
  void *v16; // rdx
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v20; // [rsp+28h] [rbp-D8h] BYREF
  wil::details *v21; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+268h] [rbp+168h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  StringCchCatW(Name, v5, L"_p0");
  v6 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v21 = v6;
  if ( v6 )
  {
    v19 = 0;
    v18 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v6, &v19);
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
    StringCchCatW(Name, v11, L"h");
    v12 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v20 = v12;
    if ( v12 )
    {
      v15 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v18);
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
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v13);
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
  LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v8);
LABEL_13:
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
    &v21,
    v7);
  return LastError;
}

```

## disassembly

```asm
0x180005088  mov     [rsp-8+arg_8], rbx
0x18000508d  mov     [rsp-8+arg_18], rdi
0x180005092  push    rbp
0x180005093  lea     rbp, [rsp-160h]
0x18000509b  sub     rsp, 260h
0x1800050a2  mov     rax, cs:__security_cookie
0x1800050a9  xor     rax, rsp
0x1800050ac  mov     [rbp+160h+var_10], rax
0x1800050b3  mov     rdi, r8
0x1800050b6  mov     qword ptr [r8], 0
0x1800050bd  mov     r8, rcx; unsigned __int16 *
0x1800050c0  mov     edx, 104h; unsigned __int64
0x1800050c5  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800050ca  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800050cf  lea     r8, aP0; "_p0"
0x1800050d6  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x1800050db  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800050e0  lea     r8, [rsp+260h+Name]; lpName
0x1800050e5  xor     edx, edx; bInheritHandle
0x1800050e7  mov     ecx, 1F0003h; dwDesiredAccess
0x1800050ec  call    cs:__imp_OpenSemaphoreW
0x1800050f2  mov     [rsp+260h+var_230], rax
0x1800050f7  test    rax, rax
0x1800050fa  jnz     short loc_18000512A
0x1800050fc  call    cs:__imp_GetLastError
0x180005102  cmp     eax, 2
0x180005105  jz      loc_18000520E
0x18000510b  mov     rcx, [rbp+168h]; this
0x180005112  lea     r8, aWil; "wil"
0x180005119  mov     edx, 0D0h; void *
0x18000511e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005123  mov     ebx, eax
0x180005125  jmp     loc_180005210
0x18000512a  lea     rdx, [rsp+260h+var_23C]; int *
0x18000512f  mov     [rsp+260h+var_23C], 0
0x180005137  mov     rcx, rax; hHandle
0x18000513a  mov     [rsp+260h+var_240], 0; int
0x180005142  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180005147  mov     ebx, eax
0x180005149  test    eax, eax
0x18000514b  jns     short loc_18000516D
0x18000514d  mov     rcx, [rbp+168h]; this
0x180005154  lea     r8, aWil; "wil"
0x18000515b  mov     r9d, eax; char *
0x18000515e  mov     edx, 0D6h; void *
0x180005163  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005168  jmp     loc_180005210
0x18000516d  lea     r8, asc_180051D68; "h"
0x180005174  lea     rcx, [rsp+260h+Name]; unsigned __int16 *
0x180005179  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000517e  lea     r8, [rsp+260h+Name]; lpName
0x180005183  xor     edx, edx; bInheritHandle
0x180005185  mov     ecx, 1F0003h; dwDesiredAccess
0x18000518a  call    cs:__imp_OpenSemaphoreW
0x180005190  mov     [rsp+260h+var_238], rax
0x180005195  test    rax, rax
0x180005198  jnz     short loc_1800051C0
0x18000519a  mov     rcx, [rbp+168h]; this
0x1800051a1  lea     r8, aWil; "wil"
0x1800051a8  mov     edx, 0DCh; void *
0x1800051ad  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800051b2  mov     ebx, eax
0x1800051b4  lea     rcx, [rsp+260h+var_238]
0x1800051b9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800051be  jmp     short loc_180005210
0x1800051c0  lea     rdx, [rsp+260h+var_240]; int *
0x1800051c5  mov     rcx, rax; hHandle
0x1800051c8  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x1800051cd  mov     ebx, eax
0x1800051cf  test    eax, eax
0x1800051d1  jns     short loc_1800051F0
0x1800051d3  mov     rcx, [rbp+168h]; this
0x1800051da  lea     r8, aWil; "wil"
0x1800051e1  mov     r9d, eax; char *
0x1800051e4  mov     edx, 0DEh; void *
0x1800051e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800051ee  jmp     short loc_1800051B4
0x1800051f0  lea     rcx, [rsp+260h+var_238]
0x1800051f5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800051fa  movsxd  rcx, [rsp+260h+var_240]
0x1800051ff  movsxd  rax, [rsp+260h+var_23C]
0x180005204  shl     rcx, 1Fh
0x180005208  or      rcx, rax
0x18000520b  mov     [rdi], rcx
0x18000520e  xor     ebx, ebx
0x180005210  lea     rcx, [rsp+260h+var_230]
0x180005215  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000521a  mov     eax, ebx
0x18000521c  mov     rcx, [rbp+160h+var_10]
0x180005223  xor     rcx, rsp; StackCookie
0x180005226  call    __security_check_cookie
0x18000522b  lea     r11, [rsp+260h+var_s0]
0x180005233  mov     rbx, [r11+18h]
0x180005237  mov     rdi, [r11+28h]
0x18000523b  mov     rsp, r11
0x18000523e  pop     rbp
0x18000523f  retn
```
