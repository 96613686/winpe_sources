# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x1800022b0`
- end: `0x180002325`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800022b0`
- `0x18000a010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x1800022f2`
- `ole32!CoCreateInstance` at `0x1800022f2`

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
0x1800022b0  mov     [rsp+arg_0], rbx
0x1800022b5  mov     [rsp+arg_8], rsi
0x1800022ba  push    rdi
0x1800022bb  sub     rsp, 30h
0x1800022bf  mov     rsi, rdx
0x1800022c2  test    rdx, rdx
0x1800022c5  jnz     short loc_1800022CE
0x1800022c7  mov     eax, 80004003h
0x1800022cc  jmp     short loc_180002315
0x1800022ce  xor     edi, edi
0x1800022d0  lea     rbx, [rcx+40h]
0x1800022d4  cmp     [rbx], rdi
0x1800022d7  jnz     short loc_1800022FE
0x1800022d9  mov     [rsp+38h+ppv], rbx; ppv
0x1800022de  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1800022e5  xor     edx, edx; pUnkOuter
0x1800022e7  lea     r8d, [rdi+1]; dwClsContext
0x1800022eb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x1800022f2  call    cs:__imp_CoCreateInstance
0x1800022f8  mov     edi, eax
0x1800022fa  test    eax, eax
0x1800022fc  js      short loc_180002313
0x1800022fe  mov     rcx, [rbx]
0x180002301  mov     [rsi], rcx
0x180002304  mov     rcx, [rbx]
0x180002307  mov     rdx, [rcx]
0x18000230a  mov     rax, [rdx+8]
0x18000230e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002313  mov     eax, edi
0x180002315  mov     rbx, [rsp+38h+arg_0]
0x18000231a  mov     rsi, [rsp+38h+arg_8]
0x18000231f  add     rsp, 30h
0x180002323  pop     rdi
0x180002324  retn
```
