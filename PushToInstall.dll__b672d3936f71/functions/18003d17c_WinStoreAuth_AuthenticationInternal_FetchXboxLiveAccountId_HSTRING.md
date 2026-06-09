# WinStoreAuth::AuthenticationInternal::FetchXboxLiveAccountId(HSTRING__ * *)

- ea: `0x18003d17c`
- end: `0x18003d565`
- name: `?FetchXboxLiveAccountId@AuthenticationInternal@WinStoreAuth@@YAJPEAPEAUHSTRING__@@@Z`
- size: `1001`
- prototype: `__int64 __fastcall(HSTRING *string, HSTRING *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003ef6c`

## callees

- `0x180010b84`
- `0x18003d17c`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d34e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d328`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d34e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d33b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d361`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d33b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003d361`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d42e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18003d42e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003d1c1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18003d1c1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d333`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d359`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d4c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d4d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d53e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d54e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d333`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d359`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d4c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d4d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d53e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d54e`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall WinStoreAuth::AuthenticationInternal::FetchXboxLiveAccountId(HSTRING *string, HSTRING *a2)
{
  HRESULT v3; // eax
  unsigned int v4; // ebx
  LPVOID v5; // rcx
  int v6; // eax
  __int64 v7; // rcx
  LPVOID v8; // rcx
  int v9; // eax
  __int64 v10; // rcx
  LPVOID v11; // rcx
  LPVOID v12; // rsi
  __int64 (__fastcall *v13)(LPVOID, PCNZWCH *, LPVOID *); // r14
  void *v14; // rdi
  DWORD LastError; // ebx
  WCHAR *v16; // rdi
  DWORD v17; // ebx
  int v18; // eax
  __int64 v19; // rcx
  LPVOID v20; // rcx
  __int64 v21; // rcx
  PCNZWCH v22; // rax
  HRESULT v23; // eax
  __int64 v24; // rcx
  LPVOID v25; // rcx
  __int64 v26; // rcx
  LPVOID v27; // rcx
  __int64 v29; // rcx
  LPVOID v30; // rcx
  int ppv; // [rsp+20h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]
  LPVOID v33; // [rsp+90h] [rbp+40h] BYREF
  __int64 v34; // [rsp+98h] [rbp+48h] BYREF
  PCNZWCH sourceString; // [rsp+A0h] [rbp+50h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp+58h] BYREF

  sourceString = 0;
  pv = 0;
  *string = 0;
  v33 = 0;
  v3 = CoCreateInstance(
         &GUID_0134a8b2_3407_4b45_ad25_e9f7c92a80bc,
         0,
         0x17u,
         &GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5,
         &v33);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5BC,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v3,
      ppv);
    v5 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v5 + 16LL))(v5);
    }
