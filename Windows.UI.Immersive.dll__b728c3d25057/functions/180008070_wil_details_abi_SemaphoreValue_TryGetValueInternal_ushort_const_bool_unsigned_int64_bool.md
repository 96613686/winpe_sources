# wil::details_abi::SemaphoreValue::TryGetValueInternal(ushort const *,bool,unsigned __int64 *,bool *)

- ea: `0x180008070`
- end: `0x18000837c`
- name: `?TryGetValueInternal@SemaphoreValue@details_abi@wil@@CAJPEBG_NPEA_KPEA_N@Z`
- size: `780`
- prototype: `__int64 __fastcall(const unsigned __int16 *, bool, unsigned __int64 *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180006b3c`
- `0x180007dfc`

## callees

- `0x180008070`
- `0x180008390`
- `0x18000853c`
- `0x180008570`
- `0x180034768`
- `0x180034db4`
- `0x180050ba0`
- `0x180058aa8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008167`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000823d`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x180008167`
- `api-ms-win-core-synch-l1-1-0!OpenSemaphoreW` at `0x18000823d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008315`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008315`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000829d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800082d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000829d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800082d1`

## pseudocode

```c
__int64 __fastcall wil::details_abi::SemaphoreValue::TryGetValueInternal(
        WCHAR *a1,
        __int64 a2,
        unsigned __int64 *a3,
        bool *a4)
{
  WCHAR *v4; // r9
  __int64 v5; // rsi
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // r10
  WCHAR *v11; // rcx
  __int64 v12; // rdx
  WCHAR *v13; // rax
  __int64 v14; // rcx
  _WORD *v15; // r8
  const unsigned __int16 *v16; // r9
  _WORD *v17; // rcx
  wil::details *v18; // rax
  wil::details *v19; // rdi
  int ValueFromSemaphore; // eax
  unsigned int v21; // ebp
  WCHAR *v23; // rax
  _WORD *v24; // r8
  const unsigned __int16 *v25; // rcx
  _WORD *v26; // rdx
  wil::details *v27; // rax
  const char *v28; // r9
  wil::details *v29; // rbx
  int v30; // eax
  unsigned int v31; // esi
  void *v32; // rdx
  void *v33; // rdx
  unsigned int v34; // r8d
  const char *v35; // r9
  unsigned int v36; // r8d
  const char *v37; // r9
  unsigned int LastError; // ebx
  const char *v39; // r9
  int v40; // [rsp+20h] [rbp-258h] BYREF
  int v41; // [rsp+24h] [rbp-254h] BYREF
  wil::details *v42; // [rsp+28h] [rbp-250h] BYREF
  wil::details *v43; // [rsp+30h] [rbp-248h] BYREF
  WCHAR Name[260]; // [rsp+40h] [rbp-238h] BYREF
  _BYTE v45[8]; // [rsp+248h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+0h]

  v4 = Name;
  v5 = 2147483646;
  *a3 = 0;
  v6 = 260;
  v7 = 2147483646;
  v8 = 260;
  do
  {
    if ( !v7 )
      break;
    if ( !*a1 )
      break;
    *v4++ = *a1++;
    --v7;
    --v8;
  }
  while ( v8 );
  v11 = v4 - 1;
  v12 = 260;
  v13 = Name;
  if ( v8 )
    v11 = v4;
  *v11 = 0;
  while ( *v13 )
  {
    ++v13;
    if ( !--v12 )
      goto LABEL_18;
  }
  v14 = 2147483646;
  v15 = &v45[-2 * v12];
  v16 = L"_p0";
  do
  {
    if ( !v14 )
      break;
    if ( !*v16 )
      break;
    *v15++ = *v16++;
    --v14;
    --v12;
  }
  while ( v12 );
  v17 = v15 - 1;
  if ( v12 )
    v17 = v15;
  *v17 = 0;
LABEL_18:
  v18 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
  v42 = v18;
  v19 = v18;
  if ( v18 )
  {
    v41 = 0;
    v40 = 0;
    ValueFromSemaphore = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v18, &v41);
    v21 = ValueFromSemaphore;
    if ( ValueFromSemaphore < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD6,
        (unsigned int)"wil",
        (const char *)(unsigned int)ValueFromSemaphore,
        v40);
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v42);
      return v21;
    }
    v23 = Name;
    while ( *v23 )
    {
      ++v23;
      if ( !--v6 )
        goto LABEL_32;
    }
    v24 = &v45[-2 * v6];
    v25 = L"h";
    do
    {
      if ( !v5 )
        break;
      if ( !*v25 )
        break;
      *v24++ = *v25++;
      --v5;
      --v6;
    }
    while ( v6 );
    v26 = v24 - 1;
    if ( v6 )
      v26 = v24;
    *v26 = 0;
LABEL_32:
    v27 = (wil::details *)OpenSemaphoreW(0x1F0003u, 0, Name);
    v43 = v27;
    v29 = v27;
    if ( v27 )
    {
      v30 = wil::details_abi::SemaphoreValue::GetValueFromSemaphore(v27, &v40);
      v31 = v30;
      if ( v30 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xDE,
          (unsigned int)"wil",
          (const char *)(unsigned int)v30,
          v40);
        wil::details::CloseHandle(v29, v32);
        wil::details::CloseHandle(v19, v33);
        return v31;
      }
      if ( !CloseHandle(v29) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v34, v35);
      *a3 = v41 | (unsigned __int64)((__int64)v40 << 31);
      if ( !CloseHandle(v19) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v36, v37);
      return 0;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xDC, (unsigned int)"wil", v28);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v43);
  }
  else
  {
    if ( GetLastError() == 2 )
      return 0;
    LastError = wil::details::in1diag3::Return_GetLastError(retaddr, (void *)0xD0, (unsigned int)"wil", v39);
  }
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v42);
  return LastError;
}

```

