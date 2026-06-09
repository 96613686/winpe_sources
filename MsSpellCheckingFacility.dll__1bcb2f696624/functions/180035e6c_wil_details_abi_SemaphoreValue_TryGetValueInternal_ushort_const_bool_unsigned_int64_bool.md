# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180035e6c`
- end: `0x180036098`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `556`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180035bcc`
- `0x18004a9a8`

## callees

- `0x180006c90`
- `0x180035e6c`
- `0x18004a904`
- `0x18004aa2c`
- `0x18004aa50`
- `0x18004cdd0`
- `0x180061320`
- `0x1800674f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003603e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003603e`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180035f3d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180035fac`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180035f3d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180035fac`

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
0x180035e6c  mov     [rsp-8+arg_0], rbx
0x180035e71  mov     [rsp-8+arg_8], rsi
0x180035e76  push    rbp
0x180035e77  push    rdi
0x180035e78  push    r14
0x180035e7a  lea     rbp, [rsp-170h]
0x180035e82  sub     rsp, 270h
0x180035e89  mov     rax, cs:__security_cookie
0x180035e90  xor     rax, rsp
0x180035e93  mov     [rbp+180h+var_20], rax
0x180035e9a  xor     esi, esi
0x180035e9c  lea     rax, [rsp+280h+Name]
0x180035ea1  mov     r14d, 104h
0x180035ea7  mov     [r8], rsi
0x180035eaa  mov     edx, r14d
0x180035ead  mov     rdi, r8
0x180035eb0  mov     r9d, 7FFFFFFEh
0x180035eb6  test    r9, r9
0x180035eb9  jz      short loc_180035EDA
0x180035ebb  movzx   r8d, word ptr [rcx]
0x180035ebf  test    r8w, r8w
0x180035ec3  jz      short loc_180035EDA
0x180035ec5  mov     [rax], r8w
0x180035ec9  add     rcx, 2
0x180035ecd  add     rax, 2
0x180035ed1  dec     r9
0x180035ed4  sub     rdx, 1
0x180035ed8  jnz     short loc_180035EB6
0x180035eda  test    rdx, rdx
0x180035edd  lea     rcx, [rax-2]
0x180035ee1  mov     rdx, r14
0x180035ee4  cmovnz  rcx, rax
0x180035ee8  lea     rax, [rsp+280h+Name]
0x180035eed  mov     [rcx], si
0x180035ef0  cmp     [rax], si
0x180035ef3  jz      short loc_180035EFF
0x180035ef5  add     rax, 2
0x180035ef9  sub     rdx, 1
0x180035efd  jnz     short loc_180035EF0
0x180035eff  mov     rcx, r14
0x180035f02  mov     rax, rdx
0x180035f05  sub     rcx, rdx
0x180035f08  neg     rax
0x180035f0b  sbb     r8, r8
0x180035f0e  and     r8, rcx; pcchNewDestLength
0x180035f11  test    rdx, rdx
0x180035f14  jz      short loc_180035F31
0x180035f16  mov     rdx, r14
0x180035f19  lea     rcx, [rsp+280h+Name]
0x180035f1e  sub     rdx, r8; cchDest
0x180035f21  lea     rcx, [rcx+r8*2]; pszDest
0x180035f25  lea     r9, aP0; "_p0"
0x180035f2c  call    StringCopyWorkerW
0x180035f31  lea     r8, [rsp+280h+Name]; lpName
0x180035f36  xor     edx, edx; bInheritHandle
0x180035f38  mov     ecx, 1F0003h; dwDesiredAccess
0x180035f3d  call    cs:__imp_OpenSemaphoreW
0x180035f43  mov     [rsp+280h+var_240], rax
0x180035f48  test    rax, rax
0x180035f4b  jz      loc_18003603E
0x180035f51  lea     rdx, [rsp+280h+var_24C]; int *
0x180035f56  mov     [rsp+280h+var_24C], esi
0x180035f5a  mov     rcx, rax; hHandle
0x180035f5d  mov     [rsp+280h+var_250], esi
0x180035f61  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180035f66  mov     ebx, eax
0x180035f68  test    eax, eax
0x180035f6a  jns     short loc_180035F8C
0x180035f6c  mov     rcx, [rbp+188h]; this
0x180035f73  lea     r8, aWil; "wil"
0x180035f7a  mov     r9d, eax; char *
0x180035f7d  mov     edx, 0D6h; void *
0x180035f82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035f87  jmp     loc_18003604B
0x180035f8c  lea     r8, asc_1800DBE1C; "h"
0x180035f93  mov     rdx, r14; unsigned __int64
0x180035f96  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180035f9b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180035fa0  lea     r8, [rsp+280h+Name]; lpName
0x180035fa5  xor     edx, edx; bInheritHandle
0x180035fa7  mov     ecx, 1F0003h; dwDesiredAccess
0x180035fac  call    cs:__imp_OpenSemaphoreW
0x180035fb2  mov     [rsp+280h+var_248], rax
0x180035fb7  test    rax, rax
0x180035fba  jz      short loc_180036018
0x180035fbc  lea     rdx, [rsp+280h+var_250]; int *
0x180035fc1  mov     rcx, rax; hHandle
0x180035fc4  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180035fc9  mov     ebx, eax
0x180035fcb  test    eax, eax
0x180035fcd  jns     short loc_180035FEC
0x180035fcf  mov     rcx, [rbp+188h]; this
0x180035fd6  lea     r8, aWil; "wil"
0x180035fdd  mov     r9d, eax; char *
0x180035fe0  mov     edx, 0DEh; void *
0x180035fe5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035fea  jmp     short loc_180036032
0x180035fec  lea     rcx, [rsp+280h+var_248]
0x180035ff1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180035ff6  movsxd  rax, [rsp+280h+var_24C]
0x180035ffb  movsxd  rcx, [rsp+280h+var_250]
0x180036000  shl     rcx, 1Fh
0x180036004  or      rcx, rax
0x180036007  mov     [rdi], rcx
0x18003600a  lea     rcx, [rsp+280h+var_240]
0x18003600f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180036014  xor     eax, eax
0x180036016  jmp     short loc_180036071
0x180036018  mov     rcx, [rbp+188h]; this
0x18003601f  lea     r8, aWil; "wil"
0x180036026  mov     edx, 0DCh; void *
0x18003602b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180036030  mov     ebx, eax
0x180036032  lea     rcx, [rsp+280h+var_248]
0x180036037  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18003603c  jmp     short loc_18003604B
0x18003603e  call    cs:__imp_GetLastError
0x180036044  cmp     eax, 2
0x180036047  jnz     short loc_180036059
0x180036049  mov     ebx, esi
0x18003604b  lea     rcx, [rsp+280h+var_240]
0x180036050  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180036055  mov     eax, ebx
0x180036057  jmp     short loc_180036071
0x180036059  mov     rcx, [rbp+188h]; this
0x180036060  lea     r8, aWil; "wil"
0x180036067  mov     edx, 0D0h; void *
0x18003606c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180036071  mov     rcx, [rbp+180h+var_20]
0x180036078  xor     rcx, rsp; StackCookie
0x18003607b  call    __security_check_cookie
0x180036080  lea     r11, [rsp+280h+var_10]
0x180036088  mov     rbx, [r11+20h]
0x18003608c  mov     rsi, [r11+28h]
0x180036090  mov     rsp, r11
0x180036093  pop     r14
0x180036095  pop     rdi
0x180036096  pop     rbp
0x180036097  retn
```
