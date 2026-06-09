# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18000c960`
- end: `0x18000cc31`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `721`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000c774`
- `0x18000cdbc`

## callees

- `0x18000c960`
- `0x18000cc38`
- `0x18000cc64`
- `0x180018248`
- `0x18001a274`
- `0x18001a324`
- `0x18004c9d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ca6c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000cb40`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000ca6c`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000cb40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cbd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000cbd2`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // rax
  __int64 v5; // r14
  __int64 v6; // r9
  __int64 v7; // rdx
  bool v9; // zf
  WCHAR *v10; // rcx
  __int64 v11; // rdx
  WCHAR *v12; // rax
  __int64 v13; // r8
  const unsigned __int16 *v14; // r9
  __int64 v15; // rcx
  WCHAR *v16; // rdx
  __int64 v17; // rax
  WCHAR *v18; // rcx
  wil::details *v19; // rax
  wil::details *v20; // rdi
  int ValueFromSemaphore; // eax
  unsigned int LastError; // esi
  __int64 v23; // rdx
  WCHAR *v24; // rax
  __int64 v25; // r8
  WCHAR *v26; // rax
  const unsigned __int16 *v27; // rcx
  __int64 v28; // rbx
  WCHAR *v29; // rdx
  wil::details *v30; // rax
  const char *v31; // r9
  wil::details *v32; // rbx
  int v33; // eax
  void *v34; // rdx
  void *v35; // rdx
  void *v36; // rdx
  void *v37; // rdx
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-E0h] BYREF
  int v41; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v42; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Name[264]; // [rsp+30h] [rbp-D0h] BYREF
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
    v15 = 2147483646;
    v16 = &Name[v13];
    v17 = 260 - v13;
    if ( v13 != 260 )
    {
      do
      {
        if ( !v15 )
          break;
        if ( !*v14 )
          break;
        *v16++ = *v14++;
        --v15;
        --v17;
      }
      while ( v17 );
    }
    v18 = v16 - 1;
    if ( v17 )
      v18 = v16;
    *v18 = 0;
  }
  v19 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v42 = v19;
  v20 = v19;
  if ( v19 )
  {
    v41 = 0;
    v40 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v41);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      v23 = 260;
      v24 = Name;
      do
      {
        if ( !*v24 )
          break;
        ++v24;
        --v23;
      }
      while ( v23 );
      v25 = (260 - v23) & -(__int64)(v23 != 0);
      if ( v23 )
      {
        v26 = &Name[v25];
        v27 = L"h";
        v28 = 260 - v25;
        if ( 260 != v25 )
        {
          do
          {
            if ( !v5 )
              break;
            if ( !*v27 )
              break;
            *v26++ = *v27++;
            --v5;
            --v28;
          }
          while ( v28 );
        }
        v29 = v26 - 1;
        if ( v28 )
          v29 = v26;
        *v29 = 0;
      }
      v30 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
      v32 = v30;
      if ( v30 )
      {
        v33 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v30, &v40);
        LastError = v33;
        if ( v33 >= 0 )
        {
          wil::details::CloseHandle(v32, v34);
          *a3 = v41 | (unsigned __int64)((__int64)v40 << 31);
          wil::details::CloseHandle(v20, v37);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"wil",
          (const char *)(unsigned int)v33,
          v40);
        wil::details::CloseHandle(v32, v35);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v31);
      }
      wil::details::CloseHandle(v20, v36);
      return LastError;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v40);
LABEL_40:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v42);
    return LastError;
  }
  if ( GetLastError() == 2 )
  {
    LastError = 0;
    goto LABEL_40;
  }
  return wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v39);
}

```

## disassembly

