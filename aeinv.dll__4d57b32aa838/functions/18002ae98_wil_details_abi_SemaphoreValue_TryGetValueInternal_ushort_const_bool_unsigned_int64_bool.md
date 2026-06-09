# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x18002ae98`
- end: `0x18002b0ab`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `531`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x18002ab5c`
- `0x18003f100`

## callees

- `0x180007420`
- `0x18002ae98`
- `0x18003f184`
- `0x18003f424`
- `0x180048fdc`
- `0x18004f970`
- `0x180059920`
- `0x180112a1c`

## import_xrefs

- `KERNEL32!OpenSemaphoreW` at `0x18002af5f`
- `KERNEL32!OpenSemaphoreW` at `0x18002afcb`
- `KERNEL32!OpenSemaphoreW` at `0x18002af5f`
- `KERNEL32!OpenSemaphoreW` at `0x18002afcb`
- `KERNEL32!GetLastError` at `0x18002b05d`
- `KERNEL32!GetLastError` at `0x18002b05d`

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
  __int64 v14; // rdx
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
    StringCopyWorkerW(&Name[v11], 260 - v11, 0, L"_p0", v21);
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
0x18002ae98  push    rbp
0x18002ae9a  push    rbx
0x18002ae9b  push    rsi
0x18002ae9c  push    rdi
0x18002ae9d  lea     rbp, [rsp-178h]
0x18002aea5  sub     rsp, 278h
0x18002aeac  mov     rax, cs:__security_cookie
0x18002aeb3  xor     rax, rsp
0x18002aeb6  mov     [rbp+190h+var_30], rax
0x18002aebd  xor     esi, esi
0x18002aebf  lea     rax, [rsp+290h+Name]
0x18002aec4  mov     edx, 104h
0x18002aec9  mov     [r8], rsi
0x18002aecc  mov     r9d, edx
0x18002aecf  mov     rdi, r8
0x18002aed2  mov     r10d, 7FFFFFFEh
0x18002aed8  test    r10, r10
0x18002aedb  jz      short loc_18002AEFC
0x18002aedd  movzx   r8d, word ptr [rcx]
0x18002aee1  test    r8w, r8w
0x18002aee5  jz      short loc_18002AEFC
0x18002aee7  mov     [rax], r8w
0x18002aeeb  add     rcx, 2
0x18002aeef  add     rax, 2
0x18002aef3  dec     r10
0x18002aef6  sub     r9, 1
0x18002aefa  jnz     short loc_18002AED8
0x18002aefc  lea     rcx, [rax-2]
0x18002af00  test    r9, r9
0x18002af03  mov     r8, rdx
0x18002af06  cmovnz  rcx, rax
0x18002af0a  lea     rax, [rsp+290h+Name]
0x18002af0f  mov     [rcx], si
0x18002af12  cmp     [rax], si
0x18002af15  jz      short loc_18002AF21
0x18002af17  add     rax, 2
0x18002af1b  sub     r8, 1
0x18002af1f  jnz     short loc_18002AF12
0x18002af21  mov     rcx, rdx
0x18002af24  mov     rax, r8
0x18002af27  sub     rcx, r8
0x18002af2a  neg     rax
0x18002af2d  sbb     r9, r9
0x18002af30  and     r9, rcx
0x18002af33  test    r8, r8
0x18002af36  jz      short loc_18002AF53
0x18002af38  sub     rdx, r9; cchDest
0x18002af3b  lea     rcx, [rsp+290h+Name]
0x18002af40  lea     rcx, [rcx+r9*2]; pszDest
0x18002af44  xor     r8d, r8d; pcchNewDestLength
0x18002af47  lea     r9, aP0; "_p0"
0x18002af4e  call    StringCopyWorkerW
0x18002af53  lea     r8, [rsp+290h+Name]; lpName
0x18002af58  xor     edx, edx; bInheritHandle
0x18002af5a  mov     ecx, 1F0003h; dwDesiredAccess
0x18002af5f  call    cs:__imp_OpenSemaphoreW
0x18002af65  mov     [rsp+290h+var_250], rax
0x18002af6a  test    rax, rax
0x18002af6d  jz      loc_18002B05D
0x18002af73  lea     rdx, [rsp+290h+var_25C]; int *
0x18002af78  mov     [rsp+290h+var_25C], esi
0x18002af7c  mov     rcx, rax; hHandle
0x18002af7f  mov     [rsp+290h+var_260], esi
0x18002af83  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002af88  mov     ebx, eax
0x18002af8a  test    eax, eax
0x18002af8c  jns     short loc_18002AFAE
0x18002af8e  mov     rcx, [rbp+198h]; this
0x18002af95  lea     r8, aWil; "wil"
0x18002af9c  mov     r9d, eax; char *
0x18002af9f  mov     edx, 0D6h; void *
0x18002afa4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002afa9  jmp     loc_18002B06A
0x18002afae  lea     r8, asc_18013B62C; "h"
0x18002afb5  lea     rcx, [rsp+290h+Name]; unsigned __int16 *
0x18002afba  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002afbf  lea     r8, [rsp+290h+Name]; lpName
0x18002afc4  xor     edx, edx; bInheritHandle
0x18002afc6  mov     ecx, 1F0003h; dwDesiredAccess
0x18002afcb  call    cs:__imp_OpenSemaphoreW
0x18002afd1  mov     [rsp+290h+var_258], rax
0x18002afd6  test    rax, rax
0x18002afd9  jz      short loc_18002B037
0x18002afdb  lea     rdx, [rsp+290h+var_260]; int *
0x18002afe0  mov     rcx, rax; hHandle
0x18002afe3  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18002afe8  mov     ebx, eax
0x18002afea  test    eax, eax
0x18002afec  jns     short loc_18002B00B
0x18002afee  mov     rcx, [rbp+198h]; this
0x18002aff5  lea     r8, aWil; "wil"
0x18002affc  mov     r9d, eax; char *
0x18002afff  mov     edx, 0DEh; void *
0x18002b004  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002b009  jmp     short loc_18002B051
0x18002b00b  lea     rcx, [rsp+290h+var_258]
0x18002b010  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002b015  movsxd  rax, [rsp+290h+var_25C]
0x18002b01a  movsxd  rcx, [rsp+290h+var_260]
0x18002b01f  shl     rcx, 1Fh
0x18002b023  or      rcx, rax
0x18002b026  mov     [rdi], rcx
0x18002b029  lea     rcx, [rsp+290h+var_250]
0x18002b02e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002b033  xor     eax, eax
0x18002b035  jmp     short loc_18002B090
0x18002b037  mov     rcx, [rbp+198h]; this
0x18002b03e  lea     r8, aWil; "wil"
0x18002b045  mov     edx, 0DCh; void *
0x18002b04a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002b04f  mov     ebx, eax
0x18002b051  lea     rcx, [rsp+290h+var_258]
0x18002b056  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002b05b  jmp     short loc_18002B06A
0x18002b05d  call    cs:__imp_GetLastError
0x18002b063  cmp     eax, 2
0x18002b066  jnz     short loc_18002B078
0x18002b068  mov     ebx, esi
0x18002b06a  lea     rcx, [rsp+290h+var_250]
0x18002b06f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18002b074  mov     eax, ebx
0x18002b076  jmp     short loc_18002B090
0x18002b078  mov     rcx, [rbp+198h]; this
0x18002b07f  lea     r8, aWil; "wil"
0x18002b086  mov     edx, 0D0h; void *
0x18002b08b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18002b090  mov     rcx, [rbp+190h+var_30]
0x18002b097  xor     rcx, rsp; StackCookie
0x18002b09a  call    __security_check_cookie
0x18002b09f  add     rsp, 278h
0x18002b0a6  pop     rdi
0x18002b0a7  pop     rsi
0x18002b0a8  pop     rbx
0x18002b0a9  pop     rbp
0x18002b0aa  retn
```
