# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180022e50`
- end: `0x1800230c5`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `629`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180022ddc`

## callees

- `0x1800066d0`
- `0x18001f734`
- `0x180020c04`
- `0x180022614`
- `0x180022634`
- `0x180022e50`
- `0x180023dd0`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x180022f22`
- `KERNEL32!OpenSemaphoreW` at `0x180022fec`
- `KERNEL32!OpenSemaphoreW` at `0x180022f22`
- `KERNEL32!OpenSemaphoreW` at `0x180022fec`
- `KERNEL32!GetLastError` at `0x180023070`
- `KERNEL32!GetLastError` at `0x180023070`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        const unsigned __int16 *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v5; // rax
  __int64 v6; // r11
  __int64 v7; // rsi
  __int64 v8; // rdx
  const wchar_t *v9; // r8
  bool v10; // zf
  __int64 v11; // rax
  __int64 v12; // rcx
  WCHAR *v13; // rdx
  WCHAR *v14; // rcx
  HANDLE v15; // rax
  int ValueFromSemaphore; // eax
  unsigned int v17; // r8d
  unsigned int LastError; // ebx
  __int64 v19; // rdx
  WCHAR *v20; // rax
  __int64 v21; // r8
  WCHAR *v22; // rax
  const wchar_t *v23; // rcx
  __int64 v24; // rdi
  WCHAR *v25; // rdx
  HANDLE v26; // rax
  unsigned int v27; // r8d
  const char *v28; // r9
  int v29; // eax
  unsigned int v30; // r8d
  unsigned int v32; // r8d
  const char *v33; // r9
  int v34; // [rsp+20h] [rbp-E0h] BYREF
  int v35; // [rsp+24h] [rbp-DCh] BYREF
  HANDLE v36; // [rsp+28h] [rbp-D8h] BYREF
  _QWORD v37[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Name[264]; // [rsp+40h] [rbp-C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+288h] [rbp+188h]

  *a3 = 0;
  StringCchCopyW(Name, 0x104u, a1);
  v5 = Name;
  v6 = 260;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v6;
  }
  while ( v6 );
  v7 = 2147483646;
  v8 = (260 - v6) & ((unsigned __int128)-(__int128)(unsigned __int64)v6 >> 64);
  if ( v6 )
  {
    v9 = L"_p0";
    v11 = 260 - v8;
    v10 = v8 == 260;
    v12 = 2147483646;
    v13 = &Name[v8];
    if ( !v10 )
    {
      do
      {
        if ( !v12 )
          break;
        if ( !*v9 )
          break;
        *v13++ = *v9++;
        --v12;
        --v11;
      }
      while ( v11 );
    }
    v14 = v13 - 1;
    if ( v11 )
      v14 = v13;
    *v14 = 0;
  }
  v15 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v37[0] = v15;
  if ( v15 )
  {
    v35 = 0;
    v34 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v15, &v35);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      v19 = 260;
      v20 = Name;
      do
      {
        if ( !*v20 )
          break;
        ++v20;
        --v19;
      }
      while ( v19 );
      v21 = (260 - v19) & -(__int64)(v19 != 0);
      if ( v19 )
      {
        v22 = &Name[v21];
        v23 = L"h";
        v24 = 260 - v21;
        if ( 260 != v21 )
        {
          do
          {
            if ( !v7 )
              break;
            if ( !*v23 )
              break;
            *v22++ = *v23++;
            --v7;
            --v24;
          }
          while ( v24 );
        }
        v25 = v22 - 1;
        if ( v24 )
          v25 = v22;
        *v25 = 0;
      }
      v26 = OpenSemaphoreW(0x1F0003u, 0, Name);
      v36 = v26;
      if ( v26 )
      {
        v29 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v26, &v34);
        LastError = v29;
        if ( v29 >= 0 )
        {
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v36);
          *a3 = v35 | (unsigned __int64)((__int64)v34 << 31);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v37);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(retaddr, (void *)0xDE, v30, (const char *)(unsigned int)v29, v34);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, v27, v28);
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v36);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(retaddr, (void *)0xD6, v17, (const char *)(unsigned int)ValueFromSemaphore, v34);
    }
  }
  else if ( GetLastError() == 2 )
  {
    LastError = 0;
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, v32, v33);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v37);
  return LastError;
}

