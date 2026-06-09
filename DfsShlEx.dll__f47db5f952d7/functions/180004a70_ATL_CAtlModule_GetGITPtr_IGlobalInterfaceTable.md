# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180004a70`
- end: `0x180004ae5`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180004a70`
- `0x18000c010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180004ab2`
- `ole32!CoCreateInstance` at `0x180004ab2`

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
0x180004a70  mov     [rsp+arg_0], rbx
0x180004a75  mov     [rsp+arg_8], rsi
0x180004a7a  push    rdi
0x180004a7b  sub     rsp, 30h
0x180004a7f  mov     rsi, rdx
0x180004a82  test    rdx, rdx
0x180004a85  jnz     short loc_180004A8E
0x180004a87  mov     eax, 80004003h
0x180004a8c  jmp     short loc_180004AD5
0x180004a8e  xor     edi, edi
0x180004a90  lea     rbx, [rcx+40h]
0x180004a94  cmp     [rbx], rdi
0x180004a97  jnz     short loc_180004ABE
0x180004a99  mov     [rsp+38h+ppv], rbx; ppv
0x180004a9e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180004aa5  xor     edx, edx; pUnkOuter
0x180004aa7  lea     r8d, [rdi+1]; dwClsContext
0x180004aab  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180004ab2  call    cs:__imp_CoCreateInstance
0x180004ab8  mov     edi, eax
0x180004aba  test    eax, eax
0x180004abc  js      short loc_180004AD3
0x180004abe  mov     rcx, [rbx]
0x180004ac1  mov     [rsi], rcx
0x180004ac4  mov     rcx, [rbx]
0x180004ac7  mov     rdx, [rcx]
0x180004aca  mov     rax, [rdx+8]
0x180004ace  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ad3  mov     eax, edi
0x180004ad5  mov     rbx, [rsp+38h+arg_0]
0x180004ada  mov     rsi, [rsp+38h+arg_8]
0x180004adf  add     rsp, 30h
0x180004ae3  pop     rdi
0x180004ae4  retn
```
