# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x14000d5b0`
- end: `0x14000d625`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14000d5b0`
- `0x140017010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000d5f2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x14000d5f2`

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
0x14000d5b0  mov     [rsp+arg_0], rbx
0x14000d5b5  mov     [rsp+arg_8], rsi
0x14000d5ba  push    rdi
0x14000d5bb  sub     rsp, 30h
0x14000d5bf  mov     rsi, rdx
0x14000d5c2  test    rdx, rdx
0x14000d5c5  jnz     short loc_14000D5CE
0x14000d5c7  mov     eax, 80004003h
0x14000d5cc  jmp     short loc_14000D615
0x14000d5ce  xor     edi, edi
0x14000d5d0  lea     rbx, [rcx+40h]
0x14000d5d4  cmp     [rbx], rdi
0x14000d5d7  jnz     short loc_14000D5FE
0x14000d5d9  mov     [rsp+38h+ppv], rbx; ppv
0x14000d5de  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x14000d5e5  xor     edx, edx; pUnkOuter
0x14000d5e7  lea     r8d, [rdi+1]; dwClsContext
0x14000d5eb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x14000d5f2  call    cs:__imp_CoCreateInstance
0x14000d5f8  mov     edi, eax
0x14000d5fa  test    eax, eax
0x14000d5fc  js      short loc_14000D613
0x14000d5fe  mov     rcx, [rbx]
0x14000d601  mov     [rsi], rcx
0x14000d604  mov     rcx, [rbx]
0x14000d607  mov     rdx, [rcx]
0x14000d60a  mov     rax, [rdx+8]
0x14000d60e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d613  mov     eax, edi
0x14000d615  mov     rbx, [rsp+38h+arg_0]
0x14000d61a  mov     rsi, [rsp+38h+arg_8]
0x14000d61f  add     rsp, 30h
0x14000d623  pop     rdi
0x14000d624  retn
```
