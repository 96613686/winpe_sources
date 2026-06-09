# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x140006c20`
- end: `0x140006c95`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140006c20`
- `0x140008010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140006c62`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140006c62`

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
0x140006c20  mov     [rsp+arg_0], rbx
0x140006c25  mov     [rsp+arg_8], rsi
0x140006c2a  push    rdi
0x140006c2b  sub     rsp, 30h
0x140006c2f  mov     rsi, rdx
0x140006c32  test    rdx, rdx
0x140006c35  jnz     short loc_140006C3E
0x140006c37  mov     eax, 80004003h
0x140006c3c  jmp     short loc_140006C85
0x140006c3e  xor     edi, edi
0x140006c40  lea     rbx, [rcx+40h]
0x140006c44  cmp     [rbx], rdi
0x140006c47  jnz     short loc_140006C6E
0x140006c49  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x140006c50  mov     [rsp+38h+ppv], rbx; ppv
0x140006c55  xor     edx, edx; pUnkOuter
0x140006c57  lea     r8d, [rdi+1]; dwClsContext
0x140006c5b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x140006c62  call    cs:__imp_CoCreateInstance
0x140006c68  mov     edi, eax
0x140006c6a  test    eax, eax
0x140006c6c  js      short loc_140006C83
0x140006c6e  mov     rcx, [rbx]
0x140006c71  mov     [rsi], rcx
0x140006c74  mov     rcx, [rbx]
0x140006c77  mov     rdx, [rcx]
0x140006c7a  mov     rax, [rdx+8]
0x140006c7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006c83  mov     eax, edi
0x140006c85  mov     rbx, [rsp+38h+arg_0]
0x140006c8a  mov     rsi, [rsp+38h+arg_8]
0x140006c8f  add     rsp, 30h
0x140006c93  pop     rdi
0x140006c94  retn
```