```

## disassembly

```asm
0x180022e50  mov     [rsp-8+arg_8], rbx
0x180022e55  push    rbp
0x180022e56  push    rsi
0x180022e57  push    rdi
0x180022e58  push    r14
0x180022e5a  push    r15
0x180022e5c  lea     rbp, [rsp-160h]
0x180022e64  sub     rsp, 260h
0x180022e6b  mov     rax, cs:__security_cookie
0x180022e72  xor     rax, rsp
0x180022e75  mov     [rbp+180h+var_30], rax
0x180022e7c  xor     r15d, r15d
0x180022e7f  mov     r14, r8
0x180022e82  mov     [r8], r15
0x180022e85  mov     edi, 104h
0x180022e8a  mov     r8, rcx; unsigned __int16 *
0x180022e8d  mov     edx, edi; unsigned __int64
0x180022e8f  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180022e94  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180022e99  lea     rax, [rsp+280h+Name]
0x180022e9e  mov     r11d, edi
0x180022ea1  cmp     [rax], r15w
0x180022ea5  jz      short loc_180022EB1
0x180022ea7  add     rax, 2
0x180022eab  sub     r11, 1
0x180022eaf  jnz     short loc_180022EA1
0x180022eb1  mov     rcx, rdi
0x180022eb4  mov     rax, r11
0x180022eb7  sub     rcx, r11
0x180022eba  mov     esi, 7FFFFFFEh
0x180022ebf  neg     rax
0x180022ec2  sbb     rdx, rdx
0x180022ec5  and     rdx, rcx
0x180022ec8  test    r11, r11
0x180022ecb  jz      short loc_180022F16
0x180022ecd  mov     rax, rdi
0x180022ed0  lea     r8, aP0; "_p0"
0x180022ed7  sub     rax, rdx
0x180022eda  mov     ecx, esi
0x180022edc  lea     rdx, [rsp+rdx*2+280h+Name]
0x180022ee1  jz      short loc_180022F07
0x180022ee3  test    rcx, rcx
0x180022ee6  jz      short loc_180022F07
0x180022ee8  movzx   r9d, word ptr [r8]
0x180022eec  test    r9w, r9w
0x180022ef0  jz      short loc_180022F07
0x180022ef2  mov     [rdx], r9w
0x180022ef6  add     r8, 2
0x180022efa  add     rdx, 2
0x180022efe  dec     rcx
0x180022f01  sub     rax, 1
0x180022f05  jnz     short loc_180022EE3
0x180022f07  test    rax, rax
0x180022f0a  lea     rcx, [rdx-2]
0x180022f0e  cmovnz  rcx, rdx
0x180022f12  mov     [rcx], r15w
0x180022f16  lea     r8, [rsp+280h+Name]; lpName
0x180022f1b  xor     edx, edx; bInheritHandle
0x180022f1d  mov     ecx, 1F0003h; dwDesiredAccess
0x180022f22  call    cs:__imp_OpenSemaphoreW
0x180022f28  mov     [rsp+280h+var_250], rax
0x180022f2d  test    rax, rax
0x180022f30  jz      loc_180023070
0x180022f36  lea     rdx, [rsp+280h+var_25C]; int *
0x180022f3b  mov     [rsp+280h+var_25C], r15d
0x180022f40  mov     rcx, rax; hHandle
0x180022f43  mov     [rsp+280h+var_260], r15d; int
0x180022f48  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180022f4d  mov     ebx, eax
0x180022f4f  test    eax, eax
0x180022f51  jns     short loc_180022F6C
0x180022f53  mov     rcx, [rbp+188h]; this
0x180022f5a  mov     r9d, eax; char *
0x180022f5d  mov     edx, 0D6h; void *
0x180022f62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022f67  jmp     loc_180023093
0x180022f6c  mov     rdx, rdi
0x180022f6f  lea     rax, [rsp+280h+Name]
0x180022f74  cmp     [rax], r15w
0x180022f78  jz      short loc_180022F84
0x180022f7a  add     rax, 2
0x180022f7e  sub     rdx, 1
0x180022f82  jnz     short loc_180022F74
0x180022f84  mov     rcx, rdi
0x180022f87  mov     rax, rdx
0x180022f8a  sub     rcx, rdx
0x180022f8d  neg     rax
0x180022f90  sbb     r8, r8
0x180022f93  and     r8, rcx
0x180022f96  test    rdx, rdx
0x180022f99  jz      short loc_180022FE0
0x180022f9b  lea     rax, [rsp+280h+Name]
0x180022fa0  lea     rax, [rax+r8*2]
0x180022fa4  lea     rcx, asc_18006A408; "h"
0x180022fab  sub     rdi, r8
0x180022fae  jz      short loc_180022FD1
0x180022fb0  test    rsi, rsi
0x180022fb3  jz      short loc_180022FD1
0x180022fb5  movzx   edx, word ptr [rcx]
0x180022fb8  test    dx, dx
0x180022fbb  jz      short loc_180022FD1
0x180022fbd  mov     [rax], dx
0x180022fc0  add     rcx, 2
0x180022fc4  add     rax, 2
0x180022fc8  dec     rsi
0x180022fcb  sub     rdi, 1
0x180022fcf  jnz     short loc_180022FB0
0x180022fd1  test    rdi, rdi
0x180022fd4  lea     rdx, [rax-2]
0x180022fd8  cmovnz  rdx, rax
0x180022fdc  mov     [rdx], r15w
0x180022fe0  lea     r8, [rsp+280h+Name]; lpName
0x180022fe5  xor     edx, edx; bInheritHandle
0x180022fe7  mov     ecx, 1F0003h; dwDesiredAccess
0x180022fec  call    cs:__imp_OpenSemaphoreW
0x180022ff2  mov     [rsp+280h+var_258], rax
0x180022ff7  test    rax, rax
0x180022ffa  jz      short loc_180023051
0x180022ffc  lea     rdx, [rsp+280h+var_260]; int *
0x180023001  mov     rcx, rax; hHandle
0x180023004  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180023009  mov     ebx, eax
0x18002300b  test    eax, eax
0x18002300d  jns     short loc_180023025
0x18002300f  mov     rcx, [rbp+188h]; this
0x180023016  mov     r9d, eax; char *
0x180023019  mov     edx, 0DEh; void *
0x18002301e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023023  jmp     short loc_180023064
0x180023025  lea     rcx, [rsp+280h+var_258]
0x18002302a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002302f  movsxd  rax, [rsp+280h+var_25C]
0x180023034  movsxd  rcx, [rsp+280h+var_260]
0x180023039  shl     rcx, 1Fh
0x18002303d  or      rcx, rax
0x180023040  mov     [r14], rcx
0x180023043  lea     rcx, [rsp+280h+var_250]
0x180023048  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002304d  xor     eax, eax
0x18002304f  jmp     short loc_18002309F
0x180023051  mov     rcx, [rbp+188h]; this
0x180023058  mov     edx, 0DCh; void *
0x18002305d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023062  mov     ebx, eax
0x180023064  lea     rcx, [rsp+280h+var_258]
0x180023069  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002306e  jmp     short loc_180023093
0x180023070  call    cs:__imp_GetLastError
0x180023076  cmp     eax, 2
0x180023079  jnz     short loc_180023080
0x18002307b  mov     ebx, r15d
0x18002307e  jmp     short loc_180023093
0x180023080  mov     rcx, [rbp+188h]; this
0x180023087  mov     edx, 0D0h; void *
0x18002308c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180023091  mov     ebx, eax
0x180023093  lea     rcx, [rsp+280h+var_250]
0x180023098  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002309d  mov     eax, ebx
0x18002309f  mov     rcx, [rbp+180h+var_30]
0x1800230a6  xor     rcx, rsp; StackCookie
0x1800230a9  call    __security_check_cookie
0x1800230ae  mov     rbx, [rsp+280h+arg_8]
0x1800230b6  add     rsp, 260h
0x1800230bd  pop     r15
0x1800230bf  pop     r14
0x1800230c1  pop     rdi
0x1800230c2  pop     rsi
0x1800230c3  pop     rbp
0x1800230c4  retn
```
