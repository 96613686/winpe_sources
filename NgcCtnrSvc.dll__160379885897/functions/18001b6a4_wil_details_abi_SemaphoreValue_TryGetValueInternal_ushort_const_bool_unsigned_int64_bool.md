# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18001b6a4`
- end: `0x18001b8e3`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `575`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18003138c`

## callees

- `0x18000c920`
- `0x1800191d8`
- `0x18001b6a4`
- `0x180022510`
- `0x180022e68`
- `0x180023278`
- `0x1800257e8`
- `0x18002c640`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001b775`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001b7ea`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001b775`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18001b7ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b882`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b882`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // rdx
  __int64 v7; // r9
  bool v8; // zf
  WCHAR *v9; // rcx
  __int64 v10; // rdx
  WCHAR *v11; // rax
  __int64 v12; // r8
  HANDLE v13; // rax
  int ValueFromSemaphore; // eax
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
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

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
  v8 = v5 == 0;
  v9 = v4 - 1;
  v10 = 260;
  if ( !v8 )
    v9 = v4;
  v11 = Name;
  *v9 = 0;
  do
  {
    if ( !*v11 )
      break;
    ++v11;
    --v10;
  }
  while ( v10 );
  if ( v10 )
  {
    v12 = (260 - v10) & -(__int64)(v10 != 0);
    StringCopyWorkerW(&Name[v12], 260 - v12, (size_t *)v12, L"_p0", v21);
  }
  v13 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v25[0] = v13;
  if ( v13 )
  {
    v23 = 0;
    v22 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v23);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      StringCchCatW(Name, 0x104u, L"h");
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
0x18001b6a4  mov     [rsp-8+arg_0], rbx
0x18001b6a9  mov     [rsp-8+arg_8], rsi
0x18001b6ae  push    rbp
0x18001b6af  push    rdi
0x18001b6b0  push    r14
0x18001b6b2  lea     rbp, [rsp-170h]
0x18001b6ba  sub     rsp, 270h
0x18001b6c1  mov     rax, cs:__security_cookie
0x18001b6c8  xor     rax, rsp
0x18001b6cb  mov     [rbp+180h+var_20], rax
0x18001b6d2  xor     esi, esi
0x18001b6d4  lea     rax, [rsp+280h+Name]
0x18001b6d9  mov     r14d, 104h
0x18001b6df  mov     [r8], rsi
0x18001b6e2  mov     edx, r14d
0x18001b6e5  mov     rdi, r8
0x18001b6e8  mov     r9d, 7FFFFFFEh
0x18001b6ee  test    r9, r9
0x18001b6f1  jz      short loc_18001B712
0x18001b6f3  movzx   r8d, word ptr [rcx]
0x18001b6f7  test    r8w, r8w
0x18001b6fb  jz      short loc_18001B712
0x18001b6fd  mov     [rax], r8w
0x18001b701  add     rcx, 2
0x18001b705  add     rax, 2
0x18001b709  dec     r9
0x18001b70c  sub     rdx, 1
0x18001b710  jnz     short loc_18001B6EE
0x18001b712  test    rdx, rdx
0x18001b715  lea     rcx, [rax-2]
0x18001b719  mov     rdx, r14
0x18001b71c  cmovnz  rcx, rax
0x18001b720  lea     rax, [rsp+280h+Name]
0x18001b725  mov     [rcx], si
0x18001b728  cmp     [rax], si
0x18001b72b  jz      short loc_18001B737
0x18001b72d  add     rax, 2
0x18001b731  sub     rdx, 1
0x18001b735  jnz     short loc_18001B728
0x18001b737  mov     rcx, r14
0x18001b73a  mov     rax, rdx
0x18001b73d  sub     rcx, rdx
0x18001b740  neg     rax
0x18001b743  sbb     r8, r8
0x18001b746  and     r8, rcx; pcchNewDestLength
0x18001b749  test    rdx, rdx
0x18001b74c  jz      short loc_18001B769
0x18001b74e  mov     rdx, r14
0x18001b751  lea     rcx, [rsp+280h+Name]
0x18001b756  sub     rdx, r8; cchDest
0x18001b759  lea     rcx, [rcx+r8*2]; pszDest
0x18001b75d  lea     r9, aP0; "_p0"
0x18001b764  call    StringCopyWorkerW
0x18001b769  lea     r8, [rsp+280h+Name]; lpName
0x18001b76e  xor     edx, edx; bInheritHandle
0x18001b770  mov     ecx, 1F0003h; dwDesiredAccess
0x18001b775  call    cs:__imp_OpenSemaphoreW
0x18001b77c  nop     dword ptr [rax+rax+00h]
0x18001b781  mov     [rsp+280h+var_240], rax
0x18001b786  test    rax, rax
0x18001b789  jz      loc_18001B882
0x18001b78f  lea     rdx, [rsp+280h+var_24C]; int *
0x18001b794  mov     [rsp+280h+var_24C], esi
0x18001b798  mov     rcx, rax; hHandle
0x18001b79b  mov     [rsp+280h+var_250], esi
0x18001b79f  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001b7a4  mov     ebx, eax
0x18001b7a6  test    eax, eax
0x18001b7a8  jns     short loc_18001B7CA
0x18001b7aa  mov     rcx, [rbp+188h]; this
0x18001b7b1  lea     r8, aWil; "wil"
0x18001b7b8  mov     r9d, eax; char *
0x18001b7bb  mov     edx, 0D6h; void *
0x18001b7c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b7c5  jmp     loc_18001B895
0x18001b7ca  lea     r8, asc_180091310; "h"
0x18001b7d1  mov     rdx, r14; unsigned __int64
0x18001b7d4  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x18001b7d9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001b7de  lea     r8, [rsp+280h+Name]; lpName
0x18001b7e3  xor     edx, edx; bInheritHandle
0x18001b7e5  mov     ecx, 1F0003h; dwDesiredAccess
0x18001b7ea  call    cs:__imp_OpenSemaphoreW
0x18001b7f1  nop     dword ptr [rax+rax+00h]
0x18001b7f6  mov     [rsp+280h+var_248], rax
0x18001b7fb  test    rax, rax
0x18001b7fe  jz      short loc_18001B85C
0x18001b800  lea     rdx, [rsp+280h+var_250]; int *
0x18001b805  mov     rcx, rax; hHandle
0x18001b808  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18001b80d  mov     ebx, eax
0x18001b80f  test    eax, eax
0x18001b811  jns     short loc_18001B830
0x18001b813  mov     rcx, [rbp+188h]; this
0x18001b81a  lea     r8, aWil; "wil"
0x18001b821  mov     r9d, eax; char *
0x18001b824  mov     edx, 0DEh; void *
0x18001b829  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001b82e  jmp     short loc_18001B876
0x18001b830  lea     rcx, [rsp+280h+var_248]
0x18001b835  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001b83a  movsxd  rax, [rsp+280h+var_24C]
0x18001b83f  movsxd  rcx, [rsp+280h+var_250]
0x18001b844  shl     rcx, 1Fh
0x18001b848  or      rcx, rax
0x18001b84b  mov     [rdi], rcx
0x18001b84e  lea     rcx, [rsp+280h+var_240]
0x18001b853  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001b858  xor     eax, eax
0x18001b85a  jmp     short loc_18001B8BB
0x18001b85c  mov     rcx, [rbp+188h]; this
0x18001b863  lea     r8, aWil; "wil"
0x18001b86a  mov     edx, 0DCh; void *
0x18001b86f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001b874  mov     ebx, eax
0x18001b876  lea     rcx, [rsp+280h+var_248]
0x18001b87b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001b880  jmp     short loc_18001B895
0x18001b882  call    cs:__imp_GetLastError
0x18001b889  nop     dword ptr [rax+rax+00h]
0x18001b88e  cmp     eax, 2
0x18001b891  jnz     short loc_18001B8A3
0x18001b893  mov     ebx, esi
0x18001b895  lea     rcx, [rsp+280h+var_240]
0x18001b89a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001b89f  mov     eax, ebx
0x18001b8a1  jmp     short loc_18001B8BB
0x18001b8a3  mov     rcx, [rbp+188h]; this
0x18001b8aa  lea     r8, aWil; "wil"
0x18001b8b1  mov     edx, 0D0h; void *
0x18001b8b6  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001b8bb  mov     rcx, [rbp+180h+var_20]
0x18001b8c2  xor     rcx, rsp; StackCookie
0x18001b8c5  call    __security_check_cookie
0x18001b8ca  lea     r11, [rsp+280h+var_10]
0x18001b8d2  mov     rbx, [r11+20h]
0x18001b8d6  mov     rsi, [r11+28h]
0x18001b8da  mov     rsp, r11
0x18001b8dd  pop     r14
0x18001b8df  pop     rdi
0x18001b8e0  pop     rbp
0x18001b8e1  retn
```
