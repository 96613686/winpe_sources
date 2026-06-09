# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x140003d70`
- end: `0x140003de5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140003d70`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140003db2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140003db2`

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
0x140003d70  mov     [rsp+arg_0], rbx
0x140003d75  mov     [rsp+arg_8], rsi
0x140003d7a  push    rdi
0x140003d7b  sub     rsp, 30h
0x140003d7f  mov     rsi, rdx
0x140003d82  test    rdx, rdx
0x140003d85  jnz     short loc_140003D8E
0x140003d87  mov     eax, 80004003h
0x140003d8c  jmp     short loc_140003DD5
0x140003d8e  xor     edi, edi
0x140003d90  lea     rbx, [rcx+40h]
0x140003d94  cmp     [rbx], rdi
0x140003d97  jnz     short loc_140003DBE
0x140003d99  mov     [rsp+38h+ppv], rbx; ppv
0x140003d9e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x140003da5  xor     edx, edx; pUnkOuter
0x140003da7  lea     r8d, [rdi+1]; dwClsContext
0x140003dab  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x140003db2  call    cs:__imp_CoCreateInstance
0x140003db8  mov     edi, eax
0x140003dba  test    eax, eax
0x140003dbc  js      short loc_140003DD3
0x140003dbe  mov     rcx, [rbx]
0x140003dc1  mov     [rsi], rcx
0x140003dc4  mov     rcx, [rbx]
0x140003dc7  mov     rdx, [rcx]
0x140003dca  mov     rax, [rdx+8]
0x140003dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003dd3  mov     eax, edi
0x140003dd5  mov     rbx, [rsp+38h+arg_0]
0x140003dda  mov     rsi, [rsp+38h+arg_8]
0x140003ddf  add     rsp, 30h
0x140003de3  pop     rdi
0x140003de4  retn
```
