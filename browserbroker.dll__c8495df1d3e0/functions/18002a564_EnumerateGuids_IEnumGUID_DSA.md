# _EnumerateGuids(IEnumGUID *,_DSA * *)

- ea: `0x18002a564`
- end: `0x18002a61f`
- name: `?_EnumerateGuids@@YAJPEAUIEnumGUID@@PEAPEAU_DSA@@@Z`
- size: `187`
- prototype: `__int64 __fastcall(struct IEnumGUID *, struct _DSA **)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002a31c`

## callees

- `0x180002ce0`
- `0x18000dc94`
- `0x18002a564`
- `0x18002d010`

## import_xrefs

- `iertutil!__imp_DSA_Create` at `0x18002a58b`
- `iertutil!__imp_DSA_Create` at `0x18002a58b`
- `iertutil!__imp_DSA_InsertItem` at `0x18002a5d6`
- `iertutil!__imp_DSA_InsertItem` at `0x18002a5d6`

## string_xrefs

- `0x18002a59e`: `onecoreuap\inetcore\spartan\desktopbroker\filebrokers\comcatex.cpp`

## pseudocode

```c
__int64 __fastcall _EnumerateGuids(struct IEnumGUID *a1, struct _DSA **a2)
{
  struct _DSA *v4; // rax
  const char *v5; // r9
  int v6; // ecx
  __int64 result; // rax
  int v8; // [rsp+30h] [rbp-28h] BYREF
  __int128 pitem; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = DSA_Create(16, 4);
  *a2 = v4;
  if ( !v4 )
    wil::details::in1diag3::_FailFast_NullAlloc(
      retaddr,
      (void *)0x18A,
      (unsigned int)"onecoreuap\\inetcore\\spartan\\desktopbroker\\filebrokers\\comcatex.cpp",
      v5);
  v8 = 0;
  for ( pitem = 0; ; DSA_InsertItem(*a2, 0x7FFFFFFF, &pitem) )
  {
    v6 = ((__int64 (__fastcall *)(struct IEnumGUID *, __int64, __int128 *, int *))a1->lpVtbl->Next)(a1, 1, &pitem, &v8);
    if ( v6 < 0 || !v8 )
      break;
  }
  result = 0;
  if ( v6 < 0 )
    return (unsigned int)v6;
  return result;
}

```

## disassembly

```asm
0x18002a564  mov     [rsp+arg_10], rbx
0x18002a569  push    rdi
0x18002a56a  sub     rsp, 50h
0x18002a56e  mov     rax, cs:__security_cookie
0x18002a575  xor     rax, rsp
0x18002a578  mov     [rsp+58h+var_10], rax
0x18002a57d  mov     rdi, rdx
0x18002a580  mov     rbx, rcx
0x18002a583  mov     edx, 4; cItemGrow
0x18002a588  lea     ecx, [rdx+0Ch]; cbItem
0x18002a58b  call    cs:__imp_DSA_Create
0x18002a591  mov     [rdi], rax
0x18002a594  test    rax, rax
0x18002a597  jnz     short loc_18002A5B0
0x18002a599  mov     rcx, [rsp+58h]; this
0x18002a59e  lea     r8, aOnecoreuapInet_5; "onecoreuap\\inetcore\\spartan\\desktopb"...
0x18002a5a5  mov     edx, 18Ah; void *
0x18002a5aa  call    ?_FailFast_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_NullAlloc(void *,uint,char const *)
0x18002a5b0  xorps   xmm0, xmm0
0x18002a5b3  mov     [rsp+58h+var_28], 0
0x18002a5bb  movups  [rsp+58h+pitem], xmm0
0x18002a5c0  jmp     short loc_18002A5DC
0x18002a5c2  cmp     [rsp+58h+var_28], 0
0x18002a5c7  jbe     short loc_18002A600
0x18002a5c9  mov     rcx, [rdi]; hdsa
0x18002a5cc  lea     r8, [rsp+58h+pitem]; pitem
0x18002a5d1  mov     edx, 7FFFFFFFh; i
0x18002a5d6  call    cs:__imp_DSA_InsertItem
0x18002a5dc  mov     rax, [rbx]
0x18002a5df  lea     r9, [rsp+58h+var_28]
0x18002a5e4  lea     r8, [rsp+58h+pitem]
0x18002a5e9  mov     edx, 1
0x18002a5ee  mov     rcx, rbx
0x18002a5f1  mov     rax, [rax+18h]
0x18002a5f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a5fa  mov     ecx, eax
0x18002a5fc  test    eax, eax
0x18002a5fe  jns     short loc_18002A5C2
0x18002a600  xor     eax, eax
0x18002a602  test    ecx, ecx
0x18002a604  cmovs   eax, ecx
0x18002a607  mov     rcx, [rsp+58h+var_10]
0x18002a60c  xor     rcx, rsp; StackCookie
0x18002a60f  call    __security_check_cookie
0x18002a614  mov     rbx, [rsp+58h+arg_10]
0x18002a619  add     rsp, 50h
0x18002a61d  pop     rdi
0x18002a61e  retn
```
