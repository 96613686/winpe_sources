# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180009fc0`
- end: `0x18000a21e`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `606`
- prototype: `__int64 __fastcall(WCHAR *, __int64, unsigned __int64 *, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180011c60`

## callees

- `0x180009fc0`
- `0x18000a224`
- `0x18000a2ec`
- `0x18000a934`
- `0x18000a9cc`
- `0x180010438`
- `0x18001a380`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a0c3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a132`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a0c3`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000a132`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a1c4`

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
0x180009fc0  mov     [rsp-8+arg_0], rbx
0x180009fc5  mov     [rsp-8+arg_8], rsi
0x180009fca  push    rbp
0x180009fcb  push    rdi
0x180009fcc  push    r15
0x180009fce  lea     rbp, [rsp-160h]
0x180009fd6  sub     rsp, 260h
0x180009fdd  mov     rax, cs:__security_cookie
0x180009fe4  xor     rax, rsp
0x180009fe7  mov     [rbp+170h+var_20], rax
0x180009fee  xor     esi, esi
0x180009ff0  lea     rax, [rsp+270h+Name]
0x180009ff5  mov     r10d, 7FFFFFFEh
0x180009ffb  mov     [r8], rsi
0x180009ffe  mov     r15d, 104h
0x18000a004  mov     r9d, r10d
0x18000a007  mov     edx, r15d
0x18000a00a  mov     rdi, r8
0x18000a00d  test    r9, r9
0x18000a010  jz      short loc_18000A031
0x18000a012  movzx   r8d, word ptr [rcx]
0x18000a016  test    r8w, r8w
0x18000a01a  jz      short loc_18000A031
0x18000a01c  mov     [rax], r8w
0x18000a020  add     rcx, 2
0x18000a024  add     rax, 2
0x18000a028  dec     r9
0x18000a02b  sub     rdx, 1
0x18000a02f  jnz     short loc_18000A00D
0x18000a031  test    rdx, rdx
0x18000a034  lea     rcx, [rax-2]
0x18000a038  mov     rdx, r15
0x18000a03b  cmovnz  rcx, rax
0x18000a03f  lea     rax, [rsp+270h+Name]
0x18000a044  mov     [rcx], si
0x18000a047  cmp     [rax], si
0x18000a04a  jz      short loc_18000A056
0x18000a04c  add     rax, 2
0x18000a050  sub     rdx, 1
0x18000a054  jnz     short loc_18000A047
0x18000a056  mov     rcx, r15
0x18000a059  mov     rax, rdx
0x18000a05c  sub     rcx, rdx
0x18000a05f  neg     rax
0x18000a062  sbb     r8, r8
0x18000a065  and     r8, rcx
0x18000a068  test    rdx, rdx
0x18000a06b  jz      short loc_18000A0B7
0x18000a06d  mov     rax, r15
0x18000a070  lea     rdx, [rsp+270h+Name]
0x18000a075  lea     rcx, aP0; "_p0"
0x18000a07c  lea     rdx, [rdx+r8*2]
0x18000a080  sub     rax, r8
0x18000a083  jz      short loc_18000A0A9
0x18000a085  test    r10, r10
0x18000a088  jz      short loc_18000A0A9
0x18000a08a  movzx   r8d, word ptr [rcx]
0x18000a08e  test    r8w, r8w
0x18000a092  jz      short loc_18000A0A9
0x18000a094  mov     [rdx], r8w
0x18000a098  add     rcx, 2
0x18000a09c  add     rdx, 2
0x18000a0a0  dec     r10
0x18000a0a3  sub     rax, 1
0x18000a0a7  jnz     short loc_18000A085
0x18000a0a9  test    rax, rax
0x18000a0ac  lea     rcx, [rdx-2]
0x18000a0b0  cmovnz  rcx, rdx
0x18000a0b4  mov     [rcx], si
0x18000a0b7  lea     r8, [rsp+270h+Name]; lpName
0x18000a0bc  xor     edx, edx; bInheritHandle
0x18000a0be  mov     ecx, 1F0003h; dwDesiredAccess
0x18000a0c3  call    cs:__imp_OpenSemaphoreW
0x18000a0c9  mov     [rsp+270h+var_240], rax
0x18000a0ce  test    rax, rax
0x18000a0d1  jz      loc_18000A1C4
0x18000a0d7  lea     rdx, [rsp+270h+var_24C]; int *
0x18000a0dc  mov     [rsp+270h+var_24C], esi
0x18000a0e0  mov     rcx, rax; hHandle
0x18000a0e3  mov     [rsp+270h+var_250], esi; int
0x18000a0e7  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a0ec  mov     ebx, eax
0x18000a0ee  test    eax, eax
0x18000a0f0  jns     short loc_18000A112
0x18000a0f2  mov     rcx, [rbp+178h]; this
0x18000a0f9  lea     r8, aWil; "wil"
0x18000a100  mov     r9d, eax; char *
0x18000a103  mov     edx, 0D6h; void *
0x18000a108  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a10d  jmp     loc_18000A1D1
0x18000a112  lea     r8, asc_18001E6F4; "h"
0x18000a119  mov     rdx, r15; unsigned __int64
0x18000a11c  lea     rcx, [rsp+270h+Name]; unsigned __int16 *
0x18000a121  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000a126  lea     r8, [rsp+270h+Name]; lpName
0x18000a12b  xor     edx, edx; bInheritHandle
0x18000a12d  mov     ecx, 1F0003h; dwDesiredAccess
0x18000a132  call    cs:__imp_OpenSemaphoreW
0x18000a138  mov     [rsp+270h+var_248], rax
0x18000a13d  test    rax, rax
0x18000a140  jz      short loc_18000A19E
0x18000a142  lea     rdx, [rsp+270h+var_250]; int *
0x18000a147  mov     rcx, rax; hHandle
0x18000a14a  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x18000a14f  mov     ebx, eax
0x18000a151  test    eax, eax
0x18000a153  jns     short loc_18000A172
0x18000a155  mov     rcx, [rbp+178h]; this
0x18000a15c  lea     r8, aWil; "wil"
0x18000a163  mov     r9d, eax; char *
0x18000a166  mov     edx, 0DEh; void *
0x18000a16b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a170  jmp     short loc_18000A1B8
0x18000a172  lea     rcx, [rsp+270h+var_248]
0x18000a177  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a17c  movsxd  rax, [rsp+270h+var_24C]
0x18000a181  movsxd  rcx, [rsp+270h+var_250]
0x18000a186  shl     rcx, 1Fh
0x18000a18a  or      rcx, rax
0x18000a18d  mov     [rdi], rcx
0x18000a190  lea     rcx, [rsp+270h+var_240]
0x18000a195  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a19a  xor     eax, eax
0x18000a19c  jmp     short loc_18000A1F7
0x18000a19e  mov     rcx, [rbp+178h]; this
0x18000a1a5  lea     r8, aWil; "wil"
0x18000a1ac  mov     edx, 0DCh; void *
0x18000a1b1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a1b6  mov     ebx, eax
0x18000a1b8  lea     rcx, [rsp+270h+var_248]
0x18000a1bd  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a1c2  jmp     short loc_18000A1D1
0x18000a1c4  call    cs:__imp_GetLastError
0x18000a1ca  cmp     eax, 2
0x18000a1cd  jnz     short loc_18000A1DF
0x18000a1cf  mov     ebx, esi
0x18000a1d1  lea     rcx, [rsp+270h+var_240]
0x18000a1d6  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18000a1db  mov     eax, ebx
0x18000a1dd  jmp     short loc_18000A1F7
0x18000a1df  mov     rcx, [rbp+178h]; this
0x18000a1e6  lea     r8, aWil; "wil"
0x18000a1ed  mov     edx, 0D0h; void *
0x18000a1f2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000a1f7  mov     rcx, [rbp+170h+var_20]
0x18000a1fe  xor     rcx, rsp; StackCookie
0x18000a201  call    __security_check_cookie
0x18000a206  lea     r11, [rsp+270h+var_10]
0x18000a20e  mov     rbx, [r11+20h]
0x18000a212  mov     rsi, [r11+28h]
0x18000a216  mov     rsp, r11
0x18000a219  pop     r15
0x18000a21b  pop     rdi
0x18000a21c  pop     rbp
0x18000a21d  retn
```