```asm
0x18000c960  mov     [rsp-8+arg_0], rbx
0x18000c965  mov     [rsp-8+arg_8], rsi
0x18000c96a  push    rbp
0x18000c96b  push    rdi
0x18000c96c  push    r12
0x18000c96e  push    r14
0x18000c970  push    r15
0x18000c972  lea     rbp, [rsp-150h]
0x18000c97a  sub     rsp, 250h
0x18000c981  mov     rax, cs:__security_cookie
0x18000c988  xor     rax, rsp
0x18000c98b  mov     [rbp+170h+var_30], rax
0x18000c992  xor     r12d, r12d
0x18000c995  lea     rax, [rsp+270h+Name]
0x18000c99a  mov     r14d, 7FFFFFFEh
0x18000c9a0  mov     [r8], r12
0x18000c9a3  mov     ebx, 104h
0x18000c9a8  mov     r9d, r14d
0x18000c9ab  mov     edx, ebx
0x18000c9ad  mov     r15, r8
0x18000c9b0  test    r9, r9
0x18000c9b3  jz      short loc_18000C9D4
0x18000c9b5  movzx   r8d, word ptr [rcx]
0x18000c9b9  test    r8w, r8w
0x18000c9bd  jz      short loc_18000C9D4
0x18000c9bf  mov     [rax], r8w
0x18000c9c3  add     rcx, 2
0x18000c9c7  add     rax, 2
0x18000c9cb  dec     r9
0x18000c9ce  sub     rdx, 1
0x18000c9d2  jnz     short loc_18000C9B0
0x18000c9d4  test    rdx, rdx
0x18000c9d7  lea     rcx, [rax-2]
0x18000c9db  mov     rdx, rbx
0x18000c9de  cmovnz  rcx, rax
0x18000c9e2  lea     rax, [rsp+270h+Name]
0x18000c9e7  mov     [rcx], r12w
0x18000c9eb  cmp     [rax], r12w
0x18000c9ef  jz      short loc_18000C9FB
0x18000c9f1  add     rax, 2
0x18000c9f5  sub     rdx, 1
0x18000c9f9  jnz     short loc_18000C9EB
0x18000c9fb  mov     rcx, rbx
0x18000c9fe  mov     rax, rdx
0x18000ca01  sub     rcx, rdx
0x18000ca04  neg     rax
0x18000ca07  sbb     r8, r8
0x18000ca0a  and     r8, rcx
0x18000ca0d  test    rdx, rdx
0x18000ca10  jz      short loc_18000CA60
0x18000ca12  mov     rax, rbx
0x18000ca15  lea     rdx, [rsp+270h+Name]
0x18000ca1a  lea     r9, aP0; "_p0"
0x18000ca21  mov     rcx, r14
0x18000ca24  lea     rdx, [rdx+r8*2]
0x18000ca28  sub     rax, r8
0x18000ca2b  jz      short loc_18000CA51
0x18000ca2d  test    rcx, rcx
0x18000ca30  jz      short loc_18000CA51
0x18000ca32  movzx   r8d, word ptr [r9]
0x18000ca36  test    r8w, r8w
0x18000ca3a  jz      short loc_18000CA51
0x18000ca3c  mov     [rdx], r8w
0x18000ca40  add     r9, 2
0x18000ca44  add     rdx, 2
0x18000ca48  dec     rcx
0x18000ca4b  sub     rax, 1
0x18000ca4f  jnz     short loc_18000CA2D
0x18000ca51  test    rax, rax
0x18000ca54  lea     rcx, [rdx-2]
0x18000ca58  cmovnz  rcx, rdx
0x18000ca5c  mov     [rcx], r12w
0x18000ca60  lea     r8, [rsp+270h+Name]; lpName
0x18000ca65  xor     edx, edx; bInheritHandle
0x18000ca67  mov     ecx, 1F0003h; dwDesiredAccess
0x18000ca6c  call    cs:__imp_OpenSemaphoreW
0x18000ca72  mov     [rsp+270h+var_248], rax
0x18000ca77  mov     rdi, rax
0x18000ca7a  test    rax, rax
0x18000ca7d  jz      loc_18000CBD2
0x18000ca83  lea     rdx, [rsp+270h+var_24C]; int *
0x18000ca88  mov     [rsp+270h+var_24C], r12d
0x18000ca8d  mov     rcx, rax; hHandle
0x18000ca90  mov     [rsp+270h+var_250], r12d; int
0x18000ca95  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000ca9a  mov     esi, eax
0x18000ca9c  test    eax, eax
0x18000ca9e  jns     short loc_18000CAC0
0x18000caa0  mov     rcx, [rbp+178h]; this
0x18000caa7  lea     r8, aWil; "wil"
0x18000caae  mov     r9d, eax; char *
0x18000cab1  mov     edx, 0D6h; void *
0x18000cab6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cabb  jmp     loc_18000CBE0
0x18000cac0  mov     rdx, rbx
0x18000cac3  lea     rax, [rsp+270h+Name]
0x18000cac8  cmp     [rax], r12w
0x18000cacc  jz      short loc_18000CAD8
0x18000cace  add     rax, 2
0x18000cad2  sub     rdx, 1
0x18000cad6  jnz     short loc_18000CAC8
0x18000cad8  mov     rcx, rbx
0x18000cadb  mov     rax, rdx
0x18000cade  sub     rcx, rdx
0x18000cae1  neg     rax
0x18000cae4  sbb     r8, r8
0x18000cae7  and     r8, rcx
0x18000caea  test    rdx, rdx
0x18000caed  jz      short loc_18000CB34
0x18000caef  lea     rax, [rsp+270h+Name]
0x18000caf4  lea     rax, [rax+r8*2]
0x18000caf8  lea     rcx, asc_18004FC48; "h"
0x18000caff  sub     rbx, r8
0x18000cb02  jz      short loc_18000CB25
0x18000cb04  test    r14, r14
0x18000cb07  jz      short loc_18000CB25
0x18000cb09  movzx   edx, word ptr [rcx]
0x18000cb0c  test    dx, dx
0x18000cb0f  jz      short loc_18000CB25
0x18000cb11  mov     [rax], dx
0x18000cb14  add     rcx, 2
0x18000cb18  add     rax, 2
0x18000cb1c  dec     r14
0x18000cb1f  sub     rbx, 1
0x18000cb23  jnz     short loc_18000CB04
0x18000cb25  test    rbx, rbx
0x18000cb28  lea     rdx, [rax-2]
0x18000cb2c  cmovnz  rdx, rax
0x18000cb30  mov     [rdx], r12w
0x18000cb34  lea     r8, [rsp+270h+Name]; lpName
0x18000cb39  xor     edx, edx; bInheritHandle
0x18000cb3b  mov     ecx, 1F0003h; dwDesiredAccess
0x18000cb40  call    cs:__imp_OpenSemaphoreW
0x18000cb46  mov     rbx, rax
0x18000cb49  test    rax, rax
0x18000cb4c  jz      short loc_18000CBAE
0x18000cb4e  lea     rdx, [rsp+270h+var_250]; int *
0x18000cb53  mov     rcx, rax; hHandle
0x18000cb56  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000cb5b  mov     esi, eax
0x18000cb5d  test    eax, eax
0x18000cb5f  jns     short loc_18000CB86
0x18000cb61  mov     rcx, [rbp+178h]; this
0x18000cb68  lea     r8, aWil; "wil"
0x18000cb6f  mov     r9d, eax; char *
0x18000cb72  mov     edx, 0DEh; void *
0x18000cb77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cb7c  mov     rcx, rbx; this
0x18000cb7f  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000cb84  jmp     short loc_18000CBC8
0x18000cb86  mov     rcx, rbx; this
0x18000cb89  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000cb8e  movsxd  rax, [rsp+270h+var_24C]
0x18000cb93  movsxd  rcx, [rsp+270h+var_250]
0x18000cb98  shl     rcx, 1Fh
0x18000cb9c  or      rcx, rax
0x18000cb9f  mov     [r15], rcx
0x18000cba2  mov     rcx, rdi; this
0x18000cba5  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000cbaa  xor     eax, eax
0x18000cbac  jmp     short loc_18000CC06
0x18000cbae  mov     rcx, [rbp+178h]; this
0x18000cbb5  lea     r8, aWil; "wil"
0x18000cbbc  mov     edx, 0DCh; void *
0x18000cbc1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000cbc6  mov     esi, eax
0x18000cbc8  mov     rcx, rdi; this
0x18000cbcb  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000cbd0  jmp     short loc_18000CBEA
0x18000cbd2  call    cs:__imp_GetLastError
0x18000cbd8  cmp     eax, 2
0x18000cbdb  jnz     short loc_18000CBEE
0x18000cbdd  mov     esi, r12d
0x18000cbe0  lea     rcx, [rsp+270h+var_248]
0x18000cbe5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000cbea  mov     eax, esi
0x18000cbec  jmp     short loc_18000CC06
0x18000cbee  mov     rcx, [rbp+178h]; this
0x18000cbf5  lea     r8, aWil; "wil"
0x18000cbfc  mov     edx, 0D0h; void *
0x18000cc01  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000cc06  mov     rcx, [rbp+170h+var_30]
0x18000cc0d  xor     rcx, rsp; StackCookie
0x18000cc10  call    __security_check_cookie
0x18000cc15  lea     r11, [rsp+270h+var_20]
0x18000cc1d  mov     rbx, [r11+30h]
0x18000cc21  mov     rsi, [r11+38h]
0x18000cc25  mov     rsp, r11
0x18000cc28  pop     r15
0x18000cc2a  pop     r14
0x18000cc2c  pop     r12
0x18000cc2e  pop     rdi
0x18000cc2f  pop     rbp
0x18000cc30  retn
```
