# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180004d8c`
- end: `0x180005072`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `742`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180004a80`
- `0x1800053e8`

## callees

- `0x180004d8c`
- `0x180005078`
- `0x1800051e8`
- `0x180005214`
- `0x1800077c8`
- `0x18003169c`
- `0x180037780`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180004e98`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180004feb`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180004e98`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180004feb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004eaf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004eaf`

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
  const char *v21; // r9
  unsigned int LastError; // ebx
  int v24; // eax
  void *v25; // rdx
  unsigned int v26; // esi
  void *v27; // rdx
  int ValueFromSemaphore; // eax
  __int64 v29; // rdx
  WCHAR *v30; // rax
  __int64 v31; // r8
  WCHAR *v32; // rax
  const unsigned __int16 *v33; // rcx
  __int64 v34; // rbx
  WCHAR *v35; // rdx
  wil::details *v36; // rax
  const char *v37; // r9
  wil::details *v38; // rbx
  void *v39; // rdx
  void *v40; // rdx
  int v41; // [rsp+20h] [rbp-E0h] BYREF
  int v42; // [rsp+24h] [rbp-DCh] BYREF
  wil::details *v43; // [rsp+28h] [rbp-D8h] BYREF
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
  v43 = v19;
  v20 = v19;
  if ( !v19 )
  {
    if ( GetLastError() != 2 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v21);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v43);
      return LastError;
    }
    return 0;
  }
  v42 = 0;
  v41 = 0;
  ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v19, &v42);
  v26 = ValueFromSemaphore;
  if ( ValueFromSemaphore < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD6,
      (unsigned int)"wil",
      (const char *)(unsigned int)ValueFromSemaphore,
      v41);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v43);
  }
  else
  {
    v29 = 260;
    v30 = Name;
    do
    {
      if ( !*v30 )
        break;
      ++v30;
      --v29;
    }
    while ( v29 );
    v31 = (260 - v29) & -(__int64)(v29 != 0);
    if ( v29 )
    {
      v32 = &Name[v31];
      v33 = L"h";
      v34 = 260 - v31;
      if ( 260 != v31 )
      {
        do
        {
          if ( !v5 )
            break;
          if ( !*v33 )
            break;
          *v32++ = *v33++;
          --v5;
          --v34;
        }
        while ( v34 );
      }
      v35 = v32 - 1;
      if ( v34 )
        v35 = v32;
      *v35 = 0;
    }
    v36 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v38 = v36;
    if ( v36 )
    {
      v24 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v36, &v41);
      v26 = v24;
      if ( v24 >= 0 )
      {
        wil::details::CloseHandle(v38, v25);
        *a3 = v42 | (unsigned __int64)((__int64)v41 << 31);
        wil::details::CloseHandle(v20, v27);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDE,
        (unsigned int)"wil",
        (const char *)(unsigned int)v24,
        v41);
      wil::details::CloseHandle(v38, v40);
    }
    else
    {
      v26 = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v37);
    }
    wil::details::CloseHandle(v20, v39);
  }
  return v26;
}

```

## disassembly

