# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18002b398`
- end: `0x18002b609`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `625`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18001ab80`
- `0x18002b144`

## callees

- `0x18000dcc0`
- `0x18002b1c8`
- `0x18002b1f0`
- `0x18002b398`
- `0x18002b610`
- `0x18002ba04`
- `0x180034070`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002b49b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002b510`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002b49b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18002b510`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b5a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b5a8`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // r10
  __int64 v6; // r9
  __int64 v7; // rdx
  bool v9; // zf
  WCHAR *v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // rax
  __int64 v13; // r8
  const unsigned __int16 *v14; // rcx
  WCHAR *v15; // rdx
  __int64 v16; // rax
  WCHAR *v17; // rcx
  HANDLE v18; // rax
  int ValueFromSemaphore; // eax
  unsigned int LastError; // ebx
  HANDLE v21; // rax
  const char *v22; // r9
  int v23; // eax
  const char *v25; // r9
  int v26; // [rsp+20h] [rbp-E0h] BYREF
  int v27; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v28; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v29[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  v4 = Name;
  v5 = 2147483646;
  *a3 = 0;
  v6 = 2147483646;
  v7 = 260;
  do
  {
    if ( !v6 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v6;
    --v7;
  }
  while ( v7 );
  v9 = v7 == 0;
  v10 = v4 - 1;
  v11 = 260;
  if ( !v9 )
    v10 = v4;
  v12 = Name;
  *v10 = 0;
  do
  {
    if ( !*v12 )
      break;
    ++v12;
    --v11;
  }
  while ( v11 );
  v13 = (260 - v11) & -(__int64)(v11 != 0);
  if ( v11 )
  {
    v14 = L"_p0";
    v15 = &Name[v13];
    v16 = 260 - v13;
    if ( v13 != 260 )
    {
      do
      {
        if ( !v5 )
          break;
        if ( !*v14 )
          break;
        *v15++ = *v14++;
        --v5;
        --v16;
      }
      while ( v16 );
    }
    v17 = v15 - 1;
    if ( v16 )
      v17 = v15;
    *v17 = 0;
  }
  v18 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v29[0] = v18;
  if ( v18 )
  {
    v27 = 0;
    v26 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v27);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      StringCchCatW(Name, 0x104u, L"h");
      v21 = OpenSemaphoreW(0x1F0003u, 0, Name);
      v28 = v21;
      if ( v21 )
      {
        v23 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v21, &v26);
        LastError = v23;
        if ( v23 >= 0 )
        {
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v28);
          *a3 = v27 | (unsigned __int64)((__int64)v26 << 31);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v29);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"wil",
          (const char *)(unsigned int)v23,
          v26);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v22);
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v28);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v26);
    }
    goto LABEL_29;
  }
  if ( GetLastError() == 2 )
  {
    LastError = 0;
LABEL_29:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v29);
    return LastError;
  }
  return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v25);
}

