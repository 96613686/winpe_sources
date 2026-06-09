# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180002ce0`
- end: `0x180002d55`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180002ce0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002d22`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002d22`

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
0x180002ce0  mov     [rsp+arg_0], rbx
0x180002ce5  mov     [rsp+arg_8], rsi
0x180002cea  push    rdi
0x180002ceb  sub     rsp, 30h
0x180002cef  mov     rsi, rdx
0x180002cf2  test    rdx, rdx
0x180002cf5  jnz     short loc_180002CFE
0x180002cf7  mov     eax, 80004003h
0x180002cfc  jmp     short loc_180002D45
0x180002cfe  xor     edi, edi
0x180002d00  lea     rbx, [rcx+40h]
0x180002d04  cmp     [rbx], rdi
0x180002d07  jnz     short loc_180002D2E
0x180002d09  mov     [rsp+38h+ppv], rbx; ppv
0x180002d0e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180002d15  xor     edx, edx; pUnkOuter
0x180002d17  lea     r8d, [rdi+1]; dwClsContext
0x180002d1b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180002d22  call    cs:__imp_CoCreateInstance
0x180002d28  mov     edi, eax
0x180002d2a  test    eax, eax
0x180002d2c  js      short loc_180002D43
0x180002d2e  mov     rcx, [rbx]
0x180002d31  mov     [rsi], rcx
0x180002d34  mov     rcx, [rbx]
0x180002d37  mov     rdx, [rcx]
0x180002d3a  mov     rax, [rdx+8]
0x180002d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d43  mov     eax, edi
0x180002d45  mov     rbx, [rsp+38h+arg_0]
0x180002d4a  mov     rsi, [rsp+38h+arg_8]
0x180002d4f  add     rsp, 30h
0x180002d53  pop     rdi
0x180002d54  retn
```
