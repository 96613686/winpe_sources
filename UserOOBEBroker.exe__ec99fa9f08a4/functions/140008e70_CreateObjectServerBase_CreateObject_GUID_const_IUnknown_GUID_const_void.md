# CreateObjectServerBase::CreateObject(_GUID const &,IUnknown *,_GUID const &,void * *)

- ea: `0x140008e70`
- end: `0x140008eee`
- name: `?CreateObject@CreateObjectServerBase@@UEAAJAEBU_GUID@@PEAUIUnknown@@0PEAPEAX@Z`
- size: `126`
- prototype: `CreateObject *__fastcall(CreateObject *this, const struct _GUID *, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x140003544`
- `0x140008e70`
- `0x14000cef0`
- `0x14000d78c`
- `0x14000f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140008ea6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140008ea6`

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
  unsigned int v8; // r8d
  const char *v9; // r9
  CreateObject *result; // rax
  unsigned int v11; // eax
  void *v12; // rdx
  unsigned int v13; // r8d
  __int64 v14; // [rsp+0h] [rbp-38h] BYREF
  LPVOID *ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  try
  {
    if ( !(*(unsigned __int8 (__fastcall **)(CreateObject *))(*(_QWORD *)this + 40LL))(this) )
    {
      v11 = wil::verify_hresult<long>(2147942405LL);
      wil::details::in1diag3::Throw_Hr(retaddr, v12, v13, (const char *)v11, (int)ppv);
    }
    Instance = CoCreateInstance(a2, 0, 1u, a4, a5);
    if ( Instance < 0 )
      wil::details::in1diag3::_Throw_Hr(retaddr, (void *)0x27, v8, (const char *)(unsigned int)Instance, (int)ppv);
    result = 0;
  }
  catch ( ... )
  {
    return (CreateObject *)(unsigned int)wil::details::in1diag3::Return_CaughtException(retaddr, &v14, v8, v9);
  }
  return result;
}

```

## disassembly

```asm
0x140008e70  mov     [rsp+arg_8], rbx
0x140008e75  push    rdi
0x140008e76  sub     rsp, 30h
0x140008e7a  mov     rdi, r9
0x140008e7d  mov     rbx, rdx
0x140008e80  mov     rax, [rcx]
0x140008e83  mov     rax, [rax+28h]
0x140008e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008e8c  test    al, al
0x140008e8e  jz      short loc_140008ED5
0x140008e90  mov     rax, [rsp+38h+arg_20]
0x140008e95  mov     [rsp+38h+ppv], rax; int
0x140008e9a  mov     r9, rdi; riid
0x140008e9d  xor     edx, edx; pUnkOuter
0x140008e9f  lea     r8d, [rdx+1]; dwClsContext
0x140008ea3  mov     rcx, rbx; rclsid
0x140008ea6  call    cs:__imp_CoCreateInstance
0x140008eac  mov     rcx, [rsp+38h]; this
0x140008eb1  test    eax, eax
0x140008eb3  js      short loc_140008EC8
0x140008eb5  xor     eax, eax
0x140008eb7  jmp     short loc_140008EBD
0x140008eb9  mov     eax, [rsp+38h+arg_0]
0x140008ebd  mov     rbx, [rsp+38h+arg_8]
0x140008ec2  add     rsp, 30h
0x140008ec6  pop     rdi
0x140008ec7  retn
0x140008ec8  mov     r9d, eax; char *
0x140008ecb  mov     edx, 27h ; '''; void *
0x140008ed0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x140008ed5  mov     ecx, 80070005h
0x140008eda  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x140008edf  mov     r9d, eax; char *
0x140008ee2  mov     rcx, [rsp+38h]; this
0x140008ee7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
