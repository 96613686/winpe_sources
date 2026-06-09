# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x1800094d0`
- end: `0x180009545`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800094d0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009512`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180009512`

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
0x1800094d0  mov     [rsp+arg_0], rbx
0x1800094d5  mov     [rsp+arg_8], rsi
0x1800094da  push    rdi
0x1800094db  sub     rsp, 30h
0x1800094df  mov     rsi, rdx
0x1800094e2  test    rdx, rdx
0x1800094e5  jnz     short loc_1800094EE
0x1800094e7  mov     eax, 80004003h
0x1800094ec  jmp     short loc_180009535
0x1800094ee  xor     edi, edi
0x1800094f0  lea     rbx, [rcx+40h]
0x1800094f4  cmp     [rbx], rdi
0x1800094f7  jnz     short loc_18000951E
0x1800094f9  mov     [rsp+38h+ppv], rbx; ppv
0x1800094fe  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180009505  xor     edx, edx; pUnkOuter
0x180009507  lea     r8d, [rdi+1]; dwClsContext
0x18000950b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180009512  call    cs:__imp_CoCreateInstance
0x180009518  mov     edi, eax
0x18000951a  test    eax, eax
0x18000951c  js      short loc_180009533
0x18000951e  mov     rcx, [rbx]
0x180009521  mov     [rsi], rcx
0x180009524  mov     rcx, [rbx]
0x180009527  mov     rdx, [rcx]
0x18000952a  mov     rax, [rdx+8]
0x18000952e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009533  mov     eax, edi
0x180009535  mov     rbx, [rsp+38h+arg_0]
0x18000953a  mov     rsi, [rsp+38h+arg_8]
0x18000953f  add     rsp, 30h
0x180009543  pop     rdi
0x180009544  retn
```
