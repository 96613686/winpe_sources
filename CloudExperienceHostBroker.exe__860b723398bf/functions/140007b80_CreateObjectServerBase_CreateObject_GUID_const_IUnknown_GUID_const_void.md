# CreateObjectServerBase::CreateObject(_GUID const &,IUnknown *,_GUID const &,void * *)

- ea: `0x140007b80`
- end: `0x140007bfe`
- name: `?CreateObject@CreateObjectServerBase@@UEAAJAEBU_GUID@@PEAUIUnknown@@0PEAPEAX@Z`
- size: `126`
- prototype: `CreateObject *__fastcall(CreateObject *this, const struct _GUID *, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x140007b80`
- `0x140008c74`
- `0x14000923c`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140007bb6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140007bb6`

## string_xrefs

- `0x140007bc8`: `onecoreuap\internal\shell\inc\cloudexperiencehostbrokerhelpers.h`

## pseudocode

```c
CreateObject *__fastcall CreateObjectServerBase::CreateObject(
        CreateObject *this,
        const struct _GUID *a2,
        struct IUnknown *a3,
        const struct _GUID *a4,
        void **a5)
{
  void *v7; // rdx
  unsigned int v8; // r8d
  HRESULT Instance; // eax
  unsigned int v10; // r8d
  const char *v11; // r9
  __int64 v13; // [rsp+0h] [rbp-38h] BYREF
  LPVOID *ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  try
  {
    if ( !(*(unsigned __int8 (__fastcall **)(CreateObject *))(*(_QWORD *)this + 40LL))(this) )
      wil::details::in1diag3::Throw_Hr(retaddr, v7, v8, (const char *)0x80070005LL, (int)ppv);
    Instance = CoCreateInstance(a2, 0, 1u, a4, a5);
    if ( Instance < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x27,
        (unsigned int)"onecoreuap\\internal\\shell\\inc\\cloudexperiencehostbrokerhelpers.h",
        (const char *)(unsigned int)Instance,
        (int)ppv);
  }
  catch ( ... )
  {
    return (CreateObject *)(unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, &v13, v10, v11);
  }
  return 0;
}

```

## disassembly

```asm
0x140007b80  mov     [rsp+arg_8], rbx
0x140007b85  push    rdi
0x140007b86  sub     rsp, 30h
0x140007b8a  mov     rdi, r9
0x140007b8d  mov     rbx, rdx
0x140007b90  mov     rax, [rcx]
0x140007b93  mov     rax, [rax+28h]
0x140007b97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007b9c  test    al, al
0x140007b9e  jz      short loc_140007BDE
0x140007ba0  mov     rax, [rsp+38h+arg_20]
0x140007ba5  mov     [rsp+38h+ppv], rax; int
0x140007baa  mov     r9, rdi; riid
0x140007bad  xor     edx, edx; pUnkOuter
0x140007baf  lea     r8d, [rdx+1]; dwClsContext
0x140007bb3  mov     rcx, rbx; rclsid
0x140007bb6  call    cs:__imp_CoCreateInstance
0x140007bbc  mov     rcx, [rsp+38h]; this
0x140007bc1  test    eax, eax
0x140007bc3  jns     short loc_140007BDA
0x140007bc5  mov     r9d, eax; char *
0x140007bc8  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\shell\\inc\\cloud"...
0x140007bcf  mov     edx, 27h ; '''; void *
0x140007bd4  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140007bda  xor     eax, eax
0x140007bdc  jmp     short loc_140007BF3
0x140007bde  mov     rcx, [rsp+38h]; this
0x140007be3  mov     r9d, 80070005h; char *
0x140007be9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140007bef  mov     eax, [rsp+38h+arg_0]
0x140007bf3  mov     rbx, [rsp+38h+arg_8]
0x140007bf8  add     rsp, 30h
0x140007bfc  pop     rdi
0x140007bfd  retn
```
