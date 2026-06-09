# TryGetRegisteredTask(Microsoft::WRL::ComPtr<ITaskService> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001cb18`
- end: `0x18001cc7a`
- name: `?TryGetRegisteredTask@@YA?AV?$tuple@_NV?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@@std@@AEBV?$ComPtr@UITaskService@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z`
- size: `354`
- prototype: `__int64 __fastcall(__int64, _QWORD *, const OLECHAR *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001b83c`

## callees

- `0x180003520`
- `0x18000a7fc`
- `0x1800181c4`
- `0x18001cb18`
- `0x1800222e4`
- `0x18002a010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001cbd9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cc2c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cbd9`
- `OLEAUT32!__imp_SysFreeString` at `0x18001cc2c`

## string_xrefs

- `0x18001cc68`: `onecore\internal\shell\inc\taskutils.h`

## pseudocode

```c
__int64 __fastcall TryGetRegisteredTask(__int64 a1, _QWORD *a2, const OLECHAR *a3)
{
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rcx
  void (*v10)(void); // rax
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v14; // [rsp+20h] [rbp-30h]
  __int64 v15; // [rsp+28h] [rbp-28h] BYREF
  __int64 v16; // [rsp+30h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  bstrString = (BSTR)a1;
  GetNewTaskFolder(&v16, a2);
  if ( *((_QWORD *)a3 + 3) > 7u )
    a3 = *(const OLECHAR **)a3;
  wil::make_bstr(&bstrString, a3);
  v15 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, BSTR, __int64 *))(*(_QWORD *)v16 + 104LL))(v16, bstrString, &v15);
  if ( (unsigned int)(v5 + 2147024894) <= 1 )
  {
    *(_QWORD *)a1 = 0;
    *(_BYTE *)(a1 + 8) = 0;
    v11 = v15;
    if ( v15 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v11 + 16LL))(v11, v6, v7, (unsigned int)v5);
    }
    if ( bstrString )
      SysFreeString(bstrString);
    v12 = v16;
    if ( v16 )
    {
      v16 = 0;
      v10 = *(void (**)(void))(*(_QWORD *)v12 + 16LL);
      goto LABEL_19;
    }
  }
  else
  {
    if ( v5 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x34,
        (int)"onecore\\internal\\shell\\inc\\taskutils.h",
        (const char *)(unsigned int)v5,
        v14);
    v8 = v15;
    *(_QWORD *)a1 = v15;
    if ( v8 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 8LL))(v8);
      v8 = v15;
    }
    *(_BYTE *)(a1 + 8) = 1;
    if ( v8 )
    {
      v15 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    }
    if ( bstrString )
      SysFreeString(bstrString);
    v9 = v16;
    if ( v16 )
    {
      v16 = 0;
      v10 = *(void (**)(void))(*(_QWORD *)v9 + 16LL);
LABEL_19:
      v10();
    }
  }
  return a1;
}

```

## disassembly

