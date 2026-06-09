# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180004f40`
- end: `0x180004fb5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004f40`
- `0x180017010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180004f82`
- `ole32!CoCreateInstance` at `0x180004f82`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::GetGITPtr(ATL::CAtlModule *this, struct IGlobalInterfaceTable **a2)
{
  HRESULT Instance; // edi
  _QWORD *v5; // rbx

  if ( !a2 )
    return 2147500035LL;
  Instance = 0;
  v5 = (_QWORD *)((char *)this + 64);
  if ( *((_QWORD *)this + 8)
    || (Instance = CoCreateInstance(
                     &CLSID_StdGlobalInterfaceTable,
                     0,
                     1u,
                     &GUID_00000146_0000_0000_c000_000000000046,
                     (LPVOID *)this + 8),
        Instance >= 0) )
  {
    *a2 = (struct IGlobalInterfaceTable *)*v5;
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 8LL))(*v5);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180004f40  mov     [rsp+arg_0], rbx
0x180004f45  mov     [rsp+arg_8], rsi
0x180004f4a  push    rdi
0x180004f4b  sub     rsp, 30h
0x180004f4f  mov     rsi, rdx
0x180004f52  test    rdx, rdx
0x180004f55  jnz     short loc_180004F5E
0x180004f57  mov     eax, 80004003h
0x180004f5c  jmp     short loc_180004FA5
0x180004f5e  xor     edi, edi
0x180004f60  lea     rbx, [rcx+40h]
0x180004f64  cmp     [rbx], rdi
0x180004f67  jnz     short loc_180004F8E
0x180004f69  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180004f70  mov     [rsp+38h+ppv], rbx; ppv
0x180004f75  xor     edx, edx; pUnkOuter
0x180004f77  lea     r8d, [rdi+1]; dwClsContext
0x180004f7b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180004f82  call    cs:__imp_CoCreateInstance
0x180004f88  mov     edi, eax
0x180004f8a  test    eax, eax
0x180004f8c  js      short loc_180004FA3
0x180004f8e  mov     rcx, [rbx]
0x180004f91  mov     [rsi], rcx
0x180004f94  mov     rcx, [rbx]
0x180004f97  mov     rdx, [rcx]
0x180004f9a  mov     rax, [rdx+8]
0x180004f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fa3  mov     eax, edi
0x180004fa5  mov     rbx, [rsp+38h+arg_0]
0x180004faa  mov     rsi, [rsp+38h+arg_8]
0x180004faf  add     rsp, 30h
0x180004fb3  pop     rdi
0x180004fb4  retn
```