## disassembly

```asm
0x180008070  mov     [rsp+arg_8], rbx
0x180008075  mov     [rsp+arg_18], rsi
0x18000807a  push    rdi
0x18000807b  push    r14
0x18000807d  push    r15
0x18000807f  sub     rsp, 260h
0x180008086  mov     rax, cs:__security_cookie
0x18000808d  xor     rax, rsp
0x180008090  mov     [rsp+278h+var_28], rax
0x180008098  xor     r15d, r15d
0x18000809b  lea     r9, [rsp+278h+Name]
0x1800080a0  mov     esi, 7FFFFFFEh
0x1800080a5  mov     [r8], r15
0x1800080a8  mov     ebx, 104h
0x1800080ad  mov     eax, esi
0x1800080af  mov     r10d, ebx
0x1800080b2  mov     r14, r8
0x1800080b5  mov     rdx, rcx
0x1800080b8  test    rax, rax
0x1800080bb  jz      short loc_1800080DA
0x1800080bd  movzx   ecx, word ptr [rdx]
0x1800080c0  test    cx, cx
0x1800080c3  jz      short loc_1800080DA
0x1800080c5  mov     [r9], cx
0x1800080c9  add     rdx, 2
0x1800080cd  add     r9, 2
0x1800080d1  dec     rax
0x1800080d4  sub     r10, 1
0x1800080d8  jnz     short loc_1800080B8
0x1800080da  test    r10, r10
0x1800080dd  lea     rcx, [r9-2]
0x1800080e1  mov     rdx, rbx
0x1800080e4  lea     rax, [rsp+278h+Name]
0x1800080e9  cmovnz  rcx, r9
0x1800080ed  mov     [rcx], r15w
0x1800080f1  cmp     [rax], r15w
0x1800080f5  jz      short loc_180008103
0x1800080f7  add     rax, 2
0x1800080fb  sub     rdx, 1
0x1800080ff  jnz     short loc_1800080F1
0x180008101  jmp     short loc_180008153
0x180008103  lea     rax, [rdx+rdx]
0x180008107  mov     rcx, rsi
0x18000810a  lea     r8, [rsp+278h+var_30]
0x180008112  sub     r8, rax
0x180008115  lea     r9, aP0; "_p0"
0x18000811c  test    rdx, rdx
0x18000811f  jz      short loc_180008144
0x180008121  test    rcx, rcx
0x180008124  jz      short loc_180008144
0x180008126  movzx   eax, word ptr [r9]
0x18000812a  test    ax, ax
0x18000812d  jz      short loc_180008144
0x18000812f  mov     [r8], ax
0x180008133  add     r9, 2
0x180008137  add     r8, 2
0x18000813b  dec     rcx
0x18000813e  sub     rdx, 1
0x180008142  jnz     short loc_180008121
0x180008144  test    rdx, rdx
0x180008147  lea     rcx, [r8-2]
0x18000814b  cmovnz  rcx, r8
0x18000814f  mov     [rcx], r15w
0x180008153  lea     r8, [rsp+278h+Name]; lpName
0x180008158  mov     [rsp+278h+arg_0], rbp
0x180008160  xor     edx, edx; bInheritHandle
0x180008162  mov     ecx, 1F0003h; dwDesiredAccess
0x180008167  call    cs:__imp_OpenSemaphoreW
0x18000816d  mov     [rsp+278h+var_250], rax
0x180008172  mov     rdi, rax
0x180008175  test    rax, rax
0x180008178  jz      loc_180008315
0x18000817e  lea     rdx, [rsp+278h+var_254]; int *
0x180008183  mov     [rsp+278h+var_254], r15d
0x180008188  mov     rcx, rax; hHandle
0x18000818b  mov     [rsp+278h+var_258], r15d; int
0x180008190  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008195  mov     ebp, eax
0x180008197  test    eax, eax
0x180008199  jns     short loc_1800081C8
0x18000819b  mov     rcx, [rsp+278h]; this
0x1800081a3  lea     r8, aWil; "wil"
0x1800081aa  mov     r9d, eax; char *
0x1800081ad  mov     edx, 0D6h; void *
0x1800081b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800081b7  lea     rcx, [rsp+278h+var_250]
0x1800081bc  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x1800081c1  mov     eax, ebp
0x1800081c3  jmp     loc_18000834B
0x1800081c8  lea     rax, [rsp+278h+Name]
0x1800081cd  nop     dword ptr [rax]
0x1800081d0  cmp     [rax], r15w
0x1800081d4  jz      short loc_1800081E2
0x1800081d6  add     rax, 2
0x1800081da  sub     rbx, 1
0x1800081de  jnz     short loc_1800081D0
0x1800081e0  jmp     short loc_180008231
0x1800081e2  lea     rax, [rbx+rbx]
0x1800081e6  lea     r8, [rsp+278h+var_30]
0x1800081ee  sub     r8, rax
0x1800081f1  lea     rcx, asc_1800FD680; "h"
0x1800081f8  test    rbx, rbx
0x1800081fb  jz      short loc_180008222
0x1800081fd  nop     dword ptr [rax]
0x180008200  test    rsi, rsi
0x180008203  jz      short loc_180008222
0x180008205  movzx   eax, word ptr [rcx]
0x180008208  test    ax, ax
0x18000820b  jz      short loc_180008222
0x18000820d  mov     [r8], ax
0x180008211  add     rcx, 2
0x180008215  add     r8, 2
0x180008219  dec     rsi
0x18000821c  sub     rbx, 1
0x180008220  jnz     short loc_180008200
0x180008222  test    rbx, rbx
0x180008225  lea     rdx, [r8-2]
0x180008229  cmovnz  rdx, r8
0x18000822d  mov     [rdx], r15w
0x180008231  lea     r8, [rsp+278h+Name]; lpName
0x180008236  xor     edx, edx; bInheritHandle
0x180008238  mov     ecx, 1F0003h; dwDesiredAccess
0x18000823d  call    cs:__imp_OpenSemaphoreW
0x180008243  mov     [rsp+278h+var_248], rax
0x180008248  mov     rbx, rax
0x18000824b  test    rax, rax
0x18000824e  jz      loc_1800082EE
0x180008254  lea     rdx, [rsp+278h+var_258]; int *
0x180008259  mov     rcx, rax; hHandle
0x18000825c  call    ?GetValueFromSemaphore@SemaphoreValue@details_abi@wil@@CAJPEAXPEAJ@Z; wil::details_abi::SemaphoreValue::GetValueFromSemaphore(void *,long *)
0x180008261  mov     esi, eax
0x180008263  test    eax, eax
0x180008265  jns     short loc_18000829A
0x180008267  mov     rcx, [rsp+278h]; this
0x18000826f  lea     r8, aWil; "wil"
0x180008276  mov     r9d, eax; char *
0x180008279  mov     edx, 0DEh; void *
0x18000827e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008283  mov     rcx, rbx; this
0x180008286  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000828b  mov     rcx, rdi; this
0x18000828e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180008293  mov     eax, esi
0x180008295  jmp     loc_18000834B
0x18000829a  mov     rcx, rbx; hObject
0x18000829d  call    cs:__imp_CloseHandle
0x1800082a3  test    eax, eax
0x1800082a5  jnz     short loc_1800082BA
0x1800082a7  mov     rcx, [rsp+278h]; this
0x1800082af  mov     edx, 0A0Bh; void *
0x1800082b4  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800082ba  movsxd  rax, [rsp+278h+var_254]
0x1800082bf  movsxd  rcx, [rsp+278h+var_258]
0x1800082c4  shl     rcx, 1Fh
0x1800082c8  or      rcx, rax
0x1800082cb  mov     [r14], rcx
0x1800082ce  mov     rcx, rdi; hObject
0x1800082d1  call    cs:__imp_CloseHandle
0x1800082d7  test    eax, eax
0x1800082d9  jnz     short loc_180008320
0x1800082db  mov     rcx, [rsp+278h]; this
0x1800082e3  mov     edx, 0A0Bh; void *
0x1800082e8  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800082ee  mov     rcx, [rsp+278h]; this
0x1800082f6  lea     r8, aWil; "wil"
0x1800082fd  mov     edx, 0DCh; void *
0x180008302  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180008307  lea     rcx, [rsp+278h+var_248]
0x18000830c  mov     ebx, eax
0x18000830e  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008313  jmp     short loc_18000833F
0x180008315  call    cs:__imp_GetLastError
0x18000831b  cmp     eax, 2
0x18000831e  jnz     short loc_180008324
0x180008320  xor     eax, eax
0x180008322  jmp     short loc_18000834B
0x180008324  mov     rcx, [rsp+278h]; this
0x18000832c  lea     r8, aWil; "wil"
0x180008333  mov     edx, 0D0h; void *
0x180008338  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000833d  mov     ebx, eax
0x18000833f  lea     rcx, [rsp+278h+var_250]
0x180008344  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180008349  mov     eax, ebx
0x18000834b  mov     rbp, [rsp+278h+arg_0]
0x180008353  mov     rcx, [rsp+278h+var_28]
0x18000835b  xor     rcx, rsp; StackCookie
0x18000835e  call    __security_check_cookie
0x180008363  lea     r11, [rsp+278h+var_18]
0x18000836b  mov     rbx, [r11+28h]
0x18000836f  mov     rsi, [r11+38h]
0x180008373  mov     rsp, r11
0x180008376  pop     r15
0x180008378  pop     r14
0x18000837a  pop     rdi
0x18000837b  retn
```
