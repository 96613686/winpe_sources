# SetTaskEnabledValueForCurrentUser(Microsoft::WRL::ComPtr<ITaskService> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x18001b970`
- end: `0x18001ba98`
- name: `?SetTaskEnabledValueForCurrentUser@@YAXAEBV?$ComPtr@UITaskService@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z`
- size: `296`
- prototype: `void __fastcall(_QWORD *, _QWORD *, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001b728`

## callees

- `0x180003520`
- `0x18000a7fc`
- `0x18001b970`
- `0x1800222e4`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001ba15`
- `OLEAUT32!__imp_SysFreeString` at `0x18001ba15`

## string_xrefs

- `0x18001ba57`: `onecore\internal\shell\inc\taskutils.h`
- `0x18001ba71`: `onecore\internal\shell\inc\taskutils.h`
- `0x18001ba86`: `onecore\internal\shell\inc\taskutils.h`

## pseudocode

```c
void __fastcall SetTaskEnabledValueForCurrentUser(_QWORD *a1, _QWORD *a2, char a3)
{
  int v5; // eax
  __int64 v6; // rax
  int v7; // eax
  int v8; // eax
  __int64 *v9; // rcx
  int v10[2]; // [rsp+20h] [rbp-28h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_QWORD *)v10 = 0;
  v5 = (**(__int64 (__fastcall ***)(_QWORD, GUID *, int *))*a1)(*a1, &GUID_ee57976b_0c5e_4fe9_8c91_a54082ef699b, v10);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x53,
      (unsigned int)"onecore\\internal\\shell\\inc\\taskutils.h",
      (const char *)(unsigned int)v5,
      v10[0]);
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  wil::make_bstr(&bstrString, a2);
  v6 = **(_QWORD **)v10;
  if ( a3 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, BSTR))(v6 + 64))(*(_QWORD *)v10, bstrString);
    if ( v7 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x58,
        (unsigned int)"onecore\\internal\\shell\\inc\\taskutils.h",
        (const char *)(unsigned int)v7,
        v10[0]);
  }
  else
  {
    v8 = (*(__int64 (__fastcall **)(_QWORD, BSTR))(v6 + 56))(*(_QWORD *)v10, bstrString);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x5C,
        (unsigned int)"onecore\\internal\\shell\\inc\\taskutils.h",
        (const char *)(unsigned int)v8,
        v10[0]);
  }
  if ( bstrString )
    SysFreeString(bstrString);
  v9 = *(__int64 **)v10;
  if ( *(_QWORD *)v10 )
  {
    *(_QWORD *)v10 = 0;
    (*(void (__fastcall **)(__int64 *))(*v9 + 16))(v9);
  }
}

```

## disassembly

```asm
0x18001b970  mov     [rsp+arg_10], rbx
0x18001b975  push    rdi
0x18001b976  sub     rsp, 40h
0x18001b97a  mov     rax, cs:__security_cookie
0x18001b981  xor     rax, rsp
0x18001b984  mov     [rsp+48h+var_18], rax
0x18001b989  mov     dil, r8b
0x18001b98c  mov     rbx, rdx
0x18001b98f  mov     qword ptr [rsp+48h+var_28], 0; int
0x18001b998  mov     rcx, [rcx]
0x18001b99b  mov     rax, [rcx]
0x18001b99e  lea     r8, [rsp+48h+var_28]
0x18001b9a3  lea     rdx, _GUID_ee57976b_0c5e_4fe9_8c91_a54082ef699b
0x18001b9aa  mov     rax, [rax]
0x18001b9ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9b2  nop
0x18001b9b3  mov     rcx, [rsp+48h]; this
0x18001b9b8  test    eax, eax
0x18001b9ba  js      loc_18001BA83
0x18001b9c0  cmp     qword ptr [rbx+18h], 7
0x18001b9c5  jbe     short loc_18001B9CA
0x18001b9c7  mov     rbx, [rbx]
0x18001b9ca  mov     rdx, rbx
0x18001b9cd  lea     rcx, [rsp+48h+bstrString]
0x18001b9d2  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18001b9d7  nop
0x18001b9d8  mov     rcx, qword ptr [rsp+48h+var_28]
0x18001b9dd  mov     rdx, [rsp+48h+bstrString]
0x18001b9e2  mov     rax, [rcx]
0x18001b9e5  test    dil, dil
0x18001b9e8  jz      short loc_18001B9F9
0x18001b9ea  mov     rax, [rax+40h]
0x18001b9ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b9f3  test    eax, eax
0x18001b9f5  js      short loc_18001BA69
0x18001b9f7  jmp     short loc_18001BA0B
0x18001b9f9  mov     rax, [rax+38h]
0x18001b9fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba02  mov     rcx, [rsp+48h]; this
0x18001ba07  test    eax, eax
0x18001ba09  js      short loc_18001BA54
0x18001ba0b  mov     rcx, [rsp+48h+bstrString]; bstrString
0x18001ba10  test    rcx, rcx
0x18001ba13  jz      short loc_18001BA1C
0x18001ba15  call    cs:__imp_SysFreeString
0x18001ba1b  nop
0x18001ba1c  mov     rcx, qword ptr [rsp+48h+var_28]
0x18001ba21  test    rcx, rcx
0x18001ba24  jz      short loc_18001BA3C
0x18001ba26  mov     qword ptr [rsp+48h+var_28], 0
0x18001ba2f  mov     rax, [rcx]
0x18001ba32  mov     rax, [rax+10h]
0x18001ba36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba3b  nop
0x18001ba3c  mov     rcx, [rsp+48h+var_18]
0x18001ba41  xor     rcx, rsp; StackCookie
0x18001ba44  call    __security_check_cookie
0x18001ba49  mov     rbx, [rsp+48h+arg_10]
0x18001ba4e  add     rsp, 40h
0x18001ba52  pop     rdi
0x18001ba53  retn
0x18001ba54  mov     r9d, eax; char *
0x18001ba57  lea     r8, aOnecoreInterna_8; "onecore\\internal\\shell\\inc\\taskutil"...
0x18001ba5e  mov     edx, 5Ch ; '\'; void *
0x18001ba63  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001ba69  mov     rcx, [rsp+48h]; this
0x18001ba6e  mov     r9d, eax; char *
0x18001ba71  lea     r8, aOnecoreInterna_8; "onecore\\internal\\shell\\inc\\taskutil"...
0x18001ba78  mov     edx, 58h ; 'X'; void *
0x18001ba7d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001ba83  mov     r9d, eax; char *
0x18001ba86  lea     r8, aOnecoreInterna_8; "onecore\\internal\\shell\\inc\\taskutil"...
0x18001ba8d  mov     edx, 53h ; 'S'; void *
0x18001ba92  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
