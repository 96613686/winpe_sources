# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x18000cbf0`
- end: `0x18000cc65`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000cbf0`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000cc32`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000cc32`

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
0x18000cbf0  mov     [rsp+arg_0], rbx
0x18000cbf5  mov     [rsp+arg_8], rsi
0x18000cbfa  push    rdi
0x18000cbfb  sub     rsp, 30h
0x18000cbff  mov     rsi, rdx
0x18000cc02  test    rdx, rdx
0x18000cc05  jnz     short loc_18000CC0E
0x18000cc07  mov     eax, 80004003h
0x18000cc0c  jmp     short loc_18000CC55
0x18000cc0e  xor     edi, edi
0x18000cc10  lea     rbx, [rcx+40h]
0x18000cc14  cmp     [rbx], rdi
0x18000cc17  jnz     short loc_18000CC3E
0x18000cc19  mov     [rsp+38h+ppv], rbx; ppv
0x18000cc1e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x18000cc25  xor     edx, edx; pUnkOuter
0x18000cc27  lea     r8d, [rdi+1]; dwClsContext
0x18000cc2b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000cc32  call    cs:__imp_CoCreateInstance
0x18000cc38  mov     edi, eax
0x18000cc3a  test    eax, eax
0x18000cc3c  js      short loc_18000CC53
0x18000cc3e  mov     rcx, [rbx]
0x18000cc41  mov     [rsi], rcx
0x18000cc44  mov     rcx, [rbx]
0x18000cc47  mov     rdx, [rcx]
0x18000cc4a  mov     rax, [rdx+8]
0x18000cc4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc53  mov     eax, edi
0x18000cc55  mov     rbx, [rsp+38h+arg_0]
0x18000cc5a  mov     rsi, [rsp+38h+arg_8]
0x18000cc5f  add     rsp, 30h
0x18000cc63  pop     rdi
0x18000cc64  retn
```
