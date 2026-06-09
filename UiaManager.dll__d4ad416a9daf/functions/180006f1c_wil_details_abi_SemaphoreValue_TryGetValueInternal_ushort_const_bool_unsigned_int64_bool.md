# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180006f1c`
- end: `0x18000712c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `528`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180006b58`
- `0x18002bda4`

## callees

- `0x180006edc`
- `0x180006f00`
- `0x180006f1c`
- `0x180012838`
- `0x180024f38`
- `0x18002b810`
- `0x18002b908`
- `0x180043680`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006fe0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000704c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180006fe0`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000704c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800070de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800070de`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // r9
  __int64 v7; // r10
  WCHAR *v8; // rcx
  __int64 v9; // r8
  WCHAR *v10; // rax
  __int64 v11; // r9
  HANDLE v12; // rax
  int ValueFromSemaphore; // eax
  unsigned __int64 v14; // rdx
  unsigned int LastError; // ebx
  HANDLE v16; // rax
  const char *v17; // r9
  int v18; // eax
  const char *v20; // r9
  size_t v21; // [rsp+20h] [rbp-E0h]
  int v22; // [rsp+30h] [rbp-D0h] BYREF
  int v23; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v24; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v25[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+198h]

  v4 = Name;
  *a3 = 0;
  v5 = 260;
  v7 = 2147483646;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v5;
  }
  while ( v5 );
  v8 = v4 - 1;
  v9 = 260;
  if ( v5 )
    v8 = v4;
  v10 = Name;
  *v8 = 0;
  do
  {
    if ( !*v10 )
      break;
    ++v10;
    --v9;
  }
  while ( v9 );
  if ( v9 )
  {
    v11 = (260 - v9) & -(__int64)(v9 != 0);
    StringCopyWorkerW(&Name[v11], 260 - v11, (size_t *)v9, L"_p0", v21);
  }
  v12 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v25[0] = v12;
  if ( v12 )
  {
    v23 = 0;
    v22 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v12, &v23);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      StringCchCatW(Name, v14, L"h");
      v16 = OpenSemaphoreW(0x1F0003u, 0, Name);
      v24 = v16;
      if ( v16 )
      {
        v18 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v16, &v22);
        LastError = v18;
        if ( v18 >= 0 )
        {
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
          *a3 = v23 | (unsigned __int64)((__int64)v22 << 31);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v25);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"wil",
          (const char *)(unsigned int)v18,
          v21);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v17);
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v24);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v21);
    }
    goto LABEL_23;
  }
  if ( GetLastError() == 2 )
  {
    LastError = 0;
LABEL_23:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v25);
    return LastError;
  }
  return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v20);
}

