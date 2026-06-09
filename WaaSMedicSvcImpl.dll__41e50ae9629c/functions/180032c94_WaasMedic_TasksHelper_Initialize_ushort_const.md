# WaasMedic::TasksHelper::Initialize(ushort const *)

- ea: `0x180032c94`
- end: `0x180032f64`
- name: `?Initialize@TasksHelper@WaasMedic@@QEAAJPEBG@Z`
- size: `720`
- prototype: `__int64 __fastcall(LPVOID *ppv, OLECHAR *psz)`
- caller_count: `4`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18001fe68`
- `0x180039e40`
- `0x18003a7d0`
- `0x180067020`

## callees

- `0x18000bbd4`
- `0x18002e81c`
- `0x18002fffc`
- `0x180032c94`
- `0x1800639bc`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180032dc3`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180032dc3`
- `OLEAUT32!__imp_SysAllocString` at `0x180032cb5`
- `OLEAUT32!__imp_SysAllocString` at `0x180032cd8`
- `OLEAUT32!__imp_SysAllocString` at `0x180032e6a`
- `OLEAUT32!__imp_SysAllocString` at `0x180032cb5`
- `OLEAUT32!__imp_SysAllocString` at `0x180032cd8`
- `OLEAUT32!__imp_SysAllocString` at `0x180032e6a`
- `OLEAUT32!__imp_SysFreeString` at `0x180032d57`
- `OLEAUT32!__imp_SysFreeString` at `0x180032f20`
- `OLEAUT32!__imp_SysFreeString` at `0x180032f2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180032f38`
- `OLEAUT32!__imp_SysFreeString` at `0x180032d57`
- `OLEAUT32!__imp_SysFreeString` at `0x180032f20`
- `OLEAUT32!__imp_SysFreeString` at `0x180032f2b`
- `OLEAUT32!__imp_SysFreeString` at `0x180032f38`
- `OLEAUT32!__imp_SysStringLen` at `0x180032d85`
- `OLEAUT32!__imp_SysStringLen` at `0x180032da2`
- `OLEAUT32!__imp_SysStringLen` at `0x180032d85`
- `OLEAUT32!__imp_SysStringLen` at `0x180032da2`
- `OLEAUT32!__imp_VariantClear` at `0x180032eb4`
- `OLEAUT32!__imp_VariantClear` at `0x180032eb4`

## string_xrefs

- `0x180032d32`: `onecore\enduser\waasmedic\lib\util\taskshelper.cpp`
- `0x180032cfc`: `Failed to connect to the task scheduler service! hr = 0x%08x`
- `0x180032e2b`: `Failed to Get task folder! hr = 0x%08x`
- `0x180032df7`: `Failed to find the task folder path: [%ws] with error hr = 0x%08x. Attempting to create it.`
- `0x180032ed1`: `Failed to Create task folder! hr = 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WaasMedic::TasksHelper::Initialize(LPVOID *ppv, OLECHAR *psz)
{
  OLECHAR *v4; // rdi
  WCHAR *v5; // rbx
  int v6; // eax
  int v7; // esi
  LPVOID *v8; // r12
  LPVOID v9; // r14
  __int64 (__fastcall *v10)(LPVOID, BSTR *); // rsi
  bool v11; // zf
  UINT cchCount2; // eax
  int v13; // eax
  int v14; // eax
  _QWORD *v15; // rcx
  _QWORD *v16; // rsi
  __int64 v17; // r14
  BSTR v18; // rax
  HRESULT v19; // eax
  _QWORD *v20; // rcx
  _QWORD *v21; // rcx
  int lpString2; // [rsp+20h] [rbp-58h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-48h] BYREF
  VARIANTARG v25; // [rsp+50h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]
  BSTR bstrString; // [rsp+C0h] [rbp+48h] BYREF
  _QWORD *v28; // [rsp+C8h] [rbp+50h] BYREF
  WCHAR *v29; // [rsp+D0h] [rbp+58h]
  OLECHAR *v30; // [rsp+D8h] [rbp+60h]

  v4 = SysAllocString(L"\\");
  v30 = v4;
  bstrString = 0;
  v5 = 0;
  v29 = 0;
  if ( psz )
  {
    v5 = SysAllocString(psz);
    v29 = v5;
  }
  if ( !*((_BYTE *)ppv + 16) )
  {
    v6 = WaasMedic::TasksHelper::Connect(ppv);
    v7 = v6;
    if ( v6 < 0 )
    {
      LogLevelW(2u, L"Failed to connect to the task scheduler service! hr = 0x%08x", (unsigned int)v6);
      goto LABEL_29;
    }
  }
  v8 = ppv + 1;
  if ( *((_BYTE *)ppv + 17) )
  {
    if ( !*v8 )
    {
      v7 = -2147019873;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x51,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\taskshelper.cpp",
        (const char *)0x8007139FLL,
        lpString2);
      goto LABEL_29;
    }
    v9 = *v8;
    v10 = *(__int64 (__fastcall **)(LPVOID, BSTR *))(*(_QWORD *)*v8 + 64LL);
    SysFreeString(bstrString);
    bstrString = 0;
    v7 = v10(v9, &bstrString);
    if ( v7 < 0 )
      goto LABEL_29;
    if ( SysStringLen(bstrString) )
    {
      cchCount2 = SysStringLen(bstrString);
      v11 = CompareStringW(0x400u, 0, v5, -1, bstrString, cchCount2) == 2;
    }
    else
    {
      if ( !v5 )
        goto LABEL_29;
      v11 = *v5 == 0;
    }
    if ( v11 )
      goto LABEL_29;
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, WCHAR *, LPVOID *))(*(_QWORD *)*ppv + 56LL))(*ppv, v5, ppv + 1);
  v7 = v13;
  if ( v13 >= 0 )
  {
LABEL_28:
    *((_BYTE *)ppv + 17) = 1;
    goto LABEL_29;
  }
  LogLevelW(
    4u,
    L"Failed to find the task folder path: [%ws] with error hr = 0x%08x. Attempting to create it.",
    psz,
    (unsigned int)v13);
  v28 = 0;
  v14 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, _QWORD **))(*(_QWORD *)*ppv + 56LL))(*ppv, v4, &v28);
  v7 = v14;
  if ( v14 < 0 )
  {
    LogLevelW(2u, L"Failed to Get task folder! hr = 0x%08x", (unsigned int)v14);
    v15 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v15 + 16LL))(v15);
    }
    goto LABEL_29;
  }
  v16 = v28;
  v17 = *v28;
  v18 = SysAllocString(word_180073298);
  if ( !v18 )
    _com_issue_error(-2147024882);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)v18;
  v25 = pvarg;
  v7 = (*(__int64 (__fastcall **)(_QWORD *, WCHAR *, VARIANTARG *, LPVOID *))(v17 + 88))(v16, v5, &v25, ppv + 1);
  v19 = VariantClear(&pvarg);
  if ( v19 < 0 )
    _com_issue_error(v19);
  if ( v7 >= 0 )
  {
    v21 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v21 + 16LL))(v21);
    }
    goto LABEL_28;
  }
  LogLevelW(2u, L"Failed to Create task folder! hr = 0x%08x", (unsigned int)v7);
  v20 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v20 + 16LL))(v20);
  }
