# WaasMedic::TasksHelper::GetLastTaskRuntime(ushort const *,_FILETIME *)

- ea: `0x18005f68c`
- end: `0x18005f7c6`
- name: `?GetLastTaskRuntime@TasksHelper@WaasMedic@@QEAAJPEBGPEAU_FILETIME@@@Z`
- size: `314`
- prototype: `__int64 __fastcall(WaasMedic::TasksHelper *__hidden this, const unsigned __int16 *, struct _FILETIME *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800534f0`

## callees

- `0x180009a54`
- `0x18002543c`
- `0x18005c55c`
- `0x18005f68c`
- `0x180060638`
- `0x180064010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18005f7b3`
- `OLEAUT32!__imp_SysFreeString` at `0x18005f7b3`

## string_xrefs

- `0x18005f77b`: `StartComponentCleanup`
- `0x18005f6d5`: `onecore\enduser\waasmedic\lib\util\taskshelper.cpp`
- `0x18005f714`: `onecore\enduser\waasmedic\lib\util\taskshelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaasMedic::TasksHelper::GetLastTaskRuntime(
        WaasMedic::TasksHelper *this,
        const unsigned __int16 *a2,
        struct _FILETIME *a3)
{
  unsigned int v4; // ebx
  int v5; // eax
  __int64 v7; // [rsp+20h] [rbp-30h] BYREF
  _QWORD v8[5]; // [rsp+28h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  const unsigned __int16 *v10; // [rsp+68h] [rbp+18h] BYREF
  struct _FILETIME *v11; // [rsp+70h] [rbp+20h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp+28h] BYREF

  v11 = a3;
  v10 = a2;
  wil::make_bstr(&bstrString);
  v10 = 0;
  v7 = 0;
  if ( v11 )
  {
    if ( *((_BYTE *)this + 17) )
    {
      *v11 = 0;
      v8[0] = this;
      v8[1] = &bstrString;
      v8[2] = &v10;
      v8[3] = &v7;
      v8[4] = &v11;
      v5 = lambda_41a5acf67e518ea8637ec79e87cfb27d_::operator()(v8);
      v4 = v5;
      if ( v5 < 0 )
        LogLevelW(2u, L"Failed to get last runtime for %s! hr = 0x%08x", L"StartComponentCleanup", (unsigned int)v5, v7);
      if ( v10 )
        (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v10 + 16LL))(v10);
    }
    else
    {
      v4 = -2147019873;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x19F,
        (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\taskshelper.cpp",
        (const char *)0x8007139FLL,
        v7);
      if ( v10 )
        (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v10 + 16LL))(v10);
    }
  }
  else
  {
    v4 = -2147467261;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x19E,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\util\\taskshelper.cpp",
      (const char *)0x80004003LL,
      v7);
    if ( v10 )
      (*(void (__fastcall **)(const unsigned __int16 *))(*(_QWORD *)v10 + 16LL))(v10);
  }
  if ( bstrString )
    SysFreeString(bstrString);
  return v4;
}

```

## disassembly

```asm
0x18005f68c  mov     [rsp-8+arg_0], rbx
0x18005f691  mov     [rsp-8+arg_10], r8
0x18005f696  mov     [rsp-8+arg_8], rdx
0x18005f69b  push    rbp
0x18005f69c  mov     rbp, rsp
0x18005f69f  sub     rsp, 50h
0x18005f6a3  mov     rbx, rcx
0x18005f6a6  lea     rcx, [rbp+bstrString]
0x18005f6aa  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18005f6af  nop
0x18005f6b0  mov     [rbp+arg_8], 0
0x18005f6b8  xorps   xmm0, xmm0
0x18005f6bb  movsd   [rbp+var_30], xmm0
0x18005f6c0  mov     rax, [rbp+arg_10]
0x18005f6c4  test    rax, rax
0x18005f6c7  jnz     short loc_18005F702
0x18005f6c9  mov     rcx, [rbp+8]; this
0x18005f6cd  mov     ebx, 80004003h
0x18005f6d2  mov     r9d, ebx; char *
0x18005f6d5  lea     r8, aOnecoreEnduser_18; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18005f6dc  mov     edx, 19Eh; void *
0x18005f6e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f6e6  nop
0x18005f6e7  mov     rcx, [rbp+arg_8]
0x18005f6eb  test    rcx, rcx
0x18005f6ee  jz      short loc_18005F6FD
0x18005f6f0  mov     rax, [rcx]
0x18005f6f3  mov     rax, [rax+10h]
0x18005f6f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f6fc  nop
0x18005f6fd  jmp     loc_18005F7AA
0x18005f702  cmp     byte ptr [rbx+11h], 0
0x18005f706  jnz     short loc_18005F73E
0x18005f708  mov     rcx, [rbp+8]; this
0x18005f70c  mov     ebx, 8007139Fh
0x18005f711  mov     r9d, ebx; char *
0x18005f714  lea     r8, aOnecoreEnduser_18; "onecore\\enduser\\waasmedic\\lib\\util"...
0x18005f71b  mov     edx, 19Fh; void *
0x18005f720  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005f725  nop
0x18005f726  mov     rcx, [rbp+arg_8]
0x18005f72a  test    rcx, rcx
0x18005f72d  jz      short loc_18005F73C
0x18005f72f  mov     rax, [rcx]
0x18005f732  mov     rax, [rax+10h]
0x18005f736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f73b  nop
0x18005f73c  jmp     short loc_18005F7AA
0x18005f73e  mov     qword ptr [rax], 0
0x18005f745  mov     [rbp+var_28], rbx
0x18005f749  lea     rax, [rbp+bstrString]
0x18005f74d  mov     [rbp+var_20], rax
0x18005f751  lea     rax, [rbp+arg_8]
0x18005f755  mov     [rbp+var_18], rax
0x18005f759  lea     rax, [rbp+var_30]
0x18005f75d  mov     [rbp+var_10], rax
0x18005f761  lea     rax, [rbp+arg_10]
0x18005f765  mov     [rbp+var_8], rax
0x18005f769  lea     rcx, [rbp+var_28]
0x18005f76d  call    _lambda_41a5acf67e518ea8637ec79e87cfb27d___operator__
0x18005f772  mov     ebx, eax
0x18005f774  test    eax, eax
0x18005f776  jns     short loc_18005F794
0x18005f778  mov     r9d, eax
0x18005f77b  lea     r8, aStartcomponent; "StartComponentCleanup"
0x18005f782  lea     rdx, aFailedToGetLas; "Failed to get last runtime for %s! hr ="...
0x18005f789  mov     ecx, 2; unsigned __int8
0x18005f78e  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18005f793  nop
0x18005f794  mov     rcx, [rbp+arg_8]
0x18005f798  test    rcx, rcx
0x18005f79b  jz      short loc_18005F7AA
0x18005f79d  mov     rax, [rcx]
0x18005f7a0  mov     rax, [rax+10h]
0x18005f7a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f7a9  nop
0x18005f7aa  mov     rcx, [rbp+bstrString]; bstrString
0x18005f7ae  test    rcx, rcx
0x18005f7b1  jz      short loc_18005F7B9
0x18005f7b3  call    cs:__imp_SysFreeString
0x18005f7b9  mov     eax, ebx
0x18005f7bb  mov     rbx, [rsp+50h+arg_0]
0x18005f7c0  add     rsp, 50h
0x18005f7c4  pop     rbp
0x18005f7c5  retn
```