```

## disassembly

```asm
0x180006f1c  push    rbp
0x180006f1e  push    rbx
0x180006f1f  push    rsi
0x180006f20  push    rdi
0x180006f21  lea     rbp, [rsp-178h]
0x180006f29  sub     rsp, 278h
0x180006f30  mov     rax, cs:__security_cookie
0x180006f37  xor     rax, rsp
0x180006f3a  mov     [rbp+190h+var_30], rax
0x180006f41  xor     esi, esi
0x180006f43  lea     rax, [rsp+290h+Name]
0x180006f48  mov     edx, 104h
0x180006f4d  mov     [r8], rsi
0x180006f50  mov     r9d, edx
0x180006f53  mov     rdi, r8
0x180006f56  mov     r10d, 7FFFFFFEh
0x180006f5c  test    r10, r10
0x180006f5f  jz      short loc_180006F80
0x180006f61  movzx   r8d, word ptr [rcx]
0x180006f65  test    r8w, r8w
0x180006f69  jz      short loc_180006F80
0x180006f6b  mov     [rax], r8w
0x180006f6f  add     rcx, 2
0x180006f73  add     rax, 2
0x180006f77  dec     r10
0x180006f7a  sub     r9, 1
0x180006f7e  jnz     short loc_180006F5C
0x180006f80  lea     rcx, [rax-2]
0x180006f84  test    r9, r9
0x180006f87  mov     r8, rdx
0x180006f8a  cmovnz  rcx, rax
0x180006f8e  lea     rax, [rsp+290h+Name]
0x180006f93  mov     [rcx], si
0x180006f96  cmp     [rax], si
0x180006f99  jz      short loc_180006FA5
0x180006f9b  add     rax, 2
0x180006f9f  sub     r8, 1; pcchNewDestLength
0x180006fa3  jnz     short loc_180006F96
0x180006fa5  mov     rcx, rdx
0x180006fa8  mov     rax, r8
0x180006fab  sub     rcx, r8
0x180006fae  neg     rax
0x180006fb1  sbb     r9, r9
0x180006fb4  and     r9, rcx
0x180006fb7  test    r8, r8
0x180006fba  jz      short loc_180006FD4
0x180006fbc  sub     rdx, r9; cchDest
0x180006fbf  lea     rcx, [rsp+290h+Name]
0x180006fc4  lea     rcx, [rcx+r9*2]; pszDest
0x180006fc8  lea     r9, aP0; "_p0"
0x180006fcf  call    StringCopyWorkerW
0x180006fd4  lea     r8, [rsp+290h+Name]; lpName
0x180006fd9  xor     edx, edx; bInheritHandle
0x180006fdb  mov     ecx, 1F0003h; dwDesiredAccess
0x180006fe0  call    cs:__imp_OpenSemaphoreW
0x180006fe6  mov     [rsp+290h+var_250], rax
0x180006feb  test    rax, rax
0x180006fee  jz      loc_1800070DE
0x180006ff4  lea     rdx, [rsp+290h+var_25C]; int *
0x180006ff9  mov     [rsp+290h+var_25C], esi
0x180006ffd  mov     rcx, rax; hHandle
0x180007000  mov     [rsp+290h+var_260], esi
0x180007004  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007009  mov     ebx, eax
0x18000700b  test    eax, eax
0x18000700d  jns     short loc_18000702F
0x18000700f  mov     rcx, [rbp+198h]; this
0x180007016  lea     r8, aWil; "wil"
0x18000701d  mov     r9d, eax; char *
0x180007020  mov     edx, 0D6h; void *
0x180007025  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000702a  jmp     loc_1800070EB
0x18000702f  lea     r8, asc_1800A2350; "h"
0x180007036  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18000703b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180007040  lea     r8, [rsp+290h+Name]; lpName
0x180007045  xor     edx, edx; bInheritHandle
0x180007047  mov     ecx, 1F0003h; dwDesiredAccess
0x18000704c  call    cs:__imp_OpenSemaphoreW
0x180007052  mov     [rsp+290h+var_258], rax
0x180007057  test    rax, rax
0x18000705a  jz      short loc_1800070B8
0x18000705c  lea     rdx, [rsp+290h+var_260]; int *
0x180007061  mov     rcx, rax; hHandle
0x180007064  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180007069  mov     ebx, eax
0x18000706b  test    eax, eax
0x18000706d  jns     short loc_18000708C
0x18000706f  mov     rcx, [rbp+198h]; this
0x180007076  lea     r8, aWil; "wil"
0x18000707d  mov     r9d, eax; char *
0x180007080  mov     edx, 0DEh; void *
0x180007085  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000708a  jmp     short loc_1800070D2
0x18000708c  lea     rcx, [rsp+290h+var_258]
0x180007091  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180007096  movsxd  rax, [rsp+290h+var_25C]
0x18000709b  movsxd  rcx, [rsp+290h+var_260]
0x1800070a0  shl     rcx, 1Fh
0x1800070a4  or      rcx, rax
0x1800070a7  mov     [rdi], rcx
0x1800070aa  lea     rcx, [rsp+290h+var_250]
0x1800070af  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800070b4  xor     eax, eax
0x1800070b6  jmp     short loc_180007111
0x1800070b8  mov     rcx, [rbp+198h]; this
0x1800070bf  lea     r8, aWil; "wil"
0x1800070c6  mov     edx, 0DCh; void *
0x1800070cb  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800070d0  mov     ebx, eax
0x1800070d2  lea     rcx, [rsp+290h+var_258]
0x1800070d7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800070dc  jmp     short loc_1800070EB
0x1800070de  call    cs:__imp_GetLastError
0x1800070e4  cmp     eax, 2
0x1800070e7  jnz     short loc_1800070F9
0x1800070e9  mov     ebx, esi
0x1800070eb  lea     rcx, [rsp+290h+var_250]
0x1800070f0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800070f5  mov     eax, ebx
0x1800070f7  jmp     short loc_180007111
0x1800070f9  mov     rcx, [rbp+198h]; this
0x180007100  lea     r8, aWil; "wil"
0x180007107  mov     edx, 0D0h; void *
0x18000710c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180007111  mov     rcx, [rbp+190h+var_30]
0x180007118  xor     rcx, rsp; StackCookie
0x18000711b  call    __security_check_cookie
0x180007120  add     rsp, 278h
0x180007127  pop     rdi
0x180007128  pop     rsi
0x180007129  pop     rbx
0x18000712a  pop     rbp
0x18000712b  retn
```
