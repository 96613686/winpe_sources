# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x140003530`
- end: `0x1400035a5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140003530`
- `0x140041010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140003572`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140003572`

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
0x140003530  mov     [rsp+arg_0], rbx
0x140003535  mov     [rsp+arg_8], rsi
0x14000353a  push    rdi
0x14000353b  sub     rsp, 30h
0x14000353f  mov     rsi, rdx
0x140003542  test    rdx, rdx
0x140003545  jnz     short loc_14000354E
0x140003547  mov     eax, 80004003h
0x14000354c  jmp     short loc_140003595
0x14000354e  xor     edi, edi
0x140003550  lea     rbx, [rcx+40h]
0x140003554  cmp     [rbx], rdi
0x140003557  jnz     short loc_14000357E
0x140003559  mov     [rsp+38h+ppv], rbx; ppv
0x14000355e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x140003565  xor     edx, edx; pUnkOuter
0x140003567  lea     r8d, [rdi+1]; dwClsContext
0x14000356b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x140003572  call    cs:__imp_CoCreateInstance
0x140003578  mov     edi, eax
0x14000357a  test    eax, eax
0x14000357c  js      short loc_140003593
0x14000357e  mov     rcx, [rbx]
0x140003581  mov     [rsi], rcx
0x140003584  mov     rcx, [rbx]
0x140003587  mov     rdx, [rcx]
0x14000358a  mov     rax, [rdx+8]
0x14000358e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003593  mov     eax, edi
0x140003595  mov     rbx, [rsp+38h+arg_0]
0x14000359a  mov     rsi, [rsp+38h+arg_8]
0x14000359f  add     rsp, 30h
0x1400035a3  pop     rdi
0x1400035a4  retn
```
