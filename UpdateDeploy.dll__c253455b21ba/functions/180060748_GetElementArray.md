# GetElementArray

- ea: `0x180060748`
- end: `0x180060a27`
- name: `GetElementArray`
- size: `735`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180060a30`

## callees

- `0x180003180`
- `0x180007b6c`
- `0x1800605f4`
- `0x180060748`
- `0x1800612a4`
- `0x1800612e8`
- `0x180061960`
- `0x180068ea0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800608e4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800608e4`
- `OLEAUT32!__imp_SysFreeString` at `0x180060898`
- `OLEAUT32!__imp_SysFreeString` at `0x1800608bd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800608f4`
- `OLEAUT32!__imp_SysFreeString` at `0x180060898`
- `OLEAUT32!__imp_SysFreeString` at `0x1800608bd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800608f4`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall GetElementArray(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rbx
  int v7; // r12d
  int v8; // edi
  int v9; // r8d
  __int64 v10; // rdx
  signed int v11; // r13d
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  __int64 v13; // rbx
  int v14; // eax
  int (__fastcall *v15)(__int64, BSTR *); // rdi
  OLECHAR *v16; // rcx
  int v17; // eax
  int NextSlot; // eax
  int Element; // eax
  __int64 v20; // r9
  __int64 v21; // r9
  int lpString2; // [rsp+20h] [rbp-50h]
  unsigned __int8 *v24; // [rsp+30h] [rbp-40h] BYREF
  __int64 v25; // [rsp+38h] [rbp-38h]
  __int64 v26; // [rsp+40h] [rbp-30h]
  __int64 v27; // [rsp+48h] [rbp-28h] BYREF
  unsigned int v28; // [rsp+50h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v26 = a4;
  v6 = a1;
  v25 = a1;
  v27 = 0;
  v24 = 0;
  v28 = 0;
  v7 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a1 + 64LL))(a1, &v28);
  if ( v8 < 0 )
  {
    v10 = 1112;
    goto LABEL_37;
  }
  v8 = CDSArrayBuilder::put_MinimumSize((CDSArrayBuilder *)a3, v28, v9);
  if ( v8 < 0 )
  {
    v10 = 1113;
    goto LABEL_37;
  }
  v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 80LL))(v6);
  if ( v8 < 0 )
  {
    v10 = 1114;
LABEL_37:
    v21 = (unsigned int)v8;
LABEL_35:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\updparse\\dsparse.cpp",
      (const char *)v21,
      lpString2);
    goto LABEL_39;
  }
  v11 = 0;
  if ( (int)v28 <= 0 )
    goto LABEL_32;
  do
  {
    v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6 + 72LL);
    if ( v27 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      v27 = 0;
    }
    v8 = v12(v25, &v27);
    if ( v8 < 0 )
    {
      v10 = 1122;
      goto LABEL_37;
    }
    v13 = v27;
    if ( !v27 )
      goto LABEL_40;
    if ( *(_DWORD *)(a2 + 24) == 22 )
    {
      LODWORD(bstrString) = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v27 + 80LL))(v27, &bstrString);
      if ( v14 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x468,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\updparse\\dsparse.cpp",
          (const char *)(unsigned int)v14,
          lpString2);
      if ( (_DWORD)bstrString != 1 )
        goto LABEL_30;
    }
    else
    {
      bstrString = 0;
      v15 = *(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v27 + 56LL);
      SysFreeString(0);
      bstrString = 0;
      if ( v15(v13, &bstrString) < 0 )
      {
        v16 = bstrString;
LABEL_19:
        SysFreeString(v16);
        goto LABEL_30;
      }
      v17 = CompareStringW(0x7Fu, 0, bstrString, -1, *(PCNZWCH *)(a2 + 8), -1);
      v16 = bstrString;
      if ( v17 != 2 )
        goto LABEL_19;
      SysFreeString(bstrString);
    }
    ++v7;
    NextSlot = CDSArrayBuilder::get_NextSlot((CDSArrayBuilder *)a3, &v24);
    if ( NextSlot < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x485,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\updparse\\dsparse.cpp",
        (const char *)(unsigned int)NextSlot,
        lpString2);
    Element = GetElement(v27, v24, a2, v26);
    v8 = Element;
    if ( Element < 0 )
    {
      v21 = (unsigned int)Element;
      v10 = 1158;
      goto LABEL_35;
    }
    if ( v24 == (unsigned __int8 *)(*(_QWORD *)(a3 + 8) + (unsigned int)(*(_DWORD *)(a3 + 16) * *(_DWORD *)(a3 + 24))) )
    {
      ++*(_DWORD *)(a3 + 24);
      v20 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x85,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\dsutil\\dsarray.cpp",
        (const char *)0x80070057LL,
        lpString2);
      v20 = 2147942487LL;
    }
    if ( (int)v20 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x487,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\updparse\\dsparse.cpp",
        (const char *)v20,
        lpString2);
LABEL_30:
    ++v11;
    v6 = v25;
  }
  while ( v11 < (int)v28 );
  if ( v7 )
    goto LABEL_38;
LABEL_32:
  if ( *(_BYTE *)(a2 + 32) )
  {
    v8 = -2145124339;
    v21 = 2149842957LL;
    v10 = 1162;
    goto LABEL_35;
  }
LABEL_38:
  v8 = 0;
LABEL_39:
  v13 = v27;
LABEL_40:
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180060748  push    rbp
0x18006074a  push    rbx
0x18006074b  push    rdi
0x18006074c  push    r12
0x18006074e  push    r13
0x180060750  push    r14
0x180060752  push    r15
0x180060754  mov     rbp, rsp
0x180060757  sub     rsp, 70h
0x18006075b  mov     rax, cs:__security_cookie
0x180060762  xor     rax, rsp
0x180060765  mov     [rbp+var_10], rax
0x180060769  mov     [rbp+var_30], r9
0x18006076d  mov     r15, r8
0x180060770  mov     r14, rdx
0x180060773  mov     rbx, rcx
0x180060776  mov     [rbp+var_38], rcx
0x18006077a  xor     r13d, r13d
0x18006077d  mov     [rbp+var_28], r13
0x180060781  mov     [rbp+var_40], r13
0x180060785  mov     [rbp+var_20], r13d
0x180060789  mov     r12d, r13d
0x18006078c  mov     rax, [rcx]
0x18006078f  lea     rdx, [rbp+var_20]
0x180060793  mov     rax, [rax+40h]
0x180060797  call    _guard_dispatch_icall
0x18006079c  mov     edi, eax
0x18006079e  test    eax, eax
0x1800607a0  jns     short loc_1800607AC
0x1800607a2  mov     edx, 458h
0x1800607a7  jmp     loc_1800609E9
0x1800607ac  mov     edx, [rbp+var_20]; unsigned int
0x1800607af  mov     rcx, r15; this
0x1800607b2  call    ?put_MinimumSize@CDSArrayBuilder@@QEAAJKH@Z; CDSArrayBuilder::put_MinimumSize(ulong,int)
0x1800607b7  mov     edi, eax
0x1800607b9  test    eax, eax
0x1800607bb  jns     short loc_1800607C7
0x1800607bd  mov     edx, 459h
0x1800607c2  jmp     loc_1800609E9
0x1800607c7  mov     rax, [rbx]
0x1800607ca  mov     rcx, rbx
0x1800607cd  mov     rax, [rax+50h]
0x1800607d1  call    _guard_dispatch_icall
0x1800607d6  mov     edi, eax
0x1800607d8  test    eax, eax
0x1800607da  jns     short loc_1800607E6
0x1800607dc  mov     edx, 45Ah
0x1800607e1  jmp     loc_1800609E9
0x1800607e6  xor     r13d, r13d
0x1800607e9  cmp     [rbp+var_20], r12d
0x1800607ed  jle     loc_1800609B4
0x1800607f3  mov     rax, [rbx]
0x1800607f6  mov     rbx, [rax+48h]
0x1800607fa  mov     rcx, [rbp+var_28]
0x1800607fe  test    rcx, rcx
0x180060801  jz      short loc_180060817
0x180060803  mov     rdx, [rcx]
0x180060806  mov     rax, [rdx+10h]
0x18006080a  call    _guard_dispatch_icall
0x18006080f  mov     [rbp+var_28], 0
0x180060817  lea     rdx, [rbp+var_28]
0x18006081b  mov     rcx, [rbp+var_38]
0x18006081f  mov     rax, rbx
0x180060822  call    _guard_dispatch_icall
0x180060827  mov     edi, eax
0x180060829  test    eax, eax
0x18006082b  js      loc_1800609E4
0x180060831  mov     rbx, [rbp+var_28]
0x180060835  test    rbx, rbx
0x180060838  jz      loc_1800609F4
0x18006083e  cmp     dword ptr [r14+18h], 16h
0x180060843  jnz     short loc_180060887
0x180060845  mov     dword ptr [rbp+bstrString], 0
0x18006084c  mov     rax, [rbx]
0x18006084f  lea     rdx, [rbp+bstrString]
0x180060853  mov     rcx, rbx
0x180060856  mov     rax, [rax+50h]
0x18006085a  call    _guard_dispatch_icall
0x18006085f  mov     rcx, [rbp+38h]; this
0x180060863  test    eax, eax
0x180060865  jns     short loc_18006087B
0x180060867  mov     r9d, eax; char *
0x18006086a  lea     r8, aCW1SSrcClientE_0; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x180060871  mov     edx, 468h; void *
0x180060876  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006087b  cmp     dword ptr [rbp+bstrString], 1
0x18006087f  jnz     loc_18006099E
0x180060885  jmp     short loc_1800608FA
0x180060887  mov     [rbp+bstrString], 0
0x18006088f  mov     rax, [rbx]
0x180060892  mov     rdi, [rax+38h]
0x180060896  xor     ecx, ecx; bstrString
0x180060898  call    cs:__imp_SysFreeString
0x18006089e  mov     [rbp+bstrString], 0
0x1800608a6  lea     rdx, [rbp+bstrString]
0x1800608aa  mov     rcx, rbx
0x1800608ad  mov     rax, rdi
0x1800608b0  call    _guard_dispatch_icall
0x1800608b5  test    eax, eax
0x1800608b7  jns     short loc_1800608C8
0x1800608b9  mov     rcx, [rbp+bstrString]; bstrString
0x1800608bd  call    cs:__imp_SysFreeString
0x1800608c3  jmp     loc_18006099E
0x1800608c8  or      edi, 0FFFFFFFFh
0x1800608cb  mov     [rsp+70h+cchCount2], edi; cchCount2
0x1800608cf  mov     rax, [r14+8]
0x1800608d3  mov     [rsp+70h+lpString2], rax; int
0x1800608d8  mov     r9d, edi; cchCount1
0x1800608db  mov     r8, [rbp+bstrString]; lpString1
0x1800608df  xor     edx, edx; dwCmpFlags
0x1800608e1  lea     ecx, [rdx+7Fh]; Locale
0x1800608e4  call    cs:__imp_CompareStringW
0x1800608ea  nop
0x1800608eb  mov     rcx, [rbp+bstrString]; bstrString
0x1800608ef  cmp     eax, 2
0x1800608f2  jnz     short loc_1800608BD
0x1800608f4  call    cs:__imp_SysFreeString
0x1800608fa  inc     r12d
0x1800608fd  lea     rdx, [rbp+var_40]; unsigned __int8 **
0x180060901  mov     rcx, r15; this
0x180060904  call    ?get_NextSlot@CDSArrayBuilder@@QEAAJPEAPEAE@Z; CDSArrayBuilder::get_NextSlot(uchar * *)
0x180060909  mov     rcx, [rbp+38h]; this
0x18006090d  test    eax, eax
0x18006090f  jns     short loc_180060925
0x180060911  mov     r9d, eax; char *
0x180060914  lea     r8, aCW1SSrcClientE_0; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x18006091b  mov     edx, 485h; void *
0x180060920  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180060925  mov     r9, [rbp+var_30]
0x180060929  mov     r8, r14
0x18006092c  mov     rdx, [rbp+var_40]
0x180060930  mov     rcx, [rbp+var_28]
0x180060934  call    GetElement
0x180060939  mov     edi, eax
0x18006093b  test    eax, eax
0x18006093d  js      loc_1800609CA
0x180060943  mov     edx, [r15+18h]
0x180060947  mov     ecx, edx
0x180060949  imul    ecx, [r15+10h]
0x18006094e  add     rcx, [r15+8]
0x180060952  cmp     [rbp+var_40], rcx
0x180060956  jz      short loc_18006097A
0x180060958  mov     rcx, [rbp+38h]; this
0x18006095c  mov     ebx, 80070057h
0x180060961  mov     r9d, ebx; char *
0x180060964  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\dsutil"...
0x18006096b  mov     edx, 85h; void *
0x180060970  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180060975  mov     r9d, ebx
0x180060978  jmp     short loc_180060984
0x18006097a  lea     eax, [rdx+1]
0x18006097d  mov     [r15+18h], eax
0x180060981  xor     r9d, r9d; char *
0x180060984  mov     rcx, [rbp+38h]; this
0x180060988  test    r9d, r9d
0x18006098b  jns     short loc_18006099E
0x18006098d  lea     r8, aCW1SSrcClientE_0; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x180060994  mov     edx, 487h; void *
0x180060999  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18006099e  inc     r13d
0x1800609a1  cmp     r13d, [rbp+var_20]
0x1800609a5  mov     rbx, [rbp+var_38]
0x1800609a9  jl      loc_1800607F3
0x1800609af  test    r12d, r12d
0x1800609b2  jnz     short loc_1800609EE
0x1800609b4  cmp     byte ptr [r14+20h], 0
0x1800609b9  jz      short loc_1800609EE
0x1800609bb  mov     edi, 8024000Dh
0x1800609c0  mov     r9d, edi
0x1800609c3  mov     edx, 48Ah
0x1800609c8  jmp     short loc_1800609D2
0x1800609ca  mov     r9d, eax; char *
0x1800609cd  mov     edx, 486h; void *
0x1800609d2  mov     rcx, [rbp+38h]; this
0x1800609d6  lea     r8, aCW1SSrcClientE_0; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x1800609dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800609e2  jmp     short loc_1800609F0
0x1800609e4  mov     edx, 462h
0x1800609e9  mov     r9d, edi
0x1800609ec  jmp     short loc_1800609D2
0x1800609ee  xor     edi, edi
0x1800609f0  mov     rbx, [rbp+var_28]
0x1800609f4  test    rbx, rbx
0x1800609f7  jz      short loc_180060A09
0x1800609f9  mov     rcx, [rbx]
0x1800609fc  mov     rax, [rcx+10h]
0x180060a00  mov     rcx, rbx
0x180060a03  call    _guard_dispatch_icall
0x180060a08  nop
0x180060a09  mov     eax, edi
0x180060a0b  mov     rcx, [rbp+var_10]
0x180060a0f  xor     rcx, rsp; StackCookie
0x180060a12  call    __security_check_cookie
0x180060a17  add     rsp, 70h
0x180060a1b  pop     r15
0x180060a1d  pop     r14
0x180060a1f  pop     r13
0x180060a21  pop     r12
0x180060a23  pop     rdi
0x180060a24  pop     rbx
0x180060a25  pop     rbp
0x180060a26  retn
```
