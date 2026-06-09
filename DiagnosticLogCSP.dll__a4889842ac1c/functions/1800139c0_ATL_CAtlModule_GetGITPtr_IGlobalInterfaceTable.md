# ATL::CAtlModule::GetGITPtr(IGlobalInterfaceTable * *)

- ea: `0x1800139c0`
- end: `0x180013a35`
- name: `?GetGITPtr@CAtlModule@ATL@@UEAAJPEAPEAUIGlobalInterfaceTable@@@Z`
- size: `117`
- prototype: `__int64 __fastcall(ATL::CAtlModule *__hidden this, struct IGlobalInterfaceTable **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x1800139c0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013a02`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180013a02`

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
0x1800139c0  mov     [rsp+arg_0], rbx
0x1800139c5  mov     [rsp+arg_8], rsi
0x1800139ca  push    rdi
0x1800139cb  sub     rsp, 30h
0x1800139cf  mov     rsi, rdx
0x1800139d2  test    rdx, rdx
0x1800139d5  jnz     short loc_1800139DE
0x1800139d7  mov     eax, 80004003h
0x1800139dc  jmp     short loc_180013A25
0x1800139de  xor     edi, edi
0x1800139e0  lea     rbx, [rcx+40h]
0x1800139e4  cmp     [rbx], rdi
0x1800139e7  jnz     short loc_180013A0E
0x1800139e9  mov     [rsp+38h+ppv], rbx; ppv
0x1800139ee  lea     r9, _GUID_00000146_0000_0000_c000_000000000046; riid
0x1800139f5  xor     edx, edx; pUnkOuter
0x1800139f7  lea     r8d, [rdi+1]; dwClsContext
0x1800139fb  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x180013a02  call    cs:__imp_CoCreateInstance
0x180013a08  mov     edi, eax
0x180013a0a  test    eax, eax
0x180013a0c  js      short loc_180013A23
0x180013a0e  mov     rcx, [rbx]
0x180013a11  mov     [rsi], rcx
0x180013a14  mov     rcx, [rbx]
0x180013a17  mov     rdx, [rcx]
0x180013a1a  mov     rax, [rdx+8]
0x180013a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a23  mov     eax, edi
0x180013a25  mov     rbx, [rsp+38h+arg_0]
0x180013a2a  mov     rsi, [rsp+38h+arg_8]
0x180013a2f  add     rsp, 30h
0x180013a33  pop     rdi
0x180013a34  retn
```