LABEL_29:
  SysFreeString(v5);
  SysFreeString(bstrString);
  bstrString = 0;
  SysFreeString(v4);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180032c94  push    rbp
0x180032c96  push    rbx
0x180032c97  push    rsi
0x180032c98  push    rdi
0x180032c99  push    r12
0x180032c9b  push    r13
0x180032c9d  push    r14
0x180032c9f  push    r15
0x180032ca1  mov     rbp, rsp
0x180032ca4  sub     rsp, 78h
0x180032ca8  mov     r13, rdx
0x180032cab  mov     r15, rcx
0x180032cae  lea     rcx, asc_180081F30; "\\"
0x180032cb5  call    cs:__imp_SysAllocString
0x180032cbb  mov     rdi, rax
0x180032cbe  mov     [rbp+arg_18], rax
0x180032cc2  xor     r14d, r14d
0x180032cc5  mov     [rbp+bstrString], r14
0x180032cc9  mov     ebx, r14d
0x180032ccc  mov     [rbp+arg_10], rbx
0x180032cd0  test    r13, r13
0x180032cd3  jz      short loc_180032CE5
0x180032cd5  mov     rcx, r13; psz
0x180032cd8  call    cs:__imp_SysAllocString
0x180032cde  mov     rbx, rax
0x180032ce1  mov     [rbp+arg_10], rax
0x180032ce5  cmp     [r15+10h], r14b
0x180032ce9  jnz     short loc_180032D12
0x180032ceb  mov     rcx, r15; ppv
0x180032cee  call    ?Connect@TasksHelper@WaasMedic@@AEAAJXZ; WaasMedic::TasksHelper::Connect(void)
0x180032cf3  mov     esi, eax
0x180032cf5  test    eax, eax
0x180032cf7  jns     short loc_180032D12
0x180032cf9  mov     r8d, eax
0x180032cfc  lea     rdx, aFailedToConnec; "Failed to connect to the task scheduler"...
0x180032d03  mov     ecx, 2; unsigned __int8
0x180032d08  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180032d0d  jmp     loc_180032F1D
0x180032d12  lea     r12, [r15+8]
0x180032d16  cmp     [r15+11h], r14b
0x180032d1a  jz      loc_180032DD2
0x180032d20  cmp     [r12], r14
0x180032d24  jnz     short loc_180032D48
0x180032d26  mov     rcx, [rbp+40h]; this
0x180032d2a  mov     esi, 8007139Fh
0x180032d2f  mov     r9d, esi; char *
0x180032d32  lea     r8, aOnecoreEnduser_8; "onecore\\enduser\\waasmedic\\lib\\util"...
0x180032d39  mov     edx, 51h ; 'Q'; void *
0x180032d3e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180032d43  jmp     loc_180032F1D
0x180032d48  mov     r14, [r12]
0x180032d4c  mov     rax, [r14]
0x180032d4f  mov     rsi, [rax+40h]
0x180032d53  mov     rcx, [rbp+bstrString]; bstrString
0x180032d57  call    cs:__imp_SysFreeString
0x180032d5d  mov     [rbp+bstrString], 0
0x180032d65  lea     rdx, [rbp+bstrString]
0x180032d69  mov     rcx, r14
0x180032d6c  mov     rax, rsi
0x180032d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032d74  mov     esi, eax
0x180032d76  xor     r14d, r14d
0x180032d79  test    eax, eax
0x180032d7b  js      loc_180032F1D
0x180032d81  mov     rcx, [rbp+bstrString]; pbstr
0x180032d85  call    cs:__imp_SysStringLen
0x180032d8b  test    eax, eax
0x180032d8d  jnz     short loc_180032D9E
0x180032d8f  test    rbx, rbx
0x180032d92  jz      loc_180032F1D
0x180032d98  cmp     [rbx], r14w
0x180032d9c  jmp     short loc_180032DCC
0x180032d9e  mov     rcx, [rbp+bstrString]; pbstr
0x180032da2  call    cs:__imp_SysStringLen
0x180032da8  mov     rcx, [rbp+bstrString]
0x180032dac  mov     [rsp+78h+cchCount2], eax; cchCount2
0x180032db0  mov     [rsp+78h+lpString2], rcx; lpString2
0x180032db5  or      r9d, 0FFFFFFFFh; cchCount1
0x180032db9  mov     r8, rbx; lpString1
0x180032dbc  xor     edx, edx; dwCmpFlags
0x180032dbe  mov     ecx, 400h; Locale
0x180032dc3  call    cs:__imp_CompareStringW
0x180032dc9  cmp     eax, 2
0x180032dcc  jz      loc_180032F1D
0x180032dd2  mov     rcx, [r15]
0x180032dd5  mov     rax, [rcx]
0x180032dd8  mov     r8, r12
0x180032ddb  mov     rdx, rbx
0x180032dde  mov     rax, [rax+38h]
0x180032de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032de7  mov     esi, eax
0x180032de9  test    eax, eax
0x180032deb  jns     loc_180032F18
0x180032df1  mov     r9d, eax
0x180032df4  mov     r8, r13
0x180032df7  lea     rdx, aFailedToFindTh; "Failed to find the task folder path: [%"...
0x180032dfe  mov     ecx, 4; unsigned __int8
0x180032e03  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180032e08  mov     [rbp+arg_8], r14
0x180032e0c  mov     rcx, [r15]
0x180032e0f  mov     rax, [rcx]
0x180032e12  lea     r8, [rbp+arg_8]
0x180032e16  mov     rdx, rdi
0x180032e19  mov     rax, [rax+38h]
0x180032e1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e22  mov     esi, eax
0x180032e24  test    eax, eax
0x180032e26  jns     short loc_180032E5C
0x180032e28  mov     r8d, eax
0x180032e2b  lea     rdx, aFailedToGetTas; "Failed to Get task folder! hr = 0x%08x"
0x180032e32  mov     ecx, 2; unsigned __int8
0x180032e37  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180032e3c  nop
0x180032e3d  mov     rcx, [rbp+arg_8]
0x180032e41  test    rcx, rcx
0x180032e44  jz      short loc_180032E57
0x180032e46  mov     [rbp+arg_8], r14
0x180032e4a  mov     rax, [rcx]
0x180032e4d  mov     rax, [rax+10h]
0x180032e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032e56  nop
0x180032e57  jmp     loc_180032F1D
0x180032e5c  mov     rsi, [rbp+arg_8]
0x180032e60  mov     r14, [rsi]
0x180032e63  lea     rcx, word_180073298; psz
0x180032e6a  call    cs:__imp_SysAllocString
0x180032e70  test    rax, rax
0x180032e73  jz      loc_180032F59
0x180032e79  mov     ecx, 8
0x180032e7e  mov     word ptr [rbp+pvarg], cx
0x180032e82  mov     qword ptr [rbp+pvarg+8], rax
0x180032e86  movups  xmm0, xmmword ptr [rbp+pvarg]
0x180032e8a  movaps  [rbp+var_28], xmm0
0x180032e8e  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x180032e93  movsd   [rbp+var_18], xmm1
0x180032e98  mov     r9, r12
0x180032e9b  lea     r8, [rbp+var_28]
0x180032e9f  mov     rdx, rbx
0x180032ea2  mov     rcx, rsi
0x180032ea5  mov     rax, [r14+58h]
0x180032ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032eae  mov     esi, eax
0x180032eb0  lea     rcx, [rbp+pvarg]; pvarg
0x180032eb4  call    cs:__imp_VariantClear
0x180032eba  xor     r14d, r14d
0x180032ebd  test    eax, eax
0x180032ebf  js      loc_180032F51
0x180032ec5  mov     eax, esi
0x180032ec7  shr     eax, 1Fh
0x180032eca  test    al, al
0x180032ecc  jz      short loc_180032EFE
0x180032ece  mov     r8d, esi
0x180032ed1  lea     rdx, aFailedToCreate_17; "Failed to Create task folder! hr = 0x%0"...
0x180032ed8  lea     ecx, [r14+2]; unsigned __int8
0x180032edc  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180032ee1  nop
0x180032ee2  mov     rcx, [rbp+arg_8]
0x180032ee6  test    rcx, rcx
0x180032ee9  jz      short loc_180032EFC
0x180032eeb  mov     [rbp+arg_8], r14
0x180032eef  mov     rax, [rcx]
0x180032ef2  mov     rax, [rax+10h]
0x180032ef6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032efb  nop
0x180032efc  jmp     short loc_180032F1D
0x180032efe  mov     rcx, [rbp+arg_8]
0x180032f02  test    rcx, rcx
0x180032f05  jz      short loc_180032F18
0x180032f07  mov     [rbp+arg_8], r14
0x180032f0b  mov     rax, [rcx]
0x180032f0e  mov     rax, [rax+10h]
0x180032f12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180032f17  nop
0x180032f18  mov     byte ptr [r15+11h], 1
0x180032f1d  mov     rcx, rbx; bstrString
0x180032f20  call    cs:__imp_SysFreeString
0x180032f26  nop
0x180032f27  mov     rcx, [rbp+bstrString]; bstrString
0x180032f2b  call    cs:__imp_SysFreeString
0x180032f31  mov     [rbp+bstrString], r14
0x180032f35  mov     rcx, rdi; bstrString
0x180032f38  call    cs:__imp_SysFreeString
0x180032f3e  mov     eax, esi
0x180032f40  add     rsp, 78h
0x180032f44  pop     r15
0x180032f46  pop     r14
0x180032f48  pop     r13
0x180032f4a  pop     r12
0x180032f4c  pop     rdi
0x180032f4d  pop     rsi
0x180032f4e  pop     rbx
0x180032f4f  pop     rbp
0x180032f50  retn
0x180032f51  mov     ecx, eax; int
0x180032f53  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180032f59  mov     ecx, 8007000Eh; int
0x180032f5e  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
