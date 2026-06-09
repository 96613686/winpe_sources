# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x18000b600`
- end: `0x18000b67f`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `127`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000b600`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b64c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000b64c`

## pseudocode

```c
__int64 __fastcall ATL::CAtlModule::GetGITPtr(ATL::CAtlModule *this, struct IGlobalInterfaceTable **a2)
{
  HRESULT Instance; // edi
  _QWORD **v5; // rbx

  if ( !a2 )
    return 2147500035LL;
  Instance = 0;
  v5 = (_QWORD **)((char *)this + 64);
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
    (*(void (__fastcall **)(_QWORD, _QWORD))(**v5 + 8LL))(*v5, **v5);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x18000b600  push    rdi
0x18000b602  sub     rsp, 40h
0x18000b606  mov     [rsp+48h+var_18], 0FFFFFFFFFFFFFFFEh
0x18000b60f  mov     [rsp+48h+arg_0], rbx
0x18000b614  mov     [rsp+48h+arg_8], rsi
0x18000b619  mov     rsi, rdx
0x18000b61c  test    rdx, rdx
0x18000b61f  jnz     short loc_18000B628
0x18000b621  mov     eax, 80004003h
0x18000b626  jmp     short loc_18000B66F
0x18000b628  xor     edi, edi
0x18000b62a  lea     rbx, [rcx+40h]
0x18000b62e  cmp     [rbx], rdi
0x18000b631  jnz     short loc_18000B658
0x18000b633  mov     [rsp+48h+ppv], rbx; ppv
0x18000b638  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000b63f  xor     edx, edx; pUnkOuter
0x18000b641  lea     r8d, [rdi+1]; dwClsContext
0x18000b645  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000b64c  call    cs:__imp_CoCreateInstance
0x18000b652  mov     edi, eax
0x18000b654  test    eax, eax
0x18000b656  js      short loc_18000B66D
0x18000b658  mov     rcx, [rbx]
0x18000b65b  mov     [rsi], rcx
0x18000b65e  mov     rcx, [rbx]
0x18000b661  mov     rdx, [rcx]
0x18000b664  mov     rax, [rdx+8]
0x18000b668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b66d  mov     eax, edi
0x18000b66f  mov     rbx, [rsp+48h+arg_0]
0x18000b674  mov     rsi, [rsp+48h+arg_8]
0x18000b679  add     rsp, 40h
0x18000b67d  pop     rdi
0x18000b67e  retn
```
