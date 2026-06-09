# SetTaskEnabledValue(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,bool)

- ea: `0x18001b83c`
- end: `0x18001b968`
- name: `?SetTaskEnabledValue@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_N@Z`
- size: `300`
- prototype: `char *__fastcall(__int64, unsigned __int8)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180014788`

## callees

- `0x180003520`
- `0x18000a7fc`
- `0x180018350`
- `0x18001b83c`
- `0x18001cb18`
- `0x18002a010`

## string_xrefs

- `0x18001b956`: `onecore\internal\shell\inc\taskutils.h`

## pseudocode

```c
char *__fastcall SetTaskEnabledValue(__int64 a1, unsigned __int8 a2)
{
  char *result; // rax
  char v5; // bl
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // [rsp+20h] [rbp-30h] BYREF
  char v12; // [rsp+30h] [rbp-20h] BYREF
  __int64 v13; // [rsp+38h] [rbp-18h]
  int v14[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  GetTaskService((int)v14);
  v13 = 0;
  result = (char *)TryGetRegisteredTask(&v11, v14, a1);
  v5 = result[8];
  v6 = 0;
  if ( &v12 != result )
  {
    v6 = *(_QWORD *)result;
    *(_QWORD *)result = 0;
  }
  v7 = v13;
  v13 = v6;
  if ( v7 )
    result = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = v11;
  if ( v11 )
  {
    v11 = 0;
    result = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  }
  if ( v5 )
  {
    result = (char *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v13 + 88LL))(
                       v13,
                       (unsigned __int16)((a2 ^ 1) - 1));
    if ( (int)result < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x40,
        (unsigned int)"onecore\\internal\\shell\\inc\\taskutils.h",
        (const char *)(unsigned int)result,
        v11);
  }
  v9 = v13;
  if ( v13 )
  {
    v13 = 0;
    result = (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
  }
  v10 = *(_QWORD *)v14;
  if ( *(_QWORD *)v14 )
  {
    *(_QWORD *)v14 = 0;
    return (char *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  }
  return result;
}

```

## disassembly

```asm
0x18001b83c  mov     [rsp-8+arg_8], rbx
0x18001b841  mov     [rsp-8+arg_10], rdi
0x18001b846  push    rbp
0x18001b847  mov     rbp, rsp
0x18001b84a  sub     rsp, 50h
0x18001b84e  mov     rax, cs:__security_cookie
0x18001b855  xor     rax, rsp
0x18001b858  mov     [rbp+var_8], rax
0x18001b85c  mov     dil, dl
0x18001b85f  mov     rbx, rcx
0x18001b862  lea     rcx, [rbp+var_10]; int
0x18001b866  call    ?GetTaskService@@YA?AV?$ComPtr@UITaskService@@@WRL@Microsoft@@XZ; GetTaskService(void)
0x18001b86b  nop
0x18001b86c  mov     [rbp+var_18], 0
0x18001b874  mov     r8, rbx
0x18001b877  lea     rdx, [rbp+var_10]
0x18001b87b  lea     rcx, [rbp+var_30]
0x18001b87f  call    ?TryGetRegisteredTask@@YA?AV?$tuple@_NV?$ComPtr@UIRegisteredTask@@@WRL@Microsoft@@@std@@AEBV?$ComPtr@UITaskService@@@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; TryGetRegisteredTask(Microsoft::WRL::ComPtr<ITaskService> const &,std::wstring const &)
0x18001b884  mov     bl, [rax+8]
0x18001b887  xor     edx, edx
0x18001b889  lea     rcx, [rbp+var_20]
0x18001b88d  cmp     rcx, rax
0x18001b890  jz      short loc_18001B89C
0x18001b892  mov     rdx, [rax]
0x18001b895  mov     qword ptr [rax], 0
0x18001b89c  mov     rcx, [rbp+var_18]
0x18001b8a0  mov     [rbp+var_18], rdx
0x18001b8a4  test    rcx, rcx
0x18001b8a7  jz      short loc_18001B8B6
0x18001b8a9  mov     rax, [rcx]
0x18001b8ac  mov     rax, [rax+10h]
0x18001b8b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8b5  nop
0x18001b8b6  mov     rcx, [rbp+var_30]
0x18001b8ba  test    rcx, rcx
0x18001b8bd  jz      short loc_18001B8D4
0x18001b8bf  mov     [rbp+var_30], 0
0x18001b8c7  mov     rax, [rcx]
0x18001b8ca  mov     rax, [rax+10h]
0x18001b8ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8d3  nop
0x18001b8d4  test    bl, bl
0x18001b8d6  jz      short loc_18001B8FB
0x18001b8d8  mov     rcx, [rbp+var_18]
0x18001b8dc  mov     rax, [rcx]
0x18001b8df  xor     dil, 1
0x18001b8e3  movzx   edx, dil
0x18001b8e7  dec     dx
0x18001b8ea  mov     rax, [rax+58h]
0x18001b8ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b8f3  mov     rcx, [rbp+8]; this
0x18001b8f7  test    eax, eax
0x18001b8f9  js      short loc_18001B953
0x18001b8fb  mov     rcx, [rbp+var_18]
0x18001b8ff  test    rcx, rcx
0x18001b902  jz      short loc_18001B919
0x18001b904  mov     [rbp+var_18], 0
0x18001b90c  mov     rax, [rcx]
0x18001b90f  mov     rax, [rax+10h]
0x18001b913  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b918  nop
0x18001b919  mov     rcx, qword ptr [rbp+var_10]
0x18001b91d  test    rcx, rcx
0x18001b920  jz      short loc_18001B937
0x18001b922  mov     qword ptr [rbp+var_10], 0
0x18001b92a  mov     rax, [rcx]
0x18001b92d  mov     rax, [rax+10h]
0x18001b931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b936  nop
0x18001b937  mov     rcx, [rbp+var_8]
0x18001b93b  xor     rcx, rsp; StackCookie
0x18001b93e  call    __security_check_cookie
0x18001b943  mov     rbx, [rsp+50h+arg_8]
0x18001b948  mov     rdi, [rsp+50h+arg_10]
0x18001b94d  add     rsp, 50h
0x18001b951  pop     rbp
0x18001b952  retn
0x18001b953  mov     r9d, eax; char *
0x18001b956  lea     r8, aOnecoreInterna_8; "onecore\\internal\\shell\\inc\\taskutil"...
0x18001b95d  mov     edx, 40h ; '@'; void *
0x18001b962  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