```asm
0x18001cb18  push    rbp
0x18001cb1a  push    rbx
0x18001cb1b  push    rdi
0x18001cb1c  mov     rbp, rsp
0x18001cb1f  sub     rsp, 50h
0x18001cb23  mov     rax, cs:__security_cookie
0x18001cb2a  xor     rax, rsp
0x18001cb2d  mov     [rbp+var_10], rax
0x18001cb31  mov     rdi, r8
0x18001cb34  mov     rbx, rcx
0x18001cb37  mov     [rbp+bstrString], rcx
0x18001cb3b  lea     rcx, [rbp+var_20]
0x18001cb3f  call    ?GetNewTaskFolder@@YA?AV?$ComPtr@UITaskFolder@@@WRL@Microsoft@@AEBV?$ComPtr@UITaskService@@@23@@Z; GetNewTaskFolder(Microsoft::WRL::ComPtr<ITaskService> const &)
0x18001cb44  nop
0x18001cb45  cmp     qword ptr [rdi+18h], 7
0x18001cb4a  jbe     short loc_18001CB4F
0x18001cb4c  mov     rdi, [rdi]
0x18001cb4f  mov     rdx, rdi
0x18001cb52  lea     rcx, [rbp+bstrString]
0x18001cb56  call    ?make_bstr@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAG@Z$1?SysFreeString@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@PEBG@Z; wil::make_bstr(ushort const *)
0x18001cb5b  nop
0x18001cb5c  mov     [rbp+var_28], 0
0x18001cb64  mov     rcx, [rbp+var_20]
0x18001cb68  mov     rax, [rcx]
0x18001cb6b  lea     r8, [rbp+var_28]
0x18001cb6f  mov     rdx, [rbp+bstrString]
0x18001cb73  mov     rax, [rax+68h]
0x18001cb77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb7c  mov     r9d, eax; char *
0x18001cb7f  add     eax, 7FF8FFFEh
0x18001cb84  cmp     eax, 1
0x18001cb87  jbe     short loc_18001CBFA
0x18001cb89  mov     rcx, [rbp+18h]; this
0x18001cb8d  test    r9d, r9d
0x18001cb90  js      loc_18001CC68
0x18001cb96  mov     rcx, [rbp+var_28]
0x18001cb9a  mov     [rbx], rcx
0x18001cb9d  test    rcx, rcx
0x18001cba0  jz      short loc_18001CBB2
0x18001cba2  mov     rax, [rcx]
0x18001cba5  mov     rax, [rax+8]
0x18001cba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbae  mov     rcx, [rbp+var_28]
0x18001cbb2  mov     byte ptr [rbx+8], 1
0x18001cbb6  test    rcx, rcx
0x18001cbb9  jz      short loc_18001CBD0
0x18001cbbb  mov     [rbp+var_28], 0
0x18001cbc3  mov     rax, [rcx]
0x18001cbc6  mov     rax, [rax+10h]
0x18001cbca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cbcf  nop
0x18001cbd0  mov     rcx, [rbp+bstrString]; bstrString
0x18001cbd4  test    rcx, rcx
0x18001cbd7  jz      short loc_18001CBE0
0x18001cbd9  call    cs:__imp_SysFreeString
0x18001cbdf  nop
0x18001cbe0  mov     rcx, [rbp+var_20]
0x18001cbe4  test    rcx, rcx
0x18001cbe7  jz      short loc_18001CC51
0x18001cbe9  mov     [rbp+var_20], 0
0x18001cbf1  mov     rax, [rcx]
0x18001cbf4  mov     rax, [rax+10h]
0x18001cbf8  jmp     short loc_18001CC4B
0x18001cbfa  mov     qword ptr [rbx], 0
0x18001cc01  mov     byte ptr [rbx+8], 0
0x18001cc05  mov     rcx, [rbp+var_28]
0x18001cc09  test    rcx, rcx
0x18001cc0c  jz      short loc_18001CC23
0x18001cc0e  mov     [rbp+var_28], 0
0x18001cc16  mov     rax, [rcx]
0x18001cc19  mov     rax, [rax+10h]
0x18001cc1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc22  nop
0x18001cc23  mov     rcx, [rbp+bstrString]; bstrString
0x18001cc27  test    rcx, rcx
0x18001cc2a  jz      short loc_18001CC33
0x18001cc2c  call    cs:__imp_SysFreeString
0x18001cc32  nop
0x18001cc33  mov     rcx, [rbp+var_20]
0x18001cc37  test    rcx, rcx
0x18001cc3a  jz      short loc_18001CC51
0x18001cc3c  mov     [rbp+var_20], 0
0x18001cc44  mov     rdx, [rcx]
0x18001cc47  mov     rax, [rdx+10h]
0x18001cc4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cc50  nop
0x18001cc51  mov     rax, rbx
0x18001cc54  mov     rcx, [rbp+var_10]
0x18001cc58  xor     rcx, rsp; StackCookie
0x18001cc5b  call    __security_check_cookie
0x18001cc60  add     rsp, 50h
0x18001cc64  pop     rdi
0x18001cc65  pop     rbx
0x18001cc66  pop     rbp
0x18001cc67  retn
0x18001cc68  lea     r8, aOnecoreInterna_8; "onecore\\internal\\shell\\inc\\taskutil"...
0x18001cc6f  mov     edx, 34h ; '4'; void *
0x18001cc74  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
