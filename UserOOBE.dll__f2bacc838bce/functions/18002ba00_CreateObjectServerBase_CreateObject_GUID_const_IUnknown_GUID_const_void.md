# CreateObjectServerBase::CreateObject(_GUID const &,IUnknown *,_GUID const &,void * *)

- ea: `0x18002ba00`
- end: `0x18002ba8a`
- name: `?CreateObject@CreateObjectServerBase@@UEAAJAEBU_GUID@@PEAUIUnknown@@0PEAPEAX@Z`
- size: `138`
- prototype: `CreateObject *__fastcall(CreateObject *this, const struct _GUID *, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000e2bc`
- `0x18002ba00`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ba36`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ba36`

## string_xrefs

- `0x18002ba48`: `onecoreuap\internal\shell\inc\cloudexperiencehostbrokerhelpers.h`
- `0x18002ba69`: `onecoreuap\internal\shell\inc\cloudexperiencehostbrokerhelpers.h`

## pseudocode

```c
CreateObject *__fastcall CreateObjectServerBase::CreateObject(
        CreateObject *this,
        const struct _GUID *a2,
        struct IUnknown *a3,
        const struct _GUID *a4,
        void **a5)
{
  HRESULT Instance; // eax
  const char *v8; // r9
  int ppv; // [rsp+20h] [rbp-18h]
  int ppva; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  try
  {
    if ( !(*(unsigned __int8 (__fastcall **)(CreateObject *))(*(_QWORD *)this + 40LL))(this) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2B,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostbrokerhelpers.h",
        (const char *)0x80070005LL,
        ppv);
    Instance = CoCreateInstance(a2, 0, 1u, a4, a5);
    if ( Instance < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x27,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostbrokerhelpers.h",
        (const char *)(unsigned int)Instance,
        ppva);
  }
  catch ( ... )
  {
    return (CreateObject *)(unsigned int)wil::details::in1diag3::Return_CaughtException(
                                           retaddr,
                                           (void *)0x2E,
                                           (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostbrokerhelpers.h",
                                           v8);
  }
  return 0;
}

```

## disassembly

```asm
0x18002ba00  mov     [rsp+arg_8], rbx
0x18002ba05  push    rdi
0x18002ba06  sub     rsp, 30h
0x18002ba0a  mov     rdi, r9
0x18002ba0d  mov     rbx, rdx
0x18002ba10  mov     rax, [rcx]
0x18002ba13  mov     rax, [rax+28h]
0x18002ba17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba1c  test    al, al
0x18002ba1e  jz      short loc_18002BA5E
0x18002ba20  mov     rax, [rsp+38h+arg_20]
0x18002ba25  mov     qword ptr [rsp+38h+ppv], rax; int
0x18002ba2a  mov     r9, rdi; riid
0x18002ba2d  xor     edx, edx; pUnkOuter
0x18002ba2f  lea     r8d, [rdx+1]; dwClsContext
0x18002ba33  mov     rcx, rbx; rclsid
0x18002ba36  call    cs:__imp_CoCreateInstance
0x18002ba3c  mov     rcx, [rsp+38h]; this
0x18002ba41  test    eax, eax
0x18002ba43  jns     short loc_18002BA5A
0x18002ba45  mov     r9d, eax; char *
0x18002ba48  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x18002ba4f  mov     edx, 27h ; '''; void *
0x18002ba54  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ba5a  xor     eax, eax
0x18002ba5c  jmp     short loc_18002BA7F
0x18002ba5e  mov     rcx, [rsp+38h]; this
0x18002ba63  mov     r9d, 80070005h; char *
0x18002ba69  lea     r8, aOnecoreuapInte_1; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x18002ba70  mov     edx, 2Bh ; '+'; void *
0x18002ba75  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002ba7b  mov     eax, [rsp+38h+arg_0]
0x18002ba7f  mov     rbx, [rsp+38h+arg_8]
0x18002ba84  add     rsp, 30h
0x18002ba88  pop     rdi
0x18002ba89  retn
```
