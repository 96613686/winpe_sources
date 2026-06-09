# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x18000da30`
- end: `0x18000daa5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000da30`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000da72`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000da72`

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
0x18000da30  mov     [rsp+arg_0], rbx
0x18000da35  mov     [rsp+arg_8], rsi
0x18000da3a  push    rdi
0x18000da3b  sub     rsp, 30h
0x18000da3f  mov     rsi, rdx
0x18000da42  test    rdx, rdx
0x18000da45  jnz     short loc_18000DA4E
0x18000da47  mov     eax, 80004003h
0x18000da4c  jmp     short loc_18000DA95
0x18000da4e  xor     edi, edi
0x18000da50  lea     rbx, [rcx+40h]
0x18000da54  cmp     [rbx], rdi
0x18000da57  jnz     short loc_18000DA7E
0x18000da59  mov     [rsp+38h+ppv], rbx; ppv
0x18000da5e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000da65  xor     edx, edx; pUnkOuter
0x18000da67  lea     r8d, [rdi+1]; dwClsContext
0x18000da6b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000da72  call    cs:__imp_CoCreateInstance
0x18000da78  mov     edi, eax
0x18000da7a  test    eax, eax
0x18000da7c  js      short loc_18000DA93
0x18000da7e  mov     rcx, [rbx]
0x18000da81  mov     [rsi], rcx
0x18000da84  mov     rcx, [rbx]
0x18000da87  mov     rdx, [rcx]
0x18000da8a  mov     rax, [rdx+8]
0x18000da8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da93  mov     eax, edi
0x18000da95  mov     rbx, [rsp+38h+arg_0]
0x18000da9a  mov     rsi, [rsp+38h+arg_8]
0x18000da9f  add     rsp, 30h
0x18000daa3  pop     rdi
0x18000daa4  retn
```
