# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x180003ef0`
- end: `0x180003f65`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003ef0`
- `0x18000d010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x180003f32`
- `ole32!CoCreateInstance` at `0x180003f32`

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
0x180003ef0  mov     [rsp+arg_0], rbx
0x180003ef5  mov     [rsp+arg_8], rsi
0x180003efa  push    rdi
0x180003efb  sub     rsp, 30h
0x180003eff  mov     rsi, rdx
0x180003f02  test    rdx, rdx
0x180003f05  jnz     short loc_180003F0E
0x180003f07  mov     eax, 80004003h
0x180003f0c  jmp     short loc_180003F55
0x180003f0e  xor     edi, edi
0x180003f10  lea     rbx, [rcx+40h]
0x180003f14  cmp     [rbx], rdi
0x180003f17  jnz     short loc_180003F3E
0x180003f19  mov     [rsp+38h+ppv], rbx; ppv
0x180003f1e  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x180003f25  xor     edx, edx; pUnkOuter
0x180003f27  lea     r8d, [rdi+1]; dwClsContext
0x180003f2b  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180003f32  call    cs:__imp_CoCreateInstance
0x180003f38  mov     edi, eax
0x180003f3a  test    eax, eax
0x180003f3c  js      short loc_180003F53
0x180003f3e  mov     rcx, [rbx]
0x180003f41  mov     [rsi], rcx
0x180003f44  mov     rcx, [rbx]
0x180003f47  mov     rdx, [rcx]
0x180003f4a  mov     rax, [rdx+8]
0x180003f4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f53  mov     eax, edi
0x180003f55  mov     rbx, [rsp+38h+arg_0]
0x180003f5a  mov     rsi, [rsp+38h+arg_8]
0x180003f5f  add     rsp, 30h
0x180003f63  pop     rdi
0x180003f64  retn
```
