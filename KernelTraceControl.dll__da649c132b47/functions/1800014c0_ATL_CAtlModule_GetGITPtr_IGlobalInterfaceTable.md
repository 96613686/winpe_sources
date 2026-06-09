# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x1800014c0`
- end: `0x180001536`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `118`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800014c0`
- `0x180027910`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180001502`
- `ole32!CoCreateInstance` at `0x180001502`

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
0x1800014c0  mov     [rsp+arg_0], rbx
0x1800014c5  mov     [rsp+arg_8], rsi
0x1800014ca  push    rdi
0x1800014cb  sub     rsp, 30h
0x1800014cf  mov     rsi, rdx
0x1800014d2  test    rdx, rdx
0x1800014d5  jnz     short loc_1800014DE
0x1800014d7  mov     eax, 80004003h
0x1800014dc  jmp     short loc_180001526
0x1800014de  xor     edi, edi
0x1800014e0  lea     rbx, [rcx+40h]
0x1800014e4  cmp     [rbx], rdi
0x1800014e7  jnz     short loc_18000150E
0x1800014e9  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1800014f0  mov     [rsp+38h+ppv], rbx; ppv
0x1800014f5  xor     edx, edx; pUnkOuter
0x1800014f7  lea     r8d, [rdi+1]; dwClsContext
0x1800014fb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180001502  call    cs:__imp_CoCreateInstance
0x180001508  mov     edi, eax
0x18000150a  test    eax, eax
0x18000150c  js      short loc_180001524
0x18000150e  mov     rcx, [rbx]
0x180001511  mov     [rsi], rcx
0x180001514  mov     rcx, [rbx]
0x180001517  mov     rdx, [rcx]
0x18000151a  mov     rax, [rdx+8]
0x18000151e  call    cs:__guard_dispatch_icall_fptr
0x180001524  mov     eax, edi
0x180001526  mov     rbx, [rsp+38h+arg_0]
0x18000152b  mov     rsi, [rsp+38h+arg_8]
0x180001530  add     rsp, 30h
0x180001534  pop     rdi
0x180001535  retn
```
