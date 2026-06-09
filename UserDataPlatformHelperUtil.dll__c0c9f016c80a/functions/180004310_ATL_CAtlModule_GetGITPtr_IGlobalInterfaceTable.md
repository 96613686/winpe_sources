# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180004310`
- end: `0x180004385`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004310`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004352`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180004352`

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
0x180004310  mov     [rsp+arg_0], rbx
0x180004315  mov     [rsp+arg_8], rsi
0x18000431a  push    rdi
0x18000431b  sub     rsp, 30h
0x18000431f  mov     rsi, rdx
0x180004322  test    rdx, rdx
0x180004325  jnz     short loc_18000432E
0x180004327  mov     eax, 80004003h
0x18000432c  jmp     short loc_180004375
0x18000432e  xor     edi, edi
0x180004330  lea     rbx, [rcx+40h]
0x180004334  cmp     [rbx], rdi
0x180004337  jnz     short loc_18000435E
0x180004339  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180004340  mov     [rsp+38h+ppv], rbx; ppv
0x180004345  xor     edx, edx; pUnkOuter
0x180004347  lea     r8d, [rdi+1]; dwClsContext
0x18000434b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180004352  call    cs:__imp_CoCreateInstance
0x180004358  mov     edi, eax
0x18000435a  test    eax, eax
0x18000435c  js      short loc_180004373
0x18000435e  mov     rcx, [rbx]
0x180004361  mov     [rsi], rcx
0x180004364  mov     rcx, [rbx]
0x180004367  mov     rdx, [rcx]
0x18000436a  mov     rax, [rdx+8]
0x18000436e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004373  mov     eax, edi
0x180004375  mov     rbx, [rsp+38h+arg_0]
0x18000437a  mov     rsi, [rsp+38h+arg_8]
0x18000437f  add     rsp, 30h
0x180004383  pop     rdi
0x180004384  retn
```
