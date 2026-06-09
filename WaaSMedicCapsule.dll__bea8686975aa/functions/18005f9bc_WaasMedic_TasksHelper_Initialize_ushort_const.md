# WaasMedic::TasksHelper::Initialize(ushort const *)

- ea: `0x18005f9bc`
- end: `0x18005fc77`
- name: `?Initialize@TasksHelper@WaasMedic@@QEAAJPEBG@Z`
- size: `699`
- prototype: `__int64 __fastcall(LPVOID *ppv, OLECHAR *psz)`
- caller_count: `6`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800534f0`
- `0x180054390`
- `0x180054fd0`
- `0x1800555cc`
- `0x180055b30`
- `0x18005acb8`

## callees

- `0x180009a54`
- `0x18002543c`
- `0x180036918`
- `0x18005f1c8`
- `0x18005f9bc`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005faeb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005faeb`
- `OLEAUT32!__imp_SysAllocString` at `0x18005f9dd`
- `OLEAUT32!__imp_SysAllocString` at `0x18005fa00`
- `OLEAUT32!__imp_SysAllocString` at `0x18005fb92`
- `OLEAUT32!__imp_SysAllocString` at `0x18005f9dd`
- `OLEAUT32!__imp_SysAllocString` at `0x18005fa00`
- `OLEAUT32!__imp_SysAllocString` at `0x18005fb92`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fa7f`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fc40`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fc4b`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fc58`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fa7f`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fc40`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fc4b`
- `OLEAUT32!__imp_SysFreeString` at `0x18005fc58`
- `OLEAUT32!__imp_SysStringLen` at `0x18005faad`
- `OLEAUT32!__imp_SysStringLen` at `0x18005faca`
- `OLEAUT32!__imp_SysStringLen` at `0x18005faad`
- `OLEAUT32!__imp_SysStringLen` at `0x18005faca`
- `OLEAUT32!__imp_VariantClear` at `0x18005fbdc`
- `OLEAUT32!__imp_VariantClear` at `0x18005fbdc`

## string_xrefs

- `0x18005fa5a`: `onecore\enduser\waasmedic\lib\util\taskshelper.cpp`
- `0x18005fb1f`: `Failed to find the task folder path: [%ws] with error hr = 0x%08x. Attempting to create it.`
- `0x18005fa24`: `Failed to connect to the task scheduler service! hr = 0x%08x`
- `0x18005fb53`: `Failed to Get task folder! hr = 0x%08x`
- `0x18005fbf1`: `Failed to Create task folder! hr = 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
  int v19; // ecx
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
      goto LABEL_28;
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
      goto LABEL_28;
    }
    v9 = *v8;
    v10 = *(__int64 (__fastcall **)(LPVOID, BSTR *))(*(_QWORD *)*v8 + 64LL);
    SysFreeString(bstrString);
    bstrString = 0;
    v7 = v10(v9, &bstrString);
    if ( v7 < 0 )
      goto LABEL_28;
    if ( SysStringLen(bstrString) )
    {
      cchCount2 = SysStringLen(bstrString);
      v11 = CompareStringW(0x400u, 0, v5, -1, bstrString, cchCount2) == 2;
    }
    else
    {
      if ( !v5 )
        goto LABEL_28;
      v11 = *v5 == 0;
    }
    if ( v11 )
      goto LABEL_28;
  }
  v13 = (*(__int64 (__fastcall **)(_QWORD, WCHAR *, LPVOID *))(*(_QWORD *)*ppv + 56LL))(*ppv, v5, ppv + 1);
  v7 = v13;
  if ( v13 >= 0 )
  {
LABEL_27:
    *((_BYTE *)ppv + 17) = 1;
    goto LABEL_28;
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
    goto LABEL_28;
  }
  v16 = v28;
  v17 = *v28;
  v18 = SysAllocString(&word_18006939C);
  if ( !v18 )
    _com_issue_error(v19);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)v18;
  v25 = pvarg;
  v7 = (*(__int64 (__fastcall **)(_QWORD *, WCHAR *, VARIANTARG *, LPVOID *))(v17 + 88))(v16, v5, &v25, ppv + 1);
  VariantClear(&pvarg);
  if ( v7 >= 0 )
  {
    v21 = v28;
    if ( v28 )
    {
      v28 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v21 + 16LL))(v21);
    }
    goto LABEL_27;
  }
  LogLevelW(2u, L"Failed to Create task folder! hr = 0x%08x", (unsigned int)v7);
  v20 = v28;
  if ( v28 )
  {
    v28 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v20 + 16LL))(v20);
  }
LABEL_28:
  SysFreeString(v5);
  SysFreeString(bstrString);
  bstrString = 0;
  SysFreeString(v4);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18005f9bc  push    rbp
