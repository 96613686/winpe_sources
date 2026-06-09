# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180061514`
- end: `0x180061708`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `500`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002f5c0`
- `0x180061478`

## callees

- `0x180045264`
- `0x1800614e4`
- `0x180061514`
- `0x180061710`
- `0x180061c98`
- `0x180061fb4`
- `0x18006d43c`
- `0x180075e60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800615e5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180061646`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x1800615e5`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180061646`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800616bc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800616bc`

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
  unsigned int v15; // edx
  int v16; // r9d
  unsigned int LastError; // ebx
  HANDLE v18; // rax
  unsigned int v19; // edx
  const char *v20; // r8
  int v21; // eax
  unsigned int v22; // edx
  int v23; // r9d
  unsigned int v25; // edx
  const char *v26; // r8
  size_t v27; // [rsp+20h] [rbp-E0h]
  int v28; // [rsp+30h] [rbp-D0h] BYREF
  int v29; // [rsp+34h] [rbp-CCh] BYREF
  HANDLE v30; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v31[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-B0h] BYREF

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
    StringCopyWorkerW(&Name[v12], 260 - v12, (size_t *)v12, L"_p0", v27);
  }
  v13 = OpenSemaphoreW(0x1F0003u, 0, Name);
  v31[0] = v13;
  if ( v13 )
  {
    v29 = 0;
    v28 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v13, &v29);
    LastError = ValueFromSemaphore;
    if ( ValueFromSemaphore >= 0 )
    {
      StringCchCatW(Name, 0x104u, L"h");
      v18 = OpenSemaphoreW(0x1F0003u, 0, Name);
      v30 = v18;
      if ( v18 )
      {
        v21 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v28);
        LastError = v21;
        if ( v21 >= 0 )
        {
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v30);
          *a3 = v29 | (unsigned __int64)((__int64)v28 << 31);
          __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v31);
          return 0;
        }
        wil::details::in1diag3::Return_Hr((wil::details::in1diag3 *)0xDE, v22, (const char *)(unsigned int)v21, v23);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError((wil::details::in1diag3 *)0xDC, v19, v20);
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v30);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        (wil::details::in1diag3 *)0xD6,
        v15,
        (const char *)(unsigned int)ValueFromSemaphore,
        v16);
    }
    goto LABEL_23;
  }
  if ( GetLastError() == 2 )
  {
    LastError = 0;
LABEL_23:
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(v31);
    return LastError;
  }
  return wil::details::in1diag3::Return_GetLastError((wil::details::in1diag3 *)0xD0, v25, v26);
}