```asm
0x180004d8c  mov     [rsp-8+arg_0], rbx
0x180004d91  mov     [rsp-8+arg_8], rsi
0x180004d96  push    rbp
0x180004d97  push    rdi
0x180004d98  push    r12
0x180004d9a  push    r14
0x180004d9c  push    r15
0x180004d9e  lea     rbp, [rsp-150h]
0x180004da6  sub     rsp, 250h
0x180004dad  mov     rax, cs:__security_cookie
0x180004db4  xor     rax, rsp
0x180004db7  mov     [rbp+170h+var_30], rax
0x180004dbe  xor     r12d, r12d
0x180004dc1  lea     rax, [rsp+270h+Name]
0x180004dc6  mov     r14d, 7FFFFFFEh
0x180004dcc  mov     [r8], r12
0x180004dcf  mov     ebx, 104h
0x180004dd4  mov     r9d, r14d
0x180004dd7  mov     edx, ebx
0x180004dd9  mov     r15, r8
0x180004ddc  test    r9, r9
0x180004ddf  jz      short loc_180004E00
0x180004de1  movzx   r8d, word ptr [rcx]
0x180004de5  test    r8w, r8w
0x180004de9  jz      short loc_180004E00
0x180004deb  mov     [rax], r8w
0x180004def  add     rcx, 2
0x180004df3  add     rax, 2
0x180004df7  dec     r9
0x180004dfa  sub     rdx, 1
0x180004dfe  jnz     short loc_180004DDC
0x180004e00  test    rdx, rdx
0x180004e03  lea     rcx, [rax-2]
0x180004e07  mov     rdx, rbx
0x180004e0a  cmovnz  rcx, rax
0x180004e0e  lea     rax, [rsp+270h+Name]
0x180004e13  mov     [rcx], r12w
0x180004e17  cmp     [rax], r12w
0x180004e1b  jz      short loc_180004E27
0x180004e1d  add     rax, 2
0x180004e21  sub     rdx, 1
0x180004e25  jnz     short loc_180004E17
0x180004e27  mov     rcx, rbx
0x180004e2a  mov     rax, rdx
0x180004e2d  sub     rcx, rdx
0x180004e30  neg     rax
0x180004e33  sbb     r8, r8
0x180004e36  and     r8, rcx
0x180004e39  test    rdx, rdx
0x180004e3c  jz      short loc_180004E8C
0x180004e3e  mov     rax, rbx
0x180004e41  lea     rdx, [rsp+270h+Name]
0x180004e46  lea     r9, aP0; "_p0"
0x180004e4d  mov     rcx, r14
0x180004e50  lea     rdx, [rdx+r8*2]
0x180004e54  sub     rax, r8
0x180004e57  jz      short loc_180004E7D
0x180004e59  test    rcx, rcx
0x180004e5c  jz      short loc_180004E7D
0x180004e5e  movzx   r8d, word ptr [r9]
0x180004e62  test    r8w, r8w
0x180004e66  jz      short loc_180004E7D
0x180004e68  mov     [rdx], r8w
0x180004e6c  add     r9, 2
0x180004e70  add     rdx, 2
0x180004e74  dec     rcx
0x180004e77  sub     rax, 1
0x180004e7b  jnz     short loc_180004E59
0x180004e7d  test    rax, rax
0x180004e80  lea     rcx, [rdx-2]
0x180004e84  cmovnz  rcx, rdx
0x180004e88  mov     [rcx], r12w
0x180004e8c  lea     r8, [rsp+270h+Name]; lpName
0x180004e91  xor     edx, edx; bInheritHandle
0x180004e93  mov     ecx, 1F0003h; dwDesiredAccess
0x180004e98  call    cs:__imp_OpenSemaphoreW
0x180004e9e  mov     [rsp+270h+var_248], rax
0x180004ea3  mov     rdi, rax
0x180004ea6  test    rax, rax
0x180004ea9  jnz     loc_180004F4A
0x180004eaf  call    cs:__imp_GetLastError
0x180004eb5  cmp     eax, 2
0x180004eb8  jz      short loc_180004F1D
0x180004eba  mov     rcx, [rbp+178h]; this
0x180004ec1  lea     r8, aWil; "wil"
0x180004ec8  mov     edx, 0D0h; void *
0x180004ecd  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180004ed2  lea     rcx, [rsp+270h+var_248]
0x180004ed7  mov     ebx, eax
0x180004ed9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180004ede  mov     eax, ebx
0x180004ee0  jmp     short loc_180004F1F
0x180004ee2  lea     rdx, [rsp+270h+var_250]; int *
0x180004ee7  mov     rcx, rbx; hHandle
0x180004eea  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180004eef  mov     esi, eax
0x180004ef1  test    eax, eax
0x180004ef3  js      loc_180005026
0x180004ef9  mov     rcx, rbx; this
0x180004efc  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180004f01  movsxd  rax, [rsp+270h+var_24C]
0x180004f06  movsxd  rcx, [rsp+270h+var_250]
0x180004f0b  shl     rcx, 1Fh
0x180004f0f  or      rcx, rax
0x180004f12  mov     [r15], rcx
0x180004f15  mov     rcx, rdi; this
0x180004f18  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180004f1d  xor     eax, eax
0x180004f1f  mov     rcx, [rbp+170h+var_30]
0x180004f26  xor     rcx, rsp; StackCookie
0x180004f29  call    __security_check_cookie
0x180004f2e  lea     r11, [rsp+270h+var_20]
0x180004f36  mov     rbx, [r11+30h]
0x180004f3a  mov     rsi, [r11+38h]
0x180004f3e  mov     rsp, r11
0x180004f41  pop     r15
0x180004f43  pop     r14
0x180004f45  pop     r12
0x180004f47  pop     rdi
0x180004f48  pop     rbp
0x180004f49  retn
0x180004f4a  lea     rdx, [rsp+270h+var_24C]; int *
0x180004f4f  mov     [rsp+270h+var_24C], r12d
0x180004f54  mov     rcx, rdi; hHandle
0x180004f57  mov     [rsp+270h+var_250], r12d; int
0x180004f5c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180004f61  mov     esi, eax
0x180004f63  test    eax, eax
0x180004f65  js      loc_18000504B
0x180004f6b  mov     rdx, rbx
0x180004f6e  lea     rax, [rsp+270h+Name]
0x180004f73  cmp     [rax], r12w
0x180004f77  jz      short loc_180004F83
0x180004f79  add     rax, 2
0x180004f7d  sub     rdx, 1
0x180004f81  jnz     short loc_180004F73
0x180004f83  mov     rcx, rbx
0x180004f86  mov     rax, rdx
0x180004f89  sub     rcx, rdx
0x180004f8c  neg     rax
0x180004f8f  sbb     r8, r8
0x180004f92  and     r8, rcx
0x180004f95  test    rdx, rdx
0x180004f98  jz      short loc_180004FDF
0x180004f9a  lea     rax, [rsp+270h+Name]
0x180004f9f  lea     rax, [rax+r8*2]
0x180004fa3  lea     rcx, asc_18009133C; "h"
0x180004faa  sub     rbx, r8
0x180004fad  jz      short loc_180004FD0
0x180004faf  test    r14, r14
0x180004fb2  jz      short loc_180004FD0
0x180004fb4  movzx   edx, word ptr [rcx]
0x180004fb7  test    dx, dx
0x180004fba  jz      short loc_180004FD0
0x180004fbc  mov     [rax], dx
0x180004fbf  add     rcx, 2
0x180004fc3  add     rax, 2
0x180004fc7  dec     r14
0x180004fca  sub     rbx, 1
0x180004fce  jnz     short loc_180004FAF
0x180004fd0  test    rbx, rbx
0x180004fd3  lea     rdx, [rax-2]
0x180004fd7  cmovnz  rdx, rax
0x180004fdb  mov     [rdx], r12w
0x180004fdf  lea     r8, [rsp+270h+Name]; lpName
0x180004fe4  xor     edx, edx; bInheritHandle
0x180004fe6  mov     ecx, 1F0003h; dwDesiredAccess
0x180004feb  call    cs:__imp_OpenSemaphoreW
0x180004ff1  mov     rbx, rax
0x180004ff4  test    rax, rax
0x180004ff7  jnz     loc_180004EE2
0x180004ffd  mov     rcx, [rbp+178h]; this
0x180005004  lea     r8, aWil; "wil"
0x18000500b  mov     edx, 0DCh; void *
0x180005010  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180005015  mov     esi, eax
0x180005017  mov     rcx, rdi; this
0x18000501a  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000501f  mov     eax, esi
0x180005021  jmp     loc_180004F1F
0x180005026  mov     rcx, [rbp+178h]; this
0x18000502d  lea     r8, aWil; "wil"
0x180005034  mov     r9d, eax; char *
0x180005037  mov     edx, 0DEh; void *
0x18000503c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005041  mov     rcx, rbx; this
0x180005044  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180005049  jmp     short loc_180005017
0x18000504b  mov     rcx, [rbp+178h]; this
0x180005052  lea     r8, aWil; "wil"
0x180005059  mov     r9d, esi; char *
0x18000505c  mov     edx, 0D6h; void *
0x180005061  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180005066  lea     rcx, [rsp+270h+var_248]
0x18000506b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180005070  jmp     short loc_18000501F
```