LABEL_52:
    if ( pv )
      CoTaskMemFree(pv);
    if ( sourceString )
      CoTaskMemFree((LPVOID)sourceString);
    return v4;
  }
  v34 = 0;
  v6 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v33)(
         v33,
         &GUID_0000013d_0000_0000_c000_000000000046,
         &v34);
  v4 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C0,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v6,
      ppv);
    v7 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
    }
    v8 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v8 + 16LL))(v8);
    }
    goto LABEL_52;
  }
  v9 = (*(__int64 (__fastcall **)(__int64, LPVOID, __int64, __int64))(*(_QWORD *)v34 + 32LL))(
         v34,
         v33,
         0xFFFFFFFFLL,
         0xFFFFFFFFLL);
  v4 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C1,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v9,
      -1);
    v10 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    }
    v11 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v11 + 16LL))(v11);
    }
    goto LABEL_52;
  }
  v12 = v33;
  v13 = *(__int64 (__fastcall **)(LPVOID, PCNZWCH *, LPVOID *))(*(_QWORD *)v33 + 448LL);
  v14 = pv;
  if ( pv )
  {
    LastError = GetLastError();
    CoTaskMemFree(v14);
    SetLastError(LastError);
  }
  pv = 0;
  v16 = (WCHAR *)sourceString;
  if ( sourceString )
  {
    v17 = GetLastError();
    CoTaskMemFree(v16);
    SetLastError(v17);
  }
  sourceString = 0;
  v18 = v13(v12, &sourceString, &pv);
  v4 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C3,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v18,
      -1);
    v19 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
    }
    v20 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v20 + 16LL))(v20);
    }
    goto LABEL_52;
  }
  if ( !sourceString )
  {
    v4 = -2147024809;
LABEL_48:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C6,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)v4,
      -1);
    v29 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
    }
    v30 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v30 + 16LL))(v30);
    }
    goto LABEL_52;
  }
  v21 = 0x7FFFFFFF;
  v22 = sourceString;
  do
  {
    if ( !*v22 )
      break;
    ++v22;
    --v21;
  }
  while ( v21 );
  v4 = v21 == 0 ? 0x80070057 : 0;
  if ( !v21 )
    goto LABEL_48;
  v23 = WindowsCreateString(sourceString, v21 != 0 ? 0x7FFFFFFF - v21 : 0, string);
  v4 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C7,
      (unsigned int)"onecoreuap\\enduser\\winstore\\auth\\lib\\winstoreauth.cpp",
      (const char *)(unsigned int)v23,
      -1);
    v24 = v34;
    if ( v34 )
    {
      v34 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
    }
    v25 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v25 + 16LL))(v25);
    }
    goto LABEL_52;
  }
  v26 = v34;
  if ( v34 )
  {
    v34 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  }
  v27 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v27 + 16LL))(v27);
  }
  if ( pv )
    CoTaskMemFree(pv);
  if ( sourceString )
    CoTaskMemFree((LPVOID)sourceString);
  return 0;
}

