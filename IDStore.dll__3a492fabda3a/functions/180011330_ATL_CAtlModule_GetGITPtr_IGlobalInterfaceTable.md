# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180011330`
- end: `0x1800113a5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180011330`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011372`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180011372`

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
0x180011330  mov     [rsp+arg_0], rbx
0x180011335  mov     [rsp+arg_8], rsi
0x18001133a  push    rdi
0x18001133b  sub     rsp, 30h
0x18001133f  mov     rsi, rdx
0x180011342  test    rdx, rdx
0x180011345  jnz     short loc_18001134E
0x180011347  mov     eax, 80004003h
0x18001134c  jmp     short loc_180011395
0x18001134e  xor     edi, edi
0x180011350  lea     rbx, [rcx+40h]
0x180011354  cmp     [rbx], rdi
0x180011357  jnz     short loc_18001137E
0x180011359  mov     [rsp+38h+ppv], rbx; ppv
0x18001135e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180011365  xor     edx, edx; pUnkOuter
0x180011367  lea     r8d, [rdi+1]; dwClsContext
0x18001136b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180011372  call    cs:__imp_CoCreateInstance
0x180011378  mov     edi, eax
0x18001137a  test    eax, eax
0x18001137c  js      short loc_180011393
0x18001137e  mov     rcx, [rbx]
0x180011381  mov     [rsi], rcx
0x180011384  mov     rcx, [rbx]
0x180011387  mov     rdx, [rcx]
0x18001138a  mov     rax, [rdx+8]
0x18001138e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011393  mov     eax, edi
0x180011395  mov     rbx, [rsp+38h+arg_0]
0x18001139a  mov     rsi, [rsp+38h+arg_8]
0x18001139f  add     rsp, 30h
0x1800113a3  pop     rdi
0x1800113a4  retn
```
