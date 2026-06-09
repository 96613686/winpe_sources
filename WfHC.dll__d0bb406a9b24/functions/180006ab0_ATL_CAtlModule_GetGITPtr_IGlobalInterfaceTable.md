# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180006ab0`
- end: `0x180006b35`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `133`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180006ab0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006b02`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180006b02`

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
0x180006ab0  mov     [rsp+arg_0], rbx
0x180006ab5  mov     [rsp+arg_8], rsi
0x180006aba  push    rdi
0x180006abb  sub     rsp, 30h
0x180006abf  mov     rsi, rdx
0x180006ac2  test    rdx, rdx
0x180006ac5  jnz     short loc_180006ADC
0x180006ac7  mov     eax, 80004003h
0x180006acc  mov     rbx, [rsp+38h+arg_0]
0x180006ad1  mov     rsi, [rsp+38h+arg_8]
0x180006ad6  add     rsp, 30h
0x180006ada  pop     rdi
0x180006adb  retn
0x180006adc  xor     edi, edi
0x180006ade  lea     rbx, [rcx+40h]
0x180006ae2  cmp     [rbx], rdi
0x180006ae5  jnz     short loc_180006B0E
0x180006ae7  mov     [rsp+38h+ppv], rbx; ppv
0x180006aec  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180006af3  xor     edx, edx; pUnkOuter
0x180006af5  mov     r8d, 1; dwClsContext
0x180006afb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180006b02  call    cs:__imp_CoCreateInstance
0x180006b08  mov     edi, eax
0x180006b0a  test    eax, eax
0x180006b0c  js      short loc_180006B23
0x180006b0e  mov     rcx, [rbx]
0x180006b11  mov     [rsi], rcx
0x180006b14  mov     rcx, [rbx]
0x180006b17  mov     rdx, [rcx]
0x180006b1a  mov     rax, [rdx+8]
0x180006b1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b23  mov     eax, edi
0x180006b25  mov     rbx, [rsp+38h+arg_0]
0x180006b2a  mov     rsi, [rsp+38h+arg_8]
0x180006b2f  add     rsp, 30h
0x180006b33  pop     rdi
0x180006b34  retn
```
