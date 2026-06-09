# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180019d6c`
- end: `0x180019f98`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `556`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18000fe70`
- `0x180019ce8`

## callees

- `0x18000720c`
- `0x180011434`
- `0x180019d6c`
- `0x18001a0d4`
- `0x18001a0f4`
- `0x18001a208`
- `0x18001a2d8`
- `0x180046e50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180019e3d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180019eac`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180019e3d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180019eac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f3e`

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
0x180019d6c  mov     [rsp-8+arg_0], rbx
0x180019d71  mov     [rsp-8+arg_8], rsi
0x180019d76  push    rbp
0x180019d77  push    rdi
0x180019d78  push    r14
0x180019d7a  lea     rbp, [rsp-170h]
0x180019d82  sub     rsp, 270h
0x180019d89  mov     rax, cs:__security_cookie
0x180019d90  xor     rax, rsp
0x180019d93  mov     [rbp+180h+var_20], rax
0x180019d9a  xor     esi, esi
0x180019d9c  lea     rax, [rsp+280h+Name]
0x180019da1  mov     r14d, 104h
0x180019da7  mov     [r8], rsi
0x180019daa  mov     edx, r14d
0x180019dad  mov     rdi, r8
0x180019db0  mov     r9d, 7FFFFFFEh
0x180019db6  test    r9, r9
0x180019db9  jz      short loc_180019DDA
0x180019dbb  movzx   r8d, word ptr [rcx]
0x180019dbf  test    r8w, r8w
0x180019dc3  jz      short loc_180019DDA
0x180019dc5  mov     [rax], r8w
0x180019dc9  add     rcx, 2
0x180019dcd  add     rax, 2
0x180019dd1  dec     r9
0x180019dd4  sub     rdx, 1
0x180019dd8  jnz     short loc_180019DB6
0x180019dda  test    rdx, rdx
0x180019ddd  lea     rcx, [rax-2]
0x180019de1  mov     rdx, r14
0x180019de4  cmovnz  rcx, rax
0x180019de8  lea     rax, [rsp+280h+Name]
0x180019ded  mov     [rcx], si
0x180019df0  cmp     [rax], si
0x180019df3  jz      short loc_180019DFF
0x180019df5  add     rax, 2
0x180019df9  sub     rdx, 1
0x180019dfd  jnz     short loc_180019DF0
0x180019dff  mov     rcx, r14
0x180019e02  mov     rax, rdx
0x180019e05  sub     rcx, rdx
0x180019e08  neg     rax
0x180019e0b  sbb     r8, r8
0x180019e0e  and     r8, rcx; pcchNewDestLength
0x180019e11  test    rdx, rdx
0x180019e14  jz      short loc_180019E31
0x180019e16  mov     rdx, r14
0x180019e19  lea     rcx, [rsp+280h+Name]
0x180019e1e  sub     rdx, r8; cchDest
0x180019e21  lea     rcx, [rcx+r8*2]; pszDest
0x180019e25  lea     r9, aP0; "_p0"
0x180019e2c  call    StringCopyWorkerW
0x180019e31  lea     r8, [rsp+280h+Name]; lpName
0x180019e36  xor     edx, edx; bInheritHandle
0x180019e38  mov     ecx, 1F0003h; dwDesiredAccess
0x180019e3d  call    cs:__imp_OpenSemaphoreW
0x180019e43  mov     [rsp+280h+var_240], rax
0x180019e48  test    rax, rax
0x180019e4b  jz      loc_180019F3E
0x180019e51  lea     rdx, [rsp+280h+var_24C]; int *
0x180019e56  mov     [rsp+280h+var_24C], esi
0x180019e5a  mov     rcx, rax; hHandle
0x180019e5d  mov     [rsp+280h+var_250], esi
0x180019e61  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180019e66  mov     ebx, eax
0x180019e68  test    eax, eax
0x180019e6a  jns     short loc_180019E8C
0x180019e6c  mov     rcx, [rbp+188h]; this
0x180019e73  lea     r8, aWil; "wil"
0x180019e7a  mov     r9d, eax; char *
0x180019e7d  mov     edx, 0D6h; void *
0x180019e82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019e87  jmp     loc_180019F4B
0x180019e8c  lea     r8, asc_18004D874; "h"
0x180019e93  mov     rdx, r14; unsigned __int64
0x180019e96  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180019e9b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180019ea0  lea     r8, [rsp+280h+Name]; lpName
0x180019ea5  xor     edx, edx; bInheritHandle
0x180019ea7  mov     ecx, 1F0003h; dwDesiredAccess
0x180019eac  call    cs:__imp_OpenSemaphoreW
0x180019eb2  mov     [rsp+280h+var_248], rax
0x180019eb7  test    rax, rax
0x180019eba  jz      short loc_180019F18
0x180019ebc  lea     rdx, [rsp+280h+var_250]; int *
0x180019ec1  mov     rcx, rax; hHandle
0x180019ec4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180019ec9  mov     ebx, eax
0x180019ecb  test    eax, eax
0x180019ecd  jns     short loc_180019EEC
0x180019ecf  mov     rcx, [rbp+188h]; this
0x180019ed6  lea     r8, aWil; "wil"
0x180019edd  mov     r9d, eax; char *
0x180019ee0  mov     edx, 0DEh; void *
0x180019ee5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019eea  jmp     short loc_180019F32
0x180019eec  lea     rcx, [rsp+280h+var_248]
0x180019ef1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180019ef6  movsxd  rax, [rsp+280h+var_24C]
0x180019efb  movsxd  rcx, [rsp+280h+var_250]
0x180019f00  shl     rcx, 1Fh
0x180019f04  or      rcx, rax
0x180019f07  mov     [rdi], rcx
0x180019f0a  lea     rcx, [rsp+280h+var_240]
0x180019f0f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180019f14  xor     eax, eax
0x180019f16  jmp     short loc_180019F71
0x180019f18  mov     rcx, [rbp+188h]; this
0x180019f1f  lea     r8, aWil; "wil"
0x180019f26  mov     edx, 0DCh; void *
0x180019f2b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019f30  mov     ebx, eax
0x180019f32  lea     rcx, [rsp+280h+var_248]
0x180019f37  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180019f3c  jmp     short loc_180019F4B
0x180019f3e  call    cs:__imp_GetLastError
0x180019f44  cmp     eax, 2
0x180019f47  jnz     short loc_180019F59
0x180019f49  mov     ebx, esi
0x180019f4b  lea     rcx, [rsp+280h+var_240]
0x180019f50  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180019f55  mov     eax, ebx
0x180019f57  jmp     short loc_180019F71
0x180019f59  mov     rcx, [rbp+188h]; this
0x180019f60  lea     r8, aWil; "wil"
0x180019f67  mov     edx, 0D0h; void *
0x180019f6c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180019f71  mov     rcx, [rbp+180h+var_20]
0x180019f78  xor     rcx, rsp; StackCookie
0x180019f7b  call    __security_check_cookie
0x180019f80  lea     r11, [rsp+280h+var_10]
0x180019f88  mov     rbx, [r11+20h]
0x180019f8c  mov     rsi, [r11+28h]
0x180019f90  mov     rsp, r11
0x180019f93  pop     r14
0x180019f95  pop     rdi
0x180019f96  pop     rbp
0x180019f97  retn
```