```

## disassembly

```asm
0x18002b398  mov     [rsp-8+arg_0], rbx
0x18002b39d  mov     [rsp-8+arg_8], rsi
0x18002b3a2  push    rbp
0x18002b3a3  push    rdi
0x18002b3a4  push    r15
0x18002b3a6  lea     rbp, [rsp-160h]
0x18002b3ae  sub     rsp, 260h
0x18002b3b5  mov     rax, cs:__security_cookie
0x18002b3bc  xor     rax, rsp
0x18002b3bf  mov     [rbp+170h+var_20], rax
0x18002b3c6  xor     esi, esi
0x18002b3c8  lea     rax, [rsp+270h+Name]
0x18002b3cd  mov     r10d, 7FFFFFFEh
0x18002b3d3  mov     [r8], rsi
0x18002b3d6  mov     r15d, 104h
0x18002b3dc  mov     r9d, r10d
0x18002b3df  mov     edx, r15d
0x18002b3e2  mov     rdi, r8
0x18002b3e5  test    r9, r9
0x18002b3e8  jz      short loc_18002B409
0x18002b3ea  movzx   r8d, word ptr [rcx]
0x18002b3ee  test    r8w, r8w
0x18002b3f2  jz      short loc_18002B409
0x18002b3f4  mov     [rax], r8w
0x18002b3f8  add     rcx, 2
0x18002b3fc  add     rax, 2
0x18002b400  dec     r9
0x18002b403  sub     rdx, 1
0x18002b407  jnz     short loc_18002B3E5
0x18002b409  test    rdx, rdx
0x18002b40c  lea     rcx, [rax-2]
0x18002b410  mov     rdx, r15
0x18002b413  cmovnz  rcx, rax
0x18002b417  lea     rax, [rsp+270h+Name]
0x18002b41c  mov     [rcx], si
0x18002b41f  cmp     [rax], si
0x18002b422  jz      short loc_18002B42E
0x18002b424  add     rax, 2
0x18002b428  sub     rdx, 1
0x18002b42c  jnz     short loc_18002B41F
0x18002b42e  mov     rcx, r15
0x18002b431  mov     rax, rdx
0x18002b434  sub     rcx, rdx
0x18002b437  neg     rax
0x18002b43a  sbb     r8, r8
0x18002b43d  and     r8, rcx
0x18002b440  test    rdx, rdx
0x18002b443  jz      short loc_18002B48F
0x18002b445  mov     rax, r15
0x18002b448  lea     rdx, [rsp+270h+Name]
0x18002b44d  lea     rcx, aP0; "_p0"
0x18002b454  lea     rdx, [rdx+r8*2]
0x18002b458  sub     rax, r8
0x18002b45b  jz      short loc_18002B481
0x18002b45d  test    r10, r10
0x18002b460  jz      short loc_18002B481
0x18002b462  movzx   r8d, word ptr [rcx]
0x18002b466  test    r8w, r8w
0x18002b46a  jz      short loc_18002B481
0x18002b46c  mov     [rdx], r8w
0x18002b470  add     rcx, 2
0x18002b474  add     rdx, 2
0x18002b478  dec     r10
0x18002b47b  sub     rax, 1
0x18002b47f  jnz     short loc_18002B45D
0x18002b481  test    rax, rax
0x18002b484  lea     rcx, [rdx-2]
0x18002b488  cmovnz  rcx, rdx
0x18002b48c  mov     [rcx], si
0x18002b48f  lea     r8, [rsp+270h+Name]; lpName
0x18002b494  xor     edx, edx; bInheritHandle
0x18002b496  mov     ecx, 1F0003h; dwDesiredAccess
0x18002b49b  call    cs:__imp_OpenSemaphoreW
0x18002b4a2  nop     dword ptr [rax+rax+00h]
0x18002b4a7  mov     [rsp+270h+var_240], rax
0x18002b4ac  test    rax, rax
0x18002b4af  jz      loc_18002B5A8
0x18002b4b5  lea     rdx, [rsp+270h+var_24C]; int *
0x18002b4ba  mov     [rsp+270h+var_24C], esi
0x18002b4be  mov     rcx, rax; hHandle
0x18002b4c1  mov     [rsp+270h+var_250], esi; int
0x18002b4c5  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002b4ca  mov     ebx, eax
0x18002b4cc  test    eax, eax
0x18002b4ce  jns     short loc_18002B4F0
0x18002b4d0  mov     rcx, [rbp+178h]; this
0x18002b4d7  lea     r8, aWil; "wil"
0x18002b4de  mov     r9d, eax; char *
0x18002b4e1  mov     edx, 0D6h; void *
0x18002b4e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b4eb  jmp     loc_18002B5BB
0x18002b4f0  lea     r8, asc_180086470; "h"
0x18002b4f7  mov     rdx, r15; unsigned __int64
0x18002b4fa  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18002b4ff  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002b504  lea     r8, [rsp+270h+Name]; lpName
0x18002b509  xor     edx, edx; bInheritHandle
0x18002b50b  mov     ecx, 1F0003h; dwDesiredAccess
0x18002b510  call    cs:__imp_OpenSemaphoreW
0x18002b517  nop     dword ptr [rax+rax+00h]
0x18002b51c  mov     [rsp+270h+var_248], rax
0x18002b521  test    rax, rax
0x18002b524  jz      short loc_18002B582
0x18002b526  lea     rdx, [rsp+270h+var_250]; int *
0x18002b52b  mov     rcx, rax; hHandle
0x18002b52e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002b533  mov     ebx, eax
0x18002b535  test    eax, eax
0x18002b537  jns     short loc_18002B556
0x18002b539  mov     rcx, [rbp+178h]; this
0x18002b540  lea     r8, aWil; "wil"
0x18002b547  mov     r9d, eax; char *
0x18002b54a  mov     edx, 0DEh; void *
0x18002b54f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b554  jmp     short loc_18002B59C
0x18002b556  lea     rcx, [rsp+270h+var_248]
0x18002b55b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002b560  movsxd  rax, [rsp+270h+var_24C]
0x18002b565  movsxd  rcx, [rsp+270h+var_250]
0x18002b56a  shl     rcx, 1Fh
0x18002b56e  or      rcx, rax
0x18002b571  mov     [rdi], rcx
0x18002b574  lea     rcx, [rsp+270h+var_240]
0x18002b579  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002b57e  xor     eax, eax
0x18002b580  jmp     short loc_18002B5E1
0x18002b582  mov     rcx, [rbp+178h]; this
0x18002b589  lea     r8, aWil; "wil"
0x18002b590  mov     edx, 0DCh; void *
0x18002b595  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002b59a  mov     ebx, eax
0x18002b59c  lea     rcx, [rsp+270h+var_248]
0x18002b5a1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002b5a6  jmp     short loc_18002B5BB
0x18002b5a8  call    cs:__imp_GetLastError
0x18002b5af  nop     dword ptr [rax+rax+00h]
0x18002b5b4  cmp     eax, 2
0x18002b5b7  jnz     short loc_18002B5C9
0x18002b5b9  mov     ebx, esi
0x18002b5bb  lea     rcx, [rsp+270h+var_240]
0x18002b5c0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002b5c5  mov     eax, ebx
0x18002b5c7  jmp     short loc_18002B5E1
0x18002b5c9  mov     rcx, [rbp+178h]; this
0x18002b5d0  lea     r8, aWil; "wil"
0x18002b5d7  mov     edx, 0D0h; void *
0x18002b5dc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002b5e1  mov     rcx, [rbp+170h+var_20]
0x18002b5e8  xor     rcx, rsp; StackCookie
0x18002b5eb  call    __security_check_cookie
0x18002b5f0  lea     r11, [rsp+270h+var_10]
0x18002b5f8  mov     rbx, [r11+20h]
0x18002b5fc  mov     rsi, [r11+28h]
0x18002b600  mov     rsp, r11
0x18002b603  pop     r15
0x18002b605  pop     rdi
0x18002b606  pop     rbp
0x18002b607  retn
```