```

## disassembly

```asm
0x180061514  mov     [rsp-8+arg_0], rbx
0x180061519  mov     [rsp-8+arg_8], rsi
0x18006151e  push    rbp
0x18006151f  push    rdi
0x180061520  push    r14
0x180061522  lea     rbp, [rsp-170h]
0x18006152a  sub     rsp, 270h
0x180061531  mov     rax, cs:__security_cookie
0x180061538  xor     rax, rsp
0x18006153b  mov     [rbp+180h+var_20], rax
0x180061542  xor     esi, esi
0x180061544  lea     rax, [rsp+280h+Name]
0x180061549  mov     r14d, 104h
0x18006154f  mov     [r8], rsi
0x180061552  mov     edx, r14d
0x180061555  mov     rdi, r8
0x180061558  mov     r9d, 7FFFFFFEh
0x18006155e  test    r9, r9
0x180061561  jz      short loc_180061582
0x180061563  movzx   r8d, word ptr [rcx]
0x180061567  test    r8w, r8w
0x18006156b  jz      short loc_180061582
0x18006156d  mov     [rax], r8w
0x180061571  add     rcx, 2
0x180061575  add     rax, 2
0x180061579  dec     r9
0x18006157c  sub     rdx, 1
0x180061580  jnz     short loc_18006155E
0x180061582  test    rdx, rdx
0x180061585  lea     rcx, [rax-2]
0x180061589  mov     rdx, r14
0x18006158c  cmovnz  rcx, rax
0x180061590  lea     rax, [rsp+280h+Name]
0x180061595  mov     [rcx], si
0x180061598  cmp     [rax], si
0x18006159b  jz      short loc_1800615A7
0x18006159d  add     rax, 2
0x1800615a1  sub     rdx, 1
0x1800615a5  jnz     short loc_180061598
0x1800615a7  mov     rcx, r14
0x1800615aa  mov     rax, rdx
0x1800615ad  sub     rcx, rdx
0x1800615b0  neg     rax
0x1800615b3  sbb     r8, r8
0x1800615b6  and     r8, rcx; pcchNewDestLength
0x1800615b9  test    rdx, rdx
0x1800615bc  jz      short loc_1800615D9
0x1800615be  mov     rdx, r14
0x1800615c1  lea     rcx, [rsp+280h+Name]
0x1800615c6  sub     rdx, r8; cchDest
0x1800615c9  lea     rcx, [rcx+r8*2]; pszDest
0x1800615cd  lea     r9, aP0; "_p0"
0x1800615d4  call    StringCopyWorkerW
0x1800615d9  lea     r8, [rsp+280h+Name]; lpName
0x1800615de  xor     edx, edx; bInheritHandle
0x1800615e0  mov     ecx, 1F0003h; dwDesiredAccess
0x1800615e5  call    cs:__imp_OpenSemaphoreW
0x1800615eb  mov     [rsp+280h+var_240], rax
0x1800615f0  test    rax, rax
0x1800615f3  jz      loc_1800616BC
0x1800615f9  lea     rdx, [rsp+280h+var_24C]; int *
0x1800615fe  mov     [rsp+280h+var_24C], esi
0x180061602  mov     rcx, rax; hHandle
0x180061605  mov     [rsp+280h+var_250], esi
0x180061609  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18006160e  mov     ebx, eax
0x180061610  test    eax, eax
0x180061612  jns     short loc_180061626
0x180061614  mov     r8d, eax; char *
0x180061617  mov     ecx, 0D6h; this
0x18006161c  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x180061621  jmp     loc_1800616C9
0x180061626  lea     r8, asc_1800C9AE8; "h"
0x18006162d  mov     rdx, r14; unsigned __int64
0x180061630  lea     rcx, [rsp+280h+Name]; unsigned __int16 *
0x180061635  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18006163a  lea     r8, [rsp+280h+Name]; lpName
0x18006163f  xor     edx, edx; bInheritHandle
0x180061641  mov     ecx, 1F0003h; dwDesiredAccess
0x180061646  call    cs:__imp_OpenSemaphoreW
0x18006164c  mov     [rsp+280h+var_248], rax
0x180061651  test    rax, rax
0x180061654  jz      short loc_1800616A4
0x180061656  lea     rdx, [rsp+280h+var_250]; int *
0x18006165b  mov     rcx, rax; hHandle
0x18006165e  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180061663  mov     ebx, eax
0x180061665  test    eax, eax
0x180061667  jns     short loc_180061678
0x180061669  mov     r8d, eax; char *
0x18006166c  mov     ecx, 0DEh; this
0x180061671  call    ?Return_Hr@in1diag3@details@wil@@YAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(uint,char const *,long)
0x180061676  jmp     short loc_1800616B0
0x180061678  lea     rcx, [rsp+280h+var_248]
0x18006167d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180061682  movsxd  rax, [rsp+280h+var_24C]
0x180061687  movsxd  rcx, [rsp+280h+var_250]
0x18006168c  shl     rcx, 1Fh
0x180061690  or      rcx, rax
0x180061693  mov     [rdi], rcx
0x180061696  lea     rcx, [rsp+280h+var_240]
0x18006169b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800616a0  xor     eax, eax
0x1800616a2  jmp     short loc_1800616E1
0x1800616a4  mov     ecx, 0DCh; this
0x1800616a9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJIPEBD@Z; wil::details::in1diag3::Return_GetLastError(uint,char const *)
0x1800616ae  mov     ebx, eax
0x1800616b0  lea     rcx, [rsp+280h+var_248]
0x1800616b5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800616ba  jmp     short loc_1800616C9
0x1800616bc  call    cs:__imp_GetLastError
0x1800616c2  cmp     eax, 2
0x1800616c5  jnz     short loc_1800616D7
0x1800616c7  mov     ebx, esi
0x1800616c9  lea     rcx, [rsp+280h+var_240]
0x1800616ce  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800616d3  mov     eax, ebx
0x1800616d5  jmp     short loc_1800616E1
0x1800616d7  mov     ecx, 0D0h; this
0x1800616dc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJIPEBD@Z; wil::details::in1diag3::Return_GetLastError(uint,char const *)
0x1800616e1  mov     rcx, [rbp+180h+var_20]
0x1800616e8  xor     rcx, rsp; StackCookie
0x1800616eb  call    __security_check_cookie
0x1800616f0  lea     r11, [rsp+280h+var_10]
0x1800616f8  mov     rbx, [r11+20h]
0x1800616fc  mov     rsi, [r11+28h]
0x180061700  mov     rsp, r11
0x180061703  pop     r14
0x180061705  pop     rdi
0x180061706  pop     rbp
0x180061707  retn
```
