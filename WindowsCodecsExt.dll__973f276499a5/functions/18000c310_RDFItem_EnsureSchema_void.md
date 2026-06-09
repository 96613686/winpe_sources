# RDFItem::EnsureSchema(void)

- ea: `0x18000c310`
- end: `0x18000c44e`
- name: `?EnsureSchema@RDFItem@@MEAAJXZ`
- size: `318`
- prototype: `__int64 __fastcall(RDFItem *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000c310`
- `0x1800171c4`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000c36c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000c36c`
- `OLEAUT32!__imp_SysStringLen` at `0x18000c3fb`
- `OLEAUT32!__imp_SysStringLen` at `0x18000c3fb`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000c3a7`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18000c3a7`

## string_xrefs

- `0x18000c386`: `xmlns`

## pseudocode

```c
__int64 __fastcall RDFItem::EnsureSchema(RDFItem *this)
{
  __int64 result; // rax
  int v3; // eax
  unsigned int v4; // esi
  int v5; // eax
  __int64 *v6; // rcx
  char *v7; // rdx
  __int64 v8; // r8
  int v9; // esi
  BSTR bstrString; // [rsp+40h] [rbp+8h] BYREF

  result = 0;
  bstrString = 0;
  if ( *((_QWORD *)this + 8) )
    return result;
  v3 = (*(__int64 (__fastcall **)(_QWORD, BSTR *))(**((_QWORD **)this + 2) + 56LL))(*((_QWORD *)this + 2), &bstrString);
  v4 = v3;
  if ( v3 >= 0 )
  {
    if ( v3 )
    {
      v4 = -2147467259;
      if ( g_doStackCaptures )
        DoStackCapture(-2147467259);
      goto LABEL_5;
    }
    v5 = CompareStringW(0x400u, 0, bstrString, 5, L"xmlns", 5);
    v6 = (__int64 *)*((_QWORD *)this + 2);
    v7 = (char *)this + 64;
    v8 = *v6;
    if ( v5 == 2 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64 *, char *))(v8 + 208))(v6, v7);
      if ( *((_QWORD *)this + 8) && SysStringLen(bstrString) && v9 >= 0 )
        goto LABEL_17;
      v3 = (*(__int64 (__fastcall **)(_QWORD, char *))(**((_QWORD **)this + 2) + 312LL))(
             *((_QWORD *)this + 2),
             (char *)this + 64);
    }
    else
    {
      v3 = (*(__int64 (__fastcall **)(__int64 *, char *))(v8 + 312))(v6, v7);
    }
    v4 = v3;
    if ( v3 < 0 )
    {
      if ( !g_doStackCaptures )
        goto LABEL_5;
      goto LABEL_4;
    }
LABEL_17:
    v4 = 0;
    goto LABEL_5;
  }
  if ( g_doStackCaptures )
LABEL_4:
    DoStackCapture(v3);
LABEL_5:
  if ( bstrString )
    SysFreeString(bstrString);
  return v4;
}

```

## disassembly

```asm
0x18000c310  mov     [rsp+arg_10], rbx
0x18000c315  push    rdi
0x18000c316  sub     rsp, 30h
0x18000c31a  xor     eax, eax
0x18000c31c  mov     rbx, rcx
0x18000c31f  mov     [rsp+38h+bstrString], rax
0x18000c324  cmp     [rcx+40h], rax
0x18000c328  jz      short loc_18000C335
0x18000c32a  mov     rbx, [rsp+38h+arg_10]
0x18000c32f  add     rsp, 30h
0x18000c333  pop     rdi
0x18000c334  retn
0x18000c335  mov     rcx, [rcx+10h]
0x18000c339  lea     rdx, [rsp+38h+bstrString]
0x18000c33e  mov     [rsp+38h+arg_8], rsi
0x18000c343  mov     rax, [rcx]
0x18000c346  mov     rax, [rax+38h]
0x18000c34a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c34f  mov     esi, eax
0x18000c351  test    eax, eax
0x18000c353  jns     short loc_18000C37B
0x18000c355  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000c35c  jnz     loc_18000C410
0x18000c362  mov     rcx, [rsp+38h+bstrString]; bstrString
0x18000c367  test    rcx, rcx
0x18000c36a  jz      short loc_18000C372
0x18000c36c  call    cs:__imp_SysFreeString
0x18000c372  mov     eax, esi
0x18000c374  mov     rsi, [rsp+38h+arg_8]
0x18000c379  jmp     short loc_18000C32A
0x18000c37b  jnz     loc_18000C430
0x18000c381  mov     r8, [rsp+38h+bstrString]; lpString1
0x18000c386  lea     rax, aXmlns; "xmlns"
0x18000c38d  mov     [rsp+38h+cchCount2], 5; cchCount2
0x18000c395  mov     r9d, 5; cchCount1
0x18000c39b  xor     edx, edx; dwCmpFlags
0x18000c39d  mov     [rsp+38h+lpString2], rax; lpString2
0x18000c3a2  mov     ecx, 400h; Locale
0x18000c3a7  call    cs:__imp_CompareStringW
0x18000c3ad  mov     rcx, [rbx+10h]
0x18000c3b1  lea     rdx, [rbx+40h]
0x18000c3b5  mov     r8, [rcx]
0x18000c3b8  cmp     eax, 2
0x18000c3bb  jz      short loc_18000C3E1
0x18000c3bd  mov     rax, [r8+138h]
0x18000c3c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3c9  mov     esi, eax
0x18000c3cb  test    eax, eax
0x18000c3cd  jns     short loc_18000C409
0x18000c3cf  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000c3d6  jz      short loc_18000C362
0x18000c3d8  mov     ecx, eax; int
0x18000c3da  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000c3df  jmp     short loc_18000C362
0x18000c3e1  mov     rax, [r8+0D0h]
0x18000c3e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3ed  cmp     qword ptr [rbx+40h], 0
0x18000c3f2  mov     esi, eax
0x18000c3f4  jz      short loc_18000C41C
0x18000c3f6  mov     rcx, [rsp+38h+bstrString]; pbstr
0x18000c3fb  call    cs:__imp_SysStringLen
0x18000c401  test    eax, eax
0x18000c403  jz      short loc_18000C41C
0x18000c405  test    esi, esi
0x18000c407  js      short loc_18000C41C
0x18000c409  xor     esi, esi
0x18000c40b  jmp     loc_18000C362
0x18000c410  mov     ecx, eax; int
0x18000c412  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000c417  jmp     loc_18000C362
0x18000c41c  mov     rcx, [rbx+10h]
0x18000c420  lea     rdx, [rbx+40h]
0x18000c424  mov     rax, [rcx]
0x18000c427  mov     rax, [rax+138h]
0x18000c42e  jmp     short loc_18000C3C4
0x18000c430  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000c437  mov     esi, 80004005h
0x18000c43c  jz      loc_18000C362
0x18000c442  mov     ecx, esi; int
0x18000c444  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000c449  jmp     loc_18000C362
```
