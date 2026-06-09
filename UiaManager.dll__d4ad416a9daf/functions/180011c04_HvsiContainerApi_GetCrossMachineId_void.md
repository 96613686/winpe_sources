# HvsiContainerApi::GetCrossMachineId(void)

- ea: `0x180011c04`
- end: `0x180011cff`
- name: `?GetCrossMachineId@HvsiContainerApi@@SA?AU_GUID@@XZ`
- size: `251`
- prototype: `struct _GUID *__fastcall(struct _GUID *__return_ptr __struct_ptr retstr)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180011810`
- `0x180080648`

## callees

- `0x180011c04`
- `0x18002bfd8`
- `0x180031540`
- `0x180043680`
- `0x180091010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180011cbb`
- `OLEAUT32!__imp_SysFreeString` at `0x180011cbb`
- `RPCRT4!UuidFromStringW` at `0x180011c85`
- `RPCRT4!UuidFromStringW` at `0x180011c85`

## string_xrefs

- `0x180011c60`: `onecore\windows\accessibletech\common\hvsicontainerapi.cpp`
- `0x180011c95`: `onecore\windows\accessibletech\common\hvsicontainerapi.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct _GUID *__fastcall HvsiContainerApi::GetCrossMachineId(struct _GUID *__return_ptr retstr)
{
  __int64 v2; // rax
  int v3; // eax
  LPVOID v4; // rcx
  RPC_WSTR StringUuid; // [rsp+20h] [rbp-30h] BYREF
  LPVOID ppv; // [rsp+28h] [rbp-28h] BYREF
  UUID Uuid; // [rsp+30h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]

  anonymous_namespace_::CreateHvsiContainerManager(&ppv);
  StringUuid = 0;
  v2 = *(_QWORD *)ppv;
  StringUuid = 0;
  v3 = (*(__int64 (__fastcall **)(LPVOID, RPC_WSTR *))(v2 + 80))(ppv, &StringUuid);
  if ( v3 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x61,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\hvsicontainerapi.cpp",
      (const char *)(unsigned int)v3,
      (int)StringUuid);
  Uuid = 0;
  if ( UuidFromStringW(StringUuid, &Uuid) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x64,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\hvsicontainerapi.cpp",
      (const char *)0x80004005LL,
      (int)StringUuid);
  *retstr = Uuid;
  if ( StringUuid )
    SysFreeString(StringUuid);
  v4 = ppv;
  if ( ppv )
  {
    ppv = 0;
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v4 + 16LL))(v4);
  }
  return retstr;
}

```

## disassembly

```asm
0x180011c04  mov     [rsp-8+arg_0], rbx
0x180011c09  mov     [rsp-8+arg_8], rdi
0x180011c0e  push    rbp
0x180011c0f  mov     rbp, rsp
0x180011c12  sub     rsp, 50h
0x180011c16  mov     rax, cs:__security_cookie
0x180011c1d  xor     rax, rsp
0x180011c20  mov     [rbp+var_10], rax
0x180011c24  mov     rbx, rcx
0x180011c27  lea     rcx, [rbp+ppv]; ppv
0x180011c2b  call    _anonymous_namespace___CreateHvsiContainerManager
0x180011c30  nop
0x180011c31  mov     [rbp+StringUuid], 0
0x180011c39  mov     rcx, [rbp+ppv]
0x180011c3d  mov     rax, [rcx]
0x180011c40  mov     [rbp+StringUuid], 0
0x180011c48  lea     rdx, [rbp+StringUuid]
0x180011c4c  mov     rax, [rax+50h]
0x180011c50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c55  mov     rcx, [rbp+8]; this
0x180011c59  test    eax, eax
0x180011c5b  jns     short loc_180011C72
0x180011c5d  mov     r9d, eax; char *
0x180011c60  lea     r8, aOnecoreWindows_23; "onecore\\windows\\accessibletech\\commo"...
0x180011c67  mov     edx, 61h ; 'a'; void *
0x180011c6c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180011c72  xorps   xmm0, xmm0
0x180011c75  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x180011c79  mov     rdi, [rbp+8]
0x180011c7d  lea     rdx, [rbp+Uuid]; Uuid
0x180011c81  mov     rcx, [rbp+StringUuid]; StringUuid
0x180011c85  call    cs:__imp_UuidFromStringW
0x180011c8b  test    eax, eax
0x180011c8d  jz      short loc_180011CAA
0x180011c8f  mov     r9d, 80004005h; char *
0x180011c95  lea     r8, aOnecoreWindows_23; "onecore\\windows\\accessibletech\\commo"...
0x180011c9c  mov     edx, 64h ; 'd'; void *
0x180011ca1  mov     rcx, rdi; this
0x180011ca4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180011caa  movups  xmm0, xmmword ptr [rbp+Uuid.Data1]
0x180011cae  movdqu  xmmword ptr [rbx], xmm0
0x180011cb2  mov     rcx, [rbp+StringUuid]; bstrString
0x180011cb6  test    rcx, rcx
0x180011cb9  jz      short loc_180011CC2
0x180011cbb  call    cs:__imp_SysFreeString
0x180011cc1  nop
0x180011cc2  mov     rcx, [rbp+ppv]
0x180011cc6  test    rcx, rcx
0x180011cc9  jz      short loc_180011CE0
0x180011ccb  mov     [rbp+ppv], 0
0x180011cd3  mov     rax, [rcx]
0x180011cd6  mov     rax, [rax+10h]
0x180011cda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011cdf  nop
0x180011ce0  mov     rax, rbx
0x180011ce3  mov     rcx, [rbp+var_10]
0x180011ce7  xor     rcx, rsp; StackCookie
0x180011cea  call    __security_check_cookie
0x180011cef  mov     rbx, [rsp+50h+arg_0]
0x180011cf4  mov     rdi, [rsp+50h+arg_8]
0x180011cf9  add     rsp, 50h
0x180011cfd  pop     rbp
0x180011cfe  retn
```