```

## disassembly

```asm
0x18003d17c  push    rbp
0x18003d17e  push    rbx
0x18003d17f  push    rsi
0x18003d180  push    rdi
0x18003d181  push    r12
0x18003d183  push    r14
0x18003d185  push    r15
0x18003d187  mov     rbp, rsp
0x18003d18a  sub     rsp, 50h
0x18003d18e  mov     r15, rcx
0x18003d191  xor     r12d, r12d
0x18003d194  mov     [rbp+sourceString], r12
0x18003d198  mov     [rbp+pv], r12
0x18003d19c  mov     [rcx], r12
0x18003d19f  mov     [rbp+arg_0], r12
0x18003d1a3  lea     rax, [rbp+arg_0]
0x18003d1a7  mov     [rsp+50h+ppv], rax; int
0x18003d1ac  lea     r9, _GUID_097ad6b8_203b_4506_a509_02e4b11b6bb5; riid
0x18003d1b3  xor     edx, edx; pUnkOuter
0x18003d1b5  lea     r8d, [r12+17h]; dwClsContext
0x18003d1ba  lea     rcx, _GUID_0134a8b2_3407_4b45_ad25_e9f7c92a80bc; rclsid
0x18003d1c1  call    cs:__imp_CoCreateInstance
0x18003d1c7  mov     ebx, eax
0x18003d1c9  test    eax, eax
0x18003d1cb  jns     short loc_18003D205
0x18003d1cd  mov     rcx, [rbp+38h]; this
0x18003d1d1  mov     r9d, eax; char *
0x18003d1d4  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003d1db  mov     edx, 5BCh; void *
0x18003d1e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d1e5  nop
0x18003d1e6  mov     rcx, [rbp+arg_0]
0x18003d1ea  test    rcx, rcx
0x18003d1ed  jz      short loc_18003D200
0x18003d1ef  mov     [rbp+arg_0], r12
0x18003d1f3  mov     rax, [rcx]
0x18003d1f6  mov     rax, [rax+10h]
0x18003d1fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d1ff  nop
0x18003d200  jmp     loc_18003D535
0x18003d205  mov     [rbp+arg_8], r12
0x18003d209  mov     rcx, [rbp+arg_0]
0x18003d20d  mov     rax, [rcx]
0x18003d210  lea     r8, [rbp+arg_8]
0x18003d214  lea     rdx, _GUID_0000013d_0000_0000_c000_000000000046
0x18003d21b  mov     rax, [rax]
0x18003d21e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d223  mov     ebx, eax
0x18003d225  test    eax, eax
0x18003d227  jns     short loc_18003D27B
0x18003d229  mov     rcx, [rbp+38h]; this
0x18003d22d  mov     r9d, eax; char *
0x18003d230  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003d237  mov     edx, 5C0h; void *
0x18003d23c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d241  nop
0x18003d242  mov     rcx, [rbp+arg_8]
0x18003d246  test    rcx, rcx
0x18003d249  jz      short loc_18003D25C
0x18003d24b  mov     [rbp+arg_8], r12
0x18003d24f  mov     rax, [rcx]
0x18003d252  mov     rax, [rax+10h]
0x18003d256  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d25b  nop
0x18003d25c  mov     rcx, [rbp+arg_0]
0x18003d260  test    rcx, rcx
0x18003d263  jz      short loc_18003D276
0x18003d265  mov     [rbp+arg_0], r12
0x18003d269  mov     rax, [rcx]
0x18003d26c  mov     rax, [rax+10h]
0x18003d270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d275  nop
0x18003d276  jmp     loc_18003D535
0x18003d27b  mov     rcx, [rbp+arg_8]
0x18003d27f  mov     rax, [rcx]
0x18003d282  mov     [rsp+50h+var_10], 40h ; '@'
0x18003d28a  mov     [rsp+50h+var_18], r12
0x18003d28f  mov     [rsp+50h+var_20], 3
0x18003d297  mov     [rsp+50h+var_28], r12d
0x18003d29c  mov     [rsp+50h+ppv], 0FFFFFFFFFFFFFFFFh; int
0x18003d2a5  or      r8d, 0FFFFFFFFh
0x18003d2a9  mov     r9d, r8d
0x18003d2ac  mov     rdx, [rbp+arg_0]
0x18003d2b0  mov     rax, [rax+20h]
0x18003d2b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2b9  mov     ebx, eax
0x18003d2bb  test    eax, eax
0x18003d2bd  jns     short loc_18003D311
0x18003d2bf  mov     rcx, [rbp+38h]; this
0x18003d2c3  mov     r9d, eax; char *
0x18003d2c6  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003d2cd  mov     edx, 5C1h; void *
0x18003d2d2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d2d7  nop
0x18003d2d8  mov     rcx, [rbp+arg_8]
0x18003d2dc  test    rcx, rcx
0x18003d2df  jz      short loc_18003D2F2
0x18003d2e1  mov     [rbp+arg_8], r12
0x18003d2e5  mov     rax, [rcx]
0x18003d2e8  mov     rax, [rax+10h]
0x18003d2ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d2f1  nop
0x18003d2f2  mov     rcx, [rbp+arg_0]
0x18003d2f6  test    rcx, rcx
0x18003d2f9  jz      short loc_18003D30C
0x18003d2fb  mov     [rbp+arg_0], r12
0x18003d2ff  mov     rax, [rcx]
0x18003d302  mov     rax, [rax+10h]
0x18003d306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d30b  nop
0x18003d30c  jmp     loc_18003D535
0x18003d311  mov     rsi, [rbp+arg_0]
0x18003d315  mov     rax, [rsi]
0x18003d318  mov     r14, [rax+1C0h]
0x18003d31f  mov     rdi, [rbp+pv]
0x18003d323  test    rdi, rdi
0x18003d326  jz      short loc_18003D341
0x18003d328  call    cs:__imp_GetLastError
0x18003d32e  mov     ebx, eax
0x18003d330  mov     rcx, rdi; pv
0x18003d333  call    cs:__imp_CoTaskMemFree
0x18003d339  mov     ecx, ebx; dwErrCode
0x18003d33b  call    cs:__imp_SetLastError
0x18003d341  mov     [rbp+pv], r12
0x18003d345  mov     rdi, [rbp+sourceString]
0x18003d349  test    rdi, rdi
0x18003d34c  jz      short loc_18003D367
0x18003d34e  call    cs:__imp_GetLastError
0x18003d354  mov     ebx, eax
0x18003d356  mov     rcx, rdi; pv
0x18003d359  call    cs:__imp_CoTaskMemFree
0x18003d35f  mov     ecx, ebx; dwErrCode
0x18003d361  call    cs:__imp_SetLastError
0x18003d367  mov     [rbp+sourceString], r12
0x18003d36b  lea     r8, [rbp+pv]
0x18003d36f  lea     rdx, [rbp+sourceString]
0x18003d373  mov     rcx, rsi
0x18003d376  mov     rax, r14
0x18003d379  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d37e  mov     ebx, eax
0x18003d380  test    eax, eax
0x18003d382  jns     short loc_18003D3D6
0x18003d384  mov     rcx, [rbp+38h]; this
0x18003d388  mov     r9d, eax; char *
0x18003d38b  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003d392  mov     edx, 5C3h; void *
0x18003d397  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d39c  nop
0x18003d39d  mov     rcx, [rbp+arg_8]
0x18003d3a1  test    rcx, rcx
0x18003d3a4  jz      short loc_18003D3B7
0x18003d3a6  mov     [rbp+arg_8], r12
0x18003d3aa  mov     rax, [rcx]
0x18003d3ad  mov     rax, [rax+10h]
0x18003d3b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d3b6  nop
0x18003d3b7  mov     rcx, [rbp+arg_0]
0x18003d3bb  test    rcx, rcx
0x18003d3be  jz      short loc_18003D3D1
0x18003d3c0  mov     [rbp+arg_0], r12
0x18003d3c4  mov     rax, [rcx]
0x18003d3c7  mov     rax, [rax+10h]
0x18003d3cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d3d0  nop
0x18003d3d1  jmp     loc_18003D535
0x18003d3d6  mov     r9, [rbp+sourceString]
0x18003d3da  test    r9, r9
0x18003d3dd  jz      loc_18003D4E3
0x18003d3e3  mov     edx, 7FFFFFFFh
0x18003d3e8  mov     ecx, edx
0x18003d3ea  mov     rax, r9
0x18003d3ed  cmp     [rax], r12w
0x18003d3f1  jz      short loc_18003D3FD
0x18003d3f3  add     rax, 2
0x18003d3f7  sub     rcx, 1
0x18003d3fb  jnz     short loc_18003D3ED
0x18003d3fd  mov     rax, rcx
0x18003d400  neg     rax
0x18003d403  sbb     ebx, ebx
0x18003d405  not     ebx
0x18003d407  and     ebx, 80070057h
0x18003d40d  mov     rax, rcx
0x18003d410  sub     rdx, rcx
0x18003d413  neg     rax
0x18003d416  sbb     r8, r8
0x18003d419  and     r8, rdx
0x18003d41c  test    rcx, rcx
0x18003d41f  jz      loc_18003D4E8
0x18003d425  mov     edx, r8d; length
0x18003d428  mov     r8, r15; string
0x18003d42b  mov     rcx, r9; sourceString
0x18003d42e  call    cs:__imp_WindowsCreateString
0x18003d434  mov     ebx, eax
0x18003d436  test    eax, eax
0x18003d438  jns     short loc_18003D48C
0x18003d43a  mov     rcx, [rbp+38h]; this
0x18003d43e  mov     r9d, eax; char *
0x18003d441  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003d448  mov     edx, 5C7h; void *
0x18003d44d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d452  nop
0x18003d453  mov     rcx, [rbp+arg_8]
0x18003d457  test    rcx, rcx
0x18003d45a  jz      short loc_18003D46D
0x18003d45c  mov     [rbp+arg_8], r12
0x18003d460  mov     rax, [rcx]
0x18003d463  mov     rax, [rax+10h]
0x18003d467  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d46c  nop
0x18003d46d  mov     rcx, [rbp+arg_0]
0x18003d471  test    rcx, rcx
0x18003d474  jz      short loc_18003D487
0x18003d476  mov     [rbp+arg_0], r12
0x18003d47a  mov     rax, [rcx]
0x18003d47d  mov     rax, [rax+10h]
0x18003d481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d486  nop
0x18003d487  jmp     loc_18003D535
0x18003d48c  mov     rcx, [rbp+arg_8]
0x18003d490  test    rcx, rcx
0x18003d493  jz      short loc_18003D4A6
0x18003d495  mov     [rbp+arg_8], r12
0x18003d499  mov     rax, [rcx]
0x18003d49c  mov     rax, [rax+10h]
0x18003d4a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d4a5  nop
0x18003d4a6  mov     rcx, [rbp+arg_0]
0x18003d4aa  test    rcx, rcx
0x18003d4ad  jz      short loc_18003D4C0
0x18003d4af  mov     [rbp+arg_0], r12
0x18003d4b3  mov     rax, [rcx]
0x18003d4b6  mov     rax, [rax+10h]
0x18003d4ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d4bf  nop
0x18003d4c0  mov     rcx, [rbp+pv]; pv
0x18003d4c4  test    rcx, rcx
0x18003d4c7  jz      short loc_18003D4D0
0x18003d4c9  call    cs:__imp_CoTaskMemFree
0x18003d4cf  nop
0x18003d4d0  mov     rcx, [rbp+sourceString]; pv
0x18003d4d4  test    rcx, rcx
0x18003d4d7  jz      short loc_18003D4DF
0x18003d4d9  call    cs:__imp_CoTaskMemFree
0x18003d4df  xor     eax, eax
0x18003d4e1  jmp     short loc_18003D556
0x18003d4e3  mov     ebx, 80070057h
0x18003d4e8  mov     rcx, [rbp+38h]; this
0x18003d4ec  mov     r9d, ebx; char *
0x18003d4ef  lea     r8, aOnecoreuapEndu_0; "onecoreuap\\enduser\\winstore\\auth\\li"...
0x18003d4f6  mov     edx, 5C6h; void *
0x18003d4fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d500  nop
0x18003d501  mov     rcx, [rbp+arg_8]
0x18003d505  test    rcx, rcx
0x18003d508  jz      short loc_18003D51B
0x18003d50a  mov     [rbp+arg_8], r12
0x18003d50e  mov     rax, [rcx]
0x18003d511  mov     rax, [rax+10h]
0x18003d515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d51a  nop
0x18003d51b  mov     rcx, [rbp+arg_0]
0x18003d51f  test    rcx, rcx
0x18003d522  jz      short loc_18003D535
0x18003d524  mov     [rbp+arg_0], r12
0x18003d528  mov     rax, [rcx]
0x18003d52b  mov     rax, [rax+10h]
0x18003d52f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d534  nop
0x18003d535  mov     rcx, [rbp+pv]; pv
0x18003d539  test    rcx, rcx
0x18003d53c  jz      short loc_18003D545
0x18003d53e  call    cs:__imp_CoTaskMemFree
0x18003d544  nop
0x18003d545  mov     rcx, [rbp+sourceString]; pv
0x18003d549  test    rcx, rcx
0x18003d54c  jz      short loc_18003D554
0x18003d54e  call    cs:__imp_CoTaskMemFree
0x18003d554  mov     eax, ebx
0x18003d556  add     rsp, 50h
0x18003d55a  pop     r15
0x18003d55c  pop     r14
0x18003d55e  pop     r12
0x18003d560  pop     rdi
0x18003d561  pop     rsi
0x18003d562  pop     rbx
0x18003d563  pop     rbp
0x18003d564  retn
```