0x18005f9be  push    rbx
0x18005f9bf  push    rsi
0x18005f9c0  push    rdi
0x18005f9c1  push    r12
0x18005f9c3  push    r13
0x18005f9c5  push    r14
0x18005f9c7  push    r15
0x18005f9c9  mov     rbp, rsp
0x18005f9cc  sub     rsp, 78h
0x18005f9d0  mov     r13, rdx
0x18005f9d3  mov     r15, rcx
0x18005f9d6  lea     rcx, asc_18006E878; "\\"
0x18005f9dd  call    cs:__imp_SysAllocString
0x18005f9e3  mov     rdi, rax
0x18005f9e6  mov     [rbp+arg_18], rax
0x18005f9ea  xor     r14d, r14d
0x18005f9ed  mov     [rbp+bstrString], r14
0x18005f9f1  mov     ebx, r14d
0x18005f9f4  mov     [rbp+arg_10], rbx
0x18005f9f8  test    r13, r13
0x18005f9fb  jz      short loc_18005FA0D
0x18005f9fd  mov     rcx, r13; psz
0x18005fa00  call    cs:__imp_SysAllocString
0x18005fa06  mov     rbx, rax
0x18005fa09  mov     [rbp+arg_10], rax
0x18005fa0d  cmp     [r15+10h], r14b
0x18005fa11  jnz     short loc_18005FA3A
0x18005fa13  mov     rcx, r15; ppv
0x18005fa16  call    ?Connect@TasksHelper@WaasMedic@@AEAAJXZ; WaasMedic::TasksHelper::Connect(void)
0x18005fa1b  mov     esi, eax
0x18005fa1d  test    eax, eax
0x18005fa1f  jns     short loc_18005FA3A
0x18005fa21  mov     r8d, eax
0x18005fa24  lea     rdx, aFailedToConnec; "Failed to connect to the task scheduler"...
0x18005fa2b  mov     ecx, 2; unsigned __int8
0x18005fa30  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005fa35  jmp     loc_18005FC3D
0x18005fa3a  lea     r12, [r15+8]
0x18005fa3e  cmp     [r15+11h], r14b
0x18005fa42  jz      loc_18005FAFA
0x18005fa48  cmp     [r12], r14
0x18005fa4c  jnz     short loc_18005FA70
0x18005fa4e  mov     rcx, [rbp+40h]; this
0x18005fa52  mov     esi, 8007139Fh
0x18005fa57  mov     r9d, esi; char *
0x18005fa5a  lea     r8, aOnecoreEnduser_18; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18005fa61  mov     edx, 51h ; 'Q'; void *
0x18005fa66  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005fa6b  jmp     loc_18005FC3D
0x18005fa70  mov     r14, [r12]
0x18005fa74  mov     rax, [r14]
0x18005fa77  mov     rsi, [rax+40h]
0x18005fa7b  mov     rcx, [rbp+bstrString]; bstrString
0x18005fa7f  call    cs:__imp_SysFreeString
0x18005fa85  mov     [rbp+bstrString], 0
0x18005fa8d  lea     rdx, [rbp+bstrString]
0x18005fa91  mov     rcx, r14
0x18005fa94  mov     rax, rsi
0x18005fa97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fa9c  mov     esi, eax
0x18005fa9e  xor     r14d, r14d
0x18005faa1  test    eax, eax
0x18005faa3  js      loc_18005FC3D
0x18005faa9  mov     rcx, [rbp+bstrString]; pbstr
0x18005faad  call    cs:__imp_SysStringLen
0x18005fab3  test    eax, eax
0x18005fab5  jnz     short loc_18005FAC6
0x18005fab7  test    rbx, rbx
0x18005faba  jz      loc_18005FC3D
0x18005fac0  cmp     [rbx], r14w
0x18005fac4  jmp     short loc_18005FAF4
0x18005fac6  mov     rcx, [rbp+bstrString]; pbstr
0x18005faca  call    cs:__imp_SysStringLen
0x18005fad0  mov     rcx, [rbp+bstrString]
0x18005fad4  mov     [rsp+78h+cchCount2], eax; cchCount2
0x18005fad8  mov     [rsp+78h+lpString2], rcx; lpString2
0x18005fadd  or      r9d, 0FFFFFFFFh; cchCount1
0x18005fae1  mov     r8, rbx; lpString1
0x18005fae4  xor     edx, edx; dwCmpFlags
0x18005fae6  mov     ecx, 400h; Locale
0x18005faeb  call    cs:__imp_CompareStringW
0x18005faf1  cmp     eax, 2
0x18005faf4  jz      loc_18005FC3D
0x18005fafa  mov     rcx, [r15]
0x18005fafd  mov     rax, [rcx]
0x18005fb00  mov     r8, r12
0x18005fb03  mov     rdx, rbx
0x18005fb06  mov     rax, [rax+38h]
0x18005fb0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fb0f  mov     esi, eax
0x18005fb11  test    eax, eax
0x18005fb13  jns     loc_18005FC38
0x18005fb19  mov     r9d, eax
0x18005fb1c  mov     r8, r13
0x18005fb1f  lea     rdx, aFailedToFindTh; "Failed to find the task folder path: [%"...
0x18005fb26  mov     ecx, 4; unsigned __int8
0x18005fb2b  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005fb30  mov     [rbp+arg_8], r14
0x18005fb34  mov     rcx, [r15]
0x18005fb37  mov     rax, [rcx]
0x18005fb3a  lea     r8, [rbp+arg_8]
0x18005fb3e  mov     rdx, rdi
0x18005fb41  mov     rax, [rax+38h]
0x18005fb45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fb4a  mov     esi, eax
0x18005fb4c  test    eax, eax
0x18005fb4e  jns     short loc_18005FB84
0x18005fb50  mov     r8d, eax
0x18005fb53  lea     rdx, aFailedToGetTas; "Failed to Get task folder! hr = 0x%08x"
0x18005fb5a  mov     ecx, 2; unsigned __int8
0x18005fb5f  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005fb64  nop
0x18005fb65  mov     rcx, [rbp+arg_8]
0x18005fb69  test    rcx, rcx
0x18005fb6c  jz      short loc_18005FB7F
0x18005fb6e  mov     [rbp+arg_8], r14
0x18005fb72  mov     rax, [rcx]
0x18005fb75  mov     rax, [rax+10h]
0x18005fb79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fb7e  nop
0x18005fb7f  jmp     loc_18005FC3D
0x18005fb84  mov     rsi, [rbp+arg_8]
0x18005fb88  mov     r14, [rsi]
0x18005fb8b  lea     rcx, word_18006939C; psz
0x18005fb92  call    cs:__imp_SysAllocString
0x18005fb98  test    rax, rax
0x18005fb9b  jz      loc_18005FC71
0x18005fba1  mov     ecx, 8
0x18005fba6  mov     word ptr [rbp+pvarg], cx
0x18005fbaa  mov     qword ptr [rbp+pvarg+8], rax
0x18005fbae  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18005fbb2  movaps  [rbp+var_28], xmm0
0x18005fbb6  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18005fbbb  movsd   [rbp+var_18], xmm1
0x18005fbc0  mov     r9, r12
0x18005fbc3  lea     r8, [rbp+var_28]
0x18005fbc7  mov     rdx, rbx
0x18005fbca  mov     rcx, rsi
0x18005fbcd  mov     rax, [r14+58h]
0x18005fbd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fbd6  mov     esi, eax
0x18005fbd8  lea     rcx, [rbp+pvarg]; pvarg
0x18005fbdc  call    cs:__imp_VariantClear
0x18005fbe2  mov     eax, esi
0x18005fbe4  shr     eax, 1Fh
0x18005fbe7  xor     r14d, r14d
0x18005fbea  test    al, al
0x18005fbec  jz      short loc_18005FC1E
0x18005fbee  mov     r8d, esi
0x18005fbf1  lea     rdx, aFailedToCreate_23; "Failed to Create task folder! hr = 0x%0"...
0x18005fbf8  lea     ecx, [r14+2]; unsigned __int8
0x18005fbfc  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005fc01  nop
0x18005fc02  mov     rcx, [rbp+arg_8]
0x18005fc06  test    rcx, rcx
0x18005fc09  jz      short loc_18005FC1C
0x18005fc0b  mov     [rbp+arg_8], r14
0x18005fc0f  mov     rax, [rcx]
0x18005fc12  mov     rax, [rax+10h]
0x18005fc16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fc1b  nop
0x18005fc1c  jmp     short loc_18005FC3D
0x18005fc1e  mov     rcx, [rbp+arg_8]
0x18005fc22  test    rcx, rcx
0x18005fc25  jz      short loc_18005FC38
0x18005fc27  mov     [rbp+arg_8], r14
0x18005fc2b  mov     rax, [rcx]
0x18005fc2e  mov     rax, [rax+10h]
0x18005fc32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005fc37  nop
0x18005fc38  mov     byte ptr [r15+11h], 1
0x18005fc3d  mov     rcx, rbx; bstrString
0x18005fc40  call    cs:__imp_SysFreeString
0x18005fc46  nop
0x18005fc47  mov     rcx, [rbp+bstrString]; bstrString
0x18005fc4b  call    cs:__imp_SysFreeString
0x18005fc51  mov     [rbp+bstrString], r14
0x18005fc55  mov     rcx, rdi; bstrString
0x18005fc58  call    cs:__imp_SysFreeString
0x18005fc5e  mov     eax, esi
0x18005fc60  add     rsp, 78h
0x18005fc64  pop     r15
0x18005fc66  pop     r14
0x18005fc68  pop     r13
0x18005fc6a  pop     r12
0x18005fc6c  pop     rdi
0x18005fc6d  pop     rsi
0x18005fc6e  pop     rbx
0x18005fc6f  pop     rbp
0x18005fc70  retn
0x18005fc71  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
```
