# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18004bf68`
- end: `0x18004c1e1`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `633`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18004bd54`
- `0x18006b720`

## callees

- `0x18000f858`
- `0x1800133c4`
- `0x18004bf48`
- `0x18004bf68`
- `0x18004c1e8`
- `0x180057430`
- `0x1800764d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18004c06b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18004c0fa`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18004c06b`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18004c0fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c085`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004c085`

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
  const wchar_t *v14; // rcx
  WCHAR *v15; // rdx
  __int64 v16; // rax
  WCHAR *v17; // rcx
  HANDLE v18; // rax
  const char *v19; // r9
  HANDLE v21; // rax
  const char *v22; // r9
  unsigned int LastError; // ebx
  int ValueFromSemaphore; // eax
  int v25; // eax
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
        v25 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v21, &v26);
        LastError = v25;
        if ( v25 >= 0 )
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
          (const char *)(unsigned int)v25,
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
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v29);
    return LastError;
  }
  else
  {
    if ( GetLastError() == 2 )
      return 0;
    return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v19);
  }
}

```

## disassembly

```asm
0x18004bf68  mov     [rsp-8+arg_0], rbx
0x18004bf6d  mov     [rsp-8+arg_8], rsi
0x18004bf72  push    rbp
0x18004bf73  push    rdi
0x18004bf74  push    r15
0x18004bf76  lea     rbp, [rsp-160h]
0x18004bf7e  sub     rsp, 260h
0x18004bf85  mov     rax, cs:__security_cookie
0x18004bf8c  xor     rax, rsp
0x18004bf8f  mov     [rbp+170h+var_20], rax
0x18004bf96  xor     esi, esi
0x18004bf98  lea     rax, [rsp+270h+Name]
0x18004bf9d  mov     r10d, 7FFFFFFEh
0x18004bfa3  mov     [r8], rsi
0x18004bfa6  mov     r15d, 104h
0x18004bfac  mov     r9d, r10d
0x18004bfaf  mov     edx, r15d
0x18004bfb2  mov     rdi, r8
0x18004bfb5  test    r9, r9
0x18004bfb8  jz      short loc_18004BFD9
0x18004bfba  movzx   r8d, word ptr [rcx]
0x18004bfbe  test    r8w, r8w
0x18004bfc2  jz      short loc_18004BFD9
0x18004bfc4  mov     [rax], r8w
0x18004bfc8  add     rcx, 2
0x18004bfcc  add     rax, 2
0x18004bfd0  dec     r9
0x18004bfd3  sub     rdx, 1
0x18004bfd7  jnz     short loc_18004BFB5
0x18004bfd9  test    rdx, rdx
0x18004bfdc  lea     rcx, [rax-2]
0x18004bfe0  mov     rdx, r15
0x18004bfe3  cmovnz  rcx, rax
0x18004bfe7  lea     rax, [rsp+270h+Name]
0x18004bfec  mov     [rcx], si
0x18004bfef  cmp     [rax], si
0x18004bff2  jz      short loc_18004BFFE
0x18004bff4  add     rax, 2
0x18004bff8  sub     rdx, 1
0x18004bffc  jnz     short loc_18004BFEF
0x18004bffe  mov     rcx, r15
0x18004c001  mov     rax, rdx
0x18004c004  sub     rcx, rdx
0x18004c007  neg     rax
0x18004c00a  sbb     r8, r8
0x18004c00d  and     r8, rcx
0x18004c010  test    rdx, rdx
0x18004c013  jz      short loc_18004C05F
0x18004c015  mov     rax, r15
0x18004c018  lea     rdx, [rsp+270h+Name]
0x18004c01d  lea     rcx, aP0; "_p0"
0x18004c024  lea     rdx, [rdx+r8*2]
0x18004c028  sub     rax, r8
0x18004c02b  jz      short loc_18004C051
0x18004c02d  test    r10, r10
0x18004c030  jz      short loc_18004C051
0x18004c032  movzx   r8d, word ptr [rcx]
0x18004c036  test    r8w, r8w
0x18004c03a  jz      short loc_18004C051
0x18004c03c  mov     [rdx], r8w
0x18004c040  add     rcx, 2
0x18004c044  add     rdx, 2
0x18004c048  dec     r10
0x18004c04b  sub     rax, 1
0x18004c04f  jnz     short loc_18004C02D
0x18004c051  test    rax, rax
0x18004c054  lea     rcx, [rdx-2]
0x18004c058  cmovnz  rcx, rdx
0x18004c05c  mov     [rcx], si
0x18004c05f  lea     r8, [rsp+270h+Name]; lpName
0x18004c064  xor     edx, edx; bInheritHandle
0x18004c066  mov     ecx, 1F0003h; dwDesiredAccess
0x18004c06b  call    cs:__imp_OpenSemaphoreW
0x18004c072  nop     dword ptr [rax+rax+00h]
0x18004c077  mov     [rsp+270h+var_240], rax
0x18004c07c  test    rax, rax
0x18004c07f  jnz     loc_18004C145
0x18004c085  call    cs:__imp_GetLastError
0x18004c08c  nop     dword ptr [rax+rax+00h]
0x18004c091  cmp     eax, 2
0x18004c094  jnz     short loc_18004C0C0
0x18004c096  xor     eax, eax
0x18004c098  mov     rcx, [rbp+170h+var_20]
0x18004c09f  xor     rcx, rsp; StackCookie
0x18004c0a2  call    __security_check_cookie
0x18004c0a7  lea     r11, [rsp+270h+var_10]
0x18004c0af  mov     rbx, [r11+20h]
0x18004c0b3  mov     rsi, [r11+28h]
0x18004c0b7  mov     rsp, r11
0x18004c0ba  pop     r15
0x18004c0bc  pop     rdi
0x18004c0bd  pop     rbp
0x18004c0be  retn
0x18004c0c0  mov     rcx, [rbp+178h]; this
0x18004c0c7  lea     r8, aWil; "wil"
0x18004c0ce  mov     edx, 0D0h; void *
0x18004c0d3  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004c0d8  jmp     short loc_18004C098
0x18004c0da  lea     r8, asc_1800DC48C; "h"
0x18004c0e1  mov     rdx, r15; unsigned __int64
0x18004c0e4  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18004c0e9  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18004c0ee  lea     r8, [rsp+270h+Name]; lpName
0x18004c0f3  xor     edx, edx; bInheritHandle
0x18004c0f5  mov     ecx, 1F0003h; dwDesiredAccess
0x18004c0fa  call    cs:__imp_OpenSemaphoreW
0x18004c101  nop     dword ptr [rax+rax+00h]
0x18004c106  mov     [rsp+270h+var_248], rax
0x18004c10b  test    rax, rax
0x18004c10e  jnz     short loc_18004C181
0x18004c110  mov     rcx, [rbp+178h]; this
0x18004c117  lea     r8, aWil; "wil"
0x18004c11e  mov     edx, 0DCh; void *
0x18004c123  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18004c128  mov     ebx, eax
0x18004c12a  lea     rcx, [rsp+270h+var_248]
0x18004c12f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004c134  lea     rcx, [rsp+270h+var_240]
0x18004c139  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004c13e  mov     eax, ebx
0x18004c140  jmp     loc_18004C098
0x18004c145  lea     rdx, [rsp+270h+var_24C]; int *
0x18004c14a  mov     [rsp+270h+var_24C], esi
0x18004c14e  mov     rcx, rax; hHandle
0x18004c151  mov     [rsp+270h+var_250], esi; int
0x18004c155  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18004c15a  mov     ebx, eax
0x18004c15c  test    eax, eax
0x18004c15e  jns     loc_18004C0DA
0x18004c164  mov     rcx, [rbp+178h]; this
0x18004c16b  lea     r8, aWil; "wil"
0x18004c172  mov     r9d, eax; char *
0x18004c175  mov     edx, 0D6h; void *
0x18004c17a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c17f  jmp     short loc_18004C134
0x18004c181  lea     rdx, [rsp+270h+var_250]; int *
0x18004c186  mov     rcx, rax; hHandle
0x18004c189  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18004c18e  mov     ebx, eax
0x18004c190  test    eax, eax
0x18004c192  jns     short loc_18004C1B4
0x18004c194  mov     rcx, [rbp+178h]; this
0x18004c19b  lea     r8, aWil; "wil"
0x18004c1a2  mov     r9d, eax; char *
0x18004c1a5  mov     edx, 0DEh; void *
0x18004c1aa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004c1af  jmp     loc_18004C12A
0x18004c1b4  lea     rcx, [rsp+270h+var_248]
0x18004c1b9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004c1be  movsxd  rax, [rsp+270h+var_24C]
0x18004c1c3  movsxd  rcx, [rsp+270h+var_250]
0x18004c1c8  shl     rcx, 1Fh
0x18004c1cc  or      rcx, rax
0x18004c1cf  mov     [rdi], rcx
0x18004c1d2  lea     rcx, [rsp+270h+var_240]
0x18004c1d7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18004c1dc  jmp     loc_18004C096
```
