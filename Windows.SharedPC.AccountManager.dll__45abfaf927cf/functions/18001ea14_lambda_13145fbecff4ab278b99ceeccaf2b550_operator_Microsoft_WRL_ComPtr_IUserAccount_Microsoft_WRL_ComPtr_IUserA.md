# _lambda_13145fbecff4ab278b99ceeccaf2b550_::operator()(Microsoft::WRL::ComPtr<IUserAccount> &,Microsoft::WRL::ComPtr<IUserAccount> &)

- ea: `0x18001ea14`
- end: `0x18001eaaa`
- name: `??R_lambda_13145fbecff4ab278b99ceeccaf2b550_@@QEBA@AEAV?$ComPtr@UIUserAccount@@@WRL@Microsoft@@0@Z`
- size: `150`
- prototype: `bool __fastcall(unsigned __int64, __int64 *, __int64 *)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001e3bc`
- `0x18001e47c`
- `0x18001e4f8`
- `0x18001e694`

## callees

- `0x18000ccd4`
- `0x18001ea14`
- `0x180026010`

## string_xrefs

- `0x18001ea7b`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\util.h`
- `0x18001ea95`: `shellcommon\shell\sharedpc\accountmanager\lib\policy\util.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
bool __fastcall _lambda_13145fbecff4ab278b99ceeccaf2b550_::operator()(unsigned __int64 a1, __int64 *a2, __int64 *a3)
{
  __int64 v3; // rcx
  int v5; // eax
  __int64 v6; // rcx
  int v7; // eax
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  unsigned __int64 v11; // [rsp+30h] [rbp+8h] BYREF
  unsigned __int64 v12; // [rsp+38h] [rbp+10h] BYREF

  v11 = a1;
  v3 = *a2;
  v12 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v3 + 48LL))(v3, &v12);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x21,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\util.h",
      (const char *)(unsigned int)v5,
      v9);
  v6 = *a3;
  v11 = 0;
  v7 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v6 + 48LL))(v6, &v11);
  if ( v7 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"shellcommon\\shell\\sharedpc\\accountmanager\\lib\\policy\\util.h",
      (const char *)(unsigned int)v7,
      v9);
  return v12 > v11;
}

```

## disassembly

```asm
0x18001ea14  mov     [rsp+arg_0], rcx
0x18001ea19  push    rbx; int
0x18001ea1a  sub     rsp, 20h
0x18001ea1e  mov     rcx, [rdx]
0x18001ea21  mov     rbx, r8
0x18001ea24  mov     [rsp+28h+arg_8], 0
0x18001ea2d  lea     rdx, [rsp+28h+arg_8]
0x18001ea32  mov     rax, [rcx]
0x18001ea35  mov     rax, [rax+30h]
0x18001ea39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea3e  test    eax, eax
0x18001ea40  js      short loc_18001EA90
0x18001ea42  mov     rcx, [rbx]
0x18001ea45  lea     rdx, [rsp+28h+arg_0]
0x18001ea4a  mov     [rsp+28h+arg_0], 0
0x18001ea53  mov     rax, [rcx]
0x18001ea56  mov     rax, [rax+30h]
0x18001ea5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ea5f  test    eax, eax
0x18001ea61  js      short loc_18001EA76
0x18001ea63  mov     rax, [rsp+28h+arg_0]
0x18001ea68  cmp     [rsp+28h+arg_8], rax
0x18001ea6d  setnbe  al
0x18001ea70  add     rsp, 20h
0x18001ea74  pop     rbx
0x18001ea75  retn
0x18001ea76  mov     rcx, [rsp+28h]; this
0x18001ea7b  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001ea82  mov     r9d, eax; char *
0x18001ea85  mov     edx, 24h ; '$'; void *
0x18001ea8a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001ea90  mov     rcx, [rsp+28h]; this
0x18001ea95  lea     r8, aShellcommonShe_4; "shellcommon\\shell\\sharedpc\\accountma"...
0x18001ea9c  mov     r9d, eax; char *
0x18001ea9f  mov     edx, 21h ; '!'; void *
0x18001eaa4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
