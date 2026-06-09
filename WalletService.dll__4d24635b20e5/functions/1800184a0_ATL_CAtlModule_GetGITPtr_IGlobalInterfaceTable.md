# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x1800184a0`
- end: `0x180018515`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800184a0`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800184e2`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800184e2`

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
0x1800184a0  mov     [rsp+arg_0], rbx
0x1800184a5  mov     [rsp+arg_8], rsi
0x1800184aa  push    rdi
0x1800184ab  sub     rsp, 30h
0x1800184af  mov     rsi, rdx
0x1800184b2  test    rdx, rdx
0x1800184b5  jnz     short loc_1800184BE
0x1800184b7  mov     eax, 80004003h
0x1800184bc  jmp     short loc_180018505
0x1800184be  xor     edi, edi
0x1800184c0  lea     rbx, [rcx+40h]
0x1800184c4  cmp     [rbx], rdi
0x1800184c7  jnz     short loc_1800184EE
0x1800184c9  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1800184d0  mov     [rsp+38h+ppv], rbx; ppv
0x1800184d5  xor     edx, edx; pUnkOuter
0x1800184d7  lea     r8d, [rdi+1]; dwClsContext
0x1800184db  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1800184e2  call    cs:__imp_CoCreateInstance
0x1800184e8  mov     edi, eax
0x1800184ea  test    eax, eax
0x1800184ec  js      short loc_180018503
0x1800184ee  mov     rcx, [rbx]
0x1800184f1  mov     [rsi], rcx
0x1800184f4  mov     rcx, [rbx]
0x1800184f7  mov     rdx, [rcx]
0x1800184fa  mov     rax, [rdx+8]
0x1800184fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018503  mov     eax, edi
0x180018505  mov     rbx, [rsp+38h+arg_0]
0x18001850a  mov     rsi, [rsp+38h+arg_8]
0x18001850f  add     rsp, 30h
0x180018513  pop     rdi
0x180018514  retn
```
